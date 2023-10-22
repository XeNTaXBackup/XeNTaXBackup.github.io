## Post #1
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-09-12T21:14:22+00:00
- Post Title: Dead Rising 3 textures

Does anyone have working tools for extracting/converting the textures for Dead Rising 3?  Just picked up this game, want to pull some models from it.
## Post #2
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2019-09-13T08:11:43+00:00
- Post Title: Dead Rising 3 textures

Try use max script for Dead Rising 4, i convert dr3 .tex use this script [download/file.php?id=13550](https://forum.xentax.com/download/file.php?id=13550)
## Post #3
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-09-14T03:22:37+00:00
- Post Title: Dead Rising 3 textures

I don't have 3DS Max.  I've tried using the quickbms tex to dds scripts from the Dead Rising 3 thread here, but the dds files produced are unusable - not even Noesis can read them.  I'm using the Blender 2.49 tool to extract the models and textures, but the textures it extracts all throw a EOF error in GIMP.

I have found a method that works using TextureFinder 2.1 and Rawtex, but it's time consuming and tedious.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-09-25T20:11:31+00:00
- Post Title: Dead Rising 3 textures

you must post some samples for examination.   
perhaps the samples you tried aren't yet supported by his tex2dds script:
[viewtopic.php?f=10&t=11900&p=112757&hil ... +3#p101663](https://forum.xentax.com/viewtopic.php?f=10&t=11900&p=112757&hilit=Dead+Rising+3#p101663)
## Post #5
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-09-27T03:54:38+00:00
- Post Title: Dead Rising 3 textures

I figured it out!  I was able to write a bms script to extract the textures from the .tex container:

```
get UNKN long
get FILESIZE long
get COUNT long
get UNKN long
get STRGOFFSET long

for i = 0 < COUNT

	get FILENAMEOFFSET long
	get UNKN long
	get SIZE long
	get SIZE2 long
	get OFFSET long
	get UNKN long
	get ZERO long

	savepos START

	goto FILENAMEOFFSET

	get FILENAME string

	string NAME = FILENAME

	string NAME += ".tex"

	goto OFFSET
	
	log NAME OFFSET SIZE

	goto START

next i
```


After that, I modified the bms merlinsvk posted to properly write the dds:

```
# texture to DDS converter
# by MerlinSVK    		Dec 2014
# version 1.0
# note: I hadn't enough textures so I don't know if there are any DXT3, DXT5, ... formats
# script for QuickBMS	http://aluigi.org/papers.htm#quickbms

get SIZE asize
get NAME basename
string H_NAME = NAME
string M_NAME = NAME
string H_NAME += ".head"
string NAME += ".dds"

goto 0x4
get WIDTH short
get HEIGHT short
get FORMAT byte
goto 0x10
get MIP_LIST long
goto MIP_LIST
get DATA_OFF long
xmath MIP_COUNT "(DATA_OFF - 0x1C) / 0x10"
xmath DATA_SIZE "SIZE - DATA_OFF"

if FORMAT == 0x00			# RGBA8
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x0F\x10\x00\x00\x41\x41\x41\x41\x42\x42\x42\x42\x43\x43\x43\x43\x43\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x41\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\xFF\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif FORMAT == 0x08		# DXT1
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif FORMAT == 0x26		# ATI2 - normal map
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\xDD\xDD\xDD\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x41\x54\x49\x32\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
endif

	putVarChr MEMORY_FILE 0XC HEIGHT long
	putVarChr MEMORY_FILE 0x10 WIDTH long
	putVarChr MEMORY_FILE 0x14 DATA_SIZE long
	putVarChr MEMORY_FILE 0X1C MIP_COUNT long

append
log MEMORY_FILE DATA_OFF DATA_SIZE
append

get DDS_SIZE asize MEMORY_FILE
log NAME 0 DDS_SIZE MEMORY_FILE	# save DDS texture
```

Now I can extract the textures and convert them easily!
