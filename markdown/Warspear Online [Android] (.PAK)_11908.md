## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-05T11:09:16+00:00
- Post Title: Warspear Online [Android] (*.PAK)

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype bzip2

idstring "MDPK"
get VERSION short
get FILES short
goto 0x18

for i = 0 < FILES
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get FLAG byte
    getdstring NAME 55
	
    if SIZE == ZSIZE
      log NAME OFFSET SIZE
    elif SIZE == 0
      log NAME OFFSET SIZE
    else
      clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #2
- Username: RuneOracle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 04, 2023 2:53 pm
- Post datetime: 2023-09-22T16:36:14+00:00
- Post Title: Warspear Online [Android] (*.PAK)

Just by some odd chance you still dabble in this... Any chance of an update to the newest game version?
