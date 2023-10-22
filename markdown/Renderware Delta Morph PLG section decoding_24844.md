## Post #1
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2021-12-13T09:47:26+00:00
- Post Title: Renderware Delta Morph PLG section decoding

Digging one game, extracting resources, now doing skeletal meshes. The game is old 2007-2008 (psp-ps2), ps2 version. The engine is a modification of renderware, I came across a section in a file called Delta Morph PLG, about which there is no information on the network at all. It is only known that this is not a DMA format. I managed to think of the structure (chunk of the dff file), which is something like this: 

```
    uint32_t count;
    Record recs[count];
};
struct Record {
    uint32_t nameLength;
    char name[nameLength]; //name of delta
    uint32_t unknown; //constant 18
    uint32_t unknown; //constant 6, may be number components in data1
    uint32_t size;
    uint32_t count;
    char data0[size]; //may be contain data distribution to mesh, usually large and small numbers alternate
    float data1[count * 6]; //main data, may be vec3 normals deltas of count and after vec3 vertex deltas of count
    float data2[4]; //may be bounding sphere xyzr
};
```

The mesh itself looks like this 

contains 587 points for each uv, pos, normal, as well as 1310 indexes of the Triangle_Strip (format, ps2 always have grids in this form)
Model in attachment in gltf format (all data in the Traviso.bin binary file as float, in order of position, normals, texture coordinates, then uint32_t indices). I chose this format because it is simple (too lazy to study fbx, sdk is not very clear, but what I want is ideal) and its description is textual (in my favorite json), and the data is in binary form that is ready to be loaded into the video card. I know about collage, but this format is entirely textual, based on xml I don't like and is outdated.
The Delta Morph PLG chunk contains 12 facial states

```
18      6       54      107     Travis_Eyes_Open
18      6       102     320     Travis_Oat
18      6       84      270     Travis_Cage
18      6       91      293     Travis_Wet
18      6       92      200     Travis_Bump
18      6       88      248     Travis_Size
18      6       104     235     Travis_Frown
18      6       140     239     Travis_Smile
18      6       68      131     Travis_Blink
18      6       38      78      Travis_RaiseRightEye
18      6       94      253     Travis_Fave
18      6       46      68      Travis_RaiseLeftEye
```

There are only 587 points in the grid, and the deltas data are always much less (the count column), which means that they must somehow be correlated with the grid. This is my question. I have no ideas. For the morph, there is no more data anywhere, so it's worth digging this section, namely the data0 field, which is less than deltas in size.
An example of this field has 3 records (the smallest) 

```
7F 0A 93 01 82 01 84 04 81 18 86 24 83 11 84 01 87 06 81 17 83 02 81 08 82 43 81 03 93 01 82 01 83 02 81 04 81 0F 86 23 82 10 84 01 87 04 81 10 83 01 82 07 82 2F
Travis_RaiseRightEye
7F 04 81 05 9C 03 81 01 81 01 83 11 87 24 83 11 84 01 8F 09 82 0B 83 01 83 02 81 04 82 43 81 1C 81 55 81 01 81 59
Travis_RaiseLeftEye
7F 04 81 1E 83 5D 81 01 81 17 82 0F 81 4E 81 03 82 01 8C 02 81 02 86 02 81 01 81 01 83 0F 85 23 82 10 84 01 8D 0F 83 01 82 02 81 04 82 2F
```

Hopefully it's not just any Huffman codes or binary trees or opcodes. Judging by the sample, the number is not always even, more and small numbers always alternate, 81 82 83 are often found.
In the attachment Travis_Eyes_Open-587.deltamorph is one record without a name (starts with 2 unknown numbers) and travis.deltamorph is the entire section.
For several days now I have been puzzling over how to correlate deltas and grid vertices. Although the section with data on points has 1 more set of indices for the mesh (with which it did not work to build a mesh), but it is one for the entire mesh, and the set of indices I used is considered an optimized set. It is unlikely to be useful, besides, it has 954 face 3 indexes + material index, and the set of points to which the indexes are applied is the same. I think deltas should be applied to grid points and has nothing to do with indices. And the data0 field should contain the point numbers.
[Travis.7z](https://xentaxbackup.github.io/file/21393_Travis.7z)
## Post #2
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2021-12-14T13:56:18+00:00
- Post Title: Renderware Delta Morph PLG section decoding

Found example from rwsdk. Mesh have 1908 points and Delta Morph PLG have 1908 points, but section have 16 byte length

```
FE FE FE FE FE FE FE FE FE FE FE FE FE FE FE 92
```

All constants some equal

```
18 6 16 1908 smile01
```

Archive with example [link](https://www27.zippyshare.com/v/Uxm4ulWD/file.html) (file too big for attach)

More easy for reversing (but stiil impossible, because not known) binary opengl file from pc...
## Post #3
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2021-12-22T08:42:37+00:00
- Post Title: Renderware Delta Morph PLG section decoding

i found solution, simple lossless compression, RLE
first bit flag (mask 0x80) if 1 then include indices else exclude, other bits data (mask 0x7F)
example

```
FE FE FE FE FE FE FE FE FE FE FE FE FE FE FE 92
```

FE : 0xFE & 0x80 != 0 -> include, count: 0xFE & 0x7F = 0x7E = 126
92 : 0x92 & 0x80 != 0 -> include, count: 0x92 & 0x7F = 0x12 = 18
in result 126 + ... + 126 + 18 = 1908, include all indices from 0 to 1908
for my model eyes open and smile



Screenshot_15.png (246.29 KiB) Viewed 46 times
