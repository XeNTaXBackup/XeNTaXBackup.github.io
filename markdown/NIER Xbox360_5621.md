## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-24T01:22:23+00:00
- Post Title: NIER Xbox360

BMS Script

```
get name FILENAME
string name + ".dec"
get lzo long
get version long
get subversion long
get files long
get TotalUncompSize long
get unk long
goto 0x20
comtype LZO1X
for i = 1 to files
get memoffset long
get size long
get zsize long
savepos offset
if size == zsize
append
log MEMORY_FILE offset zsize
append
else
append
clog MEMORY_FILE offset zsize size
append
endif
math offset + zsize
goto offset
Padding 0x10000
next i
log NAME 0 TotalUncompSize MEMORY_FILE

```


here is the Max script.

This is a great import with bones and materials.

```
   heapSize = 30000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \
caption:"NIER Model File" \
types:"NIER Model File(*.mdv)|*.mdv" \
historyCategory:"NIERObjectPresets"
f = fopen fname "rb"
fname2 = ((getFilenamePath fname) + (getFilenameFile fname)) + ".MDP.dec"
g = fopen fname2 "rb"

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
--0x20 size is an lod can delete them
fseek f 0x10#seek_set
BoneOff = ReadBElong f + 0x80
fseek f 0x110#seek_set
NODToff = ReadBElong f + 0x100
heapoff = ReadBElong f + 0x100

fseek f 0x180#seek_set
MESH1 = ReadFixedString f 4
MESH1Size = ReadBElong f
MESH1Off = (ftell f) + MESH1Size
REM0 = ReadFixedString f 4
REM0Size = ReadBElong f
REM0Name = ReadFixedString f REM0Size

STRB = ReadFixedString f 4
STRBSize = ReadBElong f
STRBOff = (ftell f) + STRBSize
STRBCount = ReadBElong f
STRL = ReadFixedString f 4
STRLSize = ReadBElong f
Name2_Array = #()
for a = 1 to STRBCount Do (
Name2 = readstring f
append Name2_Array  Name2
)
print Name2_Array
fseek f STRBOff#seek_set
meditMaterials[1] = Multimaterial ()
MatID_array = #()
MatSlotTexID = #()
While (ftell f) != MESH1Off Do (
Name1 = ReadFixedString f 4
print Name1
Name1Size = ReadBElong f
if Name1 == "DSNA" Do (
fseek f Name1Size#seek_cur
)
if Name1 == "TRSP" Do (
fseek f Name1Size#seek_cur
)
if Name1 == "EFFE" Do (
fseek f 0x10#seek_cur
)
if Name1 == "TPAS" Do (
fseek f Name1Size#seek_cur
)
if Name1 == "CSTS" Do (
fseek f 0x4#seek_cur
)
if Name1 == "CSTV" Do (
fseek f Name1Size#seek_cur
)

if Name1 == "SAMP" Do (
MatID = ReadBElong f + 1
append MatID_array MatID
print ("This is the material info for slot " + MatID as string)
)
if Name1 == "SSTV" Do (
MatSlot = ReadBElong f
TexID = ReadBElong f + 1
MatNameID = ReadBElong f

if MatSlot == 29 Do (
print ("The Diffuse Texture is " + Name2_Array[TexID])
meditMaterials[1].materialList[MatID_array.count].diffuseMap = Bitmaptexture fileName:((getFilenamePath fname) + (Name2_Array[TexID] + ".tga"))
meditMaterials[1].materialList[MatID_array.count].opacityMap = Bitmaptexture fileName:((getFilenamePath fname) + (Name2_Array[TexID] + ".tga"))
meditMaterials[1].materialList[MatID_array.count].opacityMap.monoOutput = 1
meditMaterials[1].materialList[MatID_array.count].opacityMapEnable = on
meditMaterials[1].materialList[MatID_array.count].diffuseMap.alphaSource = 2
)
if MatSlot == 32 Do (
print ("The Normal Texture is " + Name2_Array[TexID])
meditMaterials[1].materialList[MatID_array.count].bumpMap = Normal_Bump ()
meditMaterials[1].materialList[MatID_array.count].bumpMap.normal_map = Bitmaptexture fileName:((getFilenamePath fname) + (Name2_Array[TexID] + ".tga"))
meditMaterials[1].materialList[MatID_array.count].bumpMap.normal_map.Output.Invert = true
)
if MatSlot == 35 Do (
print ("The Specular Texture is " + Name2_Array[TexID])
meditMaterials[1].materialList[MatID_array.count].specularLevelMap = Bitmaptexture fileName:((getFilenamePath fname) + (Name2_Array[TexID] + ".tga"))
meditMaterials[1].materialList[MatID_array.count].specularLevelMapEnable = off
)
if MatSlot == 44 Do (
print ("The 2nd Normal Texture is " + Name2_Array[TexID])
meditMaterials[1].materialList[MatID_array.count].specularMap = Bitmaptexture fileName:((getFilenamePath fname) + (Name2_Array[TexID] + ".tga"))
meditMaterials[1].materialList[MatID_array.count].specularMapEnable = off
)
)
if Name1 == "MATE" Do (
MatSlotID = ReadBElong f + 1
MatSlotN1 = ReadBElong f + 1
MatSlotN2 = ReadBElong f + 1
MatSlotID2 = ReadBElong f
MatSlotTexID1 = ReadBElong f + 1
MatSlotN = ReadBElong f
MatSlotN = ReadBElong f
MatSlotTexID2 = ReadBElong f + 1
meditMaterials[1].names[MatSlotID] = Name2_Array[MatSlotN1]
meditMaterials[1][MatSlotID].name = Name2_Array[MatSlotN2]
)
if Name1 == "VARI" Do (
fseek f 0x10#seek_cur   
)
if Name1 == "PRIM" Do (
MshSlotID = ReadBElong f
MshSlotID = ReadBElong f
MshSlotID = ReadBElong f
MshSlotID = ReadBElong f
MshSlotID = ReadBElong f
MshMatID = ReadBElong f + 1
MshSlotID = ReadBElong f
   append MatSlotTexID MshMatID
)
if Name1 == "BONE" Do (
fseek f 0x4#seek_cur   
)
if Name1 == "BOIF" Do (
fseek f Name1Size#seek_cur      
)
if Name1 == "IMTX" Do (
fseek f Name1Size#seek_cur      
)
if Name1 == "" Do (
   
)
)

fseek f BoneOff#seek_set
CJF = ReadFixedString f 4
RigName = ReadFixedString f 0x20
BoneCount = ReadBElong f
Unk01Count = ReadBElong f
BoneNameStart = ReadBElong f + BoneOff
Unk01Start = ReadBElong f + BoneOff
BoneParentStart = ReadBElong f + BoneOff
BoneMatrixStart = ReadBElong f + BoneOff
BoneInvMatrixStart = ReadBElong f + BoneOff

Bone_Name_Array = #()
Bone_Parent_Array = #()
struct Bone_Info_Struct
(
   BonePID01,BonePID02,BonePID03
)
fseek f BoneNameStart#seek_set
with undo off with redraw off for a = 1 to BoneCount Do (
Unk01 = ReadBElong f
BoneName = ReadFixedString f 0x20
append Bone_Name_Array BoneName
)
print Bone_Name_Array
fseek f BoneParentStart#seek_set
with undo off with redraw off for a = 1 to BoneCount Do (
BonePID01 = ReadBEword f + 1
append Bone_Parent_Array BonePID01
)
print Bone_Parent_Array
fseek f BoneMatrixStart#seek_set
BNArr = #()
with undo off with redraw off for a = 1 to BoneCount Do (
m11 = ReadBEFloat f; m12 = ReadBEFloat f; m13 = ReadBEFloat f; m14 = ReadBEFloat f
m21 = ReadBEFloat f; m22 = ReadBEFloat f; m23 = ReadBEFloat f; m24 = ReadBEFloat f
m31 = ReadBEFloat f; m32 = ReadBEFloat f; m33 = ReadBEFloat f; m34 = ReadBEFloat f
m41 = ReadBEFloat f; m42 = ReadBEFloat f; m43 = ReadBEFloat f; m44 = ReadBEFloat f
tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]

   newBone = bonesys.createbone   \
              tfm.row4   \
              (tfm.row4 + 0.01 * (normalize tfm.row1)) \
              (normalize tfm.row3)
         newBone.name = Bone_Name_Array[a]
         newBone.width  = 0.01
         newBone.height = 0.01
         newBone.transform = tfm
         newBone.setBoneEnable false 0
         newBone.wirecolor = yellow
         newbone.showlinks = true
         newBone.pos.controller      = TCB_position ()
         newBone.rotation.controller = TCB_rotation ()
   append BNArr newBone
)
with undo off with redraw off for a = 1 to BoneCount Do (
select BNArr[a]
if (Bone_Parent_Array[a] != 0) then
$.parent = BNArr[(Bone_Parent_Array[a])]
)


fseek f heapoff#seek_set
HEAP = ReadFixedString f 4
Null1= ReadBElong f
SectSize= ReadBElong f
Heap1Size= ReadBElong f
Count1= ReadBElong f
NameSize= ReadBElong f
Null1= ReadBElong f
HeapCount= ReadBElong f
myoff = (ftell f)
fseek f (heapoff + Heap1Size)#seek_set
Mesh_Name_array = #()
while (ftell f) <= (heapoff + Count1) do (
Mesh_Name = readstring f
if Mesh_Name != "" do (
append Mesh_Name_array Mesh_Name
)
)
print Mesh_Name_array
fseek f myoff#seek_set
IXBF_array = #()
VXBF_array = #()
VXST_array = #()
struct Mesh_Info_Struct
(
   HEAPID,Size,Offset,TotalSize
)

for a = 1 to HeapCount do (
HEAPID = ReadFixedString f 4
print HEAPID
fseek f 0x1C#seek_cur
if HEAPID == "IXBF" do (
fseek f -0x10#seek_cur
Size = ReadBElong f
Offset = ReadBElong f
TotalSize = ReadBElong f
Null1 = ReadBElong f
append IXBF_array (Mesh_Info_Struct HEAPID:HEAPID Size:Size Offset:Offset TotalSize:TotalSize)
)
if HEAPID == "VXBF" do (
fseek f -0x10#seek_cur
Size = ReadBElong f
Offset = ReadBElong f
TotalSize = ReadBElong f
Null1 = ReadBElong f
append VXBF_array (Mesh_Info_Struct HEAPID:HEAPID Size:Size Offset:Offset TotalSize:TotalSize)
)
if HEAPID == "VXST" do (
fseek f -0x14#seek_cur
Offset = (ReadBElong f)  + ((Count1 + heapoff) + 0x30)
print Offset
fseek f 0x10#seek_cur
append VXST_array Offset
)
)
print IXBF_array
print VXBF_array
print VXST_array
vsize_array = #()

for a = 1 to VXST_array.count do (
fseek f VXST_array[a]#seek_set
vertsize = ReadBElong f
append vsize_array vertsize
)
print vsize_array
with undo off with redraw off for a = 1 to IXBF_array.count Do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
used_id_array =#()
Weight_array = #()
fseek g IXBF_array[a].offset#seek_set
FaceEnd = (IXBF_array[a].offset + (IXBF_array[a].TotalSize))
StartDirection = -1
f1 = ReadBEword g + 1
f2 = ReadBEword g + 1
IndexCounter = 2
FaceDirection = StartDirection
do (
f3 = ReadBEword g
IndexCounter += 1
if (f3==0xFFFF) then (
f1 = ReadBEword g + 1
f2 = ReadBEword g + 1
IndexCounter += 2
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
if FaceDirection > 0 then append Face_array [(f1),(f2),(f3)]
else append Face_array [(f1),(f3),(f2)]
)
f1 = f2
f2 = f3
) 
)while (ftell g) <= FaceEnd
printoffset (ftell g)
fseek g VXBF_array[a].offset#seek_set
VertCount = (VXBF_array[a].TotalSize / vsize_array[a])
for b = 1 to VertCount Do (
if vsize_array[a] == 12 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
tu =0
tv = 0
   
weight1 = 0
weight2 = 0
weight3 = 0
weight4 = 0
bone1 = 1
bone2 = 1
bone3 = 1
bone4 = 1
)
if vsize_array[a] == 20 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
tu = 0
tv = 0
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned

)
if vsize_array[a] == 24 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2

)
if vsize_array[a] == 28 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2
unk24 = ReadBEfloat g
)
if vsize_array[a] == 32   do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g

weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
nz = ReadBEfloat g
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2
unk24 = ReadBEfloat g   
)
if vsize_array[a] == 36 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
nz = ReadBEfloat g
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2
unk24 = ReadBEfloat g
unk24 = ReadBEfloat g   

)
if vsize_array[a] == 40 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
nz = ReadBEfloat g
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2
unk24 = ReadBEfloat g
unk24 = ReadBEfloat g   
unk24 = ReadBEfloat g   

)
if vsize_array[a] == 44 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
nz = ReadBEfloat g
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2
unk24 = ReadBEfloat g
unk24 = ReadBEfloat g   
unk24 = ReadBEfloat g
unk24 = ReadBEfloat g

)
if vsize_array[a] == 48 do (
vx = ReadBEfloat g
vy = ReadBEfloat g
vz = ReadBEfloat g
weight1 = readbyte g#unsigned
weight2 = readbyte g#unsigned
weight3 = readbyte g#unsigned
weight4 = readbyte g#unsigned
bone1 = readbyte g#unsigned
bone2 = readbyte g#unsigned
bone3 = readbyte g#unsigned
bone4 = readbyte g#unsigned
nz = ReadBEfloat g
tu = ReadBEHalfFloat g * 2
tv = ReadBEHalfFloat g * -2
unk24 = ReadBEfloat g
unk24 = ReadBEfloat g   
unk24 = ReadBEfloat g
unk24 = ReadBEfloat g   
unk24 = ReadBEfloat g

)


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

if(maxweight != 0) then
   (
      if(weight1 != 0) then
      (
         w1 = weight1 as float
         append w.boneids (bone1 + 2)
         append w.weights (w1 / 100)
         append used_id_array (bone1)
      )
      if(weight2 != 0) then
      (
         w2 = weight2 as float
         append w.boneids (bone2 + 2)
         append w.weights (w2 / 100)
         append used_id_array (bone2 )
      )
      if(weight3 != 0) then
      (
         w3 = weight3 as float
         append w.boneids (bone3 + 2)
         append w.weights (w3 / 100)
         append used_id_array (bone3)
      )
      if(weight4 != 0) then
      (
         w4 = weight4 as float
         append w.boneids (bone4 + 2)
         append w.weights (w4 / 100)
         append used_id_array (bone4)
      )      
   )   
append Weight_array w
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name = Mesh_Name_array[a]
msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
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

for i = 1 to Weight_array.count do (
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
)
actionMan.executeAction 0 "63508"  -- Views: Standard Display with Maps

fclose f
fclose g


```


