## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-06-22T08:04:58+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Hi guys I need some help importing the weight data back into the game. Some background:

I have coded an application which can export and import data into the yukes model format (yobj). I am exporting and importing using the wavefront model format and am limited to importing the uv's and verts. 

With the pc version of the game I am having issues with editing the heads of the models. Any changes causes the head to get corrupted in game as follows:



If I disable the facial animations it looks fine in game but the models have no expressions:



I am assuming that the issue is with the weights?

I took a look the weights of the model when imported with brienj's import script but it seems like the weights are not being imported correctly into 3ds max. 

I then looked at chrrox's script in this thread [viewtopic.php?f=16&t=6183&hilit=Rumble+Roses](http://forum.xentax.com/viewtopic.php?f=16&t=6183&hilit=Rumble+Roses) 
and rewrote parts of it to read the new model format. After making the modifications, the xbox 360 models are imported with the correct weights. 

The new PC models have up to 7 bones assigned to each vert whereas the old format had a maximum of 4 bones per vert. I have modified the script to add the additional bones but it crashes when trying to load the newer models with the error: Exceeded the vertex countSkin:Skin

I am not an expert in max script as I code in C#, if someone can help me with the script it would be appreciated. 


The modified script looks like this:

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \
caption:"WWE2012 upwards Model File" \
types:"WWEModel File(*.yobj)|*.yobj" \
historyCategory:"WWE Object Presets"
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
Unk999 = ReadBElong f
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
--scale1 = ReadBEfloat f
scale1 = 10
VertOff = ReadBElong f + 8
print VertOff
fseek f VertOff#seek_set	
--print scale1
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
Bone5 = -1
Bone6 = -1
Bone7 = -1
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


if Mesh_Info_Arr[a].WeightCount == 5 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f 
   
)

if Mesh_Info_Arr[a].WeightCount == 6 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f  
Bone6 = readbyte f
fseek f 0x3#seek_cur
Weight6 = readfloat f     
)


if Mesh_Info_Arr[a].WeightCount == 7 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f  
Bone6 = readbyte f
fseek f 0x3#seek_cur
Weight6 = readfloat f   
Bone7 = readbyte f
fseek f 0x3#seek_cur
Weight7 = readfloat f   
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
if(Bone5 != -1) then
   maxweight = maxweight + weight5
if(Bone6 != -1) then
   maxweight = maxweight + weight6
if(Bone7 != -1) then
   maxweight = maxweight + weight7
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
	if(Bone5 != -1) then (
         w5 = weight5 as float
         append w.boneids (bone5 + 1)
         append w.weights w5
      )    
	if(Bone6 != -1) then (
         w6 = weight6 as float
         append w.boneids (bone6 + 1)
         append w.weights w6
      )    
	if(Bone7 != -1) then (
         w7 = weight7 as float
         append w.boneids (bone7 + 1)
         append w.weights w7
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
print     "skinOps.getNumberVertices"
format "vCnt skinMod %\n" (skinOps.getNumberVertices skinMod)
for i = 1 to Used_Bone_array.count do
(
   maxbone = BNArr[(Used_Bone_array[i])]
   if i != Used_Bone_array.count then
      skinOps.addBone skinMod maxbone 0
   else
      skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod
print "weight array count"
print Weight_array.count
for i = 1 to Weight_array.count do
(
   w = Weight_array[i]
   bi = #()
   wv = #()
	print "bone id's count"
	print w.boneids.count
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


As I've said, the script works for the xbox 360 models but not the pc models. Here are two models to test: [http://www69.zippyshare.com/v/VWtwuiha/file.html](http://www69.zippyshare.com/v/VWtwuiha/file.html)



Secondly, what is the easiest way to export the weight data from 3ds max. The yobj files have the weight data in the format: 

boneId weight, etc

I am looking into the collada model format but it doesn't seem to contain the weight data in this format.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-23T00:53:48+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

usedID = ReadBElong f
is zero for the PC model, so Used_Bone_array is empty and no skin is built
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-06-23T09:09:29+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Ok thanks for the reply. I've checked the model file and you are right there are no references to which bones are assigned to the faces in the header. I am assuming that this is due to the fact that the pc version has many more bones and the header does not have space for more bones. 

I've looked through the pc model file and can't seem to find the bone assignments anywhere else.
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-06-26T11:58:27+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

I've rewritten the script to read the bone values directly from the weight assignments. I assume that the pc model format assigns the bones in this manner, however I'm not sure. The script works fine for the first object in the model i.e. the head but gives me an error on the subsequent objects, not sure what's wrong. 

Here's the updated script:

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"
clearlistener()
fname = getOpenFileName \
caption:"WWE2012 upwards Model File" \
types:"WWEModel File(*.yobj)|*.yobj" \
historyCategory:"WWE Object Presets"
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
              )
if isvalidnode (getNodeByName Barr[a]) == true then (
newBone = getNodeByName Barr[a]
)
if (Parr[a] != -1) then
newBone.parent = BNArr[(Parr[a] + 1)]
append BNArr newBone

)
format "BoneCount % \n" BoneCount
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
Unk999 = ReadBElong f
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
--for a = 1 to 1 Do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
UsedBonesPCArray = #()

fseek f Mesh_Info_Arr[a].VertOff#seek_set
--scale1 = ReadBEfloat f
scale1 = 10
VertOff = ReadBElong f + 8
print VertOff
fseek f VertOff#seek_set	
--print scale1
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
Bone5 = -1
Bone6 = -1
Bone7 = -1
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


if Mesh_Info_Arr[a].WeightCount == 5 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f 
   
)

