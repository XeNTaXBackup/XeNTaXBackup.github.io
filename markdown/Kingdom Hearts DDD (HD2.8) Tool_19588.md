## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-04T01:17:30+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

Tools for loading models and animations from the PS4/PC versions of Dream Drop Distance. It will load the models with the remastered GNF/DDS textures. Character/Monster/Weapon stuff seems to work fine. Maps are loaded too, but not sure how complete they are, or if everything is placed correctly. I don't know about the rest, give it a try yourself. 

(NEW) Animation Tool (PC)
[viewtopic.php?p=172939#p172939](https://forum.xentax.com/viewtopic.php?p=172939#p172939)

Animation Tool (PS4)
[viewtopic.php?p=169270#p169270](https://forum.xentax.com/viewtopic.php?p=169270#p169270)

Tool overview and example exported model



How to use

Load

PMO/PMP : Loads a single model file (PMO) or map file (PMP)
Load Folder: Adds all the PMO/PMP files inside the selected folder to the list. You can load them by selecting them from the list.
Export

NEX : Exports the model in custom binary format (.nexh), intended to be loaded by Noesis. Noesis script for this format : Nexh Script
OBJ: Exports the model in OBJ format. Might be a better option for maps.
PNG : Exports the textures in PNG format.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/4zv02pel ... x.rar/file](https://www.mediafire.com/file/4zv02pel88fn1n9/KH3DViewer_FixTex.rar/file)

Some maps and weapons loaded



Credits
GNF Loader - [Scarlet](https://github.com/xdanieldzd/Scarlet) by xdanieldzd
## Post #2
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-03-11T02:35:24+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

Will you be uploading the PS4 models?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-11T09:32:30+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from wonka1004 ↑Mon Mar 11, 2019 10:35 am at Mon Mar 11, 2019 10:35 am
>
> 
Will you be uploading the PS4 models?
No, I won't be sharing the extracted models. Just the tool.
## Post #4
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-03-11T12:18:49+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

So then would I have to extract the models from 2.8 directly? If so, how? I understand that it’s probably a long process, so if you don’t want to go into it, that’s fine
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-11T15:57:31+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

Google how to dump/get ps4 game pkg files and how to extract them. Once you extract the pkg you will have 2 .psarc files. Use Noesis to extract them and get the PMO/PMP files. Finally you can load them with my tool.
## Post #6
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-03-13T01:41:20+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

So I extracted the models and got them to view in the viewer, but when I extract them and the model's textures, some of the textures are just transparent squares, do you know why? I got the Sora model to load, then I extracted the model and it's textures, and a couple of them are unviewable
[khddd sora.PNG](https://xentaxbackup.github.io/file/15872_khddd sora.PNG)
## Post #7
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-03-13T01:42:09+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

here are the textures I extracted
[textures.PNG](https://xentaxbackup.github.io/file/15873_textures.PNG)
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-13T10:55:49+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

What do you mean by unviewable? I can see in your screenshot that they are loaded fine inside Noesis, so there shouldn't be a problem. You might have something wrong with your image viewer.

Edit :

I remembered that some textures have alpha channel set to fully transparent. You can just remove the alpha channel to view them properly. This might be a problem related to GNF loader library, but it might also be how the textures actually are inside the PMO files. I am not sure about that. It can be fixed easily though.

Edit 2 :

I changed a setting in GNF loader and it seems to remove that full transparency issue. At least should make it easier than fixing manually. You can download the new version from the link in the first post.
## Post #9
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-03-13T11:54:38+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

how do I remove the Alpha Channel? Sorry for all the questions by the way
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-13T12:01:20+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from wonka1004 ↑Wed Mar 13, 2019 7:54 pm at Wed Mar 13, 2019 7:54 pm
>
> 
how do I remove the Alpha Channel? Sorry for all the questions by the way
I have updated the program. It shouldn't have fully transparent alpha now. Download and give it a try. Tell me if it works fine.
## Post #11
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-03-13T12:05:32+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

I tested it and it works, thanks a lot man
## Post #12
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2020-03-24T01:25:17+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

any plans to fix the maps export?
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-24T09:16:12+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from DaniZaya ↑Tue Mar 24, 2020 9:25 am at Tue Mar 24, 2020 9:25 am
>
> 
any plans to fix the maps export?

Can you be more specific about the problem? Obj doesn't export/deformed mesh/wrong material/wrong positioning etc.
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-02T15:46:13+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

ANIMATION TOOL

A new tool for loading skinned models and animations. The usage should be self-explanatory. The export format is NUX which is a custom format made to be loaded with Noesis. The Noesis script for it is in the rar file also.

Use arrow keys to cycle animations

Tool download: [http://www.mediafire.com/file/u5v7t769a ... m.rar/file](http://www.mediafire.com/file/u5v7t769ai9jg4w/KH3DAnim.rar/file)

Sora random animations
## Post #15
- Username: trentroy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 05, 2021 9:23 am
- Post datetime: 2021-02-05T01:25:55+00:00
- Post Title: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Mon Mar 11, 2019 5:32 pm at Mon Mar 11, 2019 5:32 pm
>
> 
wonka1004 wrote: ↑Mon Mar 11, 2019 10:35 am
Will you be uploading the PS4 models?

No, I won't be sharing the extracted models. Just the tool.
Hello, sorry to bother you, but is there a version of the tool that supports viewing the 3DS pmo models without the gnf textures?
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-03T11:55:07+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

PC TOOL

Made slight changes to make the animation tool work with the PC files.

Extracting Files

Use "KH28PCDec" included in the download to unpack the files from hed/pkg. Drag and drop the hed file on to KHPCDecCore.exe. The corresponding pkg file must be in the same directory as the hed. The tool will create a new folder in that directory and extract the files in it.

Download: [https://www.mediafire.com/file/rq7mw0k9 ... C.rar/file](https://www.mediafire.com/file/rq7mw0k9o8co6q4/KH3DAnim_PC.rar/file)

Credits
Decryption method - xeeynamo
## Post #17
- Username: Jhagrin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 07, 2021 4:40 am
- Post datetime: 2021-04-06T22:46:15+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

Sorry if this is a dumb question, but what would be the process (or where would I go to find the correct process) for getting the models from the PC version of the game? I tried following the steps I saw elsewhere in this thread, but they all seemed to be assuming that I'm working with the PS4 version. I'm hoping to be able to extract the models of some keyblades and know basically nothing about file extracting from games. I dragged the hed files onto the executable which then extracted all the files into a folder, but all the files show up as .dat files and I'm not entirely sure where to go from there. Right now I'm trying to use Noesis but it fails to read every one of them that I've tried and they all just show up as "00001.dat, 000002.dat, etc.
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-07T08:03:24+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Jhagrin ↑Wed Apr 07, 2021 6:46 am at Wed Apr 07, 2021 6:46 am
>
> 
but all the files show up as .dat files
Interesting. Can you see the folder names? The exe should create a folder like "kh3d_first_export" and inside it there should be other folders like "cam", "chara", "effect". Do you have these folders?
## Post #19
- Username: Jhagrin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 07, 2021 4:40 am
- Post datetime: 2021-04-07T08:16:46+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Wed Apr 07, 2021 4:03 pm at Wed Apr 07, 2021 4:03 pm
>
> 
Jhagrin wrote: ↑Wed Apr 07, 2021 6:46 am
but all the files show up as .dat files

Interesting. Can you see the folder names? The exe should create a folder like "kh3d_first_export" and inside it there should be other folders like "cam", "chara", "effect". Do you have these folders?

I just realized I'm a fool. I was trying to extract the KH2 game files instead of the 3D files. Now that I did it with the right game, everything's working perfectly fine. Although now I'm wondering if there's an easier way to find particular models instead of just clicking through all the PMOs one by one. Would you know anything about that?
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-07T08:27:37+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Jhagrin ↑Wed Apr 07, 2021 4:16 pm at Wed Apr 07, 2021 4:16 pm
>
> 
Would you know anything about that?

There are some small hints in the names, but other than that you need to try them out. For example n_rg02 is an NPC(n) in Radiant Garden(rg). Traverse Town is "tw", Pinocchio's world is "pi" and so on. There might be a list for it somewhere but I don't know.
## Post #21
- Username: Jhagrin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 07, 2021 4:40 am
- Post datetime: 2021-04-07T08:34:03+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Wed Apr 07, 2021 4:27 pm at Wed Apr 07, 2021 4:27 pm
>
> 
Jhagrin wrote: ↑Wed Apr 07, 2021 4:16 pm
Would you know anything about that?


There are some small hints in the names, but other than that you need to try them out. For example n_rg02 is an NPC(n) in Radiant Garden(rg). Traverse Town is "tw", Pinocchio's world is "pi" and so on. There might be a list for it somewhere but I don't know.

Thanks a lot for all your help so far. I managed to find one of the Keyblades I was looking for, but I'm not entirely sure how I'm supposed to export the files. I only have the options to export the NUX and the texture, but I don't see the option to export as an obj even though it's mentioned in the post.
## Post #22
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-07T08:40:25+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Jhagrin ↑Wed Apr 07, 2021 4:34 pm at Wed Apr 07, 2021 4:34 pm
>
> 
 I only have the options to export the NUX and the texture, but I don't see the option to export as an obj even though it's mentioned in the post.
Yea, it was the old version of the tool. I haven't updated it for the pc, I just updated the new one. However, you should still be able to export the keyblades. Export the model as NUX from the tool. You should also have "fmt_Nux.py" in the downloaded files. Copy that to Noesis' plugins/python folder. Now you should be able to load the NUX files in Noesis and export to anything you want. I haven't tested keyblades too much, so some might fail exporting.
## Post #23
- Username: Jhagrin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 07, 2021 4:40 am
- Post datetime: 2021-04-07T08:48:11+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Wed Apr 07, 2021 4:40 pm at Wed Apr 07, 2021 4:40 pm
>
> 
Jhagrin wrote: ↑Wed Apr 07, 2021 4:34 pm
 I only have the options to export the NUX and the texture, but I don't see the option to export as an obj even though it's mentioned in the post.

Yea, it was the old version of the tool. I haven't updated it for the pc, I just updated the new one. However, you should still be able to export the keyblades. Export the model as NUX from the tool. You should also have "fmt_Nux.py" in the downloaded files. Copy that to Noesis' plugins/python folder. Now you should be able to load the NUX files in Noesis and export to anything you want. I haven't tested keyblades too much, so some might fail exporting.

So the NUX file should work even if it's saved as "NoAnim.nux?" Or do I need to go in and find the right animation files for each keyblade as well before that will work?

Never mind, looks like it did work. Everything seems to be working properly now, the only thing I'm not sure about is why the .obj files seem to be noticeably lower resolution than the model in the viewer. I wonder if I might just be expecting too much from it. They're still definitely usable.
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-07T09:03:03+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Jhagrin ↑Wed Apr 07, 2021 4:48 pm at Wed Apr 07, 2021 4:48 pm
>
> 
So the NUX file should work even if it's saved as "NoAnim.nux?"

It should work. Why not try it?
## Post #25
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-04-18T10:30:27+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

Hi. Can you show me how to use tool for the PC version please

Thanks,
## Post #26
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2021-07-07T03:25:56+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

Hey, I have an issue with the model viewer tool. I tried to load a .pmp file from the PC version (tw_05.pmp specifically) and it's showing up without any textures. I thought this might've been an issue with the model's gnf textures but I saw that the tool does support gnf textures so I'm a tad confused. Does anyone know of a way to fix this?
## Post #27
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2021-07-07T03:45:02+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Century300 ↑Wed Jul 07, 2021 11:25 am at Wed Jul 07, 2021 11:25 am
>
> 
Hey, I have an issue with the model viewer tool. I tried to load a .pmp file from the PC version (tw_05.pmp specifically) and it's showing up without any textures. I thought this might've been an issue with the model's gnf textures but I saw that the tool does support gnf textures so I'm a tad confused. Does anyone know of a way to fix this?

P.s 
This issue seems to happen with every .pmo and .pmp that I put into the tool. I'm pretty sure the reason why all the models I've been passing through the tool show up without textures is that they're files from the pc release. Maybe the gnf texture type was changed between ps4 and pc? idk
## Post #28
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-07T06:15:08+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Century300 ↑Wed Jul 07, 2021 11:45 am at Wed Jul 07, 2021 11:45 am
>
> 
Maybe the gnf texture type was changed between ps4 and pc? idk
PC is using DDS instead of GNF. Textures of the PC models will not work with the PS4 tool. Trying the PC version of the tool would make more sense: [viewtopic.php?p=172939#p172939](https://forum.xentax.com/viewtopic.php?p=172939#p172939)
## Post #29
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2021-07-07T06:44:05+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Wed Jul 07, 2021 2:15 pm at Wed Jul 07, 2021 2:15 pm
>
> 
Century300 wrote: ↑Wed Jul 07, 2021 11:45 am
Maybe the gnf texture type was changed between ps4 and pc? idk

PC is using DDS instead of GNF. Textures of the PC models will not work with the PS4 tool. Trying the PC version of the tool would make more sense: viewtopic.php?p=172939#p172939

Yeah, I did see that the PC Anim tool worked with the textures just fine. My only problem is that it can only read .pmo and .pam files. I actually wanted to extract the map models from .pmp files which don't load in the animation tool.
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-07T06:48:25+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Century300 ↑Wed Jul 07, 2021 2:44 pm at Wed Jul 07, 2021 2:44 pm
>
> 
I actually wanted to extract the map models from .pmp files which don't load in the animation tool.

Yes, there is no support for pmp in the PC tool. If you want textured maps you can try getting the PS4 files, or maybe look for another tool that can handle PC maps.
## Post #31
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2021-07-07T13:05:29+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Wed Jul 07, 2021 2:48 pm at Wed Jul 07, 2021 2:48 pm
>
> 
Century300 wrote: ↑Wed Jul 07, 2021 2:44 pm
I actually wanted to extract the map models from .pmp files which don't load in the animation tool.


Yes, there is no support for pmp in the PC tool. If you want textured maps you can try getting the PS4 files, or maybe look for another tool that can handle PC maps.

I don't think there's another tool that can handle DDD's maps apparently. And I don't think I'm gonna be able to dump the PS4 version since the files aren't publically available anywhere and the pkg can't be extracted without a passcode. But thanks anyway.

Have you considered posting the source code for your tool on GitHub? Maybe I could try to add .dds support for it.
## Post #32
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-07T15:01:17+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Century300 ↑Wed Jul 07, 2021 9:05 pm at Wed Jul 07, 2021 9:05 pm
>
> 
Have you considered posting the source code for your tool on GitHub? Maybe I could try to add .dds support for it.

I am not planning to open source it atm. You can find the dumped ps4 pkg on the internet easily. It also doesn't require a special passcode.

You can also find open source projects dealing with DDD formats including pmp: [https://github.com/Xeeynamo/OpenKh/blob ... Program.cs](https://github.com/Xeeynamo/OpenKh/blob/master/OpenKh.Command.PmpConverter/Program.cs)
## Post #33
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2021-07-07T15:21:03+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Wed Jul 07, 2021 11:01 pm at Wed Jul 07, 2021 11:01 pm
>
> 
Century300 wrote: ↑Wed Jul 07, 2021 9:05 pm
Have you considered posting the source code for your tool on GitHub? Maybe I could try to add .dds support for it.


I am not planning to open source it atm. You can find the dumped ps4 pkg on the internet easily. It also doesn't require a special passcode.

You can also find open source projects dealing with DDD formats including pmp: https://github.com/Xeeynamo/OpenKh/blob ... Program.cs

Ah nice, I thought all ps4 pkgs required a passcode but I guess not. I'll check out the other projects under OpenKh too. Thanks!
## Post #34
- Username: dallin1016
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 10, 2021 12:08 pm
- Post datetime: 2021-11-10T04:11:32+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

Any chance of updating the PC tool so textures load for maps on the PC Version? Wanting to get the Sanctum of Time/YMX Arena for a KH3 mod, but it doesn't load the textures or even give it materials. Would be MASSIVELY appreciated
## Post #35
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2021-11-25T09:15:38+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

KH3D Viewer doesnt load any texture for me
## Post #36
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2022-06-28T10:16:25+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

And i drag and drop the files on KHPCDecCore making sure everything is in the same folder, but nothing happens, it open and close as soon as it start
## Post #37
- Username: jc97
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 29, 2021 9:50 pm
- Post datetime: 2022-09-22T07:02:23+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

KHPCDecCore doesn't seem to work anymore, same problem as above but the CMD doesn't open at all.
## Post #38
- Username: peachnkey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 19, 2023 8:21 am
- Post datetime: 2023-03-19T00:24:56+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from Tsunani ↑Tue Jun 28, 2022 6:16 pm at Tue Jun 28, 2022 6:16 pm
>
> 
And i drag and drop the files on KHPCDecCore making sure everything is in the same folder, but nothing happens, it open and close as soon as it start

I am also having this issue :c I feel like I'm missing something or doing something wrong (I'm a total noob but I know enough to work my way around stuff like this) I've tried moving the hed and pkg files into their own folders, moving them into the folder with the exe, running the program as administrator and then dragging and dropping, restarting my computer and trying again, everything! The files I'm supposed to be working with are called "kh3d_first" second, third, etc. right? Am I supposed to do anything else with these files before I drag and drop them? I simply found them through my epic games directory, is this incorrect?
## Post #39
- Username: meatbirb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 26, 2023 6:19 am
- Post datetime: 2023-09-25T22:33:35+00:00
- Post Title: Re: Kingdom Hearts DDD (HD/2.8) Tool

> Reply from akderebur ↑Mon Mar 11, 2019 11:57 pm at Mon Mar 11, 2019 11:57 pm
>
> 
Google how to dump/get ps4 game pkg files and how to extract them. Once you extract the pkg you will have 2 .psarc files. Use Noesis to extract them and get the PMO/PMP files. Finally you can load them with my tool.

hello im really sorry for bumping but i really want to get the sudo neku model from KH3D and i never done any model ripping before. i searched so much how i could rip the model but everything i find are dead links and i cant find a pkg of the game and a tool to extract pkg and get pmo files. i tried everything i could but cant get anything to work. i cant seem to find anyone who rips KH3D models and cant seem to do it myself at all. is there hope for this or i should give up? i really need the sudo neku model for a personal project
