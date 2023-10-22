## Post #1
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-11-05T00:00:30+00:00
- Post Title: MaxScript Bone Help

So I've been ripping some 3D models from some of my favorite games, just for fun, and I found this weird problem that I hope someone can help me with.
Basically I have the whole format figured out: Vertex data + bone matrices + skin info (bones indices + weights). However, I can only import meshes:

In most cases, bones are 4*4 matrices (plus parent index) that I don't know how to import using maxscript.
I've read the documentation but creating a bone involves [its position + length + z axis](http://docs.autodesk.com/3DSMAX/15/ENU/MAXScript-Help/index.html?url=files/GUID-6BD7F514-04E9-45E9-A10D-D63E837074C6.htm,topicNumber=d30e193082) and I don't really know how to get that information out of the bone matrix.

So I hope anyone can point me in the right direction, or show me an example script that can help me. I've checked some other script but haven't found any that actually imports a bone from it's 4*4 matrix. If you need and example, just let me know 

Thanks in advance:

~Sky
## Post #2
- Username: shakotay2
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-05T00:06:21+00:00
- Post Title: MaxScript Bone Help

example

fseek f bone90Start#seek_set
BoneCount = ((MeshTableStart - bone90Start) / 0x90)
struct Bone_Table_Data
(
	BoneName,BoneParentID,BoneID
)

BNArr = #()
for i = 1 to BoneCount Do (
BoneParentID = readlong f
BoneParentID = BoneParentID + 1
m11 = readfloat f; m12 = readfloat f; m13 = readfloat f
m21 = readfloat f; m22 = readfloat f; m23 = readfloat f
m31 = readfloat f; m32 = readfloat f; m33 = readfloat f
m41 = readfloat f; m42 = readfloat f; m43 = readfloat f
tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
tfm = inverse tfm
m11 = readfloat f; m12 = readfloat f; m13 = readfloat f
m21 = readfloat f; m22 = readfloat f; m23 = readfloat f
m31 = readfloat f; m32 = readfloat f; m33 = readfloat f
m41 = readfloat f; m42 = readfloat f; m43 = readfloat f
tfm2 = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
bnamesize = readbyte f#unsigned
BoneName = readstring f	

	newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name   = BoneName
			newBone.width  = 0.3
			newBone.height = 0.3
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.setBoneEnable false 0
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()

append BNArr newBone
 if (BoneParentID != 0) then
 newBone.parent = BNArr[BoneParentID]
)

if you have questions let me know
## Post #3
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-11-05T00:15:14+00:00
- Post Title: MaxScript Bone Help

Thanks chrrox, I'm gonna try it right away and report back!
In the meantime, dumb question, why does your script have two matrices? I guess the second one is not really necessary since it's not used anyway..^^"

...

EDIT: I'm sorry, but I'm still getting mixed results. The overall shape of the skeleton looks right, but hierarchy looks kinda messed up. In this specific example file, the root index is already 0 (and oddly enough, it seems there are more than just one root?), but I don't see what's the problem:

Model File:

