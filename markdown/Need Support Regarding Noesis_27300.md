## Post #1
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2023-10-18T03:51:51+00:00
- Post Title: Need Support Regarding Noesis

If there are any noesis plugin scripters here, could you please explain the logic of the piece of code/ api call
rapi.rpgCommitTriangles ?

My friend @plodtrew is trying to code an application to manipulate WWE RAW 2 .fml files.
## Post #2
- Username: FreddyA
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 18, 2023 1:02 pm
- Post datetime: 2023-10-18T17:33:36+00:00
- Post Title: Need Support Regarding Noesis

Certainly, "rapi.rpgCommitTriangles" is an API call commonly used in game development, particularly for rendering 3D graphics. It's often part of a game engine's rendering pipeline, used to draw triangles or other geometric shapes on the screen. In this context, it's a fundamental function for creating graphics in a game like WWE RAW 2. Your friend may be using it to render 3D elements or perform other graphics-related tasks in their application.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-18T18:06:14+00:00
- Post Title: Need Support Regarding Noesis

> Reply from eri619 ↑Wed Oct 18, 2023 11:51 am at Wed Oct 18, 2023 11:51 am
>
> 
If there are any noesis plugin scripters here, could you please explain the logic of the piece of code/ api call
rapi.rpgCommitTriangles ?
Not really being a "Noesis scripter" but whatever answer is expected; hints are to be found in Noesis' \source\pluginshare.h:

	void				(*rpgCommitTriangles)(void *idxData, rpgeoDataType_e dataType, int numIdx, rpgeoPrimType_e primType, bool usePlotMap);

```
{
	RPGEODATA_FLOAT = 0,
	RPGEODATA_INT,
	RPGEODATA_UINT,
	RPGEODATA_SHORT,
	RPGEODATA_USHORT,
	RPGEODATA_HALFFLOAT,
	RPGEODATA_DOUBLE,
	RPGEODATA_BYTE,
	RPGEODATA_UBYTE,
	NUM_RPGEO_DATATYPES
} rpgeoDataType_e;

typedef enum
{
	RPGEO_NONE = 0,
	RPGEO_POINTS,
	RPGEO_TRIANGLE,
	RPGEO_TRIANGLE_STRIP,
	RPGEO_QUAD, //ABC_DCB
	RPGEO_POLYGON,
	RPGEO_TRIANGLE_FAN,
	RPGEO_QUAD_STRIP,
	RPGEO_TRIANGLE_STRIP_FLIPPED,
	RPGEO_QUAD_ABC_BCD,
	RPGEO_QUAD_ABC_ACD,
	RPGEO_QUAD_ABC_DCA,
	NUM_RPGEO_TYPES
} rpgeoPrimType_e;
```


*idxData is a pointer to the face index data (buffer), afair. Surprise. 

Most common "PrimTypes" are RPGEO_TRIANGLE and RPGEO_TRIANGLE_STRIP.
## Post #4
- Username: marryjoy6374
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 20, 2023 10:05 am
- Post datetime: 2023-10-20T02:07:39+00:00
- Post Title: Need Support Regarding Noesis

The code or API call rapi.rpgCommitTriangles you're referring to seems to be specific to a particular software, framework, or game engine, and its logic may not be universally known or standardized [heardle](https://heardlewordle.io/). To understand the logic behind this code, you would need to refer to the documentation or resources provided by the software or framework where it's used.
