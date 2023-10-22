## Post #1
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-21T23:42:17+00:00
- Post Title: Manhunt 2 MDL/DFF

-
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-07-22T05:36:01+00:00
- Post Title: Manhunt 2 MDL/DFF

They are just the same format and compressd with zlib
you can decompressed them with this BMS

```
# by Fatduck    Jul2013
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "Z2HM"
get USIZE long
get RESNAME basename
get RESEXT fileext
string RESNAME += _dec.
string RESNAME += RESEXT
get CSIZE asize
math CSIZE -= 8
clog RESNAME 8 CSIZE USIZE
```


The actual models format is pretty straight forward.
DIY mate!
## Post #3
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-23T18:12:24+00:00
- Post Title: Manhunt 2 MDL/DFF

-
