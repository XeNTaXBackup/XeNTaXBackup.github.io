## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2015-01-31T00:49:09+00:00
- Post Title: Bad Company 2

So me and my friend are working on a reversing BFBC2 files using .PDB generated classes, we are stuck on. Finding anything pointing to vertex buffer layout, like 

vxpos, 0
vypos, 1
vzpos, 2

BoneIndex, 3
BoneWeights, 4

Uv`s, ....
Binormal,...

What is an industry standard name for this structure? vertex buffer?, vertex element map? vertex attribute layout?

So far I found this but it does not seem to be mesh related

```
{
 ShaderVertexElementUsage_Unknown = 0x0,
 ShaderVertexElementUsage_Pos = 0x1,
 ShaderVertexElementUsage_BoneIndices = 0x2,
 ShaderVertexElementUsage_BoneWeights = 0x3,
 ShaderVertexElementUsage_Normal = 0x4,
 ShaderVertexElementUsage_Tangent = 0x5,
 ShaderVertexElementUsage_Binormal = 0x6,
 ShaderVertexElementUsage_BinormalSign = 0x7,
 ShaderVertexElementUsage_WorldTrans1 = 0x8,
 ShaderVertexElementUsage_WorldTrans2 = 0x9,
 ShaderVertexElementUsage_WorldTrans3 = 0xA,
 ShaderVertexElementUsage_XenonIndex = 0xB
};
```
