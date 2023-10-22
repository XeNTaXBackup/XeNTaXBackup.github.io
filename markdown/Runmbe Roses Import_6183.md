## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-07T04:44:08+00:00
- Post Title: Runmbe Roses Import

I have tested this on 2011 models i will improve it more this is just a start

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"SVR2011 Model File" \
types:"SVR2011 Model File(*.yobj)|*.yobj" \
historyCategory:"SVR2011 Object Presets"
f = fopen fname "rb"

fn ReadBEShort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 2 1
b = (bit.get short 16)
for i = 17 to 32 do short = bit.set short i b
return short
) 
fn PrintOffset Var =
(
        local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
        Var
)

fn floatSwap2 f = 
(
        i = bit.floatAsInt f
        h = bit.intashex i
        while h.count < 8 do h = "0" + h
        
        s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
        bit.intAsFloat (bit.hexasint s)
)       

fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
)

        fn convertTo32 input16 = (
                inputAsInt = input16
                sign = bit.get inputAsInt 16
                exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
                fraction = bit.and inputAsInt (bit.hexasint "03FF")
                if sign==true then sign = 1 else sign = 0
                exponentF = exponent + 127
                --Ouput 32 bit integer representing a 32 bit float
                outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
                --Output Check  
                return bit.intasfloat outputasfloat
        )

fn ReadBEHalfFloat fstream = (
return convertTo32(ReadBEword fstream)
)

fn ReadHalfFloat fstream = (
return convertTo32(readshort fstream#unsigned)
)

fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)

fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
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

Idstring = ReadFixedString f 4
Totalsize = ReadBElong f
Unk001 = ReadBElong f
Unk002 = ReadBElong f
Unk003 = ReadBElong f
Unk004 = ReadBElong f
MeshCount = ReadBElong f
MeshOff = ReadBElong f + 8
BoneCount = ReadBElong f
Unk008 = ReadBElong f
BoneOffset = ReadBElong f + 8
Unk010 = ReadBElong f
Unk011 = ReadBElong f
Unk012 = ReadBElong f
Unk013 = ReadBElong f
Unk014 = ReadBElong f
Unk015 = ReadBElong f
Unk016 = ReadBElong f
fseek f BoneOffset#seek_set
tarr = #()
rarr = #()
qarr = #()
Barr = #()
Parr = #()

for a = 1 to BoneCount Do (
BoneName = ReadFixedString f 16
tx = ReadBEfloat f
ty = ReadBEfloat f
tz = ReadBEfloat f
tw = ReadBEfloat f
rx = (ReadBEfloat f * 180) / pi
ry = (ReadBEfloat f * 180) / pi
rz = (ReadBEfloat f * 180) / pi
rw = ReadBEfloat f
parent = ReadBElong f
fseek f 0xC#seek_cur
qx = ReadBEfloat f
qy = ReadBEfloat f
qz = ReadBEfloat f
qw = ReadBEfloat f
tfm = (eulerangles rx ry rz) as matrix3
append tarr [tx,ty,tz]
append rarr tfm
append qarr [qx,qy,qz,qw]
append Barr BoneName
append Parr parent
)
BNArr = #()
for a = 1 to BoneCount Do (
tfm = rarr[a]
tfm.row4 = tarr[a]
 if (Parr[a] != -1) do (
tfm = tfm * BNArr[(Parr[a] + 1)].objecttransform
 )
newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = Barr[a]
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (Parr[a] != -1) then
 newBone.parent = BNArr[(Parr[a] + 1)]
append BNArr newBone
)

struct Mesh_Info_Struct
(
	Objname,VertOff,WeightOff,UVOff,MatPCount,matPOff,FaceOff,FaceSec,VertCount
)

