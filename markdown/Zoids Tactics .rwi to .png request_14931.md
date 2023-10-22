## Post #1
- Username: Falcarius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 4:34 pm
- Post datetime: 2016-08-24T14:32:26+00:00
- Post Title: Zoids Tactics .rwi to .png request

I was looking through the PS2 game Zoids Tactics and found that all the images are stored as .rwi files, which seems to be a very rare extension. I couldn't find any useful information through Google, so I had a look at the files in a hex editor and I now have a pretty solid idea of how they work...

The first 0x28 bytes are the header, made up of 10 little-endian ints. The second int is the number of bytes in the file minus 0x0C, the seventh and tenth ints are the image's width in pixels, and the eighth int is its height. I'm not sure what the other six ints represent, but they were the same in every image I checked.

The last 0x400 bytes are the palette, made up of 256 big-endian RGBA values (or little-endian ABGR values, if you prefer). Between the header and the palette, every byte represents a pixel, running in the normal left-to-right top-to-bottom order and pointing to a location on the palette. All simple enough for a novice like me to figure out 

Problem is, I don't have the programming knowledge to be able to convert the files into something usable (preferably .png). If somebody could create a converter for me, or point me to any that already exist, it would be much appreciated.
[cf001_01.zip](https://xentaxbackup.github.io/file/11607_cf001_01.zip)
## Post #2
- Username: Falcarius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 4:34 pm
- Post datetime: 2016-08-26T07:17:17+00:00
- Post Title: Zoids Tactics .rwi to .png request

Okay, I've managed to figure out a slow but functional method using QuickBMS. I just run the following script on the .rwi file...

```
endian guess UNK1
get FILESIZE long
getdstring UNK2 16
get XSIZE long
get YSIZE long
getdstring UNK3 8
append
set PIXNUM long XSIZE
math PIXNUM * YSIZE
for i = 0 < PIXNUM
	get PALADD byte
	math PALADD * 4
	set OFFSETR long FILESIZE
	math OFFSETR - 0x3F4
	math OFFSETR + PALADD
	set OFFSETG long OFFSETR
	math OFFSETG + 1
	set OFFSETB long OFFSETG
	math OFFSETB + 1
	set OFFSETA long OFFSETB
	math OFFSETA + 1
	log "extracted.tga" OFFSETB 1
	log "extracted.tga" OFFSETG 1
	log "extracted.tga" OFFSETR 1
	log "extracted.tga" OFFSETA 1
next i
```

...add the following bytes to the start of the resulting .tga in a hex editor (replacing "80 00 80 00" with the image width and height as two-byte little-endian values)...

```
00 00 02 00 00 00 00 00 00 00 00 00 80 00 80 00 20 28
```

...and I have a working .tga file that I can convert to .png using Photoshop or similar.

Still hoping someone will provide a better converter, because this one is laughably inefficient, it's just that QuickBMS is the only automated-byte-editing-type program I have the slightest familiarity with.


EDIT: I wrote another script that converts the .rwi files to colour-mapped .tga, which is significantly faster than plain ARGB (1 second instead of 10+ minutes for 640x448 images) and makes much smaller files... but for some reason, the .tga files aren't working with 32-bit colour map values. They work fine with 24-bit, but as soon as I include the alpha values, they refuse to open. Any tips?

EDIT2: Okay, looks like they are valid after all, and it's just that one program that's failing to open them. Here's the colour-map code and header bytes:

```
endian guess UNK1
get FILESIZE long
getdstring UNK2 16
get XSIZE long
get YSIZE long
getdstring UNK3 8
append
set PIXNUM long XSIZE
math PIXNUM * YSIZE
set OFFSET long FILESIZE
math OFFSET - 0x3F2
for i = 0 < 0x100
	log "extracted.tga" OFFSET 1
	math OFFSET - 1
	log "extracted.tga" OFFSET 1
	math OFFSET - 1
	log "extracted.tga" OFFSET 1
	math OFFSET + 3
	log "extracted.tga" OFFSET 1
	math OFFSET + 3
next i
log "extracted.tga" 0x28 PIXNUM

00 01 01 00 00 00 01 20 00 00 00 00 80 00 80 00 08 28
```


This is almost what I was after, but I still can't do batch conversions with it. So, new questions: how would I tell QuickBMS to A) add the header bytes to the start of each file (I think "log" only works with addresses, not variables), and B) use the input filenames as the output filenames, just with a different extension (if possible)?
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-26T20:23:04+00:00
- Post Title: Zoids Tactics .rwi to .png request

i see in a lot of dxt conversion scripts where people use MEMORY_FILE
to store the header and append it to the main data, something like this added to your script

set MEMORY_FILE binary "\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x28"
....
putVarChr MEMORY_FILE 0xc XSIZE short
putVarChr MEMORY_FILE 0xe YSIZE short
....
log "" 0 0x12 MEMORY_FILE
append

i don't know enough about quickbms to get it working, but 
aluigi at Zenhax could get it working for you in 2 minutes though
## Post #4
- Username: Falcarius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 4:34 pm
- Post datetime: 2016-08-29T09:11:27+00:00
- Post Title: Zoids Tactics .rwi to .png request

Thanks, that was just what I needed! Here's my final script, in case anyone else comes across some .rwi files they want converted. I'm sure it could be improved, but it did the job (at about 1000 files per minute).

```
string FNAME + ".tga" 
get UNK1 long
endian guess UNK1
get FILESIZE long
getdstring UNK2 16
get XSIZE long
get YSIZE long
getdstring UNK3 8
set MEMORY_FILE binary "\x00\x01\x01\x00\x00\x00\x01\x20\x00\x00\x00\x00\x00\x00\x00\x00\x08\x28"
putVarChr MEMORY_FILE 0xc XSIZE short
putVarChr MEMORY_FILE 0xe YSIZE short
set PIXNUM long XSIZE
math PIXNUM * YSIZE
set OFFSET long FILESIZE
math OFFSET - 0x3F2
append
for i = 0 < 0x100
	log MEMORY_FILE OFFSET 1
	math OFFSET - 1
	log MEMORY_FILE OFFSET 1
	math OFFSET - 1
	log MEMORY_FILE OFFSET 1
	math OFFSET + 3
	log MEMORY_FILE OFFSET 1
	math OFFSET + 3
next i
log MEMORY_FILE 0x28 PIXNUM
set MSIZE long 0x412
math MSIZE + PIXNUM
log FNAME 0 MSIZE MEMORY_FILE
```
