## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-13T22:15:24+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-14T03:39:19+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-23T22:13:16+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #4
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-24T05:13:37+00:00
- Post Title: SW Battlefront 2015 model files

Any chance you could post a link to what you have so far?
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-24T11:44:17+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-26T22:24:47+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #7
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-12-26T22:53:47+00:00
- Post Title: SW Battlefront 2015 model files

Wow glad to see some progress on this game =) Nice work!
## Post #8
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-12-26T23:10:09+00:00
- Post Title: SW Battlefront 2015 model files

Very interested in this since this runs on Frostbite which is the same engine as Battlefield 3, 4 and Hardlline. I'm hoping this would support those games as well.
## Post #9
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-27T05:06:20+00:00
- Post Title: SW Battlefront 2015 model files

Ah man awesome job, Does it get out the UVs of the model?
## Post #10
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-27T11:55:11+00:00
- Post Title: SW Battlefront 2015 model files

looks promising! did you manage to get bones/weights working on the cloth physics meshes too?
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-27T14:25:31+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #12
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-27T15:19:48+00:00
- Post Title: SW Battlefront 2015 model files

> Reply from Wobble
>
> urgarulga wrote:looks promising! did you manage to get bones/weights working on the cloth physics meshes too?

[...]

Why do you ask?  What makes them different than any other mesh?

[...]

Because if the tool isn't extracting them, then the resType must not be correct?   I'm no Python expert.
Where are the textures?  Are they being dumped as nameless .chunk files?  Do I have to scan every single chunk file to find them?

Some people that worked on mesh importer scripts for 3dsmax had troubles with the havok physics meshes - I don't know anything about reverse engineering so I was just curious.

Also for the textures if you dump the entire SWBF content and use the Chunk and Mesh management tool and then the Batch ltexture Converter you should get this folder structure:



YsM7flF.jpg (150.91 KiB) Viewed 574 times



hope that helps? oh and your UVWs are mirrored in Y.
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-27T15:57:31+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #14
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-27T16:12:16+00:00
- Post Title: SW Battlefront 2015 model files

> Reply from Wobble
>
> 

Thanks.  btw, that management tool doesn't work for me.  0 successful, 0 failed.

I think I had the same problem as I extracted the content.

if i remember correctly there are three of the chunk and mesh tools available:

