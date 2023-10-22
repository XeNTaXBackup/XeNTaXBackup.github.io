## Post #1
- Username: Tanasoo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 31, 2008 10:20 am
- Post datetime: 2008-01-31T19:00:53+00:00
- Post Title: Crytek CGF models

I saw this site when I was googling info on cracking model files, so I decided to make a post to see if anyone wanted to help me with cracking the new (crysis) CGF files.

I have done this sort of thing before. I was one of the guys that cracked the Halo 3 beta models, but I was more on the end of coding an importer in maxscript then finding out the actual data. Although once I knew the general layout I was able to help by finding out things like the UV, and bone weight data.

I really want to get these imported into  3ds max, so any help would be great!
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-02T08:15:18+00:00
- Post Title: Crytek CGF models

So what do you already know!?

I did have a look at the format and it is very complicated! Although I can basically "import" the mesh, but I can't find the skin/weight data!

I don't have any document in hand atm. But I recall it is a tag base format. The tag is a dword, something like 0xCCCC000F. You can find a resource table at the beginning of the cgf as well.
## Post #3
- Username: Tanasoo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 31, 2008 10:20 am
- Post datetime: 2008-02-02T20:48:19+00:00
- Post Title: Crytek CGF models

Wow, really? That's awesome!

I don't really know anything about them, but I might be able to help find some of the other stuff. If I could know what parts of the file are used for storing data like vert positions, triangle strips, etc.  Also, are these models compressed in any way?
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-04T22:00:42+00:00
- Post Title: Crytek CGF models

[out]
## Post #5
- Username: Tanasoo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 31, 2008 10:20 am
- Post datetime: 2008-02-05T08:21:57+00:00
- Post Title: Crytek CGF models

OK, here are a few objects.

