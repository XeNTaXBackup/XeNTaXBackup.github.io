## Post #1
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-21T10:43:04+00:00
- Post Title: Megamind pac file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-21T11:13:32+00:00
- Post Title: Megamind pac file

Why not say the game Megamind
## Post #3
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-21T11:22:11+00:00
- Post Title: Megamind pac file

No!
Pack and Unpack the file I want.
------------------------------------
This means to open the archive file is opened later ascribe to the pristine state.
Changed I want some texture.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-21T11:40:20+00:00
- Post Title: Megamind pac file

script for quickbms:

```
# simply dump each encrypted UDP packet sent/received from *.quazal.net in a file and pass it to this script

comtype xmemdecompress
endian big
idstring "pack"
get DUMMY long
get DUMMY long
get OFFSET long
get SIZE long
get NAME_BASE long
get FILES long
math NAME_BASE += OFFSET
goto OFFSET
for i = 0 < FILES
    get OFFSET longlong
    get ZSIZE longlong
    get SIZE longlong
    get NAME_OFF long
    get DUMMY long
    savepos TMP
    math NAME_OFF += NAME_BASE
    goto NAME_OFF
    get NAME string
    goto TMP
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
