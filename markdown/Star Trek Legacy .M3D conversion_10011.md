## Post #1
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-01-05T22:36:10+00:00
- Post Title: Star Trek Legacy .M3D conversion

I've been looking into the Star Trek Legacy .M3D files in an attempt to get the geometry out of them.

The vertices are stored as 32bit little endian floats, and the face indexes look like they're stored as little endian shorts.  Before the vertex block starts there are 3 counts and a possible type flag.  The first count is the amount of vertices, and for now I haven't figured out what the second and third counts mean, (possibly uv data, and something else).  After the 2 unknown blocks I just mentioned, the face indexes start.  There is a count that seems to coincide with the size of the face indexes block, and then another block containing some odd values after the face indexes that follow this pattern.

0, 1, 1
1, 2, 2
2, 3, 3
3, 4, 4
4, 5, 5
etc...

Here is a good visual representation of the block structure.


The vertex data in green can be represented as spheres using maxscript.  So at least I can see the shape of the object the data represents.
Here are some examples of what I've exported so far. (The spherical shape in the top example is the light blue section of bytes represented as spheres, me thinks uv data)



I've been looking through the file to try to find pointers, but it seems this file may use a tree structure and some other way of specifying the data.
The pointers aren't my problem for now.  

Its the faces indexes that are giving me trouble.

I begin to get good data for the face indexes, but about 30 to 50 faces into a mesh, they begin to really go out of whack.
In the following pic at offset 317502, the face index says 0xC403 (965 in decimal).  The model only has 499 vertices.


So I change it to a vertex that is more suitable for the triangle's location in the mesh. (In this case 34 works)


I can then get through a few more bad indexes like this until all of a sudden the index data doesn't seem to match the vertex data anymore.  The problem is, I've barely even started mapping faces to the verts using the mentioned face data.


If you keep adding more faces from this index data it just gets worse.



Has anyone seen this kind of face indexing before?  It may be face index data sectioned out for a certain reason, I just haven't been able to put my finger on it yet.
## Post #2
- Username: EcheloCross
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-06T01:59:50+00:00
- Post Title: Star Trek Legacy .M3D conversion

they look like normal triangle lists.
i think you are just starting at the wrong offset.
after the name right before the face data you need to skip 2 bytes.
then you read 6 bytes * the count they gave you.
then they give another count as a long.
and you read 6 bytes * that count.
this part seems kind of pointless mabee its vertex information like an order? i don't think its really needed.
## Post #3
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-01-06T02:31:11+00:00
- Post Title: Star Trek Legacy .M3D conversion

Thanks for responding chrrox. I do skip 2 bytes past the string default, and begin to read faces 6 bytes at a time.  I think the face count is just above the string default right before the mesh name as a short.  If I use the entire block based on that count though, it generates way too many faces.  And some of them are oddball face values like 965 when it should be less than the vertex count.

I don't see an accurate face count, nor the long you're talking about.  What file are you looking at, or are you looking at the pics I provided?  

Thanks for your help.
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-01-06T11:14:04+00:00
- Post Title: Star Trek Legacy .M3D conversion

this format is really annoying >_<

the header is pretty useless, it gives the file magic "Mad3D_SW" followed by the version number "2.05" and a object count

After which you can expect to parse hundreds of nodes. but these nudes are defined in an odd way, I'm not sure how to accurately parse them.

the struct for the nodes is pretty simple, but from what I can tell it only gives name, matrix, hierarchy info, and possibly a size?
{
SHORT char_length
STRING string
LONG unk
SHORT unk
LONG unk
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
FLOAT32 matrix3*4
LONG unk
LONG unk
}

following all the nodes you'll reach the vertex buffer.
a quick way to reach this buffer is to search for this string of 6 bytes "0x100000000000" and skip node parsing

this will bring you to a vertex buffer header, the struct is here;
vertex_header {
SHORT num_verts
SHORT num_norms
SHORT num_tverts
SHORT facetype?
}

three sets of vertex data are present in the buffer data following. and loop according to each count specified previous

position_data {
FLOAT32 x_position
FLOAT32 y_position
FLOAT32 z_position
}

normal_data {
FLOAT32 x_normal
FLOAT32 y_normal
FLOAT32 z_normal
}

texture_data {
FLOAT32 u_coordinate
FLOAT32 v_coordinate
}



now you'll reach the face buffer

face_header {
SHORT num_faces
SHORT char_length
STRING string
SHORT char_length
STRING string
BYTE[22] whitespace, possibly variable // skip until no 0's
SHORT char_length
STRING string
LONG index
SHORT char_length
STRING string
SHORT unk
SHORT unk
}



OK!

so here's where it gets weird, I don't understand it 

clearly since we receive three sets of variably sized vertex data {Position,Normal,Texture} it must mean we will see three sets of face data
But as you read through as triangle list the indices you read will get beyond the number of vertices you collected previous
The next assumption is that instead of them defining each face set one after the other, they have defined all three in the same set.

example:
{Single-Trilist}
{face = [SHORT(a1),SHORT(a2),SHORT(a3)]} 

