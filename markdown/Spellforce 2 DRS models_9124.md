## Post #1
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-21T19:48:14+00:00
- Post Title: Spellforce 2 DRS models

Spellforce 2 stores its models in '*.DRS' files, which can now be extracted:


Positioning of bones relative to a model's mesh in 3DSmax.


Skinning detail in 3DSmax.


Model with textures in 3DSmax.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-21T19:52:09+00:00
- Post Title: Spellforce 2 DRS models

It can be extracted...but with what?
## Post #3
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-21T20:17:51+00:00
- Post Title: Spellforce 2 DRS models

I made a little VB6 program, which exports a DRS model in an SMD file
(SMD is nice for storing vertex weights).

Only today I was able to get the bones' position and orientation right,
so I'll need to brushup my tool a little, and then I'll publish it.

btw. The tool will be called 'LightSong v0.1' ..
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-21T20:31:39+00:00
- Post Title: Spellforce 2 DRS models

oh alright lol
Will you be releasing the specs as well if someone wants to write a direct importer?
## Post #5
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-21T20:56:56+00:00
- Post Title: Spellforce 2 DRS models

'Would have to talk about that.
I mean, the DRS file format is pretty straightforward, so I don't mind sharing that,
but getting positions and orientations right.. that was a real hard nut to crack, and I'm really happy I found out how to do that. To share that particular type of info, I'd rather (only) talk to someone who's knowledgeable about 3D mathematics.

I have to add that I haven't figured out the file format entirely - that depends on public interest in a two-way converter.
In fact my primary interest is Spellforce 2 character animations, so after I release the tool, I want to continue with the Spellforce 2 SKA file format. The most interesting thing about that might be the 'talk' animations, because they use 22 facial bones (!).
## Post #6
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-22T07:54:07+00:00
- Post Title: Spellforce 2 DRS models

Here's an introduction to the Spellforce 2 DRS file format:

To start out, there's two types of DRS files, one for 'static' models and one for animated models. Static models are for example weapons. Animated models are obviously heroes, NPCs etc., but buildings are animated as well (**).

The first four bytes in a DRS file determine the model style. Static object DRS files can be recognized by the character sequence "srrd". Animated model DRS files start with HEX(1E F1 7C C5), which can be interpreted as float(-4047.07). For convenience, the different DRS file formats will be designated "srrd" format and "4047" format.

The general DRS header is:

magicNumber	-	4 bytes	string "srrd" or float -4047.07
numberOfModels	-	4 bytes	integer 1

Hereafter, the content of the two types greatly differs.

The srrd format is the most straightforward, as it starts out with a mesh header (designated "hsem"), a mesh chunk, a geometry header (designated "moeg"), and a geometry chunk. There's a footer in the srrd format, containing the characters "FOE".

The 4047 format contains two offsets after the general DRS header. These offsets point to two lists at the end of the file. These lists in turn describe and point at the entities in the file. After these two offsets, the number of entities follows. So a 4047 DRS file has an extended header, containing:

entityList01	-	4 bytes	offset to the first entity list (list of offsets)
entityList02	-	4 bytes	offset to the second entity list (list of entity class names)
numberOfEntities	-	4 bytes	integer

In order to read out the contents of a 4047 DRS it is best to get these lists first, and then jump through the file using the offsets from entityList01. Identify and parse each entity's contents depending on the class names from entityList02. These class names can be:

"CDspMeshFile"
"CDspJointMap"
"CSkSkeleton"
"CGeoOBBTree"	-	this class is not sifted yet;
"CGdLocatorList"	-	this class is sifted only rudimentary;
"CGeoMesh"	-	this class is sifted only partially;
"CSkSkinInfo"

In addition, the list of class names can contain two additional entities with names containing the words:

"collisionShape"	-	this class is not sifted yet;
"placementShape"	-	this class is not sifted yet.

In the DRS file directories, the names of the individual DRS files contains a version number. It seems that "v7" is the latest 4047 DRS file format version, containing only the absolutely required chunks / entities for a complete model. Based on this, it seems that chunks designated with "CGeoMesh", "collisionShape", and "placementShape" are not required for a complete model. It also appears that chunks designated with "CGeoOBBTree" are only required for models of buildings.
## Post #7
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-24T22:19:01+00:00
- Post Title: Spellforce 2 DRS models

My tool for Spellforce 2 DRS files is uploaded:
[http://tatooinebase.star-fleet.org/UPLO ... g.v0.1.rar](http://tatooinebase.star-fleet.org/UPLOAD/LightSong.v0.1.rar)

LightSong v0.1 beta converts DRS files to SMD files.

There's also an option for exporting global rotations and global positions of the bones to MAXscript.
In case you select this option, then an SMD will also be exported, which doesn't contain bone positions/rotations.
The purpose of this 'empty' SMD file is to combine it with the scripts in 3DSmax.
## Post #8
- Username: jacquel
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 29, 2011 5:21 pm
- Post datetime: 2012-06-25T20:25:25+00:00
- Post Title: Spellforce 2 DRS models

thanks very well
## Post #9
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-06-29T19:00:08+00:00
- Post Title: Spellforce 2 DRS models

LightSong v0.2 beta is out:
[http://tatooinebase.star-fleet.org/UPLO ... g.v0.2.rar](http://tatooinebase.star-fleet.org/UPLOAD/LightSong.v0.2.rar)

New in version 0.2 Beta:
- Lightsong now loads and displays both kinds of SP2 DRS files (see 'testfiles2.txt');
- improved selection of (sub)meshes;
- improved model display initial orientation;
- improved display of bones (not finished yet);
- etc. (see readme.rtf).
## Post #10
- Username: jacquel
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 29, 2011 5:21 pm
- Post datetime: 2012-07-03T09:41:54+00:00
- Post Title: Spellforce 2 DRS models

sorry but on my pc V.02 don't work and can't open new models at all.
ex for sf1_building_orc_forge.drs
V.01 try but export smd 0 octet
V.02 nothing, just mitchmach
there are no spellforce2.dll in install folder.
or it's update ?
## Post #11
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-07-03T20:57:04+00:00
- Post Title: Spellforce 2 DRS models

It's best to uninstall v0.1 before you install v0.2.

Uninstalling LightSong might ask you whether to uninstall some OCX files, but that is not necessary. Just clean out the entire directory of LightSong v0.1

In your case I think you need to uninstall v0.2 as well. Then reinstall v0.2 after your system has no more references to any LightSong files.
