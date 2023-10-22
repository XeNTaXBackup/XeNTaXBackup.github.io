## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-06-18T14:13:07+00:00
- Post Title: 倩女幽魂 Online .wdf file

Free MMO

Name: 倩女幽魂
HP: [http://qn2.163.com/](http://qn2.163.com/)
DL page: [http://qn2.163.com/download/](http://qn2.163.com/download/)
Direct link: [http://qn.gdl.netease.com/qnyh-2.0.31.exe](http://qn.gdl.netease.com/qnyh-2.0.31.exe)

Could you please look at this *.wdf file,THX!!!
[shader.rar](https://xentaxbackup.github.io/file/6474_shader.rar)
## Post #2
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-09-30T13:39:26+00:00
- Post Title: 倩女幽魂 Online .wdf file

can someone help?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-30T14:21:16+00:00
- Post Title: 倩女幽魂 Online .wdf file

Maybe half floats, nothing clear. Don't see face indices. In the header an offset 0xC377 +(0xC?) to the file end.

What do you expect to be in it?
## Post #4
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-09-30T14:31:14+00:00
- Post Title: 倩女幽魂 Online .wdf file

need help with unpacking archives in this game. could u try to extract them??   REQ unpacking.wdf file QuickBMS script。thanks！！！
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-30T14:41:39+00:00
- Post Title: 倩女幽魂 Online .wdf file

> Reply from mappy2012
>
> need help with unpacking archives in this game. could u try to extract them??   REQ unpacking.wdf file QuickBMS script。thanks！！！Nope, sry. That's not my preferred subject. Just answered 'cause noone answered so far.

You could try comtype_scan2 from Aluigi/quickbms. (Why let others do your work?  )
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-30T14:52:52+00:00
- Post Title: 倩女幽魂 Online .wdf file

Basic info

```
{
	DWORD	pID; //PFDW
	DWORD	pUnknown1;
	DWORD	pUnknown2;
	DWORD	pEntryOffset;
};
```


```
{
	DWORD	pHash;
	DWORD	pOffset;
	DWORD	pZSize;
	DWORD	pSize;
	DWORD	pNulls;
};
```


Script for unpack (can't decompress files)

```
#
# Written by Ekey (h4x0r)
# http://forum.xentax.com
#
# script for QuickBMS http://quickbms.aluigi.org

idstring "PFDW"
get UNKNOWN long
get FILES long
get ENTRYOFFSET long

goto ENTRYOFFSET

for i = 0 < FILES
    get HASH long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get NULLS long
    string NAME p= "%08X" HASH
    log NAME OFFSET ZSIZE
next i
```

Encryption

```
    0xEB, 0xC2, 0xDC, 0xC3, 0xC4, 0xB5, 0xD2, 0xCA,
    0xF7, 0xD7, 0xA4, 0xB9, 0xF0, 0xBB, 0xD7, 0xC0};

    for (int i = 0; i < pZSize; i++)
    pBuffer[i] ^= GSOKey[i & 0xF];
```

Compression
LZMA

```
#define LZMA_HEADER_SIZE	(LZMA_PROPS_SIZE + 3)
```
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-30T19:20:12+00:00
- Post Title: 倩女幽魂 Online .wdf file

Done. Filenames currently can't be detected. Decompress function implemented.



Win7/8 not tested.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-30T20:45:20+00:00
- Post Title: 倩女幽魂 Online .wdf file

New fixed version. Now it works fine
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-05T15:46:57+00:00
- Post Title: 倩女幽魂 Online .wdf file

Fixed problem with extracting sound files. About hashes - seems they used same system like game JianLong. I don't know how it work 
[GSOUnpacker_0.4.rar](https://xentaxbackup.github.io/file/6671_GSOUnpacker_0.4.rar)
## Post #10
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-06T03:35:26+00:00
- Post Title: 倩女幽魂 Online .wdf file

> Reply from Ekey
>
> Fixed problem with extracting sound files. About hashes - seems they used same system like game JianLong. I don't know how it work

cool~~THX!!!Works perfect！You are God！
