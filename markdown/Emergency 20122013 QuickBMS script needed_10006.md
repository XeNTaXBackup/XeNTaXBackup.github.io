## Post #1
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2013-01-04T12:21:09+00:00
- Post Title: Emergency 2012/2013 QuickBMS script needed

Hello.

Can someone write a very simply BMS script for Emergency 2012/2013 files? All files are LZ compressed and ZLib's deflate unpacks them fine, but I would like to have a batch script to unpack and repack files.

each file has a header of 20 bytes:
DWORD 0x1337C0D3 //magic#1
DWORD 0x00000001
DWORD deflateSize
DWORD 0x00000000
DWORD 0xECC83F2C //magic#2

and followed by LZ-packed data until the end of file.

I would like the script to check magic#1 and magic#2 on all files and unpack (with replace of original) all packed files recursively (including subfolders).

An example files are attached.

Thank you.
[em2012_test.zip](https://xentaxbackup.github.io/file/6111_em2012_test.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-28T14:01:09+00:00
- Post Title: Emergency 2012/2013 QuickBMS script needed

```
get VER long
get SIZE long
get DUMMY long
get DUMMY long
savepos OFFSET
get ZSIZE asize
math ZSIZE -= OFFSET

get TMP basename
get EXT extension
string NAME p= "%s_unpack.%s" TMP EXT
clog NAME OFFSET ZSIZE SIZE
```
## Post #3
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2013-01-28T14:44:18+00:00
- Post Title: Emergency 2012/2013 QuickBMS script needed

Thanks.

Is it possible to force it run recursive on subfolders and make inplace/replacement unpack?

I've altered the script with

```

```

to unpack over existen files and ran it with command line:

```

```


It does go deep into subfolders, but it unpacks all files into current folder. May be I'm missing some option argument?

(using QuickBMS 0.4.8a)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-28T14:50:12+00:00
- Post Title: Emergency 2012/2013 QuickBMS script needed

Emergency 2012 file decompressor

[http://www.nullsecurity.org/gametools](http://www.nullsecurity.org/gametools)

> Reply from Oleg
>
> It does go deep into subfolders, but it unpacks all files into current folder. May be I'm missing some option argument?

(using QuickBMS 0.4.8a)

```
quickbms.exe -9 "C:\em.bms" "C:\Games\E2012\Superarchive.ggg" "C:\Extracted"
```
## Post #5
- Username: Oleg
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 14, 2011 8:31 pm
- Post datetime: 2013-01-28T15:07:35+00:00
- Post Title: Emergency 2012/2013 QuickBMS script needed

strange, it wasn't linked statically against zlib, it took some time to find zlib1.dll...

I get 

```
woops, something went wrong. (FFIND:3)
Done!

```

whichever command I try. even copied some files into c:\temp just to check if it works or not.
