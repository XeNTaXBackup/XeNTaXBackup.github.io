## Post #1
- Username: joqqy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-19T02:34:30+00:00
- Post Title: Heaven of the three kingdoms

Here is a max script to import these models I only tested it on this model I attached here so if it does not work on other models let me know.


Max script save into a text document and give it the extension .ms

```
	heapSize = 40000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = GetOpenFileName caption:"Open Clare3d Model File" types:"Clare3d Model File(*.c3m)|*.c3m"
f = fopen fname "rb"   --open file in read only format
p = getFilenamePath fname


fseek f 0x20 #seek_set
Count1 = readlong f
Null1 = readlong f
Count2 = readlong f
Null2 = readlong f
Null3 = readlong f
Null4 = readlong f
Count3 = readlong f
MeshNumber = readlong f
VertCount = readlong f
FaceCount = readlong f

fn readword fstream = (
return (readshort fstream #unsigned)
)
VertexOffset = ftell f
fseek f (0x20 * VertCount)#seek_cur
FaceOffset = ftell f
fseek f (0x2 * FaceCount)#seek_cur
TableOffset = ftell f

for aa = 1 to MeshNumber do (
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()
Mesh_array = #() 
fseek f TableOffset #seek_set
fseek f 0x44 #seek_cur
VertOffsetAdd = readlong f
FaceOffsetAdd = readlong f
VertCountAdd = readlong f
FaceCountAdd = readlong f
float1 = readfloat f
float2 = readfloat f
float3 = readfloat f
Null1 = readlong f
Null2 = readlong f
DiffuseTexture = readstring f
skipbytes = 0x20 - DiffuseTexture.count - 1
fseek f skipbytes #seek_cur
fseek f 0x20 #seek_cur
append Mesh_array VertOffsetAdd
append Mesh_array FaceOffsetAdd
append Mesh_array VertCountAdd
append Mesh_array FaceCountAdd
append Mesh_array DiffuseTexture
TableOffset = ftell f

fseek f ((Mesh_array[1] * 0x20) + VertexOffset)#seek_set
for i = 1 to Mesh_array[3] Do (
vx = readfloat f     --read xyz coordinates
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz] --save verts to Vert_array
        --since UV in Max are in point3 format, so we add 0 for z value
nx = readlong f    --read Normal ??
ny = readlong f
nz = readlong f
append Normal_array [nx,ny,nz] --save normals to Normal_array
tu = readfloat f     --read UV float value
tv = (readfloat f) * -1 
append UV_array [tu,tv,0]  --save UVs to UV_array
)
fseek f ((Mesh_array[2] * 0x2) + FaceOffset)#seek_set
for i = 1 to Mesh_array[4] / 3 Do (

f1 = (readword f) + 1   --read face indices, games are start form 0, but Max start from 1
f2 = (readword f) + 1   --so we add 1 to each index
f3 = (readword f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.material = meditMaterials[aa]
meditMaterials[aa].name = Mesh_array[5]
meditMaterials[aa].diffuseMap = Bitmaptexture fileName:(p + Mesh_array[5] + ".dds")
meditMaterials[aa].opacityMap = copy meditMaterials[aa].diffuseMap
meditMaterials[aa].diffuseMap.alphaSource = 2
meditMaterials[aa].opacityMap.monoOutput = 1
meditMaterials[aa].opacityMapEnable = on

for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
actionMan.executeAction 0 "40021"  -- Selection: Select All
modPanel.addModToSelection (Normalmodifier ()) ui:on
$Object01.modifiers[#Normal].flip = on
actionMan.executeAction 0 "311"  -- Tools: Zoom Extents All Selected
clearSelection()
actionMan.executeAction 0 "63508"  -- Views: Standard Display with Maps
fclose f     --close file

```