{Combined-Trilist}
{face = [SHORT(a1),SHORT(a2),SHORT(a3),SHORT(b1),SHORT(b2),SHORT(b3),SHORT(c1),SHORT(c2),SHORT(c3)]} 

where;
a=position indices
b=normal indices
c=uvw indices
1=face index 1
2=face index 2
3=face index 3

!!However it still wont work the indices will still exceed the vertex totals of all three vertex sets O_O!! WTF!?

I found if you skip the beginning of the face buffer you'll get to that convention [f=(a1,a2,a3,b1,b2,b3,c1,c2,c3)]

Anyway here's my max script if it helps


```

fsource = GetOpenFileName \
caption:"Select m3d File" \
types: "m3d(*.m3d)|*.m3d|All files (*.*)|*.*|"

if (fsource!=undefined) then (
fpath=getFilenamePath fsource
fname=getFilenameFile fsource
fsize=getFileSize fsource
if ((doesFileExist fsource)==true) then (
f = fopen fsource "rb"

obj = $*;delete obj

buildMsh = true

fn readFixedString bstream fixedLen = (
local str = ""
for i = 1 to fixedLen do (
str += bit.intAsChar (ReadByte bstream #unsigned))
str
)

fn jumpwhitespace fstream = (
byte = readbyte fstream #unsigned
while byte == 0 do (byte = readbyte fstream #unsigned)
fseek fstream -1 #seek_cur
)

fileMagic = readFIxedString f 8
if fileMagic == "Mad3D_SW" then (
ukn001 = readshort f #unsigned -- magic?? always 0x0000
ukn002 = readfloat f -- Scale? or version?
obj_count = readshort f #unsigned

if ukn002 == (2.05) then (
for i = 1 to obj_count do (
mat_name = readFixedString f (readshort f #unsigned)
ukn003 = readfloat f
ukn004 = readfloat f
ukn007 = readfloat f
ukn008 = readfloat f
ukn009 = readfloat f
ukn010 = readfloat f
ukn011 = readfloat f
ukn012 = readfloat f
ukn013 = readfloat f
ukn014 = readfloat f
ukn015 = readshort f #unsigned -- type 0x01=Node? | 0x02=Material?
ukn016 = readshort f #unsigned -- flag?
ukn017 = readlong f #unsigned  -- ?? What the!?
format "mat %: % | % | % | % | %\n" i ukn003 ukn004 ukn015 ukn016 ukn017
)

chrlimit = 64
mshmagic = 16

nodeName = ""
do (
ukn035 = readshort f #unsigned

if ukn035 == 0 do (
while ukn035 == 0 do (
ukn035 = readbyte f #unsigned
)
fseek f -1 #seek_cur
ukn035 = readshort f #unsigned
)

if ukn035>=chrlimit do (
ukn035 = readshort f #unsigned
)

if ukn035 == mshmagic do (
check4str = readlong f #unsigned
if check4str == 0 do (
ukn035 = 0
)
)

nodeName = readFixedString f ukn035


subName = ""
if nodeName[nodeName.count] == ";" do (
subName = readFixedString f (readshort f #unsigned)
)

if nodeName!="" do (
print nodeName
ukn020 = readlong f #unsigned
ukn021 = readshort f #unsigned
ukn022 = readlong f #unsigned
ukn023 = readfloat f
ukn024 = readfloat f
ukn025 = readfloat f
ukn026 = readfloat f
ukn027 = readfloat f
ukn028= readfloat f
ukn029 = readfloat f
ukn030 = readfloat f
ukn031 = readfloat f
ukn032 = readfloat f
ukn033 = readfloat f
ukn034 = readfloat f
format "mat: % Counts: % | % | % | % | %\n\n" i ukn020 ukn021 ukn022 ukn035 subName
)
) while nodeName!=""


if buildMsh == true do (

vertArray=#()
normArray=#()
uvwArray1=#()
faceArray=#()

num_verts = readshort f #unsigned
num_norms = readshort f #unsigned
num_tverts = readshort f #unsigned
facetype = readshort f #unsigned


format "Counts\n\t%\n\t%\n\t%\n" num_verts num_norms num_tverts

for i = 1 to num_verts do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append vertArray [vx,vy,vz]
)

for i = 1 to num_norms do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append normArray [nx,ny,nz]
)

for i = 1 to num_tverts do (
tu = readfloat f
tv = readfloat f
append uvwArray1 [tv,tu,0]
)


num_faces = readshort f #unsigned
mshName = readFixedString f (readshort f #unsigned)
matName = readFixedString f (readshort f #unsigned)
jumpwhitespace f -- ?? whitespace
subMatName = readFixedString f (readshort f #unsigned)
subMatIndex = readlong f #unsigned + 1
texName = readFixedString f (readshort f #unsigned)
ukn061 = readshort f #unsigned
ukn062 = readshort f #unsigned

faceaddon = 1

for i = 1 to num_faces do ( -- What the!? faces are out of range!!
fa = readshort f #unsigned + faceaddon
fb = readshort f #unsigned + faceaddon
fc = readshort f #unsigned + faceaddon
)

ukn063 = readlong f #unsigned

num_faces = 10


for i = 1 to num_faces do (
fa_msh = readshort f #unsigned + faceaddon
fa_nrm = readshort f #unsigned + faceaddon
fa_uvw = readshort f #unsigned + faceaddon
fb_msh = readshort f #unsigned + faceaddon
fb_nrm = readshort f #unsigned + faceaddon
fb_uvw = readshort f #unsigned + faceaddon
fc_msh = readshort f #unsigned + faceaddon
fc_nrm = readshort f #unsigned + faceaddon
fc_uvw = readshort f #unsigned + faceaddon
-- append faceArray [fa_msh,fb_msh,fc_msh]
)

print faceArray

msh = mesh vertices:vertArray faces:faceArray --materialIDs:matidArray
msh.numTVerts = uvwArray1.count
buildTVFaces msh
select msh
)

)else(messagebox ("File Skipped!\n\nVersion "+(ukn002 as string)+" Not Supported\n"))
)else(print "invalid Mad3D_SW Header")
fclose f
) else (Print "Failed to Load File")) else (Print "Aborted.")

```