fseek f MeshOff#seek_set
Mesh_Info_Arr = #()
for a = 1 to MeshCount Do (
VCount1 = ReadBElong f
FaceSec = ReadBElong f
UsedFF = ReadBElong f
fseek f 0x50#seek_cur
Unk101 = ReadBElong f
Unk102 = ReadBElong f
Unk103 = ReadBElong f
VertOff = ReadBElong f + 8
WeightOff = ReadBElong f + 8
UVOff = ReadBElong f + 8
Unk107 = ReadBElong f
Objname = ReadFixedString f 16
Unk108 = ReadBElong f
Unk109 = ReadBElong f
MatPCount = ReadBElong f
matPOff = ReadBElong f + 8
FaceOff = ReadBElong f + 8
VertCount = ReadBElong f
Unk114 = ReadBElong f
fseek f 0x10#seek_cur
append Mesh_Info_Arr (Mesh_Info_Struct Objname:Objname VertOff:VertOff WeightOff:WeightOff UVOff:UVOff MatPCount:MatPCount matPOff:matPOff FaceOff:FaceOff FaceSec:FaceSec VertCount:VertCount)
)
print Mesh_Info_Arr
for a = 1 to MeshCount Do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()	

fseek f Mesh_Info_Arr[a].VertOff#seek_set
scale1 = ReadBEfloat f
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
fseek f 0x10#seek_cur
append Vert_array [vx,vy,vz]
)

fseek f Mesh_Info_Arr[a].UVOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
tu = ReadBEfloat f
tv = ReadBEfloat f * -1
append UV_array [tu,tv,0]
)
fseek f Mesh_Info_Arr[a].FaceOff#seek_set
Ftmp = #()
for b = 1 to Mesh_Info_Arr[a].FaceSec Do (
FSize = ReadBElong f as float
FCount = ReadBElong f as float
FStart = (ReadBElong f + 8) as float
append Ftmp [FSize,FCount,FStart]
)
for b = 1 to Mesh_Info_Arr[a].FaceSec Do (
fseek f Ftmp[b].z#seek_set
FaceEnd = ((ftell f) + (2 * Ftmp[b].y))
StartDirection = 1
Face_array2 = #()
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection
do (
f3 = ReadBEword f
if (f3==0xFFFF) then (
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
append Face_array2 [(f1),(f2),(f3)]
if FaceDirection > 0 then append Face_array [(f1),(f2),(f3)]
else append Face_array [(f1),(f3),(f2)]
)
f1 = f2
f2 = f3
)
)while (ftell f) < (FaceEnd)
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
--msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)

fclose f

