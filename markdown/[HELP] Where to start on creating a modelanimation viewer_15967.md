## Post #1
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-03-07T23:47:31+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

I am really interested in creating a viewer for the models/animation for Rainbow Six Rouge Spear. What coding language would you guys recommend I start with?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-08T06:42:55+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

Did you ever code?
If 'yes' which programming language did you use?
If 'no' it's a bad idea to start with a modelviewer. Check some basic tutorials instead about Java for beginners,
C# (or 'C'). You could also look for python (not recommended, imho  ).

Coding a modelviewer from scratch doesn't make much sense, imho, since there's dozens of sources.

Take a look at hex2obj (view link in my sig) which makes use of mesh_viewer.exe which is a simple one but fulfills my needs. (hex2obj creates an obj file, then calls the viewer with the *.obj as a parameter.)
## Post #3
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-03-09T03:11:00+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

I am familiar with both coding languages. Also, after viewing your suggestion I still do not believe that HextoObj will work; My case is a bit more complex. I have types of files. CRP, SKL, and DAM. 

CRP-Model
SKL-Rig
DAM-animation

I want to create an application that will allow the user to view a model, and play its animations by injecting the .DAM into a .SKL file. That is wh I want to design it from scratch.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-09T03:20:00+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

Noesis can be your model/animation viewer, you just need to feed it your data in C++(?) or Python
## Post #5
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-03-09T03:59:45+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

So if wanted to create a script to read the model files and inject a .DAM(animation) into the .SKL(rig/model) of the model, I would just have to create a simple script from c++ to run off of noesis? The models themselves are really old so I imagine it wouldn't require a ton of work to create such a code.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-09T04:09:44+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

yeah i suppose you could write a dll plugin from C/C#/C++ code, i'm not 100% sure on the languages.
## Post #7
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-03-10T02:14:59+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

Thank you for your answers so far. If you were trying to do this yourself how would you go about it?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-10T03:58:55+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

i'm not qualified to give input on C* language plugin development, i just tinker in python because it easy and fun   
there is some plugin creation info at the bottom of the ReadMe.txt file that comes with noesis though that could 
answer your questions better than i can. it mentions C and C++ so you should be good there, and examples are in
the "pluginsource.zip" that also comes with noesis.
## Post #9
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-03-11T00:31:53+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

Ill give it a shot, if it doesnt work out ill try python as well. Thanks alot!
## Post #10
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-05-14T16:55:27+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

I have busy these past few months, so ive lost my drive a bit; but I am getting back into the swing of things. Instead of creating a separate exe that reads the .SKL and .DAM; I want to create a quickbms script to view the files on Noesis. I did a little searching through HxD and I've discovered that inside the SKL file's (Characters rig) offset shows a value of 
00 11 00 00 00 01. 

