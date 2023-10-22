## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T06:46:08+00:00
- Post Title: Approaches of Parsing Bone Representations

As far as I know, bones are a set of linked nodes with transformation info includes translation, rotation and scaling, and due to the various representations of rotation, there're mostly 3 forms of representing a bone: Euler angle, rotation matrix and quaternion combined with the rest transformation. 

Recognizing these forms is not a big deal, but parsing them correctly is. Therefore I decided to create a thread for an in-depth discussion of the common approaches of parsing different forms of bone representations, hopefully to give those who have only a scanty knowledge to this topic, me included, a hint of parsing a specific bone format.

For those who're completely new to these stuffs, you can refer to the [Background/Basic Knowledge](http://forum.xentax.com/viewtopic.php?f=29&t=19428) for a rough understanding.

Since I'd like to focus on parsing bones correctly, I will use minimum dumps of bone data only as samples, and a quick approach to build the skeleton, which in my case would be SkelBuilder — a lightweight ASCII FBX creator I made for constructing skeleton only, after countless failures with Noesis. Guess I may also post the Noesis python code to see if someone could spot the issues. But any other approaches are fine, so long as it's easy for understanding the process. 

Source of SkelBuilder(Bone data not included).


 SkelBuilder_VS2015.zip
v0.3.1 (14.66 KiB) Downloaded 150 times



There're several working demonstrations in the source so I'm not exploring the usage here.

Quick entrance:
Right-Handed System
Quaternion Rotation
Asphalt 8: Airborne (Android)
Asphalt 9: Legends (Android)
GuJian3 (PC)
Ben 10 Ultimate Alien: Cosmic Destruction (Xbox 360)

3x3 Matrices
Ben 10 Omniverse (Xbox 360)

3x4 Matrices
Ben 10 Omniverse 2 (3DS)

4x4 Matrices

Left-Handed System
Quaternion Rotation
Assalt Fire (PC)
James Cameron's AVATAR THE GAME (PC)
League of Angels III (Browser)

3x3 Matrices
Star Wars: Episode III – Revenge of the Sith (Xbox)

4x4 Matrices
Iron Man 2 (PS3)
Cyber Hunter (Android)
IDOLM@STER One For All (PS3)

Conclusion:
So far, seems there's no extra things needed to do for right-handed formats. For left-handed formats, you'll need to convert the transformation in world space of every node to right-handed one. In some circumstances, swapping the x-z axis can do the trick.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T06:54:47+00:00
- Post Title: Approaches of Parsing Bone Representations

Think I'll start with a few working examples first. 


 car_pagani_huayra.zip
(1.11 KiB) Downloaded 77 times



```
# From Game: Asphalt 8: Airborne
# Platform: Android
# Bone Format: Quaternion Rotation, Translation
# Coordinate System: Right-Hand
# Endian: Little

```

Bone data structure:

```
word	boneCount
for i = 0 < boneCount
	long	Signature
	word	nameLen
	char	boneName[nameLen]
	char	Zero
	short	parentID
	float	Translation[3]
	float	Rotation[4] // Quaternion Rotation
	float	Scaling[3]
	char	NULL[6]
```

Very simple format and since it's already in right-handed system, you don't even need to worry about the convertion between different coordinate systems. 
Transformation is referenced to parent space so just need to convert quaternion to Euler angle. It's even working with Noesis.



Noesis python code:

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	boneCount = bs.readUShort()
	bones = []
	for i in range(0, boneCount):
		bs.seek(4, NOESEEK_REL)
		NameLen = bs.readUShort()
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		bs.seek(1, NOESEEK_REL)
		bonePIndex = bs.readShort()
		Tran = NoeVec3.fromBytes(bs.readBytes(12))
		Rot = NoeQuat.fromBytes(bs.readBytes(16))
		Scal = NoeVec3.fromBytes(bs.readBytes(12))
		bs.seek(6, NOESEEK_REL)
		boneMat = Rot.toMat43(transposed = 1)
		boneMat[3] = Tran
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
			
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "-90 0 0")
	return 1
