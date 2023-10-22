## Post #1
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-26T13:16:38+00:00
- Post Title: Reposition Noesis Mesh

Is there any way to re-position a Noesis Mesh after creating it, on the models I have 6 half-floats that I think represent the positioning of that model, or do I have to change each of the position values on the model?

Thank you in advance for any help

Edit: Think its this:
{"rpgSetPosScaleBias", RPGSetPosScaleBias, METH_VARARGS, "sets geometry scale and bias - pass None, None to disable. (O)"}, //args=NoeVec3 (scale), NoeVec3 (bias) - or None, None
at least its repositioning the models. What does bias mean? xD
## Post #2
- Username: fierce
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-11-28T22:09:44+00:00
- Post Title: Reposition Noesis Mesh

Position scale and bias will scale and bias each vertex position, there's one for UV's too. You can use that if you just want to offset. You can also apply a full transform matrix using rapi.rpgSetTransform. However, scale/bias and transforms only take effect before calls to CommitTriangles/immVertex.

If you want to reposition a mesh after you've generated it from the RPG interface, you'll have to transform the vertices yourself. Which isn't all that difficult, you can just run through the list transforming with a NoeMat43. But I would recommend using the built-in RPG transform functionality, it's faster than running through lists in Python.
## Post #3
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-29T08:09:39+00:00
- Post Title: Reposition Noesis Mesh

Thank you for the help
## Post #4
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-01T14:07:58+00:00
- Post Title: Reposition Noesis Mesh

I could use some help here repositioning the meshes. I got 14 floats related to each mesh.
6 floats are before the file. Samples:
-1157.259 -3446.758 -1539.372 :: 1157.259 3446.758 1539.372
-1695.031 -3353.958 -953.4059 :: 1695.031 3353.959 953.406
-703.8727 -1029.683 -325.7906 :: 703.8727 1029.685 325.7906
-2395.909 -3875.31 -553.4999 :: 2395.909 3875.309 553.4999
And 8 floats inside the file. Samples:
-132.0858 569.5042 -96.5169  4267.608 :: -132.0858 569.5042 -96.5169 4267.608 
-285.3021 637.0676 -231.5025 4153.701 :: -285.3021 637.0676 -231.5025 4153.701
-13.20699 124.4372 -85.20573 1279.005 :: -13.20699 124.4372 -85.20573 1279.005 
109.8093 107.231 435.2258 4481.151 :: 109.8093 107.231 435.2258 4481.151 

The 8 floats (that repeat themselves) represent the median point of each mesh, but I have no idea what the last value is, it might also be 2 half-floats:
5.519531 311.25
5.503906 -22.4375
4.621094 -533.
5.546875 0.000159

I've tried repositioning those meshes using those values but got no success positioning them correctly.

Does someone have any idea what the 6 floats before the file represent and why are they both positive and negative?
Could someone also give me some positioning methods that are usually used?
Something tells me that the positioning on this meshes might be related to some vertex (first or last maybe) and not the median points.

Thank you in advance for any help
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-12-01T15:34:11+00:00
- Post Title: Reposition Noesis Mesh

> Reply from fierce
>
> I could use some help here repositioning the meshes. I got 14 floats related to each mesh.
6 floats are before the file. Samples:
-1157.259 -3446.758 -1539.372 :: 1157.259 3446.758 1539.372
-1695.031 -3353.958 -953.4059 :: 1695.031 3353.959 953.406
-703.8727 -1029.683 -325.7906 :: 703.8727 1029.685 325.7906
-2395.909 -3875.31 -553.4999 :: 2395.909 3875.309 553.4999

Does someone have any idea what the 6 floats before the file represent and why are they both positive and negative?Should be 4 bounding boxes. Two vectors defining one box.

"when it is required to find intersections in the set of objects, the initial check is the intersections between their bounding boxes"
## Post #6
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-01T16:06:30+00:00
- Post Title: Reposition Noesis Mesh

Thank you for the help shakotay2.

I checked the values and it actually makes sense that those are boundary boxes.
So I guess on those values I have:
Boundary boxes and Median points
what about the value after the median points?
Could those be positioning values?
The 2 half-floats could make sense, but that would only make X and Y values, and in those 4 meshes there seems to be one that repositions on X, Y and Z.
Or maybe I don't have any positioning values. Any ideas?

Thank you
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-12-01T16:19:06+00:00
- Post Title: Reposition Noesis Mesh

what game is it?
## Post #8
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-01T16:22:07+00:00
- Post Title: Reposition Noesis Mesh

Naruto Shippuden: Ultimate Ninja Storm (CyberConnect2)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-12-01T17:26:15+00:00
- Post Title: Reposition Noesis Mesh

> Reply from fierce
>
> Or maybe I don't have any positioning values. Any ideas?
Do you find a similar structure in your files like this one?

```
    0.000000 1.000000 0.000000 0.000000
    0.896406 0.000000 -0.443235 0.000000

    5890.063477 1600.000000 -93515.218750 1.000000
```

It's the rotation matrix and x,y,z of a crate in a Piranha Bytes game.
Changing 5890.06 changes the x-position of the crate in the world.
## Post #10
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-01T18:57:51+00:00
- Post Title: Reposition Noesis Mesh

Besides the data I posted on this topic the only data I have is some extra half-floats on the vertex data but I think that's just UV2 data, doesn't seem to make sense that values like 0.1242065, 0.2097168, 0.6489258,.. are positioning values. I've been going through some other files of that game that appear to have data that could be the positioning of the objects/meshes, but It would take some time to be able to assign that data to the corresponding meshes, nevertheless I think I'm going to try that 

On a side note, my script already extracts the meshes and textures from all the files of the game, I still haven't assigned the textures because some of the meshes have textures from different files and I wanted to assign them automatically.
## Post #11
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-02T11:03:07+00:00
- Post Title: Reposition Noesis Mesh

Are there any games that position the meshes according to the last vertex of the previous mesh? For example on a house.
This might be a possibility here, of some kind, I tried positioning the first mesh median point on the last vertex of the second mesh and it appear perfectly positioned on X and Y, not Z though. I'm going to try on different meshes and different vertex now. But would be great if someone could give me a hint if some games do position them like that.

Thank you in advance
## Post #12
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-12-03T10:54:22+00:00
- Post Title: Reposition Noesis Mesh

Ok I've found the positions, they are after the models and before the materials, it was a simple one if I just looked at the file header:
.nuccChunkNull
.nuccChunkModel
.nuccChunkClump
.nuccChunkMaterial
.nuccChunkCoord
.nuccChunkTexture
.nuccChunkPage
.nuccChunkIndex.

The only weird think is that I have 4 meshes and 5 coordinates:

Mesh1 positions:
1360.588
-19589.84
1036.864

Mesh2 positions:
1632.67
-18746.47
1531.496

Mesh3 positions:
-400.391
-20737.43
308.4857

???:
991.3789
-18947.13
627.3003

Mesh4 positions:
997.4419
-19314.31
53.50012
