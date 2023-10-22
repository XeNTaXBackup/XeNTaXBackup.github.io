## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-07T15:55:04+00:00
- Post Title: PS2 packed weighted vertex data

I'm trying to deal with an issue here.
I've been working on a ps2 format that uses viftags but the way weighted vertices are stored confuses me.
Each model consists of bones, and those bones all offset to a table with offsets to model batches
The model batch header is something like:

```
UInt32 batchSize; //in multiples of 16
UInt32 matID;
UInt32 batchOffset;
UInt32 usedBoneCount;
UInt16 usedBoneID[usedBoneCount];

```


If the meshType is 1 then the batch doesn't use weights (usedBoneCount = 0) and the local position of the batch needs to be multiplied with the associated bone's transform
If the meshType >= 2 then the batch uses weights, and the usedBoneCount indicates how many bones are assigned to that batch.
I can parse meshType 1 just fine, but meshType 2 and up works a bit differently
You seek to the batchOffset and read till you hit the batchSize from the current position
Batches consist out of vif packets, the general structure of the meshType 2 meshes is (assuming a usedBoneCount of 2)

```
UInt16 faceCount;
UInt16 vertCount;
UInt16 arrFlag1;
UInt16 arrFlag2; //arrFlag 1 & 2 indicate what the following data contains.. eg: arrFlag1 bit 4 is always set when there is a 0x6C type viftag in the data

//VIFCode 0x6C, vertCount * (4 elements, 4 bytes each)
Vector3 pos;
float weight; //if weight is 0, then the pos values are also 0 (!?)

//VIFCode 0x68, vertCount * (3 elements, 4 bytes each)
Vector3 normal;

//VIFCode 0x14, upload data to vif

//VIFCode 0x6D, again

//VIFCode 0x6E, faceCount * (4 elements, 1 byte each)
byte fIndex1;
byte fIndex2;
byte fIndex3;
byte zero;

//VIFCode 0x6C, again
//The values that were zero in the first 0x6C packet, are now filled in in this packet

//VIFCode 0x68, second normals packet (!?)

//VIFCode 0x64, vertCount * (2 elements, 4 bytes each)
Vector2 uv;

//VIFCode 0x14, upload data to VIF

```


This structure would then repeat for the rest of the remaining size of the batch.
The last entry of usedBoneCount packets is always the only packet to have the face index and uvs.
Every entry contains a normal packet, which is odd.
Now, if I just parse the data as is, remove the null vertices and merge the 0x6C arrays into one vertex array and transform the object with the bone's transfrom it's assigned to, you get something like this:

For reference, this is how the model looks with only the modelType 1 batches


Which isn't quite right. Notice how mostly the areas where the objects connect are all screwed up.
So yeah I'm not quite sure how this works, I hope anyone else has an idea. If you need some more details just ask.
