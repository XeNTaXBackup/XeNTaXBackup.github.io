## Post #1
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2013-02-27T23:28:41+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

Hello all,

I'm looking at extracting the 3D files from the Star Wars Pinball PKG archive. 

Edit: PKG file has been extracted and now we have PXP archives. I'm now looking into the PXP files. Again, any further help would be appreciated.

Thanks


Here is a sample of the PXP file
[http://www.sendspace.com/file/4bv1uz](http://www.sendspace.com/file/4bv1uz)

Here is a sample of the PKG file
[http://www.sendspace.com/file/kueg10](http://www.sendspace.com/file/kueg10)
This is from the PS3 Zen Pinball 2 DLC

Developer: Zen Studios
[http://www.starwarspinball.com/](http://www.starwarspinball.com/)
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-02-28T00:24:53+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

[http://ps3zone.ifcaro.net/archivos/PkgView_1.3.rar](http://ps3zone.ifcaro.net/archivos/PkgView_1.3.rar)
## Post #3
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2013-02-28T03:36:41+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

> Reply from Thief1987
>
> http://ps3zone.ifcaro.net/archivos/PkgView_1.3.rar
Thanks for the download. It works every time!

Now we have a couple of PXP files extracted, which contains all assets by the looks of them.
## Post #4
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2013-02-28T04:07:28+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

Now, looking into the PXP files we can see some file names with extensions such as DFT and DMV. Haven't figured out decompression method yet.

Any advice?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-02T19:29:16+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

the pxp files use an unknown compression where all the data begins with 0x04, while the following is the format:

```
idstring "PX"
get DUMMY short
get INFO_SIZE long
get DATA_OFFSET long
get FILES long
get DUMMY long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get TYPE byte
    get NAMESZ byte
    getdstring NAME NAMESZ
    padding 4
    get ZSIZE long
    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #6
- Username: datahaven
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 09, 2013 6:23 am
- Post datetime: 2013-10-09T14:19:40+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

Anyone still interested in this? I have the droids you are looking for ...  

This QuickBMS script (exactly the same as the one above but with clog replaced by log) extracts the raw compressed data into separate files:

```
# Extracts the compressed resources from the .PXP
# file but does NOT decompress them
idstring "PX"
get DUMMY short
get INFO_SIZE long
get DATA_OFFSET long
get FILES long
get DUMMY long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get TYPE byte
    get NAMESZ byte
    getdstring NAME NAMESZ
    padding 4
    get ZSIZE long
	log NAME OFFSET ZSIZE
next i

```

You can use the -f option if you only want to extract particular kinds of files.

Here's the good bit - the following script will take one of the single files that you extracted above and will decompress it:

```
# (CastleStorm, Pinball FX2)
# Adrian Dale 09/10/2013
# 
# Needs NeoWizLib.dll provided by Ekey
# http://forum.xentax.com/viewtopic.php?f=10&t=10654
#
# This script decompresses a single resource file that has previously
# been extracted from a .PXP file.
# This has been tested with files from Pinball FX2 and appears to
# successfully decompress most of the files in the archives.
log MEMORY_FILE3 0 0

do
  get CHUNKTYPE byte
  If CHUNKTYPE == 0x03
    get ZSIZE threebyte
    SavePos IN_OFFSET
	set SIZE long 0x80000
	#print "%CHUNKTYPE% %ZSIZE|hex% %SIZE|hex% %IN_OFFSET|hex%\n"
    log MEMORY_FILE IN_OFFSET ZSIZE
    putvarchr MEMORY_FILE2 SIZE 0
    CallDLL NeoWizLib.dll NWDecompress stdcall "" MEMORY_FILE MEMORY_FILE2 SIZE
    
	math IN_OFFSET + ZSIZE
    goto IN_OFFSET
	
  ElseIf CHUNKTYPE == 0x04
    get SIZE threebyte
	get ZSIZE threebyte
	SavePos IN_OFFSET
	#print "%CHUNKTYPE% %SIZE% %ZSIZE|hex% %IN_OFFSET|hex%\n"
	log MEMORY_FILE IN_OFFSET ZSIZE
	putvarchr MEMORY_FILE2 SIZE 0
    CallDLL NeoWizLib.dll NWDecompress stdcall "" MEMORY_FILE MEMORY_FILE2 SIZE
  Endif
  
  # Now tag MEMORY_FILE2, which is the decompressed chunk
  # onto the end of MEMORY_FILE3
  append
  log MEMORY_FILE3 0 SIZE MEMORY_FILE2
  append
  
while CHUNKTYPE != 0x04

get NAME basename
get EXT extension
string NAME += "_unpacked."
string NAME += EXT

get FULL_SIZE asize MEMORY_FILE3
log NAME 0 FULL_SIZE MEMORY_FILE3

```


To run this you'll need the NeoWizLib.dll file from Ekey's CastleStorm decompression tool. That's attached to his post [here](http://forum.xentax.com/viewtopic.php?f=10&t=10654). Drop that so that QuickBMS can find it when you run it.

I can't guarantee that this works on every file. In fact it crashes on dotmatrix\csicsa.dmv in the two archives I tried. This makes Ekey's tool crash, otherwise you could just use that to unpack the whole pxp file. I've got round that by allowing you to decompress files individually. Note that I used the PC version of the game from Steam to test this.

I don't know where Ekey got the NeoWizLib.dll file from - did it come with CastleStorm? I checked that because it is also made by Zen Studios. Anyway, the code in that dll looks identical to the code compiled into the PFX2 exe.

I have a rough idea of how it works - it seems to be a variant of the Deflate algorithm but with a different file format and slightly different way of storing the data. I can post more if anyone is interested? It would be great if there was already an existing compressor for this format, as then it would be possible to mod the PFX2 files and put them back into the game.

There are some interesting files in the archives. There is an obfuscated python file for each table, which appears to describe how the various switches and lights connect together.

There are also the .dmv files which are the Dot Matrix Video files. Their format is pretty simple:
A two byte frame count; then for each frame four bytes of unknown purpose, possibly frame timing info; then 1024 bytes of frame data. So, 32 rows, x 32 bytes is 1024, which means a byte is 4 pixels. This translates to a 128x32 pixel three colour screen with the other bit being an alpha flag.

I may have a look at extracting the model and animation data as there are some cool resources in this game. If you are curious, you can download the main game for free on Steam [here](http://store.steampowered.com/app/226980/) and it comes with one playable table, with the rest available as paid DLC. If you're only interested in extracting the resources, then you won't even need to pay to unlock the DLC as the files are already there on your PC for the preview versions of the tables.

Adrian
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-09T18:12:17+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

I noticed decompress work fine only on plaintext files, on other files like sounds, textures and .ect it crashed. Later I will try to do something.
## Post #8
- Username: nbajam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 24, 2010 5:39 am
- Post datetime: 2013-11-24T22:36:10+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

What about re-packing the raw compressed data into a .pxp file? If it's a lot of work, forget I ever asked... but if it's simple (I'm not familiar with QuickBMS), I'd love to use such a script. Why? Well, right now there's one table that's only on the 360 / PS3 versions of the game (Plants Vs. Zombies).

Between the 360 and PC versions, they both use .pxp files. I've tried renaming the Plants Vs. Zombies table to the name of a table that is on the PC version (ex. "Paranormal.pxp" or "MARVEL_CivilWar.pxp"), but so far I'm unsuccessful in getting it to load. It greys-out the table in the main menu and tells you to re-download it.

If it's possible to re-pack PXP files, I can try using some of the meta and XML files from an existing table, and only swap in the table design and graphics files.

In case anyone accuses me of doing something immoral, please be aware that I have a near-complete pinball collection between the 360 and PC versions of the game, and I did buy the Plants Vs. Zombies table on the Xbox 360.

> Reply from datahaven
>
> Anyone still interested in this? I have the droids you are looking for ...  

This QuickBMS script (exactly the same as the one above but with clog replaced by log) extracts the raw compressed data into separate files:
## Post #9
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2014-06-22T22:54:40+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

Hi, I tried the above qbms to extract the files from kickbeat and worked ok. Now, I can't make the decompression script works on the sound files, as they do not start neither with 0x3 nor 0x4. They are mp3 files that seems to be compressed with an unknown algo. If you drop the files on any music player they play, but you can hear a lot of glitches here and there (probably because of the compression).

Can someone take a look at one file and see if you can decompress it with the above decompression tool? [Here you have test file...](http://www.extremefx.com.ar/files.axd?src=Tutorial01.mp3)
## Post #10
- Username: Kylor
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 09, 2016 2:59 am
- Post datetime: 2016-01-19T09:26:04+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

> Reply from datahaven
>
> Anyone still interested in this? I have the droids you are looking for ...  

This QuickBMS script (exactly the same as the one above but with clog replaced by log) extracts the raw compressed data into separate files:
Code: Select all# Pinball FX2 .PXP resource extractor
# Extracts the compressed resources from the .PXP
# file but does NOT decompress them
idstring "PX"
get DUMMY short
get INFO_SIZE long
get DATA_OFFSET long
get FILES long
get DUMMY long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get TYPE byte
    get NAMESZ byte
    getdstring NAME NAMESZ
    padding 4
    get ZSIZE long
	log NAME OFFSET ZSIZE
next i

You can use the -f option if you only want to extract particular kinds of files.

Here's the good bit - the following script will take one of the single files that you extracted above and will decompress it:
Code: Select all# Zen Studios .PXP file decompresser
# (CastleStorm, Pinball FX2)
# Adrian Dale 09/10/2013
# 
# Needs NeoWizLib.dll provided by Ekey
# http://forum.xentax.com/viewtopic.php?f=10&t=10654
#
# This script decompresses a single resource file that has previously
# been extracted from a .PXP file.
# This has been tested with files from Pinball FX2 and appears to
# successfully decompress most of the files in the archives.
log MEMORY_FILE3 0 0

do
  get CHUNKTYPE byte
  If CHUNKTYPE == 0x03
    get ZSIZE threebyte
    SavePos IN_OFFSET
	set SIZE long 0x80000
	#print "%CHUNKTYPE% %ZSIZE|hex% %SIZE|hex% %IN_OFFSET|hex%\n"
    log MEMORY_FILE IN_OFFSET ZSIZE
    putvarchr MEMORY_FILE2 SIZE 0
    CallDLL NeoWizLib.dll NWDecompress stdcall "" MEMORY_FILE MEMORY_FILE2 SIZE
    
	math IN_OFFSET + ZSIZE
    goto IN_OFFSET
	
  ElseIf CHUNKTYPE == 0x04
    get SIZE threebyte
	get ZSIZE threebyte
	SavePos IN_OFFSET
	#print "%CHUNKTYPE% %SIZE% %ZSIZE|hex% %IN_OFFSET|hex%\n"
	log MEMORY_FILE IN_OFFSET ZSIZE
	putvarchr MEMORY_FILE2 SIZE 0
    CallDLL NeoWizLib.dll NWDecompress stdcall "" MEMORY_FILE MEMORY_FILE2 SIZE
  Endif
  
  # Now tag MEMORY_FILE2, which is the decompressed chunk
  # onto the end of MEMORY_FILE3
  append
  log MEMORY_FILE3 0 SIZE MEMORY_FILE2
  append
  
while CHUNKTYPE != 0x04

get NAME basename
get EXT extension
string NAME += "_unpacked."
string NAME += EXT

get FULL_SIZE asize MEMORY_FILE3
log NAME 0 FULL_SIZE MEMORY_FILE3


To run this you'll need the NeoWizLib.dll file from Ekey's CastleStorm decompression tool. That's attached to his post here. Drop that so that QuickBMS can find it when you run it.

I can't guarantee that this works on every file. In fact it crashes on dotmatrix\csicsa.dmv in the two archives I tried. This makes Ekey's tool crash, otherwise you could just use that to unpack the whole pxp file. I've got round that by allowing you to decompress files individually. Note that I used the PC version of the game from Steam to test this.

I don't know where Ekey got the NeoWizLib.dll file from - did it come with CastleStorm? I checked that because it is also made by Zen Studios. Anyway, the code in that dll looks identical to the code compiled into the PFX2 exe.

I have a rough idea of how it works - it seems to be a variant of the Deflate algorithm but with a different file format and slightly different way of storing the data. I can post more if anyone is interested? It would be great if there was already an existing compressor for this format, as then it would be possible to mod the PFX2 files and put them back into the game.

There are some interesting files in the archives. There is an obfuscated python file for each table, which appears to describe how the various switches and lights connect together.

There are also the .dmv files which are the Dot Matrix Video files. Their format is pretty simple:
A two byte frame count; then for each frame four bytes of unknown purpose, possibly frame timing info; then 1024 bytes of frame data. So, 32 rows, x 32 bytes is 1024, which means a byte is 4 pixels. This translates to a 128x32 pixel three colour screen with the other bit being an alpha flag.

I may have a look at extracting the model and animation data as there are some cool resources in this game. If you are curious, you can download the main game for free on Steam here and it comes with one playable table, with the rest available as paid DLC. If you're only interested in extracting the resources, then you won't even need to pay to unlock the DLC as the files are already there on your PC for the preview versions of the tables.

Adrian

This is good but can someone please explain how to set this up so I can extract stuff? Like what must I put in a new folder to get this ready to extract?
## Post #11
- Username: ariarosmurf
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 14, 2016 7:51 pm
- Post datetime: 2016-05-10T17:16:40+00:00
- Post Title: Star Wars Pinball (PS3) *.PXP File

Hello I was trying to play force awakensi n Pinball. But when i heard Kylo rens voice i had to get the voice lines "sound files" i was trynig to go in the folders but they dont show the folders for kylo rens voice "voice only" how can i get the sound files? help!
