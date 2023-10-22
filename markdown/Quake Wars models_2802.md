## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-10-06T00:37:50+00:00
- Post Title: Quake Wars models

[out]
## Post #2
- Username: namshub
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 14, 2007 1:15 pm
- Post datetime: 2007-10-14T21:16:17+00:00
- Post Title: Quake Wars models

I've just spent several hours pulling the MD5B file apart and now have the mesh rendered in its bind pose.  The format is definately nothing like MD5Mesh or previous id binary files ( with the data in chunks, and a header with byte offsets to each chunk)  I've figured out the basic structures, but some parts seem very strange, and I was hoping maybe someone smarter then me could figure out the last bits.
Heres the basic Layout of the file:

int one			(always = 1)
int two			(always = 2, maybe refers to the number of LOD levels for each mesh)
int numJoints
Joint[numJoints] joints
int numMeshes 		(usually 3, head, body and shadow)
Mesh[numMeshes] meshes
int numLODMeshes	(usually 3 again)
Mesh[numLODMeshes] LODmeshes
byte[28] ?		(at the end of each file are 28 bytes with no pattern i can find)

Joint Structure:
int namelength
char[namelength] jointName
int parent
float[4] rot	(a unit quaternion, presumably the rotation of the joint in bind pose)
float[16] mat	(looks like a 4X4 matrix)

