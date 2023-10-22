## Post #1
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-10-14T14:38:23+00:00
- Post Title: Planet Alcatraz .PAK and .BM

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-14T14:45:39+00:00
- Post Title: Planet Alcatraz .PAK and .BM

```
get DUMMY long
for i = 0 < FILES
    getdstring NAME 0x80
    get SIZE long
    get ZSIZE long
    get OFFSET long
    getdstring DUMMY 12
    get ZIP long

    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
