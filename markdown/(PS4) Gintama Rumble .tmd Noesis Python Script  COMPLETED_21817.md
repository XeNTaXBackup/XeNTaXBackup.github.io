## Post #1
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-02-28T01:04:09+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Final version of the BMS and Noesis scripts for Gintama Rumble viewtopic.php?f=16&t=21817#p160618

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Hello guys, I'm trying to create a python script to extract the Gintama Rumble models from the PS4 version.
I'm using hex2obj as guide, trying to pars the values I found to a Noesis py script using chrrox's Noesis rapi tutorial, the problem is that in hex2obj the UVs are in WORDUV and the UV POS is 40 with a vertex size of 44.



My question is how to re-write this line from the tutorial using this information?
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 48)

Cause I tried using
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 44, 40)
But the UVs came out so tiny.



This is my script.

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Gintama Rumble PS4",".tmd")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "tmd0"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readBytes(4).decode("ASCII") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.seek(0xcc, NOESEEK_ABS)
	FCount = bs.read("i")
	bs.seek(0xc, NOESEEK_REL)
	VCount = bs.read("i")
	bs.seek(0x70, NOESEEK_ABS)
	FAddress = bs.readUInt()
	bs.seek(0x1c, NOESEEK_REL)
	VAddress = bs.readUInt()
	#print("{} {} {} {}".format(FCount[0]*3, VCount[0], hex(FAddress), hex(VAddress)))
	bs.seek(VAddress, NOESEEK_ABS)
	VertBuff = bs.readBytes(VCount[0] * 0x2c)
	#print("\n{}".format(VertBuff))
	rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
	rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 44, 40)
	bs.seek(FAddress, NOESEEK_ABS)
	FaceBuff = bs.readBytes(FCount[0] * 6)
	rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FCount[0]*3, noesis.RPGEO_TRIANGLE, 1)
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1
```


Here is the [sample file](https://www.mediafire.com/file/2x2yth899sby19q/pl00Hair00_00.tmd/file).
## Post #2
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-02-29T00:44:30+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Ok someone already helped with my UV's question.

The files come in .cat containers format, inside the .cat there are .tmd (the models) and .gnf (the textures)

The playable characters and bosses are divided into 4 elements in different folders: Body, Face, Hair and Weapons, and the support characters are one whole mesh each: Strikers.

BMS Script to split Gintama Rumble .cat files.
TamsoftGintama_CAT.bms

```
get UNK1 long
get FILES1 long
get UNK2 Long

for i = 0 < FILES1
get FILEOFFSET1[i] Long
next i

for i = 0 < FILES1
get FILESIZE1[i] long
next i

math TMP = 0

for i = 0 < FILES1

goto FILEOFFSET1[i]
get UNK3 long
get FILES2 long
get UNK5 long
get UNK6 long
get UNK7 long

for x = 0 < FILES2
get FILEOFFSET2[x] long
next x

for x = 0 < FILES2
get FILESIZE2[x] long
next x

for x = 0 < FILES2
math FILEOFFSET2[x] + FILEOFFSET1[i]
goto FILEOFFSET2[x]
get FILEHEADER long
if FILEHEADER == 0x1
set EXT string .cat
elseif FILEHEADER == 0x30646d74
set EXT string .tmd
elseif FILEHEADER == 0x316f6d74
set EXT string .tmo
elseif FILEHEADER == 0x20464e47
set EXT string .gnf
else
set EXT string .dat
endif
get NAME basename
set FILEN string NAME
if FILETOTAL > 1
string NAME + /
string NAME + FILEN
string NAME + _
string NAME + TMP
math TMP + 1
endif
string NAME + EXT

log NAME FILEOFFSET2[x] FILESIZE2[x]
next x

