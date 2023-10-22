## Post #1
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-05-18T10:42:20+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

Hey,

for the last days I finally extracted the archive-files from Unreal Engine 1 (Splinter Cell 1). Now I'm able to look on every single Meshfile. For example this:


But I'm not getting that format. You can clearly see the data in this pattern: Floats, Indices, Floats (maybe VBO, Faces, UV's). But I'm unable to find any information to Vertex-Count or Index-Count.

Maybe someone see's something, I can't see.

I've attached two files: Normal meshfile and collision file (as I think it is). Thank you very much in forefield!

pivke

EDIT: Get demo here: [http://www.fileplanet.com/118136/110000 ... l-Demo-[PC](http://www.fileplanet.com/118136/110000/fileinfo/Tom-Clancy%27s-Splinter-Cell-Demo-%5BPC)] (Url won't work)
[Vitrine.rar](https://xentaxbackup.github.io/file/7346_Vitrine.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-18T16:12:16+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

> Reply from pivke
>
> But I'm unable to find any information to Vertex-Count or Index-Count.Me, too. For some formats they aren't contained in the model file. Using hex2obj (view link in my sig) you only need to calculate/estimate the face indices count - the resulting vertex count is shown in the lower left list box then (hidden by the model atm):



Vitrine.JPG (37.82 KiB) Viewed 145 times

Vitrine_CIA.mesh, UV pos might be 24.
There's another vector block 42 * x,y,z at 0x100E building a square point cloud.
(The 214 face indices starting at 0xC34 (max face index=88) won't fit here.)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-18T17:20:08+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

in Vitrine_CIA.mesh
The vertex count is
58 01
the 58 is the vertex count
then the first face count
02 00 00 00 7E 01
is 7E
## Post #4
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-05-18T18:56:59+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

Hey,

thanks to you guys! Awesome with that results you are coming with.   

@chrrox
My first question: How did you notice that? I've sawn a pattern of floats, too, but I didn't get to find the start of that float-block.

But; Are you sure these values are the counts? I mean, when I'm looking at them, it seems legit, but the block of floats is much larger than the vertexcount. Even if you multiplicate 0x5801 with 3 or 4. What do you think about that?
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-18T21:48:43+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

the vertex size is 0x20
just look at the size.
so multiply that value * 0x20
## Post #6
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-05-19T15:44:31+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

Hey,

thanks for your answer! I'm a bit confused for now. 

So, 1) What do you mean by vertex size and 2) Where do you see 0x20?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-19T17:36:21+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

0x20 is hex for 32 bytes.
vertex size is also called vertex stride.
its the length each vertex point takes up.
Example for 32 byte stride
12 bytes vertex position
12 bytes normal
8 bytes uv's
total would be 32
12 + 12 = 24
24 + 8 is 32
32 is 0x20 in hex
## Post #8
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-06T16:46:05+00:00
- Post Title: Splinter Cell 1 - Meshfile extracted :)

Ok, so after some time: (In reference to CIA_Vitrine.msh)
-There is always a 42 byte-header.
-After that 42 byte-header starts the VertexCount (short, 2 byte)
-After that VertexCount, there follows the VBO (vertex-stride seems not to be 0x20, because on different files, the VBO would be too long or too short)
-When skipping a few byte after VBO, there comes FaceCount and FaceIndices (At FaceIndices same as above)

So again, someone able to crack this weird stuff? "chroxx" just made a great start. 

Thanks so far!  

(If you guys need another file just say it   )