```
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T07:01:06+00:00
- Post Title: Approaches of Parsing Bone Representations

Similiar format like Asphalt 8. 


 Genty_Akylone_car.json.zip
(1.42 KiB) Downloaded 47 times



```
# From Game: Asphalt 9: Legends
# Platform: Android
# Bone Format: Quaternion Rotation, Translation
# Coordinate System: Right-Hand
# Engine: Jet Engine
# Endian: Little
```

Bone data format:

```
long	boneDataOffset
word	boneCount
byte	Skip2[0x1C]
for i = 0 < boneCount
	word	nameLen
	char	boneName[nameLen]
	short	parentID
	float	Translation[3]
	float	Rotation[4] // Quaternion Rotation
	float	Scaling[3]
	word	NULL
```



Noesis python code:

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	bs.seek(0x11, NOESEEK_ABS)
	boneOffset = bs.readUInt()
	boneCount = bs.readUShort()
	bs.seek(boneOffset, NOESEEK_ABS)
	bones = []
	for i in range(0, boneCount):
		NameLen = bs.readUShort()
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		bonePIndex = bs.readShort()
		Tran = NoeVec3.fromBytes(bs.readBytes(12))
		Rot = NoeQuat.fromBytes(bs.readBytes(16))
		Scal = NoeVec3.fromBytes(bs.readBytes(12))
		bs.seek(2, NOESEEK_REL)
		boneMat = Rot.toMat43(transposed = 0)
		boneMat[3] = Tran
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
			
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 0 180")
	return 1
```
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T07:06:18+00:00
- Post Title: Approaches of Parsing Bone Representations

VenomSkel.zip
(2.28 KiB) Downloaded 56 times



```
# From Game: Assalt Fire
# Platform: PC
# Bone Format: Quaternion Rotation, Translation
# Coordinate System: Left-Hand
# Engine: Unreal Engine
# Endian: Little
```

Bone data structure:

```
for i = 0 < boneCount
	long	boneNameIdx // Indexing to original string buffer
	long	NULL
	long	NULL
	float	Rotation[4] // Quaternion Rotation
	float	Translation[3]
	long	Unknown
	long	parentID
	long	Marker // FFFFFFFF
for i = 0 < boneCount
	string	boneName	// Mapping to bone[i]
```

Unreal Engine use left-handed system so need to flip the XZ-axis to fit with right-handed system. Transformation is also in parent space.



Noesis code works now thanks to shakotay2's correction(lack convertion to right-handed though):

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	boneCount = bs.readUInt()
	bs.seek(boneCount * 0x34, NOESEEK_REL)
	boneNames = []
	for i in range(0, boneCount):
		boneNames.append(bs.readString())
	bs.seek(0x4, NOESEEK_ABS)
	bones = []
	for i in range(0, boneCount):
		bs.seek(12, NOESEEK_REL)
		Rot = NoeQuat.fromBytes(bs.readBytes(16))
		Tran = NoeVec3.fromBytes(bs.readBytes(12))
		bs.seek(4, NOESEEK_REL)
		bonePIndex = bs.readInt()
		if bonePIndex == i:
			bonePIndex = -1
		bs.seek(4, NOESEEK_REL)
		boneMat = Rot.toMat43(1)
		boneMat[3] = Tran
		bones.append(NoeBone(i, boneNames[i], boneMat, None, bonePIndex))
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 90 0")
	return 1

```
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T07:12:23+00:00
- Post Title: Approaches of Parsing Bone Representations

CHAR_Bloxx.zip
(1.55 KiB) Downloaded 78 times



```
# From Game: Ben 10 Omniverse
# Platform: Xbox 360
# Bone Format: 3x3 Matrices, Translations
# Coordinate System: Right-Hand
# Engine: Vicious Engine 2
# Endian: Big
```

Bone data structure:

```
for i = 0 < boneCount
	long	parentID
	float	Translation[3]
	float	Rotation[3][3]
	long	nameLen
	char	boneName[nameLen]
	long	Unknown

```

The 3x3 rotation matries are in column-major order so need to transpose them before converting to Euler angles.



Noesis code works now thanks to shakotay2's correction:

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data, NOE_BIGENDIAN)
	boneCount = bs.readUInt()
	bones = []
	for i in range(0, boneCount):
		bonePIndex = bs.readInt()
		Matrix = []
		for j in range(0, 12):
			Matrix.append(bs.readFloat())
		boneMat = NoeMat43( [(Matrix[3],Matrix[4],Matrix[5]), 
								 (Matrix[6],Matrix[7],Matrix[8]), 
								 (Matrix[9],Matrix[10],Matrix[11]), 
								 (Matrix[0],Matrix[1],Matrix[2])] ).transpose()
		NameLen = bs.readInt()
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		bs.seek(4, NOESEEK_REL)
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 90 0")
	return 1

```
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T07:19:45+00:00
- Post Title: Approaches of Parsing Bone Representations

