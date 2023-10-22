## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-11-25T22:13:16+00:00
- Post Title: Graphics/Texture finders and viewers

TextureFinder 1.3.2

Designed to find textures inside any uncompressed files. Any size, any pixel bit format, any binary file. It only requires that the file be uncompressed. This tool is intended to be used by researchers and developers with a good understanding of bitmap formats.
VERSION 1.3.2 is the last one of this first series.

Formats implemented so far:

TRUE COLOUR (RGBA) FORMATS :
64bits                  16x4
48bits                  16x3
32bits                  8888
24bits                    888
16bits                    565
15+1bits              1555
12+4bits              4444
08+8bits              8332
08bits                    332
06+2bits              2222

PALETTE FORMATS :
P8             256 colours
P4               16 colours
P1                 2 colours

QUAD FORMATS (alpha channel implemented only in series 2) :
DXT1
DXT3
DXT5

TextureFinder 2.1


Newer and better version of TextureFinder.

Tile Molester 0.16

Tile Molester, or TM for short, is a program that facilitates the viewing and editing of raw graphics data; that is, graphics contained in arbitrary binary files, where one usually doesn't have initial knowledge about the location and/or format of the graphics. The main area of application thus far has been videogame console binaries. In most cases, these files contain a large variety of data, not just graphics -- sound data and actual game code are two examples. Collections of data in one and the same file may be interspersed in any conceivable fashion, subject to hardware/software-constraints of the intended runtime-environment as well as the decisions made by the producers of the binary (the developers).

TM is a kind of visual explorer of such files, in that it allows the file contents to be interpreted and displayed in a multitude of ways. By perusing the file and tweaking the settings of the renderer, the binary data that corresponds to graphics may be made accessible in the way they are intended, and edited to the satisfaction of the user. 

TiledGGD 2.0.3.0

A generic graphics dumping tool, based on the elusive program GGD

TiledGGD - basically it’s GGD (General Graphical Dump tool), with some extra features: Currently working (extra) features:

* Support for tiled graphics (tiles of any size) and palettes (tile sizes are restricted, because they need to fit a 16*16 grid) * Copy visible graphics and palette directly to clipboard * ‘Go To Offset’ functionality * Toggle Endianness of graphics and palette separately * Save the entire graphics * Built-in NCGR/NCBR and NCLR support (I’m not using all the data from the files, so there are most likely still some bugs) * Lua plugin support 




DOWNLOAD TOOLS

If you know any other useful programs to search for graphics in files, you can share here.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-12-07T11:13:37+00:00
- Post Title: Graphics/Texture finders and viewers

Nice !
## Post #3
- Username: Acewell
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-06-18T10:39:46+00:00
- Post Title: Graphics/Texture finders and viewers

Rainbow is a tool intended to convert different graphics formats from video games assets to and from user editable images (like png). It currently supports almost every variant of the TIM2 format.

The main difference with other great tools like Tile Molester and Crystal Tile 2 is to provide direct support to proprietary graphics formats found in "new generation" consoles, like PS2, PSP, Wii, etc., instead of dealing with just the raw image data.

Features

    The underlying image library has almost complete support to TIM2 texture files usually found in PS2 and PSP games. The app supports multi-layer, multi-clut, swizzled (PSP)/unswizzled TIM2 images with both linear, interleaved palettes, and segments headers eventually extended with custom user data (usually used by programmers).
    Can open textures in any format supported by the underlying image library.
    Can open whole folders in search of supported texture formats. All known texture files are then displayed in a list.
    Can export and import textures in suitable image formats for editing (like png).
    Any additional information specific to the texture is preserved when exporting/importing (like the TIM2 header data), in order to have a one-to-one correspondence with the original texture.
    Customizable background color for transparent and semi-transparent images with chessboard like pattern.
    Finally, Rainbow supports parameters via command line: the first parameter is the name of a texture you would like to open.


DOWNLOAD


Console Texture Explorer (PSP/PS2) is an application that allows working with PSP and PS2 textures. It helps to minimize manual work during texture resources manual scanning and graphics data research in raw archives.

Version: 1.0b
Designed and made by: Dageron
Year: 2012

======
Supported platforms: PSP and PS2
Supported formats: any texture dictionaries with 4bpp/8bpp graphics data

DOWNLOAD
## Post #4
- Username: Tosyk
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-06-03T14:04:30+00:00
- Post Title: Graphics/Texture finders and viewers

Raw texture previewer/converter



screenshot000046.jpg (232.53 KiB) Viewed 2920 times



