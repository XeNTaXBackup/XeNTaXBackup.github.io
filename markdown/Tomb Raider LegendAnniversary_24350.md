## Post #1
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2021-08-12T14:31:56+00:00
- Post Title: Tomb Raider Legend/Anniversary

Over the past few months, I've been researching Tomb Raider Legend/Anniversary's mesh format. There was already a Noesis plugin to import models from Tomb Raider: Legend, by Gh0stBlade, but it only works to import the Next-Gen version of the models (Next-Gen is a mode that can be enabled in the game, and changes the whole aspect of the game providing higher poly geometry for levels and character models, and supports normal and specular maps). This mode can be enabled in Anniversary too via the advances settings tab in the setup, but no Next-Gen assets have been made for the game, so enabling it will just break the game and make it crash. So this means that no models from Tomb Raider: Anniversary could be ripped from the files, if not by using 3D Ripper DX/Ninja Ripper or other softwares like that to rip geometry in runtime.

After a lot of time of searching, I figured out the Old-Gen meshes are stored in .GNC files, inside the .DRM files. DKDave helped writing a Noesis plugin to import the models from that format, and he's done an amazing job figuring out all the components (normals, UVs, weights) also thanks to the help of Joschka, Aesirhod, akderebur and others from the Xentax Discord server. He also managed to directly read the models from the .DRM files, with all textures loaded too, making it unnecessary to unpack the DRMs, if your only goal is to rip the models. Here's some examples:





I have also been researching the texture formats used by the game (.PCD, .RAW). I made it possible to import and export custom textures to these formats (.PCD is used inside the .DRM files, .RAW is used outside of them, for things like loading screens and concept arts screens).

I researched these texture formats for the PS3 version of the games too, and I have made it possible to import .PCD and .RAW texture files in Noesis from the PS3 version of the game. Many thanks go to TheIndra for helping with this.


Features

- Importing models and textures from/to .DRM files (PC)
- Importing and exporting models from/to .TR7AEMESH files (PC)
- Importing and exporting textures from/to .PCD files (PC, PS3)
- Importing and exporting textures from/to .RAW files (PC, PS3)
- Importing BGObjects from .DRM files (PC)



Every feature of this plugin works for both Tomb Raider Legend and Anniversary.



CHANGELOG:

16 August 2021: Changed the bone names from being "Bone_X" to "bonexxx" to make it consistent with the other Noesis plugins for the newer TR games (Underworld, TR2013, ROTTR, SOTTR).

21 March 2022: Added code to import BGObjects by TheIndra. BGObjects are basically "accessory" meshes that appear in level files. You can import them by looking at the levels' drm files (puxx, maxx, egxx and so on). If there are some level files that just won't load, that just means that the .drm file has no BGObjects.

EXPORTER:

v1.0 - Initial release

v1.1 - Optimized the code to write VirtSegments. Now they are being written 100% correctly.
v1.1 - Fixed an issue where a random vertex would get corrupted UVs. That happened because I wasn't correctly writing envMappedVertices and EyeRefEnvMappedVertices.

v1.2 - Added a prompt to export over Lara's original 5_0.tr7aemesh file to get HInfo (signals trigger and weapon attachments).
v1.2 - Added code to write tpageid and drawgroup from the mesh names.
v1.2 - Added code to add export parameters to remove gear attachments.

v1.3 - Fixed an issue where exporting with -noshotgun would also remove the guns attachment.

v1.4 - Fixed an issue where importing some weapon .tr7aemesh files would cause an error.
v1.4 - Tweaked code to hide gun and shotgun. Now they are completely invisible, and the instances are not birthed at all if Lara is not equipping the weapons.

v1.5 - Replaced mesh .gnc extension to .tr7aemesh in favour of the new DRM Tool update by TheIndra.

v1.6 - Added code to add an export parameter to remove all gear attachments except grapple hook since that breaks the mechanic.

v1.7 - Added code to remove the .XXX suffix from mesh names which gets added in Blender if it detects the same mesh name on more meshes.

TO DO:

- Make the exporter able to export over any .tr7aemesh file, write all the HInfo of the donor file (if present) and write the section reference of the donor file

