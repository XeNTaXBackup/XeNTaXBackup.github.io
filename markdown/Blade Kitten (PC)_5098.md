## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-27T20:23:27+00:00
- Post Title: Blade Kitten (PC)

I finally have these models working with bones and weighting.
http://img412.images...2/6272/bk1u.png

The models would look like they do in game with the proper cartoon shading.

bms for archives

```
#   Blade Kitten, Game Room, Star Wars: The Clone Wars - Repulic Heroes
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
getdstring NAME 0x40
get DUMMY long  # maybe 64bit
get INFO_OFF long
get DUMMY long
get FILES long
goto INFO_OFF

for i = 0 < FILES
    getdstring NAME 0x40
    get TIMESTAMP longlong
    get ZERO long   # maybe 64bit
    get OFFSET long
    get CRC long
    get SIZE long
    get ZSIZE long
    get ZERO long

    if SIZE == ZSIZE
        log NAME OFFSET SIZE
    else
        savepos TMP
        goto OFFSET
        get TYPE byte
        if TYPE == 2
            comtype lzf
        else
            print "unknown compression method (%TYPE%), contact me"
            cleanexit
        endif
        goto TMP

        math OFFSET += 1    # first byte is 0x02
        math ZSIZE  -= 1
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

```


and the max script
This only works on character models not stage models so you will get an error if you try to import models that start with p.