if Mesh_Info_Arr[a].WeightCount == 6 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f  
Bone6 = readbyte f
fseek f 0x3#seek_cur
Weight6 = readfloat f     
)


if Mesh_Info_Arr[a].WeightCount == 7 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f  
Bone6 = readbyte f
fseek f 0x3#seek_cur
Weight6 = readfloat f   
Bone7 = readbyte f
fseek f 0x3#seek_cur
Weight7 = readfloat f   
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
if(Bone5 != -1) then
   maxweight = maxweight + weight5
if(Bone6 != -1) then
   maxweight = maxweight + weight6
if(Bone7 != -1) then
   maxweight = maxweight + weight7
if(maxweight != 0) then (
      if(Bone1 != -1  ) then (
         w1 = weight1 as float
         append w.boneids (bone1 + 1)
         append w.weights w1
		 if (bone1 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone1 + 1)
		)
      )
      if(Bone2 != -1 ) then (
         w2 = weight2 as float
         append w.boneids (bone2 + 1)
         append w.weights w2
		if (bone2 + 1 > -1) then
		(  
	  appendIfUnique UsedBonesPCArray (bone2 + 1)
		) 
      )
      if(Bone3 != -1) then (
         w3 = weight3 as float
         append w.boneids (bone3 + 1)
         append w.weights w3
		   if (bone3 + 1 > -1) then
		(
	  appendIfUnique UsedBonesPCArray (bone3 + 1)
		) 
      )
      if(Bone4 != -1 ) then (
         w4 = weight4 as float
         append w.boneids (bone4 + 1)
         append w.weights w4
		if (bone4 + 1 > -1) then
		(   
	  appendIfUnique UsedBonesPCArray (bone4 + 1)
		) 
      )  
	if(Bone5 != -1)  then (
         w5 = weight5 as float
         append w.boneids (bone5 + 1)
         append w.weights w5
		 if (bone5 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone5 + 1)
		)
      )    
	if(Bone6 != -1 ) then (
         w6 = weight6 as float
         append w.boneids (bone6 + 1)
         append w.weights w6
		 if (bone6 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone6 + 1)
		)
      )    
	if(Bone7 != -1  ) then (
         w7 = weight7 as float
         append w.boneids (bone7 + 1)
         append w.weights w7
		if (bone7 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone7 + 1)
		)
		  
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
print     "skinOps.getNumberVertices"
format "vCnt skinMod %\n" (skinOps.getNumberVertices skinMod)
if Used_Bone_array.count != 0 then
	(
		for i = 1 to Used_Bone_array.count do
		(
		   maxbone = BNArr[(Used_Bone_array[i])]
		   if i != Used_Bone_array.count then
			  skinOps.addBone skinMod maxbone 0
		   else
			  skinOps.addBone skinMod maxbone 1
		)
	)
