## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-13T11:11:10+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Hello guys, well after a lot hours I finish download this really cool game, ok the format of files is .tbl2 like Argo,etc, ok with script of chrox for ARGO ONLINE we can unpack this files, so well here I upload some shots, ok thanks a lot for support CHROX and others members of this great community.

Web: [Warbane Online](http://warbane.mgame.com)
Client: [Warbane Online Client Download](http://warbane.mgame.com/data/?rtype=D)

Quickbms Script for Unpack TBL2

```
#WarBane Rising of Darkness
#from chrrox

open FDDE tbl2 1
set arcnum 0


goto 0x10001C 1

for i = 0
    get offset long 1
    get zsize long 1
    get null3 long 1
    get size long 1
    get arcnum long 1
    print "%arcnum%"
        set NAME1 string "file0"
    set MYEXT string arcnum
    strlen MYEXTSZ MYEXT
    if MYEXTSZ == 1
        string NAME1 += "00"
    endif
    if MYEXTSZ == 2
        string name1 - 1
        string NAME1 += "0"
    endif
    if MYEXTSZ == 3
        string name1 - 1
        string NAME1 += ""
    endif
    string NAME1 += MYEXT
    string NAME1 += .data2
    open FDSE NAME1 0


    get null1 long 1
    get null2 long 1

    get name string 1
    Padding 4 1

    get null long 1
if zsize == size
        log name offset zsize
else
clog name offset zsize size
endif
next i
```


3D Max Importer

```
	heapSize = 200000000

fname = getOpenFileName \
caption:"Argo Online Model File" \
types:"Argo Online Model File(*.xac)|*.xac" \
historyCategory:"Argo Online Object Presets"
f = fopen fname "rb"

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
struct weight_data
(
	boneids,weights
)
struct weight_data2
(
	weightid,wcount
)
total_size = getFileSize fname
print total_size
idstring = readlong f
id1 = readbyte f#unsigned
id2 = readbyte f#unsigned
id3 = readbyte f#unsigned
id4 = readbyte f#unsigned
Type_0_offset_array =#()
Type_1_offset_array =#()
Type_2_offset_array =#()
Type_3_offset_array =#()
Type_3_2_offset_array =#()
Type_4_offset_array =#()
Type_5_offset_array =#()
Type_6_offset_array =#()
Type_7_offset_array =#()
Mesh_Name_array =#()
while (ftell f) != total_size do (
type = readlong f
size = readlong f
type2 = readlong f
if type == 0 do (

append Type_0_offset_array (ftell f)

)
if type == 1 do (
append Type_1_offset_array (ftell f)
)
if type == 2 do (
append Type_2_offset_array (ftell f)
)
if type == 3 do (
if type2 == 2 do (
append Type_3_offset_array (ftell f)
)
if type2 == 10000 do (
append Type_3_offset_array (ftell f)
)
)
if type == 4 do (
append Type_4_offset_array (ftell f)
)
if type == 5 do (
append Type_6_offset_array (ftell f)
)
if type == 6 do (
append Type_6_offset_array (ftell f)
)
if type == 7 do (
append Type_7_offset_array (ftell f)
)
fseek f size #seek_cur
)
printoffset Type_0_offset_array.count
printoffset Type_1_offset_array.count
printoffset Type_2_offset_array.count
printoffset Type_3_offset_array.count
printoffset Type_4_offset_array.count
printoffset Type_5_offset_array.count
printoffset Type_6_offset_array.count
printoffset Type_7_offset_array.count


BNArr = #()

for a = 1 to Type_0_offset_array.count do (
fseek f Type_0_offset_array[a]#seek_set
float11 = readfloat f
float12 = readfloat f 
float13 = readfloat f 
float14 = readfloat f * -1
float21 = readfloat f
float22 = readfloat f
float23 = readfloat f
float24 = readfloat f
float31 = readfloat f
float32 = readfloat f
float33 = readfloat f
float34 = readfloat f
float41 = readfloat f
float42 = readfloat f
float43 = readfloat f
float44 = readfloat f
long1 = readlong f
long2 = readlong f
BoneParent = readlong f
long4 = readlong f
BoneNameSize = readlong f
BoneName = ReadFixedString f BoneNameSize
tfm = (quat float11 float12 float13 float14) as matrix3
tfm.row4 = [float31,float32,float33]
print (getNodeByName BoneName)
if (getNodeByName BoneName) != undefined do (
append BNArr (getNodeByName BoneName)
)
if (getNodeByName BoneName) == undefined do (
 if (BoneParent != -1) do (
tfm = tfm * BNArr[(BoneParent + 1)].objecttransform
 )

newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = BoneName
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (BoneParent != -1) then
 newBone.parent = BNArr[(BoneParent + 1)]
append BNArr newBone
				  )					  

)

Weight_array = #()
for a = 1 to Type_2_offset_array.count do (
count_array = #()
fseek f Type_2_offset_array[a]#seek_set
fseek f -8#seek_cur
chunksize = readlong f
fseek f Type_2_offset_array[a]#seek_set
unk01 = readlong f
WeightCount = readlong f
unk03 = readlong f
weight1start = (ftell f)
fseek f (8 * WeightCount)#seek_cur
weight2start = (ftell f)
numvert = ((chunksize - 12) - (8 * WeightCount)) / 8
for b = 1 to numvert do (
weightid = readlong f
wcount = readlong f
append count_array (weight_data2 weightid:weightid wcount:wcount) 
)
fseek f weight1start#seek_set
printoffset (count_array.count)
for b = 1 to count_array.count do (
Bone1 = -1
Bone2 = -1
Bone3 = -1
Bone4 = -1
weight1 = 0
weight2 = 0
weight3 = 0
weight4 = 0
if count_array[b].wcount == 1 do (
weight1 = readfloat f
Bone1 = readshort f
pad = readshort f
)
if count_array[b].wcount == 2 do (
weight1 = readfloat f
Bone1 = readshort f#unsigned
pad = readshort f
weight2 = readfloat f
Bone2 = readshort f#unsigned
pad2 = readshort f
)
if count_array[b].wcount == 3 do (
weight1 = readfloat f
Bone1 = readshort f#unsigned
pad = readshort f
weight2 = readfloat f
Bone2 = readshort f#unsigned
pad2 = readshort f
weight3 = readfloat f
Bone3 = readshort f#unsigned
pad3 = readshort f
)
if count_array[b].wcount == 4 do (
weight1 = readfloat f
Bone1 = readshort f#unsigned
pad = readshort f
weight2 = readfloat f
Bone2 = readshort f#unsigned
pad2 = readshort f
weight3 = readfloat f
Bone3 = readshort f#unsigned
pad3 = readshort f
weight4 = readfloat f
Bone4 = readshort f#unsigned
pad4 = readshort f
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
)
for a = 1 to Type_1_offset_array.count do (
fseek f Type_1_offset_array[a]#seek_set
Count1 = readlong f
Count2 = readlong f
Count3 = readlong f
Count4 = readlong f
FaceSections = readlong f
Count5 = readlong f
Count6 = readlong f
Count7 = readlong f
Count9 = readlong f
Count10 = readlong f
vertstart_array = #()
normalstart_array = #()
wertstart_array = #()
uvstart_array = #()
Facestart_array = #()
VertIDStart_array = #()

append VertIDStart_array (ftell f)
for b = 1 to Count3 do (
fseek f 4#seek_cur
)
for b = 1 to (Count5 - 1) do (
type = readlong f
size = readlong f
unk01 = readlong f
if type == 0 do (
append vertstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0xC#seek_cur
)
)
if type == 1 do (
append normalstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0xC#seek_cur
)
)
if type == 2 do (
append wertstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0x10#seek_cur
)
)
if type == 3 do (
append uvstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0x8#seek_cur
)
)
)
append Facestart_array (ftell f)
for c = 1 to FaceSections do (
Vert_array = #()
UV_array = #()
Normal_array = #()
Face_array = #()
Used_Bone_array = #()
vertid_array = #()
weightid_array = #()
Used_Bone_Name_array = #()
fseek f Facestart_array[c]#seek_set
facecount = readlong f
vertcount = readlong f
unk02 = readlong f
UsedBoneID = readlong f
for b = 1 to facecount / 3 do (
f1 = (readlong f) + 1
f2 = (readlong f) + 1
f3 = (readlong f) + 1
append Face_array [f1,f2,f3]
)
for b = 1 to UsedBoneID do (
boneid = readlong f + 1
append Used_Bone_array boneid
append Used_Bone_Name_array BNArr[boneid].name
)
append Facestart_array (ftell f)

if VertIDStart_array.count != 0 do (
fseek f VertIDStart_array[c]#seek_set
for d = 1 to vertcount do (
vertid = readlong f + 1
append vertid_array vertid
)
append VertIDStart_array (ftell f)
)
if vertstart_array.count != 0 do (
fseek f vertstart_array[c]#seek_set
for d = 1 to vertcount do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz]
)
append vertstart_array (ftell f)
)

if normalstart_array.count != 0 do (
fseek f normalstart_array[c]#seek_set
for d = 1 to vertcount do (
nx = readfloat f
ny = readfloat f
nz = readfloat f
append Normal_array [nx,ny,nz]
)
append normalstart_array (ftell f)
)

if wertstart_array.count != 0 do (
fseek f wertstart_array[c]#seek_set
for d = 1 to vertcount do (
wx = readfloat f
wy = readfloat f
wz = readfloat f
ww = readfloat f
)
append wertstart_array (ftell f)
)

if uvstart_array.count != 0 do (
fseek f uvstart_array[c]#seek_set
for d = 1 to vertcount do (
tu = readfloat f
tv = readfloat f * -1
append UV_array [tu,tv,0]
)
append uvstart_array (ftell f)
)
if UV_array.count == 0 do (
for d = 1 to vertcount do (
tu = 0
tv = 0
append UV_array [tu,tv,0]
)	
)
print Used_Bone_Name_array

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
--for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
print weightid_array
max modify mode
select msh
skinMod = skin ()
addModifier msh skinMod

for i = 1 to BNArr.count do
(
	maxbone = BNArr[i]
	if i != Used_Bone_array.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod

for i = 1 to vertcount do
(
	w = Weight_array[(vertid_array[i])]
	bi = #()
	wv = #()
	for j = 1 to w.boneids.count do
	(
		boneid = w.boneids[j]
		weight = w.weights[j]
		append bi boneid
		append wv weight
	)	
	skinOps.setVertexWeights skinMod i bi wv
)


max create mode


)
printoffset (ftell f)
printoffset Facestart_array[Facestart_array.count]
)


fclose f
```
## Post #2
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-13T12:04:14+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Thanks. As i understand script also imports bones and weights?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-13T12:38:27+00:00
- Post Title: WarBane Rising of Darkness [BMS]

> Reply from Axolotl
>
> Thanks. As i understand script also imports bones and weights?yes import bones and weights.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T15:03:40+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Noesis plugin works?
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-13T15:51:38+00:00
- Post Title: WarBane Rising of Darkness [BMS]

> Reply from finale00
>
> Noesis plugin works?
yes work but not at all, some of them not load and uv's wrong.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T15:58:35+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Post the ones that don't load or are wrong with their textures. Also post a link to the client.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-13T18:14:19+00:00
- Post Title: WarBane Rising of Darkness [BMS]

> Reply from finale00
>
> Post the ones that don't load or are wrong with their textures. Also post a link to the client.the client stay in the first topic, you need use Internet Explorer for get it, because use control of activex and in mozilla or chrome not working.



[WarBane 3D Samples Errors](http://www.mediafire.com/download.php?924dqs499ky4zdk)
## Post #8
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-13T19:28:55+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Are the ones that don't load all static meshes?
Trees have no bones.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T19:55:25+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Does the maxscript actually load these models?

There are two more structs in the mesh.
If you look at chrrox's script, 

```
append vertstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0xC#seek_cur
)
)
if type == 1 do (
append normalstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0xC#seek_cur
)
)
if type == 2 do (
append wertstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0x10#seek_cur
)
)
if type == 3 do (
append uvstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0x8#seek_cur
)

```


You will find this part inside my parse_mesh method.

Basically, there is an extra struct type 4. Type 4 struct has 4*numVerts bytes.

For the tree you sent, I think it is assigned the wrong material. As mentioned in the DK online thread, I don't know how the material is correctly assigned and simply did some hacking around to get things to work. Clearly it isn't working here.

Are there any meshes that actually have UV problems when rendered?
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-13T23:36:27+00:00
- Post Title: WarBane Rising of Darkness [BMS]

> Reply from finale00
>
> Does the maxscript actually load these models?

There are two more structs in the mesh.
If you look at chrrox's script, 
Code: Select allif type == 0 do (
append vertstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0xC#seek_cur
)
)
if type == 1 do (
append normalstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0xC#seek_cur
)
)
if type == 2 do (
append wertstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0x10#seek_cur
)
)
if type == 3 do (
append uvstart_array (ftell f)
for c = 1 to Count3 do (
fseek f 0x8#seek_cur
)


You will find this part inside my parse_mesh method.

Basically, there is an extra struct type 4. Type 4 struct has 4*numVerts bytes.

For the tree you sent, I think it is assigned the wrong material. As mentioned in the DK online thread, I don't know how the material is correctly assigned and simply did some hacking around to get things to work. Clearly it isn't working here.

Are there any meshes that actually have UV problems when rendered?
well not load, all I get is lagged PC and after some minutes I get error.

```
--   called in a loop; filename: C:\Program Files (x86)\Autodesk\3ds Max 9\stdplugs\stdscripts\Warbane Online Importer by chrox.ms; position: 3021
--  Frame:
--   BoneParent: -1
--   float22: 0.0
--   float32: 0.0
--   float42: 1.0
--   long2: -1
--   float21: 0.0
--   tfm: undefined
--   a: 1
--   float31: 0.0
--   float41: 1.0
--   long1: 0
--   newBone: undefined
--   float14: -1.0
--   BoneNameSize: 1065353216
--   float24: 1.0
--   float12: 0.0
--   float34: 1.0
--   boneName: undefined
--   float44: 0.0
--   float13: 0.0
--   long4: 5
--   float23: 0.0
--   float11: 0.0
--   float33: 0.0
--   float43: 0.0
-- Error occurred during fileIn in <File:C:\Program Files (x86)\Autodesk\3ds Max 9\stdplugs\stdscripts\Warbane Online Importer by chrox.ms>
>> MAXScript Auto-load Script Error - C:\Program Files (x86)\Autodesk\3ds Max 9\stdplugs\stdscripts\Warbane Online Importer by chrox.ms Exception: -- Unknown system exception <<
```
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T04:06:53+00:00
- Post Title: WarBane Rising of Darkness [BMS]

lol I wrote 2 extra structs but there's only one extra.

Anyways I've updated the XAC script so maybe the ones you couldn't load will load now.
Also that extra struct might have something to do with bones since there are only 4 bytes per vertex and a lot of them are FF's.

Can you get a direct link to the client? It is more convenient than downloading and installing weird things.
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-14T13:14:55+00:00
- Post Title: WarBane Rising of Darkness [BMS]

> Reply from finale00
>
> lol I wrote 2 extra structs but there's only one extra.

Anyways I've updated the XAC script so maybe the ones you couldn't load will load now.
Also that extra struct might have something to do with bones since there are only 4 bytes per vertex and a lot of them are FF's.

Can you get a direct link to the client? It is more convenient than downloading and installing weird things.Direct link I don't have, they have 3 links of Launcher but not direct links xX
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T18:27:49+00:00
- Post Title: WarBane Rising of Darkness [BMS]

Do you have direct link to launcher?
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-14T19:03:01+00:00
- Post Title: WarBane Rising of Darkness [BMS]

> Reply from finale00
>
> Do you have direct link to launcher?yes man, how say before the link is posted in first topic, but you need log into mgame for get launcher, without account can't open it.

[http://warbane.mgame.com/data/?rtype=D](http://warbane.mgame.com/data/?rtype=D)
## Post #15
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-04-03T20:19:45+00:00
- Post Title: WarBane Rising of Darkness [BMS]

how did you unpack the .data2 files?
