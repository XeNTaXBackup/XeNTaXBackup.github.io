## Post #1
- Username: sliverbaer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 07, 2022 2:37 am
- Post datetime: 2022-04-11T21:49:43+00:00
- Post Title: Rebel Galaxy Outlaw Ships for 3D Printing

Howdy,

Curious if anyone has or knows of Rebel Galaxy Outlaw ships extracted from game?  Specifically wanting to 3D print some of the ships.

I saw this thread but not sure if it is related to 3D files.
[viewtopic.php?f=10&t=20958&p=179305&hil ... xy#p179305](https://forum.xentax.com/viewtopic.php?f=10&t=20958&p=179305&hilit=rebel+galaxy#p179305)

I attempted to extract them from the game files, I think OGRE is used, but it seemed encrypted or I was doing something wrong.

Thanks!
## Post #2
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-06T00:16:11+00:00
- Post Title: Rebel Galaxy Outlaw Ships for 3D Printing

Unfortunately there's no way to open the .mdl files yet, [according to the developer](https://steamcommunity.com/app/290300/discussions/0/490125737485635772/) he created a custom exporter for 3DS Max for the meshes. Which seems to identify as "[MeshSerializer_Runic]". MeshSerializer is an Ogre3D identifier, but he somehow seems to have modified it. It also seems to indicate that he maybe used the same exporter when he still worked for Runic Games (the Torchlight series), so maybe there's something to be found from this angle.

I've at least found an [.mdl import script for Blender](https://github.com/rgmdl/rg_mdl_import) for the first Rebel Galaxy game (before Outlaw), but it seems to fail for RGO's .mdl files.
