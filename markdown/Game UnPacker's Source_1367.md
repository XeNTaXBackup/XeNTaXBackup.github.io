## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:11:03+00:00
- Post Title: Game UnPacker's Source

Greetings to all... I here have thought to share with you source codes on Delphi I think will be useful... Can also you share?Originaled with extractor and cheater .Let's write MultiEx Commander 2 in Delphi   

3DMark 2003-2004 DAT UnPacker

```
{$APPTYPE CONSOLE}
Uses SysUtils;
Var
    Fi, Fl: File;
    P: Array Of Byte;
    M: Array Of Byte;
    I, HS, FSize, FOffs, TF: LongInt;
    S, St, Sd, DPath: String;
Begin
WriteLn('T#i$ PR0GR@M bY -=CHE@TER=-'); 
WriteLn('HTTP://CTPAX-CHEATER.narod.RU');
  If ParamCount<>1 Then
    Begin
      WriteLn('Usage: M0304Unp filename.dat');
      Exit;
    End;
  If FileExists(ParamStr(1))=False Then
    Begin
      WriteLn('File not found.');
      Exit;
    End;
  DPath:=ParamStr(1);
  Delete(DPath, Length(DPath)-3, 4);
  If DirectoryExists(DPath)=False Then CreateDir(DPath);
  AssignFile(Fi, ParamStr(1));
  Reset(Fi, 1);
  BlockRead(Fi, I, 4);
  BlockRead(Fi, HS, 4);
  WriteLn('Header Size = ', HS);
  SetLength(P, HS);
  BlockRead(Fi, P[0], HS);
  For I:=0 To HS-1 Do P[I]:=P[I] Xor $AD;
  I:=0;
  TF:=0;
  While I<HS Do
    Begin
      Move(P[I], FSize, 4);
      I:=I+4;
      SetLength(S, FSize);
      Move(P[I], S[1], FSize);
      I:=I+FSize;
      Move(P[I], FSize, 4);
      I:=I+4;
      Move(P[I], FOffs, 4);
      I:=I+4+4; { +unused long ??? }
      WriteLn(DPath+'\'+S);
      SetLength(M, FSize);
      Seek(Fi, FOffs);
      BlockRead(Fi, M[0], FSize);
      For FOffs:=0 To FSize-1 Do M[FOffs]:=M[FOffs] Xor $AD;
      St:=S;
      While (Length(St)>0) And (St[Length(St)]<>'\') Do
        Delete(St, Length(St), 1);
      If Length(St)>0 Then
        Begin
          Sd:=DPath;
          While Length(St)<>0 Do
            Begin
              Sd:=Sd+'\'+Copy(St, 1, Pos('\',St));
              Delete(Sd, Length(Sd), 1);
              If DirectoryExists(Sd)=False Then CreateDir(Sd);
              St:=Copy(St, Pos('\', St)+1, Length(St));
            End;
        End;
       AssignFile(Fl, DPath+'\'+S);
       ReWrite(Fl, 1);
       BlockWrite(Fl, M[0], FSize);
       CloseFile(Fl);
       TF:=TF+1;
    End;
  SetLength(M, 0);
  SetLength(S, 0);
  SetLength(P, 0);
  CloseFile(Fi);
  WriteLn('Total files: ', TF);
  WriteLn('Done.');
End.
```
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:12:46+00:00
- Post Title: Game UnPacker's Source

3DMark 2005 DAT UnPacker

```
{$APPTYPE CONSOLE}
Uses SysUtils;
Type
     FStruct = Record
                 FName: String;
                 FSize: LongInt;
               End;
Var
    Fi, Fl: File;
    J, I, K, FSz: LongInt;
    B, N: Byte;
    S, St, Sd, DPath: String;
    M: Array Of Byte;
    FList: Array Of FStruct;
Function Un05(BT: Byte): Byte; Assembler;
Asm
  mov al, BT
  xor al, 0ADh
  rol al, 4
End;
Begin
WriteLn('T#i$ PR0GR@M bY -=CHE@TER=-');
WriteLn('HTTP://CTPAX-CHEATER.narod.RU');
  If ParamCount<>1 Then
    Begin
      WriteLn('Usage: M05Unp filename.dat');
      Exit;
    End;
  If FileExists(ParamStr(1))=False Then
    Begin
      WriteLn('File not found.');
      Exit;
    End;
  DPath:=ParamStr(1);
  Delete(DPath, Length(DPath)-3, 4);
  If DirectoryExists(DPath)=False Then CreateDir(DPath);
  AssignFile(Fi, ParamStr(1));
  Reset(Fi, 1);
  Seek(Fi, 9);
  {!!!}
  If FileSize(Fi)>2000000 Then Seek(Fi, 10); { "3DMark05.dat" shifted on byte }
  FSz:=0;
  J:=0;
  Repeat
    BlockRead(Fi, B, 1);
    B:=Un05(B);
    SetLength(FList, J+1);
    FList[J].FName:='';
    For N:=1 To B Do
      Begin
        BlockRead(Fi, B, 1);
        B:=Un05(B);
        If Chr(B)='/' Then B:=Ord('\');
        FList[J].FName:=FList[J].FName+Chr(B);
      End;
    SetLength(St, 4);
    BlockRead(Fi, St[1], 4);
    For N:=1 To 4 Do St[N]:=Chr(Un05(Ord(St[N])));
    Move(St[1], FList[J].FSize, 4);
    FSz:=FSz+FList[J].FSize;
    J:=J+1;
  Until FSz+FilePos(Fi)>=FileSize(Fi);
  WriteLn('Header Size = ', FilePos(Fi));
  K:=J-1;
  For J:=0 To K Do
    Begin
      S:=FList[J].FName;
      WriteLn(DPath+'\'+S);
      St:=S;
      While (Length(St)>0) And (St[Length(St)]<>'\') Do
        Delete(St, Length(St), 1);
      If Length(St)>0 Then
        Begin
          Sd:=DPath;
          While Length(St)<>0 Do
            Begin
              Sd:=Sd+'\'+Copy(St, 1, Pos('\',St));
              Delete(Sd, Length(Sd), 1);
              If DirectoryExists(Sd)=False Then CreateDir(Sd);
              St:=Copy(St, Pos('\', St)+1, Length(St));
            End;
        End;
      SetLength(M, FList[J].FSize);
      BlockRead(Fi, M[0], FList[J].FSize);
      For I:=0 To FList[J].FSize-1 Do
        M[I]:=Un05(M[I]);
      AssignFile(Fl, DPath+'\'+S);
      ReWrite(Fl, 1);
      BlockWrite(Fl, M[0], FList[J].FSize);
      CloseFile(Fl);
  End;
  SetLength(M, 0);
  SetLength(FList, 0);
  CloseFile(Fi);
  WriteLn('Total files: ', K+1);
  WriteLn('Done.');
End.

```
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:15:18+00:00
- Post Title: Game UnPacker's Source

Grand theft Auto San Andreas Audio Decoder
( Convert audio in OGG Vorbis Format )

```
{$APPTYPE CONSOLE}
Uses SysUtils;

Const
      M: Array[0..15] Of Byte =
      ($EA, $3A, $C4, $A1, $9A, $A8, $14, $F3, $48, $B0, $D7, $23, $9D, $E8, $FF, $F1);

Function VorbisParser(Var vFl: File): LongInt;
Var
    B, I, T, Z: Byte;
             N: LongInt;
             S: String;
Begin
  Repeat
    SetLength(S, 4);
    BlockRead(VFl, S[1], 4);
    If S<>'OggS' Then
      Begin
        Seek(VFl, FilePos(vFl) - 4);
        Break;
      End;
    Seek(vFl, FilePos(vFl) + 1);
    BlockRead(vFl, B, 1);
    Seek(vFl, FilePos(vFl) + 20);
    BlockRead(vFl, T, 1);
    N:=0;
    For I:=1 To T Do
      Begin
        BlockRead(vFl, Z, 1);
        N:=N + Z;
      End;
    Seek(vFl, FilePos(vFl) + N);
  Until EOF(vFl);
  VorbisParser:=FilePos(vFl);
End;

Var
    Finp, Fl: File;
    W, I, Sz: LongInt;
           P: Array Of Byte;
           S: String;
          Cr: Cardinal;

Begin
  WriteLn('Grand Theft Auto San Andreas Audio Decoder);
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  If ParamCount<>1 Then
    Begin
      WriteLn('Usage: gtasamc filename');
      Exit;
    End;
  AssignFile(Finp, ParamStr(1));
  {$I-}
  Reset(Finp, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('Can''t open input file!');
      Exit;
    End;
  AssignFile(Fl, ParamStr(1)+'.tmp');
  {$I-}
  ReWrite(Fl, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      Close(Finp);
      WriteLn('Can''t open output file!');
      Exit;
    End;
  WriteLn('>>> Decoding...');
  Cr:=$1F30;
  SetLength(P, Cr);
  For I:=0 To Cr - 1 Do P[I]:=0;
  BlockWrite(Fl, P[0], Cr);
  Seek(Finp, Cr);
  Cr:=$1000;
  SetLength(P, Cr);
  While NOT EOF(Finp) Do
    Begin
      W:=Cr;
      BlockRead(Finp, P[0], W, W);
      For I:=0 To W-1 Do
        P[I]:=P[I] Xor M[I Mod 16];
      BlockWrite(Fl, P[0], W);
    End;
  SetLength(P, 0);
  CloseFile(Fl);
  WriteLn('>>> Decoding Complited...');
  CloseFile(Finp);
  WriteLn('>>> Extracting...');
  AssignFile(Finp, ParamStr(1)+'.tmp');
  WriteLn('>>> Write Temp File...');
  Reset(Finp, 1);
  Seek(Finp, $1F40);
  I:=0;
  CreateDir(ParamStr(1)+'_OGGS');
  WriteLn('>>> Create OGG Dir...');
  Repeat
    BlockRead(Finp, Cr, 4);
    BlockRead(Finp, W, 4);
    If Cr = $FFFFFFFF Then Continue;
    Seek(Finp, FilePos(Finp) + 60);
    I:=I+1;
    W:=FilePos(Finp);
    Sz:=VorbisParser(Finp);
    Seek(Finp, W);
    Sz:=Sz - W;
    S:=IntToStr(I);
    While Length(S)<3 Do S:='0'+S;
    WriteLn('Convert OGG File : '+S+'.ogg');
    S:=S+'.ogg';
    AssignFile(Fl, ParamStr(1)+'_OGGS\'+S);
    ReWrite(Fl, 1);
    SetLength(P, Sz);
    BlockRead(Finp, P[0], Sz);
    BlockWrite(Fl, P[0], Sz);
    CloseFile(Fl);
  Until EOF(Finp);
  SetLength(P, 0);
  CloseFile(Finp);
  DeleteFile(ParamStr(1)+'.tmp');
  WriteLn('>>> Delete Temp File Complited...');
  WriteLn('>>> Extracting Complited...');
  WriteLn('Total .OGG files: ', I);
End.

```
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:17:50+00:00
- Post Title: Game UnPacker's Source

Grand Theft Auto Vice City ADF2MP3

```
{$APPTYPE CONSOLE} 
Uses SysUtils;

Var Finp, Fl: File;
           P: Pointer;
           B: Byte;
           W, I: Word;
Begin
  WriteLn('Grand Theft Auto Vice City ADF2MP3');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  If ParamCount<>2 Then
    Begin
      WriteLn('Usage: gta3vcmc filename.adf filename.mp3');
      WriteLn;
      Exit;
    End;
  Assign(Finp, ParamStr(1));
  {$I-}
  Reset(Finp, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('Can''t open input file!');
      WriteLn;
      Exit;
    End;
  Assign(Fl, ParamStr(2));
  {$I-}
  ReWrite(Fl, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      Close(Finp);
      WriteLn('Can''t open output file!');
      WriteLn;
      Exit;
    End;
  GetMem(P, $FF00);
  Write('Please wait, working... ');
  While NOT EOF(Finp) Do
    Begin
      W:=$FF00;
      BlockRead(Finp, P^, W, W);
      For I:=0 To W-1 Do
        Mem[Seg(P^):Ofs(P^)+I]:=Mem[Seg(P^):Ofs(P^)+I] Xor 34;
      BlockWrite(Fl, P^, W);
    End;
  FreeMem(P, $FF00);
  Close(Fl);
  Close(Finp);
  WriteLn('done');
End.
```
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:19:52+00:00
- Post Title: Game UnPacker's Source

Silent Hill 2 ASF UnPacker

