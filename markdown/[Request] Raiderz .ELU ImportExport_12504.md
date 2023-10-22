## Post #1
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-14T19:11:47+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

I'm just wondering if anyone has a working .elu importer/exporter for the latest versions of Raiderz. I'm willing to pay for any help that anyone can give me on getting the models and animations into either blender or 3ds max.

Notes: I'm using blender 2.49b with the script from Phantom* at [http://forum.ragezone.com/f245/elu-ani- ... er-488857/](http://forum.ragezone.com/f245/elu-ani-blender-importer-488857/) and get the following error: bad version number 20499

Notes2: I'm trying to find an older client to see if I can get it working. I've found the 2012/10/22 client, but can't seem to find anything older.
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-01-15T16:51:41+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

Hi

For reversing please send >5 samples of models with animations.
## Post #3
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-15T16:58:35+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

> Reply from Szkaradek123
>
> Hi

For reversing please send >5 samples of models with animations.

Here you go - [https://mega.co.nz/#!NwNBQIZJ!zzuLXWGWH ... 1NY7d2dlXs](https://mega.co.nz/#!NwNBQIZJ!zzuLXWGWH0EvqC3-JKa1vMOL3Xnlc9Y7Z1NY7d2dlXs)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-15T21:28:04+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

edit

yeah that is the latest script, sorry about that   

is 0x5013 still the highest model version?
## Post #5
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-15T22:57:49+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

> Reply from WRS
>
> edit

yeah that is the latest script, sorry about that   

is 0x5013 still the highest model version?

How would I go about finding out? I'm a complete noob to this.
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-01-16T08:40:36+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

Hi
Here is an importer for *.elu and *.xml files. 
It requires Blender 249 and Python 26.
How import:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
- *.elu file - mesh with skinweights and skeleton
- *.xml file - for textured models
- *.ani file - for first frame of animation (pose frame)


Updated 2015-01-16:
- added materials
- support xml files for autotexturing. (don't delete or move files from original folder localization)
- fixed position of meshes (used bind matrices for transform vertex groups to bone position)
- support first frame of animation
[Blender249[RaiderzOnline][elu][xml][ani][2015-01-16].zip](https://xentaxbackup.github.io/file/8490_Blender249[RaiderzOnline][elu][xml][ani][2015-01-16].zip)
## Post #7
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-16T11:34:14+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

> Reply from Szkaradek123
>
> Hi
Here is an importer for *.elu files from samples  viewtopic.php?p=102951#p102951
It requires Blender 249 and Python 26.
How import:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select *.elu file - mesh with skinweights and skeleton

Animations and autotexturing are not supported.

Edit: It works wonderfully!
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-01-16T12:13:09+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

> Reply from Szkaradek123
>
> Hi
Here is an importer for *.elu files from samples  viewtopic.php?p=102951#p102951
It requires Blender 249 and Python 26.
How import:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select *.elu file - mesh with skinweights and skeleton

Animations and autotexturing are not supported.very well，Szkaradek123，Thank you very much for the great work , I've been really looking forward to this game, I tested the script and introduced some models, is perfect, but some npc and player models can not be imported. Really looking forward to the update script,  Szkaradek123 Thanks for the great work again
[BaiduShurufa_2015-1-16_19-41-24.jpg](https://xentaxbackup.github.io/file/8487_BaiduShurufa_2015-1-16_19-41-24.jpg)
## Post #9
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-01-17T02:11:19+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

Here we go, downloading another game. 

Thanks Szkaradek123, your scripts are always exceptional.
## Post #10
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-17T17:51:09+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

I don't know if anyone else is having this problem, but on some of the models such as the "Wolf Boss" there are model errors when applying the first frame animation like in the attached photo.
[AnimationError.jpg](https://xentaxbackup.github.io/file/8495_AnimationError.jpg)
## Post #11
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-01-17T18:06:05+00:00
- Post Title: [Request] Raiderz .ELU Import/Export

srry about noobs question :

how to unpack xxx.mrf File?? or can just only work for older version rip file??
