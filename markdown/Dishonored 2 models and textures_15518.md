## Post #1
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-11-21T14:02:48+00:00
- Post Title: Dishonored 2 models and textures

Has anyone had any luck getting those? They are packed as .resources, is there currently any software that can unpack this format?
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-11-21T15:52:17+00:00
- Post Title: Dishonored 2 models and textures

.index file is table of contents
.resources file is compressed format
Engine used in Dishonored 2 (Void) is basically modified id tech 5.
It uses bmd6model, md6skl, bimage7 etc. but most of them will be stored in havok container (.hkx) including some animations.
I also found edgeskl and edgeanim, edged skeletons and animations are also used in previous game.
As far for textures, I dont think it uses megatextures but I might be wrong about this one.
## Post #3
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-11-21T16:27:46+00:00
- Post Title: Dishonored 2 models and textures

Okay, do you know what I can use to unpack the files and convert them to something like fbx and dds?
## Post #4
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-02T19:43:54+00:00
- Post Title: Dishonored 2 models and textures

There's a quickbms script for unpacking:

[http://aluigi.altervista.org/bms/dishonored2.bms](http://aluigi.altervista.org/bms/dishonored2.bms)

But of course the game being so new, support isn't 100%, and like any game, it will take time for people to develop extraction techniques. As stated, it uses modified Tech5 engine, so perhaps some of the Tech5 tools will work. I don't own the game yet, so I can't look into it yet.
## Post #5
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-10T02:08:07+00:00
- Post Title: Dishonored 2 models and textures

[viewtopic.php?p=124908#p124908](http://forum.xentax.com/viewtopic.php?p=124908#p124908)
I released my texture converter for Dishonored 2 there. I have a bit more work to do on it, to fix cubemaps, then I'll start looking at models.
## Post #6
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-10T23:06:49+00:00
- Post Title: Dishonored 2 models and textures

I've made good progress figuring out the model format.



There's still some sections I haven't figured out, I believe they are normals and bone weights, but they are being mysterious.  Also haven't looked at the skeleton yet, it's in a separate file.  I'll keep at it.
## Post #7
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2016-12-11T12:45:04+00:00
- Post Title: Dishonored 2 models and textures

Great! I'm looking forward to it!
## Post #8
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-12T03:10:35+00:00
- Post Title: Dishonored 2 models and textures

Ok, the model importer is functional, so I'll release. but there's a lot of caveats:

A) No skeleton or bone weight support at this time. (I am having trouble working out the weighting part).
B) Solved
C) models are broken up into a lot of parts, and positions aren't stored in the model files (uncertain, more research needed) So you'll have to move all the parts around to fit them together.

The good news is, Multiple models per file and multiple materials per model is supported, as is the two UV maps each model has (some duplicate the UV on both channels, but some, especially the main characters do have different UVs on each channel.  I expect this is for effects like texturing and dirt/normal to be on separately laid out maps. But I have not looked into this in depth)
Also, this importer supports two model formats the game uses Bmd6model, and bmodel. should load either with no problem.

Example:


  Multiple Material zones as defined in-game


