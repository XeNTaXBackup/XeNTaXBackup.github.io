## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2011-05-01T15:20:07+00:00
- Post Title: Amazing aventures forgoten dinasty

Hello friends i need the code to .z file.
  i need the code to decompress, Thanks

[http://www.megaupload.com/?d=FE6KH137](http://www.megaupload.com/?d=FE6KH137)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-01T16:12:45+00:00
- Post Title: Amazing aventures forgoten dinasty

*edit* the name of the game is Amazing Adventures The Forgotten Dynasty
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-01T16:28:03+00:00
- Post Title: Amazing aventures forgoten dinasty

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype lzma86head
get FILES long
for EXTRACT = 0 < 2
    goto 4
    for i = 0 < FILES
        get OFFSET long
        get XSIZE long
        get SIZE long
        get ZSIZE long
        get DUMMY longlong
        get NAMESZ long
        math NAMESZ *= 2
        getdstring NAME NAMESZ
        set NAME unicode NAME
        padding 4
        if EXTRACT != 0
            math OFFSET += BASE_OFF
            if SIZE == ZSIZE
                log NAME OFFSET SIZE
            else
                clog NAME OFFSET ZSIZE SIZE
            endif
        endif
    next i
    savepos BASE_OFF
next EXTRACT
```
