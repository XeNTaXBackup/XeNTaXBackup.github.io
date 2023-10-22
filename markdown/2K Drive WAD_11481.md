## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-03T16:01:41+00:00
- Post Title: 2K Drive WAD

A script I came up with to extract image_ios.wad from the game 2K Drive.

```

goto 2048
get PAIRS long
for i = 0 < PAIRS
	get DUMMY1 long
	get DUMMY2 long
next i

get FILES long
savepos FILEDATA
math NAMES_OFF = FILES
math NAMES_OFF *= 48
math NAMES_OFF += FILEDATA
math NAMES_OFF += 4	#NAMES SIZE

for i = 0 < FILES
	get DUMMY long
	get NAME_OFF long
	math NAME_OFF += NAMES_OFF
	get TYPE long
	get DUMMY long
	get OFFSET long
	get ZERO long
	get SIZE long
	get ZERO long	#could indicate compressed/uncompressed
	get ZSIZE long	#untested
	get ZERO long
	get DUMMY long
	get ZERO long
	savepos LASTFILE

	goto NAME_OFF
	get NAME string
	log NAME OFFSET SIZE
	goto LASTFILE
next i
```
