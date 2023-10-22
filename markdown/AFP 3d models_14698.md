## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-07-29T00:47:09+00:00
- Post Title: AFP 3d models

Hope you guys can take a look on 3d model . Those files in Temp folder when you are playing. Those folders which I upload, just my thinking. I'm not sure about that.
 Edited
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-31T17:25:57+00:00
- Post Title: AFP 3d models

first submesh h2o file for f_00012b  

```
Vb1
36 12
0x6D 8091
040000
0x0 255

```

*image removed by request and replaced with h2o contents*

the vertices are Little Endian and the face indices are Big Endian
i used 010 editor to swap the byte order of the face indices before opening with Hex2obj

0x08 - number of vertices
0x10 - length of vertex block (divide length by number of verts to get vertex stride)
0x1c - absolute offset to 5 bytes before start of face indices 
0x28 - number of faces (multiply by 3 to get actual count, and multiply that by 4 to get length of data) 
0x2c - absolute offset to the length of submesh name
0x5589d - first submesh name
