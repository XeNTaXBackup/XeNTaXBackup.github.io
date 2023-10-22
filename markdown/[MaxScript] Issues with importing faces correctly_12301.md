## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-30T23:58:47+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

Trying to import models from the PS2 game SMT: Nocturne

Faces aren't importing correctly, don't know why.

```
clearlistener()
fname = getOpenFileName \ 
caption:"Open File" \
types:"Packed Binary(*.PB)|*.pb|Model Binary(*.MB)|*.MB|*.*|*.*" \
historyCategory:"AtlusPB Object Presets"

fn ReadFixedString bstream fixedLen =
(
   local str = ""
   for i = 1 to fixedLen do
   (
      str0 = ReadByte bstream #unsigned
      if str0!=0xFD AND str0!=0xFC do str+= bit.intAsChar str0
   )
   str
)

if fname != undefined do (	
f = fopen fname "rb"
filename = GetFilenameFile fname

--read PB header--
PBStart = ftell f
PBEnd = (
	fseek f 0 #seek_end
	ftell f
)
fseek f PBStart #seek_set
PBFlag = readlong f
PBSomeSize = readlong f --not the actual size of the header
PIB0Tag = readstring f
if PIB0Tag!="PIB0" then fseek f 0 #seek_set
else if PIB0Tag=="PIB0" do (


--skip to MD00 chunk--
if PBSomeSize == 0x48 then (
	fseek f 0x84 #seek_set
	D3PSize = readlong f
	fseek f (D3PSize + 0x10) #seek_cur
	TXP0Tag = readfixedstring f 4
	if TXP0Tag != "TXP0" do ( -- some D3P chunks have tmx files stored in them and the D3PSize isn't accurate for those
		fseek f 0xC #seek_cur
		TXP0Tag = readfixedstring f 4
	)
	fseek f -0x8 #seek_cur
	TXP0Size = readlong f
	fseek f (TXP0Size - 0x8) #seek_cur
)
else if PBSomeSize == 0x5C then (
	fseek f 0x84 #seek_set
	D3PSize = readlong f
	fseek f (D3PSize + -0x4) #seek_cur
	D3PSize2 = readlong f						-- multiple D3P chunks
	fseek f (D3PSize2 + 0x10) #seek_cur
	TXP0Tag = readfixedstring f 4
	if TXP0Tag != "TXP0" do ( -- some D3P chunks have tmx files stored in them and the D3PSize isn't accurate for those
		fseek f 0xC #seek_cur
		TXP0Tag = readfixedstring f 4
	)
	fseek f -0x8 #seek_cur
	TXP0Size = readlong f
	fseek f (TXP0Size - 0x8) #seek_cur
)
else if PBSomeSize == 0x24 then (
	fseek f 0x44 #seek_set
	TXP0Size = readlong f
	fseek f (TXP0Size - 0x8) #seek_cur
)
else if PBSomeSize == 0x264 then (
	fseek f 0x284 #seek_set
	TXP0Size = readlong f
	fseek f (TXP0Size - 0x8) #seek_cur
)
else if PBSomeSize == 0x28C then (
	fseek f 0x2C4 #seek_set
	TXP0Size = readlong f
	fseek f (TXP0Size - 0x8) #seek_cur
)
else 
(
print ("Unknown PBSize!" + PBSomeSize as string)
break() 
)
print ("Start of MD00 section @ 0x"+((bit.intAsHex(ftell f))as string))
)

--start reading MD00 chunk--
MD00Start = ftell f
MD00Flag = readlong f
MD00Size = readlong f
MD00End = (
	fseek f (MD00Size - 0x8) #seek_cur
	ftell f
)
fseek f (MD00Start + 0x8) #seek_set
MD00Tag = readfixedstring f 4
if MD00Tag != "MD00" then (
	print ("Invalid model signature!" + MD00Tag as string)
	break()
)
fseek f 4 #seek_cur
EOFChunkOffset = readlong f
EOFByteCount = readlong f
fseek f 8 #seek_cur
InfoArrayOffset = ftell f
InfoArrayID = readlong f
SomeChunkOffset = readlong f
fseek f (SomeChunkOffset - 0x8) #seek_cur
SomeChunkRealOffset = ftell f
fseek f (InfoArrayOffset + 0x8) #seek_set
SomeChunkSize = readlong f
NDNMOffset = readlong f

BoneCount = readlong f
	Print ("Bone count: " + BoneCount as string)
fseek f 0xC #seek_cur
	Print ("Bone data start @ 0x"+((bit.intAsHex(ftell f))as string))
BoneStart = ftell f
fseek f InfoArrayOffset #seek_set
fseek f NDNMOffset #seek_cur
Bone_Data_Array = #()

struct BoneDData (
BoneName, BoneID, BoneParentID, BOffset1, BOffset2, BOffset3, BOffset4
)

if NDNMOffset != 0x0 do (
	NDNMTag = readfixedstring f 4
	NDNMSize = readlong f

for b = 1 to BoneCount do
(
BoneName = readstring f
	Print (BoneName as string)
-- 	Print ("Bone name char count: " + BoneName.count as string)
-- 	Print ("Bone name end @ 0x"+((bit.intAsHex(ftell f))as string))
-- 	Print ("Bone Array ID: " + b as string)
if BoneName.count == 0 do (
	print "Invalid bone name!"
	break()
)
if (mod BoneName.count 4) == 0 do (
	fseek f (0x4-1) #seek_cur
	BoneID = readlong f
)
if (mod BoneName.count 4) == 1 do (
	fseek f (0x3-1) #seek_cur
	BoneID = readlong f
)
if (mod BoneName.count 4) == 2 do (
	fseek f (0x2-1) #seek_cur
	BoneID = readlong f
)
if (mod BoneName.count 4) == 3 do (
	fseek f (0x1-1) #seek_cur
	BoneID = readlong f
)
append Bone_Data_Array (BoneDData BoneName:BoneName )
)
)

fseek f BoneStart #seek_set
if BoneCount != 0 do (
BNArr = #()
for i = 1 to BoneCount Do 
(
fseek f 0x8 #seek_cur --skipping junk
BoneID = readlong f
BoneParentID = readlong f
rx = readfloat f; ry = readfloat f; rz = readfloat f; rw = readfloat f
px = readfloat f; py = readfloat f; pz = readfloat f; pw = readfloat f
sx = readfloat f; sy = readfloat f; sz = readfloat f; sw = readfloat f
BOffset1 = readlong f
BOffset2 = readlong f
BOffset3 = readlong f
BOffset4 = readlong f
BoneRot = (quat rx ry rz rw)
BonePos = [px,py,pz]
BoneScl = [sx,sy,sz,sw]
append Bone_Data_Array (BoneDData BoneID:BoneID BoneParentID:BoneParentID BOffset1:BOffset BOffset2:BOffset2 BOffset3:BOffset3 BOffset4:BOffset4)
bne = dummy showLinks:true showLinksOnly:true
bne.scale = BoneScl
if Bone_Data_array[i].BoneName != undefined then (	
	bne.name = Bone_Data_array[i].BoneName
)
if Bone_Data_array[i].BoneName == undefined then (
	bne.name = "Bone" + i as string
)
bne.rotation = BoneRot
bne.pos = BonePos
append BNArr bne
if (BoneParentID != -1) then (
bne.parent = BNArr[BoneParentID+1]
bne.transform *= bne.parent.transform
)
)
	Print ("Bone data end @ 0x"+((bit.intAsHex(ftell f))as string))
)

struct ArrayInfoData
(
	ArrayType, Unknown, DataCount, DataType
)
ArrayInfoData_Array = #()
FaceIndex_Array = #()
NormalVerts_Array = #()
TexVerts_Array = #()
PosVerts_Array = #()
BBoxMin = #()
BBoxMax = #()
MeshOffsetArray = #()

--fseek f 0x40 #seek_cur -- skip
BoundingBox = (
	minbbx = readfloat f
	minbby = readfloat f
	minbbz = readfloat f
	maxBBx = readfloat f
	maxBBy = readfloat f
	maxBBz = readfloat f
	append BBoxMin [minbbx,minbby,minbbz]
	append BBoxMax [maxBBx,maxBBy,maxBBz]
)

OffsetTable_Offset = readlong f 
fseek f InfoArrayOffset #seek_set
fseek f OffsetTable_Offset #seek_cur

MeshCount = readshort f
Unknown = readshort f
for z = 1 to MeshCount do (
	MeshOffset = readlong f
	append MeshOffsetArray MeshOffset
)
fseek f InfoArrayOffset #seek_set
fseek f MeshOffsetArray[1] #seek_cur
Print ("Mesh Data start @ 0x"+((bit.intAsHex(ftell f))as string))

while ftell f != SomeChunkRealOffset do (
ArrayType = readbyte f
Print ("Array Type 0x" + ((bit.intAsHex(ArrayType))as string))
case of
(
(ArrayType == 0x00):( -- Mesh Data Info Array
SubMeshCount = 0
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x6D):(
TotalFaceCount = readshort f
TotalVertCount = readshort f
Unknown = readshort f
SubMeshID = readshort f				
)
(DataType == 0x00):(
while PaddingTest == 0x00 do (
PaddingTest = readlong f
)	
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x01):( -- Index Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x6E):( -- 0x40 index data
for x = 1 to DataCount do (
f1 = readbyte f+1
f2 = readbyte f+1
f3 = readbyte f+1
ff = readbyte f -- flag
append FaceIndex_Array [f1,f2,f3,ff]
)
)
(DataType == 0x00):( -- Mesh Object header, following sub meshes
MeshFaceCount = readlong f
MeshVertCount = readlong f
Unknown = readlong f
)
default:(
print ("Unknown Array Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x05):( -- Vertex Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append PosVerts_Array [vx,vy,vz]
)
)
default:(
print ("Unknown Array Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x0B):( -- Normal Array 
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x0C):( -- Submesh End Array
Unknown = readbyte f
Unknown = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x14):(
print ("Submesh end @ 0x"+((bit.intAsHex(ftell f))as string))
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x11):( -- Vertex Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append PosVerts_Array [vx,vy,vz]
)
)
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x1B):( -- Vertex Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append PosVerts_Array [vx,vy,vz]
)
)
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x21):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x23):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x24):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x25):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x27):( -- Normal Array 
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Array Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x28):( -- Normal Array 
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Array Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x2A):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x2B):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x2C):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x2D):( -- Normal Array 
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
default:(
print ("Unknown Data Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x31):( -- Normal Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of
(
(DataType == 0x68):(
for x = 1 to DataCount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append NormalVerts_Array [nx,ny,nz]
)
)
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
default:(
print ("Unknown Array Type! @ 0x"+((bit.intAsHex(ftell f))as string))
)
)
)
(ArrayType == 0x35):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x37):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x39):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x3D):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x3F):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x43):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x47):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x49):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
(ArrayType == 0x51):( -- UV Array
Unknown = readbyte f
DataCount = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x64):(
for x = 1 to DataCount do (
tu = readfloat f
tv = readfloat f
append TexVerts_Array [tu,tv,0]
)
)
)
)
---
---
default:(
print ("Unknown Array Type! @ 0x"+((bit.intAsHex(ftell f))as string))
break()
)
)
)

DummyFaceArray = #()
msh = mesh vertices:PosVerts_Array faces:FaceIndex_Array
msh.numTVerts = TexVerts_Array.count
msh.name = filename	
setNumCPVVerts msh msh.numTVerts
setCVertMode msh false
setShadeCVerts msh false
defaultVCFaces msh
buildTVFaces msh
-- for j = 1 to Color_array.count do setvertcolor msh j Color_array[j]
for j = 1 to TexVerts_array.count do setTVert msh j TexVerts_array[j]
for j = 1 to FaceIndex_array.count do setTVFace msh j FaceIndex_array[j]
for j = 1 to msh.numfaces do setFaceSmoothGroup msh j 1
max modify mode
select msh
	addmodifier msh (Edit_Normals ()) ui:off
	msh.Edit_Normals.MakeExplicit selection:#{1..NormalVerts_array.count}
	EN_convertVS = msh.Edit_Normals.ConvertVertexSelection
	EN_setNormal = msh.Edit_Normals.SetNormal
	normID = #{}

	for v = 1 to NormalVerts_array.count do(
		free normID
		EN_convertVS #{v} &normID
		for id in normID do EN_setNormal id NormalVerts_array[v]
	)
	
--end of file functions
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
)
```

