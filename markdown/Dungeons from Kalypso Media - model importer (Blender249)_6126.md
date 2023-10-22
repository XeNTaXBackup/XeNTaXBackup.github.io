## Post #1
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-23T21:27:14+00:00
- Post Title: Dungeons from Kalypso Media - model importer (Blender249)

The contents of this post was deleted because of possible forum rules violation.


Updated 2014-12-19:

After 3 years i find a way to import animations from skeleton files.
Here is importer for  models and animations from this game.
It requires Blender249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select a mesh file for importing textured models. 
Imported mesh' vertexgroups have no names, but ID of bone.
4.press alt+p and select skeleton file.
If skeleton file has animations than importer extract all animations in new folder with name "animfiles".
5.press alt+p and select in animation folder anim file for importing animation
[Dungeons.zip](https://xentaxbackup.github.io/file/8307_Dungeons.zip)
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-23T22:31:02+00:00
- Post Title: Dungeons from Kalypso Media - model importer (Blender249)

You are a true blender programer man. Wath you think abouth make one importer for Rohan (Only meshes), this its a very hard job for all the programers here.
## Post #3
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2011-02-25T20:13:01+00:00
- Post Title: Dungeons from Kalypso Media - model importer (Blender249)

Great!!!
Nice Models!!! Is it possible to import animation?
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-25T21:22:47+00:00
- Post Title: Dungeons from Kalypso Media - model importer (Blender249)

Animations are in .skeleton files. Not in all. Some have only position of bones . Some bones+animations.
Script import animations, but rotation and position of 'root bones' is still to fixed . I don't know how do it. So animations are 'ugly'.
## Post #5
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-03-13T16:47:33+00:00
- Post Title: Dungeons from Kalypso Media - model importer (Blender249)

Where are located the .mesh files?
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-13T18:35:42+00:00
- Post Title: Dungeons from Kalypso Media - model importer (Blender249)

...\data\optimized\optimized.dat - simple zip archive.
