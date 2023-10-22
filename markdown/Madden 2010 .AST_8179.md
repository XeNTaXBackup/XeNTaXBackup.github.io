## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-02-03T04:24:45+00:00
- Post Title: Madden 2010 *.AST

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-03T09:33:03+00:00
- Post Title: Madden 2010 *.AST

I don't know if it's an archive or something like a video plus an index.
the video probably starts from offset 0x1f590 or similar.
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-02-03T09:40:51+00:00
- Post Title: Madden 2010 *.AST

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-03T16:17:19+00:00
- Post Title: Madden 2010 *.AST

good, job done:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BGFA"
get DUMMY long
get DUMMY long
get FILES long
get OFFSET long
goto OFFSET
get NAME string
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get ZSIZE long
    get SIZE threebyte
    get DUMMY byte
    get DUMMY byte
    math OFFSET *= 0x10
    if SIZE == 0
        log "" OFFSET ZSIZE
    else
        math SIZE += ZSIZE
        clog "" OFFSET ZSIZE SIZE
    endif
next i
```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-10T20:18:42+00:00
- Post Title: Madden 2010 *.AST

*edit* the script was perfect :)

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BGFA"
getdstring VER 4
get DUMMY long
get FILES long
get OFFSET long
goto OFFSET
getdstring DUMMY 12
for i = 0 < FILES
    getdstring DUMMY 10
    get OFFSET long
    get ZSIZE threebyte
    get SIZE threebyte
    getdstring NAME 0x2a
    math OFFSET *= 8
    if SIZE == 0
        log NAME OFFSET ZSIZE
    else
        math SIZE += ZSIZE
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #6
- Username: sdot
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 19, 2012 7:30 am
- Post datetime: 2012-05-18T16:09:45+00:00
- Post Title: Madden 2010 *.AST

Got it figured out aluigi, the archive we were working with was damaged. Tried a new dump of the game and the script worked like a charm. So change your script to "does work extremely well". Thanks, you're awesome.
