## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-23T20:33:53+00:00
- Post Title: FLOCK! (*.FPK)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "FKP."
get VERSION long
get FILES long
get DUMMY long

for i = 0 < FILES
	getdstring NAME 0x38
	get SIZE long
	get OFFSET long
    log NAME OFFSET SIZE
next i
```