suitUpTony.zip
(4.03 KiB) Downloaded 53 times



```
# From Game: Iron Man 2
# Platform: PS3
# Bone Format: 4x4 Matrices
# Coordinate System: Left-Hand
# Endian: Big
```

Bone data structure:

```
long	indexOffset // Relative from 0x10
long	boneNameOffset // Relative from 0x10
long	boneCount
for i = 0 < boneCount
	long	boneID
	long	parentID
	long	RelBoneNameOffset // Relative from boneNameOffset
	float	boneMat[4][4]
long	boneIdx[boneCount]
for i = 0 < boneCount
	string	boneName
```


If you'd tried loading the data as ordinary matrices but seen something like this:



then the matries should probably have been inversed.

Also the transformation is in world space so altogether you need to inverse the matrices first, then convert them to right-handed system and finally, to parent space for FBX format.



Noesis code (lack convertion to right-handed):

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data, NOE_BIGENDIAN)
	bs.seek(8, NOESEEK_ABS)
	indexOffset = bs.readUInt() + 0x10
	boneNameOffset = bs.readUInt() + 0x10
	boneCount = bs.readUInt()
	boneIDs=[]
	boneNames = []
	bs.seek(indexOffset, NOESEEK_ABS)
	for i in range(0, boneCount):
		boneIDs.append(bs.readUInt())
	for i in range(0, boneCount):
		boneNames.append(bs.readString())
	bs.seek(0x14, NOESEEK_ABS)
	bones = []
	for i in range(0, boneCount):
		boneIndex = bs.readInt()
		bonePIndex = bs.readInt()
		RelBoneNameOffset = bs.readInt()
		if boneIndex == bonePIndex:
			bonePIndex = -1
		Mat44 = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_BIGENDIAN )
		boneMat = Mat44.toMat43().inverse()
		bones.append( NoeBone(boneIndex, boneNames[boneIndex], boneMat, None, bonePIndex) )#boneIDs[i]
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	#rapi.setPreviewOption("setAngOfs", "0 0 0")
	return 1

```
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-03T20:40:46+00:00
- Post Title: Approaches of Parsing Bone Representations

(pmed you) seems you need to replace "while" like such for .ve2/.AFM:
      j = bones.parentIndex
      if j != -1:
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-12T05:02:22+00:00
- Post Title: Approaches of Parsing Bone Representations

leonopteryx.zip
(5.37 KiB) Downloaded 41 times



```
# From Game: James Cameron's AVATAR THE GAME
# Platform: PC
# Bone Format: Quaternion Rotation, Translation
# Coordinate System: Left-Hand
# Engine: Dunia Engine
# Endian: Little

```

Bone data structure:

```
for i = 0 < boneCount	
	long 	CRC?
	long 	boneIndex // sometimes -1
	long 	Unknown
	long 	parentIndex
	float	Rotation[4] // Quaternion
	float	Tanslation[3]
	float	Scaling[3]
	long 	Unknown[3]
	long 	boneNameLen
	char 	boneName[boneNameLen + 1] // null-terminated

```

Same procedure as for Assalt Fire.	



Noesis code(lack convertion to right-handed):

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	boneCount = bs.readUInt()
	bones = []
	for i in range(0, boneCount):
		bs.seek(0xC, NOESEEK_REL)
		bonePIndex = bs.readInt()
		Rot = NoeQuat.fromBytes(bs.readBytes(16))
		Tran = NoeVec3.fromBytes(bs.readBytes(12))
		bs.seek(0x18, NOESEEK_REL)
		NameLen = bs.readUInt() + 1
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		boneMat = Rot.toMat43(transposed = 1)
		boneMat[3] = Tran
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
			
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 -90 0")
	return 1

```
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-12T05:09:06+00:00
- Post Title: Approaches of Parsing Bone Representations

Rath.zip
(4.56 KiB) Downloaded 63 times



```
# From Game: Ben 10 Omniverse 2
# Platform: 3DS
# Bone Format: 3x4 Matrix
# Coordinate System: Right-Hand
# Endian: Little

```