[http://www.megaupload.com/?d=GV19C3MV](http://www.megaupload.com/?d=GV19C3MV)

box.cgf is, well, a box...
box_nodraw is a low poly sphere.
nannoSuit_us.chr is a different format. It is the format used for characters. It looks, to my untrained eye, to be similar, with the exception of extra stuff for probably bones, skin, nodes, etc.

From what I can tell about the chr, again, from my untrained eye, after the "header" there is a string with the name of the original 3ds max file, a BS timestamp (or proof of time travel  ) and possibly the artist's name? Then it looks like it lists all of the node names, but I don't see any position or orientation numbers... in fact, I see very little except 0000.  A little ways down (approximately offset 13984) it looks like it is listing the original 3ds max material names, then more nodes, and more mat names. Not sure what this is all about... Then @~ 24918 it looks like it starts listing the actual skeleton (bone) data, with some values, although I don't know what they mean. Moving right along, down to about 92368. I'm not sure exactly what all this is, but if I was to hazard a guess, I would say vertex data because: @98894 there are some values that look an awful lot like triangle strip data. Then it looks like there is another vertex data chunk, then more tri-strips, etc. until the end. Keep in mind that there are a few "regions" or separate model sections in this file (like arms, body head, etc.)

I hope that helps a little, and wish I could be more help.
Thanks!
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-05T09:05:22+00:00
- Post Title: Crytek CGF models

Before you guys go to the wrong direction, I show you what I found!

CGF and CHR are model file, and strange enough they share the same format!!!

first 20 byte should be the header, possibility version etc

```
word       unknown1           //??0x00 or 0x7400
word       unknown2           //constant 0x00
word       unknown3           //constant 0xFFFF
word       unknown4           //constant 0x0744
word       unknown5           //constant 0x00
dword     ofsResTable         //usually point to 0x14

```


As I said the format is "tag" based. And the Resource Table list out all the tag section, offset, index etc.

Resource Table

```
struct ResTable {
dword     Tag
dword     ??
dword     ofsTag
dword     Index
}

```

AFAIK:
CCCC0013     Filelog
CCCC000E     Distance related (LOD distance etc??)
CCCC000B     Name and Transform
CCCC0000     Mesh Description
CCCC0016     mesh data (0-vert, 1-normal, 2-UV, 3-VertColor, 5-Face Index)

each Tag/Section share same format as ResTable:

```
dword     ??
dword     ofsTagStart
dword     Index
{data}

```
## Post #7
- Username: Tanasoo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 31, 2008 10:20 am
- Post datetime: 2008-02-05T19:24:35+00:00
- Post Title: Crytek CGF models

That's great!

Is there any reference to the size of each tag? How do you tell when you reached the end?

Thanks for all of the help!
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-05T21:51:24+00:00
- Post Title: Crytek CGF models

[out]
## Post #9
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-06T08:00:15+00:00
- Post Title: Crytek CGF models

> Reply from Wobble
>
> 
In fact, from the two files posted, the mesh structure has changed completely.
Before, it stored vertices, uvs, and trigs, but now, all that information has 
been removed.  All I see is an empty structure with some counts, just a descriptor.
All the other stuff must have been moved to new chunks.
Those are not count, they are index number. All point to the CCCC0016 mesh data. The spaces are fixed for specific data like:
00 -> 15 chunk index 0x15 (vert)
01 -> 16 chunk index 0x16 (normal)
02 -> 00 no such data (UV)
03 -> 17 chunk index 0x17 (VertColor)

> Reply from Tanasoo
>
> 
Is there any reference to the size of each tag? How do you tell when you reached the end?

There is no size data, but each section/chunk is followed one form the other, so you can calculate the size form the ResTable.
## Post #10
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-06T18:15:57+00:00
- Post Title: Crytek CGF models

[out]
## Post #11
- Username: Tanasoo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 31, 2008 10:20 am
- Post datetime: 2008-02-07T01:41:42+00:00
- Post Title: Crytek CGF models

I think you're right about the bounding box (-X, -Y, -Z, X, Y, Z)

I'm not sure about the rest, but thanks a ton for all of your work
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-07T12:33:30+00:00
- Post Title: Crytek CGF models

> Reply from Wobble
>
> 
Are you saying chunk 0xCCCC0000 contain chunk table indices?

Because NanoSuit_us.chr has 144 chunk table entries, and these numbers exceed 144:

If you look carefully, the indices are not in orders!!!

As I said, I already "import" the mesh! I just can't found materialID(which faces belong to which material) and skinning data!
[NanoSuit_Table.jpg](https://xentaxbackup.github.io/file/1441_NanoSuit_Table.jpg)
## Post #13
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-07T12:59:16+00:00
- Post Title: Crytek CGF models

Just realize that I forgot to mention how CCCC0016 work!

```
dword     ChunkVer
dword     ofsChunk
dword     ChunkIndex
dword     Unknown00        //always 00
dword     DataType         //0-vert, 1-normal ...
dword     numData
dword     BytePerData      //eg: type 00, it is 0x0C(12) = float X 3(vert pos XYZ)
dword     Unknown00        //always 00
dword     Unknown00        //always 00
<data>

```
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-07T18:40:51+00:00
- Post Title: Crytek CGF models

[out]
## Post #15
- Username: Tanasoo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 31, 2008 10:20 am
- Post datetime: 2008-02-07T19:27:33+00:00
- Post Title: Crytek CGF models

If someone could explain this 0XCCCC0000 stuff to me, I might be able to help with the materials and weights. I just need to know where to look.

I'm going to take a wild guess and say that after CCCC there are eight Dwords with data about the chunk. And the ChunkIndex is the location of the chunk. Right?
## Post #16
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-08T09:37:36+00:00
- Post Title: Re: Crytek CGF models

> Reply from Wobble
>
> 
Ok, I see above you said in 0xCCCC0016 as type 5?  I would guess face materials would be in the triangle list.

Yes, the Tri-list(I call them Face Indices) chunk is 5
No, face materials are not in chunk 5
[Suit_dump.jpg](https://xentaxbackup.github.io/file/1442_Suit_dump.jpg)
## Post #17
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-08T09:49:17+00:00
- Post Title: Re: Crytek CGF models

> Reply from Tanasoo
>
> If someone could explain this 0XCCCC0000 stuff to me, I might be able to help with the materials and weights. I just need to know where to look.

Is it clear?

```
dword     ChunkVer
dword     ofsChunk
dword     ChunkIndex
dword     Unknown00        //always 00
dword     Unknown00        //always 00
dword     VertCount
dword     FaceIndexCount
dword     ??               //point to CCCC0017
dword     ??
dword     Vert_Index
dword     Normal_Index
dword     UV_Index
dword     VertColor_Index

dword     ??
dword     Tri-List_Index
dword
dword

dword
dword
dword
dword

dword
dword
dword
dword

dword
dword
dword
dword

float X 3 BBmin
float X 3 BBmax
...

```


> Reply from Tanasoo
>
> I'm going to take a wild guess and say that after CCCC there are eight Dwords with data about the chunk. And the ChunkIndex is the location of the chunk. Right?

No, different chunk had different structure. But the chunk-header (ChunkID, Ver, Offset, Index) are same. The actual location are located in ofsChunk, which is the third dword of the list/chunk-header.

PS: CCCC0014 seems to be material Chunk, if it is multimaterial (type 1), it use same kind of indice look-up method as CCCC0000.
But for type 12 (Standardmaterial??), it just a empty container??
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-08T21:24:35+00:00
- Post Title: Re: Crytek CGF models

[out]
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-08T21:30:33+00:00
- Post Title: Re: Crytek CGF models

[out]
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-02-25T02:30:44+00:00
- Post Title: Re: Crytek CGF models

[out]
## Post #21
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-28T15:27:18+00:00
- Post Title: Re: Crytek CGF models

Did you guys found anything new? One Question: do you know that the NanoSuit_us had a morph data ingame? Some kind of inflatten suit?

Last time I work on it, I found the skin data then morph data(?). 0xCCCC0016 type 9 and type 8

And I guess the material IDs are stored in the new format of material chunk.
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-03-10T15:47:12+00:00
- Post Title: Re: Crytek CGF models

[out]
## Post #23
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-13T08:36:15+00:00
- Post Title: Re: Crytek CGF models

Any progress? It turned out someone to get a model with skinning data?
## Post #24
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-12-14T11:00:30+00:00
- Post Title: Re: Crytek CGF models

The SDK seems to have all the info you need in the various headers.
To get at it you download something called universal extractor and run it on the exe file. This will generate some internal files. Then after that, you download something called iscabvu which can open Installshield cab files and extract the .h files. Looking at the CryHeaders.h from this SDK, it looks like it has all the same bits listed above except with new Crysis bits.
## Post #25
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-21T09:18:07+00:00
- Post Title: Re: Crytek CGF models

Just joining. Nice screenshot in max looks like you guys are making progress, but I have a question.  On top of the newer CGF format, apparently .CHR is yet another format for model content?  I have 3d Object Converter 4.40 and it opens both these formats flawlessly, perhaps if you can look into this program to see how it handles the .CHR files

Most object directories hold several files in the following formats  and i'm trying to make sense of what's useless that can be deleted or what to keep if I can get access to it (including animation data).  
These are all located in the Objects directories depending on the sub-directory. I'm wonderin why there's so many different types.
.animevents
.cal (?)
.cdf (?
.cgf (known)
.cga (probably animation data reference?)
.chr (known alt.)
.pwf
Also under Prefabs - > .veg

Then, under the animations directory: Animations.cba
subdirectories contain: 
.dba
.anmevents
.ag
.anm
.caf (largest number of files, and on average larger data size per file vs other formats, most likely the animation data here?)
.fsq (main mocap facial data?)
.fxl (most these files end in "_expressions.fxl" so most likely preset facial expressions)
.lmg (Seems local to weapons and other misc objects)
.joy (perhaps joystick calibration and other settings used for their mocap?)

I noticed in the main Objects directory there is a "CrysisCharacterConversion.ccc" which is xml or other format with a table of data to do the same thing to a huge list of .chr files:

```
<Model File="objects/Characters/Alien/AlienBase/alienBase.chr" RotatePosRoot="90" RotateQuatRoot="90" RotatePosChild="180" RotateQuatChild="180"/>
```


noticed: reference_objects.grp seems to be just code and item table for the cgf objects referenced in other directories.

```
 <Object ColorRGB="65280" Id="{358168DB-C065-462D-9EA9-933B963B55E8}" Layer="reference_objects" MergeGeom="0" Name="reference_objects" Opened="0" Pos="1634.6064,4809.0542,128.52861" Rotate="0.90996128,0,0,0.41469327" Type="Group" >
  <Objects>
   <Object CastOcclusionmap="1" CastShadowMaps="1" ColorRGB="16777215" GoodOccluder="0" Hideable="0" Id="{4B3B2376-A8FB-48EE-BAAD-4D3FFB26F17A}" Layer="reference_objects" LodRatio="100" Name="bartable_1" NotTriangulate="0" OcclusionmapQuality="1" OutdoorOnly="0" Parent="{358168DB-C065-462D-9EA9-933B963B55E8}" Pos="1.1967773,-0.10742188,-0.65699768" Prefab="objects/prototype/lighting_referenz/table/table.cgf" ReceiveOcclusionmap="1" RecvShadowMaps="1" RndFlags="556" Rotate="0.70090926,0,0,0.71325046" Type="Brush" ViewDistRatio="100" />
   <Object CastOcclusionmap="1" CastShadowMaps="1" ColorRGB="16777215" GoodOccluder="0" Hideable="0" Id="{28C6A4C4-B472-4109-9233-BF90F7D1D9DB}" Layer="reference_objects" LodRatio="100" Name="bartable_2" NotTriangulate="0" OcclusionmapQuality="1" OutdoorOnly="0" Parent="{358168DB-C065-462D-9EA9-933B963B55E8}" Pos="-0.3717041,-0.13623047,-0.65699768" Prefab="objects/prototype/lighting_referenz/table/table.cgf" ReceiveOcclusionmap="1" RecvShadowMaps="1" RndFlags="556" Rotate="0.70090926,0,0,0.71325046" Type="Brush" ViewDistRatio="100" />
   <Object CastShadow="1" ColorRGB="16777215" EntityClass="BasicEntity" HiddenInGame="0" Id="{6F8365B7-CF82-493E-9D01-EA2E48C088EF}" Layer="reference_objects" LodRatio="100" Name="fire_extinguisher1" Parent="{358168DB-C065-462D-9EA9-933B963B55E8}" Pos="1.1024193,-0.37281239,0.095581055" RecvShadow="1" Rotate="1,0,0,8.3060323e-009" Type="SimpleEntity" ViewDistRatio="100" >
    <Properties bFrozen="0" bUsable="0" damage_players="0" object_Model="Objects/Prototype/Lighting_referenz/fire extinguisher/fire_extinguisher.cgf" objFrozenModel="" soclasses_SmartObjectClass="" UseMessage="press USE to grab object!" >
     <Animation Animation="Default" bAlwaysUpdate="0" bLoop="0" bPlaying="0" sound_AnimStart="" sound_AnimStop="" Speed="1" />
     <Physics bActivateOnDamage="0" bCanBreakOthers="0" bPhysicalize="1" bResting="1" bRigidBody="1" bRigidBodyActive="1" Density="-1" Mass="10" >
      <Buoyancy water_damping="0" water_density="1000" water_resistance="1000" />
      <Simulation bFixedDamping="0" bUseSimpleSolver="0" damping="0" sleep_speed="0.04" />
     </Physics>
    </Properties>
   </Object>
```


this data doesn't seem useful to me, so i'm wondering if it's worth keeping?


I'm also wondering what your guy's purpose is for this thread? Are you making an importer tool for 3dsmax to directly import these format(s)?
