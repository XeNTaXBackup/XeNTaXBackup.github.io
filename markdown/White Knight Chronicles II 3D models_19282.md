## Post #1
- Username: MinimalSight
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 18, 2018 10:47 pm
- Post datetime: 2019-01-08T12:13:20+00:00
- Post Title: White Knight Chronicles II 3D models

Hello!

I've been trying to extract models from the PS3 game 'White Knight Chronicles II', but I have no idea how to convert/open the .p3 formats (.p3mmg , .p3msk , .p3msh and .p3mms) that I assume contain the 3D model data. (Was able to get to them and the textures thanks to Chrrox' thread here  : [viewtopic.php?f=10&t=5037&hilit=white+knight+chronicles](http://forum.xentax.com/viewtopic.php?f=10&t=5037&hilit=white+knight+chronicles) )
Apparently it's a format the game 'Ni No Kuni' also uses but I couldn't find anything to extract the models from this game either.
Tried to use HextoObj and ModelResearcher for this but hex reading/editing is quite difficult for me  

Here are the files I'm trying to figure out currently (I hope it's allowed to share these)

Any help is appreciated!
( sorry if I posted this in the wrong section, first time posting on this forum! )
[WKCSamplefiles.zip](https://xentaxbackup.github.io/file/15432_WKCSamplefiles.zip)
## Post #2
- Username: KosKr19
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 03, 2020 5:28 am
- Post datetime: 2023-05-24T21:49:38+00:00
- Post Title: White Knight Chronicles II 3D models

Man I've resorted to ninja rippering the Rpcs3 game I would have to find out how to patch the game to the latest version
so I can get my old GR 30 character.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-28T18:21:32+00:00
- Post Title: White Knight Chronicles II 3D models

Looks like something but I dunno what:
.



WKC_II.png (26.76 KiB) Viewed 104 times


(Maybe simply a misinterpretation of data?)
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-05-28T20:25:56+00:00
- Post Title: White Knight Chronicles II 3D models

did not check the model, only the skeleton



a001.p3msk.png (60.52 KiB) Viewed 94 times



*offtopic
heh, I noticed that I forgot to add reading the name as a string before the first null byte (in SkelFinder). and you also can to add (as in this file) reading lines by indentation

EDIT:

> Reply from shakotay2 ↑Mon May 29, 2023 2:21 am at Mon May 29, 2023 2:21 am
>
> 
Looks like something but I dunno what:
yes , something strange
bigE,short,stride 12
subMeshes:

```
[6976, 1240]
[32176, 1240]
[57312, 1246]
[82464, 692]
[96688, 1239]
[121872, 1240]
[147056, 1239]
[171952, 190]
[176144, 1238]
[201296, 1239]
[226480, 1240]
[251664, 1239]
[276848, 1238]
[301984, 1246]
[327136, 620]
[339648, 225]
[344544, 1240]
[369728, 1239]
[394912, 1239]
[419792, 97]

```
## Post #5
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-31T08:28:35+00:00
- Post Title: White Knight Chronicles II 3D models

I got this but I don't know if it is correct(1st mesh):



a001_1st mesh.jpg (85.68 KiB) Viewed 49 times
