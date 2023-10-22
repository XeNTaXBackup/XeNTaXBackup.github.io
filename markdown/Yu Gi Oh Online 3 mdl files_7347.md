## Post #1
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-12T11:47:47+00:00
- Post Title: Yu Gi Oh Online 3 mdl files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-01T22:36:26+00:00
- Post Title: Yu Gi Oh Online 3 mdl files

Format uses a single byte to identify the data that follows.

It starts with a 4-byte identifier and you can see the YO3 clearly.
Then there are 4 more bytes which might mean something, and then you start reading a byte and parsing the data accordingly.

0x00, don't know
0x01 is followed by a short
0x02 is followed by a material
0x03 is followed by a texture name
0x04, don't know
0x0A is followed by a bone name
0x0B is followed by a 4x4 matrix (often seen in conjunction with bone names)
0x0C, don't know
0x14 is the start of a mesh.
0x18 is the mesh material list (assigning material to face)
0x19 is a mesh material entry
0xFF means EOF



The name of this "mesh" is "ashi" which is legs
The previous one I was looking at was "kao" (face) and it did look like someone's face.

EDIT:

There is a section of data that comes right after the coords, and before the UV.
It is rather odd. It might actually be indices, but it's not obvious how they are drawn.



The light-blue highlighted integers are the numbers that actually represent something. The one on the bottom is the number of vertices (followed by UV data). The one on the top is the integer that appears immediately after the coords.

Then there's the highlighted section.

EDIT2:

After searching the file for any other occurrences of these integers, the one that appears after the coords also appears again after the UV section, which is followed by a bunch of bytes like 1 1 1 1 1 1 0 0 2 2 1 1, followed by material names.

This may suggest that the material for each face is individually assigned (like the direct3D .x format), and that integer is in fact the number of faces.

Though, that doesn't make it any easier because although I know how many indices there are, it's not immediately obvious how the faces should be drawn; whether they are all triangles, or could have quads (much like the .x format).

Those 3's and 4's may provide some hints, like maybe "the next 15 vertices are triangles" or "the next 60 vertices are quads." Basically repeat until you've dealt with every vertex, and then move on to the UV section. But that isn't consistent either.
## Post #3
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-01-03T01:14:47+00:00
- Post Title: Yu Gi Oh Online 3 mdl files

Awesome finale, I guess that's a whole lot of work huh.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T06:50:18+00:00
- Post Title: Yu Gi Oh Online 3 mdl files

Looked at this format again briefly.
The faces are still absolutely no sense to me.



This particular model has 0x58 (88) vertices. It also has the same number of UV's.
It has 0x18 faces (or something).

0x16 always appears before the UV count, so presumably that's the byte tag that indicates the start of UV's.

So there's 3 odd bytes that I don't understand.
Here's another file



That 3C might be something useful, but...



Maybe not.

Oh well, makes no sense to me.
There is no explicit index. Some meshes have 4 vertices (rectangle), and then that face chunk would just say "4", followed by some possibly large byte, followed by 0x16 and then UV stuff.