[https://dl.dropboxusercontent.com/u/881 ... h_Tool.rar](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/Chunk_%26_Mesh_Tool.rar)
[http://www.mediafire.com/download/8bk91 ... Reader.rar](http://www.mediafire.com/download/8bk91mob7bgxovg/Bf3_MeshFile_Type_Reader.rar)
[https://dl.dropboxusercontent.com/u/881 ... 20tool.rar](https://dl.dropboxusercontent.com/u/88155050/SWBF%20Open%20Beta/Chunk%20and%20Mesh%20management%20tool.rar)

I'm not entirely sure which one I used. maybe try these?

also theres a youtube guide for the tool: [https://www.youtube.com/watch?v=4EKxrBnRNBc](https://www.youtube.com/watch?v=4EKxrBnRNBc)
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-27T16:25:14+00:00
- Post Title: SW Battlefront 2015 model files

[out]
## Post #16
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-27T16:39:31+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> Thanks, tried it again.  I think I got it this time.  No itextures though.
It moved chunk files and renamed all of my meshes.  I didn't care for that. 

Is there a video or instructions for the iTexture Converter?  Tried it, and it doesn't work for me.
The "Select Itexture folder" isn't doing anything for me.  "Count" field doesn't change.

same story when it comes to the texture converter. You got to use the correct tool for that. I used the Batch_Itexture_Converter.exe included in swbf.rar found here: [viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584).

After selecting the two folders and hitting get dds files the program will freeze but it will start to find the proper dds and place them in folders like the picture I posted earlier (takes a while).
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-27T16:57:59+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #18
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-27T16:59:13+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> Thanks, that one worked!  The other was a dud.  They don't make this easy without instructions.

took me quite some trial and error too. I guess you already know the dds are some kind of newer DX10 format and need a special viewer/converter for these, just want to mention it anyways.
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-27T17:25:13+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #20
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-27T17:30:35+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> 

I see "DX10" embedded in all of the DDS files.  I think it's been around since 2010, so it shouldn't be that hard to find source code for a DX10 decoder.

I used PicoPixel ([http://pixelandpolygon.com/](http://pixelandpolygon.com/)) to preview them and used a converter to get them in a common readable format: [https://dl.dropboxusercontent.com/u/881 ... verter.rar](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/DDS_Converter.rar).
## Post #21
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-27T20:08:17+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> Thanks, tried it again.  I think I got it this time.  No itextures though.
It moved chunk files and renamed all of my meshes.  I didn't care for that. 

Is there a video or instructions for the iTexture Converter?  Tried it, and it doesn't work for me.
The "Select Itexture folder" isn't doing anything for me.  "Count" field doesn't change.

Okay here is what you wanna do,

When it tells you to select the Itexture folder that is the Res folder and than just select the chunk folder it's really not that hard.

But if it can get the Meshes,UVs and Bones why not just go ahead and release it?

> Reply from urgarulga
>
> Wobble wrote:

I see "DX10" embedded in all of the DDS files.  I think it's been around since 2010, so it shouldn't be that hard to find source code for a DX10 decoder.

I used PicoPixel (http://pixelandpolygon.com/) to preview them and used a converter to get them in a common readable format: https://dl.dropboxusercontent.com/u/881 ... verter.rar.

No this method is probably the most stupid and most time consuming.

What you wanna do is when it dumps the textures you wanna open them in MS Visual Studio 2013 (which is free) that is the best program atm that works with the textures and you can than save them as png (don't save as anything else) and load them in XNview and export them back out as DDS files so it separates the alpha layer from the RGB channel.
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-12-27T23:56:02+00:00
- Post Title: Re: SW Battlefront 2015 model files

It's not shocking to see confusion about extracting files from this game correctly, there is 7 threads here talking about it and everyone is giving different advice and sharing different versions of the same tools...
## Post #23
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-28T02:52:58+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #24
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-28T11:27:34+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> 

Anyway, the DDS Converter tool fails on half of the .dds files.   And PicoPixel crashes on some of them too.

I'm guessing the iTexture Converter finds the texture chunk and adds its own DX10 header?   Perhaps it's setting the wrong pixel format?  Which could explain why PicoPixel is crashing. I don't know.

yeah the Batch_Itexture_Converter should just add its stuff and spit it out as DDS then it should be viewable with PicoPixel. After that I just recursively ran the DDS converter through the dumped content I wanted.

Which dds files didn't work for you? So I can see if it works on my side.
## Post #25
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-28T20:23:00+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #26
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-12-28T23:09:28+00:00
- Post Title: Re: SW Battlefront 2015 model files

The Batch iTexture converter I think renames chunks to the appropriate file name but from what I read I'm just assuming you need to use the right converter for the appropriate game (BF3 converter doesn't work for BF4 and Hardline and vice-versa) so you'll need to use the converter for SWBF for the SWBF files. I'm guessing the chunks got renamed differently when you used the previous converter but that's just a guess on my part.
## Post #27
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-29T08:13:34+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #28
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-29T09:53:37+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> Well, I deleted everything and started over.  Ugh.

Question:
Should SWBFdumper.py execute successfully to the end?
After extracting almost 40GB, the script ended in a KeyError.

I skipped using the management tool.  Didn't want my files renamed.

Tried the texture converter again, and the vader folder only created 86kb .dds files.
I think those are all failed textures.

Why don't they bundle these programs together, so we know they *all* work together?
Or at least have one Python script that does it all, so we don't have to screw around with this?

You want the texture tool from this thread and it's in the first post with the rest of the scripts.
[viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)
## Post #29
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-29T11:18:27+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #30
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-12-29T21:33:35+00:00
- Post Title: Re: SW Battlefront 2015 model files

@Wobble
I have to ask, did you encounter any problems with getting head meshes to import properly? dainiuxxx's Frostbite mesh importer maxscript had problems extracting head meshes and since SWBF is a Frostbite game, well... I'm just assuming they'd have the same format problems.
## Post #31
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-29T21:57:51+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from artworkplay
>
> @Wobble
I have to ask, did you encounter any problems with getting head meshes to import properly? dainiuxxx's Frostbite mesh importer maxscript had problems extracting head meshes and since SWBF is a Frostbite game, well... I'm just assuming they'd have the same format problems.

When you say imported properly you're meaning it looking normal as normal can be for a face or something else?

Cause all frostbite games mess their heads up bad and use code to tell the rigging were to go to make it proper.

Because no matter what frostbite game you rip from the faces are most likely going to look like this or worse.
## Post #32
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-12-29T22:30:00+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from JakeGreen
>
> artworkplay wrote:@Wobble
I have to ask, did you encounter any problems with getting head meshes to import properly? dainiuxxx's Frostbite mesh importer maxscript had problems extracting head meshes and since SWBF is a Frostbite game, well... I'm just assuming they'd have the same format problems.

When you say imported properly you're meaning it looking normal as normal can be for a face or something else?

Cause all frostbite games mess their heads up bad and use code to tell the rigging were to go to make it proper.

Because no matter what frostbite game you rip from the faces are most likely going to look like this or worse.

Figured as much. For every great engine there's one lousy trade-off.
## Post #33
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-30T11:15:25+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #34
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-12-30T21:25:53+00:00
- Post Title: Re: SW Battlefront 2015 model files

Lower eyelids looked unnaturally stretched forward. Same as JakeGreen's Leia pic above.
## Post #35
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-30T23:40:15+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #36
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-31T00:36:32+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> 

Ah, I see it now.  Is there a reason for that?  That's how the vertices are originally stored.  The loader does no transformations whatsoever.

to make the facial animations as universal as possible - if every single head has the same bind pose it is way easier to make animation sequences for all of them. You'd have to find the animation file for the 'idle' pose and the proper bone positions for the facial features to fix them.
## Post #37
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-31T01:29:55+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #38
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-31T10:37:55+00:00
- Post Title: Re: SW Battlefront 2015 model files

Man it would be really nice if you'd share the 3ds max script here cause it'd be a lot of help getting out other models i haven't been able to get out.
## Post #39
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-31T12:50:02+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> Well, if you know where those eyelid animations or transforms are, please let me know.

I wish I knew. this is only a theory - the entire thing could be hard-coded as well, its just an educated guess on how I would have done it.

After searching through the folders I've found these:

```
bundles\ebx\animations\rigs\humanoids	battlebeyond_01_masterskel.ebx
bundles\ebx\animations\rigs\humanoids	battlebeyond_01_skeleton.ebx
bundles\ebx\animations\rigs\humanoids	hero_forceuser_darthvader_masterskel.ebx
bundles\ebx\animations\rigs\humanoids	humanmale.ebx
bundles\ebx\animations\rigs\humanoids	humanmale_1p.ebx
bundles\ebx\animations\rigs\humanoids	humanmale_1p_masterskel.ebx
bundles\ebx\animations\rigs\humanoids	humanmale_masterskel.ebx
bundles\ebx\animations\rigs\humanoids	wshumanmale_ragdoll_convertedragdollmodel.ebx
bundles\ebx\animations\rigs\humanoids	wshumanmale_ragdoll_convertedragdollmodel_physics_win32.ebx
--RES
bundles\res\animations\rigs\humanoids	wshumanmale_ragdoll_convertedragdollmodel_physics_win32 49411f5f3584d239 10030001a0200000e02000005c050000.hknondestruction

```


Not sure if the .ebx files contain any data (probably a pointer to a chunk file?) at all and there is only one full skeleton in the RES folders. These master skeletons could contain the information for the 'default' facial position but I don't really know - just a guess.
## Post #40
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-31T16:14:00+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #41
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-12-31T17:22:31+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> 

That's what I'm using for my own skeleton.  However, the mesh is already transformed, so the skeleton by itself doesn't help to fix the eyelids.  What we need is a frame of animation.

Also, I'm not entirely sure if skeletal animation would help to transform them info place.  There are only two bones controlling an entire eyelid. (LeftUpEyelid, LeftLowEyelid), and each bone is assigned to almost 300 vertices.  Can only two bones transform all of those vertices back into place?  Maybe.  Hopefully, they are not controlled by morphs or physics.

Just for example... in BF4 and Hardline, skeleton was accessed by the maxscript importer is an ebx file converted to .txt in Animations called WarsawAntSkel01.txt. In BF3 it was called VeniceAntSke01.txt. It had bones for eyelids, eyebrows, nose, cheeks, eyeballs, lips etc.
## Post #42
- Username: urgarulga
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 11, 2015 1:12 am
- Post datetime: 2015-12-31T18:06:19+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> 

That's what I'm using for my own skeleton.  However, the mesh is already transformed, so the skeleton by itself doesn't help to fix the eyelids.  What we need is a frame of animation.

Also, I'm not entirely sure if skeletal animation would help to transform them info place.  There are only two bones controlling an entire eyelid. (LeftUpEyelid, LeftLowEyelid), and each bone is assigned to almost 300 vertices.  Can only two bones transform all of those vertices back into place?  Maybe.  Hopefully, they are not controlled by morphs or physics.

bummer. can't judge just from pictures if 2 bones could fix all of that, there's a chance that they do.

Probably need an animation sequence where the faces are animated as you suggested. sadly there's no animation file management tool so I can't help you there - maybe you can do one? If I remember correctly the older SWBF scripts for the beta had the ability to import full animations but I think the guy didn't share anything regarding that in the end.
## Post #43
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-31T21:49:34+00:00
- Post Title: Re: SW Battlefront 2015 model files

I'm guess you just need skeleton not animation or anim. sequence, if this game using base skeletons, then you just need one of them. I did script for Army of Two: The Devil's Cartel and one more Frostbite game, there faces were even worse. They used skeletal animation (matrix palette skinning) or gpu skinning like someone calling this technique. Maybe here too?
## Post #44
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-01T02:35:23+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from zaramot
>
> I'm guess you just need skeleton not animation or anim. sequence, if this game using base skeletons, then you just need one of them. I did script for Army of Two: The Devil's Cartel and one more Frostbite game, there faces were even worse. They used skeletal animation (matrix palette skinning) or gpu skinning like someone calling this technique. Maybe here too?

You can get the bones out just fine with dainazinas BF4_Bone_Maker(1.3).ms but it wont be any good until someone edits his main 3ds max model importer cause it gives the proper skin modifier to the meshes.

You just have to manually set the bone count for characters,vehicles....ect and the bone count for the alpha was 266 and in the beta i think it was 268 and not sure what it is in the full game but it's probably around that.

The ones you want are humanmale_masterskel.txt and humanmale.txt

This is apart of the code you'd need to edit from dainazinas script.

	--bone count has to be set manually for now

	bone_count = 266

I think you can find it here [viewtopic.php?f=33&t=13145](http://forum.xentax.com/viewtopic.php?f=33&t=13145)
## Post #45
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-01T04:44:49+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #46
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-01-01T19:10:34+00:00
- Post Title: Re: SW Battlefront 2015 model files

Hey!

I went through the painful process of extracting files for this game, trying all of the tools, etc.
Now, I got the chunks/meshes/textures in the right places, but the MAXScript does not work for me. lol!

Is the Maxscript working for you guys? MAX Listener returns this:

```
"ObjectFullName atat_posed_01_Mesh"
"ObjectType 2"
"GUID_Count 6"
"First_Data_Block_Offset 1296"
"Mesh_Object_Count 13"
"Mesh_FaceIndice_Format 46"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"
"------------------------------"
"loop1"
"Submesh_1_VB_Size 0"

```


Also uploaded the files here: [https://mega.nz/#!OJFAwAZR!TZ1vAFhiCdre ... brHn-CEbuQ](https://mega.nz/#!OJFAwAZR!TZ1vAFhiCdre_giqtgmojPo1xr4Hx6uOtbrHn-CEbuQ)

Help is much appreciated!
## Post #47
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-03T02:24:22+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #48
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-01-03T07:18:41+00:00
- Post Title: Re: SW Battlefront 2015 model files

Ha, yeah! I read about your importer in the other posts, this is looking pretty good!

Can you, by any chance, export the mesh to OBJ or something? - If I'm not asking for too much already.
If not, this is fine, I'll wait! 

thank you!
## Post #49
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-04T02:21:59+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-04T04:24:46+00:00
- Post Title: Re: SW Battlefront 2015 model files

or grab Hex2obj   
first submesh of atatwreck_01.chunk



atatwreck_01_chunk.png (36.93 KiB) Viewed 312 times



h2o file for first submesh

```
Vb1
48 36
0x0 4588
040100
0x0 255
```
## Post #51
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-04T04:46:20+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from AceWell
>
> or grab Hex2obj   
first submesh of atatwreck_01.chunk


h2o file for first submesh
Code: Select all0x7040F0 12360
Vb1
48 36
0x0 4588
040100
0x0 255

Yeah but you need to learn hex and try to find the starting point for each mesh and not everyone can understand that.
## Post #52
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-01-04T23:52:06+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from JakeGreen
>
> AceWell wrote:or grab Hex2obj   
first submesh of atatwreck_01.chunk


h2o file for first submesh
Code: Select all0x7040F0 12360
Vb1
48 36
0x0 4588
040100
0x0 255

Yeah but you need to learn hex and try to find the starting point for each mesh and not everyone can understand that.

Yesh, that's a struggle for me too. 
Not that I haven't tried, but it doesn't seem to get in my head. hehe.
Personally don't like to be requesting/asking stuff, so I really wish I could learn that.
## Post #53
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-06T15:38:42+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #54
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-07T05:35:10+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> You can find a SWBF 2015 loader on the UU3D plugins page.

That moment you see the program it's made for is stuck behind a pay wall if you wanna export said models.
## Post #55
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-07T15:46:44+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #56
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-19T04:09:39+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #57
- Username: badhorse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 14, 2016 11:00 am
- Post datetime: 2016-09-28T19:02:34+00:00
- Post Title: Re: SW Battlefront 2015 model files

Wobble -- I've been using the SWBF2015 import plugin for UU3D Pro for a few weeks not and it's been working great. However, with the new Death Star DLC, DICE seems to have added a new .meshset file format. The actual .meshset file is much larger than expected, and there is no corresponding .chunk file (see directory listing below). Looking at it with HexEdit (with my untrained eye), it really appears as though DICE has simply merged the two files -- like the chunk data picks up immediately following the meshset header. When I try to use the UU3D pro SWBF2015 import plugin, it actually reads the metadata correctly (e.g. lods, meshes, bones), but when I hit OK to complete the import, it gives me an error, I assume because there's no .chunk file. I tried manually splitting the file into separate .meshet and .chunk files, but without success. Any thoughts?
## Post #58
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-29T04:28:17+00:00
- Post Title: Re: SW Battlefront 2015 model files

> .... with the new Death Star DLC, DICE seems to have added a new .meshset file format. The actual .meshset file is much larger than expected, and there is no corresponding .chunk file... it really appears as though DICE has simply merged the two files -- like the chunk data picks up immediately following the meshset header.
you got any of these new samples?
## Post #59
- Username: badhorse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 14, 2016 11:00 am
- Post datetime: 2016-09-29T11:37:08+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from AceWell
>
> .... with the new Death Star DLC, DICE seems to have added a new .meshset file format. The actual .meshset file is much larger than expected, and there is no corresponding .chunk file... it really appears as though DICE has simply merged the two files -- like the chunk data picks up immediately following the meshset header.
you got any of these new samples?

Here's one.

[http://www.mediafire.com/file/j14jmr7ny ... t_mesh.rar](http://www.mediafire.com/file/j14jmr7ny5vqehz/stardestroyer_detailsside_07_right_mesh.rar)
## Post #60
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-09-30T00:17:55+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #61
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-30T05:36:48+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from badhorse
>
> Here's one.some scaling required for one axis (z in blender)?



stardestroyer_DS_07_rght_mesh.jpg (171.96 KiB) Viewed 245 times
## Post #62
- Username: parzivail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 04, 2016 5:46 am
- Post datetime: 2016-11-04T18:05:08+00:00
- Post Title: Re: SW Battlefront 2015 model files

Would there happen to be a complete file format description, or a Maya importer?
## Post #63
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-11-28T18:56:11+00:00
- Post Title: Re: SW Battlefront 2015 model files

Is the hex2obj the only way to convert the mesh/chunk files to an obj file?  I just need to get the vertices/model into blender  no need for texture or skeleton
## Post #64
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-28T21:17:06+00:00
- Post Title: Re: SW Battlefront 2015 model files

It's not the only way, for sure, but it's the simplest way I could think of
in case you can't script or code and don't have the luck to be a UU3D user.
## Post #65
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-12-08T18:32:29+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from shakotay2
>
> It's not the only way, for sure, but it's the simplest way I could think of
in case you can't script or code and don't have the luck to be a UU3D user.

Any way to get it to fbx?
## Post #66
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-08T18:46:09+00:00
- Post Title: Re: SW Battlefront 2015 model files

(in case you don't need weights and bones:)
once you've got it as obj there should be little problems to convert it to fbx
## Post #67
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-12-09T21:28:54+00:00
- Post Title: Re: SW Battlefront 2015 model files

Ok,  I gave it a shot.  the rar has the mesh and chunk file I'm messing with and jogs of what happened. I loaded the mesh. pressed go1 (see go1 picture) pressed go2 (see go2 picture) then go3 (see go3 picture).  Then not really sure what happened.  any help is greatly appreciated!
[heads_jingxu_01_hair_bob_02.zip](https://xentaxbackup.github.io/file/12001_heads_jingxu_01_hair_bob_02.zip)
## Post #68
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-12-09T21:33:12+00:00
- Post Title: Re: SW Battlefront 2015 model files

grrr post limit. Here are the jpgs
[go1.zip](https://xentaxbackup.github.io/file/12002_go1.zip)
## Post #69
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-09T23:16:26+00:00
- Post Title: Re: SW Battlefront 2015 model files

We should refrain from hijacking wobble's thread; see my answer here:
[viewtopic.php?f=29&t=14695&p=124145#p124145](http://forum.xentax.com/viewtopic.php?f=29&t=14695&p=124145#p124145)

btw: your uploaded pics show that you don't seem to have read the tutorial (tut button)
## Post #70
- Username: BAKMS
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 01, 2015 2:46 am
- Post datetime: 2017-01-04T15:13:29+00:00
- Post Title: Re: SW Battlefront 2015 model files

I am looking for the Y-Wing from Battlefront
Could someone help me out.
## Post #71
- Username: badhorse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 14, 2016 11:00 am
- Post datetime: 2017-01-26T04:16:02+00:00
- Post Title: Re: SW Battlefront 2015 model files

Not sure if anyone's still checking this thread, but I'm hoping someone with more experienced eyes can help me out. Without going into too much detail, I've been trying to extract the CR90 from the SWBF2015 Alpha for conversion into an FBX. There's a CR90 in the full released version of the game, but it's less detailed than the one in the Alpha. I used the SWBF_Tool, but that only exports OBJ, and I know that this model has multiple UV sets, so OBJ won't do. I managed to run a version of the python extraction script on the Alpha, so I now have both meshset and chunk files for the model. Usually at this point, I feed them to UU3D/Pro, and the rest is history, but for some reason I'm getting "SW Battlefron 2015 model import error". Looking at both files with HexEdit, to my untrained eye they look about how I would expect .meshset and .chunk files to look, but they refuse to load. Any ideas?

Here's a link to the files: [http://www.mediafire.com/file/u5ccjdvosyret44/CR90.rar](http://www.mediafire.com/file/u5ccjdvosyret44/CR90.rar)

Thanks in advance for any help.
## Post #72
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-26T06:30:13+00:00
- Post Title: Re: SW Battlefront 2015 model files

cr-90_easwbf.png (47.77 KiB) Viewed 79 times



```
http://www.mediafire.com/file/7s6zn1t9np4v9kv/CR90_0.zip
```
## Post #73
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-26T14:39:19+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #74
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-27T00:55:51+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
## Post #75
- Username: badhorse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 14, 2016 11:00 am
- Post datetime: 2017-01-27T02:46:37+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from Wobble
>
> Alright, one plugin can now load both.  To load alpha models, add ".alpha" to both the mesh and chunk filename.  For example:
cr90.alpha.meshset
cr90.alpha.chunk

Otherwise, the plugin will try to load the full version.

Worked like a charm! Thanks for the assist.
## Post #76
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-28T15:27:27+00:00
- Post Title: Re: SW Battlefront 2015 model files

> Reply from parzivail
>
> Would there happen to be a complete file format description, or a Maya importer?
there is that maxscript linked in this post but i can't make heads or tails from most of it
[viewtopic.php?f=33&t=13145](http://forum.xentax.com/viewtopic.php?f=33&t=13145)

i know enough about it to draw the meshes with UVs in Noesis and i will post my notes soon 



```
# http://forum.xentax.com/viewtopic.php?p=123087#p123087
# this is a single file and needs to be split at 0x1fd0 into a chunk file
	
header	
	0x20 - 4bytes - start LOD offsets for up to 7 LOD levels, 56 bytes total
				--offset for LOD0 data = 0x90

LOD0 data (0x90)
	0x90 - offset for first LOD data (LOD0)
	0x98 - 4bytes - num submeshes in LOD0 or maybe material groups (*see Checks)
	0x9c - 4bytes - offset to LOD0 section data (0x450)
	0xec - 4bytes - offset to start of face indices in *.chunk file

LOD0 section data (0x450)
	0x450 - start of LOD0 first submesh data
	0x458 - 4bytes - offset to first submesh name
	0x468 - 4bytes - num faces for first submesh --multiply by 3
	0x474 - 4bytes - num verts for first submesh
	0x484 - 2bytes - flag to indicate vertex type (0x701 = 1793 = HalfFloat)  (see vertex type table)
	0x486 - 2bytes - position in vertex format
		  --loop through these flag/pos shorts (total 64 bytes)
	0x4c4 - 2bytes - vertex stride for first submesh

	0x510 - start of LOD0 second submesh data
	#0x528 - num faces for second submesh --multiply by 3
	#0x534 - num verts for second submesh

	0x5d0 - start of LOD0 last submesh data
	#0x5e8 - num faces for third submesh --multiply by 3
	#0x5f4 - num verts for third submesh


--------------Vertex type table----------------------------------------------------------------
   Vert_Pos_Float           = 769  (0x301)
   Vert_Pos_HalfFloat       = 1793 (0x701)
   Vert_Pos_HalfFloat_plus  = 2049 (0x801) - add 2 to face indice offset only for z depth model 
   Vert_BiNormals           = 2054 (0x806)
   Vert_Tangents            = 2055 (0x807)
   Vert_Normals_UV          = 1569 (0x621) 
   Vert_Diffuse_UV          = 1570 (0x622) 
   Vert_Bone_Indices        = 3074 (0xc02)         
   Vert_Blend_Weights       = 3332 (0xd04)
   Vert_Unk_Flag1           = 1289 (0x509)
   Vert_Unk_Flag2           = 3358 (0xd1e) - for vehicles (?)
   Vert_Unk_Flag3           = 2056 (0x808)
   Vert_Unk_Flag4           = 1571 (0x623) - could be UV related
-----------------------------------------------------------------------------------------------


Checks
    Calculate length of LOD section data blocks for looping by number of submeshes
        0x28 read offset for LOD1 data 
        goto LOD1 data + 12 and read offset for LOD1 section data
        subtract LOD0 section data offset from LOD1 section data offset
        divide result by num of LOD0 submeshes

    Face indices could be word or dword
        read first 4 bytes of indices, if int > 0 they are word else dword
  
    The num submeshes may include collision etc and could be more than you need
        goto submesh name offset and read the string, if == 0 (zero), skip it
```


edit
there is another pretty good outline of the format for another frostbite game here
[http://zenhax.com/viewtopic.php?p=23000#p23000](http://zenhax.com/viewtopic.php?p=23000#p23000)
## Post #77
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-28T19:49:17+00:00
- Post Title: Re: SW Battlefront 2015 model files

[out]