sample files [http://puu.sh/dc8ye.7z](http://puu.sh/dc8ye.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-01T00:47:30+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

log your face indices:

f 1 2 3
f 3 4 1
f 5 6 7
f 7 8 5
f 9 10 11
f 11 12 9
f 13 14 15
f 15 16 13
f 17 18 19
f 20 21 22
f 22 23 20
f 24 25 26
f 27 28 29
f 29 30 27
f 31 32 18
f 18 17 31
"Array Type 0x11"
"Array Type 0x31"
"Array Type 0x51"
"Array Type 0xc"
"Submesh end @ 0x530L"
"Array Type 0x0"
"Array Type 0x1"
"Array Type 0x1"
f 1 2 3 -- starting with vertex 1 again, wrong!
f 3 4 1
f 5 6 7
...
see the problem?

should look like
f 33 34 35
f 35 36 33
f 37 38 39
...

introduce vars fiStart, maxFi, f1_,f2_,f3_ for example and apply these lines to your script:

maxFi = 0 (before for x = 1 to DataCount do )

if f1 > maxFi then maxFi= f1
if f2 > maxFi then maxFi= f2
if f3 > maxFi then maxFi= f3	
ff = readbyte f -- flag
f1_= f1+fiStart; f2_= f2+fiStart; f3_= f3+fiStart
append FaceIndex_Array [f1_,f2_,f3_,ff]
)
fiStart += maxFi

