## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-11T01:23:06+00:00
- Post Title: Achtung Panzer *.flatdata

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-11T07:46:25+00:00
- Post Title: Achtung Panzer *.flatdata

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "AZP"
get VER byte
get FILES long
get INFO_OFF long
get DUMMY long
get INFO_SIZE long
math INFO_OFF *= 8
math INFO_OFF += 0x40
goto INFO_OFF
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get DUMMY long
    get SIZE long
    padding 16
    getdstring NAME 32
    getdstring TYPE 32
    getdstring PATH 32
    set FULLNAME string PATH
    string FULLNAME += /
    string FULLNAME += NAME
    string FULLNAME += .
    string FULLNAME += TYPE
    log FULLNAME OFFSET SIZE
next i
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-12T22:21:07+00:00
- Post Title: Achtung Panzer *.flatdata

The contents of this post was deleted because of possible forum rules violation.
