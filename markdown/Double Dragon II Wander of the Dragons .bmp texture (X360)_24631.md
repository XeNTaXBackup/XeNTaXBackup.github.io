## Post #1
- Username: burom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 22, 2017 2:51 am
- Post datetime: 2021-10-24T14:48:45+00:00
- Post Title: Double Dragon II Wander of the Dragons .bmp texture (X360)

Extracted the game with xenia-vfs-dump, extracted game's archives (.pack files) with QuickBMS ([https://zenhax.com/viewtopic.php?f=9&t=15982](https://zenhax.com/viewtopic.php?f=9&t=15982)), character meshes are in OGRE .mesh files ([https://github.com/OGRECave/blender2ogre](https://github.com/OGRECave/blender2ogre)), character textures are supposedly .bmp but checking in a hex editor shows seemingly no header. TextureFinder and Rawtex don't seem to find anything in the .bmp file.

Attached is a sample .bmp and the same texture extracted from Xenia + RenderDoc (i.e. what it's supposed to look like).


 char.zip
(200.4 KiB) Downloaded 18 times