All the parts with textures (I frankly don't know where all the gears go LOL)

The parts were found in these various directories:
 Base Model: Pack 1\generated\basemodel\models\characters\mech\clockwork
 Wooden Armor parts: Pack 1\generated\model\models\characters\mech\clockwork\breakables
 Gears and Guts: Pack 1\generated\model\models\characters\mech\clockwork\wheels
 Textures were all in: Pack 1\generated\image\models\characters\mech\clockwork\textures

Edit: Head parts are in the root of the extraction directory, Named like this: "nocloth_f_str_alexi_head_6381dc2474fd3c558dde926c5129fcad.bmd6model" for Alexi model.

Additionally, it seems like a lot of small parts to models are in the 'voidresourcecache' folder.

So that's the basic arrangement for assets.

If you come across any model files that produce an error, let me know the model name and location and I'll see what I can do about fixing.

Oh yeah I should add, importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
[viewtopic.php?p=103131#p103131](http://forum.xentax.com/viewtopic.php?p=103131#p103131)

   Enjoy.

Edit: new version below.
## Post #9
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-12T19:36:20+00:00
- Post Title: Dishonored 2 models and textures

I was wrong about the high poly heads, they were just in an odd location. I updated the above post to explain how to find them.
## Post #10
- Username: copeland3300
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 20, 2017 9:25 am
- Post datetime: 2017-01-20T02:00:51+00:00
- Post Title: Dishonored 2 models and textures

Any ideas on where to find levels/maps? I've found many references to maps in general, but the files seem way too small to be the actual model data.
## Post #11
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-20T18:57:29+00:00
- Post Title: Dishonored 2 models and textures

> Reply from copeland3300
>
> Any ideas on where to find levels/maps? I've found many references to maps in general, but the files seem way too small to be the actual model data.
yeah this is something I haven't looked hard into yet. But I believe if you go to like:
\maps\campaign\dunwall\escape\streets  in Game2 extraction folder, you'll see files called 'dunwall_escape_streets_p.entities'  and 'dunwall_escape_streets_p.soundpropa'.

I believe these are the actual level files and 'sound zones' used for the main level.  the Entities file is an XML file that contains position, rotation, and other definitions for every item in the level. This indicates the levels aren't one solid item but just a collection of a lot of tiny parts.

There may be some large 'base chunks' but you'd have to wade through all the entries in the xml to figure out which those are. And they may be in the new shared_2_3.sharedrsc file we just figured out how to extract. I've not yet examined that, been tied up with other projects.  If you figure something out, let us know.
## Post #12
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-27T02:46:24+00:00
- Post Title: Dishonored 2 models and textures

Minor update:
- Ensure Object mode is active before attempting import
- Validated functionality back to Blender version 2.70 (oldest supported)


Edit: newer version on page 3.
## Post #13
- Username: iello
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 27, 2017 11:45 am
- Post datetime: 2017-01-29T08:00:07+00:00
- Post Title: Dishonored 2 models and textures

Hi, first time posting on these boards. Came to ask a favor/question. 

I was looking for an extract of the coin textures, specifically the Empress style coins in the game. I've found an extracted what I think are the right textures, in "generated\image\models\interactive\pickups\coins_01" and I found "coins_old_regent_emily_n.bimage7" and "coins_old_regent_empress_n.bimage7"

After extracting all the resource files and converting to dds, it looks like those two are the only images like that -- I guess they're just normal maps? And then the other old regent coins are the diffuse maps and whatever "g" means for textures? For example, "coins_old_regent_01_d.bimage7" and "coins_old_regent_01_g.bimage7" for the gold coins? That was a pain, I was looking for a clear, head-on image of those gold Empress/Emily coins.  

Is there any way to layer them together in Photoshop so that they look like a clean coin design, like they do in-game? Or do I have to put them onto the coin models at "generated\model\models\interactive\pickups\coins_01" ?

Playing with models is a bit beyond my abilities sadly... -- if the latter, is it possible for somebody to help me with pictures of those coins?
## Post #14
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-29T17:58:59+00:00
- Post Title: Dishonored 2 models and textures

> Reply from iello
>
> Hi, first time posting on these boards. Came to ask a favor/question. 

I was looking for an extract of the coin textures, specifically the Empress style coins in the game. I've found an extracted what I think are the right textures, in "generated\image\models\interactive\pickups\coins_01" and I found "coins_old_regent_emily_n.bimage7" and "coins_old_regent_empress_n.bimage7"

After extracting all the resource files and converting to dds, it looks like those two are the only images like that -- I guess they're just normal maps? And then the other old regent coins are the diffuse maps and whatever "g" means for textures? For example, "coins_old_regent_01_d.bimage7" and "coins_old_regent_01_g.bimage7" for the gold coins? That was a pain, I was looking for a clear, head-on image of those gold Empress/Emily coins.  

Is there any way to layer them together in Photoshop so that they look like a clean coin design, like they do in-game? Or do I have to put them onto the coin models at "generated\model\models\interactive\pickups\coins_01" ?

Playing with models is a bit beyond my abilities sadly... -- if the latter, is it possible for somebody to help me with pictures of those coins?

Photoshop itself can load models. Starting with CS5 they added that feature.

But if you want a head-on image, just load the '_g' texture, that shows the coin:



But it would look better if you did it on the model:
## Post #15
- Username: iello
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 27, 2017 11:45 am
- Post datetime: 2017-01-29T18:04:02+00:00
- Post Title: Dishonored 2 models and textures

edit: Sorry for all the questions, I figured out how to export the object from Blender, how to texture the diffuse, normal, and gloss textures on photoshop. But this thing is dark as heck, especially when viewed straight-on. Is there a way to get some illumination on it? (edit: figured out I can mess with the infinite light and rotate it around.... do you think the lighting on the second image is as ideal as it gets?)
## Post #16
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-30T00:45:45+00:00
- Post Title: Re: Dishonored 2 models and textures

yeah photoshop doesn't have the best lighting setup. You'd have to set up materials in some other engine to get better results.
## Post #17
- Username: rawfish38
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 21, 2017 12:54 pm
- Post datetime: 2017-02-21T21:27:17+00:00
- Post Title: Re: Dishonored 2 models and textures

I'm trying to find furniture files specifically, like chairs and tables, Any idea where those may be located?
## Post #18
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-03-08T18:03:57+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from rawfish38
>
> I'm trying to find furniture files specifically, like chairs and tables, Any idea where those may be located?

I've seen a few, was there a specific one you were looking for? I'd suggest looking at generated/model/models/environment/props if you haven't found them yet.

Has anyone happened to stumble onto the models for the 'outsider origin story' scene? Specifically like the sacrifice stone, the statue cultists (I assume they're a character file somewhere), and most importantly the double bladed cult knife. I've been tearing this game apart and swear I've seen pretty much everything but that chunk of models, and it's driving me up the wall.
## Post #19
- Username: Sttmccln
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 17, 2015 8:12 am
- Post datetime: 2017-04-11T09:25:36+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> Ok, the model importer is functional, so I'll release. but there's a lot of caveats:

A) No skeleton or bone weight support at this time. (I am having trouble working out the weighting part).
B) Solved
C) models are broken up into a lot of parts, and positions aren't stored in the model files (uncertain, more research needed) So you'll have to move all the parts around to fit them together.

The good news is, Multiple models per file and multiple materials per model is supported, as is the two UV maps each model has (some duplicate the UV on both channels, but some, especially the main characters do have different UVs on each channel.  I expect this is for effects like texturing and dirt/normal to be on separately laid out maps. But I have not looked into this in depth)
Also, this importer supports two model formats the game uses Bmd6model, and bmodel. should load either with no problem.

Example:


  Multiple Material zones as defined in-game


