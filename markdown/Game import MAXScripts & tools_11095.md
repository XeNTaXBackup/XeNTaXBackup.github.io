## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-12-31T16:19:32+00:00
- Post Title: Game import MAXScripts & tools

All scripts and tools have been thoroughly tested, but let me know if you run into any problems. Unless otherwise specified, meshes are imported/exported with all available properties: vertex normals, UV mapping (all channels), vertex color, transformations, hierarchy, materials and textures.
Sadly, no animations. This is something I've been meaning to research for a long time, but I never had the time.

FBX converters typically require .NET Framework 3.5 and use FBX 2011.1 format specs. More details and instructions are provided with each app.

My MAXScripts are meant to run on max 2010 and up. Sorry, but max 2009 has less/different maxscript features and some of the functions won't work.
How to install scripts in 3ds Max:
1. Drag&drop mcr or mzp files in one of the viewports - this will initialize&install the script
2. Click on Customize -> "Customize User Interface" and switch over to the Toolbars tab; optionally select "Game file import" in Category, which is what I assign to all my scripts
3. Drag&drop the script from the list onto your toolbar; this will create a button that you can use from there on to run the script

So I don't repeat myself, I'd like to thank vagos21 for teaching me most of what I know about game formats and maxscript, helping me with several formats and issues, and also aluigi, Rick, Ekey and everyone else who created extraction scripts/tools.

In no particular order:

[kn5 converter](http://www.mediafire.com/download/i8xoax1ddjif2rx/kn5_converter.zip)
Supports all Assetto Corsa models (cars, tracks...) from Early builds to 1.1 final.

Usage: kn5conv.exe [-fbx|-obj|-objZMhack] [input_file/folder]
More info in the readme

- FBX supports almost all model features, except specific shader settings or textures (ex. dirt, damage).
  In case of multi-layer diffuse textures, the second (txDetail) map is used as diffuse, and the first is used as specular since it's usually a grayscale map.
  A complete list of material properties is included for reference as user-defined settings
- OBJ does not support hierarchy, transformations or UV tiling. Therefore, these are "baked" into the model so at least it looks good.
- OBJ ZMhack takes advantage of a bug (or feature?) in ZModeler2 that creates usable hierarchy from OBJ models
  I won't go into detail, it just works even if it's not supposed to  Small boxes are created instead of dummies which you can convert and use to set pivot positions.

[](http://www.imagebam.com/image/447fbe408033747) [](http://www.imagebam.com/image/a0d220408033873) [](http://www.imagebam.com/image/49cbc0408033964)

[M3G2FBX converter](http://www.mediafire.com/download/5b5gfesy459i4cg/M3G2FBX.zip).
- supports all models from RR3, NFS:MW and NFS:NL
- All LODs with normals, UV coordinates, vertex colors, hierarchy, transformations, materials, and texture names (for reference only)

Usage options:
- drag&drop an m3g file to convert it
- run the exe to convert any m3g file from the current folder
- use the command line to specify a file: M3G2FBX.exe input_file.m3g
- same thing with a folder or a path, only this time it will include all subfolders: M3G2FBX.exe input_folder
- run with -u argument (M3G2FBX -u file/folder) to make unique mesh names; useful if you plan to convert to OBJ afterwards

FBX files will always be saved in the same place as their m3g couterparts.
[](http://www.imagebam.com/image/df8b84381489527) [](http://www.imagebam.com/image/2b7dfc381489514) [](http://www.imagebam.com/image/de5401381489550) [](http://www.imagebam.com/image/011c05381492113) [](http://www.imagebam.com/image/20ffcf381492128) [](http://www.imagebam.com/image/793c2c381492143)

[SBA Brute](http://www.mediafire.com/download/m00pmunv9vjbvsg/sbaBrute.zip) - .sba texture converter for NFS:MW and NFS:NL
It is by no means a "true" converter. It basically guesses the image format and number of mipmaps based in width, height and image data size. Most textures are successfully converted, except cube maps and some special sba files.


[Dunia 2 mesh importer - WIP](http://www.mediafire.com/download/nh6st6783qea1vh/XBGimporter_0.8.zip)

It works with all XBG models from FC3, FC4 and The Crew, with the following features:
- vertex positions scaled with shader constants
- texture coordinates scaled with shader constants
- vertex normals decoded
- vertex colors
- LODs & submeshes
- hierarchy where available

After my last release, the meshes are now split by material and also all submeshes are properly imported (some were missing in the earlier version).
Unfortunately I haven't had the time to investigate material files properly, so textures will need to be applied manualy.

Far Cry 3:
[](http://www.imagebam.com/image/10fe47370074044) [](http://www.imagebam.com/image/1417ee370074065) [](http://www.imagebam.com/image/df7bd5370074084) 

Far Cry 4:
[](http://www.imagebam.com/image/0cf626370074220) [](http://www.imagebam.com/image/29e504370074237) [](http://www.imagebam.com/image/57ec08370074252) 

The Crew:
[](http://www.imagebam.com/image/940887342917674) [](http://www.imagebam.com/image/4a483d342917677) [](http://www.imagebam.com/image/df1c5d347610037) 


[Unity Assets Importer v0.8.9](https://www.mediafire.com/folder/y2id147f8iqe0//Latest%20release)
This is one of the biggest projects I've tackled, and it's till being updated as new Unity versions are launched.

[Unity Importer 1.0 beta](https://www.mediafire.com/folder/y2id147f8iqe0//Latest%20release)
It has more or less the same functionality but its entire interface is built in .NET, allowing me to integrate a TreeView of the actual asset hierarchy. This gives you extended filtering options so that you can import only the objects you need.

I will continue to update both scripts for a while, but at some point the old script will be retired.

The scripts are compatible with Web, PC, iOS, Android, PS3, Xbox 360, OSX and Linux games built with Unity 2, 3 and 4 (up to 4.3.2f1). It doesn't work with games created with Unity versions older than 2.5.0, which I believe were iOS-exclusive and lack some elements of identification.

There are a lot of Unity games out there. To name a few interesting examples:
[Porsche model showcase](http://www.porsche.com/international/modelstart/all/) - click the 3D button - [screenshot gallery](http://www.imagebam.com/gallery/jy5mjvh167gwgixqvbipts1f152dn936)
[Scion car showcase](http://www.scion.ca/scion/en/build-price) - click the 3D button - [screenshot gallery](http://www.imagebam.com/gallery/1lr4mogi9233ewnsr1yaqto8ueq3fdrh)
[List of Unity games](http://forum.xentax.com/viewtopic.php?f=16&t=11154) with instructions on how to extract files.
[](http://www.imagebam.com/image/29f718276886922) [](http://www.imagebam.com/image/80e38a276887017) [](http://www.imagebam.com/image/f4585c290522612) [](http://www.imagebam.com/image/40c3bb290522621) [](http://www.imagebam.com/image/5b26e5255178231) [](http://www.imagebam.com/image/a60590255178215) 
[More screenshots](http://www.imagebam.com/gallery/l4yo1pftkn3hzh6i7pfxqqobotab7dcs)


[Away3D script collection](https://www.mediafire.com/folder/fsis1fzc0l4aa/Away3D)
awd maxscript + quickbms decompressor
This is a beta release and has been tested only on models from Honda 3D Design Archives and Nissan UK Personalization pages (2014 Note, Micra, Juke, 2013 Juke).
No texture support at this time. Use URL Snooper or similar to get .awd or .swf resources. Extraction tools are also provided in the link above.
atf texture convertor (from old version into a new format readable by ATF Viewer)
maxscript for loading GarageFuse scenes + abg to obj converter
I'm not yet sure if this is an Away3D format or if it's something custom for garagefuse.com.
Again, use URL Snooper to get .abg .xml and texture files from garagefuse.com

[](http://www.imagebam.com/image/a29bde341878664) [](http://www.imagebam.com/image/8c01b0341878669) [](http://www.imagebam.com/image/eb1773341878655) [](http://www.imagebam.com/image/41fdab342554359) [](http://www.imagebam.com/image/886cf2342554371) [](http://www.imagebam.com/image/18ec46342554364) [](http://www.imagebam.com/image/3c5a80342554367) 


[GT Racing 2 BDAE Importer](http://www.mediafire.com/download/k5cbufkc7qj7qfl/GT_Racing_2_importer_0.4.zip)
Supports cars and tracks, probably other models too.
Textures are in PVR format, but their extension is from the source file (usually TGA). The script will rename them but make sure you have the PVR plugin installed.
Also don't forget to supply the texture path before importing.
Tools for extraction:
- [Gameloft ZIP Unscrambler](http://forum.xentax.com/viewtopic.php?f=32&t=11527) to convert gla archives; big thanks to GMMan for making this possible!
- my [obb unpacker](http://forum.xentax.com/viewtopic.php?f=10&t=11462) for the Android game (not needed for iOS)

Bdae files are actually zip with no compression, and they contain the actual bdae models plus other files. The script can read data directly from packed bdae, so there's no need to extract them.
[](http://www.imagebam.com/image/b2f010340512266) [](http://www.imagebam.com/image/e7911e340512311) [](http://www.imagebam.com/image/6f7a19340512275) [](http://www.imagebam.com/image/24de14340512283) 


[Gameloft Pig Importer](http://www.mediafire.com/download/puyen85su71ppy5/Gameloft_pig_importer.zip) - Deprecated; use PIG2FBX instead
Supports cars, tracks, characters and pretty much any game model.
Most textures are in PVR format, but their extension is from the source image (TGA, PSD). The script will rename them but make sure you have the [PVR plugin](https://www.mediafire.com/folder/gib7qadk4zv1g//PVR%20plugins) installed.

Works only with Asphalt 1.5 or older and Minion Rush.
Newer versions of Asphalt8 use lz4 compressed buffers and textures. Decompression is impossible with MAXScript, so I've created a standalone command-line tool that will convert models to FBX.
[Download PIG2FBX here](http://www.mediafire.com/download/3aafbwswjqjk00c/PIG2FBX.zip)

[](http://www.imagebam.com/image/08bebc375682013) [](http://www.imagebam.com/image/0a897f375682032) [](http://www.imagebam.com/image/90afad375682068) [](http://www.imagebam.com/image/6d2dba375682052)
[](http://www.imagebam.com/image/bff015324346109) [](http://www.imagebam.com/image/8e2eab324346116) [](http://www.imagebam.com/image/624296324346129) [](http://www.imagebam.com/image/0997c1324346139) [](http://www.imagebam.com/image/5830ea324346154) 


[Assetto Corsa Importer](http://www.mediafire.com/download/5tu326io08tc87l/Assetto_Corsa_Importer.zip)
I made this way back in March when the Tech Preview came out with only one car. Since then the Early Access game was released with several new cars.

Supports cars, tracks, characters and pretty much any game model.
Textures are packed inside model files and the script will extract (but not overwrite) them in a texture folder.
[](http://www.imagebam.com/image/fe4fca295088291) [](http://www.imagebam.com/image/167214295088341) [](http://www.imagebam.com/image/a4c964295088276)


[Eutechnix Model Importer](http://www.mediafire.com/download/xn7ifzn0p72888c/EutechnixMeshImporter.zip)
Model importer for Nascar 2013 and '14 PC games. Partial support for Auto Club Revolution.

Textures have to be extracted first using this script: [viewtopic.php?f=18&t=11326](http://forum.xentax.com/viewtopic.php?f=18&t=11326)
In some cases you will have to set tiling factors manually (eg. carbon fiber, track grass or asphalt).

You'll need aluigi's [nascar2011.bms](http://aluigi.altervista.org/papers/bms/nascar2011.bms) script to extract *.AR archives and then you can import *.ARC files.
[](http://www.imagebam.com/image/f1f73d317104018) [](http://www.imagebam.com/image/77a241317104008) [](http://www.imagebam.com/image/59e7a9317103939) [](http://www.imagebam.com/image/cc0047317103969) [](http://www.imagebam.com/image/4617c2317103994) 
[](http://www.imagebam.com/image/c04c48314733414) [](http://www.imagebam.com/image/fc1196314733418) [](http://www.imagebam.com/image/eea4ee314733423) [](http://www.imagebam.com/image/b749ef314733427) [](http://www.imagebam.com/image/4afe18314733456)


[DriverSF Importer v1.01](http://www.mediafire.com/download/3ylja32hgt45j40/DriverSF_Importer_1.01.zip)
Vehicle importer for Driver San Francisco.

The script is able to load dngvehicles.sp and extract vehicle files or import them directly.
There are 3 files per car: cockpit, LOD1 and LOD2-5. Once extracted, vehicle files can also be loaded separately. If you do so, remember to extract the Shared Resources file!
Textures are extracted automatically as you import a specific car, but they are spread out within the car files, so you will first have to import all 3 to get all textures.
[](http://www.imagebam.com/image/5d5f69263972910) [](http://www.imagebam.com/image/f95e9e263972944)


[Milestone Importer v1.2](http://www.mediafire.com/file/7mion0y3ay4s36a/Milestone_import_1.2.mcr)
Works with vehicles and characters from SBK2011, SBK Generatins, MUD, WRC3 and Superstars V8 Next Challenge.

Game files can be extracted with aluigi's [msmixext tool](http://aluigi.altervista.org/papers/msmixext.zip)
[](http://www.imagebam.com/image/007086222012327) [](http://www.imagebam.com/image/ee718e222012334) [](http://www.imagebam.com/image/5d355e222012740)


[I3D Importer v1.2](http://www.mediafire.com/download/klxd1nx5x47xjlp/I3Dimport_1.2.mcr)
Model importer for Farming simulator (tested with 2012 and 2013). Supports vehicles and characters (drivers, peds, cows, chickens )

This is one of the first scripts I made by myself, so it could use some optimizations. But it works...
[](http://www.imagebam.com/image/09f2f3217436179) [](http://www.imagebam.com/image/d82a65217436180) [](http://www.imagebam.com/image/70e167217438973) 


[SMS Importer v3.0](http://www.mediafire.com/download/i41xinqq4a4vn3y/SMS_Importer_3.1c.zip)
Capable of importing vehicle, track and character models from games created by Sligtly Mad Studios with their Madness engine: Shift1&2, TRFRL and pCars.
This script was originally created by vagos21 ~2 years ago. Since then, we've been working together to optimize and update the script.

Game files can be extracted with aluigi's [BFF script](http://aluigi.altervista.org/papers/bms/nfsshift.bms). The script is also capable of renaming MEB and BMT files with their internal names.
[](http://www.imagebam.com/image/6d7b4c134000870) [](http://www.imagebam.com/image/58bd18134000874) [](http://www.imagebam.com/image/8bceff235532723)
## Post #2
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2013-12-31T23:38:46+00:00
- Post Title: Game import MAXScripts & tools

Just wanted to say "Thank You Thank You Thank You" for these.  ive been looking for weeks for a AC extractor and i was just about to give up, i came here and gave it one last shot and this thread was the only result and Lo and behold you have a script.  So thank you, this makes for a very good new years present..

And on that note. there is only 20 mins until new year here (im in the UK ) so id like to wish you a Happy new year.
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-01T13:47:01+00:00
- Post Title: Game import MAXScripts & tools

You're welcome  And Happy new year!

I've also added an incomplete script for Far Cry 3, maybe someone finds use for it or manages to finish it.
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-01-01T14:11:45+00:00
- Post Title: Game import MAXScripts & tools

Chipicao, would be great if you add support for CSR Classics game on ios. unity engine.

thanks for your work and happy new year!
## Post #5
- Username: Guerra8888
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 06, 2010 10:47 am
- Post datetime: 2014-01-01T17:26:55+00:00
- Post Title: Game import MAXScripts & tools

Many THX Chipicao...
## Post #6
- Username: Freakydevil
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 03, 2010 12:38 am
- Post datetime: 2014-01-01T21:19:36+00:00
- Post Title: Game import MAXScripts & tools

Many thanks for this great scripts!

Would it be possible for the pCars script to also rename the dds textures?
## Post #7
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-01T22:07:33+00:00
- Post Title: Game import MAXScripts & tools

Absolutely impossible. MEB and BMT files contain internal names that in 99% of the cases match the intended filename.
But DDS texture don't have any names inside, only image data.

However, the script outputs a list of missing textures in the Listener (press F11 or open it from the MAXScript menu). You can use that to manually rename textures and then load the car again.
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-01-01T22:11:04+00:00
- Post Title: Game import MAXScripts & tools

> Reply from Chipicao
>
> the scripthey Chipicao, what about CSR Classics? i can upload some samples via pm
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-01T22:55:01+00:00
- Post Title: Game import MAXScripts & tools

Hey Tosyk. I didn't ignore your post. 
I'm working on adding support for Unity 4.3 as we speak.

And thanks, but I can get the game from iTunes.
## Post #10
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-02T02:29:25+00:00
- Post Title: Game import MAXScripts & tools

Ah, I thought it was a new game, but it's not.
Cars are stored in separate bundles in this folder: \Payload\csrclassics.app\AppDataRoot\AssetBundles
They have extensions like numbers (.7, .8, .18...) but they are all UnityWeb archives like .unity3d, so you can use aluigi's script on them.

The only real problem was that this game uses strange array indices for assets, something I encountered before with Blizzard's Hearthstone.
I already had a workaround in mind for some time, and I guess now was the time to implement it. 
[](http://www.imagebam.com/image/881840298339544) [](http://www.imagebam.com/image/17a615298343294) 

Hearthstone:
[](http://www.imagebam.com/image/b080c3298346775) [](http://www.imagebam.com/image/4d1da1298346779)

Updated first post with new download link.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-01-02T11:33:18+00:00
- Post Title: Game import MAXScripts & tools

Chipicao, great work! but how to use it with unpacked .7,.6,.8,.22... file?

importer doesn't want to see unpacked files. i tried to rename them to .unityweb/.unity3d/.assets but nothing seems to work.

edit:
aah, extension has to be .high
## Post #12
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-02T12:55:55+00:00
- Post Title: Game import MAXScripts & tools

When I unpack .7 .6 .8 files with aluigi's script, the extension of CustomAssetBundle files is already .high
Isn't it the same for you?
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-01-02T13:43:40+00:00
- Post Title: Game import MAXScripts & tools

> Reply from Chipicao
>
> When I unpack .7 .6 .8 files with aluigi's script, the extension of CustomAssetBundle files is already .high
Isn't it the same for you?that is true, it is .high, but as a perfectionist i'm trying to make everything perfect, including extensions, so i've just renamed .high to .unity3d and .tex.
Can't find a tool for converting .pvr, though.

p.s.: would be great if your scripts were adapted for 3ds max 2009
## Post #14
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-02T14:06:27+00:00
- Post Title: Game import MAXScripts & tools

Well they're not supposed to be .unity3d or .tex.
My script uses a filter to exclude non-unity files, that's why it didn't work (even though .unity3d is a unity file, it's an archive)

If you want to be a perfectionist, CAB files usually have no extension at all, so you can remove .high and it will still work. 

PVRTexTool: [http://www.imgtec.com/powervr/insider/p ... extool.asp](http://www.imgtec.com/powervr/insider/powervr-pvrtextool.asp)

Sorry, max 2009 support will probably never happen. I would have to go through the whole script (3000+ lines of code) and check the documentation to see which command is supported in 09, which has different parameters, and so on.
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-01-02T14:40:32+00:00
- Post Title: Game import MAXScripts & tools

Chipicao, roger that. Still, great work, thank you    I really like rusty textures in CSR Classics.

edit:
Chipicao, would you be able to support weights too? I found a game called Avengers Initiative, and your script work perfect with it, game has cool characters, and would be great if your script support weights with adding skin modifier on the skinned models. Thank you
## Post #16
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-01-12T22:17:35+00:00
- Post Title: Re: My MAXScripts

great tools thank you very much for publishing them. Which android car games use unity3d? I tried with Real Racing 3 and Asphalt 6 but the plugin didnt find nothing
## Post #17
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-15T01:19:45+00:00
- Post Title: Re: My MAXScripts

Real Racind 3 and Asphalt 6 are not unity games.

The best way to tell is if you find a folder called Data with level# and sharedassets# files inside.
## Post #18
- Username: 9lXA
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 06, 2011 5:25 am
- Post datetime: 2014-01-24T14:38:59+00:00
- Post Title: Re: My MAXScripts

Excellent! But how you rip cars from The Walking Dead Chop Shop? I can import only garage..
## Post #19
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-27T12:35:58+00:00
- Post Title: Re: My MAXScripts

idk what to say, all versions worked for me ([iOS](https://itunes.apple.com/us/app/the-walking-dead-chop-shop/id670418183), [Android](https://play.google.com/store/apps/details?id=com.Bossa.Chopshop&hl=en), [Web](http://walkingdeadchopshop.com/))

Are you sure you're importing the proper nodes?
## Post #20
- Username: 9lXA
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 06, 2011 5:25 am
- Post datetime: 2014-01-27T14:41:51+00:00
- Post Title: Re: My MAXScripts

Yes i download from PM, and unpack .apk (unpacked size ~900Mb). Script find only one "level1" file (assets/bin/Data folder, 1.8Mb). This is garage, where is cars i don't know((
## Post #21
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-27T15:53:00+00:00
- Post Title: Re: My MAXScripts

You can't have level1 without level0, and there should also be a mainData file (I think cars are in the later)
Try to load the whole Data folder instead
## Post #22
- Username: StewMM
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 17, 2007 3:09 am
- Post datetime: 2014-01-30T17:00:10+00:00
- Post Title: Re: My MAXScripts

Have you got any tips for importing from iOS apps.  I've managed to import cars from CSR, Kia, Mercedes Valencia, Chop Shop and xDrive Challenge.
The others like Peugeot, Opel and Mazda apps open up the assets but don't load the car models.
## Post #23
- Username: Pfreak
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 05, 2012 4:01 am
- Post datetime: 2014-01-30T20:58:32+00:00
- Post Title: Re: My MAXScripts

Brillant script! Really helps a lot.
May i ask if there are other car manufactors as well?
## Post #24
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-31T07:48:27+00:00
- Post Title: Re: My MAXScripts

@StewMM Load the whole Data folder and look for nodes named that contain the words "car" or "image target", or generally nodes with many meshes.
For Opel Adam import the node called "Opel"; for Mazda3 it's called "PointCloud-Tabletop".

@Pfreak see here: [viewtopic.php?f=16&t=11154](http://forum.xentax.com/viewtopic.php?f=16&t=11154)
## Post #25
- Username: Freakydevil
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 03, 2010 12:38 am
- Post datetime: 2014-01-31T14:02:54+00:00
- Post Title: Re: My MAXScripts

Since today im facing this weird problem that the parts arent correctly aligned anymore with the pCars Script. 

[](http://abload.de/image.php?img=unbenannt-1uzjh6.jpg)

Does anyone have an idea what setting i messed up in 3ds max?

And another request, would it be possible to load every material into a single slot instead of all into one multimat?
## Post #26
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-31T17:59:20+00:00
- Post Title: Re: My MAXScripts

I have no idea what max setting could affect transformations. I can confirm the script is working on my side (max 2014 as well).
Try this and see if it makes any difference: [http://www.mediafire.com/download/b8m0w ... er_3.1.zip](http://www.mediafire.com/download/b8m0wvcsw6l9qww/SMS_Importer_3.1.zip)

Regarding materials, even if I don't make them into one big multimaterial, most objects use more than one so max would require multimaterials anyway. The only difference is you would have many smaller multimaterials and maybe a few standard materials.
## Post #27
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-02-01T18:15:46+00:00
- Post Title: Re: My MAXScripts

Any possible date for the animation support feature of unity importer?
## Post #28
- Username: StewMM
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 17, 2007 3:09 am
- Post datetime: 2014-02-02T17:30:40+00:00
- Post Title: Re: My MAXScripts

When loading the Seat Mii it says there's 125 meshes but only loads a base square.
[https://itunes.apple.com/gb/app/seat-mi ... 54072?mt=8](https://itunes.apple.com/gb/app/seat-mii-ar/id490654072?mt=8)
[mii.jpg](https://xentaxbackup.github.io/file/6991_mii.jpg)
## Post #29
- Username: Pfreak
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 05, 2012 4:01 am
- Post datetime: 2014-02-02T19:48:37+00:00
- Post Title: Re: My MAXScripts

Ah ok thx for the Link 
I kinda have the same problem as StewMM when loading an "App" car.
2 more questions: What does the "apply mesh normals" button do exactly in max?
Any chance for bringing up a ".carbin" script for the Forza Models?
Forza cars always had a normal issue and didnt reflect a 100% clean. (Thats why i asked the first question about the "mesh normals")
Greetz
## Post #30
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-02T23:05:12+00:00
- Post Title: Re: My MAXScripts

@StewMM Strange, it works fine here. Restart max and try again. Let me know if it still doesn't work.

@Pfreak Which car app gives you problems?

The "apply mesh normals" does exactly what the name suggests.
Importing vertex normals with maxscript requires quite a lot of CPU resources, because the standard function is broken and I have to use a workaround. So I included that checkbox in case you want to load the mesh faster as a "preview".

No, Forza Studio exports normals properly. The issue you are seeing with normals is caused by the fact that in Forza3 they are heavily compressed. It is a format issue and there's nothing anyone can do about it.
In Forza 4 and Horizon they use a different method to store normals which allows better precision. You probably noticed that models look smoother than FM3.
## Post #31
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-02T23:14:51+00:00
- Post Title: Re: Game import MAXScripts

Hi guys,


thanks for this script...........I´m just downloading it , and will go to have a look on how that works 


I use to do renders with max , of cars from games ......I ve been using 3DSIMED to extract the 3D from ASSETTO CORSA and rFactor . I´ve use also Forzastudio and wuick BMS for an other game 


I´m interesting to see how it works for the cars in PCars......
## Post #32
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-02T23:58:43+00:00
- Post Title: Re: Game import MAXScripts

Al ready back here for a question.

The car files in PCars are .bff....The script only take : bml,vhf etc........ There is maybe something i´m missing ?...I need maybe to use QUICK BMS first , but it should have the "pcars.bms" somewhere maybe ?

In advance thanks
## Post #33
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T00:23:34+00:00
- Post Title: Re: Game import MAXScripts

Sorry i´m not flooding lol, i´ve just understood how the luigi sceipt works with note pad and just to save the file as BMS .......

Sorry
## Post #34
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T00:31:42+00:00
- Post Title: Re: Game import MAXScripts

Okay the files are extrated in a folder,

I ve found how to import them in MAX, but only one by one .......There is a way to import them in one go?
## Post #35
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-03T06:32:28+00:00
- Post Title: Re: Game import MAXScripts

Yes, you're supposed to use aluigi's script, which I assume you already found: [http://aluigi.altervista.org/papers/bms/nfsshift.bms](http://aluigi.altervista.org/papers/bms/nfsshift.bms)

Do you mean how to import all MEB files from one car at once? Tick "Rename files" (you only need to do this once) and then import the bml or vhf file. It will automatically load every part.
## Post #36
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T08:31:18+00:00
- Post Title: Re: Game import MAXScripts

Hi,

thanks for your support ....Yes i´ve used "Luigi script" ......So now in a folder , i have BML, MEB, BMT and the DDS files for the textures.....

After that i open 3ds max and i do like this:

[http://i57.servimg.com/u/f57/17/93/51/86/proces10.jpg](http://i57.servimg.com/u/f57/17/93/51/86/proces10.jpg)


By clicking on import model, i can only choose one by one bmt file......
## Post #37
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T09:26:39+00:00
- Post Title: Re: Game import MAXScripts

Ok , i ve done it "one by one" (and the files are not named, engine door etc....Hard work  )



After that in the material editor i have the mane of all the texture but DDS have a number ....Any solution , or i have to start a "painstaking work"  ?
## Post #38
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-03T09:48:33+00:00
- Post Title: Re: Game import MAXScripts

No, you have to do it like this:
[](http://www.imagebam.com/image/3767be311659176) 
Step 2 will rename the files to their intended names so that they can be imported through the BML/VHF.
After they are renamed, if you want to import the car again later, you can skip step 2.

There's also a Rename button that will do just that, without importing the car.
[](http://www.imagebam.com/image/916c33311667327) [](http://www.imagebam.com/image/dbe494311667322) 
before . . . . . . . after

Textures are the only ones that you will have to rename yourself. If you press F11 or goto MAXScript menu and click on MAXScript Listener, you will see a list of missing texture names.
It's pretty easy to identify them, and if you manage to rename them all, the next time you import the car it will have textures too.
[](http://www.imagebam.com/image/4e8b96311661940)

Some tips:
- they usually come in triplets (duffuse, specular and normal map)
- wheels, brakes and tires are easy to spot, and they have a second set of blurred maps (to simulate high-speed rotation)
- check the listener for texture sets that have a 4th component called "_GLOW". These are light-emissive maps for lights or cockpit dials. If you find the glow map it's easy to spot the diffuse, spec and norm because they have the same layout
[](http://www.imagebam.com/image/520625311666115) 

In the listener you will also notice that some car parts have failed to load. This usually happens to the LODX cockpit, I think because the cars are still in development.
Anyway, all you have to do is import the missing cockpit MEB files.
## Post #39
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T19:29:14+00:00
- Post Title: Re: Game import MAXScripts

Thanks a lot for your support,


it´s true that by this way it looks easier 

I have a last question regarding that , in your screen , i can see that we see the image of your DDS file......Me i can´t 



I use W7 64....Any ideas ?


Also i want to thanks  you  all , who take the time to people like me to do scropt and all this stuff ( i don´t know nothing about it)......
## Post #40
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T20:12:26+00:00
- Post Title: Re: Game import MAXScripts

I´ve find something to see the dds files images:

[https://code.google.com/p/sagethumbs/](https://code.google.com/p/sagethumbs/)
## Post #41
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-03T20:19:49+00:00
- Post Title: Re: Game import MAXScripts

I use SageThumbs as well
## Post #42
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-03T21:09:38+00:00
- Post Title: Re: Game import MAXScripts

I´ve started the process.............It´s a  big challenge lol
## Post #43
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-05T21:32:24+00:00
- Post Title: Re: Game import MAXScripts

After days,


every car i render , this happend, the same parts are not showing..................If i take a model wich is nor from this game everything works fine....Any crypted objet ? Is that possible?

[http://i57.servimg.com/u/f57/17/93/51/86/missin10.jpg](http://i57.servimg.com/u/f57/17/93/51/86/missin10.jpg)
## Post #44
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-06T06:26:12+00:00
- Post Title: Re: Game import MAXScripts

What exactly is the issue?

If you're talking about transparency, simply adjust your texture alpha settings.
If it's the missing cockpit, as I've said, for some cars you have to import the interior MEB files separately.
## Post #45
- Username: phil671
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 08, 2011 7:50 pm
- Post datetime: 2014-03-06T07:39:29+00:00
- Post Title: Re: Game import MAXScripts

Thanks 


Sometimes, i´m a bit stupid........Yes the alpha channel 

[http://i57.servimg.com/u/f57/17/93/51/86/rs50010.jpg](http://i57.servimg.com/u/f57/17/93/51/86/rs50010.jpg)
## Post #46
- Username: StewMM
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 17, 2007 3:09 am
- Post datetime: 2014-03-09T17:58:21+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> @StewMM Strange, it works fine here. Restart max and try again. Let me know if it still doesn't work.
I've got back into this.. and I still can't get the plugin to load some of the car meshes.
 Not sure how to explain the bug when nothing happens when you click 'Import Selected'.
If it helps..
Windows 7 64bit
3DSmax 2014 - 16.0
Unity plugin: 0.8.7f4

iOS Apps that work:
    Kia Quoris, Chop Shop HD, CSR Racing, CSR Classics, Audi LeMans 2011, Audi A3, xDrive Challenge.

iOS Apps that don't work:
    Peugeot 208 and 208GTi, Peugeot 308, Adam & You, Mazda 3, McLaren 650S, 

Mercedes Benz Valencia can only import the lower mesh/poly models.


-- edit --

I found the 0.8.8 update and it appears to be working now
## Post #47
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-03-09T18:37:04+00:00
- Post Title: Re: Game import MAXScripts

It works better in max2011 no idea how. I have the same problems in max2014
## Post #48
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-10T06:11:42+00:00
- Post Title: Re: Game import MAXScripts

@TomWin Make sure you have the latest 0.8.8 version.
## Post #49
- Username: StewMM
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 17, 2007 3:09 am
- Post datetime: 2014-03-10T10:14:15+00:00
- Post Title: Re: Game import MAXScripts

Don't forget to update the first post with new updates
## Post #50
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-10T10:46:31+00:00
- Post Title: Re: Game import MAXScripts

I always do. The first post actually links to a "Latest release" folder" in case I forget
## Post #51
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-16T21:17:41+00:00
- Post Title: Re: Game import MAXScripts

I just finished an import script for Nascar '13 and '14 (PC). Thanks jimjack for bugging me about it and samples/unpacking.
It supports both car and track models with vertex normals, colors, UV1, UV2, UV3, object transformations, hierarchy and instancing.
Materials are applied but only just; no diffuse/specular information or textures. I might get back on this later after I fix texture extraction (read below).

[](http://www.imagebam.com/image/c04c48314733414) [](http://www.imagebam.com/image/fc1196314733418) [](http://www.imagebam.com/image/eea4ee314733423) [](http://www.imagebam.com/image/b749ef314733427) [](http://www.imagebam.com/image/4afe18314733456) [](http://www.imagebam.com/image/a6c715314733463) [](http://www.imagebam.com/image/3804ca314733466) [](http://www.imagebam.com/image/09e34b314733471) [](http://www.imagebam.com/image/3cbb2d314733475) 

Get the download link in my first post.
Importing the body or interior of a car takes about 1 minute. Tracks take between 5 and 7 minutes because they have thousands of objects.

You'll need aluigi's [nascar2011.bms](http://aluigi.altervista.org/papers/bms/nascar2011.bms) script to extract *.AR archives and then you can import *.ARC files.
aluigi also made a script for ARC files, but I don't recommend using it because the data is actually serialized. It's good for extracting textures, but it needs some modifications for that as well. Read more here: [viewtopic.php?f=18&t=11326](http://forum.xentax.com/viewtopic.php?f=18&t=11326)
## Post #52
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-20T08:19:25+00:00
- Post Title: Re: Game import MAXScripts

> Reply from StewMM
>
> Don't forget to update the first post with new updates
> Reply from Chipicao
>
> I always do. The first post actually links to a "Latest release" folder" in case I forgetApologies. It seems the link was not actually updated to version 0.8.8. It's fixed now.
## Post #53
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-27T14:39:47+00:00
- Post Title: Re: Game import MAXScripts

I have re-released the Nascar script under the name Eutechnix Mesh Importer, with support for diffuse, specular and normal maps, and partial support for Auto Club Revolution models.
Textures have to be extracted first using this script: [viewtopic.php?f=18&t=11326](http://forum.xentax.com/viewtopic.php?f=18&t=11326)
See the readme file for more information.
## Post #54
- Username: Fengo
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Aug 12, 2011 3:02 pm
- Post datetime: 2014-04-04T12:06:32+00:00
- Post Title: Re: Game import MAXScripts

With the NASCAR '14 thing, the bms script is not working, it gives an error

[](http://imgur.com/m7t7mhZ)


Any ideas why?
## Post #55
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-04T12:44:47+00:00
- Post Title: Re: Game import MAXScripts

You have to run the script on cdfiles#.dat, not on the .AR archives.
## Post #56
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2014-05-09T18:17:30+00:00
- Post Title: Re: Game import MAXScripts

Well, maybe I do something wrong with I3D importer, but I can only import camera and dummies.  
Here's the pic:
[](http://www.imagebam.com/image/c13377325671887)
## Post #57
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-09T20:00:50+00:00
- Post Title: Re: Game import MAXScripts

Which vehicle are you trying to import, and from which game?
## Post #58
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2014-05-09T21:14:09+00:00
- Post Title: Re: Game import MAXScripts

Game: Farming Simulator 2013.
Vehicle: Buehrer6135A.
Only traffic cars can be imported without any problems
## Post #59
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-10T09:12:45+00:00
- Post Title: Re: Game import MAXScripts

Could you send me the model files via PM?
The one I have works without issues...

Edit: activate viewport statistics (key 7) and see if the number of vertices is 0 or not
The script might be missing mesh faces in your case.
## Post #60
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-11T16:26:52+00:00
- Post Title: Re: Game import MAXScripts

Never mind, I see what's going on. The file format has changed with the Titanium edition or one of the new updates.

I've been meaning to re-write a better I3D script, so I guess this is a good opportunity. I'll get back when I have something.
## Post #61
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-05-11T19:28:51+00:00
- Post Title: Re: Game import MAXScripts

hi, Chipicao
would you support weights for your scripts?
## Post #62
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-05-15T05:40:31+00:00
- Post Title: Re: Game import MAXScripts

Also, would it be hard for you to improve on the Mafia/LS3D 4DS import/export? It's been twelve years yet we don't have a decent tool besides Zmodeler 1.x, to which skinned character/ped meshes aren't supported.
## Post #63
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-15T06:49:41+00:00
- Post Title: Re: Game import MAXScripts

The problem is I'm not good with skinning in maxscript. Vagos and I tried it once and it all went to shit. 

I do have some clues on how to make it work, but not the time or disposition. Sorry.
## Post #64
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-23T08:52:06+00:00
- Post Title: Re: Game import MAXScripts

I have updated the Unity script to fix an issue with certain meshes from Unity 4.3.x games.
@those who sent me PMs about meshes not loading, this should fix it. Let me know if there are any more problems.

LE: Fix something and break something else...
The latest release had an issue with meshes from Unity 4.0-4.2.
Please re-download the fixed script (version # remains the same).
## Post #65
- Username: vladikkgg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 01, 2011 8:44 pm
- Post datetime: 2014-06-15T17:24:22+00:00
- Post Title: Re: Game import MAXScripts

I find configurator of VW auto [http://configurator.atlant-m.kiev.ua/](http://configurator.atlant-m.kiev.ua/) .This made whis TurnTool(file .tnt). How to convert it to obj,3ds?
## Post #66
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-15T18:41:22+00:00
- Post Title: Re: Game import MAXScripts

Hi, 
I exported my first PCARS circuit, but I feel it lacks textures. Do you know if PCARS stores textures in another file than the circuit?
## Post #67
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-15T23:13:28+00:00
- Post Title: Re: Game import MAXScripts

Textures cannot be applied automatically for pCars models because they lack correct names. You will have to do everything manually, and unfortunately it's not easy for tracks.
## Post #68
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-17T10:51:28+00:00
- Post Title: Re: Game import MAXScripts

Actually it is not simple, another question I get an error on some tracks 

--No "findstring" function for undefinened

Have you an idea of the problem

No problem to import a cars
## Post #69
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-17T11:30:55+00:00
- Post Title: Re: Game import MAXScripts

Which track?
## Post #70
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-17T12:07:40+00:00
- Post Title: Re: Game import MAXScripts

Brands Hatch Indy, no problems with Bathurst !!
## Post #71
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-20T14:19:54+00:00
- Post Title: Re: Game import MAXScripts

My first import Pcars - Bathurst, Now I must find the names of Textures
[whereisit.jpg](https://xentaxbackup.github.io/file/7495_whereisit.jpg)
## Post #72
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-20T14:21:24+00:00
- Post Title: Re: Game import MAXScripts

Have you any idea how to extract the circuit and car Raceroom or DTM Experience?
## Post #73
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-21T06:14:25+00:00
- Post Title: Re: Game import MAXScripts

I checked Brands_hatch_indy and indeed there's an error in the loading process. I'll post once I have a fix.

IIRC DTM Experience is encrypted, we need tools to decrypt. No idea about Raceroom.
## Post #74
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-21T16:41:51+00:00
- Post Title: Re: Game import MAXScripts

Thanks in advance for the debug, RaceRoom is certainly as DTM Exp. This is the same game
## Post #75
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-21T18:55:09+00:00
- Post Title: Re: Game import MAXScripts

Raceroom Racing Experience is what i want right now, almost all the racing games can be ripped except this one that have the awesome Audi 90 IMSA GTO from 1989 #4
## Post #76
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-06-21T23:02:28+00:00
- Post Title: Re: Game import MAXScripts

Released Unity Assets Importer 0.8.9 with Unity 4.5.0 compatibility, a few bugfixes and general code optimization. The script is not encrypted anymore, you can view the full code if you're interested.

Also releasing a new script called Unity Importer 1.0 beta. It has more or less the same functionality but its entire interface is built in .NET, allowing me to integrate a TreeView of the actual asset hierarchy. This gives you extended filtering options so that you can import only the objects you need.

I will continue to update both scripts for a while, but at some point the old script will be retired.

Old vs. New:
[](http://www.imagebam.com/image/fca80f334493724) [](http://www.imagebam.com/image/eac969334493731) 
[](http://www.imagebam.com/image/8d5ab0334493728) [](http://www.imagebam.com/image/9ab636334493734)
## Post #77
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-06-22T12:32:29+00:00
- Post Title: Re: Game import MAXScripts

Does not have the name of textures is annoying for Pcars, I can not find the texture for asphalt. Strange
## Post #78
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-06-22T15:16:02+00:00
- Post Title: Re: Game import MAXScripts

Thank you very much for the script updates
## Post #79
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2014-06-29T07:55:09+00:00
- Post Title: Re: Game import MAXScripts

Chipicao, thanks you!
Support bones and animation planned? Bones really need.
## Post #80
- Username: Gucio85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 08, 2011 2:09 am
- Post datetime: 2014-07-09T08:58:52+00:00
- Post Title: Re: Game import MAXScripts

Will it be possible to add an option to "load folder" button in your scripts, so each file will import into seperate layer, named after file name?
## Post #81
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-07-09T09:02:31+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Mrtest
>
> Chipicao, thanks you!
Support bones and animation planned? Bones really need.bones are there, only weight information is lost.
## Post #82
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-09T10:42:00+00:00
- Post Title: Re: Game import MAXScripts

Support for bones and animation is planned, but no ETA. I have bones and blend weights too, it's just a matter of putting them together.

> Reply from Gucio85
>
> Will it be possible to add an option to "load folder" button in your scripts, so each file will import into seperate layer, named after file name?
There is already a Load folder option, and in the new beta script you will see everything structured by folder and file. Have a look at the screenshots above.
## Post #83
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-07-09T11:33:54+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> in the new beta script you will see everything structured by folder and file. Have a look at the screenshots above.already tried it out from your mediafire folder. looks and works really great. many thanks
## Post #84
- Username: Gucio85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 08, 2011 2:09 am
- Post datetime: 2014-07-09T11:34:25+00:00
- Post Title: Re: Game import MAXScripts

Ok, but other than unity scripts? currently i'm playing with Gameloft PIG Importer...
## Post #85
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-09T11:41:49+00:00
- Post Title: Re: Game import MAXScripts

I think I updated the Pig Importer with a folder button shortly after it was released. I must have forgotten to announce it.
Please re-download and let me know if it has the button.
## Post #86
- Username: Gucio85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 08, 2011 2:09 am
- Post datetime: 2014-07-19T16:31:34+00:00
- Post Title: Re: Game import MAXScripts

After i put PVR plugin into 3dsmax (2012, 32bit) I have this error/warning
[](http://imageshack.us/photo/my-images/537/63b708.jpg/)

in 3dsmax folder i have only one PVRTexTool_v2012.dle file - in plugins directory
## Post #87
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-20T05:09:49+00:00
- Post Title: Re: Game import MAXScripts

Look for a file called PVRTexTool3DSMax2012.dle and delete it. That's the old version of the plugin; the script probably couldn't delete it due to file permissions.
## Post #88
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-22T19:28:36+00:00
- Post Title: Re: Game import MAXScripts

GT Racing 2 script released, link and description in first post.

The BDAE format turned out to be pretty complex. Fairly easy to parse but very cumbersome.
In theory I could adapt the script to work with any Gameloft game, but there are quite a few differences between bdae versions and it would take some time. Maybe in the future, right now I have other projects.
## Post #89
- Username: jlp369
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 15, 2012 9:32 am
- Post datetime: 2014-07-23T03:11:29+00:00
- Post Title: Re: Game import MAXScripts

How do I import the bdae file into max if the script only imports .pig?
## Post #90
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-23T05:39:51+00:00
- Post Title: Re: Game import MAXScripts

Sorry, I uploaded the wrong file  Re-download please.
## Post #91
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-07-25T08:12:20+00:00
- Post Title: Re: Game import MAXScripts

Thanks Chipicao for the GT Racing 2 script much apreciate  
[https://fbcdn-sphotos-g-a.akamaihd.net/ ... 9069_o.jpg](https://fbcdn-sphotos-g-a.akamaihd.net/hphotos-ak-xpf1/t31.0-8/1501645_877564372271634_2841901870709489069_o.jpg)
## Post #92
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-07-29T19:16:27+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> I checked Brands_hatch_indy and indeed there's an error in the loading process. I'll post once I have a fix.

Did you find a fix for this circuit?
## Post #93
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-29T19:19:05+00:00
- Post Title: Re: Game import MAXScripts

Sorry, I didn't have the time. And I probably won't work on pCars until the game is released.
## Post #94
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-07-30T15:17:54+00:00
- Post Title: Re: Game import MAXScripts

the game kritika online for android seems to work partially. That is nice
## Post #95
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-31T17:05:00+00:00
- Post Title: Re: Game import MAXScripts

I've just uploaded a beta script for Away3D models. Link and more info in 1st post.
[](http://www.imagebam.com/image/a29bde341878664) [](http://www.imagebam.com/image/8c01b0341878669) [](http://www.imagebam.com/image/eb1773341878655)

I'm still working on this one as I find new model formats used by the Away3D engine.
## Post #96
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-02T11:19:06+00:00
- Post Title: Re: Game import MAXScripts

Added scripts for garagefuse.com models in the Away3D collection.

[](http://www.imagebam.com/image/41fdab342554359) [](http://www.imagebam.com/image/886cf2342554371) [](http://www.imagebam.com/image/18ec46342554364) [](http://www.imagebam.com/image/3c5a80342554367)
## Post #97
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2014-08-06T14:04:00+00:00
- Post Title: Re: Game import MAXScripts

Model is loaded incorrectly. In the center of the mess. Chipicao, Please fix it.
[https://yadi.sk/d/6Ih2F9dPZBSg9](https://yadi.sk/d/6Ih2F9dPZBSg9)
## Post #98
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-06T14:30:43+00:00
- Post Title: Re: Game import MAXScripts

I saw your PM but unfortunately my hands are full these days. I'll see what I can do and I'll post here.
## Post #99
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2014-08-06T14:37:58+00:00
- Post Title: Re: Game import MAXScripts

Thanks
## Post #100
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-08-10T13:19:42+00:00
- Post Title: Re: Game import MAXScripts

i have a problem con I3d importer( 3ds studio 2015)
when I start the script I immediately generates an error

[farming.jpg](https://xentaxbackup.github.io/file/7652_farming.jpg)
## Post #101
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-10T16:51:52+00:00
- Post Title: Re: Game import MAXScripts

Sorry, I3D importer doesn't work with the new version of Farming Simulator because they changed the format. It is now compressed and/or encrypted, and unless somebody makes an extractor there's not much I can do.
## Post #102
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-08-10T18:33:09+00:00
- Post Title: Re: Game import MAXScripts

I'm not importing the new version of FS.
not start the script
## Post #103
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-11T20:40:05+00:00
- Post Title: Re: Game import MAXScripts

Can you send me a sample via PM?
## Post #104
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-08-11T20:52:35+00:00
- Post Title: Re: Game import MAXScripts

the error occurs when I click "run script"
before selecting any file
## Post #105
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-11T23:04:33+00:00
- Post Title: Re: Game import MAXScripts

OK, I think I know what's going on. The link I posted is for viewing the script in plain-text, and your browser or mediafire fails to save it.
Try this: [http://www.mediafire.com/download/klxd1 ... rt_1.2.mcr](http://www.mediafire.com/download/klxd1nx5x47xjlp/I3Dimport_1.2.mcr)
Open it in notepad first and make sure it begins with "-- I3D model import script" and not with "<html>".
## Post #106
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-08-12T09:49:21+00:00
- Post Title: Re: Game import MAXScripts

thanks now it works   
However, as has already written MATT55, it does not work with tractors   
need an example?
## Post #107
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-12T11:46:51+00:00
- Post Title: Re: Game import MAXScripts

No use, I explained what's going on with the new format.
## Post #108
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-08-12T19:25:22+00:00
- Post Title: Re: Game import MAXScripts

Chipicao, can you look into another bdae? A game called 'Fast & Furious' has a deal with some sort of brres and bdae combination.

pmed you with example.
## Post #109
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-14T10:03:13+00:00
- Post Title: Re: Game import MAXScripts

Unfortunately that's a different format, not related to Gameloft BDAE.
## Post #110
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-08-14T10:06:03+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Unfortunately that's a different format, not related to Gameloft BDAE.thanks, sorry to hear it, though.
## Post #111
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-08-20T21:12:45+00:00
- Post Title: Re: Game import MAXScripts

2 questions
 any have a max script to import old Unity files?
is hard to make max or quick script?
## Post #112
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-08-27T21:57:11+00:00
- Post Title: Re: Game import MAXScripts

> Reply from MacedoSTI
>
> 2 questions
 any have a max script to import old Unity files?
is hard to make max or quick script?

go here:
[viewtopic.php?f=10&t=10085&hilit=unity](http://forum.xentax.com/viewtopic.php?f=10&t=10085&hilit=unity)
## Post #113
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-28T05:29:02+00:00
- Post Title: Re: Game import MAXScripts

How old? My current maxscript supports Unity from version 2.5.0 till the latest 4.5.3.

Unity files prior to 2.5.0 are a bit different and it's hard to identify their version in order to automate the process.
## Post #114
- Username: weisuolong0
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 20, 2014 12:41 pm
- Post datetime: 2014-09-02T16:12:46+00:00
- Post Title: Re: Game import MAXScripts

Chipicao  hi ~
my enlish is poor but i am a coder!
thank you for you collections!
i just want to unpackage a gameloft game named Asphalt 7 

i used script of  bdae but 3dmax cannot do .

if you have time , can you see this resourse of game?

link [http://www.mz6.net/game/12219.html](http://www.mz6.net/game/12219.html)
## Post #115
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-02T17:54:27+00:00
- Post Title: Re: Game import MAXScripts

I already looked at Asphalt 7 and other Gameloft games.

The format is very similar to Asphalt 8, but at the same time it has many differences. Unfortunately I don;t have time to do a proper research, sorry.
## Post #116
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-09-02T22:16:27+00:00
- Post Title: Re: Game import MAXScripts

12tails online works quite nice



I can import models with bones, stage objects and some other stuff. Would be nice to have it all 

Here is homepage for game. No extaction needed

[http://12tails.herorangers.com/home/home](http://12tails.herorangers.com/home/home)
## Post #117
- Username: yoda
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 30, 2008 5:28 am
- Post datetime: 2014-09-05T21:11:23+00:00
- Post Title: Re: Game import MAXScripts

chipicao : can you take a look on this and made a importer ?

[viewtopic.php?f=10&t=10997](http://forum.xentax.com/viewtopic.php?f=10&t=10997)
## Post #118
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-06T09:22:17+00:00
- Post Title: Re: Game import MAXScripts

Sorry but I don't have time for new formats right now.

However, I did make a script that will import Ninja Ripper rips with propper normals and UV mapping (only for Rivals!).
You can get it here, along with rip files: [http://kotschopshop.com/topic/5312889/](http://kotschopshop.com/topic/5312889/)
## Post #119
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-06T20:51:34+00:00
- Post Title: Re: Game import MAXScripts

Ah, i wish i had checked that topic before 

3 or 4 months now, i made a blender script for the Minion Rush game models, which happen to be .pig files and as i am seeing now they are pretty  much common stuff for Gameloft games.

I don't have the skeletons right yet,  but i've managed to get the models, and make some homemade functions for converting pvr textures and get them directly to blender.

I was planning to make a topic about it but since i found this one, if chipicao is ok with that, i can post the blender script here as an additional .pig importer for Blender
## Post #120
- Username: yoda
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 30, 2008 5:28 am
- Post datetime: 2014-09-06T23:02:38+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Sorry but I don't have time for new formats right now.

However, I did make a script that will import Ninja Ripper rips with propper normals and UV mapping (only for Rivals!).
You can get it here, along with rip files: http://kotschopshop.com/topic/5312889/

arf sad news

i check the link you give me , script work fine , but unfortunaly the car i seek is not present on the two rips links, i want the new gallardo lp 560 4.
## Post #121
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-07T07:08:34+00:00
- Post Title: Re: Game import MAXScripts

> Reply from gregkwaste
>
> AI was planning to make a topic about it but since i found this one, if chipicao is ok with that, i can post the blender script here as an additional .pig importer for Blender
You're welcome to post it here if you'd like.

@yoda post in that topic, maybe someone will help.
## Post #122
- Username: yoda
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 30, 2008 5:28 am
- Post datetime: 2014-09-07T08:06:18+00:00
- Post Title: Re: Game import MAXScripts

done
## Post #123
- Username: weisuolong0
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 20, 2014 12:41 pm
- Post datetime: 2014-09-11T16:46:53+00:00
- Post Title: Re: Game import MAXScripts

lz 
i am very sorry to read  this following codes from the script of  

if (bit.or vmask 256) == vmask do --dirt map
						(
							fseek f (readShort f #unsigned) #seek_cur
							for v=1 to numVerts do
							(
								tx = (readshort f #signed)/32767.0
								ty = (readshort f #signed)/32767.0
								append t2arr [tx, 1-ty, 0]
							)

							align = readShort f #unsigned
							if (align > 16 or align == 0 or (mod align 2) != 0.0) then -- 32bit components
							(
								free t2Arr
								fseek f (-numVerts*4 - 2) #seek_cur
								for v=1 to numVerts do
								(
									tx = readfloat f
									ty = readfloat f
									append t2arr [tx, 1-ty, 0]
								)
							)
							else fseek f -2 #seek_cur
							format "vmask========  % \n" 256
						)
## Post #124
- Username: weisuolong0
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 20, 2014 12:41 pm
- Post datetime: 2014-09-11T16:49:50+00:00
- Post Title: Re: Game import MAXScripts

up floor script from Gameloft_pig_importer.mcr   just to load pig file from asphalt 8  gameloft game

can you explain why the code do this  


how to understand 'vmask' word mean？
## Post #125
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-11T18:33:02+00:00
- Post Title: Re: Game import MAXScripts

'vmask' is just the name I gave to the [FVF code](http://msdn.microsoft.com/en-us/library/windows/desktop/bb173428%28v=vs.85%29.aspx) variable.

If you haven't heard of it before, FVF code is basically an integer composed of smaller power of 2 numbers (2^n).
Each 2^n number is assigned to a specific vertex property, so by analyzing the FVF code you can tell which properties are available in a vertex buffer.
These are always different from game to game, but in case of Gameloft Pig format this is what we have:
2^0 = vertex positions
2^1 = vertex normals
2^7 = UV coordinates for channel 1
2^8 = UV coordinates for channel 2

So for example a vmask of 387 has all of the above, and bit.or checks if 256 is in 387 (which it is).
There are other properties such as tangents, binormals or blend weights, but they weren't needed so I'm just seeking over them.
I should also be noted that vertex properties are always in the same order.


The second part of the code is a workaround for an issue I had with this format.
Most elements of a vertex property are 16bit integers, but in some cases they are 32bit floats. There should be an indicator somewhere that tells the game which is when, but I couldn't find it in the time I worked on this format.

So I came up with a quick and dirty solution that guesses if the values were read properly or not. It's based on the fact that after each set of vertex properties there is a 16bit integer for alignment - which I read as 'align'.
'align' should always be higher than 0 but lower than 16, and a multiple of 2. If one of these conditions isn't met, it means the script hasn't reached the end of the set, so it goes back and reads the values again as 32bit floats.
It's not an ideal solution but it seems to work.


I hope I cleared everything up, if not let me know.
## Post #126
- Username: weisuolong0
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 20, 2014 12:41 pm
- Post datetime: 2014-09-13T02:14:00+00:00
- Post Title: Re: Game import MAXScripts

first  thank you very much   

i study study （in Chinese  means 学习学习 (*^__^*) 嘻嘻……）

by the way where are you from、？  my Colleague says that maybe we are all in china 

o(╯□╰)o
## Post #127
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-14T07:29:33+00:00
- Post Title: Re: Game import MAXScripts

Nah, I'm not from China
## Post #128
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-09-22T21:36:57+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> I checked Brands_hatch_indy and indeed there's an error in the loading process. I'll post once I have a fix.

IIRC DTM Experience is encrypted, we need tools to decrypt. No idea about Raceroom.

Aluigi offers a first script for RaceRoom ... it advance

[http://aluigi.altervista.org/papers/bms ... _kluns.bms](http://aluigi.altervista.org/papers/bms/others/raceroom_kluns.bms)
## Post #129
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-09-26T12:04:23+00:00
- Post Title: Re: Game import MAXScripts

Any plans on adding support for Asphalt Overdrive on your Pig Engine script? The game's cheesy and reeks of a Minion Rush-esque cash-in, but the cars seem exploitable enough for us to mess with.
## Post #130
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-26T13:07:41+00:00
- Post Title: Re: Game import MAXScripts

@PseT & huckleberrypie I'll have a look
## Post #131
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-26T13:34:30+00:00
- Post Title: Re: Game import MAXScripts

Asphalt Overdrive just works, they haven't changed the format.
[](http://www.imagebam.com/image/53b2ef353783957) 

But I can only find 2 cars in the IPA. I think the rest are probably downloaded after you install the game.
## Post #132
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-09-27T03:08:18+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Asphalt Overdrive just works, they haven't changed the format.
 

But I can only find 2 cars in the IPA. I think the rest are probably downloaded after you install the game.

So I noticed. The game downloads the cars ad-hoc as the user chooses them, which accounts for why the .IPA's so small.
## Post #133
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-27T06:21:40+00:00
- Post Title: Re: Game import MAXScripts

Surprisingly the downloaded cars are in a different format, at least on android.

Can anyone please check on iOS and send me the app folder via PM? You only have to play the first mission (after the intro) then go to the dealer and scroll through cars.
## Post #134
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-09-27T13:17:03+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> @PseT & huckleberrypie I'll have a look

Cool
## Post #135
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-09-28T01:22:44+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Surprisingly the downloaded cars are in a different format, at least on android.

Can anyone please check on iOS and send me the app folder via PM? You only have to play the first mission (after the intro) then go to the dealer and scroll through cars.

How different is it? Could they be encrypted, scrambled or something?
## Post #136
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-28T07:02:58+00:00
- Post Title: Re: Game import MAXScripts

It's hard to say, there are plenty of differences and similarities. Not compressed, but the filesize definitely indicates that models are lower-poly.
## Post #137
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-09-28T10:51:01+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Surprisingly the downloaded cars are in a different format, at least on android.

Can anyone please check on iOS and send me the app folder via PM? You only have to play the first mission (after the intro) then go to the dealer and scroll through cars.

I'll download on iPad and mail you the folders. Hold on a little. hehe
## Post #138
- Username: SomeTemp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 27, 2014 6:49 pm
- Post datetime: 2014-10-01T06:57:43+00:00
- Post Title: Re: Game import MAXScripts

Hi guys, nice work. Any gamoft pig importer for blender?
## Post #139
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2014-10-03T12:54:23+00:00
- Post Title: Re: Game import MAXScripts

Actually, I downloaded and installed Asphalt OverDrive on iTunes.
But, its archive consists of only pieces of s**t I thought.
Supposing its composed files, we've to completely install it anyway and break the protection of it.

Also, Driftspirits / ドリフトスピリッツ (Bandai Namco Games) is protected by the publisher from the works like Mr.chipi's.
Thus, when Driftspirits is downloaded via iTunes or Google Play, its composed files aren't complete and its models are pieces of s**t in this case.
## Post #140
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2014-10-12T11:34:02+00:00
- Post Title: Re: Game import MAXScripts

wow,you are great.
i like i3d importer.i have some question about this script.
Why it dont set scale for rescaled mesh in giants editor?

And if possible to make version able to import new format of i3d? (i3d+shape).

thank you.


---edit
So ok,i've fixed it for import correct scale,now start work at shape import
## Post #141
- Username: Ha3aP
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 02, 2013 1:40 am
- Post datetime: 2014-10-12T17:34:42+00:00
- Post Title: Re: Game import MAXScripts

raceroom pls pls pls
## Post #142
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-10-12T21:52:30+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> How old? My current maxscript supports Unity from version 2.5.0 till the latest 4.5.3.

Unity files prior to 2.5.0 are a bit different and it's hard to identify their version in order to automate the process.

really i dont know
extract correctly but don't open

Assembly - UnityScript.dll 12kb
mainData 57 kb
sharedassets-1.assets 19.431 kb


Assets Explorer


your importer (Autodesk 3Dmax 2010 32bits)


When I met the forum I talked to you about this car (I do not know if you remember)




  i tried sometimes to see it 
and looks like "protected file"
or very old unity idk idk ;_;

idk what i do ;-;

[http://www.mediafire.com/download/5pahp ... 60Unit.rar](http://www.mediafire.com/download/5pahpoi03zkn4up/Gol360Unit.rar) < unity file

on others Unity / assets files works fine

examples (others assets)

[](https://flic.kr/p/pb5qVY)[Passat Variant](https://flic.kr/p/pb5qVY) by [Ｌ ｕ ｃ ａ ｓ.](https://www.flickr.com/people/85099067@N08/), on Flickr
[](https://flic.kr/p/oESNmY)[S0N1K](https://flic.kr/p/oESNmY) by [Ｌ ｕ ｃ ａ ｓ.](https://www.flickr.com/people/85099067@N08/), on Flickr
## Post #143
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-10-22T04:15:45+00:00
- Post Title: Re: Game import MAXScripts

Yeah, that's a very old 2.0.2f2.

Where did you find the other cars?
## Post #144
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-10-23T04:00:50+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Yeah, that's a very old 2.0.2f2.

Where did you find the other cars?

dont have a way to get this model?

btw
sonic : old site from chevrolet brazil 
passat : New Passat view ( [www.animechtechnologies.com](http://www.animechtechnologies.com) )
## Post #145
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-25T12:07:09+00:00
- Post Title: Re: Game import MAXScripts

And what about watch gods?
## Post #146
- Username: Icaab2607
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 02, 2014 7:51 pm
- Post datetime: 2014-11-02T13:40:57+00:00
- Post Title: Re: Game import MAXScripts

In 3d max,after installation plugin,there is such a an error:
## Post #147
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-11-02T22:30:12+00:00
- Post Title: Re: Game import MAXScripts

I'm afraid there is no official PVR plugin for max 2015 yet.
## Post #148
- Username: Icaab2607
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 02, 2014 7:51 pm
- Post datetime: 2014-11-03T13:01:41+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> I'm afraid there is no official PVR plugin for max 2015 yet.
I understund,need to download max 2014.
## Post #149
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-11-03T14:01:01+00:00
- Post Title: Re: Game import MAXScripts

Check PM, I've sent you a working plugin.
## Post #150
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-04T00:34:05+00:00
- Post Title: Re: Game import MAXScripts

Anyone can say about MaxScript formatters (similar this for Java [http://jsbeautifier.org/](http://jsbeautifier.org/)) ?

thx ...
## Post #151
- Username: caolamds
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 13, 2014 11:33 am
- Post datetime: 2014-11-09T08:14:09+00:00
- Post Title: Re: Game import MAXScripts

Gameloft Pig Importer error

importer 3ds Max 2014 file pig Asphalt 8 ver 1.6.2

Runtime error: Vertex index in face out of range
[Untitled.jpg](https://xentaxbackup.github.io/file/8054_Untitled.jpg)
## Post #152
- Username: Icaab2607
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 02, 2014 7:51 pm
- Post datetime: 2014-11-12T13:49:23+00:00
- Post Title: Re: Game import MAXScripts

No, he continues to write:
PVR texture plugin not supported in max version 17(and in 2015,and in 2014).
What the crap?
## Post #153
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-11-13T21:26:02+00:00
- Post Title: Re: Game import MAXScripts

Hello,
Now the script for Project Cars does'nt works
## Post #154
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-04T04:16:42+00:00
- Post Title: Re: Game import MAXScripts

> Reply from caolamds
>
> Gameloft Pig Importer error

importer 3ds Max 2014 file pig Asphalt 8 ver 1.6.2

Runtime error: Vertex index in face out of range
Hello, I suggest using the Android version, I have successfully imported
[BaiduShurufa_2014-12-4_3-35-29.png](https://xentaxbackup.github.io/file/8193_BaiduShurufa_2014-12-4_3-35-29.png)
## Post #155
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-04T04:31:21+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Check PM, I've sent you a working plugin.Hello, my friends, thank you for your great work. I tested Minion Rush game with Gameloft Pig Importer script error, hope to upgrade scripts, attach a sample file
[models.rar](https://xentaxbackup.github.io/file/8194_models.rar)
## Post #156
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-05T09:44:45+00:00
- Post Title: Re: Game import MAXScripts

The PIG format has been updated with lz4 compression. My MAXScript only works with old game versions.

I've started a standalone tool to export models to FBX, but development is on hold. I'll post here when I have something ready.
## Post #157
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-07T10:32:22+00:00
- Post Title: Re: Game import MAXScripts

I've released the Dunia 2 script I was working on a few months ago. Works with Far Cry 3, FC4 and The Crew.

It's still incomplete as it doesn't import materials or textures, but everything else works fine, including LODs, submeshes, normals, mesh and UV scaling, hierarchy.
Link in 1st post.
## Post #158
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-12-07T15:57:05+00:00
- Post Title: Re: Game import MAXScripts

Oh dang! I guess maybe I shouldn't have created this thread......
[viewtopic.php?f=16&t=12339&p=101414#p101414](http://forum.xentax.com/viewtopic.php?f=16&t=12339&p=101414#p101414)
## Post #159
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-07T17:10:13+00:00
- Post Title: Re: Game import MAXScripts

Don't sweat it, it's always good to have multiple tools 

Actually it was your thread that reminded me about this script and I thought there's no point not to share it.
## Post #160
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-12-07T18:05:50+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Don't sweat it, it's always good to have multiple tools 

Actually it was your thread that reminded me about this script and I thought there's no point not to share it.

Cool. I looked at the new mcr file and it's certainly an update! 【•】_【•】
Looks like mine has a ways to go still.  

BTW, do you know if there has been any update to the extraction tools?
Without filenames, finding the textures is a real pain.
The models are easy enough to find using grepWin, but of course the xbt files have nothing to search with.
( no strings attached   ) 

Also, I haven't found anything that reads DX10 DDS files.
## Post #161
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-07T19:06:27+00:00
- Post Title: Re: Game import MAXScripts

Well Far Cry 3 has a pretty good file list, as I'm sure you know.
Don't know anything about FC4.

No updates for the Crew unfortunately.  Ekey has been of great help with his extractor, but he wasn't able to get too far due to the protection used in the beta.
For now he doesn't have access to the final game, but if anyone can help with a key, you know where to find him.

As for textures, I was able to read them without issues using the nVidia plugin for Photoshop.
## Post #162
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2014-12-07T19:13:40+00:00
- Post Title: Re: Game import MAXScripts

Decided to try this one for FC3 till Dude is done with Maya, I have no Max 2010, using 2012 instead, I managed to get the model imported and the skeleton but...there are no weights?
## Post #163
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-07T19:22:37+00:00
- Post Title: Re: Game import MAXScripts

Sorry, there aren't any. I am not experienced in working with weights, skeletons and maxscript, nor am I interested at the time.
## Post #164
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2014-12-07T19:24:38+00:00
- Post Title: Re: Game import MAXScripts

Oh...I thought it's cause of 2012.
## Post #165
- Username: thor96ita
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 31, 2014 8:41 pm
- Post datetime: 2014-12-15T22:29:30+00:00
- Post Title: Re: Game import MAXScripts

Hi, I have a problem with max scripts, I drag and drop the script for the crew in but nothing happen. I have autodesk 3d max 2015. Some one can help me pls?
## Post #166
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-16T16:21:56+00:00
- Post Title: Re: Game import MAXScripts

Nothing is supposed to happen after you drag&drop. Follow steps 2 and 3.
## Post #167
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T17:24:55+00:00
- Post Title: Re: Game import MAXScripts

HI Chipicao, my friends, thank you for your great work. I used Milestone Importer v1.2 script test SuperstarsV8Racing game, error, I am using max2012 and max2015. here is a sample file car02.rar [https://onedrive.live.com/redir?resid=6 ... file%2crar](https://onedrive.live.com/redir?resid=6A28B826BE5F1236!169&authkey=!AGHJAuUKMknP2W8&ithint=file%2Crar).
[BaiduShurufa_2014-12-23_1-10-34.png](https://xentaxbackup.github.io/file/8345_BaiduShurufa_2014-12-23_1-10-34.png)
## Post #168
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-23T14:54:08+00:00
- Post Title: Re: Game import MAXScripts

Sorry but Superstars V8 Racing is not supported. Only Superstars V8 Next Challenge and the others I listed.
## Post #169
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-23T15:34:57+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> Sorry but Superstars V8 Racing is not supported. Only Superstars V8 Next Challenge and the others I listed.Hi Chipicao, thank you very much for your help.
## Post #170
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2014-12-25T08:00:54+00:00
- Post Title: Re: Game import MAXScripts

MotoGP 14 will be supported for the Milestone Importer?
## Post #171
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-01-01T16:24:34+00:00
- Post Title: Re: Game import MAXScripts

Hello =)

I have a question about the Unity 3d game Dreamfall: Chapters.

While the script exports every texture fine and loads most character models, there are some characters that do not appear in the list after loading the archieves at all (they are definetly ingame tho and their textures extract fine when choosing to extract all textures). I tested the old and the new version of the importer and both just don't show them on the list. Is there a fix for this or sth i'm doing wrong?
## Post #172
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-01T18:49:07+00:00
- Post Title: Re: Game import MAXScripts

Can you give me a couple of character names that you can't find?
## Post #173
- Username: JoshuaX
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 06, 2015 7:59 pm
- Post datetime: 2015-01-06T16:16:07+00:00
- Post Title: Re: Game import MAXScripts

Hi Chipicao,
I just wonder - is there a way that Dunia 2 mesh importer script will/would properly named imported meshes by their internal names? Find a proper wheels mesh (or other car part like engine, exhaust etc...) to import for imported car model mesh is a quite a adventure...
## Post #174
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T16:49:22+00:00
- Post Title: Re: Game import MAXScripts

There are no internal mesh names! Mwuahahaha  
Sorry. The format does does have names for dummy nodes, which I see I forgot to apply, but even those are null strings in The Crew.

The script will probably get a refresh soon to allow multiple file import and LOD selection.
## Post #175
- Username: JoshuaX
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 06, 2015 7:59 pm
- Post datetime: 2015-01-06T17:08:42+00:00
- Post Title: Re: Game import MAXScripts

> Reply from Chipicao
>
> The script will probably get a refresh soon to allow multiple file import and LOD selection.
No meshes / material internal names = bad news
Multiple file import and LOD selection optin = good news
At the end - thank you!
## Post #176
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-06T17:15:04+00:00
- Post Title: Re: Game import MAXScripts

You might want to check this, maybe it will help in some way: [viewtopic.php?p=102641#p102641](http://forum.xentax.com/viewtopic.php?p=102641#p102641)
## Post #177
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-01-11T08:45:20+00:00
- Post Title: Re: Game import MAXScripts

Can anyone tell me how to unpack The Crew dat files... Gibbed Dunia 2 is not working for me
## Post #178
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-11T09:20:23+00:00
- Post Title: Re: Game import MAXScripts

All required tools are here: [viewtopic.php?f=10&t=11719](http://forum.xentax.com/viewtopic.php?f=10&t=11719)
## Post #179
- Username: Snoopy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 12, 2015 9:50 pm
- Post datetime: 2015-01-12T14:03:31+00:00
- Post Title: Re: Game import MAXScripts

Hello, thank you for so many importers. I am having trouble importing tracks from pcars. I get this message:

--   End: undefined
--   OBJini: "C:\Users\****\AppData\Local\Autodesk\3dsMax\2014 - 64bit\ENU\en-US\plugcfg\gw_objimp.ini"
--   modelDir: #("D:", "DOWNLOAD", "pcars", "pCars", "Pakfiles", "TRACKS", "extracted")
--   matcount: 360
--   start: 56876509
--   iFiletype: #.sgb
>> MAXScript Rollout Handler Exception:
-- Unable to convert: undefined to type: Integer64 <<

I am using max 2014, I tried 2011 and it crashed there too. Maybe it was a different exception there. I tried the florence and dubai tracks. Works fine for cars.
## Post #180
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-12T18:53:48+00:00
- Post Title: Re: Game import MAXScripts

There seem to have been many problems with tracks during pCars development.
To be honest the track import part was a bit of a patch-job on my part.

When the game is released I will have another look at the format and update the script, or perhaps make a faster standalone converter.
Until then I'm sorry but I don;t have the time.
## Post #181
- Username: Snoopy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 12, 2015 9:50 pm
- Post datetime: 2015-01-13T10:01:48+00:00
- Post Title: Re: Game import MAXScripts

Fair enough. I managed to import a track from an old build, but they randomly crash on import too. Thanks for the work still.
## Post #182
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-01-23T07:56:15+00:00
- Post Title: Re: Game import MAXScripts

Chipicao, regarding this Unity game: [https://itunes.apple.com/ca/app/raids-o ... 93204?mt=8](https://itunes.apple.com/ca/app/raids-of-glory/id808793204?mt=8)



First time ever this happens, Lol.
Unity Studio says the same, nothing to extract, but there is data there:



Any idea?
## Post #183
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-01-23T08:30:37+00:00
- Post Title: Re: Game import MAXScripts

This is made with Unity 5 beta, that's why it doesn't work.

I've done most of the research on Unity 5, I just need to "code it in". I'll announce here when I have something ready.
## Post #184
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2015-02-01T05:11:06+00:00
- Post Title: Re: Game import MAXScripts

Thank you for your amazing work Chipicao.  

not sure why but I simply can not make the following to work   ..

[http://www.mediafire.com/download/i41xi ... r_3.1c.zip](http://www.mediafire.com/download/i41xinqq4a4vn3y/SMS_Importer_3.1c.zip)

.. not on max2012 not even on max2014

not sure why, any suggestions please  ?


UPDATE

It worked only if I opened Max with admin rights, then had to open it by "run script", otherwise would not work for me, closed it then opened max as usual and it was there.


thank you.
## Post #185
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2015-02-06T17:45:18+00:00
- Post Title: Re: Game import MAXScripts

Chipicao,

The script for PCARS, not working now, I just did a test on a track I'd managed to imported there a few months. Now there are errors.

Do you make an update soon?

Thanks
## Post #186
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2015-02-06T22:44:58+00:00
- Post Title: Re: Game import MAXScripts

Does the SMS Importer v3.0 properly rename every single file the way it does with the geometry?
when trying to render in max it sais textures missing do to wrong names.



Capture.PNG (18.1 KiB) Viewed 325 times
## Post #187
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-02-15T11:10:19+00:00
- Post Title: Re: Game import MAXScripts

@PseT the script will be updated after the game is released

@mono24 it can only rename geometry and material files, and it does so by using their internal names which are the same in 99% of cases.
## Post #188
- Username: wana7262
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 13, 2014 4:51 pm
- Post datetime: 2015-02-22T19:18:49+00:00
- Post Title: Re: Game import MAXScripts

asphalt 7 has .bdae files in it can't find .pig files..!!!
## Post #189
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-02-23T16:56:08+00:00
- Post Title: Re: Game import MAXScripts

Asphalt 7 uses a different version of the BDAE format which I'm not going to research.
## Post #190
- Username: kana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 08, 2011 7:54 pm
- Post datetime: 2015-03-08T10:50:03+00:00
- Post Title: Re: Game import MAXScripts

edit :
## Post #191
- Username: gpfan
- Rank: beginner
- Number of posts: 33
- Joined date: Sat Apr 02, 2011 2:59 am
- Post datetime: 2015-03-13T13:52:46+00:00
- Post Title: Re: Game import MAXScripts

Hi, AC script doesn't work with the new update 1.1 only on new dream pack models. Hope to see soon a fix for it. Just letting you know!
## Post #192
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-03-14T01:50:43+00:00
- Post Title: Re: Game import MAXScripts

Yep, it works on Cinderella Free Fall too, though the AI Tool can be a little flaky at times - it's either that the models appear a little squashed or UV maps looking horribly wrong if you rip another model after doing one.
## Post #193
- Username: pipistrello27
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 19, 2014 2:11 pm
- Post datetime: 2015-03-14T17:55:09+00:00
- Post Title: Re: Game import MAXScripts

Unfortunately it is not possible to extract models from AC dream pack 1.1, hope in an updating of the script the first possible.

Thanks.
## Post #194
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-03-17T11:39:55+00:00
- Post Title: Re: Game import MAXScripts

> Reply from pipistrello27
>
> Unfortunately it is not possible to extract models from AC dream pack 1.1, hope in an updating of the script the first possible.

Thanks.

What are you using the convert models? 3Dsimed can do that but yeah it have also the problem for last update/dlc ...
## Post #195
- Username: pipistrello27
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 19, 2014 2:11 pm
- Post datetime: 2015-03-18T05:02:39+00:00
- Post Title: Re: Game import MAXScripts

> Reply from KarinFutoGT
>
> pipistrello27 wrote:Unfortunately it is not possible to extract models from AC dream pack 1.1, hope in an updating of the script the first possible.

Thanks.

What are you using the convert models? 3Dsimed can do that but yeah it have also the problem for last update/dlc ...

----------------------

I use, with success, the script for max, and yes, I know, for the last update the problem it's the same beetween 3d simed and 3dsmax.

I wait the good news for solve it.
## Post #196
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2015-03-20T16:35:47+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from pipistrello27
>
> 
I use, with success, the script for max, and yes, I know, for the last update the problem it's the same beetween 3d simed and 3dsmax.

I wait the good news for solve it.

Chipicao has already been given some examples of the new Assetto corsa 1.1 KN5 files to look at. it is just a matter of if/when he gets chance to do something about it.
## Post #197
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-03-22T10:05:10+00:00
- Post Title: Re: Game import MAXScripts & tools

Chipicao, just noticed your milestone importer doesn't work for RIDE. Just got my hands on the Demo of RIDE. They still use .MIX to compress the files. Managed to extract contents with msmixext. Textures are fine. Models are the problem. The models might be using a newer format (?).

[](http://imgur.com/Ncz7cVB)

Here's the bike file : [http://www.mediafire.com/download/higl7 ... IKE303.rar](http://www.mediafire.com/download/higl7fkv7g7reg8/BIKE303.rar)
I didn't upload the textures files, because they're big in size (71 MB. 23 MB after compression). Probably because milestone promised to make the models look detailed. But if you need the texture files to fix the script, gimme a reply of this post, and i'll upload it for ya. Thanks in advance.
## Post #198
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2015-03-22T11:58:23+00:00
- Post Title: Re: Game import MAXScripts & tools

yes, error on line 97
## Post #199
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-03-23T08:52:34+00:00
- Post Title: Re: Game import MAXScripts & tools

Help extract this files:
[https://yadi.sk/d/-MhbEKHwfT3mV](https://yadi.sk/d/-MhbEKHwfT3mV)
Header - UnityRaw, but plugin to extract web unity3d not working. :\
## Post #200
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2015-03-24T14:17:28+00:00
- Post Title: Re: Game import MAXScripts & tools

all 3d models from Assetto Corsa and from Assetto Corsa Dream Pack #1 here  here [https://vk.com/topic-84830094_31137514?offset=40](https://vk.com/topic-84830094_31137514?offset=40)

Formats: max, obj, z3d.
includes high ploy lod and LOD_B
all skins in archives
All 3d parts detached
all textures in DDS includes
normal UV mapping
high poly cockpit includes


Alfa Romeo 4C 3D model 
[http://dfiles.ru/files/0qsck2n78](http://dfiles.ru/files/0qsck2n78)
Alfa Romeo 155 V6
[http://dfiles.ru/files/mxmvrtwf5](http://dfiles.ru/files/mxmvrtwf5)
Alfa Romeo GTA
[http://dfiles.ru/files/l75f4x5rs](http://dfiles.ru/files/l75f4x5rs)
Corvette C7R GTE
[http://dfiles.ru/files/lss1b70qk](http://dfiles.ru/files/lss1b70qk)
Mercedes 190 EVO2
[http://dfiles.ru/files/aqkcb32tz](http://dfiles.ru/files/aqkcb32tz)
McLaren F1 GTR
[http://dfiles.ru/files/gyqgt5kzi](http://dfiles.ru/files/gyqgt5kzi)
McLaren P1
[http://dfiles.ru/files/0k2k1lirp](http://dfiles.ru/files/0k2k1lirp)
BMW 235i Racing
[http://dfiles.ru/files/slcj0ol3k](http://dfiles.ru/files/slcj0ol3k)
Nissan GTR GT3
[http://dfiles.ru/files/s28ihel7y](http://dfiles.ru/files/s28ihel7y)
Mercedes C9
[http://dfiles.ru/files/1wmdm3n15](http://dfiles.ru/files/1wmdm3n15)
## Post #201
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2015-03-25T16:07:35+00:00
- Post Title: Re: Game import MAXScripts & tools

So somebody still has a way to export them...
## Post #202
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2015-03-25T16:57:43+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Nobby
>
> a way to export 3d simed + script assetto corsa
## Post #203
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-03-30T10:49:20+00:00
- Post Title: Re: Game import MAXScripts & tools

Full game of RIDE is out. No workaround for a script?
## Post #204
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2015-04-02T13:02:10+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from REDZOEU
>
> Full game of RIDE is out. No workaround for a script?
only dds files with bin (bin dont want to open with SMS script)
## Post #205
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-02T18:26:51+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from TolikGT
>
> 
only dds files with bin (bin dont want to open with SMS script)
The DDS files are hi res textures of the bike. I tried ripping with 3DRipperDX and Ninja Ripper (Intruder and D3D9 mode) and got no ripping result (ripped the 2015 R1 from loading).
I havent tried with D3D10 or 11 yet tho, but i can confirm it doesn't use DirectX 9.
We really need a script for this. Imagine all those riding gears, helmets, exhausts, and epicly detailed classic and modern superbikes and streetfighters. Awesomeness at is best.
## Post #206
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-04-05T10:32:20+00:00
- Post Title: Re: Game import MAXScripts & tools

hey, Chipicao. Can you make DriverSF Importer window smaller? I can't see bottom buttons.
## Post #207
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-05T16:51:32+00:00
- Post Title: Re: Game import MAXScripts & tools

+1 for the Ride script, it would be so helpful to get it. The content of this game is huge (more than 100 bikes, a lot of accessories, tracks, etc) and very well modeled.

Moreover, I think that if a script is created, it should be also working with MotoGP14 and the upcoming MotoGP15 and the bran new Sebastien Loeb Rallly Evo.

Thanks again Chipicao and all people involved in those great scripts!
## Post #208
- Username: mcboom2007
- Rank: n00b
- Number of posts: 14
- Joined date: Fri May 06, 2011 12:53 am
- Post datetime: 2015-04-09T10:30:18+00:00
- Post Title: Re: Game import MAXScripts & tools

+1 for the Ride script
## Post #209
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-09T12:40:27+00:00
- Post Title: Re: Game import MAXScripts & tools

And what about a new sms script that can rename pcars/test drive ferrari racing legends textures?
## Post #210
- Username: Wonderman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 20, 2014 6:41 am
- Post datetime: 2015-04-12T00:43:40+00:00
- Post Title: Re: Game import MAXScripts & tools

Chipicao, Ive used your Unity Import 3DSMAXScript 1.0Beta on a level# file from an iOS game, when imported it, i got the model, but only with one texture. thats one of my problems with this script, the other one is that when i import every level object, it imports all the objects as the Combined Mesh (root scene).43 file & looks like one huge mess.
can you or someone help me out?
## Post #211
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-04-15T18:26:56+00:00
- Post Title: Re: Game import MAXScripts & tools

Hey guys, sorry I ignored this thread but I really don't have much free time these days.
I will try to answer some of the issues.

- Assetto Corsa update
Since many people have requested it and it is an interesting game I will have a look and it's first on my list.

- RIDE
The Milestone script was made to work up to SBK Generations and WRC3, and being one of my early scripts there's a lot of guesswork going on.
In order to make it work with the new MotoGP and RIDE games I would have to completely overhaul it and re-do some of the research. For that unfortunately I don;t have time right now.

- pCars tracks, file renaming
I know I promised some time ago I'll have a look at tracks, but I never got to it. No promisses this time, it's not a priority for me.
As for renaming textures, there will never be such a script. I'll say it again: my script guesses some file names based on internal names, and 99% of the time they match. Textures don't have internal names so there's no way to do it.
You should bother aluigi about it to research filenames in the new BFF format 

@TolikGT I appreciate your work, as always. But please don't post links to such content here. It is against forum rules and I would have to have my topic closed because of it.

@Tosyk The window is resizable as far as I remember

@Wonderman that is an issue I've encountered as well with some games. I'm not sure weather it's a bug in my script or if those games use some methods to filter meshes. Sorry I can't help
## Post #212
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-04-15T18:49:59+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> @Tosyk The window is resizable as far as I rememberI wish, but it's not.
## Post #213
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2015-04-16T18:14:10+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> @TolikGT I appreciate your work, as always. But please do
ok, understood
## Post #214
- Username: Wonderman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 20, 2014 6:41 am
- Post datetime: 2015-04-16T21:35:44+00:00
- Post Title: Re: Game import MAXScripts & tools

alright, thanks.
but wait, which glitch? the Texture thing or the combined Mesh level thing?
## Post #215
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-04-22T06:39:48+00:00
- Post Title: Re: Game import MAXScripts & tools

I finally had some free time today and I looked into Assetto Corsa.
Please try the [updated script](http://www.mediafire.com/download/5tu326io08tc87l/Assetto_Corsa_Importer.zip) and let me know if there are any more issues.
[](http://www.imagebam.com/image/13407a405125648) 

@Wonderman textures could be anywhere. Unity files work by sharing resources between them, and if you have all of them in the right place my script should load shared resources from other files. Some games also store image assets in separate CAB files and load them by scripts.
What game is it exactly?
## Post #216
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-22T13:12:49+00:00
- Post Title: Re: Game import MAXScripts & tools

Thanks it works really good better than 3Dsimed and can import correctly the drive mesh with his gloves/hands etc..
## Post #217
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-04-23T22:30:56+00:00
- Post Title: Re: Game import MAXScripts & tools

Updated [M3G2FBX](http://www.mediafire.com/download/5b5gfesy459i4cg/M3G2FBX.zip) to work with latest version of Real Racing 3. Thanks to Barti for pointing out the change!

[](http://www.imagebam.com/image/1b9338405497549) 

Btw, the STILL haven't released NFS No Limits in the US app store??
## Post #218
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-24T03:00:38+00:00
- Post Title: Re: Game import MAXScripts & tools

Chipicao, are you still busy? We're still waiting for an update to milestone importer to import RIDE motorcycles :\
## Post #219
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-04-26T13:13:55+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> 
@TolikGT I appreciate your work, as always. But please don't post links to such content here. It is against forum rules and I would have to have my topic closed because of it.
@TolikGT, did you understand?
## Post #220
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2015-04-26T19:41:39+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Automotive Gaming
>
> Chipicao wrote:
@TolikGT I appreciate your work, as always. But please don't post links to such content here. It is against forum rules and I would have to have my topic closed because of it.
@TolikGT, did you understand?
understood, sry, link deleted
## Post #221
- Username: Wonderman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 20, 2014 6:41 am
- Post datetime: 2015-05-02T15:08:49+00:00
- Post Title: Re: Game import MAXScripts & tools

@Chipaco 1. Its not the texture mapping thats the problem, i can get around that, that is, if the assets within the level# files worked correctly, heres what i mean: [https://www.youtube.com/watch?v=w5Jz27EEf3w](https://www.youtube.com/watch?v=w5Jz27EEf3w) hope you (or someone) can help me out.

2. Dont laugh, but the game is Calling All Mixels for the iOS, someone requested me to rip from it, but ive never played this game, so ripping from this game is a pain in the ass for me.

3. i didnt see any .CAB files in the .ipa app, where are they usually?
## Post #222
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2015-05-04T23:52:36+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> Released Unity Assets Importer 0.8.9 with Unity 4.5.0 compatibility, a few bugfixes and general code optimization. The script is not encrypted anymore, you can view the full code if you're interested.

Also releasing a new script called Unity Importer 1.0 beta. It has more or less the same functionality but its entire interface is built in .NET, allowing me to integrate a TreeView of the actual asset hierarchy. This gives you extended filtering options so that you can import only the objects you need.

I will continue to update both scripts for a while, but at some point the old script will be retired.

Old vs. New:
useing 3dsmax8 the script is not working at all! please help!
do I need a diffent version of 3dsmax?
does it work with a version that works with windows xp 32 bit?
## Post #223
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-05-06T17:19:18+00:00
- Post Title: Re: Game import MAXScripts & tools

I'm releasing a new tool: [kn5 converter](http://www.mediafire.com/download/i8xoax1ddjif2rx/kn5_converter.zip)
Supports all Assetto Corsa models (cars, tracks...) from Early builds to 1.1 final.

Usage: kn5conv.exe [-fbx|-obj|-objZMhack] [input_file/folder]
More info in the readme

- FBX supports almost all model features, except specific shader settings or textures (ex. dirt, damage).
  In case of multi-layer diffuse textures, the second (txDetail) map is used as diffuse, and the first is used as specular since it's usually a grayscale map.
  A complete list of material properties is included for reference as user-defined settings
- OBJ does not support hierarchy, transformations or UV tiling. Therefore, these are "baked" into the model so at least it looks good.
- OBJ ZMhack takes advantage of a bug (or feature?) in ZModeler2 that creates usable hierarchy from OBJ models
  I won't go into detail, it just works even if it's not supposed to  Small boxes are created instead of dummies which you can convert and use to set pivot positions.

[](http://www.imagebam.com/image/447fbe408033747) [](http://www.imagebam.com/image/a0d220408033873) [](http://www.imagebam.com/image/49cbc0408033964) 


@REDZOEU I will try to have another look at milestone recent games. But I can't promise anything, and even if I make something it could take some time.

@Wonderman Can you send me the game files via PM? I can't find the free version anywhere 

@Starlow My scripts are generally compatible with max 2010 and up.
## Post #224
- Username: Wonderman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 20, 2014 6:41 am
- Post datetime: 2015-05-06T18:06:06+00:00
- Post Title: Re: Game import MAXScripts & tools

@Chipaco [http://www.mediafire.com/download/uubk7 ... 0-weip.ipa](http://www.mediafire.com/download/uubk7czcm3sap2k/Mixels-3.0.0-weip.ipa) i reuploaded it onto mediafire
## Post #225
- Username: SandroX
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Apr 20, 2010 3:43 am
- Post datetime: 2015-05-07T18:06:39+00:00
- Post Title: Re: Game import MAXScripts & tools

Chipicao, will you update SMS Importer v3.0 script? Can't import tracks and materials.
## Post #226
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2015-05-08T02:03:49+00:00
- Post Title: Re: Game import MAXScripts & tools

Hey Chipicao.

Just wanted to report. both the new version of the kn5 importer and the kn5 converter work perfectly. 
Thank you so much for looking into the importer update. The converter was just an added bonus.
I hope the sample file i provided helped in some way.

Again. Thank you so much, i am a very happy man again  

And here is that internet cookie i promised you ...
## Post #227
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-05-09T15:50:17+00:00
- Post Title: Re: Game import MAXScripts & tools

@SandroX I will not touch SMS Import until we have a solution to extract BFF archives with correct filenames and paths.

@Nobby My pleasure

@Wonderman It's exactly as I stated before, sometimes a single object is linked to a bigger mesh. IDK if and how the game would separate the mesh, but this is how the assets are stored.
In your video, the script says it imports "Combined Mesh (root: scene)" because that's the actual name of the mesh object.
To clarify, "antenna_b" is a GameObject (think of it as a scene node or dummy) linked to a Mesh called "Combined Mesh (root: scene)".
## Post #228
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-05-09T17:49:00+00:00
- Post Title: Re: Game import MAXScripts & tools

Sorry for being annoying again, just wanted to ask about RIDE. Someone made a thread for getting models from the .BIN files, but the method is absolutely not noob-friendly ([viewtopic.php?f=16&t=12791](http://forum.xentax.com/viewtopic.php?f=16&t=12791)). Is the maxscript for this game far to be finished? It would be great if the old SBK/MotoGP maxscript for milestone games gets updated to import bikes from RIDE (including the accesories and stuff).
Again, sorry for being annoying. I tried ripping with Ninja Ripper and 3DRipperDX and got no luck, and got depressed because of that.

Thanks in advance
## Post #229
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2015-05-13T23:07:25+00:00
- Post Title: Re: Game import MAXScripts & tools

News for Asphalt Overdrive? (.PIG files)
## Post #230
- Username: DragonSlayer765
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 24, 2015 5:20 pm
- Post datetime: 2015-06-24T10:47:26+00:00
- Post Title: Re: Game import MAXScripts & tools

Gla2 files are spitting out errors with the latest gameloft gla extractor but im running on a virtual machine so I don't know what to think.. Basically I want some models from Modern Combat 5. Is a remodel worth the time or is ripping it achievable??
## Post #231
- Username: runsrr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 01, 2015 7:44 am
- Post datetime: 2015-07-01T00:01:41+00:00
- Post Title: Re: Game import MAXScripts & tools

Has Unity Importer 1.0 beta support Unity 5 yet?
when will this support unity 5?
## Post #232
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-07-03T18:38:44+00:00
- Post Title: Re: Game import MAXScripts & tools

it seems the Alchemy Dialog scripts (which is usually known to import the IGB files like from Marvel Ultimate Alliance (n-space for the second one) & X-Men Legends series) needs an update, such able to convert PSP, Wii, PS3 & Xbox 360 version of the models, in order to be able to use it on the current Max, instead of just in 4.2/5. & BTW, it's on marvelmods for the info like this
## Post #233
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-07-05T18:19:25+00:00
- Post Title: Re: Game import MAXScripts & tools

Cartoon Network Racing on PS2 was made by Eutechnix and uses the same format as the NASCAR games, but nothing imports. Here's a few samples:
[http://puu.sh/iO8sT.zip](http://puu.sh/iO8sT.zip)
## Post #234
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-07-15T00:17:23+00:00
- Post Title: Re: Game import MAXScripts & tools

Will the UAI ever support Bones/Weights?
At the moment it ignores Bones or imports them as Dummies with hierarchy.
unless it depends of the Format and version of Unity?

Here is a picture of what i have ATM the Version of the File says "4.6.5p4"
## Post #235
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-07-15T12:28:37+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Arymond
>
> Will the UAI ever support Bones/Weights?
At the moment it ignores Bones or imports them as Dummies with hierarchy.
unless it depends of the Format and version of Unity?

Here is a picture of what i have ATM the Version of the File says "4.6.5p4"

Kamen Rider Drive Type Formula? Where that come from? Which game is this model from?
## Post #236
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-07-15T16:15:05+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from LarsMasters
>
> Arymond wrote:Will the UAI ever support Bones/Weights?
At the moment it ignores Bones or imports them as Dummies with hierarchy.
unless it depends of the Format and version of Unity?

Here is a picture of what i have ATM the Version of the File says "4.6.5p4"



Kamen Rider Drive Type Formula? Where that come from? Which game is this model from?

Kamen Rider Storm Heroes, Android/IOS
## Post #237
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2015-07-25T14:58:51+00:00
- Post Title: Re: Game import MAXScripts & tools

How do I import animations and bones from levels\assets files? with unity importer\unity asset importer 3dsmax Script?
## Post #238
- Username: goreface13
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 10, 2014 4:26 pm
- Post datetime: 2015-08-07T13:22:14+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Arymond
>
> Will the UAI ever support Bones/Weights?
At the moment it ignores Bones or imports them as Dummies with hierarchy.
unless it depends of the Format and version of Unity?

Here is a picture of what i have ATM the Version of the File says "4.6.5p4"

how about the textures ?  low res ?
## Post #239
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-08-14T06:23:50+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from goreface13
>
> Arymond wrote:Will the UAI ever support Bones/Weights?
At the moment it ignores Bones or imports them as Dummies with hierarchy.
unless it depends of the Format and version of Unity?

Here is a picture of what i have ATM the Version of the File says "4.6.5p4"

-Image Removed because Big-

how about the textures ?  low res ?

yeah the UV's are Merged in to one Low end Texture Set.
## Post #240
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-08-15T06:35:53+00:00
- Post Title: Re: Game import MAXScripts & tools

hey, Chipicao

can you look into this files:
[https://yadi.sk/d/MTuaQqgchtThN](https://yadi.sk/d/MTuaQqgchtThN)

it's from The Man from U.N.C.L.E. - Mission: Berlin unity game. Some textures wont load with any importer however meshes loads very well.

[http://androidlife.ru/games/3640-the-ma ... piony.html](http://androidlife.ru/games/3640-the-man-from-uncle-mission-berlin-novye-shpiony.html)

here's online version of the game:
[http://9fish.ru/unity3d/3d-shooting/the ... c-l-e.html](http://9fish.ru/unity3d/3d-shooting/the-man-from-u-n-c-l-e.html)
## Post #241
- Username: oqee
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 12, 2014 4:49 am
- Post datetime: 2015-08-18T04:48:39+00:00
- Post Title: Re: Game import MAXScripts & tools

Hello! i'have problem to open this file/ help extract 3d [https://yadi.sk/d/IvUL0cnUiLrn3](https://yadi.sk/d/IvUL0cnUiLrn3)
BMW Augmented from Germany App Store
## Post #242
- Username: legende973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 24, 2015 8:28 pm
- Post datetime: 2015-08-24T12:33:14+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi,

Fisrt ! thanks a lot for this community.   

Now....   I try to install the sms importer on 3d max 2014 , Did it work on it please because i can't arrive ; i follow thr read me , but i don't see where i have to put the Sms importer file.

I use the v3.1c

Thanks you a lot
## Post #243
- Username: legende973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 24, 2015 8:28 pm
- Post datetime: 2015-08-25T21:29:44+00:00
- Post Title: Re: Game import MAXScripts & tools

hello
## Post #244
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-08-26T22:33:36+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from legende973
>
> hello

> Reply from Chipicao
>
> My MAXScripts are meant to run on max 2010 and up. Sorry, but max 2009 has less/different maxscript features and some of the functions won't work.
How to install scripts in 3ds Max:
1. Drag&drop mcr or mzp files in one of the viewports - this will initialize&install the script
2. Click on Customize -> "Customize User Interface" and switch over to the Toolbars tab; optionally select "Game file import" in Category, which is what I assign to all my scripts
3. Drag&drop the script from the list onto your toolbar; this will create a button that you can use from there on to run the script
## Post #245
- Username: legende973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 24, 2015 8:28 pm
- Post datetime: 2015-08-26T22:49:57+00:00
- Post Title: Re: Game import MAXScripts & tools

sorry im french and google traduction dont help me here ....  so put the mzp in the viewport hmm i don't know where he is in french...  but thanks for answer
## Post #246
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-08-27T09:46:31+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from legende973
>
> sorry im french and google traduction dont help me here ....  so put the mzp in the viewport hmm i don't know where he is in french...  but thanks for answer
Viewport it's main interface windows of 3dsmax, where it draws all 3d information 
So, you need to drag'n'drop mzp-file close to center of 3dsmax window, it's thinking for sec, and you can go to interface setup and find new buttons here to drag'n'drop to max tool panels.

1. [](http://fastpic.ru/view/70/2015/0827/2010062624d8f2a11a82f3f93c5df566.png.html)
(visually nothing happens, just small cursor change to "thinking")
2. [](http://fastpic.ru/view/72/2015/0827/9b9d0ffab83b701c1902d5ae960d20fa.png.html)
## Post #247
- Username: legende973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 24, 2015 8:28 pm
- Post datetime: 2015-08-27T20:12:45+00:00
- Post Title: Re: Game import MAXScripts & tools

i follow exactly what you show me snif , and in category i dont have game file importer  sniff ....

so i cant add the sms importer toolbar   


thank you a lot for your picture , really appreciating ,
## Post #248
- Username: legende973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 24, 2015 8:28 pm
- Post datetime: 2015-08-28T22:49:41+00:00
- Post Title: Re: Game import MAXScripts & tools

I finaly found it , i have to work 3D max in administrator pfff.... thanks to you !
## Post #249
- Username: MikeYedi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 06, 2015 8:04 pm
- Post datetime: 2015-09-06T12:12:48+00:00
- Post Title: Re: Game import MAXScripts & tools

need Help modding asphalt 8 textures I have the windows 8 version of asphalt 8 I found the tga files they were located in a bin file but cannot open them for the life of me plz help here are the tga files I got from the car textures bin archive 
[http://www.filedropper.com/newwinrarziparchive_1](http://www.filedropper.com/newwinrarziparchive_1)
## Post #250
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-09-07T03:12:02+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from MikeYedi
>
> need Help modding asphalt 8 textures I have the windows 8 version of asphalt 8 I found the tga files they were located in a bin file but cannot open them for the life of me plz help here are the tga files I got from the car textures bin archive 
http://www.filedropper.com/newwinrarziparchive_1
From first post in this topic:

> Reply from Chipicao
>
> Gameloft Pig Importer - Deprecated; use PIG2FBX instead
Supports cars, tracks, characters and pretty much any game model.
Most textures are in PVR format, but their extension is from the source image (TGA, PSD). The script will rename them but make sure you have the PVR plugin installed.

Works only with Asphalt 1.5 or older and Minion Rush.
Newer versions of Asphalt8 use lz4 compressed buffers and textures. Decompression is impossible with MAXScript, so I've created a standalone command-line tool that will convert models to FBX.
Download PIG2FBX here
## Post #251
- Username: MikeYedi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 06, 2015 8:04 pm
- Post datetime: 2015-09-08T05:01:36+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Andrakann
>
> MikeYedi wrote:need Help modding asphalt 8 textures I have the windows 8 version of asphalt 8 I found the tga files they were located in a bin file but cannot open them for the life of me plz help here are the tga files I got from the car textures bin archive 
http://www.filedropper.com/newwinrarziparchive_1
From first post in this topic:
Chipicao wrote:Gameloft Pig Importer - Deprecated; use PIG2FBX instead
Supports cars, tracks, characters and pretty much any game model.
Most textures are in PVR format, but their extension is from the source image (TGA, PSD). The script will rename them but make sure you have the PVR plugin installed.

Works only with Asphalt 1.5 or older and Minion Rush.
Newer versions of Asphalt8 use lz4 compressed buffers and textures. Decompression is impossible with MAXScript, so I've created a standalone command-line tool that will convert models to FBX.
Download PIG2FBX here
Its crashes every time also do you know if you will get banned for mods such as this?
[Capture.PNG](https://xentaxbackup.github.io/file/9699_Capture.PNG)
## Post #252
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-09-08T06:19:38+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from MikeYedi
>
> Its crashes every time also do you know if you will get banned for mods such as this?
You need to convert PIG file, and tool automatically converts all related textures into .PVR.
Also .Net Framework 3.5 is required.
I'm not care about bans, because I not a modder 
I just collect models.
## Post #253
- Username: muskieratboi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 01, 2012 5:35 pm
- Post datetime: 2015-09-22T09:42:31+00:00
- Post Title: Re: Game import MAXScripts & tools

Been examining this. trying to get the files from Order and Chaos Online 2. Managed to get the .BDAEs out, but the max Script doesn't work on it. What's the rules on posting a sample?
## Post #254
- Username: vladikkgg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 01, 2011 8:44 pm
- Post datetime: 2015-10-30T18:30:42+00:00
- Post Title: Re: Game import MAXScripts & tools

What about Unity Importer for apps 5.1.3f.1 or hi?
## Post #255
- Username: varetyr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 04, 2015 4:12 pm
- Post datetime: 2015-11-04T08:14:40+00:00
- Post Title: Re: Game import MAXScripts & tools

I would like to know if there is anybody working into The Crew model exporter, to make the meshes have texture info(UV Maps).
If there is someone, can you please update me if there is going to be a new release of the tool with updated exporting?

Thank You very much!
## Post #256
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2015-11-15T21:15:37+00:00
- Post Title: Re: Game import MAXScripts & tools

Chipicao you can help me?

still working but have a blackout in my house
turn on my computer again and only show this error


Yess i try to Reinstall a script, anothers scripts works fine
## Post #257
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2015-12-21T15:05:48+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi! In PIG2FBX. Is posible add support to gods of rome?
[https://itunes.apple.com/us/app/gods-of ... 33772?mt=8](https://itunes.apple.com/us/app/gods-of-rome/id680733772?mt=8)
## Post #258
- Username: zDark11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 02, 2016 5:20 pm
- Post datetime: 2016-03-02T10:40:58+00:00
- Post Title: Re: Game import MAXScripts & tools

Error please Helpme form Unity Importer.
## Post #259
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2016-03-20T02:18:38+00:00
- Post Title: Re: Game import MAXScripts & tools

@Chipicao, Hi.  

Was wondering, will it be possible for the SMS to be updated to fully import pCars vehicles the way it does with NFSShift 1&2?  
Or you need first nfsshift.bms to be updated by aluigi to extract them fully with names and all in order for a successful import in 3ds max?  
Bought the game last night, and wanted to mess a bit with the models, but unfortunately can not be imported with in 3dsMax.  

Also, any chance for an updated PIG2FBX because it will not work on newly updated Asphalt 8 game and car additions.
Always gets the following "Unhandled Exception: OutOfMemoryException."

Thank you.
Cheers.
## Post #260
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2016-04-13T02:43:23+00:00
- Post Title: Re: Game import MAXScripts & tools

yes, i install the PVR Tex Tool, update my Runtime library, and not work

later of this error, the script stop to work

any help?

--------------------------------------------------------------------------------------------

I Can solve that

Just install C++ 2005

---------------------------------------------------------------------------------------------

another question

i try to open Nitro Nation Files
but, i unpack the OBB file and have more than 4.500 Files without extension
have any way to extract them? your unity pluguin don't open it
## Post #261
- Username: Sc4recroW1687
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 16, 2016 3:20 am
- Post datetime: 2016-04-15T19:59:44+00:00
- Post Title: Re: Game import MAXScripts & tools

I was wondering if you could take a look at this script, it wasn't made by me and the creator said they were too busy to finish it, so I was wondering if you could take a crack at finishing it. As of now the script only imports around 80% of the mesh from the AMO files, in every character it imports all of the mesh but the top half of the head and the hands, it doesn't import the textures ( AMT files) but I'm okay with that. I've been wanting the models from DragonBall Z Budokai 3 for a while now, so I can make them into Garry's Mod Playermodels, but none of the models have been ported yet, even though this game has been out for years. I find this quite strange though considering the fact that just about every character model from DragonBall Z Budokai Tenkaichi 3 has been ripped. The maxscript -> [http://www.mediafire.com/download/j6069 ... udokai3.ms](http://www.mediafire.com/download/j60696zs4p1dri2/budokai3.ms) also here's a link to an example AMO and AMT file -> [http://www.mediafire.com/download/ccqt8 ... Vegeta.zip](http://www.mediafire.com/download/ccqt8hs8kddf4s2/Vegeta.zip)
## Post #262
- Username: cjs007
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 23, 2016 2:00 pm
- Post datetime: 2016-05-15T15:33:50+00:00
- Post Title: Re: Game import MAXScripts & tools

is the unity assets importer updated for unity 5?
## Post #263
- Username: RSJ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 15, 2016 12:38 am
- Post datetime: 2016-06-14T17:22:21+00:00
- Post Title: Re: Game import MAXScripts & tools

warning - this is my first post here and i'm a complete noob   

i came across this site when i was looking at the Porsche configurator and wondered if i could somehow extract the model from the Unity web viewer.

i saw in the first post to this long thread that Chipicao has done exactly this and has the models showing in Max.  i've downloaded the Unity Importer 1.0 beta8 and have also downloaded, installed and run URLSnooper2 as indicated.

however nothing seems to be working for me...

1. Snooper isn't snooping anything at all and i have used the tool exactly as specified.  there are no Porsche URLs or that many URLs at all and i have many tabs open.
2. i've managed to find some URLs in Firefox itself (see attachment), but not nothing happens when i copy to the address bar.
3. even if i do eventually manage to download and rip, i don't have Max (i use Blender instead).  my understanding is that there are some other apps available that can extract the models without having to use Max?

can anyone help me with this?



porscheconfig01.png (155.57 KiB) Viewed 341 times
## Post #264
- Username: RSJ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 15, 2016 12:38 am
- Post datetime: 2016-06-16T06:42:29+00:00
- Post Title: Re: Game import MAXScripts & tools

update:

i've managed to get all the meshes i needed downloaded and extracted.  i've imported them into Blender, and they come in great except for one thing - the coordinates of a many meshes are slightly off, so for example a seat may be made from 50 objects and they're all slightly misaligned or maybe the backrest is about 1m away from the rest of the seat.

i used Disunity to extract the meshes - is this likely to be a Disunity error or is something else going on?



seat01.png (94.77 KiB) Viewed 315 times
## Post #265
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2016-07-02T07:08:57+00:00
- Post Title: Re: Game import MAXScripts & tools

Hmm, for some reason I couldn't find some of the assets for Temple Run Oz, namely Oz himself and China Girl, using Unity Importer. The only other meshes that turn up are Finley the monkey and the baboons. :/
## Post #266
- Username: nicociri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 08, 2016 1:44 am
- Post datetime: 2016-07-10T20:00:49+00:00
- Post Title: Re: Game import MAXScripts & tools

I am being unable to import Gameloft's Magic Kingdom BDAE files into max 2011 using the importer.

I get a "Incompatible Types 62 and undefined".

Had no troubles finding the data in android version. They put it in the data folder, in files named "*.DLC" (just zip files).

Inside those DLC you find the BDAE and the tga textures.

The DLC is 40mb big so i've uploaded to dropbox
[https://www.dropbox.com/s/0z4wqchk4ronz ... 5.zip?dl=0](https://www.dropbox.com/s/0z4wqchk4ronzzr/CoreAssets_Model_0_Pack_15.zip?dl=0)

i'm guessing it's a new format? o more likely, i'm doing something wrong... either case, any help would be appreciated...
## Post #267
- Username: nicociri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 08, 2016 1:44 am
- Post datetime: 2016-07-12T03:41:29+00:00
- Post Title: Re: Game import MAXScripts & tools

I don't know maxscript but i can read code and try to understand. this is the error im getting

-- Error occurred in t loop; filename: C:\Users\pendragon\AppData\Local\Autodesk\3dsMax\2011 - 32bit\enu\UI\usermacros\Game file import-GTRacing2BDAEImporter.mcr; position: 17046; line: 471
--  Frame:
--   texFolders: undefined
--   searchTexFile: undefined
--   texName: undefined
--   texFile: undefined
--   pvrFile: undefined
--   texFilename: undefined
--   t: 1
--   foundTexture: undefined

and that t loop is:

for t=1 to textureCount do
		(
			texFilename = readStrAtOffset binstr (BDAEoffset + (readLong binstr #unsigned))
			texName = readStrAtOffset binstr (BDAEoffset + (readLong binstr #unsigned))
			texFilename = readStrAtOffset binstr (BDAEoffset + (readLong binstr #unsigned))
			texArr[t] =  BitmapTexture name:texName
blahblah it goes...

so, it has to do with textures?
Then, texfilename is undefined, so it means that assignation failed. It cannot be BDAEoffset, because it is used before the t loop and there were no errors there. So the readstratoffset is failing at the position indicated by BDAEoffset... why?
If i input a textures folders, BDAEoffset is 62 and the error i get is incompatible types:62
if i DON'T inputo a texture folder, BDAEoffset is 0, and the error i get is incompatible types 0

so i'm guessing a numeric value is not what readStratOffset expects?

edit:
on the contrary: readstratoffset expects a binstream (the file) and an integer.
BUT
>> getvar binstr
<BinStream:D:\fml.DLC\CoreAssets_Model_0_Pack_15\mainstreet_buildings.bdae>

and a readlong binstr #unsigned is throwing an undefined.... thats where 62 and undefined comes from, 62 BDAEoffset and undefined this readlong.

what i can't seem to understand yet is what is the script trying to acomplish with this....
## Post #268
- Username: aowzone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 19, 2016 3:11 am
- Post datetime: 2016-08-18T19:13:11+00:00
- Post Title: Re: Game import MAXScripts & tools

Getting an error with track import in SMS Importer and Max 2014 x64. 

```
--No ""findstring"" function for undefined
```


The MaxScript window shows it crashing on line 1251, which is in this code block.

```
		(
			NODEtype = getSTR filestr OBJoff
			NODEname = getSTR filestr (OBJoff + 4)
			mebpath = getSTR filestr (OBJoff + 8)
			
			lng5 = readlong filestr #unsigned
			sphereOffset = [readfloat filestr, readfloat filestr, readfloat filestr]
			sphereRadius = readfloat filestr
			MatrixNumber = readlong filestr #unsigned
			userflags = readlong filestr #unsigned
			lng8 = readlong filestr #unsigned
			
			dataoff = findstring mebpath "_data"
			if dataoff == undefined then mebfile = modelPath + (filenameFromPath mebpath)
			else mebfile = sharedTrackObj + (substring mebpath (dataoff + 5) (mebpath.count - dataoff - 4))
				
			if (LODtest (filenameFromPath mebpath)) == true do importPart mebfile OBJpos OBJorient OBJscale
		)
	)


```


Sometimes, I also am getting 
```
-- Unable to convert: undefined to type: Integer64
```
 depending on which sgb I am loading.  This happens at line 1202.

```
fseek filestr STRpos #seek_set
```
## Post #269
- Username: lukamas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 07, 2015 3:12 am
- Post datetime: 2016-09-19T19:03:07+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi, I was wondering, Is there a way I can import Far Cry 4 animations?
## Post #270
- Username: aowzone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 19, 2016 3:11 am
- Post datetime: 2016-10-03T20:23:34+00:00
- Post Title: Re: Game import MAXScripts & tools

Any plans for support of NASCAR Heat Evolution?  It's Unity, and we have a process in place to import created skins but I'm working to get the models out so I can create new shadow maps for blank car templates.
## Post #271
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2016-12-13T01:35:44+00:00
- Post Title: Re: Game import MAXScripts & tools

hi is Chipi here ? wondering if we can have a updated milestone importer for Sebastien Loeb Evo Rally? the .mix format changed slightly, and from the new game, textures ARE THE ONLY THING i am able to extract, even with the use of Aluigi MSMIXEXT tool, no joy, hope you can help .. (would i need to make a donation to speed this up? id be happy to) 

love n respect for Chipicao
## Post #272
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2016-12-25T15:36:06+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> 
Eutechnix Model Importer
Model importer for Nascar 2013 and '14 PC games. Partial support for Auto Club Revolution.

Textures have to be extracted first using this script: viewtopic.php?f=18&t=11326
In some cases you will have to set tiling factors manually (eg. carbon fiber, track grass or asphalt).

You'll need aluigi's nascar2011.bms script to extract *.AR archives and then you can import *.ARC files.
Merry Christmas and much thanks to Chipicao for his incredible works!

I just wonder is there any chance to import tracks from Auto Club Revolution in 3dsmax? How can that script be corrected to work that way?

That game is closed now so we have no other chance to extract some nice props models from the tracks... 
May be Chipicao knows how we can handle it?

Thx a lot anyway!
## Post #273
- Username: ManuJDT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 08, 2017 11:47 pm
- Post datetime: 2017-02-08T22:51:02+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi guys. Anything new to the Milestone importer? MotoGP/Ride/Ride2?
## Post #274
- Username: javanesse
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 13, 2017 1:45 am
- Post datetime: 2017-02-12T17:49:22+00:00
- Post Title: Re: Game import MAXScripts & tools

hy, i really appreciated for your scripts. thank you so much.

recently, i was trying to import milestone model but i've got this message.

FYI: im using 3ds max ver 2017

what should i do?

thank you again.
[2017-02-13 02_47_20-Untitled - Autodesk 3ds Max 2017.png](https://xentaxbackup.github.io/file/12436_2017-02-13 02_47_20-Untitled - Autodesk 3ds Max 2017.png)
## Post #275
- Username: nm69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 03, 2010 5:12 pm
- Post datetime: 2017-02-28T17:06:41+00:00
- Post Title: Re: Game import MAXScripts & tools

I don't think Chipi has been around the forum in a while.  Can anyone with some max script experience fix the above problem? I too am running the same error with Ride 2 and Milestone import script in max.    No "">"" function for undefined    error at line 88 and 509. 

I'm on Max 2015 btw
## Post #276
- Username: chrisu12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 09, 2017 8:09 pm
- Post datetime: 2017-07-13T05:00:23+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> 
I3D Importer v1.2
Model importer for Farming simulator (tested with 2012 and 2013). Supports vehicles and characters (drivers, peds, cows, chickens )

Wanted times to ask whether who can expand this importer.
I need the skinbindenodes still.
Since it is unfortunately not the animation etc. with imported.
Would be really cool if it could make one, the I3D I can provide you to test.



Regards
Chrisu

Wollte mal fragen ob wer diesen Importer erweitern kann .
Ich bräuchte die skinbindenodes noch.
Da es leider nicht die Animation usw mit importiert.
Wäre echt cool wenn es einer machen könnte , die I3D kann ich euch bereit stellen zum testen.



MfG
Chrisu
## Post #277
- Username: rina9455
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 13, 2017 6:50 am
- Post datetime: 2017-07-19T20:34:13+00:00
- Post Title: Re: Game import MAXScripts & tools

I was wondering if there is any possible way to get something similar to the 3DS Max Eutechnix Model Importer that works for NASCAR /13/14/15 on the NASCAR Heat Evolution game?  As far as I can tell, once it's upacked NHE's contents are in the same exact style as the previous Eutechnyx games except they've changed the file extension from ARC to RAB/SAB.  Currently I can get the textures via the Unity Assets Bundle/Extractor, but the 3D content is a complete mess trying to export it from that program (and I've tried a lot of different methods for it).  I would even be willing to negotiate a price for such a tool.
## Post #278
- Username: chrisu12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 09, 2017 8:09 pm
- Post datetime: 2017-07-24T15:48:30+00:00
- Post Title: Re: Game import MAXScripts & tools

hi @all


Oh, I could also put an i3d of the fs17 to the test.
Where the shape and animation in the i3d stands.

Regards
Chrisu


Ach ja , ich könnte auch eine i3d vom fs17 zur verfügung stellen zum testen.
Da wo die shape und animation in der i3d steht.

MfG
Chrisu
## Post #279
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2017-08-01T10:01:30+00:00
- Post Title: Re: Game import MAXScripts & tools

about sbaBrute, can someone make support for .sb file? I really need to extract fonts.
## Post #280
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2017-08-04T03:55:50+00:00
- Post Title: Re: Game import MAXScripts & tools

Can somebody import Land Rover Velar
[https://itunes.apple.com/es/app/land-ro ... ?l=en&mt=8](https://itunes.apple.com/es/app/land-rover-range-rover-velar/id1233619891?l=en&mt=8)
## Post #281
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-08-05T11:21:40+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from TolikGT
>
> Can somebody import Land Rover Velar
Imported Data folder without any issues in Unity Studio v0.7.0 x64. Level 14 and 16 contains this model.
## Post #282
- Username: k1995
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 09, 2016 3:30 pm
- Post datetime: 2017-09-24T15:04:03+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Arymond
>
> Will the UAI ever support Bones/Weights?
At the moment it ignores Bones or imports them as Dummies with hierarchy.
unless it depends of the Format and version of Unity?

Here is a picture of what i have ATM the Version of the File says "4.6.5p4"
My God, how did you import it? He's really beautiful! Can you tell me? I find that I can't read in any form
## Post #283
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-10-11T13:57:06+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> Unity Assets Importer v0.8.9
This is one of the biggest projects I've tackled, and it's till being updated as new Unity versions are launched.

Unity Importer 1.0 beta
It has more or less the same functionality but its entire interface is built in .NET, allowing me to integrate a TreeView of the actual asset hierarchy. This gives you extended filtering options so that you can import only the objects you need.

I will continue to update both scripts for a while, but at some point the old script will be retired.

The scripts are compatible with Web, PC, iOS, Android, PS3, Xbox 360, OSX and Linux games built with Unity 2, 3 and 4 (up to 4.3.2f1). It doesn't work with games created with Unity versions older than 2.5.0, which I believe were iOS-exclusive and lack some elements of identification.

There are a lot of Unity games out there. To name a few interesting examples:
Porsche model showcase - click the 3D button - screenshot gallery
Direct links to [Porsche models for 2015, 2016, 2017, 2018, 2019 and 2020 years](http://www.mediafire.com/file/s42sewj8hzoeb4h/Links4AllPorscheModels_2018-12-20.zip/file).
Can be downloaded with Download Master or other downloader able to handle links lists.
Unity Web Player is unsupported by most browsers now, so Showcase can be closed or remastered - it's better to hurry up.
## Post #284
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-10-25T06:40:32+00:00
- Post Title: Re: Game import MAXScripts & tools

Link above updated, added 3 "new" models:
2018 Porsche 718 Boxster GTS (98234)
2018 Porsche 718 Cayman GTS (98214)
2018 Porsche 911 Carrera T (99115)
## Post #285
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-13T01:14:36+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Andrakann
>
> Link above updated,
Really neat to have them all in one place, thank you.
Got them all @10.6GB of .unity3d files.
Except some files that are no longer available from them and shows 404 error, you happen o have them as well?
Those that are missing are mostly from visualDefinitionMega and from year 2018 even more are missing and shows 404 error, between 1 to 10 files per car.
Lets say we want this model Porsche 911 GT2 RS
A total of 76 files are downloaded,
And missing files for it are:
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Ext_Headlamps_Basis_PDLS.unity3d
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Acc_489_StrWHeating.unity3d
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Acc_541_AirConditioning_SeatVentilation.unity3d"
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_CeCo_Buttons_176_474_LifeSystem.unity3d
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_CeCo_Buttons_176_SportsExhaustSystem.unity3d
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_CeCo_Buttons_CarreraS_639_640_SportChrono.unity3d
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Gearshift_250_PDK_EE_Decor.unity3d
-http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Seats_P06_P07_Memory.unity3d

You have them all?
## Post #286
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-11-13T11:56:11+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from mono24
>
> Really neat to have them all in one place, thank you.
You are welcome 

> Got them all @10.6GB of .unity3d files.
>
> Except some files that are no longer available from them and shows 404 error, you happen o have them as well?
>
> Those that are missing are mostly from visualDefinitionMega and from year 2018 even more are missing and shows 404 error, between 1 to 10 files per car.
>
> Lets say we want this model Porsche 911 GT2 RS
>
> A total of 76 files are downloaded,
>
> And missing files for it are:
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Ext_Headlamps_Basis_PDLS.unity3d
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Acc_489_StrWHeating.unity3d
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Acc_541_AirConditioning_SeatVentilation.unity3d"
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_CeCo_Buttons_176_474_LifeSystem.unity3d
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_CeCo_Buttons_176_SportsExhaustSystem.unity3d
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_CeCo_Buttons_CarreraS_639_640_SportChrono.unity3d
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Gearshift_250_PDK_EE_Decor.unity3d
>
> -http://***/content/mJ2018/99186/Unity3d/AssetBundles/MY15_991_Int_Seats_P06_P07_Memory.unity3d
>
> 
>
> You have them all?
I filter all lines with model parts names from visualDefinitionMega with LineFilter2 plugin for Notepad++ by searching "MY15_" (never seen MY16 or MY17 parts, so it's ok i think), then replace all in front of "MY15_" with path to file and add ".unity3d" after each part name.
Those lines can be in commented or unused parts of visualDefinitionMega, only way to check it is use of old method with sniffing links from viewer and compare.
I did compare at the beginning and found nothing missed, but even more parts then from sniffing.

Also i think parts with same name have the same meshes inside (at least for model year) and all parts from your list can be found in other cars folders.
## Post #287
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2017-11-13T21:04:41+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Andrakann
>
> 
Also i think parts with same name have the same meshes inside (at least for model year) and all parts from your list can be found in other cars folders.
Correct, and that's neat too, except that they hold different coordinates for 3D placement, thus are misplaced, yet its a minor issue anyway, was just wondering if I am the only one getting the error or missing files, also checking online they do not exist either for that specific car, none the less thank you.
## Post #288
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2017-12-05T14:58:40+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Chipicao
>
> Updated M3G2FBX to work with latest version of Real Racing 3. Thanks to Barti for pointing out the change!

 

Btw, the STILL haven't released NFS No Limits in the US app store??

i download the obb (739mb) of RR3 and i find only 5 cars
what i can do to find all cars from this game? lol
## Post #289
- Username: chrisu12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 09, 2017 8:09 pm
- Post datetime: 2018-01-16T09:23:11+00:00
- Post Title: Re: Game import MAXScripts & tools

Hello

wanted to ask if anyone who can help with the bones.
It is the i3d importer.
I myself have already extended it a bit and now it also reads all UV's map.
Unfortunately, I have no idea about programming and that's why I'm over-asked at the bones.

I would be very happy if someone could help me.

I can upload the files for testing!

with friendly greeting

Christian
## Post #290
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2018-01-17T00:24:32+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from MacedoSTI
>
> Chipicao wrote:Updated M3G2FBX to work with latest version of Real Racing 3. Thanks to Barti for pointing out the change!

 

Btw, the STILL haven't released NFS No Limits in the US app store??

i download the obb (739mb) of RR3 and i find only 5 cars
what i can do to find all cars from this game? lol

play RR3 through android phone or its emulator and download all assets.
## Post #291
- Username: vladikkgg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 01, 2011 8:44 pm
- Post datetime: 2018-01-28T20:27:55+00:00
- Post Title: Re: Game import MAXScripts & tools

Hello, i have a problem with Unity bundle. Compressed bundle didn't extract, i trying extract UnityStudio x64 0.9.0.0. In file is 3d model of car. Maybe he encrypted.I don't now. I will be grateful for help! [https://yadi.sk/d/txugm4Eh3RrzaY](https://yadi.sk/d/txugm4Eh3RrzaY)
## Post #292
- Username: longpinkytoes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Feb 27, 2018 2:19 am
- Post datetime: 2018-02-26T19:40:05+00:00
- Post Title: Re: Game import MAXScripts & tools

i have the free download of Dungeon Hunter for pc, and can see all of the .bdae / .pak / .swf files,
and would like to be able to open all of the assets to learn more about how the game's engine works.
Autodesk offers a free .dae to .fbx converter for Max (and Maya?) but is there one for blender?
This will be my first attempt at modding on a game engine without access to the engine's editor.
Any help, or suggestions, or rough outlines of what pipeline works best would all be appreciated.
Thanks!~ ^^
## Post #293
- Username: chrisu12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 09, 2017 8:09 pm
- Post datetime: 2018-03-11T16:55:26+00:00
- Post Title: Re: Game import MAXScripts & tools

Thanks for your help, I've done it myself


> Reply from chrisu12
>
> hi @all


Oh, I could also put an i3d of the fs17 to the test.
Where the shape and animation in the i3d stands.

Regards
Chrisu


Ach ja , ich könnte auch eine i3d vom fs17 zur verfügung stellen zum testen.
Da wo die shape und animation in der i3d steht.

MfG
Chrisu
## Post #294
- Username: Antti
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 19, 2018 10:53 pm
- Post datetime: 2018-03-19T14:57:37+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi everyone, is the Milestone importer been updated in the years? I'm trying to import a track into 3dsmax but while asking me the folder texture i got this error



Any idea on how to solve this error and import the track? Thanks
## Post #295
- Username: PixelCoder
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 24, 2018 6:58 pm
- Post datetime: 2018-03-24T11:05:18+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi friends,

Did anyone managed to extract track models from NFS NL? I need them a lot  Thanks!
## Post #296
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2018-06-28T13:34:35+00:00
- Post Title: Re: Game import MAXScripts & tools

...is pCARS 2 working with this? QuickBMS script manages to extract it, but script for Max seems as it always stuck on loading some of the models...

Or is there another way?

Thanks...
## Post #297
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-12-15T13:56:54+00:00
- Post Title: Re: Game import MAXScripts & tools

Updated my [links lists for Porshe models](http://forum.xentax.com/viewtopic.php?p=134423#p134423).

Upd: Added another 2 models (2019 Boxter and Cayman "T").
## Post #298
- Username: nutbomb
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 03, 2007 3:34 pm
- Post datetime: 2019-03-20T13:39:59+00:00
- Post Title: Re: Game import MAXScripts & tools

Thanks for your kind help with neat model list！
## Post #299
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2019-04-05T01:46:18+00:00
- Post Title: Re: Game import MAXScripts & tools

2020 3D models
2020 Porsche Cayenne Turbo Coupe New
2020 Porsche Cayenne Coupe New
2020 Porsche 911 (992) Carrera S Cabriolet 
2020 Porsche 911 Carrera S

> Stop linking to 3d model downloads of your facebook page.
## Post #300
- Username: AUSDoug
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 26, 2019 9:45 am
- Post datetime: 2019-04-26T01:57:50+00:00
- Post Title: Re: Game import MAXScripts & tools

Hi all.
I've been using the KN5 convertor for some time now, getting models for rendering in Keyshot, and have run into my first ever issue with the tool.
Upon trying to convert the latest VRC car, the Formula Lithium i get an almost immediate hang:



Capture_000.PNG (21.17 KiB) Viewed 144 times


After confirming via the 'Close Program' button, Powershell reports an unhandled exception, out of memory error.

I then tried importing the model into 3D SimEd - which crashed immediately - and then into 3DS Max via the script on page 1. Max went unresponsive for about ~5 minutes, before giving me a script error related to an integer conversion.

If anyone has any idea of what could be going on here, I'd be grateful for some help.

Cheers.

EDIT: I've just downloaded the source from GitHub, and, on a hunch, recompiled to target a 64-bit platform.
That appears to have solved the Out of Memory exception, but now I'm getting an 'Illegal characters in path' exception, relating to the readKN5() method.
## Post #301
- Username: Jorge Soares
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 04, 2020 3:28 am
- Post datetime: 2020-03-03T19:35:39+00:00
- Post Title: Re: Game import MAXScripts & tools

hello someone already used to open the 3d files in automobilista 2
## Post #302
- Username: 3drussiangrabber
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 27, 2020 12:12 am
- Post datetime: 2020-03-24T17:46:29+00:00
- Post Title: Re: Game import MAXScripts & tools

What about Unity Importer for apps hi 5.1.3f.1 ?
## Post #303
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2020-04-06T19:15:12+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from Jorge Soares ↑Wed Mar 04, 2020 3:35 am at Wed Mar 04, 2020 3:35 am
>
> 
hello someone already used to open the 3d files in automobilista 2

+1

Really looking for some models of this new game, anyone already looked at the .meb mesh files please? Thanks
## Post #304
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-07-02T12:31:34+00:00
- Post Title: Re: Game import MAXScripts & tools

Can you please make a Blender plugin script? I can't buy 3DS Max
## Post #305
- Username: Jorge Soares
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 04, 2020 3:28 am
- Post datetime: 2020-08-26T12:51:43+00:00
- Post Title: Re: Game import MAXScripts & tools

I can extract the BMS files. the files do not open in 3ds max, 3DSim. owes this encryption.
auto the files you break encryption, based rfactor
## Post #306
- Username: StrifeHistorian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2020 9:54 pm
- Post datetime: 2020-10-05T13:58:01+00:00
- Post Title: Re: Game import MAXScripts & tools

Hey guys! I'm new at anything related to format conversion so this may be a newbie question, but I am trying to convert models from a m3g format to a FBX format. The models come from Mass Effect: Infiltrator, and I've already tried to use the present M3G2FBX converter linked here but it seems it doesn't work in my situation, the fbx files are pretty much empty. Anybody has any idea on why that is so? I know this subject is 7 years old but still, maybe I have a shot xD!
## Post #307
- Username: StrifeHistorian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2020 9:54 pm
- Post datetime: 2020-10-05T17:11:14+00:00
- Post Title: Re: Game import MAXScripts & tools

Well to continue on what I said, some of the models could be extracted, but some others just don't get converted to fbx. I'm gonna try to use the hex2obj tool i was able to find, but i'm bad at hex so we'll see.
## Post #308
- Username: StrifeHistorian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2020 9:54 pm
- Post datetime: 2020-10-06T12:48:16+00:00
- Post Title: Re: Game import MAXScripts & tools

Alright I understand even less now xD. All models actually extract properly but some aren't readable although the data is there if i open the FBX with N++. Anyone has had that issue?
## Post #309
- Username: yoda
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 30, 2008 5:28 am
- Post datetime: 2020-11-28T12:30:58+00:00
- Post Title: Re: Game import MAXScripts & tools

what do you use for extract the model ?
## Post #310
- Username: StrifeHistorian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2020 9:54 pm
- Post datetime: 2020-12-01T09:00:11+00:00
- Post Title: Re: Game import MAXScripts & tools

I used the M3G2FBX tool
## Post #311
- Username: GabenHood
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 25, 2017 9:40 pm
- Post datetime: 2021-07-05T21:32:19+00:00
- Post Title: Re: Game import MAXScripts & tools

Anyone have any ideas why the SMS importer keeps failing for me? 



I am not sure what to do with the texture/shared assets folders either. 
Are they supposed to be the exported files from QuickBMS or the stock game file/folders?

Cheers,
## Post #312
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2022-08-19T16:14:45+00:00
- Post Title: Re: Game import MAXScripts & tools

Im actually having problems with the "PIGTOFBX" one
everytime i try load a .pig file, it says are converting it, but after some seconds, it crashes without a reason and doesnt convert nothing
## Post #313
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-08-19T18:06:02+00:00
- Post Title: Re: Game import MAXScripts & tools

> Reply from GabenHood ↑Tue Jul 06, 2021 5:32 am at Tue Jul 06, 2021 5:32 am
>
> 
Anyone have any ideas why the SMS importer keeps failing for me? ...
A bit more information would help in identifying the problem but it seems based on your screenshot your using  a new game that isn't fully supported by the script, also, the actual dev that made is long gone, no one else ever edited/updated his scripts/tools.

> Reply from DiMickfoxed65 ↑Sat Aug 20, 2022 12:14 am at Sat Aug 20, 2022 12:14 am
>
> 
Im actually having problems with the "PIGTOFBX" one...
That tool no longer works, it was created based on reversing done on a older version of the game assets.