don't forget to initialyze fiStart = 0 somewhere at the beginning

result:



smt_nocturne.JPG (44.68 KiB) Viewed 122 times
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-01T02:55:23+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

> Reply from shakotay2
>
> 
introduce vars fiStart, maxFi, f1_,f2_,f3_ for example and apply these lines to your script:
I do not understand how fiStart is supposed to be used.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-01T09:39:17+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

fiStart = 0
--read PB header--

Is it that what you mean?

It's use is to calculate absolute faceindices instead of "relative" ones.
"Relative" means referring to the start of a submesh (SM).

For the box sample the 2nd SM starts from vertex number 33 so for this SM
fiStart is 32. Maybe you should name it absoluteFi to make it more clear.

edit: upps, sry I've lost a very important line in my previous post:
append FaceIndex_Array [f1_,f2_,f3_,ff]
)
fiStart += maxFi
## Post #5
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-01T10:22:12+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

Ah yes, I figured there was something missing.
Thanks for your help as always.
## Post #6
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-02T17:37:18+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

Would you perhaps know how to import each submesh as a seperate object? It'd be easier to debug that way.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-02T18:39:47+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

I could think of doing it this way:

```

	for i = 1 to numSubMeshes do (
		...
		append subMeshes(...)
	)
```


(A maxscript expert probably would have a simpler solution.)

