## Post #1
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-09-10T02:21:30+00:00
- Post Title: [WIP/REQ] Battlestations Pacific .MMOD

Hello! I've tried searching this topic here, but only found one thread in the wrong section with no posts.

Anyway, I'd like to ask about the .mmod model format from the PC game Battlestations Pacific. 

Battlestations Pacific is an RTS game, where you can take direct control of an enormous variety of Japanese and American warships and airplanes. 
The game was released in 2009, and while the texture resolution isn't that high, as you can see the models are stunningly detailed. 



All game files are stored in .mpack files, which can be opened with [BSPRipper](http://battlestations.eu/index.php/en/downloads/category/9-pacific-modders-tools). 
The textures are stored in plain .dds files, but models are in this .mmod format. Lots of people have already tried to figure this out, but nobody seems to be able to. 

[A fellow by the name of richimoto made some decent progress on the official game forums](http://battlestations.eu/index.php/forum/topic?id=525&lang=en), but he left before finishing anything. 

I'll repost his work here, maybe it'll be helpful:

> Reply from richimoto
>
> simple.mvfm geometry cracked! 

In each .mmod file, you will find: 
MMOD 
--------BoundingSphere 
--------BoundingBox 
--------Resource 
--------------------Mesh 
---------------------------VertexStream 
----------------------------------------------*.mvfm 

I have not yet had any luck with BoundingSphere, so I skipped BoundingBox.  VertexStream is pretty straightforward but I cracked the geometry format for simple.mvfm! 

right after simple.mvfm in the file begins a list of FLOATs.  in the case of simple.mvfm, they are in a sequence of x,y,z,n1,n2,n3,u,v. This sequence represents one vertex.  x=position left to right, y=position down to up, z= position front to back. n1,n2,n3 combined represent a vector, the direction light reflects from the vertex, u=the vertex' position on the texture map from left to right, v=the vertex' position on the texture map from top to bottom.  the next float is x of the next vertex. 

after the vertex stream is the index. 
---------------------------Indices 

The index is a list of how the vertices are put together to make polygons. in this example, directx is calling it a "ushort"-the u for unsigned and short as 0x XX XX... (also WORD) 00 00=0, 00 01=1 etc...  for example, the index contains: 0,1,2,3,4,0,5,6,3,7...  this means that vertices 0,1,2 make a polygon.  verts 3,4,0 make a polygon.  Notice that these two polygons share vertex0. 

I have attached two images showing the relevant research data for vertices and indices: 

VertexStream: 
http://battlestations.eu/components/com ... tream.jpeg 

Indices: 
http://battlestations.eu/components/com ... dices.jpeg
Since posting links in public is apparently against the rules now, PM me for file samples.
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2014-09-11T01:50:48+00:00
- Post Title: [WIP/REQ] Battlestations Pacific .MMOD

i had a look, the geometry data is easy.. but the way they structured the file is very poor.

its a stacking format where they define a string, then you must appropriately load the correct structure. If not, then you cannot skip to a known structure.

and soo they define a structure called RESOURCE, but then theres audio, animation etc mixed together with geometry data. which they also modulate between different geometry types..

its not something I'm use to, and I can't think of an easy way to eat through the file. so i'm going to have to pass on this one :\

also for the vertex data I was looking at, it wasn't float data, it was integers. the bounding box is required to properly rescale the object
## Post #3
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-09-11T02:55:44+00:00
- Post Title: [WIP/REQ] Battlestations Pacific .MMOD

Oh. No wonder the guy before couldn't figure it out too.

Well, thanks for trying at least.
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-09-25T04:03:54+00:00
- Post Title: [WIP/REQ] Battlestations Pacific .MMOD

I took the initiative and poked about in the files using Shakotay's Hex2obj, but always ended up with a garbled mess.

Maybe I didn't look through the tutorial enough or the other guy's stuff I posted is a misleading reference. Either way, I have a feeling I'm missing something. 
To make things worse 3D rippers don't work, it's either this or nothing. 

Is there really nobody that can help with this? I don't really care about animation or bounding boxes or all that stuff necessary to repack the file, I just need the mesh and UVs.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-26T06:29:41+00:00
- Post Title: [WIP/REQ] Battlestations Pacific .MMOD

sounds like a format where you can waste much time on  

If you sent me a small sample like a box, a book, a plank or something like that I could give it a try.
But don't expect too much.

edit: the sample you sent me gives a regular structure but is weird. Will have to think about it...
Other than sky_003.mmod the vertex data is not float as mariokart64n stated.



deptchargebomb.JPG (72.01 KiB) Viewed 79 times



Maybe it's a problem of vertex sorting.
(I used big endian for a better result but for PC games it should be little endian.)

The x coordinate toggles between 0x7FFF and 0x8001 so that's not very likely to be a coordinate, is it?
(That's the reason having a flat model using little endian.)
## Post #6
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-04T00:43:22+00:00
- Post Title: [WIP/REQ] Battlestations Pacific .MMOD

Thanks for the tip. I tried it again using the references you posted but still wasn't able to get anything meaningful. 
I think I'm just not getting it. I'll guess have to read the tutorials some more until I actually know what I'm doing.

Sorry about the delayed response, but with university in full swing and Sleeping Dogs Definitive Edition right around the corner, I'll probably have to put this on the backburner for a while.