```

{$APPTYPE CONSOLE}

Uses SysUtils;

Var Finp, Fl: File;
           S: String;
 I, TF, FOfs, FSz: LongInt;
 FlOfs, NameOfs: LongInt;
          Si: Byte;
           P: Pointer;
Begin
  WriteLn('Silent Hill 2 ASF UnPacker');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  If ParamCount<>1 Then
    Begin
      WriteLn('Usage: AFS_UNP filename.afs');
      Exit;
    End;
  If FileExists(ParamStr(1))=False Then
    Begin
      WriteLn('File not found!');
      Exit;
    End;
  AssignFile(Finp, ParamStr(1));
  Reset(Finp, 1);
  SetLength(S, 4);
  BlockRead(Finp, S[1], 4);
  If S<>'AFS'#0 Then
    Begin
      WriteLn('This is not a AFS file.');
      Exit;
    End;
  BlockRead(Finp, TF, 4);
  BlockRead(Finp, FlOfs, 4);
  Seek(Finp, FlOfs-8);
  BlockRead(Finp, NameOfs, 4);
  Seek(Finp, 8);
  FlOfs:=FilePos(Finp);
  For I:=1 To TF Do
    Begin
      SetLength(S, 48);
      Seek(Finp, NameOfs);
      BlockRead(Finp, S[1], 48);
      NameOfs:=FilePos(Finp);
      Si:=1;
      While S[Si]<>#0 Do Si:=Si+1;
      S:=Copy(S, 1, Si-1);
      Write(S);
      Seek(Finp, FlOfs);
      BlockRead(Finp, FOfs, 4);
      BlockRead(Finp, FSz, 4);
      FlOfs:=FilePos(Finp);
      AssignFile(Fl, S);
      ReWrite(Fl, 1);
      GetMem(P, FSz);
      Seek(Finp, FOfs);
      BlockRead(Finp, P^, FSz);
      BlockWrite(Fl, P^, FSz);
      FreeMem(P, FSz);
      CloseFile(Fl);
      WriteLn(' - done');
    End;
  CloseFile(Finp);
  WriteLn;
  WriteLn('All done.');
End.
```
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:22:07+00:00
- Post Title: Game UnPacker's Source

Syberia 2 SYB UnPacker

```

{$APPTYPE CONSOLE}

Uses SysUtils;
Var
    FPos1, FPos2, Sz, FSz, TF: LongInt;
                        Fl, F: File;
                            P: Pointer;
                            S: String;
                            B: Byte;
                            
Begin
  WriteLn('Syberia 2 SYB UnPacker');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  If ParamCount<>1 Then
    Begin
      WriteLn('Usage: syb2unp filename.syb');
      Exit;
    End;
  If FileExists(ParamStr(1))=False Then
    Begin
      WriteLn('Input file not found!');
      Exit;
    End;
  AssignFile(Fl, ParamStr(1));
  Reset(Fl, 1);
  SetLength(S, 4);
  BlockRead(Fl, S[1], 4);
  If S<>'VXBG' Then
    Begin
      CloseFile(Fl);    
      WriteLn('This is not a .SYB archive!');
      Exit;
    End;
  BlockRead(Fl, Sz, 4); { Header size }
  Sz:=Sz+8; { + size of 'VXBG' and LONG value }
  FPos2:=Sz;
  TF:=0;
  While FilePos(Fl)<Sz Do
    Begin
      S:='';
      Repeat
        BlockRead(Fl, B, 1);
        If B<>0 Then S:=S+Chr(B);
      Until B=0;
      BlockRead(Fl, FSz, 4);
      FPos1:=FilePos(Fl);
      Seek(Fl, FPos2);
      GetMem(P, FSz);
      BlockRead(Fl, P^, FSz);
      AssignFile(F, S);
      ReWrite(F, 1);
      BlockWrite(F, P^, FSz);
      CloseFile(F);
      FreeMem(P, FSz);
      FPos2:=FilePos(Fl);
      Seek(Fl, FPos1);
      TF:=TF+1;
      WriteLn(S);
    End;
  WriteLn;
  WriteLn('Total Files: ', TF);
  CloseFile(Fl);
End.
```
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:25:03+00:00
- Post Title: Game UnPacker's Source

Who has what source codes on Delphi, Basic, C ++ write here
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:35:59+00:00
- Post Title: Game UnPacker's Source

Age of Mythology BAR Unit For DELPHI

```

interface

uses Classes, SysUtils, Dialogs;

type
  TBarHeader = record
    Unknown0   : Longword; // Always 0?
    Unknown1   : Longword; // Always 0?
    Unknown2   : Longword;
    NumEntries : Longword;
    EntrySectionSize : Longword;
    TableOffs  : Longword;
    Unknown4   : Longword; // 8?
  end;

  TBarEntryInfo = record
    Offset: Longword;
    Size1: Longword;
    Size2: Longword;
    u0: Longword;
    u1: Longword;
  end;
  PBarEntryInfo = ^TBarEntryInfo;

  TBarEntry = record
    Entry: PBarEntryInfo;
    Name: PChar;
  end;

  TBarFile = class
  private
    FFile: TFileStream;
    FHeader: TBarHeader;
    FEntryOfsTable: array of Longword;
    FEntries: array of TBarEntry;
    FEntryData: Pointer;
    procedure LoadBar(Stream: TStream);
    function GetEntryInfo(Index: Integer): TBarEntryInfo;
    function GetEntryName(Index: Integer): PChar;
    function GetEntryCount: Integer;
  public
    constructor Create(FileName: string);
    destructor Destroy; override;
    function Extract(EntryIndex: Integer; Stream: TStream): Integer;
    property EntryInfo[Index: Integer]: TBarEntryInfo read GetEntryInfo;
    property EntryName[Index: Integer]: PChar read GetEntryName;
    property EntryCount: Integer read GetEntryCount;
  end;

implementation

constructor TBarFile.Create(FileName: string);
begin
  inherited Create;
  FFile := TFileStream.Create(FileName, fmShareDenyNone);
  LoadBar(FFile);
end;

destructor TBarFile.Destroy;
begin
  FEntries := nil;
  FEntryOfsTable := nil;
  FreeMem(FEntryData);
  FFile.Free;
  inherited
end;

procedure TBarFile.LoadBar(Stream: TStream);
var
  i: Integer;
begin
  Stream.Read(FHeader, SizeOf(TBarHeader));

  SetLength(FEntryOfsTable, FHeader.NumEntries);
  SetLength(FEntries, FHeader.NumEntries);
  GetMem(FEntryData, FHeader.EntrySectionSize);

  // Read Entry offset table
  Stream.Position := FHeader.TableOffs;
  Stream.Read(FEntryOfsTable[0], FHeader.NumEntries * 4);

  // Read entries
  Stream.Read(FEntryData^, FHeader.EntrySectionSize);
  for i := 0 to FHeader.NumEntries -1 do
  begin
    Longword(FEntries[i].Entry) := Longword(FEntryData);
    Inc(Longword(FEntries[i].Entry), FEntryOfsTable[i]);

    Pointer(FEntries[i].Name) := FEntryData;
    Inc(FEntries[i].Name, FEntryOfsTable[i] + SizeOf(TBarEntryInfo));
  end;
end;

function TBarFile.Extract(EntryIndex: Integer; Stream: TStream): Integer;
begin
  Result := 0;
  FFile.Position := FEntries[EntryIndex].Entry^.Offset;
  if FEntries[EntryIndex].Entry^.Size1 > 0 then
    Result := Stream.CopyFrom(FFile, FEntries[EntryIndex].Entry^.Size1);
end;

function TBarFile.GetEntryInfo(Index: Integer): TBarEntryInfo;
begin
  try
    Result := TbarEntryInfo(FEntries[Index].Entry^);
  except
    on E: Exception do
      showmessage(IntToStr(Index));
  end;
end;

function TBarFile.GetEntryName(Index: Integer): PChar;
begin
  Result := FEntries[Index].Name;
end;

function TBarFile.GetEntryCount: Integer;
begin
  Result := FHeader.NumEntries;
end;

end.
```
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:38:44+00:00
- Post Title: Game UnPacker's Source

C&C Tiberian Sun INI UnPacker
( Extract only INI files )

```

{$APPTYPE CONSOLE}

uses
  SysUtils;

Var
  Ftibsun,Fdump: File of byte;

Procedure Dumpfile(start:longint;length:longint;outfile:string);
var
  I: longint;
  NumRead, NumWritten: Integer;
  Buf: array[1..2048] of Char;
begin
  WriteLn('Extracting: ' + outfile);
  Assign(Fdump, 'extracted/' + outfile);
  Rewrite(Fdump);
  Seek(Ftibsun,start);

  For i:= 0 to (length div SizeOf(Buf))-1 do begin
    BlockRead(Ftibsun, buf, SizeOf(Buf), NumRead);
    BlockWrite(Fdump, buf, NumRead, Numwritten);
  end;

  BlockRead(Ftibsun, buf, length mod SizeOf(buf), NumRead);
  BlockWrite(Fdump, buf, NumRead, Numwritten);
  Close(Fdump);
end; {Dumpfile}

begin
  Writeln('C&C Tiberian Sun INI UnPacker');
  Writeln('Version 1.0');
  Writeln;
  Writeln('KorNet');
  Writeln;
  if FileExists('tibsun.mix') then begin
    try
      mkdir('extracted');
    except
    end;

      WriteLn('Found ''tibsun.mix''');
      WriteLn('');
      Assign(Ftibsun, 'tibsun.mix');
      reset(Ftibsun);

      Dumpfile(22115880, 280778,'ai.ini');      // Ai.ini Position
      Dumpfile(22396664, 86624, 'art.ini');     // Art.ini Position
      Dumpfile(23578792, 1213,  'battle.ini');  // Battle.ini Position
      Dumpfile(22722648, 17159, 'mapsel.ini');  // Mapsel.ini Position
      Dumpfile(23580008, 42005, 'mission.ini'); // Mission.ini Position
      Dumpfile(22483288, 239357,'rules.ini');   // Rules.ini Position
      Dumpfile(22739817, 13020, 'sound.ini');   // Sound.ini Position
      Dumpfile(22752840, 47550, 'themes.ini');  // Themes.ini Position
      Close(Ftibsun);
      WriteLn('');
      WriteLn('.....Done!');
    end else begin
      WriteLn('Tibsun.Mix not found in this directory.');
    end;
  WriteLn('');
  write('press ENTER to continue');
  ReadLn;
end.
```
## Post #10
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:41:33+00:00
- Post Title: Game UnPacker's Source

Crimsonland PAQ Packer