Mesh Structure:
int namelength
char[namelength] jointName
int 0
int 0
int ?
int numVPart1
byte[3]	( always seems to be 0,0,0  just to make life miserable)
int shaderNamelength
char[shaderNamelength] shader		(this seems to just point to a folder.  I've found textures that work, but they were dds files that had random strings of numbers for names)
int  numVPart1 (again)
int ?
int numTriangleIndex
short[numTriangleIndex] triangleIndices
int numshadowstuff			(this number always seems to be 0 unless the shader and meshname imply this mesh is only used for casting shadows)
short[numshadowstuff * 4] shadowstuff	(a list of what looks like 4 vertex indices)
byte[numVPart1 * 2] vertPart1		(16 bits per vert, the first four and last four are always 0.  I have no idea what these are)
int  numVPart1 				(for the third time =\)
int numVerts 				(this is always equal to numVPart1 + numExtendedVerts)
int numExtendedVerts			(the number of verts that don't have a VertPart1, and instead have an index to a vert it shares one with)
int[numExtendedVerts] sVertIndices	(the above mentioned indices)
int numVerts				(for good measure?)
int 0
int numBones				(the number of joints used for this mesh)
byte[numBones] bone 			(index of joints used in this mesh)
Vertex[numTVerts] vertices
VertPart2[numTVerts] vertPart2
byte[5] jibberish				(5 bytes at the end of each mesh with no pattern i can find)

Vertex Structure:
float[3] pos
float[2] texture coordinates
float[3] normal
float[3] tangent				(a unit vector orthagonal to the normal, used for bump mapping)
float ?					always -1 or 1
int ?					(always -1)

VertPart2 Structure:	(definately the most absurd looking part of the format)
byte[8] ???		(bytes 1,3,5 and 7 are always multiples of 3)
			(bytes 1,5 and 7 are always equal to eachother)
			(bytes 6 and 8 are always 0)
			(byte 2 is always equal to (byte 3) * -1 - 1)

Rendering the first 2 meshes using the triangle indices and vertex data will give you the model in bindpos, the 3rd mesh is a lower LOD of the entire model used for casting shadows it seems.  I would guess that each vertex should have bone indices and weights, but I can't imagine how the remaining parts can represent that.
## Post #3
- Username: namshub
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 14, 2007 1:15 pm
- Post datetime: 2007-10-14T21:28:01+00:00
- Post Title: Quake Wars models

I couldn't figure out what the extra numbers in the header were either, but here's what the next bit of the file looks like:

short[numFrames * 6] (positive and negative integers usually < 100)
int numJoints
Joints[numJoints]
int numJoints (seems to be lots of redundancy in these files)

Joint Structure:
int nameLength
char[nameLength] name
short parent
short ?
short ?

the rest looks like a random sea of 1's and 0's to me
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-10-15T22:51:20+00:00
- Post Title: Quake Wars models

[out]
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-10-15T23:15:06+00:00
- Post Title: Quake Wars models

[out]
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-10-15T23:48:53+00:00
- Post Title: Quake Wars models

[out]
## Post #7
- Username: SlippytheWeasel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 23, 2007 4:32 pm
- Post datetime: 2007-10-26T05:57:32+00:00
- Post Title: Quake Wars models

What is a good program for viewing the model files for ET:QW?

I'm trying to self-teach myself how to do mapping/modelling/etc, and I thought this looked like a good website to get some information.

I'm interested in trying to create a few new death animations once the SDK comes out.


Thanks.


Slippy
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-10-26T21:41:59+00:00
- Post Title: Quake Wars models

[out]
## Post #9
- Username: SlippytheWeasel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 23, 2007 4:32 pm
- Post datetime: 2007-11-03T06:50:12+00:00
- Post Title: Quake Wars models

Well, they should be releasing the SDK soon, maybe that'll be what I need.

Thanks.


Slippy
## Post #10
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-11-03T23:07:19+00:00
- Post Title: Quake Wars models

[out]
## Post #11
- Username: SlippytheWeasel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 23, 2007 4:32 pm
- Post datetime: 2007-11-04T09:37:51+00:00
- Post Title: Quake Wars models

Well, jRad (Jared 'jRAD' Hefty, Splash Damage's Tools and User Interface Programmer) said on 29 Oct 07:

"We plan to launch the ETQW Editing Wiki alongside the full Software Developers Kit, Tools, Media, Tutorials, and Documentation after the ETQW 1.2 update is released. Keep an eye on the developer blog for the latest on this."

1.2 was released this week, so the SDK should be following.

[http://community.enemyterritory.com/ind ... q=node/189](http://community.enemyterritory.com/index.php?q=node/189)


Slippy
## Post #12
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-11-04T20:07:23+00:00
- Post Title: Quake Wars models

[out]
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-12-02T01:52:13+00:00
- Post Title: Quake Wars models

[out]
## Post #14
- Username: SlippytheWeasel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 23, 2007 4:32 pm
- Post datetime: 2007-12-19T05:34:30+00:00
- Post Title: Quake Wars models

> Reply from Wobble
>
> Well, they finally released the 1.2 Beta SDK, and I found the binary animation format:
Code: Select allstatic const int ANIMB_IDENT    = (('A'<<24)+('N'<<16)+('M'<<8)+'B');
static const int ANIMB_VERSION  = 1;


but I searched the entire SDK, and there is no mention of the binary model format, MD5B!

Anybody know where it is??

Might try looking on the wiki for the SDK.

[http://wiki.splashdamage.com/index.php/Main_Page](http://wiki.splashdamage.com/index.php/Main_Page)


Slippy
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-12-21T20:25:56+00:00
- Post Title: Quake Wars models

[out]
## Post #16
- Username: frustum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 27, 2007 2:06 pm
- Post datetime: 2007-12-27T08:41:34+00:00
- Post Title: 

I have successfully loaded md5b files with animation.
There are many unused and repeated records in the structures.

md5b format is:

```
int unused

int number of joints
each joint is:
  string name
  int parent
  float[8] unused
  float[4] row_0 of bind pose matrix
  float[4] row_1 of bind pose matrix
  float[4] row_2 of bind pose matrix

int number of meshes
each mesh is:
  string name
  int[3] unused
  int number of shadow vertices
  uchar vertex buffer index (0 or 1)
  uchar vertex buffer shared flag (1 means mesh without vertex)
  uchar vertex rigid flag (0 means 4 bones per vertex, 1 means 1 bone)
  string shader
  int[2] unused
  int number of triangles
  ushort[num_of_triangles * 3] array of indices
  int number of shadow indices unused
  short[num_of_shadow_indices * 4] unused
  uchar[num_of_shadow_vertices * 2] unused
  int number of vertex
  int number of extended vertices unused
  int[num_of_extended_vertices] unused
  int[2] unused
  int number of joints
  uchar[num_of_joints] joints indices
  vertex[num_of_vertex]
  each vertex is:
     float[3] coordinate
     float[2] texcoord
     float[3] normal
     float[3] tangent
     float binormal direction (cross(normal,tangnet) * binormal)
     int unused
  if rigid is 1
     uchar[num_of_vertex] each uchar is joint index * 3
  else
     uchar[num_of_vertex * 8] each pair of uchars are joint undex * 3 and joint weight
   uchar[5] unused

```


animb format is:

```
int version (1)

int number of frames
int[4] unused

int number of frames
bounds[num_of_frames]
each bound is:
  short[3] min
  short[3] max

int number of joints
joint[num_of_joints]
each joint is:
   string name
   int parent
   int flags
   int offset

int number of joints
baseframe[num_of_joints]
each baseframe is:
  short[3] rotation
  short[3] position

int number of components
short[components]

```


i don't want to describe algorithms
piece of code will be better:

components to frames:

```
for(int j = 0; j < joints.size(); j++) {
	int flags = joints[j].flags;
	if(flags & 0x01) offset++;
	if(flags & 0x02) offset++;
	if(flags & 0x04) offset++;
	if(flags & 0x08) offset++;
	if(flags & 0x10) offset++;
	if(flags & 0x20) offset++;
}

for(int i = 0; i < frames.size(); i++) {
	Vector<Frame> &frame = frames[i];
	frame.resize(joints.size());
	
	for(int j = 0; j < joints.size(); j++) {
		int parent = joints[j].parent;
		int flags = joints[j].flags;
		int index = joints[j].index + offset * i;
		vec3 xyz = joints[j].xyz;
		quat rot = joints[j].rot;
		
		if(flags & 0x01) xyz.x = components[index++] * 256.0f / 32767.0f;
		if(flags & 0x02) xyz.y = components[index++] * 256.0f / 32767.0f;
		if(flags & 0x04) xyz.z = components[index++] * 256.0f / 32767.0f;
		if(flags & 0x08) rot.x = components[index++] / 32767.0f;
		if(flags & 0x10) rot.y = components[index++] / 32767.0f;
		if(flags & 0x20) rot.z = components[index++] / 32767.0f;
	
		rot.w = -sqrtf(max(1.0f - length2(vec3(rot)),0.0f));
		
		if(parent == -1) {
			frame[j].xyz = xyz;
			frame[j].rot = rot;
		} else {
			frame[j].xyz = frame[parent].rot * xyz + frame[parent].xyz;
			frame[j].rot = normalize(frame[parent].rot * rot);
		}
	}
}

```


mesh vertex buffer:

```
if(mesh->shared) {
	for(int i = 0; i < meshes.size(); i++) {
		if(meshes[i].shared == 0 && meshes[i].index == mesh->index && meshes[i].shader == mesh->shader) {
			vertex = meshes[i].vertex.get();
			break;
		}
	}
}

```
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-12-30T00:54:41+00:00
- Post Title: 

[out]
## Post #18
- Username: frustum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 27, 2007 2:06 pm
- Post datetime: 2007-12-30T06:07:40+00:00
- Post Title: 

Character meshes has vertex buffer in each mesh.
But other meshes can share vertex buffer with others.
For example vehicles.
## Post #19
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2007-12-30T07:52:40+00:00
- Post Title: 

Fustrum,

I think I did find 2 bugs in your great description:

uchar[num_of_shadow_vertices * 2] unused
int numVPart1 (for the third time =\)
   'missed line from the namshub's doc'
int number of vertex


int number of triangles   -----> (number of triangles)/3
ushort[num_of_triangles * 3] array of indices



I uploaded the latest 3d converter package (v4.025) to my web page now (today, 8:30 am). It has two ETQW related loader modules:
   Enemy Territory: QUAKE Wars	*.MD5B
   Enemy Territory: QUAKE Wars	*.MD5MESH

[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…).
## Post #20
- Username: frustum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 27, 2007 2:06 pm
- Post datetime: 2007-12-30T08:02:35+00:00
- Post Title: 

Karpati,

yeah two misprints

```
each mesh is:
  string name
  int[3] unused
  int number of shadow vertices
  uchar vertex buffer index (0 or 1)
  uchar vertex buffer shared flag (1 means mesh without vertex)
  uchar vertex rigid flag (0 means 4 bones per vertex, 1 means 1 bone)
  string shader
  int[2] unused
  int number of indices
  ushort[num_of_indices] array of indices
  int number of shadow indices unused
  short[num_of_shadow_indices * 4] unused
  uchar[num_of_shadow_vertices * 2] unused
  int number of vertex unused
  int number of vertex
  int number of extended vertices unused
  int[num_of_extended_vertices] unused
  int[2] unused
  int number of joints
  uchar[num_of_joints] joints indices
  vertex[num_of_vertex]
  each vertex is:
     float[3] coordinate
     float[2] texcoord
     float[3] normal
     float[3] tangent
     float binormal direction (cross(normal,tangnet) * binormal)
     int unused
  if rigid is 1
     uchar[num_of_vertex] each uchar is joint index * 3
  else
     uchar[num_of_vertex * 8] each pair of uchars are joint undex * 3 and joint weight
   uchar[5] unused 

```
## Post #21
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-12-30T23:05:58+00:00
- Post Title: 

[out]
## Post #22
- Username: frustum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 27, 2007 2:06 pm
- Post datetime: 2007-12-31T06:02:47+00:00
- Post Title: 

Probably index is boolean flag because i didn't see values different from 0 and 1.

I posted code to select vertex buffer above.
I'm not sure in this code, but it works for all models from quakeWars.

```
-- | num_vertex: 1003 | index:  0 | shared:  0 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
-- | num_vertex: 1001 | index:  1 | shared:  0 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  1 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1
-- | num_vertex:  400 | index:  0 | shared:  0 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
-- | num_vertex:  387 | index:  1 | shared:  0 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  1 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  1 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  1 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  0 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  1 | shared:  1 | shader: textures/common/shadow_vehicle
   | num_vertex:    0 | index:  1 | shared:  1 | shader: textures/common/shadow_vehicle
-- | num_vertex:    8 | index:  0 | shared:  0 | shader: models/vehicles/edf_badger/brakelight
   | num_vertex:    0 | index:  0 | shared:  1 | shader: dummy/metal/shader1

```
## Post #23
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-01-01T01:32:26+00:00
- Post Title: 

[out]
## Post #24
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-01-01T04:30:02+00:00
- Post Title: 

[out]
## Post #25
- Username: frustum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 27, 2007 2:06 pm
- Post datetime: 2008-01-01T06:34:17+00:00
- Post Title: 

> Reply from Wobble
>
> 
Look at Mesh[37].  The max vertex index is 1955.  The only VB buffer that is a logical match
is found at Mesh[0] with 1956 vertices.  It can't use the VB buffer at Mesh[36], since there's
only 527 vertices there.

Append shader name into the table.

Probably bone index multiplied by 3 for direct loading bone matrices in shader (3 rows per bone).
And engine must pass some vectors into shader for rendering in additional to bones.
Direct3d9 level hardware has only 255 shader parameters.
Therefore uchar is the reasonable format for bones.
