## Post #1
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-06-25T05:00:05+00:00
- Post Title: Magna Carta: Phantom of Avalanche (PCport)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-25T08:55:47+00:00
- Post Title: Magna Carta: Phantom of Avalanche (PCport)

I am able to read some of the meshes in the file, but there is some strangeness going on.
## Post #3
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-25T16:07:42+00:00
- Post Title: Magna Carta: Phantom of Avalanche (PCport)

the strange thing is, the models share one vertex buffer.  but some of the vertex are crazy and way off in the middle of nowhere.  there is another array of shorts that corresponds to each vertex in the buffer.  the number is either -1 or some other value.  if its -1 then the vertex is a good vertex, if its something else than its a weird vertex.  


some of the models reference these weird vertex so i'm wondering if a polygon references a weird one (non -1) does it mean you are suppose to do something special like scan forward in the array until you find a good one and ref that instead?  or perhaps a strange vertex signifies the beginning a polygon strip and you should start hitting all the good vertex in a row until you get to another weird one, then stop? 

The model of the face refed no weird vertex so it came out good.  the model of some type of armour refed mostly good ones and a few weird ones.  the largest model in the file refed almost all weird ones so it looks like a giant mess of polygons.  I wonder if theses weird vertex are something to do with physics or some gpu trick to achieve some effect.

These are just ideas being I have not seen this before.  Trying stuff out.    Anyone else have seen something similar?
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-28T22:18:07+00:00
- Post Title: Magna Carta: Phantom of Avalanche (PCport)

> Reply from surix
>
> the strange thing is, the models share one vertex buffer.  but some of the vertex are crazy and way off in the middle of nowhere.  there is another array of shorts that corresponds to each vertex in the buffer.  the number is either -1 or some other value.  if its -1 then the vertex is a good vertex, if its something else than its a weird vertex.  


some of the models reference these weird vertex so i'm wondering if a polygon references a weird one (non -1) does it mean you are suppose to do something special like scan forward in the array until you find a good one and ref that instead?  or perhaps a strange vertex signifies the beginning a polygon strip and you should start hitting all the good vertex in a row until you get to another weird one, then stop? 

The model of the face refed no weird vertex so it came out good.  the model of some type of armour refed mostly good ones and a few weird ones.  the largest model in the file refed almost all weird ones so it looks like a giant mess of polygons.  I wonder if theses weird vertex are something to do with physics or some gpu trick to achieve some effect.

These are just ideas being I have not seen this before.  Trying stuff out.    Anyone else have seen something similar?
From what I am seeing in the face index section between each sub mesh index there are 4byte floating point numbers. The index begins at offset 0x263C4 with the number of submeshes a 4byteInteger, which in this case is four.
Then this is followed by 17, 4byteFloat numbers, followed by an unknown 4byteInteger, followed by 00 00 00 00 00 00 00 00 followed by the 4byteInteger for the number of faces in the submesh, followed by the index, (VertexA, VertexB, VertexC). This repeats for each submesh.
Submesh #2: 00027910
Submesh #3: 0002899C
Submesh #4: 0002A118
Plotting the floats between the submeshes would defiantly corrupt the meshes, so just ingnore them they are probably just weights defining some type of meta data.
## Post #5
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-29T01:07:32+00:00
- Post Title: Magna Carta: Phantom of Avalanche (PCport)

yeah i skip over those floats.  they are probably position, rotation, scale, etc, color info,


i think this is the vertex format more or less

position
normal
uv
boneindex1
boneindex2(if there is only 1 bone index then this is -1)
boneweight1
boneweight2

vertex with a bone index2 are huge, in the thousands, maybe they are encoded different or something, so i ignore them for now

the 2 armour meshes have parts kind of sticking into each other but i think if they were rigged to bones, you could pull apart the bones to seperate them.
I dont know how to set up rigs in maxscript yet so im working on that now.
## Post #6
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-06-29T02:41:31+00:00
- Post Title: Magna Carta: Phantom of Avalanche (PCport)

wow thank you sir surix and sir furryfan for the help, i really appreciate it