- Figure out how to write MFace data in order to be able to write custom wetmasks, dirtmasks and some specific model files such as g_lara.drm
[fmt_tr7ae1.7.7z](https://xentaxbackup.github.io/file/22670_fmt_tr7ae1.7.7z)
## Post #2
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2021-08-13T00:12:16+00:00
- Post Title: Tomb Raider Legend/Anniversary

OK, you guys rock!!  Have always wanted to be able to rip TRA models!
## Post #3
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-06-19T20:00:31+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Thu Aug 12, 2021 10:31 pm at Thu Aug 12, 2021 10:31 pm
>
> 
After a lot of time of searching, I figured out the Old-Gen meshes are stored in .GNC files, inside the .DRM files. DKDave helped writing a Noesis plugin to import the models from that format, and he's done an amazing job figuring out all the components (normals, UVs, weights) also thanks to the help of Joschka, Aesirhod, akderebur and others from the Xentax Discord server. He also managed to directly read the models from the .DRM files, with all textures loaded too, making it unnecessary to unpack them, if your only goal is to rip the models.

That's great. Is there any info available somewhere on .GNC file format, or any tool or know-how how to "extract" them from .DRM files. (Also any info on .DRM file structure/format?)


> Reply from Raq ↑Thu Aug 12, 2021 10:31 pm at Thu Aug 12, 2021 10:31 pm
>
> I have also been researching the texture formats used by the game (.PCD, .RAW). I made it possible to import and export custom textures to these formats (.PCD is used inside the .DRM files, .RAW is used outside of them, for things like loading screens and concept arts screens).

Any info on PCD format? Right now textures can be replaced with Texmod, but once we can replace models it would make more sense to replace those directly in DRM file along with the model.


> Reply from Raq ↑Thu Aug 12, 2021 10:31 pm at Thu Aug 12, 2021 10:31 pm
>
> So, summarizing, this script includes:

- Importing models and textures from .DRM files
- Importing models from .GNC files
- Importing and exporting textures from/to .PCD files
- Importing and exporting textures from/to .RAW files
- Importing textures from .PCD files (PS3)
- Importing textures from .RAW files (PS3)

That's fantastic, but what about exporting them back to DRM? Surely if someone wrote importing, exporting would be just reverse process.

I understand that DRM contains much more data than just model files, so probably exported file would be intermediary and would contain just model data (meshes, vertex data, UV maps, weights and probably skeleton) (is this GNC file?) and converting to game loadable DRM would require another step - an external program that takes as an input such exported intermediary model data and original .DRM file from game and create new DRM file with replaced model data.

So I would like to have exporting procedure even with those incomplete data (model only).

So far with your script I can load Anniversary models into Blender and edit them, but there is no way to export them back to game compatible format or even something close to it. This is the last piece of the puzzle that is missing.
## Post #4
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-06-22T07:59:50+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Greg5 ↑Mon Jun 20, 2022 4:00 am at Mon Jun 20, 2022 4:00 am
>
> 

Is there any info available somewhere on .GNC file format, or any tool or know-how how to "extract" them from .DRM files. (Also any info on .DRM file structure/format?)

I wrote a full overview of the .GNC file format in my GitHub, with an included binary template for 010 Editor: [https://github.com/Raq1/TR7AE-Mesh-Format](https://github.com/Raq1/TR7AE-Mesh-Format)

I also made a video showing the process of extracting DRM files, modding textures and more: [https://www.youtube.com/watch?v=cdmOsXdNtmY&t=2s](https://www.youtube.com/watch?v=cdmOsXdNtmY&t=2s)

> Reply from Greg5 ↑Mon Jun 20, 2022 4:00 am at Mon Jun 20, 2022 4:00 am
>
> Any info on PCD format? Right now textures can be replaced with Texmod, but once we can replace models it would make more sense to replace those directly in DRM file along with the model.

It is already possible to replace textures without using TexMod, with the tutorial I linked above.


> Reply from Greg5 ↑Mon Jun 20, 2022 4:00 am at Mon Jun 20, 2022 4:00 am
>
> That's fantastic, but what about exporting them back to DRM? Surely if someone wrote importing, exporting would be just reverse process.

I understand that DRM contains much more data than just model files, so probably exported file would be intermediary and would contain just model data (meshes, vertex data, UV maps, weights and probably skeleton) (is this GNC file?) and converting to game loadable DRM would require another step - an external program that takes as an input such exported intermediary model data and original .DRM file from game and create new DRM file with replaced model data.

So I would like to have exporting procedure even with those incomplete data (model only).

So far with your script I can load Anniversary models into Blender and edit them, but there is no way to export them back to game compatible format or even something close to it. This is the last piece of the puzzle that is missing.

First of all, do not underestimate the effort that goes in making an exporter. Just because an importer is possible, an exporter not always is. Especially with a format like DRM, which contains a LOT of data which has a lot of specific flags which were determined during development and are hardcoded.

It is already possible to make mesh mods for Legend and Anniversary, I made a lot of them, example: [https://twitter.com/CroftCrazy31/status ... 27680?s=20](https://twitter.com/CroftCrazy31/status/1417117961177927680?s=20)

But the tools are not ready and it will still take a lot of time to release them because Irastris doesn't have time to continue them. Maybe one day I'll try to finish them myself, I don't know.
## Post #5
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-06-23T01:41:47+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Wed Jun 22, 2022 3:59 pm at Wed Jun 22, 2022 3:59 pm
>
> 
I wrote a full overview of the .GNC file format in my GitHub, with an included binary template for 010 Editor: https://github.com/Raq1/TR7AE-Mesh-Format

I also made a video showing the process of extracting DRM files, modding textures and more: https://www.youtube.com/watch?v=cdmOsXdNtmY&t=2s

Thanks for those links! Before I first posted here I managed to find only bigfile packer/unpacker on [tombraiderforums](https://www.tombraiderforums.com/showthread.php?t=192773) and indeed I was able to change/switch some .drm files with it (like replace lara models in outfit selection menu).

After my initial post I researched this further and found DRM Extractor/Repacker ([https://github.com/Gh0stBlade/cdcEngineTools](https://github.com/Gh0stBlade/cdcEngineTools)) and PCD2DDS converter that allowed converting PCD textures back and forth so I was able to build modified .DRM files with modified textures and load them into game by repacking bigfile using previous tool.

But after wathing your video I realize I can export textures to PCD directly from Noesis which is more convienient (doesn't require dealing with DDS and also PCD2DDS was kinda buggy and required fixing headers with hex editor).

But most importantly I was able to get to those GNC files by unpacking DRM and indeed it seems I was correct that being able to edit those GNC files is the last piece of the puzzle left to solve to have model editing.


I started writing GNC import script for Blender looking at the code of your Noesis script (now I will also try to use the info from your .GNC file format overview) and if I succceed and am able to import .GNC files to Blender directly, I will try to write export script as well.


And I finally managed to get the [TRAE-menu-hook](https://github.com/TheIndra55/TRAE-menu-hook) working. I found it earlier too, but downloaded wrong binkw32.dll and thought this utility is not working with GOG.com version. Now it loads fine. This will be super usefull for testing/debugging exported models in game if I ever get there. Without it I would have to repack and copy 4 Gigabyte database everytime I want to change model, which woudn't be very efficient way of doing it.
## Post #6
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-06-24T12:36:11+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Greg5 ↑Thu Jun 23, 2022 9:41 am at Thu Jun 23, 2022 9:41 am
>
> 
Raq wrote: ↑Wed Jun 22, 2022 3:59 pm
I wrote a full overview of the .GNC file format in my GitHub, with an included binary template for 010 Editor: https://github.com/Raq1/TR7AE-Mesh-Format

I also made a video showing the process of extracting DRM files, modding textures and more: https://www.youtube.com/watch?v=cdmOsXdNtmY&t=2s

But most importantly I was able to get to those GNC files by unpacking DRM and indeed it seems I was correct that being able to edit those GNC files is the last piece of the puzzle left to solve to have model editing.


I started writing GNC import script for Blender looking at the code of your Noesis script (now I will also try to use the info from your .GNC file format overview) and if I succceed and am able to import .GNC files to Blender directly, I will try to write export script as well.

That's awesome! If you need any further help with the format other than my documentation on GitHub don't hesitate to contact me on Discord, Raq#6517
## Post #7
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-06-25T17:17:45+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Fri Jun 24, 2022 8:36 pm at Fri Jun 24, 2022 8:36 pm
>
> 
Greg5 wrote: ↑Thu Jun 23, 2022 9:41 am
I started writing GNC import script for Blender looking at the code of your Noesis script (now I will also try to use the info from your .GNC file format overview) and if I succceed and am able to import .GNC files to Blender directly, I will try to write export script as well.


That's awesome! If you need any further help with the format other than my documentation on GitHub don't hesitate to contact me on Discord, Raq#6517

Well, writing a plugin turn out to be not the best idea given my near zero knowledge of both Blender API and Python. 

I will try instead to write converter from .GNC to some established 3D format like .FBX or Collada. This way I can do it in language I'm familiar with and the added benefit is that this will allow to import the model to any 3D software. I only need to choose the output format and learn it before I start.


If I have a working converter from GNC to known 3D format and run into probems converting it back to .GNC I will surely contact you.
## Post #8
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-06-27T17:22:30+00:00
- Post Title: Tomb Raider Legend/Anniversary

The Noesis Plugin that is linked in the first post can already convert .GNC to .FBX, which can then be imported into any 3D program, so I'm not sure what the point of that would be
## Post #9
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-02T12:07:08+00:00
- Post Title: Tomb Raider Legend/Anniversary

The Noesis Plugin can't convert back to .GNC. I thoght it was obvious from my first post that I'm interested in complete 2 way solution.

I would really like to load a higher poly model into game.
## Post #10
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-07-03T02:49:15+00:00
- Post Title: Tomb Raider Legend/Anniversary

You'd need a complete understanding of how data is stored and structured in the .gnc file, as well as a complete understanding of how data is stored and structured in a .drm file.  I don't think either file type has been completely reverse engineered.
## Post #11
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-05T18:39:19+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from nightwolf1982 ↑Sun Jul 03, 2022 10:49 am at Sun Jul 03, 2022 10:49 am
>
> 
You'd need a complete understanding of how data is stored and structured in the .gnc file, as well as a complete understanding of how data is stored and structured in a .drm file.  I don't think either file type has been completely reverse engineered.

I just sent a GitHub with my full documentaion of the .GNC format in my long reply above. And Indra also made a full documentation of the .DRM format. We have all the documentation, we just lack tools.
## Post #12
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-09T19:10:33+00:00
- Post Title: Tomb Raider Legend/Anniversary

Thanks to the help of alphaZomega and peeps from the Xentax Discord server (Edness to be more specific, helped with writing the UVs) I was able to write an exporter to the format with Noesis. For now it writes vertex positions, normal vectors and UVs.



Technically the exporter would already be ready for exporting static objects, but I won't release it now anyway as I still want to improve the way it writes the file. For now it just copies the data from another .gnc file and just writes the vertex and face data, but I want to be able to just write a .gnc file from scratch, I think I got some ideas on how to do that.

Also no skinning yet. That is probably the hardest thing to deal with given how weirdly the weights are stored in this format.

The calculation of the scaling of the vertices is also not 100% accurate, I need to figure out what's the correct calculation.
## Post #13
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-10T14:39:45+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from nightwolf1982 ↑Sun Jul 03, 2022 10:49 am at Sun Jul 03, 2022 10:49 am
>
> 
You'd need a complete understanding of how data is stored and structured in the .gnc file, as well as a complete understanding of how data is stored and structured in a .drm file.  I don't think either file type has been completely reverse engineered.

There is a .drm format packer/repacker I linked in my post earlier, so the only thing is .gnc format, but people had been working on it as well (see Raq's replies).

I started playing TRA with default model (in Natla's mine now ), but I will probably want to play it once more in some time with new model hopefully. Minor modification to a model like changing few vertices can be done easily possible, only with bigger changes like increased polygon count you could run into problems if you don't have full spec. If you have more vertices you will also have more weights and larger UV-maps and normal maps.

> Reply from Raq ↑Sun Jul 10, 2022 3:10 am at Sun Jul 10, 2022 3:10 am
>
> 
Thanks to the help of alphaZomega and peeps from the Xentax Discord server (Edness to be more specific, helped with writing the UVs) I was able to write an exporter to the format with Noesis.
To gnc?

> Reply from Raq ↑Sun Jul 10, 2022 3:10 am at Sun Jul 10, 2022 3:10 am
>
> For now it writes vertex positions, normal vectors and UVs.
And weights?

> Reply from Raq ↑Sun Jul 10, 2022 3:10 am at Sun Jul 10, 2022 3:10 am
>
> 2
This looks like meshes are not attached to skeleton. If you try to run model from other TR game you probably can do it, but you will need to transfer weights from TRA meshes to the model you want to use (and have the same mesh layout/naming ofc). It's generally more work, so for testing it's better to modify original TRA model a bit and see if it works fine.

> Reply from Raq ↑Sun Jul 10, 2022 3:10 am at Sun Jul 10, 2022 3:10 am
>
> Technically the exporter would already be ready for exporting static objects, but I won't release it now anyway as I still want to improve the way it writes the file. For now it just copies the data from another .gnc file and just writes the vertex and face data, but I want to be able to just write a .gnc file from scratch, I think I got some ideas on how to do that.

Also no skinning yet. That is probably the hardest thing to deal with given how weirdly the weights are stored in this format.

What you mean by "no skinning yet". Skinning normally means textures and this has been covered basically from day one.
## Post #14
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-10T22:35:05+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Greg5 ↑Sun Jul 10, 2022 10:39 pm at Sun Jul 10, 2022 10:39 pm
>
> 
Raq wrote: ↑Sun Jul 10, 2022 3:10 am
Thanks to the help of alphaZomega and peeps from the Xentax Discord server (Edness to be more specific, helped with writing the UVs) I was able to write an exporter to the format with Noesis.
To gnc?
Yes, to gnc.

> Reply from Greg5 ↑Sun Jul 10, 2022 10:39 pm at Sun Jul 10, 2022 10:39 pm
>
> And weights?
Skinning = weights. So no. No weights yet.

> Reply from Raq ↑Sun Jul 10, 2022 3:10 am at Sun Jul 10, 2022 3:10 am
>
> Picture

> Reply from Greg5 ↑Sun Jul 10, 2022 10:39 pm at Sun Jul 10, 2022 10:39 pm
>
> This looks like meshes are not attached to skeleton. If you try to run model from other TR game you probably can do it, but you will need to transfer weights from TRA meshes to the model you want to use (and have the same mesh layout/naming ofc). It's generally more work, so for testing it's better to modify original TRA model a bit and see if it works fine.
As I said, skinning is not yet supported. Also, transfer weights is not needed.

> Reply from Greg5 ↑Sun Jul 10, 2022 10:39 pm at Sun Jul 10, 2022 10:39 pm
>
> What you mean by "no skinning yet". Skinning normally means textures and this has been covered basically from day one.

Never heard of skinning being related to textures. Skinning means weights in 3D.
## Post #15
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-11T18:29:56+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Mon Jul 11, 2022 6:35 am at Mon Jul 11, 2022 6:35 am
>
> 
Never heard of skinning being related to textures. Skinning means weights in 3D.

It seems you are right. I've just never seen this term used to describe weight painting...

In MMORPGs models are highly customisable including various skin colours, facial textures, makeups, etc., independently of outfit textures.
So I confused the term with making skin textures.   In TRA only one skin texture and one outfit textures per model...


Anyway I hope you get exporting working and I won't have to work on it.
## Post #16
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-13T12:59:43+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Thanks to the huge help by Joschka on the Discord server, the Noesis plugin is now able to write weights



Unfortunately, only 1 weight per vertex can be written as for now. I'm having a lot of trouble understanding some things.

I'm going to write an overview of how the weights in this format are written:

First of all, keep in mind the word Segments. This is the game's terminology for bones. For weights, they call them VirtSegments (full word is probably Virtual Segments)

This is a Segment:



The first 8 values (the min/max ones) are most likely bounding boxes which are only used during the development of the game for debug. So these values can be written as 0, it won't make any difference ingame.

The next 4 values are the bone positions (W is always 1065353216). Next value, flags, is always 0.

Now we have the next 2 values, FirstVertex and LastVertex. These values are needed to declare which vertices will be using this Segment. For example, if FirstVertex is 5 and LastVertex is 10, the Segment is going to be used for the vertices from 5 to 10.

Next value is the bone parent, then HInfo which is an offset to the Segment's HInfo. HInfo is basically information on some stuff to add to the bones or something (for example, they are used for the weapon attachments, like making the pistols "glued" to the leg bones).

Now, let's see a VirtSegment:



The first 8 values are for bounding boxes again, like the Segments.

After that, we have some bone positions. These bone positions are the ones from the bone referenced in weightIndex. In fact, if you look at the bone positions of the VirtSegment and the ones of the Segment, you'll notice they're the same, with a difference: the ones in the VirtSegment are inverted (0.1608615 becomes -0.1608615)

flags is always 8

First/LastVertex have the same purpose

index is the bone index to which the "rest" of the weight goes. weightIndex is the bone index to which weight declared in weight goes.



Now, you would think that I know how everything is working and that I should be able to use all this info to write the second weight. But no, there is one thing that I still cannot wrap my head around with.

Some VirtSegments have a completely new bone position that is not present in neither of the mentioned bone indices. After some tinkering, I figured out that it's a sum between the bone positions of both bones. This confuses me a lot because I cannot find a criteria in which this has to be done. Does it have to be done when the two bone indices are numbers that are very far away from each other (like 2 and 100)? Or does it have to be done when the weight has a specific value? I really don't know and this is making my mind explode. If anyone wants to help me figure this out I would be very grateful lol
## Post #17
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-13T23:40:18+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Latest progress: I managed to write the second weight for most of the model correctly. I don't know why the face is all screwed up like that, I think there needs to be done a different calculation of the bone positions for the VirtSegments of some vertices, but for now I'm clueless.
## Post #18
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-14T12:55:18+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Wed Jul 13, 2022 8:59 pm at Wed Jul 13, 2022 8:59 pm
>
> 
Next value is the bone parent, then HInfo which is an offset to the Segment's HInfo. HInfo is basically information on some stuff to add to the bones or something (for example, they are used for the weapon attachments, like making the pistols "glued" to the leg bones).

These are attachment points. I've noticed your importer (or Noesis' fbx exporter) do not support those as after loading model into Blender they ae not present.

This is minor issue of course, because people will need to edit attachment points only if they doing something crazy like much slimmer or rounder/curvier version of Lara. Then they would need to move those attachment points to avoid guns floating next to Lara's legs or be inside her legs.


> Reply from Raq ↑Thu Jul 14, 2022 7:40 am at Thu Jul 14, 2022 7:40 am
>
> 
Latest progress: I managed to write the second weight for most of the model correctly. I don't know why the face is all screwed up like that, I think there needs to be done a different calculation of the bone positions for the VirtSegments of some vertices, but for now I'm clueless.

It's hard to guess just from image but I've seen similar things happpen when developers made some changes in game to a model and you tried to load older model. These changes usually were some bones shifts / weighs changes. From what you wrote before you don't need weight transfer for TRAOD Lara, so I'm guessing there were none to little changes in Lara's skeleton between TRAOD and TRA (I don't have TRAOD lara models to check it).

So my guess it could be either caused by weights on TRAOD Lara's face not really maching TRA skeleton, or if you're copying TRAOD bones positions (which I guess you do) to TRA model and since they shrinked Lara's head in TRA (so facial bones are at different locations) TRA facial animations will not work well with TRAOD bones positions. So even if you write weights correctly it might not work with older models without extra model editing to correctly "port" it.

Could you upload your TRAOD Lara model somewhere in .fbx format, so I could load in into editor and look up differences?
## Post #19
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-14T18:59:18+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Latest progress: Got most of the face virtSegments to write correctly. Still a little bit of tinkering for the rest and then the exporter should finally be able to fully export 2 weights.
## Post #20
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-14T19:30:09+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Wow! Can't wait. It looks better and better.
## Post #21
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-16T17:57:28+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

The Noesis plugin is now able to fully export weights!

The process to do this was extremely weird. Most virtSegments are written in a common way, but some virtSegments require a different calculation of their pivots, depending on the bone indices.

I also ported this other model as a test, made by HenrysArts, a friend of mine. It actually helped me add a couple more ifs for other bone indices which needed fixing.

The plugin is not yet ready for release, but it will be soon. I still need to figure out how to write multiple meshes and then I have to re-organize the entire code to make it so it exports a game-ready file. (Until now I had to export the data to a .gnc file and manually copy some stuff to another .gnc file which was ready for the game)

I gotta thank again alphaZomega and Joschka for extensively helping with this





The code for all of this is kinda disgusting but I don't think there is a better way to organize this lol



EDIT: Turns out there is, thanks to Joschka for suggesting this
## Post #22
- Username: fitz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 02, 2017 5:09 am
- Post datetime: 2022-07-16T21:02:02+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Would it be possible to import Anniversary braid hairstyle into Legend, or Legend ponytail hairstyle into Anniversary?

Also, could a mod be created for both Legend and Anniversary to swap the classic hairstyle with this one: 
[https://youtu.be/ze5u9qi4Fbg?t=24](https://youtu.be/ze5u9qi4Fbg?t=24) ?
## Post #23
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-18T15:37:01+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Once the plugin will be released you'll be able to create any kind of mod you desire
## Post #24
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-18T15:46:04+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Sun Jul 17, 2022 1:57 am at Sun Jul 17, 2022 1:57 am
>
> 

It's still does the same only coded in more compact way. I hope I'm wrong but this really gets me worried. Will this exporter be general purpose or this "hand-tuning" will make it work only with TRAOD models...


> Reply from fitz ↑Sun Jul 17, 2022 5:02 am at Sun Jul 17, 2022 5:02 am
>
> 
Would it be possible to import Anniversary braid hairstyle into Legend, or Legend ponytail hairstyle into Anniversary?

Also, could a mod be created for both Legend and Anniversary to swap the classic hairstyle with this one: 
https://youtu.be/ze5u9qi4Fbg?t=24 ?

With general purpose exporter you could convert any models that can be matched upon TRA's skeleton, even models from other games. So those hairstyles look like could be brought into TRA once there is working exporter. So wait for exporter to be published and if/when that happens you can think about switching or editing meshes.
## Post #25
- Username: fitz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 02, 2017 5:09 am
- Post datetime: 2022-07-18T22:00:28+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Many thanks for your helpful and exciting answers!
Can't wait to see these turned into actual mods:
[https://www.deviantart.com/henrysdlcs/a ... -860018952](https://www.deviantart.com/henrysdlcs/art/XPS-Beta-Legend-Lara-Pack-860018952)
## Post #26
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-19T03:05:57+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

The Noesis exporter is now able to write multiple meshes!

I did this thanks to the help by alphaZomega and Joschka again. It was very tricky but at the end we managed to get multiple meshes written in one .gnc file. The exporter is very close to being considered done, I just need to write the code to make it create a game-ready .gnc instead of the mess I've been doing until now.



Higher res version of the picture here: [https://cdn.discordapp.com/attachments/ ... a_coso.png](https://cdn.discordapp.com/attachments/922284054353674273/998786551339302983/cosa_coso.png)

This model contains 11 meshes, all with their own texture. It's also a very high poly model, being 19476 vertices and 31139 faces. The model was extracted from The Last of Us and ported to the game without any kind of decimation, it's the original geometry. The vertex count is actually very close to the limit, being 21850. This is very exciting and I can't wait to see what you people will do once the exporter is released. We're very close!
## Post #27
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-19T17:49:46+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Tue Jul 19, 2022 11:05 am at Tue Jul 19, 2022 11:05 am
>
> 
The Noesis exporter is now able to write multiple meshes!

I did this thanks to the help by alphaZomega and Joschka again. It was very tricky but at the end we managed to get multiple meshes written in one .gnc file. The exporter is very close to being considered done, I just need to write the code to make it create a game-ready .gnc instead of the mess I've been doing until now.

If you are able to write meshes I suggest exporting them to intermediary format, say with .ignc extention and then leaving instructions how to build game ready .gnc file.

Someone will eventually automate this by writing external program to take as input such .ignc and source .gnc to generate final game ready .gnc.


If .gnc files contain some game specific data - it might be lost when loading in 3d editors and your exporter won't be able then to generate complete .gnc file, unless you're going to do something awkward during export process like asking user for original/source .gnc so you can load that missing data.
## Post #28
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-28T16:37:29+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

First public release of the exporter is here!

After a lot of testing by me and some modders from the Tomb Raider Modding Discord server, the first public release of the exporter is now available. I will also update the first post of the thread.

The exporter has already been used to make many awesome mods by me, HenrysArts, EvilLord, Nicotsu and lifeistombraider. The two screenshots on the bottom right have been made by franqui. 

I've made a video tutorial on how to use the exporter, you can see it here: [https://www.youtube.com/watch?v=3DYFVwyHF1Q](https://www.youtube.com/watch?v=3DYFVwyHF1Q)


[fmt_tr7ae.7z](https://xentaxbackup.github.io/file/22570_fmt_tr7ae.7z)
## Post #29
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-07-28T18:59:47+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Ah, i see now why Ghostblade banned me from discord. Because you two are Tomb Raider lovers or something. You have 18 post to my 160. Been on that server for two years here for 4 years.. Sad to see such power abused.
## Post #30
- Username: Raq
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2022-07-28T19:24:09+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Sharppy ↑Fri Jul 29, 2022 2:59 am at Fri Jul 29, 2022 2:59 am
>
> 
Ah, i see now why Ghostblade banned me from discord. Because you two are Tomb Raider lovers or something. You have 18 post to my 160. Been on that server for two years here for 4 years.. Sad to see such power abused.

No power has been abused here. You know what you are doing. Calling out users for no reason making them feel unwelcome etc. I have also applied a ban to your fourm account for continuing drama from other platforms. Have a good day.

-Gh0stblade.
## Post #31
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-30T12:20:52+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Fri Jul 29, 2022 12:37 am at Fri Jul 29, 2022 12:37 am
>
> 
First public release of the exporter is here!

After a lot of testing by me and some modders from the Tomb Raider Modding Discord server, the first public release of the exporter is now available. I will also update the first post of the thread.

Wow! Awesome job! I've tested it a bit and was able to load higher poly model in game (increased vertice count for one mesh and edited it a bit).



Are you planning to add support for other models? If I change Anniversary model, I would like to also change frontend_lara and c_lara (model shown in outfit selection menu) for consistency. There is also cine_lara (cinematic?) bit I'm not sure if it's actually used.

The other outfit models would be nice too.


Also there is a bug in the exporter (or it is Noesis feature) that sometimes a number is added to mesh name when loading to Noesis from .fbx, so you end up with mesh name like "0000_Mesh_20_tpageid_2826256_dg_27" instead "Mesh_20_tpageid_2826256_dg_27" and exporter fails with error:
ERROR: The mesh name of one or more of your meshes is written incorrectly

For now I have "fixed" it like this:

```

if len(splitted) == 7:
    del splitted[0]
    
if len(splitted) != 6:
    print ("\nERROR: The mesh name of one or more of your meshes is written incorrectly")
    print(mesh.name)
    return 0

```


But you might want to look at it.
## Post #32
- Username: SwiftStarz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 30, 2022 10:12 am
- Post datetime: 2022-07-30T17:59:15+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Wow, this is wonderful.  Great job.

I am curious if you have looked at the Wii version at all?  A couple months ago I looked at some of the tools and tried to piece together an extractor.  I think I got the files extracted out of the DRM but not much further than that.  I'll take a look at your scripts and see if it might be modifiable for the Wii version.

My end goal is to extract all the textures from the game via a tool (along with some post processing).  If you have any details that would help, please let me know.  Thanks again!
## Post #33
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-07-31T06:32:53+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Greg5 ↑Sat Jul 30, 2022 8:20 pm at Sat Jul 30, 2022 8:20 pm
>
> 

Also there is a bug in the exporter (or it is Noesis feature) that sometimes a number is added to mesh name when loading to Noesis from .fbx, so you end up with mesh name like "0000_Mesh_20_tpageid_2826256_dg_27" instead "Mesh_20_tpageid_2826256_dg_27" and exporter fails with error:
ERROR: The mesh name of one or more of your meshes is written incorrectly

For now I have "fixed" it like this:
Code: Select allsplitted = mesh.name.split("_")

if len(splitted) == 7:
    del splitted[0]
    
if len(splitted) != 6:
    print ("\nERROR: The mesh name of one or more of your meshes is written incorrectly")
    print(mesh.name)
    return 0


But you might want to look at it.

This is not an issue with the exporter. Noesis automatically adds that prefix whenever it encounters two or more meshes named exactly the same.

> Reply from SwiftStarz ↑Sun Jul 31, 2022 1:59 am at Sun Jul 31, 2022 1:59 am
>
> 
Wow, this is wonderful.  Great job.

I am curious if you have looked at the Wii version at all?  A couple months ago I looked at some of the tools and tried to piece together an extractor.  I think I got the files extracted out of the DRM but not much further than that.  I'll take a look at your scripts and see if it might be modifiable for the Wii version.

My end goal is to extract all the textures from the game via a tool (along with some post processing).  If you have any details that would help, please let me know.  Thanks again!

I remember looking at Wii texture format but I couldn't make sense out of it. Consoles always have some weird compressions. If you research it and manage to understand them I'll gladly add support for them on the script.
## Post #34
- Username: Greg5
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 19, 2022 8:00 am
- Post datetime: 2022-07-31T11:27:12+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Raq ↑Sun Jul 31, 2022 2:32 pm at Sun Jul 31, 2022 2:32 pm
>
> 
Greg5 wrote: ↑Sat Jul 30, 2022 8:20 pm

Also there is a bug in the exporter (or it is Noesis feature) that sometimes a number is added to mesh name when loading to Noesis from .fbx, so you end up with mesh name like "0000_Mesh_20_tpageid_2826256_dg_27" instead "Mesh_20_tpageid_2826256_dg_27" and exporter fails with error:
ERROR: The mesh name of one or more of your meshes is written incorrectly

For now I have "fixed" it like this:
Code: Select allsplitted = mesh.name.split("_")

if len(splitted) == 7:
    del splitted[0]
    
if len(splitted) != 6:
    print ("\nERROR: The mesh name of one or more of your meshes is written incorrectly")
    print(mesh.name)
    return 0


But you might want to look at it.


This is not an issue with the exporter. Noesis automatically adds that prefix whenever it encounters two or more meshes named exactly the same.

It must be adding that prefix on some other occassions as well. I had 21 uniquely named meshes and it added prefix to all of them. This happens sometimes only. I think Noesis splits the mesh into two if one is too high poly...    Edit: Yeah, the one I edited is shown in Noesis twice and splitted... But anyway, with the fix I provided model works even if .gnc has extra mesh...   


Also I tried yesterday to convert lara_classic from Legend and I couldn't get it working. After trying to move even single mesh from legend over tra skeleton (regardles if I transfer weights from original mesh to Legend one or not) modded meshes are complete mess.

Did anyone have success converting Legend models? Maybe with copying skeleton it would work? - They are nearly the same anyway.
## Post #35
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-08-10T23:11:52+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Think you could make an exporter for Tomb Raider: Underworld too?
## Post #36
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-08-31T11:41:36+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from AxelNoir ↑Thu Aug 11, 2022 7:11 am at Thu Aug 11, 2022 7:11 am
>
> 
Think you could make an exporter for Tomb Raider: Underworld too?

Underworld's format is an absolute chore, but maybe I will look more into it in the future. For now I will just keep improving the exporter for Legend and Anniversary
## Post #37
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2023-04-04T10:39:16+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Good work. A little bit crooked exporting graphics, takes all the graphics resources from the container, although the texture on the model is original. 
 Question.

            meshStream.Position = 0x4;
            int bone_count1 = meshStream.ReadValueS32();
            MeshBone[] bones = new MeshBone[bone_count1];
            int bone_count2 = meshStream.ReadValueS32();
            int bone_Offset = meshStream.ReadValueS32();
            float scaleX = meshStream.ReadValueF32();
            float scaleY = meshStream.ReadValueF32();
            float scaleZ = meshStream.ReadValueF32();
            meshStream.Position += 0x04;
            int BlokVertexCount = meshStream.ReadValueS32();
            int BlokVertexOffset = meshStream.ReadValueS32();
            meshStream.Position = 0x58;
            int FaceOffset = meshStream.ReadValueS32();

            for (int boneID = 0; boneID < bone_count1; boneID++)
            {
                bones[boneID] = new MeshBone(boneID);
            }
            int z = 0;
            foreach (MeshBone bone in bones)
            {
                meshStream.Position = bone_Offset + z * 0x40 + 0x20;
                float dx = meshStream.ReadValueF32();
                float dy = meshStream.ReadValueF32();
                float dz = meshStream.ReadValueF32();
                meshStream.Position += 12;
                int parentID = meshStream.ReadValueS32();
                bone.relPosition = new MeshBone.Point(dx, dy, dz);
                if (parentID >= 0)
                {
                    bone.parent = bones[parentID];
                }
                z++;
            }
            foreach (MeshBone bone in bones)
            {
                bone.CalculateAbsPosition();
                MeshBone parent = bone.parent;
                if (parent != null)
                {
                    parent.children.Add(bone);
                }
            }

            meshStream.Position = BlokVertexOffset;
            for (int i = 0; i < BlokVertexCount; i++)
            {
                float vX = meshStream.ReadValueS16() * scaleX;//point
                float vY = meshStream.ReadValueS16() * scaleY;//point
                float vZ = meshStream.ReadValueS16() * scaleZ;//point
                float nX = meshStream.ReadValueS8() / 128.0f;//normaly
                float nY = meshStream.ReadValueS8() / 128.0f;//normaly
                float nZ = meshStream.ReadValueS8() / 128.0f;//normaly
                meshStream.ReadValueS8();
                int segment = meshStream.ReadValueS16();
                float tU = BitConverter.ToSingle(BitConverter.GetBytes(meshStream.ReadValueU16() << 16), 0);//texture
                float tV = BitConverter.ToSingle(BitConverter.GetBytes(meshStream.ReadValueU16() << 16), 0);//texture
                long backpos = meshStream.Position;
                if (segment >= bone_count1)
                {
                    meshStream.Position = bone_Offset + segment * 0x40 + 0x38;
                    segment = meshStream.ReadValueS16();
                }
                if(segment < bone_count1)
                {
                    var absPos = bones[segment].AbsPosition;                
                    vX += absPos.x;
                    vY += absPos.y;
                    vZ += absPos.z;
                }
                meshStream.Position = backpos;

                temp = string.Format("v {0:0.000000} {1:0.000000} {2:0.000000}", vX, vZ, -vY);
                temp = temp.Replace(",", ".");
                linev.Add(temp);
                temp = string.Format("vn {0:0.000000} {1:0.000000} {2:0.000000}", nX, nY, nZ);
                temp = temp.Replace(",", ".");
                linevn.Add(temp);
                temp = string.Format("vt {0:0.000000} {1:0.000000} 0.000000", tU, tV);
                temp = temp.Replace(",", ".");
                linevt.Add(temp);
            }
            meshStream.Position = FaceData;
            var blokcount = meshStream.ReadValueS16()/3;
            meshStream.Position += 2;
            while (blokcount != 0)
            {
                int groupid = meshStream.ReadValueU8();
                Indices.Add(string.Format("usemtl Texture_{0}", groupid));
                meshStream.Position += 0x0B;
                int nextpos = meshStream.ReadValueS32();
                for (int i = 0; i < blokcount; i++)
                {
                    ushort IndexX = meshStream.ReadValueU16();
                    ushort IndexY = meshStream.ReadValueU16();
                    ushort IndexZ = meshStream.ReadValueU16();
                    Indices.Add(string.Format("f {0}/{0}/{0} {1}/{1}/{1} {2}/{2}/{2}", IndexX + 1, IndexY + 1, IndexZ + 1));
                }
                meshStream.Position = nextpos;
                blokcount = meshStream.ReadValueS16()/3;
                meshStream.Position += 2;
            }
----------
## Post #38
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2023-04-05T06:22:54+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Paliha ↑Tue Apr 04, 2023 6:39 pm at Tue Apr 04, 2023 6:39 pm
>
> 
Good work. A little bit crooked exporting graphics, takes all the graphics resources from the container, although the texture on the model is original. 
 Question. Without a script, in c or c++ or c#, how to transform points, normals, uvs coordinates and indices? The skeleton is not needed.
This code gives a distorted rendering result:             
            meshStream.Position = 0x10;
            float scaleX = meshStream.ReadValueF32(Endian.Little);
            float scaleY = meshStream.ReadValueF32(Endian.Little);
            float scaleZ = meshStream.ReadValueF32(Endian.Little);
            meshStream.Position = 0x20;
            int BlokVertexCount = meshStream.ReadValueS32();
            int BlokVertexOffset = meshStream.ReadValueS32();
            meshStream.Position = 0x58;
            int FaceData = meshStream.ReadValueS32();
            meshStream.Position = BlokVertexOffset;
            for (int i = 0; i < BlokVertexCount; i++)
            {
                float vX = meshStream.ReadValueS16() * scaleX;//point
                float vY = meshStream.ReadValueS16() * scaleY;//point
                float vZ = meshStream.ReadValueS16() * scaleZ;//point
                //var vec = new System.Numerics.Vector3(vX, vZ, vY);

                double nx = ReadNormaly(meshStream);
                double ny = ReadNormaly(meshStream);
                double nz = ReadNormaly(meshStream);
                double length = Math.Sqrt(nx * nx + ny * ny + nz * nz);
                float nX = Convert.ToSingle(nx / length);//normaly
                float nY = Convert.ToSingle(ny / length);//normaly
                float nZ = Convert.ToSingle(nz / length);//normaly
                meshStream.ReadValueS8();
                int segment = meshStream.ReadValueS16();
                float tU = meshStream.ReadValueS16()/ 512.0f;//texture
                float tV = meshStream.ReadValueS16()/ 512.0f;//texture

                temp = string.Format("v {0:0.000000} {1:0.000000} {2:0.000000}", vX, vZ, -vY);
                temp = temp.Replace(",", ".");
                linev.Add(temp);
                temp = string.Format("vn {0:0.000000} {1:0.000000} {2:0.000000}", nX, nY, nZ);
                temp = temp.Replace(",", ".");
                linevn.Add(temp);
                temp = string.Format("vt {0:0.000000} {1:0.000000} 0.000000", tU, tV);
                temp = temp.Replace(",", ".");
                linevt.Add(temp);
            }
            meshStream.Position = FaceData;
            var blokcount = meshStream.ReadValueS16()/3;
            meshStream.Position += 2;
            while (blokcount != 0)
            {
                int groupid = meshStream.ReadValueU8();
                Indices.Add(string.Format("usemtl Texture_{0}", groupid));
                meshStream.Position += 0x0B;
                int nextpos = meshStream.ReadValueS32();
                for (int i = 0; i < blokcount; i++)
                {
                    ushort IndexX = meshStream.ReadValueU16();
                    ushort IndexY = meshStream.ReadValueU16();
                    ushort IndexZ = meshStream.ReadValueU16();
                    Indices.Add(string.Format("f {0}/{0}/{0} {1}/{1}/{1} {2}/{2}/{2}", IndexX + 1, IndexY + 1, IndexZ + 1));
                }
                meshStream.Position = nextpos;
                blokcount = meshStream.ReadValueS16()/3;
                meshStream.Position += 2;
            }
----------
If there is a working solution, I can help later with parsing containers, animation resources, media, models, textures and levels, for the entire Tomb Raider(PC) line of games to choose from.

Hi can you share this tools
## Post #39
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2023-04-06T14:28:33+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

<< Hi can you share this tools
There is too much not yet done to put the drm viewer out to the public.
With the models for this edition, all the problems are solved.
## Post #40
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2023-06-19T18:31:39+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

Hello guys I am download steam this is game but how to extract files any help ?
## Post #41
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2023-07-24T20:04:36+00:00
- Post Title: Re: Tomb Raider Legend/Anniversary

> Reply from Paliha ↑Tue Apr 04, 2023 6:39 pm at Tue Apr 04, 2023 6:39 pm
>
> 

I'm super late to the party, but this looks amazing! Great work!
