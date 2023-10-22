## Post #1
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-25T16:48:10+00:00
- Post Title: Shadows - Heretic Kingdoms

Model viewer here - [viewtopic.php?f=16&t=12132](http://forum.xentax.com/viewtopic.php?f=16&t=12132)

Import models into 3DS Max:
1. Download tools:
[Ogre 3d command line tools](https://www.dropbox.com/s/svx5bbx9e433vc0/%5B2014-11-25%5D%20ogre3d%20tools.7z?dl=0)
[3d Models, animation importer - FatImporter](http://forum.xentax.com/viewtopic.php?f=33&t=7901&hilit=torchlight)
2. Degrade mesh version to 1.4 with command: OgreMeshUpgrader.exe -V 1.4 <MESHFILE>
3. Import mesh into 3ds max using Fat Importer (Torchlight section).

Know issues: I don't why, but UV map broken into 3ds max, if anyone have method to fix it, please say about it ...

P.S. Anyone have importers for Ogre3d xml to 3ds max or to .md5mesh / .smd  with animation support ?

thx ...
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-20T07:47:24+00:00
- Post Title: Shadows - Heretic Kingdoms

Here is another importer for models and animations from this game.
It requires Blender249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select a mesh file for importing textured models. 
4.press alt+p and select skeleton file for importing armature.
If skeleton file has animations than importer extract all animations in new folder with name "animfiles".
5.press alt+p and select in animation folder anim file for importing animation
[Blender249[ShadowHeretic][PC][mesh][skeleton][2014-12-20].zip](https://xentaxbackup.github.io/file/8306_Blender249[ShadowHeretic][PC][mesh][skeleton][2014-12-20].zip)
## Post #3
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-20T09:40:11+00:00
- Post Title: Shadows - Heretic Kingdoms

> Reply from Szkaradek123
>
> Here is another importer for models and animations from this game.
It requires Blender249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select a mesh file for importing textured models. 
4.press alt+p and select skeleton file for importing armature.
If skeleton file has animations than importer extract all animations in new folder with name "animfiles".
5.press alt+p and select in animation folder anim file for importing animation
Very good, thank you, my friend