```
if (heapSize < 200000) then
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \
caption:"Blade Kitten Model File" \
types:"Blade Kitten Model File(*.mdg)|*.mdg" \
historyCategory:"Blade KittenObjectPresets"
f = fopen fname "rb"
t = getFilenameType fname -- returns the type "obj"
p = getFilenamePath fname -- return the path "c:\\test\\"
h = getFilenameFile fname -- return the file "test"
fname2 = (p + h) + ".mdlb"
g = fopen fname2 "rb"

struct weight_data
(
    boneids,weights
)
struct Mesh_data
(
    facestart,vertstart,vertcount,facecount,sectid1
)

fn PrintOffset Var =
(
    local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
    Var
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




idstring = readlong g
unk01 = readlong g
MeshCount = readlong g
Mesh2Count = readlong g
MainSectionCount = readlong g
unk05 = readlong g
unk06 = readlong g
unk07 = readlong g
unk08 = readlong g
unk09 = readlong g
unk10 = readlong g
Mesh3Count = readlong g
unk12 = readlong g
unk13 = readlong g
unk14 = readlong g
unk15 = readlong g
unk16 = readlong g
unk17 = readlong g
unk18 = readlong g
unk19 = readlong g
---- 0x50 section
fseek g 0x20#seek_cur
SectionAOffset = readlong g
NameOffsetTable = readlong g
MeshOffsetTable = readlong g
Null00 = readlong g
MDGOffsetTable = readlong g
FileStructureTable = readlong g
FaceTableOffset= readlong g
BoneSectionOffset = readlong g
Null01 = readlong g
Null02 = readlong g
BoneLookupTable = readlong g
Null03 = readlong g
---- 0x40 sections * mesh count
fseek g FaceTableOffset#seek_set
FaceOffsetStart_Array = #()
for a = 1 to MainSectionCount Do (
FaceOffsetStart = readlong g
fseek g 0xC#seek_cur
append FaceOffsetStart_Array FaceOffsetStart
)
fseek g NameOffsetTable#seek_set
for a = 1 to MeshCount Do (
MeshNameOffset = readlong g
)
fseek g MeshOffsetTable#seek_set
MeshTableOffset = readlong g
while MeshTableOffset == 0 do (
MeshTableOffset = readlong g
)
fseek g MeshTableOffset#seek_set
Mesh_Data_array = #()
meshcount2 = (MDGOffsetTable - MeshTableOffset) / 0x40
id4Array = #()
for a = 1 to meshcount2 Do (
fseek g 0xC#seek_cur
id1 = readbyte g#unsigned
id2 = readbyte g#unsigned
id3 = readbyte g#unsigned
id4 = readbyte g#unsigned

vertstart = readlong g
facestart = readlong g
Facecount = readlong g
Vertcount = readshort g
sectid1 = readbyte g#unsigned
sectid2 = readbyte g#unsigned
fseek g 0x20#seek_cur
append Mesh_Data_array (Mesh_data facestart:facestart vertstart:vertstart vertcount:vertcount facecount:facecount sectid1:sectid1)
append id4Array id3
)
File_Structure_array = #()
File_Structure_array1 = #()
File_Structure_array2 = #()
fseek g FileStructureTable#seek_set
for a = 1 to (4 * MainSectionCount) do (
unk01 = readlong g
SectionStart = readlong g
unk03 = readlong g
SectionCount = readlong g
SectionSize = readlong g
unk06 = readlong g
unk07 = readlong g
unk08 = readlong g   
append File_Structure_array SectionStart
append File_Structure_array1 SectionCount
append File_Structure_array2 SectionSize
)

fseek g BoneSectionOffset#seek_set
BoneTableStart = readlong g
type = readlong g
if type != 0xC do (
fseek g 0x8#seek_cur
BoneTableStart = readlong g
)
fseek g BoneTableStart#seek_set
BoneCount = readlong g
BoneParentOffset = readlong g
BoneMatrixOffset = readlong g
null = readlong g
BoneNameOffset = readlong g

Bone_Parent_array = #()
Bone_Matrix_array = #()
Bone_Name_array = #()

fseek g (BoneTableStart + BoneParentOffset)#seek_set
for a = 1 to BoneCount Do (
fseek g 0x10#seek_cur
BoneParent = readlong g
Unk01 = readlong g
BoneNameof = readlong g
Unk02 = readlong g
append Bone_Parent_array BoneParent
)
fseek g (BoneTableStart + BoneMatrixOffset)#seek_set
for a = 1 to BoneCount Do (
m11 = readfloat g; m12 = readfloat g; m13 = readfloat g; m14 = readfloat g
m21 = readfloat g; m22 = readfloat g; m23 = readfloat g; m24 = readfloat g
m31 = readfloat g; m32 = readfloat g; m33 = readfloat g; m34 = readfloat g
m41 = readfloat g; m42 = readfloat g; m43 = readfloat g; m44 = readfloat g
tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
append Bone_Matrix_array tfm
)
fseek g (BoneTableStart + BoneNameOffset)#seek_set
for a = 1 to BoneCount Do (
BoneName = readstring g
append Bone_Name_array BoneName
)

BNArr = #()
for i = 1 to BoneCount Do (
BoneName = Bone_Name_array[i]
BoneParentID = Bone_Parent_array[i]
tfm = Bone_Matrix_array[i]
    newBone = bonesys.createbone    \
                  tfm.row4    \
                  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
                  (normalize tfm.row3)
            newBone.name   = BoneName
            newBone.width  = 0.3
            newBone.height = 0.3
            newBone.transform = tfm
            newBone.wirecolor = yellow
            newbone.showlinks = true
            newBone.setBoneEnable false 0
            newBone.pos.controller      = TCB_position ()
            newBone.rotation.controller = TCB_rotation ()


if (BoneParentID != -1) then
newBone.parent = BNArr[BoneParentID + 1]

append BNArr newBone
)

for a = 1 to meshcount2 do (
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()
Weight_array = #()
fseek f (File_Structure_array[(1 + (Mesh_Data_array[a].sectid1 * 4))] + (Mesh_Data_array[a].vertstart * 0xC))#seek_set
for b = 1 to Mesh_Data_array[a].vertcount do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz]
)
fseek f (File_Structure_array[(2 + (Mesh_Data_array[a].sectid1 * 4))] + (Mesh_Data_array[a].vertstart * 0x8))#seek_set
for b = 1 to Mesh_Data_array[a].vertcount do (
tu = readfloat f
tv = readfloat f * -1
append UV_array [tu,tv,0]
)

fseek f (File_Structure_array[(4 + (Mesh_Data_array[a].sectid1 * 4))] + (Mesh_Data_array[a].vertstart * 0x8))#seek_set
for b = 1 to Mesh_Data_array[a].vertcount do (
bone1 = readbyte f#unsigned
bone2 = readbyte f#unsigned
bone3 = readbyte f#unsigned
bone4 = readbyte f#unsigned
weight1 = readbyte f#unsigned
weight2 = readbyte f#unsigned
weight3 = readbyte f#unsigned
weight4 = readbyte f#unsigned

w = (weight_data boneids:#() weights:#())
maxweight = 0
   
if(weight1 != 0) do (
    maxweight = maxweight + weight1
)
if(weight2 != 0) do (
    maxweight = maxweight + weight2
)
if(weight3 != 0) do (
    maxweight = maxweight + weight3
)
if(weight4 != 0) do (
    maxweight = maxweight + weight4
)
if(maxweight != 0) do (
            if(weight1 != 0) do (
            w1 = weight1 as float
            append w.boneids (bone1 + 1) --BoneID_array[bone1+1])
            append w.weights (w1 / 255.0) )
            if(weight2 != 0) do (
            w2 = weight2 as float
            append w.boneids (bone2+1) --BoneID_array[bone1+1])
            append w.weights (w2 / 255.0) )
            if(weight3 != 0) do (
            w3 = weight3 as float
            append w.boneids (bone3 + 1) --BoneID_array[bone1+1])
            append w.weights (w3 / 255.0) )
            if(weight4 != 0) do (
            w4 = weight4 as float
            append w.boneids (bone4 + 1) --BoneID_array[bone1+1])
            append w.weights (w4 / 255.0) ) )
append Weight_array w
        )


fseek f (FaceOffsetStart_Array[(Mesh_Data_array[a].sectid1 + 1)] + (Mesh_Data_array[a].facestart * 0x2))#seek_set
for b = 1 to Mesh_Data_array[a].facecount / 3 do (
f1 = (readshort f) + 1   --read face indices, games are start form 0, but Max start from 1
f2 = (readshort f) + 1   --so we add 1 to each index
f3 = (readshort f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--msh.name = GroupName + "_" + (c as string)
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

fseek g (BoneLookupTable + (id4array[a] * 0x101))#seek_set
boneidcount = readbyte g#unsigned
UsedBoneIdArray = #()
for a = 1 to boneidcount do (
bid = readbyte g#unsigned + 1
append UsedBoneIdArray bid
    )

max modify mode
select msh
skinMod = skin ()
addModifier msh skinMod
for i = 1 to  UsedBoneIdArray.count do
(
        maxbone = getnodebyname  BNArr[(UsedBoneIdArray[i])].name
        if i !=  UsedBoneIdArray.count then
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
clearSelection()
max create mode
)
fclose f     --close file
fclose g


```
## Post #2
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-28T13:15:00+00:00
- Post Title: Blade Kitten (PC)

