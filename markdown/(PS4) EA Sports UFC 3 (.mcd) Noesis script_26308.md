## Post #1
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-01-21T04:39:52+00:00
- Post Title: (PS4) EA Sports UFC 3 (.mcd) Noesis script

I wrote a script for Noesis to import models from UFC 3. I never done it before, so the script may not work with all files, in fact i know that it fails to load some of the models, but it should load heads, bodies, hairs, clothes and such. Only loads mesh and uvs, i couldn't figure out bones.
.big files can be unpacked using this utility - [https://zenhax.com/viewtopic.php?t=11568](https://zenhax.com/viewtopic.php?t=11568) . If you use "extract all" function, you'll also have to decompress the files afterwards using quickbms with chunklzx.bms script (included with utility). 


```

from inc_noesis import *

import noesis
import inspect

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
	handle = noesis.register("EA Sports UFC 3", ".mcd")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
		#noesis.setHandlerWriteModel(handle, noepyWriteModel)
		#noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
	noesis.logPopup()
		#print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
	return 1

NOEPY_HEADER = "RSF"

#check if it's this type based on the data
def noepyCheckType(data):
	bs = NoeBitStream(data)
	if len(data) < 8:
		return 0
	if bs.readBytes(8).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
		return 0
	return 1

class McdReader:
	class FPGD:
		def __init__(self, data):
			self.unk1 = data.readBytes(4)
			self.chunkSize = data.readUInt()
			self.unk2 = data.readBytes(self.chunkSize - 12)

	class GEOM:
		class INDX:
			class Face:
				def __init__(self, data):
					self.indices = []
					for i in range(3):
						self.indices.append(data.readUShort())
			
			def __init__(self, data):
				self.chunk = data.readBytes(4).decode("ASCII")
				self.pad1 = data.readBytes(5)
				self.indNum = data.readUInt()
				self.unk1 = data.readBytes(4).decode("ASCII")
				"""
				self.faces = []
				for i in range(self.indNum // 3):
					self.faces.append(self.Face(data))
				"""
				self.faces = data.readBytes(self.indNum * 2)
		
		class STRM:
			class Vertex:
				def readData(self, data, fmt):
					out = None
					num = fmt[0]
					fmt = fmt[1:]
					if fmt == "f16":
						out = struct.unpack(str(num)+"e", data.read(num * 2))
					elif fmt == "f32":
						out = struct.unpack(str(num)+"f", data.read(num * 4))
					elif fmt == "u8n":
						out = struct.unpack(str(num)+"B", data.read(num))
					else:
						print("fmt : " + fmt + "  is not defined")
					return out
			
				def __init__(self, data, par):
					keys = par.fmt.keys()
					self.data = dict()
					for k in keys:
						fmt = par.fmt.get(k)
						self.data.update({k: self.readData(data, fmt[-1])})
					print(self.data.get("t0"))
			
			def __init__(self, data, vfmt):
				self.chunk = data.readBytes(4).decode("ASCII")
				self.pad1 = data.readBytes(5)
				self.vertNum = data.readUInt()
				self.vertStride = data.readUInt()
				self.formatIndex = data.readUInt()
				self.fmt = vfmt[self.formatIndex].fmt
				"""
				self.vertices = []
				if self.vertStride >= 30:
					for i in range(self.vertNum):
						self.vertices.append(self.Vertex(data, self))
				else:
					for i in range(self.vertNum):
						self.vertices.append(data.readBytes(self.vertStride))
				"""
				self.vertices = data.readBytes(self.vertNum * self.vertStride)
		
		class VFMT:
			def __init__(self, data):
				self.chunk = data.readBytes(4).decode("ASCII")
				self.size = data.readUInt()
				inp = data.readBytes(self.size).decode("ASCII")
				self.fmt = dict()
				inp = inp.split(" ")
				for i in inp:
					i = i.split(":")
					self.fmt.update({i[0]: i[1:]})
				self.pad1 = data.readBytes(1)
		
		def __init__(self, data):
			self.unk1 = data.readBytes(4)
			self.chunkSize = data.readUInt()
			self.unk2 = data.readBytes(4)
			self.vfmtNum = data.readUInt()
			self.vfmt = []
			for i in range(self.vfmtNum):
				self.vfmt.append(self.VFMT(data))
			self.meshNum = data.readUInt()
			self.meshes = []
			self.morphs = []
			for i in range(self.meshNum):
				strm = self.STRM(data, self.vfmt)
				if strm.fmt.get("t0") == None:
					self.morphs.append(strm)
				else:
					self.meshes.append(strm)
			self.meshNum = len(self.meshes)
			self.ibufNum = data.readUInt()
			self.iBuffers = []
			for i in range(self.ibufNum):
				self.iBuffers.append(self.INDX(data))
	
	class FPOF:
		class FBone:
			def __init__(self, data, par):
				self.nameLength = data.readUInt()
				self.name = data.readBytes(self.nameLength).decode("ASCII")
				self.pad1 = data.readBytes(1)
				self.unk1 = []
				for i in range(4):
					self.unk1.append(data.readFloat())
				par.size = par.size + 21 + self.nameLength
		
		def __init__(self, data):
			self.unk1 = data.readBytes(4)
			self.chunkSize = data.readUInt()
			self.unk2 = data.readBytes(4)
			self.boneNum = data.readUInt()
			self.size = 21
			self.bones = []
			for i in range(self.boneNum):
				self.bones.append(self.FBone(data, self))
			self.pad1 = data.readBytes(self.chunkSize - self.size + 1)
	
	class SKTN:
		class SBone:
			def __init__(self, data, par):
				self.nameLength = data.readUInt()
				self.name = data.readBytes(self.nameLength).decode("ASCII")
				self.pad1 = data.readBytes(1)
				par.size = par.size + 5 + self.nameLength
		
		def __init__(self, data):
			self.unk1 = data.readBytes(4)
			self.chunkSize = data.readUInt()
			self.unk2 = data.readBytes(4)
			self.boneNum = data.readUInt()
			self.size = 21
			self.bones = []
			for i in range(self.boneNum):
				self.bones.append(self.SBone(data, self))
			self.matrices = []
			for i in range(self.boneNum):
				self.matrices.append(data.readBytes(64))
				self.size += 64
			self.pad1 = data.readBytes(self.chunkSize - self.size + 1)
	
	class WEIT:
		class Weights:
			class BoneIndices:
				def __init__(self, data, par):
					self.indices = []
					for i in range(par.boneNum):
						self.indices.append(data.readUShort())
						par.size += 2
			
			class BoneWeights:
				def __init__(self, data, par):
					self.weights = []
					for i in range(par.boneNum):
						self.weights.append(data.readFloat())
						par.size += 4
			
			def __init__(self, data, par):
				self.index = data.readUInt()
				self.boneNum = data.readUInt()
				self.vertNum = data.readUInt()
				self.size = 12
				"""
				self.boneWeights = []
				self.boneIndices = []
				for i in range(self.vertNum):
					self.boneWeights.append(self.BoneWeights(data, self))
				for i in range(self.vertNum):
					self.boneIndices.append(self.BoneIndices(data, self))
				par.size += self.size
				"""
				self.boneWeights = data.readBytes(self.vertNum * self.boneNum * 4)
				self.boneIndices = data.readBytes(self.vertNum * self.boneNum * par.indexLength)
				self.size += (self.vertNum * self.boneNum * (4 + par.indexLength))
				par.size += self.size
		
		def __init__(self, data):
			self.indexLength = data.readUInt()
			self.chunkSize = data.readUInt()
			self.unk2 = data.readBytes(4)
			self.meshNum = data.readUInt()
			self.size = 20
			self.weights = []
			for i in range(self.meshNum):
				self.weights.append(self.Weights(data, self))
			self.pad1 = data.readBytes(self.chunkSize - self.size)
			
	def __init__(self, data):
		self.header = data.readBytes(16)
		self.chunk1 = data.readBytes(4).decode("ASCII")
		self.weit = self.WEIT(data)
		self.chunk2 = data.readBytes(4).decode("ASCII")
		if self.chunk2 == "NTKS":
			self.skeleton = self.SKTN(data)
			self.chunk3 = data.readBytes(4).decode("ASCII")
			self.fpof = self.FPOF(data)
			self.chunk4 = data.readBytes(4).decode("ASCII")
			if self.chunk4 == "DGPF":
				self.fpgd = self.FPGD(data)
				self.chunk5 = data.readBytes(4).decode("ASCII")
				self.geometry = self.GEOM(data)
			elif self.chunk4 == "MOEG":
				self.geometry = self.GEOM(data)
		elif self.chunk2 == "MOEG":
			self.geometry = self.GEOM(data)

#load the model
def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	mcd = McdReader(bs)
	for i in range(len(mcd.geometry.meshes)):
		vFormat = mcd.geometry.meshes[i].fmt
		uv1Offset = int(vFormat.get("t0")[0], 16)
		normOffset = int(vFormat.get("n0")[0], 16)
		rapi.rpgSetName("Mesh{:02}".format(i))
		rapi.rpgBindPositionBufferOfs(mcd.geometry.meshes[i].vertices, noesis.RPGEODATA_FLOAT, mcd.geometry.meshes[i].vertStride, 0) #Vertices
		rapi.rpgBindNormalBufferOfs(mcd.geometry.meshes[i].vertices, noesis.RPGEODATA_HALFFLOAT, mcd.geometry.meshes[i].vertStride, normOffset) #Normals
		#rapi.rpgBindBoneWeightBufferOfs(mcd.weit.weights[i].boneWeights, noesis.RPGEODATA_FLOAT, mcd.weit.weights[i].boneNum * 4, 0, mcd.weit.weights[i].boneNum) #Bone Weights
		#rapi.rpgBindBoneIndexBufferOfs(mcd.weit.weights[i].boneIndices, noesis.RPGEODATA_USHORT, mcd.weit.weights[i].boneNum * 2, 0, mcd.weit.weights[i].boneNum) #Bone Indices
		rapi.rpgBindUV1BufferOfs(mcd.geometry.meshes[i].vertices, noesis.RPGEODATA_HALFFLOAT, mcd.geometry.meshes[i].vertStride, uv1Offset) #UV1
		t1 = vFormat.get("t1")
		if t1 != None:
			uv2Offset = int(vFormat.get("t1")[0], 16)
			rapi.rpgBindUV2BufferOfs(mcd.geometry.meshes[i].vertices, noesis.RPGEODATA_HALFFLOAT, mcd.geometry.meshes[i].vertStride, uv2Offset) #UV2
		rapi.rpgCommitTriangles(mcd.geometry.iBuffers[i].faces, noesis.RPGEODATA_USHORT, mcd.geometry.iBuffers[i].indNum, noesis.RPGEO_TRIANGLE, 1) #Faces
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	rapi.rpgClearBufferBinds()
	return 1
```

[fmt_EaSportsUFC3_mcd.zip](https://xentaxbackup.github.io/file/23334_fmt_EaSportsUFC3_mcd.zip)
## Post #2
- Username: 1476435277
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 06, 2023 1:02 am
- Post datetime: 2023-03-05T17:24:12+00:00
- Post Title: (PS4) EA Sports UFC 3 (.mcd) Noesis script

good
## Post #3
- Username: HotavioH
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 17, 2010 11:45 am
- Post datetime: 2023-05-09T06:33:47+00:00
- Post Title: (PS4) EA Sports UFC 3 (.mcd) Noesis script

Hey brother, any chance of you give a look at UFC 4 .mcd files? Sadly, I couldn't import the model with the UFC 3 Script.
[https://drive.google.com/file/d/1I4ZZ_4 ... 0f6l3ic4ZT](https://drive.google.com/file/d/1I4ZZ_4f42757s4ng7qnv-Z0f6l3ic4ZT)
[https://drive.google.com/file/d/1rCEsET ... m0zTuelbXr](https://drive.google.com/file/d/1rCEsETxN6pMrogw3O9Hvjjm0zTuelbXr)
