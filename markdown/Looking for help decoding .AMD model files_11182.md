## Post #1
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-02T09:25:31+00:00
- Post Title: Looking for help decoding .AMD model files

I've been trying my hand at ripping models (and hopefully animations as well) from an old Atlus game on GCN called Go! Go! Hypergrind. I've had some experience hacking games and deciphering file formats in the past, and I've made some progress already: I can figure out the file offsets in the main .amd model files, for the most part, and I've written up a little Python program that can read verts, or what look very much like verts - I'll admit I'm not 100% sure I'm looking at the right data.

I've been using sunglass.amd as a test bed for my format-reading capabilities, and while I get something that does look like sunglasses by reading the (big-endian) floats that start at the offset given at 0x30 (unsigned int, big-endian), the outline I'm getting doesn't quite match the model I've seen in screenshots. Reading the other sets of vertices (offset at 0x34) usually gives me these odd geometric patterns, like spheres or ring shapes: I was assuming they were something like collision shapes, or perhaps normals, but given what I thought were verts aren't quite matching up, I have to reexamine my assumptions. Even more confusing, the data starting from the offset given at 0x2C appears to be face data, but the vertex indices go up to 0x1E when my first set of vertices has only 0x10, and even if I use only the indices that are under 0x10 to construct triangles, I get random junk. However, the second set of vertices has 0x1F, and using them to make triangles gives me nice geometric shapes - not at all the ones I'm expecting, but it certainly suggests these are the real model verts...somehow.

