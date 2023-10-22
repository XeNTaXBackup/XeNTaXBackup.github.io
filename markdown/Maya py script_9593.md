## Post #1
- Username: TheDude
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-03T21:38:03+00:00
- Post Title: Maya py script

here is a sample maya py import script for hatsune miku for ipad.
its working great now including uv's
maya help
[http://download.autodesk.com/us/maya/20 ... f40f22b125](http://download.autodesk.com/us/maya/2010help/api/class_m_fn_mesh.html#5b9f4c3cf1438bfca200f7f40f22b125)

```
# Maya Python script

import maya.cmds as cmds
import maya.OpenMaya as om
import struct

def get_mobject(node):
	selectionList = om.MSelectionList()
	selectionList.add(node)
	oNode = om.MObject()
	selectionList.getDependNode(0, oNode)
	return oNode 

fname = cmds.fileDialog2(fm=1, ff='Music Girl:Hatsune Miku .mdl (*.mdl);;All Files (*.*)')[0]
f = open(fname, "rb")

magic = struct.unpack("4s",f.read(4))[0]
header = struct.unpack("4i",f.read(16))
f.seek(0x60, 0)
vertInfo = []
for i in range(0 ,header[3]):
	meshInfo = struct.unpack("4i",f.read(0x10))
	meshMatrix = struct.unpack("12f",f.read(0x30))
	meshInfo2 = struct.unpack("4i",f.read(0x10))
	vertInfo.append([meshInfo,meshMatrix,meshInfo2])
print(f.tell())
boneInfo = struct.unpack("4i",f.read(0x10))
texInfo = struct.unpack("4i",f.read(0x10))
matInfo = struct.unpack("4i",f.read(0x10))
vertOff = struct.unpack(str(header[3]) + "i",f.read(header[3] * 4))
faceOff = struct.unpack(str(header[3]) + "i",f.read(header[3] * 4))
weightOff = struct.unpack(str(header[3]) + "i",f.read(header[3] * 4))

for i in range(0 ,header[3]):
	vertexArray = om.MFloatPointArray()
	normalArray = om.MFloatPointArray()
	uArray = om.MFloatArray()
	vArray = om.MFloatArray()
	uvCounts = om.MIntArray()
	uvIds = om.MIntArray()
	f.seek(vertOff[i], 0)
	for a in range(0 ,vertInfo[i][0][1]):
		verts = struct.unpack("8f",f.read(32))
		pt = om.MFloatPoint(verts[0],verts[1], verts[2])
		vertexArray.append(pt)
		uArray.append(verts[6])
		vArray.append((verts[7] * -1) + 1)

	f.seek(faceOff[i], 0)
	pConnects = om.MIntArray()
	pCounts = om.MIntArray()
	for a in range(0 ,vertInfo[i][0][0]):
		faceCount = struct.unpack("H",f.read(2))[0]	
		matID = struct.unpack("H",f.read(2))[0]
		fstart = f.tell()
		StartDirection = -1
		f1 = struct.unpack("H",f.read(2))[0]
		f2 = struct.unpack("H",f.read(2))[0]
		FaceDirection = StartDirection
		while f.tell() < (fstart + (2 *faceCount )):
			f3 = struct.unpack("H",f.read(2))[0]
			if f3 == 0xFFFF:
				f1 = struct.unpack("H",f.read(2))[0]
				f2 = struct.unpack("H",f.read(2))[0]
				FaceDirection = StartDirection
			else:
				FaceDirection *= -1
				if (f1 != f2 and f1 != f3 and f3 != f2) : 
					if FaceDirection > 0:
						pConnects.append(f1)
						pConnects.append(f2)
						pConnects.append(f3)
					else:
						pConnects.append(f1)
						pConnects.append(f3)
						pConnects.append(f2)
					pCounts.append(3)
				f1 = f2
				f2 = f3

	f.seek(weightOff[i], 0)
	uvCounts = pCounts
	mesh = om.MFnMesh()
	ShapeMesh = cmds.group(em=True) # <-- we create an empty group/ trnasform node that will receive the mesh node as a sibling
	parentOwner = get_mobject( ShapeMesh )
	meshMObj = mesh.create(vertInfo[i][0][1], len(pCounts), vertexArray, pCounts, pConnects, uArray, vArray ,parentOwner ) #<-- don't forget to add a parent owner
	cmds.sets( 'null' + str(i + 1), e=True,forceElement='initialShadingGroup') # <--assign the defaut lambert shader
	defaultUVSetName = ''
	defaultUVSetName = mesh.currentUVSetName(-1)
	mesh.setUVs( uArray, vArray, defaultUVSetName )
        #if you want to manually set the uv's
	#for a in range(0 ,mesh.numPolygons()):
	#	for point in range(0 ,3):
	#		mesh.assignUV(a, point, pConnects[a*3+point] )
	mesh.assignUVs(pCounts,pConnects, defaultUVSetName)

#struct.unpack(4*"i",f.read(struct.calcsize(4*"i")))[0] 
#f.seek(4, 0) absolute
#f.seek(4, 1) current pos
#f.seek(4, 2) end of file

f.close()

```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T23:24:26+00:00
- Post Title: Maya py script

How does the maya plugin interface work?
Do you just write your plugin and then say "load plugin" and then it will just execute your file? Since you specified a file open dialog.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-04T00:18:28+00:00
- Post Title: Maya py script

i am going to make a dock-able gui once i get the format strait but for now i just open the script editor and paste it in and hit run.
but you can setup python plugins to register at start-up just like noesis.
edit this is a good start
[http://etoia.free.fr/?p=1771](http://etoia.free.fr/?p=1771)
## Post #4
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-02-06T17:44:00+00:00
- Post Title: Maya py script

Awesome work chrrox!
I used this along with your code over here: [http://gameresearch.5d6d.net/archiver/tid-199.html](http://gameresearch.5d6d.net/archiver/tid-199.html) to learn how to create importers for Maya.
Do you have any example skinning/skeleton code? For some reason I understand source code better than docs.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-02-06T19:21:29+00:00
- Post Title: Maya py script

> Reply from TheDude
>
> For some reason I understand source code better than docs.

Because it's a damn sight harder to make docs worth anything than it is to simply make some illustrative source code (as I'm sure just about anyone who's done both will tell you).
## Post #6
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-02-07T00:30:36+00:00
- Post Title: Maya py script

> Reply from Dinoguy1000
>
> 
Because it's a damn sight harder to make docs worth anything than it is to simply make some illustrative source code (as I'm sure just about anyone who's done both will tell you).
## Post #7
- Username: TheDude
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-07T01:59:57+00:00
- Post Title: Maya py script

here is the sample weight importing.

```
# Maya Python script

import maya.cmds as cmds
import pymel.core as pm
import maya.OpenMaya as om
import maya.OpenMayaAnim as oma
import os
import struct

def get_mobject(node):
	selectionList = om.MSelectionList()
	selectionList.add(node)
	oNode = om.MObject()
	selectionList.getDependNode(0, oNode)
	return oNode 

fname = cmds.fileDialog2(fm=1, ff='Music Girl:Hatsune Miku .mdl (*.mdl);;All Files (*.*)')[0]
f = open(fname, "rb")

base=os.path.basename(fname)
os.path.splitext(base)
base=os.path.splitext(base)[0]

magic = struct.unpack("4s",f.read(4))[0]
header = struct.unpack("4i",f.read(16))
f.seek(0x60, 0)
vertInfo = []
for i in range(0 ,header[3]):
	meshInfo = struct.unpack("4i",f.read(0x10))
	meshMatrix = struct.unpack("12f",f.read(0x30))
	meshInfo2 = struct.unpack("4i",f.read(0x10))
	vertInfo.append([meshInfo,meshMatrix,meshInfo2])
print(f.tell())
boneInfo = struct.unpack("4i",f.read(0x10))
texInfo = struct.unpack("4i",f.read(0x10))
matInfo = struct.unpack("4i",f.read(0x10))
vertOff = struct.unpack(str(header[3]) + "i",f.read(header[3] * 4))
faceOff = struct.unpack(str(header[3]) + "i",f.read(header[3] * 4))
weightOff = struct.unpack(str(header[3]) + "i",f.read(header[3] * 4))

f.seek(boneInfo[1], 0)
boneArray = []
for i in range(0 ,boneInfo[0]):
	boneMat = struct.unpack("16f",f.read(0x40))
	boneDat = struct.unpack("4I",f.read(0x10))
	bonePosition = om.MVector(boneMat[0], boneMat[1], boneMat[2])
	boneOritation = om.MQuaternion(boneMat[4], boneMat[5], boneMat[6], boneMat[7])
	#boneScale = om.MVector(boneMat[8], boneMat[9], boneMat[10])
	if boneDat[0] == 0xFFFFFFFF:
		cmds.select( clear=True)
	else:
		pm.select(boneArray[boneDat[0]])
	newBone = pm.joint( p=(0,0,0), name='joint' + str(i),radius= (0.1) )
	newBone.setTranslation(bonePosition)
	newBone.setOrientation(boneOritation)
	boneArray.append(newBone)
	cmds.objExists("joint' + str(i)")
if len(boneArray) != 0:
    cmds.setAttr (str(boneArray[0]) + ".overrideEnabled", 1)
    cmds.setAttr (str(boneArray[0]) + ".overrideColor", 16)

for i in range(0 ,header[3]):
	vertexArray = om.MFloatPointArray()
	normalArray = om.MFloatPointArray()
	uArray = om.MFloatArray()
	vArray = om.MFloatArray()
	uvCounts = om.MIntArray()
	uvIds = om.MIntArray()
	f.seek(vertOff[i], 0)
	for a in range(0 ,vertInfo[i][0][1]):
		verts = struct.unpack("8f",f.read(32))
		pt = om.MFloatPoint(verts[0],verts[1], verts[2])
		vertexArray.append(pt)
		uArray.append(verts[6])
		vArray.append((verts[7] * -1) + 1)

	f.seek(faceOff[i], 0)
	pConnects = om.MIntArray()
	pCounts = om.MIntArray()
	for a in range(0 ,vertInfo[i][0][0]):
		faceCount = struct.unpack("H",f.read(2))[0]	
		matID = struct.unpack("H",f.read(2))[0]
		fstart = f.tell()
		StartDirection = -1
		f1 = struct.unpack("H",f.read(2))[0]
		f2 = struct.unpack("H",f.read(2))[0]
		FaceDirection = StartDirection
		while f.tell() < (fstart + (2 *faceCount )):
			f3 = struct.unpack("H",f.read(2))[0]
			if f3 == 0xFFFF:
				f1 = struct.unpack("H",f.read(2))[0]
				f2 = struct.unpack("H",f.read(2))[0]
				FaceDirection = StartDirection
			else:
				FaceDirection *= -1
				if (f1 != f2 and f1 != f3 and f3 != f2) : 
					if FaceDirection > 0:
						pConnects.append(f1)
						pConnects.append(f2)
						pConnects.append(f3)
					else:
						pConnects.append(f1)
						pConnects.append(f3)
						pConnects.append(f2)
					pCounts.append(3)
				f1 = f2
				f2 = f3

	f.seek(weightOff[i], 0)
	weights = {}
	for a in range(0 ,vertInfo[i][0][1]):
		vWeights = {}
		wCount = struct.unpack("I",f.read(4))[0]
		for b in range(0 ,wCount):
			boneId = struct.unpack("I",f.read(4))[0]
			weight = struct.unpack("f",f.read(4))[0]
			vWeights[boneId] = weight
		weights[a] = vWeights
	uvCounts = pCounts
	mesh = om.MFnMesh()
	ShapeMesh = cmds.group( em=True, name='null_' + base + str(i) )  # <-- we create an empty group/ trnasform node that will receive the mesh node as a sibling
	parentOwner = get_mobject( ShapeMesh )
	meshMObj = mesh.create(vertInfo[i][0][1], len(pCounts), vertexArray, pCounts, pConnects, uArray, vArray ,parentOwner ) #<-- don't forget to add a parent owner
	cmds.sets( 'null_' + base + str(i), e=True,forceElement='initialShadingGroup') # <--assign the defaut lambert shader
	defaultUVSetName = ''
	defaultUVSetName = mesh.currentUVSetName(-1)
	mesh.setUVs( uArray, vArray, defaultUVSetName )
	#for a in range(0 ,mesh.numPolygons()):
	#	for point in range(0 ,3):
	#		mesh.assignUV(a, point, pConnects[a*3+point] )
	mesh.assignUVs(pCounts,pConnects, defaultUVSetName)
	mesh.setName('mesh_' + base + str(i))
	if len(boneArray) != 0:
	    pm.skinCluster( str(boneArray[0]), 'mesh_' + base + str(i),sm=2,mi=4,omi=1,n='skinCluster_' + base + str(i))
	#pm.rename( 'skinCluster' + str(i + 1), 'miku_Skin' + str(i))

	# poly mesh and skinCluster name
	shapeName = 'mesh_' + base + str(i)
	clusterName = 'skinCluster_' + base + str(i)

	# get the MFnSkinCluster for clusterName
	selList = om.MSelectionList()
	selList.add(clusterName)
	clusterNode = om.MObject()
	selList.getDependNode(0, clusterNode)
	skinFn = oma.MFnSkinCluster(clusterNode)

	# get the MDagPath for all influence
	infDags = om.MDagPathArray()
	skinFn.influenceObjects(infDags)

	# create a dictionary whose key is the MPlug indice id and 
	# whose value is the influence list id
	infIds = {}
	infs = []
	for x in xrange(infDags.length()):
		infPath = infDags[x].fullPathName()
		infId = int(skinFn.indexForInfluenceObject(infDags[x]))
		infIds[infId] = x
		infs.append(infPath)

	# get the MPlug for the weightList and weights attributes
	wlPlug = skinFn.findPlug('weightList')
	wPlug = skinFn.findPlug('weights')
	wlAttr = wlPlug.attribute()
	wAttr = wPlug.attribute()
	wInfIds = om.MIntArray()

	# unlock influences used by skincluster
	for inf in infs:
		cmds.setAttr('%s.liw' % inf)

	# normalize needs turned off for the prune to work
	skinNorm = cmds.getAttr('%s.normalizeWeights' % clusterName)
	if skinNorm != 0:
		cmds.setAttr('%s.normalizeWeights' % clusterName, 0)
	cmds.skinPercent(clusterName, shapeName, nrm=False, prw=100)

	# restore normalize setting
	if skinNorm != 0:
		cmds.setAttr('%s.normalizeWeights' % clusterName, skinNorm)

	for vertId, weightData in weights.items():
		wlAttr = '%s.weightList[%s]' % (clusterName, vertId)
		for infId, infValue in weightData.items():
			wAttr = '.weights[%s]' % infId
			cmds.setAttr(wlAttr + wAttr, infValue)


#struct.unpack(4*"i",f.read(struct.calcsize(4*"i")))[0] 
#f.seek(4, 0) absolute
#f.seek(4, 1) current pos
#f.seek(4, 2) end of file

f.close()
```
## Post #8
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-02-07T18:30:48+00:00
- Post Title: Maya py script

Thanks chrrox!
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-02-07T22:28:04+00:00
- Post Title: Maya py script

You could also thank him for his post (the little yellow thumbs-up button at the bottom of his post).
## Post #10
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-02-08T01:02:52+00:00
- Post Title: Maya py script

It's a sad day when digital cookies aren't enough.   
Ugh, forums are too complicated - Python is easier.
