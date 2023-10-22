## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-04T22:10:35+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-04T23:21:28+00:00
- Post Title: World of Warcraft file formats

Nice work, man!
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-04T23:32:58+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-05T02:17:37+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-05T08:35:42+00:00
- Post Title: World of Warcraft file formats

Yes, I would love to support theMPQ format, but it will be something for a plug-in, and Rahly and I are working on implementing a new Pluginmanager (which Rahly has completed). If that is all up and running, we can go create plugins for it. A plugin will enable us to work with more sophisticated archives, such as MPQ.
## Post #6
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-07T06:49:11+00:00
- Post Title: World of Warcraft file formats

wow! someone else who is interested in the wow formats. I have a little more than you on the m2 done, and all the blp2 done as well as another model format, the wmo, email me sometime at [warbeta3@hotmail.com](mailto:warbeta3@hotmail.com) if youd like to get together and compare notes
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-01-08T02:07:43+00:00
- Post Title: World of Warcraft file formats

MPQ is not a problem, although, unfortunately, the StormLib has change with the different games SC,Diablo,Diablo2, Warcraft III, WoW.  Its also good to note that the MPQs for Diablo+ can also be encrypted.  This means you need to know the right password to DECRYPT it.  Unfortunately, MPQ do NOT store file names.  You are expected to know the filename before you access it.  You might be saying "WHAT?".  The MPQ stores data in a large hashing table.  when you say "open this file in the mpq" the stormlib hashes the file name 4 times.  once to find its entry in the hash table, and 3 other hash to verify entry.
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-08T02:09:48+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-08T03:56:52+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #10
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-09T02:04:24+00:00
- Post Title: World of Warcraft file formats

wmo data:
here is the WMO header
REVM
	long	Nbytes;
	long	Version;

DHOM
	long	Nbytes;
	long	numtextures;	
	long	numsubfiles;
	long	???;
	long	???;
	long 	num mdxs;
	long	???;
	long	num SDOMs;
	(11 unknown longs)

XTOM
	long	Nbytes;
	struct	{
		string	TexturePath;	// There appears to be no real method to how many null bytes follow the texture filenames
	} Texturepath[numtextures];

TMOM
	long	Nbytes;
	???

NGOM
	long	Nbytes;
	short	???;	// (0)
	struct	{
		string	SubName;	// Null terminated with one byte
	} SubName[numsubfiles];

IGOM
	long	Nbytes;
	struct	{
		long	???;
		float	minx;
		float	miny;
		float	minz;
		float	maxx;
		float	maxy;
		float	maxz;
		float	???;
	} BoundsInfo[numsubfiles];

VPOM
	long	Nbytes;
	???

TPOM
	long	Nbytes;
	???

RPOM
	long	Nbytes;
	???

SDOM
	long	Nbytes;
	string	???;		// Null terminated with one byte, have no idea what it means

NDOM
	long	Nbytes;
	???

DDOM	long	Nbytes;
	???

GOFM
	long	Nbytes;
	???

Here is the actual model files, they are referenced by the name of the wmo file with _### at the end

REVM
	long	Nbytes;
	long	Version;

PGOM
	???	//Contains no Nbytes, but is always 72 bytes in size

YPOM
	long	Nbytes;
	struct	{
		byte	flags;
		byte	TextureId;
	} VertTextData[Nbytes/2]

IVOM
	long	Nbytes;
	struct	{
		short	x;
		short	y;
		short	z;
	} FaceData[Nbytes/6]
TVOM
	long	Nbytes;
	struct	{
		float	x;
		float	y;
		float	z;
	} VertData[Nbytes/12]

RNOM
	long	Nbytes;
	struct	{
		float	x;
		float	y;
		float	z;
	} NormalData[Nbytes/12]

VTOM
	long	Nbytes;
	struct	{
		float	x;
		float	y;
	} TexVertData[Nbytes/8]

ABOM
	long	Nbytes;
	???

NBOM
	long	Nbytes;
	???

RBOM
	long	Nbytes;
	???

and last but not least, the m2 specs

