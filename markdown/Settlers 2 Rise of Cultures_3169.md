## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-29T19:37:18+00:00
- Post Title: Settlers 2: Rise of Cultures

The predecessor of this game used Granny. But Granny Viewer isn't able to to open the files used by this one.
Seems like they use a proprietary format now.
I attached the donkey model files as an example.

EDIT: k, the strings are saved Pascal-style, preceded by their size (4 bytes).
Regarding LOD3...The second string is followed by an int denoting the number of dwords following it. Don't know what this is. Indices?
[donkey.rar](https://xentaxbackup.github.io/file/1665_donkey.rar)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-09-30T11:03:06+00:00
- Post Title: Settlers 2: Rise of Cultures

Since I am good in 3D models data, so I help you out here!
Hope that people can help me in compression data!

Back to the topic, It seems all 3D data use the same extension *.KEX!
-donkey_mesh.KEX, donkey_mesh_LOD1.KEX, donkey_mesh_LOD2.KEX and donkey_mesh_LOD3.KEX are models
-donkey_model.KEX is skeleton file
-all others are animation files

Here is the Model format:

```

dword         nLen
Char[nLen]    Filename
float_12      Matrix_3X4
float         ??
byte          numMesh

Struct Mesh {
  dword       nLen
  Char[nLen]  MeshName
  dword       nLen
  Char[nLen]  subMeshName
  dword       numFaceIndices
  dword       numVerts
  dword       numVertPoolData
  dword       numBones
  dword       numMaterial

  struct Face {
    dword_3   Index_123
  }

  Struct VertPool {
    byte      DataType
    dword     ofsDataSize
    //<PoolData>           //see below

    struct Vert {         //DataType = 0
      float_3 Pos_XYZ
    }
  
    struct Normal {       //DataType = 1
      float_3 Nomal_XYZ
    }  
  
    struct Unknown {      //DataType = 3; Maybe VertexColor
      byte_4  ??
    }  

    struct UV {           //DataType = 4
      float_2 Texture_UV
    }

    struct Unknon2D {     //DataType = 5 and 6
      float_2 Texture_UV
    }
    
    struct Weight {       //DataType = 12
      float_4 weight_1234
    }

    struct BoneID {       //DataType = 13
      byte_4  weight_1234
    }
    
  }

  struct BoneName {
    dword       nLen
    Char[nLen]  Bonename
  }

  struct Material {
    dword       nLen
    Char[nLen]  MaterialName
    dword       nLen
    Char[nLen]  SubMaterialName
    dword       ??
    dword       numMatFaces //for Multi-Material
    dword       numTexture
    struct Texture {
      dword       nLen
      Char[nLen]  SlotName
      dword       nLen
      Char[nLen]  TextureName
    }
  }  
    
}
```

[Settlers2_mesh.jpg](https://xentaxbackup.github.io/file/1667_Settlers2_mesh.jpg)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-30T11:23:47+00:00
- Post Title: Settlers 2: Rise of Cultures

> Reply from fatduck
>
> Since I am good in 3D models data, so I help you out here!
Hope that people can help me in compression data!
I knew I can count on you 

> Back to the topic, It seems all 3D data use the same extension *.KEX!
>
> -donkey_mesh.KEX, donkey_mesh_LOD1.KEX, donkey_mesh_LOD2.KEX and donkey_mesh_LOD3.KEX are models
>
> -donkey_model.KEX is skeleton file
>
> -all others are animation files
Already wondered what that _model.KEX is. Yeah all 3D files use *.KEX extension.

> Code: Select all//No sure about the follow, since only 1 Texture
>
> 
>
> dword       ??
>
> dword       ??
>
> dword       ??
>
> dword       nLen
>
> Char[nLen]  SlotName
>
> dword       nLen
>
> Char[nLen]  TextureName
Ok, I attached some more files.
Thanks for your help!


EDIT: But somehow I can't comprehend in which order those structs are saved in the file 
[models.rar](https://xentaxbackup.github.io/file/1668_models.rar)
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-09-30T13:33:49+00:00
- Post Title: Settlers 2: Rise of Cultures

Job done!  

A KEX can have more than 1 mesh.
And skeleton can be in the same KEX as well!

See the above updated format!

> Reply from Rheini
>
> 
EDIT: But somehow I can't comprehend in which order those structs are saved in the file

```
    byte      DataType     <- base on this flag
    dword     ofsDataSize
    //<PoolData>           //see below
```

For the whole file:

```
  Faces
  VertPool
    -Base on DataType
  Bones
  Materials

  Faces
  VertPool
    -Base on DataType
  Bones
  Materials

  ...

Skeleton
```
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-30T14:33:43+00:00
- Post Title: Settlers 2: Rise of Cultures

EDIT: Yeah, the meshes are followed by the skeleton.
I uploaded some more files containing no mesh.

EDIT: What could be contained in the skeleton?
[files.rar](https://xentaxbackup.github.io/file/1670_files.rar)
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-11T21:49:49+00:00
- Post Title: Settlers 2: Rise of Cultures

And the skeleton is followed by the animations.
But I can't even figure out the skeleton parts, since they have variable length.
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-10-12T17:12:29+00:00
- Post Title: Settlers 2: Rise of Cultures

I can't believe you can not figure them out!

```

struct Header {
  dword       nLen
  Char[nLen]  Filename
  float_12    Matrix_3X4
  float       ??
  byte        NumMesh
}
byte          SkeletonID        //01
dword         nLen
Char[nLen]    RootName  
dword         nLen
Char[nLen]    MeshName
dword         NumBones

struct Bone {
  dword       nLen
  Char[nLen]  BoneName
  dword       TransformType
  float_3     PosXYZ            //TransformType:1,3,5
  float_5     ??                //TransformType:5
  float_4     RotXYZW           //TransformType:2,3,5
  float_16    Matrix_4X4
  dword       ParentID
}
```


And AFAIK there is not skeleton in animation files, purely animation data!
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-12T18:57:11+00:00
- Post Title: Settlers 2: Rise of Cultures

I already had the skeleton header, but thought that your transformType is some kind of count variable.
Could it be that this variable is a flag byte (bitwise coding)?

Btw, what is your way of importing that stuff into a 3D-program?

EDIT:

> Reply from fatduck
>
> And AFAIK there is not skeleton in animation files, purely animation data!
Yeah, but I found a file containing a mesh and animations, but no skeleton 

This is getting bigger and bigger, my binary template is already 180 lines long 

```
	uint size;
	char data[size];
};

typedef struct Matrix3x4 {
	float elems[12];
};

String filename;
Matrix3x4 uk;
float uk;
byte numMeshes;

struct Mesh {

String meshName;
String subMeshName;
uint numFaceIndices;
uint numVerts;
uint numVertPoolData;
uint numBones;
uint numMaterials;

struct Face {
	uint index1;
	uint index2;
	uint index3;
};
Face faces[numFaceIndices/3];

struct Vert {         //DataType = 0
	float xpos;
	float ypos;
	float zpos;
};
//Vert verts[numVerts];

struct Normal {       //DataType = 1
	float xnorm;
	float ynorm;
	float znorm;
};

struct Type2 { // DataType = 2
	float x;
	float y;
	float z;
};

//maybe vertex color
struct Unknown {      //DataType = 3
	byte uk[4];
};

struct UV {           //DataType = 4
	float u;
	float v;
};

struct Unknown2D {	// DataType = 5 and 6
	float u;
	float v;
};

struct Weight {       //DataType = 12
	float w1;
	float w2;
	float w3;
	float w4;
};

struct BoneID {       //DataType = 13
	byte weight1;
	byte weight2;
	byte weight3;
	byte weight4;
};

struct VertPool {
	byte DataType;
	uint ofsDataSize;

	switch(DataType)
	{
		case 0:
			Vert verts[numVerts];
			break;
		case 1:
			Normal normals[numVerts];
			break;
		case 2:
			Type2 types2[numVerts];
			break;
		case 3:
			Unknown uks[numVerts];
			break;
		case 4:
			UV uvs[numVerts];
			break;
		case 5:
		case 6:
			Unknown2D uk2ds[numVerts];
			break;
		case 12:
			Weight weights[numVerts];
			break;
		case 13:
			BoneID boneIDs[numVerts];
			break;
		default :
			Warning("Unknown VertPoolData type: %i", DataType);
	}
};

VertPool vertPools[numVertPoolData]<optimize=false>;
String boneNames[numBones]<optimize=false>;

struct Texture
{
	String slotName;
	String textureNames;
};

struct Material
{
	String materialName;
	String subMaterialName;
	uint uk1;
	uint numMatFaces; //for Multi-Material
	uint numTextures;
	Texture textures[numTextures]<optimize=false>;
};
Material materials[numMaterials]<optimize=false>;

};
Mesh meshes[numMeshes]<optimize=false>;

byte numSkeletons;

struct Bone
{
	String boneName;
	uint transformType;
	if(transformType == 1 || transformType == 3 || transformType == 5)
		float posXYZ[3];
	if(transformType == 5)
		float uk[5];
	if(transformType == 2 || transformType == 3 || transformType == 5)
		float rotXYZW[4];
	float matrix[16];
	int parentID;
};

struct Skeleton
{
	String rootName;
	String meshName;
	uint numBones;
	Bone bones[numBones]<optimize=false>;

};
Skeleton skeletons[numSkeletons]<optimize=false>;

byte numAnimations;

struct Animation
{
	String rootName;
	String animName;
	float uk;
};

Animation anims[numAnimations]<optimize=false>;
```

[files.rar](https://xentaxbackup.github.io/file/1686_files.rar)
## Post #9
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-10-15T09:15:29+00:00
- Post Title: Settlers 2: Rise of Cultures

> Reply from Rheini
>
> I already had the skeleton header, but thought that your transformType is some kind of count variable.
Could it be that this variable is a flag byte (bitwise coding)?
No, Because type 5 got all the data from type 1,2, and bitflag 5 = 00000101 which shouldn't have type 2!


> Reply from Rheini
>
> Btw, what is your way of importing that stuff into a 3D-program?
I use maxscript(3dsmax), simply because it is a powerful 3D ready scripting language, easily edit and have the result instantly...


> Reply from Rheini
>
> EDIT:
fatduck wrote:And AFAIK there is not skeleton in animation files, purely animation data!
Yeah, but I found a file containing a mesh and animations, but no skeleton
I am almost finish everything include animation and skeleton! Only have some problem in root bone animation! The animation data are based on parent coordinate so it is very unusual for a model without skeleton! Maybe the animation data there are all in world coordinate(which I am having problem with). 

By the way the KEX format should be like this:

```
dword         nLen
Char[nLen]    Filename
float_12      Matrix_3X4
float         ??KEXScale
}
byte          numMesh
<Mesh Data>
byte          numSkeleton
<SkeletonData>
byte          numAnimation
<AnimationData>

```

That why all model, skeleton and animation are in same extenstion .KEX!!!
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-15T16:14:13+00:00
- Post Title: Settlers 2: Rise of Cultures

> Reply from fatduck
>
> I use maxscript(3dsmax), simply because it is a powerful 3D ready scripting language, easily edit and have the result instantly...
Ah ok. Gotta write something to import it.

> I am almost finish everything include animation and skeleton! Only have some problem in root bone animation! The animation data are based on parent coordinate so it is very unusual for a model without skeleton! Maybe the animation data there are all in world coordinate(which I am having problem with).
Unfortunately I'm not familiar with this stuff.

> By the way the KEX format should be like this:
>
> Code: Select allstruct Header {
>
> dword         nLen
>
> Char[nLen]    Filename
>
> float_12      Matrix_3X4
>
> float         ??KEXScale
>
> }
>
> byte          numMesh
>
> <Mesh Data>
>
> byte          numSkeleton
>
> <SkeletonData>
>
> byte          numAnimation
>
> <AnimationData>
>
> 
>
> That why all model, skeleton and animation are in same extenstion .KEX!!!
Yep, I know, it is already contained in my template
## Post #11
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-10-15T22:20:23+00:00
- Post Title: Settlers 2: Rise of Cultures

OK! I sovled my problem and had a look in that boat file!
The animation is simply unused, so no needs to care about it!
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-16T21:07:48+00:00
- Post Title: Settlers 2: Rise of Cultures

Wow, will you release your import script (mabye at least partly)?
