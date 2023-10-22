## Post #1
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-02-16T21:14:26+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

I've released a plugin to view models and animations from MGS4. This will allow you to view textured models without having to extract textures from their cache files, you can also view animations. To view animations you have to select 'Prompt for Motion Archive' in the tool menu. You can grab it here. [https://github.com/Jayveer/MGS-MDN-Noesis/releases](https://github.com/Jayveer/MGS-MDN-Noesis/releases)

It is worth reading the usage to see the various options. In particular if things aren't looking right you can choose 'Skip Normal Maps' in the options as there are material flags I haven't researched yet. As stage and slot files are linked the stage related slot files may require the DLZ and TXN files from their related stage files to be placed in their directory. In order to make sure you have the files extracted properly it's best to use the MGS4 extraction tool I made here here. [https://github.com/Jayveer/Solideye/releases](https://github.com/Jayveer/Solideye/releases)

EDIT: In a recent update I have added support for Metal Gear Arcade files and started implementing different material flags. I noticed a problem with Noesis when exporting an FBX file and having Multiple UVs. It creates a 'LayerElementMaterial' for each UV and only applies the material to the last one rather than all of them. There is something manual that can be done to resolve this. If you export with the -fbxascii flag, open the generated fbx file in a text editor of your choice, and then find and replace all instances of 'NoMappingInformation' with 'ByPolygon' and save it, then materials should resolve properly afterwards.
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-04-29T20:24:32+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

I know this isn't that relevant to the topic but will there be support for Portable Ops/Portable Ops Plus? It has some great character models and animations
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-04-29T23:32:34+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Eventually I'll add that to the peace walker plugin.
## Post #4
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2021-05-16T03:18:02+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Whoa Jay! This works like a charm! Thank you so much for releasing it. I was able to utilize the tool successfully with no problems at all.

The only thing I was having trouble with is that some models are separated from each other and the animations are out of sync when trying to link them all together. For example, Raven's wings are separate from her body and the animations don't line up when they are both imported and playing. It seems the animation sets are not lined up with each other and play independently. The same is true for Crying Wolf, the railgun, and the character inside the bot. For Wolf specifically, it's interesting because some of the railgun animations line up with the wolf-bot but then it gets out of sync as the sequence progresses. I also had to roughly line up where the railgun would be oriented and constrain it to the bot and it looks right until the animation desyncs.

In all honesty, it's nothing wrong with your plugin/script, just a technicality I suppose. I don't really know how you would fix this, perhaps having the animations split into separate clips instead of one whole sequence/file would make it easier to line up where the animations fit? Or maybe an option for the plugin could put the parts altogether when imported into Nosesis? Or maybe another solution? I wouldn't know. But either way, it's not a problem at all, more of a suggestion. I can get around this, it's just takes more time to split up all the animations into clips and to find the right one and line them up manually, just another project for me!
Still, excellent work, great stuff and let everyone know if you have any updates! Thanks again!
## Post #5
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-05-25T15:30:50+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

It was mentioned previously that you could use this command to split animations when exporting maybe that will help?

Single fbx file with the animations split inside instead of a single one long animation : -fbxmultitake
## Post #6
- Username: Sypheria
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 11, 2015 9:33 am
- Post datetime: 2021-06-27T09:45:51+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Does this work on stage/map files?

I'm trying to use it on the MGO maps specifically, I don't have MGS4 downloaded. 

As I understand it, textures are stored in a dlz file. How do you extract those textures? Noesis seems to be able to pull the textures, but only when you open an accompanying mdn file from the slot folders. The stage folders don't have mdn files, but geom files instead. And Solideye doesn't seem to work on the qar/dar in there either. 

I found a download for the MGO maps in obj format, but they don't have textures or even UVs. I'm at a loss on how to extract the models/textures myself. I don't mind having to sort and apply the textures completely manually, or manually fix bugged textures. But I can't manage to get the textures or UV'd models in the first place. I found a video of C.C. with textures, so it must be possible somehow.
## Post #7
- Username: bestgj
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 10, 2021 9:36 am
- Post datetime: 2021-08-10T02:15:30+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Very good. I learned to use it
## Post #8
- Username: bestgj
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 10, 2021 9:36 am
- Post datetime: 2021-08-11T03:47:18+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Finger animation stiff
## Post #9
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2022-01-30T00:16:23+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

I have posted an update to the Solideye tool which now allows you to decrypt files from the stage folders of the MGS4 Database, Metal Gear Online and the MGS4 Demo package. It also adds basic Dar and Qar file repacking features. You can get the update here;

