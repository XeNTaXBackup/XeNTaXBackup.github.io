## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2012-02-02T22:59:43+00:00
- Post Title: Sprout Games .saf Files

This archive is used by Sprout Games. It isn't compressed or encrypted. This one is from Feeding Frenzy 2. Could someone help me unpack it? Download: [http://www.mediafire.com/download.php?ekm8fw4ky2hiysv](http://www.mediafire.com/download.php?ekm8fw4ky2hiysv)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-03T09:39:20+00:00
- Post Title: Sprout Games .saf Files

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "FFAS"
get DUMMY long
get OFFSET long
goto OFFSET
get DUMMY long
getdstring DUMMY 0x10
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    getdstring DUMMY 0x10
    get NAMESZ short
    getdstring NAME NAMESZ
    log NAME OFFSET SIZE
next i
```
