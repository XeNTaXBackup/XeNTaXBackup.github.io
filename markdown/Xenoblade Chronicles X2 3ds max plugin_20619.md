## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-04T20:54:11+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

The plugin will let you to import models and animations.
In addition, it can export textures to .dds or .png format, while loading model.
Now I know, that there is already one made by me like year or so old, however it runs on maxscript and was real messy mess for both me, and user.
This plugin is much faster and safer than maxscript one.
I'm aware of making a possible duplicate, however since this plugin should be released a year ago, shit happened, and since has been abandoned.
Due the fact, that plugin is relatively new and have nothing to do with older maxscript one, it's logically better for me to make another thread, to not generate necessary chaos inside single thread.



Master page for 3ds max plugin.
Master page for toolset.


I will also require from you any and every feedback you can think of.
For plugin, you can create issues in repo.
For everything else here, or on blog. 
Thank you.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-06-06T01:26:53+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

This is awesome dude, great work.
I was wondering if there are plans to support environment meshes such as props and the maps at all.
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-06T14:04:56+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from lionheartuk ↑Thu Jun 06, 2019 9:26 am at Thu Jun 06, 2019 9:26 am
>
> 
This is awesome dude, great work.
I was wondering if there are plans to support environment meshes such as props and the maps at all.

Props are using oj prefix. (oj.cpk?)
Map support is coming up, but only for XenobladeX.
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-17T12:46:12+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

XenoToolset V1 has been released.

Added casmExtract (Xenoblade X map converter/extractor)
Added mdoTextureExtract (Extracts textures from camdo/wimdo/wismt(DRSM) files)
Added xenoTextureConvert (Converts MTXT/LBIM into DDS/PNG formats)

XenoMax V1.1 has been released.

Added support for loading instanced meshes and external textures.
Small fixes.
## Post #5
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-06-17T14:37:21+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

I tried to import the .wimdo models in 3ds max 2015, and it crashed (tried it multiple times, one of which gave me a actual error), can you fix the compatibility with 3ds max 2015 please?
## Post #6
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-06-18T00:24:33+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

Any chances of ya adding support for XC2 maps?

Also works perfectly for me on 3ds max 2016, altho seems like it doesn't grab vertex normals properly, and seems like some animations changes vertex weights on some meshes.
## Post #7
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-18T14:31:36+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from demonslayerx8 ↑Tue Jun 18, 2019 8:24 am at Tue Jun 18, 2019 8:24 am
>
> 
Any chances of ya adding support for XC2 maps?

Also works perfectly for me on 3ds max 2016, altho seems like it doesn't grab vertex normals properly, and seems like some animations changes vertex weights on some meshes.

Can you please tell a name of the file and a name of the animation that causes vertex weights glitch?
Can you also post a name of the file causing vertex normals glitch?
## Post #8
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-06-19T00:41:11+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from PredatorCZ ↑Tue Jun 18, 2019 10:31 pm at Tue Jun 18, 2019 10:31 pm
>
> 
demonslayerx8 wrote: ↑Tue Jun 18, 2019 8:24 am
Any chances of ya adding support for XC2 maps?

Also works perfectly for me on 3ds max 2016, altho seems like it doesn't grab vertex normals properly, and seems like some animations changes vertex weights on some meshes.


Can you please tell a name of the file and a name of the animation that causes vertex weights glitch?
Can you also post a name of the file causing vertex normals glitch?
for animation glitches
np453201 (importing any NPC animations seems to cause the whole bone structure to get all messed up)


Vertex normal and weight glitches when importing certain animations
bl300901
animation: battle_eye (or something close like that)
## Post #9
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-21T18:18:50+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from demonslayerx8 ↑Wed Jun 19, 2019 8:41 am at Wed Jun 19, 2019 8:41 am
>
> 
Vertex normal and weight glitches when importing certain animations
bl300901
animation: battle_eye (or something close like that)

Some animations are used as additive animations, these are not supported (yet?).
I didn't knew, that they are even using those.
As for the vertex weight and vertex normal glitches you mentioned, they are caused by these animations.
## Post #10
- Username: MACandCHEEZWIZ1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 26, 2019 7:46 am
- Post datetime: 2019-06-25T23:53:54+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

Hi, and thanks for your hard work. I've recently been trying to get to the point where I can view Xenoblade 2 models, and I'm almost there.

I'm using Autodesk 3ds Max 2018, and I downloaded your releases for XenoMax, HavokMax, and XenoToolset. When I load models, their textures don't seem to come with them despite being part of the WIMDO file. Some textures partially loaded for Pyra once, but I don't know how to replicate that. How might I go about getting them to load properly?

