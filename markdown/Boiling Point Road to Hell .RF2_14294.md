## Post #1
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-04-30T20:22:06+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

I'm creating new characters for Xenus: Boiling Point (Road to Hell) game, and i want to use original animations for new recreating models. But official plugins for *.RF2 format contain only Exporter without import. Somebody can help me and create 3ds max import script?

RF2 files of characters models contain together geometry, bones, animations. How i know about animations, is Position format 16 bits/key TFLOAT16 and Rotation format 48 bits/key TQUAT 48. Also RF2 files contains specific collisions and hitmesh geometry, ports and dummies, animations curve data. Detailed information about models structures might be found in doc files from SDK. Also _RF2View tool from SDK for preview all models from game. And VEExchange plugin for 3ds max can load all geometry from game Level Editor to 3ds max, and back. But characters and other objects loading to Max without bones, anims, and of course not in T-Poses.

Plugins can be download [here](http://www.mediafire.com/download/blu5kzoe93j4o2r/VEPluginsMax67.exe) (for 3ds max 6-8), and Boiling Point SDK is [here](http://www.moddb.com/games/boiling-point-road-to-hell/downloads/boiling-point-sdk).


Some samples of characters, vehicles (also using bones) and weapons: [http://www.mediafire.com/download/bgx0a ... q18/RF2.7z](http://www.mediafire.com/download/bgx0a91mh1hiq18/RF2.7z)


And question about textures: 
Engine of this game is Vital Engine 2.0. And this engine uses texture cache instead textures. For any one texture use two files with extensions *.DT1 and *.DT2. In tools from SDK this textures get uncached and can be ripped. But navigate and sort in ripped textures very hard and long, because in game 3000+ textures. 
Availability sources of textures in Textures game folder is important, because without them LevelEditor can't working in developer mode, and lose some functionality.
So, my question is, maybe possible to create a converter for this cached textures?

Samples of cached textures: [http://www.mediafire.com/download/7r384 ... 8/CACHE.7z](http://www.mediafire.com/download/7r3849dz2415b08/CACHE.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-01T07:49:19+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from StreamThread
>
> Somebody can help me and create 3ds max import script?What exactly do you mean by "help"? Do you know maxscript?
If so then read here:
[viewtopic.php?f=16&t=11090&p=118039&hil ... pt#p118039](http://forum.xentax.com/viewtopic.php?f=16&t=11090&p=118039&hilit=maxscrript#p118039)
(When modifying the script for RF2 you'll need to use readFloat insted of readShort and readHalfFloat for example.)

> RF2 files of characters models contain together geometry, bones, animations.
The mesh format seems to be pretty simple:



STS_Hummer_Door_Fallen-RF2.jpg (152.96 KiB) Viewed 261 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-01T08:31:03+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

here's the script (will work with the door only, startaddress of FI's block 0x256 to be modified for other models):

```
faceArray =#()
UVarray=#()

function ReadModelFile fName=
(     
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"          -- Open the file for reading
    fSeek stream 0x234 #seek_set      -- find the counts
    vertCount = readShort stream       -- vertex count of (first) submesh
    faceCnt     = readShort stream
    vertStride= 36
   
    --print ("@ 0x"+ bit.intAsHex(ftell stream) as string)      

    fSeek stream 0x256 #seek_set   -- face indices block
    for x = 1 to faceCnt do (
        fa= readShort stream #unsigned
        fb= readShort stream #unsigned
        fc= readShort stream #unsigned
            format "f % % %\n" fa fb fc
        append faceArray[fa+1,fb+1,fc+1]   
   )   
    print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
    for i=1 to vertCount do (      --
       x  = readFloat stream
       y  = readFloat stream
       z  = readFloat stream
       fSeek stream (16) #seek_cur
       tu  = readFloat stream; tv  = readFloat stream
       append vertArray ([x,y,z]/127.0)   
      --format "v %\n" vertArray[i]
       append UVarray [tu,tv,0]             
    )
   
    msh = mesh vertices:vertArray faces:faceArray
    msh.numTVerts = vertCount
    buildTVFaces msh
    for j = 1 to vertCount do setTVert msh j UVarray[j]
    for j = 1 to faceCnt do setTVFace msh j faceArray[j]

    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open BP: R2Hell 3D Model" \
types:"3D Model (*.RF2)|*.rf2"
--historyCategory:"3D Model chunk
format "fname: %\n" fname
   
ReadModelFile fname
```
(startaddress of counts (0x234) to be modified, too, for other models)



RF2_3dsmax.JPG (81.44 KiB) Viewed 254 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-01T09:09:50+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

start of counts (check it for other models!):



STS_hummer.jpg (178.55 KiB) Viewed 251 times
## Post #5
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-01T11:10:10+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

shakotay2, it's good! 
But me need import script with support bones and animations. Just models can be easy imported with official VEEchange plugin or with using NinjaRipper.

I'm more 3d artist than programmer, so i'm can't writing something for import by himself =( 
I don't know MaxScript. I just hope, what someone writing that script if format is really so easiest. The hope it's all what i can do in this situation, unfortunately =(

I'm already created some models of characters for my "nonamed' mod of this game, and i want transfer animations from original models to new. Also i want change ingame cutscenes models. Models are exactly the same in structure, but i give link to samples of one cutscene just in case: [http://www.mediafire.com/download/78ls8 ... CENE-1A.7z](http://www.mediafire.com/download/78ls868133yzpos/SCENE-1A.7z)


There is screens how looks the official RF2Viewer:
[http://fs5.directupload.net/images/160501/xfk8owkk.jpg](http://fs5.directupload.net/images/160501/xfk8owkk.jpg)
[http://fs5.directupload.net/images/160501/bmi8dxtc.jpg](http://fs5.directupload.net/images/160501/bmi8dxtc.jpg)
[http://fs5.directupload.net/images/160501/xyiwhzqz.jpg](http://fs5.directupload.net/images/160501/xyiwhzqz.jpg)

And 3ds max with VEExchange from LevEditor:
[http://fs5.directupload.net/images/160501/5u97x85i.jpg](http://fs5.directupload.net/images/160501/5u97x85i.jpg)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-01T17:06:30+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from StreamThread
>
> But me need import script with support bones and animations.that's not a "15 minutes job", so sry.

> There is screens how looks the official RF2Viewer:does this viewer have an export option (for skeleton bones etc.)?
Is there an option to export the mesh? 
Guess noone will care just for "bones and animations" without dealing with the mesh:



KIR_girl.jpg (117.8 KiB) Viewed 227 times

(uncomplete, should be about 16 submeshes or so)
## Post #7
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-01T19:37:11+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from shakotay2
>
> that's not a "15 minutes job", so sry.
Of course i understand it and can wait as long as required. Thank for your help.


> Reply from shakotay2
>
> does this viewer have an export option (for skeleton bones etc.)?
Is there an option to export the mesh?
The point is that is not. If it is was be possible, i'm not start this thread. Sry for my english, if i'm unclear write. 

Something like it might be found only in _RF2View tool from leaked sdk for Vital Engine 3.0 ("The Precursors", "White Gold" games). In Menu of program have button with interesting name "Send to Max", but it requires new version of VEExchange plugin for Vital Engine 3.0. These plugins never leaked.
[http://fs5.directupload.net/images/160501/xupys8gs.jpg](http://fs5.directupload.net/images/160501/xupys8gs.jpg)

I'm not sure what it may be useful even with reverse engineering, but unofficial SDK for The Precursors can be found [here](http://www.moddb.com/games/the-precursors/downloads/the-precursors-sdk).

Ask developers is without avail, someone already tried. Their сompany has been closed.
## Post #8
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-06T07:05:20+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

Well, then maybe someone can tell me, where in this RF2 files is stored animation data? I'm can recreate all skeletons and hope so is possible just to copy hex data of anims from original models to new characters. 

Of course, hexing is hard for me, so detailed manual will desirable. But i will try to do it anyway. It's very important for me.

Thanks in advance.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-06T13:32:05+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from StreamThread
>
> Well, then maybe someone can tell me, where in this RF2 files is stored animation data?guess, there's no "Animation" data in your uploaded RF2 files (Actor folder). But you could search for "Bip" in KIR_GIRL_1.RF2 to find the bones, which are widely spread therein (up to 0xB49FC).

(Not sure if you know the difference between skeleton/skinning and animation.
Search for "idle", "walk", "run" in filenames, or in files assumed to contain animations.)

> and hope so is possible just to copy hex data of anims from original models to new characters.(You mean "to copy the skinning", don't you?)

Keep in mind that copying the skinning requires the original and new mesh to be very similar.
(Even with the skeletons assumed to be identical.)
From my experience copying fails if the vertex counts of meshes are too different.

(Use of existing animations requires the bone count and bone names to be identical in the original files and your new character.
Also you need to know how characters and animations are linked together. May be simple such as by the file names - diablo, mesh/skeleton: Adria.app, anim: Adria_walk_01.ani)

btw: does the RF2_viewer show animations if you load KIR_GIRL_1.RF2 for example from a folder where only this file is contained? (There is data "around" the bone names in the RF2 file which I can't identify.)
## Post #10
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-06T15:55:24+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

shakotay2

No, RF2 files contain all animations is absolute exactly. I'm already have exported characters with new animations from other games. 


Description of RF2 format possibilities from SDK:

> 1. Format possibilities.
>
> 
>
> 
>
> RF2 files intended for storage models of Vital Engine ZL 2.0.
>
> 
>
> In Vital Engine 2.0 uses skeletal animation.
>
> 
>
> RF2 file contain next bank of data:
>
> 
>
> *Skinned mesh 
>
>  Mesh (triangles and verticles), linked to bones; optional - LOD levels.
>
> 
>
> *Sets of bones with used animations
>
> 
>
> Skeleton for Skinned mesh.
>
> 
>
> * Information about bones partition groups
>
> 
>
> See Breaking bones into groups.
>
> 
>
> *Curve of character movement
>
>  See Characters Movements.
>
> 
>
> *List of materials, used by model.
>
> 
>
> See Names of materials.
>
> 
>
> * HitMesh
>
> See HitMesh
>
> 
>
> *Collision boxes with used animations
>
>  See Collision Boxes
>
> 
>
> * Additional information
>
> Distances of changing LOD-levels, order of simplify the skeleton.

This is from RF2_files.rtf file, which includes SDK. But original of file only on Russian language. 
There is link: [http://www.mediafire.com/download/q425a ... _files.rtf](http://www.mediafire.com/download/q425a4g5vgidcit/RF2_files.rtf)

I'm can try to translate it, but then sorry in advance for my breakin-english.

Also i'm can export one model to several files with differences in amounts of keyframes and animation quality export settings, if it may helped.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-06T16:13:54+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from StreamThread
>
> No, RF2 files contain all animations is absolute exactly.ok, do you know this from the rtf you've uploaded or from using the RF2_viewer? If the latter, could you try out the edit from my previous post?

> Also i'm can export one model to several files with differences in amounts of keyframes and animation quality export settings, if it may helped.well, that could help. (Just asking myself why you didn't tell this sooner?)

Could you export from KIR_GIRL_1.RF2, please, possibly uncompressed animations (and/or highest quality).
50 keyframes should be enough, but it should be "raw" frames, no interpolation or such.

An exported skeleton would be nice, too. 

edit: got some translation(?) data but maybe the values are to similar?
spine
3.869141 -0.190674 -0.366943
3.869141 -0.190674 -0.366943
3.869141 -0.190674 -0.366943
3.869141 -0.190918 -0.366943
3.869141 -0.191162 -0.366943
3.869141 -0.191406 -0.366943
3.869141 -0.192261 -0.366943
3.869141 -0.195679 -0.366943
3.869141 -0.196533 -0.366943
[...]
3.869141 -0.190796 -0.366943
3.869141 -0.190674 -0.366943
3.869141 -0.190674 -0.366943
3.871094 -0.190552 -0.366943
3.871094 -0.190674 -0.366699
3.871094 -0.190552 -0.366699
3.869141 -0.190674 -0.366943
3.871094 -0.190552 -0.367188
3.871094 -0.190552 -0.367188
3.871094 -0.190552 -0.367188
3.871094 -0.190552 -0.367188

clavicle
-2.267578 1.079102 4.824219
-2.267578 1.079102 4.824219
-2.269531 1.079102 4.824219
-2.273438 1.078125 4.820313
-2.275391 1.078125 4.820313
-2.277344 1.078125 4.820313
-2.281250 1.078125 4.820313
-2.283203 1.078125 4.820313
-2.287109 1.078125 4.816406
-2.289063 1.078125 4.816406
[...]
-2.240234 1.087891 4.828125
-2.242188 1.086914 4.824219
-2.259766 1.083984 4.812500
-2.279297 1.082031 4.804688
-2.279297 1.082031 4.804688
-2.273438 1.082031 4.804688
-2.273438 1.082031 4.804688
-2.273438 1.082031 4.804688
-2.273438 1.082031 4.804688
-2.273438 1.082031 4.804688

> Reply from StreamThread
>
> I'm already have exported characters with new animations from other games.just for curiosity: copied or new created animations?
## Post #12
- Username: E3245
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 20, 2015 9:35 pm
- Post datetime: 2022-01-14T01:17:17+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

Sorry for necroing this thread, but I have managed to write a working Noesis script using all available information from this thread and using the included debug symbols shipped with the game and the SDK to figure out the data structures and calculations for the *.RF2. So far, the script can read hitboxes, meshes, bone groups, and bones.

However, the animations are a pain to figure out and I need some help interpreting that. I've looked around for animations in the game directory, but I could not find any external animation files. It seems like it's embedded in the files (according to the documentation) on export.



The header is 0x5A bytes long, includes offsets to different sectors of the file (Bones, Mesh, Hitbox, Movement Vectors, etc.), FOV, LOD Distances in floats, Bounding Boxes.

Here's the header extracted from Gihidra:

```
    unsigned short int Signature;
    unsigned char version;
    unsigned char LODCount;
    unsigned short framescount;
    unsigned long Materials;		// offset to array
    unsigned long BipedBones;		// offset to array
    unsigned long SkinedMesh;		// offset to array
    unsigned long MovementVectors;	// offset to array 
    unsigned long HitMesh;		// offset to array
    unsigned long BonesGroups;		// offset to array 
    unsigned long CollisionBoxes;	// offset to array
    struct T3DBOX ModelBBox;		// 3x3 Matrix of a bounding box
    float CameraFOV;			// In Radians
    unsigned long flags;
    float LODDistance[6];
};

```


Longs are 4-byte integers, T3DBox is a 3x3 matrix.

With the information here, I was able to determine how the faces and vertices worked (thanks shakotay2 for the pointers  ), then by using IDA Pro and Gihidra, I was able to figure out the bone format along with positions/rotations of the initial bones.

Bone names have a 20-byte maximum length, followed by Parent, GroupID, and if there's a special label in one of the bones. The actual initial positions are at the very end of the chain, which is how I was able to load them in Noesis.
This is where it gets complicated. I got an int that is the block size of the entire animation for that bone, a short that is the array size count of both a Vector3 (3 * float16) and Quat (4 * short), and then another short that is the frame index. Not all frames are listed.



This is where I'm having issues: I'm trying to figure out the relation of those extra vectors and quats and how they add up to the actual keyframe. I tried using IDA and Gihidra to see how the data is used but it only goes so far. If I can figure that out, then I can read in the animation in Noesis and export them, which is the last part of this.

Here's some extra models to test with, although the ones in the OP are also good to test with:
[https://www.mediafire.com/file/i140i0nf ... ls.7z/file](https://www.mediafire.com/file/i140i0nf8sfziwk/BP+rf2+models.7z/file)

Attached is a noesis script that can read in most *.RF2 in Boiling Point: Road to Hell/Xenus 1.
[fmt_vitalengine_rf2.zip](https://xentaxbackup.github.io/file/21599_fmt_vitalengine_rf2.zip)
## Post #13
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-01-14T06:46:12+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from E3245 ↑Fri Jan 14, 2022 9:17 am at Fri Jan 14, 2022 9:17 am
>
> 
Sorry for necroing this thread

Necroing is always fine here if you're contributing something to the thread, and you definitely contributed here!
## Post #14
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-01-16T18:49:48+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

> Reply from E3245 ↑Fri Jan 14, 2022 9:17 am at Fri Jan 14, 2022 9:17 am
>
> 
I got an int that is the block size of the entire animation for that bone, a short that is the array size count of both a Vector3 (3 * float16) and Quat (4 * short), and then another short that is the frame index. Not all frames are listed.

Hello.
I am author of this topic (On another login because i'm often forgot a mail passwords  ).
On the past time i'm figure out almost whole format. I wrote my MaxScript and had issues with applying the vertex weights. And not researhed animations because of that.
How i see you got luck with skinning, nice job.

Animation keys are packed and seems what would be unpacked with the functions TPacked3dVECTOR and tagPackedQUAT from verender2.dll. I provide them in attach, but check maybe Gihidra pseudocode will be more clearly..
[VE_PackedVectors.zip](https://xentaxbackup.github.io/file/21627_VE_PackedVectors.zip)
## Post #15
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-02-09T19:39:12+00:00
- Post Title: Boiling Point: Road to Hell *.RF2

Trying to research bone anim format. By reverse engineering the verender2.dll file with included *.pdb, managed to get bone structures. Turned out what they having the following format:

```
    char name[20];
    byte parentID;
    byte groupID;
    byte rootGroupID;
    uint32 packedAnimSize;
    if( packedAnimSize )
    {
        PACKED_ANIM packedVectors;
        PACKED_ANIM packedQuats;
    };

};
```


PACKED_ANIM structure is next:

```
    uint32 numPackedItems;
    PACKED_VECTOR3 item[numPackedItems]; //Vectors or Quats packed to 3x uint16 per item. Unpacking functions is included.
    ARRAY packedIDs;
    ARRAY originalIDs;
    uint16 numFrames; //total frame count for bone. Often same value as in header. Useful for determine structure ending.
};
```


Array structure in turn:

```
    uint16 numItems;
    uint16 numBits; //per item
    
    uint64 item : numBits  // in the count of numItems. uint64 because numBits can be 48. Bitfield padding off
    ubyte numBitsKey : 8;
    uint64 mask : numBits; //not used?
};
```


Main problem here is how to allocate correct size of items in array. No matter how I tried, I cant figure out. Obvious things such as numItems mul to numBits and align to ceil bytes dont fit here.
This is the last frontier in the fully research of the format. In attch I privide my 010 editor template for parsing bones and verender2.dll & pdb.

[ve_boneanim_research.zip](https://drive.google.com/file/d/1EBLBm9F-5vPvHRZU077cWPAdwWRlSkvX/view?usp=sharing)
## Post #16
- Username: E3245
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 20, 2015 9:35 pm
- Post datetime: 2022-02-09T21:50:52+00:00
- Post Title: Re: Boiling Point: Road to Hell *.RF2

> Reply from grandshot ↑Thu Feb 10, 2022 3:39 am at Thu Feb 10, 2022 3:39 am
>
> 
Trying to research bone anim format. By reverse engineering the verender2.dll file with included *.pdb, managed to get bone structures. Turned out what they having the following format:
Code: Select allstruct BONE {
    char name[20];
    byte parentID;
    byte groupID;
    byte rootGroupID;
    uint32 packedAnimSize;
    if( packedAnimSize )
    {
        PACKED_ANIM packedVectors;
        PACKED_ANIM packedQuats;
    };

};

PACKED_ANIM structure is next:
Code: Select allstruct PACKED_ANIM( int itemType ) {
    uint32 numPackedItems;
    PACKED_VECTOR3 item[numPackedItems]; //Vectors or Quats packed to 3x uint16 per item. Unpacking functions is included.
    ARRAY packedIDs;
    ARRAY originalIDs;
    uint16 numFrames; //total frame count for bone. Often same value as in header. Useful for determine structure ending.
};

Array structure in turn:
Code: Select allstruct ARRAY {
    uint16 numItems;
    uint16 numBits; //per item
    
    uint64 item : numBits  // in the count of numItems. uint64 because numBits can be 48. Bitfield padding off
    ubyte numBitsKey : 8;
    uint64 mask : numBits; //not used?
};

Main problem here is how to allocate correct size of items in array. No matter how I tried, I cant figure out. Obvious things such as numItems mul to numBits and align to ceil bytes dont fit here.
This is the last frontier in the fully research of the format. In attch I privide my 010 editor template for parsing bones and verender2.dll & pdb.

ve_boneanim_research.zip

From what I gathered in BipedBones section of the RF2 file, each bone has the following properties:

```
char* name (Always 0x15)
byte parent;
byte group;
byte rootGroupID (I think this is supposed to be for special bone names);
uint32 MemoryCommitSize;
uint32 array_count
packed3DVector* v
packedQuat* q

```


The animation format is a series of Vector3 half floats (x, y, z) followed by a series of Quaternions shorts (x, y, z, w), so they're 1-to-1 with each other. There's always at least 2 array_count even for objects that assumingly have no animations to them (ded-ak47-low).

I still have not figured out the operations needed to turn it into a standard animation format, but I think it requires using Slerp(quat) and Lerp(vector), several unknown math operations, then converting the resultant 4x3 Matrix into a TAnimKey structure.

That's all I know so far. I've been busy writing tools to decompress the *.dt textures in the cache folder, parsing the map format, and documenting (and eventually writing tools to decompile) the LV2 file structure. I'm still trying to figure out the layer masks and the detail object layer but it's coming along.

EDIT: Upon further inspection, I was looking at the wrong place for this. I see that the sequence of data where i assumed the Quats were is actually a TShrinkedArray of elements or struct ARRAY in the quoted data structure.

According to IDA Pro, allocating a TShrinkedArray may look like this: 
```
{
  __int64 v2; // rax
  int v3; // ecx
  unsigned int *element; // edi
  unsigned int *v5; // eax
  size_t v6; // [esp-8h] [ebp-Ch]

  v2 = s * this->nBits + 31;
  v3 = ((BYTE4(v2) & 0x1F) + (int)v2) >> 5;
  if ( v3 != (this->nBits * this->array_size + 31) / 32 )
  {
    element = this->element;
    this->array_size = s;
    v5 = (unsigned int *)operator new(4 * v3);
    v6 = 4 * ((this->nBits * this->num + 31) / 32);
    this->element = v5;
    memmove(v5, element, v6);
    if ( element )
      operator delete(element);
  }
}
```
## Post #17
- Username: E3245
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 20, 2015 9:35 pm
- Post datetime: 2022-02-21T00:29:20+00:00
- Post Title: Re: Boiling Point: Road to Hell *.RF2

Animations support is almost done, just got to figure out how to sync the frames together.



I wrote up a long post explaining my findings but it got wiped before I got a chance to post it   

In short, I had to look around in the dlls and the RF2_Export.dlu that came with pdb symbols to figure out some information, from the Shrinked Array stuff, to the Vector3s and Packed Quats to Quats conversion. Shrinked Arrays are still a bit of a mystery with how they're structured but it's essential to get the proper key timings.

I'm not sure if I'll support movement vectors since it's a bit more complicated than it seems. We'll see though.
## Post #18
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-02-21T21:18:18+00:00
- Post Title: Re: Boiling Point: Road to Hell *.RF2

I'm also can't find a way how to allocate a proper size of these shrinked arrays. They should contain a 'Pack Indexes' which i'm imagine as ids of packed vectors & quats, and 'Original Indexes' which may pointing to frame positions on timeline. 



2022-02-21.png (146.57 KiB) Viewed 33 times



Anims in Vital Engine 2.0 should be framerate independent because they speed in fps sets in model settings.



Movement Vectors it's just a positions of root bone per each frame on timeline.
