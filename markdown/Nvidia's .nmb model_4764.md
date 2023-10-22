## Post #1
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-07-17T12:18:04+00:00
- Post Title: Nvidia's .nmb model

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-07-17T23:02:11+00:00
- Post Title: Nvidia's .nmb model

I'm looking for this converter too!
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-18T16:59:30+00:00
- Post Title: Nvidia's .nmb model

[out]
## Post #4
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2010-07-19T05:48:50+00:00
- Post Title: Nvidia's .nmb model

Found something that converted the model into alot of .obj's, you had to import all of them, really pain in the ass >_> I'll look for it again, If I find it I'll let you know.
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-07-22T05:16:18+00:00
- Post Title: Nvidia's .nmb model

SBibi's docs were kinda of thick to read. and his first assumptions about the file structure seemed way off O_o

I don't get why he thought FFFF was a starting tag, since almost always it's used as a closer or terminator to chunk based formats.
anyway I tried to read through the NMB in the Adrianne demo. since it has no scene information, just direct mesh info.

and got a crude import through maxscripitng


I'm not sure exactly how SBibi got the strips to import correctly, so I'll have to read further through his docs

my maxscript only works on Adrianne at the moment. but here's the script, just encase I never get around to it again.

I have to get around to investigating as many IDs as possible, otherwise I need to write a skip from FFFF to FFFF to skip each unknown chunk

EDIT - nevermind, its because I was reading the trilist data as strips.. Adrianne should import now

