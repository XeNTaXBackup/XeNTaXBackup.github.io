## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-11T14:31:15+00:00
- Post Title: MadWorld face indices

I'm having trouble with these face indices, they don't make sense to me.
MaxScript:

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fn floatSwap2 f = (
	i = bit.floatAsInt f
	h = bit.intashex i
	while h.count < 8 do h = "0" + h
	
	s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
	bit.intAsFloat (bit.hexasint s)
)	

fn readBEshort fstream = (
	short = readshort fstream #unsigned
	short = bit.swapBytes short 1 2
	return short
)

fn readBElong fstream = (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)

fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
)

fn ReadFixedString bstream fixedLen = (
    local str = ""
    for i = 1 to fixedLen do
    (
        str += bit.intAsChar (ReadByte bstream #unsigned)
    )
    str
)

fn ReadFixedString bstream fixedLen = (
    local str = ""
    for i = 1 to fixedLen do
    (
        str += bit.intAsChar (ReadByte bstream #unsigned)
    )
    str
)

fn ReadBEBAMS fstream = (
	(ReadBEShort fstream /65536)*360
)

clearlistener()
fname = getOpenFileName \ 
caption:"Open File" \
types:"Model Binary(*.mdb)|*.mdb|Data Package(*.dat)|*.dat|*.*|*.*" \
historyCategory:"MadWorldMDB Object Presets"

-- Implement .DAT stuff here--

if fname != undefined do (
f = fopen fname "rb"
filename = GetFilenameFile fname
fseek f 0x0 #seek_end
FileEnd = ftell f
fseek f 0x0 #seek_set

FileIdentifier = readfixedstring f 2
FileVersion = readBEshort f
if FileIdentifier != "JK" then fclose f
VertexCount = readBElong f
VertexOffset = readBElong f
NormalsCount = readBElong f
NormalsOffset = readBElong f
UVCount = readBElong f
UVOffset = readBElong f
UnknownChunk4Count = readBElong f
UnknownChunk4Offset = readBElong f	
BoneRotCount = readBElong f
BoneRotOffset = readBElong f
BoneLinksCount = readBElong f
BoneLinksOffset = readBElong f
BoneLocalOffset = readBElong f
BoneWorldOffset = readBElong f
UnknownChunk7Count = readBElong f
UnknownChunk7Offset = readBElong f
FaceIndexStartCount = readBElong f
FaceIndexStartOffset = readBElong f
Unknown = readBEShort f
Unknown = readBEShort f
Unknown = readBElong f
UnknownChunk8Offset = readBELong f
UnknownChunk9Offset = readBElong f
UnknownChunk10Offset = readBElong f
UnknownChunk11Offset = readBElong f
Unknown = ReadBEShort f
Unknown = readBEShort f

Vert_Array = #()
Normal_Array = #()
Face_Array = #()
UV_Array = #()
Bone_Array = #()
BoneInfo_Array = #()
MatID_Array = #()

struct BoneData (
	BoneID, BoneParent, tfm
)

fseek f VertexOffset #seek_set

Print ("Vertex Buffer start @ 0x"+((bit.intAsHex(ftell f))as string)) -- Needs a flag to determine which type is used
-- for x = 1 to VertexCount do (
-- 	vx = readBEshort f
-- 	vy = readBEshort f
-- 	vz = readBEshort f
-- 	vf = readBEshort f
-- 	append Vert_Array [vx,vy,vz]
-- )
for x = 1 to VertexCount do (
	vx = readBEfloat f
	vy = readBEfloat f
	vz = readBEfloat f
	boneID = readBEshort f
	fseek f 0x2 #seek_cur
	append Vert_Array [vx,vy,vz]
)
Print ("Vertices done @ 0x"+((bit.intAsHex(ftell f))as string))
	
fseek f NormalsOffset #seek_set

Print ("Normals Buffer start @ 0x"+((bit.intAsHex(ftell f))as string))
for x = 1 to NormalsCount do (
	nx = readbyte f as float
	ny = readbyte f as float
	nz = readbyte f as float
	append Normal_Array [nx,ny,nz]
)
Print ("Normals done @ 0x"+((bit.intAsHex(ftell f))as string))

fseek f UVOffset #seek_set
	
Print ("UV Buffer start @ 0x"+((bit.intAsHex(ftell f))as string))
for x = 1 to UVCount do (
	tu = readBEshort f as float
	tv= ((readBEshort f as float) * -1)
	append UV_Array [tv,tu,0]
)
Print ("UVs done @ 0x"+((bit.intAsHex(ftell f))as string))

fseek f BoneRotOffset #seek_set
for x = 1 to BoneRotCount do (
	rx = readBEBAMS f
	ry = readBEBAMS f
	rz = readBEBAMS f
	rw = readBEBAMS f
	tfm = (quat rx ry rz rw) as matrix3
	append BoneInfo_Array (BoneData tfm:tfm)
)
	
fseek f BoneLinksOffset #seek_set
for x = 1 to BoneLinksCount do ( -- This doesn't work
	BoneID = readbyte f+1
	BoneParent = readbyte f+1
	append BoneInfo_Array (BoneData BoneID:BoneID BoneParent:BoneParent)
)
	
fseek f BoneWorldOffset #seek_set
for x = 1 to BoneLinksCount do (
	px = readBEfloat f
	py = readBEfloat f
	pz = readBEfloat f
	tfm = BoneInfo_Array[x].tfm
	tfm.row4 = [px,py,pz]
	newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = ("Bone"+(x as string))
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
-- 	if (BoneInfo_Array[x].BoneParent != 0) then (
-- 	newBone.parent = Bone_Array[(BoneInfo_Array[x].BoneParent)]
-- 	)
	append Bone_Array newBone
)


fseek f FaceIndexStartOffset #seek_set
-- fseek f 0x10980 #seek_set
Print ("Face Buffer Info Start @ 0x"+((bit.intAsHex(ftell f))as string))
while (ftell != FileEnd) do (
start = ftell f
NextSM = readBElong f
fseek f 0x10 #seek_cur	
FaceBufferSize = readBElong f
fseek f 0x8 #seek_cur
MaterialName = readfixedstring f 0x3C
FaceUnknown = readBElong f
FaceUnknown2 = readbyte f
FaceCount = readBEshort f
-- Print ("Face Buffer Start @ 0x"+((bit.intAsHex(ftell f))as string))

for x = 1 to FaceCount do (
f1 = (ReadBEshort f) + 1
f2 = (ReadBEshort f) + 1
f3 = (ReadBEshort f) + 1
-- print (((("f ")+f1 as string)+(" ")+f2 as string)+(" ")+f3 as string)
append Face_Array [f1,f2,f3]
)

-- Print ("Faces done! @ 0x"+((bit.intAsHex(ftell f))as string))
if NextSM != 0 then (
fseek f (start+NextSM) #seek_set
-- Print ("Test @ 0x"+((bit.intAsHex(ftell f))as string))
)
else exit
)	

msh = mesh vertices:Vert_Array faces:Face_Array
msh.numTVerts = Vert_Array.count
msh.name = FileName	
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to msh.numfaces do setFaceSmoothGroup msh j 1

--end of file functions
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
)

```

Sample:


 pl0030.7z
(32.73 KiB) Downloaded 25 times
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-01-11T22:48:23+00:00
- Post Title: MadWorld face indices

Each face index seems to have two additional properties (maybe they're bone related?)
This is how I modified the faces loop to make it work (note that the n and x names are completely arbitrary):

EDIT: Actually the other two are normal indices and UV indices (so normals and UVs are applied per face)

```
f1 = (ReadBEshort f) + 1
n1 = (ReadBEshort f) + 1
x1 = (ReadBEshort f) + 1
f2 = (ReadBEshort f) + 1
n2 = (ReadBEshort f) + 1
x2 = (ReadBEshort f) + 1	
f3 = (ReadBEshort f) + 1
n3 = (ReadBEshort f) + 1
x3 = (ReadBEshort f) + 1

append Face_Array [f3,f2,f1]
append NormalIndex_Array [n3,n2,n1]
append UVIndex_Array [x3,x2,x1]
)
```

[](http://www.imagebam.com/image/fcdb18380796990)
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-13T14:02:00+00:00
- Post Title: MadWorld face indices

In case anyone is wondering how I applied the UVs (took me a few minutes)

```
for j = 1 to UVIndex_array.count do setTVFace msh j UVIndex_array[j]

```
