## Post #1
- Username: Grayne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 09, 2015 1:18 pm
- Post datetime: 2015-10-09T08:35:38+00:00
- Post Title: [HELP] Noesis Mesh Exporter

Hello everyone!
I'd like to ask if it was posted here or someone made an Exporter Script for Noesis.
The script from himeworks enables you to view RF Online mesh files but you can't export it.
I'm hoping if anyone is familiary with python can help me.

Here's the importer script btw:

> from inc_noesis import *
>
> import noesis
>
> import rapi
>
> import os
>
> import struct
>
> 
>
> MODE = 1
>
> 
>
> def registerNoesisTypes():
>
>     '''Register the plugin. Just change the Game name and extension.'''
>
> 
>
>     handle = noesis.register("RFOnline", ".msh")
>
>     noesis.setHandlerTypeCheck(handle, noepyCheckType)
>
>     noesis.setHandlerLoadModel(handle, noepyLoadModel)
>
>     return 1
>
> 
>
> def noepyCheckType(data):
>
>     '''Verify that the format is supported by this plugin. Default yes'''
>
> 
>
>     if len(data) < 2:
>
>         return 0
>
>     try:
>
>         bs = NoeBitStream(data)
>
>         idstring = noeStrFromBytes(bs.readBytes(6))
>
>         if idstring != "MESH08":
>
>             bs.seek(0)
>
>             numMesh = bs.readShort()
>
>             if numMesh <= 0 or numMesh > 50:
>
>                 return 0
>
>         return 1
>
>     except:
>
>         return 0
>
> 
>
> def get_type(data):
>
> 
>
>     bs = NoeBitStream(data)
>
>     string = bs.readBytes(6)
>
>     try:
>
>         if noeStrFromBytes(string) == "MESH08":
>
>             return 1
>
>         return 0
>
>     except:
>
>         return 0
>
> 
>
> def load_all_models(mdlList):
>
>     '''Load all models'''
>
> 
>
>     #carry over from previous models
>
>     matList = []
>
>     texList = []
>
> 
>
>     dirPath = rapi.getDirForFilePath(rapi.getInputName())
>
>     fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".msh")]
>
>     for file in fileList:
>
>         f = open(dirPath + file, 'rb')
>
>         data2 = f.read()
>
>         modelType = get_type(data2)
>
>         if modelType == 0:
>
>             parser = SanaeParser(data2)
>
>         else:
>
>             parser = RFParser(data2)        
>
>         parser.parse_file()
>
>         matList.extend(parser.matList)
>
>         texList.extend(parser.texList)
>
>         mdl = rapi.rpgConstructModel()
>
>     mdl.setModelMaterials(NoeModelMaterials(texList, matList))
>
>     mdlList.append(mdl)    
>
> 
>
> def load_single_model(data, mdlList):
>
>     '''Loads a single model. For testing purposes'''
>
> 
>
>     modelType = get_type(data)
>
>     if modelType == 0:
>
>         parser = SanaeParser(data)
>
>     else:
>
>         parser = RFParser(data)    
>
>     parser.parse_file()
>
>     mdl = rapi.rpgConstructModel()
>
>     mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
>
>     mdlList.append(mdl)       
>
> 
>
> def noepyLoadModel(data, mdlList):
>
>     '''Load the model'''
>
> 
>
>     ctx = rapi.rpgCreateContext()
>
>     if MODE == 1:
>
>         load_all_models(mdlList)
>
>     else:
>
>         load_single_model(data, mdlList)
>
>     return 1
>
> 
>
> #def noepyLoadModel(data, mdlList):
>
>     #'''Build the model, set materials, bones, and animations. You do not
>
>     #need all of them as long as they are empty lists (they are by default)'''
>
> 
>
>     #ctx = rapi.rpgCreateContext()
>
>     #modelType = get_type(data)
>
>     #if modelType == 0:
>
>         #parser = SanaeParser(data)
>
>     #else:
>
>         #parser = RFParser(data)
>
>     #parser.parse_file()
>
>     #mdl = rapi.rpgConstructModel()
>
>     #mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
>
>     #mdl.setBones(parser.boneList)
>
>     #mdl.setAnims(parser.animList)
>
>     #mdlList.append(mdl)
>
>     #return 1
>
> 
>
> class RFParser(object):
>
>     '''Type MESH08 parser'''
>
> 
>
>     def __init__(self, data):    
>
>         '''Initialize some data. Refer to Sanae.py to see what is already
>
>         initialized'''
>
> 
>
>         self.inFile = NoeBitStream(data)
>
>         self.animList = []
>
>         self.texList = []
>
>         self.matList = []
>
>         self.boneList = []
>
> 
>
>     def plot_points(self, numVerts):
>
> 
>
>         rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, numVerts, noesis.RPGEO_POINTS, 1)    
>
> 
>
>     def read_name(self, n):
>
> 
>
>         string = self.inFile.readBytes(n)
>
>         try:
>
>             return noeStrFromBytes(string)
>
>         except:
>
>             return ""    
>
> 
>
>     def parse_vertices(self, numVerts):
>
> 
>
>         vertBuff = self.inFile.readBytes(numVerts*64)
>
>         rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 0)
>
>         rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 32)
>
>         rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 44)
>
> 
>
>     def parse_faces(self, numIdx):
>
> 
>
>         return self.inFile.readBytes(numIdx*2)
>
> 
>
>     def parse_mesh(self, numMesh):
>
> 
>
>         for i in range(1):
>
>             print(i, self.inFile.tell())
>
>             meshName = self.read_name(100)
>
> 
>
>             #print(i, meshName, self.inFile.tell())
>
>             unk = self.read_name(100)
>
>             matrix1 = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
>
>             matrix2 = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
>
>             matrix3 = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
>
>             unk, unk2, unk3 = self.inFile.read('3H')
>
>             texName = os.path.basename(self.read_name(204))
>
>             self.inFile.seek(91, 1)    
>
> 
>
>             numVerts = self.inFile.readUShort()
>
>             if numVerts:
>
>                 self.parse_vertices(numVerts)
>
>                 numIdx = self.inFile.readUShort()
>
>             if numIdx:
>
>                 idxBuff = self.parse_faces(numIdx)
>
>                 rapi.rpgSetMaterial(texName)
>
>                 rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
>
> 
>
>     def parse_file(self):
>
> 
>
>         idstring = self.inFile.readBytes(6)
>
>         numMesh = self.inFile.readUShort()
>
>         self.parse_mesh(numMesh)
>
> 
>
> class SanaeParser(object):
>
> 
>
>     def __init__(self, data):    
>
>         '''Initialize some data. Refer to Sanae.py to see what is already
>
>         initialized'''
>
> 
>
>         self.inFile = NoeBitStream(data)
>
>         self.animList = []
>
>         self.texList = []
>
>         self.matList = []
>
>         self.boneList = []
>
> 
>
>     def read_name(self, n):
>
> 
>
>         string = self.inFile.readBytes(n)
>
>         try:
>
>             return noeStrFromBytes(string)
>
>         except:
>
>             return ""
>
> 
>
>     def build_mesh(self, vertList, normList, uvList, idxList, matrix1, texName):
>
> 
>
>         #build buffers
>
>         vertBuff = bytes()
>
>         normBuff = bytes()
>
>         uvBuff = bytes()
>
>         idxBuff = bytes()
>
>         count = 0
>
>         for idx in idxList:
>
>             vertBuff += bytes(struct.pack('3f', *vertList[idx]))
>
>             normBuff += struct.pack('3f', *normList[idx])
>
>             uvBuff += struct.pack('2f', *uvList[count])
>
>             idxBuff += struct.pack('L', count)
>
>             count += 1
>
> 
>
>         rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, 12)
>
>         rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_FLOAT, 12)
>
>         rapi.rpgBindUV1Buffer(uvBuff, noesis.RPGEODATA_FLOAT,  
>
>         rapi.rpgSetTransform(matrix1)
>
>         rapi.rpgSetMaterial(texName)
>
>         rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_UINT, count, noesis.RPGEO_TRIANGLE, 1)
>
> 
>
>         #rapi.immBegin(noesis.RPGEO_TRIANGLE)
>
>         #count = 0
>
>         #for index in idxList:
>
>             #rapi.immVertex3(vertList[index])
>
>             #rapi.immNormal3(normList[index])
>
>             #rapi.immUV2(uvList[count])
>
>             #count += 1
>
>         #rapi.immEnd()
>
>         #rapi.rpgSetTransform(matrix1)
>
> 
>
>     def parse_vertices(self, numVerts):
>
> 
>
>         #vertBuff = self.inFile.readBytes(numVerts*28)
>
>         #rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 28, 0)
>
>         #rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 28, 16)
>
> 
>
>         vertList = []
>
>         normList = []
>
>         for i in range(numVerts):
>
>             vertList.append(self.inFile.read('3f'))
>
>             self.inFile.readUInt()
>
>             normList.append(self.inFile.read('3f'))
>
>         return vertList, normList
>
> 
>
>     def parse_faces(self, numFaces):
>
> 
>
>         #idxBuff = bytes()
>
>         #uvBuff = bytes()
>
>         #for i in range(numFaces):
>
>             #idxBuff += self.inFile.readBytes(12)
>
>             #self.inFile.seek(36, 1)
>
>             #uvBuff += self.inFile.readBytes(8)
>
>             #self.inFile.readFloat()
>
>             #uvBuff += self.inFile.readBytes(8)
>
>             #self.inFile.readFloat()
>
>             #uvBuff += self.inFile.readBytes(8)
>
>             #self.inFile.readFloat()
>
>             #self.inFile.readUInt()
>
>         #rapi.rpgBindUV1Buffer(uvBuff, noesis.RPGEODATA_FLOAT,  
>
>         #return idxBuff
>
> 
>
>         idxList = []
>
>         uvList = []
>
>         for i in range(numFaces):
>
>             idxList.extend(self.inFile.read('3L'))
>
>             self.inFile.seek(36, 1)
>
>             uvList.append([self.inFile.readFloat(), self.inFile.readFloat() * -1])
>
>             self.inFile.readFloat()
>
>             uvList.append([self.inFile.readFloat(), self.inFile.readFloat() * -1])
>
>             self.inFile.readFloat()                        
>
>             uvList.append([self.inFile.readFloat(), self.inFile.readFloat() * -1])
>
>             self.inFile.readFloat()    
>
>             self.inFile.readUInt()
>
>         return idxList, uvList
>
> 
>
>     def parse_bones(self, numBones):
>
> 
>
>         for i in range(numBones):
>
>             self.inFile.seek(100, 1)
>
> 
>
>     def parse_unk(self, count):
>
> 
>
>         for i in range(count):
>
>             self.inFile.seek(40, 1)
>
> 
>
>     def parse_mesh(self, numMesh):
>
> 
>
>         for i in range(numMesh):
>
>             meshName = self.read_name(100)
>
>             unk = self.read_name(100)
>
>             matrix1 = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
>
>             matrix2 = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
>
>             matrix3 = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
>
>             numVerts, numFaces, unk1 = self.inFile.read('3H')
>
>             texName = os.path.basename(self.read_name(204))
>
>             self.inFile.seek(91, 1)
>
> 
>
>             if numVerts:
>
>                 vertList, normList = self.parse_vertices(numVerts)
>
>                 #rapi.rpgSetTransform(matrix1)
>
> 
>
>             if numFaces:
>
>                 idxList, uvList = self.parse_faces(numFaces)
>
>                 #numIdx = numFaces * 3
>
>                 #rapi.rpgSetMaterial(texName)            
>
>                 #rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_UINT, numIdx, noesis.RPGEO_TRIANGLE, 1)
>
>                 self.build_mesh(vertList, normList, uvList, idxList, matrix1, texName)
>
> 
>
>             numBones = self.inFile.readUInt()
>
>             self.parse_bones(numBones)
>
>             self.parse_unk(unk1)
>
> 
>
> 
>
>     def parse_file(self):
>
>         '''Main parser method'''
>
> 
>
>         numMesh = self.inFile.readUShort()
>
>         self.parse_mesh(numMesh)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-09T08:51:51+00:00
- Post Title: [HELP] Noesis Mesh Exporter

Afaik you can export every format supported by Noesis as obj or fbx for example.

Or do you mean an export for reimport into the game?
## Post #3
- Username: Grayne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 09, 2015 1:18 pm
- Post datetime: 2015-10-09T10:14:43+00:00
- Post Title: [HELP] Noesis Mesh Exporter

> Or do you mean an export for reimport into the game?
Yes, export it back to .msh that is readable for RF Online.
It would be nice to see new mods for this game.
## Post #4
- Username: dimajack
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 16, 2016 4:07 am
- Post datetime: 2016-10-16T07:35:54+00:00
- Post Title: [HELP] Noesis Mesh Exporter

> Reply from Grayne
>
> Or do you mean an export for reimport into the game?
Yes, export it back to .msh that is readable for RF Online.
It would be nice to see new mods for this game.
ap !
