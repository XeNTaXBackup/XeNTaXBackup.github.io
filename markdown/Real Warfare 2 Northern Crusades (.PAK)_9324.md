## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-21T12:33:23+00:00
- Post Title: Real Warfare 2: Northern Crusades (*.PAK)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PACK"
get NULLS long
get TABLEOFFSET long
get NULLS long
get FILES long

goto TABLEOFFSET
get DUMMY longlong
get DUMMY longlong

for i = 0 < FILES
	get NSIZE long
	get NULLS long
	getdstring NAME NSIZE
	get OFFSET long
	get NULLS long
	get SIZE long
	get NULLS long
	log NAME OFFSET SIZE
next i
```