[](https://www.4shared.com/photo/mTRArW09ca/r6help0.html)

I thought to myself, "Oh hey, I think I found a pattern here!" so I conducted a search using the same hex-value and- 

[](https://www.4shared.com/photo/B3jnSwHKca/r6help2.html)

Uh-oh! Looks like I ran into a problem here! There aren't any more hex-values that match! I looked into the problem and found out that a similar pattern exists, but the 3rd and 4th digit in the hex-value are different. (I don't think I explained that correctly in hex format and I don't really care.)

Example:
if you look at offset 8E and block 8E-96 (I have that highlighted in red at the bottom left of the screencap) it shows "RightFoot"  on the right.

[](https://www.4shared.com/photo/ctHUTP5uei/r6help3.html)




After the right foot, it shows a bunch of dots "......" which on the left side of HxD you will see 00 11 00 00 00 01 (6-bytes in length)

[](https://www.4shared.com/photo/Xxouoad9ei/r6help4.html)

Now look at this screencap:

[](https://www.4shared.com/photo/MIojupGUca/r6help5.html)

It shows a different bodypart "RightLowLeg", and the hex value in the "......" portion is slightly altered by 4 bytes. 


So I figure I'm in the clear, and can get to the root of my problem when I discover that each hex prior to the body part has a unique length. 

[](https://www.4shared.com/photo/QkFGI-fIca/r6help6.html)

I just cant catch a break today. It shows that the length prior to reaching the first body-part is 8E. Now your wondering, "hey askb, its probably the pattern used to distinguish and separate each body part." 

I mean, it is; but its not consistent. After the 6-byte length pattern that I had noticed prior before the next body-part; I find another pattern that has a length of A8; I'm assuming this is the data of the file. 

[](https://www.4shared.com/photo/xLmWZ7z2ca/r6help7.html)

This pattern continues RightFoot, RightLowLeg, and RightUpLeg; then I reach LeftFoot and it gives me a new length of AD

[](https://www.4shared.com/photo/VrXt3UsNca/r6help8.html)

It seems that after the hex gets to another section of the body altogether (IE: Right side of body to left side, left side to chest, chest to neck) it continues to the pattern of A8 in length (LeftFoot, LeftLowLeg, LeftUpLeg have a length of A8 after the 6 byte "......")

The pattern goes like this:

-Has a Unique pattern in length (specifc sections of the body (Legs, arms, chest, neck, etc))
-Has a consistent pattern of A8 in Length (Separate body-parts from the section: LeftFoot, LeftLowLeg, LeftUpLeg) 
-Has an ending value of 2C (After the 6-byte "......" from Chest)

I must have been dropped on my head recently, but I can't seem to remember how to do anything up to this point. I even completely forgot how to tell the difference between endian.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-15T06:45:17+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

For "RightFoot 00 11 000000":
First zero is the zero termination of the string "RightFoot".
DWORD 11 00 00 00 (little endian) is 17 decimal, boneID (or parenting ID?)

(If it's the parenting ID then the boneID can be derived from the string order probably, 
 first bone name, 'root' for example, bone ID=0, 2nd bone name, bone ID=1, etc)

I usually proceed like this:

 getting bone names
 getting bone IDs and parenting IDs
 looking for hierarchy table (parenting)
 looking for matrices
(4x4 in most cases, rotation matrix and translation vector)

(If you uploaded hsf_exce1_a.skl I could have a look at.)
## Post #12
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-05-16T00:58:45+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

Sure thing, here's the file. In the meantime, im gonna search through the .DAM(animation) file; and see if i can find any patterns with that.
[Rogue Spear.zip](https://xentaxbackup.github.io/file/12893_Rogue Spear.zip)
## Post #13
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-16T02:29:58+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

> Reply from askB
>
> Sure thing, here's the file. In the meantime, im gonna search through the .DAM(animation) file; and see if i can find any patterns with that.

looking at this 


I'm thinking its

```
C String = Name (null-terminated)
UInt32 LE = Bone ID (notice all is unique)
UInt8 1 (always 1)
Bunch-of-Floats (variable length, some is 33 floats long like the RightFoot, or 41 floats long for the RightLowLeg)

```


Looking for this pattern "00 00 00 01" will give you 19 results or (number of bones + 1). You can find number of bones at offset 0x04. "12 00" = 18.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-16T20:24:33+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

just another annoying format? breaking the matrices' analysing by purging some 01/00 sequences in between
which doesn't make sense to me:



bone_matrix.jpg (108.65 KiB) Viewed 176 times

edit: I'd say those 01010100.. are some starting sequence for bone data (0x09: lower body, 0x464: upper body),
so the rotation matrix of RightHand to start at 0x48B with a rotation angle of zero degree?

(offset 0x23A, 0x750: 0100 0100 xx might separate between right and left side, just a wild guess)

Assuming the positions to be located at
offset 0x5E for  RightFoot 8.4425 -94.846 0.9284
and 0x28B: for LefttFoot  -9.185 -94.8 0.268
-----------------------------------------

LeftLowLeg
# 0x381: 
 0.000000 -22.007288 0.552109 
 22.014198 -0.771508 -49.444622 
 0.815535 -0.771508 0.000000 
 0.815535 8.392866 -9.184999 
 -4.152500 -0.000000 0.000000 
 -0.000000 0.000000 1.000000 

 1.000000 0.000000 0.000000 
 0.000000 1.000000 0.000000 
 0.000000 0.000000 1.000000 
 0.000000 0.000000 0.000000 

v -9.184999 -4.152500 -0.000000 
 0.000000 0.000000 0.000000 
 1.000000 0.000000 0.000000 
 0.000000 1.000000 0.000000 
# 0x429


RightCollar 0100 0100 010000


LeftUpLeg
# 0x438: 
 0.000000 -23.314224 -0.418062 
 23.317944 -1.970615 -54.207619 
 -1.123106 -1.970615 0.000000 
 -1.123106 15.045624 

010101 ..01 0000 sequence

# 0x46f:
 -0.000000 -27.445000 -0.000000 
 0.000000 -0.000000 0.000000 
 1.000000 

1.000000 0.000000 0.000000 
0.000000 1.000000 0.000000 
0.000000 0.000000 1.000000 
0.000000 0.000000 0.000000 

20.502531 -9.843071 0.078699 
0.000000 0.000000  0.000000 1.000000 
0.000000  0.000000 0.000000 1.000000 
# 0x4e7

btw: bonename strings zero terminated plus leading DWORD char count+1
## Post #15
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-06-13T00:34:55+00:00
- Post Title: [HELP] Where to start on creating a model/animation viewer

> ~~UInt32 LE = Parent ID (notice some is repeated)~~ (scratch this, as shakotay2 said its actually the string size)
>
> C String = Name (null-terminated)
>
> UInt32 LE = Bone ID (notice all is unique)
>
> UInt8 1 (always 1)
>
> Bunch-of-Floats (variable length, some is 33 floats long like the RightFoot, or 41 floats long for the RightLowLeg)

I did some studying on the script template for noesis; I am having a hard time understanding how i would be able to put something like this into one of the templates they provide. 

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
	handle = noesis.register("Noesis Python Test Model", ".noepy")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
	noesis.setHandlerWriteModel(handle, noepyWriteModel)
	noesis.setHandlerWriteAnim(handle, noepyWriteAnim)

	#noesis.logPopup()
	#print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
	return 1

NOEPY_HEADER = 0x1337455
NOEPY_VERSION = 0x7178173

#check if it's this type based on the data
def noepyCheckType(data):
	if len(data) < 8:
		return 0
	bs = NoeBitStream(data)

	if bs.readInt() != NOEPY_HEADER:
		return 0
	if bs.readInt() != NOEPY_VERSION:
		return 0

	return 1

#load the model
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	if bs.readInt() != NOEPY_HEADER:
		return 0
	if bs.readInt() != NOEPY_VERSION:
		return 0

	meshes = []
	numMeshes = bs.readInt()
	for i in range(0, numMeshes):
		meshName = bs.readString()
		meshMat = bs.readString()
		numIdx = bs.readInt()
		numPos = bs.readInt()
		numNrm = bs.readInt()
		numUVs = bs.readInt()
		numTan = bs.readInt()
		numClr = bs.readInt()
		numWeights = bs.readInt()
		idxList = []
		posList = []
		for j in range(0, numIdx):
			idxList.append(bs.readInt())
		for j in range(0, numPos):
			posList.append(NoeVec3.fromBytes(bs.readBytes(12)))
		mesh = NoeMesh(idxList, posList, meshName, meshMat)
		for j in range(0, numNrm):
			mesh.normals.append(NoeVec3.fromBytes(bs.readBytes(12)))
		for j in range(0, numUVs):
			mesh.uvs.append(NoeVec3.fromBytes(bs.readBytes(12)))
		for j in range(0, numTan):
			mesh.tangents.append(NoeMat43.fromBytes(bs.readBytes(48)))
		for j in range(0, numClr):
			mesh.colors.append(NoeVec4.fromBytes(bs.readBytes(16)))
		for j in range(0, numWeights):
			vwNum = bs.readInt()
			bidx = []
			bwgt = []
			for k in range(0, vwNum):
				bidx.append(bs.readInt())
			for k in range(0, vwNum):
				bwgt.append(bs.readFloat())
			mesh.weights.append(NoeVertWeight(bidx, bwgt))
		mfList = []
		numMorphFrames = bs.readInt()
		for j in range(0, numMorphFrames):
			morphPL = []
			morphNL = []
			numPos = bs.readInt()
			numNrm = bs.readInt()
			for k in range(0, numPos):
				vec = NoeVec3.fromBytes(bs.readBytes(12))
				morphPL.append(vec)
			for k in range(0, numNrm):
				vec = NoeVec3.fromBytes(bs.readBytes(12))
				morphNL.append(vec)
			mf = NoeMorphFrame(morphPL, morphNL)
			mfList.append(mf)
		mesh.setMorphList(mfList)
		meshes.append(mesh)

	bones = []
	numBones = bs.readInt()
	for i in range(0, numBones):
		bone = noepyReadBone(bs)
		bones.append(bone)

	anims = []
	numAnims = bs.readInt()
	for i in range(0, numAnims):
		animName = bs.readString()
		numAnimBones = bs.readInt()
		animBones = []
		for j in range(0, numAnimBones):
			animBone = noepyReadBone(bs)
			animBones.append(animBone)
		animNumFrames = bs.readInt()
		animFrameRate = bs.readFloat()
		numFrameMats = bs.readInt()
		animFrameMats = []
		for j in range(0, numFrameMats):
			frameMat = NoeMat43.fromBytes(bs.readBytes(48))
			animFrameMats.append(frameMat)
		anim = NoeAnim(animName, animBones, animNumFrames, animFrameMats, animFrameRate)
		anims.append(anim)

	mdl = NoeModel(meshes, bones, anims)
	mdlList.append(mdl)			#important, don't forget to put your loaded model in the mdlList

	#this would be the default offset for quake models
	#rapi.setPreviewOption("setAngOfs", "0 180 0")
	return 1

#write it
def noepyWriteModel(mdl, bs):
	anims = rapi.getDeferredAnims()

	bs.writeInt(NOEPY_HEADER)
	bs.writeInt(NOEPY_VERSION)

	bs.writeInt(len(mdl.meshes))
	for mesh in mdl.meshes:
		bs.writeString(mesh.name)
		bs.writeString(mesh.matName)
		bs.writeInt(len(mesh.indices))
		bs.writeInt(len(mesh.positions))
		bs.writeInt(len(mesh.normals))
		bs.writeInt(len(mesh.uvs))
		bs.writeInt(len(mesh.tangents))
		bs.writeInt(len(mesh.colors))
		bs.writeInt(len(mesh.weights))
		for idx in mesh.indices:
			bs.writeInt(idx)
		for vcmp in mesh.positions:
			bs.writeBytes(vcmp.toBytes())
		for vcmp in mesh.normals:
			bs.writeBytes(vcmp.toBytes())
		for vcmp in mesh.uvs:
			bs.writeBytes(vcmp.toBytes())
		for vcmp in mesh.tangents:
			bs.writeBytes(vcmp.toBytes())
		for vcmp in mesh.colors:
			bs.writeBytes(vcmp.toBytes())
		for vcmp in mesh.weights:
			bs.writeInt(vcmp.numWeights())
			for wval in vcmp.indices:
				bs.writeInt(wval)
			for wval in vcmp.weights:
				bs.writeFloat(wval)
		bs.writeInt(len(mesh.morphList))
		for mf in mesh.morphList:
			bs.writeInt(len(mf.positions))
			bs.writeInt(len(mf.normals))
			for vec in mf.positions:
				bs.writeBytes(vec.toBytes())
			for vec in mf.normals:
				bs.writeBytes(vec.toBytes())

	bs.writeInt(len(mdl.bones))
	for bone in mdl.bones:
		noepyWriteBone(bs, bone)

	bs.writeInt(len(anims))
	for anim in anims:
		bs.writeString(anim.name)
		bs.writeInt(len(anim.bones))
		for bone in anim.bones:
			noepyWriteBone(bs, bone)
		bs.writeInt(anim.numFrames)
		bs.writeFloat(anim.frameRate)
		bs.writeInt(len(anim.frameMats))
		for mat in anim.frameMats:
			bs.writeBytes(mat.toBytes())

	return 1

#when you want animation data to be written out with a model format, you should make a handler like this that catches it and defers it
def noepyWriteAnim(anims, bs):
	#it's good practice for an animation-deferring handler to inform the user that the format only supports joint model-anim export
	if rapi.isGeometryTarget() == 0:
		print("WARNING: Stand-alone animations cannot be written to the .noepy format.")
		return 0

	rapi.setDeferredAnims(anims)
	return 0

#write bone
def noepyWriteBone(bs, bone):
	bs.writeInt(bone.index)
	bs.writeString(bone.name)
	bs.writeString(bone.parentName)
	bs.writeInt(bone.parentIndex)
	bs.writeBytes(bone.getMatrix().toBytes())

#read bone
def noepyReadBone(bs):
	boneIndex = bs.readInt()
	boneName = bs.readString()
	bonePName = bs.readString()
	bonePIndex = bs.readInt()
	boneMat = NoeMat43.fromBytes(bs.readBytes(48))
	return NoeBone(boneIndex, boneName, boneMat, bonePName, bonePIndex)




#demonstrates using the rich procedural geometry interface to draw the model into memory, instead of a direct data load
#(not actually used by the script)
def noepyLoadModelRPG(data, mdlList):
	bs = NoeBitStream(data)
	if bs.readInt() != NOEPY_HEADER:
		return 0
	if bs.readInt() != NOEPY_VERSION:
		return 0

	#no need to explicitly free the context (created contexts are auto-freed after the handler), but DO NOT hold any references to it outside of this method
	ctx = rapi.rpgCreateContext()

	numMeshes = bs.readInt()
	for i in range(0, numMeshes):
		meshName = bs.readString()
		meshMat = bs.readString()
		numIdx = bs.readInt()
		numPos = bs.readInt()
		numNrm = bs.readInt()
		numUVs = bs.readInt()
		numTan = bs.readInt()
		numClr = bs.readInt()
		numWeights = bs.readInt()

		rapi.rpgSetName(meshName)
		rapi.rpgSetMaterial(meshMat)

		triangles = bs.readBytes(numIdx * 4)
		positions = bs.readBytes(numPos * 12)
		normals = bs.readBytes(numPos * 12) if numNrm == numPos else None
		uvs = bs.readBytes(numPos * 12) if numUVs == numPos else None
		tans = bs.readBytes(numPos * 48) if numTan == numPos else None
		colors = bs.readBytes(numPos * 16) if numClr == numPos else None

		rapi.rpgBindPositionBuffer(positions, noesis.RPGEODATA_FLOAT, 12)
		rapi.rpgBindNormalBuffer(normals, noesis.RPGEODATA_FLOAT, 12)
		rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_FLOAT, 12)
		rapi.rpgBindColorBuffer(colors, noesis.RPGEODATA_FLOAT, 16, 4)
		if numWeights > 0:
			vwList = []
			for j in range(0, numWeights):
				vwNum = bs.readInt()
				bidx = []
				bwgt = []
				for k in range(0, vwNum):
					bidx.append(bs.readInt())
				for k in range(0, vwNum):
					bwgt.append(bs.readFloat())
				vwList.append(NoeVertWeight(bidx, bwgt))
			fw = NoeFlatWeights(vwList)
			rapi.rpgBindBoneIndexBuffer(fw.flatW[:fw.weightValOfs], noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
			rapi.rpgBindBoneWeightBuffer(fw.flatW[fw.weightValOfs:], noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)
		numMorphFrames = bs.readInt()
		for j in range(0, numMorphFrames):
			numMFPos = bs.readInt()
			numMFNrm = bs.readInt()
			morphPosAr = bs.readBytes(numMFPos * 12)
			rapi.rpgFeedMorphTargetPositions(morphPosAr, noesis.RPGEODATA_FLOAT, 12)
			if numMFNrm > 0:
				morphNrmAr = bs.readBytes(numMFNrm * 12)
				rapi.rpgFeedMorphTargetNormals(morphNrmAr, noesis.RPGEODATA_FLOAT, 12)
			rapi.rpgCommitMorphFrame(numMFPos)
		rapi.rpgCommitMorphFrameSet()

		rapi.rpgCommitTriangles(triangles, noesis.RPGEODATA_INT, numIdx, noesis.RPGEO_TRIANGLE, 1)
		rapi.rpgClearBufferBinds() #reset in case a subsequent mesh doesn't have the same components

		#the mesh could also be drawn in immediate mode like this:
		#rapi.immBegin(noesis.RPGEO_TRIANGLE)
		#for i in range(0, numIdx):
		#	idx = noeUnpackFrom("<i", triangles, i*4)[0]
		#	vcmp = noeUnpackFrom("<ff", uvs, idx*12)
		#	rapi.immUV2(vcmp)
		#	vcmp = noeUnpackFrom("<fff", normals, idx*12)
		#	rapi.immNormal3(vcmp)
		#	vcmp = noeUnpackFrom("<" + "i"*fw.weightsPerVert, fw.flatW, idx*4*fw.weightsPerVert)
		#	rapi.immBoneIndex(vcmp)
		#	vcmp = noeUnpackFrom("<" + "f"*fw.weightsPerVert, fw.flatW, fw.weightValOfs + idx*4*fw.weightsPerVert)
		#	rapi.immBoneWeight(vcmp)
		#	vcmp = noeUnpackFrom("<fff", positions, idx*12)
		#	rapi.immVertex3(vcmp)
		#rapi.immEnd()

	mdl = rapi.rpgConstructModel()

	bones = []
	numBones = bs.readInt()
	for i in range(0, numBones):
		bone = noepyReadBone(bs)
		bones.append(bone)

	anims = []
	numAnims = bs.readInt()
	for i in range(0, numAnims):
		animName = bs.readString()
		numAnimBones = bs.readInt()
		animBones = []
		for j in range(0, numAnimBones):
			animBone = noepyReadBone(bs)
			animBones.append(animBone)
		animNumFrames = bs.readInt()
		animFrameRate = bs.readFloat()
		numFrameMats = bs.readInt()
		animFrameMats = []
		for j in range(0, numFrameMats):
			frameMat = NoeMat43.fromBytes(bs.readBytes(48))
			animFrameMats.append(frameMat)
		anim = NoeAnim(animName, animBones, animNumFrames, animFrameMats, animFrameRate)
		anims.append(anim)

	mdl.setBones(bones)
	mdl.setAnims(anims)
	mdlList.append(mdl)			#important, don't forget to put your loaded model in the mdlList
	return 1

```


Would I be able to use something like this? It searches for the amount of bones and bodyparts that are on the model it is trying to import.
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-06-13T11:44:03+00:00
- Post Title: Re: [HELP] Where to start on creating a model/animation view

you should use the sample script to export an animation then look at the exported animation file in a hex editor.
then follow the script along with the hex as it reads to understand how animation is stored.
Then you should try to re write the importer on your own.
once you do this it should be much easier for you to look at the data in your format and make an import script.
## Post #17
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-06-13T13:11:37+00:00
- Post Title: Re: [HELP] Where to start on creating a model/animation view

Even though there are scripts made for specfic animations, do they generally have the same structure when you code one?
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-06-13T17:53:39+00:00
- Post Title: Re: [HELP] Where to start on creating a model/animation view

animations always follow a close format they just pack the data differently.
one developer could store the entire position each frame or another developer might only keep changes and need the original skeleton complete the animation.
but if you can follow this sample your sample should not be too hard.
## Post #19
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2017-06-21T01:20:52+00:00
- Post Title: Re: [HELP] Where to start on creating a model/animation view

Like always, I appreciate all of everyone assistance thus far; im starting to understand how data is read through hexing. However, I cant code python...at all. Ive decided to take a class on basic python scripting, then within in a few weeks try to create a script using what you all have provided for me.