```

{$APPTYPE CONSOLE}

uses 
  SysUtils;

Var
OutFile, InFile: file of byte;
ByteName: array [1..50] of byte;
ReadByte, CC: byte;
TempInt: integer;
SearchRec: TSearchRec;
Buf: array [0..1048576] of char;

Procedure StrToByteArray(str: string);
var c: byte;
begin
For c:=1 to length(str) do
  begin
  ByteName[c]:=Ord(str[c])
  end;
end;

begin
if (paramstr(1)='') or (paramstr(1)='help') then begin
writeln('Crimsonland PAQ Packer');
writeln('Version 1.0');
writeln;
writeln('KorNet');
writeln;
exit;
end;
assign(OutFile,paramstr(1)+'.paq');
rewrite(OutFile);
StrToByteArray('paq');
Write(OutFile,ByteName[1]);
Write(OutFile,ByteName[2]);
Write(OutFile,ByteName[3]);
ReadByte:=0;
Write(OutFile,ReadByte);
Writeln('Packing...');
If Paramstr(1)='sfx' then
begin
If FindFirst('*.OGG', faAnyFile, SearchRec)=0 then
 repeat
 assign(InFile, SearchRec.name);
 reset(InFile);
 StrToByteArray(SearchRec.name);
 For CC:=1 to length(SearchRec.name) do
 Write(OutFile,ByteName[CC]);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 TempInt:=(FileSize(InFile) MOD 65536) MOD 256;
 Write(OutFile,TempInt);
 TempInt:=(FileSize(InFile) MOD 65536) DIV 256;
 Write(OutFile,TempInt);
 TempInt:=FileSize(InFile) DIV 65536;
 Write(OutFile,TempInt);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 BlockRead(InFile,Buf,FileSize(InFile));
 BlockWrite(OutFile,Buf,FileSize(InFile));
 until FindNext(SearchRec) <> 0;
FindClose(SearchRec);
end;
If Paramstr(1)='crimson' then
begin
If FindFirst('ui\*.*', faAnyFile, SearchRec)=0 then
 repeat
 If SearchRec.name[1]<>'.' THEN BEGIN
 assign(InFile, 'ui\'+SearchRec.name);
 reset(InFile);
 StrToByteArray('ui\'+SearchRec.name);
 For CC:=1 to length('ui\'+SearchRec.name) do
 Write(OutFile,ByteName[CC]);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 TempInt:=(FileSize(InFile) MOD 65536) MOD 256;
 Write(OutFile,TempInt);
 TempInt:=(FileSize(InFile) MOD 65536) DIV 256;
 Write(OutFile,TempInt);
 TempInt:=FileSize(InFile) DIV 65536;
 Write(OutFile,TempInt);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 BlockRead(InFile,Buf,FileSize(InFile));
 BlockWrite(OutFile,Buf,FileSize(InFile));
 END;
 until FindNext(SearchRec) <> 0;
FindClose(SearchRec);
If FindFirst('ter\*.*', faAnyFile, SearchRec)=0 then
 repeat
 If SearchRec.name[1]<>'.' THEN BEGIN
 assign(InFile, 'ter\'+SearchRec.name);
 reset(InFile);
 StrToByteArray('ter\'+SearchRec.name);
 For CC:=1 to length('ter\'+SearchRec.name) do
 Write(OutFile,ByteName[CC]);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 TempInt:=(FileSize(InFile) MOD 65536) MOD 256;
 Write(OutFile,TempInt);
 TempInt:=(FileSize(InFile) MOD 65536) DIV 256;
 Write(OutFile,TempInt);
 TempInt:=FileSize(InFile) DIV 65536;
 Write(OutFile,TempInt);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 BlockRead(InFile,Buf,FileSize(InFile));
 BlockWrite(OutFile,Buf,FileSize(InFile));
 END;
 until FindNext(SearchRec) <> 0;
FindClose(SearchRec);
If FindFirst('load\*.*', faAnyFile, SearchRec)=0 then
 repeat
 If SearchRec.name[1]<>'.' THEN BEGIN
 assign(InFile, 'load\'+SearchRec.name);
 reset(InFile);
 StrToByteArray('load\'+SearchRec.name);
 For CC:=1 to length('load\'+SearchRec.name) do
 Write(OutFile,ByteName[CC]);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 TempInt:=(FileSize(InFile) MOD 65536) MOD 256;
 Write(OutFile,TempInt);
 TempInt:=(FileSize(InFile) MOD 65536) DIV 256;
 Write(OutFile,TempInt);
 TempInt:=FileSize(InFile) DIV 65536;
 Write(OutFile,TempInt);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 BlockRead(InFile,Buf,FileSize(InFile));
 BlockWrite(OutFile,Buf,FileSize(InFile));
 END;
 until FindNext(SearchRec) <> 0;
FindClose(SearchRec);
If FindFirst('game\*.*', faAnyFile, SearchRec)=0 then
 repeat
 If SearchRec.name[1]<>'.' THEN BEGIN
 assign(InFile, 'game\'+SearchRec.name);
 reset(InFile);
 StrToByteArray('game\'+SearchRec.name);
 For CC:=1 to length('game\'+SearchRec.name) do
 Write(OutFile,ByteName[CC]);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 TempInt:=(FileSize(InFile) MOD 65536) MOD 256;
 Write(OutFile,TempInt);
 TempInt:=(FileSize(InFile) MOD 65536) DIV 256;
 Write(OutFile,TempInt);
 TempInt:=FileSize(InFile) DIV 65536;
 Write(OutFile,TempInt);
 ReadByte:=0;
 Write(OutFile,ReadByte);
 BlockRead(InFile,Buf,FileSize(InFile));
 BlockWrite(OutFile,Buf,FileSize(InFile));
 END;
 until FindNext(SearchRec) <> 0;
FindClose(SearchRec);
end;
end.
```
## Post #11
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:43:14+00:00
- Post Title: Game UnPacker's Source

Crimsonland PAQ UnPacker

```

{$APPTYPE CONSOLE}

uses
  SysUtils;

var
InFile, OutFile: File of Byte;
ReadByte, FileCount, ToFile: byte;
Pos, Size, TempSize: LongInt;
Buf: array [0..1048576] of Char;
FileName, TempFileName: String;

begin

if (Paramstr(1)='') or (Paramstr(1)='help') then
begin
writeln('Crimsonland PAQ UnPacker');
writeln('Version 1.0');
writeln;
writeln('KorNet');
writeln;
exit;
end;

If paramstr(2)='' then ToFile:=255 else ToFile:=StrToInt(Paramstr(2));

Assign(InFile,Paramstr(1));
Reset(InFile);

Pos:=4;

Writeln('Unpacking...');
For FileCount:=0 To ToFile do
  begin
  Seek(InFile,Pos);
  ReadByte:=255;
  While ReadByte<>0 do
    begin
    Read(InFile, ReadByte);
    FileName:=FileName+Chr(ReadByte);
    end;
  Seek(InFile, Pos+Length(FileName)+2);
  Read(InFile,ReadByte);
  TempSize:=65536*ReadByte;
  Seek(InFile, Pos+Length(FileName)+1);
  Read(InFile,ReadByte);
  TempSize:=TempSize+256*ReadByte;
  Seek(InFile, Pos+Length(FileName));
  Read(InFile,ReadByte);
  TempSize:=TempSize+ReadByte;
  Size:=TempSize;
  Assign(OutFile,FileName);
  Rewrite(OutFile);
  Seek(InFile,Pos+Length(FileName)+4);
  BlockRead(InFile,Buf,Size);
  BlockWrite(OutFile,Buf,Size);
  Close(OutFile);
  Pos:=Pos+Length(FileName)+4+Size;
  FileName:='';
  end;
end.
 
```
## Post #12
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:44:52+00:00
- Post Title: Game UnPacker's Source

FlatOut BFS unit for DELPHI

```

interface

uses
  Classes, SysUtils, ZLib;

type
  TBfsHeader = record
    Marker: Cardinal;
    Version: Cardinal;
    DataOffset: Cardinal;
    NumEntries: Cardinal;
  end;

  TBfsEntry = packed record
    Info: packed record
      CompMethod: Cardinal; // 4 = raw, 5 = zlib
      DataOffs: Cardinal;
      Size: Cardinal;
      CompSize: Cardinal;
      CheckSum: Integer; // Checksum of compressed data. read as signed int, remove the sign and - 1 and you have the crc32. I.E checksum = -165278610 crc32 = 165278609
      NameLen: Word;
    end;
    Name: packed array of Char;
  end;

  TBfsReader = class
  private
    function GetCount: Integer;
    function GetEntry(Index: Integer): TBfsEntry;
  protected
    FEntries: array of TBfsEntry;
    FHeader: TBfsHeader;
    FStream: TStream;
  public
    constructor Create(FileName: string);
    destructor Destroy; override;
    function Extract(Index: Integer; Dest: TStream): Integer;
    property Entries[Index: Integer]: TBfsEntry read GetEntry;
    property Count: Integer read GetCount;
  end;

implementation

{ TBfsReader }

constructor TBfsReader.Create(FileName: string);
var
  i: Integer;
  Offsets: array of Cardinal;
begin
  inherited Create;
  FStream := TFileStream.Create(FileName, fmOpenRead + fmShareCompat);

  // Read header
  FStream.Read(FHeader, SizeOf(FHeader));

  SetLength(Offsets, FHeader.NumEntries);
  SetLength(FEntries, FHeader.NumEntries);

  // Read File entry offfsets
  FStream.Read(Offsets[0], FHeader.NumEntries * SizeOf(Cardinal));

  // Skip unknown (parent/child/sibbling structure or something?) Two words for
  // each entry
  FStream.Read(i, SizeOf(Cardinal));
  FStream.Seek(i * (SizeOf(Word)*2), soFromCurrent);

  // Read entries
  for i := 0 to FHeader.NumEntries -1 do
  begin
    FStream.Seek(Offsets[i], soFromBeginning);
    FStream.Read(FEntries[i].Info, SizeOf(FEntries[i].Info));
    SetLength(FEntries[i].Name, FEntries[i].Info.NameLen +1);
    FStream.Read(FEntries[i].Name[0], FEntries[i].Info.NameLen);
    FEntries[i].Name[FEntries[i].Info.NameLen] := #0;
  end;
end;

destructor TBfsReader.Destroy;
begin
  FreeAndNil(FStream);
  inherited;
end;

function TBfsReader.Extract(Index: Integer; Dest: TStream): Integer;
var
  DecompStream: TDecompressionStream;
begin
  Result := 0;
  if FEntries[Index].Info.Size = 0 then Exit;
  FStream.Seek(FEntries[Index].Info.DataOffs, soFromBeginning);

  case FEntries[Index].Info.CompMethod of
    // Raw data, just copy
    4: Result := Dest.CopyFrom(FStream, FEntries[Index].Info.Size);
    // ZLib compressed data, decompress
    5: begin
         DecompStream := TDecompressionStream.Create(FStream);
         try
           Result := Dest.CopyFrom(DecompStream, FEntries[Index].Info.Size);
         finally
           FreeAndNil(DecompStream);
         end;
       end;
  else
    raise Exception.Create('Unknown compression format');
  end
end;

function TBfsReader.GetCount: Integer;
begin
  Result := Length(FEntries);
end;

function TBfsReader.GetEntry(Index: Integer): TBfsEntry;
begin
  Result := FEntries[Index];
end;

end.
```
## Post #13
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:47:37+00:00
- Post Title: Game UnPacker's Source

Grand theft Auto Vice City SFX Audio UnPacker
( Support Grand Theft Auto III )

```

{$APPTYPE CONSOLE}

uses
  SysUtils;

var
  raw,sdt,wav :file;
  inf :text;
  sdtstruc:record
    startpos : integer;
    length : integer;
    samplerate : integer;
    unknown1 : integer;
    unknown2 : integer;
  end;
  wavheader:record
    RIFF : array[0..3] of char;
    filesizeminus8 : integer;
    WAVEfmt : array[0..7] of char;
    const16 : integer;
    const1 : word;
    channels : word;
    samplerate : integer;
    byterate : integer;
    bytespersamples : word;
    bitspersample : word;
    data : array[0..3] of char;
    filesizeminus44 : integer;
  end;
  buf:pointer;
  n :integer;
  s :string;
  path :string;

begin
  // insert the path to the GTA3 audio folder if you are not going to run this
  // program from within that folder
  path := '';

  // The SDT file contains information about the audio pieces
  AssignFile(sdt,path+'sfx.SDT');
  Reset(sdt,1);

  // The RAW file contains the audio itself - plain audio without further info
  AssignFile(raw,path+'sfx.RAW');
  Reset(raw,1);

  // This file will be required by the importer - it holds all information
  // that does not fit into the WAV files
  AssignFile(inf,path+'sfx.INF');
  Rewrite(inf);

  // write a few lines of information
   Writeln(inf,'; File generated by GTAVC SFX UnPacker');
  Writeln(inf,'; Each line consists of three parts: WAVfilename, unknown1, unknown2');
  Writeln(inf,';');
  Writeln(inf,'; These parts are separated by tabulator signs. Inserting/removing text may corrupt this file.');
  Writeln(inf,';');
  Writeln(inf,'; I recommend editing this file with notepad.');
  Writeln(inf,';');
  Writeln(inf,'; If a wav file does not loop correctly try using 0 for unknown1 and -1 for unknown2.');
  Writeln(inf,';');
  
  // The main extractor loop
  n := 0;
  while not eof(sdt) do begin

    // load info for a piece of audio
    BlockRead(sdt,sdtstruc,20);

    // construct the WAV file header
    with wavheader do begin
      RIFF := 'RIFF';
      filesizeminus8 := sdtstruc.length+36;
      WAVEfmt := 'WAVEfmt ';
      const16 := 16;
      const1 := 1;
      channels := 1;
      samplerate := sdtstruc.samplerate;
      bitspersample := 16;
      bytespersamples := 2;
      byterate := samplerate*bytespersamples;
      data := 'data';
      filesizeminus44 := sdtstruc.length;
    end;

    // constructs a numbered wav file name
    s := 'sfx'
      +char(n div 10000 mod 10+48)
      +char(n div 1000 mod 10+48)
      +char(n div 100 mod 10+48)
      +char(n div 10 mod 10+48)
      +char(n div 1 mod 10+48)
      +'.wav';

    // create wav file
    AssignFile(wav,path+s);
    Rewrite(wav,1);
    BlockWrite(wav,wavheader,44);

    // read the sound itself from the RAW file and put it into the WAV file
    GetMem(buf,sdtstruc.length);
    Seek(raw,sdtstruc.startpos);
    BlockRead(raw,buf^,sdtstruc.length);
    BlockWrite(wav,buf^,sdtstruc.length);
    FreeMem(buf,sdtstruc.length);

    // close the WAV file
    CloseFile(wav);

    // create a line of info for the INF file
    Writeln(inf,s,#9,sdtstruc.unknown1,#9,sdtstruc.unknown2);

    // increment the file counter
    inc(n)
  end;

  // close all involved files
  CloseFile(inf);
  CloseFile(raw);
  CloseFile(sdt);
end.
```
## Post #14
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:50:24+00:00
- Post Title: Game UnPacker's Source

Grand Theft Auto III IMG unit for DELPHI

