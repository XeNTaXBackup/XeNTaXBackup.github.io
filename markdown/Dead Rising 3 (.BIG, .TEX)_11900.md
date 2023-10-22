## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-04T14:01:16+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "\x06\x05\x04\x03"
get HEADER_SIZE long
get ARCHIVE_SIZE long
get FILES long
get ENTRY_OFFSET long
goto ENTRY_OFFSET

for i = 0 < FILES
    get NAME_OFFSET long
    savepos TEMP
    goto NAME_OFFSET
    get NAME string
    goto TEMP
    get HASH long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get DUMMY long # 4
    get FLAG long # 0, 1 - Compressed (Encrypted??)
	
    if SIZE == ZSIZE
      log NAME OFFSET SIZE
    else
      # Unknown Compression or Encryption
      log NAME OFFSET ZSIZE
    endif
next i
```


Also you can try use [http://aluigi.altervista.org/papers/bms ... g2_otr.bms](http://aluigi.altervista.org/papers/bms/deadrising2_otr.bms)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-09-04T22:27:37+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

Thank you sir!!
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-09-07T03:01:36+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

i wish one day there will be an repacker for dead rising
## Post #4
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2014-09-07T09:32:57+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

what about cvs files with texts??
## Post #5
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2014-09-07T09:35:09+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

Thanks for bms Ekey. How about texts ? Do you know where is texts ?
## Post #6
- Username: Thevoid
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 23, 2010 9:23 pm
- Post datetime: 2014-09-07T09:39:36+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

How about the .bin files? maybe part of the text from the game are inside these files.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-07T10:43:30+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

> Reply from desperado
>
> Thanks for bms Ekey. How about texts ? Do you know where is texts ?
I don't know.
## Post #8
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2014-09-08T03:30:15+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

> Reply from desperado
>
> Do you know where is texts ?
There: data\ui\dr3main\dr3main_en.cvs
## Post #9
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2014-09-08T09:03:31+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

> Reply from LinkOFF
>
> desperado wrote:Do you know where is texts ?
There: data\ui\dr3main\dr3main_en.cvs

Thanks
## Post #10
- Username: FriskyNoodle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 09, 2014 1:14 am
- Post datetime: 2014-09-08T17:25:24+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

I saved your script as a .txt file. Open QuickBMs, choose script>location>save location for unapacked .big files

I tried to unpack gen_shader-ps.big and then the location those extracted to had more gen_shader-XX.big files, tried to unpack those and did the same process as listed above and it throws me an error 

Screen attached:



After that I replaced the "expected" with "this one" and re ran the process it did nothing at all. All it did do was show the CMD window for QuickBMS

Am I stupid and did something obviously wrong? Or is the script only working for certain .big archives?
## Post #11
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2014-09-08T22:02:56+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

Looks like the first 8 bytes of that .big file are missing.
## Post #12
- Username: FriskyNoodle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 09, 2014 1:14 am
- Post datetime: 2014-09-08T23:11:37+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

> Reply from Sir Kane
>
> Looks like the first 8 bytes of that .big file are missing.

I dont see why? Would that be a problem with the script and quickbms not finding the first 8 bytes, or the games encryption method to prevent unpacking the game?

Or does no one else have this issue and I have a bad copy?
## Post #13
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2014-09-09T00:29:31+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

Try opening the file in a hex editor and check if the first few bytes are 06 05 04 03.
## Post #14
- Username: FriskyNoodle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 09, 2014 1:14 am
- Post datetime: 2014-09-09T01:45:07+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

> Reply from Sir Kane
>
> Try opening the file in a hex editor and check if the first few bytes are 06 05 04 03.

06 05 04 03 D3 88 07 00 04 E5 F3 0B CF 2F 00 00

Yeah it is. I know it may be something that Im doing wrong, maybe since my game is located in program files(x86) but I made sure to run the QuickBMS CMD window in Administrator (UAC is disabled). So I really dont know what the issue is.


**EDIT**

For the first archive it works, and thats what the first 8 bytes are, but I want to unpack the "sub archive" that was inside the .big file, another like 4 .big files. 

So I have to open a HEX Editor, look at the first 8 bytes and change them from 06 05 04 03 to 0B F3 E5 04 in the script right? If thats the issue then I'm really stupid.

**EDIT2**

This is what happened after I tried it on the sub archives first 8 bytes I replaced in the script



Even though the file I attempted to unpack is 47mb


Also how do I make it so images are so huge and annoying/off putting to everyone else?
## Post #15
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2014-09-09T02:32:15+00:00
- Post Title: Dead Rising 3 (*.BIG, *.TEX)

Oh wait, it's like that because the script doesn't handle the compression.
Might post something that does tomorrow.
## Post #16
- Username: FriskyNoodle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 09, 2014 1:14 am
- Post datetime: 2014-09-09T02:39:17+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

> Reply from Sir Kane
>
> Oh wait, it's like that because the script doesn't handle the compression.
Might post something that does tomorrow.

Thanks for clarifying, would love to see something soon.
## Post #17
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2014-09-09T08:35:35+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

Script for MultiEx:

```
Get U1 Long 0 ;
Get HeaderSize Long 0 ;
Get ArchiveSize Long 0 ;
Get FNum Long 0 ;
Get ITableOffset Long 0 ;
Get ITableEnd Long 0 ;
For T = 1 To FNum ;
Get NameOffset Long 0;
Get U2 Long 0 ;
Get PackSize Long 0 ;
Get UnpackSize Long 0 ;
Get Offset Long 0 ;
Get PadSize Long 0 ;
Get Compressed Long 0 ;
SavePos POS 0 ;
GoTo NameOffset 0 ;
Get Name String 0 ;
Log Name Offset PackSize 0 0 ;
GoTo POS 0 ;
Next T ;
```


P.S. How to decrypt BCT and BCF files in archives?
## Post #18
- Username: FriskyNoodle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 09, 2014 1:14 am
- Post datetime: 2014-09-17T03:55:32+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

Any progress to extract sub archives?
## Post #19
- Username: Thevoid
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 23, 2010 9:23 pm
- Post datetime: 2014-10-20T21:40:42+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

Is there any progress with the extractor and packer for this?
## Post #20
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-10-21T10:38:42+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

> Reply from LinkOFF
>
> desperado wrote:Do you know where is texts ?
There: data\ui\dr3main\dr3main_en.cvs

Anyone found font file image? Thanks!
## Post #21
- Username: filu23
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Feb 03, 2014 8:30 pm
- Post datetime: 2014-10-22T13:41:51+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

font: Dead Rising 3\data\system

You extracted the file dr3main_en.cvs?
## Post #22
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-08T10:37:12+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

Hi 

At one time  i wrote python script for importing characters  from Dead Rising 3.
It is not finished, but it can to use.
It requires Blender 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select big file

It supports:
- autotexturing 
- weighting
- skeleton
[Blender249[DeadRising3][PC][big][tex][2014-12-08].zip](https://xentaxbackup.github.io/file/8219_Blender249[DeadRising3][PC][big][tex][2014-12-08].zip)
## Post #23
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2014-12-11T01:27:27+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

i know the script isn't finished but is there any way to convert the normal maps proper?
unfortunately they come out checkered.
or maybe there's another way to convert the .tex files alone.
here's a sample file, if anyone's interested.
[https://www.dropbox.com/s/s1lezerm2sm05 ... 02.7z?dl=0](https://www.dropbox.com/s/s1lezerm2sm05ap/psy_02.7z?dl=0)
## Post #24
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-11T19:18:32+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

TheMask85: are there any DXT3 and DXT5 textures? Normal maps are saved in ATI2 (BC5) format.

Example: psy_02_head_nm
[](http://www.fastimages.eu/?v=psy02headn.png)

So here are my QBMS scripts for texture converting.

tex to dds

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

if FORMAT == "0x00"			# RGBA8
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x0F\x10\x00\x00\x41\x41\x41\x41\x42\x42\x42\x42\x43\x43\x43\x43\x43\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x41\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\xFF\x00\x00\xFF\x00\x00\xFF\x00\x00\x00\x00\x00\x00\xFF\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif FORMAT == "0x08"		# DXT1
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
elif FORMAT = "0x26"		# ATI2 - normal map
	set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\xDD\xDD\xDD\xDD\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x41\x54\x49\x32\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
endif

	putVarChr MEMORY_FILE 0XC HEIGHT long
	putVarChr MEMORY_FILE 0x10 WIDTH long
	putVarChr MEMORY_FILE 0x14 DATA_SIZE long
	putVarChr MEMORY_FILE 0X1C MIP_COUNT long

append
log MEMORY_FILE DATA_OFF DATA_SIZE
append

get DDS_SIZE asize MEMORY_FILE
log H_NAME 0 DATA_OFF			# save header
log NAME 0 DDS_SIZE MEMORY_FILE	# save DDS texture

```


