## Post #1
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2012-06-07T15:49:15+00:00
- Post Title: [PS2] TT Superbikes *.lmp

Good day guys!

can you please help me in unpacking the data for the *.lmp container files?
I've already tried Watto Game Extractor because it has compatibility with baldur's gate *lmp, but unfortunately it didn't work.

here's a link to the file> [http://www.mediafire.com/?3gcwz7633etzavn](http://www.mediafire.com/?3gcwz7633etzavn).

thank you in advanced!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-08T07:38:18+00:00
- Post Title: [PS2] TT Superbikes *.lmp

```
# script for QuickBMS http://quickbms.aluigi.org

get FULLSIZE asize
get FILES long
getdstring NAME 8
get DUMMY long
for i = 0 < FILES
    getdstring NAME 9
    get SIZE long
    get OFFSET threebyte
    math OFFSET *= 0x100
    math SIZE *= 0x100
    log NAME OFFSET SIZE
next i
```