```

interface

uses
  Classes, SysUtils, Math, Dialogs;

type
  TDirEntry = packed record
    StartBlock: Longword;
    BlockCount: Longword;
    Name: array[0..23] of Char;
    Index: Integer;
    Delete: Boolean;
  end;
  PDirEntry = ^TDirEntry;

  TGTA3Archive = class
  private
    FFileName: string;
    FDir: TFileStream;
    FImg: TFileStream;
    FEntries: TList;
    function GetEntry(Index: Integer): TDirEntry;
  public
    constructor Create(FileName: string; CreateNew: Boolean = False);
    destructor Destroy; override;
    procedure Extract(Index: Integer; Stream: TStream);
    procedure Add(FileName: string; Stream: TStream);
    procedure Rename(Index: Integer; NewName: string);
    procedure MarkForRemoval(Index: Integer);
    procedure DoRemove;
    procedure Sort(Compare: TListSortCompare);
    function EntryCount: Integer;
    property Entry[Index: Integer]: TDirEntry read GetEntry;
    property ArchiveName: string read FFileName;
  end;


implementation

uses
  SortFunctions;

constructor TIMGunit.Create(FileName: string; CreateNew: Boolean);
var
  Entry: PDirEntry;
  Mode: Word;
begin
  if CreateNew then
    Mode := fmCreate
  else
    Mode := fmOpenReadWrite;

  FFileName := FileName;
  FEntries := TList.Create;
  FImg := TFileStream.Create(FileName, Mode);
  FDir := TFileStream.Create(ChangeFileExt(FileName, '.dir'), Mode);

  FEntries.Capacity := FDir.Size div 32 + 1;
  while FDir.Position + 31 < FDir.Size do
  begin
    New(Entry);
    FDir.Read(Entry^, 32);
    Entry^.Index := FEntries.Count;
    Entry^.Delete := False;
    FEntries.Add(Entry)
  end;
end;

destructor TIMGunit.Destroy;
begin
  FDir.Free;
  FImg.Free;
  while FEntries.Count > 0 do
  begin
    Dispose(FEntries.Items[0]);
    FEntries.Delete(0);
  end;
  FEntries.Free;
end;

function TIMGunit.GetEntry(Index: Integer): TDirEntry;
begin
  Result := TDirEntry(FEntries.Items[Index]^);
end;

function TIMGunit.EntryCount: Integer;
begin
  Result := FEntries.Count;
end;

procedure TIMGunit.Sort(Compare: TListSortCompare);
begin
  FEntries.Sort(Compare);
end;

procedure TIMGunit.Extract(Index: Integer; Stream: TStream);
begin
  with Entry[Index] do
  begin
    FImg.Position := StartBlock * 2048;
    if BlockCount > 0 then
      Stream.CopyFrom(FImg, BlockCount * 2048);
  end;
end;

procedure TIMGunit.Add(FileName: string; Stream: TStream);
var
  Entry: PDirEntry;
  Old: Int64;
begin
  New(Entry);
  Entry^.BlockCount := Stream.Size div 2048;
  if Stream.Size mod 2048 <> 0 then
    Inc(Entry^.BlockCount);

  FImg.Seek(0, soFromEnd);
  FDir.Seek(0, soFromEnd);
  Old := FImg.Size;

  Entry^.StartBlock := FImg.Position div 2048;
  FImg.Size := FImg.Size + Entry^.BlockCount * 2048;
  FImg.Position := Old;
  Entry^.Delete := False;
  Entry^.Index := FDir.Position div 32;
  FillChar(Entry^.Name, 24, 0);
  Move(FileName[1], Entry^.Name, Min(24, Length(FileName)));
  try
    if Stream.Size > 0 then
    begin
      FImg.CopyFrom(Stream, Stream.Size);
    end;

    FDir.Write(Entry^, 32);
    FEntries.Add(Entry);

  except
    FImg.Size := Old;
    raise;
  end;
end;

procedure TIMGunit.Rename(Index: Integer; NewName: string);
begin
  FillChar(TDirEntry(FEntries.Items[Index]^).Name, 24, 0);
  Move(NewName[1], TDirEntry(FEntries.Items[Index]^).Name, Min(24, Length(NewName)));
  FDir.Position := Entry[Index].Index * 32;
  FDir.Write(FEntries.Items[Index]^, 32);
end;

procedure TIMGunit.MarkForRemoval(Index: Integer);
begin
  TDirEntry(FEntries.Items[Index]^).Delete := True;
end;

procedure TIMGunit.DoRemove;
var i: Integer;
begin
  FEntries.Sort(@SortByIndex);
  for i := FEntries.Count -1 downto 0 do
  begin
    if TDirEntry(FEntries.Items[i]^).Delete then
    begin
      FEntries.Delete(i);
    end;
  end;
  FDir.Size := FEntries.Count * 32;
  FDir.Position := 0;
  for i := 0 to FEntries.Count -1 do
  begin
    TDirEntry(FEntries.Items[i]^).Index := i;
    FDir.Write(FEntries.Items[i]^, 32);
  end;
end;

end.
```
## Post #15
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:54:14+00:00
- Post Title: Game UnPacker's Source

Rallisport Challenge RFF units for DELPHI

FinkelArchive.pas

```

interface

uses
  Classes, SysUtils, ZLib, FinkelArchiveCrypt;

type
  TFinkelArchiveEntry = class;

  TFinkelArchiveHeader = record
    Marker: array[0..31] of Char;
    EntryOffs: Longword;
    unknown: Longword;
  end;

  TArchiveMode = (amCreate, amReadOnly, amEdit);
  TProgressType = (ptExtract, ptAdd, ptUpdate, ptRemove);
  TProgressStartEvent = procedure(Sender: TObject; ProgressType: TProgressType) of object;
  TProgressEvent = procedure(Sender: TObject; Percent: Integer) of object;

  TFinkelArchive = class
  private
    FHeader: TFinkelArchiveHeader;
    FArchiveMode: TArchiveMode;
    FArchiveStrm: TFileStream;
    FBlowFish: TBlowFish;
    FEntries: TList;
    FModified: Boolean;

    FOnProgressStart: TProgressStartEvent;
    FOnProgress: TProgressEvent;
    FOnProgressDone: TNotifyEvent;

    function GetCount: Integer;
    function GetEntry(Index: Integer): TFinkelArchiveEntry;
    procedure ParseArchive;
  public
    constructor Create(FileName: string; ArchiveMode: TArchiveMode);
    destructor Destroy; override;
    procedure ForceArchiveUpdate;
    procedure Add(Name: string; Data: TStream; Size: Longword);
    procedure Extract(EntryIndex: Integer; FileName: string); overload;

    procedure Extract(EntryIndex: Integer; Dest: TStream); overload;
    property Count: Integer read GetCount;
    property Entry[Index: Integer]: TFinkelArchiveEntry read GetEntry;

    property OnProgressStart: TProgressStartEvent read FOnProgressStart write FOnProgressStart;
    property OnProgressDone: TNotifyEvent read FOnProgressDone write FOnProgressDone;
    property OnProgress: TProgressEvent read FOnProgress write FOnProgress;
  end;

  TFinkelArchiveEntryRec = record
    CompSize: Longword;
    RawSize: Longword;
    Offset: Longword;
    u0,u1,u2: Longword;
  end;

  TFinkelArchiveEntry = class
  private
    FEntryRec: TFinkelArchiveEntryRec;
    FName: string;
    function GetCompSize: Longword;
    function GetRawSize: Longword;
    function GetOffset: Longword;
  protected
    procedure ReadFromStream(Stream: TStream);
  public
    property Name: string read FName;
    property CompressedSize: Longword read GetCompSize;
    property UncompressedSize: Longword read GetRawSize;
    property Offset: Longword read GetOffset;
  end;

const
  RSC_RETAIL_KEY : TBlowFishKey = ($72, $03, $17, $f4, $12, $43, $92, $88);
  RSC_TRIAL_KEY  : TBlowFishKey = ($23, $43, $55, $02, $37, $99, $af, $c7);

  FINKEL_ARCHIVE_MARKER = 'Refractor2 FinkelArchive 1.0' + #0#0#0#0;

implementation

function GetPadToQword(Val: Longword): Cardinal;
begin
  Result := (Val and 7 + 7) and 8 - Val and 7;
end;

function GetQwordPaded(Val: Longword): Cardinal;
begin
  Result := Val + ((Val and 7 + 7) and 8 - Val and 7);
end;


{ TFinkelArchive }

constructor TFinkelArchive.Create(FileName: string; ArchiveMode: TArchiveMode);
var
  FileMode: Word;
begin
  inherited Create;
  FArchiveMode := ArchiveMode;
  case FArchiveMode of
    amCreate:   FileMode := fmCreate;
    amReadOnly: FileMode := fmOpenRead + fmShareDenyWrite;
    amEdit:     FileMode := fmOpenReadWrite;
  else
    raise Exception.Create('Invalid archive mode.');
  end;
    FEntries := TList.Create;

  FBlowFish := TBlowFish.Create;

  FBlowFish.SetKey(RSC_RETAIL_KEY);

  FArchiveStrm := TFileStream.Create(FileName, FileMode);
  FArchiveStrm.Read(FHeader, SizeOf(FHeader));

  if not CompareMem(@FHeader.Marker[0], @FINKEL_ARCHIVE_MARKER[1], 32) then
    raise Exception.Create('Not a valid Refractor2 FinkelArchive.');

  FModified := (FArchiveMode = amCreate);
  ParseArchive;
end;

destructor TFinkelArchive.Destroy;
var i: Integer;
begin
  if (FArchiveMode in [amCreate, amEdit]) and FModified then
  begin
    ForceArchiveUpdate;
  end;

  for i := 0 to FEntries.Count -1 do
  begin
    TFinkelArchiveEntry(FEntries.Items[i]).Free;
  end;
  FEntries.Free;
  FArchiveStrm.Free;
  FBlowFish.Free;
  inherited;
end;

procedure TFinkelArchive.ForceArchiveUpdate;
var
  i,n: Integer;
  Entry: TFinkelArchiveEntry;
begin
  if Assigned(FOnProgressStart) then
    FOnProgressStart(Self, ptUpdate);

  if Assigned(FOnProgress) then
    FOnProgress(Self, 0);

  // Write marker
  FArchiveStrm.Position := 0;
  FArchiveStrm.Write(FINKEL_ARCHIVE_MARKER[1], 32);

  // Write offset to entry table and then jump to that offset
  FArchiveStrm.Write(FHeader.EntryOffs, 4);
  FArchiveStrm.Position := FHeader.EntryOffs;

  // Write NumEntries + Entry table
  n := FEntries.Count;
  FArchiveStrm.Write(n, 4);

  for i := 0 to FEntries.Count -1 do
  begin
    Entry := TFinkelArchiveEntry(FEntries.Items[i]);
    // Write name
    n := Length(Entry.FName);
    FArchiveStrm.Write(n, 4);
    FArchiveStrm.Write(Entry.FName[1], n);
    FArchiveStrm.Write(Entry.FEntryRec, SizeOf(Entry.FEntryRec));

    if Assigned(FOnProgress) then
      FOnProgress(Self, Round(100 * i / (FEntries.Count-1)));
  end;

  // Truncate the archive, not needed at the moment, but will be if delete is implemented
  if FArchiveStrm.Position < FArchiveStrm.Size then
    FArchiveStrm.Size := FArchiveStrm.Position;

  if Assigned(FOnProgressDone) then
    FOnProgressDone(Self);

end;

procedure TFinkelArchive.Add(Name: string; Data: TStream; Size: Longword);
var
  Entry: TFinkelArchiveEntry;
  CompStrm: TCompressionStream;
  TmpStrm: TMemoryStream;
  i: Integer;
  z: Int64;
begin
  if Assigned(FOnProgressStart) then
    FOnProgressStart(Self, ptAdd);

  if Assigned(FOnProgress) then
    FOnProgress(Self, 0);

  if FArchiveMode = amReadOnly then
    raise Exception.Create('Archive is read only, can not add an entry!');

  Entry := TFinkelArchiveEntry.Create;
  Entry.FName := Name;
  Entry.FEntryRec.RawSize := Size;

  TmpStrm := TMemoryStream.Create;
  try
    // Zlib compress
    CompStrm := TCompressionStream.Create(clMax, TmpStrm);
    try
      CompStrm.CopyFrom(Data, Size);
    finally
      CompStrm.Free;
    end;
    Entry.FEntryRec.CompSize := TmpStrm.Size;

    if Assigned(FOnProgress) then
      FOnProgress(Self, 50);

    // Pad it to qword alignment
    z := 0;
    //TmpStrm.Seek(0, soFromEnd);
    TmpStrm.Position := TmpStrm.Size;
    TmpStrm.Write(z, GetPadToQword(TmpStrm.Size));
    TmpStrm.Position := 0;

    // Blowfish encrypt
    Entry.FEntryRec.Offset := FHeader.EntryOffs;
    FArchiveStrm.Position := FHeader.EntryOffs;
    if TmpStrm.Size > 0 then
      FBlowFish.EncryptStream(TmpStrm, FArchiveStrm, TmpStrm.Size);

    if Assigned(FOnProgress) then
      FOnProgress(Self, 100);
  finally
    TmpStrm.Free;
  end;
  FEntries.Add(Entry);
  FHeader.EntryOffs := FArchiveStrm.Position;
  FModified := True;

  if Assigned(FOnProgressDone) then
    FOnProgressDone(Self);
end;

procedure TFinkelArchive.Extract(EntryIndex: Integer; FileName: string);
var
  TmpStrm: TFileStream;
begin
  TmpStrm := TFileStream.Create(FileName, fmCreate);
  try
    Extract(EntryIndex, TmpStrm);
  finally
    TmpStrm.Free;
  end;
end;

procedure TFinkelArchive.Extract(EntryIndex: Integer; Dest: TStream);
var
  DecompStrm: TDecompressionStream;
  TmpStrm: TMemoryStream;
  Entry: TFinkelArchiveEntry;
begin
  if Assigned(FOnProgressStart) then
    FOnProgressStart(Self, ptExtract);

  if Assigned(FOnProgress) then
    FOnProgress(Self, 0);

  Entry := TFinkelArchiveEntry(FEntries.Items[EntryIndex]);

  TmpStrm := TMemoryStream.Create;
  try
    FArchiveStrm.Position := Entry.FEntryRec.Offset;
    FBlowFish.DecryptStream(FArchiveStrm, TmpStrm, GetQwordPaded(Entry.FEntryRec.CompSize));
    TmpStrm.Position := 0;

    if Assigned(FOnProgress) then
      FOnProgress(Self, 50);

    DecompStrm := TDecompressionStream.Create(TmpStrm);
    try
      Dest.CopyFrom(DecompStrm, Entry.FEntryRec.RawSize);
      if Assigned(FOnProgress) then
        FOnProgress(Self, 100);
    finally
      DecompStrm.Free;
    end;
  finally
    TmpStrm.Free;
    if Assigned(FOnProgressDone) then
      FOnProgressDone(Self);
  end;
end;

function TFinkelArchive.GetCount: Integer;
begin
  Result := FEntries.Count;
end;

function TFinkelArchive.GetEntry(Index: Integer): TFinkelArchiveEntry;
begin
  Result := TFinkelArchiveEntry(FEntries.Items[Index]);
end;

procedure TFinkelArchive.ParseArchive;
var
  Num, i: Integer;
begin
  FArchiveStrm.Position := FHeader.EntryOffs;
  FArchiveStrm.Read(Num, 4);
  FEntries.Capacity := Num+1;
  for i := 0 to Num -1 do
  begin
    FEntries.Add(TFinkelArchiveEntry.Create);
    TFinkelArchiveEntry(FEntries.Items[i]).ReadFromStream(FArchiveStrm);
  end;
end;


{ TFinkelArchiveEntry }

procedure TFinkelArchiveEntry.ReadFromStream(Stream: TStream);
var
  NameLen: Longword;
begin
  Stream.Read(NameLen, 4);
  SetLength(FName, NameLen);
  Stream.Read(FName[1], NameLen);
  Stream.Read(FEntryRec, SizeOf(FEntryRec));
end;

function TFinkelArchiveEntry.GetCompSize: Longword;
begin
  Result := FEntryRec.CompSize;
end;

function TFinkelArchiveEntry.GetRawSize: Longword;
begin
  Result := FEntryRec.RawSize;
end;

function TFinkelArchiveEntry.GetOffset: Longword;
begin
  Result := FEntryRec.Offset;
end;

end.
```


