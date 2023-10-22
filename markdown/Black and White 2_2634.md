## Post #1
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2007-05-26T20:43:28+00:00
- Post Title: Black and White 2

[http://wiki.planetblackandwhite.gamespy ... Models:BWM](http://wiki.planetblackandwhite.gamespy.com/PBnWModdingWIKI/index.php/Formats:Models:BWM)
[http://wiki.planetblackandwhite.gamespy ... Models:CHA](http://wiki.planetblackandwhite.gamespy.com/PBnWModdingWIKI/index.php/Formats:Models:CHA)
[http://wiki.planetblackandwhite.gamespy ... Models:CSK](http://wiki.planetblackandwhite.gamespy.com/PBnWModdingWIKI/index.php/Formats:Models:CSK)
[http://wiki.planetblackandwhite.gamespy ... Models:CSS](http://wiki.planetblackandwhite.gamespy.com/PBnWModdingWIKI/index.php/Formats:Models:CSS)
[http://wiki.planetblackandwhite.gamespy ... dels:%2ABN](http://wiki.planetblackandwhite.gamespy.com/PBnWModdingWIKI/index.php/Formats:Models:%2ABN)

The first one is non-Creature models. Houses, villagers, etc etc.

The last one seems to be an archive of some sort that is storing at least animations.
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2011-03-24T17:21:33+00:00
- Post Title: Black and White 2

There are creature models (there might be higher/lower detailed ones in other files) in CCS (not css) files. Here is a picture of the lion and the lion's model. Bones and animations are in other files because there were none in in the blion.ccs  The format looks very simple, I will look into this more after my test tomorrow.


[http://ps23dformat.wikispaces.com/file/view/lion.3ds](http://ps23dformat.wikispaces.com/file/view/lion.3ds)
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-01-31T23:30:52+00:00
- Post Title: Black and White 2

Here is a script to convert the creature CCS files, into .3ds files. First you must use the program called "gameextractor" [http://www.watto.org/extract/](http://www.watto.org/extract/)   to extract the ccs files from the everything.data file.
Then use the following quickbms script [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
[http://ps23dformat.wikispaces.com/file/ ... sTo3ds.bms](http://ps23dformat.wikispaces.com/file/view/BW2ccsTo3ds.bms)

```
GoTo 0x88 0 ;
Get vertexnumber Long 0 ;
SavePos vertexstart 0 ;
Math bw = vertexnumber ;
Math bw *= 0x1c ;
GoTo bw 0 SEEK_CUR ;
SavePos white 0 ;
Get facenumber Long 0 ;
Math bw = facenumber ;
Math bw *= 0x4 ;
GoTo bw 0 SEEK_CUR ;
SavePos facestart 0 ;
Math lion = vertexnumber ;
Math lion *= 0x14 ;
Math liger = facenumber ;
Math liger *= 0xa ;
Math total3ds = lion ;
Math total3ds += liger ;
Math total3ds += 0x89 ;
Math total1 = total3ds ;
Math total1 -= 0x10 ;
Math total2 = total3ds ;
Math total2 -= 0x54 ;
Math total3 = total3ds ;
Math total3 -= 0x5E ;
Math vertexbase = 0x6c ;
Math WHEREvertex = vertexbase ;
Math tigervertex = vertexnumber ;
Math tigervertex *= 0xc ;
Math facebase1 = vertexbase ;
Math facebase1 += tigervertex ;
Math tigerface = facenumber ;
Math tigerface *= 0x8 ;
Math tigertigerface = facenumber ;
Math tigertigerface *= 0xa ;
Math facebase2 = facebase1 ;
Math facebase2 += 0x8 ;
Math WHEREface = facebase2 ;
Math facebase3 = facebase2 ;
Math facebase3 += tigerface ;
Math tigertigertigerface = facenumber ;
Math tigertigertigerface *= 0x2 ;
Math weretiger = tigertigerface ;
Math weretiger += 0x15 ;
Math tiger1 = tigervertex ;
Math tiger1 += 0x8 ;
Math tiger4 = tigertigertigerface ;
Math tiger4 += 0xd ;
Math WHEREfacecount = facebase3 ;
Math WHEREfacecount += 0xd ;
Math uvbase = WHEREfacecount ;
Math uvbase += tigertigertigerface ;
Math tigon = tigerface ;
Math tigon += 0x8 ;
Math WHEREuv = uvbase ;
Math WHEREuv += 0x8 ;
Math WHEREvertexq = WHEREvertex ;
Math WHEREuvq = WHEREuv ;
Math WHEREfaceq = WHEREface ;
Math WHEREfacecountq = WHEREfacecount ;
set M Byte 0x4d ;
Put M Byte 1 ;
set M Byte 0x4d ;
Put M Byte 1 ;
set M Byte 0xed ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x02 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x0a ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x03 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x3d ;
Put M Byte 1 ;
set M Byte 0x3d ;
Put M Byte 1 ;
set M Byte 0xdd ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0xaf ;
Put M Byte 1 ;
set M Byte 0x3e ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0b ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x4e ;
Put M Byte 1 ;
set M Byte 0x6f ;
Put M Byte 1 ;
set M Byte 0x6e ;
Put M Byte 1 ;
set M Byte 0x65 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0f ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x09 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0f ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x09 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xcc ;
Put M Byte 1 ;
set M Byte 0xcc ;
Put M Byte 1 ;
set M Byte 0xcc ;
Put M Byte 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0xa0 ;
Put M Byte 1 ;
set M Byte 0x0f ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x11 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x09 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0xff ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x99 ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x64 ;
Put M Byte 1 ;
set M Byte 0x69 ;
Put M Byte 1 ;
set M Byte 0x6x ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
set M Byte 0x8f ;
Put M Byte 1 ;
set M Byte 0x22 ;
Put M Byte 1 ;
set M Byte 0x01 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x10 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
set M Byte 0x64 ;
Put M Byte 1 ;
set M Byte 0x67 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x00 ;
Put M Byte 1 ;
set M Byte 0x9d ;
Put M Byte 1 ;
set M Byte 0x08 ;
Put M Byte 1 ;
GoTo 0x2 1 ;
Put total3ds Long 1 ;
GoTo 0x12 1 ;
Put total1 Long 1 ;
GoTo 0x56 1 ;
Put total2 Long 1 ;
GoTo 0x60 1 ;
Put total3 Long 1 ;
GoTo 0x66 1 ;
Put tiger1 Long 1 ;
GoTo 0x6A 1 ;
Put vertexnumber Short 1 ;
GoTo facebase1 1 ;
set M Byte 0x20 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Put weretiger Long 1 ;
Put facenumber Short 1 ;
GoTo facebase3 1 ;
set M Byte 0x30 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Put tiger4 Long 1 ;
set M Byte 0x4e ;
Put M Byte 1 ;
set M Byte 0x6f ;
Put M Byte 1 ;
set M Byte 0x6e ;
Put M Byte 1 ;
set M Byte 0x65 ;
Put M Byte 1 ;
set M Byte 0x0 ;
Put M Byte 1 ;
Put facenumber Short 1 ;
GoTo uvbase 1 ;
set M Byte 0x40 ;
Put M Byte 1 ;
set M Byte 0x41 ;
Put M Byte 1 ;
Put tigon Long 1 ;
Put vertexnumber Short 1 ;
For vwolf = 0 < vertexnumber ;
GoTo vertexstart 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
SavePos vertexstart 0 ;
GoTo WHEREvertexq 1 ;
Put Type1 Long 1 ;
Put Type2 Long 1 ;
Put Type3 Long 1 ;
SavePos WHEREvertexq 1 ;
Next vwolf ;
For fwolf = 0 < facenumber ;
GoTo facestart 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
SavePos facestart 0 ;
GoTo WHEREfaceq 1 ;
Put Type1 short 1 ;
Put Type3 short 1 ;
Put Type2 short 1 ;
Put 0 short 1 ;
SavePos WHEREfaceq 1 ;
Next fwolf ;
For uvwolf = 0 < vertexnumber ;
GoTo WHEREuvq 1 ;
Put 00 Long 1 ;
Put 00 Long 1 ;
SavePos WHEREuvq 1 ;
Next uvwolf ;
For fcwolf = 0 < facenumber ;
GoTo WHEREfacecountq 1 ;
Put fcwolf short 1 ;
SavePos WHEREfacecountq 1 ;
Next fcwolf ;
```


The script must be run using the Microsoft Windows Command Prompt (it will not work by double-clicking quickbms.exe), also you must use the -w option (the w must be lowercase). When the script asks you what other file to open up, simply type in the name (without path), that you want to SAVE the model as making sure to include the .3ds extension. For example you could type in tiger.3ds
For example

```
C:\quickbms\quickbms.exe -w C:\quickbms\BW2ccsTo3ds.bms C:\quickbms\btiger.ccs C:\quickbms
```
## Post #4
- Username: arcs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2012 2:51 am
- Post datetime: 2013-02-04T18:02:44+00:00
- Post Title: Black and White 2

There are actually already tools for extracting creature models...too bad I didn't notice this thread before, though I suppose it is a little on the old side!

You can use the [official BW2 modding tools](http://www.kayssplace.com/files/index.php?display=798) to unpack everything.stuff (note that you'll probably need to edit the included unstuffer.bat with your BW2 installation path, as it uses absolute rather than relative paths, and the default location is C:\Program Files\Lionhead Studios\Black & White 2 whereas for most this will now be C:\Program Files (x86)\Lionhead Studios\Black & White 2).

The unstuffer will dump the CCS/CHA/CSK files into Data\ctr, and the textures into appropriate subdirectories. You can then use [Ego's Misc Mod Tools](http://www.kayssplace.com/files/index.php?display=1380) to convert the CCS/etc files to obj.

It's worth noting that Ego's tools include documentation on findings relating to some of the file formats, and while the links in the OP are down, the pages are available through archive.org if you (or anyone else) wants to explore the formats any further.
