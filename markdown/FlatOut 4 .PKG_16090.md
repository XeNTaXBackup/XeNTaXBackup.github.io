## Post #1
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2017-04-04T22:14:36+00:00
- Post Title: FlatOut 4 .PKG

```
get DUMMY long
get FILES long
get TOC_SIZE long
goto 0x30
comtype lz4f
for i = 0 < FILES
	get NAME_SIZE long
	getdstring NAME NAME_SIZE
	get DUMMY long
	get OFFSET longlong
	get DUMMY longlong
	get ZSIZE longlong
	get SIZE longlong
	getdstring DUMMY 0x2C
	math OFFSET += 4
	clog NAME OFFSET ZSIZE SIZE
next i

```