FinkelArchiveCrypt.pas

```

interface

uses Classes;

type
  TBlowFishKey  = array[0..7] of Byte;
  TBlowFishPKey = array[0..17] of Longword;
  TBlowFishSKey = array[0..3,0..255] of Longword;

  TBlowFish = class
  private
    FP: TBlowFishPKey;
    FS: TBlowFishSKey;
    FKey: TBlowFishKey;
    procedure Decrypt(var L,R: Longword);
    procedure Encrypt(var L,R: Longword);
  public
    constructor Create;
    destructor Destroy; override;
    procedure SetKey(Key: TBlowFishKey);
    function DecryptStream(Source, Dest: TStream; Size: Longword): Longword;
    function EncryptStream(Source, Dest: TStream; Size: Longword): Longword;
  end;

const
  BLOWFISH_P: TBlowFishPKey = (
    $243f6a88, $85a308d3, $13198a2e, $03707344, $a4093822, $299f31d0,
    $082efa98, $ec4e6c89, $452821e6, $38d01377, $be5466cf, $34e90c6c,
    $c0ac29b7, $c97c50dd, $3f84d5b5, $b5470917, $9216d5d9, $8979fb1b);

  BLOWFISH_S: TBlowFishSKey = (
   ($d1310ba6, $98dfb5ac, $2ffd72db, $d01adfb7, $b8e1afed, $6a267e96,
    $ba7c9045, $f12c7f99, $24a19947, $b3916cf7, $0801f2e2, $858efc16,
    $636920d8, $71574e69, $a458fea3, $f4933d7e, $0d95748f, $728eb658,
    $718bcd58, $82154aee, $7b54a41d, $c25a59b5, $9c30d539, $2af26013,
    $c5d1b023, $286085f0, $ca417918, $b8db38ef, $8e79dcb0, $603a180e,
    $6c9e0e8b, $b01e8a3e, $d71577c1, $bd314b27, $78af2fda, $55605c60,
    $e65525f3, $aa55ab94, $57489862, $63e81440, $55ca396a, $2aab10b6,
    $b4cc5c34, $1141e8ce, $a15486af, $7c72e993, $b3ee1411, $636fbc2a,
    $2ba9c55d, $741831f6, $ce5c3e16, $9b87931e, $afd6ba33, $6c24cf5c,
    $7a325381, $28958677, $3b8f4898, $6b4bb9af, $c4bfe81b, $66282193,
    $61d809cc, $fb21a991, $487cac60, $5dec8032, $ef845d5d, $e98575b1,
    $dc262302, $eb651b88, $23893e81, $d396acc5, $0f6d6ff3, $83f44239,
    $2e0b4482, $a4842004, $69c8f04a, $9e1f9b5e, $21c66842, $f6e96c9a,
    $670c9c61, $abd388f0, $6a51a0d2, $d8542f68, $960fa728, $ab5133a3,
    $6eef0b6c, $137a3be4, $ba3bf050, $7efb2a98, $a1f1651d, $39af0176,
    $66ca593e, $82430e88, $8cee8619, $456f9fb4, $7d84a5c3, $3b8b5ebe,
    $e06f75d8, $85c12073, $401a449f, $56c16aa6, $4ed3aa62, $363f7706,
    $1bfedf72, $429b023d, $37d0d724, $d00a1248, $db0fead3, $49f1c09b,
    $075372c9, $80991b7b, $25d479d8, $f6e8def7, $e3fe501a, $b6794c3b,
    $976ce0bd, $04c006ba, $c1a94fb6, $409f60c4, $5e5c9ec2, $196a2463,
    $68fb6faf, $3e6c53b5, $1339b2eb, $3b52ec6f, $6dfc511f, $9b30952c,
    $cc814544, $af5ebd09, $bee3d004, $de334afd, $660f2807, $192e4bb3,
    $c0cba857, $45c8740f, $d20b5f39, $b9d3fbdb, $5579c0bd, $1a60320a,
    $d6a100c6, $402c7279, $679f25fe, $fb1fa3cc, $8ea5e9f8, $db3222f8,
    $3c7516df, $fd616b15, $2f501ec8, $ad0552ab, $323db5fa, $fd238760,
    $53317b48, $3e00df82, $9e5c57bb, $ca6f8ca0, $1a87562e, $df1769db,
    $d542a8f6, $287effc3, $ac6732c6, $8c4f5573, $695b27b0, $bbca58c8,
    $e1ffa35d, $b8f011a0, $10fa3d98, $fd2183b8, $4afcb56c, $2dd1d35b,
    $9a53e479, $b6f84565, $d28e49bc, $4bfb9790, $e1ddf2da, $a4cb7e33,
    $62fb1341, $cee4c6e8, $ef20cada, $36774c01, $d07e9efe, $2bf11fb4,
    $95dbda4d, $ae909198, $eaad8e71, $6b93d5a0, $d08ed1d0, $afc725e0,
    $8e3c5b2f, $8e7594b7, $8ff6e2fb, $f2122b64, $8888b812, $900df01c,
    $4fad5ea0, $688fc31c, $d1cff191, $b3a8c1ad, $2f2f2218, $be0e1777,
    $ea752dfe, $8b021fa1, $e5a0cc0f, $b56f74e8, $18acf3d6, $ce89e299,
    $b4a84fe0, $fd13e0b7, $7cc43b81, $d2ada8d9, $165fa266, $80957705,
    $93cc7314, $211a1477, $e6ad2065, $77b5fa86, $c75442f5, $fb9d35cf,
    $ebcdaf0c, $7b3e89a0, $d6411bd3, $ae1e7e49, $00250e2d, $2071b35e,
    $226800bb, $57b8e0af, $2464369b, $f009b91e, $5563911d, $59dfa6aa,
    $78c14389, $d95a537f, $207d5ba2, $02e5b9c5, $83260376, $6295cfa9,
    $11c81968, $4e734a41, $b3472dca, $7b14a94a, $1b510052, $9a532915,
    $d60f573f, $bc9bc6e4, $2b60a476, $81e67400, $08ba6fb5, $571be91f,
    $f296ec6b, $2a0dd915, $b6636521, $e7b9f9b6, $ff34052e, $c5855664,
    $53b02d5d, $a99f8fa1, $08ba4799, $6e85076a),

   ($4b7a70e9, $b5b32944, $db75092e, $c4192623, $ad6ea6b0, $49a7df7d,
    $9cee60b8, $8fedb266, $ecaa8c71, $699a17ff, $5664526c, $c2b19ee1,
    $193602a5, $75094c29, $a0591340, $e4183a3e, $3f54989a, $5b429d65,
    $6b8fe4d6, $99f73fd6, $a1d29c07, $efe830f5, $4d2d38e6, $f0255dc1,
    $4cdd2086, $8470eb26, $6382e9c6, $021ecc5e, $09686b3f, $3ebaefc9,
    $3c971814, $6b6a70a1, $687f3584, $52a0e286, $b79c5305, $aa500737,
    $3e07841c, $7fdeae5c, $8e7d44ec, $5716f2b8, $b03ada37, $f0500c0d,
    $f01c1f04, $0200b3ff, $ae0cf51a, $3cb574b2, $25837a58, $dc0921bd,
    $d19113f9, $7ca92ff6, $94324773, $22f54701, $3ae5e581, $37c2dadc,
    $c8b57634, $9af3dda7, $a9446146, $0fd0030e, $ecc8c73e, $a4751e41,
    $e238cd99, $3bea0e2f, $3280bba1, $183eb331, $4e548b38, $4f6db908,
    $6f420d03, $f60a04bf, $2cb81290, $24977c79, $5679b072, $bcaf89af,
    $de9a771f, $d9930810, $b38bae12, $dccf3f2e, $5512721f, $2e6b7124,
    $501adde6, $9f84cd87, $7a584718, $7408da17, $bc9f9abc, $e94b7d8c,
    $ec7aec3a, $db851dfa, $63094366, $c464c3d2, $ef1c1847, $3215d908,
    $dd433b37, $24c2ba16, $12a14d43, $2a65c451, $50940002, $133ae4dd,
    $71dff89e, $10314e55, $81ac77d6, $5f11199b, $043556f1, $d7a3c76b,
    $3c11183b, $5924a509, $f28fe6ed, $97f1fbfa, $9ebabf2c, $1e153c6e,
    $86e34570, $eae96fb1, $860e5e0a, $5a3e2ab3, $771fe71c, $4e3d06fa,
    $2965dcb9, $99e71d0f, $803e89d6, $5266c825, $2e4cc978, $9c10b36a,
    $c6150eba, $94e2ea78, $a5fc3c53, $1e0a2df4, $f2f74ea7, $361d2b3d,
    $1939260f, $19c27960, $5223a708, $f71312b6, $ebadfe6e, $eac31f66,
    $e3bc4595, $a67bc883, $b17f37d1, $018cff28, $c332ddef, $be6c5aa5,
    $65582185, $68ab9802, $eecea50f, $db2f953b, $2aef7dad, $5b6e2f84,
    $1521b628, $29076170, $ecdd4775, $619f1510, $13cca830, $eb61bd96,
    $0334fe1e, $aa0363cf, $b5735c90, $4c70a239, $d59e9e0b, $cbaade14,
    $eecc86bc, $60622ca7, $9cab5cab, $b2f3846e, $648b1eaf, $19bdf0ca,
    $a02369b9, $655abb50, $40685a32, $3c2ab4b3, $319ee9d5, $c021b8f7,
    $9b540b19, $875fa099, $95f7997e, $623d7da8, $f837889a, $97e32d77,
    $11ed935f, $16681281, $0e358829, $c7e61fd6, $96dedfa1, $7858ba99,
    $57f584a5, $1b227263, $9b83c3ff, $1ac24696, $cdb30aeb, $532e3054,
    $8fd948e4, $6dbc3128, $58ebf2ef, $34c6ffea, $fe28ed61, $ee7c3c73,
    $5d4a14d9, $e864b7e3, $42105d14, $203e13e0, $45eee2b6, $a3aaabea,
    $db6c4f15, $facb4fd0, $c742f442, $ef6abbb5, $654f3b1d, $41cd2105,
    $d81e799e, $86854dc7, $e44b476a, $3d816250, $cf62a1f2, $5b8d2646,
    $fc8883a0, $c1c7b6a3, $7f1524c3, $69cb7492, $47848a0b, $5692b285,
    $095bbf00, $ad19489d, $1462b174, $23820e00, $58428d2a, $0c55f5ea,
    $1dadf43e, $233f7061, $3372f092, $8d937e41, $d65fecf1, $6c223bdb,
    $7cde3759, $cbee7460, $4085f2a7, $ce77326e, $a6078084, $19f8509e,
    $e8efd855, $61d99735, $a969a7aa, $c50c06c2, $5a04abfc, $800bcadc,
    $9e447a2e, $c3453484, $fdd56705, $0e1e9ec9, $db73dbd3, $105588cd,
    $675fda79, $e3674340, $c5c43465, $713e38d8, $3d28f89e, $f16dff20,
    $153e21e7, $8fb03d4a, $e6e39f2b, $db83adf7),

   ($e93d5a68, $948140f7, $f64c261c, $94692934, $411520f7, $7602d4f7,
    $bcf46b2e, $d4a20068, $d4082471, $3320f46a, $43b7d4b7, $500061af,
    $1e39f62e, $97244546, $14214f74, $bf8b8840, $4d95fc1d, $96b591af,
    $70f4ddd3, $66a02f45, $bfbc09ec, $03bd9785, $7fac6dd0, $31cb8504,
    $96eb27b3, $55fd3941, $da2547e6, $abca0a9a, $28507825, $530429f4,
    $0a2c86da, $e9b66dfb, $68dc1462, $d7486900, $680ec0a4, $27a18dee,
    $4f3ffea2, $e887ad8c, $b58ce006, $7af4d6b6, $aace1e7c, $d3375fec,
    $ce78a399, $406b2a42, $20fe9e35, $d9f385b9, $ee39d7ab, $3b124e8b,
    $1dc9faf7, $4b6d1856, $26a36631, $eae397b2, $3a6efa74, $dd5b4332,
    $6841e7f7, $ca7820fb, $fb0af54e, $d8feb397, $454056ac, $ba489527,
    $55533a3a, $20838d87, $fe6ba9b7, $d096954b, $55a867bc, $a1159a58,
    $cca92963, $99e1db33, $a62a4a56, $3f3125f9, $5ef47e1c, $9029317c,
    $fdf8e802, $04272f70, $80bb155c, $05282ce3, $95c11548, $e4c66d22,
    $48c1133f, $c70f86dc, $07f9c9ee, $41041f0f, $404779a4, $5d886e17,
    $325f51eb, $d59bc0d1, $f2bcc18f, $41113564, $257b7834, $602a9c60,
    $dff8e8a3, $1f636c1b, $0e12b4c2, $02e1329e, $af664fd1, $cad18115,
    $6b2395e0, $333e92e1, $3b240b62, $eebeb922, $85b2a20e, $e6ba0d99,
    $de720c8c, $2da2f728, $d0127845, $95b794fd, $647d0862, $e7ccf5f0,
    $5449a36f, $877d48fa, $c39dfd27, $f33e8d1e, $0a476341, $992eff74,
    $3a6f6eab, $f4f8fd37, $a812dc60, $a1ebddf8, $991be14c, $db6e6b0d,
    $c67b5510, $6d672c37, $2765d43b, $dcd0e804, $f1290dc7, $cc00ffa3,
    $b5390f92, $690fed0b, $667b9ffb, $cedb7d9c, $a091cf0b, $d9155ea3,
    $bb132f88, $515bad24, $7b9479bf, $763bd6eb, $37392eb3, $cc115979,
    $8026e297, $f42e312d, $6842ada7, $c66a2b3b, $12754ccc, $782ef11c,
    $6a124237, $b79251e7, $06a1bbe6, $4bfb6350, $1a6b1018, $11caedfa,
    $3d25bdd8, $e2e1c3c9, $44421659, $0a121386, $d90cec6e, $d5abea2a,
    $64af674e, $da86a85f, $bebfe988, $64e4c3fe, $9dbc8057, $f0f7c086,
    $60787bf8, $6003604d, $d1fd8346, $f6381fb0, $7745ae04, $d736fccc,
    $83426b33, $f01eab71, $b0804187, $3c005e5f, $77a057be, $bde8ae24,
    $55464299, $bf582e61, $4e58f48f, $f2ddfda2, $f474ef38, $8789bdc2,
    $5366f9c3, $c8b38e74, $b475f255, $46fcd9b9, $7aeb2661, $8b1ddf84,
    $846a0e79, $915f95e2, $466e598e, $20b45770, $8cd55591, $c902de4c,
    $b90bace1, $bb8205d0, $11a86248, $7574a99e, $b77f19b6, $e0a9dc09,
    $662d09a1, $c4324633, $e85a1f02, $09f0be8c, $4a99a025, $1d6efe10,
    $1ab93d1d, $0ba5a4df, $a186f20f, $2868f169, $dcb7da83, $573906fe,
    $a1e2ce9b, $4fcd7f52, $50115e01, $a70683fa, $a002b5c4, $0de6d027,
    $9af88c27, $773f8641, $c3604c06, $61a806b5, $f0177a28, $c0f586e0,
    $006058aa, $30dc7d62, $11e69ed7, $2338ea63, $53c2dd94, $c2c21634,
    $bbcbee56, $90bcb6de, $ebfc7da1, $ce591d76, $6f05e409, $4b7c0188,
    $39720a3d, $7c927c24, $86e3725f, $724d9db9, $1ac15bb4, $d39eb8fc,
    $ed545578, $08fca5b5, $d83d7cd3, $4dad0fc4, $1e50ef5e, $b161e6f8,
    $a28514d9, $6c51133c, $6fd5c7e7, $56e14ec4, $362abfce, $ddc6c837,
    $d79a3234, $92638212, $670efa8e, $406000e0),

   ($3a39ce37, $d3faf5cf, $abc27737, $5ac52d1b, $5cb0679e, $4fa33742,
    $d3822740, $99bc9bbe, $d5118e9d, $bf0f7315, $d62d1c7e, $c700c47b,
    $b78c1b6b, $21a19045, $b26eb1be, $6a366eb4, $5748ab2f, $bc946e79,
    $c6a376d2, $6549c2c8, $530ff8ee, $468dde7d, $d5730a1d, $4cd04dc6,
    $2939bbdb, $a9ba4650, $ac9526e8, $be5ee304, $a1fad5f0, $6a2d519a,
    $63ef8ce2, $9a86ee22, $c089c2b8, $43242ef6, $a51e03aa, $9cf2d0a4,
    $83c061ba, $9be96a4d, $8fe51550, $ba645bd6, $2826a2f9, $a73a3ae1,
    $4ba99586, $ef5562e9, $c72fefd3, $f752f7da, $3f046f69, $77fa0a59,
    $80e4a915, $87b08601, $9b09e6ad, $3b3ee593, $e990fd5a, $9e34d797,
    $2cf0b7d9, $022b8b51, $96d5ac3a, $017da67d, $d1cf3ed6, $7c7d2d28,
    $1f9f25cf, $adf2b89b, $5ad6b472, $5a88f54c, $e029ac71, $e019a5e6,
    $47b0acfd, $ed93fa9b, $e8d3c48d, $283b57cc, $f8d56629, $79132e28,
    $785f0191, $ed756055, $f7960e44, $e3d35e8c, $15056dd4, $88f46dba,
    $03a16125, $0564f0bd, $c3eb9e15, $3c9057a2, $97271aec, $a93a072a,
    $1b3f6d9b, $1e6321f5, $f59c66fb, $26dcf319, $7533d928, $b155fdf5,
    $03563482, $8aba3cbb, $28517711, $c20ad9f8, $abcc5167, $ccad925f,
    $4de81751, $3830dc8e, $379d5862, $9320f991, $ea7a90c2, $fb3e7bce,
    $5121ce64, $774fbe32, $a8b6e37e, $c3293d46, $48de5369, $6413e680,
    $a2ae0810, $dd6db224, $69852dfd, $09072166, $b39a460a, $6445c0dd,
    $586cdecf, $1c20c8ae, $5bbef7dd, $1b588d40, $ccd2017f, $6bb4e3bb,
    $dda26a7e, $3a59ff45, $3e350a44, $bcb4cdd5, $72eacea8, $fa6484bb,
    $8d6612ae, $bf3c6f47, $d29be463, $542f5d9e, $aec2771b, $f64e6370,
    $740e0d8d, $e75b1357, $f8721671, $af537d5d, $4040cb08, $4eb4e2cc,
    $34d2466a, $0115af84, $e1b00428, $95983a1d, $06b89fb4, $ce6ea048,
    $6f3f3b82, $3520ab82, $011a1d4b, $277227f8, $611560b1, $e7933fdc,
    $bb3a792b, $344525bd, $a08839e1, $51ce794b, $2f32c9b7, $a01fbac9,
    $e01cc87e, $bcc7d1f6, $cf0111c3, $a1e8aac7, $1a908749, $d44fbd9a,
    $d0dadecb, $d50ada38, $0339c32a, $c6913667, $8df9317c, $e0b12b4f,
    $f79e59b7, $43f5bb3a, $f2d519ff, $27d9459c, $bf97222c, $15e6fc2a,
    $0f91fc71, $9b941525, $fae59361, $ceb69ceb, $c2a86459, $12baa8d1,
    $b6c1075e, $e3056a0c, $10d25065, $cb03a442, $e0ec6e0e, $1698db3b,
    $4c98a0be, $3278e964, $9f1f9532, $e0d392df, $d3a0342b, $8971f21e,
    $1b0a7441, $4ba3348c, $c5be7120, $c37632d8, $df359f8d, $9b992f2e,
    $e60b6f47, $0fe3f11d, $e54cda54, $1edad891, $ce6279cf, $cd3e7e6f,
    $1618b166, $fd2c1d05, $848fd2c5, $f6fb2299, $f523f357, $a6327623,
    $93a83531, $56cccd02, $acf08162, $5a75ebb5, $6e163697, $88d273cc,
    $de966292, $81b949d0, $4c50901b, $71c65614, $e6c6c7bd, $327a140a,
    $45e1d006, $c3f27b9a, $c9aa53fd, $62a80f00, $bb25bfe2, $35bdd2f6,
    $71126905, $b2040222, $b6cbcf7c, $cd769c2b, $53113ec0, $1640e3d3,
    $38abbd60, $2547adf0, $ba38209c, $f746ce76, $77afa1c5, $20756060,
    $85cbfe4e, $8ae88dd8, $7aaaf9b0, $4cf9aa7e, $1948c25c, $02fb8a8c,
    $01c36ae4, $d6ebe1f9, $90d4f869, $a65cdea0, $3f09252d, $c208e69f,
    $b74e6132, $ce77e25b, $578fdfe3, $3ac372e6));

////////////////////////////////////////////////////////////////////////////////

implementation


{ TBlowFish }

constructor TBlowFish.Create;
begin
  inherited;
  FillChar(FP, SizeOf(TBlowFishPKey), 0);
  FillChar(FS, SizeOf(TBlowFishSKey), 0);
  FillChar(FKey, SizeOf(TBlowFishKey), 0);
end;

destructor TBlowFish.Destroy;
begin
  FillChar(FP, SizeOf(TBlowFishPKey), $ff);
  FillChar(FS, SizeOf(TBlowFishSKey), $ff);
  FillChar(FKey, SizeOf(TBlowFishKey), $ff);
  inherited;
end;

procedure TBlowFish.SetKey(Key: TBlowFishKey);
var
  i,j: Integer;
  R,L: Longword;
begin
  FKey := Key;
  FP := BLOWFISH_P;
  FS := BLOWFISH_S;

  j := 0;
  for i := 0 to 17 do
  begin
    FP[i] := FP[i] xor (FKey[j mod 8] shl 24 or FKey[(j+1) mod 8] shl 16 or
      FKey[(j+2) mod 8] shl  8 or FKey[(j+3) mod 8]);
    Inc(j, 4);
    j := j mod 8;
  end;

  L := 0;
  R := 0;

  for i := 0 to 8 do
  begin
    Encrypt(L, R);
    FP[i*2]   := L;
    FP[i*2+1] := R;
  end;

  for i := 0 to 3 do
  begin
    for j := 0 to 127 do
    begin
      Encrypt(L, R);
      FS[i,j*2]   := L;
      FS[i,j*2+1] := R;
    end;
  end;
end;

procedure TBlowFish.Decrypt(var L,R: Longword);
var
  xL, xR: Longword;
begin
  {$IFDEF SWAP_BYTES}
    asm
      MOV    EAX, L;
      BSWAP  EAX
      MOV    xL, EAX;
      MOV    EAX, R;
      BSWAP  EAX
      MOV    xR, EAX;
    end;
  {$ELSE}
    xL := L;
    xR := R;
  {$ENDIF}
  xL := xL xor FP[17];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[16];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[15];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[14];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[13];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[12];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[11];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[10];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[9];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[8];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[7];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[6];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[5];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[4];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[3];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[2];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[1];
  xR := xR xor FP[0];
  {$IFDEF SWAP_BYTES}
    asm
      MOV    EAX, xL;
      BSWAP  EAX
      MOV    R, EAX;
      MOV    EAX, xR;
      BSWAP  EAX
      MOV    L, EAX;
    end;
  {$ELSE}
    L := xR;
    R := xL;
  {$ENDIF}
end;

procedure TBlowFish.Encrypt(var L,R: Longword);
var
  xL, xR: Longword;
begin
  {$IFDEF SWAP_BYTES}
    asm
      MOV    EAX, L;
      BSWAP  EAX
      MOV    xL, EAX;
      MOV    EAX, R;
      BSWAP  EAX
      MOV    xR, EAX;
    end;
  {$ELSE}
    xL := L;
    xR := R;
  {$ENDIF}
  xL := xL xor FP[0];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[1];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[2];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[3];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[4];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[5];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[6];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[7];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[8];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[9];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[10];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[11];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[12];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[13];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[14];
  xR := xR xor (((FS[0, (xL shr 24) and $ff] + FS[1, (xL shr 16) and $ff]) xor
    FS[2, (xL shr 8) and $ff]) + FS[3, (xL shr 0) and $ff]) xor FP[15];
  xL := xL xor (((FS[0, (xR shr 24) and $ff] + FS[1, (xR shr 16) and $ff]) xor
    FS[2, (xR shr 8) and $ff]) + FS[3, (xR shr 0) and $ff]) xor FP[16];
  xR := xR xor FP[17];
  {$IFDEF SWAP_BYTES}
    asm
      MOV    EAX, xL;
      BSWAP  EAX
      MOV    R, EAX;
      MOV    EAX, xR;
      BSWAP  EAX
      MOV    L, EAX;
    end;
  {$ELSE}
    L := xR;
    R := xL;
  {$ENDIF}
end;

////////////////////////////////////////////////////////////////////////////////

//  Decrypts a stream. IMPORTANT: Size must be qword (64bit) padded!
function TBlowFish.DecryptStream(Source, Dest: TStream; Size: Longword): Longword;
var
  i,start: Integer;
  Data: record
    l,r: Longword;
  end;
begin
  //TODO: Implement a read buffer to speed it up...
  start := Dest.Position;

  for i := 0 to (Size div 8) - 1 do
  begin
    Source.Read(Data, 8);
    Decrypt(Data.l, Data.r);
    Dest.Write(Data, 8);
  end;
  Result := Dest.Position - start;

end;

//  Encrypts a stream. IMPORTANT: Size must be qword (64bit) padded!
function TBlowFish.EncryptStream(Source, Dest: TStream; Size: Longword): Longword;
var
  i,start: Integer;
  Data: record
    l,r: Longword;
  end;
begin
  //TODO: Implement a read buffer to speed it up...
  start := Dest.Position;

  for i := 0 to (Size div 8) - 1 do
  begin
    Source.Read(Data, 8);
    Encrypt(Data.l, Data.r);
    Dest.Write(Data, 8);
  end;
  Result := Dest.Position - start;
//  Dest.Position := start;  
end;


end.
```
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:04:04+00:00
- Post Title: 