All the parts with textures (I frankly don't know where all the gears go LOL)

The parts were found in these various directories:
 Base Model: Pack 1\generated\basemodel\models\characters\mech\clockwork
 Wooden Armor parts: Pack 1\generated\model\models\characters\mech\clockwork\breakables
 Gears and Guts: Pack 1\generated\model\models\characters\mech\clockwork\wheels
 Textures were all in: Pack 1\generated\image\models\characters\mech\clockwork\textures

Edit: Head parts are in the root of the extraction directory, Named like this: "nocloth_f_str_alexi_head_6381dc2474fd3c558dde926c5129fcad.bmd6model" for Alexi model.

Additionally, it seems like a lot of small parts to models are in the 'voidresourcecache' folder.

So that's the basic arrangement for assets.

If you come across any model files that produce an error, let me know the model name and location and I'll see what I can do about fixing.

Oh yeah I should add, importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
viewtopic.php?p=103131#p103131

   Enjoy.

Edit: new version below.

Any way you could send that Clockwork Soldier file to me? Huge downside to owning on console is that I cant rip things myself...
## Post #20
- Username: Emissaryofwind
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 18, 2016 6:00 am
- Post datetime: 2017-04-11T10:44:46+00:00
- Post Title: Re: Dishonored 2 models and textures

If you want to get it on PC to rip things yourself, now's a great time, the game is half-off on steam! And there's a free trial with the first 3 missions that you might be able to rip things from as well.
## Post #21
- Username: Sttmccln
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 17, 2015 8:12 am
- Post datetime: 2017-04-11T22:22:45+00:00
- Post Title: Re: Dishonored 2 models and textures

Just tried, Steam wont let me because I dont have a 64 bit os.
## Post #22
- Username: Stut29
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 07, 2017 2:17 pm
- Post datetime: 2017-04-13T11:04:44+00:00
- Post Title: Re: Dishonored 2 models and textures

Hello,

Was skeleton support added to the model importer? I see mention of skeletons in the file, but I'm new to this stuff and don't understand it.
Also, is there a simple way I'm missing to batch import the models into Blender? Will that require additional scripting?

Thanks for creating these tools.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-05T17:46:22+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from Stut29
>
> Also, is there a simple way I'm missing to batch import the models into Blender? Will that require additional scripting?the models would overlap each other. You'd to separate them manually. Is that what you really want?

If so it's possible using a rather simple script:



Dishonored2_batch_import.jpg (179.3 KiB) Viewed 645 times



btw: please ignore/replace the string 'obj'; I was too lazy to adjust that
## Post #24
- Username: JG123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 17, 2017 12:12 am
- Post datetime: 2017-06-16T16:20:01+00:00
- Post Title: Re: Dishonored 2 models and textures

Hi, I'm new here, but I love the games and the models pretty cool, How can't I get Dishonored 2 models? 
If someone has it, I'm  expecialy looking for, those guard's like saylor type.
## Post #25
- Username: minitiv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 01, 2017 12:28 am
- Post datetime: 2017-06-17T12:58:51+00:00
- Post Title: Re: Dishonored 2 models and textures

-snip-
## Post #26
- Username: HooptyHaupt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 23, 2016 1:13 am
- Post datetime: 2017-07-11T21:01:50+00:00
- Post Title: Re: Dishonored 2 models and textures

It still works perfectly for me, I get both textures and models when extracting each package.
## Post #27
- Username: minitiv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 01, 2017 12:28 am
- Post datetime: 2017-07-11T21:27:36+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from HooptyHaupt
>
> It still works perfectly for me, I get both textures and models when extracting each package.
Which game version you had?
## Post #28
- Username: HooptyHaupt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 23, 2016 1:13 am
- Post datetime: 2017-07-12T22:04:39+00:00
- Post Title: Re: Dishonored 2 models and textures

I have the newest version.
## Post #29
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-09-18T22:49:44+00:00
- Post Title: Re: Dishonored 2 models and textures

To resurrect this thread a bit, I was able to extract Death of The Outsider's contents... but for all of the BMD6models that aren't static (character files, animals), Volfin's blender import plugin isn't working. No error, no objects listed, hit import and nothing happens for those files. Any ideas? I'm completely clueless at this part.
## Post #30
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-09-19T02:34:03+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from windswept
>
> To resurrect this thread a bit, I was able to extract Death of The Outsider's contents... but for all of the BMD6models that aren't static (character files, animals), Volfin's blender import plugin isn't working. No error, no objects listed, hit import and nothing happens for those files. Any ideas? I'm completely clueless at this part.

I don't have this game, but I'll go out on a limb and say they probably changed the model format a bit, since it's a completely standalone game and not a DLC. With any model format even one byte difference is enough to throw an importer off.

it's also possible whatever method you're using to unpack the files isn't producing the same format of files as the unpacker for Dishonored 2.

If you can provide a few model files, i'll take a quick look and see what I can see.
## Post #31
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-09-19T19:24:03+00:00
- Post Title: Re: Dishonored 2 models and textures

Sure, [here's a couple files it happens on.](https://drive.google.com/file/d/0B_GaRFw4El5ZckxWUmNjQ0F2cmc/view?usp=sharing) Hope that helps!
## Post #32
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-09-20T03:00:32+00:00
- Post Title: Re: Dishonored 2 models and textures

Yes, I compared the file you sent with the original one from the first Dishonored 2. 



As you can see, they are identical except for the 4 digit ID at the start of the file. They changed it (version #?) and that's the only difference.

I've updated the plugin to accept that as a valid model type, and both of your samples load fine.

Enjoy.
[io_scene_Dishonored2.zip](https://xentaxbackup.github.io/file/13329_io_scene_Dishonored2.zip)
## Post #33
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-09-20T16:29:56+00:00
- Post Title: Re: Dishonored 2 models and textures

Aaah, I see. Thanks for the update, much appreciated!
## Post #34
- Username: fathomprops
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 10, 2017 9:04 am
- Post datetime: 2017-09-22T01:57:43+00:00
- Post Title: Re: Dishonored 2 models and textures

Hey guys!

Alright so I am new to this site, and actually joined because of this thread in particular. 
I'm an amateur 3d modeler, propmaker, and carpeting and have been dying to do a real life wood carved Clockwork Soldier Head. A 3D model of this would help IMMENSELY, but for the life of me I can't figure out what you guys are doing to get these models lol. 

Is there any way someone would be able to help me out with a model of a Clockwork Soldier or just his head at least, I'm working in Maya or blender so any file type that is compatible with those would be fine. I've been looking forever and trying to model my own but it never seems to be right. Any help is soooooo appreciated!
## Post #35
- Username: halfriv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 31, 2016 2:06 am
- Post datetime: 2017-09-27T00:40:43+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from fathomprops
>
> Hey guys!

Alright so I am new to this site, and actually joined because of this thread in particular. 
I'm an amateur 3d modeler, propmaker, and carpeting and have been dying to do a real life wood carved Clockwork Soldier Head. A 3D model of this would help IMMENSELY, but for the life of me I can't figure out what you guys are doing to get these models lol. 

Is there any way someone would be able to help me out with a model of a Clockwork Soldier or just his head at least, I'm working in Maya or blender so any file type that is compatible with those would be fine. I've been looking forever and trying to model my own but it never seems to be right. Any help is soooooo appreciated!

The one titled head is just the wooden armor part, the rest of the objs are the body and the machinery in the head. When I loaded the head armor it was at the feet so i moved it up to where it seems like it's supposed to be, but it's its own file so you can move it as well. I unfortunately deleted the texture files so someone else is gonna have to help you out with that if you need them.

[https://drive.google.com/open?id=0B0F51 ... DlLSXp2dkk](https://drive.google.com/open?id=0B0F51fqxBKG5MWpHbDlLSXp2dkk)
## Post #36
- Username: fathomprops
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 10, 2017 9:04 am
- Post datetime: 2017-09-28T04:33:14+00:00
- Post Title: Re: Dishonored 2 models and textures

This really is great! I can't thank you enough! Ive been struggling so much with this project and this will be a huge help. Thanks again!
## Post #37
- Username: HooptyHaupt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 23, 2016 1:13 am
- Post datetime: 2017-10-11T19:50:33+00:00
- Post Title: Re: Dishonored 2 models and textures

Will there be bones support sometime in the future ? The number of usable assets is pretty small, bones support would fill up that void a little bit :/
## Post #38
- Username: mmorfee
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 09, 2017 5:24 pm
- Post datetime: 2017-10-12T16:05:17+00:00
- Post Title: Re: Dishonored 2 models and textures

Guys, where can I find modular pieces for buildings, rooms, wall panels etc? In \model\environment\archi\.. and \model\environment\buildings\ only few pieces.
## Post #39
- Username: HooptyHaupt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 23, 2016 1:13 am
- Post datetime: 2017-10-12T18:06:46+00:00
- Post Title: Re: Dishonored 2 models and textures

They are packed with the maps unfortunately so there's no chance of getting them in a usable state(yet). You can get them with Ninjaripper but the UVs are destroyed beyond repair.
## Post #40
- Username: copeland3300
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 20, 2017 9:25 am
- Post datetime: 2017-12-31T02:53:52+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from HooptyHaupt
>
> They are packed with the maps unfortunately so there's no chance of getting them in a usable state(yet). You can get them with Ninjaripper but the UVs are destroyed beyond repair.

EDITED!

Hey, I'm also interested in extracting some of the assets from the maps. 

I've been playing with NinjaRipper for a few hours, but aside from random textures, I haven't really been able to extract any of the mesh data. All I'm getting is 1KB .rip files.

Any suggestions would be awesome!

I've seeming had some success with DDRAW mode, but still need to play with it a little more.
## Post #41
- Username: NervousEnergy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 01, 2018 11:18 pm
- Post datetime: 2018-01-01T15:21:31+00:00
- Post Title: Re: Dishonored 2 models and textures

Two quick questions; I've converted a few of the bimage textures to DDS using @volfin's converter, and then to PNG using Photoshop and the DDS plugin; mostly in-game posters and signs.

However they appear to be stretched thin a lil bit, see attached image. Anyone know the correct ratio the images should be in? I can then just resize the PNGs in Photoshop, but I want to know what ratio they should be. 

Secondly; I can't find anywhere the textures for Delilah's paintings that appear in end of Dunwall Tower. They don't appear to be in any of the normal folders like /pickups or /props. I've gone through hundreds of files. Are they stored in the maps directly...? Shame as they're really nice.
## Post #42
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-14T19:06:48+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> I've made good progress figuring out the model format.



There's still some sections I haven't figured out, I believe they are normals and bone weights, but they are being mysterious.  Also haven't looked at the skeleton yet, it's in a separate file.  I'll keep at it.
Hey, Volfin. ALL the links are broken (to all converters etc). So could you please upload importer script for Blender or 3Ds Max and texture converter? I need it so much.
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-15T00:00:13+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from MommoXX
>
> 
Hey, Volfin. ALL the links are broken (to all converters etc). So could you please upload importer script for Blender or 3Ds Max and texture converter? I need it so much.

I've never used 3rd party hosting, everything I release is an attachment stored on this website, there's no links to be broken, it's all still there.

example: [viewtopic.php?p=133901#p133901](http://forum.xentax.com/viewtopic.php?p=133901#p133901)
## Post #44
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T05:09:26+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> MommoXX wrote:
Hey, Volfin. ALL the links are broken (to all converters etc). So could you please upload importer script for Blender or 3Ds Max and texture converter? I need it so much.

I've never used 3rd party hosting, everything I release is an attachment stored on this website, there's no links to be broken, it's all still there.

example: viewtopic.php?p=133901#p133901
Oh, I mean, not all of them is broken, but some important is. Like texture converter (the link on dropbox and also on some site are broken). And is the link that you sent me now is importer? Or it's scene from D2? Uh.. please, upload texture converter to some Drive and send it here, also importer script for 3Ds Max (if you create one for 3ds Max of course).
Upd. Nvm, I just searched better...
## Post #45
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T10:27:01+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> Ok, the model importer is functional, so I'll release. but there's a lot of caveats:

A) No skeleton or bone weight support at this time. (I am having trouble working out the weighting part).
B) Solved
C) models are broken up into a lot of parts, and positions aren't stored in the model files (uncertain, more research needed) So you'll have to move all the parts around to fit them together.

The good news is, Multiple models per file and multiple materials per model is supported, as is the two UV maps each model has (some duplicate the UV on both channels, but some, especially the main characters do have different UVs on each channel.  I expect this is for effects like texturing and dirt/normal to be on separately laid out maps. But I have not looked into this in depth)
Also, this importer supports two model formats the game uses Bmd6model, and bmodel. should load either with no problem.

Example:


  Multiple Material zones as defined in-game


All the parts with textures (I frankly don't know where all the gears go LOL)

The parts were found in these various directories:
 Base Model: Pack 1\generated\basemodel\models\characters\mech\clockwork
 Wooden Armor parts: Pack 1\generated\model\models\characters\mech\clockwork\breakables
 Gears and Guts: Pack 1\generated\model\models\characters\mech\clockwork\wheels
 Textures were all in: Pack 1\generated\image\models\characters\mech\clockwork\textures

Edit: Head parts are in the root of the extraction directory, Named like this: "nocloth_f_str_alexi_head_6381dc2474fd3c558dde926c5129fcad.bmd6model" for Alexi model.

Additionally, it seems like a lot of small parts to models are in the 'voidresourcecache' folder.

So that's the basic arrangement for assets.

If you come across any model files that produce an error, let me know the model name and location and I'll see what I can do about fixing.

Oh yeah I should add, importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
viewtopic.php?p=103131#p103131

   Enjoy.

Edit: new version below.
Okay.. how to import skeleton? Your script can import only meshes.
## Post #46
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-15T15:08:07+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from MommoXX
>
> volfin wrote:Ok, the model importer is functional, so I'll release. but there's a lot of caveats:

A) No skeleton or bone weight support at this time. (I am having trouble working out the weighting part).
B) Solved
C) models are broken up into a lot of parts, and positions aren't stored in the model files (uncertain, more research needed) So you'll have to move all the parts around to fit them together.

The good news is, Multiple models per file and multiple materials per model is supported, as is the two UV maps each model has (some duplicate the UV on both channels, but some, especially the main characters do have different UVs on each channel.  I expect this is for effects like texturing and dirt/normal to be on separately laid out maps. But I have not looked into this in depth)
Also, this importer supports two model formats the game uses Bmd6model, and bmodel. should load either with no problem.

Example:


  Multiple Material zones as defined in-game


All the parts with textures (I frankly don't know where all the gears go LOL)

The parts were found in these various directories:
 Base Model: Pack 1\generated\basemodel\models\characters\mech\clockwork
 Wooden Armor parts: Pack 1\generated\model\models\characters\mech\clockwork\breakables
 Gears and Guts: Pack 1\generated\model\models\characters\mech\clockwork\wheels
 Textures were all in: Pack 1\generated\image\models\characters\mech\clockwork\textures

Edit: Head parts are in the root of the extraction directory, Named like this: "nocloth_f_str_alexi_head_6381dc2474fd3c558dde926c5129fcad.bmd6model" for Alexi model.

Additionally, it seems like a lot of small parts to models are in the 'voidresourcecache' folder.

So that's the basic arrangement for assets.

If you come across any model files that produce an error, let me know the model name and location and I'll see what I can do about fixing.

Oh yeah I should add, importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
viewtopic.php?p=103131#p103131

   Enjoy.

Edit: new version below.
Okay.. how to import skeleton? Your script can import only meshes.

Read point A).
## Post #47
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T15:15:40+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> MommoXX wrote:volfin wrote:Ok, the model importer is functional, so I'll release. but there's a lot of caveats:

A) No skeleton or bone weight support at this time. (I am having trouble working out the weighting part).
B) Solved
C) models are broken up into a lot of parts, and positions aren't stored in the model files (uncertain, more research needed) So you'll have to move all the parts around to fit them together.

