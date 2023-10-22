## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-13T16:28:05+00:00
- Post Title: Evocron Legends EXE archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-13T19:43:05+00:00
- Post Title: Evocron Legends EXE archive

this is the fast way, the long good way would be to analyze the PE header and going after the last section... too long.

```
math OFFSET -= 4
for
    goto OFFSET
    get NAMESZ long
    if NAMESZ <= 0
        cleanexit
    endif
    getdstring NAME NAMESZ
    get SIZE long
    savepos OFFSET
    log NAME OFFSET SIZE
    math OFFSET += SIZE
next
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-17T02:52:54+00:00
- Post Title: Evocron Legends EXE archive

Thanks Luigi! I'm amazed as always...
