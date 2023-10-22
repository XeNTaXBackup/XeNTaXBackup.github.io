## Post #1
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-03-21T10:25:23+00:00
- Post Title: Anno 2070 models

first, I can get models from "Anno2070" by [viewtopic.php?f=10&t=7641&p=102989&hilit=rdm#p102989](http://forum.xentax.com/viewtopic.php?f=10&t=7641&p=102989&hilit=rdm#p102989),very great and easy!!
but, every models with anim can't be converted, I uploaded some sample files, hope get some help,thanks very much!!

sample files:
[https://mega.co.nz/#!INRShZIK!K4nc5CCmN ... F2gtwidBLw](https://mega.co.nz/#!INRShZIK!K4nc5CCmN-9waRBM4T4OmnZOkuW0dG91jF2gtwidBLw)
[https://mega.co.nz/#!8AomCY4B!KLmpvTk3U ... prHlPEXge8](https://mega.co.nz/#!8AomCY4B!KLmpvTk3UGBaT314ZRVf9z7JoRa-bzTORprHlPEXge8)
[bakery_ecos.jpg](https://xentaxbackup.github.io/file/8851_bakery_ecos.jpg)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-21T20:30:02+00:00
- Post Title: Anno 2070 models

> Reply from amzerof6
>
> but, every models with anim can't be converted, I uploaded some sample files, hope get some help,thanks very much!!need the static models or the anims?
Your uploads contain models with a vertex stride of 28, some with 24.
Seem to use tristripped faces but something is wrong. Thought of a bug in the algo hex2obj is using but with Noesis it's similar:



anti_aircraft_site_ecos_transport_lod0.rdm.JPG (195.42 KiB) Viewed 493 times


hmm, that's strange. When loading the obj export from Noesis into blender it looks better (most right pic).

edit: well, sometimes it's NOT tristrips.
## Post #3
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-03-22T15:51:51+00:00
- Post Title: Anno 2070 models

thank U shakotay2  for your try,that so weird
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-03-25T13:14:26+00:00
- Post Title: Anno 2070 models

Hi
Here is a script for import models and animations from this game.
It requires to install Blender 249 and Python 2.6.6.
How to use:
1. double click Blender249.blend
2. in Blender Text Window press alt+p and select:
 - cfg file - for textured and rigged meshes
 - rdm - for not textured meshes and for animations (if armature object exists). 

If "select cfg file" get nothing, import rdm file and apply textures manual.

Vehicles are not supported yet.
[Blender249[Anno2070][PC][cfg][rdm][2015-03-25].zip](https://xentaxbackup.github.io/file/8884_Blender249[Anno2070][PC][cfg][rdm][2015-03-25].zip)
## Post #5
- Username: Vizor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 08, 2016 10:16 am
- Post datetime: 2016-01-12T10:47:59+00:00
- Post Title: Anno 2070 models

Hello! I saw this post, and tried as Szkaradek123 said with the blender included in the download. However, I got a syntax error when I pressed alt+p. It said I was missing the parentheses in the call to 'print' at line 121. Am I doing anything incorrectly? Can someone help?
## Post #6
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2016-01-29T20:31:13+00:00
- Post Title: Anno 2070 models

[viewtopic.php?f=10&t=7641&p=102989&hilit=rdm#p102989](http://forum.xentax.com/viewtopic.php?f=10&t=7641&p=102989&hilit=rdm#p102989)

Back in time when I used the codes from the link that amzerof6 points, i converted various objects in OBJ. using 010 Editor, not all of them could be extracted for some reason. However when I try to use now in 2016 give me always a error no matter how much i correct the directory, so i'm going to assume the codes are... outdated??

I don't know how to work with textures, i'm now trying Szkaradek123 Blender (extractor?) but something between the line 121 doesn't add up, what can i do??
## Post #7
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2016-02-03T01:19:46+00:00
- Post Title: Anno 2070 models

*bump*

is the topic dead?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-03T12:15:39+00:00
- Post Title: Anno 2070 models

dunno. 

(Sry, I don't use/don't support 010 Editor because it's not free, afaik.)

Concerning Mariusz' script: guess the people who could answer are a little bit tired of telling how his scripts work.
(blender version, python version: it was explained in this forums 500 times, I feel.  )

> Reply from Valkorion
>
> i'm now trying Szkaradek123 Blender (extractor?) but something between the line 121 doesn't add up, what can i do??  is this a problem with textures only?

if 'no': 
-- did you ever manage to use one of his blender python scripts (no matter for which model format)? 

---- If 'yes': upload the model sample which causes the problem.
---- If 'no': learn how to use Mariusz' scripts

(Since you seem to have the same problem as Vizor I guess the last advice will solve your problem.)
## Post #9
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2016-02-03T17:51:50+00:00
- Post Title: Anno 2070 models

> is this a problem with textures only?

It just happens that when I click ALT + P simply pops up an error on line 121 just like Vizor. Nothing else happens.

> -- did you ever manage to use one of his blender python scripts (no matter for which model format)?

Actually i'm new at Xentax   ,no  i don't know how to code either, just trying to find an easy way to extract ANNO models to use them in Cities Skylines, so this is my first try, if this is what you mean.
By the way i am using Blender2.73, is Blender 249 a version conflict? Also using Python 3.5.1.

> ...I guess the last advice will solve your problem.)

hmm could you point it?   Unless i have accidently realized the problem above.

P.S: Could Noesis work? If so what kind of plugin i need? (if there is any)



EDIT: OMG, suddenly i realized everything in the universe, the versions were the conflict, thank you overlords of wisdom.   
Looking for ANNO 2205 metropolitan buildings, thanks in advance.
## Post #10
- Username: Judekw
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 07, 2016 12:10 am
- Post datetime: 2016-03-06T17:24:12+00:00
- Post Title: Anno 2070 models

Hey guys,

this is Julian, creator of the Judekwmod for Anno 2070 plus Addon ([http://forums-de.ubi.com/showthread.php ... ost2076805](http://forums-de.ubi.com/showthread.php/120067-Judekwmod?p=2076805&viewfull=1#post2076805))

Me and my friends over at maug-projekt.de have been struggling for ages to find ways to convert the .rdm files. But since none of us is a pro when it comes to 3d-models, we were not able to find a way how to do. So thanks a lot to you guys over here; now we're able to convert the .rdm files to .obj.

What is more interesting for us though is how to get that .obj files back into .rdm. We have found ways to convert the .gr2 files from earlier Anno games into .obj, so it is our goal to implement some of the earlier Anno's buildings into 2070 and of course to create our own models for the game.

Since some of you were able to code a converter for .rdm files, I'm asking you for help: Is there a way to convert .obj back into .rdm? This is one of the last frontiers we're facing but it would allow so much possibilities for our mods.

Any help is highly appreciated. Thanks in advance!

With kind regards
Julian aka Judekw
## Post #11
- Username: Zok93
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 30, 2018 11:24 am
- Post datetime: 2018-07-30T10:18:22+00:00
- Post Title: Anno 2070 models

> Reply from Szkaradek123
>
> Hi
Here is a script for import models and animations from this game.
It requires to install Blender 249 and Python 2.6.6.
How to use:
1. double click Blender249.blend
2. in Blender Text Window press alt+p and select:
 - cfg file - for textured and rigged meshes
 - rdm - for not textured meshes and for animations (if armature object exists). 

If "select cfg file" get nothing, import rdm file and apply textures manual.

Vehicles are not supported yet.
找不到pby文件，可以上传一下吗~