Doom 2D WAD UnPacker

```
{$APPTYPE CONSOLE} 
Uses SysUtils;

Var Fl, F: File;
     S: String;
TotalFiles, I, Now, Sz, Ps: LongInt;
     P: Pointer;
     W: Word;
Begin
  WriteLn('Doom 2D WAD UnPacker');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');

  Assign(Fl, 'doom2d.wad'); //Read doom2d.wad
  {$I-}
  Reset(Fl, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('Can''t open doom2D.wad!'); 
      WriteLn;
      Exit;
    End;
  BlockRead(Fl, S[1], 4);
  S[0]:=#4;
  If S<>'IWAD' Then
    Begin
      WriteLn('Not a ''IWAD''!');
      Close(Fl);
      Exit;
    End;
  BlockRead(Fl, TotalFiles, 4);
  BlockRead(Fl, I, 4);
  Now:=I;
  GetMem(P, $FFF0);
  For I:=1 To TotalFiles Do
    Begin
      Seek(Fl, Now);
      {offs: 4 bytes; size: 4 bytes; name: 8 bytes}
      BlockRead(Fl, Ps, 4);
      BlockRead(Fl, Sz, 4);
      S[0]:=#8;
      BlockRead(Fl, S[1], 8);
      While S[Length(S)]=#0 Do Delete(S, Length(S), 1); 
      While (Pos('[',S)<>0) Or (Pos(']',S)<>0) Or (Pos('\',S)<>0) Do
        Begin
          If Pos('[', S)<>0 Then S[Pos('[', S)]:='(';
          If Pos(']', S)<>0 Then S[Pos(']', S)]:=')';
          If Pos('\', S)<>0 Then S[Pos('\', S)]:='-';
        End;
      WriteLn('|', S, '|');
      Now:=FilePos(Fl);
      Seek(Fl, Ps);
      Assign(F, S);
      ReWrite(F, 1);
      W:=$FFF0;
      While Sz<>0 Do
        Begin
          If Sz>=W Then Sz:=Sz-$FFF0
          Else
            Begin
              W:=Sz;
              Sz:=0;
            End;
          BlockRead(Fl, P^, W);
          BlockWrite(F, P^, W);
        End;
      Close(F);
    End;
  FreeMem(P, $FFF0);
  Close(Fl);
  WriteLn;
  WriteLn('All files unpacked!');
End.
```
## Post #17
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:07:01+00:00
- Post Title: 

