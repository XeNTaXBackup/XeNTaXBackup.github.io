## Post #1
- Username: Aliyon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 21, 2009 1:00 pm
- Post datetime: 2009-10-21T06:51:05+00:00
- Post Title: BattleForge PAK Files

I was wondering if anyone would be able to help with unpacking BattleForge PAK files. I've attached one of the files in question.

 bf1_script01.zip
BattleForge PAK file. (84.25 KiB) Downloaded 33 times
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-21T10:03:34+00:00
- Post Title: BattleForge PAK Files

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "PAK\x01"
get INFO_OFF long
get INFO_SIZE long
get INFO_ZSIZE long
clog MEMORY_FILE INFO_OFF INFO_ZSIZE INFO_SIZE

get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    math SIZE -= OFFSET
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Aliyon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 21, 2009 1:00 pm
- Post datetime: 2009-10-21T12:50:21+00:00
- Post Title: BattleForge PAK Files

Man you are awesome.