Bone data structure:

```
long	boneDataOffset // Absolute
long	boneCount
long	Skip[4]

for i = 0 < boneCount
	long 	Unknown
	short	UnknownID1
	short	UnknownID2
	long 	UnknownOffset // useless
	long 	boneDataOffset // relative from this field
		
for i = 0 < boneCount	
	long 	Ignore[2]
	long 	boneIndex
	long 	parentIndex?
	long 	Ignore[4]
	float	Scaling[3]
	float	Rotation[3] // Euler, in radian
	float	Translation[3]
	
	float	Mat34[12] // row-major
	float	identityMatrix[12] // row-major
	float	Mat34Reverse[12] // row-major
	
	float	Null[3]

```

Similar to Ben 10 Omniverse on Xbox 360 except the matries are packed. Guess the tricky part would be identifying the parent IDs and the required matries.



Noesis code:

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	bs.seek(8, NOESEEK_REL)
	boneCount = bs.readUInt()
	bs.seek(boneCount * 0x10 + 0x10, NOESEEK_REL)
	bones = []
	#noesis.logPopup()
	for i in range(0, boneCount):
		bs.seek(8, NOESEEK_REL)
		boneIndex = bs.readInt()
		bonePIndex = bs.readInt()
		bs.seek(0x34, NOESEEK_REL)
		Matrix = []
		for j in range(0, 12):
			Matrix.append(bs.readFloat())
		boneMat = NoeMat43( [(Matrix[0],Matrix[1],Matrix[2]), 
							 (Matrix[4],Matrix[5],Matrix[6]), 
							 (Matrix[8],Matrix[9],Matrix[10]), 
							 (Matrix[3],Matrix[7],Matrix[11])] )#.transpose()
		bs.seek(0x6C, NOESEEK_REL)
		bones.append( NoeBone(boneIndex, 'bone%02d'%i, boneMat, None, bonePIndex) )
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	return 1

```
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-12T05:12:20+00:00
- Post Title: Approaches of Parsing Bone Representations

mermaid_normal.zip
(6.29 KiB) Downloaded 37 times



```
# From Game: GuJian3
# Platform: PC
# Bone Format: Translation, Quaternion
# Coordinate System: Right-Hand
# Engine: Vision Engine
# Endian: Little

```

Bone data structure:

```
for i = 0 < boneCount	
	long 	nameLen
	char 	Name[nameLen]
	short	parentID
	
	float	UnknownTranslation[3]
	float	UnknownRotation[4] // Quaternion
	
	float	Translation[3]
	float	Rotation[4] // Quaternion

```

Similiar to previous examples.



Noesis code:

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	boneCount = bs.readUShort()
	bones = []
	for i in range(0, boneCount):
		NameLen = bs.readInt()
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		bonePIndex = bs.readShort()
		bs.seek(28, NOESEEK_REL)
		Tran = NoeVec3.fromBytes(bs.readBytes(12))
		Rot = NoeQuat.fromBytes(bs.readBytes(16))
		boneMat = Rot.toMat43(transposed = 0)
		boneMat[3] = Tran
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
			
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 -90 0")
	return 1

```
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-11T13:41:22+00:00
- Post Title: Approaches of Parsing Bone Representations

base02.zip
(9.4 KiB) Downloaded 40 times



```
# From Game: Cyber Hunter
# Platform: Android
# Bone Format: 4x4 Matrices
# Coordinate System: Left-Hand
# Endian: Little

```

Bone data structure:

```
for i = 0 < boneCount
	BYTE	parentID // 0xFF means parentless
for i = 0 < boneCount
	char	boneName[32]
for i = 0 < boneCount
	float	boneMatrix[16] // Column-major
```

The matrices are in world space while FBX parenting is in parent space. So they need to be converted to parent space by premultiply the inverse
of world matrix of their parents'. This format uses DirectX axis system, and swapping the X-Z axis simply won't work. So you need to convert the world space matrix of each node to right-handed before the premultiplication.
Check the code in the source for details.



