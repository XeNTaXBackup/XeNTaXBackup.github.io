## Post #1
- Username: lantarm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 01, 2018 11:40 pm
- Post datetime: 2022-07-01T18:16:06+00:00
- Post Title: Need help with Noesis script

I have a noesis script by chrrox for Prime World .skin files. I edited this script for .stat files. More of them opened correctly, but some files not open with this error:
 
or:


```
import noesis
import rapi
import os.path

def registerNoesisTypes():
	handle = noesis.register("Prime World", ".stat")
	noesis.setHandlerTypeCheck(handle, PrimeWorldCheckType)
	noesis.setHandlerLoadModel(handle, PrimeWorldLoadModel)
	#noesis.logPopup()
	return 1

def PrimeWorldCheckType(data):
	bs = NoeBitStream(data)
	idMagic = bs.readInt()
	if idMagic != 0x54415458:
		return 0
	return 1       

def PrimeWorldLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	texList = []; matList = []; boneList = []
	#print(rapi.getDirForFilePath(rapi.getInputName()))
	#print(rapi.getLocalFileName(rapi.getInputName()))
	fileName, fileExtension = os.path.splitext(rapi.getLocalFileName(rapi.getInputName()))
	#print(fileName, fileExtension)

	rapi.setPreviewOption('setAngOfs',"0 -90 0")

	header = bs.read("9I")
	#print(header)
	tblOff = bs.tell()
	meshCount, mTableOff = bs.read("2I")
	bs.seek(tblOff + mTableOff, NOESEEK_ABS)
	meshInfo = []
	for a in range(0, meshCount):
		meshInfo.append([bs.read("10I"), (bs.tell() - 4)])
	#print(meshInfo)
	meshFVF = []
	for a in range(0, meshCount):
		tmp = []
		bs.seek(meshInfo[a][1] + meshInfo[a][0][9], NOESEEK_ABS)
		for b in range(0, meshInfo[a][0][8]):
			tmp.append(bs.read("5I"))
		meshFVF.append(tmp)
	#print(meshFVF)
	BoneInfo = []
	for a in range(0, meshCount):
		bs.seek(header[7] + 0x10 + (8 * a), NOESEEK_ABS)
		BoneInfo.append([bs.tell(), bs.readUInt(), bs.readUInt()])
	#print(BoneInfo)
	for a in range(0, meshCount):
		bs.seek(BoneInfo[a][0] + BoneInfo[a][2], NOESEEK_ABS)
		boneMap = bs.read("H" * BoneInfo[a][0])
		rapi.rpgSetBoneMap(boneMap)

		material = NoeMaterial(fileName + str(a), "")
		material.setTexture(fileName + ".dds")
		material.setSpecularTexture(fileName + "SPC.dds")
		#material.setFlags(0, 1)
		matList.append(material)
		rapi.rpgSetMaterial(fileName + str(a))

		bs.seek(header[5] + (meshInfo[a][0][0] * meshInfo[a][0][1]), NOESEEK_ABS)
		vertBuff = bs.readBytes(meshInfo[a][0][0] * meshInfo[a][0][3])
		for b in range(0, meshInfo[a][0][8]):
			if meshFVF[a][b][2] == 0:
				rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, meshInfo[a][0][0], meshFVF[a][b][0])
			elif meshFVF[a][b][2] == 3:
				rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, meshInfo[a][0][0], meshFVF[a][b][0])
			elif meshFVF[a][b][2] == 5:
				rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, meshInfo[a][0][0], meshFVF[a][b][0])
			elif meshFVF[a][b][2] == 1:
				rapi.rpgBindBoneWeightBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, meshInfo[a][0][0], meshFVF[a][b][0], 4)
			elif meshFVF[a][b][2] == 2:
				rapi.rpgBindBoneIndexBufferOfs(vertBuff, noesis.RPGEODATA_UBYTE, meshInfo[a][0][0], meshFVF[a][b][0], 4)
		bs.seek(header[6] + (meshInfo[a][0][4] * 4), NOESEEK_ABS)
		faceBuff = bs.readBytes(meshInfo[a][0][5] * 0x18)
		rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_UINT, (meshInfo[a][0][5] * 6), noesis.RPGEO_TRIANGLE, 1)

	#sd = rapi.loadIntoByteArray(rapi.getDirForFilePath(rapi.getInputName()) + fileName + ".skel")
	#sd = NoeBitStream(sd)
	#sdHeader = sd.read("9I")
	#print(sdHeader)
	#sd.seek(0x14 + sdHeader[6], NOESEEK_ABS)
	#boneName = []
	#for a in range(0, sdHeader[5]):
	#	sd.seek(0x14 + sdHeader[6] + (8 * a), NOESEEK_ABS)
	#	info = [sd.tell(), sd.readUInt(), sd.readUInt()]
	#	sd.seek(info[0] + info[1], NOESEEK_ABS)
	#	boneName.append(sd.readBytes(info[2]).decode("ASCII").rstrip("\0"))
	#sd.seek(0xC + sdHeader[4], NOESEEK_ABS)
	#boneParent = []
	#for a in range(0, sdHeader[3]):
	#	boneParent.append(sd.readInt())
	#print(boneParent)
	#sd.seek(0x4 + sdHeader[2], NOESEEK_ABS)
	#for a in range(0, sdHeader[1]):
	#	mtx = NoeMat43.fromBytes(sd.readBytes(0x30)).transpose() 
	#	bn = NoeBone(a, boneName[a], mtx, None, boneParent[a])
	#	boneList.append(bn)
	#boneList = rapi.multiplyBones(boneList)

	#mdl = NoeModel()
	mdl = rapi.rpgConstructModel()
	mdl.setModelMaterials(NoeModelMaterials(texList, matList))
	mdlList.append(mdl); mdl.setBones(boneList)	
	return 1
```

I do not understand well, but may be problem with it? 

[example .stat files.rar](https://xentaxbackup.github.io/file/22443_example .stat files.rar)
