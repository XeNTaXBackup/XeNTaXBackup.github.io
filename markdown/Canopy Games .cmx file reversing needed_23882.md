## Post #1
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-05-16T07:55:18+00:00
- Post Title: Canopy Games .cmx file reversing needed

Has anyone tried to reverse .cmx files?

[https://www.mediafire.com/file/ymk0lswz ... mx.7z/file](https://www.mediafire.com/file/ymk0lswzv4b72h6/cmx.7z/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-16T13:39:25+00:00
- Post Title: Canopy Games .cmx file reversing needed

Using hex2obj (view link in my sig):
.



CarA_01-cmx.png (73.28 KiB) Viewed 52 times


One sub mesh (of 13), no higher lods expected.
## Post #3
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-05-16T19:16:34+00:00
- Post Title: Canopy Games .cmx file reversing needed

> Reply from shakotay2 ↑Sun May 16, 2021 9:39 pm at Sun May 16, 2021 9:39 pm
>
> 
Using hex2obj (view link in my sig):
.
CarA_01-cmx.png
One sub mesh (of 13), no higher lods expected.

About the UVs.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-16T21:11:38+00:00
- Post Title: Canopy Games .cmx file reversing needed

are assumed to start at 0x191c5, don't have the time to find suiting face indices:
.



uvs-cmx.png (6.97 KiB) Viewed 31 times



There's strings in the file, 13 x "VertexLoc", 13 x "VertexTexCoordsPass1Stage1" and 31 assumed starts of face indices blocks (000000000100000002000000).
So you need to fiddle out for yourself which FI block belongs to which vertex or uv block.