Download here: [viewtopic.php?f=18&t=16461](http://forum.xentax.com/viewtopic.php?f=18&t=16461)
## Post #5
- Username: swosho
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-07-16T09:28:29+00:00
- Post Title: Graphics/Texture finders and viewers

PVRTexTool



screenshot000515.jpg (207.98 KiB) Viewed 2879 times



Download: [https://community.imgtec.com/downloads/ ... k-2018-r1/](https://community.imgtec.com/downloads/windows-installer-powervr-tools-and-sdk-2018-r1/)
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-10T14:29:36+00:00
- Post Title: Graphics/Texture finders and viewers

Cheat Engine - Graphical Memory View



screenshot000803.png (134.59 KiB) Viewed 2208 times


[CHEAT ENGINE DOWNLOAD](https://www.cheatengine.org/downloads.php)
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-08T18:52:13+00:00
- Post Title: Graphics/Texture finders and viewers

screenshot000884.png (106.38 KiB) Viewed 2150 times



AMD Compressonator --> [https://gpuopen.com/compressonator/](https://gpuopen.com/compressonator/)
[https://github.com/GPUOpen-Tools/compressonator](https://github.com/GPUOpen-Tools/compressonator)
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-21T18:35:14+00:00
- Post Title: Graphics/Texture finders and viewers

Some new tools are listed here --> [https://tcrf.net/Help:Contents/Finding_ ... g_graphics](https://tcrf.net/Help:Contents/Finding_Content/Finding_graphics)
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-15T14:01:48+00:00
- Post Title: Graphics/Texture finders and viewers

> RAW pixels viewer
>
> This application allows you analyze raw image data, you can display memory dumps of frame buffers, video buffers and uncompressed video files. Play with image parameters below to explore world of colors.
[https://imgur.com/a/ZJQtO8B](https://imgur.com/a/ZJQtO8B)

[http://rawpixels.net/](http://rawpixels.net/)
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-20T17:32:37+00:00
- Post Title: Graphics/Texture finders and viewers

TileShop and ImageMagitek

> TileShop is a WPF application for Windows that implements ImageMagitek and allows end-users to manage specialized graphics in a modern GUI environment. ImageMagitek is an internal .NET library written in C# to view, edit, and organize common and complex retro videogame system graphics. Emphasis is given to the features most valuable to the common, cumbersome tasks when encountering graphics embedded within binaries without any distinguishable headers or identifiers. Exporting and importing is supported to allow advanced editing features to be performed in third-party image editors that operate on standard PNG.
[https://github.com/stevemonaco/ImageMagitek](https://github.com/stevemonaco/ImageMagitek)
## Post #11
- Username: th3ru
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 29, 2020 8:46 pm
- Post datetime: 2021-06-05T18:33:12+00:00
- Post Title: Graphics/Texture finders and viewers

Raw Image Viewer module of Kuriimu2. 
+ live preview as you change parameters.
- no drag&drop, to be launched from K2, extracts only to png.
[https://github.com/FanTranslatorsInternational/Kuriimu2](https://github.com/FanTranslatorsInternational/Kuriimu2)
[K2RIV.jpg](https://xentaxbackup.github.io/file/20257_K2RIV.jpg)
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-04T19:25:25+00:00
- Post Title: Graphics/Texture finders and viewers

Mumm-Ra's Game Graphics Tool



mumm_ra_tool.png (279.33 KiB) Viewed 1408 times



Download:
old version -> [https://drive.google.com/file/d/1ZeRQcU ... sp=sharing](https://drive.google.com/file/d/1ZeRQcU-cqOO5gdRGV_kgvsrq_jBoCFgH/view?usp=sharing)

version 96 -> [https://drive.google.com/file/d/1kw1YVD ... jVpmO/view](https://drive.google.com/file/d/1kw1YVDzPATMCS5fZYDTiPwosqhGjVpmO/view)

version 100 --> [https://drive.google.com/file/d/1mc8gGT ... 2f4ze/view](https://drive.google.com/file/d/1mc8gGTt_O7HpcthqXQfEc30TgV_2f4ze/view)
## Post #13
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-11-07T16:51:04+00:00
- Post Title: Graphics/Texture finders and viewers

Pixel Reader by Leo2236
[](https://ibb.co/4jy4Ljp)

Open any file to view it in pixel format
[](https://ibb.co/TMQQ04M)

Creator Site
[http://lgt.createaforum.com/index.php](http://lgt.createaforum.com/index.php)
[PixelsReader.zip](https://xentaxbackup.github.io/file/21182_PixelsReader.zip)
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-23T12:23:28+00:00
- Post Title: Graphics/Texture finders and viewers

TextureFinder (Noesis)



DOWNLOAD --> [LINK](https://forum.xentax.com/viewtopic.php?t=26113)
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-27T14:33:31+00:00
- Post Title: Graphics/Texture finders and viewers

GIMP - Load Image from Raw Data



screenshot000254.png (62.41 KiB) Viewed 702 times



How to use this functionality:
1. Download GIMP 2.10
2. Change your file's extension to *.data
3. Open GIMP
4. Go to File > Open in GIMP
5. Load your *.data file in GIMP
6. Click "Open" in the new window.
## Post #16
- Username: th3ru
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 29, 2020 8:46 pm
- Post datetime: 2023-03-06T15:47:39+00:00
- Post Title: Re: Graphics/Texture finders and viewers

PixelDbg - view any type of file as image data, using a number of different formats.



Downloads: [https://sourceforge.net/projects/pixeldbg/](https://sourceforge.net/projects/pixeldbg/) (source + binaries for Windows and Linux) 

(originally found on [tcrf](https://tcrf.net/Help:Contents/Finding_Content/Finding_graphics) | not tested personally)
