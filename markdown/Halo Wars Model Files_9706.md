## Post #1
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2012-10-03T05:43:38+00:00
- Post Title: Halo Wars Model Files

Hello. I have a bunch of model files from Halo Wars. They don't appear to be compressed or encrypted, just raw model files. I believe they are big endian because of their origin, but am unsure. I was wondering if any of you could help me get it into 3ds max via maxscript or some 3rd party program or anything that can get it into a mainstream model format that can be read by some modeling program.

[https://dl.dropbox.com/u/43157158/infectionform_01.ugx](https://dl.dropbox.com/u/43157158/infectionform_01.ugx)
[https://dl.dropbox.com/u/43157158/infectedbrute_01.ugx](https://dl.dropbox.com/u/43157158/infectedbrute_01.ugx)
[https://dl.dropbox.com/u/43157158/frcreepbase_01.ugx](https://dl.dropbox.com/u/43157158/frcreepbase_01.ugx)
## Post #2
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2012-10-05T07:31:41+00:00
- Post Title: Halo Wars Model Files

Okay I've figured out a lot of the header, but I can't seen to determine a float point.

```
[byte4] ???
[byte4] Model Type (character, vehicle, scenery)
[byte4] File size
[byte4] Tag Type (model, texture, animation)
[byte4] ???
[byte12] Blank
[byte4] points to end of geometry
[byte4] ???
[byte4] ???
[byte4] ???
[byte4] ???
[byte4] ???
[byte4] nil
[byte4] ???
[byte4] points to after strings area
[byte4] ??
[byte4] ??
[byte4] ??
[byte4]
[byte4] Geometry Offset
[byte4] Geometry Block Length
```


I don't know if that's the geometry block it's pointing to, but this is what it points to.



Does this make any sense to anyone?

Any way someone could just tell me where they think the vertex data might be?

This is also in the file but nothing in the header points to it.




more things:
[*]Game was made by Ensemble Studios
[*]File is in Big Endian
[*]Animations were done with Granny by RAD Game Tools, might be part of the model format?
[*]From what I can tell it's a pretty simple model format.
## Post #3
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2012-10-05T22:36:38+00:00
- Post Title: Halo Wars Model Files

Well files are big endian.
after the filesize (position 16) goes the number of blocks.
the header

```
{
  long magic;
  long headerLength; //?? =32 bytes
  long unk1; //hash?
  long fileSize; 
  short nBlocks; //number of blocks
  short null1; //=0
  long unk2; //hash?
  long null2[2];// 8 zero bytes
};
```

then go block definitions
each block is described as follows

```
{
  long null;//zeros
  long blockType;//1792-1797
  long offset;// the position in the file where the block starts
  long size; //size of block data
  long unk1; //maybe some form of hash
  long unk2; //??
};
```


Note that blocks are aligned to 16 bytes.
1793 block is clearly indices data.
also you can easily find floats, there are lots of them. You need to try loading them.
## Post #4
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2012-10-06T03:47:14+00:00
- Post Title: Halo Wars Model Files

Thanks for the reply. Now I'm at block 1793's offset (0x3c80) and It kind of looks like it's put together in shorts, but verts would be floats for position in 3d space right? You meant vertices by indices right?
## Post #5
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2012-10-06T04:23:07+00:00
- Post Title: Halo Wars Model Files

> Reply from ptowery
>
> Thanks for the reply. Now I'm at block 1793's offset (0x3c80) and It kind of looks like it's put together in shorts, but verts would be floats for position in 3d space right? You meant vertices by indices right?
I suppose the vertices are somewhere above. Floats are aligned to 4 bytes probably so you should easily find them.
By indices I mean indices. Index is a short that refers to specific vertex. Three (usually) indices form a polygon.