else
	(
		for i = 1 to UsedBonesPCArray.count do
		(
			format "boneid % \n" UsedBonesPCArray[i]
		   maxbone = BNArr[(UsedBonesPCArray[i])]
		   if i != UsedBonesPCArray.count then
			  skinOps.addBone skinMod maxbone 0
		   else
			  skinOps.addBone skinMod maxbone 1
		)
	)
modPanel.setCurrentObject skinMod
print "weight array count"
print Weight_array.count
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
## Post #5
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-07-04T02:44:30+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Hm, you sure it's not using morphers?
## Post #6
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-10-20T11:37:24+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

^I'm not sure what you mean. 

Here's the final script, it seems to work on most models:

```
-- Edited by tekken57 for importing of newer models
if (heapSize < 200000) then
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"
clearlistener()
fname = getOpenFileName \
caption:"WWE2012 upwards Model File" \
types:"WWEModel File(*.yobj)|*.yobj" \
historyCategory:"WWE Object Presets"
f = fopen fname "rb"

fn vToC valueVal = --accepts a point3 value, returns an equivalent color value
(
return [(valueVal.x*255 as integer), (valueVal.y*255 as integer), (valueVal.z*255 as integer)] as color
)
fn cToV colorVal = --accepts a color value, returns an equivalent point3 value
(
tempVal = colorVal as point3
return [(tempVal.x/255), (tempVal.y/255), (tempVal.z/255)]

)

fn RGBtoFPC clrRGB = (color (clrRGB.r/255) (clrRGB.g/255) (clrRGB.b/255))
fn FPCtoRGB clrFPC = (color (clrFPC.r*255) (clrFPC.g*255) (clrFPC.b*255))

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
              )
if isvalidnode (getNodeByName Barr[a]) == true then (
newBone = getNodeByName Barr[a]
)
if (Parr[a] != -1) then
newBone.parent = BNArr[(Parr[a] + 1)]
append BNArr newBone

)
format "BoneCount % \n" BoneCount
struct Mesh_Info_Struct
(
   Objname,VertOff,WeightOff,UVOff,MatPCount,matPOff,FaceOff,FaceSec,VertCount,WeightCount,BtableStart,  VertColorOff
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
VertColorOff = ReadBElong f + 8
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
append Mesh_Info_Arr (Mesh_Info_Struct Objname:Objname VertOff:VertOff WeightOff:WeightOff UVOff:UVOff MatPCount:MatPCount matPOff:matPOff FaceOff:FaceOff FaceSec:FaceSec VertCount:VertCount WeightCount:WeightCount BtableStart:BtableStart  VertColorOff:VertColorOff)
)
--print Mesh_Info_Arr
for a = 1 to MeshCount Do (
--for a = 1 to 1 Do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
UsedBonesPCArray = #()
VertexColor_array = #()

fseek f Mesh_Info_Arr[a].VertOff#seek_set
--scale1 = ReadBEfloat f
scale1 = 10
VertOff = ReadBElong f + 8
--print VertOff
fseek f VertOff#seek_set	
--print scale1
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
--fseek f 0x10#seek_cur
append Vert_array [vx,vy,vz]
nx = ReadBEfloat f  --read xyz coordinates
ny = ReadBEfloat f
nz = ReadBEfloat f
unk4444 = ReadBEfloat f
append Normal_array [nx,ny,nz]	
)

fseek f Mesh_Info_Arr[a].UVOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
tu = ReadBEfloat f
tv = ReadBEfloat f * -1
append UV_array [tu,tv,0]
)


--format  "vertcolor offset %\n" Mesh_Info_Arr[a].VertColorOff
fseek f Mesh_Info_Arr[a].VertColorOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
vcx = ReadBEfloat f
vcy = ReadBEfloat f 
vcz = ReadBEfloat f 	
append VertexColor_array  [vcx,vcy,vcz]
--format "vc % % %\n" vcx vcy vcz
)

fseek f Mesh_Info_Arr[a].WeightOff#seek_set
for b = 1 to Mesh_Info_Arr[a].VertCount Do (
Bone1 = -1
Bone2 = -1
Bone3 = -1
Bone4 = -1
Bone5 = -1
Bone6 = -1
Bone7 = -1
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


if Mesh_Info_Arr[a].WeightCount == 5 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f 
   
)

if Mesh_Info_Arr[a].WeightCount == 6 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f  
Bone6 = readbyte f
fseek f 0x3#seek_cur
Weight6 = readfloat f     
)


if Mesh_Info_Arr[a].WeightCount == 7 do (
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
Bone5 = readbyte f
fseek f 0x3#seek_cur
Weight5 = readfloat f  
Bone6 = readbyte f
fseek f 0x3#seek_cur
Weight6 = readfloat f   
Bone7 = readbyte f
fseek f 0x3#seek_cur
Weight7 = readfloat f   
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
if(Bone5 != -1) then
   maxweight = maxweight + weight5
if(Bone6 != -1) then
   maxweight = maxweight + weight6
if(Bone7 != -1) then
   maxweight = maxweight + weight7
if(maxweight != 0) then (
      if(Bone1 > -1  ) then (
         w1 = weight1 as float
         append w.boneids (bone1 + 1)
         append w.weights w1
		 if (bone1 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone1 + 1)
		)
      )
      if(Bone2 > -1 ) then (
         w2 = weight2 as float
         append w.boneids (bone2 + 1)
         append w.weights w2
		if (bone2 + 1 > -1) then
		(  
	  appendIfUnique UsedBonesPCArray (bone2 + 1)
		) 
      )
      if(Bone3 > -1) then (
         w3 = weight3 as float
         append w.boneids (bone3 + 1)
         append w.weights w3
		   if (bone3 + 1 > -1) then
		(
	  appendIfUnique UsedBonesPCArray (bone3 + 1)
		) 
      )
      if(Bone4 > -1 ) then (
         w4 = weight4 as float
         append w.boneids (bone4 + 1)
         append w.weights w4
		if (bone4 + 1 > -1) then
		(   
	  appendIfUnique UsedBonesPCArray (bone4 + 1)
		) 
      )  
	if(Bone5 > -1)  then (
         w5 = weight5 as float
         append w.boneids (bone5 + 1)
         append w.weights w5
		 if (bone5 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone5 + 1)
		)
      )    
	if(Bone6 > -1 ) then (
         w6 = weight6 as float
         append w.boneids (bone6 + 1)
         append w.weights w6
		 if (bone6 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone6 + 1)
		)
      )    
	if(Bone7 > -1  ) then (
         w7 = weight7 as float
         append w.boneids (bone7 + 1)
         append w.weights w7
		if (bone7 + 1 > -1) then
		(
		appendIfUnique UsedBonesPCArray (bone7 + 1)
		)
		  
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

msh = mesh vertices:Vert_array faces:Face_array  normals:Normal_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
--msh.material = meditMaterials[1].materialList[(MatSlotTexID[a])]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

setNumCPVVerts msh UV_array.count 
defaultVCFaces msh

for j = 1 to VertexColor_array.count do
(	
	vertColor = VertexColor_array[j] as point3
	convertedColor = vToC (vertColor) as color
	--convertedColor = vertColor as color
	format "convertedColor %\n" convertedColor
	setvertcolor msh j convertedColor
)

max modify mode
select msh
skinMod = skin ()
addModifier msh skinMod
print     "skinOps.getNumberVertices"
format "vCnt skinMod %\n" (skinOps.getNumberVertices skinMod)
if Used_Bone_array.count != 0 then
	(
		for i = 1 to Used_Bone_array.count do
		(
		   maxbone = BNArr[(Used_Bone_array[i])]
		   if i != Used_Bone_array.count then
			  skinOps.addBone skinMod maxbone 0
		   else
			  skinOps.addBone skinMod maxbone 1
		)
	)
else
	(
		for i = 1 to UsedBonesPCArray.count do
		(
			--format "bone array % \n" UsedBonesPCArray[i]
			--format "boneid % \n" UsedBonesPCArray[i]
		   --maxbone = BNArr[(UsedBonesPCArray[i])]
			maxbone = BNArr[(UsedBonesPCArray[i])]
		   if i != UsedBonesPCArray.count then
			  skinOps.addBone skinMod maxbone 0
		   else
			  skinOps.addBone skinMod maxbone 1
		)
	)
modPanel.setCurrentObject skinMod
print "weight array count"
print Weight_array.count
for i = 1 to Weight_array.count do
(
   w = Weight_array[i]
   bi = #()
   wv = #()	
   for j = 1 to w.boneids.count do
   (
	   --format "boneId % index % \n " w.boneids[j] (findItem UsedBonesPCArray w.boneids[j])
	   if Used_Bone_array.count != 0 then
	   (
		    boneid = w.boneids[j]
	   )
	   else
	   (
		    boneid = findItem UsedBonesPCArray w.boneids[j]
	   )
     
      weight = w.weights[j]
	 	   
      append bi boneid
      append wv weight
	--format "boneId % weight % \n "	boneid weight
   ) 

  skinOps.ReplaceVertexWeights skinMod i bi wv
)
max create mode
)

fclose f

```
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-10-20T11:48:35+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Now that I have the importer working. I need some help exporting the data back into the model. I have modified chorrox's script to import the models into 3dsmax above and have written c# code to import edits to the model in wavefront format.

