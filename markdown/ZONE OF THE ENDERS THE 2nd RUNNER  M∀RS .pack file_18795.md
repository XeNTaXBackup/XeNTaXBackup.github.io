## Post #1
- Username: cyber212
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 05, 2017 7:20 pm
- Post datetime: 2018-09-10T11:38:57+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

how extract the ".pack" files? hlp
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-10T16:18:40+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

> Reply from cyber212
>
> how extract the ".pack" files? hlp
Upload file samples.
## Post #3
- Username: cyber212
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 05, 2017 7:20 pm
- Post datetime: 2018-09-10T19:44:49+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

[https://mega.nz/#!Cksh0A5Z!5pHdNqx_8yXX ... b53sOGhEw8](https://mega.nz/#!Cksh0A5Z!5pHdNqx_8yXXcqWgFnzUzxhC7bmPT0M5Lb53sOGhEw8)
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-10T21:39:28+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

looks complicated. it's not packed but 'encoded' or 'encrypted'. this archive seems to contain only shader files and lots of text in it.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-10T22:10:24+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

this url is compressed at the end of the file for some reason.
[https://www.gamedev.net/forums/topic/60 ... eam-issue/](https://www.gamedev.net/forums/topic/602143-texture-atlas-seam-issue/)
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-10T22:27:30+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

> Reply from chrrox
>
> this url is compressed at the end of the file for some reason.
https://www.gamedev.net/forums/topic/60 ... eam-issue/

that 'some reason' is developing the port. i know how bad the rendering code runs on emulators or the ps2 emulator out there. i'm sure they had to optimize a good portion of the game to run nicely on x86 and current rendering tech.
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-10T23:18:37+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Yeah it's a weird format. Can we have more samples?
## Post #8
- Username: cyber212
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 05, 2017 7:20 pm
- Post datetime: 2018-09-11T14:16:10+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

> Reply from Gh0stBlade
>
> Yeah it's a weird format. Can we have more samples?
[https://mega.nz/#F!epVUyICZ!WsaKTGHsGjPqrxDFqSkF-g](https://mega.nz/#F!epVUyICZ!WsaKTGHsGjPqrxDFqSkF-g)
## Post #9
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-11T16:02:35+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

same format. and looking at the steam demo data the models and textures might be in the atlas or zoe2 .dat files. still downloading. will mess with it later.

well now. demo been played. ran pretty nice on my craptop. barely any cpu utilisation. had to play in 720p tho. my gpu got no fillrate with bs vram. 

about the data: i'm certain the meshes and animation data are 'reused' from the original game data. the container is identical to the ps2 version, just the offsets are switched to little endian. good luck figuring the data out. probably ps2 format data.

edit: done the atlas file texture dumper. you can find it in your zenhax thread.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-18T09:26:09+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

model, using hex2obj (view links in my sig):



0000001b-mdl.jpg (195.37 KiB) Viewed 322 times
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-18T09:41:21+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

bigger one:



00000011-mdl.jpg (170.1 KiB) Viewed 321 times
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-18T09:47:50+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

character model:



00000031-mdl.jpg (177 KiB) Viewed 321 times


(models from 010.pack of the demo version)
## Post #13
- Username: Sephiroth89
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 09, 2012 1:13 am
- Post datetime: 2018-09-18T19:03:00+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

hey, im interested to extract 3d models from this game, can someone tell me all the steps? ( or link guidelines wuould be ok too) beacuse im feel confused
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-18T19:34:19+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

unpack *.pack files using zoe2_cygames.bms with quickbms.exe (author: aluigi).
Extract meshes from *.mdl file using hex2obj for example (view links in my sig).

Ship mdl from 010.pack:


 ZoE-0000001b.zip
(143.66 KiB) Downloaded 39 times
## Post #15
- Username: Sephiroth89
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 09, 2012 1:13 am
- Post datetime: 2018-09-18T20:14:37+00:00
- Post Title: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

> Reply from shakotay2
>
> unpack *.pack files using zoe2_cygames.bms with quickbms.exe (author: aluigi).
Extract meshes from *.mdl file using hex2obj for example (view links in my sig).

ok i unpacked some mdl files, now i try with hex2obj, hope to understand what to do
 tnx for the advice
## Post #16
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2018-12-04T21:34:02+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Is there any consistent way to use hex2obj for zoe? or another way?
Have got the files extracted and have been trying to use hex2obj on them but no success.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-04T23:12:01+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

> Reply from 09williamsad
>
> Is there any consistent way to use hex2obj for zoe?dunno what "consistent" should mean exactly (hex2obj is intended to be a helper tool with trial 'n error included   ).

edit: a "consistent way" would be to make use of the Make_obj project ([http://forum.xentax.com/viewtopic.php?f=29&t=15955](http://forum.xentax.com/viewtopic.php?f=29&t=15955))
which requires knowledge in 'C', though.

example 0000001b.mdl:
(vertex count assumed to be found at file's beginning, FVFsize is 88 bytes here)
.



ZOE_mdl.png (28.86 KiB) Viewed 68 times
## Post #18
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-12-05T19:20:55+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Can someone provide MDL file samples?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-06T23:10:55+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

some tool to test ZoE .mdl files:


 Make_obj-ZoE.zip
(43.12 KiB) Downloaded 34 times


FVFsize in hex: 58
for chars: 70 (112 decimal)

sample from the ZoE demo, 010.pack
[viewtopic.php?f=16&t=18795&p=144198&hil ... ck#p144198](http://forum.xentax.com/viewtopic.php?f=16&t=18795&p=144198&hilit=+010.pack#p144198)

more mdl files to be found in 008.pack: [viewtopic.php?f=16&t=18795&p=143991#p143991](http://forum.xentax.com/viewtopic.php?f=16&t=18795&p=143991#p143991)

00000005.mdl is a sphere, created .obj file needs to be scaled down by 100 on blender import to get it displayed.

You need to use hex2obj for some "flat" mdl in 008.pack (00000007.mdl for example):
Copy these 6 lines into a .txt file and rename it to whatever.H2O. Load mdl and H2O into hex2obj, 
switch 'noPtC' button to 'Fake' for auto creation of face indices
then press 'mesh' button.

0x0 500
Vb1
88 64
0x6C 7560
020000
0x0 255
## Post #20
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-01-24T14:50:42+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Well I am giving it a shot now.
If anyone wants the suits pre converted with textures and whatever else I can convert, I have them (and a load of other models) uploaded here [https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ](https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ)

Update:
Pretty sure there are models in non mdl format, does not seem to be enough MDLs to account for all models.
## Post #21
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-02-06T19:32:12+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Since this info does not seem to be anywhere online that I can find I will post it here.

The .Dat file structure for zoe2 mars is different to the HD and PS2 versions, the usual extractors do not work.

I tried ninja ripper with Mars but I think Denuovo is blocking it as the game does not launch but ninja ripper 32 bit and the demo works.
Ninja ripper gets the textures, enviroment meshes but the meshes for the frames/mechas are deformed and have no UVs:

This is the LEV (miner frame)
[https://imgur.com/a/AeH2Vl3](https://imgur.com/a/AeH2Vl3)

I also tried the model capture in PCSX2 0.98, that gets the models but it gets the whole scene flattened so each model has to be unflattened with undesired elements removed manually.
## Post #22
- Username: chowderstone34
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 23, 2019 10:25 am
- Post datetime: 2019-07-23T17:59:21+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Has anyone managed to extract the full jehuty model yet?
## Post #23
- Username: chowderstone34
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 23, 2019 10:25 am
- Post datetime: 2019-07-24T20:36:37+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

Attempting to make my own jehuty model using the game as reference.



Capture3.PNG (52.48 KiB) Viewed 264 times
## Post #24
- Username: chowderstone34
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 23, 2019 10:25 am
- Post datetime: 2019-07-26T17:25:31+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

If anyone would like a copy of this model when i'm finished, hmu so i can sen you the file.


Capture 4.PNG (96.66 KiB) Viewed 253 times
## Post #25
- Username: chowderstone34
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 23, 2019 10:25 am
- Post datetime: 2019-08-19T21:17:16+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

[url]Check out this scene in 3D and virtual reality on Sketchfab:

Zone of the Enders: Jehuty (WIP) [https://sketchfab.com/models/cce0acb0a1 ... 79a35d/url](https://sketchfab.com/models/cce0acb0a115404099298d315379a35d/url)]
## Post #26
- Username: Sura Modder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 14, 2018 3:30 am
- Post datetime: 2023-05-07T15:56:26+00:00
- Post Title: Re: ZONE OF THE ENDERS THE 2nd RUNNER : M∀RS ".pack" file

I made a tool for unpacking and repacking these .pack files as the bms script linked here doesn't support repacking and also extracts with hexadecimal filenames with incorrect extensions for few of the files. 

Download this tool in the releases section from the link below:
[https://github.com/Surihix/CyArchiveTool](https://github.com/Surihix/CyArchiveTool)

You can also check out the format struct here:
[https://github.com/Surihix/CyArchiveToo ... tStruct.md](https://github.com/Surihix/CyArchiveTool/blob/master/FormatStruct.md)

Do note that the format is not fully reversed at the time of this post and the unpacked files won't extract with the correct filepaths and filenames as they are hashed or encrypted somewhere in the .pack file. my tool would extract all of the files with a "FILE_" filename with a number appended at the end. the number would indicate the order of the file in the .pack file and you would get a generic .bin as the extension for most of the files that lack a proper header. files that have a proper header or a common beginning string like image files, shader files, json files and few model related files would extract with .dds, .dxb, .json, .mdlbin, and .mdzx extensions.


Additionally, there is also a tool that I made for unpacking and repacking .pac texture archive files stored in the atlas folder of the game. you can download this tool in the releases section from this link here:
[https://github.com/Surihix/Zoe2PacTool](https://github.com/Surihix/Zoe2PacTool)

The struct for this .pac archive format is available in the linked repo above.