next i
```


Batch file to extract multiple .cat files
recursive_cat.bat

```
set back=%cd%
for /R %%i in (.) do (
cd "%%i"
for %%f in (*.cat) do (%back%\quickbms.exe %back%\TamsoftGintama_CAT.bms %%f "%%i")
)
cd %back%
```


GNF texture files are already supported on Noesis so you can easily export them.

Current fmt_GintamaRumble_tmd_ps4.py script.

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Gintama Rumble PS4",".tmd")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "tmd0"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readBytes(4).decode("ASCII") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	fn = rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getInputName())) + '_0'
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	
	bs.seek(0x6)
	UVFlag = bs.readUByte()
	BoneFlag = bs.readUByte()
	bs.seek(0x68)
	SubmeshOffset = bs.readUInt64()
	FAddress = bs.readUInt64()
	bs.readBytes(0x18)
	VAddress = bs.readUInt64()
	bs.readBytes(0x30)
	SubmeshesCount = bs.readUInt()
	FCount = bs.readUInt()
	bs.readBytes(0xc)
	VCount = bs.readUInt()
	bs.readBytes(0x10)
	BoneAddress = bs.readUInt64()
	BHierarchyAddress = bs.readUInt64()
	bs.readUInt64()
	BCount = bs.readUInt()
	VBSize = (bs.getSize()-VAddress)//VCount
	
	texList = []
	matList = []
	vwList = []
	bones = []
	BoneHash_array = []
	BoneParent_array = []
	
	bs.seek(VAddress)
	VertBuff = bs.readBytes(VCount * VBSize)
	
	rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, VBSize, 0)
	
	if UVFlag == 0xb7:
		rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, VBSize, VBSize-12)
	elif UVFlag == 0xf7:
		rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, VBSize, VBSize-20)
	else:
		rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, VBSize, VBSize-4)
	
	rapi.rpgSetUVScaleBias((32.0285,32.0285,32.0285),None)
	
	if BoneFlag in [0xa4, 0x24]:
		rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_UBYTE, VBSize, 20)
		bs.seek(VAddress + 0xc)	
		for j in range(0, VCount):
			bidx = []
			bwgt = []
			for k in range(0, 4):
				bwgt.append(bs.readUByte())
			for k in range(0, 4):
				bidx.append(bs.readUByte())
			vwList.append(NoeVertWeight(bidx, bwgt))
			bs.readBytes(VBSize-8)
		fw = NoeFlatWeights(vwList)
		rapi.rpgBindBoneIndexBuffer(fw.flatW[:fw.weightValOfs], noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
		rapi.rpgBindBoneWeightBuffer(fw.flatW[fw.weightValOfs:], noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)
		
		bs.seek(BHierarchyAddress)	
		for i in range(0, BCount):
			BoneHash = bs.readUInt()
			bs.readBytes(0xc)
			BoneParent = bs.readInt()
			bs.readUInt()
			BoneHash_array.append(BoneHash)
			BoneParent_array.append(BoneParent)
	
		bs.seek(BoneAddress)
		for i in range(0, BCount):
			BoneName = "Bone {:02x}".format(BoneHash_array[i])
			BonePIdx = BoneParent_array[i]
			Mat44 = NoeMat44.fromBytes(bs.readBytes(0x40))
			Mat43 = Mat44.toMat43().inverse()
			bones.append(NoeBone(i,BoneName, Mat43, None, BonePIdx))
	elif not BoneFlag:
		rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_UBYTE, VBSize, 12)
	
	bs.seek(SubmeshOffset)
	SubmeshesInfo = []
	for j in range(SubmeshesCount):
		SubmeshFaceCount = bs.readUInt()
		bs.readUInt()
		SubmeshBufferOffset = bs.readUInt64()
		SubmeshesInfo.append((SubmeshFaceCount,SubmeshBufferOffset))	
	
	FaceBuff = bs.readBytes(FCount * 3 * 2)	
	for i,info in enumerate(SubmeshesInfo):
		rapi.rpgSetName(fn + str(i))
		material = NoeMaterial('Material ' + fn + str(i), "")
		material.setTexture(fn + str(i) + '_dif')
		material.setNormalTexture(fn + str(i) + '_nml')
		matList.append(material)
		rapi.rpgSetMaterial('Material ' + fn + str(i))
		rapi.rpgCommitTriangles(FaceBuff[info[1]*3*2:info[1]*3*2+info[0]*3*2], noesis.RPGEODATA_USHORT, info[0]*3, noesis.RPGEO_TRIANGLE, 1)
	
	mdl = rapi.rpgConstructModel()
	mdl.setModelMaterials(NoeModelMaterials(texList, matList))
	mdl.setBones(bones)
	
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1	
```


I'm sharing both the cat files and extracted tmd and gnf files of 1 Boss, 1 Playable and 1 Support so you can replicate and see how the files should be. [samples](https://www.mediafire.com/file/gnm1awzdzk6dgfj/samples_gintama.7z/file)
The bodies of Playable and Boss characters are in the "Chara" folder, their faces, hairs and weapons in the "Playable" folder and the support is in the "Striker" folder, that's the original structure of the game.


