## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-28T11:29:06+00:00
- Post Title: This War of Mine (.binfont, .texture)

So I finally managed to make a texture converting BMS scripts for both, the .binfont and .texture files.

For easier localization, there would by neat to have some tool/script to convert/import/export strings from l??n.bin file (editing is doable via hex or Notepad++, but plain text would be better)   

EDIT2: Mipmaps in .texture files are supported and written in the correct way   

```
# BINFONT to DDS converter
# by MerlinSVK    Nov 2014
# version 1.0
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

get SIZE asize
get NAME basename
string HNAME = NAME
string TNAME = NAME
string HNAME += ".head"
string TNAME += ".tail"
string NAME += ".dds"

idstring "\xE3\x0A\xF2\x23"
get UNK long
get TYPE byte
get COUNT long
math HEIGHT = 0

for i = 0 < COUNT
	get TMP long
	math HEIGHT += TMP
next i
savepos OFFSET

xmath DATASZ "(SIZE / 0x1000) * 0x1000"		# length of texture data
xmath TOFFSET "OFFSET + DATASZ"				# start of tail
xmath TSIZE "SIZE - TOFFSET"				# length of tail

if COUNT > 1 then
	xmath OFFSET "(COUNT * 4) + (OFFSET - 4)"
endif

if TYPE == 1		# L8A8 format
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x01\x00\x02\x00\x00\x00\x00\x00\x10\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\xFF\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
	xmath WIDTH "(DATASZ / HEIGHT) / 2"
else				# L8 format
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x0F\x10\x00\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x08\x00\x00\x00\xFF\x00\x00\x00\xFF\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
	xmath WIDTH "DATASZ / HEIGHT"
endif

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 DATASZ long

append
log MEMORY_FILE OFFSET DATASZ
append

get DDSSIZE asize MEMORY_FILE
log HNAME 0 OFFSET				# save header
log TNAME TOFFSET TSIZE			# save tail (char descriptions)
log NAME 0 DDSSIZE MEMORY_FILE	# save DDS texture

```


```
# DDS to BINFONT converter
# version 1.0
# by MerlinSVK    Nov 2014
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

open FDDE DDS 0
open FDDE HEAD 1
open FDDE TAIL 2

get NAME basename
string NAME += ".binfont_NEW"

get DSIZE asize 0
get HSIZE asize 1
get TSIZE asize 2

math DSIZE -= 0x80				# subtract the DDS header

log MEMORY_FILE 0 HSIZE 1		# copy header into memory_file
append
log MEMORY_FILE 0x80 DSIZE 0	# append texture data
log MEMORY_FILE 0 TSIZE 2		# append tail
append

get BINSZ asize MEMORY_FILE
log NAME 0 BINSZ MEMORY_FILE

```


```
# TEXTURE to DDS converter
# by MerlinSVK    		Dec 2014
# version 1.2			(added support for RGBA format & mipmaps)
# script for QuickBMS	http://aluigi.org/papers.htm#quickbms

get SIZE asize
get NAME basename
string HNAME = NAME
string MNAME = NAME
string HNAME += ".head"
string NAME += ".dds"

get WIDTH long
get HEIGHT long
get TYPE long
get MIPS long

xmath DATASZ "SIZE - 0x90"

if TYPE == "0x31545844"			# DXT1
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif TYPE == "0x33545844"		# DXT3
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x33\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif TYPE == "0x35545844"		# DXT5
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif TYPE == "0x15"				# RGBA8
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x0F\x10\x00\x00\x41\x41\x41\x41\x42\x42\x42\x42\x43\x43\x43\x43\x43\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x41\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\xFF\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
endif

	putVarChr MEMORY_FILE 0XC HEIGHT long
	putVarChr MEMORY_FILE 0x10 WIDTH long
	putVarChr MEMORY_FILE 0x14 DATASZ long

if MIPS == 1
	append
	log MEMORY_FILE 0x90 DATASZ
	append
else
	putVarChr MEMORY_FILE 0XA 0x0A byte
	putVarChr MEMORY_FILE 0X1C MIPS long
	putVarChr MEMORY_FILE 0X6C 0x08 byte
	putVarChr MEMORY_FILE 0X6E 0x40 byte

	math MIPOFFSET = 0x90					# offset of the smallest mipmap
	for i = 1 <= MIPS						# read mipmap lenghts
		get MIPWIDTH short
		get MIPHEIGHT short
		get MIPSIZE[i] long

		set MIPSTART[i] long MIPOFFSET
		set MIPSZ long MIPSIZE[i]
		xmath MIPOFFSET "MIPOFFSET + MIPSZ"	# calculate next mipmap offset
	next i
			
	append
	for i = MIPS >= 1						# writing mipmaps in reversed order
		log MEMORY_FILE MIPSTART[i] MIPSIZE[i]
	next i - 1
	append
endif

get DDSSIZE asize MEMORY_FILE
log HNAME 0 0x90				# save header
log NAME 0 DDSSIZE MEMORY_FILE	# save DDS texture


```


