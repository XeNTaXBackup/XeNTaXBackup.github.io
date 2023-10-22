## Post #1
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-03T01:07:30+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Imports mesh, rig and morphs (all files need to be in the same folder). Should work with character and clothing models, haven't tried the static meshes. Does not import materials. The imported meshes and armature should be ready to be exported as .fbx and converted back into game format using SR IV sdk tools without much hassle, just have to add a material, and normals might need to be recalculated.

Update: fixed some issues, added SR3R version, added a function to import NPC head morphs.

[io_import_ccmesh.zip](https://www.mediafire.com/file/22al0kvuevh3yun/io_import_ccmesh.zip/file)

Also there's a [texture unpacking script](https://forum.xentax.com/viewtopic.php?p=193840#p193840) for .cpeg_pc and .cvbm_pc files if you need it. (requires Python)
## Post #2
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-10T08:54:19+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Added a modified version of the script that works with Saints Row 3 Remastered.
[](https://ibb.co/8cnwQsV)
## Post #3
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-10T19:39:23+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Thu Aug 10, 2023 4:54 pm at Thu Aug 10, 2023 4:54 pm
>
> 
Added a modified version of the script that works with Saints Row 3 Remastered.

Where did you get the textures from, Ninja Ripper or something? I tried the tool here: [https://www.saintsrowmods.com/forum/thr ... 646/page-2](https://www.saintsrowmods.com/forum/threads/a-fix-for-the-srtt-texture-unpacker-to-support-srttr.18646/page-2)

But I'm getting DLL errors and such.
## Post #4
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2023-08-10T21:47:37+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

you download the gibbed tools linked in the first post here with the srttr importer [https://www.saintsrowmods.com/forum/thr ... ttr.18646/](https://www.saintsrowmods.com/forum/threads/a-fix-for-the-srtt-texture-unpacker-to-support-srttr.18646/)

only seems to work in command line too, but it's literally just "SR3UnpackTextures kinzie_body_high.cpeg_pc" etc

speaking of kinzie; i'm getting an error on trying to import her model



the head model loads but i get this trying to load her body model; seems to be ONLY her model out of the six or so i've tried?
## Post #5
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-11T00:21:52+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from foulveins ↑Fri Aug 11, 2023 5:47 am at Fri Aug 11, 2023 5:47 am
>
> 
speaking of kinzie; i'm getting an error on trying to import her model

the head model loads but i get this trying to load her body model; seems to be ONLY her model out of the six or so i've tried?

Yeah, i see the problem with it. I'll try to fix it soon.

> Reply from AxelNoir ↑Fri Aug 11, 2023 3:39 am at Fri Aug 11, 2023 3:39 am
>
> 
Where did you get the textures from, Ninja Ripper or something? I tried the tool here: https://www.saintsrowmods.com/forum/thr ... 646/page-2

But I'm getting DLL errors and such.

This one you linked works for me. Maybe it requires some Visual Studio libraries or something? Anyway, it only exports diffuse and "arm" textures, but errors on normals. I was gonna write a simple script to export textures, just have to figure out how to write a proper .dds file header.
## Post #6
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-11T01:13:24+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Fri Aug 11, 2023 8:21 am at Fri Aug 11, 2023 8:21 am
>
> 
This one you linked works for me. Maybe it requires some Visual Studio libraries or something? Anyway, it only exports diffuse and "arm" textures, but errors on normals. I was gonna write a simple script to export textures, just have to figure out how to write a proper .dds file header.

Huh, strange. I'm getting errors like, ""ucrtbased.dll" "VCRUNTIME140D.dll" "msvcp140d.DLL" was not found." basically. I have Visual C++ Runtime 2015-2022 Redistributable x64 installed, is there anything else I'd need for it to work? And okay I wasn't aware of the diffuse only aspect, I've seen a user Tosyk rip the models and the textures with full shaders like here:

[https://www.deviantart.com/tosyk/art/Sh ... -970642531](https://www.deviantart.com/tosyk/art/Shaundi-R-Leather-Jacket-and-Top-Outfit-2014-970642531)

Not sure how they did it but, hopefully we can get full textures going. Also one more thing I noticed, I'm not sure if this happens with everyone, but I imported Shaundi's head into Blender and everytime I turn on a shapekey her head moves out of place as if the shapekey was recorded in a different position. Any fix?
## Post #7
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-11T01:29:45+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Well, maybe he did used NinjaRipper. It does work with Remastered, i tried it before.

> Reply from AxelNoir ↑Fri Aug 11, 2023 9:13 am at Fri Aug 11, 2023 9:13 am
>
> 
Also one more thing I noticed, I'm not sure if this happens with everyone, but I imported Shaundi's head into Blender and everytime I turn on a shapekey her head moves out of place as if the shapekey was recorded in a different position. Any fix?

Facial animation shape keys are calculated relative to base head shape, not relative to the given NPC's head shape key, that's the way it should be.

When you select one of those shape keys you're trying to adjust, which shape does "Relative To" parameter points to? It should be "Base", not whatever the shape key for Shaundi's head is called.

Maybe you have "Shape Key Lock" turned on? It's the button with a pin icon to the right, right under the list of shape keys.

Edit:
Merged the scripts, and updated it to fix the issue pointed out by foulveins.
## Post #8
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-11T10:15:45+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Tried to write a script that extracts textures from SR3R peg files. Drag and drop .cpeg_pc or .cvbm_pc files on it to extract a single file, or, if you run the script without arguments, it will attempt to extract all peg files in the current folder and all subfolders one level below.
[SR3RtextureUnpacker.zip](https://xentaxbackup.github.io/file/24213_SR3RtextureUnpacker.zip)
## Post #9
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-11T14:01:18+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Fri Aug 11, 2023 6:15 pm at Fri Aug 11, 2023 6:15 pm
>
> 
Tried to write a script that extracts textures from SR3R peg files. Drag and drop .cpeg_pc or .cvbm_pc files on it to extract a single file, or, if you run the script without arguments, it will attempt to extract all peg files in the current folder and all subfolders one level below.

Which version of Python do I need installed for this?

Edit: Nevermind, installed the latest version of Python 3 and it worked, thank you so much!
## Post #10
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-12T19:15:45+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Thu Aug 03, 2023 9:07 am at Thu Aug 03, 2023 9:07 am
>
> 
Update: fixed some issues, added SR3R version, added a function to import NPC head morphs.

io_import_ccmesh.zip

Unfortunately I ran into an issue importing Zimos, I'm getting a traceback error: 



The file is, "npc_Zimos.str2_pc"

Will this be fixed?
## Post #11
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-13T02:09:09+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from AxelNoir ↑Sun Aug 13, 2023 3:15 am at Sun Aug 13, 2023 3:15 am
>
> 
Unfortunately I ran into an issue importing Zimos, I'm getting a traceback error: 

The file is, "npc_Zimos.str2_pc"

Will this be fixed?

Strange, there doesn't seem to be a rig for this model, even though it is supposed to be there. Don't know where the game loads it from, but i updated the script to make it load the meshes at least even if the rig was not found.
## Post #12
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-13T02:12:01+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Sun Aug 13, 2023 10:09 am at Sun Aug 13, 2023 10:09 am
>
> 
Strange, there doesn't seem to be a rig for this model, even though it is supposed to be there. Don't know where the game loads it from, but i updated the script to make it load the meshes at least even if the rig was not found.

Very odd, could it be using some default male npc skeleton? Not that that makes much sense to me but that's all I can think of. Thanks anyway though!
## Post #13
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-13T02:21:25+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from AxelNoir ↑Sun Aug 13, 2023 10:12 am at Sun Aug 13, 2023 10:12 am
>
> 
Very odd, could it be using some default male npc skeleton? Not that that makes much sense to me but that's all I can think of. Thanks anyway though!

The default rig has fewer bones. And character_definitions.xtbl file says that there is supposed to be a rig file.
Btw, in case if you already downloaded the script after i replied, download it again cause i had to add another small edit to prevent a potential issue.

Edit: His rig is in preload_rigs.vpp_pc, though my script doesn't load it. I'll see if i can find what the issue is.

Oh... His rig file, as well as some others inside preload_rigs, has strings containing the names of bones, which are supposed to be at the bottom of the file, "wrap around" and end up at the top before the header. WTF?
I think the program i use to extract vpp_pc files (sr-tools.exe) does not unpack preload_rigs.vpp_pc properly.
## Post #14
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-13T03:08:48+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Sun Aug 13, 2023 10:21 am at Sun Aug 13, 2023 10:21 am
>
> 
The default rig has fewer bones. And character_definitions.xtbl file says that there is supposed to be a rig file.
Btw, in case if you already downloaded the script after i replied, download it again cause i had to add another small edit to prevent a potential issue.

Edit: His rig is in preload_rigs.vpp_pc, though my script doesn't load it. I'll see if i can find what the issue is.

Oh... His rig file, as well as some others inside preload_rigs, has strings containing the names of bones, which are supposed to be at the bottom of the file, "wrap around" and end up at the top before the header. WTF?
I think the program i use to extract vpp_pc files (sr-tools.exe) does not unpack preload_rigs.vpp_pc properly.

Huh, what the hell? That's so weird, of all the characters, why place his in a separate container? Who else's rigs are in there, just random characters or something?
## Post #15
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-13T03:38:10+00:00
- Post Title: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

The rigs for Cyrus and default PC male\female are in there too. And rigs for some of the cars (i assume?).
## Post #16
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-13T03:42:23+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Interesting, I wonder why they chose to stash their rigs seperately in there while the other characters's rigs are defined within their own containers...
## Post #17
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-13T04:12:20+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Dunno. Anyway, here's the rigs for Cyrus and Zimos if anyone wants to import them.
[SR3preloadRigs.zip](https://xentaxbackup.github.io/file/24220_SR3preloadRigs.zip)
## Post #18
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-13T04:17:06+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Thanks it worked!
## Post #19
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-13T19:22:21+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Thu Aug 03, 2023 9:07 am at Thu Aug 03, 2023 9:07 am
>
> 
Imports mesh, rig and morphs (all files need to be in the same folder). Should work with character and clothing models, haven't tried the static meshes. Does not import materials. The imported meshes and armature should be ready to be exported as .fbx and converted back into game format using SR IV sdk tools without much hassle, just have to add a material, and normals might need to be recalculated.

Update: fixed some issues, added SR3R version, added a function to import NPC head morphs.

io_import_ccmesh.zip

Appears to be a weights issue with Viola as someone pointed out to me today:



Doesn't seem to be an issue with every single character but so far I've found this issue present on Viola, I don't know if others have this problem yet or not.
## Post #20
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-13T22:57:33+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Yeah, vertices on the legs are weighted to wrong bones, but i'm not sure why.
## Post #21
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-14T13:04:53+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Mon Aug 14, 2023 6:57 am at Mon Aug 14, 2023 6:57 am
>
> 
Yeah, vertices on the legs are weighted to wrong bones, but i'm not sure why.

Yeah, it seems both Viola and Kiki have the same issue, hopefully this can be resolved soon. Also I have a question if you don't mind, would you happen to know where the assets for the default playable character might be stored?
## Post #22
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-14T14:30:42+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

You mean like the base body? Female body is in custmesh_1632961868, male body in custmesh_-233129239 in customize_item.vpp_pc, their rigs are in preload too. Normal maps are in files "Male\Female White\Black\Asian\Hispanic.str2_pc", diffuse is in "Default male\female diffuse.str2_pc", all  in customize_player.vpp_pc.
## Post #23
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-14T14:54:37+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Thank you!
## Post #24
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-14T19:09:24+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Ok, the issue with weights should be fixed now.
Man, does this game assign weights to vertices in a convoluted way for seemingly no reason.
## Post #25
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-14T22:22:18+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Tue Aug 15, 2023 3:09 am at Tue Aug 15, 2023 3:09 am
>
> 
Ok, the issue with weights should be fixed now.
Man, does this game assign weights to vertices in a convoluted way for seemingly no reason.

Thanks, looks like they're fixed. Unfortunately I had to be the bearer of bad news...lol, but the Bloody Cannoness outfit for Viola is now broken and appears to be giving a traceback error regarding adding weights or a rig to her model. Believe the file is, "morningstar_female_violaBC.str2_pc".

Also is it possible to be able to import the .cmorph_pc files by any chance?
## Post #26
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-15T06:19:43+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from AxelNoir ↑Tue Aug 15, 2023 6:22 am at Tue Aug 15, 2023 6:22 am
>
> 
Unfortunately I had to be the bearer of bad news...
Nah, thanks for the feedback. I probably would not have noticed most of the bugs until way later, when i would have already felt too lazy to go back and fix anything.
Now though, i finally came up with a genius idea to batch test the script instead of just trying several files, and i'm cautiously optimistic that it shouldn't have any critical bugs now.

> Reply from AxelNoir ↑Tue Aug 15, 2023 6:22 am at Tue Aug 15, 2023 6:22 am
>
> 
Also is it possible to be able to import the .cmorph_pc files by any chance?
Meaning what? Morphs for the appropriate models are imported. 
If you mean like importing multiple NPC face shapes on a single head mesh, well, all NPC heads use the same base mesh and should have the same number of vertices and the same vertex order, so you can import them separately and just join them as shapes in Blender.
## Post #27
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-31T03:17:55+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Looks like one of the decker females is missing UVs:



File for reference: npc_decker_female_lt.str2_pc
## Post #28
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-09-01T03:36:58+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Check the UV Maps drop down menu, most of the models in the game have multiple uv layers.
## Post #29
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-01T16:10:53+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Fri Sep 01, 2023 11:36 am at Fri Sep 01, 2023 11:36 am
>
> 
Check the UV Maps drop down menu, most of the models in the game have multiple uv layers.

Thanks looks like you were right, sorry for the inconvenience haha! Would you by any chance happen to know where weapons and props are stored?
## Post #30
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-09-01T16:23:55+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Nah, i only ever looked at character models. Try using file search engine on saintsrowmods.com:

[https://saintsrowmods.com/search/Files/ ... erm=pistol](https://saintsrowmods.com/search/Files/Results?game=2&searchTerm=pistol)
## Post #31
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-01T20:20:06+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Oh didn't know about this, thanks!
## Post #32
- Username: shorewake
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Feb 16, 2023 9:37 am
- Post datetime: 2023-09-03T00:09:43+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

Will there be Saints Row 2022 .cmesh_pc support?
## Post #33
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-09-03T01:14:13+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

I will love one for Agents of Mayhem. They're some interesting models in the game aside of the DLC outfits too.
## Post #34
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-19T22:48:23+00:00
- Post Title: Re: (PC) Saints Row 3\4\Remastered (.ccmesh) Blender import addon

> Reply from Moff ↑Fri Aug 11, 2023 6:15 pm at Fri Aug 11, 2023 6:15 pm
>
> 
Tried to write a script that extracts textures from SR3R peg files. Drag and drop .cpeg_pc or .cvbm_pc files on it to extract a single file, or, if you run the script without arguments, it will attempt to extract all peg files in the current folder and all subfolders one level below.

Having trouble with some of the textures for Spacesuit Killbane, they appear to be corrupted or swizzled in some odd way? I've attached a sample. It only seems to occur with the high res textures though.

[https://mega.nz/file/D4x3CZoS#fnkSiwjnn ... ytU2cBnhS0](https://mega.nz/file/D4x3CZoS#fnkSiwjnn3X0fwFUfFC2xCc24wkOVz27WytU2cBnhS0)
