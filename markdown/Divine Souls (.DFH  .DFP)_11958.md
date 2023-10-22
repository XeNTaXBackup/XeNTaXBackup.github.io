## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-14T18:16:35+00:00
- Post Title: Divine Souls (*.DFH / *.DFP)

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

open FDDE DFH 0
open FDDE DFP 1

get VERSION long 0

if VERSION != 0x1A
    print "Invalid package version!"
    cleanexit
endif

get FILES long 0
get NULL long 0

for i = 0 < FILES
    get SIZE long 0
    get HASH long 0
    get OFFSET long 0
    string NAME p= "%08X" HASH
    log NAME OFFSET SIZE 1
next i
```
## Post #2
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2016-07-28T06:09:23+00:00
- Post Title: Divine Souls (*.DFH / *.DFP)

Could u make a file list as there r thousands file to access!!! Thanks in advance
