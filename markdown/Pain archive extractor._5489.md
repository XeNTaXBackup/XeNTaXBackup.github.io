## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-04T01:29:10+00:00
- Post Title: Pain archive extractor.

```
#PAIN ps3
#from chrrox

endian big

open FDDE PAK 0
open FDDE DAT 1


set offset 0
get files long 1
get id long 1
for i = 0 < files
    get SIZE long 1
    getdstring name 0xFC 1
        log name offset size
    math offset + size
next i
```