```
# DDS to TEXTURE converter
# by MerlinSVK    		Dec 2014
# version 1.1			(added support for mipmaps)
# script for QuickBMS	http://aluigi.org/papers.htm#quickbms

open FDDE DDS 0
open FDDE HEAD 1

get NAME basename
string NAME += ".texture_NEW"

get DSIZE asize 0
get HSIZE asize 1

goto 0xC 1						# read number of mipmaps from header
get MIPS long 1

math DDSSIZE = DSIZE
math DSIZE -= 0x80				# subtract the DDS header
log MEMORY_FILE 0 HSIZE 1		# copy header into memory_file

if MIPS == 1
	append
	log MEMORY_FILE 0x80 DSIZE 0	# append whole texture data
	append
else
	for i = 1 <= MIPS				# read mipmap lenghts
		get MIPWIDTH short 1
		get MIPHEIGHT short 1
		get MIPSIZE[i] long 1
	next i

	math MIPOFFSET = 0x80			# offset of the biggest texture
	for i = MIPS >= 1
		set MIPSTART[i] long MIPOFFSET
		set MIPSZ long MIPSIZE[i]
		xmath MIPOFFSET "MIPOFFSET + MIPSZ"			# calculate next mipmap offset
	next i - 1
			
	append
	for i = 1 <= MIPS								# writing mipmaps in reversed order
		log MEMORY_FILE MIPSTART[i] MIPSIZE[i]
	next i
	append
endif

get BINSZ asize MEMORY_FILE
log NAME 0 BINSZ MEMORY_FILE

```


```
https://www.dropbox.com/s/dz1ygg7uv2koh82/l01n.7z

```
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-28T12:31:47+00:00
- Post Title: This War of Mine (.binfont, .texture)

And I also have partially done font description reader, for those who would like to add new letters into font textures.
But I don't know what UNK1 and UNK2 represents.



```
https://www.dropbox.com/s/dtamrn1ulg9nx0y/font_example.7z
```


```
# Font descripion reader (from .tail file)

get COUNT long
for i = 0 < COUNT
	get CHAR short
	get UNK1 short
	get UNK2 short
	get X1 short
	get X2 short
	get Y1 short
	get Y2 short
	xmath WIDTH  "X2 - X1"
	xmath HEIGHT "Y2 - Y1"
	print "Char: %CHAR|h%, X1: %X1%, Y1: %Y1%, X2: %X2%, Y2: %Y2%, Width: %WIDTH%, Height: %HEIGHT%"
next i

```
## Post #3
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2014-12-02T03:54:56+00:00
- Post Title: This War of Mine (.binfont, .texture)

You can use Cartographer to dump text with your table to extract text and use atlas to insert your text.
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-09T12:28:47+00:00
- Post Title: This War of Mine (.binfont, .texture)

Scripts for converting .texture/.dds texture in first post were updated. Now they support mipmaps  
The only "disadvantage" is that you can't change: format of texture (DXT, RGBA, etc.), resolution or number of mipmaps, because DDS to TEXTURE script reads the original .head file. But if you don't change any of these, everything is OK.
## Post #5
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-09T16:28:27+00:00
- Post Title: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> Scripts for converting .texture/.dds texture in first post were updated. Now they support mipmaps  
The only "disadvantage" is that you can't change: format of texture (DXT, RGBA, etc.), resolution or number of mipmaps, because DDS to TEXTURE script reads the original .head file. But if you don't change any of these, everything is OK.

Can translate?Thanks for your Scripts,but I tried to use  Ekey's unpacker/packer and don't edit any file,it create much unknow files ,the common.dat are bigger, and game can't start.
I haven't tried your Scripts,because i can't pack the "common.dat"
Sorry for my English,and i'm beginner,please help me. :<
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-09T18:22:25+00:00
- Post Title: This War of Mine (.binfont, .texture)