if you have problems please tell me the file name
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-24T05:20:04+00:00
- Post Title: NIER Xbox360

hi, chrrox, what about skeleton and textures?
## Post #3
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2010-12-24T11:10:50+00:00
- Post Title: NIER Xbox360

I am a noobie, How come use this script?
Plis!!!!!!!!
## Post #4
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2010-12-24T11:27:46+00:00
- Post Title: NIER Xbox360

Thanks Chrrox for your work,
I was waiting for this  

P.s. for Logan
It's a MAXScript
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-24T12:38:07+00:00
- Post Title: NIER Xbox360

Textures are swizzled with the standard xbox swizzle i am working on a way to mass convert them.

please let me know what files give trouble and ill fix it.
[04  1024x1024 DXT1.jpg](https://xentaxbackup.github.io/file/3713_04  1024x1024 DXT1.jpg)
## Post #6
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-12-24T13:53:41+00:00
- Post Title: NIER Xbox360

Wow that was awesome
Oh yeah chrrox by any chance can you make a model extractor for guilty gear 2 overture x360
Cause the game got a lot of good model
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-24T14:02:01+00:00
- Post Title: NIER Xbox360

You would need to start a new topic and post samples if you want help on a model format.
Stages also work now.
[nier2.png](https://xentaxbackup.github.io/file/3714_nier2.png)
## Post #8
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2010-12-24T19:31:40+00:00
- Post Title: NIER Xbox360

Some .mdp file can't be decompress, it's normal?
Like bookb011
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-24T20:46:48+00:00
- Post Title: NIER Xbox360

Once I finish up the script ill fix it for 2011. 2011 is very picky and hates text that is commented out and spaces.
I am very close 
[nierbones.png](https://xentaxbackup.github.io/file/3716_nierbones.png)
## Post #10
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2010-12-24T21:03:17+00:00
- Post Title: NIER Xbox360

I feel so stupid, i was trying a undecompress mdp file........

Your script work like a charm in 3DS max 2011
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-24T22:28:01+00:00
- Post Title: NIER Xbox360


## Post #12
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-25T04:23:59+00:00
- Post Title: NIER Xbox360

Here is a script mario made for the textures in max ill make a bms for this  later for speed.
you will need unbundler in the same directory as the main mesh files.
do not ask for that file here.

If anyone can help with bone parent id's or material info that would be great.
[read heap(1).rar](https://xentaxbackup.github.io/file/3717_read heap(1).rar)
## Post #13
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-12-27T12:52:12+00:00
- Post Title: NIER Xbox360

thanks chrrox! 

and here is cpk.bms

layer1.cpk -- 2.93gb

layer2.cpk -- 1.37gb

```
#   derived from cpk_unpack of hcs
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

quickbmsver 0.3.12
endian big
comtype cpk

idstring "CPK "

set query->offset long 0
set query->index long 0
set query->name string "TocOffset"
callfunction query_utf 1
set toc_offset long UTF_VALUE

set query->offset long 0
set query->index long 0
set query->name string "ContentOffset"
callfunction query_utf 1
set content_offset long UTF_VALUE

set query->offset long 0
set query->index long 0
set query->name string "Files"
callfunction query_utf 1
set CpkHeader_count long UTF_VALUE

goto toc_offset
getdstring signature 4
if signature != "TOC "
    print "TOC signature not found"
    cleanexit
endif

set query->offset long toc_offset
set query->index long 0
set query->name string ""
callfunction query_utf 1
set CpkHeader_count long UTF_VALUE
set toc_entries long table_info.rows    # it remains saved after the call

if content_offset < 0           # "if" can't be unsigned
    set add_offset long toc_offset
elif toc_offset < 0
    set add_offset long content_offset
elif content_offset < toc_offset
    set add_offset long content_offset
else
    set add_offset long toc_offset
endif

for mytoc = 0 < toc_entries
    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "DirName"
    callfunction query_utf 1
    set file_name string UTF_VALUE

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "FileName"
    callfunction query_utf 1
    set file_name2 string UTF_VALUE

    string file_name += /
    string file_name += file_name2

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "FileSize"
    callfunction query_utf 1
    set file_size long UTF_VALUE

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "ExtractSize"
    callfunction query_utf 1
    set extract_size long UTF_VALUE

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "FileOffset"
    callfunction query_utf 1
    set file_offset long UTF_VALUE

    math file_offset += add_offset
    if extract_size > file_size
        clog file_name file_offset file_size extract_size
    else
        log file_name file_offset file_size
    endif
next mytoc



startfunction query_utf
    set COLUMN_STORAGE_MASK        long 0xf0
    set COLUMN_STORAGE_PERROW      long 0x50
    set COLUMN_STORAGE_CONSTANT    long 0x30
    set COLUMN_STORAGE_ZERO        long 0x10
    set COLUMN_TYPE_MASK           long 0x0f
    set COLUMN_TYPE_DATA           long 0x0b
    set COLUMN_TYPE_STRING         long 0x0a
    set COLUMN_TYPE_FLOAT          long 0x08
    set COLUMN_TYPE_8BYTE2         long 0x07
    set COLUMN_TYPE_8BYTE          long 0x06
    set COLUMN_TYPE_4BYTE2         long 0x05
    set COLUMN_TYPE_4BYTE          long 0x04
    set COLUMN_TYPE_2BYTE2         long 0x03
    set COLUMN_TYPE_2BYTE          long 0x02
    set COLUMN_TYPE_1BYTE2         long 0x01
    set COLUMN_TYPE_1BYTE          long 0x00

    set UTF_VALUE string ""
    math offset = query->offset
    math offset += 0x10     # needed by the tool
    goto offset

    set table_info.table_offset long offset
    getdstring UTF_signature 4
    if UTF_signature != "@UTF"
        print "not a @UTF table at %offset%"
        cleanexit
    endif
    get table_info.table_size long
    set table_info.schema_offset long 0x20
    get table_info.rows_offset long
    get table_info.string_table_offset long
    get table_info.data_offset long
    get table_name_string long
    get table_info.columns short
    get table_info.row_width short
    get table_info.rows long

    for i = 0 < table_info.columns
        get schema.type byte
        get schema.column_name long
        putarray 0 i schema.type
        putarray 1 i schema.column_name
        putarray 2 i -1     # schema.constant_offset

        math TMP = schema.type
        math TMP &= COLUMN_STORAGE_MASK
        if TMP == COLUMN_STORAGE_CONSTANT
            savepos schema.constant_offset
            putarray 2 i schema.constant_offset

            math TMP = schema.type
            math TMP &= COLUMN_TYPE_MASK
            if TMP == COLUMN_TYPE_STRING
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_DATA
                getdstring DUMMY 8
            elif TMP == COLUMN_TYPE_FLOAT
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_8BYTE2
                getdstring DUMMY 8
            elif TMP == COLUMN_TYPE_8BYTE
                getdstring DUMMY 8
            elif TMP == COLUMN_TYPE_4BYTE2
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_4BYTE
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_2BYTE2
                getdstring DUMMY 2
            elif TMP == COLUMN_TYPE_2BYTE
                getdstring DUMMY 2
            elif TMP == COLUMN_TYPE_1BYTE2
                getdstring DUMMY 1
            elif TMP == COLUMN_TYPE_1BYTE
                getdstring DUMMY 1
            else
                print "unknown type for constant"
                cleanexit
            endif
        endif
    next i

    math TMP = table_info.string_table_offset
    math TMP += 8
    math TMP += offset
    math string_table_size = table_info.data_offset
    math string_table_size -= table_info.string_table_offset
    log MEMORY_FILE TMP string_table_size

    for i = query->index < table_info.rows
        math TMP = i
        math TMP *= table_info.row_width
        math row_offset = table_info.table_offset
        math row_offset += 8
        math row_offset += table_info.rows_offset
        math row_offset += TMP

        for j = 0 < table_info.columns
            getarray type 0 j
            getarray column_name 1 j
            getarray constant_offset 2 j

            if constant_offset >= 0
                math data_offset = constant_offset
            else
                math data_offset = row_offset
            endif

            math TMP = type
            math TMP &= COLUMN_STORAGE_MASK
            if TMP == COLUMN_STORAGE_ZERO
                set value long 0
            else
                goto data_offset
                math TMP = type
                math TMP &= COLUMN_TYPE_MASK
                if TMP == COLUMN_TYPE_STRING
                    get string_offset long
                    goto string_offset MEMORY_FILE
                    get value string MEMORY_FILE
                elif TMP == COLUMN_TYPE_DATA
                    get vardata_offset long
                    get vardata_size long
                    goto vardata_offset MEMORY_FILE
                    getdstring value vardata_size MEMORY_FILE
                elif TMP == COLUMN_TYPE_FLOAT
                    get value long
                elif TMP == COLUMN_TYPE_8BYTE2
                    get DUMMY long  # no 64 bit support!
                    get value long
                elif TMP == COLUMN_TYPE_8BYTE
                    get DUMMY long  # no 64 bit support!
                    get value long
                elif TMP == COLUMN_TYPE_4BYTE2
                    get value long
                elif TMP == COLUMN_TYPE_4BYTE
                    get value long
                elif TMP == COLUMN_TYPE_2BYTE2
                    get value short
                elif TMP == COLUMN_TYPE_2BYTE
                    get value short
                elif TMP == COLUMN_TYPE_1BYTE2
                    get value byte
                elif TMP == COLUMN_TYPE_1BYTE
                    get value byte
                else
                    print "unknown normal type"
                    cleanexit
                endif

                if constant_offset < 0
                    savepos row_offset  # row_offset += bytes_read
                endif
            endif

            goto column_name MEMORY_FILE
            get column_name string MEMORY_FILE
            if column_name == query->name
                set UTF_VALUE string value  # result.value.value (qthis)
                math i = table_info.rows    # break
                math j = table_info.columns # break
            endif
        next j
    next i
endfunction


```
## Post #14
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-12-27T16:22:00+00:00
- Post Title: NIER Xbox360

This program can convert xpr to dds.
[Tecmo Texture Extractor.7z](https://xentaxbackup.github.io/file/3725_Tecmo Texture Extractor.7z)
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-27T17:50:06+00:00
- Post Title: NIER Xbox360

does that really work? DOA used tpr, which was different then a normal xpr
## Post #16
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-12-28T05:20:00+00:00
- Post Title: Re: NIER Xbox360

> Reply from mariokart64n
>
> does that really work? DOA used tpr, which was different then a normal xpr
Yes, it works ok
but it doesnt make a normal map. Only for diffuse.

Sorry, I didn't notice that
## Post #17
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2010-12-28T16:29:08+00:00
- Post Title: Re: NIER Xbox360

HI! I need help with this files: [viewtopic.php?f=10&t=5549](http://forum.xentax.com/viewtopic.php?f=10&t=5549)

Thanks!!
## Post #18
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2010-12-28T20:10:45+00:00
- Post Title: Re: NIER Xbox360

I get this error after I select a .mdv file ... 

```

```
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-28T20:19:05+00:00
- Post Title: Re: NIER Xbox360

make sure you decompress the file with the bms first
## Post #20
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2010-12-28T20:31:36+00:00
- Post Title: Re: NIER Xbox360

I get this one now by using bms script you posted for .MDV files, works for .MDP 

```
Error: Not enough space

```


Updated quickbms also "QuickBMS generic files extractor 0.4.7 (quickbms)"
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-28T20:53:30+00:00
- Post Title: Re: NIER Xbox360

are you decompressing the right file?

theres 2 files, only ones compressed. that error might be from you trying to decompress the wrong file or a file that has already been decompressed.

that or you ran out of space, and you need to buy a new HD O_O
## Post #22
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2010-12-28T22:24:56+00:00
- Post Title: Re: NIER Xbox360

Well guess im trying the right file   

bms script + KAINE010.MDP I get the decompressed file .dec 
bms script + KAINE010.MDV I get that error ^ 

There's enough space   like 177gb on this HDD

files that i try are from layer1/CHARA/
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-28T22:43:01+00:00
- Post Title: Re: NIER Xbox360

what version of max what is the error you get what is the file you are importing
## Post #24
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2010-12-28T22:56:31+00:00
- Post Title: Re: NIER Xbox360

3DS Max 2010 x64 

Getting this error 



Tryied alot of different files, same thing, the files from /BG/ doesn't load, 3DSMax just goes not responding after a while.

Edit: 

I get this trying the bms script on KAINE020.MDV 

> Error: the compressed LZO input is wrong or incomplete (-4)
>
> 
>
> Error: there is an error with the decompression
>
>        the returned output size is negative (-1)
>
> 
>
> Press RETURN to quit

Edit2:

Tryied to import KAINE020.MDV now, but now MAX goes not responding with a message in the bottom left corner "This is the offset 0xf2aa"

Edit3: 

Loaded after a while, and this error showed up, only bones showing.



Edit4: Managed to load the mesh, textures should load auto or ?

Edit5: Fixed everything, thanks for ya replies guys
## Post #25
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-28T23:52:05+00:00
- Post Title: Re: NIER Xbox360

ah i updated my script but forgot to upload the update here this will fix that mesh.
Th script should be faster now I increased the heap size.
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-07T02:43:31+00:00
- Post Title: Re: NIER Xbox360

Ok, so please tell me what bms script i need to use for decompress mdv files, and how to get textures?

i'm trying all things in this thread.

ADD:
So first, i need unbundler!

ADD2:
Ok, so

1 - i unpacked *.cpk using cpk_unpacker.bms from epopoe
2 - i'm trying to decompress AMA010.MDV from "\media\layer1_cpk\CHARA\AMA010", but i can not, i don't know what bms need to using
3 - convert textures...
## Post #27
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-01-07T07:47:08+00:00
- Post Title: Re: NIER Xbox360

Here's how I managed to import the model in 3DSMax

Unpacked the .cpk files ofc 

I'm using this BMS script to uncompress the files, but how I said doesn't work on .MDV files  so I tried on .MDP files and works 

```
get name FILENAME
string name + ".dec"
get lzo long
get version long
get subversion long
get files long
get TotalUncompSize long
get unk long
goto 0x20
comtype LZO1X
for i = 1 to files
get memoffset long
get size long
get zsize long
savepos offset
if size == zsize
append
log MEMORY_FILE offset zsize
append
else
append
clog MEMORY_FILE offset zsize size
append
endif
math offset + zsize
goto offset
Padding 0x10000
next i
log NAME 0 TotalUncompSize MEMORY_FILE

```


Export the textures with this lil script [viewtopic.php?p=46423#p46423](http://forum.xentax.com/viewtopic.php?p=46423#p46423) select the MDP file when the "Select File" prompts 

Convert them to .DDS with this one [viewtopic.php?p=46515#p46515](http://forum.xentax.com/viewtopic.php?p=46515#p46515) Just put the exe in the same folder as the .xpr texture files and open it, it'll convert them auto

After that import the model using the script posted by chroxx in the 1st post, Sometimes I get some errors, but after a 2nd try or 3rd i gets imported, non textured ... 

Maybe this is not the right way to do it but that's how I managed to import the character in 3DSMax, exporting it in .FBX or .OBJ would result in a low poly model ... dunno why
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-07T18:14:35+00:00
- Post Title: Re: NIER Xbox360

You need to activate the textures in the viewport to see them click this button.
[max.png](https://xentaxbackup.github.io/file/3781_max.png)
## Post #29
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-10T01:50:57+00:00
- Post Title: Re: NIER Xbox360

CMihai
Thanks, i'm decompressed *.mdp and loaded *.mdv model in 3ds max with bones successfully, but this

> Reply from CMihai
>
> 
Export the textures with this lil script viewtopic.php?p=46423#p46423 select the MDP file when the "Select File" prompts
don't work for me. Maybe i'm doing something wrong?

ADD:
ok, i'm tried other files and they work fine, it seems that some models without textures, but where we can get textures, for example for AMA010.MDV?

ADD2:
i have a problem with NIER012.MDV
> -- Runtime error: Bone index out of range 201
ms script line: 232

so it won't loading all bones i supposed and i can't see any loaded (yes, some objects and bones loaded in max) objects in 3ds max viewport.

ADD3:
problem with extracting *.mdp files from BG folder, almost every time unbundler.exe gives error (just crashing), hope Mario see this..
## Post #30
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-25T18:29:48+00:00
- Post Title: Re: NIER Xbox360

chrrox and mariokart64n scripts for 3ds max translate in python importer for blender249
[import-nier-2011-06-25.zip](https://xentaxbackup.github.io/file/4375_import-nier-2011-06-25.zip)
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-23T04:11:00+00:00
- Post Title: Re: NIER Xbox360

Absolutly amazing this resume all the steeps need to fix the swizled textures also?.
## Post #32
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-23T11:15:47+00:00
- Post Title: Re: NIER Xbox360

I am a bit lost again.
I only have layer1.cpk and layer2.cpk to extract files from. But if I use the script I obtain a bunch of files with .2DP and .2DV extensions in a folder called 2D (so not 3D at all)... is my copy corrupt and something is missing?

EDIT: Allright, for some reason it didn't extracted the CHARA folder. I did it again and this time the folder appears. But what about the texture extractor? I should I use it?
## Post #33
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-09-23T20:55:43+00:00
- Post Title: Re: NIER Xbox360

Hey,

sorry for posting in this damn old topic again but... does anyone here still have a version of the script that works with the sceneries? The one in the first post crashes on them and the blender one imports the wrong UV channel ><
## Post #34
- Username: NeahNEET
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 09, 2015 10:26 pm
- Post datetime: 2015-06-10T16:44:48+00:00
- Post Title: Re: NIER Xbox360

Hi there!
Sorry for posting in this old topic but if someone can help me...
In Max 2016 x64 script for import .mdv works perfect. Meshes and bones works fine.
But script for textures don't work for me. I have UnBundler in the same directory as the main mesh files but I get an empty files with the correct names. Like for KAINE010.MDV it creates NIER00_KAINE010_ALL_001_A_psd.xpr, NIER00_KAINE010_ALL_001_C_psd.xpr, NIER00_KAINE010_ALL_001_N_psd.xpr, etc. But zero bytes.