At any rate, my own research into the subject of GCN 3D models has run into a dead end: all the documentation I've been able to find on the subject is either incomplete or irrelevant. I'm hoping someone with more experience and sharper eyes for this kind of stuff could outline what I'm getting wrong and put me back on the right track. I've attached a sample .zip containing some files: two simple meshes, the aforementioned sunglass.amd and castanets.amd, and some additional files which go with them. I know .tpl is a texture format (and some of my successful Google delving suggests they're S3TC-encoded - hopefully I can find some more information on the format), but I'm not sure what to do with the .ld or .skn files. I'm assuming .skn is "skin"; perhaps UV data of some kind? But I don't know what to make of .ld apart from the "LNK" magic ID at the start - and the main model has one that's over 2 megabytes in size, so I have a feeling it's important. I'm not looking for hand-holding or people to do the hard work for me; I've had experience with this kind of stuff before (though never in relation to 3D files, I'll admit) and I can write my own tools, but I just don't have the experience or the context to solve this puzzle on my own.

I just hope I've done a good enough job explaining what I've worked out so far that I don't sound like some newbie crying for help. ^_^;

EDIT: It might also help if someone could point me to info on any documented GCN model/animation formats. They might not be compatible, but they'd give me a point of reference to work from.
[ggh-sample.zip](https://xentaxbackup.github.io/file/6990_ggh-sample.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-02T10:16:03+00:00
- Post Title: Looking for help decoding .AMD model files

sunglasses.amd: could be submeshes with 16 and 31 vertices. 
47 vertices (big endian) from offset 0x60 (at offset 0x30: 00 00 00 60 )

at 0x24: 00 10 00 1F
16+31= 47
## Post #3
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-02T18:56:19+00:00
- Post Title: Looking for help decoding .AMD model files

Submeshes! Okay, that's a good start. I'll admit I wasn't sure what those were until I looked them up just now - still not sure I completely understand (they're for rendering materials, right?), but it'd explain why the first block of verts is shaped like the model but doesn't quite look like it.

Here's a screenshot of the tool I've put together:



Three different views of the same set of verts. Not bad for a first try at a 3D viewer. The problem is, it should look more like this:



I can see where this particular model might fit into only 0x10 verts, but note that the shape of the lenses doesn't match, among other things.

This is what the second set of verts looks like:



Which looks more like a ring than anything.

There's also a third set of floats, but I'm not sure what they are - UV coordinates, maybe? All I know is, the address is at 0x3C, and they look like this when I read them as verts:



So I've got some not-quite sunglasses, a ring, and a...blob. I hope someone here can make more sense of this than I can. ^_^; (Is there any chance I'm reading the floats wrong, somehow?)
## Post #4
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-03T12:07:58+00:00
- Post Title: Looking for help decoding .AMD model files

Okay, another update. I did some testing the old-fashioned way - editing the file in a hex editor, inserting it into the ISO, running the game, seeing what changed. And from the looks of things, the first chunk of verts is the actual model mesh. I've also figured out an explanation for some - though not yet all - the shape discrepancies: the reason the bottom corner is truncated is because the texture there is transparent.

I still can't figure out how the faces are put together, though, and I have no idea what the other sets of verts are for - I tried blanking out the second one, but I haven't noticed anything different yet. Blanking the third made the model vanish as if I'd deleted the mesh vertices; I need to double-check, but I suspect it might be UV coordinates.

EDIT: Third block of verts seems to have something to do with texture mapping - not sure they're UV coordinates (there's only 8 vertices' worth total), mind. Still not sure about the faces, though. The data starting from the address at 0x2C is definitely face data, but I'm still having trouble figuring out how exactly they define faces...

EDIT #2: And I've also figured out the remaining shape discrepancies. I wasn't quite grasping the shape the verts made properly - it matches exactly.
## Post #5
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-05T00:37:45+00:00
- Post Title: Looking for help decoding .AMD model files

Aaaaand...success. :3



Figured out how the triangle strips were stored. Each one's prefixed by 0x98 followed by the number of vertices. Each vertex is actually four bytes' worth of data - the actual mesh vertex, followed by the UV coordinate and submesh (in some order; I haven't worked out all the details yet).

Next step is to work out texture unpacking. :3

EDIT: Okay, I'm having a devil of a time here working this out: does anyone have any documentation on the Gamecube's S3TC texture format? Again, my Google-fu is failing me...
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-02-05T21:53:26+00:00
- Post Title: Looking for help decoding .AMD model files

> Reply from Ryusui
>
> Submeshes! Okay, that's a good start. I'll admit I wasn't sure what those were until I looked them up just now - still not sure I completely understand (they're for rendering materials, right?), but it'd explain why the first block of verts is shaped like the model but doesn't quite look like it.

Some 3D formats allow only one material per surface, so if they wanted to have, say, a skin texture and then a clothing texture for a single model, they'd have to break it down into separate surfaces.

By grouping all of those faces into a "sub mesh" they would avoid having to store a material index for each face since it would be implied.

Even if they assign two meshes with the same material, they probably did it for other reasons like maybe it's just easier to maintain as separate meshes.
## Post #7
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-05T23:35:17+00:00
- Post Title: Looking for help decoding .AMD model files

And it turns out I was overthinking things - the Gamecube's texture format is just vanilla DXT1. :3

So now I'm at a point where I can dump a model and have it look good. I had some weird problems with .OBJ format (missing verts and faces), which is probably for the best - I didn't realize OBJ didn't support bones and animations. XD On the upside, I discovered there's a Python library for working with COLLADA files, though I haven't yet rewritten my tools to make use of it.

EDIT: Okay, to be clear, these are my findings.

First batch of floats is verts.
Second is normals.
Third is UV coordinates.

Then we have the faces, which are prefixed by 0x0098 followed by the number of verts in the face, and then the actual vert data - four two-byte big-endian sequences consisting of the vertex index, the normal index, something I haven't figured out yet, and the UV index. A mesh can consist of multiple submeshes, which will be indicated in the header.
## Post #8
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-16T09:36:10+00:00
- Post Title: Looking for help decoding .AMD model files

Well, it's been a week and a half since I last posted about my progress, and thanks to this and other resources, I'm at a point where I can import textured, rigged AMD models directly into Blender. But I'm still having a little trouble.



As you can see here, I've got bones and meshes importing and displaying properly in Blender. But there seems to be something wrong with how the vertices are getting assigned to bones.



It seems at first glance like the vertex groups are off by one, but a little tweak to "fix" that gives me this:



I'm fairly certain I've worked out the skin file properly; I suspect there's something about the actual process of assigning verts to bones that's escaped me. Has anyone seen issues like this before, and if so, what do I need to do to fix them?
## Post #9
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-20T06:32:20+00:00
- Post Title: Looking for help decoding .AMD model files

...it's insane. The bones are all backwards.

I...think I've got rigging working properly now. It's ugly, but it's serviceable. The animation data is all that remains. (Also got shape keys working. Good times.)
## Post #10
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2014-02-23T07:15:32+00:00
- Post Title: Looking for help decoding .AMD model files

If you have a set of vertexes, a set of UV coordinates and a set of unknown data, its quite likely that the unknown data could be vertex normals.
## Post #11
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-02-24T18:57:56+00:00
- Post Title: Looking for help decoding .AMD model files

I already figured out the meshes. What I'm having trouble with now is the rigging.

Okay, going back to the screenshots above: as it turns out, the "tails" of the bones are actually where each vertex group is supposed to rotate. Right now I've got things set up where the bones are flipped: the heads are being placed where I'd been putting the tails, and vice versa. It's not a pretty solution by a long shot - setting "use_connect" to True means that the tails will join up with the child bones, no matter where I specifically place them - but it's working. I just want to know if there's a more elegant solution, one that I'm missing due to my lack of experience with Blender and its API.

The other - last, really - issue I'm having is importing the animations. I have, against all odds, worked out the animation data format, but I'm having trouble finding decent documentation and tutorials for how to implement armature animations in Blender. For one thing, the rotations are stored as quaternions, which are apparently pretty obscure. Anyone got any good tutorials or examples they can share?
