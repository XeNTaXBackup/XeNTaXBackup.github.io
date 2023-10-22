## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-03-06T21:49:54+00:00
- Post Title: Old code: DiceWars mapping engine in Turbo Pascal

Hi, 

Here's a personal blast from the past.   

[https://www.youtube.com/watch?v=_l9O_0X ... e=youtu.be](https://www.youtube.com/watch?v=_l9O_0XzA3s&feature=youtu.be)

Here's the source and binaries and stuff: 

 MAPSC.ZIP
(11.55 KiB) Downloaded 26 times



```
 It uses RAW Picture Processing (TST-Files: Totally Sane Textures)
 The VESA Unit Was Coded By

 MEM : Total  MAP : 160 x 160      = 25600  bytes
       Visual Map : 13  x 12       = 156    bytes
       TSTPictures: 32  x 32 x 256 = 262144 bytes
}

Program Map_Scroller;

Uses Vesaun, Crt, Dos;

Const
  TotalPics = 3;        {+1 , e.g.: 0 is one too!}
  MapSize   = 25599;    {as above                }
  MaxMapX   = 159;      {as above                }
  MaxMapY   = 159;      {as above                }
Type
  MAPPICM = array[0..1023] of byte;
  MapP    = ^MAPPICM;
  VMapM   = array[0..156] of byte;
  TMapM   = array[0..MapSize] of byte;
Var
  P       : array[0..TotalPics] of MaPP;
  Pall    : array[0..255, 0..2] of word;
  VMap    : ^VmapM;
  TMap    : ^TMapM;
  MX, MY  : byte;
  PalFile : text;
  ByteCnt : longint;
  QuitLoad: Boolean;
  i, s    : word;
  Ch      : char;

Procedure LoadPal(PalFileName: string);

var I : word;
    D : char;
Begin
  Writeln('Loading Palette : ', PalFileName);

  assign(PalFile, PalFileNAme);
  {$I-}
  reset(PalFile);
  {$I+}
  If Ioresult<>0 then QuitLoad:=true;
  If QuitLoad then Exit;
  for i:=0 to 18 do read(palfile, d);

  For i:=0 to 255 do Begin
    read(PalFile, Pall[i, 0]);
    read(PalFile, Pall[i, 1]);
    read(PalFile, Pall[i, 2]);
  end;
  Close(PalFile);
  GotoXY(60, WhereY-1); writeln(I*3+3);
  ByteCnt:=Bytecnt+(I*3+3);
end;

Procedure SetPalette;

var i: word;

Begin
  for i:=0 to 255 do SetColor(i, Pall[i, 0], Pall[i, 1], Pall[i, 2]);
end;

Procedure LoadTSTMEM(FileName: string; K: word);

var i,j   : word;
    F     : File OF BYTE;
    D     : BYTE;
BEGIN
  writeln('Loading TST     : ',  FileName);
  GetMEm(P[k], SizeOF(MapPIcm));
  Assign(F, FileName);
  {$I-}
  reset(F);
  {$I+}
  If Ioresult<>0 then QuitLoad:=true;
  If QuitLoad then Exit;
  For j:=0 to 1023 do begin
    read(F, P[k]^[j]);
  END;
  I:=FileSize(F);
  Close(f);
  GotoXY(60, WhereY-1); writeln(I);
  ByteCnt:=Bytecnt+i;
END;

Procedure PutTST(P: word; x, y: word; Le:byte); Assembler;

ASM
  cli                     {Clear Interupts                }
  Mov SI, $0000           {Wipe SI                        }
  Mov Cl, Le              {Store X-width of TST           }
  Mov Ch, Le              {Store Y-width of TST           }
  DEC Word Ptr X          {IMPORTANT for CORRECT LOOPING! }
{  inc ch}
@GoOn:
  cmp Cl, $00             {Compare X-count With 0         }
  je @InCP                {If Equal Jump to InCp          }
  dec Cl                  {If not Decrease X-count        }
  inc Word Ptr X          {Increase X                     }
  inc SI                  {Increase SI                    }
  Mov  AX, Ymax           {Store MaxY                     }
  Mul  pp                 {Multiply                       }
  Add  Ax, Y              {Ad Y to Ax                     }
  Mov  Bx, AX             {Store New Ax into BX           }
  Mov  Ax, Xmax           {Store MaxX now into Ax         }
  Mul  Bx                 {Multiply AX with BX            }
  Add  Ax, X              {Ad X to Ax                     }
  Adc  Dx, 0              {                               }
  Mov  Di, Ax             {Store Ax into DI               }
  Cmp  Dl, Current_bank   {Compare DI with Current Bank   }
  Je   @skip              {If equal skip setting it again!}
  Mov  Current_bank, Dl   {Not equal so set the new Bank  }
  Mov  Ax, 4F05h          {                               }
  Xor  Bx, Bx             {Wipe BX                        }
  Int  10h                {Call Interrupt 10              }
  @Skip:                  {                               }
  Mov  ES, Word Ptr P     {Store Segment of P into ES     }
  Mov  Al, ES:[Si]        {Store the color at segES:ofsSI }
  Mov  ES, SegA000        {Set ES to video Mem            }
  Mov  Es:[Di], Al        {Store the Color at A000:ofsDI  }
  jmp @GoOn               {And Return to go on            }
  @InCP:                  {                               }
  cmp Ch, $00             {Compare Y-count with 0         }
  je @exit                {If equal->TST drawn-->exit     }
  dec Ch                  {Else decrease Y-Count          }
  inc Word Ptr Y          {Increase Y                     }
  mov Cl, le              {Store X-width again at Cl      }
@ResetX:
  dec Word ptr X          {Decrease X,                    }
  dec Cl                  {while counting X-count,        }
  cmp Cl, $00             {until X-count is 0:            }
  jne @ResetX             {Now X is again at it's startpos}
  mov cl, le              {Store X-width to Cl to         }
  jmp @GoOn               {GoOn drawing!                  }
@Exit:                    {                               }
  sti                     {Set Interrupts Back            }
end;

Procedure LoadTESTMap(FileName: string);

Var
    k   : word;
    F   : FIle of Byte;
Begin
  Writeln('Loading Map     : ', FileName);
  Randomize;
  k:=0;
  GetMem(TMap, SizeOf(TMapM));
  Assign(F, FileName);
  {$I-}
  reset(F);
  {$I+}
  If Ioresult<>0 then QuitLoad:=true;
  If QuitLoad then Exit;
  Repeat
    read(F, Tmap^[k]);
    inc(k);
  until k=MapSize+1;
  K:=FileSize(F);
  Close(f);
  GotoXY(60, WhereY-1); writeln(K);
  ByteCnt:=Bytecnt+k;
end;

Procedure GETVisualMap(MX, MY: byte);

Var k, l   : word;

BEGIN
  k:=0; l:=0;
  Repeat
    Vmap^[l*13+k]:=Tmap^[(MX+k)+((my+l)*160)];
    inc(k);
    if k=13 then Begin K:=0; inc(l); end;
  until l=12;
end;

Procedure PUTVisualMap;

Var i, j     : byte;
    Pad, k   : word;

BEGIN
  k:=0;
  For j:=0 to 11 do begin
    k:=j*13;
    for i:=0 to 12 do begin
      Pad:=seg(P[Vmap^[k+i]]^)+ofs(p[Vmap^[K+i]]^);
      PutTST(Pad, 32+i*32, 64+j*32, 32);
    end;
  end;
END;

Procedure MemInit;

Begin
  QUitLoad:=false;
  GetMem(Vmap, SizeOf(VmapM));
END;

Procedure FreeAllMem;

var i: word;

Begin
Write('Freeing Memory...');
Freemem(Vmap , SizeOf(VmapM));
Freemem(Tmap , SizeOf(TmapM));
Writeln('Done.');
writeln('END OF SADCOM TEST');
End;

Procedure StuffLoad;

var B: byte;

Begin
writeln('-* Test-Program 1 for WarDice SadCom Ltd M.W.Zuurman *-');
writeln;
writeln('Action            Filename                                 Bytes');
writeln('------------------------------------------------------------------');
ByteCnt:=0;
LoadTSTMEM('grass.tst', 0);
If QuitLoad then Exit;
LoadTSTMEM('water.tst', 1);
If QuitLoad then Exit;
LoadTSTMEM('mount.tst', 2);
If QuitLoad then Exit;
LoadTSTMEM('none.tst', 3);
If QuitLoad then Exit;
LoadTESTMap('testmap.tst');
If QuitLoad then Exit;
LoadPal('testp.pal');
If QuitLoad then Exit;
writeln('------------------------------------------------------------------');
Gotoxy(45, WhereY); writeln('Total Amount : ', ByteCnt);

Writeln('-- Press a key to Start MapScroller --');
Writeln('   Keys: Arrows : Scroll Map ');
Writeln('         X      : Exit       ');

Readkey;
end;

Procedure DrawRec;

Begin
  HLine(30, 62, 450, 215);
  HLine(30, 450, 450, 215);
  VLine(30, 62, 450, 215);
  VLine(450, 62, 450,215);{}
end;

Procedure MapToVisual;

Begin
  GETVisualMap(MX, MY);
  PUTVisualMap;
end;

(* MAIN PROGRAM *)

BEGIN
  ClrScr;
  xmax:=640; ymax:=480;
  MemInit;
  StuffLoad;
  If QuitLoad then
    Begin Writeln('One or More Files Missing...Terminating'); Exit; End;
  MX:=0; MY:=0;
  SetMode(_640x480x256);{}
  SetPalette;
  DrawRec;
  MapToVisual;
  Repeat
  if keypressed then begin
    ch:=readkey;
    case ch of
      #72 : if my>0 then begin
              Dec(MY); MapToVisual; end;
      #80 : if my+11<MaxMapY then begin
              inc(MY); MapToVisual; end;
      #75 : if mx>0 then begin
              Dec(Mx); MapToVisual; end;
      #77 : if mx+12<MaxMapX then begin
              inc(Mx); MapToVisual; end;
    end;
  end;
  until ch='x';
  SetMode(_80x25t);
  FreeAllMem;
END.

```
