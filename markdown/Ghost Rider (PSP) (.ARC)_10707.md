## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-21T09:12:27+00:00
- Post Title: Ghost Rider (PSP) (*.ARC)

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "A2\x2E\x30"
get FILES long
get FIRSTFILEPOS long
get NAMESTABLEOFFSET long
get NAMESTABLESIZE long

for i = 0 < FILES
	get NOFFSET long
	get OFFSET long
	get ZSIZE long
	get SIZE long
	savepos TEMP
	set NAMEOFFSET = NAMESTABLEOFFSET
	math NAMEOFFSET += NOFFSET
	goto NAMEOFFSET
	get NAME string
	clog NAME OFFSET ZSIZE SIZE
	goto TEMP
next i
```
