## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-03-18T16:05:28+00:00
- Post Title: Post Apocalyptic Mayhem .dat files

Hello,

I just bought this game and i want to extract the files from this archive:
[http://www.sendspace.com/file/rmrlx2](http://www.sendspace.com/file/rmrlx2)
This game use zlib for compression.

Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-18T21:30:15+00:00
- Post Title: Post Apocalyptic Mayhem .dat files

scripts for QuickBMS, the first for the fs* files and the second for the header/content files:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get FULLSIZE asize
for OFFSET = 0 < FULLSIZE
    get NAMESZ short
    getdstring NAME NAMESZ
    get SIZE long
    savepos OFFSET
    log NAME OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next
```

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDSE "header.dat" 0
idstring CSPR
get FILES long
math NAME_OFF = FILES
math NAME_OFF *= 0x10
math NAME_OFF += 0x8
math NAME_OFF += 0x4    # DEPR
math OLD_CONTENT = -1
for i = 0 < FILES
    get CONTENT long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    savepos TMP
    goto NAME_OFF
    get NAMESZ short
    getdstring NAME NAMESZ
    getdstring DUMMY 0xc
    savepos NAME_OFF
    goto TMP
    if CONTENT != OLD_CONTENT
        string CNAME p= "content_%02x.dat" CONTENT
        open FDSE CNAME 1
        math OLD_CONTENT = CONTENT
    endif
    clog NAME OFFSET ZSIZE SIZE 1
next i
```
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-12T05:41:40+00:00
- Post Title: Post Apocalyptic Mayhem .dat files

And how to pack these files again?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-16T17:40:53+00:00
- Post Title: Post Apocalyptic Mayhem .dat files

use quickbms and the same script following the steps explained here (obviously it's another game but it's the same):
[viewtopic.php?p=52546#p52546](http://forum.xentax.com/viewtopic.php?p=52546#p52546)
## Post #5
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-17T01:55:22+00:00
- Post Title: Post Apocalyptic Mayhem .dat files

Tanks Aluigi! You are the best!!!
## Post #6
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-19T05:01:09+00:00
- Post Title: Post Apocalyptic Mayhem .dat files

Repack of Header.dat not work.
