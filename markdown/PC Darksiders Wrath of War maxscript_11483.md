## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-05-04T10:02:41+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

Hi guys! Here's maxscript to import Darksiders: Wrath of War (2010) PC models with bones+weights (3ds max 2009-2012)

P.S. Report bugs, maybe some models will cause errors - I guess, static ones, since generally I wrote script for characters (but if someone will need static objects/levels much I'll fix this)

EDIT: Updated script

[](http://piccy.info/view3/6332882/8385e70a650885f580a751ad085dfb42/1200/)[](http://i.piccy.info/a3c/2014-05-04-10-01/i9-6332882/519x800-r)
[](http://piccy.info/view3/6340528/51f2a95d6ff42141258347a2c57d76a1/1200/)[](http://i.piccy.info/a3c/2014-05-05-15-27/i9-6340528/744x574-r)
[Darksiders.7z](https://xentaxbackup.github.io/file/7303_Darksiders.7z)
## Post #2
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2014-05-04T10:48:55+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

Good news! One question, how do You extract Darksiders1 archives?
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-05-05T06:43:51+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

Run offzip on them, do it twice. First time on .oppc file with model you want (like abaddon_dragon.oppc), and second time on resulted .bod file (you will have .dat models).
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2014-05-05T10:09:29+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

It seems the time to re-install my copy of darksiders....hehe. Awesome work! 
I hope to have some time to test your script. Thank you so much!

PS: I know that there already exists an old noesis plugin for darkiders 2 made by Finale, but it doesn't support uv maps , bones crash with some characters.So actually the only way to obtain the uv mapped model is to convert manually whit the shakotay2 tool.
I would like to ask u if u have time to take a look even at darksiders2  game.
Let me know if u need some sample files.
## Post #5
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2014-05-05T13:54:38+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Run offzip on them, do it twice. First time on .oppc file with model you want (like abaddon_dragon.oppc), and second time on resulted .bod file (you will have .dat models).
many thanks!
## Post #6
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-05-05T14:54:23+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

wow,so may years,finally....
thank u,very mach
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-05-05T15:09:02+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from Ares722
>
> It seems the time to re-install my copy of darksiders....hehe. Awesome work! 
I hope to have some time to test your script. Thank you so much!

PS: I know that there already exists an old noesis plugin for darkiders 2 made by Finale, but it doesn't support uv maps , bones crash with some characters.So actually the only way to obtain the uv mapped model is to convert manually whit the shakotay2 tool.
I would like to ask u if u have time to take a look even at darksiders2  game.
Let me know if u need some sample files.

Script for Darksider 2 models was ready before script for first game, since there is a nice file extractor. I'm going to release it soon

[](http://piccy.info/view3/6337337/79585aecf04067d64037367c671e4ec2/1200/)[](http://i.piccy.info/a3c/2014-05-05-15-08/i9-6337337/744x574-r)
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-05-09T20:32:41+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Run offzip on them, do it twice. First time on .oppc file with model you want (like abaddon_dragon.oppc), and second time on resulted .bod file (you will have .dat models).i really wanna extract models. can you explain this more detail? thanks
## Post #9
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-06-01T15:51:14+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

thanks，I waiting for this few years....
## Post #10
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2014-06-05T02:48:04+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Run offzip on them, do it twice. First time on .oppc file with model you want (like abaddon_dragon.oppc), and second time on resulted .bod file (you will have .dat models).

There's a problem, when I use offzip to extract a .oppc file, it bring me a .dat file directly(not a .bod), and it can't be imported to MAX with the script(freeze or occurs error).
what's wrong with this?
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-06-05T19:03:33+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

Are you using command like this for offzip?

```
offzip -a filename.oppc extract 0
```
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-06-05T19:20:14+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Are you using command like this for offzip?
Code: Select alloffzip -a filename.oppc extract 0i'm getting .bod files at first place, but can't unpack them.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-06-06T05:53:29+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

Run same command on .bod file and you will get .dat models

```
offzip -a filename.bod extract 0
```
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-06-06T06:21:01+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Run same command on .bod file and you will get .dat models
Code: Select alloffzip -a filename.bod extract 0i did it, it doesn't work. or maybe it work not for all .oppc files?

edit: okay, it actually does work for Azrael.oppc.
## Post #15
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2014-06-10T01:16:27+00:00
- Post Title: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Are you using command like this for offzip?
Code: Select alloffzip -a filename.oppc extract 0

Finally, I down another offzip from luigi's HP, and it solved the problem. 
And, maybe there's something wrong during unpacking with offzip, not of all .dat file can be imported to MAX, just like Abaddon the final boss, and War's berserker mode, it's a pity but still thanks a lot.
and now I'm going to rip textures form the gameXD
## Post #16
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2014-12-02T07:50:04+00:00
- Post Title: Re: PC Darksiders: Wrath of War maxscript

> Reply from zaramot
>
> Are you using command like this for offzip?
Code: Select alloffzip -a filename.oppc extract 0

I used it like this "offzip.exe -a uriel.oppc uriel 0"

And all i get is "00006004.dat" file. Please explain it for complete morons to understand. From the very start and to the very end.
## Post #17
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-03T13:31:33+00:00
- Post Title: Re: PC Darksiders: Wrath of War maxscript

Hi

Here is extractor and skeleton importer for PC Darksiders models for Blender users.
It requires Blender version 249 and Python 26.

It supports:
-oppc - archives. Some files are not supported
-meshpack - select this file for unpacking meshes (*.mesh)
-mesh - skinned mesh with textures
-o3d - skeleton (armature)

Steps:
1. press alt+p and select oppc archive for unpacking archive. It creates new folder.
2. press alt+p and select in new folder meshpack file.
3. press alt+p and select in new folder mesh file - this step repeat for all meshes
4. press alt+p and select o3d file for skeleton

I use file research done by zaramot and get info from [viewtopic.php?f=10&t=9172](http://forum.xentax.com/viewtopic.php?f=10&t=9172).
[Blender249[Darksiders][PC][2014-12-03].zip](https://xentaxbackup.github.io/file/8187_Blender249[Darksiders][PC][2014-12-03].zip)
## Post #18
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-12-03T14:09:31+00:00
- Post Title: Re: PC Darksiders: Wrath of War maxscript

zaramot has some scripts for the two? and you've arranged scripts demon soul? and you can pass the script to other people?
## Post #19
- Username: sandman2009
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 19, 2012 8:43 pm
- Post datetime: 2015-03-09T11:41:04+00:00
- Post Title: Re: PC Darksiders: Wrath of War maxscript

thanks，I waiting for this few years....
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-09-26T19:39:37+00:00
- Post Title: Re: PC Darksiders: Wrath of War maxscript

> Reply from Szkaradek123
>
> Hi

Here is extractor and skeleton importer for PC Darksiders models for Blender users.
It requires Blender version 249 and Python 26.

It supports:
-oppc - archives. Some files are not supported
-meshpack - select this file for unpacking meshes (*.mesh)
-mesh - skinned mesh with textures
-o3d - skeleton (armature)

Steps:
1. press alt+p and select oppc archive for unpacking archive. It creates new folder.
2. press alt+p and select in new folder meshpack file.
3. press alt+p and select in new folder mesh file - this step repeat for all meshes
4. press alt+p and select o3d file for skeleton

I use file research done by zaramot and get info from viewtopic.php?f=10&t=9172.I appreciate for your work and wonder if you able to look at these oppc-files which are gives me an error every time I'm trying to open them in blender.

pmed you with files.

p.s.: according to the names these are characters.
## Post #21
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-10-01T18:25:39+00:00
- Post Title: Re: PC Darksiders: Wrath of War maxscript

sorry I can use it to extract models and animzioni of darksiders 2?
