## Post #1
- Username: jaax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 09, 2008 11:43 am
- Post datetime: 2009-03-08T21:58:51+00:00
- Post Title: Killer Loop [Crave ent.][.dat]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-18T20:27:51+00:00
- Post Title: Killer Loop [Crave ent.][.dat]

old thread but the game is enough known and the format is simple, so why not making a bms script for it? :)

```
    get SIZE long
    get OFFSET long
    if OFFSET == 0
        cleanexit
    endif
    get DUMMY long
    get DUMMY long
    getdstring NAME 32

    math OFFSET *= 0x800
    log NAME OFFSET SIZE
next
```