[https://github.com/Jayveer/Solideye/releases/tag/1.2](https://github.com/Jayveer/Solideye/releases/tag/1.2)
## Post #10
- Username: jimmy12345
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 06, 2021 12:24 pm
- Post datetime: 2022-02-28T03:22:46+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

This tool is for PS3 Game iso?
## Post #11
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2022-02-28T09:55:59+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

> Reply from jimmy12345 ↑Mon Feb 28, 2022 11:22 am at Mon Feb 28, 2022 11:22 am
>
> 
This tool is for PS3 Game iso?

yes
## Post #12
- Username: darkside970
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 21, 2018 12:56 am
- Post datetime: 2022-03-18T21:50:15+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

One question, is there a possibility to import models from MGS3 HD to noesis?
## Post #13
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2022-03-19T11:43:30+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Yeah there is, but it's not high on the priority list for me to make that plugin right now.
## Post #14
- Username: FatTpose
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 24, 2022 8:05 pm
- Post datetime: 2022-05-11T23:35:36+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

Thanks for this plugin tool, works like a charm.

Just a question though, are the cutscenes pre-rendered or are the animations stored inside one of those MTAR files
## Post #15
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2022-05-15T10:15:54+00:00
- Post Title: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

They're not pre-rendered except for the Eastern Europe river custscene. They use mtar's as well but there's more to those ones and I haven't worked on those ever.
## Post #16
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-08-02T11:05:29+00:00
- Post Title: Re: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

> Reply from JayK ↑Wed Feb 17, 2021 5:14 am at Wed Feb 17, 2021 5:14 am
>
> 
I've released a plugin to view models and animations from MGS4. This will allow you to view textured models without having to extract textures from their cache files, you can also view animations. To view animations you have to select 'Prompt for Motion Archive' in the tool menu. You can grab it here. https://github.com/Jayveer/MGS-MDN-Noesis/releases

It is worth reading the usage to see the various options. In particular if things aren't looking right you can choose 'Skip Normal Maps' in the options as there are material flags I haven't researched yet. As stage and slot files are linked the stage related slot files may require the DLZ and TXN files from their related stage files to be placed in their directory. In order to make sure you have the files extracted properly it's best to use the MGS4 extraction tool I made here here. https://github.com/Jayveer/Solideye/releases

EDIT: In a recent update I have added support for Metal Gear Arcade files and started implementing different material flags. I noticed a problem with Noesis when exporting an FBX file and having Multiple UVs. It creates a 'LayerElementMaterial' for each UV and only applies the material to the last one rather than all of them. There is something manual that can be done to resolve this. If you export with the -fbxascii flag, open the generated fbx file in a text editor of your choice, and then find and replace all instances of 'NoMappingInformation' with 'ByPolygon' and save it, then materials should resolve properly afterwards.


when trying to load or export some from the stage02/s02a85I folder the plugin crashes and keeps loading forever and makes noesis unresponsive
## Post #17
- Username: segabit
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 21, 2016 3:05 am
- Post datetime: 2022-12-17T16:38:10+00:00
- Post Title: Re: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

> when trying to load or export some from the stage02/s02a85I folder the plugin crashes and keeps loading forever and makes noesis unresponsive

I independently found this issue too. In addition, stage01/s01a55l has the same issue. Every single mdn file in both of these folders crashes Noesis, even when copied elsewhere to be loaded independently. I looked at them in a hex editor and nothing looked wrong to me. I even tried doing a batch export in case it was the viewing of the model that caused the issue, but that also resulted in an endless hang. I confirmed that all of the other folders work fine.

Another issue I found was that there are a handful of textures that don't seem to decrypt properly. Here's BigMama's hair in Stage03/s03a90l/78a3f2 (and other locations where this is duplicated).



BigMamaHair0_tex00.png (127.93 KiB) Viewed 88 times



Second example is from Stage04/s04a30l/173111 (as well as other duplicate locations), in the warning labels on the Crying Wolf Beast. They are offset in this weird way here:



Third is a palm tree at Stage00/s30a00l/e0c06a



That being said, I went through and looked at every single model in the game, and those were the only texture issues that stuck out to me. This plugin is so good! Thank you very much for making this. I couldn't have dug into all of this without your work.
## Post #18
- Username: Bungdrtyu
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 13, 2023 1:04 am
- Post datetime: 2023-01-22T23:36:52+00:00
- Post Title: Re: Metal Gear Solid 4 Noesis Plugin (Models, Anims)

> Reply from JayK ↑Sun May 15, 2022 6:15 pm at Sun May 15, 2022 6:15 pm
>
> 
They're not pre-rendered except for the Eastern Europe river custscene. They use mtar's as well but there's more to those ones and I haven't worked on those ever.

I can't put into words how amazing this would be if you got it working!
