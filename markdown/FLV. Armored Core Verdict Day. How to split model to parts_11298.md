## Post #1
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-10T13:18:23+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

Template updated. At Now, for Xbox 360 FLV container:

```
{
    FLVENDIANESS_BIG = 0x42,
    FLVENDIANESS_LITTLE = 0x4C
} FLVENDIANESS;


typedef enum<DWORD> _D3DDECLTYPE
{
    D3DDECLTYPE_FLOAT1,
    D3DDECLTYPE_FLOAT2,
    D3DDECLTYPE_FLOAT3,
    D3DDECLTYPE_FLOAT4,
    D3DDECLTYPE_INT1,
    D3DDECLTYPE_INT2,
    D3DDECLTYPE_INT4,
    D3DDECLTYPE_UINT1,
    D3DDECLTYPE_UINT2,
    D3DDECLTYPE_UINT4,
    D3DDECLTYPE_INT1N,
    D3DDECLTYPE_INT2N,
    D3DDECLTYPE_INT4N,
    D3DDECLTYPE_UINT1N,
    D3DDECLTYPE_UINT2N,
    D3DDECLTYPE_UINT4N,
    D3DDECLTYPE_D3DCOLOR,
    D3DDECLTYPE_UBYTE4,
    D3DDECLTYPE_BYTE4,
    D3DDECLTYPE_UBYTE4N,
    D3DDECLTYPE_BYTE4N,
    D3DDECLTYPE_SHORT2,
    D3DDECLTYPE_SHORT4,
    D3DDECLTYPE_USHORT2,
    D3DDECLTYPE_USHORT4,
    D3DDECLTYPE_SHORT2N,
    D3DDECLTYPE_SHORT4N,
    D3DDECLTYPE_USHORT2N,
    D3DDECLTYPE_USHORT4N,
    D3DDECLTYPE_UDEC3,
    D3DDECLTYPE_DEC3,
    D3DDECLTYPE_UDEC3N,
    D3DDECLTYPE_DEC3N,
    D3DDECLTYPE_UDEC4,
    D3DDECLTYPE_DEC4,
    D3DDECLTYPE_UDEC4N,
    D3DDECLTYPE_DEC4N,
    D3DDECLTYPE_UHEND3,
    D3DDECLTYPE_HEND3,
    D3DDECLTYPE_UHEND3N,
    D3DDECLTYPE_HEND3N,
    D3DDECLTYPE_UDHEN3,
    D3DDECLTYPE_DHEN3,
    D3DDECLTYPE_UDHEN3N,
    D3DDECLTYPE_DHEN3N,
    D3DDECLTYPE_FLOAT16_2,
    D3DDECLTYPE_FLOAT16_4,
    D3DDECLTYPE_UNUSED
} D3DDECLTYPE;

typedef enum<DWORD> _D3DDECLUSAGE
{
    D3DDECLUSAGE_POSITION = 0,
    D3DDECLUSAGE_BLENDWEIGHT = 1,
    D3DDECLUSAGE_BLENDINDICES = 2,
    D3DDECLUSAGE_NORMAL = 3,
    D3DDECLUSAGE_PSIZE = 4,
    D3DDECLUSAGE_TEXCOORD = 5,
    D3DDECLUSAGE_TANGENT = 6,
    D3DDECLUSAGE_BINORMAL = 7,
    D3DDECLUSAGE_TESSFACTOR = 8,
    D3DDECLUSAGE_COLOR = 10,
    D3DDECLUSAGE_FOG = 11,
    D3DDECLUSAGE_DEPTH = 12,
    D3DDECLUSAGE_SAMPLE = 13
} D3DDECLUSAGE;


void AlignTo(int value)
{
    if((FTell()%value) > 0)
    {
        FSeek(FTell() + value - (FTell()%value));
    }
}

typedef struct _FLVFloat3
{
    float x, y, z;
} FLVFloat3 <read=ReadFLVFloat3>;

string ReadFLVFloat3(FLVFloat3& f3)
{
    string s;
    SPrintf(s, "%f, %f, %f", f3.x, f3.y, f3.z);
    return s;
}

struct FLVDescriptor
{
    DWORD Unknown0;
    DWORD Unknown1 <format=hex>;
    DWORD Unknown2 <format=hex>;
    DWORD Unknown3 <format=hex>;
    DWORD NumIndexBuffers;
    DWORD NumVertexDestriptors;
    DWORD NumMaterialParams;
    DWORD Reserved[9];
};

typedef struct _FLVMaterialDescriptor
{
    DWORD MaterialNameOffset <format=hex>;
    DWORD ShaderNameOffset <format=hex>;
    DWORD TextureCount;
    DWORD Index;
    DWORD DataSize;
    DWORD MatLibOffset <format=hex>;
    DWORD Reserved[2];
} FLVMaterialDescriptor <read=ReadMaterialDescriptor>;

string ReadMaterialDescriptor(FLVMaterialDescriptor& md)
{
    string out;
    string s1 = ReadString(md.MaterialNameOffset);
    string s2 = ReadString(md.ShaderNameOffset);

    SPrintf(out, "Material Name: %s, Shader Name: %s", s1, s2);

    return out;
}


struct FLVBonesHierarhyDescriptor
{
    DWORD Unknown0;
    DWORD Index;
    DWORD Unknown2;
    DWORD Unknown3;
    DWORD Unknown4;
    DWORD Size0;
    DWORD Unknown6;
    DWORD Offset0 <format=hex>;
    DWORD Size1;
    DWORD Offset1 <format=hex>;
    DWORD Size2;
    DWORD Offset2 <format=hex>;
};

struct FLVIndexBufferDescriptor
{
    DWORD LOD <format=hex>;
    DWORD Flags <format=hex>;
    DWORD NumIndices;
    DWORD Offset <format=hex>; // + DataStart
    DWORD IndexBufferSize;
    DWORD Reserved[3];
};

struct FLVVertexBufferDescriptor
{
    DWORD Unknown00;
    DWORD VertexDescriptorIndex;
    DWORD Stride;
    DWORD NumElements;
    DWORD Unknown05;
    DWORD Unknown06;
    DWORD Size;
    DWORD Offset <format=hex>; // + DataOffset
};


struct FLVVertexDesctiptor
{
    DWORD NumElements;
    DWORD Unknown2;
    DWORD Unknown3;
    DWORD Offset <format=hex>;
};

struct FLVVertexElementDesctiptor // ???
{
    DWORD Stream;
    DWORD Offset;
    D3DDECLTYPE Type;
    D3DDECLUSAGE Usage;
    DWORD Index;
};


typedef struct _FLVMaterialParameter
{
    DWORD TextureNameOffset <format=hex>;
    DWORD ShaderParameterOffset <format=hex>;
    float Unknown2;
    float Unknown3;
    DWORD Unknown4 <format=hex>;
    DWORD Unknown5;
    DWORD Unknown6;
    DWORD Unknown7;
} FLVMaterialParameter <read=ReadMaterialParams>;

string ReadMaterialParams(FLVMaterialParameter& mp)
{
    string s;
    SPrintf(s, "TN: %s, SP: %s", ReadString(mp.TextureNameOffset), ReadString(mp.ShaderParameterOffset));
    return s;
}

struct FLVPartDescriptor
{
    FLVFloat3 Translation;
    SHORT Unknown30;
    SHORT Unknown31;
    FLVFloat3 Euler;
    DWORD BoneIndex;
    FLVFloat3 Unknown8;
    SHORT UnknownB0;
    SHORT UnknownB1;
    FLVFloat3 UnknownC;
    SHORT UnknownF0;
    SHORT UnknownF1;
};



typedef struct _FLVBone
{
    FLVFloat3 Translation;
    DWORD NameOffset;
    FLVFloat3 Euler;
    SHORT ParentIndex;
    SHORT FirstChildIndex;
    FLVFloat3 Scale;
    SHORT FirstSiblingIndex;
    SHORT CopyOfIndex;
    FLVFloat3 BBLower;
    WORD IsNub;
    WORD Unknown5;
    FLVFloat3 BBUpper;
    DWORD Unknown6;
    DWORD Reserved[12];
} FLVBone <read=ReadPart>;

string ReadPart(FLVBone& p)
{
    string s;
    SPrintf(s, "Name: %s, Parent: %d, Child0: %d, Child1: %d, Child2: %d", ReadString(p.NameOffset), p.ParentIndex, p.FirstChildIndex, p.FirstSiblingIndex, p.CopyOfIndex);
    return s;
}

struct MatLibHeader
{
    DWORD Unknown0;
    DWORD Unknown1;
    DWORD Unknown2;
    DWORD Reserved[9];
};

local int i;

struct FLVHeader
{
    BYTE Signature[6];
    FLVENDIANESS Endianess;
    if(Endianess == FLVENDIANESS_BIG)
        BigEndian();
    
    DWORD Version <format=hex>;
    DWORD DataOffset <format=hex>;
    DWORD DataSize;
    DWORD NumParts;
    DWORD NumMaterials;
    DWORD NumBones;
    DWORD NumVertexBuffers;
    DWORD NumPartsHierarhyDescriptors;
    float BBox[6];
};

FLVHeader header;
if((header.Version == 0x2000F) || (header.Version == 0x20009))
{
FLVDescriptor flvDescriptor;
FLVPartDescriptor partsDescriptors[header.NumParts];
FLVMaterialDescriptor Materials[header.NumMaterials];
FLVBone bones[header.NumBones];
FLVBonesHierarhyDescriptor bonesHierarhyDescriptor[header.NumPartsHierarhyDescriptors];
FLVIndexBufferDescriptor indexBufferDescriptor[flvDescriptor.NumIndexBuffers];
FLVVertexBufferDescriptor vertexBufferDescriptor[header.NumVertexBuffers];
FLVVertexDesctiptor vertexDesctiptor[flvDescriptor.NumVertexDestriptors];
FLVMaterialParameter materialParameter[flvDescriptor.NumMaterialParams];

for(i = 0; i < flvDescriptor.NumVertexDestriptors; i++)
{
    FSeek(vertexDesctiptor[i].Offset);
    struct { FLVVertexElementDesctiptor data[vertexDesctiptor[i].NumElements]; } vertexElementDesctiptor;
}

for(i = 0; i < header.NumPartsHierarhyDescriptors; i++)
{
    FSeek(bonesHierarhyDescriptor[i].Offset0);
    struct { DWORD BoneIndices[bonesHierarhyDescriptor[i].Size0]; } boneSegment;
    FSeek(bonesHierarhyDescriptor[i].Offset1);
    struct { DWORD IndexBufferIndices[bonesHierarhyDescriptor[i].Size1]; } indexBufferSegment;
    FSeek(bonesHierarhyDescriptor[i].Offset2);
    struct { DWORD VertexBufferIndices[bonesHierarhyDescriptor[i].Size2]; } vertexBufferSegment;
}

if(Materials[0].MatLibOffset)
{
    FSeek(Materials[0].MatLibOffset);
    MatLibHeader matLibHeader;
}
for(i = 0; i < header.NumMaterials; i++)
{
    FSeek(Materials[i].MaterialNameOffset);
        struct
        {
            string MaterialName;
            FSeek(Materials[i].ShaderNameOffset);
            string ShaderName;
            struct
            {
                string TextureName;
                string TextureShaderParamName;
            } textures[Materials[i].TextureCount] <optimize=false>;
        } material;
}
AlignTo(16);
struct { string Name; } boneNames[header.NumBones] <optimize=false>;

////////////////////////////////////////////////////////////////////////////////////
// Data Start
////////////////////////////////////////////////////////////////////////////////////
FSeek(header.DataOffset);
for(i = 0; i < flvDescriptor.NumIndexBuffers; i++)
{
    FSeek(header.DataOffset + indexBufferDescriptor[i].Offset);
    struct { WORD vd[indexBufferDescriptor[i].NumIndices]; } IndexBuffer;
}
for(i = 0; i < header.NumVertexBuffers; i++)
{
    FSeek(header.DataOffset + vertexBufferDescriptor[i].Offset);
    struct { BYTE vd[vertexBufferDescriptor[i].Size]; } VertexBuffer;
}
}
```


