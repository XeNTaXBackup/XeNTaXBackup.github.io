## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-02-21T14:48:47+00:00
- Post Title: Metal Gear Solid (series) - Tools

I have for you tool pack with all tools that can make your life easier 
Tools are for games from Metal Gear Solid series.

[DOWNLOAD METAL GEAR SOLID TOOLS](http://ikskoks.pl/XENTAX/metal_gear_solid_tools.zip)


Solidus
Multi-purpose toolset for Metal Gear Solid 2 
Extracts and replaces files in DAR and QAR archives 
Converts XTI textures to TGA and DDS files (single texture mode), extracts TGA subtextures needed for models 
Converts TGA and DDS files to XTI textures 
Converts (most) static KMY models to OBJ file
Solidus supports MGS:TTS (The Twin Snakes), the GameCube game.
Thanks to Turfster, LionheartUK & TheDyingInformant for their hard work. They spent months researching and pulling things apart.

Masher
Masher is a package for creating and playing back highly compressed high quality movies under Win95/98/NT. It is targeted especially for game development. The movie player is coded almost entirely in Assembler and takes advantage of MMX technology. Playback is in 16 bit color exclusively,  but the use of realtime dithering effectively displays more than 2 million colors.
This tool can play DDV movies from Metal Gear Solid and convert AVI to DDV files.

Konami DAT Utility 
Packer and unpacker for almost all *.DAT files from konami games)

UnMass
Unpacker and REPACKER for *.DAR files
(thanks to mirex, unmass has a packing function)

Metal Gear Solid 2 KMY Importer for Milkshape 1.7 
This plugin allows you to load all static Metal Gear Solid 2 3D objects 
into Milkshape.)

BioHazard File Archive Tool 
for extracting *.DIR files from MGS PSX version)

This pack also contains many tutorials and guides about translating and modding Metal Gear Solid games.


Edit: Some new tools below

