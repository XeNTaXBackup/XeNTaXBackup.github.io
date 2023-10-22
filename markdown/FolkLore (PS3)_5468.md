## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-27T05:11:39+00:00
- Post Title: FolkLore (PS3)

I have made a max script to import the meshes into max no bones yet.


```
	heapSize = 200000000

fname = getOpenFileName \ 
caption:"Open Folklore Model File" \
types:"Folklore Model File(*cmd)|*cmd" \
historyCategory:"FolkloreObjectPresets"
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
return convertTo32(ReadBEword fstream) * 2
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
idstring = ReadFixedString f 4
Unk01 = ReadBElong f
MeshCount = ReadBEword f
TextureCount = ReadBEword f
Version = ReadFixedString f 4
Unk02 = ReadBElong f
NameOffset = ReadBElong f
Unk03 = ReadBElong f
Unk04 = ReadBElong f
struct Mesh_Info_Struct
(
	Unk11,FaceCount,VertCount,FaceOffset,MeshOffset,Unk16,X30SectOffset
)
Mesh_Info_Array = #()
for a = 1 to MeshCount Do (
fseek f 0x7C#seek_cur
Unk11 = ReadBElong f	
FaceCount = ReadBElong f
VertCount = ReadBElong f
FaceOffset = ReadBElong f
MeshOffset = ReadBElong f
Unk16 = ReadBElong f
X30SectOffset = ReadBElong f
fseek f 0x18#seek_cur
append Mesh_Info_Array (Mesh_Info_Struct Unk11:Unk11 FaceCount:FaceCount VertCount:VertCount FaceOffset:FaceOffset MeshOffset:MeshOffset Unk16:Unk16 X30SectOffset:X30SectOffset)
)
for a = 1 to MeshCount Do (
fseek f Mesh_Info_Array[a].FaceOffset #seek_set

Vert_array = #() 
Normal_array = #()
UV_array = #()
Face_array = #()

StartDirection = -1
f1 = (ReadBElong f) + 1
f2 = (ReadBElong f) + 1  
FaceDirection = StartDirection
while (ftell f) != (Mesh_Info_Array[a].FaceOffset + (Mesh_Info_Array[a].FaceCount * 4))Do (
f3 = (ReadBElong f)
if (f3==0xFFFF) then (
f1 = (ReadBElong f) + 1
f2 = (ReadBElong f) + 1
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
)
	

fseek f Mesh_Info_Array[a].MeshOffset #seek_set
for b = 1 to Mesh_Info_Array[a].VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f

ny = ReadBEfloat f

nz = ReadBEfloat f
	

unk21 = ReadBEfloat f

unk22 = ReadBEfloat f

unk23 = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
unk24 = ReadBEfloat f

unk25 = ReadBEfloat f

unk26 = ReadBEfloat f

unk27 = ReadBEfloat f

unk28 = ReadBEfloat f

unk29 = ReadBEfloat f

append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = Mesh_Name_array[a]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
print Mesh_Info_Array
fclose f

```
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-11-28T04:52:44+00:00
- Post Title: FolkLore (PS3)

Nice, thanks  Folklore is one of my favorite game. It would be great to see models from there! Any plans to supporting bones?

