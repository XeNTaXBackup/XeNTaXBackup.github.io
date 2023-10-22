## Post #1
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2010-04-29T11:22:37+00:00
- Post Title: ChangChun2 online .ygj file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-29T16:32:45+00:00
- Post Title: ChangChun2 online .ygj file

they are only compressed dds files:

```
savepos OFFSET
get ZSIZE asize
math ZSIZE -= OFFSET
get NAME basename
string NAME += ".dds"
clog NAME OFFSET ZSIZE SIZE
```
## Post #3
- Username: cloudslsw
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 04, 2010 5:37 pm
- Post datetime: 2012-03-29T01:51:18+00:00
- Post Title: ChangChun2 online .ygj file

thanks aluigi,this is also working for sound files
