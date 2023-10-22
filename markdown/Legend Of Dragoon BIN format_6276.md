## Post #1
- Username: azraelaxel
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 24, 2011 10:01 am
- Post datetime: 2011-03-24T02:08:36+00:00
- Post Title: Legend Of Dragoon BIN format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-24T13:49:52+00:00
- Post Title: Legend Of Dragoon BIN format

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "MRG\x1a"
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    math OFFSET *= 0x800
    log "" OFFSET SIZE
next i
```
## Post #3
- Username: azraelaxel
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 24, 2011 10:01 am
- Post datetime: 2011-03-24T19:59:27+00:00
- Post Title: Legend Of Dragoon BIN format

Thx A LOT!! works very good!!!