Yes, I'm translating (version 1.0.0). I wrote a script to import/export text file. And some other scripts (QuickBMS, Lua, Batch files and 010 scripts) to split l10n.bin file into thousands string files. It's a mess and not real tools to publish.
## Post #7
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2014-12-12T04:08:33+00:00
- Post Title: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> Yes, I'm translating (version 1.0.0). I wrote a script to import/export text file. And some other scripts (QuickBMS, LUA, Batch files and 010 scripts) to split l10n.bin file into thousands string files. It's a mess and not real tools to publish.

Could you help me extract text from this game, please? Thanks for any help!
## Post #8
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-12T10:46:46+00:00
- Post Title: This War of Mine (.binfont, .texture)

For text export use this script. It can be also used to reimporting, just type "force" when QBMS prompt you.

```
# uncomment the appropriate line
comtype gzip
#clog "l10n.bin" 0xC9C0EA 0x1310E2 0x1310E2		# version 1.0.0
#clog "l10n.bin" 0xD455D0 0x131179 0x131179		# version 1.1.0
clog "l10n.bin" 0xD41BF5 0x156BE6 0x156BE6		# version 1.1.3

```


But there is still no easy way to extract the strings.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-12T15:47:22+00:00
- Post Title: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> But there is still no easy way to extract the strings.

