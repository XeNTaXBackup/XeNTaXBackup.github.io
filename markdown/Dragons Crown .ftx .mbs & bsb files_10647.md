## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-08-01T11:47:27+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

Hi Guys

I've extracted from the game Dragons Crown, the .CPK file, inside of this archive was a lot of different folders for characters, environments etc, however 3 specific formats popped up commonly:

.bsb
.ftx
.mbs
.mcb


I know that .ftx files are textures, and I've tried to use this Noesis script from however there's an error and the files don't successfully open, nor are they exportable.

I'm not sure what the other files contain however, but its all in the graphics/stages folder, so it should be graphics I imagine.

I've uploaded the files to dropbox here: [https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q](https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q)

The Noesis script is here:

```
def registerNoesisTypes():
   handle = noesis.register("FTX Texture Bundle", ".ftx")
   noesis.setHandlerTypeCheck(handle, ftxCheckType)
   noesis.setHandlerLoadModel(handle, ftxLoad)
   return 1

class FtxFile:
   def __init__(self, bs):
      self.bs = bs
   def loadImageInfo(self):
      if self.bs.dataSize < 32:
         return 0
      self.texInfos = []
      hdrInfo = noeUnpack("<iiii", self.bs.readBytes(32)[:16])
      if hdrInfo[0] != 0x58455446 or hdrInfo[3] <= 0 or 32+hdrInfo[3]*48+32+4 >= self.bs.dataSize:
         return 0
      for i in range(0, hdrInfo[3]):
         self.texInfos.append( (noeStrFromBytes(self.bs.readBytes(32)), self.bs.readBytes(16)) )
      self.bs.seek(32, NOESEEK_REL)
      return 1
   def loadImages(self, texList = []):
      for texInfo in self.texInfos:
         texHdr = noeUnpack("<iii", self.bs.readBytes(12))
         self.bs.seek(texHdr[2]-12, NOESEEK_REL)
         tex = rapi.loadTexByHandler(self.bs.readBytes(texHdr[1]), ".gim")
         tex.name = texInfo[0]
         texList.append(tex)
      return texList

def ftxCheckType(data):
   ftx = FtxFile(NoeBitStream(data))
   if ftx.loadImageInfo() == 0:
      return 0
   return 1
def ftxLoad(data, mdlList):
   ftx = FtxFile(NoeBitStream(data))
   if ftx.loadImageInfo() == 0:
      return 0
   mdlList.append(NoeModel([], [], [], NoeModelMaterials(ftx.loadImages(), [])))
   return 1

```


I hope someone is able to work out what I'm missing here.

Thankyou
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-01T21:19:25+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

