## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-11-29T19:12:23+00:00
- Post Title: Sherlock Holmes The Awakening .DAT files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2011-12-08T15:05:17+00:00
- Post Title: Sherlock Holmes The Awakening .DAT files

If you are going to do a translation of the Sherlock Holmes series search this forum for the tool made by bacter.
## Post #3
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2012-01-11T19:03:06+00:00
- Post Title: Sherlock Holmes The Awakening .DAT files

> Reply from 3pacalypse
>
> If you are going to do a translation of the Sherlock Holmes series search this forum for the tool made by bacter.

I did and the tools are unavaliable
## Post #4
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2012-01-14T12:49:42+00:00
- Post Title: Sherlock Holmes The Awakening .DAT files

Any help please?
## Post #5
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2012-01-21T13:34:02+00:00
- Post Title: Sherlock Holmes The Awakening .DAT files

Please any help?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-22T12:16:24+00:00
- Post Title: Sherlock Holmes The Awakening .DAT files

1) don't bump this thread again, if nobody has replied to you till now it means that there is no solution at the moment
2) the files you uploaded have all different formats
3) as far as I know bacter wrote a tool for the pak archives, I'm not aware about tools for locales.dat
4) in absence of alternative I guess the only solution for you is hex editing

alternatively you can use quickbms and the following script for dumping the unicode strings in files and then reimporting those you modify (read section 3 of quickbms.txt) but it's not much different than the hex editing:

```
get DATSIZE asize
for i = 0
    savepos OFFSET
    if OFFSET >= DATSIZE
        cleanexit
    endif
    get NAMESZ byte
    getdstring NAME NAMESZ
    get TYPE long
    get TEST long
    if TYPE == 3
        math SIZE = TEST
        math SIZE *= 2
        savepos OFFSET
        getdstring DATA SIZE
        get DUMMY long
        set DATA unicode DATA
        #print "%DATA%"
        set FNAME string PATH
        string FNAME += /
        string FNAME += i
        string FNAME += _
        string FNAME += NAME
        log FNAME OFFSET SIZE
    elif TYPE == 6
        string PATH = NAME
    endif
next i
```
anyway I repeat, stop bumping this thread because you are even in the wrong section!