PC DAR tool 1.5 (fugtao version)
Extract *.dar files from PC.
[http://secaproject.com/pc_dar_tool_1_5](http://secaproject.com/pc_dar_tool_1_5)

PSX DAR tool 1.5 (fugtao version)
Extract *.dar files from PSX.
[http://secaproject.com/psx_dar_tool_1_5](http://secaproject.com/psx_dar_tool_1_5)

KMD2OBJ 2.51 (fugtao version)
An advanced conversor for KMD models files.
[http://secaproject.com/kmd2obj_2_51](http://secaproject.com/kmd2obj_2_51)

DIR tool 1.5 (fugtao version)
Extract *.dir files
[http://secaproject.com/dir_tool_1_5](http://secaproject.com/dir_tool_1_5)

DIR tool 1.51 (fugtao version)
Extract contents from STAGE.DIR
[http://secaproject.com/dir_tool_1_51](http://secaproject.com/dir_tool_1_51)

CON tool 1.0 (fugtao version)
Convert CON files into text
[http://secaproject.com/con_tool_1_0](http://secaproject.com/con_tool_1_0)

RAR tool 1.0 (fugtao version)
Extract images from *.rar files
[http://secaproject.com/rar_tool_1_0](http://secaproject.com/rar_tool_1_0)

GCX tool 2.0 (fugtao version)
Decodes GCX scripts into something readable near to GCL
[http://secaproject.com/gcx_tool_2_0](http://secaproject.com/gcx_tool_2_0)

GCX tool 2.0.4 (fugtao version)
Decodes GCX scripts into something readable near to GCL
[http://secaproject.com/gcx_tool_2_0_4](http://secaproject.com/gcx_tool_2_0_4)

HZM tool 1.0 (fugtao version)
Draw on screen the info stored within.
[http://secaproject.com/hzm_tool_1_0](http://secaproject.com/hzm_tool_1_0)

HZM tool 1.2 (fugtao version)
Draw on screen the info stored within.
[http://secaproject.com/hzm_tool_1_2](http://secaproject.com/hzm_tool_1_2)

DIR tool 1.8 (fugtao version)
Extracts content from STAGE.DIR
[https://secaproject.com/dir_tool_1_8](https://secaproject.com/dir_tool_1_8)

Some Ruby Scripts
[https://github.com/metalgeardev/MGS1](https://github.com/metalgeardev/MGS1)


Edit2: New tools have been discovered today (19.09.2020). List below

> dar-extract_*, qar-extract_psp, zar-extract
>
> 
>
> Tools for unpacking archive files from the corresponding platform. dar-extract_psx supports dictionaries for giving proper names to the files within. To use the dictionary feature, place a dictionary file somename.txt in the same folder as the executable, then use dar-extract_psx file somename
>
> dat-extract_enc
>
> 
>
> Tool for unpacking STAGE.DAT and FACE.DAT from MGS2, MGS3, MGS4, ZoE2 and MGS Twin Snakes. Supports dictionaries, place a file called common.txt, suffixed with the game name, or one matching a stages name in the same folder as the executable, prefixes with your game name (e.g. mgs2-, trial2-, tts-, etc.). Dictionaries will be loaded automatically and do not need to be passed by hand. If a file fails with the autodetection (either missing or mismatched game ID), you can pass an ID as additional argument to override the autodetection. Use this at your own risk, check the code (specifically the switch around line 870) for IDs.
>
> dat-merge
>
> 
>
> Tool to unpack the files from the on-disc VFS from MGS2S on Xbox. Currently, this requires the VFS files to be merged by hand. Remember to back-up your files before doing this.
>
> To do so, simply concatenate the files, e.g. cat disc1_{0..8}.dat > disc1.dat or copy /B disc1_0.dat + disc1_1.dat + [...] + disc1_8.dat disc1.dat. Then pass the resulting disc1.dat to dat-merge. Follow the same procedure for disc2_*.dat. The unpacked files can be unpacked just like the files from the PS2 games.
>
> face-extract
>
> 
>
> Tool for unpacking MGS1 FACE.DAT, supports a dictionary as well. Place one with the name mgs1-face.txt next to the executable.
>
> gcx-decompile
>
> 
>
> Tool for decoding a gcx script into readable text. Probably incomplete.
>
> simple-hash
>
> 
>
> Pass a string to compute its kojimahash for all known flavours.
>
> stage-extract
>
> 
>
> Tool to unpack MGS1 STAGE.DIR, supports dictionaries. See dat-extract_enc for naming convention.
>
> txp-convert
>
> 
>
> Converts txp textures found in the PSP games to PNG.
>
> Other code included
>
> stage-dictionary
>
> 
>
> Code for handling the dictionaries used by the unpacking tools.
>
> kojimahash/
>
> 
>
> Contains functions to compute the hashes used for matching dictionaries against hashes contained within the archives.

Sources --> [https://github.com/Joy-Division/tools-mgs](https://github.com/Joy-Division/tools-mgs)


LiquidGear - Metal Gear Solid 3 / Collection HD *.sdt Text Editor 
[https://github.com/LeonamMiiller/LiquidGear](https://github.com/LeonamMiiller/LiquidGear)

> MGSDATool
>
> 
>
> Metal Gear Solid 3/4 translation toolkit
>
> 
>
> This is a toolkit for translating Metal Gear Solid 3: Subsistence and Metal Gear Solid 4: Guns of the Patriots.
>
> 
>
> Below you can see a list of what each tool does:
>
> 
>
> DATCodecTool - Extracts texts from the codec.dat file and inserts then back. Works on both MGS3 and MGS4.
>
> 
>
> DATMovieTool - Extracts subtitles from movie.dat and demo.dat, and can also insert the modified subtitles back. Like the codec tool, works on both MGS3 and MGS4.
>
> 
>
> DATSpeechTool - Extracts *.spc files from a speech.dat (with a scenerio.gcx from the init folder), and extracts subtitles from each *.spc. It can insert subtitles back into the *.spc, and can re-create the speech.dat aswell. Only works on MGS4, since MGS3 don't have a speech.dat file.
>
> 
>
> A note about the DATCodecTool and DATMovieTool: It's still unknown where the pointers for the data inside those files (codec.dat, movie.dat and demo.dat) are, therefore if you change the lengths of the texts inside those files, there's a possibility that the game will crash. Due to the fact that those files have paddings (with movie.dat and demo.dat being aligned into 2kb blocks), there's usually a lot of room for expansion. But again, it's recommended that you keep the same lengths, or recalculate the pointers if you know where they are. Keeping the same lengths is the sure-fire to make it work.
>
> 
>
> Please look carefully the usage instructions of each tool, since each tool is used in a different way.

Sources --> [https://github.com/gdkchan/MGSDATool](https://github.com/gdkchan/MGSDATool)


> GB Metal Gear Solid: Ghost Babel script tool. Game uses MTE and LZ compression for text. This tool can work with it.
Sources --> [https://github.com/romhack/mgsgbLz](https://github.com/romhack/mgsgbLz)

> C# Fox Engine dat/qar, fpk, fpkd, pftxs and sbp unpacker/repacker
Sources --> [https://github.com/Atvaark/GzsTool](https://github.com/Atvaark/GzsTool)

> MGSV QAR Dictionary Project
>
> The QAR dictionary project is a project to name every file used in MGSV Ground Zeroes and The Phantom Pain.
Sources --> [https://github.com/emoose/MGSV-QAR-Dictionary-Project](https://github.com/emoose/MGSV-QAR-Dictionary-Project)

> FtexTool
>
> A tool for converting files between Fox Engine texture (.ftex) and DirectDraw Surface (.dds).
Sources --> [https://github.com/Atvaark/FtexTool](https://github.com/Atvaark/FtexTool)

> TPP.FileFormats
>
> Fox Engine / Metal Gear Solid V: The Phantom Pain file format research dump.
Sources --> [https://github.com/Atvaark/TPP.FileFormats](https://github.com/Atvaark/TPP.FileFormats)

> FoxTool
>
> A tool for compiling and decompiling Fox Engine XML files. Compiled XML files have these file extensions:
Sources --> [https://github.com/Atvaark/FoxTool](https://github.com/Atvaark/FoxTool)

> FoxEngine.TranslationTool
>
> A bundle of tools related to text editing Fox Engine / MGSV Ground Zeroes files.
Sources --> [https://github.com/Atvaark/FoxEngine.TranslationTool](https://github.com/Atvaark/FoxEngine.TranslationTool)

> MGS:Peace Walker PS3 RTM CCAPI Tool
>
> A memory editor for the ps3 version of peace walker using ccapi via ps3lib.dll.
Sources --> [https://github.com/MarkH221/PeaceWalkerRTM](https://github.com/MarkH221/PeaceWalkerRTM)


Edit: BMS Scripts below

[Metal Gear Solid Pdt . Metal Gear Solid: Peace Walker PSP (*.pdt)](https://aluigi.altervista.org/bms/metal_gear_solid_pdt.bms)
[Metal Gear Solid Pdt Music . Metal Gear Solid: Peace Walker PSP music-only (*.pdt) (script 0.1.4) . XOR](https://aluigi.altervista.org/bms/metal_gear_solid_pdt_music.bms)
[Metal Gear Solid Xbarc . Metal Gear Solid HD Collection (script 0.2.2a) . xmemdecompress . XBAR](https://aluigi.altervista.org/bms/metal_gear_solid_xbarc.bms)
[Mgs5 Stpl . Metal Gear Solid V STP . STPL](https://aluigi.altervista.org/bms/mgs5_stpl.bms)
## Post #2
- Username: kurt28
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 08, 2010 1:00 am
- Post datetime: 2013-02-23T19:48:34+00:00
- Post Title: Metal Gear Solid (series) - Tools

Have you used this tool to translate MGS1?
The font in utf-8 is shown?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-02-23T20:12:59+00:00
- Post Title: Metal Gear Solid (series) - Tools

> Have you used this tool to translate MGS1?

Translating this game is only possible in hex editor. So it is very uncomfortable. 
I don't know where are the fonts, but i think they can be placed in one of the *.dar archives in *.mgz file.

All textures in MGS 1 are in *.tga and *.pcx graphic format. I found the way to edit *.tga images using Graphics Gale, but i don't have any idea how to edit .pcx files and repack tem to .dar archives.

So to edit this game you must first change extension in one of the *.mgz files to *.zip and unpack content to you disk. Then you have to use Unmass to extract PCX textures from .dar files, edit files and pack them with unmass. In the end just replace original *.dar with edited *.dar

but there's a catch 
I didn't find any way to display changed textures in game properly... If you find working method, please share it with me and others in this topic 

And about text to translate - all codec talks are in radio.dat file, all cut-scenes dialogues are in *.dmo and *.vox files and other stuff are in MGSI.exe 


And other tools are also useful. For example with Masher we can edit movies from Metal Gear Solid in *.DDV format.
Solidus can convert for us VOX files to WAV etc.
## Post #4
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2013-02-25T01:04:26+00:00
- Post Title: Metal Gear Solid (series) - Tools

THANK YOU SO MUCH!!! My dream came true thanks to you guys!
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-02-27T17:06:59+00:00
- Post Title: Metal Gear Solid (series) - Tools

You might also want to add that Solidus supports MGS:TTS (The Twin Snakes), the GameCube game.

It extracts the textures but not the models if I remember rightly.

It also works on a few files from MGS3, but only uncompresses them, it doesn't actually extract anything, it just decrypts them so you can see the original naming.

You might also want to add 'Thanks to Turfster, LionheartUK & TheDyingInformant' in the solidus section, being the 3 people that spent months researching and pulling things apart.

Thanks for collecting it all together though. The Konami.DAT tool doesn't work so great for MGS3 however.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-02-27T17:55:05+00:00
- Post Title: Metal Gear Solid (series) - Tools

> You might also want to add that Solidus supports MGS:TTS (The Twin Snakes), the GameCube game.
>
> You might also want to add 'Thanks to Turfster, LionheartUK & TheDyingInformant' in the solidus section
Added to the first post
## Post #7
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-02-28T21:34:46+00:00
- Post Title: Metal Gear Solid (series) - Tools

MGS PC PCX textures have extra data in an otherwise unused part of the [header](https://github.com/neko68k/mgsview/blob/master/mgsview/vram.cpp) that contain vram coordinates for the image and its palette(s). This data must be preserved. You also may not change the bpp(8 or 4 bpp) or the dimensions of a texture without changing _all_ of the textures. This is due to how textures are packed into [vram](http://neko68k.blogspot.com/2011/09/mgs-vram-4.html)  If you convert them to TIM's there is an official Sony [tool](http://neko68k.blogspot.com/2011/12/mgs-pcx-to-tim-conversion.html) that can make repacking them into vram easier, though there are some visual issues in the tool, then convert back to PCX. There may also be issues regarding replacing the palettes for existing textures. 

The KMD format in MGS is also somewhat documented [here](https://github.com/neko68k/mgsview/blob/master/mgsview/KMD.cpp). There is some currently unused, incomplete, and quite possibly not compiling code in this file, beware.
## Post #8
- Username: yanneric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 30, 2011 6:15 am
- Post datetime: 2013-03-22T05:29:04+00:00
- Post Title: Metal Gear Solid (series) - Tools

Thank you for those Tools!! i have a question, there is an kmy importer which is great, but does a kmy exporter exist? is it possible to convert back an obj to kmy and put it back in the game? (it would be to mod the game), thanks in advance
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-03-22T06:35:48+00:00
- Post Title: Metal Gear Solid (series) - Tools

> but does a kmy exporter exist? is it possible to convert back an obj to kmy and put it back in the game?

I'm sorry, but I think that kmy exporter doesn't exist and it isn't possible to convert back an obj to kmy. 
(At least for now, maybe someday it will be possible when someone will ceate a tool for this. Don't loose your hope. )
## Post #10
- Username: yanneric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 30, 2011 6:15 am
- Post datetime: 2013-03-22T07:25:37+00:00
- Post Title: Metal Gear Solid (series) - Tools

> Reply from ikskoks
>
> but does a kmy exporter exist? is it possible to convert back an obj to kmy and put it back in the game?

I'm sorry, but I think that kmy exporter doesn't exist and it isn't possible to convert back an obj to kmy. 
(At least for now, maybe someday it will be possible when someone will ceate a tool for this. Don't loose your hope. )

ok, i won't    thanks
## Post #11
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2013-06-25T17:27:05+00:00
- Post Title: Metal Gear Solid (series) - Tools

I'm with the translation project of MGS1 to 3 years, I intend to finish it one day kkk.
I must have the source information of the game, if you need I will look at my stuff and post here.
Another thing the. DAT to be inserted back into the ISO if the size is larger than the original is necessary to recalculate the LBA and size of the ISO, if not the codec start the game crashes.


ePSXe. stopped working
Windows is checking for a solution to the problem...



I tested the tool in the DAT files and generates error so you saw the tool Konami. Dat, only recognizes from MGS2.
I have a tool made ​​for these files in Delphi if I need to pass the source code to add to your tool.
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-06-25T17:50:00+00:00
- Post Title: Metal Gear Solid (series) - Tools

> I have a tool made ​​for these files in Delphi if I need to pass the source code to add to your tool.

I didn't create these tools. I just uploaded them here. ^^
So i don't have any source code ;p

But all users (me too) will be very grateful if you post here your tool in Delphi. It will help to translate MGS to many other languages.
## Post #13
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2013-07-04T13:44:32+00:00
- Post Title: Metal Gear Solid (series) - Tools

> Reply from ikskoks
>
> I have a tool made ​​for these files in Delphi if I need to pass the source code to add to your tool. 

I didn't create these tools. I just uploaded them here. ^^
So i don't have any source code ;p

But all users (me too) will be very grateful if you post here your tool in Delphi. It will help to translate MGS to many other languages.

Yes, I will post the BETA version, the final version will post once you finish the translation.
Put the information where the sources are, but it would be interesting to have a BMS script to do the dump / insert.

I need to resolve this problem to insert the file. DAT back to iso, I do not know if the bug image above is due to the tool or LBAs.
## Post #14
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-10-13T22:23:21+00:00
- Post Title: Metal Gear Solid (series) - Tools

I have re-uploaded Solidus [here](https://www.sendspace.com/file/y287ud).
## Post #15
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2016-07-01T12:30:03+00:00
- Post Title: Metal Gear Solid (series) - Tools

> Reply from keystothemaxim
>
> I have re-uploaded Solidus here.

Links had been dead for a while, i just joined the forum btw...

Keen to try to find out if any of these tools can be used with the MGS HD Collection / Legacy Collection Files...

There was even talk years ago of An Attempt At Porting MGS4 Elsewhere or at least Extracting all Assets for a Slow Remake etc / More MODs Featuring old Levels ETC...
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-07-01T12:42:22+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hey. I just updated link to the tools in the first post. Enjoy! 

> Keen to try to find out if any of these tools can be used with the MGS HD Collection / Legacy Collection Files...
I'm afraid it is not possible, but who knows
## Post #17
- Username: AnushkaChakrabart
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 2:56 pm
- Post datetime: 2016-08-05T07:03:09+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Yes,
I will post the BETA form, the last form will post once you complete the interpretation. 
Put the data where the sources are, however it is intriguing to have a BMS script to do the landfill/embed.
## Post #18
- Username: in3eemhd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 05, 2016 8:41 pm
- Post datetime: 2016-08-05T15:38:29+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

can anyone upload the tool in other server? i can't download it + can i use it for mgo2 models and stages?!
## Post #19
- Username: Goethes Faust
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 26, 2016 9:41 am
- Post datetime: 2016-12-26T01:56:08+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hey all,

I am totally new to this but I hope my matter is not too troublesome. I want to do a custom animated GIF based on the 1998 Metal Gear Solid main menu screen as it is shown below but I want to use the animated background, Snake's face and the 'PRESS START BUTTON' text only without the other fonts. Is there a way to extract these files and if so, where can I find these files and how can I do this?

Thanks in advance.
[None](https://xentaxbackup.github.io/file/12130_None)
## Post #20
- Username: Goethes Faust
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-12-26T11:04:33+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> where can I find these files and how can I do this?
I don't have this game installed right now, but I remember a little how to edit this image.
It is some TGA image that is in game folder. It isn't even packed as I remember.
So try to search for file titlescreen.tga or something similar to this.
## Post #21
- Username: Goethes Faust
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 26, 2016 9:41 am
- Post datetime: 2016-12-26T12:40:13+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from ikskoks
>
> where can I find these files and how can I do this?
I don't have this game installed right now, but I remember a little how to edit this image.
It is some TGA image that is in game folder. It isn't even packed as I remember.
So try to search for file titlescreen.tga or something similar to this.

Wrong, the files are packed in a subfolder called 'title' within stage.mgz. I already found it out myself. Thanks anyway.
## Post #22
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2017-05-11T17:13:50+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I made a post about a wiki and discord we have made around Metal Gear Solid Files and Tools - [viewtopic.php?f=28&t=16274](http://forum.xentax.com/viewtopic.php?f=28&t=16274)
## Post #23
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-08-25T20:07:57+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

PC DAR tool 1.5 (fugtao version)
Extract *.dar files from PC.
[http://secaproject.com/pc_dar_tool_1_5](http://secaproject.com/pc_dar_tool_1_5)

PSX DAR tool 1.5 (fugtao version)
Extract *.dar files from PSX.
[http://secaproject.com/psx_dar_tool_1_5](http://secaproject.com/psx_dar_tool_1_5)

KMD2OBJ 2.51 (fugtao version)
An advanced conversor for KMD models files.
[http://secaproject.com/kmd2obj_2_51](http://secaproject.com/kmd2obj_2_51)

DIR tool 1.5 (fugtao version)
Extract *.dir files
[http://secaproject.com/dir_tool_1_5](http://secaproject.com/dir_tool_1_5)
## Post #24
- Username: MeraoK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 04, 2019 5:59 am
- Post datetime: 2019-07-03T22:02:57+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hi Everyone How to repack files extracted from qar file?
## Post #25
- Username: ToTheMadness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 05, 2019 2:49 am
- Post datetime: 2019-10-14T13:07:35+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Does anybody found the font files yet? I already checked the dar files in the stage.mgz with specific the folders with names like "title" but there wasn't any font texture. I haven't checked the ones with names like "d01a" but since it looks like they are the missions assets I don't think if I can find fonts in there.

Also I found a file named "font.res" but I don't know what does it contains. You can find it in the attachments.
[None](https://xentaxbackup.github.io/file/16902_None)
## Post #26
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-10-14T13:44:32+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from ToTheMadness ↑Mon Oct 14, 2019 9:07 pm at Mon Oct 14, 2019 9:07 pm
>
> 
Does anybody found the font files yet? I already checked the dar files in the stage.mgz with specific the folders with names like "title" but there wasn't any font texture. I haven't checked the ones with names like "d01a" but since it looks like they are the missions assets I don't think if I can find fonts in there.

Also I found a file named "font.res" but I don't know what does it contains. You can find it in the attachments.

I haven't looked for them before, but d01a and other files/folders beginning with d are cutscene sequences, the d stands for demo.
## Post #27
- Username: ToTheMadness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 05, 2019 2:49 am
- Post datetime: 2019-10-18T10:57:43+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from Goethes Faust ↑Mon Dec 26, 2016 9:56 am at Mon Dec 26, 2016 9:56 am
>
> 
Hey all,

I am totally new to this but I hope my matter is not too troublesome. I want to do a custom animated GIF based on the 1998 Metal Gear Solid main menu screen as it is shown below but I want to use the animated background, Snake's face and the 'PRESS START BUTTON' text only without the other fonts. Is there a way to extract these files and if so, where can I find these files and how can I do this?

Thanks in advance.
1. Extract the stage.mgz file (it's a zip file)
2. From here you need to extract the .dar files with unmass and look for the section that you want to remove. I don't remember the folder name but it might be in the "title" one.
3. After finding the file open it in a image editor and make it completely transparent.
4. Repack everything and it should be done.
## Post #28
- Username: ToTheMadness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 05, 2019 2:49 am
- Post datetime: 2019-10-18T12:03:50+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from lionheartuk ↑Mon Oct 14, 2019 9:44 pm at Mon Oct 14, 2019 9:44 pm
>
> 
ToTheMadness wrote: ↑Mon Oct 14, 2019 9:07 pm
Does anybody found the font files yet? I already checked the dar files in the stage.mgz with specific the folders with names like "title" but there wasn't any font texture. I haven't checked the ones with names like "d01a" but since it looks like they are the missions assets I don't think if I can find fonts in there.

Also I found a file named "font.res" but I don't know what does it contains. You can find it in the attachments.


I haven't looked for them before, but d01a and other files/folders beginning with d are cutscene sequences, the d stands for demo.
Yeah I just looked at the readme and it was there.
I found [this](https://github.com/paulsapps/msgi) debug tool which looks like it gives you the source codes. there are a lot of lines about font too but I don't know much about C++ and I will appreciate it if somebody take a look at it. the extracted codes are there too.
## Post #29
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2020-08-20T12:25:36+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hi, main link is dead, can someone reupload the pack please?

Thanks very much!
## Post #30
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-20T12:37:15+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from Stallone ↑Thu Aug 20, 2020 8:25 pm at Thu Aug 20, 2020 8:25 pm
>
> 
Hi, main link is dead, can someone reupload the pack please?

Thanks very much!

It is not dead, but here is the mirror
[https://drive.google.com/file/d/1g8o0-_ ... sp=sharing](https://drive.google.com/file/d/1g8o0-_2z-5ywQ5I-TTf_EXN_TcPkiRxf/view?usp=sharing)
## Post #31
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2020-08-20T17:13:44+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from ikskoks ↑Thu Aug 20, 2020 8:37 pm at Thu Aug 20, 2020 8:37 pm
>
> 
Stallone wrote: ↑Thu Aug 20, 2020 8:25 pm
Hi, main link is dead, can someone reupload the pack please?

Thanks very much!


It is not dead, but here is the mirror
https://drive.google.com/file/d/1g8o0-_ ... sp=sharing

Thank you very much for quick reply!

Sorry for the trouble, it wouldn't load on my end.
## Post #32
- Username: zeaofsuos
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Apr 19, 2019 10:07 pm
- Post datetime: 2020-08-27T05:24:26+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

ADMIN, PLEASE DELETE.
## Post #33
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-27T06:34:36+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I know that voices are in vox.dat file (not sure it is PC or PSX).
You can read more here [https://www.mgsdevwiki.com/wiki/index.php/DAT](https://www.mgsdevwiki.com/wiki/index.php/DAT)

As for general sound ripping I would recommend to try to use PSound, MFAudio or Foobar2000+ vgmstream plugin
Every working tool I know for MGS1 and MGS2 is in the first post.
## Post #34
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-19T15:45:00+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

New tools have been added to the first post in this topic.
## Post #35
- Username: ToppestOfDogs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 07, 2019 9:40 am
- Post datetime: 2020-09-25T21:59:45+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

When I use the SECA tools to convert stage kmd to obj, the materials are all looking for textures that are random 4 character pngs, but the textures that I extract from the stg_tex1.dar are all properly named things like "m00_pla_flo4.png" so I have no idea which textures the model is trying to load.
## Post #36
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-25T22:15:02+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Sorry, but I have never used SECA Tools. You should contact SECA Project on MGS discord server to get some help.
## Post #37
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-09-26T07:20:58+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from ToppestOfDogs ↑Sat Sep 26, 2020 5:59 am at Sat Sep 26, 2020 5:59 am
>
> 
When I use the SECA tools to convert stage kmd to obj, the materials are all looking for textures that are random 4 character pngs, but the textures that I extract from the stg_tex1.dar are all properly named things like "m00_pla_flo4.png" so I have no idea which textures the model is trying to load.

If I remember correctly, it's trying to load the names of the ones from the PSX release.
## Post #38
- Username: ToppestOfDogs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 07, 2019 9:40 am
- Post datetime: 2020-09-27T20:14:43+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from lionheartuk ↑Sat Sep 26, 2020 3:20 pm at Sat Sep 26, 2020 3:20 pm
>
> 
If I remember correctly, it's trying to load the names of the ones from the PSX release.

Okay yeah, I just ripped the PSX textures and they all line up. Thanks.
## Post #39
- Username: zx2395
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 17, 2019 4:09 pm
- Post datetime: 2020-09-30T08:01:11+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

How do I re-compress the Konami data file?
I opened and modified the demo.dat file for the computer version of Metal Gear Solid2 and now I just need to compress it.
Please help me.
## Post #40
- Username: sinnerclown
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Aug 22, 2020 5:49 am
- Post datetime: 2020-10-01T11:32:34+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

hello metal gear solid 2 I want to localize the substance game konami dat tool does not work. Anyone have an idea?
## Post #41
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2020-10-01T15:37:08+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

The GOG edition of MGS contains .VOX files. There is no mention of this file type in the compilation.
Does anybody else working with the GOG edition?
## Post #42
- Username: HijackTheRipper
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-01T17:14:26+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I think that Solidus tool may be able to convert VOX files.
## Post #43
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2020-10-22T23:54:27+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Solidus convert the .vox files thanks so far.

Unfortunately some files are not correct converted (wrong sample rate or noise within the audio)
## Post #44
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2020-11-22T17:52:51+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Thank you for the 2020 update!
## Post #45
- Username: bestek
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 10, 2021 5:59 pm
- Post datetime: 2021-02-12T12:02:58+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hi everyone.
I'm looking for a way to edit the font map in MGS.
Font used in codek. The Polish language uses special characters as in the French language.
I only found the map displayed in HUD (it is in STAGE.dir)
Please help.
[mgs1_fontHUD.png](https://xentaxbackup.github.io/file/19524_mgs1_fontHUD.png)
## Post #46
- Username: bestek
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 10, 2021 5:59 pm
- Post datetime: 2021-02-12T12:13:32+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I am looking for a font map to correctly display special characters (Polish ĄĘĆŻŹŁÓ)
[2021-02-12 13_09_01-Zdjęcia.png](https://xentaxbackup.github.io/file/19526_2021-02-12 13_09_01-Zdjęcia.png)
## Post #47
- Username: kingsushi001
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 26, 2020 5:01 am
- Post datetime: 2021-02-21T12:22:33+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hi everyone

Can someone point me into the right direction on how to extract the textures from the PSX version of the game?
I have tried all the tools on the 1st page without success. I was able to extract STAGE.DIR and that's it. The resulting files seems to be titled the same as the PC version, but no extension.

Any help would be appreciated
## Post #48
- Username: Flag King
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 22, 2010 1:34 am
- Post datetime: 2021-03-23T18:45:07+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Wow!
This topic was incremented with some amazing tools!

I really want to work with MGS series. Maybe this is the time!
I'll follow this topic every day for updates.

Best;


Flag
CT-STARS
Resident Evil Modding Source
## Post #49
- Username: AEDude
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 26, 2021 3:31 am
- Post datetime: 2021-04-28T17:56:09+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I have all the Obj files which have names similar to this 'v4-kusa-1v8Qb7coSU1k54TtmJzrt4-00000G-znver2.obj' however I am unable to import them into blender! I'll upload a few and if someone is willing to help me I'll pay for a premiim Mega.nz account to upload all of them for one month!

[https://mega.nz/folder/znhmwACZ#5YmAqmJEkbnS0aVdbsGDPQ](https://mega.nz/folder/znhmwACZ#5YmAqmJEkbnS0aVdbsGDPQ)
## Post #50
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-04-28T23:33:04+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Just so you know, there's already a tool for noesis that can import MGS1 models with skeletons and animations (Since I'm assuming you are referring to MGS1 models).

Though it only works for the PlayStation version of the game, not the PC one.
## Post #51
- Username: SolidMGSnake
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 01, 2021 2:51 am
- Post datetime: 2021-08-31T20:34:52+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Does anyone know how or if its possible to extract the AC3/Dolby Digital 5.1 audio from the MGS2 opening cutscene? Thanks
## Post #52
- Username: glennstavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 26, 2021 2:24 pm
- Post datetime: 2021-12-26T06:39:41+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hi last month I used the tools in this thread to extract the Vox directory of MGS3 Subsistence into ~5800 wav files. They are precisely the files I am looking for, just the game's voiced dialogue and nothing else. But I noticed they were all 22050 Hz mono. I have some questions about this:

Is this the source quality of these files? At first I figured "oh yeah, this game's got like twenty hours of audio on top of all the other crap they got to cram into a PS2 disk, so maybe it is really that compressed". They definitely don't sound bad, or noticeably different when compared against youtube footage, but I know the game's audio is presented in stereo generally. Maybe something the game or PS2 does to "split" the sounds? This is my first experience digging into any game's code so forgive me if this is a bizarre question. Anyway, if these files are supposed to be in stereo, or some other, higher sample rate, then that's what I want. Am I able to get that with these tools somehow? If so please explain how because...well it's been so long that I kind of forgot how I did it. I remember trying a lot of methods mentioned here and elsewhere until I got what I wanted through one last round of troubleshooting. Really should have written it down so that I could at least say what I did to get this far in the first place.

Update: After some more digging, I discovered that some audio files are presented in Stereo, usually just because there's more than one speaker at a time in that specific case. That makes plenty of sense. The Volgin torture sequence for instance is fully three dimensional with several characters talking from different directions. So I guess that answers my biggest concern about the quality.
## Post #53
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2022-03-11T22:36:50+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

How to extract codec.dat file for MGS2 pc
[https://mir.cr/1SSHAUX5](https://mir.cr/1SSHAUX5) or
[https://www72.zippyshare.com/v/8bqep8h2/file.html](https://www72.zippyshare.com/v/8bqep8h2/file.html)
## Post #54
- Username: glennstavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 26, 2021 2:24 pm
- Post datetime: 2022-03-25T17:39:26+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Back again, this time trying to extract the audio of MGS4. I managed to collect the ~4.5 hours of Codec conversations from the Vox directory of the game, using the Demux Dat 0.3 release. It's worth mentioning that this particular version of the command line encoder is NOT in the OP, so I can vouch for its inclusion. I tried anything else I heard mentioned here and on Google to extract these .Dat files, and this was the one that got past that first step. So here's the link where I got it, at the bottom of the page:
[https://www.hcs64.com/vgm_ripping.html](https://www.hcs64.com/vgm_ripping.html)

Using Demux_Dat_be, The Vox directory (.Dat file) was extracted into MTA2 files, which I was then able to convert into Wav format using VGMstream's command line encoder. The same process also works for the Bgm and Movie directories, which contain the game's background Music and Live action cutscene audio respectively. The Demo directory is interesting. It contained audio for the games cutscenes, but this method only got me the first of four parts. For some reason my computer gave them the file extension 66600, 66601, 66602, and 66603 instead of Dat. The 66600 was the only one that would open up with Demux Dat. Trying to cheat the system, I renamed the file extension of the others to ".66600" or ".Dat", but that did not work. Cutscene audio isn't typically valuable (in most metal gear games, what you can extract from the game's code is no more clean than simply hitting record on a youtube video of the same scene), however MGS4's cutscenes are six channel audio that you can fool around with in order to get cleaner recordings of character lines - muting stuff like background noise or characters talking over each other. If anybody knows how I can get the latter three Demo files into Wav format, I'd be interested to hear it.

What I'm really after in MGS4 are the in-game character voices. None of the tools I've found on the internet can seem to get to that material. Stuff like Snake grunting when taking damage or throwing a punch. Boss characters. Or Otacon's voice giving you helpful hints and controls. I'm not entirely sure where it even is in the game's code - probably the Stage directories if I had to guess, but nothing seems to crack it. 

I've also been working on Metal Gear Solid The Twin Snakes, and came up with some interesting solutions. At first I managed to extract the in-game character voices, but not any of the codec conversations or cutscene audio. looking at the folders on both discs labeled Audio > Stream and Shared > Audio > Stream (Some sounds exist on both discs, so that is the purpose of a Shared folder, I suspect), there were lone files with no extension. I renamed the file extension to DSP, which VGmstream was able to convert to Wav. Cool. Other .Dat directories like Vox opened up with Demux_Dat as usual, however I was given MTAF files that I cannot seem to open with VGMstream. Not until I decided to use the same cheat - change the file extension from .MTAF to .ogg (referring to the Ogg vorbis, don't ask me what that is). Then add the foobar plugin to VGMstream's folder, which allowed it to convert to Wav.
## Post #55
- Username: Cameon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 18, 2022 3:45 pm
- Post datetime: 2022-05-01T18:25:35+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Can I use those tools to translate MGS2: Substrance in PC??? I want to translate MGS2: Substrance from english to thai.
## Post #56
- Username: glennstavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 26, 2021 2:24 pm
- Post datetime: 2022-05-01T22:13:51+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Still haven't gotten what I want out of MGS4. It sounds like this can help me open the stage dat files:
[https://github.com/Jayveer/Solideye](https://github.com/Jayveer/Solideye)
However, I don't know how to make it work. It says if extracting the files is all you want, just drag and drop them on the 'executable' but I see no executable file anywhere in here.
## Post #57
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2022-05-02T02:34:39+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from glennstavos ↑Mon May 02, 2022 6:13 am at Mon May 02, 2022 6:13 am
>
> 
Still haven't gotten what I want out of MGS4. It sounds like this can help me open the stage dat files:
https://github.com/Jayveer/Solideye
However, I don't know how to make it work. It says if extracting the files is all you want, just drag and drop them on the 'executable' but I see no executable file anywhere in here.

Did you get the download from here: [https://github.com/Jayveer/Solideye/releases/tag/1.2](https://github.com/Jayveer/Solideye/releases/tag/1.2)
If not, then its likely you've just gone and gotten the project files, which would need to be compiled first, so you don't want those.
## Post #58
- Username: glennstavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 26, 2021 2:24 pm
- Post datetime: 2022-05-07T02:29:44+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from lionheartuk ↑Mon May 02, 2022 10:34 am at Mon May 02, 2022 10:34 am
>
> 
glennstavos wrote: ↑Mon May 02, 2022 6:13 am
Still haven't gotten what I want out of MGS4. It sounds like this can help me open the stage dat files:
https://github.com/Jayveer/Solideye
However, I don't know how to make it work. It says if extracting the files is all you want, just drag and drop them on the 'executable' but I see no executable file anywhere in here.


Did you get the download from here: https://github.com/Jayveer/Solideye/releases/tag/1.2
If not, then its likely you've just gone and gotten the project files, which would need to be compiled first, so you don't want those.

Ah, thank you for pointing that out to me. It does open the Stage.dat files of MGS4. Tens of thousands of files in total, but as far as I can tell it's comprised entirely of textures, models, and animation data. That's no use to me, I'm looking for sound files. In particular I want npc/boss voice lines or Otacon's in-game codecs where he gives you tips during gameplay. 

One post here claims that sdpack.dat and Speech.dat have audio files, so that's my next lead:
[https://zenhax.com/viewtopic.php?t=2516](https://zenhax.com/viewtopic.php?t=2516)

And this project claims that it can open them. 
[https://github.com/gdkchan/MGSDATool](https://github.com/gdkchan/MGSDATool)

But there's no release .exe this time. I downloaded Visual Studio and managed to make a DATspeech tool.exe, however, it gets no response when I drag speech.dat onto it. This is my first experience trying to compile something, so I couldn't begin to guess where/if I went wrong.
## Post #59
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-07T09:32:45+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> But there's no release .exe this time. I downloaded Visual Studio and managed to make a DATspeech tool.exe, however, it gets no response when I drag speech.dat onto it. This is my first experience trying to compile something, so I couldn't begin to guess where/if I went wrong.

It's a command line tool. There are some tutorials explaining how to run it.
Check here [https://www.google.com/search?client=fi ... ne+program](https://www.google.com/search?client=firefox-b-d&q=how+to+run+command+line+program)
## Post #60
- Username: glennstavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 26, 2021 2:24 pm
- Post datetime: 2022-05-07T16:34:41+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from ikskoks ↑Sat May 07, 2022 5:32 pm at Sat May 07, 2022 5:32 pm
>
> 
But there's no release .exe this time. I downloaded Visual Studio and managed to make a DATspeech tool.exe, however, it gets no response when I drag speech.dat onto it. This is my first experience trying to compile something, so I couldn't begin to guess where/if I went wrong.

It's a command line tool. There are some tutorials explaining how to run it.
Check here https://www.google.com/search?client=fi ... ne+program

If I try to run the .exe that I created in a command prompt, nothing happens. And wouldn't I need to tell it what to open anyway?
## Post #61
- Username: Sput
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 30, 2022 3:03 am
- Post datetime: 2022-05-29T19:22:58+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I am having trouble downloading the first link, nothing is happening when I click it.
## Post #62
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-29T19:25:42+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from Sput ↑Mon May 30, 2022 3:22 am at Mon May 30, 2022 3:22 am
>
> 
I am having trouble downloading the first link, nothing is happening when I click it.

Try different browser.
## Post #63
- Username: leeehoang2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 08, 2023 12:04 am
- Post datetime: 2023-05-07T16:12:51+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

Hi, does anybody knows a way to translate mgs2 into another language? I intend to translate it into Vietnamese but i can't find any solutions on google
## Post #64
- Username: Bernard38
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 23, 2023 5:50 pm
- Post datetime: 2023-06-23T09:55:22+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

I'm trying to put all the original japanese audio into the US version of MGS3 Subsistence. I've figured out that VOX.DAT contains all the codec voice lines in the form of .vag files and DEMO.DAT contains all the cutscenes voice lines in the form of .raw files (or .mtaf).

I've tried, using Apache 1.1, to just exchange the entire DAT from one version to another (change TOC, correct size, update file) but it doesn't work. The voice lines don't play.


Using the Konami DAT Utility presented here I can easily unpack all the DAT contents and select only the vag/raw files to put from one version to another, which could potentially work, however I have no idea how to repack these into a DAT. It says that this utility is a 'packer and unpacker' and there is a 'rebuild' option however it is greyed out and I don't know how to use it. Can anyone help?
## Post #65
- Username: DaHeis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 03, 2023 8:53 am
- Post datetime: 2023-10-03T00:57:49+00:00
- Post Title: Re: Metal Gear Solid (series) - Tools

> Reply from glennstavos ↑Sat Mar 26, 2022 1:39 am at Sat Mar 26, 2022 1:39 am
>
> 

I know this is like 2-1 years old but i think the in-game audio files are in archive called mgs4int.ssp inside the init file
