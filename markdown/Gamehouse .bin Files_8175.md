## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2012-02-02T22:50:44+00:00
- Post Title: Gamehouse .bin Files

This archive is used by GameHouse. It isn't compressed or encrypted. This one is from Bounce Out Blitz. Could someone help me unpack it? Download: [http://www.mediafire.com/download.php?6lb9cfzucnn1ew1](http://www.mediafire.com/download.php?6lb9cfzucnn1ew1)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-03T09:51:43+00:00
- Post Title: Gamehouse .bin Files

```
# script for QuickBMS http://quickbms.aluigi.org

get SIZE long
get DUMMY long
get FILES long
for i = 0 < FILES
    get NAMESZ byte
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