Noesis python code(lack convertion to right-handed):

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	boneCount = bs.readShort()
	pIDs= []
	for i in range(0, boneCount):
		aByte = bs.readUByte()
		if aByte != 0xFF:
			pIDs.append(aByte & 0xFF)
		else:
			pIDs.append(-1)
	
	nameList = []
	for i in range(0, boneCount):
		boneName = noeStrFromBytes(bs.readBytes(32), "ASCII")
		nameList.append(boneName)
	
	bones = []
	for i in range(0, boneCount):
		Matrix = []
		for j in range(0, 16):
			Matrix.append(bs.readFloat())
		boneMat = NoeMat43( [(Matrix[0],Matrix[4],Matrix[8]), 
				(Matrix[1],Matrix[5],Matrix[9]), 
				(Matrix[2],Matrix[6],Matrix[10]), 
				(Matrix[12],Matrix[13],Matrix[14])] )
		bones.append( NoeBone(i, nameList[i], boneMat, None, pIDs[i]) )
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	return 1
```
## Post #12
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-08-17T22:01:16+00:00
- Post Title: Approaches of Parsing Bone Representations

Hi Bigchillghost,

first id like to thank you for this great tutorial, its the only tutorial i found online i could actually understand regarding bone data 
iv been trying to follow all of your examples and can reproduce all the results until i get to the following line in noesis:

bones.setMatrix(bones.getMatrix().__mul__(bones[j].getMatrix()))

could you please explain what it does?

iv also went over you C code, but it seems there you 
1. read the translation vector, 
2. read rotation 3x3 matrix then transpose the 3x3
3. then in function (Matrix33ToRS) calculate what i am assuming is in world coordinates scaling vector and rotation vector - but not sure what to do with this
i would be happy for a small explanation 

Thanks allot 


at the moment i am trying to work on the following model:
# Dump Name: CHAR_Bloxx.ve2
# From Game: Ben 10 Omniverse
# Platform: Xbox 360[/i]
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-18T01:32:01+00:00
- Post Title: Approaches of Parsing Bone Representations

> Reply from jayn23 ↑Sun Aug 18, 2019 6:01 am at Sun Aug 18, 2019 6:01 am
>
> bones.setMatrix(bones.getMatrix().__mul__(bones[j].getMatrix()))

could you please explain what it does?
To multiply the node's local matrix with the one of its parent so as to obtain its world transformation. Technically you need to do it recursively for a node in a tree structure untill you reach the root, but in Noesis for some unknown reasons you just need to do it once. So you might just consider that as a fixed routine to convert a local bone tree to world space.

> Reply from jayn23 ↑Sun Aug 18, 2019 6:01 am at Sun Aug 18, 2019 6:01 am
>
> then in function (Matrix33ToRS) calculate what i am assuming is in world coordinates scaling vector and rotation vector - but not sure what to do with this
You should probably know that FBX nodes are in parent space, which is opposite to Noesis. And what Matrix33ToRS does is to extract the Euler rotation and scaling vectors from a 3x3 row-major matrix, regardless whether it's in parent space or world space. In this case, you got parent space transformation. That's what's required for an FBX node.
## Post #14
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-08-18T11:48:35+00:00
- Post Title: Approaches of Parsing Bone Representations

Thanks for the fast reply, i guess i should read about FBX format now  

> Reply from Bigchillghost ↑Sun Aug 18, 2019 9:32 am at Sun Aug 18, 2019 9:32 am
>
> 
multiply the node's local matrix with the one of its parent so as to obtain its world transformation.
 the problem with this, is since you read the translation matrix with 3x3 matrix you get a 4x3 matrix, and you cant multiply 4x3 by 4x3 since num of columns on matrix1 should equal num of rows on matrix2.
it seems like a i am missing something here.

Until now iv just been studying the diffrent forms bones can appear in 3d files, and the code needed to extract them.
any tips on recognizing the kind of bone data: Quaternion  left or right, Row-major or columns-major. etc.. or is it just experience?

thnaks for all your help
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-18T13:59:53+00:00
- Post Title: Approaches of Parsing Bone Representations

> Reply from jayn23 ↑Sun Aug 18, 2019 7:48 pm at Sun Aug 18, 2019 7:48 pm
>
> 
the problem with this, is since you read the translation matrix with 3x3 matrix you get a 4x3 matrix,
First of all, it's not a "translation matrix", but a translation "vector". Be careful using proper terms to avoid confusion.

> Reply from jayn23 ↑Sun Aug 18, 2019 7:48 pm at Sun Aug 18, 2019 7:48 pm
>
> and you cant multiply 4x3 by 4x3 since num of columns on matrix1 should equal num of rows on matrix2.
Mathmatically, you can't. In programing it's not necessarily to store the matrix as a 4x4 one since the last row is constant.

> Reply from jayn23 ↑Sun Aug 18, 2019 7:48 pm at Sun Aug 18, 2019 7:48 pm
>
> 
any tips on recognizing the kind of bone data: Quaternion  left or right, Row-major or columns-major. etc.. or is it just experience?
For recognition of handedness, just load a mesh into a 3D app and see if it's mirrored compared with its in-game look or if the face normals are inverted. To distinguish the matrix storage, first you need to determine whether it's a 4x4 matrix, or a 3x3 one. You can easily tell by looking for the (0 0 0 1) vector. For a 4x4 matrix, it's easy once you find the translation vector, which could contain values out of the range of -1.0 to +1.0. For a 4x3 matrix, since it can also be a 3x3 matrix followed by a translation vector, there's no universal recipe. Just try to parse them respectively and see which one reveals the correct result. So yes it requires experience, but also knowledge.
## Post #16
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-08-18T20:25:13+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

Thanks for all the great tips    

i feel kind of stupid with this but i cant seem to get the correct numbers for world transformation, and was hoping you could look at the numbers and maybe tell me what i am doing wrong:
I have a picture of debug console  of noesis where first line(bones1)  is original 4x3 matrix while second line(bones2) in world transformation.
up until  i = 2 i get the correct answer by multiplying bone * bone[i-1] etc..
from i =3 no matter what combination i do i dont get the same result.
what i am doing is  Matrix[3]*matrix[2]*matrix[1]*matrix[0], i tried a few other combinations including matrix[3]*matrix[2]-world transformation but none give the same result as noesis.

i dont know how important it is to understand this if noesis does this , but it bugs the hell out of me that i cant figure it out  
[NOESSIS.PNG](https://xentaxbackup.github.io/file/16620_NOESSIS.PNG)
## Post #17
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-08-18T20:27:51+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

couldn't add  a second attachment before, here are my matrices:
if i understood correctly:

for i =3
Bones[3] * Bones[2] * Bones[1]* Bones[0] = answer
[code.PNG](https://xentaxbackup.github.io/file/16621_code.PNG)
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-19T04:51:04+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

> Reply from jayn23 ↑Mon Aug 19, 2019 4:25 am at Mon Aug 19, 2019 4:25 am
>
> 
what i am doing is  Matrix[3]*matrix[2]*matrix[1]*matrix[0]
It should be matrix[0]*matrix[1]*matrix[2]*matrix[3] since it's row-major matrix.



noe.png (78.43 KiB) Viewed 516 times



> Reply from jayn23 ↑Mon Aug 19, 2019 4:25 am at Mon Aug 19, 2019 4:25 am
>
> 
i dont know how important it is to understand this if noesis does this , but it bugs the hell out of me that i cant figure it out
Theoretically to convert a parent space tree to world space, you need to premultiply each node in a level with its parent recurrently from the root level down to the last level, or use other methods that have the same effect. So it doesn't matter how Noesis does it, so long as it works as expected. But you should know at least one way to convert it yourself.
## Post #19
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-08-19T08:11:47+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

Ill take a look at the numbers when i get home, but i am sure ill get it to work now.

Thanks a lot for all your help and fast reply's i really appreciate it.
## Post #20
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-08-23T06:17:39+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

Hello,and sorry to disturb you. 
Could you analysis the bigworld engine model?I can't find any ather idears.
[http://www.mediafire.com/file/g432vuf89 ... 05408/file](http://www.mediafire.com/file/g432vuf8986v70m/605408/file)
this is a sample. bone file is .visual 
Thanks
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-09T08:12:43+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

chr_body_rank_104_a_slender.zip
(10.48 KiB) Downloaded 35 times



```
# From Game: IDOLM@STER One For All
# Platform: PS3
# Bone Format: 4x4 Matrices (inversed)
# Coordinate System: Left-Hand
# Endian: Big

