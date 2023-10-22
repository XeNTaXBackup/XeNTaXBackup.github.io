## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T19:45:52+00:00
- Post Title: Soul Master

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T22:49:23+00:00
- Post Title: Soul Master

I don't understand how to retrieve the starting offset because there are some data ("CHAR") between the end of the file entries and the real offset... really a boring file format.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T23:35:24+00:00
- Post Title: Soul Master

Can you post the format you have found so far? 
I'll look around for other files, or maybe parse the entire file directly.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-16T23:41:30+00:00
- Post Title: Soul Master

the following, except the "skip the stupid CHAR stuff!!!" command obviously :)

```
get DUMMY long
for EXTRACT = 0 < 2
    goto 8
    get FILES long
    for i = 0 < FILES
        get NAME string
        get SIZE long
        get DUMMY long
    next i
    get DUMMY byte
    get FILES long
    for i = 0 < FILES
        get NAME string
        get SIZE long
        get DUMMY long
        if EXTRACT != 0
            log NAME OFFSET SIZE
            math OFFSET += SIZE
            savepos TMP
            goto OFFSET
            get NAME string
            savepos OFFSET
            goto TMP
        endif
    next i
    getdstring CHAR 4
    get DUMMY long

    skip the stupid CHAR stuff!!!

    savepos OFFSET
next EXTRACT
```
so it's all complete except the retrieving of the offset of the first file, it's horrible to be blocked for a so stupid thing
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-17T03:12:59+00:00
- Post Title: Soul Master

well this maybe can help.

structure NPK

```
//--- 010 Editor v3.0.6 Binary Template
//
// File: npk
// Author: Genz
// Revision: 2010-08-10
// Purpose: unpack npk
//--------------------------------------

struct FileRec                      // variable structure size for decrypted npk
{
    uint FileOffset;                // File offsets in NPK
    uint PackedFileSize;
    uint UnpackedFileSize;
    uint Flags <format=binary>;     // not important
    time_t CreateTime;
    uint Zero;                      // Always zero
    uint StrSize;                   // Size of file name
    char FileName[StrSize];
    
    //-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
    local uint64 Offset = FTell();
    FSeek(FileOffset);
    ubyte FileData[PackedFileSize];
    FSeek(Offset);
};

struct NpkHeader                    // NPK
{
    char Signature[4];              // NPK! 
    uint HeaderSize;                // always 24
    uint FileCount;
    uint OffsetToNames <format=hex>;
    uint FirstFileOffset;           // = HeaderSize
    time_t FileCreationTime;
};

NpkHeader Header;
FSeek(Header.OffsetToNames);
FileRec File[Header.FileCount] <optimize=false>;
```

[SoulMaster NPK Extractor 1.1](http://www.mediafire.com/download.php?489ro74gdb6abe8)
## Post #6
- Username: pentingloh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 26, 2011 3:55 pm
- Post datetime: 2012-02-28T11:01:34+00:00
- Post Title: Soul Master

Whta kind a file is gsga? I tried to open it in several 3d program but it's always failed.
Anyone know how to open this file?

Thanks
## Post #7
- Username: g3stapo
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 21, 2019 6:59 am
- Post datetime: 2020-11-17T11:21:43+00:00
- Post Title: Soul Master

> Reply from aluigi ↑Fri Feb 17, 2012 7:41 am at Fri Feb 17, 2012 7:41 am
>
> 
the following, except the "skip the stupid CHAR stuff!!!" command obviously 
Code: Select allidstring "GSGA"
get DUMMY long
for EXTRACT = 0 < 2
    goto 8
    get FILES long
    for i = 0 < FILES
        get NAME string
        get SIZE long
        get DUMMY long
    next i
    get DUMMY byte
    get FILES long
    for i = 0 < FILES
        get NAME string
        get SIZE long
        get DUMMY long
        if EXTRACT != 0
            log NAME OFFSET SIZE
            math OFFSET += SIZE
            savepos TMP
            goto OFFSET
            get NAME string
            savepos OFFSET
            goto TMP
        endif
    next i
    getdstring CHAR 4
    get DUMMY long

    skip the stupid CHAR stuff!!!

    savepos OFFSET
next EXTRACTso it's all complete except the retrieving of the offset of the first file, it's horrible to be blocked for a so stupid thing

can you do it?