```

[s vs r 2011.png](https://xentaxbackup.github.io/file/4021_s vs r 2011.png)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-07T15:32:33+00:00
- Post Title: Runmbe Roses Import

Amazing news  , chrrox, so without weight data for now?
I can help you with testing wrestling games, i have the following titles:
WWE Smackdown vs raw 2006 (ps2)
WWE Smackdown vs raw 2007 (xbox360)
WWE Smackdown vs raw 2008 (ps2)
WWE Smackdown vs raw 2008 (xbox360)
WWE Smackdown vs raw 2009 (xbox360)
WWE Smackdown vs raw 2010 (xbox360)
WWE Smackdown vs raw 2011 (xbox360)
WWE Legends of Wrestlemania (xbox360)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-08T16:43:20+00:00
- Post Title: Runmbe Roses Import

Now with weight support I will add materials / textures next.

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"SVR2011 Model File" \
types:"SVR2011 Model File(*.yobj)|*.yobj" \
historyCategory:"SVR2011 Object Presets"
f = fopen fname "rb"

fn ReadBEShort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 2 1
b = (bit.get short 16)
for i = 17 to 32 do short = bit.set short i b
return short
)

fn PrintOffset Var =
(
        local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
        Var
)

fn floatSwap2 f = 
(
        i = bit.floatAsInt f
        h = bit.intashex i
        while h.count < 8 do h = "0" + h
        
        s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
        bit.intAsFloat (bit.hexasint s)
)       

fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
)

        fn convertTo32 input16 = (
                inputAsInt = input16
                sign = bit.get inputAsInt 16
                exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
                fraction = bit.and inputAsInt (bit.hexasint "03FF")
                if sign==true then sign = 1 else sign = 0
                exponentF = exponent + 127
                --Ouput 32 bit integer representing a 32 bit float
                outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
                --Output Check  
                return bit.intasfloat outputasfloat
        )

fn ReadBEHalfFloat fstream = (
return convertTo32(ReadBEword fstream)
)

fn ReadHalfFloat fstream = (
return convertTo32(readshort fstream#unsigned)
)

fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)

fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
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

Idstring = ReadFixedString f 4
Totalsize = ReadBElong f
Unk001 = ReadBElong f
Unk002 = ReadBElong f
Unk003 = ReadBElong f
Unk004 = ReadBElong f
MeshCount = ReadBElong f
MeshOff = ReadBElong f + 8
BoneCount = ReadBElong f
TexCount = ReadBElong f
BoneOffset = ReadBElong f + 8
TexOff = ReadBElong f + 8
MnameOff = ReadBElong f + 8
MnameCount = ReadBElong f
Unk013 = ReadBElong f
Unk014 = ReadBElong f
Unk015 = ReadBElong f
Unk016 = ReadBElong f
fseek f BoneOffset#seek_set
tarr = #()
rarr = #()
qarr = #()
Barr = #()
Parr = #()

for a = 1 to BoneCount Do (
BoneName = ReadFixedString f 16
tx = ReadBEfloat f
ty = ReadBEfloat f
tz = ReadBEfloat f
tw = ReadBEfloat f
rx = (ReadBEfloat f * 180) / pi
ry = (ReadBEfloat f * 180) / pi
rz = (ReadBEfloat f * 180) / pi
rw = ReadBEfloat f
parent = ReadBElong f
fseek f 0xC#seek_cur
qx = ReadBEfloat f
qy = ReadBEfloat f
qz = ReadBEfloat f
qw = ReadBEfloat f
tfm = (eulerangles rx ry rz) as matrix3
append tarr [tx,ty,tz]
append rarr tfm
append qarr [qx,qy,qz,qw]
append Barr BoneName
append Parr parent
)
BNArr = #()
for a = 1 to BoneCount Do (
if isvalidnode (getNodeByName Barr[a]) != true then (
tfm = rarr[a]
tfm.row4 = tarr[a]
 if (Parr[a] != -1) do (
tfm = tfm * BNArr[(Parr[a] + 1)].objecttransform
 )
newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = Barr[a]
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
				  )
if isvalidnode (getNodeByName Barr[a]) == true then (
newBone = getNodeByName Barr[a]
)
 if (Parr[a] != -1) then
 newBone.parent = BNArr[(Parr[a] + 1)]
append BNArr newBone

)
struct Mesh_Info_Struct
(
	Objname,VertOff,WeightOff,UVOff,MatPCount,matPOff,FaceOff,FaceSec,VertCount,WeightCount,BtableStart
)
fseek f MeshOff#seek_set
Mesh_Info_Arr = #()
for a = 1 to MeshCount Do (
VCount1 = ReadBElong f
FaceSec = ReadBElong f
BtableStart = (ftell f)
UsedBoneID = ReadBElong f
fseek f 0x50#seek_cur
WeightCount = ReadBElong f
Unk102 = ReadBElong f
Unk103 = ReadBElong f
VertOff = ReadBElong f + 8
WeightOff = ReadBElong f + 8
UVOff = ReadBElong f + 8
Unk107 = ReadBElong f
Objname = ReadFixedString f 16
Unk108 = ReadBElong f
Unk109 = ReadBElong f
MatPCount = ReadBElong f
matPOff = ReadBElong f + 8
FaceOff = ReadBElong f + 8
VertCount = ReadBElong f
Unk114 = ReadBElong f
fseek f 0x10#seek_cur
append Mesh_Info_Arr (Mesh_Info_Struct Objname:Objname VertOff:VertOff WeightOff:WeightOff UVOff:UVOff MatPCount:MatPCount matPOff:matPOff FaceOff:FaceOff FaceSec:FaceSec VertCount:VertCount WeightCount:WeightCount BtableStart:BtableStart )
)
print Mesh_Info_Arr
for a = 1 to MeshCount Do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()

fseek f Mesh_Info_Arr[a].VertOff#seek_set
scale1 = ReadBEfloat f
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
fseek f 0x10#seek_cur
append Vert_array [vx,vy,vz]
)

fseek f Mesh_Info_Arr[a].UVOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
tu = ReadBEfloat f
tv = ReadBEfloat f * -1
append UV_array [tu,tv,0]
)

fseek f Mesh_Info_Arr[a].WeightOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
Bone1 = -1
Bone2 = -1
Bone3 = -1
Bone4 = -1
if Mesh_Info_Arr[a].WeightCount == 1 do (
Bone1 = readbyte f
fseek f 0x3#seek_cur
Weight1 = ReadBEfloat f
)
if Mesh_Info_Arr[a].WeightCount == 2 do (
Bone1 = readbyte f
fseek f 0x3#seek_cur
Weight1 = ReadBEfloat f
Bone2 = readbyte f
fseek f 0x3#seek_cur
Weight2 = ReadBEfloat f
)
if Mesh_Info_Arr[a].WeightCount == 3 do (
Bone1 = readbyte f
fseek f 0x3#seek_cur
Weight1 = ReadBEfloat f
Bone2 = readbyte f
fseek f 0x3#seek_cur
Weight2 = ReadBEfloat f
Bone3 = readbyte f
fseek f 0x3#seek_cur
Weight3 = ReadBEfloat f
)
if Mesh_Info_Arr[a].WeightCount == 4 do (
Bone1 = readbyte f
fseek f 0x3#seek_cur
Weight1 = ReadBEfloat f
Bone2 = readbyte f
fseek f 0x3#seek_cur
Weight2 = ReadBEfloat f
Bone3 = readbyte f
fseek f 0x3#seek_cur
Weight3 = ReadBEfloat f
Bone4 = readbyte f
fseek f 0x3#seek_cur
Weight4 = readfloat f	
)
w = (weight_data boneids:#() weights:#())
maxweight = 0
if(Bone1 != -1) then
	maxweight = maxweight + weight1
if(Bone2 != -1) then
	maxweight = maxweight + weight2
if(Bone3 != -1) then
	maxweight = maxweight + weight3
if(Bone4 != -1) then
	maxweight = maxweight + weight4

if(maxweight != 0) then (
		if(Bone1 != -1) then (
			w1 = weight1 as float
			append w.boneids (bone1 + 1)
			append w.weights w1
		)
		if(Bone2 != -1) then (
			w2 = weight2 as float
			append w.boneids (bone2 + 1)
			append w.weights w2
		)
		if(Bone3 != -1) then (
			w3 = weight3 as float
			append w.boneids (bone3 + 1)
			append w.weights w3
		)
		if(Bone4 != -1) then (
			w4 = weight4 as float
			append w.boneids (bone4 + 1)
			append w.weights w4
		)		
	)
append Weight_array w
)
fseek f Mesh_Info_Arr[a].FaceOff#seek_set
Ftmp = #()
for b = 1 to Mesh_Info_Arr[a].FaceSec Do (
FSize = ReadBElong f as float
FCount = ReadBElong f as float
FStart = (ReadBElong f + 8) as float
append Ftmp [FSize,FCount,FStart]
)
for b = 1 to Mesh_Info_Arr[a].FaceSec Do (
fseek f Ftmp[b].z#seek_set
FaceEnd = ((ftell f) + (2 * Ftmp[b].y))
StartDirection = 1
Face_array2 = #()
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection
do (
f3 = ReadBEword f
if (f3==0xFFFF) then (
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
append Face_array2 [(f1),(f2),(f3)]
if FaceDirection > 0 then append Face_array [(f1),(f2),(f3)]
else append Face_array [(f1),(f3),(f2)]
)
f1 = f2
f2 = f3
)
)while (ftell f) < (FaceEnd)
)
fseek f Mesh_Info_Arr[a].BtableStart#seek_set
usedID = ReadBElong f
Used_Bone_array = #()
for b = 1 to usedID do (
bid = ReadBElong f
append Used_Bone_array bid
)

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
--msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

max modify mode
select msh
skinMod = skin ()
addModifier msh skinMod

for i = 1 to Used_Bone_array.count do
(
	maxbone = BNArr[(Used_Bone_array[i])]
	if i != Used_Bone_array.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod
for i = 1 to Weight_array.count do
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
max create mode
)

fclose f

```

