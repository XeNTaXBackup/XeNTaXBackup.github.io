## Post #1
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2019-08-29T08:16:23+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

This project is closed, no new update! New project based on this:[https://github.com/TomEvin/neat](https://github.com/TomEvin/neat)




NorthlightTool.jpg (87.53 KiB) Viewed 1912 times


Supported games (PC/X360, possible PS4/XOne but not possible to test it yet):
- Alan Wake (PC/X360)
- Alan Wake American Nightmare (PC/X360)
- Quantum Break (PC, possible XOne)
- Control (PC, possible XOne/PS4)
- Alan Wake Remastered (PC, possible XOne/PS4)

Xbox One compatible not tested! PS4 supported in most cases.

DOWNLOAD
v1.2 beta (2022.02.10): [https://drive.google.com/file/d/1VXjMfk ... sp=sharing](https://drive.google.com/file/d/1VXjMfkXAAog7INVLwIOizAxAufpb_KXS/view?usp=sharing)

This project is closed, no new update! New project based on this:[https://github.com/TomEvin/neat](https://github.com/TomEvin/neat)
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-02T16:58:29+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

Great work! I can't wait to try it out.
## Post #3
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-03T17:15:50+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

are you gonna make changes to your blender script to support control?
I spent a day trying to amend the code to support the new binfbx and i just couldn't understand the model format. looking at the QB format, it was obvious, each block had the MO signature. but for Control its like gibberish. Maybe its not sequential? idk...
## Post #4
- Username: Apocalypse000
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 17, 2019 12:19 am
- Post datetime: 2019-09-03T17:42:29+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

I made all the files I end up with this file the

ep101-000-generic.rmdp

Here is the size of the file 6 312 580 kb I can not extract it I would like to recover models I have already recovered all the textures of jesse And still other texture

I also have a lot of texture of the game and other characters
## Post #5
- Username: Apocalypse000
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 17, 2019 12:19 am
- Post datetime: 2019-09-03T17:48:22+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

A little help on how to extract these two files

ep101-000-generic.rmdp

ep100-000-pc.rmdp

I think the models are in this file Otherwise I already have all the texture of the game the characters the decor the weapons The creatures
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2019-09-03T20:21:06+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

I could unpack ep101-000-generic.rmdp and ep100-000-pc.rmdp!
What is your error message?
## Post #7
- Username: Apocalypse000
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 17, 2019 12:19 am
- Post datetime: 2019-09-03T21:30:20+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

I do not know how to unpack them with your tool
## Post #8
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-03T23:32:39+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Bladers ↑Wed Sep 04, 2019 1:15 am at Wed Sep 04, 2019 1:15 am
>
> 
are you gonna make changes to your blender script to support control?
I spent a day trying to amend the code to support the new binfbx and i just couldn't understand the model format. looking at the QB format, it was obvious, each block had the MO signature. but for Control its like gibberish. Maybe its not sequential? idk...

Ah I was hoping the tool already converted to a known model format, I guess not. I'll of course have to work on a blender plugin. But it's a lot of work, could be days or weeks.
## Post #9
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2019-09-04T12:03:43+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Apocalypse000 ↑Wed Sep 04, 2019 5:30 am at Wed Sep 04, 2019 5:30 am
>
> 
I do not know how to unpack them with your tool

Right-upper "Browse" button, then Export button.
I do not think it is so complicated.
## Post #10
- Username: Apocalypse000
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 17, 2019 12:19 am
- Post datetime: 2019-09-04T12:28:31+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

I used another program to extract rmdp I found character texture I'm still looking for models
## Post #11
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-05T17:43:38+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

Ok, I'm making some progress on a model importer. I have the file format nearly fully mapped out. It's quite a bit different from Quantum break, in fact I'd say it's completely different.

There's pointers at the start to 3 major blocks of data, and then past that a parameter block with all the information about the model, materials, vertice counts, number of models in the file, etc. And then past that another data table.  I've only looked at a single model without skinning so far and will work today to write an importer for that, and then test it on other files. I'm sure once I start doing that I'll find mistakes and exceptions which will have to be dealt with. and Then I'll turn to skinned models and see how far I can get with those. I don't know yet if they include the skeleton and such. 

But I can say I'm making good progress and I'm confident I'll have something to share soon.
## Post #12
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-06T20:01:48+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Fri Sep 06, 2019 1:43 am at Fri Sep 06, 2019 1:43 am
>
> 
Ok, I'm making some progress on a model importer. I have the file format nearly fully mapped out. It's quite a bit different from Quantum break, in fact I'd say it's completely different.

There's pointers at the start to 3 major blocks of data, and then past that a parameter block with all the information about the model, materials, vertice counts, number of models in the file, etc. And then past that another data table.  I've only looked at a single model without skinning so far and will work today to write an importer for that, and then test it on other files. I'm sure once I start doing that I'll find mistakes and exceptions which will have to be dealt with. and Then I'll turn to skinned models and see how far I can get with those. I don't know yet if they include the skeleton and such. 

But I can say I'm making good progress and I'm confident I'll have something to share soon.

Wow you're fast. Looking forward to this, even just importing non skinned models for starters would be great.
## Post #13
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-06T22:26:35+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

I have very simple model import working now. here's a couple of examples:





I noticed they bragged about using simplygon in the opening credits, I have to say these are some of the worst looking LOD models I've ever seen.  But that's fine I guess, the highest level is usually the best anyway.  Next step is to get UV mapping working and see if I can figure out how normal are stored (I never seem to have success with normals though so won't spend a lot of time on it.)
## Post #14
- Username: Cukier
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 22, 2015 5:37 pm
- Post datetime: 2019-09-08T09:26:27+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

It works for Control game. But unfortunely when im trying to export Alan Wake files it prints me "An overflow occurred during the arithmetic operation".
What is wrong ? Also i wanted to check that tool because Alan Wake Tool v0.5 works like a charm, it don't pops up this message, but when i try to repack ep999-007.rmdp / bin the game just crashes.
## Post #15
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-09T17:40:40+00:00
- Post Title: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Sat Sep 07, 2019 6:26 am at Sat Sep 07, 2019 6:26 am
>
> 
I have very simple model import working now. here's a couple of examples:

I noticed they bragged about using simplygon in the opening credits, I have to say these are some of the worst looking LOD models I've ever seen.  But that's fine I guess, the highest level is usually the best anyway.  Next step is to get UV mapping working and see if I can figure out how normal are stored (I never seem to have success with normals though so won't spend a lot of time on it.)

That's so Neat!

What do you think about the animations? @daemon1 says its basically impossible or rather improbable. But what do you think?
Can it be done and be done in a reasonable timetable?
## Post #16
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-10T01:17:39+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Bladers ↑Tue Sep 10, 2019 1:40 am at Tue Sep 10, 2019 1:40 am
>
> 
That's so Neat!

What do you think about the animations? @daemon1 says its basically impossible or rather improbable. But what do you think?
Can it be done and be done in a reasonable timetable?
I have no plans to attempt animations. If I get skinned models with skeletons done I'll consider myself lucky.   

Since I'm posting I'll give an update.  I have UV Mapping working, and multi-material decoding done as well. 



multiple materials per model turned out to be very challenging because of a neat feature they implemented, which added a  lot of complexity.

Basically each LOD model can have an arbitrary number of materials applied. and even unique materials for every LOD if they wanted.   In the above case, the file had 3 materials defined, material 1 and 2 were used on LOD 0, but material 3 was only used on LOD 1.  I have all this working now.

I'm also seeing that texture paths aren't reliable as defined in the files:

Here you see the paths given are saying 'centurion\batch03' but the texture files are in fact in 'centurion\batch01'


for LOD1's unique textures, it was similarly confusing, the file stated the textures would be in 'centurion\batch03\lods' but they were instead in simply 'batch03\lods'. at least in all cases I've seen so far the filenames are consistent.

blender can't read DX10 DDS files so manual conversion to TGA or another format they can read is of course required, but with textures in blender:


I'm still finding some exceptions I need to address, and then I can start trying for skinned models and skeletons. I'll probably make a release without skinning support once it's stable so people can mess with static models in the meantime.
## Post #17
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-12T06:59:54+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I found another nifty feature I had to add support for, the 'breakable' items are defined as one solid mesh, however, there's a table with information about how they get broken up into parts when you 'break' them. So I figured it would be nice to have an option ("Split breakable meshes" in the plugin options, it's on by default) to break these meshes up as intended. For example the chair:


this option even works across LODS:


Since it all seems to be fairly stable at this point i'm releasing 1.0 which works for blender 2.70 thru 2.79 (2.80 version *may* happen at a later date)

Remember this doesn't yet have support for skinned meshes, so trying those will probably result in failure. If you find any static/breakable meshes that won't load or don't load right, let me know the file's name and i'll try to fix it.

If you need help installing the plugin into Blender, check my tutorial here: [viewtopic.php?p=103131#p103131](https://forum.xentax.com/viewtopic.php?p=103131#p103131)

* New version posted below *
## Post #18
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-12T14:46:10+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Thu Sep 12, 2019 2:59 pm at Thu Sep 12, 2019 2:59 pm
>
> 
I found another nifty feature I had to add support for, the 'breakable' items are defined as one solid mesh, however, there's a table with information about how they get broken up into parts when you 'break' them. So I figured it would be nice to have an option ("Split breakable meshes" in the plugin options, it's on by default) to break these meshes up as intended.

wow you have outdone yourself. can't wait to get home and get my hands on it.
## Post #19
- Username: dennysbr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 13, 2019 10:40 am
- Post datetime: 2019-09-13T02:42:52+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Hey guys, I convert the jesse files but it's binfbx, I don't know this format, did one of you make any breakthrough? Will we ever have a jesse nude?
## Post #20
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-13T04:20:37+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

characters are skinned meshes. like I said I haven't yet added support for skinned meshes. Give me time.   

as for nude, I have no idea lol, I doubt that's in the game though.
## Post #21
- Username: tivac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 13, 2019 2:31 pm
- Post datetime: 2019-09-13T06:36:30+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Anybody have any clues what the format is for the .ui files? I was able to get them all extracted from the .rmdp using the Northlight Tool (which was awesome and super-straightforward to use, thanks!) and while I can poke at the contents a bit in a hex editor it's been a long time since I wrote an unpacker script. If someone has already done the research I'd really appreciate it!
## Post #22
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-13T17:15:17+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

well according to the splash screen,  they are using Coherent Labs' UI system:


[https://coherent-labs.com/products/coherent-gameface/](https://coherent-labs.com/products/coherent-gameface/)
According to their website, their UI system is based on HTML5 and javascript, which seems backed up by what I saw when I peeked in a UI file, it looks like it's a pretty simple package with HTML/XML/and JavaScript all bumdled in it. I have never heard of Coherent, so I don't know how often they have been used in games, I have a feeling not much, so I doubt anything already exists for their UI system.

But it looks pretty simple


Looks like they use the signature 0xD34DB33F (good ol DEADBEEF) is a record block signifier (marked in green) and then it's just long integers and floats of data and strings with string length coming before. it's a great project for a beginner really.
## Post #23
- Username: tivac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 13, 2019 2:31 pm
- Post datetime: 2019-09-14T05:24:58+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I'm actually interested specifically because it's using Coherent, as I'm a JS programmer . I manually extracted a couple of files to poke at them but hopefully with your tip on the 0xD34DB33F identifier I can write a small unpacker and get a better sense of how it all fits together.

Thanks so much for the help!
## Post #24
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-16T02:35:52+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Thu Sep 12, 2019 2:59 pm at Thu Sep 12, 2019 2:59 pm
>
> 
Since it all seems to be fairly stable at this point i'm releasing 1.0 which works for blender 2.70 thru 2.79 (2.80 version *may* happen at a later date)

Remember this doesn't yet have support for skinned meshes, so trying those will probably result in failure. If you find any static/breakable meshes that won't load or don't load right, let me know the file's name and i'll try to fix it.

If you need help installing the plugin into Blender, check my tutorial here: viewtopic.php?p=103131#p103131

Looks like dead_letter_walls.binfbx and similar objects like walls floors are giving an error? These can't be skinned meshes.
Any ideas and updates?

I'm using blender 2.79b by the way
## Post #25
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-16T10:06:46+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Bladers ↑Mon Sep 16, 2019 10:35 am at Mon Sep 16, 2019 10:35 am
>
> 
volfin wrote: ↑Thu Sep 12, 2019 2:59 pm
Since it all seems to be fairly stable at this point i'm releasing 1.0 which works for blender 2.70 thru 2.79 (2.80 version *may* happen at a later date)

Remember this doesn't yet have support for skinned meshes, so trying those will probably result in failure. If you find any static/breakable meshes that won't load or don't load right, let me know the file's name and i'll try to fix it.

If you need help installing the plugin into Blender, check my tutorial here: viewtopic.php?p=103131#p103131


Looks like dead_letter_walls.binfbx and similar objects like walls floors are giving an error? These can't be skinned meshes.
Any ideas and updates?

I'm using blender 2.79b by the way

I'll give them a look, thanks.
## Post #26
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-16T18:06:59+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

yeah about the walls, it's failing because of a new never-seen shader parameter:


each parameter has to be added by name, because each has a possibly different number of arguments. First time seeing that one, so i'll have to add it to the plugin. 

I'm making good progress on skinned models, skeleton decoding is done, and i think i see how vertice weights are stored. I just need a bit more time and I'll have it done.
## Post #27
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-17T20:55:35+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Ok, I think I have everything 'nearly' there. Weights and indexes are decoded and everything looks good. It's a bit insane that even NPCs have over 500 bones, but this is remedy I guess 

I have a lot to do still, I found out the models were mirrored on the X axis, so be aware of that for version 1.0, it will be fixed in 1.10.  As well I've vastly improved the shader parameter processing so there shouldn't be any more unknown shader param problems (unless it's really something wild you find).  

As well I've noticed a peculiar issue with some models that have transparent sections/decals.  the data is structured in such a way the transparent parts aren't defined in the model table. The data is there, it's just not drawn... Maybe some engine optimization or who knows. problem is if there's no table entry for the data, my plugin doesn't know to build it. So I need to figure out a way to detect this situation and insert a dummy entry or something.

Once I've resolved all these issues and have tested it across more models, I'll release 1.10
## Post #28
- Username: dennysbr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 13, 2019 10:40 am
- Post datetime: 2019-09-18T23:16:58+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

very nice  congratulations
## Post #29
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-19T01:22:16+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Ok, what everyone wants finally   




I think i can safely say it is done, everything seems to work great.

Here's the change log from 1.0:

> # 1.10  - Added initial support for rigged characters
>
> #       - mapped shader type table, now detects 8/16 bit bone index values, 16/32 bit face index values, and 4/8 weight per vertex usage
>
> #       - added skeleton building support. *.binskeleton file must be present (and if one exists it's always next to the model anyway)
>
> #       - Fixed issue with models being flipped on X axis
>
> #       - rewrote shader parameter parsing, should better handle unexpected parameters
>
> #       - worked around issue where transparent/decal sections don't have a model entry, and weren't created.

lot of parts i redid to make it work more reliably and i have to say it's looking good.  
I checked every Jesse model, all of the costumes are there, even the preorder, PS/4 exclusive, etc.  
And even one I think nobody has seen before called "Expedition":




Have to wonder if there is some challenge that hasn't been found yet, or for the upcoming DLCs...

Oh yeah and I finished converting it to Blender 2.80 also, if you're into that. I use the "collections" instead of layers but if you're using 2.80 you should already know about collections anyway.   

As always if you find issues let me know.

and as Ahti would say:

Nauttia (enjoy)



 * New version posted on next page *
## Post #30
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-19T01:23:59+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

For some reason it won't let me put a second attachment on the post, so here's the blender 2.80 version.

* new version posted on next page *
## Post #31
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2019-09-19T09:26:22+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I have a problem with trench_default_publish_physx.binfbx. He has no skeleton and vertex groups, uvs are missing, shoes are messed up.




Tested in blender 2.78 and 2.8. Other characters I tried worked fine.
## Post #32
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-19T16:20:24+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from YourImaginaryFriend ↑Thu Sep 19, 2019 5:26 pm at Thu Sep 19, 2019 5:26 pm
>
> 
I have a problem with trench_default_publish_physx.binfbx. He has no skeleton and vertex groups, uvs are missing, shoes are messed up.
Tested in blender 2.78 and 2.8. Other characters I tried worked fine.

Okay, thanks for the report. I'll see why he's being stubborn.
## Post #33
- Username: dennysbr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 13, 2019 10:40 am
- Post datetime: 2019-09-19T18:16:57+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

you are a genius, very good, maybe one day through this project someone make a nude
## Post #34
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-19T23:15:13+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Okay it looks like the reason Trench is broken is because of his eyeglasses. That 'transparent blocks are skipped' issue I mentioned before.  But this is the first time I've seen it happen anywhere besides the first block. It is happening between the 3rd and 4th block. So I guess I'll have to assume it can occur between any two blocks.

This means I'll have to rewrite things a little so I can check and repair skipped sections no matter where they occur. I probably won't have a solve until tomorrow.
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-20T04:10:31+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Okay, I found trench's other shoe, and he agreed to cooperate after that.  Seems the problem was indeed what I suspected, adding in a tedious check of face offsets/counts seems to let me fill in the gaps.  Hopefully the fix stays true for other such models.



Enjoy

*new version below*
## Post #36
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-20T04:12:06+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

For Blender 2.80 the fix is the same as above. However I also noticed an additional bug concerning collections, The plugin was leaving an empty object behind when splitting up 'breakable' meshes.  I fixed that issue, and doesn't do it anymore.

Enjoy 

*new version below*
## Post #37
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-20T16:17:22+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I made a tiny goof with both versions, I left debug = True, so they print a ton of data that makes looking at the materials in the console a chore.

So you can either redownload the version I just changed out the posts with, or edit the file yourself (carefully) and set debug = False at the top of import_binFBX.py, or you can just not worry about it, it works the same, just prints a ton more data you might not need.
## Post #38
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-21T02:45:36+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Sat Sep 21, 2019 12:17 am at Sat Sep 21, 2019 12:17 am
>
> 
I made a tiny goof with both versions, I left debug = True, so they print a ton of data that makes looking at the materials in the console a chore.

So you can either redownload the version I just changed out the posts with, or edit the file yourself (carefully) and set debug = False at the top of import_binFBX.py, or you can just not worry about it, it works the same, just prints a ton more data you might not need.

I really appreciate how quick you were able to get this done. really stunning.
I did run into a problem with some models though. Looks like the carpet border models are throwing an error. For example tempestroom_carpet_borders.binfbx or research_sector_lobby_office_carpet_border_custom.binfbx or officekit_carpet_border_2m

Basically most of the carpet border models are, which is weird because they should be a simple model.
## Post #39
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-21T03:58:54+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Bladers ↑Sat Sep 21, 2019 10:45 am at Sat Sep 21, 2019 10:45 am
>
> 
volfin wrote: ↑Sat Sep 21, 2019 12:17 am
I made a tiny goof with both versions, I left debug = True, so they print a ton of data that makes looking at the materials in the console a chore.

So you can either redownload the version I just changed out the posts with, or edit the file yourself (carefully) and set debug = False at the top of import_binFBX.py, or you can just not worry about it, it works the same, just prints a ton more data you might not need.


I really appreciate how quick you were able to get this done. really stunning.
I did run into a problem with some models though. Looks like the carpet border models are throwing an error. For example tempestroom_carpet_borders.binfbx or research_sector_lobby_office_carpet_border_custom.binfbx or officekit_carpet_border_2m

Basically most of the carpet border models are, which is weird because they should be a simple model.

yeah it's not unusual to have strange exceptions when reverse engineering something like this. I'll check those out and see what I can do.
## Post #40
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-21T20:28:37+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Okay, the reason carpets wouldn't load is they have *zero* entries in the model block. that's a new one on me.  But I figured out a way to use the material definitions instead in such an instance. Truthfully I probably made some bad assumptions at the start and should rewrite the whole thing, but This kludge seems to work fine, so I'll roll with it.

the 'carpet border' seems to be all the baseboards for a level lol. not sure they are useful but you can extract them now.


Enjoy  

*new version next page*
## Post #41
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-21T20:29:06+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

and same update for 2.80 

*new version next page*
## Post #42
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2019-09-22T02:41:54+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Hey Volfin thanks for the update on the blender script however i have a problem with quantumbreak models doesnt matter wich one i select i get a signature is invalid lol 



Iam using blender 2.80
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-22T04:58:23+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

this doesn't work for Quantum Break, only for Control. Quantum break uses a completely different model format.

You can try the quantum break importer I did some years ago that's here (for blender 2.70 to 2.79 only):

[viewtopic.php?f=10&t=14195&start=60#p126811](https://forum.xentax.com/viewtopic.php?f=10&t=14195&start=60#p126811)

But I've never tried it with this particular unpacker, it may or may not work.
## Post #44
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2019-09-22T16:03:52+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Thanks thats explain everting also just download blender 2.78 and its working perfect.
## Post #45
- Username: kamtesel17
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 05, 2019 6:33 am
- Post datetime: 2019-09-25T17:23:55+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

hi
thanks for the plugin.
but how we edit and export the models???
## Post #46
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-26T00:39:32+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from kamtesel17 ↑Thu Sep 26, 2019 1:23 am at Thu Sep 26, 2019 1:23 am
>
> 
hi
thanks for the plugin.
but how we edit and export the models???

I'm guessing you mean re-import the models back to the game. I don't know nearly enough about the model format to even attempt that. it's a very complicated format and I figured out enough to get the models out, that's it. Maybe someone else is brave enough to tackle trying to 100% map the format so reimport would be possible.
## Post #47
- Username: kamtesel17
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 05, 2019 6:33 am
- Post datetime: 2019-09-26T07:24:00+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Thu Sep 26, 2019 8:39 am at Thu Sep 26, 2019 8:39 am
>
> 
kamtesel17 wrote: ↑Thu Sep 26, 2019 1:23 am
hi
thanks for the plugin.
but how we edit and export the models???


I'm guessing you mean re-import the models back to the game. I don't know nearly enough about the model format to even attempt that. it's a very complicated format and I figured out enough to get the models out, that's it. Maybe someone else is brave enough to tackle trying to 100% map the format so reimport would be possible.

thanks for answering
is there any hex mesh editor with simple function to edit the models? anyone know that somekind of software to introduce?

I change the models name and binfbx+texture files - but the game crashes.I want to change the default model to the hidden outfits.
## Post #48
- Username: dennysbr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 13, 2019 10:40 am
- Post datetime: 2019-09-26T19:50:43+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Regarding the clothes I downloaded a cheat, based on the program cheat engine, unlock all the clothes, I found this site

[https://fearlessrevolution.com/viewtopic.php?t=10106](https://fearlessrevolution.com/viewtopic.php?t=10106)


And yes, renaming the files certainly the game will not work, but follow this link, the cheat is so good that even has clothes for new DLC
## Post #49
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-29T02:57:55+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

did anyone figure out how to fix the black faces and the problem with trying to flip the normals when you import to 3d max or unreal?

EDIT: NVM fixed it.
## Post #50
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-29T04:24:25+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from volfin ↑Sun Sep 22, 2019 4:28 am at Sun Sep 22, 2019 4:28 am
>
> 
Okay, the reason carpets wouldn't load is they have *zero* entries in the model block. that's a new one on me.  But I figured out a way to use the material definitions instead in such an instance. Truthfully I probably made some bad assumptions at the start and should rewrite the whole thing, but This kludge seems to work fine, so I'll roll with it.

the 'carpet border' seems to be all the baseboards for a level lol. not sure they are useful but you can extract them now.


Enjoy
yup those baseboards come in handy because they also include the carpet borders, so thx alot for that. Especially when you want to recreate an entire level which i am.

hate to bug you again but i found more.
this time its the picture frames.

for example picture_frame_picture_frame_wall_big or picture_frames_picture_frame_huge



EDIT: Also belt barrier pole also has the same issue
## Post #51
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-29T19:59:42+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

it's no problem, I appreciate you letting me know.
It's the same problem as last time, just in a new form. always some edge case 

Also I'm glad you mentioned about 'black faces' and normals, I had fixed the models being inside out in 1.0, and then 1.1 I realized models were flipped on the X Axis, so fixed that, and didn't realize flipping the models turned them inside out again.     I'll be fixing that too.

In fact here's the new version:
- fixes flipped normals
- fixes last of naughty models (I hope    )
[io_scene_Control 1.4 for Blender 2.70 - 2.79.zip](https://xentaxbackup.github.io/file/16828_io_scene_Control 1.4 for Blender 2.70 - 2.79.zip)
## Post #52
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-29T20:13:48+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

And version for 2.8, same as above.  Enjoy
[io_scene_Control 1.4 for Blender 2.80.zip](https://xentaxbackup.github.io/file/16829_io_scene_Control 1.4 for Blender 2.80.zip)
## Post #53
- Username: Kempy161
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 28, 2016 5:05 am
- Post datetime: 2019-09-29T21:44:20+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Northlight Tool download link seems to be down, any chance of a new link?
## Post #54
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-30T02:28:27+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Monday on Discord he said Dropbox blocks the download for a day when too many download it. So maybe try again in 24 hours.
## Post #55
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2019-10-01T08:06:27+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

anybody knows how to model swap?
## Post #56
- Username: Kempy161
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 28, 2016 5:05 am
- Post datetime: 2019-10-01T18:50:55+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Link has been down for more than a day, would anybody that got this be able to reupload?
## Post #57
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2019-10-02T16:32:58+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Download link updated in the first post.

By the way, you should not talk about 3D modeling and stuff in the 3D topic, to everyone can find these information?!
## Post #58
- Username: dennysbr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 13, 2019 10:40 am
- Post datetime: 2019-10-11T02:31:51+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

do you intend to create a blender exporter too? to control
## Post #59
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-10-11T05:32:33+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from dennysbr ↑Fri Oct 11, 2019 10:31 am at Fri Oct 11, 2019 10:31 am
>
> 
do you intend to create a blender exporter too? to control

like I said above, the format is far too complex, and there's a lot of aspects I haven't even explored. every model i'm pretty sure has a corresponding *.binpx file with a whole lot of data about it and you'd probably have to re-write that as well as the *binfbx file, and really all the work isn't worth the payoff, IMHO anyway.
## Post #60
- Username: dennysbr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 13, 2019 10:40 am
- Post datetime: 2019-10-12T20:06:11+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I understand, ok
## Post #61
- Username: svthe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 14, 2019 1:27 am
- Post datetime: 2019-10-13T17:29:38+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

has anyone realized how to extract audio from Control?
(i tried extracting .bnk files with wwiseutil and converting .wem`s using ww2ogg, but output was unplayable junk)
upd: fixed the unplayable junk problem using revorb
## Post #62
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-10-14T17:34:09+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from svthe ↑Mon Oct 14, 2019 1:29 am at Mon Oct 14, 2019 1:29 am
>
> 
has anyone realized how to extract audio from Control?
(i tried extracting .bnk files with wwiseutil and converting .wem`s using ww2ogg, but output was unplayable junk)
upd: fixed the unplayable junk problem using revorb

So you were able to extract the audio?
## Post #63
- Username: svthe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 14, 2019 1:27 am
- Post datetime: 2019-10-15T11:01:34+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Bladers ↑Tue Oct 15, 2019 1:34 am at Tue Oct 15, 2019 1:34 am
>
> 
svthe wrote: ↑Mon Oct 14, 2019 1:29 am
has anyone realized how to extract audio from Control?
(i tried extracting .bnk files with wwiseutil and converting .wem`s using ww2ogg, but output was unplayable junk)
upd: fixed the unplayable junk problem using revorb


So you were able to extract the audio?
well, yes
I extracted .bnk files from ep100-000-generic-en using latest NT
after that, I extracted .wems from .bnk files using wwiseutil-gui and converted them using revorb and ww2ogg thanks to this guide
[https://owdev.wiki/Tutorial/Convert_Sound_files_to_Ogg](https://owdev.wiki/Tutorial/Convert_Sound_files_to_Ogg)
(yeah that's the article for Overwatch, but main difference is the way of file extraction from games, converting is the same)
## Post #64
- Username: ellis3246
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 16, 2019 1:02 pm
- Post datetime: 2019-12-21T02:14:15+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

(SORRY IF IM NECRO BUMPING)
has anyone made a .binmsh tool for blender yet??
if so can you link one
## Post #65
- Username: osx853
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 31, 2020 1:52 pm
- Post datetime: 2020-06-11T13:44:10+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I exported the ep100-000-generic-ar file and also checked the convert text file, but the bin file gave me how to open this bin file ??
## Post #66
- Username: smolbanana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 02, 2020 8:23 am
- Post datetime: 2020-06-16T15:17:33+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Whenever I try to export anything from Alan Wake, the tool throws errors.

No files are extracted into the folder, yet it identifies that there are 36,967 files. It's even worse if I don't tell the tool what type of file I want to unpack. It just continuously gives me error messages, and I have to log out of Windows just to close the tool.

Is it possible that this doesn't work with the Steam version of Alan Wake? Or am I missing something?

EDIT: I just discovered your AWTool, and it's actually extracting the files. I'm not sure what the difference is between the two besides support for the newer engine, but if anyone else is having trouble with this specific game. Try using the AWTool instead.

link: [viewtopic.php?t=8411](https://forum.xentax.com/viewtopic.php?t=8411)
## Post #67
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2020-08-19T18:58:47+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

I really hope somebody will figure out how it to re-import back the edited models in to the game, i wanna make some new clothes for Jessie
## Post #68
- Username: slumpthelump
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 26, 2020 6:48 pm
- Post datetime: 2020-08-26T10:55:04+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

There seem to be retexture mods available for the ingame outfits, at least recolored versions.
I was trying to do some recolors myself, though it`s not working as I want it to, I think there is something wrong with how I save the files in Photoshop.
Does anyone here know how to correctly retexture the outits? Also I was looking for the Office Assistant texture but couldn`t find it.
## Post #69
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-08-28T20:31:26+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Any idea what to do with *.bin files, like global/dp_global.bin? Format looks to be unknown, but the files seemingly contain some interesting data.
Also, I'm having trouble finding the actual file paths of some files inside *.packmeta files.
## Post #70
- Username: UnknDoomer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 11, 2018 2:00 am
- Post datetime: 2020-09-09T12:21:30+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Exporting script now available, you can call it "pre-alpha" version (not finished/not working). At the moment have no idea how to continue it, both in logical and theoretical aspect. Perhaps someone can take a look further.

Some more techical information can be found here - [https://www.loverslab.com/topic/128850- ... st/page/5/](https://www.loverslab.com/topic/128850-control-nude-mod-request/page/5/)
[Export_fbx_bin.zip](https://xentaxbackup.github.io/file/18719_Export_fbx_bin.zip)
## Post #71
- Username: soneday
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 23, 2014 12:25 am
- Post datetime: 2020-09-25T01:14:38+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

link dead,, update link pls
## Post #72
- Username: UnknDoomer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 11, 2018 2:00 am
- Post datetime: 2020-10-02T05:48:21+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Seems to link is fine now.
## Post #73
- Username: Bxaa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 06, 2020 2:50 pm
- Post datetime: 2020-10-06T07:15:27+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Hi! Thanks for your work!

DDS2TEX not work!

I alredy make all remastered 4k textures for alan wake, but cant reexported it   (all reexported textures is broken in game)
NorthlightTool's tex2dds just replace header, but It is not good idea to replace dds header by not changed header of original tex.

I am serious about doing a complete remaster for Alan Wake, but i need normal convertor dds  to  alan wake 'tex' 
TEX header 32 byte,  after it standard DDS (without dds header)
I looked at the TEX file header - it is clear that 8 and 12 bytes by offset (int32) are the size of the texture...other values i dont know.

Texture for test:
(True 4k Alan face; texture path: ep999-000\alanwake_2010b)
[https://www65.zippyshare.com/v/cumTTE1T/file.html](https://www65.zippyshare.com/v/cumTTE1T/file.html)
Original textures (tex\dds) for format compare:
[https://www41.zippyshare.com/v/ctLshqMW/file.html](https://www41.zippyshare.com/v/ctLshqMW/file.html)

>>>If anyone succeeds import this texture into the game, please report

For example my remasters textures:
[https://www.nexusmods.com/oblivion/mods/50381](https://www.nexusmods.com/oblivion/mods/50381)
[https://www.nexusmods.com/newvegas/mods/69848](https://www.nexusmods.com/newvegas/mods/69848)
[https://www.nexusmods.com/fallout3/mods/24340](https://www.nexusmods.com/fallout3/mods/24340)
## Post #74
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2021-01-26T11:46:50+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from CobraGamer ↑Sat Aug 29, 2020 4:31 am at Sat Aug 29, 2020 4:31 am
>
> 
Any idea what to do with *.bin files, like global/dp_global.bin? Format looks to be unknown, but the files seemingly contain some interesting data.
Also, I'm having trouble finding the actual file paths of some files inside *.packmeta files.

You have to separate between dp_*.bin files and cid_*.bin files. The cid files contain a list of structured objects, generally used to describe game data, like where are objects placed, which damage weapons do and also (stored in dp_bytecode.bin and dp_bytecodeparameters.bin) the bytecode of the scripts. The dp files on the other hand store raw data, where the cid files can have pointers into (I think, that dp stands for data pointer). More of these files, which are more level specific are actually stored in the .bin files in the worlds directory. These are actually small zlib compressed archives. Take a look at my AWTools [https://github.com/Nostritius/AWTools](https://github.com/Nostritius/AWTools), if you want to unpack them.
## Post #75
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-02-05T08:57:22+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Anyone able to port this to Noesis ?
## Post #76
- Username: Tspoon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 09, 2019 10:23 pm
- Post datetime: 2021-06-09T22:37:52+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Can somebody re-upload? Google Drive has flagged it as a virus so it's impossible to download:

> Sorry, this file is infected with a virus
>
> 
>
> Only the owner is allowed to download infected files.
## Post #77
- Username: YOEL44
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 14, 2021 9:37 am
- Post datetime: 2021-06-14T02:11:46+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Tspoon ↑Thu Jun 10, 2021 6:37 am at Thu Jun 10, 2021 6:37 am
>
> 
Can somebody re-upload? Google Drive has flagged it as a virus so it's impossible to download:
Sorry, this file is infected with a virus

Only the owner is allowed to download infected files.

I made a quick mirror until the main link is fixed:
[https://www.mediafire.com/file/pscfz4wb ... ol.7z/file](https://www.mediafire.com/file/pscfz4wbco21w7m/NorthlightTool.7z/file)
## Post #78
- Username: Tspoon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 09, 2019 10:23 pm
- Post datetime: 2021-06-14T13:57:57+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

MVP - thanks!   

I'll pay it forward and rehost if it ever goes down again!
## Post #79
- Username: RennMaus95
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 05, 2020 7:28 am
- Post datetime: 2021-06-15T04:04:13+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Tspoon ↑Thu Jun 10, 2021 6:37 am at Thu Jun 10, 2021 6:37 am
>
> 
Can somebody re-upload? Google Drive has flagged it as a virus so it's impossible to download:
Sorry, this file is infected with a virus

Only the owner is allowed to download infected files.


You can bypass this if you ever come across it again. Favorite it and there is a button to click to save a link to the file in your own drive. Then you go to your drive, right click the link to the file, and make a copy. Since you are the owner of the copy, you can download it.
## Post #80
- Username: Tama@01
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 04, 2019 12:22 pm
- Post datetime: 2021-08-14T05:37:23+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Is the alan wake plug/attachment for blender 2.0 went missing? I can't seem to find it for some reason
## Post #81
- Username: kixmix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 10, 2021 12:09 am
- Post datetime: 2021-09-09T16:17:35+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Hi Evin,
Thanks for the amazing tool.
but there is something, I could not use your "original" version of your tool to convert the string_table.bin to text. It just wasn't working. well, I looked at the source code and it was because of the 'developer flag'. I've changed it to 1/true and built the project for myself again, then it was working! I don't know why you have made it a 'for developer only' thing, I wish you added it in the original build, so everyone else becomes able to use it I guess...

Also, I have no idea how to extract .binfbx files... am I missing something?
update: never mind, I just found out there are blender plugins on page 4.
thanks again!
## Post #82
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2021-10-06T16:15:59+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

The tool is under updating (when it is done first post will be updated as well). The extraction part is done, but there are some issue with tex<->dds conversion.

In the meantime who wants to translate the game, or move the AW translation into the Remastered version, here is the AWREM texts:


 AWREM_string.zip
Alan Wake Remastered texts (191.02 KiB) Downloaded 44 times
## Post #83
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2021-10-06T18:59:16+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Do you plan update tool for AW remastered?
## Post #84
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2021-10-07T07:32:37+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

No, I'm not planning, I am doing it, and the export part is almost done.
## Post #85
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2021-10-11T10:00:33+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

First post updated with the new version and Alan Wake Remastered support.

Still in BETA phase but probably most of the thing is working. I made some changes with the backward compatibility regarding the earlier game engine versions, but it was not tested fully!
## Post #86
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-10-12T08:54:59+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from evin ↑Mon Oct 11, 2021 6:00 pm at Mon Oct 11, 2021 6:00 pm
>
> 
First post updated with the new version and Alan Wake Remastered support.

Still in BETA phase but probably most of the thing is working. I made some changes with the backward compatibility regarding the earlier game engine versions, but it was not tested fully!

it works perfectly, thank you! Sadly, Mariokart script made for the original game, doesn't work with remastered
## Post #87
- Username: eyyohbee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-10-27T22:50:47+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Very new to using tools like this. When looking through the texture files, I can't locate any high resolution textures. Specifically, I'm looking for the absolute highest resolution possible of suddenstop_poster.tex.dds which is found in AlanWakeRemastered\data\ep999-001\special. If anyone could offer some assistance, I would greatly appreciate it!
## Post #88
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2021-11-02T13:29:26+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from evin ↑Thu Oct 07, 2021 12:15 am at Thu Oct 07, 2021 12:15 am
>
> 
In the meantime who wants to translate the game, or move the AW translation into the Remastered version, here is the AWREM texts:
AWREM_string.zip
Can you share texts from all avaliable languages?
## Post #89
- Username: MrWhy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 13, 2021 6:04 pm
- Post datetime: 2021-11-13T12:27:54+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Hello  . Will there be support for a CFHD campaign? I want to make Russian subtitles for the CFHD story campaign. Can I do it? I tried to extract the files with the current version of your program, but it didn't give any results. The program just closes.
## Post #90
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2021-11-17T17:43:56+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

What is CFHD ?!
## Post #91
- Username: MrWhy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 13, 2021 6:04 pm
- Post datetime: 2021-11-17T20:03:01+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

CrossfireHD - [https://www.remedygames.com/games/crossfirehd/](https://www.remedygames.com/games/crossfirehd/)

It is available on the Chinese Steam - "WeGame".  Remedy did a story campaign for her on November 12th.
## Post #92
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2021-11-26T11:47:38+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Until the game is not available WorldWide and on PC, I am unable to check the files.
## Post #93
- Username: MrWhy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 13, 2021 6:04 pm
- Post datetime: 2021-11-29T23:32:48+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

If you only need the game files, then I can upload them to the file sharing service. I have a WeGame account and access to the game and files. 
It is unlikely that it will be released worldwide. As stated, it will be available only for China, but there is a certain Russian community that, despite all the difficulties with access to the game, plays this game.
## Post #94
- Username: nhatvpo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jul 12, 2015 5:41 pm
- Post datetime: 2022-03-19T16:16:22+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Evin ↑Fri Nov 26, 2021 7:47 pm at Fri Nov 26, 2021 7:47 pm
>
> 
Until the game is not available WorldWide and on PC, I am unable to check the files.

What files i should upload to you it too big  about 20gb for first campain and 30gb for second campain
[https://imgur.com/rszki3m](https://imgur.com/rszki3m)
[https://imgur.com/Zqw3ec0](https://imgur.com/Zqw3ec0)
[https://imgur.com/Jnb42iF](https://imgur.com/Jnb42iF)
[https://imgur.com/7daDJAd](https://imgur.com/7daDJAd)
## Post #95
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2022-03-25T16:31:12+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from nhatvpo ↑Sun Mar 20, 2022 12:16 am at Sun Mar 20, 2022 12:16 am
>
> 
Evin wrote: ↑Fri Nov 26, 2021 7:47 pm
Until the game is not available WorldWide and on PC, I am unable to check the files.


What files i should upload to you it too big  about 20gb for first campain and 30gb for second campain
https://imgur.com/rszki3m
https://imgur.com/Zqw3ec0
https://imgur.com/Jnb42iF
https://imgur.com/7daDJAd
All where the filename contain "-en" and "-de". Except if bigger than 1GB.
## Post #96
- Username: nhatvpo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jul 12, 2015 5:41 pm
- Post datetime: 2022-03-26T17:27:01+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Evin ↑Fri Nov 26, 2021 7:47 pm at Fri Nov 26, 2021 7:47 pm
>
> 
All where the filename contain "-en" and "-de". Except if bigger than 1GB.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1aUwA2sdAh6PqkNO_w2DJEHbd3X6XnB5m?usp=sharing)
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1l4maeXKXBKvFQSREdRzu8HRSeDJcBcwP?usp=sharing)

Here is all file -en i found no files with -de characters thanks :3
## Post #97
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2022-03-27T20:24:23+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from nhatvpo ↑Sun Mar 27, 2022 1:27 am at Sun Mar 27, 2022 1:27 am
>
> 
Evin wrote: ↑Fri Nov 26, 2021 7:47 pm
All where the filename contain "-en" and "-de". Except if bigger than 1GB.

https://drive.google.com/drive/folders/ ... sp=sharing
https://drive.google.com/drive/folders/ ... sp=sharing

Here is all file -en i found no files with -de characters thanks :3

Ok, downloaded. I will check them.
## Post #98
- Username: nhatvpo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jul 12, 2015 5:41 pm
- Post datetime: 2022-09-07T10:42:43+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from Evin ↑Mon Mar 28, 2022 4:24 am at Mon Mar 28, 2022 4:24 am
>
> 
nhatvpo wrote: ↑Sun Mar 27, 2022 1:27 am
Evin wrote: ↑Fri Nov 26, 2021 7:47 pm
All where the filename contain "-en" and "-de". Except if bigger than 1GB.

https://drive.google.com/drive/folders/ ... sp=sharing
https://drive.google.com/drive/folders/ ... sp=sharing

Here is all file -en i found no files with -de characters thanks :3


Ok, downloaded. I will check them.

sorry for asking but is there any chance for CrossfireX
## Post #99
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2022-09-19T17:55:15+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

> Reply from nhatvpo ↑Wed Sep 07, 2022 6:42 pm at Wed Sep 07, 2022 6:42 pm
>
> 
sorry for asking but is there any chance for CrossfireX

Not really. If I find time I will update, but I do not know when.
## Post #100
- Username: BanhMi93
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 31, 2021 9:16 am
- Post datetime: 2022-10-21T05:15:16+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

i'm sorry to bring this thread up. Evin Could you take a look in the files from nintendo switch version of Alan Wake remastered, seems like the tool not supporting it, its crash when trying to open the packed.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/13OWJyRhpZ0jTtG-dQgBje5jgEKhWGbFj?usp=sharing)
## Post #101
- Username: memz
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Dec 16, 2022 8:00 pm
- Post datetime: 2023-01-06T17:15:47+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

solved
## Post #102
- Username: memz
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Dec 16, 2022 8:00 pm
- Post datetime: 2023-04-20T08:06:53+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Hello, how do I create a patch for game? Is there a console version of the tool?
## Post #103
- Username: BlackLion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 04, 2023 4:59 am
- Post datetime: 2023-06-03T21:22:58+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Can someone explain how it works?

I want to create a localization of Alan Wake Remastered. I unpacked ep999-000-en.bin from game folder. I can see 2 localization folders in unpacked files:
..\ep999-000-en\locale\en\ - seems like here is mail localization part
..\ep999-000-en\menu\locale\en - and here is menu localization, but I am not sure

In first folder only on file string_table.bin how I can change it?
In second folder I can see files with .tex but can't do nothing with them with Northlight Tool - I don't know how to convert them to any file type that I can edit.

Tried to make changes in file string_table.bin.txt and copy it into unpacked folder ..\ep999-000-en\locale\en\ and then tried to do import in Northlight Tool - nothing happened.

I simply don't understand how it works and info in _INFO.rtf is not enough. Please, help to understand what should I do.
## Post #104
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2023-06-08T20:40:36+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Export content of ep999-000-en.
Delete the exported files you do not need (optional but recommended).
Copy the txt file from the tool package with the subfolders
Change the txt.
Use Import button. If you closed in the meantime the tool, open again ep999-000-en.bin and the OUTPUT folder where are the extracted files.
Replace the ep999-000-en.bin/rmdp files with the new ones.
## Post #105
- Username: Dumpyboi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 16, 2023 10:55 pm
- Post datetime: 2023-06-16T14:59:07+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Is it possible to edit meshes in Control?   Because It's weird that I see nothing but retextures on the nexus.
## Post #106
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2023-06-16T20:16:46+00:00
- Post Title: Re: Northlight Tool (also known as "The Alan Wake Engine")

Sneak peak into the (planned) future of this project of mine: [https://github.com/TomEvin/neat/](https://github.com/TomEvin/neat/)