And this is inside the Playable folder
## Post #3
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-02-29T01:05:06+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Can you try the psv version
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-01T23:07:44+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Very good job!!
Could you explain this to me?

```
bs.seek(0x1c, NOESEEK_REL)
```

Very good job!!
Could you explain this to me?
Because, as I understand it, this section is referring to the vertex offset, but that information is not in the 0x90?
What would that 0x1c be?
## Post #5
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-01T23:16:16+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from reh ↑Mon Mar 02, 2020 7:07 am at Mon Mar 02, 2020 7:07 am
>
> 
Very good job!!
Could you explain this to me?
Code: Select allbs.seek(0x1c, NOESEEK_REL)
Very good job!!
Could you explain this to me?
Because, as I understand it, this section is referring to the vertex offset, but that information is not in the 0x90?
What would that 0x1c be?

In that line bs.seek is in relative mode, which means from the position the cursor is, move the given number of bytes.
At that moment the cursor is in 0x74, bs.seek(0x1c, NOESEEK_REL) adds 0x1c bytes to move to the 0x90 position.
## Post #6
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-01T23:20:08+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

I've cleaned the .bms and .py scripts a little bit.
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-01T23:33:27+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Thank you for the explanation.
So does this also apply to this stretch?

```
bs.seek(0xc, NOESEEK_REL)
```
## Post #8
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-01T23:43:29+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from reh ↑Mon Mar 02, 2020 7:33 am at Mon Mar 02, 2020 7:33 am
>
> 
Thank you for the explanation.
So does this also apply to this stretch?
Code: Select allbs.seek(0xc, NOESEEK_REL)

Yes, it's same, at that moment the cursor is in 0xd0, it moves 0xc bytes to the position 0xdc where the vertex count is.
## Post #9
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-05T17:59:34+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

With the help of RandomTalkingBush's Senran Kagura max script, I noticed there are 2 bones array, one for the actual bones position and other for the bones hierarchy.

Here is a data table of the Gintama tmd file strcuture.


At offset 0xf0 it has the Bone address, at 0xf8 the Bone Hierarchy address, at 0x108 the Bone and Bone Hierarchy count. The bone stride or line length is 0x40 or 64 decimal and the Bone Hierarchy stride is 0x18 or 24 decimal.