Sample FLV-files from Xbox 360 build.
[http://rghost.ru/53252249](http://rghost.ru/53252249)
________________________________
Sorry my bad English. I am Russian.
## Post #2
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-10T19:51:28+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

template is updated
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-11T22:17:19+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

Are these from PS3? Because at offset 0x1DC0 of cr0010.flv I see PS3 EDGE SDK INDEX BUFFER COMPRESSION.
## Post #4
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-12T14:37:42+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

> Reply from howfie
>
> Are these from PS3? Because at offset 0x1DC0 of cr0010.flv I see PS3 EDGE SDK INDEX BUFFER COMPRESSION.
Yep, that’s right. PS3.

I decided to give up a models from PS3. Now I work with models from X360. There is much easier. Simple tri-strips.

Thanks for information about EDGE-compression. I suspected the presence of compression, but could not determine the algorithm. Now everything becomes clear.
## Post #5
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-12T18:15:28+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

It works.
## Post #6
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-03-22T08:02:32+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

Now I have new question. How can I split model to parts?
## Post #7
- Username: unkownac
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 18, 2014 2:15 pm
- Post datetime: 2014-09-03T13:07:10+00:00
- Post Title: FLV. Armored Core: Verdict Day. How to split model to parts?

May i ask a qusetion? what is the script use for
