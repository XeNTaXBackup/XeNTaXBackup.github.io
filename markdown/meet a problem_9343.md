## Post #1
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-07-24T10:24:31+00:00
- Post Title: meet a problem

To Mr.Adult
I'm importing my custom mesh format into noesis. I do this because I needs it's export function as a mesh convertor.
I've done most of it. but still two problems.
1st problem is:
my c++ code uses the rpgBegin(TRIANGLE) and rpgEnd() pair to import triangles, this method surely produces large mout of duplicated vertices.
so after it, I called optimize(), it cuts down the duplicated vertices as wish, but I got a vertex number of less than the original mesh.
the result is: original mesh 1794 vertices, noesis optimized mesh has 1119 vertices.

I'm interested in what happened behined the optimize() call and can you tell me is there a way to import the same vertex with the mesh?
## Post #2
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-24T10:51:16+00:00
- Post Title: meet a problem

Try using:

rapi->rpgBindPositionBuffer()
rapi->rpgCommitTriangles()

You can have a look at the bayonetta script on how these are used.
## Post #3
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-07-24T12:53:18+00:00
- Post Title: meet a problem

> Reply from Demonsangel
>
> Try using:

rapi->rpgBindPositionBuffer()
rapi->rpgCommitTriangles()

You can have a look at the bayonetta script on how these are used.

Thanks Demonsangel! these function looks extactly I need. I can see there is still binding of bones and weights, I think these are the suitable functions all. I'll try.
