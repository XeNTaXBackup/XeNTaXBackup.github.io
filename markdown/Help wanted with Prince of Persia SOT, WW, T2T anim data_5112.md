## Post #1
- Username: rogueclarkey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 22, 2008 11:01 pm
- Post datetime: 2010-09-30T17:41:06+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

I know these games are a bit old school, but I'm hoping someone out there may be able to help.

I think I've just about managed to decipher the animation data for these games, but I'm stuck with unpacking the rotation keys.

Each rotation is packed into 4 bytes, but I've no idea whether this relates to X,Y,Z rotations packed together or some form of packed quaternion.
(I've no idea why the first rotation has a key time of 64 [0x040] either )

Here is a sample of the the packed data. I'd greatly appreciate any assistance with this as I'm pretty sure I can get all other animation info.
Any suggestions on techniques to try would be happily received 

blockNum boneID: keyType
========================
0 fa03: rotation
keyNum  rotation_bytes[4] keyTime
==========================

0: 0x6b 0xca 0x4f 0x18 64
1: 0x63 0x3e 0xf6 0xbe 2
2: 0x53 0x9e 0x86 0xbe 1
3: 0x4c 0xbe 0x56 0xbe 1
4: 0x47 0xbe 0x46 0xbe 1
5: 0x43 0x9a 0x56 0xbe 1
6: 0x41 0x5a 0x86 0xbe 2
7: 0x3e 0xc2 0x5 0xbf 1
8: 0x3d 0xc2 0xff 0x15 1
9: 0x3c 0xae 0x6f 0x15 1
10: 0x3c 0xa6 0x1f 0x15 1
11: 0x3b 0xa2 0xef 0x14 1
12: 0x3b 0xa2 0xdf 0x14 1
13: 0x3b 0xa2 0xdf 0x14 1
14: 0x3b 0xa2 0xdf 0x14 1
15: 0x3b 0xa6 0xef 0x14 3
16: 0x3b 0xae 0x3f 0x15 1
17: 0x3b 0xb2 0x4f 0x15 1
18: 0x3b 0xb2 0x4f 0x15 0

blockNum boneID: keyType
========================
1 fa03: translation


keyNum  trans_x trans_y trans_z keyTime
==========================
0: 0.000000 0.000000 0.781751 0
1: 0.007761 -0.064026 0.815302 1
2: 0.017032 -0.133151 0.851556 1
3: 0.025548 -0.199727 0.886458 1
4: 0.031043 -0.256105 0.915956 1
5: 0.031253 -0.294636 0.935995 1
6: 0.024694 -0.314083 0.945550 1
7: 0.013043 -0.320854 0.947941 1
8: -0.001230 -0.318774 0.945640 1
9: -0.015655 -0.311663 0.941120 1
10: -0.027761 -0.303345 0.936850 1
11: -0.035080 -0.297642 0.935301 2
12: -0.040865 -0.289414 0.936989 7
13: -0.039388 -0.249299 0.945245 2
14: -0.038463 -0.241582 0.946818 0
## Post #2
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-09-30T22:21:40+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

Since i haven't found format information for them yet, these games are on my ever growing todo list as well.  i am unfortunately a bit backlogged with a number of other formats i am working on.  i'll see if i can make some time to take a break and look into these, heh.

Any information you already have could be useful, and would definitely help in not having to duplicate work.
## Post #3
- Username: rogueclarkey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 22, 2008 11:01 pm
- Post datetime: 2010-10-01T12:59:14+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

Here goes the brain dump of what I've found so far. At the moment I'm only interested in getting the prince character so I've not been looking to build a generic file exporter and have targeted particular data blocks to try and get skeleton, mesh and animations.

I’m looking at the Prince of Persia: The Two Thrones game at the moment.

I use the PersianRug tool from Turfster so I have to give a nod of thanks for that.

Here is the link for anyone that’s interested.
[http://prince.turfster.be/](http://prince.turfster.be/)

If you run PersianRug once it creates an entry in the windows registry. If you add a registry value called Debug to HKEY_CURRENT_USER\Software\Turfster\PersianRug then it unlocks an option to expand .bin files to their uncompressed format. Expanded files can be saved and end up with a .binexpanded extension. Very useful 

It’s these expanded files I’ve been using to get the data from.

Here is a link to files that I’m looking at.
[http://www.sendspace.com/file/1n0jxo](http://www.sendspace.com/file/1n0jxo)


Each BIN file consists of a number of blocks. Each block has the following format:

struct BLOCK_HEADER
{
	Uint32 dataSize; // number of bytes after block header that contain data
	Uint32 blockTag; // always 99 CO FF EE
	Uint32 blockID;
};

The data section of each block starts immediately after the header.

The last block has the ID 0x0FF7C0DE.


Skeleton
========

File: PrinceFinal_Shape_wow_ff051dec.binexpanded
Block ID: 0x51002324

numberOfBones = blockHeader.dataSize  / 4;
boneIDs - numberOfBones * 4 bytes 
Bones
=====

Each block in the bones list has the following format:

Block data

“.gao” – 4 bytes
Unknown – 4 bytes
nameLength – uint32
name – nameLength bytes
unknown – 10 bytes
transform matrix – 16 floats [4 bytes per float]
unknown – 52 bytes 
parentID – uint32 [blockID of parent bone]

Mesh Data
=========

File: PrinceFinal_Shape_wow_ff051dec.binexpanded
Block ID: 0x51002324

Unknown - 16 bytes
positionDataCount – uint32
unknown – 4 bytes [another count?]
unknown – 4 bytes
UVDataCount – uint32
primitiveCount – uint32

unknown – 4 bytes [float?]
unknown – 2 bytes
chunkCount – uint16 [not sure what these chunks are for]
For each chunk
  blockID? – uint16
  valuesCount – uint16
  transform matrix? – 16 floats [not sure if this actually a matrix]
  unknown – 4 bytes
  For each value
    value – float
  End For
End For
Unknown – 4 bytes
For each position
  position – 3 floats [x,y,z]
End For
For each normal [normalCount seems to be same as positionCount]
  normal – 3 floats [x,y,z]
End For
For each uv
  uv – 2 floats [u, v]
End For
For each primitive
  numTriangles – uint32 [triangles per primitive]
  primitiveID? – uint32
End For
triangleData – totalNumTriangles * 16 bytes [I think these are indices for position, normal, uvs]
unknown – 8 bytes
numIndexBuffers – uint32
For each indexBuffer
  Unknown – 4 bytes
  numTriangles – 4 bytes [triangles per index buffer]
End For
Unknown – 8 bytes
numVertices – uint32 [start of VertexBuffer]
vertexSize – uint32 [size in bytes of each vertex]
vertexData – numVertices*vertexSize
indexBufferSize – uint32 [size of index data in bytes] [start of IndexBuffer data]
For each IndexBuffer
  indexData – numTriangles*3*uint16
End For

I used the the VertexBuffer and IndexBuffer to extract the mesh data.

Each vertex had the following structure:

Position – 3 floats
Normal – 3 floats
BoneIndices – 4 shorts [4 * 2 bytes]
BoneWeights – 3 floats
UV – 2 floats

I’m not sure how the bone indices and weights are used as some of the indices seem a lot higher that the number of bones in model.

Animation
=========

File: Dynamic_Actions_Drink_wow_ff0e0dc0.binexpanded
Block ID: 0x33000068

There are a number of keyframe chunks that make up this block. At the moment I just keep reading keyframe chunks and stop when the start of the next chunk doesn’t start with 0x03 0xFA.

Unknown – 76 bytes [There is probably data is here to indicate animation length and number of key frame blocks]
For each keyframe chunk
  Start – 2 bytes [always 0x03 0xFA]
  BoneID – 2bytes
  Unknown – 4 bytes
  keyCount – uint32
  unknown – 3 bytes [seems to always be 0x01 0x80 0x00]
  keyType – 1 byte
  unknown – 2 bytes
  FOR each key
    IF keyType == 0x80 THEN
      [translation data]
      keyDuration – 1 byte
      translation – 3*float [x,y,z]
    END IF
    IF keyType == 0x10 THEN
      [rotation data]
      keyDuration – 1 byte
      rotation – 4 bytes [no idea how this breaks down]
    END IF
  End For
End For

ACCURACY DISCLAIMER  : I don’t think I’ve missed anything in my description of the data, but there is always the chance. If you do find I’ve said something that doesn’t match up, please let me know.
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-02T08:21:52+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

I'm always interesting why turfster doesn't support bones and weight data. I believe that he know a lot about game (such as prince of persia, assassin's creed 1/2, blood rayne, ghostbusters and beyond good and evil) formats, but somehow he don't want improve he's certainly a very good tools.
I will watching on this topic.

p.s.: if need any help, or files/samples i can help/upload.
## Post #5
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-13T20:49:49+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

First of all.. Thanks to rogueclarkey for putting your knowledge online.. I was looking  long time for a startingpoint. Still there are some errors in the former post that needs to be corrected, even if the thread is 10 years old.. games and knowledge never getting old.

best programs to use:
bfrepacker (to decrompress)
persianRugTool (to extract model and textures)
noesis (it has some handy functions to handle the bones, animation and matrix data)

I used the following files:

Prince_of_Persia_T2T (GC)
PrinceFinal_Shape_wow_ff051dec.bin [important: it needs to be decompressed! and renamed back to *.bin for noesis ]
Dynamic_Actions_Drink_wow_ff0e0dc0.bin [same principle like above]

```

=================================
|	SKELETON		|
=================================

THE BONELIST IS NOT THAT IMPORTANT
BUT GOOD TO GET FOR FURTHER RESEARCH

BONE_LIST_HEAD 	(0x000139D3) BE
[
	4	blockSize	0x00010000							
	4	blockTag	0x99C0FFEE	
	4	blockID		0x24230051	
]
BONE_LIST_BODY	(blockSize / 4 = BoneCount)
[
	4	blockID		0x(E422)0051	(BONE BLOCK ID 001)	 
	4	blockID		0x(ED22)0051	(BONE BLOCK ID 002)
	4	blockID		0x(F022)0051	(BONE BLOCK ID 003)
]

+________________________________________________________+

THIS IS THE IMPORTANT PART

BONE_BLOCK_HEAD 		(00013ADF) BE (FDA31000) LE
[
	4	blockSize	AA000000	(170 Bytes)
	4	blockTag	99C0FFEE	(ALWAYS)
	4	blockID		(E422)0051	(LOOK BONE LIST ABOVE) (READING JUST 2 BYTES IS ENOUGH!)
]
BONE_BLOCK_BODY
[
	4	format		2E67616F		".gao"
	4	unknown		0C000000		12				
	4	unknown		08000000		8				
	4	unknown		00102901		19468288			
	4	nameLength	14000000		20				
	X	name(nameLength)			"B_Pr_Bip Pelvis.gao."
	4	unknown		00000400		262144			
	4	unknown		00100000		4096				
	2	unknown		0000			0				
	64	TMatrix					{4 x 4 TransformationMatrix in LocalSpace}	16 x 32Float
	52	unknown		52 byte		
	4	ParentID	(0000)0000		(AGAIN JUST THE FIRST 2 BYTES MATTERS)
	...	
]

```


```

=================================
|	ANIMATION		|
=================================

THERE ARE MORE THAN 1 ANIMATION BLOCK (3 IN THIS EXAMPLE)
EACH BLOCK CONSISTS OF 34 CHUNKS. THERE MIGHT BE 64 SKELETON BONES..
BUT ONLY THE FIRST 34 _BIP BONES HAS ANIMATION.. (THE REST ARE SECONDARY
ANIMATED BY THE PHYSIC ENGINE I GUESS)

ANIM_HEAD	(0x00001823)
[
	4	blockSize	AD100000	(4269 Bytes)
	4	blockTag	99C0FFEE	(ALWAYS)
	4	blockID		(6800)0033	
]
ANIM_BODY
[
	34	unknown		YOU SHOULD SKIP 34 BYTES FIRST AFTER THAT COMES VARIABLE SIZED PART
	X	unknown		STEP FORWARD UNTIL YOU FIND THE VALUE 0x03FA
	
	FOR 0 TO Biped_Bone_Count (34 for PoP)
		2	chunkStart	0x03FA (ALWAYS)
		2	BoneIndex	0000		(INDEX NOT THE BONE ID ITSELF)
		4	unknown
		4	keyCount		
		3	unknown
		1	keyType		0x10 = TRANSLATION AND 0x08 = ROTATION
		2	unknown
	
		FOR	0 TO KeyCount
			IF	keyType == 0x08
				1	keyDuration
				4	X		32Float
				4	Y		32Float
				4	Z		32Float
			IF	keyType == 0x10
				1	keyDuration
				4	Rotation	4*1Byte PackedQuaternion?
]

AND REMEMBER THERE ARE MORE THAN JUST 1 ANIMATION BLOCK


```

Thanks to rogueclarkey (former Post), RichWhitehouse (noesis), turfster (PersiaRug), BlackDaemon (bf repacker), Sir Kane, Dimy, chrrox [hinting to fix the anomalies of the skeleton]
## Post #6
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2020-02-16T16:17:53+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

> Reply from MilesPrower ↑Fri Feb 14, 2020 4:49 am at Fri Feb 14, 2020 4:49 am
>
> 
First of all.. Thanks to rogueclarkey for putting your knowledge online.. I was looking  long time for a startingpoint. Still there are some errors in the former post that needs to be corrected, even if the thread is 10 years old.. games and knowledge never getting old.

best programs to use:
bfrepacker (to decrompress)
persianRugTool (to extract model and textures)
noesis (it has some handy functions to handle the bones, animation and matrix data)

I used the following files:

Prince_of_Persia_T2T (GC)
PrinceFinal_Shape_wow_ff051dec.bin [important: it needs to be decompressed! and renamed back to *.bin for noesis ]
Dynamic_Actions_Drink_wow_ff0e0dc0.bin [same principle like above]
Code: Select allPrinceFinal_Shape_wow_ff051dec.bin

=================================
|	SKELETON		|
=================================

THE BONELIST IS NOT THAT IMPORTANT
BUT GOOD TO GET FOR FURTHER RESEARCH

BONE_LIST_HEAD 	(0x000139D3) BE
[
	4	blockSize	0x00010000							
	4	blockTag	0x99C0FFEE	
	4	blockID		0x24230051	
]
BONE_LIST_BODY	(blockSize / 4 = BoneCount)
[
	4	blockID		0x(E422)0051	(BONE BLOCK ID 001)	 
	4	blockID		0x(ED22)0051	(BONE BLOCK ID 002)
	4	blockID		0x(F022)0051	(BONE BLOCK ID 003)
]

+________________________________________________________+

THIS IS THE IMPORTANT PART

BONE_BLOCK_HEAD 		(00013ADF) BE (FDA31000) LE
[
	4	blockSize	AA000000	(170 Bytes)
	4	blockTag	99C0FFEE	(ALWAYS)
	4	blockID		(E422)0051	(LOOK BONE LIST ABOVE) (READING JUST 2 BYTES IS ENOUGH!)
]
BONE_BLOCK_BODY
[
	4	format		2E67616F		".gao"
	4	unknown		0C000000		12				
	4	unknown		08000000		8				
	4	unknown		00102901		19468288			
	4	nameLength	14000000		20				
	X	name(nameLength)			"B_Pr_Bip Pelvis.gao."
	4	unknown		00000400		262144			
	4	unknown		00100000		4096				
	2	unknown		0000			0				
	64	TMatrix					{4 x 4 TransformationMatrix in LocalSpace}	16 x 32Float
	52	unknown		52 byte		
	4	ParentID	(0000)0000		(AGAIN JUST THE FIRST 2 BYTES MATTERS)
	...	
]

Code: Select allDynamic_Actions_Drink_wow_ff0e0dc0.bin

=================================
|	ANIMATION		|
=================================

THERE ARE MORE THAN 1 ANIMATION BLOCK (3 IN THIS EXAMPLE)
EACH BLOCK CONSISTS OF 34 CHUNKS. THERE MIGHT BE 64 SKELETON BONES..
BUT ONLY THE FIRST 34 _BIP BONES HAS ANIMATION.. (THE REST ARE SECONDARY
ANIMATED BY THE PHYSIC ENGINE I GUESS)

ANIM_HEAD	(0x00001823)
[
	4	blockSize	AD100000	(4269 Bytes)
	4	blockTag	99C0FFEE	(ALWAYS)
	4	blockID		(6800)0033	
]
ANIM_BODY
[
	34	unknown		YOU SHOULD SKIP 34 BYTES FIRST AFTER THAT COMES VARIABLE SIZED PART
	X	unknown		STEP FORWARD UNTIL YOU FIND THE VALUE 0x03FA
	
	FOR 0 TO Biped_Bone_Count (34 for PoP)
		2	chunkStart	0x03FA (ALWAYS)
		2	BoneIndex	0000		(INDEX NOT THE BONE ID ITSELF)
		4	unknown
		4	keyCount		
		3	unknown
		1	keyType		0x10 = TRANSLATION AND 0x08 = ROTATION
		2	unknown
	
		FOR	0 TO KeyCount
			IF	keyType == 0x08
				1	keyDuration
				4	X		32Float
				4	Y		32Float
				4	Z		32Float
			IF	keyType == 0x10
				1	keyDuration
				4	Rotation	4*1Byte PackedQuaternion?
]

AND REMEMBER THERE ARE MORE THAN JUST 1 ANIMATION BLOCK


Thanks to rogueclarkey (former Post), RichWhitehouse (noesis), turfster (PersiaRug), BlackDaemon (bf repacker), Sir Kane, Dimy, chrrox [hinting to fix the anomalies of the skeleton]

Thanks for the sharing information MilesProwe   This is enough info's for made worked tool for extract animation properly?
And off topic: Ive try extract models from PS2 Version (POP SOT) with  bfrepacker and decompress bin, and no PersianRUG no POP Map tools for blender can't properly read decompressed bin, ive get some errors, ive attach two files compressed and decompressed bin, maybe somebody help me out with it. 
[https://dropmefiles.com/zUmzk](https://dropmefiles.com/zUmzk)
## Post #7
- Username: Trial4life42
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 09, 2021 7:31 pm
- Post datetime: 2021-06-09T11:35:51+00:00
- Post Title: Help wanted with Prince of Persia: SOT, WW, T2T anim data

Thank you MilesPrower for sharing with us these useful informations. I'm a big fan of the Prince of Persia series, and I'm trying to extract the 3D models of the game.

Do you think it could be possible to extract the animation data of the Dahaka, read it using Blender and link it to the 3D models that I've already managed to export by using Persian Rug?

I've tried using noesis as you mentioned, but even after the .bin decompression and renaming back to ".bin", it can't read the file. Furthermore, I've no idea where these animations data could be stored.

Thanks in advice for the help.
