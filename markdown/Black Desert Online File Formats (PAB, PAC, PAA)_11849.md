## Post #1
- Username: ArthainBaka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 27, 2014 10:24 am
- Post datetime: 2014-08-27T02:28:04+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

Update:
I believe I've cracked pretty much all of it just need to determine the format of the keyframe values and we are done.
Explaination of converting the Animation's compressed scale, rotation & position can be found in my other post [here](http://forum.xentax.com/viewtopic.php?f=16&t=11849&p=97712#p97712).

I feel I've almost figured out the details for all of these formats but I may need some input for the last stretch. Huge credits go to [Ekey](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=23853) for his PAZUnpacker_CBT2 (without which I'd have nothing to do!), and to [chrrox](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=4722) for their Noesis script (which is pretty much the foundation of what I've got). There are still a few things that aren't quite complete, primarily with the PAA files which I believe have some form of compression which I talk about in their section any input here would be awesome.

For those not familiar with the files:

PAC - This file represents the model format (chrrox mapped most of this out in their script)
PAB - This file represents the skeleton format which various models depend on (chrrox mapped this out in their script)
PAA - This file represents the animation format, one file per animation
Common Structures
Below are some of the common structures in each of these files, listing them here will save some space and typing. They are pretty self explainatory. If anyone knows more about the unknown data in the FileHeader I'd be interested to know what it is, it hasn't seemed to be required so I haven't really looked at it.

```
{
	char					 fileId[4];
	unsigned_int16		fileVersion;

	unsigned_int8		 unknown[10];
} FileHeader;

typedef struct Matrix4x4
{
	float 		data[4][4];
} Matrix4x4;

typedef struct Vector3
{
	float		x;
	float		y;
	float		z;
} Vector3;

typedef struct Quaternion
{
	float		x;
	float		y;
	float		z;
	float		w;
} Quaternion;

typedef struct CompressedVector3
{
	int16		x;
	int16		y;
	int16		z;
} CompressedVector3;

typedef struct CompressedQuaternion
{
	int16		x;
	int16		y;
	int16		z;
	int16		w;
} CompressedQuaternion;

```

PAB File Format
This file starts with the standard FileHeader structure with the main data starting at 0x00000010 which lists the number of bones in the file and is followed by the array of bones.
I believe the unknown data is just a padding or chunk end or something, either way it doesn't seem to be required.
Once again, credit to [chrrox](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=4722) who's Noesis script is the framework for this.

```
{
	unsigned_int32		boneHash;
	unsigned_int8		 boneNameLength;
	char				    boneName[boneNameLength];
	unsigned_int32		boneParent;

	Matrix4x4			  boneMatrix;
	Matrix4x4			  boneMatrixInverse;
	Matrix4x4			  boneLocalMatrix;
	Matrix4x4			  boneLocalMatrixInverse;
	Vector3			    boneScale;
	Quaternion		    boneRotation;
	Vector3			    bonePosition;

	unsigned_int8		 unknown[2];
} Bone;

struct BoneFileFormat
{
	FileHeader		 fileHeader;

	unsigned_int16	boneCount;
	Bone 				bones[boneCount];
};

```

PAC File Format
Moving up in complexity slightly, this file has the mesh data. Each mesh has a texture name attached to it, I believe this is a base name so textures with other semantics (like normal map, ambient occlusion, specular power, etc) can be automatically added by searching for their relevant semantic id which is appended to the base texture name. I haven't really looked into determining what PAB file is supposed to be used for these yet, if it's not in the file then it may be a matter of searching the directory (and parent directories with a depth restriction) to find a PAB file which has the bone hashes that the PAC file contains. I've only included the version 259 of this, I haven't seen where the 513 version chrrox also uses is used (but there are a lot of models so easily possible I've missed it!)
Once again, credit to [chrrox](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=4722) who's Noesis script is the framework for this.

```
{
	Vector3			   position;
	unsigned_int8		normals[4];			// Commented out by chrrox
	unsigned_int16     uv[2];
	unsigned_int8      colour[4];			// Commented out by chrrox
	unsigned_int8      boneIndices[4];
	unsigned_int8      boneWeights[4];
} VertexBuffer;


typedef struct LOD
{
	unsigned_int16			vertexCount;
	VertexBuffer           vertexBuffer[vertexCount];
	unsigned_int32			faceCount;
	unsigned_int16			faceIndices[faceCount];
} LOD;

typedef struct Mesh
{
	unsigned_int8			 textureNameLength;
	char			          textureName[textureNameLength];
	unsigned_int16			flag;

	LOD				        lodArray[3];
} Mesh;

struct ModelFile
{
	FileHeader 		      fileHeader;

	unsigned_int8			 boneCount;
	unsigned_int32			boneHashArray[boneCount];
	unsigned_int8			 usedBoneCount;
	int8			          usedBoneArray[usedBoneCount];

	unsigned_int32			totalVertices;
	unsigned_int32			totalFaces;
	unsigned_int16			meshCount;

	Mesh 			         meshes[meshCount];
};

```

PAA File Format
This file was a pain, it's easy knowing what data needs to be in an animation file yet people find so many different ways to do so. I believe there is some form of compression being used within this file for the scale, rotation and position (and possibly key frame / frame time).
The file starts the same as normal with the FileHeader followed by a count which for this file represents the number of bones in the animation, following this is 8 bytes of data (first 4 I believe are a float for the total animation time) and from here the bone animation data starts.
The animation data appears to compress all of the floats (e.g. time frame, scale, rotation and position components) into half's. I'm not so good at decryption so maybe someone can help out, at the least we can logically infer from the scale values that "E8 03" should equal 1.0F. Once again I such ad decompression so I'd love some input here.
With this knowledge the format for the animation file is as follows:

```
{
	half						keyframe;
	CompressedVector3	 keyframeScale;  // Multiply values by 0.001F to get float value
} ScaleData;

typedef struct RotationData
{
	half						 keyframe;
	CompressedQuaternion	keyframeRotation;  // Multiply values by max value of their sign to get float value
                                                                  // value == 0 : (0.0F)
                                                                  // value < 0 : (value * 32768.0F)
                                                                  // value > 0 : (value * 32767.0F)
} RotationData;

typedef struct PositionData
{
	half						keyframe;
	CompressedVector3	 keyframePosition;  // Multiply values by 0.1F to get float value
} PositionData;

typedef struct AnimBoneData
{
	unsigned_int32		boneHash;

	unsigned_int16		scaleKeyframeCount;
	ScaleData			  scaleData[scaleKeyframeCount];

	unsigned_int16		rotationKeyframeCount;
	RotationData		  rotationData[rotationKeyframeCount];

	unsigned_int16		positionKeyframeCount;
	PositionData		  positionData[positionKeyframeCount];
} BoneAnimationData;

struct Animation
{
	FileHeader			 fileHeader;
	unsigned_int16		boneCount;

	float				   animationDuration;	// ?
	unsigned_int8		 unknown[4];			 // ?

	AnimBoneData        	boneData[boneCount];
};

```
## Post #2
- Username: BloodForce
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 30, 2013 10:49 pm
- Post datetime: 2014-08-27T05:18:40+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

You forget .pam (object files)
i think all our answers in \object\parc.exe
help for parc.exe, getting in korean windows

> Pearl-Abyss Resource Compiler Ver1.0 01:11:13 08/25/14
>
> 
>
> Pearl-Abyss RC Command-line Interface:
>
>    -h [--help] Help
>
>    -i [--input_file] arg input file name
>
>    -o [--output_file] arg output file name
>
>    -I [--input_files] Arg input file name list
>
>    Save -p [--output_path] arg the output file folder
>
>    -b [--base_path] top as a reference when creating sub-folder structure path arg
>
>    create sub-folder structure when writing files -k [--keep_subpath] in the output folder,
>
>    If the file has -w [--overwrite] overwrite the same name exists
>
>    -l [--log_output_list] logging output file list
>
>    compilation -a [--all] for all files
>
>    performed recursively for -r [--recursive] in the sub-folder
>
>    create a texture reference list -t [--texture_list] mesh file
>
>    -g [--retargetting_animation] for generating animation retargeting
>
>    -v [--verbosity] detail message output
>
>    Doing a -s [--single_thread] single-threaded
>
>    Perform compile only files --bone_only pb
>
>    -m [--skinned_mesh_only] only pc file compilation
>
>    Compiled by -e [--check_coexist] Raw data files are guys and pair
>
>                                     Verify that the coexistence
>
>    -c [--change_mode] arg object to change compiler (c followed by n (General)
>
>                                     r (r3m) c (Curly Religion) h (House) l (LOD)
>
>                                     Put the flag should generate a file for the flag
>
>                                     k (key frame Animation) m (morphing) p (pam) text
>
>                                     Reads the file.
>
>    Do other files created in r3m -x [--change_readfile] is not the Text
>
>    Change the deviation -u [--reduce_deviation] the arg object must
>
>    If -d [--delete_readfile] the object mode and delete the file read.
>
> 
>
> 
>
> 
>
> 
>
> Default: PARC.exe -cp -a
>
> 
>
> Object vertex to reduce levels (less if you are using does anhal.)
>
> -u + a ~ f a = 0.5 (-ua)
>
> b = 1.0 (-ub)
>
> c = 1.5 (-uc)
>
> d = 2.0 (-ud)
>
> e = 2.5 (-ue)
>
> f = 3.0 (-uf)
>
> If the change to all sub-folders, you can simply put the -r.
## Post #3
- Username: ArthainBaka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 27, 2014 10:24 am
- Post datetime: 2014-08-27T08:48:40+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from BloodForce
>
> You forget .pam (object files)
i think all our answers in \object\parc.exe
help for parc.exe, getting in korean windows

I had a look at it but for whatever reason my IDA chucks a fit when it tries to analyse the file and I can't get it to run for me (though maybe it's because I'm on an English install with Korean language pack). Either way I had no luck with it, or analysing the main .exe for the client.
I haven't really looked into the PAM files, so I'm not really sure what they are yet. I'm more interested in the model + animations. Once I've got those I might look at the PAM files.


Anyway I think I've cracked it!

Rotation Data
The rotation data it's being stored in four int16's and a bit of trickery to deserialize it into a float. Basically you just need to read the int16 value and and divide it by the largest value (for the given sign) to yeild the float data for the quaternion.
So if we look at some sample data:

```
7E A5 82 5A 00 00 00 00

```

If we break this into the format we know it's in (an array of four int16's) we get the following:
Break this into an array of four int16's

```
Decimal: [-23170, 23170, 0, 0]

```


Now we can convert it into float data using some simple math (my psuedo code always tends to be C++ for some reason >.>):

```
#define FMIN_INT16    32768.0F     // Positive value to preserve sign on division

// Unpacks int16 value (of a quaternion component) from the .PAA format into a float
float UnpackValue(int16 value)
{
    if (value < 0)
    {
        return ((float)value / FMIN_INT16);
    }
    else if (value > 0)
    {
        return ((float)value / FMAX_INT16);
    }

    // If we get this far then the value has to be 0
    return (0.0F);
}

```


So if we apply this to the data we get the following (which now surprisingly looked like real quaternion values):

```

```

Scale Data
Every single file I've looked at has had the same E8 03 values, interestingly this nicely converts to an int16 as 1000.
Without spending time looking into it I'd say it's pretty safe to assume this is a fixed decimal point representation, so just mutliply by 0.001F (so people know we want a float, otherwise you could just divide by 1000) to get the data as a float (results with 1.0F which I think is obviously a good standard value for bone scale):

```
// Multiply all values by 0.001F to yield float
float: [1.0F, 1.0F, 1.0F]

```

Position Data
This is where I may be wrong but it seems to be correct for all the models I'm cross-referencing with positions of exported in Maya (standard PAB bone matrices used).
It seems this is just another fixed decimal point value, which is shifted by 1, so multiply the int16 by 0.1 or divide by 10 (outcome will be the same so personal preference really, probably safer dividing by 0.1 as then people know the output is a float and not a decimal which would ignore the decimal values)
From data of the Windmill model, in Maya the "Bone_VerticalAxis" has the following position [-1371.124, -0.001, -0.000], now we know it's from different bone data so really if we can get one value close to this and have the process work for the rest of the bones similarly we can pretty much assume it's correct (or good enough).
Black Desert seems to not use a world scale of 1 = 1m (unless this windmill is almost 1.4km high >.>) so given that it's less than 1 unit = 1m then the single decimal resolution isn't really that bad (I'm guessing they use 1 unit = 1mm).
Anyway, data and results this one like scale is pretty simple:

```
// Multiply values by 0.1F for float
float: [-1371.1F, 0.0F, 0.0F]  // Pretty much identical to Maya target of [-1371.124, -0.001, -0.000]

```


So nice and easy!
That just leaves the keyframe values the be determined and we'll have a complete functional format. Hopefully I'll get enough time to finish it today ^.^
## Post #4
- Username: Rynage
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 31, 2013 9:55 pm
- Post datetime: 2014-08-27T09:16:54+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

Just wow! You guys are incredible. If you will be able to unpack all those files - just no words.
## Post #5
- Username: ArthainBaka
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 27, 2014 10:24 am
- Post datetime: 2014-08-27T09:38:33+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Rynage
>
> Just wow! You guys are incredible. If you will be able to unpack all those files - just no words.
I think I only did the easy part!
[Ekey](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=23853) was the one that made the unpacker which makes all of this possible, I can guarantee without it I wouldn't have even looked into this!
And [chrrox](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=4722) provided enough of a framework with his Noesis script that I could figure out what I have so quickly.
I can not thank those two enough.

I do a lot of game development so I think that helped me a lot since I work with these structures on pretty much a daily basis, I've never tried to unpack any file formats before (actually I recall that I datamined Fury when it came out but the files were essentially plain text) so this was actually really really fun (and oddly relaxing).

I don't think I have enough time to get a working script with Noesis today though as I need to go out for the rest of the night shortly. Tomorrow should be plenty of time to learn enough Python (for a programmer I often wonder why I know almost nothing about Python) and enough of the Noesis API to get something working.
## Post #6
- Username: Rynage
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 31, 2013 9:55 pm
- Post datetime: 2014-08-27T13:44:53+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from ArthainBaka
>
> Rynage wrote:Just wow! You guys are incredible. If you will be able to unpack all those files - just no words.
I think I only did the easy part!
Ekey was the one that made the unpacker which makes all of this possible, I can guarantee without it I wouldn't have even looked into this!
And chrrox provided enough of a framework with his Noesis script that I could figure out what I have so quickly.
I can not thank those two enough.

I do a lot of game development so I think that helped me a lot since I work with these structures on pretty much a daily basis, I've never tried to unpack any file formats before (actually I recall that I datamined Fury when it came out but the files were essentially plain text) so this was actually really really fun (and oddly relaxing).

I don't think I have enough time to get a working script with Noesis today though as I need to go out for the rest of the night shortly. Tomorrow should be plenty of time to learn enough Python (for a programmer I often wonder why I know almost nothing about Python) and enough of the Noesis API to get something working.

Yeah I see your point. Anyway I was aiming on .PAA files.
For now, it's not possible to unpack this to work.
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-01-03T14:15:53+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

Hi

Here is an animation importer for models from this game.
It requires Blender version 249 and Python 26.
I used chrrox script for Noesis [viewtopic.php?f=16&t=10909](http://forum.xentax.com/viewtopic.php?f=16&t=10909) and ArthainBaka file format research .

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-pac file - for importing a skinned mesh
-pab file - for importing a skeleton
-paa file - for importing an animation
-pam file - for importing  static objects

Updated 2015-01-10:
-added pam importer

Updated 2015-01-06:
- added new animation importer
[BlackDesert[2015-01-10].zip](https://xentaxbackup.github.io/file/8462_BlackDesert[2015-01-10].zip)
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-01-04T16:00:29+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Szkaradek123
>
> Hi

Here is an animation importer for models from this game.
It requires Blender version 249 and Python 26.
I used chrrox script for Noesis viewtopic.php?f=16&t=10909 and ArthainBaka file format research .

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-pac file - for importing a skinned mesh
-pab file - for importing a skeleton
-paa file - for importing an animationHi Szkaradek123, my friend, the script runs perfectly, great work
## Post #9
- Username: koreago
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 31, 2009 12:41 am
- Post datetime: 2015-01-08T02:40:17+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

animation import error? help me.. 
[K-2.jpg](https://xentaxbackup.github.io/file/8448_K-2.jpg)
## Post #10
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2015-01-12T18:59:51+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Szkaradek123
>
> Hi

Here is an animation importer for models from this game.
It requires Blender version 249 and Python 26.
I used chrrox script for Noesis viewtopic.php?f=16&t=10909 and ArthainBaka file format research .

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-pac file - for importing a skinned mesh
-pab file - for importing a skeleton
-paa file - for importing an animation
-pam file - for importing  static objects

Updated 2015-01-10:
-added pam importer

Updated 2015-01-06:
- added new animation importer

Thanks for the importer!!
is any way to get the correct bone names?
## Post #11
- Username: ghgldk11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 31, 2014 4:08 pm
- Post datetime: 2015-04-26T12:22:33+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

anyone know that where is the eyebrow and eye iris or pupil image files? 
recently I ported the Valkyrie model from the Korean Black Desert Client into SFM and Gmod. 
but actually I couldn't find the texture files of eyebrows, pupil or iris. so i used the eyebrow image file from the Vindictus. 
but you know, it is little bit awkward. I found the other things like body or face tattoo, eye line make-up, preview image of customization but 
damn.. there is no eye brow, iris .dds file! I think it should be inside of PAT files. 
PAT = Peal abyss Texture, isn't it? lol  if you guys can rip those PAT files too. it must be wonderful! and i will appreciate about that!
## Post #12
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-04-26T17:45:43+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

Would anyone that still has the BDO tools posted in [viewtopic.php?f=10&t=10879](http://forum.xentax.com/viewtopic.php?f=10&t=10879) but later removed mind pm'ing me a download link? Not being able to extract the files makes it hard to use the tools posted here
## Post #13
- Username: dantesai
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Feb 09, 2014 10:42 am
- Post datetime: 2015-05-06T10:34:12+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

@Szkaradek123 run step 3 alt+P just popup error window"python script error:check console"
## Post #14
- Username: gfhjkm11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2012 7:38 pm
- Post datetime: 2016-02-03T04:51:17+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

Thx for scripts and Tools .. Work perfect as import Model and import Animation ( 100 % ) in Blender 2.49b



blackdesert_1.png (148.65 KiB) Viewed 3461 times
## Post #15
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-03-01T15:00:08+00:00
- Post Title: Black Desert Online File Formats (PAB, PAC, PAA)

Do the tools used for extracting .paz exist anymore? if so, could someone please pm me?!
## Post #16
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2016-03-03T07:51:51+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Hi folks, I'm trying to make Noesis script to import animation. I have achieved some success, but the animation still loaded not correctly. Maybe someone knows what's the problem?
(you need to put skeleton file [.pab] in animation folder)
[fmt_Black_Desert_paa.7z](https://xentaxbackup.github.io/file/10551_fmt_Black_Desert_paa.7z)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-03T18:00:52+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Can't check it because I don't have paa files.

You could check the python script for blender from Marisuz
[viewtopic.php?f=16&t=11849&hilit=.paa](http://forum.xentax.com/viewtopic.php?f=16&t=11849&hilit=.paa)
and compare the results with yours.
## Post #18
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2016-03-03T19:06:03+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from shakotay2
>
> You could check the python script for blender from Marisuz
My script based on Marisuz script. 

> Reply from shakotay2
>
> and compare the results with yours.
Unfortunately the result is very different.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-05T20:34:24+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

I used shorts divided by 65535 instead of half floats and the walking anim looks better (a little bit like a spider  , but it walks).
## Post #20
- Username: kimheeseok
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 25, 2016 4:19 pm
- Post datetime: 2016-07-25T10:32:45+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

im failed animation  
help me plz!!
## Post #21
- Username: tnswls1002
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2016 2:55 am
- Post datetime: 2016-08-25T21:06:32+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

hello! 
im junior..

Running the blender file, 
The results obtained , except paa.

if input paa file, 
It was the result of the following....

plz help me...
[20160826_060123.png](https://xentaxbackup.github.io/file/11615_20160826_060123.png)
## Post #22
- Username: hassuny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 27, 2016 4:46 pm
- Post datetime: 2016-09-27T17:14:42+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Do the tools used for extracting .paz exist anymore? if so, could someone please pm me?!
## Post #23
- Username: Moonscapes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 21, 2016 3:04 pm
- Post datetime: 2016-11-02T01:24:16+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Is anyone able to upload the armor files? I don't have the game, and would really appreciate it if someone could.
## Post #24
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2017-01-14T13:50:59+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Skykila
>
> Hi folks, I'm trying to make Noesis script to import animation. I have achieved some success, but the animation still loaded not correctly. Maybe someone knows what's the problem?
(you need to put skeleton file [.pab] in animation folder)

this script is error for  "not found Utils.SkyUtils "
## Post #25
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-01-27T11:24:30+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Szkaraddek, Thanks for the scripts. I am able to import PAC and PAB files. However no luck so far with PAM (static object files)....after running the script nothing is loaded and I am not able to see any thing in the console either. Trying to extract some props and assets...

Any advise? 

> Reply from Szkaradek123
>
> Hi

Here is an animation importer for models from this game.
It requires Blender version 249 and Python 26.
I used chrrox script for Noesis viewtopic.php?f=16&t=10909 and ArthainBaka file format research .

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-pac file - for importing a skinned mesh
-pab file - for importing a skeleton
-paa file - for importing an animation
-pam file - for importing  static objects

Updated 2015-01-10:
-added pam importer

Updated 2015-01-06:
- added new animation importer
## Post #26
- Username: marmalade
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 12, 2016 6:17 am
- Post datetime: 2017-03-09T20:33:27+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Hopefully someone can advise how to import animation files properly.

I'm using blender 2.49b and python 26, using the script from Szkaradek123 I can import pac and pab files and all looks ok but when importing paa files I end up with a broken mesh that looks more like a spider than a human.

Am importing phw_00_nude_0001_noalpha.pac, the associated pab file and phw_00_00_stand_idle_00.paa but end up with this:



Capture.JPG (66.88 KiB) Viewed 671 times



Anyone know how to solve this?
## Post #27
- Username: miyuko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 23, 2017 8:59 pm
- Post datetime: 2017-04-23T14:57:14+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from marmalade
>
> Hopefully someone can advise how to import animation files properly.

I'm using blender 2.49b and python 26, using the script from Szkaradek123 I can import pac and pab files and all looks ok but when importing paa files I end up with a broken mesh that looks more like a spider than a human.

Am importing phw_00_nude_0001_noalpha.pac, the associated pab file and phw_00_00_stand_idle_00.paa but end up with this:
Capture.JPG

Anyone know how to solve this?
Me too...
## Post #28
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-04-30T22:44:11+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Same issue here...Anyone who has already successfuylly imported PAA animation, can you pls help.

Able to import PAC and associated PAB file. Both look scaled to same size. However loading any of the animation (PAA) associated with the PAB results in the armature getting deformed badly 


> Reply from miyuko
>
> marmalade wrote:Hopefully someone can advise how to import animation files properly.

I'm using blender 2.49b and python 26, using the script from Szkaradek123 I can import pac and pab files and all looks ok but when importing paa files I end up with a broken mesh that looks more like a spider than a human.

Am importing phw_00_nude_0001_noalpha.pac, the associated pab file and phw_00_00_stand_idle_00.paa but end up with this:
Capture.JPG

Anyone know how to solve this?
Me too...
## Post #29
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-04-30T23:10:07+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

PAC and PAB file imported


On loading PAA file
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-02T19:33:48+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Seems it's a matter of the blend-file version.
I used the files you sent me:
phw_00_nude_0001_noalpha.pac
phw_01.pab

phw_06_01_stand_idle_00.paa
phw_04_01_move_run_r_00.paa

with Blender249.blend as of 3.1.2015 (3rd January) and all works fine 
(apart from some oddities with the blender timeline window where the Play/Stop button had to be pressed several times)



phw_06_01_stand_idle_00-paa.JPG (61.48 KiB) Viewed 583 times
## Post #31
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-05-02T23:05:52+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Thanks for taking your time to look into this! Yes it does work with the 3rd Jan version of the blend file  Thanks again

> Reply from shakotay2
>
> Seems it's a matter of the blend-file version.
I used the files you sent me:
phw_00_nude_0001_noalpha.pac
phw_01.pab

phw_06_01_stand_idle_00.paa
phw_04_01_move_run_r_00.paa

with Blender249.blend as of 3.1.2015 (3rd January) and all works fine 
(apart from some oddities with the blender timeline window where the Play/Stop button had to be pressed several times)
## Post #32
- Username: newkuro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 18, 2010 1:55 pm
- Post datetime: 2017-06-27T05:35:44+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

black desert - new character(15_pdw) not import (.pac)  
help
## Post #33
- Username: ciabiss
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 25, 2017 9:46 pm
- Post datetime: 2017-11-25T15:01:25+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

i need help...
first i get an error in the blender console saying:
SyntaxError: Missing parentheses in call to 'print'
so i fix that and then this happened:
[blender_2017-11-25_07-48-49.png](https://xentaxbackup.github.io/file/13595_blender_2017-11-25_07-48-49.png)
## Post #34
- Username: Demrok
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 08, 2017 2:46 am
- Post datetime: 2018-01-04T06:08:00+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Is there an updated version of these scripts that is needed to run the .PAA extraction?
I am using blender 249 and the script fails and says "Missing parentheses in call to 'print' (inside blender)
I'm just trying to extract the animations, but I can not get it to work...
Anyone have any help/advice/tutorial?

Thanks!
## Post #35
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-11-03T12:41:36+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Szkaradek123
>
> Hi

Here is an animation importer for models from this game.
It requires Blender version 249 and Python 26.
I used chrrox script for Noesis viewtopic.php?f=16&t=10909 and ArthainBaka file format research .

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-pac file - for importing a skinned mesh
-pab file - for importing a skeleton
-paa file - for importing an animation
-pam file - for importing  static objects

Updated 2015-01-10:
-added pam importer

Updated 2015-01-06:
- added new animation importer
Can you please update the script? Its not working with many models in new recent game version
## Post #36
- Username: jreyesl85
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 28, 2016 10:05 am
- Post datetime: 2019-03-24T15:26:43+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

I used the method halftofloat from PAZ unpacker code to get 4bytes float values from 2bytes data representing float values
It worked for both formats PAC an PAB, even PAA keyframe values seem normal values but rotation and translation are quite weird, you can see tha t is moving but with an unacceptable result. Hope this put some light into this matter
## Post #37
- Username: jreyesl85
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 28, 2016 10:05 am
- Post datetime: 2019-03-24T15:30:34+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

public ushort FloatToHalf(float float32)
        {
            int si32 = BitConverter.ToInt32(BitConverter.GetBytes(float32),0);
            int num1 = si32 >> 16 & 32768;
            int num2 = (si32 >> 23 & (int) byte.MaxValue) - 112;
            int num3 = si32 & 8388607;
            if (num2 <= 0)
            {
                if (num2 < -10)
                    return (ushort) num1;
                int num4 = num3 | 8388608;
                int num5 = 14 - num2;
                int num6 = (1 << num5 - 1) - 1;
                int num7 = num4 >> num5 & 1;
                int num8 = num4 + num6 + num7 >> num5;
                return (ushort) (num1 | num8);
            }
            if (num2 == 143)
            {
                if (num3 == 0)
                    return (ushort) (num1 | 31744);
                int num4 = num3 >> 13;
                return (ushort) (num1 | 31744 | num4 | (num4 == 0 ? 1 : 0));
            }
            int num9 = num3 + 4095 + (num3 >> 13 & 1);
            if ((num9 & 8388608) != 0)
            {     
                num9 = 0;
                ++num2;
            }
            if (num2 > 30)
            throw new ArithmeticException("Half: Hardware floating-point overflow.");
            return (ushort) (num1 | num2 << 10 | num9 >> 13);
        }
        //---------------------------------------------
        public float HalfToFloat(ushort ui16)
        {
            int num1 = (int)ui16 >> 15 & 1;
            int num2 = (int)ui16 >> 10 & 31;
            int num3 = (int)ui16 & 1023;
            if (num2 == 0)
            {
                if (num3 == 0)
                    return num1 << 31;
                while ((num3 & 1024) == 0)
                {
                    num3 <<= 1;
                    --num2;
                }
                ++num2;
                num3 &= -1025;
            }
            else if (num2 == 31)
            {
                if (num3 == 0)
                    return num1 << 31 | 2139095040;
                return num1 << 31 | 2139095040 | num3 << 13;
            }
            int num4 = num2 + 112;
            int num5 = num3 << 13;
            int bytes =  num1 << 31 | num4 << 23 | num5;
            return BitConverter.ToSingle(BitConverter.GetBytes(bytes), 0);
        }
## Post #38
- Username: yang4228907
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 27, 2019 6:58 pm
- Post datetime: 2019-11-28T09:37:59+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

please help~~
PEARLABYSS  paa animation   

How to open and what are the steps  

Thank you very  very very much！
[paa.png](https://xentaxbackup.github.io/file/17122_paa.png)
## Post #39
- Username: yang4228907
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 27, 2019 6:58 pm
- Post datetime: 2019-12-11T08:49:30+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

hlep  error
[111.png](https://xentaxbackup.github.io/file/17177_111.png)
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-11T21:12:40+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from yang4228907 ↑Thu Nov 28, 2019 5:37 pm at Thu Nov 28, 2019 5:37 pm
>
> 
please help~~
PEARLABYSS  paa animationwhat is this? A request? How do you think anyone could know what your problem is? 

> How to open and what are the steps  
>
> 
>
> Thank you very  very very much！In blender 2.49b: with the suiting blend file open (yes, there are several .blend file versions, which version/date are you talking about?)

with the mouse cursor in blender's script window:
- press alt-p, load pac (the mesh)
- press alt-p, load pab (the skeleton)
- press alt-p, load paa (the animation)

result:
.



m0001_07_goblin_boss_armor_0001.png (44.75 KiB) Viewed 338 times


console output:
Compiled with Python version 2.6.2.
Checking for installed Python... got it!
M0001_07_Goblin_Boss_Armor_0001
WARNING: no log
WARNING: no log
WARNING: no log
...
## Post #41
- Username: Docwastaken
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 08, 2015 9:34 am
- Post datetime: 2019-12-14T22:40:02+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Skykila ↑Thu Mar 03, 2016 3:51 pm at Thu Mar 03, 2016 3:51 pm
>
> 
Hi folks, I'm trying to make Noesis script to import animation. I have achieved some success, but the animation still loaded not correctly. Maybe someone knows what's the problem?
(you need to put skeleton file [.pab] in animation folder)

Did you ever get anywhere with this? The animations work fine in Blender, but not in neosis. Can anyone who actually has some idea what they're looking at actually spot the difference here?

Blender py that works:

```
	action=Action()
	action.BONESPACE=True
	action.BONESORT=True
	action.skeleton='armature'
	g.word(4)
	g.seek(16)
	boneCount=g.H(1)[0]
	g.H(4)
	for m in range(boneCount):
		g.logWrite('key'+str(m))
		bone=ActionBone()
		bone.name=str(g.i(1)[0])	
		c1=g.H(1)[0]
		for n in range(c1):#scale key
			g.H(4)
		c2=g.H(1)[0]
		for n in range(c2):#rotation key
			bone.rotFrameList.append(g.H(1)[0]/33)
			bone.rotKeyList.append(QuatMatrix(g.half(4)).resize4x4())	
			
		c3=g.H(1)[0]
		for n in range(c3):#transaltion key
			bone.posFrameList.append(g.H(1)[0]/33)
			bone.posKeyList.append(VectorMatrix(g.half(3)))	
		action.boneList.append(bone)	
	action.draw()
	action.setContext()
```


Neosis py that returns wrong results:

```
	bs.seek(16, NOESEEK_ABS)
	boneCount = bs.readUShort()
	animationDuration = bs.readFloat()
	NumFrames = int(animationDuration * 30.0)
	bs.readBytes(4)
	
	boneList = []
	kfBones = []
	timeList=[]
	
	for m in range(0, boneCount1):
		boneHash1 = bs.readUInt()
		
		name = boneNames[m]
		Parent = boneParentList[m]

		RotKeys = []; TrnKeys = []
				
		scaleKeyframeCount = bs.readUShort()
		for n in range(0, scaleKeyframeCount):#scale key
			scalekeyframe = bs.readUShort()//33 
			bs.readHalfFloat(); bs.readHalfFloat(); bs.readHalfFloat()

		rotationKeyframeCount = bs.readUShort()
		for n in range(0, rotationKeyframeCount):#rotation key
			rotationkeyframe = bs.readUShort()//33
			BoneQuat = NoeQuat( (bs.readHalfFloat(), bs.readHalfFloat(), bs.readHalfFloat(), bs.readHalfFloat()) )
			if Parent is not -1:
				RotKeys.append(NoeKeyFramedValue(rotationkeyframe, BoneQuat * BoneLocalRotList[Parent]))
			else:
				RotKeys.append(NoeKeyFramedValue(rotationkeyframe, BoneQuat))
			
		positionKeyframeCount = bs.readUShort()
		for n in range(0, positionKeyframeCount):#transaltion key
			positionkeyframe = bs.readUShort()//33
			BonePosition = NoeVec3( (bs.readHalfFloat(), bs.readHalfFloat(), bs.readHalfFloat()) )
			if Parent is not -1:
				TrnKeys.append(NoeKeyFramedValue(positionkeyframe, BonePosition + BonePosList[Parent]))
			else:
				TrnKeys.append(NoeKeyFramedValue(positionkeyframe, BonePosition + BonePosList[m]))

		kfBone = NoeKeyFramedBone(m)
		kfBone.setRotation(RotKeys, noesis.NOEKF_ROTATION_QUATERNION_4, noesis.NOEKF_INTERPOLATE_LINEAR)
		kfBone.setTranslation(TrnKeys, noesis.NOEKF_TRANSLATION_VECTOR_3, noesis.NOEKF_INTERPOLATE_LINEAR)
		kfBones.append(kfBone)
	anims.append(NoeKeyFramedAnim("BlackDesert anim", animBones, kfBones, 1))	
```


Not a big deal as blender works fine, but Neosis is a good bit more convenient. If one of you programming super geniuses know the fix without too much effort it would be greatly appreciated!
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-15T08:18:13+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from Docwastaken ↑Sun Dec 15, 2019 6:40 am at Sun Dec 15, 2019 6:40 am
>
> The animations work fine in Blender, but not in neosis. Can anyone who actually has some idea what they're looking at actually spot the difference here?You might log the matrices in blender, then in Noesis and compare for differences. That's how I would do it if I had time.

btw: looks as if my earlier suggestion of using shorts instead of half floats was wrong:
.



goblin.png (15.85 KiB) Viewed 297 times



well, from a comparison I guess it should be a problem with the rotation values in the Noesis script because the translation values (starting from 71/0) look very similar in both scripts' log output (apart from the frames up to 70/103 which show a strange grizzling/whatever in blender, too).

```

Noesis, Skykila
...
70.90: 39.093750 -0.000008 0.000008
70.91: 39.406250 -0.000008 0.000000
70.92: 39.500000 -0.000008 0.000011
70.93: 39.312500 0.000000 0.000012
70.94: 39.906250 -0.000015 0.000011
70.95: 40.625000 0.000000 0.000015
70.96: 41.312500 0.000000 0.000011
70.97: 41.531250 -0.000015 -0.000008
70.98: 41.437500 0.000008 0.000008
70.99: 41.437500 -0.000008 -0.000008
70.100: 41.468750 0.000000 0.000008
70.101: 41.531250 -0.000002 0.000027
70.102: 41.468750 -0.000019 0.000013
rotation:
translation:
71.0: 5.140625 -8.820312 3.115234
71.1: 5.140625 -8.820312 3.115234
rotation:
translation:
72.0: 22.218750 -7.113281 -1.173828
72.1: 22.218750 -7.113281 -1.173828
rotation:
translation:
73.0: 22.187500 0.625000 -2.599609
73.1: 22.187500 0.625000 -2.599609
rotation:
translation:
74.0: 22.328125 1.821289 2.548828
74.1: 22.328125 1.821289 2.548828

-----------------------------------------------------------------
Mariusz, blender
...
70 90 : [41.312500, 0.000000, 0.000008](vector)
70 91 : [41.250000, 0.000000, 0.000000](vector)
70 92 : [41.062500, -0.000011, 0.000000](vector)
70 93 : [40.843750, 0.000004, 0.000000](vector)
70 94 : [40.656250, 0.000000, 0.000000](vector)
70 95 : [40.906250, -0.000008, 0.000000](vector)
70 96 : [41.093750, -0.000002, 0.000000](vector)
70 97 : [41.062500, -0.000015, 0.000031](vector)
70 98 : [40.781250, 0.000017, -0.000015](vector)
70 99 : [40.250000, 0.000000, 0.000015](vector)
70 100 : [39.718750, -0.000011, 0.000015](vector)
70 101 : [39.562500, 0.000004, -0.000015](vector)
70 102 : [40.000000, 0.000000, 0.000000](vector)
70 103 : [40.906250, 0.000008, 0.000008](vector)

71 0 : [5.140625, -8.820313, 3.115234](vector)
71 1 : [5.140625, -8.820313, 3.115234](vector)

72 0 : [22.218750, -7.113281, -1.173828](vector)
72 1 : [22.218750, -7.113281, -1.173828](vector)

73 0 : [22.187500, 0.625000, -2.599609](vector)
73 1 : [22.187500, 0.625000, -2.599609](vector)

74 0 : [22.328125, 1.821289, 2.548828](vector)
74 1 : [22.328125, 1.821289, 2.548828](vector)

```
## Post #43
- Username: tnt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2017 6:02 am
- Post datetime: 2020-01-10T20:09:01+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

I wrote a structure definition file for Hex Workshop 6.7.0.5247 in helping to interpret the file format (be it PAA, PAB, or PAC)

Also worked on a Noesis script to port over the animation data, but running into the same issue with the quaternions. I wasn't able to get it to work even with the original script that was written for Blender 2.49b, so I'm guessing the data format changed?
[bdo.7z](https://xentaxbackup.github.io/file/17316_bdo.7z)
## Post #44
- Username: Mammon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 07, 2020 7:30 pm
- Post datetime: 2020-02-11T05:49:28+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Can anyone create detailed video-instruction of model extraction process (step-by-step)?
From: opening PAZ-file.
To: import model in Blender.
## Post #45
- Username: ItsPedrow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 24, 2020 5:59 am
- Post datetime: 2020-04-23T22:19:08+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Hey there
The blender script isn't working anymore.
Any update to it?
## Post #46
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-24T14:39:17+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Doesn't blender script work with all models of just the newest one?
Try it with the first folder of monster ( should be the older one )  and let me know. 

They updated the graphic engine but it's unlikely they converted all the models .
## Post #47
- Username: Bruno89dh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 09, 2020 9:31 am
- Post datetime: 2020-05-09T02:21:44+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Does anyone know how to open the new Pac and Pab files, I can only open the old files
## Post #48
- Username: yang4228907
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 27, 2019 6:58 pm
- Post datetime: 2020-05-24T02:30:27+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from shakotay2 ↑Thu Dec 12, 2019 5:12 am at Thu Dec 12, 2019 5:12 am
>
> 
yang4228907 wrote: ↑Thu Nov 28, 2019 5:37 pm
please help~~
PEARLABYSS  paa animation  what is this? A request? How do you think anyone could know what your problem is? 
How to open and what are the steps  

Thank you very  very very much！
In blender 2.49b: with the suiting blend file open (yes, there are several .blend file versions, which version/date are you talking about?)

with the mouse cursor in blender's script window:
- press alt-p, load pac (the mesh)
- press alt-p, load pab (the skeleton)
- press alt-p, load paa (the animation)

result:
.
m0001_07_goblin_boss_armor_0001.png
console output:
Compiled with Python version 2.6.2.
Checking for installed Python... got it!
M0001_07_Goblin_Boss_Armor_0001
WARNING: no log
WARNING: no log
WARNING: no log
...

 very thanks
## Post #49
- Username: yang4228907
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 27, 2019 6:58 pm
- Post datetime: 2020-07-20T10:38:12+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

HI  masters  

  blender249  Is the script updated? The latest action model can't be opened, if you know, please help us to see it, thank you very much 。

The error is as follows：

Traceback (most recent call last):
  File "BlackDesert.py", line 136, in openFile
    file.close()
  File "BlackDesert.py", line 122, in Parser
    g=BinaryReader(file)
  File "BlackDesert.py", line 70, in pabParser
    bone.matrix=Matrix4x4(g.f(16))
  File "F:\参考资料\黑沙参考\Blender\.blender\scripts\newGameLib\myLibraries\binaresLib.py", line 212, in f
    data=struct.unpack(self.endian+n*'f',self.inputFile.read(n*4))
struct.error: unpack requires a string argument of length 12
[blender249.png](https://xentaxbackup.github.io/file/18499_blender249.png)
## Post #50
- Username: lujieshen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 10, 2018 2:55 pm
- Post datetime: 2020-08-20T03:43:58+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Hi all,

I just struggled to fix newer fileformats and here are modified 010 Templates. In a word: when `flag==256` in Bone, additional 9 float3 (maybe Mat3x3) is provided in the file. I can't figure out what it means but we can still get the right data from it.
[BlackDesertTemplates.zip](https://xentaxbackup.github.io/file/18628_BlackDesertTemplates.zip)
## Post #51
- Username: fre3e
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 14, 2020 11:07 am
- Post datetime: 2020-12-26T03:54:31+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

I have an answer to the ppl wanting to import newer PAC models.

All you have to do is change two things below def pacParser:
1) g.seek(0x10) -> g.seek(0x14)
2) if parVer == 259: -> if parVer == 515 or parVer == 771:

I also have a question:
The dds files always have two versions for the textures for example pem_00_cloak_0002 and pem_00_cloak_0002_dm.
Does anyone know what the "_dm" means?
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-26T12:42:04+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Don't have those textures but might stand for "diffuse map" (or dark mage, whatever  ).
## Post #53
- Username: fre3e
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 14, 2020 11:07 am
- Post datetime: 2020-12-26T14:45:42+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from shakotay2 ↑Sat Dec 26, 2020 8:42 pm at Sat Dec 26, 2020 8:42 pm
>
> 
Don't have those textures but might stand for "diffuse map" (or dark mage, whatever  ).

Actually I found it out.
There are two versions of the same texture, the un-damaged version (e.g. "pem_00_sho_0002.dds") and a damaged version (e.g. "pem_00_sho_0002_dm.dds").

Man this took me a few hours but I finally managed to have a decent workflow to export everything I need. Wish there was better documentation but what helped was piecing together info from the chrrox and this thread.

As it stands now, I have to tweak my script a bit depending on the pac version and also have to manually change the output of the paz browser, to get the right textures. I dont have the time to fix the paz_browser (but maybe this import script, as the problem here is not that complex).
Is anyone interested in a small tutorial from start-finish (from paz_browser to blender2.90 with working model/texture/animations ?) if there is enough interest, I might write it down.

The only thing thats left, just to have a bit more convenience:
Does anyone have a working python3 version of this script for Blender 2.90 ?
I tried with the simple 2to3 Python script but that didnt work. Most likely too much has changed from 2.49b to 2.90 Blender.
## Post #54
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-01-13T12:26:43+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from fre3e ↑Sat Dec 26, 2020 10:45 pm at Sat Dec 26, 2020 10:45 pm
>
> 
shakotay2 wrote: ↑Sat Dec 26, 2020 8:42 pm
Don't have those textures but might stand for "diffuse map" (or dark mage, whatever  ).


Actually I found it out.
There are two versions of the same texture, the un-damaged version (e.g. "pem_00_sho_0002.dds") and a damaged version (e.g. "pem_00_sho_0002_dm.dds").

Man this took me a few hours but I finally managed to have a decent workflow to export everything I need. Wish there was better documentation but what helped was piecing together info from the chrrox and this thread.

As it stands now, I have to tweak my script a bit depending on the pac version and also have to manually change the output of the paz browser, to get the right textures. I dont have the time to fix the paz_browser (but maybe this import script, as the problem here is not that complex).
Is anyone interested in a small tutorial from start-finish (from paz_browser to blender2.90 with working model/texture/animations ?) if there is enough interest, I might write it down.

The only thing thats left, just to have a bit more convenience:
Does anyone have a working python3 version of this script for Blender 2.90 ?
I tried with the simple 2to3 Python script but that didnt work. Most likely too much has changed from 2.49b to 2.90 Blender.

Hey guy! I'm rewriting  Szkaradek123's script with python 3 for blender 2.9.But when I tested pdw samples I attached below,blender goes wrong.
(parVer of pac ==771, of pab ==1025)
Have you figued out how to solve the "Bonename" problems? Maybe it use phw's skeleton?

Here are the sample files: containing .pac .pab .paa extracted from remastered version 2100.

[https://drive.google.com/file/d/1csZJt9 ... sp=sharing](https://drive.google.com/file/d/1csZJt9zUTDxfv2kgtJ9rPJ9Xr5XXRYET/view?usp=sharing)
## Post #55
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-01-15T17:28:49+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

Hi,here's the Noesis script I fixed for remastered game Version 2100.Supporting all classes nude model.
I skipped some data after flag 256&1025.But,what they mean?
[fmt_Black_Desert_pab_fixed2100.zip](https://xentaxbackup.github.io/file/19313_fmt_Black_Desert_pab_fixed2100.zip)
## Post #56
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-04-23T15:07:12+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from 48464385 ↑Sat Jan 16, 2021 1:28 am at Sat Jan 16, 2021 1:28 am
>
> 
Hi,here's the Noesis script I fixed for remastered game Version 2100.Supporting all classes nude model.
I skipped some data after flag 256&1025.But,what they mean?

Fix a bug.Bone name should use "euc-kr" coding instead of "ASCII".
Noesis may not display korean charset correctly. But it export to .fbx with correctly bone name.I tested on pdw_00_ub_0001.pac 

BTW,You may need to extract "core321.zip" to folder "noesis\plugins\python\core321.zip\" manually. Otherwise,Noesis may have "IOError: zipimport" 
[fmt_Black_Desert_pab_fixed2100_euc-kr.zip](https://xentaxbackup.github.io/file/19940_fmt_Black_Desert_pab_fixed2100_euc-kr.zip)
## Post #57
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-04-24T14:48:49+00:00
- Post Title: Re: Black Desert Online File Formats (PAB, PAC, PAA)

> Reply from 48464385 ↑Fri Apr 23, 2021 11:07 pm at Fri Apr 23, 2021 11:07 pm
>
> 
48464385 wrote: ↑Sat Jan 16, 2021 1:28 am
Hi,here's the Noesis script I fixed for remastered game Version 2100.Supporting all classes nude model.
I skipped some data after flag 256&1025.But,what they mean?


Fix a bug.Bone name should use "euc-kr" coding instead of "ASCII".
Noesis may not display korean charset correctly. But it export to .fbx with correctly bone name.I tested on pdw_00_ub_0001.pac 

BTW,You may need to extract "core321.zip" to folder "noesis\plugins\python\core321.zip\" manually. Otherwise,Noesis may have "IOError: zipimport"

Update:[viewtopic.php?f=16&t=10909&start=75#p173600](https://forum.xentax.com/viewtopic.php?f=16&t=10909&start=75#p173600)