Edit: I also wanted to ask about bl000302.mot. It doesn't seem to have any animation names associated with it and it crashed 3ds Max when I tried to load it for bl000302.wimdo. It seems to specifically be used for this event instance of a certain character
[https://xenoblade.github.io/xb2/bdat/co ... .html#1074](https://xenoblade.github.io/xb2/bdat/common/CHR_Bl.html#1074)
But I can't figure out what its purpose might be.
## Post #11
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-26T08:10:55+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from MACandCHEEZWIZ1 ↑Wed Jun 26, 2019 7:53 am at Wed Jun 26, 2019 7:53 am
>
> 
I'm using Autodesk 3ds Max 2018, and I downloaded your releases for XenoMax, HavokMax, and XenoToolset. When I load models, their textures don't seem to come with them despite being part of the WIMDO file. Some textures partially loaded for Pyra once, but I don't know how to replicate that. How might I go about getting them to load properly?

All necessary calls are in XenoMax project. 
If you're talking about applying textures to model, there is no specific way to replicate material flowchart.
Their materials are node based (similar/same to materials in Unreal Engine 4). I had spent a lot of time with reversing materials, but determining which nodes are used and how they're connected, will be piece of cake. Best way, would be to decompile shader program, however, there are not decompilers for wiiu shaders (but there is research like Decaf, CEMU also decompiles shaders, but it's closed source), I don't think there's any research for switch shaders at all (prolly yuzu have some). So basically it's a really long shot to add support for materials. Only thing it can do, is to load samplers for each material, then decide how to apply texture based on it's name.

> Reply from MACandCHEEZWIZ1 ↑Wed Jun 26, 2019 7:53 am at Wed Jun 26, 2019 7:53 am
>
> 
Edit: I also wanted to ask about bl000302.mot. It doesn't seem to have any animation names associated with it and it crashed 3ds Max when I tried to load it for bl000302.wimdo. It seems to specifically be used for this event instance of a certain character.

I don't have wimdo of that model. Is that from an update? 00030x should be pneuma.
## Post #12
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-06-26T20:29:45+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

.motstm_data archive files can be renamed into .anm files and can be used with this plugin, but it only loads one animation from the .motstm_data archive, can you add in support for remaining animations inside the .motstm_data files?
## Post #13
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-26T22:35:53+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from andree ↑Thu Jun 27, 2019 4:29 am at Thu Jun 27, 2019 4:29 am
>
> 
.motstm_data archive files can be renamed into .anm files and can be used with this plugin, but it only loads one animation from the .motstm_data archive, can you add in support for remaining animations inside the .motstm_data files?

motstm_data is a stream file, motstm is TOC, I should be able to make bms script for extracting files...
Also what's on the image?
## Post #14
- Username: MACandCHEEZWIZ1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 26, 2019 7:46 am
- Post datetime: 2019-06-27T14:12:01+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from MACandCHEEZWIZ1 ↑Wed Jun 26, 2019 7:53 am at Wed Jun 26, 2019 7:53 am
>
> 
Edit: I also wanted to ask about bl000302.mot. It doesn't seem to have any animation names associated with it and it crashed 3ds Max when I tried to load it for bl000302.wimdo. It seems to specifically be used for this event instance of a certain character.

I don't have wimdo of that model. Is that from an update? 00030x should be pneuma.
[/quote]

The model should be the standard bl000301.mot (Pneuma). The datamine shows that there are two separate Pneumas, with the second one at index 1074 having the debug name 覚醒ホムラ（イベント用） Awakened Homura (for event). I figure this specific instance of her is used for specific cutscenes but I was hoping that the specific motion associated with the instance (bl000302.mot) would confirm exactly what she was used for. When I tried using a save editor to insert her into the game with that motion, she's frozen in place like a model without motions applied, but of course I'd have to find the correct scenario in which it's used. Since it crashes 3ds Max when I try to load it for her and doesn't even have any animation names associated with it, I don't know what to make of it myself.
## Post #15
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-28T15:29:28+00:00
- Post Title: Xenoblade Chronicles X/2 3ds max plugin

> Reply from MACandCHEEZWIZ1 ↑Thu Jun 27, 2019 10:12 pm at Thu Jun 27, 2019 10:12 pm
>
> 
The datamine shows that there are two separate Pneumas, with the second one at index 1074 having the debug name 覚醒ホムラ（イベント用） Awakened Homura (for event). I figure this specific instance of her is used for specific cutscenes but I was hoping that the specific motion associated with the instance (bl000302.mot) would confirm exactly what she was used for. When I tried using a save editor to insert her into the game with that motion, she's frozen in place like a model without motions applied, but of course I'd have to find the correct scenario in which it's used. Since it crashes 3ds Max when I try to load it for her and doesn't even have any animation names associated with it, I don't know what to make of it myself.

