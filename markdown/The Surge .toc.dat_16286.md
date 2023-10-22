## Post #1
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2017-05-16T10:50:58+00:00
- Post Title: The Surge .toc/.dat

```
endian big
goto 0x5A
get DAT_NAME_SIZE short
getdstring DAT_NAME DAT_NAME_SIZE
string DAT_NAME += "_"
xmath ZERO_SIZE "4 - (DAT_NAME_SIZE % 4)"
if ZERO_SIZE < 4
	getdstring DUMMY ZERO_SIZE
endif
get DATS byte
get FILES long
math DAT_INDEX = -1
for i = 0 < FILES
	getdstring DUMMY 0x0E
	get NAME_SIZE short
	getdstring NAME NAME_SIZE
	xmath ZERO_SIZE "4 - (NAME_SIZE % 4)"
	if ZERO_SIZE < 4
		getdstring DUMMY ZERO_SIZE
	endif
	get OFFSET long
	if OFFSET == 0
		math DAT_INDEX += 1
		string NAME_INDEX p= "%01d" DAT_INDEX
		set NEW_DAT_NAME string DAT_NAME
		string NEW_DAT_NAME += NAME_INDEX
		string NEW_DAT_NAME += ".dat"
		open FDSE NEW_DAT_NAME 1
	endif
	get ZSIZE long
	get SIZE long
	getdstring DUMMY 0x0A
	clog NAME OFFSET ZSIZE SIZE 1
next i

```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-22T22:05:07+00:00
- Post Title: The Surge .toc/.dat

thx!



char_hero_civil.jpg (190.13 KiB) Viewed 187 times
## Post #3
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2017-08-10T09:38:34+00:00
- Post Title: The Surge .toc/.dat

Is there any chance I could get one of you wonderful people to figure out how to decompress/decompile The Surge's .bin files?
Linked is a rar with the lot of them (it's not very big, only like 9mb).

[https://www.dropbox.com/s/b3r4k9uxg64ql ... n.rar?dl=0](https://www.dropbox.com/s/b3r4k9uxg64qlgf/surge_bin.rar?dl=0)