Header:
	MD20
	Long	Version;
	Long	Name Length;		// includes null termination
	Long	Name Offset;
	Long	???;
	Long	???;
	Long	???;
	Long	nanims;		
	Long	Anim Offset;	
	...
	Long	nverts;		// offset 68
	Long	Vert Offset;	
	Long	Primitive Type;
	Long	Face Offset;	
	...
	Long	ntexs;		// offset 92
	Long	Tex Offset;	
	...
	Float	minx;		// offset 180
	Float	miny;
	Float	minz;
	Float	maxx;
	Float	maxy;
	Float	maxz;
	...
	String	name[Name Length];		// offset 336 
	//Null bytes till a multiple of 16 is reached
	struct	{			// found at Anim Offset
		Long	animid;		// found in animationdata.dbc
		Long	inststart;
		Long	intend;
		Long	movespeed;
		Long	nonlooping;	// (0:loop; 1:no loop)
		Long	???;
		Long	???;
		Long	???;
		Long	BlendTime;
		Float	minx, miny, minz;
		Float	maxx, maxy, maxz;
		Long	???;
		Long	???;
	} sequences[nanims]	// (68 bytes long)
	Long	???;
	Long	???;
... 
	struct	{
		Float	x;
		Float	y;
		Float	z;
		...
	} pivots[npivots]		// (108 bytes long)
struct	{
	float	x;
	float	y;
	float	z;
	Byte	b1w;		// these 4 bytes add up to 255
	Byte	b2w;
	Byte	b3w;
	Byte	b4w;
	Byte	b1i;
	Byte	b2i;
	Byte	b3i;
	Byte	b4i;
	float	nx;
	float	ny;
	float	nz;
	float	u;
	float	v;
	Long	???;
	Long	???;
} verts[nverts]
Long	nverts;
Long	foffsetstart;
Long	NumFaces;
Long	foffsetend;
...
struct	{	// starts at foffsetend
	short x;
	short y;
	short z;
} faces[NumFaces]
struct	{		// starts at Tex Offset
	Long	;		
	Long	???;
	Long	texlength;
	Long	pathoffset;
} texinfo[ntexs]
struct	{
	string[texlength];
	Null bytes until a multiple of 16 is reached
} texpath[ntexs]

Long	???;		// (0)
Short	???;		// FFFF
Long	???;		// (0)
Long	???;		// (0)
Long	???;		// (1)
Long	unkoff1;
Long	???;		// (1)
Long	unkoff2;
Long	???;		// (0)
Long	???;		// at unkoff1 (0)
Long	???;		// (0)
Long	???;		// (0)
Long	???;		// (0)
Long	???;		// at unkoff1 (0xFF7F)
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-09T21:21:23+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #12
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-09T22:24:31+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #13
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-10T19:06:16+00:00
- Post Title: World of Warcraft file formats

well for the extra chunks in the WMO, i know at least one of the mhas to be collission data, which is what i think the MOBA is though im not entirely sure. what im stuck with atm is on the m2, i cant figure out how multi textured geosets work. there is so much more to the face section i dont understand
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-10T23:22:43+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-10T23:52:04+00:00
- Post Title: World of Warcraft file formats

[out]
## Post #16
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-12T01:47:50+00:00
- Post Title: 

well before beta poatch 3, they had a modified version of the war3 mdx, it was pretty simple, and i was searching for the pivot point values, though im pretty sure they merged the pivot points with their respective objects, ie the bones have their pivot info in their block, but i cant be too sure
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-12T20:11:42+00:00
- Post Title: 

[out]
## Post #18
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-17T05:08:39+00:00
- Post Title: 

what im really interested in is the terain format, i remember in the beta days, someoen decoded alot of it, but alas, the post is gone, but it didnt seem that hard
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-17T20:16:13+00:00
- Post Title: 

[out]
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-17T21:22:27+00:00
- Post Title: 

[out]
## Post #21
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-18T04:23:27+00:00
- Post Title: 

sorry, that gues post was me, what i meant was figuring out the hieghtmaps stored in the terrain data. someone from back in the day made a program that could render terrain chunks, cuz the files are split into little sections, similar to the WMOs
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-18T20:58:09+00:00
- Post Title: 

[out]
## Post #23
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-19T04:46:26+00:00
- Post Title: 

well im still stuck on terrain formats, but i did find an open source m2 viewer that supports animations, but it doesnt support multi texture models, we should team up and figure this damn problem out
## Post #24
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-19T21:51:13+00:00
- Post Title: 

