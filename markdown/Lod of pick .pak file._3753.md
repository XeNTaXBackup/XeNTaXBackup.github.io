## Post #1
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2009-09-30T01:20:03+00:00
- Post Title: Lod of pick .pak file.

I am looking for a unpacker for the pak files in the game GearGrinder.I'm not sure if I need to repack the files.
Some body knows how to unpack those files? Or a tool that can unpack those files?
I uploaded some pak files, hope some body can try it.

[http://www.yourfilelink.com/get.php?fid=509577](http://www.yourfilelink.com/get.php?fid=509577)
[http://www.yourfilelink.com/get.php?fid=509576](http://www.yourfilelink.com/get.php?fid=509576)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-08T18:06:26+00:00
- Post Title: Lod of pick .pak file.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "PK\x01\x09"
get INFO_OFF long
goto INFO_OFF

get PAKSIZE asize
for
    if INFO_OFF >= PAKSIZE
        cleanexit
    endif
    get DUMMY long
    get DUMMY long
    get ZIP byte
    get DUMMY long
    get NAMESZ short
    getdstring UNAME NAMESZ
    set NAME unicode UNAME
    get SIZE long
    get ZSIZE long
    get OFFSET long
    savepos INFO_OFF

    math OFFSET += 22
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next
```
can you confirm that the correct name of the game is Gear Grinder?
## Post #3
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2009-10-09T01:23:08+00:00
- Post Title: Lod of pick .pak file.

> Reply from Bugtest
>
> Code: Select all# Gear Grinder
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "PK\x01\x09"
get INFO_OFF long
goto INFO_OFF

get PAKSIZE asize
for
    if INFO_OFF >= PAKSIZE
        cleanexit
    endif
    get DUMMY long
    get DUMMY long
    get ZIP byte
    get DUMMY long
    get NAMESZ short
    getdstring UNAME NAMESZ
    set NAME unicode UNAME
    get SIZE long
    get ZSIZE long
    get OFFSET long
    savepos INFO_OFF

    math OFFSET += 22
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
nextcan you confirm that the correct name of the game is Gear Grinder?

Yes,thanks very much.
## Post #4
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-12-08T09:00:13+00:00
- Post Title: Lod of pick .pak file.

I tried to use this bms script in Gear Grinder's "lockit.pak" and I get the following message error:

"signature doesn't match the one expected by the script"
This one: "KAPT"
expected: "PK(simbol)      "

Here is head and tail of lockit.pak:

[http://www.mediafire.com/?cgbz3a49j5oje7q](http://www.mediafire.com/?cgbz3a49j5oje7q)

Help would be much appreciated.

Regards.
## Post #5
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-02-03T14:55:37+00:00
- Post Title: Lod of pick .pak file.

Still looking for extractor for 'KAPT' files?
