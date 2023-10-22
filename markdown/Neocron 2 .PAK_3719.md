## Post #1
- Username: xmurik
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 17, 2009 2:33 am
- Post datetime: 2009-09-16T18:57:27+00:00
- Post Title: Neocron 2 *.PAK

Hi, can anyone here make a unpacker\packer for this kind of file???

thx for the attention!

[Scripts.pak](http://rapidshare.com/files/280998185/scripts.pak.html) ~2 Mb
or
[Language.pak](http://rapidshare.com/files/281001814/language.pak.html) ~44 Mb
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-09-17T09:48:26+00:00
- Post Title: Neocron 2 *.PAK

This is a container file. The contained files compressed with zlib. I don't know about editor.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-17T09:54:24+00:00
- Post Title: Neocron 2 *.PAK

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "\xde\x8c\x45\x3d"
get FILES long
for i = 0 < FILES
    get ENTRYSZ long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get NAMESZ long
    getdstring NAME NAMESZ
    if SIZE == 0
        log NAME OFFSET SIZE
    else if SIZE == ZSIZE
        log NAME OFFSET ZSIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
the check of "if SIZE == 0" in reality is not needed, it's a work-around for a small bug in quickbms that I will fix today
## Post #4
- Username: xmurik
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 17, 2009 2:33 am
- Post datetime: 2009-09-17T12:03:10+00:00
- Post Title: Neocron 2 *.PAK

Thx Bugtest !!! 

Archive unpacked. But I need packer   
can you help me ?

thx for the attention
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-17T17:54:36+00:00
- Post Title: Neocron 2 *.PAK

no I can't, I make only scripts for quickbms (so extraction)
