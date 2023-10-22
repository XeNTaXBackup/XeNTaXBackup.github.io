## Post #1
- Username: kaser
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 14, 2015 12:18 am
- Post datetime: 2015-08-06T18:32:50+00:00
- Post Title: [Help]Dragon Prophet .ros 3D;x

Hi.
I have problem with game Dragon's Prophet, because it has 3d file in .ros format.

I have max script but only model + model_skeleton. I need only  model without bones,,,

This is script:

```
http://pastebin.com/dZqThS1h
```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-08-13T21:32:03+00:00
- Post Title: [Help]Dragon Prophet .ros 3D;x

It would be helpful if you uploaded sample files as well.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-08-31T02:32:02+00:00
- Post Title: [Help]Dragon Prophet .ros 3D;x

> Reply from finale00
>
> It would be helpful if you uploaded sample files as well.ok here we go mate.

[https://dailyuploads.net/nwr6pdp8hwfr](https://dailyuploads.net/nwr6pdp8hwfr)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-31T06:41:45+00:00
- Post Title: [Help]Dragon Prophet .ros 3D;x

that script requires *_skeleton.ros (and the suiting *.ros from the Mesh folder)

for the mesh only u could use hex2obj:



2h-axe_027.JPG (40.14 KiB) Viewed 174 times
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-08-31T21:08:49+00:00
- Post Title: [Help]Dragon Prophet .ros 3D;x

You can use this code, to import just model (static model)

```
	heapSize = 200000000
fname = getOpenFileName \
caption:"Open .ros from Mesh folder" \
types:"Dragon's_Prophet (*.ros)|*.ros" \
historyCategory:"Dragon's_ProphetObjectPresets"
f = fopen fname "rb"

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
struct Bone_Info_Struct
(
	Bone1,Bone2,Bone3,Bone4
)
struct Weight_Info_Struct
(
	Weight1,Weight2,Weight3,Weight4
)
clearlistener()

	
vertArray=#()
faceArray=#()
Normal_array = #()
UVarray=#()
Weight_array=#()
B1_array=#()
W1_array=#()

fseek f 0x34 #seek_set
NSize=ReadLong f
meshname=ReadFixedString f NSize
fseek f 0x50 #seek_cur

check=ReadShort f 
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
if check==14516 then 
for x =1 to 1 do (	
fseek f 50 #seek_cur 
NSize3=ReadLong f
meshname3=ReadFixedString f NSize3
fseek f 0x50 #seek_cur	
fseek f 0x10b #seek_cur--hash	
		
)	

if check==13406 then 
for x =1 to 1 do (	
fseek f 50 #seek_cur 
NSize1=ReadLong f
meshname1=ReadFixedString f NSize1
fseek f 0x50 #seek_cur
check2=ReadShort f 
if check2==14516 then 
for x =1 to 1 do (	
fseek f 50 #seek_cur 
NSize2=ReadLong f
meshname2=ReadFixedString f NSize2
fseek f 0x50 #seek_cur
fseek f 0x6E #seek_cur--hash		
)
if check2==1 then
fseek f 0x68 #seek_cur		
)
if check==1 then fseek f 104 #seek_cur 

VertCount=readlong f
sectionCount=readlong f
CharCount=readlong f
possition=ReadFixedString f CharCount
null=readlong f
id=readlong f 		
	
for x =1 to VertCount do (--vertices
vx = readFloat f
vy = readFloat f
vz = readFloat f	
append vertArray [vx,vz,vy]			
)	

for x =1 to sectionCount-1 do (	
CharCount=readlong f 
CharCount_fixed=(CharCount-2) 
print	CharCount_fixed
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))		
SectionName=ReadFixedString f CharCount_fixed
check_w=readshort f	
print check_w
null=readlong f
id=readlong f
if id==6 then
for x =1 to VertCount do (--normals 6
nx = readFloat f
ny = readFloat f
nz = readFloat f	
append Normal_array [nx,nz,ny]
)
if id==28 then
for x =1 to VertCount do (--colors 28
ffff=readlong f		
)
if id==30 then
for x =1 to VertCount do (--blend indices 30
bone1 = readbyte f #unsigned
bone2 = readbyte f #unsigned
bone3 = readbyte f #unsigned
bone4 = readbyte f #unsigned	
append B1_array (Bone_Info_Struct Bone1:Bone1 Bone2:Bone2 Bone3:Bone3 Bone4:Bone4)		
)
if id==16 then
for x =1 to VertCount do (--uv's 16
tu = readFloat f
tv = readFloat f* -1
append UVarray [tu,tv,0]			
)	
if id==2 then
if check_w==115 then 
for x =1 to VertCount do (--blend weights 2
weight1 = readFloat f
weight2 = readFloat f
weight3 = readFloat f
weight4 = readFloat f	
append W1_array (Weight_Info_Struct Weight1:Weight1 Weight2:Weight2 Weight3:Weight3 Weight4:Weight4)	
)	
for b = 1 to W1_array.count Do (
w = (weight_data boneids:#() weights:#())
maxweight = 0
if(W1_array[b].Weight1 != 0) then
   maxweight = maxweight + W1_array[b].Weight1
if(W1_array[b].Weight2 != 0) then
   maxweight = maxweight + W1_array[b].Weight2
if(W1_array[b].Weight3 != 0) then
   maxweight = maxweight + W1_array[b].Weight3
if(W1_array[b].Weight4 != 0) then
   maxweight = maxweight + W1_array[b].Weight4

if(maxweight != 0) then
   (
      if(W1_array[b].Weight1 != 0) then
      (
         w1 = W1_array[b].Weight1 as float
         append w.boneids (B1_array[b].Bone1 + 1)
         append w.weights (w1)
      )
      if(W1_array[b].Weight2 != 0) then
      (
         w2 = W1_array[b].Weight2 as float
         append w.boneids (B1_array[b].Bone2 + 1)
         append w.weights (w2)
      )
      if(W1_array[b].Weight3 != 0) then
      (
         w3 = W1_array[b].Weight3 as float
         append w.boneids (B1_array[b].Bone3 + 1)
         append w.weights (w3)
      )
      if(W1_array[b].Weight4 != 0) then
      (
         w4 = W1_array[b].Weight4 as float
         append w.boneids (B1_array[b].Bone4 + 1)
         append w.weights (w4)
      )      
   )
append Weight_array w
)
if id==2 then
if check_w!=115 then
for x =1 to VertCount do (--tangent/quaternion 2
t1 = readFloat f
t2 = readFloat f
t3 = readFloat f
t4 = readFloat f		
)
print id
)
fseek f 0x31 #seek_cur
faceid=ReadLong f		
facecount=ReadLong f		
totalfaces=ReadLong f	

for x = 1 to facecount do (
fa=readshort f  + 1
fb=readshort f  + 1
fc=readshort f  + 1
append faceArray [fc,fb,fa] 	
)	
unk1=readlong f 
CharCount=readlong f 
flag=ReadFixedString f CharCount
null=readlong f
id=readlong f
if id==42 then
for x =1 to VertCount do (--flag 42
getPos = ftell f + 16
fseek f getPos #seek_set		
)
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))

msh = mesh vertices:vertArray faces:faceArray
msh.name=meshname
msh.numTVerts = UVarray.count
buildTVFaces msh
for j = 1 to UVarray.count do setTVert msh j UVarray[j]
for j = 1 to faceArray.count do setTVFace msh j faceArray[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]	
	
fclose f
```
