## Post #1
- Username: Andrakann
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-11T00:21:54+00:00
- Post Title: No More Heroes: Heroes' Paradise

Here is a 3ds max importer for the xbox 360 models of this game. Supports bones and weights.


```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open No More Heroes 360 Model File" \
types:"No More Heroes 360 Model File(*model)|*model" \
historyCategory:"No More Heroes 360 ObjectPresets"
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

struct weight_data
(
	boneids,weights
)

struct Mesh_Info_Struct
(
	Mesh_Name,vertstart,vertend,vertcount,facecount,InfoStart,MeshGroup,FaceStart
)
MNKS0101 = ReadFixedString f 8
Version = ReadBElong f
null = ReadBElong f
Modelname = ReadFixedString f 32
total_size = getFileSize fname
RXET_array = #()
TNOJ_array = #()
ARTM_array = #()
RDHS_array = #()
KSEM_array = #()
PHSB_array = #()
struct type_Info_Struct
(
	Pos,type,typesize
)
while (ftell f) != total_size Do (
Pos = (ftell f)
type = ReadFixedString f 4
typesize = ReadBElong f
fseek f (pos + typesize)#seek_set
case of
(
(type == "RXET"): append RXET_array (type_Info_Struct Pos:Pos type:type typesize:typesize)
(type == "TNOJ"): append TNOJ_array (type_Info_Struct Pos:Pos type:type typesize:typesize)
(type == "ARTM"): append ARTM_array (type_Info_Struct Pos:Pos type:type typesize:typesize)
(type == "RDHS"): append RDHS_array (type_Info_Struct Pos:Pos type:type typesize:typesize)
(type == "KSEM"): append KSEM_array (type_Info_Struct Pos:Pos type:type typesize:typesize)
(type == "PHSB"): append PHSB_array (type_Info_Struct Pos:Pos type:type typesize:typesize)
default: print type
)
)
BNArr = #()
for a =1 to TNOJ_array.count Do (
fseek f (TNOJ_array[a].Pos + 8)#seek_set
Size1 = ReadBElong f
Null1 = ReadBElong f
SkelName = ReadFixedString f 32
BoneCount = ReadBElong f
Version = ReadBElong f
fseek f 0x8#seek_cur

for b = 1 to BoneCount do (
BoneName = ReadFixedString f 0x20
m11 = ReadBEFloat f; m12 = ReadBEFloat f; m13 = ReadBEFloat f; m14 = ReadBEFloat f
m21 = ReadBEFloat f; m22 = ReadBEFloat f; m23 = ReadBEFloat f; m24 = ReadBEFloat f
m31 = ReadBEFloat f; m32 = ReadBEFloat f; m33 = ReadBEFloat f; m34 = ReadBEFloat f
m41 = ReadBElong f; m42 = ReadBElong f; m43 = ReadBElong f; m44 = ReadBElong f
tfm = (quat m21 m22 m23 m24) as matrix3
tfm.row4 = [m11,m12,m13]

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


 if (m41 != -1) then
 newBone.parent = BNArr[m41 + 1]
append BNArr newBone	
)
)

struct Mesh_Info2_Struct
(
	Vert_Start,FaceStart,VertTotal,FaceTotal,vertsize
)
Mesh_Info2_Array = #()
for a =1 to KSEM_array.count Do (
fseek f (KSEM_array[a].Pos + 8)#seek_set
Size1 = ReadBElong f
Null1 = ReadBElong f
SkinName = ReadFixedString f 32	
MeshSections = ReadBElong f
unk01 = ReadBElong f
MeshCount = ReadBEword f
fseek f 0x6#seek_cur
for b = 1 to MeshSections Do (
SceneName = ReadFixedString f 32
VertTotal = ReadBElong f
FaceTotal = ReadBElong f
vertsize = ReadBEword f
facesize = ReadBEword f
Unk01 = ReadBElong f
Vert_Start = (ftell f)
fseek f (Vert_Start + VertTotal)#seek_set
if mod (ftell f) 16 != 0 do (
fseek f (16 - (mod (ftell f) 16))#seek_cur
)
FaceStart = (ftell f)
fseek f (FaceStart + FaceTotal)#seek_set
if mod (ftell f) 16 != 0 do (
fseek f (16 - (mod (ftell f) 16))#seek_cur
)
append Mesh_Info2_Array (Mesh_Info2_Struct Vert_Start:Vert_Start FaceStart:FaceStart VertTotal:VertTotal FaceTotal:FaceTotal vertsize:vertsize)
)
MeshInfoOff = (ftell f)
Mesh_Info_Array = #()
PrintOffset (ftell f)

for b = 1 to MeshCount Do (
InfoStart = (ftell f)
Mesh_Name = ReadFixedString f 32
facecount = ReadBEword f
vertstart = ReadBEword f
vertend = ReadBEword f
vertcount = ReadBEword f
Unk03 = readbyte f#unsigned
Unk04 = readbyte f#unsigned
Unk05 = readbyte f#unsigned
MeshGroup = ((readbyte f#unsigned) + 1)
Unk01 = ReadBElong f
Unk02 = ReadBElong f
FaceStart = ReadBElong f
fseek f 0x68#seek_cur
append Mesh_Info_Array (Mesh_Info_Struct Mesh_Name:Mesh_Name vertstart:vertstart vertend:vertend vertcount:vertcount facecount:facecount InfoStart:InfoStart MeshGroup:MeshGroup FaceStart:FaceStart)
)
print Mesh_Info_Array


for b = 1 to MeshCount do (
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
BaseVert = Mesh_Info2_Array[(Mesh_Info_Array[b].MeshGroup)].Vert_Start
vertsize =  Mesh_Info2_Array[(Mesh_Info_Array[b].MeshGroup)].vertsize
fseek f (BaseVert + (Mesh_Info_Array[b].vertstart * vertsize))#seek_set
printoffset (ftell f)
for c = 1 to Mesh_Info_Array[b].vertcount do (

if vertsize == 48 do (
vx = ReadBEfloat f
vy = ReadBEfloat f 
vz = ReadBEfloat f
COLOR1 = readlong f
weight1 = readbyte f#unsigned
weight2 = readbyte f#unsigned
weight3 = readbyte f#unsigned
weight4 = readbyte f#unsigned
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
xy = ReadBEfloat f
xz = ReadBEfloat f
tu = (ReadBEHalfFloat f) * 2
tv = (ReadBEHalfFloat f) * -2
nx = ReadBEfloat f
ny = ReadBEfloat f
nz = ReadBEfloat f

)

if vertsize == 44 do (
vx = ReadBEfloat f
vy = ReadBEfloat f 
vz = ReadBEfloat f
COLOR1 = readlong f
weight1 = readbyte f#unsigned
weight2 = readbyte f#unsigned
weight3 = readbyte f#unsigned
weight4 = readbyte f#unsigned
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
xy = ReadBEfloat f
xz = ReadBEfloat f
tu = (ReadBEHalfFloat f) * 2
tv = (ReadBEHalfFloat f) * -2
nx = ReadBEfloat f
ny = ReadBEfloat f
nz = ReadBEfloat f
)

if 	vertsize == 40 do (
vx = ReadBEfloat f
vy = ReadBEfloat f 
vz = ReadBEfloat f
COLOR1 = readlong f
weight1 = readbyte f#unsigned
weight2 = readbyte f#unsigned
weight3 = readbyte f#unsigned
weight4 = readbyte f#unsigned
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
tu = (ReadBEHalfFloat f) * 2
tv = (ReadBEHalfFloat f) * -2
nx = ReadBEfloat f
ny = ReadBEfloat f
nz = ReadBEfloat f
)
if 	vertsize == 36 do (
vx = ReadBEfloat f
vy = ReadBEfloat f 
vz = ReadBEfloat f
COLOR1 = readlong f
weight1 = readbyte f#unsigned
weight2 = readbyte f#unsigned
weight3 = readbyte f#unsigned
weight4 = readbyte f#unsigned
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
tu = (ReadBEHalfFloat f) * 2
tv = (ReadBEHalfFloat f) * -2
fseek f 0x8#seek_cur
)
if 	vertsize == 32 do (
vx = ReadBEfloat f
vy = ReadBEfloat f 
vz = ReadBEfloat f
COLOR1 = readlong f
weight1 = 255.0
weight2 = 0
weight3 = 0
weight4 = 0
bone1 = 0
bone2 = 0
bone3 = 0
bone4 = 0
tu = (ReadBEHalfFloat f) * 2
tv = (ReadBEHalfFloat f) * -2
fseek f 0x4#seek_cur
COLOR2 = readlong f
COLOR3 = readlong f
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

if(maxweight != 0) then (
		if(weight1 != 0) then (
			w1 = weight1 as float
			append w.boneids (bone1 + 1)
			append w.weights w1
		)
		if(weight2 != 0) then (
			w2 = weight2 as float
			append w.boneids (bone2 + 1)
			append w.weights w2
		)
		if(weight3 != 0) then (
			w3 = weight3 as float
			append w.boneids (bone3 + 1)
			append w.weights w3
		)
		if(weight4 != 0) then (
			w4 = weight4 as float
			append w.boneids (bone4 + 1)
			append w.weights w4
		)		
	)
append Weight_array w
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]

)
BaseFace = Mesh_Info2_Array[(Mesh_Info_Array[b].MeshGroup)].FaceStart
fseek f ((Mesh_Info_Array[b].FaceStart * 2) + BaseFace)#seek_set
for d = 1 to Mesh_Info_Array[b].facecount do (
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
f3 = ReadBEword f + 1
append Face_array [f1,f2,f3]
)

fseek f (Mesh_Info_Array[b].InfoStart + 0x50)#seek_set
usedbones = ReadBElong f
null = ReadBElong f
bidArray = #()
for c = 1 to usedbones do (
bid = ((readbyte f#unsigned) + 1)
append bidArray bid
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name = Mesh_Info_Array[b].Mesh_Name + "_" + b as string
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

)

fclose f

```
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-11T00:44:33+00:00
- Post Title: No More Heroes: Heroes' Paradise

