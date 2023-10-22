## Post #1
- Username: lunan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 01, 2017 11:52 pm
- Post datetime: 2017-10-02T12:47:53+00:00
- Post Title: PlayStation All-Stars Battle Royal Mesh Rip Issue

Hello. I am having a bit of trouble with ripping certain models from this game. I am using this Noesis script by Chrrox

```
#C:\Users\Chris\Downloads\helpstudiosample_chm\jak\characters\jak\costumes\_vta
from inc_noesis import *
import collections
import struct
import os

def registerNoesisTypes():
	handle = noesis.register("Playtation All Stars Vita model", ".cskn")
	noesis.setHandlerTypeCheck(handle, psaVitamodCheckType)
	noesis.setHandlerLoadModel(handle, psaVitamodLoadModel)

	handle = noesis.register("Playtation All Stars Vita tex", ".ctxr")
	noesis.setHandlerTypeCheck(handle, psaVitatexCheckType)
	noesis.setHandlerLoadRGBA(handle, psaVitatexLoadRGBA)
	
	handle = noesis.register("Playtation All Stars Vita Anim", ".cesm")
	noesis.setHandlerTypeCheck(handle, cesmCheckType)
	noesis.setHandlerLoadModel(handle, cesmLoadModel)
	#noesis.logPopup()

	return 1


def psaVitamodCheckType(data):
	td = NoeBitStream(data)
	return 1

def psaVitatexCheckType(data):
	td = NoeBitStream(data)
	return 1
	
def cesmCheckType(data):
	td = NoeBitStream(data)
	return 1

class psaVitaFile: 
         
	def __init__(self, bs):
		self.bs = bs
		self.texList     = []
		self.matList     = [] 
		self.boneList    = []
		self.boneMap     = []
		self.offsetList  = []
		self.meshOffsets = []
		self.meshFvf     = []

	def loadAll(self, bs):
		self.loadModlHeader(bs)
		self.loadFVFInfo(bs)
		self.loadMeshIdx(bs)
		self.loadMatInfo(bs)

	def loadMeshNames(self, bs):
		pass
		
	def loadBones(self, bs):
		boneMtxList = []
		bp = []
		boneNameList = []
		
		#print("Loading bones at offset " + str(self.cmdlEnd))
		boneHeader    = bs.read("6I")
		boneMTXOff    = bs.tell() + bs.readUInt()
		boneParOff    = bs.tell() + bs.readUInt()
		boneOff3      = bs.tell() + bs.readUInt()
		boneOff4      = bs.tell() + bs.readUInt()
		boneOff5      = bs.tell() + bs.readUInt()
		boneOff6      = bs.tell() + bs.readUInt()
		boneNameOff   = bs.tell() + bs.readUInt()
		null00, null01, parCount = bs.read("3I")
		for a in range(0,parCount):
			bp.append(bs.read("4b"))
			#print(bp[a])
		#print(boneHeader)
		#print([boneMTXOff, boneParOff, boneOff3, boneOff4, boneOff5, boneOff6, boneNameOff])
		bs.seek(boneMTXOff, NOESEEK_ABS)
		for a in range(0,boneHeader[4]):
			m00, m01, m02, m03 = bs.read("4f")
			m10, m11, m12, m13 = bs.read("4f")
			m20, m21, m22, m23 = bs.read("4f")
			bonePos = NoeVec3([m10, m11, m12])
			boneMtx = NoeQuat([m00, m01, m02, m03]).toMat43().inverse()
			boneMtx[3] = bonePos
			#print(boneMtx)
			boneMtxList.append(boneMtx)
		bs.seek(boneParOff, NOESEEK_ABS)
		boneParList = bs.read(boneHeader[4] * "H")
		#print(boneParList)
		bs.seek(boneNameOff, NOESEEK_ABS)
		bVer, bStart, bCount, bNull = bs.read("4I")
		bNamebase = bs.tell()
		for a in range(0,bCount):
			bs.seek(bNamebase + (4 * a), NOESEEK_ABS)
			bNameOff = bs.tell() + bs.read("I")[0]
			bs.seek(bNameOff, NOESEEK_ABS)
			boneNameList.append(bs.readString().rsplit('|', 1)[1])
			#print(boneNameList[a])
		for a in range(0,boneHeader[4]):
			newBone = NoeBone(a, boneNameList[a], boneMtxList[a], None, bp[boneParList[a]][2])
			self.boneList.append(newBone)
			#print(self.boneList[a].getMatrix())
		self.boneList = rapi.multiplyBones(self.boneList)

	def loadModlHeader(self, bs):
		self.modlHeader = self.MODLInfo(*( \
		(noeStrFromBytes(bs.readBytes(4)),) \
		+ bs.read(">3I") \
		+ bs.read("I")))
		print(self.modlHeader)

	def loadFVFInfo(self, bs):
		for a in range(0,self.modlHeader.fvfCount):
			fvfHeader = self.FVFInfo(*( \
			(noeStrFromBytes(bs.readBytes(4)),) \
			+ bs.read("2H2I")))
			print(fvfHeader)
			self.meshFvf.append(fvfHeader)

	def loadMeshIdx(self, bs):
		bs.seek(self.modlHeader.modlSize + 0x10, NOESEEK_ABS)
		print(bs.tell())
		idxGroups, idxCount, self.idxBase = bs.read(">2I") + (bs.tell(),)
		print(idxGroups, idxCount, self.idxBase)
		bs.seek(self.idxBase + (2 * idxCount), NOESEEK_ABS)

	def loadBonePallet(self, bs):
		pass
		
	def loadMatProp(self, bs):
		matHash, propSize = bs.read(">IH")
		return [matHash, propSize]
		
	def loadDiffuseName(self, bs, material): 
		texName = noeStrFromBytes(bs.readBytes(bs.read("B")[0]))
		texName = rapi.getExtensionlessName(texName.rsplit('/', 1)[1])
		print(texName)
		material.setTexture(texName)

	def loadMatInfo(self, bs):
		matInfo = []
		matCount = bs.read(">I")[0]
		print(matCount)
		for a in range(0, matCount):
			bs.seek(0x14, NOESEEK_REL)
			matNameSize = bs.read("B")[0]
			matName = "mat_" + str(a) + "_" + noeStrFromBytes(bs.readBytes(matNameSize))
			print(matName)
			material = NoeMaterial(matName, "")
			bs.seek(0x25, NOESEEK_REL)
			matElemCount = bs.read(">H")[0]
			for b in range(0, matElemCount):
				matHash, matSkip = self.loadMatProp(bs)
				if matHash in fvfMatLoaderDict:
					fvfMatLoaderDict[matHash](self, bs, material)
				else:
					bs.seek(matSkip, NOESEEK_REL)
			bs.seek(0x18, NOESEEK_REL)
			print(bs.tell())
			self.matList.append(material)
			#if str(fvfTemp[a][4]) in fvfMatLoaderDict:
			#	fvfMatLoaderDict[str()](self, fvfTemp[a], vertBuff)
			#	#print("New fvf Type Found:", fvfTemp[a])
			#else:
			#	pass
				#print("New fvf Type Found:", fvfTemp[a])
		meshCount = bs.read(">I")[0]
		for a in range(0,meshCount):
			matInfo.append(self.MeshMatInfo(*bs.read(">6fHB4I")))
			print(matInfo[a])
		bs.seek(0x4, NOESEEK_REL)
		print(bs.tell())
		self.cmdlEnd = bs.tell()
		#print([self.cmdlEnd ,bs.getSize()])
		self.loadMeshs(bs, matInfo)
		if bs.getSize() > self.cmdlEnd :
			bs.seek(self.cmdlEnd , NOESEEK_ABS)
			self.loadBones(bs)
		

	def loadMeshs(self, bs, matInfo):
		for b in range(0, len(self.meshFvf)):
			print(self.meshFvf[b])
			unit, stride = fvfTypeDict[self.meshFvf[b].fvfType]
			bs.seek(self.meshFvf[b].fvfOffset + 16, NOESEEK_ABS)
			dataBuff = bs.readBytes(self.meshFvf[b].fvfSize)
			print(fvfTypeDict[self.meshFvf[b].fvfType])
			if (self.meshFvf[b].magic == "0SOP"):
				rapi.rpgBindPositionBuffer(dataBuff, unit, stride)
			elif (self.meshFvf[b].magic == "0XET"):
				rapi.rpgBindUV1Buffer(dataBuff, unit, stride)
			elif (self.meshFvf[b].magic == "WNOB"):
				rapi.rpgBindBoneWeightBuffer(dataBuff, unit, stride, 4)
			elif (self.meshFvf[b].magic == "INOB"):
				bs.seek(self.meshFvf[b].fvfOffset + 16, NOESEEK_ABS)
				idxData = []
				for a in range(0, (self.meshFvf[b].fvfSize // 8)):
					f3, f2, f1, f4 = bs.read("4H")
					idxData.append(f1)
					idxData.append(f2)
					idxData.append(f3)
					idxData.append(f4)
				dataBuff = struct.pack("<" + 'H'*len(idxData), *idxData)
				rapi.rpgBindBoneIndexBuffer(dataBuff, unit, stride, 4)
				

				
			
		for a in range(0, len(matInfo)):
			print(matInfo[a])
			rapi.rpgSetMaterial(self.matList[matInfo[a].matID].name)
			bs.seek(self.idxBase + (2 * matInfo[a].faceStart), NOESEEK_ABS)
			faceBuff = rapi.swapEndianArray(bs.readBytes(2 * matInfo[a].faceCount), 2)
			rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_SHORT, matInfo[a].faceCount, noesis.RPGEO_TRIANGLE, 1)
		
		
		
	# MODL information
	MODLInfo = collections.namedtuple('MODLInfo', ' '.join((
		'magic',
		'modlVersion',
		'null00',
		'modlSize',
		'fvfCount'
	)))
	
	# Mesh Material information
	MeshMatInfo = collections.namedtuple('MeshMatInfo', ' '.join((
		'bbMinX',
		'bbMinY',
		'bbMinZ',
		'bbMaxX',
		'bbMaxY',
		'bbMaxZ',
		'matID',
		'buffID',
		'vertStart',
		'vertCount',
		'faceStart',
		'faceCount'
	)))

	# FVF information
	FVFInfo = collections.namedtuple('FVFInfo', ' '.join((
		'magic',
		'fvfType',
		'fvfVersion',
		'fvfOffset',
		'fvfSize'
	)))


fvfMatLoaderDict = {
	0x73762EDB			: psaVitaFile.loadDiffuseName

	}
	
fvfTypeDict = {
	1			: (noesis.RPGEODATA_FLOAT, 12),
	2			: (noesis.RPGEODATA_FLOAT, 16),
	5			: (noesis.RPGEODATA_HALFFLOAT, 4),
	6			: (noesis.RPGEODATA_SHORT, 8),
	10			: (noesis.RPGEODATA_USHORT, 8)

	}
	
	
class ctxrFile: 

	def __init__(self, bs):
		self.bs = bs
		self.texList = []
		
	def loadAll(self, bs):
		self.loadGXTHeader(bs)
		self.loadGXT(bs)

	def loadGXTHeader(self, bs):
		self.texHeader = self.GXTHeader(*( \
		(noeStrFromBytes(bs.readBytes(4)),) \
		+ bs.read("7I")))
		print(self.texHeader)
	
	def loadGXT(self, bs):
		texHeader = []

		for a in range(0, self.texHeader.texCount):
			bs.seek(0x20 + (a * 0x20), NOESEEK_ABS)
			texHeader.append(bs.read("5i4B2HI"))
			#print(texHeader[a])
			texName = rapi.getLocalFileName(rapi.getInputName())
			#print(info[a].split(','))
			bs.seek(texHeader[a][0], NOESEEK_ABS)
			texData = bs.readBytes(texHeader[a][1])
			self.psaLoadRGBA(texData, texHeader[a], texName)



	def psaLoadRGBA(self, texData, texInfo, texName):
		#print([texInfo[8], texInfo[9], texInfo[10]])
		#print("I am texture " + texName)

		texFmt = 0
		if texInfo[8] == 0x80:
			#PVRT2BPP
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageDecodePVRTC(texData, texInfo[9], texInfo[10], 2, noesis.PVRTC_DECODE_PVRTC2)
		elif texInfo[8] == 0x81:
			#PVRT4BPP
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageDecodePVRTC(texData, texInfo[9], texInfo[10], 4, noesis.PVRTC_DECODE_PVRTC2)
		elif texInfo[8] == 0x82:
			#PVRTII2BPP
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageDecodePVRTC(texData, texInfo[9], texInfo[10], 2, noesis.PVRTC_DECODE_PVRTC2)
		elif texInfo[8] == 0x83:
			#PVRTII4BPP
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageDecodePVRTC(texData, texInfo[9], texInfo[10], 4, noesis.PVRTC_DECODE_PVRTC2)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "b8g8r8a8")
		elif texInfo[8] == 0xC:
			#texFmt = noesis.NOESISTEX_DXT1
			texFmt = noesis.NOESISTEX_RGBA32
			#texData = rapi.imageFromMortonOrder(texData, texInfo[9], texInfo[10])
			texData = rapi.imageFromMortonOrder(texData, texInfo[9], texInfo[10], 32 // 8, 2)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "b8g8r8a8")
		elif texInfo[8] == 0x0:
			texFmt = noesis.NOESISTEX_RGBA32
			#texData = rapi.imageFromMortonOrder(texData, texInfo[9], texInfo[10])
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 4)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "b8g8r8a8")
		elif texInfo[8] == 0x85:
			#texFmt = noesis.NOESISTEX_DXT1
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 4)
			texData = rapi.imageDecodeDXT(texData, texInfo[9], texInfo[10], noesis.FOURCC_DXT1)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "r8g8b8a8")
		elif texInfo[8] == 0x86:
			#texFmt = noesis.NOESISTEX_DXT3
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 8)
			texData = rapi.imageDecodeDXT(texData, texInfo[9], texInfo[10], noesis.FOURCC_DXT3)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "r8g8b8a8")
		elif texInfo[8] == 0x87:
			#texFmt = noesis.NOESISTEX_DXT5
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 8)
			texData = rapi.imageDecodeDXT(texData, texInfo[9], texInfo[10], noesis.FOURCC_DXT5)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "r8g8b8a8")
		elif texInfo[8] == 0x8B:
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 8)
			#texData = rapi.imageDecodeDXT(texData, texInfo[9], texInfo[10], noesis.FOURCC_ATI2)
			#texData = rapi.swapEndianArray(texData, 2)
			#texData = rapi.imageDecodePVRTC(texData, texInfo[9], texInfo[10], 4, noesis.PVRTC_DECODE_PVRTC2)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "b8g8r8a8")
		elif texInfo[8] == 0x95:
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 8)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "r8g8b8a8")
		elif texInfo[8] == 0x98:
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9], texInfo[10], 24 // 8, 2)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "b8g8r8")
		#tex1 = NoeTexture(str(texInfo[8]), texInfo[9], texInfo[10], texData, texFmt)
		tex1 = NoeTexture(texName, texInfo[9], texInfo[10], texData, texFmt)
		#print(tex1)
		if texFmt == 0:
			print("ERROR NOT FOUND")
		self.texList.append(tex1)

		
	# GXT Header
	GXTHeader = collections.namedtuple('GXTHeader', ' '.join((
		'magic',
		'version',
		'texCount',
		'texDataOff',
		'texDataSize',
		'P4Pallet',
		'P8Pallet',
		'pad0'
	)))
	
def psaVitamodLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	psaVita = psaVitaFile(NoeBitStream(data))
	rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
	#rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
	psaVita.loadAll(psaVita.bs)
	try:
		mdl = rapi.rpgConstructModel()
	except:
		mdl = NoeModel()
	mdl.setModelMaterials(NoeModelMaterials(psaVita.texList, psaVita.matList))
	mdlList.append(mdl); mdl.setBones(psaVita.boneList)	
	return 1


def psaVitatexLoadRGBA(data, texList):
	td = NoeBitStream(data)
	td.seek(0x80, NOESEEK_ABS)
	rapi.setPreviewOption("ddsAti2NoNorm", "0")
	bs = NoeBitStream(td.readBytes(len(data) - 0x80))
	ctxr = ctxrFile(bs)
	ctxr.loadAll(ctxr.bs)
	for a in range(0, len(ctxr.texList)):
		texList.append(ctxr.texList[a])
	return 1
	
def cesmLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	mdl = NoeModel()
	magic, version, count = noeStrFromBytes(bs.readBytes(4)), bs.read(">I")[0], bs.read(">I")[0]
	#print([magic, version, count])
	for a in range(0, count):
		bs.seek(0x18, NOESEEK_REL)
		animNameSize = bs.readUByte()
		animName = noeStrFromBytes(bs.readBytes(animNameSize))
		#print(animName)
		animVersion, animPartCount = bs.read(">2I")
		for b in range(0, animPartCount):
			animHash, animSize = bs.read(">IH")
			#print(animHash)
			bs.seek(animSize, NOESEEK_REL)
		bs.seek(4, NOESEEK_REL)

	mdlList.append(mdl)
	return 1
```


I can rip models like Kratos and Sly Cooper. But when it comes to other models (Fat Princess in the case), I get this error attached below.

Can anyone help me with this? Is it the model or the script that is the issue? Thank you.
[Error.png](https://xentaxbackup.github.io/file/13367_Error.png)
## Post #2
- Username: lunan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 01, 2017 11:52 pm
- Post datetime: 2017-10-03T13:13:03+00:00
- Post Title: PlayStation All-Stars Battle Royal Mesh Rip Issue

Almost forgot to attach the model file.


 Fat Princess.zip
(203.7 KiB) Downloaded 27 times