```
caption:"nmb thingy" types: \
"NMB(*.nmb)|*.nmb|All files (*.*)|*.*|"
f = fopen fsource "rb"
fname = getFilenameFile fsource
fext = getFilenameType fsource
fpath = getFilenamePath fsource
-- f = fopen "G:\\Program Files\\NVidia Corporation\\NVidia Demos\\Adrianne\\models\\geo_model_sample.nmb" "rb"
-- fpath="G:\\Program Files\\NVidia Corporation\\NVidia Demos\\Adrianne\\models\\"



fn ReadFixedString bstream fixedLen = (
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)

uknblock=false


-- Main NMB Header

version=readlong f #unsigned -- always seems to be 01
ukn1=readlong f #unsigned	-- 0x01=SkyBox | 0x04=Effects | 0x0A=Model | 0x0B=Morphs | 0x0C=Animation
itmCount=readlong f #unsigned	-- 48 ?? Count
-- itmCount=1
-- SubHeader

itmArray=#()
datArray=#()
for itm=1 to itmCount do (
PRINT "OK"


wh=ftell f
print wh
blockID=readshort f #unsigned -- 0x31 defines new mesh group / name
blockFormat=readshort f #unsigned -- 
ukn=readlong f #unsigned	-- -1?
chrLength=readlong f #unsigned
	print chrLength
if chrLength>=100 do(
chrLength=20

PRINT "CRAP!1"
wh=ftell f
print wh
		)
objName=ReadFixedString f chrLength
pad=readbyte f #unsigned -- either 1 or 0

pathflag=bit.swapBytes (bit.swapBytes (readlong f #unsigned) 1 4) 2 3
print pathflag
if pathflag!=1 do(
fseek f -1 #seek_cur
chrLength=readlong f #unsigned
	if chrLength>=100 do(
chrLength=20
PRINT "CRAP2!"
wh=ftell f
print wh
		)
filePath=ReadFixedString f chrLength
donno1=readlong f #unsigned -- count? usually 1
donno2=readlong f #unsigned -- size?
donno3=readlong f #unsigned -- 2?
donno4=readlong f #unsigned -- 0?
)
ukn=readlong f #unsigned	-- 10000

subBlockCount=readlong f #unsigned
--subBlockCount=1
append itmArray objName
	
-- DataBlocks
uvwArray=#()
faceArray=#()
vertArray=#()

for dat=1 to subBlockCount do (
PRINT "OK"


wh=ftell f
print wh
blockID=readshort f #unsigned -- 0x22=Vertices | 0x25=Normals | 0x24=UVs | 0x31=MeshGroup
blockFormat=readshort f #unsigned --? 100
ukn=readlong f #unsigned	-- 0?
chrLength=readlong f #unsigned;print chrLength
if chrLength>=100 do(
chrLength=20
PRINT "CRAP3!"
wh=ftell f
print wh
		)
blockName=ReadFixedString f chrLength

ukn5=readlong f #unsigned -- ?count 1
ukn6=readlong f #unsigned -- ?count -1
ukn7=readlong f #unsigned -- ?count 2

entryCount=readlong f #unsigned
	
append datArray blockName
		
if blockID==0x01 do( --Colour Values?
fseek f 44 #seek_cur
terminator=readlong f #unsigned --? always FF
)

if blockID==0x02 do( --Texture List?
fseek f -12 #seek_cur
	
-- do(
-- chrLength=readlong f #unsigned
-- fseek f chrLength #seek_cur
-- ukn5=readlong f #unsigned
-- )
-- while ukn5>=0xFFFFFFFC

)
	
if blockID==0x20 do( --Bone Indecies??
for c = 1 to entryCount do(
bn1=readfloat f
	)
terminator=readlong f #unsigned --? always FF
)


if blockID==0x21 do( --Bone Indecies??
for c = 1 to entryCount do(
bn1=readfloat f
bn1=readfloat f
	)
terminator=readlong f #unsigned --? always FF
)


if blockID==0x22 do(
	uknblock=true
for c = 1 to entryCount do(
vX=readfloat f
vY=readfloat f
vZ=readfloat f;vZ=-vZ
append vertArray[vX,vZ,vY]
	)
terminator=readlong f #unsigned --? always FF
)

if blockID==0x23 do( --Bone Weights
for c = 1 to entryCount do(
bn1=readfloat f
bn2=readfloat f
bn3=readfloat f
bn4=readfloat f
	)
terminator=readlong f #unsigned --? always FF
)

if blockID==0x24 do(
for c = 1 to entryCount do(
tu=readfloat f
tv=readfloat f--;vZ=-vZ
append uvwArray[tu,tv,0]
	)
terminator=readlong f #unsigned --? always FF
	)
	
if blockID==0x25 do(
for c = 1 to entryCount do(
nX=readfloat f
nY=readfloat f
nZ=readfloat f
	)
terminator=readlong f #unsigned --? always FF
)





)-- End of MainHeader







if uknblock==true do(

blockID=readlong f #unsigned -- always 2?
entries=readlong f #unsigned -- ? 2
	
for c = 1 to entries do(
ukn2=readlong f #unsigned -- ? size?
pad=readlong f #unsigned -- ? 0's Padding?
triFormat=readlong f #unsigned -- ? 5
ukn4=readlong f #unsigned -- ? 1
loopCount=(readlong f #unsigned);print loopCount -- ? number of entries
	
--if loopCount>=60000 do loopCount=600000 --Safety precaution, anything more may freeze your PC
PRINT "face data?"
wh=ftell f
print wh

	
if triFormat==3 do(
for c = 1 to loopCount/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append faceArray [fa,fb,fc]
	)
)

if triFormat==5 do(
	
 StartDirection = -1
f1 = (readshort f #unsigned) + 1
f2 = (readshort f #unsigned) + 1
FaceDirection = StartDirection
IndexCounter = 2
Do (
f3 = (readshort f #unsigned)
IndexCounter += 1
if (f3==0xFFFF) then (
f1 = (readshort f #unsigned) + 1
f2 = (readshort f #unsigned) + 1
FaceDirection = StartDirection
IndexCounter += 2
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
if FaceDirection > 0 then append faceArray [f1,f2,f3]
else append faceArray [f1,f3,f2]
)
f1 = f2
f2 = f3
)
) 
while IndexCounter !=loopCount
)






terminator=readlong f #unsigned --? always FF	
)


)


if uvwArray.count == 0 then(
	
msh = mesh vertices:vertArray faces:faceArray   --build mesh
msh.numTVerts = vertArray.count
buildTVFaces msh
msh.name=objName
for j = 1 to vertArray.count     do setTVert  msh j vertArray[j]
for j = 1 to faceArray.count   do setTVFace msh j faceArray[j]
)
else(


msh = mesh vertices:vertArray faces:faceArray   --build mesh
msh.numTVerts = uvwArray.count
buildTVFaces msh
msh.name=objName
for j = 1 to uvwArray.count     do setTVert  msh j uvwArray[j]
for j = 1 to faceArray.count   do setTVFace msh j faceArray[j]
)

terminator=readlong f #unsigned --? always FF

 ) -- End of SubHeaders



	
	

-- print itmArray
-- print datArray

-- if ukn8 !=4096 do(
-- 	
-- 	
-- 	
-- 	
-- StartDirection = -1
-- f1 = (ReadBEword f) + 1
-- f2 = (ReadBEword f) + 1  
-- FaceDirection = StartDirection
-- Do (
-- f3 = (ReadBEword f)
-- if (f3==0xFFFF) then (
-- f1 = (ReadBEword f) + 1
-- f2 = (ReadBEword f) + 1
-- FaceDirection = StartDirection   
-- ) else (
-- f3 += 1
-- FaceDirection *= -1
-- if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
-- if FaceDirection > 0 then append faceArray [f1,f2,f3]
-- else append faceArray [f1,f3,f2]
-- )
-- f1 = f2
-- f2 = f3
-- )  
-- )while (ftell f) != 0x8ADAF









-- 	)


print "Where Am I?"
wh=ftell f
print wh




print "DONE!!"




gc()
fclose f




```
