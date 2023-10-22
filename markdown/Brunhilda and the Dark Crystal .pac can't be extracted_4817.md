## Post #1
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2010-07-28T06:24:00+00:00
- Post Title: Brunhilda and the Dark Crystal *.pac can't be extracted

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-28T08:02:41+00:00
- Post Title: Brunhilda and the Dark Crystal *.pac can't be extracted

script for QuickBMS:

```
get FILES long
for i = 0 < FILES
    get NAMESZ short
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
