## Post #1
- Username: AiramCruz™
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-22T21:59:06+00:00
- Post Title: Aika Online

This will import meshes with bones and weights.
you need the .bon and the .mesh files to be in the same directory.


```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open Aika Model File" \
types:"Aika Model File(*.msh)|*.msh" \
historyCategory:"AikaObjectPresets"
f = fopen fname "rb"
h = getFilenameFile fname
gg = substring h 1 4 + ".bon"
g2 = getFilenamePath fname + gg
g = fopen g2 "rb"
print g
total_size = getFileSize g2 / 8
boneparentidarray = #()
for a = 1 to total_size Do (
boneparentid = readlong g
realboneid = readlong g
printoffset boneparentid 
print realboneid
append boneparentidarray boneparentid
)
fn PrintOffset Var =
(
	local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
	Var
)
fn PrintCount Var =
(
	local Var = Var
print ("This is the Count 0x" + (bit.intAsHex Var) as string)
	Var
)

fn Readword fstream = (
return readshort fstream #unsigned
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

struct Mesh_Info_Struct
(
	Mesh_Name,vertstart,vertend,vertcount,facecount
)
struct Offset_Info_Struct
(
	Section_Start,Vert_Start,Face_Start,vertsize
)
unk01 = readlong f
unk02 = readlong f
unk03 = readlong f
Count01 = readlong f
VertSize = readlong f
unk06 = readlong f
BoneCount = readlong f
VertCount= readlong f
FaceCount = readlong f
 
struct Bone_Table_Data
(
	BoneName,BoneParentID,BoneID
)
BoneStart = (ftell f)
fseek f (0x40 * BoneCount) #seek_cur
Bone_ID_Array = #()
for i = 1 to BoneCount Do (
boneid = readlong f
append Bone_ID_Array boneid
)
fseek f BoneStart #seek_set
BNArr = #()
for i = 1 to BoneCount Do (

m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
tfm2 = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
tfm = inverse tfm2
if isvalidnode (getnodebyname ("Bone_" + Bone_ID_Array[i] as string)) == true then (
append BNArr (getnodebyname ("Bone_" + Bone_ID_Array[i] as string))
)
if isvalidnode (getnodebyname ("Bone_" + Bone_ID_Array[i] as string)) != true then (
	newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
     		newBone.name   = ("Bone_" + Bone_ID_Array[i] as string)
			newBone.width  = 0.03
			newBone.height = 0.03
			newBone.transform = tfm
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.setBoneEnable false 0
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
append BNArr newBone
				  )

)
for i = 1 to BoneCount Do (
select (getnodebyname ("Bone_" + (Bone_ID_Array[i]) as string))
if  boneparentidarray[Bone_ID_Array[(i)]] != 0 then
$.parent = (getnodebyname ("Bone_" + boneparentidarray[Bone_ID_Array[(i)] + 1] as string))
boneid = readlong f
	print boneid
print (getnodebyname ("Bone_" + boneparentidarray[Bone_ID_Array[(i)]] as string))
)
struct weight_data
(
	boneids,weights
)
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
for a = 1 to VertCount Do (
vx = readfloat f     --read xyz coordinates
vy = readfloat f 
vz = readfloat f
	if VertSize == 0x24 do (
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
weight1 = readfloat f
weight1 = 1.0
weight2 = 0
weight3 = 0
weight4 = 0
fseek f 0x8#seek_cur
	)
	if VertSize == 0x28 do (
weight1 = readfloat f
weight2 = 0
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
weight3 = 0
weight4 = 0
fseek f 0xC#seek_cur
	)
		if VertSize == 0x2C do (
weight1 = readfloat f
weight2 = readfloat f
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
weight3 = 0
weight4 = 0
fseek f 0xC#seek_cur
	)
tu = readfloat f
tv = readfloat f * -1
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

if(maxweight != 0) Do	
	(
		if(weight1 != 0) Do 
	(
			w1 = weight1 as float
			append w.boneids (bone1+1)
			append w.weights w1
		)
		if(weight2 != 0) Do
		(
			w2 = weight2 as float
			append w.boneids (bone2+1)
			append w.weights w2
		)
		if(weight3 != 0) Do
		(
			w3 = weight3 as float
			append w.boneids (bone3+1)
			append w.weights w3
		)
		if(weight4 != 0) Do
		(
			w4 = weight4 as float
			append w.boneids (bone4+1)
			append w.weights w4
		)		
	)		
	

append Vert_array [vx,vy,vz] --save verts to Vert_array
append UV_array [tu,tv,0]  --save UVs to UV_array
append Weight_array w
)
for i = 1 to facecount / 3 do (
f1 = (readshort f) + 1   --read face indices, games are start form 0, but Max start from 1
f2 = (readshort f) + 1   --so we add 1 to each index
f3 = (readshort f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

max modify mode
select msh
skinMod = skin ()
addModifier msh skinMod
for i = 1 to BNArr.count do
(
	maxbone = getnodebyname BNArr[i].name
	if i != BNArr.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
	
)

modPanel.setCurrentObject skinMod

for i = 1 to Weight_array.count do
(
	w = Weight_array[i]
	bi = #() --bone index array
	wv = #() --weight value array
	
	for j = 1 to w.boneids.count do
	(
		boneid = w.boneids[j]
		weight = w.weights[j]
		append bi boneid
		append wv weight
	)	
	
	skinOps.ReplaceVertexWeights skinMod i bi wv
	
)
max create mode

printoffset (ftell f)
fclose f
fclose g

```
## Post #2
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2010-11-23T02:59:11+00:00
- Post Title: Aika Online

Is it possible to import the animations?
## Post #3
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-23T05:48:37+00:00
- Post Title: Aika Online

wow chrrox
excellent
## Post #4
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-11-23T22:43:30+00:00
- Post Title: Aika Online

thank you sir chroxx
## Post #5
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2010-12-14T05:52:03+00:00
- Post Title: Aika Online

wow great
## Post #6
- Username: AiramCruz™
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 17, 2011 2:30 am
- Post datetime: 2012-08-20T22:54:38+00:00
- Post Title: Aika Online

Too bad no matter the animations pro 3DS, but still an awesome script bro.
