## Post #1
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-09-22T08:18:54+00:00
- Post Title: Lego Star Wars 2

The xbox version has both the Packed (.fpk) and unpacked files available to edit.

So I jumped right into the compiled model (.HX2) becuase I wanted the textures and geometry.

These are complete enough to rip textures (.DDS).

```
{
	dword		FileSize;
	dword		null;
	dword		NumberTextures;
	dword		TextureOffset;
	dword		NumberMaterials;
	dword		MaterialOffset;
	dword		NumberJoints;
	dword		Offset;
	dword		Offset;
	dword		Offset;
	dword		unknown;
	dword		Offset;
	dword		SkeletonIndexOffset;
	dword		SkeletonIndexSize;
	dword		unknown;
	dword		offset;
	dword		unknown;
	dword		offset;
	dword		unknown;
	dword		offset;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	float		unknown;
	dword		unknown;
	dword		unknown;
	dword		unknown;
	dword		unknown;
	dword		unknown;
	dword		SizeOfBlocks;	//.htm == Unaccounted Memory
	//
	struct	TextureBlock		TBlock[NumberTextures];
	struct	MaterialBlockHeader	MBlockHeader[NumberMaterials];
	struct	MaterialBlock		MBlock[NumberMaterials];
	char				SkeletonIndex[SkeletonIndexSize]; //Can't do Null terminated strings in HW
	//
};

```


```
{
	dword		Unknown; //Offset??
};
struct MaterialBlockHeader //Per Material
{
	dword		MaterialBlockOffset;	
};
struct MaterialBlock //Per Material
{
	byte		Unknown[60];
	float		Unknown;
	dword		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	float		Unknown;
	dword		Unknown; //Offset??
	dword		Unknown;
	dword		Unknown;
	dword		Unknown;
	dword		Unknown;
	dword		Unknown;
	dword		Unknown;
	dword		Unknown;
	dword		Unknown;
	dword		Unknown; //Offset??
	dword		Unknown;
};

```


```
{
	char			ChunkID[4];
	dword			ChunkSize;
	dword			NumberTexures;
	dword			StartOffset;
	dword			TotalSize;
struct	TextureOffsets		TextureOffsets[NumberTexures];
};

struct TextureOffsets
{
	dword			Height;
	dword			Width;
	dword			Unknown;
	dword			Unknown;
	dword			Offset; //Minus the 20 byte Header
};

```


working on Vertex Data....

```
{
	char			ChunkID[4];
	dword			ChunkSize;
	dword			NumberVertexData;
	dword			Null;
	dword			Unknown;
	dword			TotalSize;
struct	VertexDataOffsets	VertexDataOffsets[NumberVertexData];
};

struct VertexDataOffsets
{
	dword			Size;
	dword			ID;
	dword			Offset; //Minus 24 byte header
};

```
## Post #2
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-09-25T05:16:02+00:00
- Post Title: Lego Star Wars 2

Getting quite a bit of text written up for this. Plus I'm starting to spec the model data as well.

Here's the Hex Workshop structures I'm using. If there's interest I'll continue working on it.
[HX2.rar](https://xentaxbackup.github.io/file/871_HX2.rar)
## Post #3
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2006-11-25T08:15:13+00:00
- Post Title: Lego Star Wars 2

Anyone still interested in this I have a DDS ripper installer

[http://www.spared-life.com/SparedLifeFi ... -Lego2.zip](http://www.spared-life.com/SparedLifeFiles/SLConverter-Lego2.zip)