wow,this is aweeeeeeeesome chroxx
Thanks a lot for sharing
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-29T01:54:08+00:00
- Post Title: Blade Kitten (PC)

Which tool do you use to convert textures (.mktx.tex)?
## Post #4
- Username: LoneTiger
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 16, 2010 3:51 am
- Post datetime: 2010-11-01T21:10:24+00:00
- Post Title: Blade Kitten (PC)

This is relevant to my interests.

The "max script" is the one to extract/convert from the "mkmesh.mdg" files?
though I am curious on how to convert or extract the art files from "meg.bin" or "min.bin" files.
## Post #5
- Username: jiforce
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 03, 2010 11:31 am
- Post datetime: 2010-11-05T02:42:52+00:00
- Post Title: Blade Kitten (PC)

Success!!   

[http://i56.tinypic.com/fk63ab.png](http://i56.tinypic.com/fk63ab.png)

I did not convert the tex files from the archive, but I used a program called TexMod to attach itself to the game executable and extract the textures directly from the executable itself.

TexMod: [http://social.bioware.com/bw_projects_f ... le_id=2924](http://social.bioware.com/bw_projects_file_download.php?project_file_id=2924) 

Read the readme in the zip for instructions.

Some antivirus prgms will identify texmod as malware and block it, so turn the antivirus off when it happens.

Steam causes problems with texmod. To get it to work with Steam, follow these steps:
1. Move TexMod to the Binaries folder.
2. Rename bladekitten.exe to bladekittenBak.exe.
3. Rename Texmod.exe to bladekitten.exe

Have fun guys!
## Post #6
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-11-05T18:09:34+00:00
- Post Title: Blade Kitten (PC)

The tex files are just dds files without the header. the header info is at the end.
## Post #7
- Username: Rives
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 06, 2011 7:57 pm
- Post datetime: 2011-02-06T12:02:43+00:00
- Post Title: Blade Kitten (PC)

That's a pretty nifty script there, but it's not working for me. It barfs up a "Unable to convert: undefined to type: Integer" error. What gives?
## Post #8
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-08T14:31:39+00:00
- Post Title: Blade Kitten (PC)

thanks a lot chrrox
## Post #9
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2017-12-25T21:45:05+00:00
- Post Title: Blade Kitten (PC)

Can't open some Kit models. Namely "a905_justicestealth.mkmesh.mdg" and "a922_gingerbunny.mkmesh.mdg". Plus some others.
## Post #10
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-26T00:39:21+00:00
- Post Title: Blade Kitten (PC)

> Reply from lezisell
>
> Can't open some Kit models. Namely "a905_justicestealth.mkmesh.mdg" and "a922_gingerbunny.mkmesh.mdg". Plus some others.If I recall, it's because they have additional colour values which the script doesn't account for. I managed to get 'em both to import with some adjustments, but I'm sure it'd be possible to revise it to automatically detect that (like some header flags or buffer information, or something along the lines).
## Post #11
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2017-12-26T07:02:11+00:00
- Post Title: Blade Kitten (PC)

So, it is possible to fix max script? Can you do it, please? Because i know nothing about that.
## Post #12
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2018-10-13T16:34:27+00:00
- Post Title: Blade Kitten (PC)

Sorry for the big bump, but Jimmy Neutron: Jet Fusion uses a similar format.
[https://puu.sh/BKpQp.zip](https://puu.sh/BKpQp.zip)
## Post #13
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-10T06:42:32+00:00
- Post Title: Blade Kitten (PC)

Any chance this can get support for Viva Pinata Party Animals? I've tried using the script on the character models in the past and it doesn't really work.
