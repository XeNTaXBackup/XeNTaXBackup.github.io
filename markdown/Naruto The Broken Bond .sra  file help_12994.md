## Post #1
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2015-06-25T23:02:37+00:00
- Post Title: Naruto: The Broken Bond .sra  file help

I was wondering if there are any ways to extract or figure out the naruto_stream and naruto_sound sra files
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-06-26T10:37:57+00:00
- Post Title: Naruto: The Broken Bond .sra  file help

Post some examples so people can take a look at them
## Post #3
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2016-12-06T15:38:17+00:00
- Post Title: Naruto: The Broken Bond .sra  file help

sorry it took this long, here is an exmple

[https://mega.nz/#!XxZDRDxT!LJifU9xW1rFq ... NGgICwq22o](https://mega.nz/#!XxZDRDxT!LJifU9xW1rFqJtCUehL0NGi5uit9EytZDNGgICwq22o)
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-12-07T06:24:34+00:00
- Post Title: Naruto: The Broken Bond .sra  file help

```

# header
46 52 53 41 	"FRSA"
02 00 00 00 	unknown
F3 6C DA 09 	offset1
95 08 00 00 	number of files
3F 5D DB 09 	offset2
E6 08 00 00 	unknown
00 00 00 00

@offset1:
for (number of files) {
00 00 00 00 	always 0
05 02 
00 10 
8B 67 01 0F 	maybe checksum?
F8 96 5E 03 	index to zlib compressed file (they start with "xœ")
97 53 05 00 	size of zlib compressed file
20 00 06 00 	size of uncompressed file
40 00 00 00	always 0x40
}

@offset2:
0x9370 bytes of unknown data
```


QuickBMS script:

```

idstring "FRSA"
get DUMMY long
get FILE_TABLE_OFFSET long
get FILE_COUNT long

goto FILE_TABLE_OFFSET

for i = 0 < FILE_COUNT
	get DUMMY long
	get DUMMY long
	get DUMMY long
	get OFFSET long
	get ZSIZE long
	get SIZE long
	get DUMMY long
	
	set NAME "FRSA_Output\sprite_"
	string NAME + i
	string NAME + ".kk2d"
	
	clog NAME OFFSET ZSIZE SIZE
next i
```
