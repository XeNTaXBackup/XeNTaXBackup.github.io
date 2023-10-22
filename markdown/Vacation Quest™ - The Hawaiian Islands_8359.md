## Post #1
- Username: xentaxus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 16, 2011 2:59 pm
- Post datetime: 2012-02-21T04:28:51+00:00
- Post Title: Vacation Quest™ - The Hawaiian Islands

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-21T12:18:15+00:00
- Post Title: Vacation Quest™ - The Hawaiian Islands

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzma86head
get FILES long
for EXTRACT = 0 < 2
    goto 4
    for i = 0 < FILES
        get OFFSET long
        get SIZE long
        get ZSIZE long
        get NAMESZ long
        math NAMESZ *= 2
        getdstring NAME NAMESZ
        padding 4
        if EXTRACT != 0
            math OFFSET += BASE_OFF
            set NAME unicode NAME
            string NAME R= "_" "/"
            if ZSIZE == SIZE
                log NAME OFFSET SIZE
            else
                clog NAME OFFSET ZSIZE SIZE
            endif
        endif
    next i
    savepos BASE_OFF
next EXTRACT
```
## Post #3
- Username: xentaxus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 16, 2011 2:59 pm
- Post datetime: 2012-02-21T15:03:59+00:00
- Post Title: Vacation Quest™ - The Hawaiian Islands

thank you aluigi