Scorcher BIN UnPacker

```
{$APPTYPE CONSOLE}

Uses SysUtils;
Const
      FName = 'tagden.bin'; 
Var
    Fl, F: File;
    TF, FPos, FSize, I, FP: Cardinal;
    S, St, Sd: String;
    P: Pointer;

{ procedure for reversed LONG value }
Function ReadLong(Var F: File): LongInt;
Var K, Bl: Byte;
    L: LongInt;
Begin
  L:=0;
  For K:=3 DownTo 0 Do
    Begin
      BlockRead(F, Bl, 1);
      L:=L+(Bl Shl (8*K));
    End;
  ReadLong:=L;
End;

Begin
  WriteLn('Scorcher BIN UnPacker');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  If FileExists(FName)=False Then
    Begin
      WriteLn('File '''+FName+''' not found.');
      Exit;
    End;
  AssignFile(Fl, FName);
  Reset(Fl, 1);
  TF:=0;
  Repeat
    I:=ReadLong(Fl); { Size of fields }
    If I=$FFFFFFFF Then Break;
    FPos:=ReadLong(Fl); { FPos }
    FSize:=ReadLong(Fl); { FSize }
    I:=ReadLong(Fl)-I; { size of all structure - size of fileds = Name Length }
    SetLength(S, I);
    BlockRead(Fl, S[1], I);
    I:=1;
    While Ord(S[I])<>0 Do I:=I+1;
    SetLength(S, I-1);
    Delete(S, 1, 3);
    WriteLn(S);

    St:=S;
    While (Length(St)>0) And (St[Length(St)]<>'\') Do
      Delete(St, Length(St), 1);
    If Length(St)>0 Then
      Begin
        Sd:='.';
        While Length(St)<>0 Do
          Begin
            Sd:=Sd+'\'+Copy(St, 1, Pos('\',St));
            Delete(Sd, Length(Sd), 1);
            If DirectoryExists(Sd)=False Then CreateDir(Sd);
            St:=Copy(St, Pos('\', St)+1, Length(St));
          End;
      End;
    FP:=FilePos(Fl);
    Seek(Fl, FPos);
    GetMem(P, FSize);
    AssignFile(F, S);
    ReWrite(F, 1);
    BlockRead(Fl, P^, FSize);
    BlockWrite(F, P^, FSize);
    CloseFile(F);
    FreeMem(P, FSize);
    Seek(Fl, FP);
    TF:=TF+1;
  Until 1=2;
  WriteLn('Total files: ', TF);
  CloseFile(Fl);
End.
```
## Post #18
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:09:11+00:00
- Post Title: 

Speed Haste JCL UnPacker

```
{$APPTYPE CONSOLE} 

Uses SysUtils;
Var
    Finp, Fl: File;
    P: Pointer;
    W: Word;
    Sz, FP, FSk, FHere: LongInt;
    S: String;
Begin
  WriteLn('Speed Haste JCL UnPacker');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  Assign(Finp, 'speedh.jcl');
  {$I-}
  Reset(Finp, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('"speedh.jcl" file not found!');
      Exit;
    End;
  If FileSize(Finp)=6548766 Then Seek(Finp, $0063BBEE) {Full verison}
  Else Seek(Finp, $0061DE58); {Shareware version} { FileSize(Finp)=6425960 }
  GetMem(P, $FFF0);
  FHere:=0;
  Repeat
    BlockRead(Finp, S[1], 24);
    S[0]:=#24;
    While S[Length(S)]=#0 Do Delete(S, Length(S), 1);
    WriteLn(S);
    BlockRead(Finp, FSk, 4);
    BlockRead(Finp, Sz, 4);
    FP:=FilePos(Finp);
    Seek(Finp, FHere);
    W:=$FFF0;
    Assign(Fl, S);
    ReWrite(Fl, 1);
    Repeat
      If Sz>=W Then Sz:=Sz-W
      Else
        Begin
          W:=Sz;
          Sz:=0;
        End;
      BlockRead(Finp, P^, W);
      BlockWrite(Fl, P^, W);
    Until Sz=0;
    Close(Fl);
    FHere:=FilePos(Finp);
    Seek(Finp, FP);
  Until FilePos(Finp)+16=FileSize(Finp);
  FreeMem(P, $FFF0);
  Close(Finp);
  WriteLn;
  WriteLn('Done.');
End.
```
## Post #19
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:10:58+00:00
- Post Title: 

Vanguard Ace DIR UnPacker

```
{$APPTYPE CONSOLE} 

Uses SysUtils;
Var FInp, FD, Fl: File;
    S: String[13];
    Sz, Offs: LongInt;
    W: Word;
    P: Pointer;
Begin
  WriteLn('Vanguard Ace DIR UnPacker'); 
  WriteLn('Version 1.0'); 
  WriteLn; 
  WriteLn('KorNet'); 
  WriteLn;
  Assign(FInp, 'vanguard.dir');
  {$I-}
  Reset(FInp, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('''vanguard.dir'' not found!');
      Exit;
    End;
  GetMem(P, $FFF0);
  Repeat
    {13 + size offs}
    BlockRead(FInp, S[1], 13);
    S[0]:=#13;
    While S[Length(S)]=#0 Do Delete(S, Length(S), 1);
    BlockRead(FInp, Sz, 4);
    BlockRead(FInp, Offs, 4);
    WriteLn(S, ' - ', Sz, ' - ', Offs);
    Assign(FD, 'vanguard.jlb');
    {$I-}
    Reset(FD, 1);
    {$I+}
    If IOResult<>0 Then
      Begin
        WriteLn('''vanguard.jlb'' not found!');
        Close(FInp);
        Exit;
      End;
    Seek(FD, Offs);
    Assign(Fl, S);
    ReWrite(Fl, 1);
    W:=$FFF0;
    Repeat
      If Sz>=W Then Sz:=Sz-W
      Else
        Begin
          W:=Sz;
          Sz:=0;
        End;
      BlockRead(FD, P^, W);
      BlockWrite(Fl, P^, W);
    Until Sz=0;
    Close(Fl);
    Close(FD);
  Until EOF(FInp);
  FreeMem(P, $FFF0);
  Close(FInp);
End.
```
## Post #20
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:13:01+00:00
- Post Title: 

