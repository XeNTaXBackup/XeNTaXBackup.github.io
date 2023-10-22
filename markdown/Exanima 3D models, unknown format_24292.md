## Post #1
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-28T08:19:14+00:00
- Post Title: Exanima 3D models, unknown format

Hello everyone, this is my first post. I've lurked this website for a while but I think i hit a roadblock with my current project.
I want to make a full set of extraction tools for this game, a hard task since this is an engine made from the ground up with OpenGL.

First I used the existing bms to open the .rpk archives, and it still works perfectly after years of game updates.
You can find it here: [http://aluigi.altervista.org/bms/exanima.bms](http://aluigi.altervista.org/bms/exanima.bms)
This left me with various files, the first issue being that there are no extensions to be found inside the archive, but its usually pretty clear.

Textures were confusing at first, but i realized that they are simple DDS, the header data was simply misplaced. I made a quick script to rebuild it to the correct codecs.

I also took a quick look at the other assets, but I'm not that interested right now as my current focus is on 3D models.

So after studying a bit the 3D model files, I started to work on a blender script to import them. For this thread i will use the model in the attachment called "hammer01", with no exension I'm aware of.

The file starts quite simple. You can see that there is a string that represents the name of the asset. The array of bytes that i selected is where the vertices start, while the hex number 29 is the 41 (42) vertices that make up the mesh.

I already managed to import the vertices into blender with no issue, they are a simple list of floats that contain the XYZ coordinates.

After the lists of vertex i encountered another block, its possible that this is the UV maps, but how the floats are structured seems strange to me and couldn't make much sense of it. However you can still see the number that identifies how long the list is going to be.


I skipped some of the data, as it seems like its just material references I'm not interested in.

What seems to be what identifies the triangles is what truly confuses me, as it starts quite normal, but the numbers go much higher than the max vertex index, and ends with repeated numbers. Even if i just select the data that could create some triangles I cant fill the whole mesh and some triangles look misplaced. I tried different configurations and nothing makes sense to me.


Do you know how the triangles could be configured? Can anything be done? Thank you very much in advance.
[hammer01.zip](https://xentaxbackup.github.io/file/20528_hammer01.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-28T13:09:12+00:00
- Post Title: Exanima 3D models, unknown format

Like vertices the uvs seem to make sense:
.



hammer01.png (4.3 KiB) Viewed 185 times


(We'd need the texture to maybe tell more.)
## Post #3
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-28T13:28:01+00:00
- Post Title: Exanima 3D models, unknown format

Hi, this is the diffuse textures.
It seems like it's lazily mapped over generic textures, but this is one of the oldest models in the game. Maybe i can upload another model.
mtliron04

wodod02
## Post #4
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-29T10:33:45+00:00
- Post Title: Exanima 3D models, unknown format

I upload another model. The texture here is much better.
Yes the UVs arent hard to read, but i have no idea how where they are related to the vertices, and i still dont understand how to read the faces.
It's almost like the vertices aren't indexed at all since the number goes much higher than the vertex count.
Help would be greatly appreciated.
[2haxe a.zip](https://xentaxbackup.github.io/file/20531_2haxe a.zip)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-29T11:22:52+00:00
- Post Title: Exanima 3D models, unknown format

well, doesn't look too bad:
.



2h_axe.png (58.18 KiB) Viewed 162 times


Guess you need to use a lesser face index count (15?) for the first sub mesh, then find the start of the next face indices block for the mesh. (For the uvs it's different, max FI is 116 there. )

edit: nope, it's indexed vertices (or to say, there's an additional FIs' block (indices fInd) which is used to create "new" FIs such like FIs[fInd], where FIs is an array of face indices for the vertices for example). Yeah, noobish explanation, but worked for me.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-29T12:00:16+00:00
- Post Title: Exanima 3D models, unknown format

Maybe for uvs are indexed are something like that?
Point cloud looks ok:
.



2h_axe_tex.png (132.6 KiB) Viewed 150 times
## Post #7
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-29T12:07:22+00:00
- Post Title: Exanima 3D models, unknown format

Thank you, but how do i know which vertex the UV point is supposed to be?
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-29T13:02:30+00:00
- Post Title: Exanima 3D models, unknown format

Using AXE:



2haxe a.png (133.97 KiB) Viewed 145 times
## Post #9
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-29T13:05:30+00:00
- Post Title: Exanima 3D models, unknown format

Wow, thank you very much dude. That looks perfect. I just need a moment to understand all of that data!
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-29T13:16:09+00:00
- Post Title: Exanima 3D models, unknown format

With texture applied:



tex_applied.png (120.35 KiB) Viewed 139 times



Edit: darn! I've just realized that I was using AXE to actually extract an axe! What a coincidence!
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-29T21:01:15+00:00
- Post Title: Exanima 3D models, unknown format

> Reply from shakotay2 ↑Thu Jul 29, 2021 8:00 pm at Thu Jul 29, 2021 8:00 pm
>
> Maybe for uvs are indexed are something like that?Yep, newbie, and the vertices, too.  

Well, indexed indices. "Data Reorganizer" of AXE is a good idea but too complex for me (and hex2obj - guess I will create/hold all the data in its memory. But no idea how to keep this simple for pos AND uv indexing.)
.



2h_axe_indexed.png (13.16 KiB) Viewed 106 times
## Post #12
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-29T21:21:55+00:00
- Post Title: Exanima 3D models, unknown format

Yeah, looked impossible at first but the indexing makes sense to me now. It assigns the uv maps to each actual 3d vertex, and the triangles are created on the uvs and geometry at the same time.
Im currently making my own blender importer. Later i will try more complicated models, but should be easy now that I've figured it out.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-30T00:57:18+00:00
- Post Title: Exanima 3D models, unknown format

> Reply from shakotay2 ↑Fri Jul 30, 2021 5:01 am at Fri Jul 30, 2021 5:01 am
>
> guess I will create/hold all the data in its memory. But no idea how to keep this simple for pos AND uv indexing.
The overall layout of the geo data is as following:

```
byte       positions[(maxPositionIdx+1)*12]
long       maxUvIdx
byte       uvs[(maxUvIdx+1)*8]
long       maxVertexIdx
word       posIndices[maxVertexIdx+1]
word       uvIndices[maxVertexIdx+1]
word       posIndices_instance2[maxVertexIdx+1]

long       maxFaceIdx
word       faceIndices[(maxFaceIdx+1)*3]

```


When you have position and texture coordinates optimized they definitely require individual channels of face indices so if you're writing the coordinate data directly to an obj file, you just need to create the direct position/uv indices respectively. The formula would be

```
directUvIdx[i] = uvIndices[ faceIndices[i] ]

```


Or you just recreate the position and uv buffer to use the face indices directly:

```
directUvCoord[i] = uvs[ uvIndices[i] ]

```
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-30T07:29:29+00:00
- Post Title: Exanima 3D models, unknown format

> Reply from Bigchillghost ↑Fri Jul 30, 2021 8:57 am at Fri Jul 30, 2021 8:57 am
>
> 
The formula would be
Code: Select alldirectPosIdx[i] = posIndices[ faceIndices[i] ]
...yeah, that's what I used in my last posted picture.

> Or you just recreate the position and uv buffer to use the face indices directly:
>
> Code: Select alldirectPosCoord[i] = positions[ posIndices[i] ]
>
> directUvCoord[i] = uvs[ uvIndices[i] ]That's what you do when creating xxx.out by the "Data Reorganizer", right?
(I'd prefer maintaining the original order of vertices to not lose my overview, ... if any.)

btw: very impressive, your AXE tool.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-30T10:46:51+00:00
- Post Title: Exanima 3D models, unknown format

> Reply from shakotay2 ↑Fri Jul 30, 2021 3:29 pm at Fri Jul 30, 2021 3:29 pm
>
> 
yeah, that's what I used in my last posted picture.
So what's it about keeping things simple? 

> Reply from shakotay2 ↑Fri Jul 30, 2021 3:29 pm at Fri Jul 30, 2021 3:29 pm
>
> 
That's what you do when creating xxx.out by the "Data Reorganizer", right?
(I'd prefer maintaining the original order of vertices to not lose my overview, ... if any.)
Yes. It's just that it'd be a complete disaster to introduce
individual indices channels for all vertex attributes, not just for the GUI. Instead, an additional "data reorganizer" will serve well in maintaining the simple and old-fashioned workflow. Besides, it can also be be applied in scenarios like converting a paletted image to ordinary RGBA format.

> Reply from shakotay2 ↑Fri Jul 30, 2021 3:29 pm at Fri Jul 30, 2021 3:29 pm
>
> 
btw: very impressive, your AXE tool.
Thanks. That's cool.
## Post #16
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-30T13:32:19+00:00
- Post Title: Re: Exanima 3D models, unknown format

I wonder what this data between the UV indices and the triangles is supposed to be? I cant find the length so I can skip it over with my script.

Oh and I upload a rigged model if you wanna take a look at it. Texture is kind kind of weird because its supposed to have a procedural material.
[fplt a armor.zip](https://xentaxbackup.github.io/file/20550_fplt a armor.zip)
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-30T14:00:40+00:00
- Post Title: Re: Exanima 3D models, unknown format

> Reply from Corus ↑Fri Jul 30, 2021 9:32 pm at Fri Jul 30, 2021 9:32 pm
>
> 
I wonder what this data between the UV indices and the triangles is supposed to be? I cant find the length so I can skip it over with my script.
Read here:

> Reply from Bigchillghost ↑Fri Jul 30, 2021 8:57 am at Fri Jul 30, 2021 8:57 am
>
> 
The overall layout of the geo data is as following:
Code: Select allbyte       positions[(maxPositionIdx+1)*12]
...
word       posIndices[maxVertexIdx+1]
word       uvIndices[maxVertexIdx+1]
word       posIndices_instance2[maxVertexIdx+1]
...
word       faceIndices[(maxFaceIdx+1)*3]
It's the same as the "posIndices", but you should check other files to make sure of that.
## Post #18
- Username: Corus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 28, 2021 3:20 pm
- Post datetime: 2021-07-30T16:02:33+00:00
- Post Title: Re: Exanima 3D models, unknown format

Progress:

I really like the armor in this game