[http://www.mediafire.com/download/98xb6 ... enaPSP.dat](http://www.mediafire.com/download/98xb6r3wd08f8yz/PasadenaPSP.dat)

This is a quick script I made to read the mesh (I invert Y/Z so the model stands up in MAX, Note that it is a very small model):

```

fname = getOpenFileName \ 
caption:"3D Model" \
types:"3D Model (*.*)|*.*" \
historyCategory:"3D Model"
f = fopen fname "rb"

fn readMesh f vertexOffset vertexNum =
(
	Vertices = #()
	Normals = #()
	TexCoords = #()
	Faces = #()
	
	fseek f vertexOffset #seek_set

	for i = 1 to vertexNum do
	(
		w1 = readbyte f
		w2 = readbyte f
		w3 = readbyte f
		w4 = readbyte f
		w5 = readbyte f
		w6 = readbyte f
		w7 = readbyte f
		w8 = readbyte f

		u = (((readshort f #unsigned) as float) / 0x8000)
		v = (((readshort f #unsigned) as float) / 0x8000) * (-1)
		
		texcoord = point3 u v 0
		--print texcoord
		TexCoords[i] = texcoord
		
		nx = ((readbyte f) as float) / 0x80
		nz = ((readbyte f) as float) / 0x80
		ny = ((readbyte f) as float) / 0x80
		nw = ((readbyte f) as float) / 0x80
		
		normal = point3 nx ny nz
		
		Normals[i] = normal
		
		x = readfloat f
		z = readfloat f
		y = readfloat f
		
		vertex = point3 x y z
		Vertices[i] = vertex	
	)

	for i = 1 to (vertexNum - 2) by 1 do
		(
			x = i
			if(mod i 2 == 0) then
				(
				y = i + 1
				z = i + 2
			)
			else
			(
				y = i + 2
				z = i + 1
			)				
			face = point3 x y z
			append Faces face
		)

	msh = mesh vertices:Vertices faces:Faces tverts:TexCoords
		
	mmesh = msh.mesh
	buildTVFaces mmesh
	for i = 1 to mmesh.numfaces do
		(setTVFace mmesh i (getFace mmesh i)
	)
)

readMesh f 0x330a 0x5e2
readMesh f 0xd964 0x162
readMesh f 0x101be 0xb1
readMesh f 0x116bc 0x89
readMesh f 0x1275a 0xb7
readMesh f 0x13d00 0x139

fclose f
```


And this is the code I'm using to import the skeleton (so far with mixed results :/)

```

struct Bone_Table_Data
(
	BoneName,BoneParentID,BoneID
)

fn readFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str0 = ReadByte bstream #unsigned
		if str0==0x0A do str+="\r\n"
		if str0!=0xFD AND str0!=0xFC do str+= bit.intAsChar str0
	)
	str
)

fname = getOpenFileName \ 
caption:"3D Model" \
types:"3D Model (*.*)|*.*" \
historyCategory:"3D Model"
f = fopen fname "rb"

boneStart = 0x266a
BoneCount = 0x1f

fseek f boneStart #seek_set

BNArr = #()
for i = 1 to BoneCount Do (
	
	boneSize0 = readlong f
	boneSize1 = readlong f
	nameSize = readbyte f
	
	boneName = readFixedString f nameSize
	
	print boneName
	
	BoneParentID = readlong f
	print BoneParentID
	BoneParentID = BoneParentID
	
	m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; ignore = readfloat f
	m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; ignore = readfloat f
	m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; ignore = readfloat f
	m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; ignore = readfloat f
	
	tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
	tfm = inverse tfm
	
	ignore = readfloat f
	
	tfm2 = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]

	newBone = bonesys.createbone	\
	tfm.row4	\
	(tfm.row4 + 0.01 * (normalize tfm.row1)) \
	(normalize tfm.row3)
	newBone.name = BoneName
	newBone.width = 0.1
	newBone.height = 0.1
	newBone.wirecolor = yellow
	newbone.showlinks = true
	newBone.setBoneEnable false 0
	newBone.pos.controller = TCB_position ()
	newBone.rotation.controller = TCB_rotation ()

	append BNArr newBone
	if (BoneParentID != 0) then
		newBone.parent = BNArr[BoneParentID]
)
```


Thank you very much again:

~Sky
## Post #4
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-11-07T11:05:07+00:00
- Post Title: MaxScript Bone Help

OK double post to say that I found the solution to my problem:

Basically the bones were parent relative, and I assumed 3DSMax would make them parent-relative by default, by simply specifying the correct hierarchy; but since this is not the case, one must of course multiply the matrix of each bone, by it's parent matrix:

```
newBone.transform = newBone.transform * (newBone.parent.transform)
```


That gives the correct result, this thread can now be closed ^_^".

~Sky
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-07T12:20:42+00:00
- Post Title: MaxScript Bone Help

Thx for sharing!  

But I'm a max script noob - where to insert the .transform line?

I put it here:

```
      newBone.parent = BNArr[BoneParentID]
	  newBone.transform = newBone.transform * (newBone.parent.transform)
   )
```
and this is the result:
[](http://www.pic-upload.de/view-21259500/SkyBC.jpg.html)
## Post #6
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-11-07T12:47:43+00:00
- Post Title: MaxScript Bone Help

Well, the hierarchy is different here so...

newBone.parent = BNArr[BoneParentID + 1]

Should do it right. Also, don't invert the bone matrices 

...
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-07T13:17:47+00:00
- Post Title: MaxScript Bone Help

thx again!
[](http://www.pic-upload.de/view-21259887/SkyBC_skel.jpg.html)

This thread should be helpful to many "skeleton beginners" in this forum.
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-01T13:55:35+00:00
- Post Title: MaxScript Bone Help

Hi guys! 
I would like to ask about help with maxscript bones import too. I wrote simple script to import models from Black Desert online.
I know there's nice model import script by Chrrox [viewtopic.php?f=16&t=10909](http://forum.xentax.com/viewtopic.php?f=16&t=10909) with fully working models, but I want to handle this game by myself with maxscript for educational porpuses. So, the problem is, that each bone has a 4 byte long hash-id at the beggining, and game uses those hash values to identify which bones should be used for actual model (bone file contains all bones for any case, and a lot of them are just unused for actual model). Those hash values represented in the very begining of model file along with count for bones which are used. So, my issues is - how to pick those used-bones only for my models, not just all of them from bone file. Get them by those hashes, any help will be highly appreciated. Here's my script

```
caption:"Open .pab from Bones folder" \
types:"BD_ONLINE (*.pab)|*.pab" \
historyCategory:"BDObjectPresets"
g = fopen gname "rb"
fname = getOpenFileName \
caption:"Open .pac from Mesh folder" \
types:"BD_ONLINE (*.pac)|*.pac" \
historyCategory:"BDObjectPresets"
f = fopen fname "rb"

fn readHalfFloat fstream = (
    hf=readshort fstream #unsigned
    sign = bit.get hf 16
    exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
    fraction = bit.and hf (bit.hexasint "03FF")
    if sign==true then sign = 1 else sign = 0
    exponentF = exponent + 127
    outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
    (bit.shift exponentF 23)) (bit.shift sign 31)
    return bit.intasfloat outputasfloat*2
    )

fn ReadFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)	

struct weight_data
(
   boneids,weights
)
clearlistener()

BNArr = #()
BoneIdArray = #()
fseek g 0x10 #seek_set
BoneCount = readshort g
print BoneCount

for a = 1 to BoneCount do (
boneIDs = readlong g #unsigned	
BoneNameSize = readbyte g
BoneName= ReadFixedString g BoneNameSize
getPos = ftell g + 302
BoneParent = readlong g
float11 = readfloat g; float12 = readfloat g; float13 = readfloat g; float14 = readfloat g 
float21 = readfloat g; float22 = readfloat g; float23 = readfloat g; float24 = readfloat g 
float31 = readfloat g; float32 = readfloat g; float33 = readfloat g; float34 = readfloat g
float41 = readfloat g; float42 = readfloat g; float43 = readfloat g; float44 = readfloat g
fseek g getPos #seek_set
tfm = (quat float11 float12 float13 float14) as matrix3
tfm.row4 = [float41,float43,float42]
	
if (getNodeByName BoneName) != undefined do (
append BNArr (getNodeByName BoneName)
)
if (getNodeByName BoneName) == undefined do (

 newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = BoneName
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = white
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (BoneParent != -1) then
 newBone.parent = BNArr[(BoneParent + 1)]					  
append BNArr newBone 
append BoneIdArray boneIds				  
)			
)
fclose g	

fseek f 0x10 #seek_set
usedbones = readbyte f
bidArray = #()
for c = 1 to usedbones do (
bid = readlong f #unsigned
append bidArray bid
)
print bidArray 

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
fseek f 0x9 #seek_cur
meshcount = readshort f
for x = 1 to meshcount do(
		
size= readbyte f
meshname=  ReadFixedString f size
meshLOD = readshort f #unsigned 
print meshname
vertexcount=readshort f #unsigned 

format "vertex: %\nvertices count: %\n" vertexcount	vertexcount
	
Vert_array=#()
Face_array=#()
UV_array=#()	
Weight_array =#()	
	
for x = 1 to vertexcount do(
vx=readfloat f
vy=readfloat f
vz=readfloat f
p1=readshort f
p2=readshort f		
p3=readHalfFloat f
p4=readHalfFloat f*-1
ff=readlong f
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
weight1 = readbyte f#unsigned
weight2 = readbyte f#unsigned
weight3 = readbyte f#unsigned
weight4 = readbyte f#unsigned		

w = (weight_data boneids:#() weights:#())
maxweight = 0
if(weight1 != 0) then
   maxweight = maxweight + weight1
if(weight2 != 0) then
   maxweight = maxweight + weight2
if(weight3 != 0) then
   maxweight = maxweight + weight3
if(weight4 != 0) then
   maxweight = maxweight + weight4

if(maxweight != 0) then (
      if(weight1 != 0) then (
         w1 = weight1 as float
         append w.boneids (bone1 + 1)
         append w.weights (w1 / 255.0)
      )
      if(weight2 != 0) then (
         w2 = weight2 as float
         append w.boneids (bone2 + 1)
         append w.weights (w2 / 255.0)
      )
      if(weight3 != 0) then (
         w3 = weight3 as float
         append w.boneids (bone3 + 1)
         append w.weights (w3 / 255.0)
      )
      if(weight4 != 0) then (
         w4 = weight4 as float
         append w.boneids (bone4 + 1)
         append w.weights (w4 / 255.0)
      )      
   )
append Weight_array w	
append Vert_array[vx,vz,vy] 
append UV_array[p3,p4,0]
)

facecount=readlong f	
for x = 1 to facecount/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append Face_array[fc,fb,fa]
)

vertex2=readshort f -- skip LODs
for x = 1 to vertex2 do(
v1=readfloat f
v2=readfloat f
v3=readfloat f
p1=readshort f
p2=readshort f	
p3=readHalfFloat f
p4=readHalfFloat f
p5=readshort f	
p6=readshort f	
p=readfloat f
p=readfloat f
)
face2=readlong f		
for x = 1 to face2/3 do(
sa=readshort f #unsigned+1
sb=readshort f #unsigned+1
sc=readshort f #unsigned+1
)

fseek f 0x6 #seek_cur

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
msh.name=meshname
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

max modify mode
select msh
skinMod = skin ()
addModifier msh skinMod
for i = 1 to bidArray.count do
(
	maxbone = BNArr[i]
	if i != bidArray.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod
for i = 1 to vertexcount do
(
	w = Weight_array[i]
	bi = #()
	wv = #()
	for j = 1 to w.boneids.count do
	(
		boneid = w.boneids[j]
		weight = w.weights[j]
		append bi boneid
		append wv weight
	)	
   skinOps.ReplaceVertexWeights skinMod i bi wv
)

)

fclose f
```


And sample with model+bones attached
[BD_SAMPLE.7z](https://xentaxbackup.github.io/file/6815_BD_SAMPLE.7z)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-01T17:15:05+00:00
- Post Title: MaxScript Bone Help

> Reply from zaramot
>
> [...]Those hash values represented in the very begining of model file along with count for bones which are used.So 0D 91 FA CC (or vice versa) is the hash for "Bip01 Spine"?
Where/what is the count?

> So, my issues is - how to pick those used-bones only for my models, not just all of them from bone file. Get them by those hashes, any help will be highly appreciated.There are 193 bones/phy_anchors in the model you uploaded, right?
All have a parent boneID so when removing some maybe you'll have to build up the parenting relationship again.

Not 193 all are required for the model? Speaking of the "phy_cloth" as helpers?

Maybe I did not get the point. Could you be more specific?
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-01T20:12:41+00:00
- Post Title: MaxScript Bone Help

Hello Shakotay!

> Reply from shakotay2
>
> So 0D 91 FA CC (or vice versa) is the hash for "Bip01 Spine"?
Where/what is the count?
Yes, you're righ 0D 91 FA CC is the hash for "Bip01 Spine". Like 8E 28 3A A2 is has for "Bip01 Head".
As for "count", count it's a number of bones which use actual model (for example model in the sample use 66 bones), to get this "count" you should go to offset 0x10 of model file and read byte, in this cave it's "42 (66 bones)" Then after count goes 66 - four bytes hashes, of bones which model should load from skeleton file.

> Reply from shakotay2
>
>  There are 193 bones/phy_anchors in the model you uploaded, right?
All have a parent boneID so when removing some maybe you'll have to build up the parenting relationship again.

Not 193 all are required for the model? Speaking of the "phy_cloth" as helpers?

Maybe I did not get the point. Could you be more specific?

Actually 192 bones  Yes, not all 192 required for the model. To say more specific for skin modifier/weighting. I've got right weights with my script, but they referenced to wrong bones, because I don't know how to pick right ones by those "hashes" not first  66 ones, as I did by using this line "maxbone = BNArr"  with this I just added first 66 bones to skin modifier, and that's not right
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-01T21:00:09+00:00
- Post Title: MaxScript Bone Help

Hi zaramot,
if I do a search for 48 7A 62 38 (the last hash in the list) I find 
"Bip01 R Elbow" in the pab file.

The boneID of this bone is 125 (when exporting the model as SMD in Noesis).
Maybe your boneIDs are different?
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-03T19:13:11+00:00
- Post Title: MaxScript Bone Help

> Reply from shakotay2
>
> Hi zaramot,
if I do a search for 48 7A 62 38 (the last hash in the list) I find 
"Bip01 R Elbow" in the pab file.

The boneID of this bone is 125 (when exporting the model as SMD in Noesis).
Maybe your boneIDs are different?

Yes, the boneID of this bone is 125. That's the main problem I guess, because if you look at bone indices inside model sample which I provided, you will notice that biggest bone id value there is 65 (for 3ds max it's 66, since we added +1 for each bone). So, when I'm importing this model with my unfinished script, for me it's bone phy_cloth_cape_21 (if I remember right) instead of bone Bip01 R Elbow. I need to pick bones by those hashes somehow.
