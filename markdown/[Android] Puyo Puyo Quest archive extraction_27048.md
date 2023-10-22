## Post #1
- Username: Shiruba
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 03, 2023 12:44 am
- Post datetime: 2023-08-02T19:54:43+00:00
- Post Title: [Android] Puyo Puyo Quest archive extraction

The assets of the game are not encrypted but I need a bms script to extract everything.
There are around 1500 files which seem to follow this pattern :
1) It is big endian
2) First 4 bytes (long in bms if I understand) is the number of files inside the archive
3) 4 bytes for the file sizes (so if they are 3 files, this means the next 12 bytes are for the first file size, the second and the third)
4) 4 bytes for the location of the filenames (same as the file sizes)
5) 4 bytes for the location of the files' contents (same as the file sizes)

Knowing this if somebody can provide a bms script thanks!

Download link : [https://drive.google.com/file/d/1cUFZxm ... sp=sharing](https://drive.google.com/file/d/1cUFZxm6uH42k89gbyOlTg2O4IdSV5x5r/view?usp=sharing)
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-03T10:47:42+00:00
- Post Title: [Android] Puyo Puyo Quest archive extraction

```

get FILES long

for i = 0 < FILES
	get SIZE long
	putarray 0 i SIZE
next i

for i = 0 < FILES
	get NAME_OFF long
	savepos TMP
	goto NAME_OFF
	get NAME string
	putarray 1 i NAME
	goto TMP
next i

for i = 0 < FILES
	get OFFSET long
	putarray 2 i OFFSET
next i
	
for i = 0 < FILES
	getarray SIZE NAME OFFSET 0 i
	log NAME OFFSET SIZE
next i

```


For the record, your files is in little endian though. Otherwise, the info you gave is correct.
