## Post #1
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2010-07-25T01:49:33+00:00
- Post Title: Grace's Quest: To Catch An Art Thief *.pak can't be extract

The head-of-file is "$PAK$z? *Package Builder v1.0 Coded by Rui Barbosa."
I've tried many extrators, but they are no use at all.
Thanks.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-25T05:43:34+00:00
- Post Title: Grace's Quest: To Catch An Art Thief *.pak can't be extract

you need to post a sample file.
## Post #3
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-25T09:25:50+00:00
- Post Title: Grace's Quest: To Catch An Art Thief *.pak can't be extract

This is the structure of the game's "Graphics.pak" file:

```
   -> DataStartPos : DWORD; // points to the start of the file data
   -> Comment: B_String; // 'Package Builder v1.0 Coded by Rui Barbosa.'
   -> NrOfDirs : DWORD;
       for each Dir:
         Dir_Name : B_String  // example: 'Graphics\GUI\Briefing\'
         NrOfFilesInDir : DWORD;
            for each file:
              File_Name : B_String // example: 'HH_MenuButtonOff_01.pec'
              File_Size : DWORD;
              File_StartPos : DWORD;
              Unk0 : DWORD; // (0)
              Unk1 : DWORD; // (1)
   -> file data: all files are encoded. .JEC files are encoded JPG files, PEC files are encoded PNG files.

  note #1: B_String means this structure:
                -> Length : Byte
                -> Chars : Array[0..Length-1] Of Chars

  note #2: 
   This is the password of the file decoding:
   Const PW : Array[0..47] Of Byte =
            ($CE,$ED,$66,$66, $CC,$0D,$00,$0B,  $03,$73,$00,$83, $00,$0C,$00,$0D,
             $00,$08,$11,$1F, $88,$89,$00,$0E,  $DC,$CC,$6E,$E6, $DD,$DD,$D9,$99,
             $BB,$BB,$67,$63, $6E,$0E,$EC,$CC,  $DD,$DC,$99,$9F, $BB,$B9,$33,$3E);
  The decoding process:
   For I := 0 To Length(Buffer)-1 Do
     Buffer[I] :=  Buffer[I] - PW[I mod PW_Length];
```

[GracesQuest_PAKextr.rar](https://xentaxbackup.github.io/file/3270_GracesQuest_PAKextr.rar)
