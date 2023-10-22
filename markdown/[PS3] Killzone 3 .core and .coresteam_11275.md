## Post #1
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2014-03-02T17:21:48+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

Hi. I'm working on Killzone 3 game but still finding weapon files for development and study. I don't know how to convert these files to readable files.
I need someone help me how to export model files from the game.

sample files :
[https://drive.google.com/folderview?id= ... sp=sharing](https://drive.google.com/folderview?id=0Bx4rRNAZOeSYandzcEdhQ29YbVE&usp=sharing)
[3-3-2014 12-20-40 AM.jpg](https://xentaxbackup.github.io/file/7060_3-3-2014 12-20-40 AM.jpg)
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-03-02T20:35:28+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

core files contains 3d models and textures in low res, corestream contains textures in 1024 resolution

the models maybe are compressed, I analized the files in this thread but there is no response.

[viewtopic.php?f=16&t=10990](http://forum.xentax.com/viewtopic.php?f=16&t=10990)

character 3d models files looks flat , map objets looks like "elongated"
## Post #3
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2014-03-03T18:48:15+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

Yeah I saw your post. Still no luck to get the model from the file. I'm trying.
## Post #4
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2014-03-16T13:04:51+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

> Reply from luxox18
>
> core files contains 3d models and textures in low res, corestream contains textures in 1024 resolution

the models maybe are compressed, I analized the files in this thread but there is no response.

viewtopic.php?f=16&t=10990

character 3d models files looks flat , map objets looks like "elongated"

 sounds like perspective issue. if you can get those models into an .obj format I know a program used to correct perspective issues in 3D meshes that was developed, oddly enough, to fix mesh rips for ps2 scene ripped models.
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-03-16T20:12:05+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

isn't perspective problem, is vertex problem
## Post #6
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2014-03-17T01:30:39+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

> Reply from luxox18
>
> isn't perspective problem, is vertex problem

 We are talking about the same thing and may not know it. pcsx2 used to have a way to rip 3d models by taking ,in essance, a 3d snapshot. you'd get the entire scene you saw on your screen if you had the right plugins to use the 3d snapshot feature. why pcsx ever took this out is beyond me. but the problem was two fold. 1. .obj file, when imported into 3d max or the like was flat as a pancake 2. while there was vertex data for volume that could be fixed by painstakingly using the scale tool to inflate the model often time the model might have a big head when looked at from on perspective or it might look very short when looked at from a different perspective when in modeling program.

 the first issues was caused because that's of a barrier that is formed when renedering out the game using that particular emulator,unlike say dolphin which rendered the scene directly and thus made most 3d scene grabbing a less thankless job. but the other second problem was harder to counter because it had to do with perspective issues that the renders presented. models looking away from the camera were specailly elongated as were parts of the scenery.  someone made a tool for the .obj files that I've been using for ref modeling now for some months that not only could unflatten the models but also fix the perspective issues that made the models have odd proprtions and elongations. so it's possible that something in that ps3 title isn't too unlike the ps2 titles of yore and that when extracting,even without an emulator, the models have the same issues as  if you had taken a 3d snapshot and perhapse this program I've been talking about can make the models work well but they have to be in .obj format or the program won't work.

 maybe you right and maybe I am barking up the wrong tree but I honestly think it's at least worth considering that this could fix the models once extracted.
## Post #7
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-03-17T02:47:52+00:00
- Post Title: [PS3] Killzone 3 .core and .coresteam

models from pcsx2 contains all vertex in correct perspective and is very easy to rescale but the vertex from killzone looks like a 2d object .... are the same that uv map, you can rescale the mesh but the vertex don't have the order for form a 3d object.