The good news is, Multiple models per file and multiple materials per model is supported, as is the two UV maps each model has (some duplicate the UV on both channels, but some, especially the main characters do have different UVs on each channel.  I expect this is for effects like texturing and dirt/normal to be on separately laid out maps. But I have not looked into this in depth)
Also, this importer supports two model formats the game uses Bmd6model, and bmodel. should load either with no problem.

Example:


  Multiple Material zones as defined in-game


All the parts with textures (I frankly don't know where all the gears go LOL)

The parts were found in these various directories:
 Base Model: Pack 1\generated\basemodel\models\characters\mech\clockwork
 Wooden Armor parts: Pack 1\generated\model\models\characters\mech\clockwork\breakables
 Gears and Guts: Pack 1\generated\model\models\characters\mech\clockwork\wheels
 Textures were all in: Pack 1\generated\image\models\characters\mech\clockwork\textures

Edit: Head parts are in the root of the extraction directory, Named like this: "nocloth_f_str_alexi_head_6381dc2474fd3c558dde926c5129fcad.bmd6model" for Alexi model.

Additionally, it seems like a lot of small parts to models are in the 'voidresourcecache' folder.

So that's the basic arrangement for assets.

If you come across any model files that produce an error, let me know the model name and location and I'll see what I can do about fixing.

Oh yeah I should add, importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
viewtopic.php?p=103131#p103131

   Enjoy.

Edit: new version below.
Okay.. how to import skeleton? Your script can import only meshes.

Read point A).
So will you solve it?
## Post #48
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T15:18:19+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> MommoXX wrote:volfin wrote:Ok, the model importer is functional, so I'll release. but there's a lot of caveats:

A) No skeleton or bone weight support at this time. (I am having trouble working out the weighting part).
B) Solved
C) models are broken up into a lot of parts, and positions aren't stored in the model files (uncertain, more research needed) So you'll have to move all the parts around to fit them together.

The good news is, Multiple models per file and multiple materials per model is supported, as is the two UV maps each model has (some duplicate the UV on both channels, but some, especially the main characters do have different UVs on each channel.  I expect this is for effects like texturing and dirt/normal to be on separately laid out maps. But I have not looked into this in depth)
Also, this importer supports two model formats the game uses Bmd6model, and bmodel. should load either with no problem.

Example:


  Multiple Material zones as defined in-game


All the parts with textures (I frankly don't know where all the gears go LOL)

The parts were found in these various directories:
 Base Model: Pack 1\generated\basemodel\models\characters\mech\clockwork
 Wooden Armor parts: Pack 1\generated\model\models\characters\mech\clockwork\breakables
 Gears and Guts: Pack 1\generated\model\models\characters\mech\clockwork\wheels
 Textures were all in: Pack 1\generated\image\models\characters\mech\clockwork\textures

Edit: Head parts are in the root of the extraction directory, Named like this: "nocloth_f_str_alexi_head_6381dc2474fd3c558dde926c5129fcad.bmd6model" for Alexi model.

Additionally, it seems like a lot of small parts to models are in the 'voidresourcecache' folder.

So that's the basic arrangement for assets.

If you come across any model files that produce an error, let me know the model name and location and I'll see what I can do about fixing.

Oh yeah I should add, importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
viewtopic.php?p=103131#p103131

   Enjoy.

Edit: new version below.
Okay.. how to import skeleton? Your script can import only meshes.

Read point A).
If you have extracted files from Dishonored 2, can you give me Corvo's textures? Cuz it will take time to unpack that BIG (7gb) package. (Just some guy send model, skeleton and anims of Corvo)
## Post #49
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-15T15:25:25+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from MommoXX
>
> So will you solve it?

Probably not, I haven't messed with it for over a year now, and I don't even have the game/files installed anymore.
## Post #50
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T15:56:59+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> MommoXX wrote:So will you solve it?

Probably not, I haven't messed with it for over a year now, and I don't even have the game/files installed anymore.
But I don't understand how to extract game files (.resources).. Help me.
## Post #51
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T15:59:18+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from MommoXX
>
> volfin wrote:MommoXX wrote:So will you solve it?