The event/cutscene animations are stored in motstm files, or in event/mot folder.
bl000302.mot doesn't contain any animation data, only state machine.
## Post #16
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-07-01T22:54:37+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from PredatorCZ ↑Thu Jun 27, 2019 6:35 am at Thu Jun 27, 2019 6:35 am
>
> 
andree wrote: ↑Thu Jun 27, 2019 4:29 am
.motstm_data archive files can be renamed into .anm files and can be used with this plugin, but it only loads one animation from the .motstm_data archive, can you add in support for remaining animations inside the .motstm_data files?


motstm_data is a stream file, motstm is TOC, I should be able to make bms script for extracting files...
Are you still working on it?
## Post #17
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2019-07-26T01:04:13+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Any update on this?
## Post #18
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2019-08-27T16:37:43+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

bump
## Post #19
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-09-19T21:28:54+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

What is taking for this too long, can someone make a fork of the 3ds max plugin?
## Post #20
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2019-10-11T16:30:47+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Bump
## Post #21
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-12-08T14:25:36+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

XenoMax v1.2 has been released

Added support for global framed animations.  #1 #5
Fixed some crash exceptions. #6 
Fixed end frame animation glitches.
Rearranged tab order for dialogs.
Added key shortcuts for dialogs.
Added support for 2020.

A new checkbox in the Animation Import dialog has been added to import global framed animations.
## Post #22
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-05-25T10:15:35+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Just to let ya know, Xenoblade Chronicles Definitive Edition works w/o textures checked, if it's checked, it'll just crash. Reason why is cause most of the textures are BC7 format.


was able to export the raw data for the textures, and used RawTex to figure out the format.


Also, instead of .arc files now, it now uses .chr files, which is shared with multiple models
## Post #23
- Username: Gremkin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 22, 2020 7:05 pm
- Post datetime: 2020-07-01T05:56:30+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Feeling really stupid with this, and feel like I am missing something really obvious with it all.
When importing models into 3DS Max 2018, I only get textures on a few models.
Rest of the time they are grey, is there something I am meant to do to get the textures to load all the time?
Then textures are exporting to a separate folder.
But if I export the model from 3DS Max the textures are staying grey.
Any help will be appreciated!



received_3108180635909733.jpeg (207.11 KiB) Viewed 262 times
## Post #24
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-07-08T23:48:45+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

If anyone is interested in joining a discord server for xenoblade ripping. PM me.
## Post #25
- Username: lucidgate
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 13, 2020 1:08 am
- Post datetime: 2020-08-13T00:26:08+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Hey guys I've tried to use this tool and it seems to work but I'm having trouble extracting my chr_pc.cpk file which I think the main character models and outfits are because I can't find them anywhere else.
Is someone able to send me the Lin and Elma models with their outfits/textures if they are accessible from that file?
## Post #26
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2020-10-13T03:54:50+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