awesome, thanks man. NMH is my favorite game, such a shame the dev closed the book on the series.

EDIT


```
(
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
fseek f 0x4#seek_cur -- FFs
tu = (ReadBEHalfFloat f) * 2
tv = (ReadBEHalfFloat f) * -2
nx = ReadBEfloat f
ny = ReadBEfloat f
nz = ReadBEfloat f
)

```
## Post #3
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-05-11T06:32:00+00:00
- Post Title: No More Heroes: Heroes' Paradise

Hi, chrrox.
You always write

> Supports bones and weights.
But never write about animation. You never tried to import animations too? I mean not this game only.
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-05-11T08:10:23+00:00
- Post Title: No More Heroes: Heroes' Paradise

Thank you so much^^ amazing work as usually,...
## Post #5
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-05-14T06:23:19+00:00
- Post Title: No More Heroes: Heroes' Paradise

Could you explain how to extract the model file ,please?
## Post #6
- Username: Andrakann
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-15T04:07:19+00:00
- Post Title: No More Heroes: Heroes' Paradise

Model BMS
run it on the 360 file default.fpd

```
#No more heroes xbox 360 .model extractor
#by chrrox
for
findloc start string "MNKS0101"
goto start
savepos offset
findloc npos string KSEM
math npos + 0x40
goto npos
getdstring name 0x20
string name + .model
findloc end string " FOE"
set size end
math size - start
log name offset size
goto end
next

```

