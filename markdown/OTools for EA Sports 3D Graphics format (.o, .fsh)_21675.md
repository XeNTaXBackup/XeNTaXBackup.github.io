## Post #1
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-01-27T15:25:46+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

Hello. I'm currently working on a tool for EA Sports 3D file formats (.o, used mainly in FIFA 2004 - FIFA 10, FIFA Manager, NBA, Cricket and some other games).

.o is a file extension in EA Sports games which is used for model and animation files. The file itself has an ELF structure. The file may contain model data, skeleton information, animations, rendering information and shaders.

OTools is a tool for importing/exporting EA Sports model format (.o)

[](https://i.imgur.com/KIF4gzw.png) [](https://i.imgur.com/i4niNoO.png) [](https://i.imgur.com/ALQGlXz.png)

The tool can be found here:
[https://bitbucket.org/fifam/otools/](https://bitbucket.org/fifam/otools/)

Some information might be placed on the wiki:
[https://bitbucket.org/fifam/otools/wiki/](https://bitbucket.org/fifam/otools/wiki/)

During the research I found that the general model format was not changed for many years, since 2004 or so (I also checked FIFA WC 2002 and it had some slight differences).
What changed during these years were shaders. Shaders determine how geometry (vertex buffer) is stored and how geometry is rendered (render code). So these 2 things may differ in different games and game versions. At this point I'm only interested in FIFA Manager series (13, 07 and 08), and maybe I will also look at FIFA 07/08.
If there's someone who interested in any other games (like NBA, Cricket or anything else) and could help with finding/testing, let me know.
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-30T11:45:57+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

Awesome!
Do you Happen to know if it also works with ssx 3 .ssh textures?
Its from ea, too and we are Stuck with its model Format:-/
[viewtopic.php?f=16&t=21408](https://forum.xentax.com/viewtopic.php?f=16&t=21408)
Could you please have a look?
## Post #3
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-01-30T16:49:13+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from Henchman800 ↑Thu Jan 30, 2020 7:45 pm at Thu Jan 30, 2020 7:45 pm
>
> 
Can you upload it here?
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-31T10:15:59+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Fri Jan 31, 2020 12:49 am at Fri Jan 31, 2020 12:49 am
>
> 
Can you upload it here?

Heres the playstation and gamecube models:
[https://cdn.discordapp.com/attachments/ ... models.zip](https://cdn.discordapp.com/attachments/628005960471805972/660483580421472296/nate_models.zip)

And here you have an xbox model:


 Mac_Small_models.zip
.mxf files (7.49 KiB) Downloaded 23 times



.mnf = gamecube
.mxf = xbox
.mpf = playstation
## Post #5
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-02-01T13:45:44+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

Henchman800, I don't see any similarity between these files and .o format.
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-01T18:50:35+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Sat Feb 01, 2020 9:45 pm at Sat Feb 01, 2020 9:45 pm
>
> 
Henchman800, I don't see any similarity between these files and .o format.

That sucks.... :-/
Thank you for trying, though!
At least we now know, that these filetypes by EA don't share much, other than their origin company
## Post #7
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-02-03T14:30:03+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

I recently released 0.140 and it supports the import of skinned meshes.

Here's the general process of skinning and importing skinned mesh to the game:
1. Import your model to the scene
2. Import original model with skeleton (.gltf)
3. Delete mesh of original model but leave skeleton
4. Move your model under skeleton (armature) and setup vertex weights
5. Apply all transformations
6. Export to one of supported formats (.glb/.gltf is recommended) and convert it to .o with otools.

Also with the tool it's possible to create a completely new skeleton, but I don't know how it can be used (because you will also need to understand animations system to change anything in this direction).

So now only these things are missed in the converter, and I'm not sure if I'll work on it:
-morphing
As I know, morphing was used only for "game-face" feature. I don't see how we can use it. Maybe it was used for other things in some other games.
-embedded textures in .o
As I know, embedded textures were never used in original files. Might be implemented later
-animations
I know that most of animations are stored in another file format. Only some animations were stored in .o. Need to compare with other games.
-effects & shaders
Effects and shaders are stored in eaglrm.o and some other variations of this file.
This is not the thing which you can import to 3d software, so probably will require a new tool. Also I don't think there's someone who will spend his time on researching assembly shaders.

I also started a research on past-gen FIFA format, RX3.
## Post #8
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-02-07T18:57:06+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

Finally some fifa fan. God blessed you brother! Are you planing to explore fifa online 4. Those rx3 are a bit different and interesting. We can be in contact. I'm very exciting
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-07T21:16:19+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

I am really happy to see progress about these old formats as well, and was wondering if maybe some support for the old NFS series games can be added too for their characters, I am trying to see if they can be exported, then re-worked in higher detail maybe and ported back in same format.
For example the following samples have inside BUN (bundles) all required textures, geometry and those O files that seem to have animation/skeletal info.
And who knows maybe can be supported from it?
[https://mega.nz/#F!b4dE1Aya!yckPmygjB66H8SkrOdyELA](https://mega.nz/#F!b4dE1Aya!yckPmygjB66H8SkrOdyELA)
If samples give trouble, I included the GAUP.wcx to unpack the bundles using quickbms.
more info about it here: [https://lhm.fandom.com/ru/wiki/Game_Archive_UnPacker](https://lhm.fandom.com/ru/wiki/Game_Archive_UnPacker)
## Post #10
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-02-08T18:46:18+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from greenlemonade1 ↑Sat Feb 08, 2020 2:57 am at Sat Feb 08, 2020 2:57 am
>
> 
Finally some fifa fan. God blessed you brother! Are you planing to explore fifa online 4. Those rx3 are a bit different and interesting. We can be in contact. I'm very exciting
I could check if you upload rx3 files.

> Reply from mono24 ↑Sat Feb 08, 2020 5:16 am at Sat Feb 08, 2020 5:16 am
>
> 
I am really happy to see progress about these old formats as well, and was wondering if maybe some support for the old NFS series games can be added too for their characters, I am trying to see if they can be exported, then re-worked in higher detail maybe and ported back in same format.
For example the following samples have inside BUN (bundles) all required textures, geometry and those O files that seem to have animation/skeletal info.
And who knows maybe can be supported from it?
https://mega.nz/#F!b4dE1Aya!yckPmygjB66H8SkrOdyELA
If samples give trouble, I included the GAUP.wcx to unpack the bundles using quickbms.
more info about it here: https://lhm.fandom.com/ru/wiki/Game_Archive_UnPacker
Those BUN files are also file archives? Can it be extracted?

PS I will create a separate thread for RX3 files here, later. I already made an exporter from .rx3 to .gltf, I hope with the help from the community we could do even more.
## Post #11
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-08T23:44:30+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Sun Feb 09, 2020 2:46 am at Sun Feb 09, 2020 2:46 am
>
> Those BUN files are also file archives? Can it be extracted?
Yes, as I've stated, their bundles/archives, and the included plugin for quickbms can extract them, and I wanted to see if you can take a look since its by EA and the format might be same.
## Post #12
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-02-09T15:38:54+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

Here are the two samples of fifa16 and fo4. Bigchillghost helped a lot, and maybe this thread can help:  [viewtopic.php?f=16&t=21320](https://forum.xentax.com/viewtopic.php?f=16&t=21320)

Samples: [https://www.mediafire.com/file/h7w2sfqc ... s.rar/file](https://www.mediafire.com/file/h7w2sfqc5he88ko/3d_models.rar/file)
It will be awesome if we can convert fifa16 or fifa online 4 to fifa14, without leaving some faces,offsets or bones. Every converted fifa16 face have mouth bug
## Post #13
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-02-09T23:48:25+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

mono24, it will be easier for me if you upload already extracted files.
greenlemonade1, ok, I will look. If I'll have something to say, I'll post in that thread you linked to.
## Post #14
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-10T03:00:07+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Mon Feb 10, 2020 7:48 am at Mon Feb 10, 2020 7:48 am
>
> mono24, it will be easier for me if you upload already extracted files.
Alright, initial mega link above updated with extracted bundles, in their respective folders.
## Post #15
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-02-10T15:35:53+00:00
- Post Title: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from mono24 ↑Mon Feb 10, 2020 11:00 am at Mon Feb 10, 2020 11:00 am
>
> 
DmitryFM wrote: ↑Mon Feb 10, 2020 7:48 ammono24, it will be easier for me if you upload already extracted files.
Alright, initial mega link above updated with extracted bundles, in their respective folders.
.O files in these bundles are used only for animations and skeleton. As I understand, meshes are stored in .geo.bin files and textures - probably in tpk.bin files.

So talking about these .o files, they can be extracted with current otools version.
But, as animation banks are not supported by the tool (it doesn't understand animations), the only purpose of extracting is that you can see skeleton:


```
Scene_DriftKingHub_BundleB.bun.000014.o - skeleton 2 (partial, only bones?)
Scene_DriftKingHub_BundleB.bun.000015.o - skeleton 3 (complete?)
Scene_DriftKingHub_BundleB.bun.000035.o - animation bank 1
Scene_DriftKingHub_BundleB.bun.000036.o - animation bank 2

```
## Post #16
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-11T05:59:44+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Mon Feb 10, 2020 11:35 pm at Mon Feb 10, 2020 11:35 pm
>
> .O files in these bundles are used only for animations and skeleton. As I understand, meshes are stored in .geo.bin files and textures - probably in tpk.bin files.
Correct. Unfortunately the geometry can not be extracted by any tool to attach the skeletal to it, and TPK are the textures.

> Reply from DmitryFM ↑Mon Feb 10, 2020 11:35 pm at Mon Feb 10, 2020 11:35 pm
>
> So talking about these .o files, they can be extracted with current otools version.
Not sure how you made it work cause I got zero results, but is there a way you could support exporting the meshes/skeletals then maybe to export back to same skeletal file and geometry format?
Or its too complicated? Most importantly samples from MW_2005 folder.
## Post #17
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-03-04T19:10:09+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Version 0.146 was released. It's available on Bitbucket.
[https://bitbucket.org/fifam/otools/downloads/](https://bitbucket.org/fifam/otools/downloads/)

Now GUI version is also available (Qt-based, requires Win7+).


Added experimental support for FIFA07 (for an example I imported [this](https://sketchfab.com/3d-models/vikinghead-9f08fa5311c84f7c879f1d8d10d29a6b) model)
[](https://i.imgur.com/1OxAhcp.png)

I already achieved what I planned and why this tool was created - all FIFA20 Switch head models (more than 2'000) were converted to FIFA Manager, including generic heads and hairs... If you want to see how new faces look in a 12-year old FIFA engine, here you go:
[](https://i.imgur.com/VjZK5qV.png) [](https://i.imgur.com/b1PyxV0.png)

[](https://i.imgur.com/epckFx3.png) [](https://i.imgur.com/CuaWc5j.png)

[](https://i.imgur.com/SbrrWZQ.png) [](https://i.imgur.com/NEuxENJ.png)

[](https://i.imgur.com/1K5q74O.png) [](https://i.imgur.com/CiYSCk0.png)

[](https://i.imgur.com/gXpvGfL.png) [](https://i.imgur.com/vAsRPve.png)

[](https://i.imgur.com/4G9k8Zl.png) [](https://i.imgur.com/EjkHi0C.png)

[](https://i.imgur.com/7xZlvt6.png) [](https://i.imgur.com/eybOmAT.png)

As you can see even skinning was converted. The fact that we can completely and automatically convert character models from one game to another is... embrassing.

@mono24 
The geometry format is not same as it is in .o files, so I can't help here.
## Post #18
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-03-12T21:11:32+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Version 0.149 was released.
[https://bitbucket.org/fifam/otools/downloads/](https://bitbucket.org/fifam/otools/downloads/)

Added support for all FIFA games, UEFA Euro games and WC 2006. Also Cricket 07 (but not fully). Most of new shaders are untested.
Some shaders may require additional setup.

[](https://i.imgur.com/TQpYMp0.png)

I also added a license agreement for tool users. Now you need to read and accept these terms before using the tool:

```

-Files made with OTools can't be sold or used to get any profit from them.
-Files made with OTools must be shared freely - without any paid links or paid file hosts.
-When sharing files made with OTools, they must be available for anyone. Thus, it's not allowed to upload such files in closed communities or groups.

If you are not agree with mentioned terms - simply do not use OTools.
```


-target option was removed, now -game option is used to specify source/target game.
GUI version was improved.

I also checked how .O files are used in other EA games. I found that o files were used in most of EA Vancouver games (1999-2009).
Every game use it in different way.
NBA Live games use base mesh for head and morph targets for each unique player face (Morph data is stored separately for each player).
NHL split .O file to .ord (file data) and .orl (file relocations) files.
Cricket is similar to FIFA (at least, shaders are similar), but uses skeleton in external file (so model files do not contain skeleton like in FIFA).
I checked Def Jam: FFNY files. There's no PC version, so I checked PS2 version. Some parts of the file are same with PC version - Model, Skeleton, but there were no RenderMethod's inside the model. I think it was used some PS2-specific structures. I won't work on console formats version.
I still didn't check NFS games.

NBA export will be available in one of next version. Full support for import might be possible only when morph structure will be fully researched. I already made something in this direction.
But I don't know what's the best way to store it in model files. GLTF allow only positions and normals in morph targets, but it seems NBA also uses texture coordinates. Anyone knows anything about this?
[](https://i.imgur.com/3m6iI6f.png) [](https://i.imgur.com/VmD6axv.png)

FIFA 07 import is already possible, but there are some problems with adding large files into the game filesystem (zdata files)
[](https://i.imgur.com/FaaXB8e.png)
(beard texture is unfinished)
## Post #19
- Username: JovoHolmes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 10, 2020 10:23 pm
- Post datetime: 2020-07-10T14:25:32+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

I have downloaded Otools but I can't see an .exe to run the GUI, how do I run it? If someone could help me? Thanks in advance.
## Post #20
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-07-12T10:53:06+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

There were some problems with hosting on BitBucket.
I re-uploaded binaries for current version (0.159).

[https://bitbucket.org/fifam/otools/downloads/](https://bitbucket.org/fifam/otools/downloads/)
## Post #21
- Username: JovoHolmes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 10, 2020 10:23 pm
- Post datetime: 2020-07-12T17:20:51+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Thank you so much for your reply, but I can't get the GUI to work correctly. When I try to select "Import .O"
and then browse for the file, the possible formats available do not include ".o" file types. I don't know if this is a possible bug or not?
## Post #22
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-07-13T12:11:00+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Select "Export .O"
## Post #23
- Username: GuruSangha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 12, 2020 8:06 pm
- Post datetime: 2020-11-20T01:27:59+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

this tool works with Def Jam ffny or Def Jam Icon i just want to extract some models from game
but i don't know anything about how to get them out of game
## Post #24
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-01-10T22:01:18+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

How can I convert .Ord and . orp files from NFL old games to .o files, to be editable in o files worker or any related tool.
Please tell me the tool or give me links
## Post #25
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2021-02-27T11:09:57+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from GuruSangha ↑Fri Nov 20, 2020 9:27 am at Fri Nov 20, 2020 9:27 am
>
> 
this tool works with Def Jam ffny or Def Jam Icon i just want to extract some models from game
but i don't know anything about how to get them out of game
Currently the tool supports only PC formats.

> Reply from DAlex ↑Mon Jan 11, 2021 6:01 am at Mon Jan 11, 2021 6:01 am
>
> 
How can I convert .Ord and . orp files from NFL old games to .o files, to be editable in o files worker or any related tool.
Please tell me the tool or give me links
Are you sure it's orp? I think it must be ORL (relocations) + ORD (data).
The tool supports export from ORL+ORD. If so, you can try to rename the extension and try.
Anyway, normally you just combine them two into one file (use hex editor or any similar tool to merge files).
## Post #26
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2021-03-28T22:20:07+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

With version 0.172, now the tool can work with:

```
Rugby 06
Rugby 2005
Cricket 07
Cricket 2005
MVP Baseball 2005
MVP Baseball 2004
MVP Baseball 2003
```

[](https://i.imgur.com/rfk4Ukv.png) [](https://i.imgur.com/qaYKd9Y.png) [](https://i.imgur.com/jpFGqvj.png) [](https://i.imgur.com/mHlZade.png)

Having  fun with adding HD models into 2004 game
[](https://i.imgur.com/hzaCdi7.png) [](https://i.imgur.com/csTRADL.png)
## Post #27
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-04-01T06:26:52+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Thanks for the update, but I haven't been able to do the psp models. It uses ord and orp format. I have tried to merge both using hex editor. I tried both methods of merging and it didn't work in the ordtool and other o files editor. I believe it's because it's in ord and orp format. It only works in ord and orl format. Do you mind if I send you the link of the psp models to try to edit or merge?
## Post #28
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-04-01T06:27:47+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Sat Feb 27, 2021 7:09 pm at Sat Feb 27, 2021 7:09 pm
>
> 
GuruSangha wrote: ↑Fri Nov 20, 2020 9:27 am
this tool works with Def Jam ffny or Def Jam Icon i just want to extract some models from game
but i don't know anything about how to get them out of game

Currently the tool supports only PC formats.
DAlex wrote: ↑Mon Jan 11, 2021 6:01 am
How can I convert .Ord and . orp files from NFL old games to .o files, to be editable in o files worker or any related tool.
Please tell me the tool or give me links

Are you sure it's orp? I think it must be ORL (relocations) + ORD (data).
The tool supports export from ORL+ORD. If so, you can try to rename the extension and try.
Anyway, normally you just combine them two into one file (use hex editor or any similar tool to merge files).

Please reply my comments.
Above, about the psp models
## Post #29
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2021-04-12T12:08:47+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

You can upload files if you want (mega/mediafire/dropbox; any other I won't be able to download).
But there might be a difference between PC and PSP file format.
There are big differences between PC and XBOX/PS2 (Def Jam FFNY) files.
## Post #30
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-04-12T12:31:31+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Mon Apr 12, 2021 8:08 pm at Mon Apr 12, 2021 8:08 pm
>
> 
You can upload files if you want (mega/mediafire/dropbox; any other I won't be able to download).
But there might be a difference between PC and PSP file format.
There are big differences between PC and XBOX/PS2 (Def Jam FFNY) files.

Okay, thanks.
I'm about to upload
## Post #31
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-04-12T13:00:19+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Mon Apr 12, 2021 8:08 pm at Mon Apr 12, 2021 8:08 pm
>
> 
You can upload files if you want (mega/mediafire/dropbox; any other I won't be able to download).
But there might be a difference between PC and PSP file format.
There are big differences between PC and XBOX/PS2 (Def Jam FFNY) files.

Here is the big file containing Messi models(ord and orp) in FIFA 08 PSP. 
You can extract it with Quickbms or any good big editor. Thanks 
[https://www.mediafire.com/download/jqbvhud3bo6u1q5](https://www.mediafire.com/download/jqbvhud3bo6u1q5)
## Post #32
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2021-04-29T06:40:15+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DAlex ↑Mon Apr 12, 2021 9:00 pm at Mon Apr 12, 2021 9:00 pm
>
> 
Here is the big file containing Messi models(ord and orp) in FIFA 08 PSP. 
You can extract it with Quickbms or any good big editor. Thanks 
https://www.mediafire.com/download/jqbvhud3bo6u1q5

The tool is not able to work with such files. There are differences in PSP format version.
## Post #33
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-04-29T06:44:13+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Oh, the PSP is something else, been trying this with different steps. I even used ord2o.bat from nfl 2000's mod, it didn't work. I tried combining both to form .o and still doesn't work. If you could try examining the file and create a tool for it, I would be grateful.
Thanks
## Post #34
- Username: murcianico
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 14, 2021 3:51 am
- Post datetime: 2021-05-13T20:03:25+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Thu Mar 05, 2020 3:10 am at Thu Mar 05, 2020 3:10 am
>
> 
Version 0.146 was released. It's available on Bitbucket.
https://bitbucket.org/fifam/otools/downloads/

Now GUI version is also available (Qt-based, requires Win7+).


Added experimental support for FIFA07 (for an example I imported this model)


I already achieved what I planned and why this tool was created - all FIFA20 Switch head models (more than 2'000) were converted to FIFA Manager, including generic heads and hairs... If you want to see how new faces look in a 12-year old FIFA engine, here you go:
 

 

 

 

 

 

 

As you can see even skinning was converted. The fact that we can completely and automatically convert character models from one game to another is... embrassing.

@mono24 
The geometry format is not same as it is in .o files, so I can't help here.

That looks amazing! I am playing FIFA Manager too and I am finding difficulty in the following: I want to use some 3D stadiums from [https://fifafaces0708.blogspot.com/2019 ... rscom.html](https://fifafaces0708.blogspot.com/2019/03/stadium-download-fifa07editorscom.html) . Let's say the European Division 1 Stadium one. The thing is that FIFA Manager only reads 9 files:
sky_0.o
sky_1.o
sky_3.o
stadium_0.o
stadium_1.o
stadium_3.o
texture_0.fsh
texture_1.fsh
texture_3.fsh

The files in the FIFA 07 format contain similar files but many more than 9, and when I rename only 9 of them the game says "Texture missing". Is there a way to use oTools to convert those FIFA 07 stadiums to FIFA Manager 08 stadiums?

Thanks in advance!
## Post #35
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-06-03T23:02:03+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Does this work for older NFS games like Hot Pursuit 2 that have a skeleton.o and other similar files?
## Post #36
- Username: St1ngLeR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 17, 2020 2:45 pm
- Post datetime: 2021-08-24T22:29:07+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from Assasinge ↑Fri Jun 04, 2021 7:02 am at Fri Jun 04, 2021 7:02 am
>
> 
Does this work for older NFS games like Hot Pursuit 2 that have a skeleton.o and other similar files?

It works, but the model loads without UV-mapping...
## Post #37
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-25T19:52:11+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

hi Dmitry.
Great tool! Appreciate for you work. Would you be able to add ps2 formats to your tool?
here's samples: [viewtopic.php?f=16&t=24397](https://forum.xentax.com/viewtopic.php?f=16&t=24397)
## Post #38
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2021-12-13T22:02:12+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from murcianico ↑Fri May 14, 2021 4:03 am at Fri May 14, 2021 4:03 am
>
> 
The files in the FIFA 07 format contain similar files but many more than 9, and when I rename only 9 of them the game says "Texture missing". Is there a way to use oTools to convert those FIFA 07 stadiums to FIFA Manager 08 stadiums?
Yes, there are wide options in OTools for creating and converting stadiums. With recent versions you can even export/import lamp lights, flag positions and collision model (for ball collisions).
There might be differences in FIFA 07 and FIFA Manager 08 file format, so maybe files must be converted.
Normally, you first export .o to .gltf (from Game 1 as target), and then import .gltf to .o (to Game 2 as target).

> Reply from Assasinge ↑Fri Jun 04, 2021 7:02 am at Fri Jun 04, 2021 7:02 am
>
> 
Does this work for older NFS games like Hot Pursuit 2 that have a skeleton.o and other similar files?

> Reply from St1ngLeR ↑Wed Aug 25, 2021 6:29 am at Wed Aug 25, 2021 6:29 am
>
> 
It works, but the model loads without UV-mapping...
Each game uses specific shaders (also shaders determine how vertex data is stored) - so this information must be researched before we can add full support for specific game. If there's no shader information, only vertex positions can be exported.

> Reply from Tosyk ↑Thu Aug 26, 2021 3:52 am at Thu Aug 26, 2021 3:52 am
>
> 
hi Dmitry.
Great tool! Appreciate for you work. Would you be able to add ps2 formats to your tool?
here's samples: viewtopic.php?f=16&t=24397
I checked PS2 format when I looked in Def Jam FFNY files... There are some differences in file layout. I don't have time to work in this direction.
## Post #39
- Username: Chaos01
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 02, 2021 3:02 am
- Post datetime: 2022-05-07T20:39:45+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Yeah I checked def jam ord files it’s not a model it’s animations files for characters it has like all characters strings and grabs moves the models are in another file called V2IP.viv 
and the ord files for characters every character has a number for there file
## Post #40
- Username: khaakaag
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 09, 2022 8:13 pm
- Post datetime: 2022-05-09T12:33:12+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Are you planing to explore fifa online 4. Those rx3 are a bit different and interesting. We can be in contact. I'm very exciting 

mobdro apk
## Post #41
- Username: ARCOG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 05, 2023 1:26 am
- Post datetime: 2023-03-18T02:06:50+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Forgive my lack of knowledge. I am modding NCAA Basketball 10 which is like NBA live. Most files are listed as .rpsgl. But some are models and not textures. Do you think this tool might work?
## Post #42
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2023-03-19T02:12:02+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

New verion 0.177 is uploaded on BitBucket.

[](https://postimg.cc/PNJKDh6Z) [](https://postimg.cc/c6zhMjjz)

[](https://postimg.cc/0Kzf1d6Z) [](https://postimg.cc/CzfNv7px)

Release notes
Finally added support for NBA Live games. For NBA Live 2003 and 2004 we have export and import, but exporting/importing morph meshes (player body and faces) is not possible. In .O format the morph implementation is very uncommon - you can apply morphing to any vertex attribute, even including bone weights. I think such morphing was never used anywhere, but in NBA Live 2004 we have morphing of texture coordinates, for example. And in most 3D applications (including Blender) and 3D formats, only morphing of positions and normals is expected. So there must be some special way to deal with it. I think morph export/import might be added in future OTools version.
We also can export Need for Speed Hot Pursuit 2 models, but import is not implemented. Also the export of some models is still not possible because they store meshes in some uncommon way. Cars in Need for Speed Hot Pursuit 2 use skeleton, but it's stored in a separate file. To export the model with this skeleton, "-skeleton" command is needed (-skeleton skeleton.o).
There's a new feature which allows to define vertex/bone connection (skinning) in 2D textures.
[](https://postimg.cc/PvNHDxJN)
More about this feature: [https://bitbucket.org/fifam/otools/wiki ... %20feature](https://bitbucket.org/fifam/otools/wiki/Texture%20to%20skin%20feature)

Changelog

0.177

```
- fixed crash in 0.176 on export, when output path was specified directly
- fixed import of bone weights in non-float format from glTF files
- option list for materials with very long name is now exported to a special .mato file
- "skeleton" option now can search for the model in the same folder with .o
- new feature: define vertex/bone connection (skinning) in 2D textures
- added import/export for NBA Live 2003 and NBA Live 2004 (editing morph models is still not possible)
- added export for Need for Speed Hot Pursuit 2 (some models still can't be exported because of different mesh storage in the file)
```

0.176

```
- fixed crash on batch fsh export
- improved fsh packing - now alignment and sections structure in most cases are identical to original fsh files
- added possibility to define output folder for FSH packing/unpacking
- added possibility to define output format for models (experimental at this moment; it's recommended to use GLTF as output format)
- possibility to define output formats in GUI tool
```

0.175

```
- removed dithering on 16-bit textures
- new options -flipNormals and -flipFaces (for import/export)
- new option -sortFaces (might help when mesh consists of many semi-transparent faces which overlap)
- new options for specific fsh packing, -fshKits,  -fshShoes, -fshBalls, -fshPatterns, -fshJNumbers, fshSNumbers
```
## Post #43
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2023-03-30T18:32:34+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Sun Mar 19, 2023 10:12 am at Sun Mar 19, 2023 10:12 am
>
> 
New verion 0.177 is uploaded on BitBucket.
Hello Dmitry, I see you have done a lot of work, is there any chance to be able to download models from Def Jam Icon in updates of your tool?
## Post #44
- Username: kinglalu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 31, 2023 11:37 am
- Post datetime: 2023-03-31T17:43:48+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Reply from DmitryFM ↑Sun Mar 19, 2023 10:12 am at Sun Mar 19, 2023 10:12 am
>
> 
New verion 0.177 is uploaded on BitBucket.

This is a neat tool I stumbled upon in my quest to figure out how to access these .o files. I am attempting to improve the models of NHL 07 on PSP, and it appears because each EA game handles its .o files differently, it may not be possible to access the files for it using this tool. I've also seen here that apparently for PSP, the process is different than what is currently supported, and so I really hope you do consider taking a look at  supporting NHL 07, as well as looking into supporting PSP .o files as well as it would be a big help for this too. I've noticed other people as well have been wanting to use this tool for PSP games, so it would also help many others too. If you want, I am in the discord for XeNTaX, and so if you want to ask or inquire about this, you can do so either on discord ideally, but here works too.

The zip file has an example .o file from NHL 07 on the PSP, if you need it.
[benchplayers.zip](https://xentaxbackup.github.io/file/23634_benchplayers.zip)
## Post #45
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2023-04-24T21:15:37+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

Ok, let's talk about PSP games.
Can you provide me a complete list of all PSP games where .o files are used?
Can you extract and upload all .o files from PSP games which you're interested in?

About the tool:
I finished research on shaders which are stored in .o files (usually it's called eaglrm.o).
[https://fifam.miraheze.org/wiki/O#EAGLMicroCode](https://fifam.miraheze.org/wiki/O#EAGLMicroCode)
Some of next OTools versions will have an option to extract shaders into readable format.



fifa08shader.PNG (41.46 KiB) Viewed 59 times


In DirectX9 FIFA games (starting from FIFA 08 PC) the shader code in .o file is not used, because game developers created a superstructure over shaders in eaglrm.o
So I'm not sure if I should work on import feature.
But still, I wanted to change shaders in the game, so I wrote an extension which allow to replace shaders on the fly:
[https://www.youtube.com/watch?v=T8FBOdE9ljI](https://www.youtube.com/watch?v=T8FBOdE9ljI)

I researched morph data earlier
[https://fifam.miraheze.org/wiki/O#Morph](https://fifam.miraheze.org/wiki/O#Morph)

So now only animations data in .O is not researched.
## Post #46
- Username: kinglalu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 31, 2023 11:37 am
- Post datetime: 2023-04-29T03:28:04+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

> Can you provide me a complete list of all PSP games where .o files are used?

They are used for essentially all EA sports games on the PSP, like NHL, FIFA, madden, NHL, and NBA

> Can you extract and upload all .o files from PSP games which you're interested in?

Yes, the main game I'm interested in is for NHL 07 on the PSP, as I want to look into updating models of the game. Linked below should be all or almost all the .o files of the game. I couldn't attach it here as file is too big, but I did upload it to mega.

[https://mega.nz/file/kQtEDAxT#30-EEwr8b ... QONcrSs5YU](https://mega.nz/file/kQtEDAxT#30-EEwr8bQsrHiayx0An-EMel6Jf2nCsrQONcrSs5YU)

While NHL 07 is what I am only interested in, I do believe there are communities out there for those other games mentioned above for the PSP, and would probably help them greatly as well, as I know that if this can support NHL 07, it would help greatly for me.

Now, there is a discord we are in for our community for modding NHL 07, and if you want to join it if you have any questions regarding NHL 07 .o files or for other PSP games that have .o files we can try our best to answer it with our knowledge. Here is the link:

[https://discord.gg/8T6443EQvV](https://discord.gg/8T6443EQvV)

Thanks for all your work so far on this, and I hope that functionality for NHL 07 on the PSP happens soon.
## Post #47
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2023-05-02T20:08:53+00:00
- Post Title: Re: OTools for EA Sports 3D Graphics format (.o, .fsh)

I checked files and now I see what's the difference.
Everything related to vertex and index buffer is different.
Also I noticed that .msh texture files are used instead of .fsh
Maybe I will add a support for PSP in future, but right now I don't have enough time.