[yukesweight.png](https://xentaxbackup.github.io/file/4026_yukesweight.png)
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-09T13:02:34+00:00
- Post Title: Runmbe Roses Import

> Reply from chrrox
>
> Now with weight support I will add materials / textures next.
Fantastic speed, chrrox, very nice. Looks like every time is same issue with weightings, but you did a great job and maybe you look at my research:

WWE Smackdown vs raw 2007 (xbox360) - bad weightings - you can notice by rotating arms - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2007-xb360-ch00.zip)
WWE Smackdown vs raw 2008 (ps2) - not sure how to unpack it
WWE Smackdown vs raw 2008 (xbox360) - bad weightings - you can notice by rotating arms - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2008-xb360-ch00.7z)
WWE Smackdown vs raw 2009 (xbox360) - looks like everything is ok - but for improving of capability you can check a [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2009-xb360-ch160-a012.7z)
WWE Smackdown vs raw 2010 (xbox360) - bad weightings - you can notice by rotating arms - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2010-xb360-00016002.zip)
WWE Smackdown vs raw 2011 (xbox360) - looks loke same problem with weightings - you can notice it by rotating arms
WWE Legends of Wrestlemania (xbox360) - bad weightings - you can notice by rotating arms - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-legends-of-wrestlemania-ch160.zip)
WWE Smackdown vs raw 2006 (ps2) - not working (something happened, but i don't know exactly what) - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2006-ps2-0001.zip)
WWE SmackDown Here Comes the Pain (ps2) - not working - same problem as in srv2006-ps2 - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-smackdown-hctp-ps2-0000.zip)
Rumble Roses XX (xbox360) - bad weightings too - on the brest
UFC 2010 Undisputed (xbox360) - importing only skeleton - it would be cool to have a model of this game - [sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/ufc-2010-undisputed-001.zip)
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T15:58:11+00:00
- Post Title: Runmbe Roses Import

