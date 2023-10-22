## Post #1
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-16T22:18:53+00:00
- Post Title: [Noesis] Need help analyzing these "obj" files

Hi guys,

I'm trying to figure out the structure of these model files and can't really seem to figure them out. They're similar to the .bsc files in some ways (see my other topic), and yet not similar (don't know if that makes sense? lol). Anyways, would you guys be as so kind to help me out on this?

Here's the files I've uploaded a bunch of obj files used in this game. (I've found that some are different in structure somewhat, like the wing_120.obj is different from aura_010.obj for  some reason)

[http://bout.evolutiongames.net/download ... 0files.zip](http://bout.evolutiongames.net/downloads/obj%20files.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-17T16:03:47+00:00
- Post Title: [Noesis] Need help analyzing these "obj" files

> Reply from Alsair
>
> Anyways, would you guys be as so kind to help me out on this?wing_120.obj is rather simple when starting from 0x12990 (I think you already got it ?):
verts format 3 floats, 3 floats (normals), DW (4x FF) 2 floats (tex), 2 DW

```
g submesh_1

# 1.   12990:
v  9.561472 0.569448 -17.335211
#  -0.233612 0.946877 -0.221020
# FF FF FF FF 
vt 0.982946 0.451261 
# 00 00 00 00  00 00 00 00 

v  30.158304 0.569457 -40.130482
#  -0.520701 0.348508 -0.779367
# FF FF FF FF 
vt 0.750353 0.487322 
# 00 00 00 00  00 00 00 00 

v  36.303497 -0.376772 -41.008362
#  0.547735 0.000000 -0.836652
# FF FF FF FF 
vt 0.715815 0.523658 
# 00 00 00 00  00 00 00 00 

v  16.760126 -0.376782 -11.365590
#  0.834879 0.000000 0.550433
# FF FF FF FF 
vt 0.983805 0.523860 
# 00 00 00 00  00 00 00 00 

v  9.561472 -1.323012 -17.335211
#  -0.475821 -0.762762 -0.437937
# FF FF FF FF 
vt 0.982946 0.451261 
# 00 00 00 00  00 00 00 00 

v  30.158304 -1.323004 -40.130482
#  -0.368984 -0.504536 -0.780573
# FF FF FF FF 
vt 0.750353 0.487322 
# 00 00 00 00  00 00 00 00 

v  9.561472 -1.323012 -17.335211
#  -0.475821 -0.762762 -0.437937
# FF FF FF FF 
vt 0.980823 0.437640 
# 00 00 00 00  00 00 00 00 

v  30.158304 -1.323004 -40.130482
#  -0.368984 -0.504536 -0.780573
# FF FF FF FF 
vt 0.748335 0.473690 
# 00 00 00 00  00 00 00 00 

v  30.158304 -1.323004 -40.130482
#  -0.368984 -0.504536 -0.780573
# FF FF FF FF 
vt 0.737870 0.478408 
# 00 00 00 00  00 00 00 00 

#   12b1c:

# 2.   12b1c:
f 1 3 2 
f 3 1 4 
f 5 3 4 
f 3 5 6 
f 7 2 8 
f 2 7 1 
f 9 2 3 
  12b46: 
# face index min/max: 1 / 9

g submesh_2

# 1.   12bc0:
v  2.562319 1.625291 -1.883709
#  0.369084 -0.182509 0.911300
# FF FF FF FF 
vt 0.478277 0.393565 
# 00 00 00 00  00 00 00 00 

[...]

#g submesh_27

[...]

```
## Post #3
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-17T20:33:41+00:00
- Post Title: [Noesis] Need help analyzing these "obj" files

How would I know how many verts to read for each mesh piece, and what about faces?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-17T21:01:35+00:00
- Post Title: [Noesis] Need help analyzing these "obj" files

2 bytes after CC-block: DW vertscount and DW faceindexcount (= 3 * facecount), indices unsigned int (2 bytes)
0x012950   CC CC CC CC CC CC 00 00  09 00 00 00 15 00 00 00 -> 9 vertices (9 normals, 9 tex), 7 faces
## Post #5
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-17T22:55:28+00:00
- Post Title: [Noesis] Need help analyzing these "obj" files

Looks like my task would be to figure out what the data prior to that is.

I think it may be anim data or something cause the mini_xxx have an independent animation for each one, and doesn't follow the global skeleton file, I can't confirm this 100% though.

There should be a standard used in all obj files though, like some appear quite different, but there may be a reason as to why.


Edit:

The first portion of the file is definitely the structure of the .bon files. It appears the .bon file is merged with the .bsc file and they named it .obj.
