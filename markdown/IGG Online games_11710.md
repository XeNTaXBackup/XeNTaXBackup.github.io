## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-18T19:07:54+00:00
- Post Title: IGG Online games

hello i just wanted to know if someone can look at theses games to make a unpacker i just want the images/music from the files 


Angels Online [http://ao.igg.com/download/download_link.php?id=121](http://ao.igg.com/download/download_link.php?id=121) (the data1.pak or music.pak)
Gods War Online [http://gw.igg.com/download/downCnt.php?did=10](http://gw.igg.com/download/downCnt.php?did=10) (tool to view images and .bms script [https://www.mediafire.com/?tixnu87crxbb7ll](https://www.mediafire.com/?tixnu87crxbb7ll))
Voyage Century [http://vc.igg.com/download/download_link.php?did=45](http://vc.igg.com/download/download_link.php?did=45)(.gm
Moonlight Online [http://mo.igg.com/trackLoad.php?atype=3](http://mo.igg.com/trackLoad.php?atype=3)
Myth War II [http://mw2.igg.com/download/downCnt.php?did=27](http://mw2.igg.com/download/downCnt.php?did=27)
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-07-18T20:56:52+00:00
- Post Title: IGG Online games

> Reply from lllccc
>
> Gods War Online http://gw.igg.com/download/downCnt.php?did=10 (.jcs/.gwo all have bzip in the hex) this might be the images its in the characters folder
The .gwo are TARGA textures. The .jcs are DirectX Meshes. The .gwm files in the PetUniteEffect folder look like simple archives containing TARGA textures and DirectX Meshes.

> Reply from lllccc
>
> Voyage Century http://vc.igg.com/download/download_link.php?did=45(.gm
The .tx files are textures. Each of those files have a 24 byte header identifying the texture dimensions and type of data that follows. The rest of the file, I've seen so far, contain DXT compressed data or raw ARGB (not necessarily in that order) data. I might make a profiler to discover what all the data types are at another time. Music is in the voyage\resource\sound folder, and they're standard Ogg Vorbis files. .gm files are meshes in their own format, I think.

> Reply from lllccc
>
> Angels Online http://ao.igg.com/download/download_link.php?id=121 (the data1.pak or music.pak)
You can use [this tool](http://forum.xentax.com/blog/?p=1183) to convert the files to .zip and then unpack it using an archiver. Music is in music.pak and update4..10.pak. Sprites are in the "shape" folder. You'll have to figure out how to convert them on your own, though.

BTW, someone else made a .pak extractor called PakRipper, but it doesn't seem to apply the extended information from the .zip headers to the extracted files.
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-18T21:01:04+00:00
- Post Title: IGG Online games

do you know what file contains the images? i will keep looking on my end to see if i see and image format in hxd
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-07-18T21:13:15+00:00
- Post Title: IGG Online games

For GodsWar Online, each .gwo are standard .tga files. Load them up in any image viewer. Rename if you have to. (You can see the "TRUEVISION-XFILE" signature at the end of those files.)
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-18T21:16:48+00:00
- Post Title: IGG Online games

thank you ^_^ i will try that right now

to view gods war models move the files (example Christmas_elder_001_all.gwo & Christmas_elder_001_all.jcs) in the foilder of the tools

rename .gwo to .tga and .jsc to .x drag the .x to DXViewer and it will load the files
 to open the tga files you can use Photoshop or tga viewer
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-08-29T13:21:25+00:00
- Post Title: IGG Online games

damn GMMan thank you for the hardwork
