## Post #1
- Username: Benny00
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 30, 2021 11:34 am
- Post datetime: 2022-09-29T23:29:19+00:00
- Post Title: Dead Island .MESH Files How to import

So i recently wanted to extract dead island assets and came come across the chrome r6 extractor, I tried it and got all the textures, as well as a bunch of other assets too

the meshes come out as:
[https://ibb.co/c83xjJT](https://ibb.co/c83xjJT)
[https://ibb.co/hsrRdpZ](https://ibb.co/hsrRdpZ)
0.Mesh
1.MeshFixup
2.VertexDara
3.IndexData
4.Skin
5.SkinFixups

here is a sample of a woman [https://www.mediafire.com/file/ti7ukeyc ... a.rar/file](https://www.mediafire.com/file/ti7ukeycf8ocxa5/woman_a.rar/file)

Here's Act 1 Sample [https://www.mediafire.com/file/6em3ett3 ... k.rar/file](https://www.mediafire.com/file/6em3ett3kifxmbh/act1a_PC_unpack.rar/file)

any idea on what can open a .mesh file tried the xps one but didn't work so must be unknown.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-06T19:15:56+00:00
- Post Title: Dead Island .MESH Files How to import

2.VertexData contains a decent point cloud (but couldn't make sense of the 3.IndexData):
.



VertexData.jpg (104.02 KiB) Viewed 213 times


(0.Mesh seems to contain a hat/point cloud.)
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-07T00:06:52+00:00
- Post Title: Dead Island .MESH Files How to import

> Reply from shakotay2 ↑Fri Oct 07, 2022 3:15 am at Fri Oct 07, 2022 3:15 am
>
> 
IndexData
using your results  
if find for the number of vertices in the "0.Mesh" file.
0x159660 >> "2661,237012,2941612..."
the offset is written there for them, and for indices.



head.png (14.36 KiB) Viewed 205 times
