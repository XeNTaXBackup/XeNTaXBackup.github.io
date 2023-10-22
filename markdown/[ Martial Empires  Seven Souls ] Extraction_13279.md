## Post #1
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-09-04T08:43:34+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

To extract the VFS content need to do this steps:
1. Download QuickBMS 
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
2. Copy this Script and save it with .bms extension 

```
#from chrrox and aluigi
open FDDE VFS 0
open FDDE INF 1

get id longlong 1
get files long 1
goto 0x48 1
for i = 0 < files
    getdstring name 0xD8 1
    get ZIPPED long 1
    get DUMMY long 1
    get offset longlong 1
    get zsize longlong 1
    get size longlong 1
    get TIMESTAMP longlong 1
    get TIMESTAMP longlong 1
    get TIMESTAMP longlong 1
    if ZIPPED == 0
        log name offset zsize
    else
        clog name offset zsize size
    endif
next i

```

3. Run quickbms_4gb_files.exe 
3.1 Choose the script created in the step 2 
3.2 Choose any vfs file for example: char.vfs 
3.3 Choose the location folder where you wish to extract the content. 
After extract the content you can import the 3D in 3DS max , i use version 2010 x64.

A. Characters

	Characters is the easier to import in 3DS max, the script needed is here:

```
	heapSize = 200000000

fname = GetOpenFileName caption:"Open 7 Souls Model File" types:"7 Souls Model File(*.msh)|*.msh"
f = fopen fname "rb"
base = getFilenamePath fname
basefile = getFilenameFile fname
basefile = substring basefile 3 (basefile.count - 2)
ss = substring base 1 (base.count - 5)
print basefile
print ss
DiffuseTex = (ss + "texture\diffuse\4" + basefile + ".dds")

print DiffuseTex
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

Vert_array = #()
Normal_array = #()
UV_array = #()
Face_Array = #()
Weight_array = #()
VertID_array = #()

idstring2 = ReadFixedString  f 4
if idstring2 != "MESH" do (
BoneFile = readlong f
Skelleton = (ss + "bind\g" + (BoneFile as string) + ".bnd")
print Skelleton
print ("BoneFile" + "_" + (BoneFile as string))
Mesh_Name_Size = readlong f
Mesh_Name = ReadFixedString  f Mesh_Name_Size
vertcount = readlong f
facecount = readlong f
weightcount = readlong f
weightcount2 = readlong f
for i = 1 to vertcount do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
nx = readfloat f
ny = readfloat f
nz = readfloat f
tu = readfloat f
tv = readfloat f * -1
append Vert_array [vx,vy,vz]
append UV_array [tu,tv,0]
append Normal_array [nx,ny,nz]
)
facedirection = 1
for i = 1 to facecount  do (
f1 = readlong f + 1
f2 = readlong f + 1
f3 = readlong f + 1
append Face_array [f1,f2,f3]
)
for i = 1 to weightcount do (
boneids = ((readlong f) + 1)
VertID = ((readlong f) + 1)
weights = readfloat f
v2 = readlong f
w2 = readfloat f
v3 = readlong f
w3 = readfloat f
v4 = readlong f
w4 = readfloat f
append Weight_array (weight_data boneids:boneids weights:weights)
append VertID_array VertID
)
for i = 1 to weightcount2 do (
bone1 = readlong f
VertID = ((readlong f) + 1)
weight1 = readfloat f
w = (weight_data boneids:#() weights:#())
			w1 = weight1 as float
			append w.boneids (bone1+1)
			append w.weights (w1)
v2 = readlong f
w2 = readfloat f
v3 = readlong f
w3 = readfloat f
v4 = readlong f
w4 = readfloat f
append Weight_array w
append VertID_array VertID
)
print (ftell f)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
meditMaterials[1] = Standardmaterial ()
msh.material = meditMaterials[1]
meditMaterials[1].diffuseMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap.monoOutput = 1
msh.name = Mesh_Name
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
print (ftell f)
usedbones_array = #()
if idstring2 == "MESH" do (
mcount = readlong f
mid = readlong f
BoneFile = readlong f
Skelleton = (ss + "bind\g" + (BoneFile as string) + ".bnd")
print Skelleton
print ("BoneFile" + "_" + (BoneFile as string))
Mesh_Name_Size = readlong f
Mesh_Name = ReadFixedString  f Mesh_Name_Size
vertcount = readlong f
facecount = readlong f
for i = 1 to vertcount do (

vx = readfloat f
vy = readfloat f
vz = readfloat f
nx = readfloat f
ny = readfloat f
nz = readfloat f
tu = readfloat f
tv = readfloat f * -1
if mcount == 2 Do (
fseek f 0x10#seek_cur
)
Bone1 = readbyte f#unsigned
Bone2 = readbyte f#unsigned
Bone3 = readbyte f#unsigned
Bone4 = readbyte f#unsigned
weight1 = readfloat f
weight2 = readfloat f
weight3 = readfloat f
weight4 = readfloat f

w = (weight_data boneids:#() weights:#())
maxweight = 0
if(Bone1 != 0) then
	maxweight = maxweight + weight1
if(Bone2 != 0) then
	maxweight = maxweight + weight2
if(Bone3 != 0) then
	maxweight = maxweight + weight3
if(Bone4 != 0) then
	maxweight = maxweight + weight4

if(maxweight != 0) then (
		if(weight1 != 0) then (
			w1 = weight1 as float
			append w.boneids (bone1 + 1)
			append w.weights w1
		)
		if(weight1 != 0) then (
			w2 = weight2 as float
			append w.boneids (bone2 + 1)
			append w.weights w2
		)
		if(weight1 != 0) then (
			w3 = weight3 as float
			append w.boneids (bone3 + 1)
			append w.weights w3
		)
		if(weight1 != 0) then (
			w4 = weight4 as float
			append w.boneids (bone4 + 1)
			append w.weights w4
		)		
	)
append Weight_array w
append Vert_array [vx,vy,vz]
append UV_array [tu,tv,0]
append Normal_array [nx,ny,nz]
)
if mcount == 2 Do (
usedbones = readbyte f#unsigned
for a = 1 to usedbones do (
bid = readbyte f#unsigned + 1
append usedbones_array bid
)
)
facedirection = 1
if mcount == 2 Do (
for i = 1 to facecount  do (
f1 = readshort f + 1
f2 = readshort f + 1
f3 = readshort f + 1
append Face_array [f1,f2,f3]
)
)
if mcount == 1 Do (
for i = 1 to facecount  do (
f1 = readlong f + 1
f2 = readlong f + 1
f3 = readlong f + 1
append Face_array [f1,f2,f3]
)
)
print (ftell f)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
meditMaterials[1] = Standardmaterial ()
msh.material = meditMaterials[1]
meditMaterials[1].diffuseMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap.monoOutput = 1
msh.name = Mesh_Name
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
actionMan.executeAction 0 "63508"

fclose f
f = fopen Skelleton "rb"
idstring = ReadFixedString f 4
BNArr = #()
if idstring != "BIND" Do (
nsize = readlong f
skelname = ReadFixedString f nsize
bonecount = readlong f
for a = 1 to bonecount Do (
boneid = readlong f + 1
boneparent = readlong f + 1
f1 = readfloat f
f2 = readfloat f
f3 = readfloat f
f4 = readfloat f
f5 = readfloat f
f6 = readfloat f
f7 = readfloat f
tfm = (quat f4 f5 f6 (f7 * -1)) as matrix3
tfm.row4 = [f1,f2,f3]
if isvalidnode (getNodeByName (a as string)) != true then (
if (boneparent != boneid) do (
tfm = tfm * BNArr[boneparent].objecttransform
 )	
newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = (a as string)
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (boneparent != 0) then
 newBone.parent = BNArr[boneparent]
append BNArr newBone
)
)
)

if idstring == "BIND" Do (
fseek f 0x8#seek_cur
nsize = readlong f
skelname = ReadFixedString f nsize
bcount1 = readbyte f#unsigned
bcount2 = readbyte f#unsigned
bonecount  = (bcount1 + bcount2)
for a = 1 to bonecount Do (
boneid = readlong f + 1
boneparent = readlong f + 1
f1 = readfloat f
f2 = readfloat f
f3 = readfloat f
f4 = readfloat f
f5 = readfloat f
f6 = readfloat f
f7 = readfloat f
null = readbyte f#unsigned
tfm = (quat f4 f5 f6 (f7 * -1)) as matrix3
tfm.row4 = [f1,f2,f3]
if isvalidnode (getNodeByName (a as string)) != true then (
if (boneparent != boneid) do (
tfm = tfm * BNArr[boneparent].objecttransform
 )	
newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = (a as string)
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (boneparent != 0) then
 newBone.parent = BNArr[boneparent]
append BNArr newBone
)
)
)
max modify mode
print idstring
if idstring2 != "MESH" do (
msh = $*
select msh
skinMod = skin ()
addModifier msh skinMod
/*	
for i = 1 to BNArr.count do
(
	maxbone = getnodebyname BNArr[i].name
	if i != BNArr.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod
for i = 1 to Weight_array.count do
(
	skinOps.SetVertexWeights skinMod VertID_array[i] Weight_array[i].boneids Weight_array[i].weights
)*/
)

if idstring2 == "MESH" do (
if mcount == 2 Do (
BNArr = #()
for a = 1 to usedbones_array.count do (
append BNArr (getnodebyname (usedbones_array[a] as string))
)
)
msh = $*
select msh
skinMod = skin ()
addModifier msh skinMod/*
for i = 1 to BNArr.count do
(
	maxbone = getnodebyname BNArr[i].name
	if i != BNArr.count then
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
)*/
)

max create mode
max zoomext sel all
fclose f
	
```


	Copy it and save as .ms, then go to "MAX Script" > "Run Script", choose the script.ms created and after choose the file.msh you wish import.
