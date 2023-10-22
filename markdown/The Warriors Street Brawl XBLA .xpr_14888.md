## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-19T01:58:19+00:00
- Post Title: The Warriors: Street Brawl XBLA .xpr

Hey guys! I've been trying to track down a copy of this for PC but had no luck, and all I've been able to turn up has been the XBLA version. I was wondering if someone might be able to help me get at the various gang members in this. I've tried a few different scripts and programs supposedly designed wot work with XPR files, but none have worked so far. I could be doing something stupidly wrong, because I'm pretty useless at really cracking these things, but I usually know how to use a tool, which makes me think the file is different somehow. I've attached links to two different samples. Hopefully someone can help me out!

[Characters.xpr](https://mega.nz/#!iVJRHDKL!ZURK_hael3TYHV1ExuRxOOUzpsO0HpKxqBsn0atRH50)
[common.xpr](https://mega.nz/#!7MpShTJL!YwAlrPGOvcOGrpHRQH2XQwG-hEASwkcs3Npni_xtD2s)

Thanks for taking a gander!
## Post #2
- Username: XBLToothPik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 23, 2013 1:44 am
- Post datetime: 2016-08-20T20:36:22+00:00
- Post Title: The Warriors: Street Brawl XBLA .xpr

Not the best, but I made a quick template for the format.  It's very simple.  Compression is ZLIB

```
//--- 010 Editor v7.0.2 Binary Template
//
//      File: XPR
//   Authors: XBLToothPik
//   Version: 0
//   Purpose: Parse XPR File
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------
struct XPR_FileEntry;

string XPR_FileEntry_ReadOffset(DWORD offset)
{
    string s;
    SPrintf(s, "%d", offset + TOCStart);
    return s;
}
string XPR_FileEntry_ReadName(XPR_FileEntry& entry)
{
    return entry.Name;
}


struct XPR_FileEntry{
    char UNK_4CHAR[4];
    DWORD Offset <read=XPR_FileEntry_ReadOffset>;
    DWORD Size;
    DWORD Flags; //Flags (compression..)
    DWORD NameOffset <read=XPR_FileEntry_ReadOffset>;

    local int curPos = FTell();
    FSeek(NameOffset + TOCStart);    
    string Name;
    FSeek(curPos);
};


local int TOCStart;
struct XPR_File_TOC {
    TOCStart = FTell();

    DWORD TocCount;

    XPR_FileEntry FileEntry[TocCount] <optimize=false, name=XPR_FileEntry_ReadName>;
};

struct XPR_File {
    DWORD dwUnk;
    DWORD TocSize;
    DWORD FileSize;
    DWORD dwUnk2;

    XPR_File_TOC TOC;
};

BigEndian();
XPR_File File;
```
## Post #3
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-10T19:39:44+00:00
- Post Title: The Warriors: Street Brawl XBLA .xpr

> Reply from trexjones ↑Fri Aug 19, 2016 9:58 am at Fri Aug 19, 2016 9:58 am
>
> 
Hey guys! I've been trying to track down a copy of this for PC but had no luck, and all I've been able to turn up has been the XBLA version. I was wondering if someone might be able to help me get at the various gang members in this. I've tried a few different scripts and programs supposedly designed wot work with XPR files, but none have worked so far. I could be doing something stupidly wrong, because I'm pretty useless at really cracking these things, but I usually know how to use a tool, which makes me think the file is different somehow. I've attached links to two different samples. Hopefully someone can help me out!

Did you manage to extract the models? I wanted to use other gangs in story mode, for example the Orphans.
I believe that just changing the name of the Warriors files by the Orphans is possible play with other gangs...
