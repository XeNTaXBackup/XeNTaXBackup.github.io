## Post #1
- Username: risy
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 01, 2009 5:45 am
- Post datetime: 2009-09-12T09:03:26+00:00
- Post Title: Unknown Encryption In Cultures Game

Hi   

I've Extracted Certain Files From A 2d stratgey game called cultures using game extractor, i assumed that i will find strings in the files i extracted, but i didn't so it seems encrypted to me, but since i don't know anything about encryption so im here to ask the experts  

you will find the file below
after decryption it should have these strings in it 
extractor,baker,brewer,miller,farmer,hunter,fisherman,potter, if you need a full list pm me
[jobs.zip](https://xentaxbackup.github.io/file/2349_jobs.zip)
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-02-25T19:58:58+00:00
- Post Title: Unknown Encryption In Cultures Game

I created a little converter proggy.
It's a console app, no GUI interface.
Usage:
1. CIF -> TXT conversion:
cif2txt.exe C infile.cif outfile.txt

2. TXT -> CIF conversion:
cif2txt.exe T infile.txt outfile.cif
[cif2txt_modified.zip](https://xentaxbackup.github.io/file/2815_cif2txt_modified.zip)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-02-26T10:17:20+00:00
- Post Title: Unknown Encryption In Cultures Game

care to share the encryption algo?
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-02-26T16:34:43+00:00
- Post Title: Unknown Encryption In Cultures Game

There are some different type of .CIF files, I figured out the two
main, text container formats:

```
Type Cultures_CIF_0041_Type = Packed Record
       ID : Word; // ($41)
       Unk0 : Word; // (1)
       NrOfEntries : Integer; // number of text entries
       NrOfEntries_dup1 : Integer; // The "NrOfEntries" again
       Unk1 : Integer; // ($0A)
       SizeOfIndexTable : Integer; // = NrOfEntries * 4
       ENCODED_INDEXTABLE : Array Of Integer;
       Unk2 : Word; // (1)
       Unk3 : Integer; // ($0A)
       SizeOfTextTable : Integer;
       ENCODED_TEXTTABLE : Array Of Char;
     End;

// note:
// Word: 2 bytes (16 bits)
// Integer: 4 bytes (32 bits)
// Char: 1 byte (8 bits)


// This type of CIF file found in games:
// "Cultures 2" "Northland" "8th Wonder of the World"
Type Cultures_CIF_03FD_Type = Packed Record
       ID : Word; //   ($3FD)
       Unk0 : Array[0..5] Of Byte; // (0)
       Unk1 : Integer; // (1)
       NrOfEntries : Integer; // number of text entries
       NrOfEntries_dup1 : Integer; //  The "NrOfEntries" again
       NrOfEntries_dup2 : Integer; //  The "NrOfEntries" again
       SizeOfTextTable : Integer;
       Unk2 : Integer; // ($3E9)
       Unk3 : Integer; // (0)
       SizeOfIndexTable : Integer; // = NrOfEntries * 4
       ENCODED_INDEXTABLE : Array Of Integer;
       Unk4 : Byte; // (1)
       Unk5 : Integer; // ($3E9)
       Unk6 : Integer; // (0)
       SizeOfTextTable_dup1 : Integer; // The "SizeOfTextTable" again
       ENCODED_TEXTTABLE : Array Of Char;
     End;


// Here is the schematic decoder procedure:
// (Where the BUFFER contains the encoced table)
// Use this algo to decode the ENCODED_INDEXTABLE
// and the ENCODED_TEXTTABLE

Procedure Cultures_CIF_block_decoder;
Var I : Integer;
    B,C,D : Byte;
Begin {Proc. Cultures_CIF_block_decoder}
  C := 71;
  D := 126;
  For I := 0 To BufferSize-1 Do
    Begin
      B := BUFFER[I];
      B := B - 1;
      B := B Xor C;
      C := C + D;  
      BUFFER[I] := B;    
      D := D + 33; 
    End;
End;  {Proc. Cultures_CIF_block_decoder}

```
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-02-26T17:41:16+00:00
- Post Title: Unknown Encryption In Cultures Game

Thanks. I think I also tried to figure out the graphics files but didn't come too far.
Only figured out the archive format: [http://durchschuss.du.funpic.de/index.p ... =cultures2](http://durchschuss.du.funpic.de/index.php?cat=games&site=cultures2)
## Post #6
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-02-27T06:04:17+00:00
- Post Title: Unknown Encryption In Cultures Game

I replaced the converter to a slightly modified version,
so I changed my previously attached file.
Now it handles special chars (#$01 .. #$2F).

And here is the decoder + encoder procedure:

```
Var I : Integer;
    B,C,D : Byte;
Begin {Proc. Cultures_CIF_block_encoder_decoder}
  C := 71;
  D := 126;
  For I := 0 To BufferSize-1 Do
    Begin
      B := BUFFER[I];
      If Mode = CULTURES_CIF_DECODE Then
        Begin
          B := B - 1;
          B := B Xor C;
        End Else
      If Mode = CULTURES_CIF_ENCODE Then
        Begin
          B := B Xor C;
          B := B + 1;
        End;
      C := C + D;
      D := D + 33;
      BUFFER[I] := B;
    End;
End;  {Proc. Cultures_CIF_block_encoder_decoder}


```
## Post #7
- Username: risy
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 01, 2009 5:45 am
- Post datetime: 2011-07-15T22:39:02+00:00
- Post Title: Unknown Encryption In Cultures Game

> Reply from bacter
>
> I replaced the converter to a slightly modified version,
so I changed my previously attached file.
Now it handles special chars (#$01 .. #$2F).

And here is the decoder + encoder procedure:
Code: Select allProcedure Cultures_CIF_block_encoder_decoder;
Var I : Integer;
    B,C,D : Byte;
Begin {Proc. Cultures_CIF_block_encoder_decoder}
  C := 71;
  D := 126;
  For I := 0 To BufferSize-1 Do
    Begin
      B := BUFFER[I];
      If Mode = CULTURES_CIF_DECODE Then
        Begin
          B := B - 1;
          B := B Xor C;
        End Else
      If Mode = CULTURES_CIF_ENCODE Then
        Begin
          B := B Xor C;
          B := B + 1;
        End;
      C := C + D;
      D := D + 33;
      BUFFER[I] := B;
    End;
End;  {Proc. Cultures_CIF_block_encoder_decoder}

Hey Back After All LOL to finish the business , Thank You Bacter For This Utility 
What A Waste The Lib doesn't deserve a crap   , there is nothing to mod, the company is absolutely a fool for a - deciding from the beginning not to let anybody innovate something for the game.
     b - Not Continuing To Develop The Game
I have Examined The Cif's there is nothing worth the trouble, it's all filled with magic numbers and words
anyway, good job  , thx again sorry for bumping
## Post #8
- Username: wae5465
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 14, 2014 2:15 am
- Post datetime: 2014-09-14T08:52:54+00:00
- Post Title: Unknown Encryption In Cultures Game

Hi everyone!

I encountered a problem while using Cif2Txt. I cannot convert a txt file to cif.

```

------------------------------------------------------------------------------
 Cultures CIF <-> TXT converter v1.2
 Created by The Bacter - the.bacter@gmail.com
------------------------------------------------------------------------------


 Error :-(
```


What can I do?