B. Weapons

        To extract weapons we gonna use "Noesis":

Download » [https://dl.dropboxusercontent.com/u/789 ... v40999.zip](https://dl.dropboxusercontent.com/u/7899346/jkhub/jka/utilities/noesisv40999.zip)

        Before continue is needed add the next script inside the folder "plugins\python\":

```

from inc_noesis import *
import noesis
import rapi
import os

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("Seven Souls", ".msh")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    # file ID is the numeric part of the filename
    filename = rapi.getLocalFileName(rapi.getInputName())
    fileID = ''.join(c for c in filename if c.isdigit())
    bs = NoeBitStream(data)
    idstring = bs.readUInt()
    if idstring == int(fileID) or idstring == 1213416781: #MESH
        return 1
    return 0

def noepyLoadModel(data, mdlList):
    '''Build the model, set materials, bones, and animations. You do not
    need all of them as long as they are empty lists (they are by default)'''
    
    ctx = rapi.rpgCreateContext()
    filename = rapi.getLocalFileName(rapi.getInputName())
    fileID = ''.join(c for c in filename if c.isdigit())    
    bs = NoeBitStream(data)
    idstring = bs.readUInt()
    idstring2 = bs.readUInt()
    
    if idstring == 1213416781: #MESH
        if idstring2 == 1:
            parser = StaticParser1(data)
        elif idstring2 == 2:
            parser = StaticParser2(data)
    else:
        parser = SanaeParser(data)
    print(idstring)
    parser.parse_file()
    mdl = rapi.rpgConstructModel()
    mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
    mdl.setBones(parser.boneList)
    mdl.setAnims(parser.animList)
    mdlList.append(mdl)
    return 1

class Mesh(object):
    '''A generic mesh object, for convenience'''
    
    def __init__(self):
        
        self.positions = bytes()
        self.normals = bytes()
        self.uvs = bytes()
        self.numVerts = 0
        self.numIdx = 0
        self.idxBuff = bytes()
        self.matName = ""
        self.meshName = ""
        
class SanaeParser(object):
    
    def __init__(self, data):    
        '''Initialize some data. Refer to Sanae.py to see what is already
        initialized'''
        
        self.inFile = NoeBitStream(data)
        self.animList = []
        self.texList = []
        self.matList = []
        self.boneList = []
        self.meshList = []
        
    def build_mesh(self):
        
        for i in range(len(self.meshList)):
            mesh = self.meshList[i]
            rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 32, 0)
            rapi.rpgBindNormalBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 32, 12)
            rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 32, 24)
   
            rapi.rpgCommitTriangles(mesh.idxBuff, noesis.RPGEODATA_UINT, mesh.numIdx, noesis.RPGEO_TRIANGLE, 1)         
        
    def read_name(self):
        
        string = self.inFile.readBytes(self.inFile.readUInt())
        return noeStrFromBytes(string)
    
    def parse_vertices(self, numVerts):
    
        return self.inFile.readBytes(numVerts*32)
    
    def parse_faces(self, numIdx):
        
        return self.inFile.readBytes(numIdx * 4)
        
    def parse_file(self):
        '''Main parser method'''
        
        idstring = self.inFile.readUInt()
        idstring2 = self.inFile.readBytes(4)
        mesh = Mesh()
        
        mesh.meshName = self.read_name()
        mesh.numVerts = self.inFile.readUInt()
        mesh.numIdx = self.inFile.readUInt() * 3
        numWeights1, numWeights2 = self.inFile.read('2L')
        mesh.vertBuff = self.parse_vertices(mesh.numVerts)
        mesh.idxBuff = self.parse_faces(mesh.numIdx)
        
        #self.parse_weights1(numWeights1)
        #self.parse_weights2(numWeights2)
        self.meshList.append(mesh)
        
        #texFile = rapi.loadPairedFileOptional("Seven Souls Textures", ".*")
        
        self.build_mesh()
        
class StaticParser1(SanaeParser):
    '''For static meshes. Idstring "MESH".'''
    
    def build_mesh(self):
        
        for i in range(len(self.meshList)):
            mesh = self.meshList[i]
            rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 52, 0)
            rapi.rpgBindNormalBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 52, 12)
            rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 52, 24)
   
            rapi.rpgCommitTriangles(mesh.idxBuff, noesis.RPGEODATA_UINT, mesh.numIdx, noesis.RPGEO_TRIANGLE, 1)                 
    
    def parse_vertices(self, numVerts):
        
        return self.inFile.readBytes(52*numVerts)
    
    def parse_file(self):
        
        idstring = self.inFile.readBytes(4)
        self.inFile.read('3L')
        modelName = self.read_name()
        
        mesh = Mesh()
        mesh.numVerts = self.inFile.readUInt()
        mesh.numIdx = self.inFile.readUInt() * 3
        mesh.vertBuff = self.parse_vertices(mesh.numVerts)
        mesh.idxBuff = self.parse_faces(mesh.numIdx)
        self.meshList.append(mesh)
        
        self.build_mesh()

class StaticParser2(StaticParser1):
    
    def build_mesh(self):
            
        for i in range(len(self.meshList)):
            mesh = self.meshList[i]
            rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 68, 0)
            rapi.rpgBindNormalBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 68, 12)
            rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 68, 24)
   
            rapi.rpgCommitTriangles(mesh.idxBuff, noesis.RPGEODATA_USHORT, mesh.numIdx, noesis.RPGEO_TRIANGLE, 1)                 
    
    def parse_vertices(self, numVerts):
        
        return self.inFile.readBytes(numVerts*68)
    
    def parse_unk(self):
        
        count = self.inFile.readUByte()
        self.inFile.seek(count, 1)
    
    def parse_faces(self, numIdx):
        
        return self.inFile.readBytes(numIdx*2)
    
    def parse_file(self):
        
        idstring = self.inFile.readBytes(4)
        self.inFile.read('3L')
        modelName = self.read_name()
        
        mesh = Mesh()
        mesh.numVerts = self.inFile.readUInt()
        mesh.numIdx = self.inFile.readUInt() * 3
        mesh.vertBuff = self.parse_vertices(mesh.numVerts)
        self.parse_unk()
        mesh.idxBuff = self.parse_faces(mesh.numIdx)
        self.meshList.append(mesh)
        
        self.build_mesh()    

```


        Save with extension .py inside "plugings\python\7soulsmsh.py"

        Once you got it, run noesis, choose option "Seven Souls (*.msh)"

        Open the wished model, now u can export as .obj, that able you to open the mesh with 3DS max.
C. Maps

To the buildings, terrains, decorations, etc... with Noesis once again.

script for files .bsb

```

from inc_noesis import *
import noesis
import rapi
import os

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("Seven Souls", ".bsb")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    bs = NoeBitStream(data)
    idstring = noeStrFromBytes(bs.readBytes(4))
    if idstring == "BSOB":
        return 1
    return 0

def noepyLoadModel(data, mdlList):
    '''Build the model, set materials, bones, and animations. You do not
    need all of them as long as they are empty lists (they are by default)'''
    
    ctx = rapi.rpgCreateContext()
    parser = SanaeParser(data)
    parser.parse_file()
    mdl = rapi.rpgConstructModel()
    mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
    mdl.setBones(parser.boneList)
    mdl.setAnims(parser.animList)
    mdlList.append(mdl)
    return 1

class Mesh(object):
    '''A generic mesh object, for convenience'''
    
    def __init__(self):
        
        self.positions = bytes()
        self.normals = bytes()
        self.uvs = bytes()
        self.numVerts = 0
        self.numIdx = 0
        self.idxBuff = bytes()
        self.matNum = -1
        self.matName = ""
        self.meshName = ""
        self.faceGroups = []
        
class Material(object):
    '''A single material contains multiple textures, each used by difference
    face groups in the mesh'''
    
    def __init__(self):
        
        self.texNames = []

class SanaeParser(object):
    
    def __init__(self, data):    
        '''Initialize some data. Refer to Sanae.py to see what is already
        initialized'''
        
        self.inFile = NoeBitStream(data)
        self.animList = []
        self.texList = []
        self.matList = []
        self.boneList = []
        self.meshList = []
        self.extraList = []  # extra meshes?
        self.tempMats = [] #temporary storage
        
        
    def build_meshes(self):
        
        matCount = 0
        for i in range(len(self.meshList)):
            mesh = self.meshList[i]
            if mesh.matNum != -1:
                mat = self.tempMats[mesh.matNum]
            rapi.rpgSetName(mesh.meshName)
            rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 56, 0)
            rapi.rpgBindNormalBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 56, 12)
            rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 56, 24)
            
            for j in range(len(mesh.faceGroups)):
                numIdx, idxBuff = mesh.faceGroups[j]
                if numIdx == 0:
                    continue
                matName = "Material[%d]" %matCount
                texName = mat.texNames[i]
                
                material = NoeMaterial(matName, texName)
                self.matList.append(material)
                rapi.rpgSetMaterial(matName)
                rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)         
                
    def build_extras(self):
        
        for i in range(len(self.extraList)):
            mesh = self.extraList[i]
            rapi.rpgBindPositionBuffer(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 12)
            rapi.rpgCommitTriangles(mesh.idxBuff, noesis.RPGEODATA_USHORT, mesh.numIdx, noesis.RPGEO_TRIANGLE, 1)
        
    def read_name(self):
        
        string = self.inFile.readBytes(self.inFile.readUInt())
        return noeStrFromBytes(string)
    
    def parse_materials(self, numMat):
        
        mat = Material()
        for i in range(numMat):
            print("material %d" %i)
            mat.matNum = self.inFile.readUInt()
            self.inFile.read('9f')
            numTex = self.inFile.readUInt()
            if numTex == 0:
                self.read_name() #null
            else:
                for j in range(numTex):
                    texNum = self.inFile.readUInt()
                    texName =self.read_name()
                    maskName = self.read_name()
                    normName = self.read_name()
                    mat.texNames.append(texName)
            self.tempMats.append(mat)
        
    def parse_vertices(self, numVerts):
    
        return self.inFile.readBytes(numVerts*56)
    
    def parse_faces(self, numFaceGroups):
        
        faceGroups = []
        for i in range(numFaceGroups):
            numIdx = self.inFile.readUInt() * 3
            idxBuff = self.inFile.readBytes(numIdx*2)
            faceGroups.append([numIdx, idxBuff])
        return faceGroups
            
    def parse_mesh(self, numMesh):
        
        for i in range(numMesh):
            mesh = Mesh()
            
            self.inFile.readUInt()
            mesh.meshName = self.read_name()
            self.read_name() # NULL
            self.inFile.readByte()
            self.read_name()
            
            unk, numVerts, totalFaces = self.inFile.read('3L')
            #light map related
            bLightMap = self.inFile.readByte()
            self.read_name()
            self.inFile.readByte()
            
            self.inFile.read('3L')
            self.inFile.read('48f')
            self.inFile.readByte()
            self.inFile.read('10f')
            mesh.numVerts = self.inFile.readUInt()
            mesh.vertBuff = self.parse_vertices(mesh.numVerts)
            print(self.inFile.tell(), "vertbuff end")
            
            # a bunch of face groups per mesh
            numFaceGroups = self.inFile.readUInt()
            mesh.faceGroups = self.parse_faces(numFaceGroups)
            print(self.inFile.tell(), "idxBuff end")
            self.meshList.append(mesh)
            
            unk, mesh.matNum = self.inFile.read('2L')
            self.inFile.readInt()
            print(self.inFile.tell(), "mesh end")
            
    def parse_extra_mesh(self, numMesh):
            
        for i in range(numMesh):
            mesh = Mesh()
            mesh.matNum = self.inFile.readUInt()
            mesh.meshName = self.read_name()
            mesh.numIdx = self.inFile.readUInt() * 3
            mesh.numVerts = self.inFile.readUInt()
            
            self.inFile.read('48f')
            mesh.vertBuff = self.inFile.readBytes(mesh.numVerts * 12)
            mesh.idxBuff = self.inFile.readBytes(mesh.numIdx * 2)
            self.extraList.append(mesh)
        
    def parse_file(self):
        '''Main parser method'''
        
        idstring = self.inFile.readBytes(4)
        self.inFile.readUInt()
        modelName = self.read_name()
        self.inFile.read('5L')
        self.inFile.readByte()
        numMesh = self.inFile.readUInt()
        self.parse_materials(numMesh)
        
        self.inFile.readUInt()
        numMesh = self.inFile.readUInt()
        self.inFile.read('6L')
        self.parse_mesh(numMesh)
        
        numExtra = self.inFile.readUInt()
        print(self.inFile.tell())
        self.parse_extra_mesh(numExtra)
        
        self.build_meshes()
        #self.build_extras()

```


Save it in "plugings\python\7SoulObjects.py"

Run noesis, choose this option "Seven Souls (*.bsb)

Folder "vfs\objects\" contain them.

Folder "vfs\textures\" contain the textures for it.


PS. thanks guys for share the knowledge, i update the post  to complete the tutorial.


Files:

Extraction script qbms
3dsmax characters script
Python script for files .msh
Python script for files .bsb


 Files.zip
(6.18 KiB) Downloaded 31 times
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-21T17:00:14+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

If you have samples, please share.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-22T16:29:13+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

ok anyway, here is the samples finale.

[https://cloud.mail.ru/public/HN9K/wTqSL5GLF](https://cloud.mail.ru/public/HN9K/wTqSL5GLF)
## Post #4
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2015-09-23T07:01:27+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

where can i download the game setup files?

( Update )

sorry , i found one .
[http://www.gamershell.com/download_86848.shtml](http://www.gamershell.com/download_86848.shtml)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-23T08:00:30+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

> Reply from Keygen
>
> B. Weapons

There no exist a working script to extract the weapons yet. If somebody know the way to create it, share here please
The one I checked (gi201132900.msh) has a very simple format:



gi_2011_32900.JPG (86.82 KiB) Viewed 281 times
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-23T19:04:53+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

Noesis scripts for BSB and non-character objects

[http://himeworks.com/redirect.php?type= ... _souls_msh](http://himeworks.com/redirect.php?type=noesis&name=seven_souls_msh)
[http://himeworks.com/redirect.php?type= ... _souls_bsb](http://himeworks.com/redirect.php?type=noesis&name=seven_souls_bsb)

MSH importer supports characters as well but doesn't load skeleton.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-24T02:25:06+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

many thanks for the wonderful work, what about textures? you know something strange there, the name of the mesh not coordinate with name of texture, so how we can load model + textures, if not respect the names in files? you know how? I try check files via hex to see if show a name material but can't see nothing there.
## Post #8
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-09-26T07:17:56+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

Nice, very nice comrades, so now we got a way to get the weapons and the maps.


Thanks everyone.
## Post #9
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-09-26T08:57:59+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

> Reply from finale00
>
> Noesis scripts for BSB and non-character objects

could you post a tutorial about how run noesis scripts?


Thanks
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-26T14:09:58+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

well very simple mate.
## Post #11
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-10-01T14:01:41+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

Working perfect! many thanks!
## Post #12
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-11-24T12:48:17+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

Some Screenes about how's going GTA mod;














Currently Keep going with the project in my free time.

If someone wants the mod files Quote this phrase.

Thanks
## Post #13
- Username: Lucky1871
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 25, 2015 3:19 am
- Post datetime: 2015-11-24T19:23:14+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

Guys, what are you actually doing here? Don't tell me what I think you will tell me 
I was playing this game since start and till the last day when they shut it down, i wanna join your work
## Post #14
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-11-24T20:33:24+00:00
- Post Title: [ Martial Empires / Seven Souls ] Extraction

> Reply from Lucky1871
>
> Guys, what are you actually doing here? Don't tell me what I think you will tell me 
I was playing this game since start and till the last day when they shut it down, i wanna join your work

Yea i do know your nick from Martial Empires.

Im Sayan dunno if you remember, contact me by Facebook to join the mod.

Bless!
