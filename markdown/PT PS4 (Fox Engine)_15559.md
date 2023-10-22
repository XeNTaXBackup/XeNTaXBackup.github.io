## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-01T06:41:25+00:00
- Post Title: PT PS4 (Fox Engine)

Hello people!

The ps4 scene has decrypted PT so all files can be analized.

The backup published contains some binary files from ps4 and a big file called pfs_image.dat (1,25Gb). This big file contains practically the entire game. (So, I don't know if I can publish a download link)

pfs_image.dat contains:

sce_module
sce_sys
chunk1.psarc  (fully extractable and readable)
eboot.bin
pathid_list_ps4.bin
sce_discmap.plt
texture.qar ( I don't know how to extract this file)

Here are some FPK, FPKD & PFTXS files for everyone that want to take a look.

[http://download1619.mediafire.com/tkdda ... player.rar](http://download1619.mediafire.com/tkddaqvav1zg/w936v777o1miakt/player.rar)

[http://download2025.mediafire.com/ymlvi ... common.rar](http://download2025.mediafire.com/ymlvik6jozag/nbz6bq1s3v7dn5d/common.rar)

[http://download1485.mediafire.com/rqy3j ... /start.rar](http://download1485.mediafire.com/rqy3j25rl1wg/dcbtcfufs3hox2i/start.rar)

[http://download1069.mediafire.com/t1ygc ... ending.rar](http://download1069.mediafire.com/t1ygcwu3aykg/ac8y5v88dcdduo5/ending.rar)

[http://download1859.mediafire.com/31tqa ... allway.rar](http://download1859.mediafire.com/31tqaucxjdtg/wedhj7iq1uyaqwj/hallway.rar)
## Post #2
- Username: Jonathan Ingram
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 22, 2015 6:20 am
- Post datetime: 2016-12-01T07:32:33+00:00
- Post Title: PT PS4 (Fox Engine)

FPK & FPKD format is the same as MGSV, but they're encrypted like the LUA and other files. Use MGSV_ResDec and then the FPK tool. PFTXS, on the other hand, isn't encrypted.
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-01T09:44:21+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from Jonathan Ingram
>
> FPK & FPKD format is the same as MGSV, but they're encrypted like the LUA and other files. Use MGSV_ResDec and then the FPK tool. PFTXS, on the other hand, isn't encrypted.

Thanks! 3d models works perfectly. Have you found a method for obtain the textures.qar file?

Edit:

A tool was published for open the PFS_Image Files, but now I can't figure out the textures.qar with correct names.

 

there is a file called pathid_list_ps4.bin that can be used with MGSV_QAR_Tool but crashes.

[https://github.com/maxton/GameArchives/ ... -0.7.0.zip](https://github.com/maxton/GameArchives/releases/download/v0.7.0/Release-0.7.0.zip) (credits to maxton)
## Post #4
- Username: Jonathan Ingram
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 22, 2015 6:20 am
- Post datetime: 2016-12-01T22:58:51+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from luxox18
>
> A tool was published for open the PFS_Image Files, but now I can't figure out the textures.qar with correct names.
Thanks for linking the tool. As for the QAR archive, we're probably gonna have to construct a new dictionary.txt for PT. I noticed there's a good number of files with the full texture name paths in them so I'll look around and try to identify all I can.
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-01T23:02:24+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from Jonathan Ingram
>
> luxox18 wrote:A tool was published for open the PFS_Image Files, but now I can't figure out the textures.qar with correct names.
Thanks for linking the tool. As for the QAR archive, we're probably gonna have to construct a new dictionary.txt for PT. I noticed there's a good number of files with the full texture name paths in them so I'll look around and try to identify all I can.

you can find all names of the textures.qar content in the file pathid_list_ps4.bin but sincerely I'm not very familiarized with fox engine
## Post #6
- Username: Sergeanur
- Rank: advanced
- Number of posts: 53
- Joined date: Fri Dec 30, 2011 7:26 pm
- Post datetime: 2016-12-02T13:16:53+00:00
- Post Title: PT PS4 (Fox Engine)

Texture.qar is the same format as Ground Zeroes, except there's no encryption. Use this to unpack

```
MGSV_QAR_Tool texture.qar -u
```

Though extentions will be wrong until EBOOT.BIN is decrypted.

UPD:
Aha, so it's actually not GZ, it's PastGen TPP with one single difference.
I used the last integer in the file to determine the version: 0x14 for GZ and 0x24 for TPP. However in PT this integer is set to 0x14 while the hash algorithms are TPP ones. So if you want to extract texture.qar with proper extentions change that last integer to 0x24 via Hex Editor.
## Post #7
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2016-12-02T19:25:37+00:00
- Post Title: PT PS4 (Fox Engine)

I don't know if it'll be usefull for you but by reading LUA files I saw:

> -- Register extension information for package creation
>
> if EditableBlockPackage then
>
> 	EditableBlockPackage.RegisterPackageExtensionInfo( {
>
> 			{ "fmdl", false },	-- Drawing model data file
>
> 			{ "geom", false },	-- Atari data file
>
> 			{ "gskl", false },
>
> 			{ "fcnp", false },
>
> 			{ "frdv", false },
>
> 			{ "fdes", false },
>
> 			{ "gani", false },
>
> 			{ "lani", false },
>
> 			{ "sani", false },
>
> 			{ "sand", false },
>
> 			{ "evb", false },
>
> 			{ "mtar", false },
>
> 			{ "caar", false },
>
> 			{ "uif", false },
>
> 			{ "uia", false },
>
> 			{ "uilb", false },
>
> 			{ "uigb", false },
>
> 			{ "mog", false },
>
> 			{ "fclo", false },
>
> 			{ "rdf", false },
>
> 			{ "lba", false }, --locater binary array
>
> 			{ "dmy", false },	-- Dummy file
>
> 			{ "pcsp", false },
>
> 			{ "ladb", false },
>
> 
>
> 			{ "lua", true },	-- Lua Script file
>
> 			{ "sdf", true },
>
> 			{ "fsd", true },
>
> 			{ "lad", true },
>
> 			{ "sim", true },
>
> 			{ "ph", true },
>
> 			{ "phsd", true },
>
> 			{ "tgt", true },
>
> 			{ "bnd", true },
>
> 			{ "des", true },
>
> 			{ "path", true },
>
> 			{ "veh", true },
>
> 			{ "clo", true },	-- Cross configuration file
>
> 			{ "fcnpx", true },	-- Parts Builder · Extended Connect Point File
>
> 			{ "vfxlf", true },
>
> 			{ "vfx", true },	-- Effect / definition file
>
> 			{ "parts", true },	-- Part Builder · Definition File
>
> 			{ "evf", true },
>
> 			{ "fsml", true },
>
> 			{ "fage", true },	-- Motion graph / graph piece file
>
> 			{ "fago", true },	-- Motion graph
>
> 			{ "fag", true },	-- Motion graph · Route graph file
>
> 			{ "fagx", true },	-- Motion graph / layer definition file
>
> 			{ "aibc", true },	-- AI behavior category file
>
> 			{ "aib", true },	-- AI behavior / definition file
>
> 			{ "uil", true },	-- Ui Layout file
>
> 			{ "uig", true },	-- UiGraph file
>
> 			{ "testd", true },	-- Test file
>
> 			{ "fox2", true },	-- Object arrangement / property data file
>
> 			{ "fxp2", true }	-- Unused
>
> 			} )
>
> end

and for peoples want to get model names

> this = {}
>
> 
>
> --Baby
>
> Gimmick.AddPartsPath{ partName = "Baby", path = "/Assets/sh/parts/chara/bab/bab0_main0_def.parts" }
>
> Gimmick.AddMotionPath{ key = "Baby", path = "/Assets/sh/motion/SI_game/fani/bodies/bab0/bab0/bab0_m00_020.gani" }
>
> Gimmick.AddMotionPath{ key = "Baby3", path = "/Assets/sh/motion/SI_game/fani/bodies/bab0/bab0/bab0_m00_030.gani" }
>
> Gimmick.AddMotionPath{ key = "Baby4", path = "/Assets/sh/motion/SI_game/fani/bodies/bab0/bab0/bab0_m00_040.gani" }
>
> 
>
> --Ocho
>
> Gimmick.AddPartsPath{ partName = "Ocho", path = "/Assets/sh/parts/chara/och/och0_main0_def.parts" }
>
> Gimmick.AddMotionPath{ key = "Ocho", path = "/Assets/sh/motion/SI_game/fani/bodies/och0/och0/och0_m01_011.gani" }
>
> Gimmick.AddMotionPath{ key = "OchoStop", path = "/Assets/sh/motion/SI_game/fani/bodies/och0/och0/och0_m01_021.gani" }
>
> Gimmick.AddMotionPath{ key = "OchoDash", path = "/Assets/sh/motion/SI_game/fani/bodies/och0/och0/och0_m01_012.gani" }
>
> 
>
> --CeilLamp
>
> Gimmick.AddPartsPath{ partName = "CeilLamp", path = "/Assets/sh/parts/chara/lte/lte0_main0_def_v00.parts" }
>
> Gimmick.AddMotionPath{ key = "CeilLamp", path = "/Assets/sh/motion/SI_game/fani/bodies/lte0/lte0/lte0_m00_010.gani" }
>
> Gimmick.AddMotionPath{ key = "CeilLampStrong", path = "/Assets/sh/motion/SI_game/fani/bodies/lte0/lte0/lte0_m00_020.gani" }
>
> 
>
> --Freezer
>
> Gimmick.AddPartsPath{ partName = "Freezer", path = "/Assets/sh/parts/chara/frz/frz0_main0_def.parts" }
>
> Gimmick.AddMotionPath{ key = "Freezer", path = "/Assets/sh/motion/SI_game/fani/bodies/frz0/frz0/frz0_m00_010.gani" }
>
> Gimmick.AddMotionPath{ key = "FreezerStrong", path = "/Assets/sh/motion/SI_game/fani/bodies/frz0/frz0/frz0_m00_020.gani" }
>
> 
>
> --Bag
>
> Gimmick.AddPartsPath{ partName = "Bag", path = "/Assets/sh/parts/chara/pab/pab0_main0_def.parts" }
>
> Gimmick.AddMotionPath{ key = "BagTalk", path = "/Assets/sh/motion/SI_game/fani/bodies/pab0/pab0/pab0_m00_010.gani" }
>
> 
>
> return this

PS bis: MtarTool work on P.T MTAR files
## Post #8
- Username: Solidcal
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Apr 30, 2015 4:05 am
- Post datetime: 2016-12-02T19:27:53+00:00
- Post Title: PT PS4 (Fox Engine)

Nice to see more being done with the files. But it seems the player.rar link is down. Might need a reupload of that one.
## Post #9
- Username: caplagrobin
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Oct 07, 2016 2:17 am
- Post datetime: 2016-12-02T19:49:47+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from Solidcal
>
> it seems the player.rar link is down. Might need a reupload of that one.

Are you sure? It's up on my end, just wait a little for it to "repair" the link


Weird models that are in the files but I don't remember being in PT, anywhere:
"DOL" [http://i.imgur.com/tCnUYTX.jpg](http://i.imgur.com/tCnUYTX.jpg)
"HSH" [http://i.imgur.com/Q6cYxGd.jpg](http://i.imgur.com/Q6cYxGd.jpg) 3dsMax: [http://i.imgur.com/1Lo9Wg7.jpg](http://i.imgur.com/1Lo9Wg7.jpg)
Don't know what they are, I don't know what they're doing here and they're odd.
## Post #10
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-02T20:01:27+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from Sergeanur
>
> Texture.qar is the same format as Ground Zeroes, except there's no encryption. Use this to unpack
Code: Select allMGSV_QAR_Tool texture.qar -u
Though extentions will be wrong until EBOOT.BIN is decrypted.

UPD:
Aha, so it's actually not GZ, it's PastGen TPP with one single difference.
I used the last integer in the file to determine the version: 0x14 for GZ and 0x24 for TPP. However in PT this integer is set to 0x14 while the hash algorithms are TPP ones. So if you want to extract texture.qar with proper extentions change that last integer to 0x24 via Hex Editor.

thanks a lot, now the extensions are correct!

also, the EBOOT is already decrypted...
## Post #11
- Username: Solidcal
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Apr 30, 2015 4:05 am
- Post datetime: 2016-12-02T20:20:20+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from caplagrobin
>
> Solidcal wrote:it seems the player.rar link is down. Might need a reupload of that one.

Are you sure? It's up on my end, just wait a little for it to "repair" the link


Weird models that are in the files but I don't remember being in PT, anywhere:
"DOL" http://i.imgur.com/tCnUYTX.jpg
"HSH" http://i.imgur.com/Q6cYxGd.jpg 3dsMax: http://i.imgur.com/1Lo9Wg7.jpg
Don't know what they are, I don't know what they're doing here and they're odd.
Ah now it works, odd. Also I am guessing those models were maybe some of the messed up enemies that were gonna be in the full silent hills game maybe?
## Post #12
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-02T21:26:50+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from caplagrobin
>
> Solidcal wrote:it seems the player.rar link is down. Might need a reupload of that one.

Are you sure? It's up on my end, just wait a little for it to "repair" the link


Weird models that are in the files but I don't remember being in PT, anywhere:
"DOL" http://i.imgur.com/tCnUYTX.jpg
"HSH" http://i.imgur.com/Q6cYxGd.jpg 3dsMax: http://i.imgur.com/1Lo9Wg7.jpg
Don't know what they are, I don't know what they're doing here and they're odd.

HSH model is from the first Silent Hills trailer but DOL I don't know.
## Post #13
- Username: caplagrobin
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Oct 07, 2016 2:17 am
- Post datetime: 2016-12-02T21:34:37+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from luxox18
>
> HSH model is from the first Silent Hills trailer but DOL I don't know.

It is, definitely! [https://youtu.be/gY91vV0rWr4?t=1m2s](https://youtu.be/gY91vV0rWr4?t=1m2s) It's oversized, too. Just what is it doing here...
## Post #14
- Username: PeeTee
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 03, 2016 8:56 am
- Post datetime: 2016-12-03T00:57:42+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from Sergeanur
>
> Texture.qar is the same format as Ground Zeroes, except there's no encryption. Use this to unpack
Code: Select allMGSV_QAR_Tool texture.qar -u
Though extentions will be wrong until EBOOT.BIN is decrypted.

UPD:
Aha, so it's actually not GZ, it's PastGen TPP with one single difference.
I used the last integer in the file to determine the version: 0x14 for GZ and 0x24 for TPP. However in PT this integer is set to 0x14 while the hash algorithms are TPP ones. So if you want to extract texture.qar with proper extentions change that last integer to 0x24 via Hex Editor.

Could you or someone post a screenshot as to what exactly I'm editing in HxD? Thanks!
## Post #15
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-03T09:20:51+00:00
- Post Title: PT PS4 (Fox Engine)

> Reply from PeeTee
>
> Sergeanur wrote:Texture.qar is the same format as Ground Zeroes, except there's no encryption. Use this to unpack
Code: Select allMGSV_QAR_Tool texture.qar -u
Though extentions will be wrong until EBOOT.BIN is decrypted.

UPD:
Aha, so it's actually not GZ, it's PastGen TPP with one single difference.
I used the last integer in the file to determine the version: 0x14 for GZ and 0x24 for TPP. However in PT this integer is set to 0x14 while the hash algorithms are TPP ones. So if you want to extract texture.qar with proper extentions change that last integer to 0x24 via Hex Editor.

Could you or someone post a screenshot as to what exactly I'm editing in HxD? Thanks!
## Post #16
- Username: PeeTee
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 03, 2016 8:56 am
- Post datetime: 2016-12-03T10:35:09+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from luxox18
>
> PeeTee wrote:Sergeanur wrote:Texture.qar is the same format as Ground Zeroes, except there's no encryption. Use this to unpack
Code: Select allMGSV_QAR_Tool texture.qar -u
Though extentions will be wrong until EBOOT.BIN is decrypted.

UPD:
Aha, so it's actually not GZ, it's PastGen TPP with one single difference.
I used the last integer in the file to determine the version: 0x14 for GZ and 0x24 for TPP. However in PT this integer is set to 0x14 while the hash algorithms are TPP ones. So if you want to extract texture.qar with proper extentions change that last integer to 0x24 via Hex Editor.

Could you or someone post a screenshot as to what exactly I'm editing in HxD? Thanks!

Awesome. Thank you so much.

What about when it comes to decrypting the LUA?
## Post #17
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2016-12-03T10:58:24+00:00
- Post Title: Re: PT PS4 (Fox Engine)

For the ones who wants a FTEX dictionary (filenames - hashs), I made this:
[http://pastebin.com/5H2LYGe0](http://pastebin.com/5H2LYGe0)
## Post #18
- Username: Jonathan Ingram
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 22, 2015 6:20 am
- Post datetime: 2016-12-04T00:36:18+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from PeeTee
>
> What about when it comes to decrypting the LUA?
The LUA files out in the open should decrypt just fine with MGSV_ResDec, however, for the one's inside of the FPK/D archives you'll wanna use the GzsTool to unpack the FPKs.
Unfortunately, the ones inside the FPKs are missing their comments, so there's a lot of empty space and needless line breaks where they used to be.
## Post #19
- Username: PeeTee
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 03, 2016 8:56 am
- Post datetime: 2016-12-04T10:32:14+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Final question:

Can someone view the model of the paper bag, and see if there's anything inside of it?

Or just straight up post all the models as they're listed?
## Post #20
- Username: caplagrobin
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Oct 07, 2016 2:17 am
- Post datetime: 2016-12-04T10:42:20+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from PeeTee
>
> Final question:

Can someone view the model of the paper bag, and see if there's anything inside of it?
[http://i.imgur.com/aPpzlMG.jpg](http://i.imgur.com/aPpzlMG.jpg)
Empty.
## Post #21
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-12-05T12:58:59+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Here's a dictionary for the texture.qar with all textures named, based off the pathid_list_ps4 file:
[http://pastebin.com/raw/Sx7dgktA](http://pastebin.com/raw/Sx7dgktA)

[https://github.com/emoose/MGSV-QAR-Dictionary-Project](https://github.com/emoose/MGSV-QAR-Dictionary-Project) has also been updated with these filenames 

Edit: for anyone interested, a small guide on unpacking PT, hopefully I didn't miss anything :

> Downloads:
>
> - GameArchives: https://github.com/maxton/GameArchives/releases
>
> - psarc-138.002: http://www.mediafire.com/file/aegbgpkm3xfot80/psarc.zip
>
> - MGSV_ResDec: https://www.dropbox.com/s/xg9slfszkyf0w ... ResDec.rar
>
> - GzsTool: https://github.com/Atvaark/GzsTool/releases
>
> - MGSV QAR Tool: https://www.dropbox.com/s/0rtpumx2mxsja ... R_Tool.rar
>
> 
>
> pfs_image.dat:
>
> - Use GameArchives to open pfs_image.dat and extract chunk1.psarc & texture.qar
>
> 
>
> chunk1.psarc:
>
> - Use psarc to extract chunk1.psarc:
>
> psarc.exe extract --input=chunk1.psarc --to=chunk1_ext
>
> - Copy MGSV_ResDec to extracted chunk1.psarc folder, in that folder create .bat file with the following:
>
> @echo off
>
> FOR /r %%X IN (*.lua, *.fpk, *.fpkd, *.json) DO (
>
>     MGSV_ResDec.exe %%X
>
> )
>
> - Run the .bat file you created, once it's finished all extracted chunk1.psarc files should be decrypted
>
> 
>
> - Once decrypted, to unpack the .fpk/.fpkd files copy GzsTool to extracted chunk1.psarc folder
>
> - Open a command prompt to the extracted chunk1.psarc folder and run the following (don't forget the . at the end):
>
> GzsTool.exe .
>
> - All .fpk/.fpkd files should now be unpacked
>
> 
>
> texture.qar:
>
> - Extract MGSV QAR Tool to the same folder as texture.qar
>
> - Replace the contents of dictionary.txt with http://pastebin.com/raw/Sx7dgktA
>
> - Open texture.qar with a hex editor, skip to the end of the file and change the last 4 bytes "14 00 00 00" to "24 00 00 00"
>
> - Open a command prompt to the folder with texture.qar and QAR tool, and run the following:
>
> MGSV_QAR_Tool.exe texture.qar -u
>
> - Once it's completed the texture.qar file should be fully extracted to a 'texture' folder
>
> 
>
> Credits to everyone making Fox Engine modding possible
## Post #22
- Username: Letal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 05, 2016 9:58 pm
- Post datetime: 2016-12-05T14:09:16+00:00
- Post Title: Re: PT PS4 (Fox Engine)

I'm sorry I probably look like a stupid noob asking that... but I'm a 3D artist long time fan of Silent Hill and I have no experience with the fox engine...

Did someone make an archive with the 3D models as fbx or obj, and textures as targa or something like that? Is that even possible? 'cause I'd really like to see those models from upclose and mess around with shaders and stuff.

Sorry for the possible terrible english.

You guys just made me so happy by dissecting this awesome game!
## Post #23
- Username: Jonathan Ingram
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 22, 2015 6:20 am
- Post datetime: 2016-12-05T20:20:43+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from Letal
>
> Did someone make an archive with the 3D models as fbx or obj, and textures as targa or something like that? Is that even possible? 'cause I'd really like to see those models from upclose and mess around with shaders and stuff.
[https://facepunch.com/showthread.php?t=1463516](https://facepunch.com/showthread.php?t=1463516)
## Post #24
- Username: Letal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 05, 2016 9:58 pm
- Post datetime: 2016-12-06T08:45:55+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Thanks a lot!
## Post #25
- Username: Zets89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 09, 2016 5:16 pm
- Post datetime: 2016-12-09T09:25:03+00:00
- Post Title: Re: PT PS4 (Fox Engine)

So did you get the pfs_image.dat file from the P.T. pkg? How did you do that with the decryption and extraction?
## Post #26
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-12-10T08:02:18+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from Zets89
>
> So did you get the pfs_image.dat file from the P.T. pkg? How did you do that with the decryption and extraction?
Don't think they've mentioned the method they used publicly yet, IIRC though for games that run on 1.76 or lower you can mount the pkg file and FTP the decrypted pfs_image.dat out from the system (pretty sure I saw a guide on psxhax for it before but can't find it right now)

That's probably the only way to do it so far until someone extracts the decryption keys from the console, which AFAIK there hasn't been much progress on 

EDIT: found the guide, might break a rule to link it though but you should be able to find it searching for "ps4 pfs ftp" on google
They also mention in that guide that eboot.bin is yet to be decrypted, but in the PT decrypted torrent the eboot.bin seems decrypted enough to me, not sure how they did that but I'd guess it was probably dumped from memory while the games running.
## Post #27
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2016-12-12T22:01:53+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Hi!

I have compared the files and I have seen that there are many similarities with ground zeroes. In fact, I've replaced some files and ground zeroes runs normally. I'm trying to load all the pt files but at some point it gets stuck. I'll see if I find out what it is.
## Post #28
- Username: CreaseInTime
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 13, 2016 11:59 am
- Post datetime: 2016-12-13T04:04:05+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Hi all, I'm visiting from Facepunch and am currently working on porting all the released assets to Source Filmmaker, but I've hit a slight snag as I'm missing a few textures. If anyone has managed to get all of them, I have a short list of the ones I need.

```
shsb_ctwk001
shsb_stpl001_vrtn001
shsb_desk001 (texture always comes out black)

```


If anyone has/had any success finding these textures, I would greatly appreciate a download for them! Thanks so much!
## Post #29
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2016-12-13T08:04:39+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Maybe inside of some fpk, for what model you need it?
## Post #30
- Username: CreaseInTime
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 13, 2016 11:59 am
- Post datetime: 2016-12-13T16:29:18+00:00
- Post Title: Re: PT PS4 (Fox Engine)

The list I provided actually are the model names, the textures are usually named the same except for an '_bsm' suffix.
## Post #31
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2016-12-13T20:09:46+00:00
- Post Title: Re: PT PS4 (Fox Engine)

I'll take a look.
## Post #32
- Username: CreaseInTime
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 13, 2016 11:59 am
- Post datetime: 2016-12-14T01:54:03+00:00
- Post Title: Re: PT PS4 (Fox Engine)

I'm also apparently missing the texture for the bottles, shsb_hous001_bn_bsm. I can only find shsb_hous001_bn_bsm_alp and shsb_hous001_bn_nrm, a subtexture and normal texture of the bottles' texture.
## Post #33
- Username: minilem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 18, 2017 4:50 am
- Post datetime: 2017-04-17T21:01:34+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from emoose
>
> Here's a dictionary for the texture.qar with all textures named, based off the pathid_list_ps4 file:
http://pastebin.com/raw/Sx7dgktA

https://github.com/emoose/MGSV-QAR-Dictionary-Project has also been updated with these filenames 

Edit: for anyone interested, a small guide on unpacking PT, hopefully I didn't miss anything :

Downloads:
- GameArchives: https://github.com/maxton/GameArchives/releases
- psarc-138.002: http://www.mediafire.com/file/aegbgpkm3xfot80/psarc.zip
- MGSV_ResDec: https://www.dropbox.com/s/xg9slfszkyf0w ... ResDec.rar
- GzsTool: https://github.com/Atvaark/GzsTool/releases
- MGSV QAR Tool: https://www.dropbox.com/s/0rtpumx2mxsja ... R_Tool.rar

pfs_image.dat:
- Use GameArchives to open pfs_image.dat and extract chunk1.psarc & texture.qar

chunk1.psarc:
- Use psarc to extract chunk1.psarc:
psarc.exe extract --input=chunk1.psarc --to=chunk1_ext
- Copy MGSV_ResDec to extracted chunk1.psarc folder, in that folder create .bat file with the following:
@echo off
FOR /r %%X IN (*.lua, *.fpk, *.fpkd, *.json) DO (
    MGSV_ResDec.exe %%X
)
- Run the .bat file you created, once it's finished all extracted chunk1.psarc files should be decrypted

- Once decrypted, to unpack the .fpk/.fpkd files copy GzsTool to extracted chunk1.psarc folder
- Open a command prompt to the extracted chunk1.psarc folder and run the following (don't forget the . at the end):
GzsTool.exe .
- All .fpk/.fpkd files should now be unpacked

texture.qar:
- Extract MGSV QAR Tool to the same folder as texture.qar
- Replace the contents of dictionary.txt with http://pastebin.com/raw/Sx7dgktA
- Open texture.qar with a hex editor, skip to the end of the file and change the last 4 bytes "14 00 00 00" to "24 00 00 00"
- Open a command prompt to the folder with texture.qar and QAR tool, and run the following:
MGSV_QAR_Tool.exe texture.qar -u
- Once it's completed the texture.qar file should be fully extracted to a 'texture' folder

Credits to everyone making Fox Engine modding possible

Thanks for this! I've had no issues getting the textures and am having heaps of fun playing with a few of them. However, I can't successfully use MGSV_RecDec.exe to decrypt the extracted chunk1_ext files. I've followed every step and it just doesn't seem to want to play ball. the .bat file is fine and i've checked it over and over. Tried a few different versions of MGSV_RecDec.exe. 

Even stranger, the first error I was having seems to have vanished. If I removed @Echo. I would see the problem was "Can't load input file". After playing with that for a while I scrapped it all and started again. Now my .bat file doesn't seem to want to do anything. It vanishes as quickly as it appears regardless of what I try. Any help would be much appreciated.
## Post #34
- Username: JasonBlack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 19, 2011 8:55 pm
- Post datetime: 2017-05-03T23:11:56+00:00
- Post Title: Re: PT PS4 (Fox Engine)

Same problem here following the steps. Getting the "ERROR: Can't open input file" message.

[Edit] Been a while since I tried my hand at this... Put the MGSV_ResDec.exe in a folder with an FPK file such as \chunk1_ext\as\sh\level\common and drag that FPK file onto the EXE. You catch a glimpse of the cmd window say it's decrypted and it creates a backup.

Then drop the same FPK file onto GzsTool.exe and you should have a load of unpacked Fox Engine FMDL files.

FMDL files are converted with Fox Engine Model Studio which is hard to get for some reason. The author takes it down when they're inbetween versions?
Here is the recommended version for PT editing: [http://www.mediafire.com/file/aj64l8jey ... Studio.exe](http://www.mediafire.com/file/aj64l8jeyrubwy2/FoxModelStudio.exe)

[Edit 2] Latest version Fox Engine Model Studio is mgs5_FMS.zip, here: [http://cra0kalo.com/public/](http://cra0kalo.com/public/)
## Post #35
- Username: minilem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 18, 2017 4:50 am
- Post datetime: 2017-05-04T23:07:40+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from JasonBlack
>
> Same problem here following the steps. Getting the "ERROR: Can't open input file" message.

[Edit] Been a while since I tried my hand at this... Put the MGSV_ResDec.exe in a folder with an FPK file such as \chunk1_ext\as\sh\level\common and drag that FPK file onto the EXE. You catch a glimpse of the cmd window say it's decrypted and it creates a backup.

Then drop the same FPK file onto GzsTool.exe and you should have a load of unpacked Fox Engine FMDL files.

FMDL files are converted with Fox Engine Model Studio which is hard to get for some reason. The author takes it down when they're inbetween versions?
Here is the recommended version for PT editing: http://www.mediafire.com/file/aj64l8jey ... Studio.exe

This worked perfectly for the file you used as an example! Thanks a lot! However, trying to do it on the FPK files in "ending"  "hallway" and "start" folders are causing issues still. Not the same issue but still issues. The Gzstool.exe causes a crash!
## Post #36
- Username: JasonBlack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 19, 2011 8:55 pm
- Post datetime: 2017-05-05T11:09:58+00:00
- Post Title: Re: PT PS4 (Fox Engine)

I tried this method on ending.fpk with GzsTool v.0.5.2.2 which I have in a folder full of other misc files and it crashed with the cmd prompt showing me a load of input not valid information that went right over my head.

Older version v.0.4.3.0 in its own folder, with a file called Cityhash.dll included along with the zlib, dictionary and config files, worked just fine.

Who knows where I downloaded it back in late 2015, I'll just put it up here for ya: [http://www.mediafire.com/file/7r711mjlj ... ol_4_3.zip](http://www.mediafire.com/file/7r711mjlj7xiaoj/GzsTool_4_3.zip)

[Edit] The zip I uploaded appears to have all the same files originally available from here: [https://github.com/Atvaark/GzsTool/releases/tag/v0.4.3](https://github.com/Atvaark/GzsTool/releases/tag/v0.4.3)
I suspect I may've thought the cityhash.dll or one of the other files in my messy collection of tools, was junk and deleted it or one of the others?

[Edit 2] Latest version (5.2.3) in its own folder with all its dependencies seems to work well.
## Post #37
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2017-05-29T13:33:11+00:00
- Post Title: Re: PT PS4 (Fox Engine)

> Reply from Jonathan Ingram
>
> luxox18 wrote:A tool was published for open the PFS_Image Files, but now I can't figure out the textures.qar with correct names.
Thanks for linking the tool. As for the QAR archive, we're probably gonna have to construct a new dictionary.txt for PT. I noticed there's a good number of files with the full texture name paths in them so I'll look around and try to identify all I can.

How do you go about generating the dictionary?
Browsing the exe?
## Post #38
- Username: DeathTempler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 26, 2018 1:33 pm
- Post datetime: 2018-06-26T05:35:18+00:00
- Post Title: Re: PT PS4 (Fox Engine)

The links seem to be dead, is there any other way to get these downloads now?