I found this: [](http://www.pic-upload.de/view-20262144/bg00a_00_arranged_000.jpg.html)

Just adding a header to the first dds (0x240..0x4023F) in bg00a_00.ftx:

```

0000   44 44 53 20 7C 00 00 00  07 10 0A 00 00 02 00 00   DDS |...........
0010   00 02 00 00 00 00 08 00  00 00 00 00 0B 00 00 00   ................
0020   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
0030   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
0040   00 00 00 00 00 00 00 00  00 00 00 00 20 00 00 00   ............ ...
0050   04 00 00 00 44 58 54 35  00 00 00 00 00 00 00 00   ....DXT5........
0060   00 00 00 00 00 00 00 00  00 00 00 00 08 10 40 00   ..............@.
0070   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
```

Did not recalculate pitch or other values in the header so DirectX Texture Tools fails.
Could open the dds using DXTBmp.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-08-02T00:50:41+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from shakotay2
>
> 
Just adding a header to the first dds (0x240..0x4023F) in bg00a_00.ftx:
Code: Select allOffset  0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

0000   44 44 53 20 7C 00 00 00  07 10 0A 00 00 02 00 00   DDS |...........
0010   00 02 00 00 00 00 08 00  00 00 00 00 0B 00 00 00   ................
0020   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
0030   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
0040   00 00 00 00 00 00 00 00  00 00 00 00 20 00 00 00   ............ ...
0050   04 00 00 00 44 58 54 35  00 00 00 00 00 00 00 00   ....DXT5........
0060   00 00 00 00 00 00 00 00  00 00 00 00 08 10 40 00   ..............@.
0070   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
Did not recalculate pitch or other values in the header so DirectX Texture Tools fails.
Could open the dds using DXTBmp.

Oh, now that was a lot simpler than I had anticipated, though with going on 1000+ ftx files at least, I wonder if theres perhaps a faster way than changing the header in each file. I'm still quite new to all this, sorry. But happy to learn.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-02T09:36:26+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

I have the format figured out for the texture files.
all the texture files are tiled and useless without their related other files that store the coordinates and frames.
all the textures are dxt 3 or 5.
I have the coordinate system mapped out i just need to assemble it when i get time.
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-08-02T14:42:23+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from chrrox
>
> I have the format figured out for the texture files.
all the texture files are tiled and useless without their related other files that store the coordinates and frames.
all the textures are dxt 3 or 5.
I have the coordinate system mapped out i just need to assemble it when i get time.

I see, are the files not similar to that of Muramasa, Grand Knights history and other Vanillaware titles?
I know for all the others its a texture sheet of sorts, but made up of tiles and they're arranged in game automatically but anyone outside of the game would have to manually match up the files, sometimes 1 scene can be on 12 or more texture sheets if I remember correctly.

Thanks for the update chroxx, look forward to your results.
## Post #6
- Username: lionheartuk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-04T13:05:25+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

Windows update made me loose all my notes and i don't care much for this game so here this lets you load the raw textures.
[tex_DragonsCrown_ftx.7z](https://xentaxbackup.github.io/file/6544_tex_DragonsCrown_ftx.7z)
## Post #7
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-08-06T11:22:08+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from chrrox
>
> Windows update made me loose all my notes and i don't care much for this game so here this lets you load the raw textures.

So this only extracts the textures as untiled, with no coordinates, etc?
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-08-06T22:48:34+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from neurotech
>
> chrrox wrote:Windows update made me loose all my notes and i don't care much for this game so here this lets you load the raw textures.

So this only extracts the textures as untiled, with no coordinates, etc?

It lets you view them as texture sheets in Noesis, export them from there.

The 'cordinates' in Vanillaware games are erm... well there sort of arnt any, each individual texture from the sheet is placed on a polygon and then that polygon is moved around the screen via code, if that makes sense.
## Post #9
- Username: neurotech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 22, 2013 9:40 pm
- Post datetime: 2013-08-06T22:58:51+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from lionheartuk
>
> neurotech wrote:chrrox wrote:Windows update made me loose all my notes and i don't care much for this game so here this lets you load the raw textures.

So this only extracts the textures as untiled, with no coordinates, etc?

It lets you view them as texture sheets in Noesis, export them from there.

The 'cordinates' in Vanillaware games are erm... well there sort of arnt any, each individual texture from the sheet is placed on a polygon and then that polygon is moved around the screen via code, if that makes sense.

Yep since my previous post I've been exporting a bunch of FTX files from Noesis using chrrox's script and I can see exactly what you mean.
## Post #10
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2013-09-20T11:12:42+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from lionheartuk
>
> Hi Guys

I've extracted from the game Dragons Crown, the .CPK file, inside of this archive was a lot of different folders for characters, environments etc, however 3 specific formats popped up commonly:

.bsb
.ftx
.mbs
.mcb


I know that .ftx files are textures, and I've tried to use this Noesis script from however there's an error and the files don't successfully open, nor are they exportable.

I'm not sure what the other files contain however, but its all in the graphics/stages folder, so it should be graphics I imagine.

I've uploaded the files to dropbox here: https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q

The Noesis script is here:
Code: Select allfrom inc_noesis import *
def registerNoesisTypes():
   handle = noesis.register("FTX Texture Bundle", ".ftx")
   noesis.setHandlerTypeCheck(handle, ftxCheckType)
   noesis.setHandlerLoadModel(handle, ftxLoad)
   return 1

class FtxFile:
   def __init__(self, bs):
      self.bs = bs
   def loadImageInfo(self):
      if self.bs.dataSize < 32:
         return 0
      self.texInfos = []
      hdrInfo = noeUnpack("<iiii", self.bs.readBytes(32)[:16])
      if hdrInfo[0] != 0x58455446 or hdrInfo[3] <= 0 or 32+hdrInfo[3]*48+32+4 >= self.bs.dataSize:
         return 0
      for i in range(0, hdrInfo[3]):
         self.texInfos.append( (noeStrFromBytes(self.bs.readBytes(32)), self.bs.readBytes(16)) )
      self.bs.seek(32, NOESEEK_REL)
      return 1
   def loadImages(self, texList = []):
      for texInfo in self.texInfos:
         texHdr = noeUnpack("<iii", self.bs.readBytes(12))
         self.bs.seek(texHdr[2]-12, NOESEEK_REL)
         tex = rapi.loadTexByHandler(self.bs.readBytes(texHdr[1]), ".gim")
         tex.name = texInfo[0]
         texList.append(tex)
      return texList

def ftxCheckType(data):
   ftx = FtxFile(NoeBitStream(data))
   if ftx.loadImageInfo() == 0:
      return 0
   return 1
def ftxLoad(data, mdlList):
   ftx = FtxFile(NoeBitStream(data))
   if ftx.loadImageInfo() == 0:
      return 0
   mdlList.append(NoeModel([], [], [], NoeModelMaterials(ftx.loadImages(), [])))
   return 1


I hope someone is able to work out what I'm missing here.

Thankyou

your link is to a zip named "music as requested" with some random mp3's. please post a proper link to the ftx's.
## Post #11
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-09-20T18:00:15+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from joeyq
>
> 
your link is to a zip named "music as requested" with some random mp3's. please post a proper link to the ftx's.

Sorry, I deleted the FTX files after obtaining the working Noesis script on how to view them.
If I know why you need the ftx files then I may be able to reupload one or 2 of them for you to checkout.
## Post #12
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2013-09-23T09:30:28+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from lionheartuk
>
> joeyq wrote:
your link is to a zip named "music as requested" with some random mp3's. please post a proper link to the ftx's.

Sorry, I deleted the FTX files after obtaining the working Noesis script on how to view them.
If I know why you need the ftx files then I may be able to reupload one or 2 of them for you to checkout.

Sorry for reacting so late, but i figured it out on my own. I'm such a noob, i just needed to extract the files from "DRACRO.CPK" with the latest noesis. 
Thanx for quick response lionheartuk, and thanx for script chrrox!!
## Post #13
- Username: maoxianfly
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 12:38 am
- Post datetime: 2014-11-07T16:53:07+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from chrrox
>
> Windows update made me loose all my notes and i don't care much for this game so here this lets you load the raw textures.

Can't Extracting  "The Demon Blade" ftx file.
## Post #14
- Username: maoxianfly
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 12:38 am
- Post datetime: 2014-11-07T16:56:00+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from lionheartuk
>
> chrrox wrote:I have the format figured out for the texture files.
all the texture files are tiled and useless without their related other files that store the coordinates and frames.
all the textures are dxt 3 or 5.
I have the coordinate system mapped out i just need to assemble it when i get time.

I see, are the files not similar to that of Muramasa, Grand Knights history and other Vanillaware titles?
I know for all the others its a texture sheet of sorts, but made up of tiles and they're arranged in game automatically but anyone outside of the game would have to manually match up the files, sometimes 1 scene can be on 12 or more texture sheets if I remember correctly.

Thanks for the update chroxx, look forward to your results.

Can't Extracting "The Demon Blade" ftx file.
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-11-08T09:19:19+00:00
- Post Title: Dragons Crown .ftx .mbs & bsb files

> Reply from maoxianfly
>
> lionheartuk wrote:chrrox wrote:I have the format figured out for the texture files.
all the texture files are tiled and useless without their related other files that store the coordinates and frames.
all the textures are dxt 3 or 5.
I have the coordinate system mapped out i just need to assemble it when i get time.

I see, are the files not similar to that of Muramasa, Grand Knights history and other Vanillaware titles?
I know for all the others its a texture sheet of sorts, but made up of tiles and they're arranged in game automatically but anyone outside of the game would have to manually match up the files, sometimes 1 scene can be on 12 or more texture sheets if I remember correctly.

Thanks for the update chroxx, look forward to your results.

Can't Extracting "The Demon Blade" ftx file.

The script was made for Dragons Crown ftx files, the only similar thing between all the vanillaware games is the name of the extension as .ftx, the files themselves are never the same.

If you're really after textures from Muramasa then just play through it in the Dolphin Emulator with texture dumping, or alternatively grab the HD texture pack fromt he Dolphin forums (which I'm not going to link to as its probably against the rules here.
## Post #16
- Username: DavidAshta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 14, 2018 8:25 pm
- Post datetime: 2018-09-14T17:23:20+00:00
- Post Title: Re: Dragons Crown .ftx .mbs & bsb files

this script just work on PS3 game or PSVita game too?
because they have the same files, but i can't open they
## Post #17
- Username: Kojinzx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 8:47 pm
- Post datetime: 2020-06-16T17:19:14+00:00
- Post Title: Re: Dragons Crown .ftx .mbs & bsb files

Hi, is there any chances to create script for noesis that allow import textures into .ftx  back?
i want create some edits then import textures back to ftx?