```

Bone data structure:

```
for i = 0 < boneCount
	long	boneID
	long	structSize
	long	unknown
	char	boneName[0x20]
	long	parentID
	byte	skip[0x9C]
	float	boneMat[4][4] // Column-major
	byte	skip2[0xC]

```

Same procedure as for Iron Man 2. Probably some kind of "feature" of PS3 games?

Noesis code(lack convertion to right-handed):

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data, NOE_BIGENDIAN)
	boneCount = bs.readInt()
	bones = []
	for i in range(0, boneCount):
		boneID = bs.readInt()
		bs.seek(8, NOESEEK_REL)
		boneName = noeStrFromBytes(bs.readBytes(0x20), "UTF8")
		if boneName == "":
			boneName = "Scene Root"
		parentID = bs.readInt()
		bs.seek(0x9C, NOESEEK_REL)
		Mat44 = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_BIGENDIAN )
		boneMat = Mat44.toMat43().inverse()
		bs.seek(0x10, NOESEEK_REL)
		bones.append( NoeBone(boneID, boneName, boneMat, None, parentID) )
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	return 1

```
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-11T10:53:18+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

g_uec.zip
(1.56 KiB) Downloaded 34 times



```
# From Game: Ben 10 Ultimate Alien: Cosmic Destruction
# Platform: XBOX 360
# Bone Format: Quaternion Rotation, Translation
# Coordinate System: Right-Hand
# Engine: Vicious Engine
# Endian: Big

```