dds to tex

```
# DDS to texture converter
# by MerlinSVK    		Dec 2014
# version 1.0
# note: If you edit a texture, save it with the exact number of mipmaps as original texture has.
#       This script will not recalculate the mipmap offsets in header section. KTHXBYE
# script for QuickBMS	http://aluigi.org/papers.htm#quickbms

open FDDE dds 0
open FDDE head 1

get NAME basename
string NAME += ".new"

get D_SIZE asize 0
get H_SIZE asize 1

math D_SIZE -= 0x80				# subtract the DDS header
log MEMORY_FILE 0 H_SIZE 1		# copy header file into memory_file

append
log MEMORY_FILE 0x80 D_SIZE 0	# append whole texture data
append

get TEX_SIZE asize MEMORY_FILE
log NAME 0 TEX_SIZE MEMORY_FILE

```
## Post #25
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-15T20:06:00+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

> Reply from Szkaradek123
>
> Hi 

At one time  i wrote python script for importing characters  from Dead Rising 3.
It is not finished, but it can to use.
It requires Blender 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select big file

It supports:
- autotexturing 
- weighting
- skeletonHi Szkaradek123, thank you for your great work, this script run the NPC character format is perfect, we very much look forward to the script will continue to support the vehicle model and the model of zombies
## Post #26
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2015-04-15T05:25:22+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

