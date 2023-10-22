## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-08-16T00:58:46+00:00
- Post Title: /PC/ Anomaly: Warzone Earth .dat Archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-04T16:49:33+00:00
- Post Title: /PC/ Anomaly: Warzone Earth .dat Archives

*script updated*

script for quickbms:

```

comtype unzip_dynamic
get FULLSIZE asize
putvarchr MEMORY_FILE FULLSIZE 0
log MEMORY_FILE 0 0
for OFFSET = 0 < FULLSIZE
    math OFFSET += 10
    goto OFFSET
    findloc SIZE string "\x1f\x8b\x08" 0 ""
    if SIZE == ""
        math SIZE = FULLSIZE
    endif
    math SIZE -= OFFSET
    clog "" OFFSET SIZE SIZE
    math OFFSET += SIZE
next
```
