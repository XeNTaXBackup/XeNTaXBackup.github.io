## Post #1
- Username: Darkman234
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 02, 2014 10:14 am
- Post datetime: 2017-02-06T17:06:00+00:00
- Post Title: Captian Morgane and the golden turtle ".wr"

The models use a .wr extension and would very much appreciate it if can anyone can lend a hand.
[mabel.zip](https://xentaxbackup.github.io/file/12411_mabel.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-06T18:18:16+00:00
- Post Title: Captian Morgane and the golden turtle ".wr"

your wr sample contains 1 dds texture and a binary compressed .x model file

this bms script will auto-split the files and auto-decompress the x file on the fly.  

```
get TABLELEN long
goto 0x800
savepos BASEOFF
get NUMFILES long
for i = 0 < NUMFILES
	getdstring ID 4
	get OFFSET long
	math OFFSET + BASEOFF
	get SIZE long
	getdstring SKIP 0xc
	get NAMEOFF long
	savepos TMP
	math NAMEOFF + BASEOFF
	goto NAMEOFF
	get NAME string
	if ID == "D2XT"
		string NAME + ".dds"
		log NAME OFFSET SIZE
	elif ID == "SEMX"
		string NAME + ".x"
		set MEMORY_FILE binary "\x78\x6f\x66\x20\xAA\xAA\xBB\xBB\xCC\xCC\xCC\xCC\xDD\xDD\xDD\xDD"
		comtype mszip
		goto OFFSET
		get SKIP long
		get MAJORVERSION short
		get MINORVERSION short
		getdstring FORMATTYPE 0x4
		get FLOATSIZE long
		get DECOMPSIZE long
		math OFFSET + 0x18
		if FORMATTYPE == "tzip"
			math FORMATTYPE = 0x20747874 //"txt " 
		elif FORMATTYPE == "bzip"
			math FORMATTYPE = 0x206e6962 //"bin " 
		endif
		putVarChr MEMORY_FILE 0x4 MAJORVERSION short //AAAA
		putVarChr MEMORY_FILE 0x6 MINORVERSION short //BBBB
		putVarChr MEMORY_FILE 0x8 FORMATTYPE long //CCCCCCCC
		putVarChr MEMORY_FILE 0xc FLOATSIZE long //DDDDDDDD
		log NAME 0 0x10 MEMORY_FILE
		append
		clog NAME OFFSET SIZE DECOMPSIZE
	endif
	goto TMP
next i
```




Mabel.png (210.02 KiB) Viewed 69 times
## Post #3
- Username: Darkman234
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 02, 2014 10:14 am
- Post datetime: 2017-02-07T04:57:02+00:00
- Post Title: Captian Morgane and the golden turtle ".wr"

Hmm..it seems everytime I run the script I get a "invalid command "formattype" or arguments at line 18. But I successfully extracted textures
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-12T02:08:27+00:00
- Post Title: Captian Morgane and the golden turtle ".wr"

no idea why you get that message, it works fine as you can see from the image....   

i updated my previous post with a better script to auto-split the files and auto-decompress the .x file   
[viewtopic.php?p=127327#p127327](http://forum.xentax.com/viewtopic.php?p=127327#p127327)
## Post #5
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-01-02T08:49:35+00:00
- Post Title: Captian Morgane and the golden turtle ".wr"

how did you open the ,x files? 
noesis gave runtime error: failed to construct model from rpgeo context
when i imported the .xfiles into blender, nothing showed up
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-02T19:34:20+00:00
- Post Title: Captian Morgane and the golden turtle ".wr"

i used unwrap3d to open the extracted mabel.x file. 
it is a paid program but has some high quality import/export plugins.