Probably not, I haven't messed with it for over a year now, and I don't even have the game/files installed anymore.
But I don't understand how to extract game files (.resources).. Help me.
Oh. Wait, I will do something. If i won't got it - I will tell you.
## Post #52
- Username: MommoXX
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 14, 2018 9:47 pm
- Post datetime: 2018-08-15T16:30:36+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> MommoXX wrote:So will you solve it?

Probably not, I haven't messed with it for over a year now, and I don't even have the game/files installed anymore.
Do you know which file contains textures?
Upd. If someone can't find textures - it's in game1.resources and game2.resources.
## Post #53
- Username: ceephax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 15, 2018 6:23 pm
- Post datetime: 2018-12-15T10:32:10+00:00
- Post Title: Re: Dishonored 2 models and textures

Guys, can't find the attachment for the model importer.(( Send me the link please
## Post #54
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-12-15T16:20:31+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from ceephax
>
> Guys, can't find the attachment for the model importer.(( Send me the link please

it's in the second post on page 3
## Post #55
- Username: ceephax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 15, 2018 6:23 pm
- Post datetime: 2018-12-15T17:29:15+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from volfin
>
> ceephax wrote:Guys, can't find the attachment for the model importer.(( Send me the link please

it's in the second post on page 3

 Thank you very much!!
Sorry for the noob question, but i've installed "Addon from file", and searched different names - bmd, io, dishonored - and can't find it in the list. What is the name of the importer?
## Post #56
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2020-07-14T18:28:41+00:00
- Post Title: Re: Dishonored 2 models and textures

Since after all these years there was no progress on importing map data, I became curious if I could figure it out, and frankly got a bit carried away. As a result, here is a new, effectively rewritten from scratch version of the model importer add-on, which supports:

1) Blender 2.8
2) Bone weights and skeletons: the skeletons are bare, so they don't look nice, but they do work.
3) Materials: while manually assembling a few materials for a character isn't that hard, when it comes to hundreds of materials in a map, with a few textures in each, doing everything manually isn't practical. The addon now reads material definition files and assembles simple PBR node materials with textures.
4) Static map geometry: the add-on can now import bwm files, with support for LOD filtering based on distance from the blender cursor.
5) Map entities: the entities files can also be imported, adding all declared lights and referenced models to the scene.

More detailed documentation is in a readme.txt file inside the add-on zip file.

Since importing a model now involves accessing other files, models should be imported directly from the directory where the resource packs were unpacked. The add-on also now includes Volfin's texture converter and texconv.exe so that it can do the bimage7 -> dds -> png conversion on demand (if a png or tga file is already there it'll just use it of course).
## Post #57
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2020-08-15T15:40:37+00:00
- Post Title: Re: Dishonored 2 models and textures

A small update to material handling:

- Slightly more correct handling of normal maps.
- Basic handling of hair materials with fake anisotropy to avoid the ugly 'glass hat' look for imported characters.
## Post #58
- Username: Stut29
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 07, 2017 2:17 pm
- Post datetime: 2021-01-16T00:52:35+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from AlexNG ↑Wed Jul 15, 2020 2:28 am at Wed Jul 15, 2020 2:28 am
>
> 
Since after all these years there was no progress on importing map data, I became curious if I could figure it out, and frankly got a bit carried away. As a result, here is a new, effectively rewritten from scratch version of the model importer add-on, which supports:

1) Blender 2.8
2) Bone weights and skeletons: the skeletons are bare, so they don't look nice, but they do work.
3) Materials: while manually assembling a few materials for a character isn't that hard, when it comes to hundreds of materials in a map, with a few textures in each, doing everything manually isn't practical. The addon now reads material definition files and assembles simple PBR node materials with textures.
4) Static map geometry: the add-on can now import bwm files, with support for LOD filtering based on distance from the blender cursor.
5) Map entities: the entities files can also be imported, adding all declared lights and referenced models to the scene.

More detailed documentation is in a readme.txt file inside the add-on zip file.

Since importing a model now involves accessing other files, models should be imported directly from the directory where the resource packs were unpacked. The add-on also now includes Volfin's texture converter and texconv.exe so that it can do the bimage7 -> dds -> png conversion on demand (if a png or tga file is already there it'll just use it of course).

Incredible! Thank you for doing this.

I'm likely overlooking something simple, but where can I locate the .bwm files? I've extracted everything using the latest quickbms script I could find but there doesn't seem to be any .bwm files. It does give me the entity files and those import perfectly.

Thanks again.
## Post #59
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2021-01-17T08:25:26+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from Stut29 ↑Sat Jan 16, 2021 8:52 am at Sat Jan 16, 2021 8:52 am
>
> 
I'm likely overlooking something simple, but where can I locate the .bwm files? I've extracted everything using the latest quickbms script I could find but there doesn't seem to be any .bwm files. It does give me the entity files and those import perfectly.

They are in a subdirectory relative to the entities file. There are a lot of other files there too, but the open dialog in blender will filter them out.
## Post #60
- Username: Stut29
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 07, 2017 2:17 pm
- Post datetime: 2021-01-17T14:39:08+00:00
- Post Title: Re: Dishonored 2 models and textures

Got it!

After realising I was also missing a lot of _mip0 files (many textures were not converting to .dds), I've run quickbms again using dishonored2.bms 0.2.1 and the one for shared_2_3.sharedrsc. After pointing them to the correct files instead of the entire folder it's started spitting out some .bwm files and the remaining _mip0 files I was missing.

Thanks again for making this. I'd manually rebuilt much of the Hound Pits Pub from the first game using extracted models and to be able to import Dishonored 2 stuff into Blender automatically is a big time saver as you might imagine.
## Post #61
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2021-01-17T22:32:25+00:00
- Post Title: Re: Dishonored 2 models and textures

is the texture coverter and model importer the same file?
## Post #62
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2021-01-28T14:16:19+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from DV9 x Drillz ↑Mon Jan 18, 2021 6:32 am at Mon Jan 18, 2021 6:32 am
>
> 
is the texture coverter and model importer the same file?

Texture converter and importer are obviously different tools, but my version of the importer includes the texture converter exe file and automatically calls it to convert specific textures it needs, instead of requiring all textures to be converted beforehand.
## Post #63
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2021-02-03T20:29:04+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from AlexNG ↑Thu Jan 28, 2021 10:16 pm at Thu Jan 28, 2021 10:16 pm
>
> 
DV9 x Drillz wrote: ↑Mon Jan 18, 2021 6:32 am
is the texture coverter and model importer the same file?


