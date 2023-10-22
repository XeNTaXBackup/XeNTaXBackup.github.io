## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T07:08:39+00:00
- Post Title: Soul Order Online HCP archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-23T10:52:06+00:00
- Post Title: Soul Order Online HCP archive

```
# script for QuickBMS

get NAME string
get NAMESZ long
getdstring NAME NAMESZ
get DUMMY long
get OFFSET long
get DUMMY long
get FILES long
math OFFSET += 0x10
goto OFFSET
for i = 0 < FILES
    get NAMESZ long
    getdstring NAME NAMESZ
    get DUMMY byte
    get OFFSET long
    get ZSIZE long
    get SIZE long
    getdstring DUMMY 0x1c
    if SIZE == 0
        log NAME OFFSET ZSIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: bender662
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Apr 07, 2012 1:21 am
- Post datetime: 2012-04-06T17:51:13+00:00
- Post Title: Soul Order Online HCP archive

can you make a packer as well?
