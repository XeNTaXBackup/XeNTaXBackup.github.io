## Post #1
- Username: InnerCircle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 01, 2014 12:29 am
- Post datetime: 2014-10-31T16:51:10+00:00
- Post Title: War Thunder .ddsx image format

Hello everyone!

I have a Problem regarding .ddsx Files. I´m creating skins for the F2P Game War Thunder. Although the game has an built-in Feature to create Skin Templates for Planes and Tanks (supports .dds/png./tga/.jpg), but some of those templates are missing elements like Normalmaps, additional Textures, etc...

A Guy from the WT Community made a tool to open/extract the content for most of the game archives. Almost every image inside those are in .ddsx though my attempts at finding a solution how to convert them have failed so far.

I´ve attached an example file so i would be very grateful if smeone could help me out here  
[h-75n.7z](https://xentaxbackup.github.io/file/8009_h-75n.7z)
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-11-01T08:50:52+00:00
- Post Title: War Thunder .ddsx image format

It's compressed by lzma.
Here's decompressed data.It's headerless dds.
[decmp.rar](https://xentaxbackup.github.io/file/8014_decmp.rar)
## Post #3
- Username: InnerCircle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 01, 2014 12:29 am
- Post datetime: 2014-11-02T13:38:50+00:00
- Post Title: War Thunder .ddsx image format

Thank you   

I found a topic on this forum which seems kinda related since this Game uses the same Engine: [viewtopic.php?p=30696#p30696](http://forum.xentax.com/viewtopic.php?p=30696#p30696)

> then I looked at the dds files in a hex editor and just pasted a valid dds header over it which was dxt5 and no mip maps.

Could you tell me how to do this? I know I´m a total noob with Hex Editing and stuff
## Post #4
- Username: InnerCircle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 01, 2014 12:29 am
- Post datetime: 2014-11-16T22:35:08+00:00
- Post Title: War Thunder .ddsx image format

Anyone else who might help me please?
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-11-17T18:02:52+00:00
- Post Title: War Thunder .ddsx image format

> Reply from InnerCircle
>
> then I looked at the dds files in a hex editor and just pasted a valid dds header over it which was dxt5 and no mip maps.

Could you tell me how to do this? I know I´m a total noob with Hex Editing and stuff
to do it through hex editing you would copy the header from another dds file and paste it at the beginning of your uncompressed headerless file. 

Example DXT5 header with no mipmaps

```
38 01 00 00 C0 F3 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 20 00 00 00
04 00 00 00 44 58 54 35 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 10 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```


If you don't want to mess with hex editing you could open the uncompressed file in TextureFinder with correct settings and save it as *.bmp then convert it to *.dds.


 h-75n.zip
(20.9 KiB) Downloaded 41 times
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-17T18:20:22+00:00
- Post Title: War Thunder .ddsx image format

> Reply from AceWell
>
> To do it through hex editing you would copy the header from another dds file and paste it at the beginning of your uncompressed headerless file. 
-snip-
If you don't want to mess with a hex editor you could open the uncompressed file in TextureFinder with correct settings and save it as *.bmp then convert it to *.dds.

I think what he means is how to unpack .ddsx textures - I've tried it myself, with QuickBMS and different variations of LZMA with different offsets, but none of them worked.
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-17T19:06:05+00:00
- Post Title: War Thunder .ddsx image format

```
# DDSx to DDS converter
# by MerlinSVK    Oct 2014
# version 1.0
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xEE\xEE\xEE\xEE\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get NAME basename
string HNAME = NAME
string HNAME += ".head"
string NAME += ".dds"

log HNAME 0 0x20	# save header for backward conversion

idstring "DDSx"
getdstring FORMAT 4
if FORMAT == "DXT1"
	math FORMAT = 0x31545844
else if FORMAT == "DXT3"
	math FORMAT = 0x33545844
else if FORMAT == "DXT5"
	math FORMAT = 0x35545844
else
	print "-- UNSUPPORTED FORMAT --"
	cleanexit
endif
get UNK byte
get UNK short
get UNK byte
get WIDTH short
get HEIGHT short
goto 0x18
get SIZE long
get ZSIZE asize
math ZSIZE -= 0x20

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 SIZE long
putVarChr MEMORY_FILE 0x54 FORMAT long

append
comtype lzma_dynamic
clog MEMORY_FILE 0x20 ZSIZE SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE

```

I got also a repack script, but I did not tested repacked texture in the game, so it may not work.

```
# DDS to DDSx converter
# by MerlinSVK    Oct 2014
# version 1.0
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

open FDDE DDS 0 
open FDDE HEAD 1

get NAME basename
string NAME += ".ddsx_NEW"

get DSIZE asize 0
math DSIZE -= 0x80
get HSIZE asize 1

goto 0xC 0
get HEIGHT long 0
get WIDTH long 0
#get DSIZE long 0
goto 0x54 0
get FORMAT long 0

log MEMORY_FILE 0 HSIZE 1		# copy header into the memory_file
append
comtype lzma_compress
clog MEMORY_FILE 0x80 DSIZE DSIZE 0	# compress texture and append it to the header
append
get DSIZE asize MEMORY_FILE
math DSIZE -= 0x20				# substract size of header

# this part is useful when you changed resolution or format of the texture
# otherwise it can be deleted
putVarChr MEMORY_FILE 0x4 FORMAT long
putVarChr MEMORY_FILE 0xC WIDTH short
putVarChr MEMORY_FILE 0xE HEIGHT short
putVarChr MEMORY_FILE 0x18 DSIZE long
#

get DDSXSIZE asize MEMORY_FILE
log NAME 0 DDSXSIZE MEMORY_FILE

```
## Post #8
- Username: InnerCircle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 01, 2014 12:29 am
- Post datetime: 2014-11-18T19:58:23+00:00
- Post Title: War Thunder .ddsx image format

> Reply from merlinsvk
>
> Code: Select all# War Thunder
# DDSx to DDS converter
# by MerlinSVK    Oct 2014
# version 1.0
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\xEE\xEE\xEE\xEE\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get NAME basename
string HNAME = NAME
string HNAME += ".head"
string NAME += ".dds"

log HNAME 0 0x20	# save header for backward conversion

idstring "DDSx"
getdstring FORMAT 4
if FORMAT == "DXT1"
	math FORMAT = 0x31545844
else if FORMAT == "DXT3"
	math FORMAT = 0x33545844
else if FORMAT == "DXT5"
	math FORMAT = 0x35545844
else
	print "-- UNSUPPORTED FORMAT --"
	cleanexit
endif
get UNK byte
get UNK short
get UNK byte
get WIDTH short
get HEIGHT short
goto 0x18
get SIZE long
get ZSIZE asize
math ZSIZE -= 0x20

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 SIZE long
putVarChr MEMORY_FILE 0x54 FORMAT long

append
comtype lzma_dynamic
clog MEMORY_FILE 0x20 ZSIZE SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE

I got also a repack script, but I did not tested repacked texture in the game, so it may not work.
Code: Select all# War Thunder
# DDS to DDSx converter
# by MerlinSVK    Oct 2014
# version 1.0
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

open FDDE DDS 0 
open FDDE HEAD 1

get NAME basename
string NAME += ".ddsx_NEW"

get DSIZE asize 0
math DSIZE -= 0x80
get HSIZE asize 1

goto 0xC 0
get HEIGHT long 0
get WIDTH long 0
#get DSIZE long 0
goto 0x54 0
get FORMAT long 0

log MEMORY_FILE 0 HSIZE 1		# copy header into the memory_file
append
comtype lzma_compress
clog MEMORY_FILE 0x80 DSIZE DSIZE 0	# compress texture and append it to the header
append
get DSIZE asize MEMORY_FILE
math DSIZE -= 0x20				# substract size of header

# this part is useful when you changed resolution or format of the texture
# otherwise it can be deleted
putVarChr MEMORY_FILE 0x4 FORMAT long
putVarChr MEMORY_FILE 0xC WIDTH short
putVarChr MEMORY_FILE 0xE HEIGHT short
putVarChr MEMORY_FILE 0x18 DSIZE long
#

get DDSXSIZE asize MEMORY_FILE
log NAME 0 DDSXSIZE MEMORY_FILE

Wow that´s exactly what i needed! Thank you!