[out]
## Post #25
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-20T17:15:15+00:00
- Post Title: 

well later today ill upload the japanee m2 viewer and its source, though i cant get itto compile for the life of me
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-21T22:42:33+00:00
- Post Title: 

[out]
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-22T08:39:45+00:00
- Post Title: 

Oh but you can upload files (attach them to your post). Depends on how big they are. But we can arrange space for that.
## Post #28
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-22T17:13:01+00:00
- Post Title: 

Yeah. You might have to fool with it a bit, like I did on my post about Zoo Tycoon in this forum. I was just about to give up when it finally worked for me, so don't be so quick to jump to conclusions.
## Post #29
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-24T15:19:30+00:00
- Post Title: 

yeah, i got that chinese one, this japanese one is alot better, it even has animations, but still no multi texture support, here's a sample of it

struct M2_HEADER					// 336 bytes, 84 DWORDs.
{	
	DWORD dwIdent;					// M2 File Identity
	DWORD dwVersion;				// version: 256

	DWORD nModelNameSize;			// strlen(szModelName) + 1
	DWORD nModelNameOffset;			// always 336(header size), points to ModelName.

	DWORD dwUnk1;					// All 0s, occasionally 1,3(World\SkillActivated\Containers\TreasureChest01: 3)

	DWORD nGlobalSequences;
	DWORD nGlobalSequencesOffset;	// points to array of DWORD

	DWORD nNumAnimations;		
	DWORD nAnimationsOffset;		// points to M2_ANIMATION_INFO

	DWORD nUnkIndices;				
	DWORD nUnkIndicesOffset;		// points to array of unsigned short	

	DWORD nUnkLongs;
	DWORD nUnkLongsOffset;			// points to array of longs

	DWORD nBonesCount;
	DWORD nBonesOffset;				// points to M2_BONE_DATA

	DWORD nUnkIndices2;
	DWORD nUnkIndicesOffset2;		// points to array of unsigned short

	DWORD nNumVertices;	
	DWORD nVerticesOffset;			// points to M2_Vertex!!!

	DWORD nNumGeoMeshs;				 
	DWORD nGeoMeshsOffset;			// Points to M2_GEOMETRY_MESH!!!

	DWORD dwMagic[2];				// 0s

	DWORD nNumTextures;				
	DWORD nTexturesOffset;			// points to M2_TEXTURE_INFO.

	DWORD dwUnk6[10];				// Other chunks

	DWORD nGroupBoneIDs;			// Bone groups data		
	DWORD nGroupBoneIDsOffset;		// points to array of unsigned short which is bone id.

	DWORD nNumMaterials;
	DWORD nMaterialsOffset;

	DWORD nStruct1Count;			// 16 bytes, only 1. 
	DWORD nStruct1Offset;

	DWORD nStruct2Count;			// 16 bytes, only 1.
	DWORD nStruct2Offset;	

	DWORD nStruct3Count;			// 16 bytes, only 1.
	DWORD nStruct3Offset;

	vec3_type vMinBox;				// Bounding box
	vec3_type vMaxBox;

	float fUnk4;					// Unknown but it's right before min box when former mdx format.

	float fUnk[5];
	DWORD dwUnk8;					// Unknown 0
	float fUnk9;				

	DWORD dwUnk10;			 		// Always 36
	DWORD dwUnk11[5];

	DWORD nAttachments;				
	DWORD nAttachmentsOffset;

	DWORD dwUnk12;
	DWORD dwUnkOffset12;

	DWORD nNumEvents;		
	DWORD nEventsOffset; 	

	DWORD dwUnk13;
	DWORD dwUnkOffset13;

	DWORD nCameras1;	
	DWORD nCameras1Offset;

	DWORD nCameras2;
	DWORD nCameras2Offset;
	DWORD dwUnk14;

	DWORD dwUnk15[6];
};       

// ÃŽÃ†Ã€Ã­Ã
## Post #30
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2005-01-25T02:22:13+00:00
- Post Title: 

[out]
## Post #31
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2005-01-28T02:53:19+00:00
- Post Title: 

you got it almost right   where you have Word end_index is actually the starting face index. Thanks to your help, I now have multi textured models working  now to get animation working in 3ds max...
