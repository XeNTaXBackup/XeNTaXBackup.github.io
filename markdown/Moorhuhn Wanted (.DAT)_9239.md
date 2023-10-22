## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T15:01:13+00:00
- Post Title: Moorhuhn Wanted (*.DAT)

Nostalgy 

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

get DUMMY long
get FILES long

for i = 0 < FILES
	getdstring NAME 128
	get OFFSET long
	get SIZE long
	get DUMMY longlong
    log NAME OFFSET SIZE
next i
```
