## Post #1
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-08-31T03:24:51+00:00
- Post Title: Request: Quest for Glory 5 (MDL & ANM)

Hi,

I have a request for an old adventure game by Sierra called Quest for Glory 5.

I have managed to extract the game's model and animation files thanks to Watto and his software "Game Extractor".

If anyone could please help me to open these files in 3DS max or blender I would greatly appreciate it. Ideally I would like to be able to save back into the original format, but just being able to view the models and animations would be a great.

I have rar'd all of the animation files along with some of the models available [here](http://rapidshare.com/files/416153414/qfg5_anm_mdl.rar)

Thanks in advance,
Robert
## Post #2
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-02T09:53:54+00:00
- Post Title: Request: Quest for Glory 5 (MDL & ANM)

Has anyone made any progress on this?

Some of those models I supplied are quite large so it may be quite hard to decipher them.

I have rar'd some of the smaller simple models available [here](http://rapidshare.com/files/416606885/qfg5_mdl.rar)
## Post #3
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-06T07:37:43+00:00
- Post Title: Request: Quest for Glory 5 (MDL & ANM)

Finally made some progress with this, managed to find the indexed color palette and textures in the model files. =)

I did this by using HexCmp to compare 2 identical models with different skins.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-09-06T14:03:13+00:00
- Post Title: Request: Quest for Glory 5 (MDL & ANM)

As for the mdl model files, there appears to be at least 2 different types, the largest mdl is appears to be terrain, and all others being characters. The following applies for all of the character meshes:

At offset 0C is the name of the mesh. Mesh names can only be up to 0h10 bytes in size.
At offset 1C there is a 4byte integer showing the number of submeshes.
Offsets 2D to 0h427 is the bitmap palette for the 256 (0h100) color bitmap texture.
Offset 0h428 is a 4byte address pointing to the start of the bitmap texture itself.
Offset 0h42c is the first 4byte address that points to the first submesh, there is an address for each submesh.

SubMesh format:
The start (SM+0) of each submesh has its name as 0h10 bytes.
SM+0h60 is an 4Byte integer showing the number of Vertexes.
SM+0h64 is an 4Byte integer showing the number of UV cords
SM+0h68 is an 4Byte integer showing the number of Faces
(Note these numbers can be different because the game maps Vertexes and UV on to Faces not the other way around)
SM+0h7C, are all the 4ByteFloatVertexes (FloatX,FloatY,FloatZ) followed by all of the 4ByteFloat UV Maps (FloatU,FloatV)
SM+0h7C+[#Vertexes]*C+[#UV]*8 are the Face Data arrays which a set of 0h28 arrays which have the following format:
{4ByteVertex#1, 4ByteVertex#2, 4ByteVertex#3, 4ByteUVMap#1, 4ByteUVMap#2, 4ByteUVMap#3, 4ByteUnknown, 4BytefloatFACENormalMappingX, 4BytefloatFACENormalMappingY, 4BytefloatFACENormalMappingZ}
## Post #5
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-06T22:04:30+00:00
- Post Title: Request: Quest for Glory 5 (MDL & ANM)

Wow nice job dude. Will have a poke around tonight =)

Cheers
## Post #6
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2013-03-25T02:23:56+00:00
- Post Title: Request: Quest for Glory 5 (MDL & ANM)

Thanks, FurryFan, for this analysis of the MDL file format. I'd like to make a minor correction, though.

> Reply from FurryFan
>
> Offsets 2D to 0h427 is the bitmap palette for the 256 (0h100) color bitmap texture.
The palette actually starts at offset 0x28 and is 0x400 bytes long (256 entries of 4 bytes each). Each color in the palette is represented as a zero byte followed by red, green, and blue bytes.

Ron
