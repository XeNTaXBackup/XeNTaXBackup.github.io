## Post #1
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-07T20:47:15+00:00
- Post Title: LEGO Star Wars: The Skywalker Saga models

They have quite complex mesh system, but for static meshes ("model" files) it's more or less simple.

In general, every mesh file consists of header and SMNR containers - you can find count of them in a model file before the first container, for example, for tree_stump and maz_castle from provided sample it will be 4. Those containers can include other kind of containers and other info. For static meshes they would contain mostly mesh data (vertices + indices and such) in DXTV sub-containers. Right before every DXTV container there will be vertices count in big endian - pay attention that fields should be parsed in big endian, but data itself is little endian. Depending on SMNR type (I think it's a second field after container's header) it can consist of one or two DXTV subcontainer - tree_stump is the first one and maz_castle is the second. In the first case all data will be included in the first block (positions as half-float + normals + UV + other) and after that there is block with indices. In the second case first DXTV subcontainer contains only normals + UV + other and the second one contains positions as float and block with indices. I believe that types of included in DXTV data are serialized in its header, also the header has variable size. You can see the purpose of each SMNR container at the end of file - for example, for tree_stump the first one will be base model, second and third are LODs and the last one is "shadow" mesh (it's usually used for effects).

Here is visual representation of results for the things explained above:
for tree_stump: [https://i.imgur.com/0DWDomn.png](https://i.imgur.com/0DWDomn.png)
for maz_castle: [https://i.imgur.com/ARSXUY9.png](https://i.imgur.com/ARSXUY9.png)

===========================================

Update:
Ok, here is a brief explanation about skeletal meshes ("ghg" files):
They work in around the same way as static meshes, but more complicated. They have single indices block for all submeshes. Also, at the end of all SMNR containers with DXTV subcontainers with mesh data there will be 78 bytes block with usage of geometry of this DXTV block. For example, in incinerator_stormtrooper file first DXTV contains both positions + other info and indices data. Right after indices there is field with start index for indices, indices count, start index for positions and positions count (actually it's stride value * count). If you're serializing them separately, start index for positions will be always zero, as in most cases current DXTV contains separate positions data (either float or half-float) - but if you'll take a look at SMNR containers hierarchy, you should notice the same index values, which are shared among submeshes, considering current SMNR container. I suppose it allows to create groups of submeshes and process them in connection with each other if needed.

Here is visual representation of results for the things explained above:
for incinerator_stormtrooper (1st DXTV block submesh): [https://i.imgur.com/QfMYTzv.png](https://i.imgur.com/QfMYTzv.png)
for incinerator_stormtrooper (3rd DXTV block submesh): [https://i.imgur.com/bR0wUlz.png](https://i.imgur.com/bR0wUlz.png)
for incinerator_stormtrooper (4th DXTV block submesh): [https://i.imgur.com/okAKBJi.png](https://i.imgur.com/okAKBJi.png)

===========================================

Samples, used here: [link](https://drive.google.com/file/d/1d8DoP3SMpqfIz5RFiUFAqyGvl3VShsNm/view?usp=sharing)

P.S. Personally I'm not interested in all this, it's just a friend asked to look into it. Maybe this info will help others in some way.
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-08T15:46:14+00:00
- Post Title: LEGO Star Wars: The Skywalker Saga models

First post is updated with more info about skeletal meshes ("ghg" files).
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-09T16:29:59+00:00
- Post Title: LEGO Star Wars: The Skywalker Saga models

As an addition to explaned above, here is script for converting TEXTURE files into respective dds and also for extracting separate dds from NXG_TEXTURES files. You can modify the script according to included comment to strip full internal paths and leave filenames only. 

Update: Small fixes for particular texture types added.
Update 2: Script is updated to support ATI1 textures. Also script should now produce proper error for unsupported texture types.
Update 3: Script is updated for proper handling of some NXG_TEXTURES files.



 skywalker_saga_textures_v5.zip
(1.21 KiB) Downloaded 24 times
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2022-04-17T09:53:42+00:00
- Post Title: LEGO Star Wars: The Skywalker Saga models

I have finished my NTT Engine (LEGO Star Wars: The Skywalker Saga)	 *.model loader module and I have released the following programs as web updates:

- 3D Object Converter v8.024 (Windows)
- i3DConverter v4.204	  (macOS)
- i3DConverter v2.204	  (Linux)

How to get the 3D Object Converter v8.024:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).
After it just use the Help/Check for updates... function to get the v8.024.

How to get the i3DConverter macOS v4.203:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
After it just use the Help/Check for updates... function to get the v4.203.

How to get the i3DConverter Linux v2.203:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
After it just use the Help/Check for updates... function to get the v2.203.
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-20T22:28:16+00:00
- Post Title: LEGO Star Wars: The Skywalker Saga models

KillzXGaming released his tool for .model files, based on Sluicer's info from [here](https://zenhax.com/viewtopic.php?f=5&t=16749#p71057) (in case if you don't know, Sluicer created similar tool for a few previous Lego games before, called ExtractNxgMESH): [https://github.com/KillzXGaming/NTT-Model-Dumper](https://github.com/KillzXGaming/NTT-Model-Dumper)