[http://three.hanbiton.com/Home/Home.aspx](http://three.hanbiton.com/Home/Home.aspx)
[horse.rar](https://xentaxbackup.github.io/file/2744_horse.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-19T13:00:54+00:00
- Post Title: Heaven of the three kingdoms

script has been updated corrected a small bug with texture name length.
[bull1.png](https://xentaxbackup.github.io/file/2745_bull1.png)
## Post #3
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2014-06-14T02:27:02+00:00
- Post Title: Heaven of the three kingdoms

Hello, I extract The heaven of three kingdoms file is not c3m format, isn't it The same game?

Translation of English, I'm sorry

This is my unzip the files:

[http://www.4shared.com/rar/qRGL0UuKba/npc.html](http://www.4shared.com/rar/qRGL0UuKba/npc.html)

it is .gmd,gsi,gut,gutx.
## Post #4
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-06-17T14:27:27+00:00
- Post Title: Heaven of the three kingdoms

sorry, on  the link for download Client are much errors, you need an Korea Pass for registering, but 1% of europe people has that, chroox can you send us an link to download the Client for unpacking that ?

or can you upload on mega or other upload company!

Nice greetings and thanks for help
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-06-17T22:35:40+00:00
- Post Title: Heaven of the three kingdoms

how unpack game files, is possible provide it? many thanks for support.
## Post #6
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2014-06-20T02:03:09+00:00
- Post Title: Heaven of the three kingdoms

I here only one client connection in 2011, not the latest

client:

[http://games.sina.com.cn/z/three/download.shtml](http://games.sina.com.cn/z/three/download.shtml)

Unzip the files here, the author is fatduck

[http://gameresearch.haotui.com/thread-398-1-1.html](http://gameresearch.haotui.com/thread-398-1-1.html)

Translation of English, I'm sorry
## Post #7
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2014-06-24T08:37:52+00:00
- Post Title: Heaven of the three kingdoms

Anyone can crack a model?
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-22T10:03:03+00:00
- Post Title: Heaven of the three kingdoms

> Reply from chrrox
>
> Here is a max script to import these models I only tested it on this model I attached here so if it does not work on other models let me know.


Max script save into a text document and give it the extension .ms
Code: Select allif (heapSize < 20000000) then
	heapSize = 40000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = GetOpenFileName caption:"Open Clare3d Model File" types:"Clare3d Model File(*.c3m)|*.c3m"
f = fopen fname "rb"   --open file in read only format
p = getFilenamePath fname


fseek f 0x20 #seek_set
Count1 = readlong f
Null1 = readlong f
Count2 = readlong f
Null2 = readlong f
Null3 = readlong f
Null4 = readlong f
Count3 = readlong f
MeshNumber = readlong f
VertCount = readlong f
FaceCount = readlong f

fn readword fstream = (
return (readshort fstream #unsigned)
)
VertexOffset = ftell f
fseek f (0x20 * VertCount)#seek_cur
FaceOffset = ftell f
fseek f (0x2 * FaceCount)#seek_cur
TableOffset = ftell f

for aa = 1 to MeshNumber do (
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()
Mesh_array = #() 
fseek f TableOffset #seek_set
fseek f 0x44 #seek_cur
VertOffsetAdd = readlong f
FaceOffsetAdd = readlong f
VertCountAdd = readlong f
FaceCountAdd = readlong f
float1 = readfloat f
float2 = readfloat f
float3 = readfloat f
Null1 = readlong f
Null2 = readlong f
DiffuseTexture = readstring f
skipbytes = 0x20 - DiffuseTexture.count - 1
fseek f skipbytes #seek_cur
fseek f 0x20 #seek_cur
append Mesh_array VertOffsetAdd
append Mesh_array FaceOffsetAdd
append Mesh_array VertCountAdd
append Mesh_array FaceCountAdd
append Mesh_array DiffuseTexture
TableOffset = ftell f

fseek f ((Mesh_array[1] * 0x20) + VertexOffset)#seek_set
for i = 1 to Mesh_array[3] Do (
vx = readfloat f     --read xyz coordinates
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz] --save verts to Vert_array
        --since UV in Max are in point3 format, so we add 0 for z value
nx = readlong f    --read Normal ??
ny = readlong f
nz = readlong f
append Normal_array [nx,ny,nz] --save normals to Normal_array
tu = readfloat f     --read UV float value
tv = (readfloat f) * -1 
append UV_array [tu,tv,0]  --save UVs to UV_array
)
fseek f ((Mesh_array[2] * 0x2) + FaceOffset)#seek_set
for i = 1 to Mesh_array[4] / 3 Do (

f1 = (readword f) + 1   --read face indices, games are start form 0, but Max start from 1
f2 = (readword f) + 1   --so we add 1 to each index
f3 = (readword f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.material = meditMaterials[aa]
meditMaterials[aa].name = Mesh_array[5]
meditMaterials[aa].diffuseMap = Bitmaptexture fileName:(p + Mesh_array[5] + ".dds")
meditMaterials[aa].opacityMap = copy meditMaterials[aa].diffuseMap
meditMaterials[aa].diffuseMap.alphaSource = 2
meditMaterials[aa].opacityMap.monoOutput = 1
meditMaterials[aa].opacityMapEnable = on

for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
actionMan.executeAction 0 "40021"  -- Selection: Select All
modPanel.addModToSelection (Normalmodifier ()) ui:on
$Object01.modifiers[#Normal].flip = on
actionMan.executeAction 0 "311"  -- Tools: Zoom Extents All Selected
clearSelection()
actionMan.executeAction 0 "63508"  -- Views: Standard Display with Maps
fclose f     --close file

http://three.hanbiton.com/Home/Home.aspxHi chrrox, I have clients that do not fit the script, can you give a client download link, thanks
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-08T07:18:27+00:00
- Post Title: Heaven of the three kingdoms

Hi

Here is  blender version of chrrox maxscript and support animation too.
It requires Blender version 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select gmd file
3.for animation select gam file

Game:   [viewtopic.php?p=95613#p95613](http://forum.xentax.com/viewtopic.php?p=95613#p95613)
[Blender249[HeavenOfTheThreeKingdoms][gmd][gam][2014-12-05].zip](https://xentaxbackup.github.io/file/8217_Blender249[HeavenOfTheThreeKingdoms][gmd][gam][2014-12-05].zip)
## Post #10
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-10T18:04:26+00:00
- Post Title: Heaven of the three kingdoms

> Reply from Szkaradek123
>
> Hi

Here is  blender version of chrrox maxscript and support animation too.
It requires Blender version 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select gmd file
3.for animation select gam file

Game:   viewtopic.php?p=95613#p95613Good news, thank you, Szkaradek123, the script is very good, we import model GMD files, but note that not all of the GMD is a model file, thanks again, Szkaradek123
## Post #11
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-12-11T00:55:18+00:00
- Post Title: Heaven of the three kingdoms

Here is the quickbms for the game, so you don't have to register on random chinese site:

```
# Package: pfs
# by Fatduck Jun 2014
# script for QuickBMS http://quickbms.aluigi.org

idstring "XGFILESYSTEM\0"

get RESEND asize
savepos RESPOS
do 
goto RESPOS
get ukn0 long
get RESTYPE long
getdstring RESNAME 0x100
get CSIZE long
get USIZE long
get ukn00 long
get NEXTOFS long
get DATAFLAG long
savepos RESPOS
if DATAFLAG == 1
clog RESNAME RESPOS CSIZE USIZE
endif
math RESPOS += CSIZE
while RESPOS < RESEND
```