I can import the verts, uv's and weights but the problem is that the face format is different and I don't know how to export the faces back to the original value. The ability to import faces will allow me to code an importer to import any mesh back into the game.

I have compiled an excel sheet with the list of face values as is in the model as well as the face values created with the import script.You will see that the 3dsmax import script changes the face format. I am attaching the model, the excel sheet and the import script. I would appreciate any help you can render.

[http://www60.zippyshare.com/v/z3sMGhYO/file.html](http://www60.zippyshare.com/v/z3sMGhYO/file.html)

To elaborate, the original model has data in the following format:

```
377
374
374
2002
2002
990
535
534
536
537
376
375
374
375
378
379
1082
772
1079
1078
1077
768
765
767
766
766
1101
1101

```


The exported file from 3dsmax has data in this format:

```
2002	990	535
990	534	535
535	534	536
534	537	536
536	537	376
537	375	376
376	375	374
374	375	378
375	379	378
378	379	1082
379	772	1082
1082	772	1079
772	1078	1079
1079	1078	1077
1078	768	1077
1077	768	765
768	767	765
765	767	766
1101	765	766
1100	1098	1101
1101	1098	765
1098	763	765
765	763	1077
763	1080	1077
1077	1080	1079
1080	774	1079
1079	774	1082
378	1082	1081
1082	774	1081
1081	774	775
775	774	773
774	1080	773
773	1080	764
1080	763	764

```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-22T19:51:45+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

looks like you'll need a reverse tristrips algorithm.
vertices:
A
B
C
D
E
F

triangles:
(1)ABC
(2)..BCD
(3)....CDE
(4)......DEF

So you start backwards from (4) F,E,D
take C from (3), B from (2) and A from (1)

That is reverse A,B,C,D,E,F

HTH

your example is a little bit harder:

```
2002 990 535
     990 535 534 <
         535 534 536
             534 536 537 <
```

where '<' marks the triangles where the last two vertices are swapped

results in 537, 536,534,535,990,2002,374,377,376 (taking the columned values once only)
which must be written down backwards (376,377,374,...)

but dunno how to double 2002 and 374
(chrrox or MrAdults may have a math theory for such  )
## Post #9
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-10-26T12:47:26+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Thanks for the reply. I've never heard of triangle strips before and have read up on the subject after you mentioned it. 

By examining the entire series of values using the tri strips method, it appears that the repetition of values occurs every 20 values if I look at the values starting at the last face and comparing this to the values in the games model backwards. 

The problem is that the repetition also randomly occurs in less than 20 values on a few occasions, then it reverts back to the 20 values pattern.  I can't seem to spot a pattern which I can code an algorithm for.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-27T07:32:40+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

btw "20": I was told you've tried to sell chrrox' script for $20.
Is that true?
(Be informed that I'm not supporting such behavior.)
## Post #11
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2015-10-27T13:10:51+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

No I haven't sold the chorrox script at all. I posted the script I edited as a ms file and in plain text. I fully credited chorrox for the original script. If it is an issue for me to repost the script, let me know and I'll remove it. 

With regards to the repeating bytes, I did some reading on the creation of triangle strips and the values are repeated when two triangles need to be joined and there are no vertices in common. 

I've spent most of the day coding a script to retrieve the values but it seems like there are many more rules which are applied to the faces. There are even some values which are repeated 3 times in the series. The values are fairly close but I am missing some values still. 

The byte swap for the x and y values also changes randomly during the series, I've read up on backface culling, not sure if this has anything to do with us.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-27T15:08:53+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

> Reply from plodtrew
>
> I fully credited chorrox for the original script. If it is an issue for me to repost the script, let me know and I'll remove it.It's not forbidden to improve other people's scripts and repost them.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-01-16T13:27:30+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Here's maxscript to import WWE 2k15 PC version models with correct in-game rig. All credits goes to Chrrox, I just edited script a bit!

P.S. Script is slow, prepare for some waiting xD
[WWE_2k15.7z](https://xentaxbackup.github.io/file/10318_WWE_2k15.7z)
## Post #14
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2016-01-20T08:00:52+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

> Reply from zaramot
>
> Here's maxscript to import WWE 2k15 PC version models with correct in-game rig. All credits goes to Chrrox, I just edited script a bit!

P.S. Script is slow, prepare for some waiting xD

Thank you~Do you known how to extract the models from the game file？
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-01-20T09:40:23+00:00
- Post Title: WWE 2k15 PC models - need help exporting face data

Sure, you can extract .pacs with (WWE 2K15 Pac Extractor/Injector (V 0.7)) I can't attach it here, because it was posted on other resource. Though, you can easily find it with google - "wwe 2k15 pc pac extractor"
## Post #16
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-06-12T00:47:05+00:00
- Post Title: Re: WWE 2k15 PC models - need help exporting face data

> Reply from zaramot
>
> Here's maxscript to import WWE 2k15 PC version models with correct in-game rig. All credits goes to Chrrox, I just edited script a bit!

P.S. Script is slow, prepare for some waiting xD

Just wondering... I know scripts are posted "as is" but does this support weights and not just rigging?
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-06-12T07:43:39+00:00
- Post Title: Re: WWE 2k15 PC models - need help exporting face data

Yes, it's supports weights
## Post #18
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-06-12T08:17:30+00:00
- Post Title: Re: WWE 2k15 PC models - need help exporting face data

Do I need to "enable" the weights? I tried this with WWE 2k16 all it imported are solid "vector" weights (none for any of the bones). The very first script posted though exported the weights but with a few bugs.
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-06-12T09:04:08+00:00
- Post Title: Re: WWE 2k15 PC models - need help exporting face data

Well, have no idea about WWE2k16 (I extracted xbox-360 version of WWE2k16, not PC and for xbox-360 version this script will not work), if you send me sample I could fix error, I guess.
## Post #20
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-06-12T10:15:04+00:00
- Post Title: Re: WWE 2k15 PC models - need help exporting face data

> Reply from zaramot
>
> Well, have no idea about WWE2k16 (I extracted xbox-360 version of WWE2k16, not PC and for xbox-360 version this script will not work), if you send me sample I could fix error, I guess. [Awesome... here's a few samples](https://www.dropbox.com/s/kk0vp2ej5rlxbhf/wwe2k16_arnie.7z?dl=0)
