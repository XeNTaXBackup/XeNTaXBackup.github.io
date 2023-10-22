## Post #1
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-09T13:29:24+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

AKIBA'S TRIP 2 (アキバズトリップ・ツー)
[http://www.acquire.co.jp/open/akbstrip/](http://www.acquire.co.jp/open/akbstrip/)
Here is a quickbms to extract the volume.dat archive.
This game uses the common .phyre format.


[Akibas Trip 2.7z](https://xentaxbackup.github.io/file/6760_Akibas Trip 2.7z)
## Post #2
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-11-18T10:49:42+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

Thank you !
## Post #3
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2015-01-02T02:09:31+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

Here is the noesis script to view the model pepd files

Replace this line in the script to point to wherever you have the textures
'E:\\AkibasTrip2\\lang_common\\phyre_texture\\'
[akiba_strip2_noesis_scripts.rar](https://xentaxbackup.github.io/file/8412_akiba_strip2_noesis_scripts.rar)
## Post #4
- Username: foxdemon90210
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 22, 2011 6:12 am
- Post datetime: 2015-06-28T02:26:00+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

> Reply from prototypesky
>
> Here is the noesis script to view the model pepd files

Replace this line in the script to point to wherever you have the textures
'E:\\AkibasTrip2\\lang_common\\phyre_texture\\'

i did what you said but the script only opens head items, i cant open heads and body parts or clothing, what am i doing wrong?
## Post #5
- Username: Kinami30
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 27, 2015 11:56 am
- Post datetime: 2016-11-14T16:02:22+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

> Reply from prototypesky
>
> Here is the noesis script to view the model pepd files

Replace this line in the script to point to wherever you have the textures
'E:\\AkibasTrip2\\lang_common\\phyre_texture\\'

When i try to use the script in Noesis, it give me this message in a Debug Log
"version: -447938560
version not supported: -447938560"

¿Why this happen?
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-01-14T05:40:20+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

I receive the following error when I try to open any PPED file, I'm using the most recent version of Noesis, which I wonder if that could be the issue here.
Given that the scripts were posted back in Jan 2015 and now its Jan 2017 the way plugins work in Noesis may have changed.
Is it possible anyone has a version of noesis from back then I could test with at all?

```
version: 22329
X Data:  (15, 38, 21, 137, 39, 0, 0, 0, 13, 100, 2320, 1, 14, 0, 240, 128, 0, 128, 16909060, 22329, 15, 136, 411, 7477, 0, 0, 150, 158, 84, 142, 6, 57, 105, 21, 170, 42, 28, 165, 68, 0, 123)
Offset A:  14956
Offset E:  22433
Unknown Data:  22973
22973 (1, 4, 464, 160, 304, 0, 4, 8, 0)
23437 (2, 2, 96, 24, 72, 0, 2, 2, 0)
Material Data: ['akbn_map.cgfx#059E311DFE7BAEDF1660DBE144114700', '', 'maptx_3poly_cl_001.dds', '']
23533 (8, 5, 400, 400, 0, 0, 0, 5, 0)
23933 (13, 1, 16, 16, 0, 0, 0, 2, 0)
23949 (26, 1, 64, 64, 0, 0, 0, 2, 0)
24013 (34, 1, 48, 44, 4, 0, 0, 5, 0)
24061 (43, 1, 32, 32, 0, 0, 0, 2, 0)
24093 (44, 1, 36, 36, 0, 0, 0, 0, 0)
24129 (45, 1, 108, 104, 4, 0, 0, 1, 0)
24237 (53, 2, 200, 192, 8, 0, 1, 3, 0)
24437 (55, 1, 244, 244, 0, 0, 0, 4, 0)
24681 (58, 1, 48, 48, 0, 0, 0, 0, 0)
24729 (70, 14, 444, 224, 220, 0, 14, 0, 0)
25173 (132, 5, 72, 60, 12, 0, 0, 5, 0)
25245 (133, 1, 48, 48, 0, 0, 0, 0, 0)
What is this:  25293
Vert Start Loc: 25952
Traceback (most recent call last):
  File "C:\Users\Dan\Downloads\Rippers\noesisv40843\plugins\python\fmt_pepd.py", line 995, in noepyLoadModel
    parsePhyre(data)
  File "C:\Users\Dan\Downloads\Rippers\noesisv40843\plugins\python\fmt_pepd.py", line 959, in parsePhyre
    elif version in [22329]:version22329(g)
  File "C:\Users\Dan\Downloads\Rippers\noesisv40843\plugins\python\fmt_pepd.py", line 236, in version22329
    material = NoeMaterial('material',texList[0].name)
IndexError: list index out of range

```
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-19T01:23:52+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

you'll need to upload some not-working samples, and specify the platform the samples came from,
looks like the Noesis python script is set to read PS3 big-endian files.
## Post #8
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-19T05:31:28+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

> Reply from AceWell
>
> you'll need to upload some not-working samples, and specify the platform the samples came from,
looks like the Noesis python script is set to read PS3 big-endian files.

You can find an attached sample to Jarten's post in this thread 
[viewtopic.php?f=16&t=12907&p=126353#p126353](http://forum.xentax.com/viewtopic.php?f=16&t=12907&p=126353#p126353)
## Post #9
- Username: MrZasen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 28, 2015 3:48 pm
- Post datetime: 2017-11-28T14:15:02+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

So, are there any news on this? I can provide anyone who could research on the 3d models with any pepd file, I'm really interested in the maps, the textures aren't a problem, since they can be easily extracted with a noesis script made for Final Fantasy X [viewtopic.php?f=18&t=16593](http://forum.xentax.com/viewtopic.php?f=18&t=16593)
[guitar.rar](https://xentaxbackup.github.io/file/13606_guitar.rar)
## Post #10
- Username: MrZasen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 28, 2015 3:48 pm
- Post datetime: 2017-12-19T14:51:55+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

I'm sorry for double posting, but I want to say exactly what is needed for extracting the models of this game.
-First of all, you will need the game with BLJM61105 ID, for PS3 ONLY.
-Once downloaded, locate the "Volume.dat" file, you can unpack it with the tool attached to this post or the bms script made.
-Get Noesis Version 412, (released in 2014).
-Download the Python script from this thread, you will have to open it with notepad and replace the textures path specified in 2 different locations, which is where the "phyre_texture" is in your computer.

Now drag the volume file to the .exe attached here, it will unpack everything contained. Locate the .pepd files, they are separated in different folders, "objects" folder, "accessories" folder, "maps", etc.
Open Noesis and find any model you might need.

I've had some issues with the script, when trying to import a map .pepd file, the log says:

```
X Data:  (24, 86, 58, 711, 335, 10, 10, 27, 24, 126, 15120, 9, 135, 0, 6712640, 128, 0, 128, 16909060, 22329, 15, 136, 411, 7477, 0, 0, 150, 158, 84, 142, 6, 57, 105, 21, 170, 42, 28, 68, 165, 0, 123)
Offset A:  14956
Offset E:  22433
Unknown Data:  23297
23297 (1, 12, 1380, 480, 900, 0, 12, 24, 0)
24677 (2, 12, 564, 144, 420, 0, 12, 12, 0)
Material Data: ['akbn_map.cgfx#B7930F5C2F450949B42DBC5EAD6A4ECD', '', 'maptx_aji_01_buil_cl_001_ps3.dds', '', 'maptx_aji_01_buil_cl_002_ps3.dds', '', 'maptx_aji_01_buil_cl_003_ps3.dds', '', 'maptx_aji_01_buil_cl_004_ps3.dds', '', 'maptx_aji_01_buil_cl_005_ps3.dds', '', 'maptx_aji_01_buil_cl_006_ps3.dds', '', 'maptx_aji_01_jimen_cl_001_ps3.dds', 'maptx_aji_01_li_001_ps3.dds', 'maptx_sister_01_buil_cl_002_ps3.dds', 'maptx_sister_01_buil_cl_003_ps3.dds', 'maptx_sister_01_li_001_ps3.dds', '', '', '']
25241 (8, 81, 6480, 6480, 0, 0, 0, 81, 0)
31721 (13, 9, 144, 144, 0, 0, 0, 18, 0)
31865 (26, 1, 64, 64, 0, 9, 0, 10, 1)
31929 (34, 1, 56, 44, 12, 0, 0, 5, 0)
31985 (43, 1, 32, 32, 0, 0, 0, 2, 0)
32017 (44, 9, 324, 324, 0, 18, 0, 18, 9)
32341 (45, 18, 224, 216, 8, 0, 18, 18, 0)
32565 (46, 9, 940, 936, 4, 0, 0, 9, 0)
33505 (54, 2, 204, 192, 12, 0, 1, 3, 0)
33709 (56, 1, 260, 260, 0, 0, 0, 6, 0)
33969 (56, 1, 260, 260, 0, 0, 0, 6, 0)
34229 (56, 1, 260, 260, 0, 0, 0, 6, 0)
34489 (56, 1, 260, 260, 0, 0, 0, 6, 0)
34749 (56, 1, 260, 260, 0, 0, 0, 6, 0)
35009 (56, 1, 260, 260, 0, 0, 0, 6, 0)
35269 (56, 1, 260, 260, 0, 0, 0, 6, 0)
35529 (56, 1, 260, 260, 0, 0, 0, 6, 0)
35789 (56, 1, 260, 260, 0, 0, 0, 6, 0)
36049 (59, 18, 864, 864, 0, 0, 0, 0, 0)
36913 (71, 15, 476, 240, 236, 0, 15, 0, 0)
37389 (132, 81, 980, 972, 8, 0, 0, 81, 0)
38369 (133, 1, 48, 48, 0, 0, 0, 0, 0)
exists: C:\Users\Dani\Desktop\AKIBAS TRIP BJLM\AkibaStrip2.PS3.360megafull.com\volume\lang_common\phyre_texture\maptx_sister_01_buil_cl_002_ps3.dds.GCM.phyre
version: 3541
maptx_sister_01_buil_cl_002_ps3.dds
tell: 3990 DXT1 699064
DXT1 format
exists: C:\Users\Dani\Desktop\AKIBAS TRIP BJLM\AkibaStrip2.PS3.360megafull.com\volume\lang_common\phyre_texture\maptx_sister_01_buil_cl_003_ps3.dds.GCM.phyre
version: 3541
maptx_sister_01_buil_cl_003_ps3.dds
tell: 3990 DXT1 699064
DXT1 format
exists: C:\Users\Dani\Desktop\AKIBAS TRIP BJLM\AkibaStrip2.PS3.360megafull.com\volume\lang_common\phyre_texture\maptx_sister_01_li_001_ps3.dds.GCM.phyre
version: 3541
maptx_sister_01_li_001_ps3.dds
tell: 3986 DXT1 699064
DXT1 format
What is this:  38417
Vert Start Loc: 41834
Traceback (most recent call last):
  File "C:\Users\Dani\Desktop\noesisv412\plugins\python\fmt_pepd.py", line 995, in noepyLoadModel
    parsePhyre(data)
  File "C:\Users\Dani\Desktop\noesisv412\plugins\python\fmt_pepd.py", line 959, in parsePhyre
    elif version in [22329]:version22329(g)
  File "C:\Users\Dani\Desktop\noesisv412\plugins\python\fmt_pepd.py", line 203, in version22329
    g.seek(indiceOff+indiceInfo[i][15])
  File "C:\Users\Dani\Desktop\noesisv412\plugins\python\inc_noesis.py", line 164, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "C:\Users\Dani\Desktop\noesisv412\plugins\python\inc_noesis.py", line 160, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "C:\Users\Dani\Desktop\noesisv412\plugins\python\inc_noesis.py", line 77, in setOffset
    noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size. (1137878123 > 6754544)

```

Along with an error message:

I have found in this forum a post saying that this error is caused when the script isn't updated, but I don't have any idea about scripting, if anyone could help me with this...
[volume.rar](https://xentaxbackup.github.io/file/13710_volume.rar)
## Post #11
- Username: nintendogamer12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 10, 2018 6:11 am
- Post datetime: 2018-01-25T16:20:11+00:00
- Post Title: Akibas Trip 2 (PS3) BLJM61105

Sorry to revive a dead-ish thread but would noesis work for extracting the maps?
im after the maps and not the character models
 ive got as far as the noesis script but it does this
[Untitled.jpg](https://xentaxbackup.github.io/file/13846_Untitled.jpg)
