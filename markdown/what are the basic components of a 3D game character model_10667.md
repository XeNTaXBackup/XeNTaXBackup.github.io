## Post #1
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-08-08T12:52:29+00:00
- Post Title: what are the basic components of a 3D game character model?

I have only opened .mesh files and see the voxels and normals, but I mostly only see solid objects with no bones and stuff. not really related to the kind of 3D models that game uses.

what kind of basic components do game models have? I am only interested in humanoid 3D models right now.

I know it's along the lines of voxels forming a surface triangle, but how are they connected? is it with edges? how are normal vectors usually defined for texture?

how are bones defined? how are they connected to a hollow 3D model?

I am a rather generic programmer. as you can see I have no experience in blender or 3D max, but that should be okay, I mean I got noesis right?
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-08T13:36:43+00:00
- Post Title: what are the basic components of a 3D game character model?

typical game model components:

one or more vertex buffers
one or more index buffers
one or more variables describing the input layout and semantics of the vertex buffers
one or more input assembly buffers 
a list of materials
a list of joints
a list of joint maps (that maps blend indices to joints)

for example, in dw games,
vertex buffers are in 0x00010004 subchunk of G1MG chunk
index buffers are in 0x00010007 subchunk of G1MG chunk
input layout and vertex buffer semantics are in 0x00010005 subchunk of G1MG chunk
input assembly buffer is in 0x00010008 subchunk of G1MG chunk
materials are listed in 0x00010002 subchunk of G1MG chunk
the list of joints is in the G1MS chunk
the list of joint maps are listed in the 0x00010006 subchunk of G1MG chunk

and indeed, once you have all this data, you just feed it into noesis and out poops a model .
## Post #3
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-08-08T22:02:30+00:00
- Post Title: what are the basic components of a 3D game character model?

let's say we start from 3D model perspective rather than file format perspective 

so you have a voxel, which connect to other things to form a triangle, then triangles connect together to form a hand, then a greater map identifies this hand ID and connect it to the arm.

how are these things usually defined? once I understand this basic idea, I think I will be able to see the relationship to the file format you posted.
## Post #4
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-08-09T09:11:25+00:00
- Post Title: what are the basic components of a 3D game character model?

> Reply from MuffinMan123
>
> voxel

Sorry to say this but, [Vertex](http://en.wikipedia.org/wiki/Vertex_%28computer_graphics%29) and [Voxel](http://en.wikipedia.org/wiki/Voxel) are differents.
## Post #5
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-08-10T11:21:24+00:00
- Post Title: what are the basic components of a 3D game character model?

ok, sounds like I am on the wrong track here. what basics do I need to know? what is the basic components of 3D model in general?
## Post #6
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-08-10T12:49:23+00:00
- Post Title: what are the basic components of a 3D game character model?

> Reply from MuffinMan123
>
> ok, sounds like I am on the wrong track here. what basics do I need to know? what is the basic components of 3D model in general?

I think that you need to understand the basic of "3D" before the basic of "3D game character".
It's like trying to know how a car works, without knowing what is a "car".

First, try to use some basic 3d modeling software like : 
- milkshape.
- blender. 
(I prefer milkshape because it's built mainly for games, giving you the possibility to learn the very basic of modeling without a tons of generic automated function like 3ds max. It sort of a handwork of 3d modeling.  =)  )

Then, try to make simple objects by following some tutorial until you get enough experience for modeling a game character.
And after that, you will be able to know "what are the basic components of a 3D game character model"

If you are motivate, it will take you less a month with 3 hours by day for understand the basic of 3D.


It's the only way !
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2013-08-10T14:05:21+00:00
- Post Title: what are the basic components of a 3D game character model?

[out]
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-11T05:43:48+00:00
- Post Title: what are the basic components of a 3D game character model?

What is a model? A miserable little pile of triangles!
## Post #9
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-08-28T00:08:25+00:00
- Post Title: what are the basic components of a 3D game character model?

> Reply from Wobble
>
> Just say the name of the game you're interested in.
the original ninja gaiden 2 - I know noesis can read it, but I can't see the script on the format itself, and the original ninja gaiden 2 thread only has the extractors, not the scripts which talk about the formats.
ninja gaiden 3 - I am trying to read through the thread to find any scripts so I can read it and hopefully understand how the data structure work
razor's edge - same thing

the thing I want to do is to understand what team ninja's general 3D format looks like for ninja gaiden games so I can hopefully learn from it and extract the sigma 2 characters that aren't in razor's edge.

problem is I don't know anything about 3D model format for characters in general
## Post #10
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2013-08-29T03:50:58+00:00
- Post Title: what are the basic components of a 3D game character model?

MuffinMan123

are these useful for you ?
[viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739)
[viewtopic.php?f=16&t=3674](http://forum.xentax.com/viewtopic.php?f=16&t=3674)
