## Post #1
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2013-07-03T22:29:06+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

Okay I have been, for a very long time, trying to crack this model format myself. I'm using maxscript and Hex Workshop and I've been able to import other model formats from other games but this format confounds me.

RoadTrain has found the Header and Block Definition data for me, but I'm still unable to find the data that makes up the vertices, I can't even find how many verts a file has.

Here's what I know:

This game was made by Ensemble Studios, so the model file might resemble one of their previous games.

File is either aligned to 16 or 32 bytes. Data is in Big Endian.
The files are a modified version of Granny3d's .gr model file, but I don't see how that's of any help.
All files have at least 1 bone: "GranyRootBone" and I think, but I'm not sure, that the files have lod data too.

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


```
{
  short unk;
  short arraycount; //number of floats / 3 (i don't think this is where the vertex data is though.)
  long null;
  float[arraycount*3] unk;
};
```

[Several_ugx_models.zip](https://dl.dropboxusercontent.com/u/43157158/several_ugx_models.zip)

Here's a zip file with 9 ugx files, some similar and varied. I just want to be able to find where the vertex data and face indices are at this point.
## Post #2
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2015-08-18T07:00:02+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

Sorry for necroposting, but wanted to share an idea.

It's quite possible that vertices are incoded in SHORTs instead of FLOATs.
If you look after GrannyRootBone, you will notice a pattern -- each stride is 16 bytes.

That's perfectly situated for 8 shorts making a vertex -- 3 for position, 3 for normals and 2 for uvmap.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-18T09:23:13+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

for barracks_damaged_01 the vertex stride is 28
but there are too many submeshes here - you'll need a script to build the whole mesh:



barracks_damaged_01.JPG (38.93 KiB) Viewed 195 times
## Post #4
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2015-08-18T11:23:14+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

1794 - vertices
1793 - indices
## Post #5
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2015-08-18T11:30:15+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

it's more interesting with assault_rifle_01

According to indices, there must be 480 vertices, but I only get 96...

Must have missed something..
[ugx.png](https://xentaxbackup.github.io/file/9556_ugx.png)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-18T13:33:09+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

> Reply from RoadTrain
>
> Must have missed something..nope - it's low poly models:



battle_rifle.JPG (15.86 KiB) Viewed 188 times
## Post #7
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2015-08-18T13:46:52+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

> Reply from shakotay2
>
> RoadTrain wrote:Must have missed something..nope - it's low poly models:
battle_rifle.JPG
Fine, but where are the rest of vertices? I have found only those located at 2440h, and there are only 96 of them with a 16 byte stride.

But according to indices, there must be 480 vertices. What's the point?
## Post #8
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2015-10-07T00:15:25+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

Oh wow fantastic, With that I should be able to write a maxscript importer, I am curious how the vertex count works though, maybe it has something to do with LOD models??
[http://www.datishop.com.br/media/catalo ... ars-46.jpg](http://www.datishop.com.br/media/catalog/product/4/2/42250_halowars-46.jpg)
The image in that link shows some of the UNSC vehicles and infantry, hard to find a good pic
There's some pretty good closeups in this video.
[https://www.youtube.com/watch?v=HxciOQjWEtc](https://www.youtube.com/watch?v=HxciOQjWEtc)
Looks to be about right though, hmm.
## Post #9
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2016-03-23T21:28:58+00:00
- Post Title: Halo Wars ugx files. Just need an expert's opinion.

> Reply from RoadTrain
>
> it's more interesting with assault_rifle_01

According to indices, there must be 480 vertices, but I only get 96...

Must have missed something..

So after some further investigation on my own of the formats, I'm getting some models that are doing what you say, They are low poly models but why would the model be saying there's more faces than there are verts?

Also I'm wondering how the stride is different for the models with shorts instead of half floats, and what tells the program if it's half floats or shorts?