Or -if you logged the data to an *.obj file - it's rather simple:
just write g subMesh_x lines when logging f f1 f2 f3 lines to the obj file
with x being the submesh number as a string
## Post #8
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-03T16:57:45+00:00
- Post Title: [MaxScript] Issues with importing faces correctly

> Reply from shakotay2
>
> I could think of doing it this way:
Code: Select allsubMmeshes = #()

	for i = 1 to numSubMeshes do (
		...
		append subMeshes(...)
	)

(A maxscript expert probably would have a simpler solution.)

Or -if you logged the data to an *.obj file - it's rather simple:
just write g subMesh_x lines when logging f f1 f2 f3 lines to the obj file
with x being the submesh number as a string
Ended up doing it like this...

```
...
(ArrayType == 0x0C):( -- Submesh End Array
Unknown = readbyte f
Unknown = readbyte f
DataType = readbyte f
case of 
(
(DataType == 0x14):(
SubMeshCounter +=1
print ("Submesh end @ 0x"+((bit.intAsHex(ftell f))as string))
msh = mesh vertices:PosVerts_Array faces:FaceIndex_Array
msh.numTVerts = TexVerts_Array.count
msh.name = filename+" "+SubMeshCounter as string
-- setNumCPVVerts msh msh.numTVerts
-- setCVertMode msh false
-- setShadeCVerts msh false
-- defaultVCFaces msh
buildTVFaces msh
-- for j = 1 to Color_array.count do setvertcolor msh j Color_array[j]
for j = 1 to TexVerts_array.count do setTVert msh j TexVerts_array[j]
for j = 1 to FaceIndex_array.count do setTVFace msh j FaceIndex_array[j]
for j = 1 to msh.numfaces do setFaceSmoothGroup msh j 1
max modify mode
select msh
	addmodifier msh (Edit_Normals ()) ui:off
	msh.Edit_Normals.MakeExplicit selection:#{1..NormalVerts_array.count}
	EN_convertVS = msh.Edit_Normals.ConvertVertexSelection
	EN_setNormal = msh.Edit_Normals.SetNormal
	normID = #{}

	for v = 1 to NormalVerts_array.count do(
		free normID
		EN_convertVS #{v} &normID
		for id in normID do EN_setNormal id NormalVerts_array[v]
	)
)

```