Texture converter and importer are obviously different tools, but my version of the importer includes the texture converter exe file and automatically calls it to convert specific textures it needs, instead of requiring all textures to be converted beforehand.

Ahhhh i see, thanks for clarifying
## Post #64
- Username: MackMasterMimik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 24, 2021 5:56 pm
- Post datetime: 2021-03-24T22:30:17+00:00
- Post Title: Re: Dishonored 2 models and textures

Hey guys, the pak tools link is not working anymore, does anyone have the tool?
And what was it, you use the pak tool to unpack the files and then use the blender import script, and you are done? Thanks in advance!
## Post #65
- Username: Generosity
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2021 3:28 pm
- Post datetime: 2021-03-25T07:50:11+00:00
- Post Title: Re: Dishonored 2 models and textures

Join the previous request. Thank you in advance
## Post #66
- Username: MackMasterMimik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 24, 2021 5:56 pm
- Post datetime: 2021-03-27T11:31:10+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from Generosity ↑Thu Mar 25, 2021 3:50 pm at Thu Mar 25, 2021 3:50 pm
>
> 
Join the previous request. Thank you in advance

What do you mean by that? I'm new here
## Post #67
- Username: MackMasterMimik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 24, 2021 5:56 pm
- Post datetime: 2021-03-29T07:25:31+00:00
- Post Title: Re: Dishonored 2 models and textures

I figured the whole process out:

Download Quick BMS

Download the dishonored bm script, which is in this thread 

Launch the QuickBMS 4gb EXE and follow the instructions in the CMD (locate the dishonored bms script, locate the input directory [which is game_1.resource file] and then output [where you wanna unpack the game] and do the same for game_2.resources and game_3.resource)

Download blender 2.8 or 2.82 and install the io_dishonroed blender add-on (link is in this thread as well). 

In Blender>File>Import>find any .bwm file (which is a level of the game) and add it. Make sure you play around with the import settings on the right side (the quality of the import). The same process can be done with individual character models.

Done!

The only thing I'm struggling with is that I can import all textures from the "escape the dunwall tower" mission. On the other .bwm files, it only loads some textures partially. I saw that the problem is either a faulty Blender material (which is easy to fix) or the material is empty in the first place. I think this happens because it uses materials from the other .bwm files, which are not imported anymore. Does anyone have an idea?

Also, when unpacking the game files, should we unpack them in the same folder, or create a different folder for every .resource file of the game?

Cheers.
## Post #68
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2021-04-05T12:31:47+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from MackMasterMimik ↑Mon Mar 29, 2021 3:25 pm at Mon Mar 29, 2021 3:25 pm
>
> 
Also, when unpacking the game files, should we unpack them in the same folder, or create a different folder for every .resource file of the game?

All resource files should be unpacked into the same folder, or you will get missing references. I don't remember the details, but there definitely are cases where maps/models from one resource file need data from a different one.
## Post #69
- Username: aruspex66
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 14, 2021 6:21 am
- Post datetime: 2021-05-13T22:31:34+00:00
- Post Title: Re: Dishonored 2 models and textures

Hey, I stumbled upon this thread after hours of searching.
I'm trying to modify in-game values in DH2 such as maximum bullet capacity, walk speed, power durations. I love the games but they're too easy and I'd like to make it ultra hard.
For original Dishonored, a user named Tautologist released a Field Editor tool that does exactly what I need, I'm hoping to find a way to tweak the values in the same way for DH2. I've been mucking about with QuickBMS and digging for where the values for maximum bullet capacity, walk speed, power durations etc..  but haven't had any luck

Also, if anyone needs help using Tautologist's tool for DH1 I can point you in the right direction, it takes a little work to figure it out and I hate to post without 'contributing' something as well. His tool is amazing and it's breathed a lot more life into DH1 for me

EDIT: I have finally found them in the .../generated/decls folder and was able to edit the values, like mana regen delay and was able to re-import the .resources files without any errors in QuickBMS but replacing the game1.resources file with the repackaged one results in a CTD. Trying to figure out if I've done something wrong or if Arkane has some kind of protections in place that keeps edited files from loading up
## Post #70
- Username: themooingfeebas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 03, 2020 9:27 am
- Post datetime: 2021-06-28T04:45:48+00:00
- Post Title: Re: Dishonored 2 models and textures

Hey, with the most recent import tool (the one that works with blender 2.8x) I can't seem to import character models from Death of the Outsider? Dishonored 2 models and models from Death of the Outsider that aren't characters work without an issue though, so I'm pretty lost on what to do.
## Post #71
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2021-07-02T18:34:00+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from themooingfeebas ↑Mon Jun 28, 2021 12:45 pm at Mon Jun 28, 2021 12:45 pm
>
> 
I can't seem to import character models from Death of the Outsider?

I guess I need to look at that game. By pure coincidence I've just happened to buy a bigger hard drive, so fortunately I don't need to find something to delete in order to install it anymore.
## Post #72
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2021-07-03T19:42:13+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from themooingfeebas ↑Mon Jun 28, 2021 12:45 pm at Mon Jun 28, 2021 12:45 pm
>
> 
I can't seem to import character models from Death of the Outsider?

Here is a fixed version of the importer - turned out to require a one line fix for a tiny difference in file structure.