take a look here: [viewtopic.php?p=101705#p101705](http://forum.xentax.com/viewtopic.php?p=101705#p101705)  

(credit to rengareng)
## Post #10
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-13T13:07:39+00:00
- Post Title: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> For text export use this script. It can be also used to reimporting, just type "force" when QBMS prompt you.
Code: Select all# This War of Mine (common.dat)
# uncomment the appropriate line
comtype gzip
#clog "l10n.bin" 0xC9C0EA 0x1310E2 0x1310E2		# version 1.0.0
#clog "l10n.bin" 0xD455D0 0x131179 0x131179		# version 1.1.0
clog "l10n.bin" 0xD41BF5 0x156BE6 0x156BE6		# version 1.1.3


But there is still no easy way to extract the strings.

I try to use [clog "l10n.bin" 0xC9C0EA 0x1310E2 0x1310E2] for Ver 1.1.0.
                [clog "l10n.bin" 0xD455D0 0x131179 0x131179] for Ver 1.1.0 error.
May be my problem.
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-13T13:41:49+00:00
- Post Title: This War of Mine (.binfont, .texture)

Sorry, I don't understand you. What is the problem?
## Post #12
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-13T15:01:10+00:00
- Post Title: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> Sorry, I don't understand you. What is the problem?

My version = 1.1.0
can use
[clog "l10n.bin" 0xC9C0EA 0x1310E2 0x1310E2      # version 1.0.0]
not
[clog "l10n.bin" 0xD455D0 0x131179 0x131179      # version 1.1.0]
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-13T16:38:19+00:00
- Post Title: This War of Mine (.binfont, .texture)

Well, it doesn't matter anymore. You can use Ekey's packer/unpacker tools.
## Post #14
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2014-12-19T15:05:52+00:00
- Post Title: This War of Mine (.binfont, .texture)

Thank you for sharing scripts. I've made binfont converter based on your scripts. 

[http://www.mediafire.com/download/78ou3 ... ol_v1_1.7z](http://www.mediafire.com/download/78ou3e1ljdmk45q/twom_tool_v1_1.7z)　(updated 2014/12/23)
(The readme in the package is Japanese only.)

* binfont tool
 binfont tool converts .binfont file to dds and fnt files. fnt file is font information xml file which is as same format as Bitmap font generater's fnt file. You can also convert new fonts generated by Bitmap font generater to binfont.

- unpack
 binfont_tool -u <binfont path> [<folder path to extract>]
- pack
 binfont_tool -p <fnt file path> [<new binfont file path>]

To create new font, The following BMFont options are required.

- Export Options
 Equalize the cell heights: Checked
 Width: 1024(fixed)
 Height: any
 Bit depth: 32
 Presets: White text with alpha
 Font descriptor: XML
 Textures: dds - DirectDraw Surface
 Compression: None

There are 2 other tools in this package. 

* l01n_tool
 l01n_tool is unpack/repack tool of l10n.bin. it converts l01n.bin to csv and dat files. The csv file is English text file and you can edit this file for translation. The dat file is data file for repacking and should not be modified.

- unpack
 l01n_tool -u <l01n.bin path> [<csv file path>]
- pack
 l01n_tool -p <csv file path> [<new l01n.bin>]

* twom_idx
 The file header of idx file repacked by Ekey's Packer is different from the valid file header for This War of Mine and the game won't start with repacked files. This tool rewrites idx header values correctly.

 twom_idx <idx file path to rewrite>

Here is a sample screen shot with Japanese fonts and texts.   

[http://3.bp.blogspot.com/-Gvb4YxqV3A4/V ... _00001.jpg](http://3.bp.blogspot.com/-Gvb4YxqV3A4/VJRAgiZEW2I/AAAAAAAAANM/lRh6AfwSmJw/s1600/2014-12-13_00001.jpg)
## Post #15
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-19T17:40:08+00:00
- Post Title: This War of Mine (.binfont, .texture)

Great tools, indeed 

Do you know a tool for creating BMFont besides Angel Code's Editor? It makes crappy looking fonts, especially that smaller ones.
## Post #16
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2014-12-19T22:24:40+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> Great tools, indeed 

Do you know a tool for creating BMFont besides Angel Code's Editor? It makes crappy looking fonts, especially that smaller ones.

Sorry, I forgot to add required BMFont options to make a new font. I've updated my previous post.
## Post #17
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-20T16:18:46+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Have you noticed that own fonts are shifted a bit upwards? It looks like the words are aligned to the top of line. It's around 6 or 7px.
## Post #18
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2014-12-24T02:04:45+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

> Reply from merlinsvk
>
> Have you noticed that own fonts are shifted a bit upwards? It looks like the words are aligned to the top of line. It's around 6 or 7px.

Yes. I've tested several font y offset patterns and changed the codes for it's conversion.  Please try new version which I've updated in my first post. New tool is required additional BMFont export option which I've also updated.

Another important thing is that you need to create a new font with same font size of the original. 

It's not best but better than previous version.
## Post #19
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-24T11:28:05+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Oh yeah, it's definitely better. Thank you very much
## Post #20
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-06-21T13:53:09+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Does anyone find out where are fonts?
I tried open all font in common.dat file (folder fonts)





Thanks!
## Post #21
- Username: artdekdok
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 13, 2016 4:46 am
- Post datetime: 2016-04-13T17:42:14+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

.
## Post #22
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-04-13T19:41:46+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Just for quick view on binfont content. It was not tested on every generated binfont. (v2.0.3 game uses TTF/OTF fonts from *.lngp in LocalizationPacks folder)

```
# BINFONT to DDS converter
# by MerlinSVK    Mar 2016
# version 1.2
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

get SIZE asize
get NAME basename
string HNAME = NAME
string TNAME = NAME
string HNAME += ".head"
string TNAME += ".tail"
string NAME += ".dds"

idstring "\xE4\x0A\xF2\x23"
get VERSION long
get TYPE long
get HEIGHT long
savepos OFFSET

if SIZE > 0x102000
	xmath DATASZ "(SIZE / 0x1000) * 0x1000 - 0x2000" 	# length of texture data, rounding down
elif SIZE > 0x101000
	xmath DATASZ "(SIZE / 0x1000) * 0x1000 - 0x1000"
elif SIZE > 0x81000
	xmath DATASZ "(SIZE / 0x1000) * 0x1000 - 0x1000"
else
	xmath DATASZ "(SIZE / 0x1000) * 0x1000"
endif
xmath TOFFSET "OFFSET + DATASZ"									# start of tail (font description)
xmath TSIZE "SIZE - TOFFSET"											# length of tail

if TYPE == 1		# L8A8 format
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x00\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x01\x00\x02\x00\x00\x00\x00\x00\x10\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\xFF\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
	xmath WIDTH "(DATASZ / HEIGHT) / 2"
else				# L8 format
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x0F\x10\x00\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x08\x00\x00\x00\xFF\x00\x00\x00\xFF\x00\x00\x00\xFF\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
	xmath WIDTH "DATASZ / HEIGHT"
endif

print "\nFILE: %NAME%\nDATASZ: %DATASZ% B (%DATASZ|h%)\n WIDTH: %WIDTH% px (%WIDTH|h%)\nHEIGHT: %HEIGHT% px (%HEIGHT|h%)"

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 DATASZ long

append
log MEMORY_FILE OFFSET DATASZ
append

get DDSSIZE asize MEMORY_FILE
log HNAME 0 OFFSET														# save header
log TNAME TOFFSET TSIZE												# save tail (char descriptions)
log NAME 0 DDSSIZE MEMORY_FILE								# save DDS texture

```
## Post #23
- Username: artdekdok
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 13, 2016 4:46 am
- Post datetime: 2016-04-15T15:19:37+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

.
## Post #24
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-04-15T19:11:38+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Forget on modifying binfonts. They would be re-written by game, when player choose another language in Settings.
You need modify included TTF fonts in .lngp pack.

LNGP consist of:
1) info header
2) text (same text, same format as .lang files, but at this moment game doesn't read included text in .lngp, so you don't need to edit it)
3) TTF or OTF fonts
4) font license (always empty)

This script will separate lngp pack into single files. You will have to use hex editor to put new fonts into .lngp. But it's doable.


```
# Written by MerlinSVK, 03/2016
###########################################
get FNAME basename
string NAME = FNAME

############### header section ###############
get HDRSIZE long									# Header size (-4 bytes)
get LNGID clsid										# LanguagePackHeader
get UNK1 long										# Game version, 01 00 00 00
get UNK2 long										# Game version, 04 00 00 00
get UNK3 long										# Game version, 01 00 00 00
get TIMET time64									# Creation time
get TIMET time64									# Creation time
getct LNGNAME string 0x00					# Language name
getct LNGLOCNAME unicode 0x00		# Native language name
getct TRANSLATOR unicode 0x00			# Author
getct CONTACT unicode 0x00				# Author e-mail address

string NAME += ".head"
math HDRSIZE += 0x4
  log NAME 0 HDRSIZE							# Extract header
savepos POSITION

############### text section ###############
get TXTSIZE long
math TXTSIZE += 0x4
string NAME = FNAME							# Name reset
string NAME += ".lang"
  log NAME POSITION TXTSIZE				# Extract text (.lang file)

math POSITION += TXTSIZE
goto POSITION

############### font section ###############
get FNTCOUNT short								# Number of included fonts
for i = 0 < FNTCOUNT
  get FNTBLOCKSIZE long						# Size of the font block
  get BYTE byte										# Unknown
  getct FNTVAR string 0x00					# Font variable
  get BYTE byte										# Unknown
  getct FNTID string 0x00						# Font ID
  get SCALE float										# Scale parameter
  get SCALEX float									# ScaleX parameter
  get SCALEY float									# ScaleY parameter
  get OFFSETX float									# OffsetX
  get OFFSETY float									# OffsetY
  get MAXSIZE float									# Font's max. size
  get LINESPACING float							# Linespacing parameter
  get FNTSIZE long									# Size of TTF/OTF font
  savepos POSITION
    log FNTID POSITION FNTSIZE
  math POSITION += FNTSIZE
  goto POSITION
  getct LICENSE unicode 0x00				# License
  get NULL long
next i

```


And BTW, game has some bugs, like missing words, small linespacing or cutted sentences, so it will be not your fault
## Post #25
- Username: artdekdok
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 13, 2016 4:46 am
- Post datetime: 2016-04-16T04:55:55+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

.
## Post #26
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-04-16T09:34:52+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Did you delete LocalizationBinFonts folder after lngp editing?
## Post #27
- Username: artdekdok
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 13, 2016 4:46 am
- Post datetime: 2016-04-16T16:10:17+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

.
## Post #28
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-04-17T08:19:15+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Yes, I also had problems with crashing. Unfortunatelly I don't know what was the problem, but I somehow made a modified English.lngp, which actually works
## Post #29
- Username: AgeNT2k21
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 28, 2021 5:54 am
- Post datetime: 2021-05-27T22:07:35+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

Good afternoon. If your please help with the script for the game Frostpunk.
The publisher is the same.
You only need binfont2dds and dds2binfon.

Example font [https://ufile.io/etjymgpy](https://ufile.io/etjymgpy)

Thank you very much for any help.
I know English poorly, I use a translator.
## Post #30
- Username: AgeNT2k21
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 28, 2021 5:54 am
- Post datetime: 2021-05-30T15:25:51+00:00
- Post Title: Re: This War of Mine (.binfont, .texture)

I understand that the theme of 2014. But the code still works. Is it so difficult to specify exactly where in the file the graphic format begins?