btw, chrrox, new cool game from the creators of Folklore is out. I posted files [here](http://forum.xentax.com/viewtopic.php?p=45442#p45442).
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-11-28T20:37:07+00:00
- Post Title: FolkLore (PS3)

yeah thumbs up for all the effort you are doing mate
## Post #4
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2010-11-30T08:51:46+00:00
- Post Title: FolkLore (PS3)

And what about the animation?
## Post #5
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2010-12-05T07:51:51+00:00
- Post Title: FolkLore (PS3)

I can not find files with cmd, only bi5_
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-05T16:47:14+00:00
- Post Title: FolkLore (PS3)

This will let you extract those files.

```
get totalsize long
get files long
math files - 1
get tablestart long
get namestart long
math tablestart + 4
for i = 0 < files
goto tablestart
get offset long
savepos tablestart
get size long
if i == files
get size asize
endif
math size - offset
goto namestart
getdstring name 0x18
savepos namestart
goto offset
getdstring ext 0x4
if ext == "CMD"
get size long
endif
string name + .
string name + ext
log name offset size
next i

```
## Post #7
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2010-12-05T22:06:08+00:00
- Post Title: FolkLore (PS3)

First to all i want to give the thanks to Chroxx for this awesome work , also guys
¿Any one know how to get textures ? or they are the SDD files?

Thanks in advance.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-05T22:32:33+00:00
- Post Title: FolkLore (PS3)

SDD is DDS backwards
the header is near identical to a real dds header just compare them and you will see.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-06T02:51:26+00:00
- Post Title: FolkLore (PS3)

> Reply from chrrox
>
> SDD is DDS backwards
the header is near identical to a real dds header just compare them and you will see.
Yes, thanks chrrox, already figured out.

[http://img403.imageshack.us/img403/8337 ... bc3ad5.jpg](http://img403.imageshack.us/img403/8337/a52975bc3ad5.jpg)
## Post #10
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2010-12-06T03:25:25+00:00
- Post Title: FolkLore (PS3)

> Reply from chrrox
>
> SDD is DDS backwards
the header is near identical to a real dds header just compare them and you will see.

Yea you are right, already figured out.
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-03T02:51:00+00:00
- Post Title: FolkLore (PS3)

Thanks to reveal8n For all his help.
dds converter

```
endian big
get name basename
string name + .dds
get size asize
set size2 size
math size2 - 0x80
goto 0xC
get width long
get height long
goto 0x54
get type byte
endian little
putVarChr MEMORY_FILE 0xC width long
putVarChr MEMORY_FILE 0x10 height long
putVarChr MEMORY_FILE 0x57 type byte
append
log MEMORY_FILE 0x80 size2
append
log name 0 size MEMORY_FILE

```


Mesh with bones and weights scripts
Bone run first

```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open Folklore Model File" \
types:"Folklore Model File(*.am2)|*.am2" \
historyCategory:"FolkloreObjectPresets"
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

struct Mesh_Info_Struct
(
	Mesh_Name,vertstart,vertend,vertcount,facecount
)
unk01 = ReadBElong f
unk02 = ReadBElong f
BoneCount = ReadBEword f
unk07 = ReadBEword f
unk03 = ReadBElong f
unk04 = ReadBElong f
unk05 = ReadBElong f
unk06 = ReadBElong f
BoneStart = ReadBElong f

struct Bone_Info_Struct
(
	index,child,next
)
fseek f BoneStart#seek_set
BNInf = #()
BNArr = #()
for a = 1 to BoneCount do (
fseek f 0x01#seek_cur
index = readbyte f #unsigned
fseek f 0x16#seek_cur
child = ReadBEword f
next  = ReadBEword f
fseek f 0x04#seek_cur
mx = ReadBEfloat f
my = ReadBEfloat f
mz = ReadBEfloat f
fseek f 0x24#seek_cur
tfm = (quat 0 0 0 1) as matrix3
tfm.row4 = [mx,my,mz]
	newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name   = (a as string)
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.setBoneEnable false 0
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()

append BNInf (Bone_Info_Struct index:index child:child next:next)
append BNArr newBone  	
)
for a = 1 to BoneCount do (
	p = BNArr[a]
	cidx = BNInf[a].child
	while (cidx != 0xFFFF) do (
		b = BNArr[cidx + 1]
		b.parent = p
		b.transform *= p.transform
		cidx = BNInf[cidx + 1].next
	)
)

fclose f

```


Mesh import run after bone

```
	heapSize = 200000000

fname = getOpenFileName \ 
caption:"Open Folklore Model File" \
types:"Folklore Model File(*cmd)|*cmd" \
historyCategory:"FolkloreObjectPresets"
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
test = ReadBEword fstream
if test == 0 then return 0
else
return convertTo32(test) * 2
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

idstring = ReadFixedString f 4
Unk01 = ReadBElong f
MeshCount = ReadBEword f
TextureCount = ReadBEword f
Version = ReadFixedString f 4
Unk02 = ReadBElong f
NameOffset = ReadBElong f
Unk03 = ReadBElong f
Unk04 = ReadBElong f
struct Mesh_Info_Struct
(
	Unk11,FaceCount,VertCount,FaceOffset,MeshOffset,TexInfoOff,BonePalletOff
)
Mesh_Info_Array = #()
for a = 1 to MeshCount Do (
fseek f 0x7C#seek_cur
Unk11 = ReadBElong f	
FaceCount = ReadBElong f
VertCount = ReadBElong f
FaceOffset = ReadBElong f
MeshOffset = ReadBElong f
TexInfoOff = ReadBElong f
BonePalletOff = ReadBElong f
fseek f 0x18#seek_cur
append Mesh_Info_Array (Mesh_Info_Struct Unk11:Unk11 FaceCount:FaceCount VertCount:VertCount FaceOffset:FaceOffset MeshOffset:MeshOffset TexInfoOff:TexInfoOff BonePalletOff:BonePalletOff)
)
for a = 1 to MeshCount Do (
fseek f Mesh_Info_Array[a].BonePalletOff#seek_set
bidArray = #()
for b = 1 to 0x100 do (
boneid = ((readbyte f#unsigned) + 1)
if boneid != 256 do (
append bidArray boneid
)
)

fseek f Mesh_Info_Array[a].FaceOffset #seek_set
Vert_array = #() 
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
StartDirection = -1
f1 = (ReadBElong f) + 1
f2 = (ReadBElong f) + 1  
FaceDirection = StartDirection
while (ftell f) != (Mesh_Info_Array[a].FaceOffset + (Mesh_Info_Array[a].FaceCount * 4))Do (
f3 = (ReadBElong f)
if (f3==0xFFFF) then (
f1 = (ReadBElong f) + 1
f2 = (ReadBElong f) + 1
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
)
	

fseek f Mesh_Info_Array[a].MeshOffset #seek_set
for b = 1 to Mesh_Info_Array[a].VertCount Do (
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
vw = ReadBEfloat f
nx = ReadBEHalfFloat f
ny = ReadBEHalfFloat f
nz = ReadBEHalfFloat f
nw = ReadBEHalfFloat f
ColorA = ReadBEHalfFloat f
ColorR = ReadBEHalfFloat f
ColorG = ReadBEHalfFloat f
ColorB = ReadBEHalfFloat f
tu2 = ReadBEHalfFloat f
tv2 = ReadBEHalfFloat f * -1
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
TangentX = ReadBEHalfFloat f
TangentY = ReadBEHalfFloat f
TangentZ = ReadBEHalfFloat f
TangentW = ReadBEHalfFloat f
weight1 = ReadBEHalfFloat f
weight2 = ReadBEHalfFloat f
weight3 = ReadBEHalfFloat f
weight4 = ReadBEHalfFloat f
bone1 = ReadBEHalfFloat f
bone2 = ReadBEHalfFloat f
bone3 = ReadBEHalfFloat f
bone4 = ReadBEHalfFloat f

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
			append w.boneids (bone1 as integer + 1)
			append w.weights w1
		)
		if(weight2 != 0) then (
			w2 = weight2 as float
			append w.boneids (bone2 as integer + 1)
			append w.weights w2
		)
		if(weight3 != 0) then (
			w3 = weight3 as float
			append w.boneids (bone3 as integer + 1)
			append w.weights w3
		)
		if(weight4 != 0) then (
			w4 = weight4 as float
			append w.boneids (bone4 as integer + 1)
			append w.weights w4
		)		
	)
append Weight_array w
append Vert_array [vx,vy,vz]
append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
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
for i = 1 to bidArray.count do
(
	maxbone = BNArr[(bidArray[i])]
	if i != bidArray.count then
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
modPanel.setCurrentObject $.baseObject prompt:false
modPanel.addModToSelection (Vertex_Weld ()) ui:on
$.modifiers[#Vertex_Weld].threshold = 0.001
max create mode
)
print Mesh_Info_Array
fclose f

```
## Post #12
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-05-03T04:20:09+00:00
- Post Title: FolkLore (PS3)

This is really awesome , thanks chrrox and reveal8n .
## Post #13
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-04T16:45:01+00:00
- Post Title: FolkLore (PS3)

Great work chrrox.
I imported the guy but I can't find the girl model, all CMD files I open is the guy, where/what file is the girl model on?
Thank you.
## Post #14
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-05-04T17:14:13+00:00
- Post Title: FolkLore (PS3)

> Reply from rexil
>
> Great work chrrox.
I imported the guy but I can't find the girl model, all CMD files I open is the guy, where/what file is the girl model on?
Thank you.

check the files LCm455 , LCm85 , LCm90 , LCm4520, LCm314, 465, 470 and 480
those files have the girl model.
## Post #15
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-04T17:36:52+00:00
- Post Title: FolkLore (PS3)

> Reply from The Chief
>
> rexil wrote:Great work chrrox.
I imported the guy but I can't find the girl model, all CMD files I open is the guy, where/what file is the girl model on?
Thank you.

check the files LCm455 , LCm85 , LCm90 , LCm4520, LCm314, 465, 470 and 480
those files have the girl model.

That's weird I don't get those files when I extract the .bin_ the bms extract only 14 files.
## Post #16
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-05-04T18:02:52+00:00
- Post Title: Re: FolkLore (PS3)

It should exctract 4306 files.
## Post #17
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-04T18:35:30+00:00
- Post Title: Re: FolkLore (PS3)

I'm using the bms script posted in the first page, it only extract those 14 files.
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-04T19:24:29+00:00
- Post Title: Re: FolkLore (PS3)

each file is only one character so that sounds correct.
## Post #19
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-04T19:38:28+00:00
- Post Title: Re: FolkLore (PS3)

> Reply from chrrox
>
> each file is only one character so that sounds correct.

I have imported the files to max but they are all the same guy. 

EDIT: Thank you Chief it's working now.
## Post #20
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2012-07-10T15:20:25+00:00
- Post Title: Re: FolkLore (PS3)

Hey peeps,

I'm new to the forums, I think the stuff you do here is really great. Would somebody kind be able to point me in the direction of a tutorial so I can attempt to extract the Folklore models? I have 3d modelling experience but have never attempted anything like an extraction before or running max scripts. Im guessing i have to get my pc to read the folklore discs and then run the extraction script posted here?

I also own all the Folklore dlc and would like to know if the same process is possible. Some of the dlc "folk" looked awesome.

thanks in advance for your help. ^__^
## Post #21
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-10T16:55:36+00:00
- Post Title: Re: FolkLore (PS3)

> Reply from Blank9
>
> Hey peeps,

I'm new to the forums, I think the stuff you do here is really great. Would somebody kind be able to point me in the direction of a tutorial so I can attempt to extract the Folklore models? I have 3d modelling experience but have never attempted anything like an extraction before or running max scripts. Im guessing i have to get my pc to read the folklore discs and then run the extraction script posted here?

I also own all the Folklore dlc and would like to know if the same process is possible. Some of the dlc "folk" looked awesome.

thanks in advance for your help. ^__^

The Normal BD Drives for pc cant read PS3 discs there was one drive the Lite on that can read those discs but dont know how much
those costs and for the DLC from the game are edat files encrypyted and there is no tool that can open them =/.
## Post #22
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2012-07-10T18:57:05+00:00
- Post Title: Re: FolkLore (PS3)

Thank you for the reply.

I'm confused however; how is it that people on the thread are extracting the models? using the lite drive you have mentioned?
## Post #23
- Username: Blank9
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-10T19:47:30+00:00
- Post Title: Re: FolkLore (PS3)

you need  hacked ps3 and a copy of the game the only way to legally extract the files.
## Post #24
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2012-07-13T23:29:23+00:00
- Post Title: Re: FolkLore (PS3)

Apologies for the noobishness, Is there a tutorial for running the max script? Or can somebody give me a layman's terms run-down so I can attempt this?

do I want to be working on the arc? bin file? the model.bin file? Or require an additional program?

I searched the tutorial forums but wasn't quite sure what I was looking for.
Again, thank u for your time.
## Post #25
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-14T00:02:37+00:00
- Post Title: Re: FolkLore (PS3)

> Reply from Blank9
>
> Apologies for the noobishness, Is there a tutorial for running the max script? Or can somebody give me a layman's terms run-down so I can attempt this?

do I want to be working on the arc? bin file? the model.bin file? Or require an additional program?

I searched the tutorial forums but wasn't quite sure what I was looking for.
Again, thank u for your time.

First you need to run the quickbms script on the bin file that are in the bin folder after that you will get many bi5_ files then just
use the bio5_ script to get the cdm files with those files just open 3dmax and use the maxscript that chroxx posted , also grab the
dds texture converter so you can convert the sdd to dds.

So in other words:

Run the bin script on the bin file
Use the bio5_ script on them to get CMD files
and last use the max script on the CMD to import the models in max studio.

All those scripts are in this thread.
## Post #26
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2012-07-14T00:13:47+00:00
- Post Title: Re: FolkLore (PS3)

> Reply from The Chief
>
> Blank9 wrote:Apologies for the noobishness, Is there a tutorial for running the max script? Or can somebody give me a layman's terms run-down so I can attempt this?

do I want to be working on the arc? bin file? the model.bin file? Or require an additional program?

I searched the tutorial forums but wasn't quite sure what I was looking for.
Again, thank u for your time.

First you need to run the quickbms script on the bin file that are in the bin folder after that you will get many bi5_ files then just
use the bio5_ script to get the cdm files with those files just open 3dmax and use the maxscript that chroxx posted , also grab the
dds texture converter so you can convert the sdd to dds.

So in other words:

Run the bin script on the bin file
Use the bio5_ script on them to get CMD files
and last use the max script on the CMD to import the models in max studio.

All those scripts are in this thread.

Excellent! thank you for the breakdown.
I only have a games art background, I have never run either a script or a max script before. How do I do this? I'm assuming the models are in the "models.bin" although there are others bin files there.

again thank you for your time.
## Post #27
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-14T00:34:55+00:00
- Post Title: Re: FolkLore (PS3)

OK first  you need to download Quickbms from aluigi site:
[http://www.aluigi.org/](http://www.aluigi.org/)

Then just open and select the .txt script for the .bin file (its a huge big file of  2 GB )

endian big
open FDDE fht_ 0
open FDDE bin_ 1
get files asize
math files / 0x28
for i = 0 < files
getdstring name 0x20
get size long
get offset long
log name offset size 1
next i

Save that in .txt format and use quickbms on that , then you will get the bio5_ files 
for the bio5_ run this other script:

endian big
get totalsize long
get files long
math files - 1
get tablestart long
get namestart long
math tablestart + 4
for i = 0 < files
goto tablestart
get offset long
savepos tablestart
get size long
if i == files
get size asize
endif
math size - offset
goto namestart
getdstring name 0x18
savepos namestart
goto offset
getdstring ext 0x4
if ext == "CMD"
get size long
endif
string name + .
string name + ext
log name offset size
next i

Runing that will get you the CMD files then just copy the text that chroxx release on the first page and paste on a txt file just 
rename that to ms and open max studio run script and select and CMD file and you will able to imprt the model file , also on the
first page copy the dds script so you can convert the SDD files to DDS.
## Post #28
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2013-03-14T08:34:07+00:00
- Post Title: Re: FolkLore (PS3)

Huge thanks for your post Chief it helped immensely and of course Chrrox for all the awesome.
Big apologies for my utter noobishness.
Im getting there, got really close but i think ive got a bit lost. If anyone could help me with the following:

1. When i extract the Bin is it just the model.bin or the others aswell?

2. When running BI5 to CMD am I supposed to keep these in the same folder or can I put in a fresh folder?
Am I narrowing it down to just the character files or keeping it in one big ol mess. 

3. What are the sort of filenames for the main SDD's to convert? 
I've noticed some of the SDD's contain 0kb and I think the converter doesn't like them. seems to just stop the process if I try to convert them in a batch. Is this normal or have I done something wrong? I tried to isolate ones with C and N in them which im assuming is colour and normal maps. IE: c353_c, c353_n but they're tiny 4kb. Or do I just want the C353s ones that are 172kb.

4. Where are the bone files contained and what is the file name?
On my 2nd attempt I couldn't even find those files so I definitely missed something.

5. Can someone give me an example of the naming conventions and files I would require to put a character together in Max? I think I might have an easier job if I could do it by single character.

On my first attempt I got Keits in Max with bones and managed to apply his hair, face and eye textures with an DDS but the rest of his body textures weren't there. I'm not sure if he should only have 1 DDS and i applied it wrong, i buggered it or i was supposed to be finding a second one. On my second attempt at the whole process i managed to get a single poly into max lol utter fail.

Any help greatly appreciated.