[badgirl1.jpg](https://xentaxbackup.github.io/file/4243_badgirl1.jpg)
## Post #7
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-05-15T04:47:51+00:00
- Post Title: No More Heroes: Heroes' Paradise

Thank you very much.
Master chrrox.
## Post #8
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-05-18T19:10:47+00:00
- Post Title: No More Heroes: Heroes' Paradise

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-18T20:24:38+00:00
- Post Title: No More Heroes: Heroes' Paradise

You extracted 360 models correct?
the ps3 models will not work.
## Post #10
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-05-18T21:10:25+00:00
- Post Title: No More Heroes: Heroes' Paradise

yes these are model files from 360 version. I used xbox backup creator to extract default.fpd from the game
## Post #11
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-05-18T21:19:39+00:00
- Post Title: No More Heroes: Heroes' Paradise

I test the files you posted on max 9 and 2009 but they dont work , max just freez every
time i test one of the files.
## Post #12
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-05-18T21:29:09+00:00
- Post Title: No More Heroes: Heroes' Paradise

> Reply from The Chief
>
> I test the files you posted on max 9 and 2009 but they dont work , max just freez every
time i test one of the files.

yes this is exactly the same issue i 've got. maybe the files are corrupted or something.
i will try to extract them with another tool.
thx
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-18T22:43:48+00:00
- Post Title: No More Heroes: Heroes' Paradise

Ah i fixed the bms one line copy paste error now it should work.
## Post #14
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-05-19T12:03:13+00:00
- Post Title: No More Heroes: Heroes' Paradise

thanks a lot chrrox
## Post #15
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-05-19T21:17:21+00:00
- Post Title: No More Heroes: Heroes' Paradise

Thanks, awesome as always.
## Post #16
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-05-19T21:43:11+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

Hi again chrrox, can you explain please how to extract textures 
thx
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-19T21:49:18+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

run the texture extractor on the ps3 file.
ill re post it here just for quick reference.

```
endian big
get name basename
string name + .dds
get size asize
set size2 size
math size2 - 0x80
goto 0x20
get width short
get height short
goto 0x18
get type byte
endian little
if type == 0x86
putVarChr MEMORY_FILE 0x57 0x31 byte
endif
if type == 0x87
putVarChr MEMORY_FILE 0x57 0x33 byte
endif
if type == 0x88
putVarChr MEMORY_FILE 0x57 0x35 byte
endif
putVarChr MEMORY_FILE 0xC height short
putVarChr MEMORY_FILE 0x10 width short
append
log MEMORY_FILE 0x80 size2
append
log name 0 size MEMORY_FILE

```
## Post #18
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-05-20T16:17:30+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

Thank you
## Post #19
- Username: DJNANO
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Apr 09, 2011 9:01 am
- Post datetime: 2011-05-20T20:39:48+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

Hi, i want to add PS3 Translations from EUR version to 360 JAP version,i need to extract all .fpd/.fpi from both games.

Im noob, please help.
## Post #20
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-22T00:56:15+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

Thanks a lot chrrox you rock
## Post #21
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-07-22T22:02:23+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

cant get textures D:
## Post #22
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-07-22T22:36:51+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

> Reply from protosk8
>
> cant get textures D:

> Reply from chrrox
>
> run the texture extractor on the ps3 file.
## Post #23
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-07-22T23:28:16+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

> Reply from rexil
>
> protosk8 wrote:cant get textures D:
chrrox wrote:run the texture extractor on the ps3 file.

I get Error: the requested amount of bytes to allocate is negative (-1435336832)
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-22T23:32:25+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

then your doing something wrong
## Post #25
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-07-23T01:13:32+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

yea huh lol
thanks anyway
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-23T01:50:59+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

you never posted any screenshots of what you were doing so no one can help.
## Post #27
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-07-23T03:44:27+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

Oh well first i gotta ask, was tha texture extractor for bms or something else?
cuz what if i show a screenshot and it shows me using quickbms and you guys are like "It's not a bms script dumbass"
then i'm like " D: aww damn "
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-23T03:48:22+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

it is a bms the one that says texture extractor it has to be run on the ps3 files.
post a screenshot of what your doing or no one will help.
## Post #29
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-07-23T08:52:49+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

Can someone tell me that where do i have to save the 3DS Max script that's posted on the first post?
## Post #30
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-07-23T11:39:27+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

This is what i was doing



Screen.png (217.96 KiB) Viewed 187 times



But then i thought " wait maybe i was suppost to do it on tha actual .model file (ps3 one) "
so i did, i get tha .dds but it wont open. In 3dmax it says it's in " Unsupported DSS Image File " and photoshop crashes.
I cant add another attachment pic. but ill post it if u need to see.
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-23T11:47:24+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

you need to go to the original extraction thread
[viewtopic.php?f=10&t=6570&p=53763&hilit ... oes#p53763](http://forum.xentax.com/viewtopic.php?f=10&t=6570&p=53763&hilit=No+More+Heroes#p53763)
## Post #32
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-07-23T11:57:38+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

aw man see i didnt even know that thread existed, Thanks again.
## Post #33
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-07-23T14:04:05+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

> Reply from Aurangzeb56
>
> Can someone tell me that where do i have to save the 3DS Max script that's posted on the first post?
Anywhere easy to find.
## Post #34
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-25T10:22:18+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

> Reply from Aurangzeb56
>
> Can someone tell me that where do i have to save the 3DS Max script that's posted on the first post?here we go, anyway thanks a lot chrox very nice work.

C:\Program Files\Autodesk\3ds Max 2009\stdplugs\stdscripts
## Post #35
- Username: Bazerand
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 06, 2011 7:41 am
- Post datetime: 2011-09-06T00:01:35+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

> Reply from chrrox
>
> You extracted 360 models correct?
the ps3 models will not work.
Is this due to the ps3 models not being importable, or is it just a matter of needing its own script? I'd like to mess around with travis/the weapons but I can only get my hands on the ps3 version.
## Post #36
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-06T00:34:43+00:00
- Post Title: Re: No More Heroes: Heroes' Paradise

the ps3 version is using the edge sdk.
that means its using bit level index compression and no one fully understands it yet.