Bone data structure:

```
word	boneCount
byte	itemBoneCount
byte	itemBoneCount
word	skip
for i = 0 < boneCount
	float	Rotation[4] // Quaternion Rotation
	float	Translation[3]
	float	Scaling[3]
	char	parentID
	byte	skip[3]
for i = 0 < itemBoneCount
	float	Rotation[4] // Quaternion Rotation
	float	Translation[3]
	char	parentID
	byte	skip[3]

```

Similar procedures as previous examples. Just with an extra bone list.

Noesis code:

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data, NOE_BIGENDIAN)
	boneCount = bs.readUShort()
	bs.seek(2, NOESEEK_REL)
	itemBoneCount = bs.readUByte()
	bs.seek(7, NOESEEK_REL)
	bones = []
	for i in range(0, boneCount):
		Rot = NoeQuat.fromBytes(bs.readBytes(16), NOE_BIGENDIAN)
		Tran = NoeVec3.fromBytes(bs.readBytes(12), NOE_BIGENDIAN)
		Scal = NoeVec3.fromBytes(bs.readBytes(12), NOE_BIGENDIAN)
		bonePIndex = bs.readByte()
		bs.seek(3, NOESEEK_REL)
		boneMat = Rot.toMat43(transposed = 0)
		boneMat[3] = Tran
		bones.append( NoeBone(i, "bone%03d"%i, boneMat, None, bonePIndex) )
	for i in range(0, itemBoneCount):
		Rot = NoeQuat.fromBytes(bs.readBytes(16), NOE_BIGENDIAN)
		Tran = NoeVec3.fromBytes(bs.readBytes(12), NOE_BIGENDIAN)
		bonePIndex = bs.readByte()
		bs.seek(3, NOESEEK_REL)
		boneMat = Rot.toMat43(transposed = 0)
		boneMat[3] = Tran
		idx = boneCount + i
		bones.append( NoeBone(idx, "bone%03d"%idx, boneMat, None, bonePIndex) )
	totalBoneCount = boneCount + itemBoneCount
	# Converting local matrix to world space
	for i in range(0, totalBoneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )
			
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	return 1

```
## Post #23
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-11T11:08:43+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

Time for some clarification. 

Why would the following method of converting a parent-space bone tree to world space work within Noesis?

```
	j = bones[i].parentIndex
	if j != -1:
		bones[i].setMatrix( bones[i].getMatrix() * bones[j].getMatrix() )

```


It has nothing to do with Noesis' feature but simply because it's logically correct for any organized bone list.

Let's see how the bone nodes are usually stored.

(bone tree of g_uec.ve1 from Ben 10 Ultimate Alien: Cosmic Destruction)


The number of each node equals to its index in the node list, the same below.

And this diagram shows how the nodes are traversed.



As you can see, the traversal order of the nodes is exactly aligned to how they're stored in the bone list. 

Bones stored as above are in the so-called depth-first traversal order. However it can also apply to bone list in breadth-first storage.

(bone tree of mermaid_normal.model from GuJian3)


The traversal order of the list:



So long as the bone nodes in the list are organized in a way where any node is stored after its parent node, this method will work correctly.
## Post #24
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-01T14:18:27+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

Can you read the bones from forza 4 car? It has 75 bones
[BUG_Chiron_17_skeleton.rar](https://xentaxbackup.github.io/file/17859_BUG_Chiron_17_skeleton.rar)
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-26T14:17:21+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

anakinhooddown.zip
(2.89 KiB) Downloaded 33 times



```
# From Game: Star Wars: Episode III – Revenge of the Sith
# Platform: Xbox
# Bone Format: 3x3 Matrices
# Coordinate System: Left-Hand
# Endian: Little

