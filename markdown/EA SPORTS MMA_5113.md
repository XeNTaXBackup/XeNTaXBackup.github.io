## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-30T18:19:05+00:00
- Post Title: EA SPORTS MMA

quickbms script for these archives.

```
get idstring long
get version long
get unk long
get files long
getdstring null 0x3C
for i = 0 < files
getdstring null 0xA
get offset THREEBYTE
math offset * 8
get zsize THREEBYTE
get size THREEBYTE
math size + zsize
getdstring name 0x3C
clog name offset zsize size
next i


```
