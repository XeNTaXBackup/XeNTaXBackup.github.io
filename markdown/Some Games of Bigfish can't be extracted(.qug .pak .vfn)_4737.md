## Post #1
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2010-07-11T11:08:43+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-11T19:51:15+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Mystery Age - The Imperial Staff
Data.qug password: www#quarterdigi@com
Local.xxx password: bigfish

Ancient Wonderland
Data.qug the password is the same as above: www#quarterdigi@com

Wizard Land .PAK files (not fully tested yet):

```
  ... read the whole file to the Buffer, and ...
  For I := 0 To FILE_SIZE - 1 Do
    Buffer[I] := Buffer[I] Xor (3*I) Xor 166;

 The (possible) structure of the decoded PAK file:
-> Header: (8 bytes)
    - ID : DWORD;   // $BAC04AC0
    - Zero : DWORD; // 0
-> Directory:
     REPEAT
       - Flag: Byte;
       if Flag==0
          - FileNameLen : Byte;
          - FileName : Array Of Char; // example: 'images\backgrounds\background_01.jpg'
          - FileSize : DWORD;
          - FileTime : TFileTime; // 8 bytes long, Windows _FILETIME format
       else if Flag==$80
         END_OF_THE_DIRECTORY
       endif
     UNTIL END_OF_THE_DIRECTORY  
-> File_Data

```

Magic Encyclopedia First Story "magic.vfn" file WORK-IN-PROGRESS

```
     -ID : Array[0..3] Of Char; // 'ASDb'
     -Something : DWORD; // nr of files???
     -DirectoryStartPos : DWORD; // Points to the end of the file
     -Unknown1 : DWORD; // 03 00 31 07
     -Unknown2 : DWORD; // 08 00 44 53
     -Unknown3 : DWORD; // 00 00 34 86
     -Unknown4 : DWORD; // 88 85 B8 3A
     -Unknown5 : DWORD; // E3 40 55 3F
     -Unknown6 : DWORD; // FB 61 E1 2A
     -Unknown7 : DWORD; // CB 6D 29 52
     -Unknown8 : DWORD; // E3 C9 AD F0
-> SomethingAfterHeader (12 bytes)
     -SomeBytes : Array[0..11] Of Byte; // 40 87 00 00 00 00 00 00 00 00 00 00
-> FILE_DATA, ZLIB compression???
-> Directory, for each file:
      -FileNameLen : DWORD;
      -FileName : Array Of Char;
      -RelativeStartPos : DWORD; // relative from the Header's end, so add 44 to this value to get the real filestartpos

```
## Post #3
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2010-07-13T07:29:48+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Thanks for your password.
Could you please give the .exe for the other two games?
Thanks a lot.
## Post #4
- Username: Relict
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 12, 2010 5:49 am
- Post datetime: 2011-01-10T11:22:31+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Please Help with password for Mystery Age: The Dark Priests
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2011-01-14T01:14:21+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Is there any news for Magic Encyclopedia First Story "magic.vfn" extractor?
## Post #6
- Username: lery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 26, 2011 5:25 pm
- Post datetime: 2011-01-26T09:29:20+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Please    help with password for Kingdom of Seven Seals
## Post #7
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2011-08-04T10:42:09+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Please, help me with unpacking .*vfn file

[https://rapidshare.com/files/2027574513/LC2.vfn](https://rapidshare.com/files/2027574513/LC2.vfn)
[1.jpg](https://xentaxbackup.github.io/file/4580_1.jpg)
## Post #8
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2011-08-16T02:12:27+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

Up!
## Post #9
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-03-04T12:53:09+00:00
- Post Title: Some Games of Bigfish can't be extracted(*.qug *.pak *.vfn)

and any working code ?