hi, chrrox, do you have a time to solve those issue above?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T18:18:23+00:00
- Post Title: Runmbe Roses Import

its not bad weighting they just use a weird skeleton system.
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T18:46:32+00:00
- Post Title: Runmbe Roses Import

> Reply from chrrox
>
> its not bad weighting they just use a weird skeleton system.
so is no way to solve this issue?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T18:50:03+00:00
- Post Title: Runmbe Roses Import

upload the model i have not had any issues moving any model i tested.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T18:56:32+00:00
- Post Title: Runmbe Roses Import

> Reply from chrrox
>
> upload the model i have not had any issues moving any model i tested.
[http://dl.dropbox.com/u/9919707/blogs/x ... 005002.zip](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2011-xb360-00005002.zip)

p.s.: also i have same error with all samples i uploaded above, i'm using 3ds max 2008 x64 btw
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T19:06:33+00:00
- Post Title: Runmbe Roses Import

yeah its because their rigs are meant for mocap only. They are just very advanced rigs all the weighting is in one area if you look at the feet and hands they move perfectly they just have a lot of movements that depend on moving more then one bone at a time.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T19:17:20+00:00
- Post Title: Runmbe Roses Import

> Reply from chrrox
>
> yeah its because their rigs are meant for mocap only. They are just very advanced rigs all the weighting is in one area if you look at the feet and hands they move perfectly they just have a lot of movements that depend on moving more then one bone at a time.
but weighting is sooooo weird, i can't just simple rotate down the hands without any movements of vertexes in his brest
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-03T04:50:42+00:00
- Post Title: Runmbe Roses Import

chrrox, can you look at this one more time? i only turning the jaw bone (open mouse) and face is screwed up
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-03T12:36:34+00:00
- Post Title: Runmbe Roses Import

All the formats are the same. I am not sure why this one model is giving you such a hard time. I am just reading what is in the file I have tested several other games and they do not have issues. Ma bee they changed something in some of the older formats I am not sure I was mainly interested in rumble rores and the newer games and they all seem to work fine. If you notice they have more then one bone effecting those areas so they must move together.
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-03T12:45:36+00:00
- Post Title: Runmbe Roses Import

i tested sample models from all games from [this post](http://forum.xentax.com/viewtopic.php?p=50552#p50552), but every time i get same result, can you show me movements of your sample models, from 2011? maybe you right and i need change my system language.

i tested script on max: 2008 x64, 2011 x32, 2010 x64

> If you notice they have more then one bone effecting those areas so they must move together.
yes, but it's just a mouth opening: jaw with a couple of bones, nothing more 

add: i checked influences between lip bones, there is some strange unsymmetrical addiction of up bone to bottom
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-03T13:13:45+00:00
- Post Title: Runmbe Roses Import

here you go
[weighting.png](https://xentaxbackup.github.io/file/4156_weighting.png)
## Post #16
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-03T13:22:59+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

> Reply from chrrox
>
> here you go
thanks, can you tell mw what model is this?
## Post #17
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2011-04-04T07:03:49+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

ch103 undertaker i think.

great script chrrox. thank you very much for it.


ps: allready asked brien. wanted to give 2008 model 2010 hair, but game crashs. are different bones the reason?
## Post #18
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-04T09:04:24+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

> Reply from redman
>
> ch103 undertaker i think.
thanks, he is undertaker, buut, here is my model:
[](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/VPGRAB_Untitled_persp_user_0f005.jpg)

can you check [this model](http://dl.dropbox.com/u/9919707/blogs/xentax.com/wwe-rvs-games/wwe-rvs-2011-xb360-00005002.zip)?
## Post #19
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2011-04-04T15:07:07+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

you have 2011 there...try 2008 undertaker.

btw: can you explain me how to move the envelopes? never worked with bones.


ps: this is 2011 chris masters, right? man, the 2011 models near impossible to edit the head and making new wrestlers cause there split in so many objects. and where not allowd to add objects or attach them.
why the creators doing this? 2008 or 07 are only split in 2 objects.
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-04T16:11:16+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

> Reply from redman
>
> you have 2011 there...try 2008 undertaker.
hm, strange, if you say that with 2008 undertaker everithing is ok, so why with 2011 is not?
i'm just trying converting characters that don't have in 2008 version  and newer version have more polygons on the model

> Reply from redman
>
> btw: can you explain me how to move the envelopes? never worked with bones.
press "1" on keyboard when your skin modifier is active then select->move any envelope

> Reply from redman
>
> ps: this is 2011 chris masters, right? man, the 2011 models near impossible to edit the head and making new wrestlers cause there split in so many objects. and where not allowd to add objects or attach them.
why the creators doing this? 2008 or 07 are only split in 2 objects.so you have same issue as me, argghh  it's shame, very shame, i don't know if chrrox can spend more time to solving this issue, but i'm hope.

p.s.: and i see in rumble roses XX same problem with weights
## Post #21
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2011-04-04T16:39:15+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

it has nothing to do with chrrox. i only know that some engines work better when a model is split in many objects. i only don't understand why 2011 although it's still the same engine like 2007.

and thanks for the tip...try it out later.
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-04T17:02:53+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

> Reply from redman
>
> it has nothing to do with chrrox
i only said about weightings and not about amount of objects
## Post #23
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2011-04-04T20:03:58+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

ah, okay, sorry
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-07T16:23:31+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

> Reply from chrrox
>
> here you go
can you tell me what this model is? and from what version of the game? because i don't see any issue on your screenshot and i hope it's just a problem of my pc/max, thanks
## Post #25
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-04-07T17:08:03+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

I have the same problem, btw. Weights are screwed.
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-07T17:20:25+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

I dont care to look into this sorry.
It works on a lot of the models from some games and they have no issues with weighting.
the format is the same between games. If someone wants to convert this script that is fine but i dont want to spend any time on it.
## Post #27
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-04-07T18:32:55+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

Sorry chroxxx i lost, this its the information you posted, this need converted in script to importh the models from rumble roses?.

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \
caption:"SVR2011 Model File" \
types:"SVR2011 Model File(*.yobj)|*.yobj" \
historyCategory:"SVR2011 Object Presets"
f = fopen fname "rb"

fn ReadBEShort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 2 1
b = (bit.get short 16)
for i = 17 to 32 do short = bit.set short i b
return short
)
fn PrintOffset Var =
(
        local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
        Var
)

fn floatSwap2 f =
(
        i = bit.floatAsInt f
        h = bit.intashex i
        while h.count < 8 do h = "0" + h
       
        s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
        bit.intAsFloat (bit.hexasint s)
)       

fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
)

        fn convertTo32 input16 = (
                inputAsInt = input16
                sign = bit.get inputAsInt 16
                exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
                fraction = bit.and inputAsInt (bit.hexasint "03FF")
                if sign==true then sign = 1 else sign = 0
                exponentF = exponent + 127
                --Ouput 32 bit integer representing a 32 bit float
                outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
                --Output Check 
                return bit.intasfloat outputasfloat
        )

fn ReadBEHalfFloat fstream = (
return convertTo32(ReadBEword fstream)
)

fn ReadHalfFloat fstream = (
return convertTo32(readshort fstream#unsigned)
)

fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)

fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
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

Idstring = ReadFixedString f 4
Totalsize = ReadBElong f
Unk001 = ReadBElong f
Unk002 = ReadBElong f
Unk003 = ReadBElong f
Unk004 = ReadBElong f
MeshCount = ReadBElong f
MeshOff = ReadBElong f + 8
BoneCount = ReadBElong f
Unk008 = ReadBElong f
BoneOffset = ReadBElong f + 8
Unk010 = ReadBElong f
Unk011 = ReadBElong f
Unk012 = ReadBElong f
Unk013 = ReadBElong f
Unk014 = ReadBElong f
Unk015 = ReadBElong f
Unk016 = ReadBElong f
fseek f BoneOffset#seek_set
tarr = #()
rarr = #()
qarr = #()
Barr = #()
Parr = #()

for a = 1 to BoneCount Do (
BoneName = ReadFixedString f 16
tx = ReadBEfloat f
ty = ReadBEfloat f
tz = ReadBEfloat f
tw = ReadBEfloat f
rx = (ReadBEfloat f * 180) / pi
ry = (ReadBEfloat f * 180) / pi
rz = (ReadBEfloat f * 180) / pi
rw = ReadBEfloat f
parent = ReadBElong f
fseek f 0xC#seek_cur
qx = ReadBEfloat f
qy = ReadBEfloat f
qz = ReadBEfloat f
qw = ReadBEfloat f
tfm = (eulerangles rx ry rz) as matrix3
append tarr [tx,ty,tz]
append rarr tfm
append qarr [qx,qy,qz,qw]
append Barr BoneName
append Parr parent
)
BNArr = #()
for a = 1 to BoneCount Do (
tfm = rarr[a]
tfm.row4 = tarr[a]
if (Parr[a] != -1) do (
tfm = tfm * BNArr[(Parr[a] + 1)].objecttransform
)
newBone = bonesys.createbone   \
              tfm.row4   \
              (tfm.row4 + 0.01 * (normalize tfm.row1)) \
              (normalize tfm.row3)
         newBone.name = Barr[a]
         newBone.width  = 0.01
         newBone.height = 0.01
         newBone.transform = tfm
         newBone.setBoneEnable false 0
         newBone.wirecolor = yellow
         newbone.showlinks = true
         newBone.pos.controller      = TCB_position ()
         newBone.rotation.controller = TCB_rotation ()
if (Parr[a] != -1) then
newBone.parent = BNArr[(Parr[a] + 1)]
append BNArr newBone
)

struct Mesh_Info_Struct
(
   Objname,VertOff,WeightOff,UVOff,MatPCount,matPOff,FaceOff,FaceSec,VertCount
)

fseek f MeshOff#seek_set
Mesh_Info_Arr = #()
for a = 1 to MeshCount Do (
VCount1 = ReadBElong f
FaceSec = ReadBElong f
UsedFF = ReadBElong f
fseek f 0x50#seek_cur
Unk101 = ReadBElong f
Unk102 = ReadBElong f
Unk103 = ReadBElong f
VertOff = ReadBElong f + 8
WeightOff = ReadBElong f + 8
UVOff = ReadBElong f + 8
Unk107 = ReadBElong f
Objname = ReadFixedString f 16
Unk108 = ReadBElong f
Unk109 = ReadBElong f
MatPCount = ReadBElong f
matPOff = ReadBElong f + 8
FaceOff = ReadBElong f + 8
VertCount = ReadBElong f
Unk114 = ReadBElong f
fseek f 0x10#seek_cur
append Mesh_Info_Arr (Mesh_Info_Struct Objname:Objname VertOff:VertOff WeightOff:WeightOff UVOff:UVOff MatPCount:MatPCount matPOff:matPOff FaceOff:FaceOff FaceSec:FaceSec VertCount:VertCount)
)
print Mesh_Info_Arr
for a = 1 to MeshCount Do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()   

fseek f Mesh_Info_Arr[a].VertOff#seek_set
scale1 = ReadBEfloat f
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
fseek f 0x10#seek_cur
append Vert_array [vx,vy,vz]
)

fseek f Mesh_Info_Arr[a].UVOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
tu = ReadBEfloat f
tv = ReadBEfloat f * -1
append UV_array [tu,tv,0]
)
fseek f Mesh_Info_Arr[a].FaceOff#seek_set
Ftmp = #()
for b = 1 to Mesh_Info_Arr[a].FaceSec Do (
FSize = ReadBElong f as float
FCount = ReadBElong f as float
FStart = (ReadBElong f + 8) as float
append Ftmp [FSize,FCount,FStart]
)
for b = 1 to Mesh_Info_Arr[a].FaceSec Do (
fseek f Ftmp[b].z#seek_set
FaceEnd = ((ftell f) + (2 * Ftmp[b].y))
StartDirection = 1
Face_array2 = #()
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection
do (
f3 = ReadBEword f
if (f3==0xFFFF) then (
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
append Face_array2 [(f1),(f2),(f3)]
if FaceDirection > 0 then append Face_array [(f1),(f2),(f3)]
else append Face_array [(f1),(f3),(f2)]
)
f1 = f2
f2 = f3
)
)while (ftell f) < (FaceEnd)
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
--msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)

fclose f
```
## Post #28
- Username: locakert22
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Mar 28, 2011 9:47 pm
- Post datetime: 2011-04-30T08:44:26+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

DELETE
## Post #29
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-04-30T20:19:32+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

The contents of this post was deleted because of possible forum rules violation.
## Post #30
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-02T01:44:28+00:00
- Post Title: Re: Smackdown Vs Raw 2011 Import

I got some weight problem
## Post #31
- Username: bondlaw
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Apr 15, 2010 5:46 am
- Post datetime: 2011-06-08T01:25:00+00:00
- Post Title: Re: Runmbe Roses Import

> Reply from chrrox
>
> I have tested this on 2011 models i will improve it more this is just a start...
Amazing chrrox!! you always remind me how much i have to learn!!
i have few  questions, is there a last version with the texture material /texture assignment done?
and if it is, 
where can i find it?
thank you very much for everything!!
## Post #32
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2011-11-19T21:30:37+00:00
- Post Title: Re: Runmbe Roses Import

The contents of this post was deleted because of possible forum rules violation.
