## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-29T15:04:30+00:00
- Post Title: Different face storage schemes

I was reading [http://en.wikipedia.org/wiki/Polygon_mesh](http://en.wikipedia.org/wiki/Polygon_mesh) and noted the various different ways to store information and thought it was pretty useful. Most of the ones I've run into so far are the face-vertex type.

Are there any other common ones that aren't listed here?
## Post #2
- Username: drunkenchipmunk
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 24, 2009 4:05 pm
- Post datetime: 2011-08-30T10:03:00+00:00
- Post Title: Different face storage schemes

> Reply from finale00
>
> I was reading http://en.wikipedia.org/wiki/Polygon_mesh and noted the various different ways to store information and thought it was pretty useful. Most of the ones I've run into so far are the face-vertex type.

Are there any other common ones that aren't listed here?

For games, vertex/face storage tries to match as closely as possible the hardware that's going to run it... the trend these last years has been to have a raw sequence of vertices with extra information (normals, UVs, skin weights, etc) and a raw list of vertex indices that can be processed as triangles, triangle strips, etc, so that's what we're finding most of the time.

Found some odd formats in the past, thought.

Doom 3 , for example, does a software preprocess of the vertices, so, for each vertex it has a variable number of bone/weights, thanks it's text based it's easy to decipher... if it was an undocumented binary it would have been damn hard to read.

Many PSX1 games store the vertex positions as signed shorts instead of floats, so looking for x3F800000 sometimes gives no results, so vertices are overlooked.

Also found one or two games in which you could only find faces, the faces didn't have vertex indices, but the vertex positions of each triangle corner already in them, that was on a PS2 game, I think, guess that maps well with PS2 hardware instead of the usual vertex/index buffers, which map nVidia/ATI hardware