Wacky Wheels DAT UnPacker

```
{$APPTYPE CONSOLE} 

Uses SysUtils;

Const
      FName = 'WACKY.DAT';

Var
    FSize, FOffs, FPos: LongInt;
                 Fi, Fl: File;
               I, TF, W: Word;
                      S: String;
                      P: Pointer;
Begin
  WriteLn('Wacky Wheels DAT UnPacker'); 
  WriteLn('Version 1.0'); 
  WriteLn; 
  WriteLn('KorNet'); 
  WriteLn;
  Assign(Fi, FName);
  {$I-}
  Reset(Fi, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('Can''t open '''+FName+'''!');
      Exit;
    End;
  BlockRead(Fi, TF, 2);
  WriteLn(TF);
  GetMem(P, $FFFE);
  For I:=1 To TF Do
    Begin
      S[0]:=#14;
      BlockRead(Fi, S[1], 14);
      BlockRead(Fi, FSize, 4); { Size }
      BlockRead(Fi, FOffs, 4); { Offs }
      S[0]:=Chr(Pos(#0, S) - 1);
      WriteLn(S);
      FPos:=FilePos(Fi);
      Seek(Fi, FOffs+2); { +2 !!! }
      W:=$FFFE;
      Assign(Fl, S);
      ReWrite(Fl, 1);
      Repeat
        If FSize>=$FFFE Then FSize:=FSize-W
        Else
          Begin
            W:=FSize;
            FSize:=0;
          End;
        BlockRead(Fi, P^, W);
        BlockWrite(Fl, P^, W);
      Until FSize = 0;
      Close(Fl);
      Seek(Fi, FPos);
    End;
  FreeMem(P, $FFFE);
  WriteLn('Total files: ', TF);
  Close(Fi);
End.
```
## Post #21
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:15:20+00:00
- Post Title: 

Zone Raides MAS UnPacker

```
{$APPTYPE CONSOLE} 

Uses SysUtils;
Var
    Fl, F: File;
    TF, Sz, FS, FP, L, Sm: LongInt;
    S: String;
    P: Pointer;
    W: Word;
Begin
  WriteLn('Zone Raides MAS UnPacker'); 
  WriteLn('Version 1.0'); 
  WriteLn; 
  WriteLn('KorNet'); 
  WriteLn;
  If ParamCount<>1 Then
    Begin
      WriteLn('Usage: UNPK filename.mas');
      Exit;
    End;
  Assign(Fl, ParamStr(1));
  Reset(Fl, 1);
  BlockRead(Fl, TF, 4);
  BlockRead(Fl, Sz, 4);
  Seek(Fl, FileSize(Fl)-Sz);
  FS:=FilePos(Fl);
  Seek(Fl, 8);
  FP:=FilePos(Fl);
  Sm:=0;
  GetMem(P, $FFF0);
  For L:=1 To TF Do
    Begin
      S[0]:=#16;
      BlockRead(Fl, S[1], 16);
      While S[Length(S)]=#0 Do Delete(S, Length(S), 1);
      Seek(Fl, FilePos(Fl)+4); { Skip }
      BlockRead(Fl, Sz, 4); { FileSize }
      Seek(Fl, FilePos(Fl)+8); { Skip }
      FP:=FilePos(Fl);
      Seek(Fl, FS);
      {...}
      Assign(F, S);
      ReWrite(F, 1);
      W:=$FFF0;
      While Sz<>0 Do
        Begin
          If Sz>=W Then Sz:=Sz-W
          Else
            Begin
              W:=Sz;
              Sz:=0;
            End;
          BlockRead(Fl, P^, W);
          BlockWrite(F, P^, W);
        End;
      Close(F);
      {...}
      FS:=FilePos(Fl);
      Seek(Fl, FP);
      WriteLn(S);
      Sm:=Sm+Sz;
    End;
  FreeMem(P, $FFF0);
  Close(Fl);
  WriteLn(TF, ' file(s) extracted');
End.
```
## Post #22
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T23:19:04+00:00
- Post Title: 

Liero SDN UnPacker

```
{$APPTYPE CONSOLE} 

Uses SysUtils;
Var Fl, Fm: File;
         P: Pointer;
         S: String;
Fp, Sz, Fs: LongInt;
 Cnt, I, J, W: Word;
Begin
  WriteLn('Liero SDN UnPacker');
  WriteLn('Version 1.0');
  WriteLn;
  WriteLn('KorNet');
  WriteLn;
  Assign(Fl, 'liero.snd');
  {$I-}
  Reset(Fl, 1);
  {$I+}
  If IOResult<>0 Then
    Begin
      WriteLn('Can''t open liero.snd!');
      Exit;
    End;
  GetMem(P, $FFFF);
  BlockRead(Fl, Cnt, 2);
  Fp:=2;
  For I:=1 To Cnt Do
    Begin
      S[0]:=#8;
      BlockRead(Fl, S[1], 8);
      While S[Length(S)]=#0 Do Delete(S, Length(S), 1);
      S:=S+'.wav';
      BlockRead(Fl, Fs, 4);
      BlockRead(Fl, Sz, 4);
      Fp:=Fp+16{FilePos(Fl)};
      Seek(Fl, Fs);
      Assign(Fm, S);
      ReWrite(Fm, 1);
      S:='RIFF';
      BlockWrite(Fm, S[1], 4);
      Fs:=Sz+36;
      BlockWrite(Fm, Fs, 4);
      S:='WAVEfmt ';
      BlockWrite(Fm, S[1], 8);
      Fs:=16;
      BlockWrite(Fm, Fs, 4);
      J:=1;
      BlockWrite(Fm, J, 2);
      BlockWrite(Fm, J, 2);
      Fs:=22050;
      BlockWrite(Fm, Fs, 4);
      BlockWrite(Fm, Fs, 4);
      J:=1;
      BlockWrite(Fm, J, 2);
      J:=8;
      BlockWrite(Fm, J, 2);
      S:='data';
      BlockWrite(Fm, S[1], 4);
      BlockWrite(Fm, Sz, 4);
      W:=$FFFF;
      Repeat
        If Sz>=$FFFF Then Sz:=Sz-$FFFF
        Else
          Begin
            W:=Sz;
            Sz:=0;
          End;
        BlockRead(Fl, P^, W);
        For J:=0 To W-1 Do
          Begin
            If Mem[Seg(P^):Ofs(P^)+J]>128 Then Mem[Seg(P^):Ofs(P^)+J]:=Mem[Seg(P^):Ofs(P^)+J]-128
            Else Mem[Seg(P^):Ofs(P^)+J]:=Mem[Seg(P^):Ofs(P^)+J]+128;
          End;
        BlockWrite(Fm, P^, W);
      Until Sz=0;
      Close(Fm);
      Seek(Fl, Fp);
    End;
  FreeMem(P, $FFFF);
  Close(Fl);
End.
```
## Post #23
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-07-03T04:24:36+00:00
- Post Title: 

BlockRead and Blockwrite?  whoa... scary
## Post #24
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-03T14:23:13+00:00
- Post Title: 

Why?
## Post #25
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-03T14:32:19+00:00
- Post Title: 

Rahly you can help me write the program with support of plug-ins for extraction of game archives? (that that similar on MultiEx Commander) or can eat what example of a writing? And that is to be tried and looked as it it is done! You will help?
## Post #26
- Username: Terminus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 27, 2005 12:14 am
- Post datetime: 2005-09-26T16:19:41+00:00
- Post Title: 

Only one problem =)
Most on these programs were stolen from extractor.ru, with edited copyrights 

The original:

> WriteLn('T#i$ PR0GR@M bY -=CHE@TER=-');
>
> WriteLn('HTTP://CTPAX-CHEATER.narod.RU');

thief...
## Post #27
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-26T16:37:30+00:00
- Post Title: 

> Reply from Terminus
>
> Only one problem =)
Most on these programs were stolen from extractor.ru, with edited copyrights 

The original:
WriteLn('T#i$ PR0GR@M bY -=CHE@TER=-');
WriteLn('HTTP://CTPAX-CHEATER.narod.RU');

thief...
Sure .... you read first topic ?
## Post #28
- Username: Terminus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 27, 2005 12:14 am
- Post datetime: 2005-09-26T18:17:06+00:00
- Post Title: 

Yes, you edited it after my post 
I have the original post and screen-shot 

> Greetings to all... I here have thought to share with you source codes on Delphi I think will be useful... Can also you share? 
>
> Let's write MultiEx Commander 2 in Delphi
Don't lie, "programmer" 

[The first page, cashed by Google](http://64.233.183.104/search?q=cache:te6qK7oi0GYJ:forum.xentax.com/viewtopic.php%3Ft%3D1367%26sid%3D2a6b33d6f9c8e43dbd10b663231c41f7+gtasamc&hl=ru&start=4)
## Post #29
- Username: Terminus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 27, 2005 12:14 am
- Post datetime: 2005-09-26T21:54:33+00:00
- Post Title: 

And also...

> Originaled with extractor and cheater
Who is "extractor" and "cheater" ?  What does it mean?

[EXTRACTOR.ru](http://www.extractor.ru) - The biggest Russian unpackers/converters web-site. 

-=CHE@TER=- - An author of great number of useful programs for unpacking/converterng of game resources.

Correct your formal reply, please   , and don't forgive in future about copyrights 

Sorry for my middling English . "As is"
## Post #30
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-26T22:07:08+00:00
- Post Title: 

Actually he is not stealing at all, as he never claimed that he owned the code or anything similar. He did mention where the code came from (note the thread subject) and no material was stolen or whatever as the main applications on this forum are written in other languages (MexCom = VB, GameExtractor = Java) so even if we were to use the code, it would need to be translated over into the appropriate language first.

However, I do agree that he may have somehow breached the software license by posting the source code here - I don't think he did but I havn't really looked at the license for this software, so I wouldn't say he is entirely in the correct here. Regardless, I think its worthy to note that at least he kept all the original comments and names such as extractor.ru in the source code too, if he was trying to steal it or whatever that certainly wouldn't be present.

If you have a problem with the code being posted here or something, then please say so and we will try to rectify the problem, however please try to keep the conversations friendly  .

Oh, and on a similar note, I have used the specification docs from extractor.ru before and they have credit in the About of my program (Game Extractor) because of this, however I don't think I used any of the source code from Game Unpacker in my own program at all (I have a bad track record of trying to convert other languages into Java  )

I hope this clarifies a few things, please let us know if you would like us to rectify any problems.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #31
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-27T00:47:03+00:00
- Post Title: 

2Terminus - kill me
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-27T07:37:47+00:00
- Post Title: 

> Reply from Terminus
>
> And also...
Originaled with extractor and cheater
Who is "extractor" and "cheater" ?  What does it mean?

EXTRACTOR.ru - The biggest Russian unpackers/converters web-site. 

-=CHE@TER=- - An author of great number of useful programs for unpacking/converterng of game resources.

Correct your formal reply, please   , and don't forgive in future about copyrights 

Sorry for my middling English . "As is"

Look, I don't think he really tried to steal anything. I know him, he wouldn't do that at all. It's not his style. When you had asked him where he got it, he would have told you, no hesitation.
## Post #33
- Username: Terminus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 27, 2005 12:14 am
- Post datetime: 2005-09-27T16:30:59+00:00
- Post Title: 

> If you have a problem with the code being posted here or something, then please say so and we will try to rectify the problem, however please try to keep the conversations friendly  .
In my first post i said, that there was only ONE problem - copyrights . Anyone can use, modify and repost source code, but it would be a good idea to note, where sources were given from . No more complaints.
## Post #34
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-28T08:55:33+00:00
- Post Title: 

Kornet, CHE@TER himself complained to me about you too, and I do notice that you have changed certain code to show 'Kornet'.  Please apologize to CHE@TER, and I think he will be satisfied.
## Post #35
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-28T14:16:42+00:00
- Post Title: 

Sorry guys
## Post #36
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-29T06:16:05+00:00
- Post Title: 

> Reply from Terminus
>
> Anyone can use, modify and repost source code, but it would be a good idea to note, where sources were given from . No more complaints.

I agree on that - it would be appropriate to mention where the sources came from, unless they were your own work, obviously. Apart from crediting the correct people, it also means that we know where to look and who to talk to for assistance in these areas.

> Kornet, CHE@TER himself complained to me about you too, and I do notice that you have changed certain code to show 'Kornet'. Please apologize to CHE@TER, and I think he will be satisfied.

This I was not aware of - and this is definately not the right way to do things - I hope and expect that Kornet repair this.

So thats all settled now? I hope so - no sense having a bunch of people arguing about the stuff that links them together in the first place. 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #37
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-29T08:18:27+00:00
- Post Title: 

Yep...to me the matter is closed. Let's all keep up the good work in exploring game archives!