PS, you should probably remove your email, I did that once and got spammed by bots.
## Post #5
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-06T13:09:46+00:00
- Post Title: Star Trek Legacy .M3D conversion

seems normal to me i just skip the 2nd 2 face buffers and it seems to load fine.

attached is the script i coded up very quickly.
[fmt_swl_m3d_beta001.zip](https://xentaxbackup.github.io/file/6117_fmt_swl_m3d_beta001.zip)
## Post #6
- Username: EcheloCross
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-06T19:15:22+00:00
- Post Title: Star Trek Legacy .M3D conversion

I found the problem with this format and why you had issues.
mario sent me the files you sent him and i looked at the 360 files.
The meshes have different counts for verts, normals, uv's
The key to making them line up is the buffer after the faces.
this contains 6 bytes and is = to the highest face index listed.
so all you have to do is constuct 3 new buffers using those as indexing into the original buffers you read from the game.
then the faces will load fine.
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-01-06T22:46:34+00:00
- Post Title: Star Trek Legacy .M3D conversion

Echelo was asking how this worked, so I scripted this up and it works. I'll leave this snippet as an example

```
fa = readshort f #unsigned + faceaddon
fb = readshort f #unsigned + faceaddon
fc = readshort f #unsigned + faceaddon
append indexArray [fa,fb,fc]
)
for i = 1 to num_faces do (
fmsh = readshort f #unsigned + faceaddon
fnrm = readshort f #unsigned + faceaddon
uvw = readshort f #unsigned + faceaddon
append temptArray [msh,nrm,uvw]
)

for i = 1 to num_indices do (
fa = temptArray[(indexArray[i][1])][1]
fb = temptArray[(indexArray[i][2])][1]
fc = temptArray[(indexArray[i][3])][1]
append faceArray [fa,fc,fb]
)

```


i'm doing 3 things there
1. read the 1st face buffer
2. read the 2nd face buffer
3. rebuilt the face buffer

note num_indices is the count from the 1st buffer and num_faces is from the 2nd buffer
## Post #8
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-01-07T23:39:48+00:00
- Post Title: Star Trek Legacy .M3D conversion

Thanks for all your help chrrox and mariokart64n.  I've finally got the faces parsing correctly.  



Time to add uv and normal extraction to my tool now. 

Update..

UVs and normals are working out just fine using the same re-indexing method.
## Post #9
- Username: StatictheVixen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 30, 2012 5:24 am
- Post datetime: 2014-09-26T00:18:30+00:00
- Post Title: Star Trek Legacy .M3D conversion

When I uploaded the model on NOESIS with the chrrox's plugin, it gives me an error which says, "Traceback (most recent call last):
File
"C:\Users\Username\Documents\NOESIS\plugins\python\fmt_swl_m3d.py
", line 62, in m3dLoadModel
texName = bs.readBytes(texNameSize).decode("ASCII")
UnicodeDecodeError: 'ascii' codec can't decode byte 0xcd in position 1:
ordinal not in range(128)"

Can anybody help me with this one, please?
## Post #10
- Username: Voxed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 30, 2014 3:59 am
- Post datetime: 2014-10-29T20:52:56+00:00
- Post Title: Star Trek Legacy .M3D conversion

> Reply from StatictheVixen
>
> When I uploaded the model on NOESIS with the chrrox's plugin, it gives me an error which says, "Traceback (most recent call last):
File
"C:\Users\Username\Documents\NOESIS\plugins\python\fmt_swl_m3d.py
", line 62, in m3dLoadModel
texName = bs.readBytes(texNameSize).decode("ASCII")
UnicodeDecodeError: 'ascii' codec can't decode byte 0xcd in position 1:
ordinal not in range(128)"

Can anybody help me with this one, please?

Hi im also having the same problem. thanks!
