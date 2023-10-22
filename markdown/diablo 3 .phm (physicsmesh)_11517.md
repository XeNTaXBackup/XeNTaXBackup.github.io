## Post #1
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-05-18T11:44:41+00:00
- Post Title: diablo 3 .phm (physicsmesh)

I'm checking out the .phy files v24 (for d3-rs) and have some "gaps". Maybe someone has some ideas on what the data there could mean.
Basically the file is a header and 3 big "chunks": triangles (40 in my testcase), vertices (30) and "something" (39).

Issue 1:

struct MeshTriangle 
{
    int VertexIndex[3];  // index into vertices
    int unk[3];               // could be index into vertices (max-values match) - but ends up as 'garbage-triangles'
    short unk1;             // 0 ( always zero - at least in my testfile) 
    short unk2;             // -1  (always -1 - at least in my testfile)
};

The funny thing being that just connecting the vertices MeshTriangle.unk point into ends up in a garbled polygon-soup. Also, when looking at the values, there is an occasional -1 ( or 0xFFFFFFFF depending on wether you use signed/unsigned). This is usually the last value, but I've seen one place where the last two were -1. Any ideas what this could be? Maybe some smart way to create edges?

(left: using "VertexTriangle" - right: using "unk[3]" )
 

Issue 2:

I have an array of these and have no clue what it is supposed to be: 

struct D3PhysicsSomething // 4*2*2=16 bytes
{
    short s[3*2];
    unsigned short c;
    unsigned short s2;
};

Looking at 'Mooege' [http://fooo.fr/~vjeux/boub/d3/mooege/sr ... hysMesh.cs](http://fooo.fr/~vjeux/boub/d3/mooege/src/Mooege/Common/MPQ/FileFormats/PhysMesh.cs) it looks like it could be nodes or edges ( since I don't have anything for that yet, and apparently there was in the old fileformat) - but the structures look completely different. The values in "s[ ]" are too large to be indexes into vertices or any other array I have (at least in the .phy file), and they aren't floats either.

Below a screenshot with some values for 's'. One guess would be that the uv's also need some division, so maybe something similar is the case here... I tried just using those value/1000 and dividing those by 's2' but that ends up in a mess to see here: [http://www.kalmiya.com/images/diablo3/d ... unk3_lines](http://www.kalmiya.com/images/diablo3/d3_phm_chunk3_lines)

If I assume 'c' is an unsigned short, the max-value for my test-.phy is 1611 . 
If I assume 'c' is two bytes, the max values would be [0] being 211 and [1] being 2. 
These values don't match my array-sizes, so it's probably not indices into something - so what could it be?

s2 is always zero in my testcase, so it's a good bet that's its there for padding to 16 bytes.



Hope someone has some ideas, 

Regards