Sorry if this is a noobie question, but how are people handling the normal maps? Still can't get them to work.

EDIT - Yes, noobish question. Once running the tex to dds BMS script, I just needed to open the file in Noesis instead of my image editor
## Post #27
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-04-25T06:05:56+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

*SNIP* Got some good advise and now understand the process. Awesome scripts and tools guys.
## Post #28
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-11-28T03:42:58+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

> Reply from Szkaradek123
>
> Hi 

At one time  i wrote python script for importing characters  from Dead Rising 3.
It is not finished, but it can to use.
It requires Blender 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select big file

It supports:
- autotexturing 
- weighting
- skeleton

Just curios if anyone found y way to extract the main character models in the "clothing" directory correctly...
## Post #29
- Username: jupiter
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 02, 2023 6:30 pm
- Post datetime: 2023-03-13T12:59:40+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

how extracted the file dr3main_en.cvs?
## Post #30
- Username: wolf84
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 16, 2019 7:00 am
- Post datetime: 2023-06-19T19:18:48+00:00
- Post Title: Re: Dead Rising 3 (*.BIG, *.TEX)

> Reply from jupiter ↑Mon Mar 13, 2023 8:59 pm at Mon Mar 13, 2023 8:59 pm
>
> 
how extracted the file dr3main_en.cvs?

Hi, you don't just have to unpack it, you also have to repack it...  [https://www.youtube.com/watch?v=5HI4HDyvGqM](https://www.youtube.com/watch?v=5HI4HDyvGqM)