Also confirmed it still works in Blender 2.93, so the script supports both 2.8 and 2.9.
[io_scene_Dishonored2-v2_02.zip.rar](https://xentaxbackup.github.io/file/20409_io_scene_Dishonored2-v2_02.zip.rar)
## Post #73
- Username: ceephax
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 15, 2018 6:23 pm
- Post datetime: 2022-01-22T09:45:20+00:00
- Post Title: Re: Dishonored 2 models and textures

Hello guys!!
I've extracted textures with the tool by Volfin, then converted to dds and everything is perfect exept normal textures. They look like mess, anyone knows how to fix the issue?? ( When i try to resave it in Nvidia Texture tool exporter in normal format i see Opengl  normal texture, but seems the lack of info and still the tool does not save the normal opengl format. In channels i see some kind of height in bad resolution.
[terracotta_tiles_01_n.bimage7.BC5S.png](https://xentaxbackup.github.io/file/21661_terracotta_tiles_01_n.bimage7.BC5S.png)
## Post #74
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2022-01-24T15:29:36+00:00
- Post Title: Re: Dishonored 2 models and textures

Dishonored 2 doesn't use the blue channel, the Z coordinate of the normal is computed in the shader based on X and Y - see the Blender materials generated by my importer. That means the textures don't contain that data since the game doesn't need it.

Edit: to be more specific, it actually uses a more complicated parabolic normal encoding, as described in this [article](http://rgba32.blogspot.com/2011/02/improved-normal-map-distributions.html) (there is actually a reference to it in the game shader comments). The final normal is basically: 
```
normalize(vec3(n.xy, 1.001f - saturate(dot(n.xy, n.xy)))
```
## Post #75
- Username: Giebels2609
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 20, 2021 3:39 pm
- Post datetime: 2022-04-28T01:41:11+00:00
- Post Title: Re: Dishonored 2 models and textures

Hey there,

I'v been using the io_scene_Dishonored2-v2_02.zip for a day now and it used to work great but now it throws an error because of one bloody line of code I cant figure out how to fix. It's line 143 in the materials.py file.

The error message is posted bellow. Sorry for starting up an old thread again but didn't know where else to ask.

```
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\__init__.py", line 216, in execute
    result = entbuilder.build_entities(context.view_layer, context.collection, filepath)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\entities.py", line 393, in build_entities
    self.build_entity(info, entity)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\entities.py", line 356, in build_entity
    obj = self.build_object(info, entity)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\entities.py", line 323, in build_object
    obj = self.build_lwo_model(info, entity, modinfo, model)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\entities.py", line 201, in build_lwo_model
    return self.build_lwo_mesh(model, self.get_custom_materials(modinfo))
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\entities.py", line 184, in build_lwo_mesh
    obj,_ = self.build_mesh(filename, materials=mats)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\models.py", line 333, in build_mesh
    obj,info = super().build_mesh(filename, bone_map, modinfo, materials)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\models.py", line 296, in build_mesh
    self.set_object_materials(obj, materials)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\models.py", line 244, in set_object_materials
    check_object_invisible(obj)
  File "C:\Users\Kevin\AppData\Roaming\Blender Foundation\Blender\3.1\scripts\addons\io_scene_Dishonored2\materials.py", line 143, in check_object_invisible
    obj.cycles_visibility.shadow = False
AttributeError: 'Object' object has no attribute 'cycles_visibility'

location: <unknown location>:-1

```
## Post #76
- Username: Atys
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 20, 2020 1:46 am
- Post datetime: 2022-06-06T12:53:49+00:00
- Post Title: Re: Dishonored 2 models and textures

First thank you for your tools.

Someone knows how/where I could extract the entire map of a level? With streets and buildings.
## Post #77
- Username: Eikeegi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 10, 2021 11:37 am
- Post datetime: 2022-06-18T20:58:33+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from Atys ↑Mon Jun 06, 2022 8:53 pm at Mon Jun 06, 2022 8:53 pm
>
> 
First thank you for your tools.

Someone knows how/where I could extract the entire map of a level? With streets and buildings.

This thread gives you all you need  for it.  You can even get high/low chaos versions properly and fully.
## Post #78
- Username: zigguratofinanna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 09, 2022 12:31 am
- Post datetime: 2022-11-08T18:26:18+00:00
- Post Title: Re: Dishonored 2 models and textures

Sorry for the necro but does anyone know where the rune, bone charm and mana potion/Addermire solution models are located? Closest I've found is a "whale_bone_charm_01.pmodel" file in ingenerated\staticparticlemodel\models\interactive\pickups\whale_bone_charm_01 but the blender addon can't import it, and no luck for the rune or mana potion anywhere.
## Post #79
- Username: Myrmyrer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 12, 2022 10:49 pm
- Post datetime: 2022-12-12T16:13:04+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from zigguratofinanna ↑Wed Nov 09, 2022 2:26 am at Wed Nov 09, 2022 2:26 am
>
> 
Sorry for the necro but does anyone know where the rune, bone charm and mana potion/Addermire solution models are located? Closest I've found is a "whale_bone_charm_01.pmodel" file in ingenerated\staticparticlemodel\models\interactive\pickups\whale_bone_charm_01 but the blender addon can't import it, and no luck for the rune or mana potion anywhere.

Found:
Mana Potion as mana_potion_01.bmodel in \generated\model\models\interactive\pickups\potions_01\mana_potion_01.bmodel" 
Bone Charm as whale_bone_charm_01.bmodel in \generated\model\models\interactive\pickups\whale_bone_charm_01\whale_bone_charm_01.bmodel
Rune as rune_01.bmodel in \generated\model\models\interactive\pickups\rune_01\rune_01.bmodel

and was able to import successfully into blender V2.7.  If you're on windows I recommend the search tool "Everything" by voidtools, it's way better than digging through by hand or having to suffer through the windows search tool.
## Post #80
- Username: joaobarosa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 22, 2022 3:03 am
- Post datetime: 2022-12-21T19:22:00+00:00
- Post Title: Re: Dishonored 2 models and textures

Is there anyway to make this script import textures and skeleton so I can be able to export it and import it in game, to make custom models and mods?
## Post #81
- Username: MightGuy4114
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 29, 2023 8:15 am
- Post datetime: 2023-02-05T02:41:57+00:00
- Post Title: Re: Dishonored 2 models and textures

After some testing I found that map importing seems to take longer but works in 2.9 where as 3.4 imports some stuff but fails to import the map geometry.
## Post #82
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-04-30T08:57:52+00:00
- Post Title: Re: Dishonored 2 models and textures

it is possible to rebuild the clockwork Maison level in UE5 with it's mechanics ?
## Post #83
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2023-04-30T19:53:30+00:00
- Post Title: Re: Dishonored 2 models and textures

> Reply from richardphone ↑Sun Apr 30, 2023 4:57 pm at Sun Apr 30, 2023 4:57 pm
>
> 
it is possible to rebuild the clockwork Maison level in UE5 with it's mechanics ?

If you know how every single thing works inside the mansion, sure.
But I would say it's nearly impossible, the systems are very intricate in that part of the game. Lots of work was put into that
