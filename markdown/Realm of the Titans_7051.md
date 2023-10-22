## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-25T03:11:03+00:00
- Post Title: Realm of the Titans

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-25T03:40:37+00:00
- Post Title: Realm of the Titans

its a really easy format its using inflate compression if o one else does it sometime tomorrow i can make a script.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-04T16:04:22+00:00
- Post Title: Realm of the Titans

script for quickbms:

```

comtype deflate
for
    get PK long
    if PK != 0x04034b50
        cleanexit
    endif
    get DUMMY short
    get ZSIZE long
    get SIZE long
    get DUMMY short
    get NAMESZ short
    get DUMMY short
    get TYPE short
    getdstring DUMMY 8
    getdstring NAME NAMESZ
    savepos OFFSET
    if TYPE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    math OFFSET += ZSIZE
    goto OFFSET
next
```

or (update):

```
#   maybe other Aeria games too
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
for
    get PK_SIGN long
    if PK_SIGN != 0x04034b50
        cleanexit
    endif
    get DUMMY short
    get ZSIZE long
    get SIZE long
    get ENTRYSZ short
    get NAMESZ short
    get EXTRASZ short
    getdstring ENTRY ENTRYSZ
    getdstring NAME NAMESZ
    getdstring EXTRA EXTRASZ
    savepos OFFSET
    getvarchr METHOD ENTRY 0
    if METHOD == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    math OFFSET += ZSIZE
    goto OFFSET
next
```