I dont really check xentax a lot so if ppl wanna join
[https://discord.gg/27Wz4QB](https://discord.gg/27Wz4QB)
## Post #27
- Username: alazeldorky
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 23, 2020 11:12 am
- Post datetime: 2020-12-23T04:05:22+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from demonslayerx8 ↑Mon May 25, 2020 6:15 pm at Mon May 25, 2020 6:15 pm
>
> 
Just to let ya know, Xenoblade Chronicles Definitive Edition works w/o textures checked, if it's checked, it'll just crash. Reason why is cause most of the textures are BC7 format.


was able to export the raw data for the textures, and used RawTex to figure out the format.


Also, instead of .arc files now, it now uses .chr files, which is shared with multiple models

How were you able to export out the textures?
## Post #28
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-12-23T04:29:25+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from alazeldorky ↑Wed Dec 23, 2020 12:05 pm at Wed Dec 23, 2020 12:05 pm
>
> 
demonslayerx8 wrote: ↑Mon May 25, 2020 6:15 pm
Just to let ya know, Xenoblade Chronicles Definitive Edition works w/o textures checked, if it's checked, it'll just crash. Reason why is cause most of the textures are BC7 format.


was able to export the raw data for the textures, and used RawTex to figure out the format.


Also, instead of .arc files now, it now uses .chr files, which is shared with multiple models




How were you able to export out the textures?
via hex editing and exporting all the textures into a single BNTX, then using a bntx bms script to extract. It's a tedious process.
## Post #29
- Username: alazeldorky
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 23, 2020 11:12 am
- Post datetime: 2020-12-23T04:41:08+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from demonslayerx8 ↑Wed Dec 23, 2020 12:29 pm at Wed Dec 23, 2020 12:29 pm
>
> 
alazeldorky wrote: ↑Wed Dec 23, 2020 12:05 pm
demonslayerx8 wrote: ↑Mon May 25, 2020 6:15 pm
Just to let ya know, Xenoblade Chronicles Definitive Edition works w/o textures checked, if it's checked, it'll just crash. Reason why is cause most of the textures are BC7 format.


was able to export the raw data for the textures, and used RawTex to figure out the format.


Also, instead of .arc files now, it now uses .chr files, which is shared with multiple models




How were you able to export out the textures?

via hex editing and exporting all the textures into a single BNTX, then using a bntx bms script to extract. It's a tedious process.

Yikes. I've been trying to get the textures for Vanea (NP630109) but there only seems to be a face texture and nothing else....which seems wrong
## Post #30
- Username: Rayved
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Jun 21, 2011 10:46 am
- Post datetime: 2021-02-18T01:00:03+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Are there any plans to get an exporter working for this? I'd like to mod characters and textures and play with them in game.
## Post #31
- Username: christiankin2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 20, 2021 5:56 am
- Post datetime: 2021-02-19T23:10:10+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Please make a video tutorial on how to use this. I have ,nop files and idk how to use this.
## Post #32
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2021-02-21T14:20:53+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from christiankin2 ↑Sat Feb 20, 2021 7:10 am at Sat Feb 20, 2021 7:10 am
>
> 
Please make a video tutorial on how to use this. I have ,nop files and idk how to use this.

iirc, .nop files are audio files in XC2
## Post #33
- Username: someoneelse2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 25, 2016 10:44 am
- Post datetime: 2021-05-03T23:25:04+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from PredatorCZ ↑Wed Jun 05, 2019 4:54 am at Wed Jun 05, 2019 4:54 am
>
> 
The plugin will let you to import models and animations.
In addition, it can export textures to .dds or .png format, while loading model.

Hello!
I used your xenoTextureConvert and successfully converted catex file to dds. But now i am heaving problem converting that file back to catex
File is containing gamepad button icon textures


I appreciate help!

P.S
i added original file to attach
[common_bc3_02.zip](https://xentaxbackup.github.io/file/20042_common_bc3_02.zip)
## Post #34
- Username: popoy101
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 20, 2022 4:19 pm
- Post datetime: 2022-05-20T08:22:10+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

I have a small question to ask. Where is the program to launch the plugin. I'm really new to this!
## Post #35
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-07-24T04:28:25+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Any plans to update the plugin to support models from Xenoblade 3?
## Post #36
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-07-24T12:40:44+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

Having an issue with the new XBC3 files. Seems you must load each .wimdo file manually, if tried in batch it fails and program just crashes. Do you know a way to change the script to read both .wimdo and .wimst at the same time on import ?
[](https://ibb.co/yfgYKCW)
## Post #37
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-07-24T16:04:00+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

XenoMax is discontinued in flavor of a new tool that PredatorCZ is working on. 
EDIT: I forgot to say that the new tool is a replacement to XenoMax.
## Post #38
- Username: DemonicDevil
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 23, 2016 12:54 pm
- Post datetime: 2022-08-04T02:14:53+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from Sharppy ↑Sun Jul 24, 2022 8:40 pm at Sun Jul 24, 2022 8:40 pm
>
> 
Having an issue with the new XBC3 files. Seems you must load each .wimdo file manually, if tried in batch it fails and program just crashes. Do you know a way to change the script to read both .wimdo and .wimst at the same time on import ?

I used the XC2 Decompiler on my Riku's .wimdo and now it's broken permanently... ; ; May you drop a link for a basic FBX of him?

Texture export also fails to create alphas it seems.

> Reply from andree ↑Mon Jul 25, 2022 12:04 am at Mon Jul 25, 2022 12:04 am
>
> 
XenoMax is discontinued in flavor of a new tool that PredatorCZ is working on. 
EDIT: I forgot to say that the new tool is a replacement to XenoMax.

Did they confirm this on Github? '3'
## Post #39
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-08-05T06:40:29+00:00
- Post Title: Re: Xenoblade Chronicles X/2 3ds max plugin

> Reply from DemonicDevil ↑Thu Aug 04, 2022 10:14 am at Thu Aug 04, 2022 10:14 am
>
> 
Sharppy wrote: ↑Sun Jul 24, 2022 8:40 pm
Having an issue with the new XBC3 files. Seems you must load each .wimdo file manually, if tried in batch it fails and program just crashes. Do you know a way to change the script to read both .wimdo and .wimst at the same time on import ?



I used the XC2 Decompiler on my Riku's .wimdo and now it's broken permanently... ; ; May you drop a link for a basic FBX of him?

Texture export also fails to create alphas it seems.
andree wrote: ↑Mon Jul 25, 2022 12:04 am
XenoMax is discontinued in flavor of a new tool that PredatorCZ is working on. 
EDIT: I forgot to say that the new tool is a replacement to XenoMax.


Did they confirm this on Github? '3'
Yes.