When we go to the bone address we found a list of 4x4 Matrices, so I followed Bigchillghost example here [viewtopic.php?f=29&t=19429#p148203](https://forum.xentax.com/viewtopic.php?f=29&t=19429#p148203) and transformed it to a 4x3 Matrix and reversed it.



The first version of the script output the model as a single mesh, but Joschka/Dimy at the discord server helped me separating it into submeshes, thanks.

I also used RTB's script to found the location of the normals and weights, I tried re-writing them to noesis and I think they're fine because the lighting and rigging seem ok. The methods could be written better, since I don't really know python.

I know the difference is almost imperceptible but here it is without normals.


And with normals.


If you look closely the shadows are more uniform.

Here is a weight example.


Dimy suggested that I should clean the code first with a more sequential order, so I'll do that before posting it later today.
Not gonna bother with textures cause noesis already supports gnf textures and can be applied manually after exporting them. I'm honestly satisfied with what the script already does.
## Post #10
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-05T23:12:07+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

I think I've finished cleaning the script, thanks to all the people that helped me with my questions.

I've updated the scripts, now the bms scripts are combined into one, I edited the one from Senran Kagura and made a batch file so that it extracts all the .cat files in one directory and its subfolders. Also updated the noesis script so it can support models without bones, it now can handle every TMD in game.

fmt_GintamaRumble_tmd_ps4.py

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Gintama Rumble PS4",".tmd")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "tmd0"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readBytes(4).decode("ASCII") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	fn = rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getInputName())) + '_0'
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	
	bs.seek(0x6)
	UVFlag = bs.readUByte()
	BoneFlag = bs.readUByte()
	bs.seek(0x68)
	SubmeshOffset = bs.readUInt64()
	FAddress = bs.readUInt64()
	bs.readBytes(0x18)
	VAddress = bs.readUInt64()
	bs.readBytes(0x30)
	SubmeshesCount = bs.readUInt()
	FCount = bs.readUInt()
	bs.readBytes(0xc)
	VCount = bs.readUInt()
	bs.readBytes(0x10)
	BoneAddress = bs.readUInt64()
	BHierarchyAddress = bs.readUInt64()
	bs.readUInt64()
	BCount = bs.readUInt()
	VBSize = (bs.getSize()-VAddress)//VCount
	
	texList = []
	matList = []
	vwList = []
	bones = []
	BoneHash_array = []
	BoneParent_array = []
	
	bs.seek(VAddress)
	VertBuff = bs.readBytes(VCount * VBSize)
	
	rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, VBSize, 0)
	
	if UVFlag == 0xb7:
		rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, VBSize, VBSize-12)
	elif UVFlag == 0xf7:
		rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, VBSize, VBSize-20)
	else:
		rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, VBSize, VBSize-4)
	
	rapi.rpgSetUVScaleBias((32.0285,32.0285,32.0285),None)
	
	if BoneFlag in [0xa4, 0x24]:
		rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_UBYTE, VBSize, 20)
		bs.seek(VAddress + 0xc)	
		for j in range(0, VCount):
			bidx = []
			bwgt = []
			for k in range(0, 4):
				bwgt.append(bs.readUByte())
			for k in range(0, 4):
				bidx.append(bs.readUByte())
			vwList.append(NoeVertWeight(bidx, bwgt))
			bs.readBytes(VBSize-8)
		fw = NoeFlatWeights(vwList)
		rapi.rpgBindBoneIndexBuffer(fw.flatW[:fw.weightValOfs], noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
		rapi.rpgBindBoneWeightBuffer(fw.flatW[fw.weightValOfs:], noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)
		
		bs.seek(BHierarchyAddress)	
		for i in range(0, BCount):
			BoneHash = bs.readUInt()
			bs.readBytes(0xc)
			BoneParent = bs.readInt()
			bs.readUInt()
			BoneHash_array.append(BoneHash)
			BoneParent_array.append(BoneParent)
	
		bs.seek(BoneAddress)
		for i in range(0, BCount):
			BoneName = "Bone {:02x}".format(BoneHash_array[i])
			BonePIdx = BoneParent_array[i]
			Mat44 = NoeMat44.fromBytes(bs.readBytes(0x40))
			Mat43 = Mat44.toMat43().inverse()
			bones.append(NoeBone(i,BoneName, Mat43, None, BonePIdx))
	elif not BoneFlag:
		rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_UBYTE, VBSize, 12)
	
	bs.seek(SubmeshOffset)
	SubmeshesInfo = []
	for j in range(SubmeshesCount):
		SubmeshFaceCount = bs.readUInt()
		bs.readUInt()
		SubmeshBufferOffset = bs.readUInt64()
		SubmeshesInfo.append((SubmeshFaceCount,SubmeshBufferOffset))	
	
	FaceBuff = bs.readBytes(FCount * 3 * 2)	
	for i,info in enumerate(SubmeshesInfo):
		rapi.rpgSetName(fn + str(i))
		material = NoeMaterial('Material ' + fn + str(i), "")
		material.setTexture(fn + str(i) + '_dif')
		material.setNormalTexture(fn + str(i) + '_nml')
		matList.append(material)
		rapi.rpgSetMaterial('Material ' + fn + str(i))
		rapi.rpgCommitTriangles(FaceBuff[info[1]*3*2:info[1]*3*2+info[0]*3*2], noesis.RPGEODATA_USHORT, info[0]*3, noesis.RPGEO_TRIANGLE, 1)
	
	mdl = rapi.rpgConstructModel()
	mdl.setModelMaterials(NoeModelMaterials(texList, matList))
	mdl.setBones(bones)
	
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1	
```


The final versions of the BMS and Noesis scripts are in the attachment.
[GintamaRumble_scripts.7z](https://xentaxbackup.github.io/file/18503_GintamaRumble_scripts.7z)
## Post #11
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-03-05T23:56:35+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

It works with estival versus and later senran kagura games.
## Post #12
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-06T00:00:37+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from ChaoticFusion40 ↑Fri Mar 06, 2020 7:56 am at Fri Mar 06, 2020 7:56 am
>
> 
It works with estival versus and later senran kagura games.

Glad it does, but honestly you should use RandomTalkingBush tools for that, they're more in line with the SK formats. [https://www.vg-resource.com/thread-29836.html](https://www.vg-resource.com/thread-29836.html)
## Post #13
- Username: prettypetal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 04, 2020 3:35 pm
- Post datetime: 2020-06-07T17:16:34+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

finally thanks jousou btw how do you attach the head tho? mines is on the floor
## Post #14
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-07-22T00:54:27+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

I've updated the scripts, now every .CAT file can be extracted with a single bms script, you need to place aluigi's quickbms.exe, the bms script and the bat file in the same directory you have your .CAT files.

Now the TMD script supports models without bones, like stages. Check it [here](https://forum.xentax.com/viewtopic.php?f=16&t=21817#p160618).
## Post #15
- Username: ryukuuma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 28, 2020 10:42 am
- Post datetime: 2020-08-12T21:35:20+00:00
- Post Title: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

I can't preview weapon with the latest script
## Post #16
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-08-13T02:48:00+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from ryukuuma ↑Thu Aug 13, 2020 5:35 am at Thu Aug 13, 2020 5:35 am
>
> 
I can't preview weapon with the latest script

They do display, you may be trying to open the effects TMD, they are the 1 KB files.
## Post #17
- Username: ryukuuma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 28, 2020 10:42 am
- Post datetime: 2020-08-15T18:58:23+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Can you tell me where the weapon located then? I only got kb size on weapo folder
## Post #18
- Username: yoyo123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 10, 2021 4:15 pm
- Post datetime: 2021-05-10T12:54:08+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Hello, excuse me
Did you unpack the. PKG file of gintama rumble first?
## Post #19
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2021-05-10T16:25:47+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from yoyo123 ↑Mon May 10, 2021 8:54 pm at Mon May 10, 2021 8:54 pm
>
> 
Hello, excuse me
Did you unpack the. PKG file of gintama rumble first?

Yes, you have to extract the pkg first.
## Post #20
- Username: yoyo123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 10, 2021 4:15 pm
- Post datetime: 2021-05-11T10:31:51+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

thank you
## Post #21
- Username: dirkthedude
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 14, 2022 5:14 pm
- Post datetime: 2022-05-07T07:28:35+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from JosouKitsune ↑Tue May 11, 2021 12:25 am at Tue May 11, 2021 12:25 am
>
> 
yoyo123 wrote: ↑Mon May 10, 2021 8:54 pm
Hello, excuse me
Did you unpack the. PKG file of gintama rumble first?


Yes, you have to extract the pkg first.

How do you extract the PKG exactly?
## Post #22
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2022-06-26T07:56:05+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

Would it be possible to add compatibility with other tamsoft games?
[cos13.zip](https://xentaxbackup.github.io/file/22425_cos13.zip)
## Post #23
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2023-07-30T16:42:29+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

[https://drive.google.com/file/d/15uQAAo](https://drive.google.com/file/d/15uQAAo) ... sp=sharing
Utawarerumono Zan 2 not working with this noesis script ;-;
## Post #24
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2023-07-30T20:06:44+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from kurokozeref ↑Mon Jul 31, 2023 12:42 am at Mon Jul 31, 2023 12:42 am
>
> 
https://drive.google.com/file/d/15uQAAo ... sp=sharing
 Utawarerumono Zan 2 not working with this noesis script ;-;

You can use the script for Captain Tsubasa: RoNC to preview the models.

You'll need to change the file extension to tmd2

[viewtopic.php?p=166307#p166307](https://forum.xentax.com/viewtopic.php?p=166307#p166307)
## Post #25
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2023-07-31T08:09:07+00:00
- Post Title: Re: (PS4) Gintama Rumble .tmd Noesis Python Script | COMPLETED

> Reply from JosouKitsune ↑Mon Jul 31, 2023 4:06 am at Mon Jul 31, 2023 4:06 am
>
> 
kurokozeref wrote: ↑Mon Jul 31, 2023 12:42 am
https://drive.google.com/file/d/15uQAAo ... sp=sharing
 Utawarerumono Zan 2 not working with this noesis script ;-;


You can use the script for Captain Tsubasa: RoNC to preview the models.

You'll need to change the file extension to tmd2

viewtopic.php?p=166307#p166307

I managed to open it but some of the model will export with super tiny UV (can't be scale, and some UV r just mess up). 
here the sample files that UV r fked (tmd2/cat included):[https://drive.google.com/file/d/19kdwSI ... sp=sharing](https://drive.google.com/file/d/19kdwSIyAzONplBTBS0oHslbAhlSFr_oq/view?usp=sharing)
included no problem model for investigation pl01cos04
