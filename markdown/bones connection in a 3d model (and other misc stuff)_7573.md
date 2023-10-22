## Post #1
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-26T18:11:28+00:00
- Post Title: bones connection in a 3d model (and other misc stuff)

I really would like to do reverse engineering on 3D models, sadly I have no idea about some needed basics.
Answering any question (or linking to associated ressources that don't need extensive OpenGL knowledge  ) are greatly appretiated

Stuff I understand:
A 3d point consists of x,y,z (int or float)
a model consists of those points that are connected, resulting in faces, those need normals and u,v (texture coords)
(sometimes materials are used instead of a texture)

after having said model there are bones (normally in a hiearchical order)

when a model has bones it maybe has an animation

Questions:
1) How are faces defined? does every 3D point get a number and a face is just a reference to 3 numbers that form a triangle? (or 4 for a quad)
2) How are normals calculated? (why are they normally 1 or -1?), are they normally booleans?
3) How are u,v coordinates defined? per triangle or per point? How do they translate to the actual texture?
3.1) How is does vertex painting work?/Is it even used somewhere
3.2) Are materials instead of textures in modern games common (XBox360,PS3,PSP,Wii)?
3.3) Is looking into DXT2 and 4 worth the trouble aka are they used anywhere?
4) How are bones defined? do they get x,y,z *2 and an atractor field? which information is needed? (again in int/float/etc)
4.1) How are bones connected? (Bonenames?)
5) Which information is needed to move the bones? (float vector?) How is an animation timeline defined? (int for each frame?)
5.1) Is per-vertex-animation common?
