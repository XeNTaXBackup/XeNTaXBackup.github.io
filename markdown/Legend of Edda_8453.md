## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T04:34:41+00:00
- Post Title: Legend of Edda

Archive: [viewtopic.php?f=10&t=8451](http://forum.xentax.com/viewtopic.php?f=10&t=8451)
Sample: [http://www.mediafire.com/download.php?y26cbm46atfxs89](http://www.mediafire.com/download.php?y26cbm46atfxs89)

Mod files are the meshes.
Chx is like configuration for model + anim.

Not too sure about the structure of the format.
You have your materials at the top (which is texName followed by material info).

Then you hit some meshes. Or at least, it looks like meshes.
And then you have your numBones with bones.

Sometimes you don't even hit that mesh section and just move on with the bones.

After the bones you get a large mesh, with vertBuffer + idxBuffer, followed by bones and weights.

I don't know what the structs after the materials are.

You might actually have to read an integer to determine what the following data is...but not sure.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-02T05:56:39+00:00
- Post Title: Legend of Edda

Here's what I've done so far:

[http://db.tt/eEpJ8G36](http://db.tt/eEpJ8G36)



Don't know how the faces work yet.

lol after staring at it for awhile and trying to work out the structs, it turns out it's chunk-based.
That's why you can have meshes all over the place. I'll just write up something verbose cause I didn't make a reference for this.

```

loop {
   dword chunk tag
   dword chunk size
   byte[size] chunk data
}

```


0x 00 F0 00 00 is material
0x F5 00 00 00 is bone
0x F4 00 00 00 is mesh

Material is straightforward. Just a bunch of padded strings and a couple ints and floats.

Mesh is kind of annoying, since there are so many counts and a lot of different structs.

You read your mesh name with 128 bytes, and then you read in 2 integers.
If those 2 integers are equal, then those are the numVerts and numUV.

Otherwise, if they are not equal, read another two as the numVerts and numUV o.O

Then you have another 7 integers:
unk1, unk2, unk3, -1, numFaceGroups, unk4, -1

It starts with the positions buffer with numVerts*12
Followed by the uv buffer with numUV * 8
After that you get 3 floats that just look out of place.
You then get a unk1 integers.

Now you have your facegroups. A single mesh may have multiple face groups, each with their own index buffer.

After face groups, you will run into another 3 integers.

If the first integer is non-zero, then you have that many 5-byte structs.
If the second integer is non-zero, then you have that many 44-byte structs.
Don't know about third integer.

And then finally you read your normal buffer.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-02T14:07:02+00:00
- Post Title: Legend of Edda

great stuff so far. Looking forward seing you brink out more cuteness to that cloud of vertices
## Post #4
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2013-03-02T16:12:07+00:00
- Post Title: Legend of Edda

me too,

thank you sir finale00 for your continous effort