```

Bone data structure:

```
for i = 0 < boneCount
	char	boneName[0x20]
	float	Rotation[3][3] // column-major
	float	Translation[3]
	short	parentID

```


The rotation matrices are in column-major so transposes are required. 
Also similar to Iron Man 2 and IDOLM@STER One For All, they need to be inversed.

Noesis code (lack convertion to right-handed):

```
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	boneCount = bs.readUInt()
	bones = []
	for i in range(0, boneCount):
		pos = bs.tell() + 0x20
		boneName = bs.readString()
		bs.seek(pos, NOESEEK_ABS)
		boneMat = NoeMat43.fromBytes(bs.readBytes(48)).transpose().inverse()
		bonePIndex = bs.readShort()
		bones.append(NoeBone(i, boneName, boneMat, None, bonePIndex))
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	return 1

```
## Post #26
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-26T19:01:30+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

Hi  Bigchillghost,

Thanks for updating this thread all the time, i still find my self checking it out every now and then to give me ideas how to do things its very useful   

> Noesis code (lack convertion to right-handed):
apparently rich thought about this to, yesterday i found a built in function for swapping from left to right hand and thought you might be interested.

```
boneMat = NoeMat43.fromBytes(bs.readBytes(48)).transpose().inverse().swapHandedness(0)
```

swapHandedness (axis) while axis can be 0,1,2
for anakin it worked with 0
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-27T03:15:15+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

> Reply from jayn23 ↑Wed May 27, 2020 3:01 am at Wed May 27, 2020 3:01 am
>
> 
i still find my self checking it out every now and then to give me ideas how to do things its very useful
Good to know.  

> yesterday i found a built in function for swapping from left to right hand and thought you might be interested.
Yeah I noticed that long time ago but never get it working. It appears that I mistook that function as one that affects the object itself and didn't overwrite the original matrix with the swapped one. I tested the other left-handed formats posted in this thread but some of them seem to be in right-handed already(Aavtar The Game, Iron Man 2 and IDOLM@STER). Not sure if it's because they use a different naming aspect from the others so I'll leave them as they are. Thanks for the hint anyway.
## Post #28
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-22T07:15:42+00:00
- Post Title: Re: Approaches of Parsing Bone Representations

mount_001_h.zip
(1.58 KiB) Downloaded 23 times



```
# From Game: League of Angels III
# Platform: PC (Browser)
# Bone Format: Quaternion Rotation, Translation
# Coordinate System: Left-Hand
# Endian: Little

```

Bone data structure:

```
for i = 0 < boneCount
	short	NameLen
	char	Name[NameLen+1]
	long	parentID
	float	Translation[3]
	float	Rotation[3] // Quaternion Rotation

```

This is really an ambiguous one because it stores the quaternion rotations as 3D vectors, which most possibly will leads to the assumption that they are Euler angles in radian. Also the transformation is stored in world space so any attempts to interpret the rotations in different manners simply won't produce any visual difference on the skeleton. But if you print out all the rotation vectors, you'll notice some special values like (-0.7071067690849304, -0.0005837682983838022, 0.7071067690849304) where 0.707106 is approximately sqrt(2)/2, so the square sum of this vector happens to be 1.0, hence the conclusion that the rotations are stored as quaternions. The 'w' factors can be calculated since they're unit vectors.

Noesis code(lack convertion to right-handed):

```
def noepyLoadModel(data, mdlList):
	noesis.logPopup()
	bs = NoeBitStream(data)
	boneCount = bs.readInt()
	bones = []
	for i in range(0, boneCount):
		NameLen = bs.readShort() + 1
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		bonePIndex = bs.readInt()
		tran = NoeVec3.fromBytes(bs.readBytes(12))
		rot = NoeQuat3.fromBytes(bs.readBytes(12))
		print(rot)
		boneMat = rot.toQuat().toMat43()
		boneMat[3] = tran
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 -90 0")
	return 1

```
