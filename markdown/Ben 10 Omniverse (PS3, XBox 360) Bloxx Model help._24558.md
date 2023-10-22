## Post #1
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-10-01T16:02:57+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

I managed to find the vertices offset and the whole set of vertices for Bloxx's mesh.
Anyone good at Hex2obj would help me get the Bloxx model?
Vertices offset (starting offset): 0x2387
Vertices count: 2474
Here is a image for the Bloxx model data in AXE.



bloxx_face_indices_problem.png (70.34 KiB) Viewed 203 times


And here's a link for the Bloxx model or decompressed data of Bloxx.
[https://drive.google.com/file/d/1CVlERq ... sp=sharing](https://drive.google.com/file/d/1CVlERqAGYxBnZXzmXDvvMGQebBXSKw-K/view?usp=sharing)
(i understand now that I know how to get the vertices offsets from .et_decomp files)
.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-01T16:32:39+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

> Reply from lilyampykidXeNTaXalt ↑Sat Oct 02, 2021 12:02 am at Sat Oct 02, 2021 12:02 am
>
> (i understand now that I know how to get the vertices offsets from .et_decomp files)I have no idea which is the criterion you used to choose that offset.  
This is what I found:
.



Bloxx.png (126.93 KiB) Viewed 195 times


I'm pretty sure this model has been analysed perfectly already - somewhere in the forum. Why not use that?

I have no idea, interest, time to solve the face indices riddle (as I've mentioned several times already).
## Post #3
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-10-01T16:35:26+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

I used HexEdit to find the model's vertices or ModelResearcher to find the offset and vertices count.
I'll solve the face indices as fast I can.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-01T17:32:36+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

It's already done - stupid me used a wrong vertex start address, in fact it's 0x143F:
.



done.png (68.4 KiB) Viewed 181 times
## Post #5
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-10-01T18:04:56+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

Thanks, dude! You are the best for researching any Ben 10 Omniverse 1 models.
I like the way how Bloxx looks when he has so many triangles.
Edit: What's the texcoord address again?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-02T02:11:44+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

> Reply from lilyampykidXeNTaXalt ↑Sat Oct 02, 2021 2:04 am at Sat Oct 02, 2021 2:04 am
>
> 
Thanks, dude! You are the best for researching any Ben 10 Omniverse 1 models.Surely not- but maybe the most patient one. 

> Edit: What's the texcoord address again?I have no idea - try "UV pos" 12 or 8. But "uvs" look weird then, maybe they are indexed or something like that.
## Post #7
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-10-03T14:52:09+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

Tried both, plus I resolved the offset for the vertices on Heatblast.et_DECOMP.
.
offset for verts: 1547
verts here: 3998
offset for face indices: 2096b
count for faces: 9315
Can I get some help here? some indices and verts may be missing, try to resolve the offsets too. when I set verts offset on 1547, the model looked fine with a better resolution but face indices are missing, same goes for vertices
edit: sorry I had to fix the word "fixes to help"
## Post #8
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-10-03T15:57:12+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

I know there is 3 submeshes of Young Ben and can someone help me rip the 3 submeshes?
Here's the Google Drive link:
[https://drive.google.com/file/d/1F3nTyX ... sp=sharing](https://drive.google.com/file/d/1F3nTyXkbr4wxl_BI-tmgEws-1Pzsz0Xa/view?usp=sharing)
Well there is 3 submeshes of Young Ben to be called:
1. the body
2. the omnitrix
3. the hair
## Post #9
- Username: SpongeBotTronPants
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 08, 2023 12:59 am
- Post datetime: 2023-01-07T17:54:44+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.

Heya, what's the UV data for the model? I forgotten, so I would love to rip the Bloxx UV data.
Sorry if I bump the post if it is 1 year old.
## Post #10
- Username: SpongeBotTronPants
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 08, 2023 12:59 am
- Post datetime: 2023-01-21T08:33:54+00:00
- Post Title: Ben 10: Omniverse (PS3, XBox 360) Bloxx Model help.


