## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-09T10:53:19+00:00
- Post Title: Resident Evil Mercenaries for iPhone

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get FILES long
get NAME_BASE long
get BASE_OFF long

savepos OFF1
math OFF2 = FILES
math OFF2 *= 8
math OFF2 += 0xc

for i = 0 < FILES
    goto OFF1
    get NAME_OFF long
    get NAMESZ long
    savepos OFF1

    math NAME_OFF += NAME_BASE
    goto NAME_OFF
    getdstring NAME NAMESZ

    goto OFF2
    get OFFSET long
    get SIZE long
    savepos OFF2

    math OFFSET += BASE_OFF
    log NAME OFFSET SIZE
next i
```
