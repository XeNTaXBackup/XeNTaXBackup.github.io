## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T10:21:09+00:00
- Post Title: men of war pc .ply models

Can someone of you pros add weight support into this script everything else works great?
Here's video:
[https://www.youtube.com/watch?v=sezVg2ZJusc](https://www.youtube.com/watch?v=sezVg2ZJusc)
Here's script:
[https://github.com/bjornmp/Men-of-War-Blender-Importer](https://github.com/bjornmp/Men-of-War-Blender-Importer)

it seems like this script was abandoned.
[ger-mgun.7z](https://xentaxbackup.github.io/file/11310_ger-mgun.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-21T14:13:11+00:00
- Post Title: men of war pc .ply models

i know you want someone to add weight support to the Blender script but i just had to run the skin.ply through Hex2obj for kicks  



skin_ply.png (46.98 KiB) Viewed 232 times



early last year i was looking for a way to open these models and found nothing
this is a very easy format for anyone to learn the basics of Hex2obj with
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T16:54:01+00:00
- Post Title: men of war pc .ply models

nice one, AceWell. the models are not that good, I know  though since I playing this old strategy game I wanted to play with it models
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-21T17:55:02+00:00
- Post Title: men of war pc .ply models

did you get the script to run?
In blender 2.73 neither installing from file (zip) nor copying the io_scene_mdl folder into the addons folder worked.

I can identify/install any other script by its name from

```
    "name": "Web3D X3D/VRML2 format",
```
for example

but not this one from Mr. Paz.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T18:40:14+00:00
- Post Title: men of war pc .ply models

> Reply from shakotay2
>
> did you get the script to run?
In blender 2.73 neither installing from file (zip) nor copying the io_scene_mdl folder into the addons folder worked.I had this issue too. Don't recall how I solved it. Luckily I have a habit to always do a readme file so here it is:

to install:

- copy folder 'io_scene_mdl' to 'C:\Program Files (x86)\Blender Foundation\Blender\2.77\scripts\addons\';
- in Blender open 'User Preferences';
- press 'Install from File' and choose '__init__.py';
- done.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-21T19:06:54+00:00
- Post Title: men of war pc .ply models

> Reply from Tosyk
>
> 
to install:

- copy folder 'io_scene_mdl' to 'C:\Program Files (x86)\Blender Foundation\Blender\2.77\scripts\addons\';
- in Blender open 'User Preferences';
- press 'Install from File' and choose '__init__.py';
- done.sadly that doesn't work for me (Win7).
(I was thinking it might be a matter of the UTF-8 encoding of the mdl scripts but that doesn't make sense because
By default, Python source files are treated as encoded in UTF-8)

But all the other scripts installed are ANSI. Sometimes I really hate blender.
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T19:13:54+00:00
- Post Title: men of war pc .ply models

> Reply from shakotay2
>
> sadly that doesn't work for me (Win7).it should appear in "Testing" in "Supported Level" btw
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-21T19:35:25+00:00
- Post Title: men of war pc .ply models

> Reply from Tosyk
>
> shakotay2 wrote:sadly that doesn't work for me (Win7).it should appear in "Testing" in "Supported Level" btwwell, that's an essential info, you know?  

Anyway, as import/export options I've Men of War  (.def) only.

This may be due to this strange icon (know what it means?):



blender_install_script_problem.jpg (26.99 KiB) Viewed 208 times



(I should have known this that those blender guys/developers are totally insane, hahaha.
But I've to confess that I don't use blender too often, so it's my fault - confirmed)
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T19:40:10+00:00
- Post Title: men of war pc .ply models

> Reply from shakotay2
>
> Anyway, as import/export options I've Men of War  (.def) only.

This may be due to this strange icon (know what it means?):
blender_install_script_problem.jpgthis is it, .def - it's file for ingame entity. you should load .def file and all the rest files will load automatically.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-21T19:47:40+00:00
- Post Title: men of war pc .ply models

would be nice if it did, but it doesn't for some reason.
It seems to read data but it doesn't display anything:

```
Number of triangles: 572
Material info: 0xf14
Material name length: 0x8
Material file: b'ammo.mtl'
Found entry b'MESH' at 0x129
Number of triangles: 2090
Material info: 0xf14
Material name length: 0x8
Material file: b'body.mtl'
Found entry b'MESH' at 0x162
Number of triangles: 374
Material info: 0xd14
<class 'Exception'>
Building Blender scene
Finished building Blender scene
MOWDEF_NODE_ROOT
  MOWDEF_NODE_GAME_ENTITY
    MOWDEF_NODE_EXTENSION
    MOWDEF_NODE_TAG
```
Maybe it's due to this <class 'Exception'>?

(Guess it works for you with ger-mgun.def, does it?)

btw: this ger-mgun.mdl contains ASCII data of a skeleton
Also did you notice that in the youtube video the import entry is named Men of War (.mdl)?

I'm on blender 2.75, this should not be an issue, should it?
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T20:14:59+00:00
- Post Title: men of war pc .ply models

unfortunately script doesn't load mgunner but it does load older (or just simplier?) models
[chkz_kv_85_1943.7z](https://xentaxbackup.github.io/file/11325_chkz_kv_85_1943.7z)
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T20:15:18+00:00
- Post Title: men of war pc .ply models

> Reply from Tosyk
>
> unfortunately script doesn't load mgunner but it does load older (or just simplier?) modelsand
[machine_gunner_male_eng_outfit.7z](https://xentaxbackup.github.io/file/11326_machine_gunner_male_eng_outfit.7z)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-21T20:41:10+00:00
- Post Title: men of war pc .ply models

okay, got them loaded, plus we've a skeleton here.

23 bones only ? For me it looks like it doesn't have (all) fingers - so dunno if it's worth dealing with it.
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T20:46:30+00:00
- Post Title: men of war pc .ply models

> Reply from shakotay2
>
> okay, got them loaded, plus we've a skeleton here.

23 bones only ? For me it looks like it doesn't have (all) fingers - so dunno if it's worth dealing with it.
true, it may look crappy since it's an old strategy game but I'd like play with the original models since I'm a huge fan of the series. plus mgunner-guy has a detailed texture, I suppose he is from cutscenes.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-21T21:17:34+00:00
- Post Title: men of war pc .ply models

you could check for weights (in FVF block?) and boneids. Weights are in the range of 0.0 to 1.0, sum of weights (for 4 boneids in most cases) is 1.0.
Boneids from 0 to 22.

For machine_gunner_male_eng_outfit (FVFsize=40) at FVF offset 20 it looks like normals (sum of squares = 1.0).
There might be boneIDs at FVF offset 16 (four bytes, maximum 2 ids, rest 0), just a wild guess - I'll check that later.

(I've planned a weights logging feature for hex2obj since ages (or less  ) but it  won't come too soon.)
## Post #16
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-21T22:37:00+00:00
- Post Title: Re: men of war pc .ply models

if it was that easy I will not asked for help at the first place. I'm an artist, I can draw things and even try to examine formats but it's hard for me to dig into engineer stuff 
however thanks for your help shak
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-22T20:38:09+00:00
- Post Title: Re: men of war pc .ply models

> Reply from Tosyk
>
> if it was that easyI didn't mean it to be easy - what I meant is (if noone cares) that it would be a good idea to start with searching for all those infos you (or I) can get easily.

> I'm an artist, I can draw things and even try to examine formats but it's hard for me to dig into engineer stuff 
>
> however thanks for your help shakAs you may know (or not) it's my intention to give people who can't code means/tools
to help themselves. (Sooner or later I hope to provide a solution for skeletons and skinning data.)

For your example machine_gunner_male_eng_outfit it's indeed a little bit confusing:
from the bone list at the beginning of the file skin.ply it looks as if it had 24 bones.

So the following list makes sense (assumed we've one weight for two bones), maximum ID: 0x18=24
weight .. 4 boneIDs
1.000000 18000000 
1.000000 18000000 
1.000000 18000000 
1.000000 0C000000 
1.000000 0C000000 
1.000000 0C000000 
0.600000 0C0D0000 
0.500000 0C0D0000 
0.710000 0D0C0000 
0.710000 0D0C0000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
0.710000 0D0C0000 
1.000000 0D000000 
0.710000 0D0C0000 
0.710000 0D0C0000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0D000000 
1.000000 0E000000 
[...]
0.727961 0B0A0000 
0.647153 0B0A0000 
1.000000 09000000 
0.574509 09180000 
0.530880 09180000 
0.679686 09180000 
0.938692 09180000 
0.952961 09180000 
0.914358 09180000 
0.746017 09180000 
0.530865 09180000 
0.680168 05010000 
0.558641 05010000 
[...]
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 09000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 
1.000000 07000000 

Problem is that there's 36 bones (created by the script from Mr. Paz) in the following picture



skel-machine_gunner_male_eng_outfit.jpg (43.7 KiB) Viewed 130 times


and even 42 "bones" in eng-mgun.mdl.

So this is not a suiting sample for learning the basics.

I could think of building a simplified skeleton using the matrices from the mdl file and these bones:

```
 foot1l
   foot2l
   foot3l

 foot1r
   foot2r
   foot3r

8 ik_leftright	
 9 ik_updown
 10 clavicle_left
 hand1l
 hand2l
 
hand_rot1l
   palm1l 
    palm2l 
     palm3l

17 clavicle_right
 hand1r
 hand2r

 hand_rot1r
   palm1r
    palm2r
     palm3r

24 headMESH
```
but it's a tedious task.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-29T18:47:27+00:00
- Post Title: Re: men of war pc .ply models

well, funny things to come:
I built a reduced skeleton manually and it looked a little bit weird.
I thought I might have misunderstood the sense/order of the ik_ bones and googled for it.

Bang, found this:
[http://www.moddb.com/tutorials/export-h ... max-to-mow](http://www.moddb.com/tutorials/export-human-models-from-3ds-max-to-mow)
[http://www.moddb.com/groups/gem-2-edito ... ls-in-game](http://www.moddb.com/groups/gem-2-editor-fan-club/downloads/plugin-for-export-models-in-game)

the latter containing gb_com.max, a 3dsmax2009 project file. Skinning works for the hands only, strangely.

If you compare the select from scene window in that project with the picture it seems I wasn't too wrong, misordered the head only
(having 24 bones only, of course).



MoW_skel.JPG (60.58 KiB) Viewed 112 times

(I should have compared to the skeleton hierarchy from Mr. Paz in my previous post.   )

Next step is to reduce the skeleton of the project (see right side of pic) to 24 bones to see whether it works better than mine (guess the matrices I used need some reversing).
## Post #19
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-07-30T05:54:19+00:00
- Post Title: Re: men of war pc .ply models

so could it be some kind of a multiplier in mr. paz script which is multiplies similar named bones, like palm or foot and gives them an index?

nice finding btw — you decided to go on the reverse and looked into the exporter
## Post #20
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2017-04-12T18:37:49+00:00
- Post Title: Re: men of war pc .ply models

3D Object Converter 6.50 open all .ply model files
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-13T11:18:58+00:00
- Post Title: Re: men of war pc .ply models

> Reply from medwed
>
> 3D Object Converter 6.50 open all .ply model filesdoes it hadle the bones as well?
## Post #22
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2017-04-13T13:40:13+00:00
- Post Title: Re: men of war pc .ply models

> Reply from Tosyk
>
> medwed wrote:3D Object Converter 6.50 open all .ply model files does it hadle the bones as well?

No
