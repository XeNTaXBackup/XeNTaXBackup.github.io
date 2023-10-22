## Post #1
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2020-01-25T20:41:55+00:00
- Post Title: Akimbo Kung Fu Hero Sprites (SPX / SPC)

Hello
Finally I unpacked .VOL archive file from this game. I spent last days to look into files with Hex Editor. In one of them I read that files are in SPC or SPX format. Example lines from this file:

!COMMON\STWORY\SPIDERTWO\SPIDERBIEGL.SPX
!COMMON\ARCHITEKTURA\LAS\KOLCE.SPC

etc.
Maybe someone knows how to open or convert (maybe with Quickbms script) files to BMPs. Also I read in one of game .dll that files maybe compressed in RLE8, RGB555 but I am not sure. I do not have enough knowledge.
Here I uploaded some files:
[https://www.mediafire.com/file/ptm5yqy1 ... s.zip/file](https://www.mediafire.com/file/ptm5yqy113sk3g7/akimbo_kung_fu_hero_samples.zip/file)

Thanks for any help. ; )
## Post #2
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-10-15T12:56:18+00:00
- Post Title: Akimbo Kung Fu Hero Sprites (SPX / SPC)

Hello after many months. I have enough informations to share. For now I'm looking someone who could write little app to get images from SPX/SPC files faster and automatically export as PNGs, still I don't have skills to write this by my own. I will try explain as best as I can, So:

SPX structure - little endian

```
	{
		11 BYTES String	- CWE sprite
		4  BYTES 		- SPX/SPC (0x2C)
		4  BYTES		- SPX/SPC (0x12)
		4  BYTES		- SPX/SPC (The same value e.g. APPLERED.SPX = APPLERED.SPC)
		4  BYTES		- SPX/SPC (0x0)
		4  BYTES		- SPX (0x2) / SPC (0x1)
		4  BYTES		- SPX (0x1) / SPC (0x4)
		4  BYTES		- SPX (0x1) / SPC (0x4)
		1  BYTE			- ? (0x0)
		1  BYTE			- SPX TypeA (0x70), TypeB (0x10) / in SPC it doesn't matter?
		4  BYTES		- ? (0x0)
		4  BYTES		- ? (0x0)
		2  BYTES		- ? (0x0)
		4  BYTES		- Frames data
		4  BYTES		- Number of FRAMES (1 or more)
	}

.FRAMES DATA (X Frames, 1 or more)
	{
		.SINGLE FRAME (frame consists of X blocks)
			{
				X BYTES with 0 value (skip) / 2 BYTES - Length of block (block starts after these 2 BYTES)
					.SINGLE BLOCK (block consists of X mini blocks)
						{
							2 BYTES	- X miniblocks in one single block
							2 BYTES	- Number of pixels to skip (number of transparent pixels)
							2 BYTES - Number of pixels to draw
							2 BYTES - indexed Pixels (pointers to the palette in file)
									  if image is TypeA draw first indexed pixel, third, fifth etc.
									  if image is TypeB draw all indexed pixels
						}
				X BYTES with 0 value (skip) / 2 BYTES - End of frame (values FF FF)
			}
	}
					
.FRAMES DIMENSIONS, OFFSETS etc. (X frames, 1 or more)
	{
		.SINGLE FRAME 20 BYTES
			{
				4 BYTES - where Frame starts (without file header)
				4 BYTES - ?
				2 BYTES - X offset
				2 BYTES - Y offset
				2 BYTES - width
				2 BYTES - height
				2 BYTES - animation time?
				2 BYTES - animation time?
			}
	}

.PALETTE SPX 768 BYTES / SPC 1024 BYTES (darkened colors)

```


Some images.





You will finid these images also in archive. Other files in archive: APPLERED.SPX and 1st frame from this file, KROPKI.SPX and 1st frame from this file, SECRET_SMALL.SPX which contains 1 image, and in this file you can see "mini blocks".
[SPX Archive.zip](https://xentaxbackup.github.io/file/21029_SPX Archive.zip)
## Post #3
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-11-08T20:49:22+00:00
- Post Title: Akimbo Kung Fu Hero Sprites (SPX / SPC)

Because no one tried to help, I started to learn about binary files etc. and now I can export graphics but still it is not the fastest way. If someone wants to make it better or make SPX/SPC viewer, just use source folder in archive.

Instruction:
1. Extract files from .vol files (use tool from this thread [viewtopic.php?f=10&t=23948](https://forum.xentax.com/viewtopic.php?f=10&t=23948))
2. Use SPX file.bms (bms script from archive) to split file into frames and palette (you will also get width & height)
3. Make new folder or move spxFrame.exe to directory where you have palette file.
4. Run app and type name of frame, width, height and TYPE of file - if bms script made *.spxa files use "112", if *.spxb "16"
5. App will make img.rawd file.
6. Open created file in TextureFinder v2.1, set pixel format - 888 = 24, check RGB - BGR, change width and save image as BMP.

I know that more experienced user can make it in one app but it is better to have this solution than nothing. ; )
All images are stored in SPX files, SPC files (very small files/graphics) in 99% are used in game for objects collisions. If you want to extract graphics from SPC files, always use value 16 in spxFrame.exe app.

Below, arhive.
[https://www.mediafire.com/file/h8mykssf ... p.zip/file](https://www.mediafire.com/file/h8mykssffjh54ds/akimbo_spx_app.zip/file)
