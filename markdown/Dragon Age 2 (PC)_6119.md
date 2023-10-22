## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-21T21:14:24+00:00
- Post Title: Dragon Age 2 (PC)

I am working on the mesh format it is going good so far trying to find out how to link all these files together.
[da2Elf.png](https://xentaxbackup.github.io/file/3963_da2Elf.png)
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-21T21:23:04+00:00
- Post Title: Dragon Age 2 (PC)

Amazing preview chroxxx, good advance. Also i finally kow how the gameassasin tool works any question or  help you need only ask. i posted a answer in the section of gameassassin tool too.
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-23T16:42:05+00:00
- Post Title: Dragon Age 2 (PC)

Great work
For import .msh files to Blender there is "DragonAge_Tools_020".
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-23T23:39:17+00:00
- Post Title: Dragon Age 2 (PC)

they are a new format for the second game.
## Post #5
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-23T23:49:12+00:00
- Post Title: Dragon Age 2 (PC)

wow you rock chrrox
## Post #6
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-26T03:42:16+00:00
- Post Title: Dragon Age 2 (PC)

what tools did you use to rip the model?
## Post #7
- Username: Erik24
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 22, 2011 7:23 am
- Post datetime: 2011-03-11T22:46:30+00:00
- Post Title: Dragon Age 2 (PC)

> Reply from sirew
>
> what tools did you use to rip the model?

answer plz
## Post #8
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-03-13T10:51:24+00:00
- Post Title: Dragon Age 2 (PC)

Probably he is working at a script to import the Dagon Age2 mesh, uv map and bones format directly into max (max script)...as he usually do.....amazing!!
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-14T02:22:22+00:00
- Post Title: Dragon Age 2 (PC)

Here is the script but i cant find any bones they must use a global skeleton somewhere but i don't know where it is.

```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open DA2 Model File" \
types:"DA2 Model File(*.msh)|*.msh" \
historyCategory:"DA2ObjectPresets"
f = fopen fname "rb"

fn PrintOffset Var =
(
	local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
	Var
)
fn PrintCount Var =
(
	local Var = Var
print ("This is the Count 0x" + (bit.intAsHex Var) as string)
	Var
)

fn Readword fstream = (
return readshort fstream #unsigned
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
fn ReadFixedUString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
		fseek bstream 0x1#seek_cur
	)
	str
)
 	fn convertTo32 input16 = (
 		inputAsInt = input16
 		sign = bit.get inputAsInt 16
 		exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
 		fraction = bit.and inputAsInt (bit.hexasint "03FF")
 		if sign==true then sign = 1 else sign = 0
 		exponentF = exponent + 127
 		--Ouput 32 bit integer representing a 32 bit float
 		outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
 		--Output Check	
 		return bit.intasfloat outputasfloat * 2
 	)

fn ReadHalfFloat fstream = (
return convertTo32(Readshort fstream)
)

struct Mesh_Info_Struct
(
	vertsize,VertCount,FaceCount,VertPos,FacePos
)

fseek f 0x1A0#seek_set
baseoff = (ftell f)
namebase = readlong f
null = readlong f
unkbase = readlong f
vertbase = readlong f
facebase = readlong f
null = readlong f
null = readlong f
MeshCount = readlong f
Mesh_Info_Array = #()
for a = 1 to MeshCount Do (
float01 = readfloat f
float02 = readfloat f
float03 = readfloat f
float04 = readfloat f
float11 = readfloat f
float12 = readfloat f
float13 = readfloat f
float14 = readfloat f
float21 = readfloat f
float22 = readfloat f
float23 = readfloat f
float34 = readfloat f
unk01 = readlong f
vertsize = readlong f
VertCount = readlong f
FaceCount = readlong f
VertPos = readlong f
FacePos = readlong f
unk02 = readlong f
long01 = readlong f
long02 = readlong f
long03 = readlong f
long04 = readlong f
VertCount2 = readlong f
append Mesh_Info_Array (Mesh_Info_Struct vertsize:vertsize VertCount:VertCount FaceCount:FaceCount VertPos:VertPos FacePos:FacePos)
)
print Mesh_Info_Array

FaceStart = (baseoff + facebase) + 4
VertStart = (baseoff + vertbase) + 4
NameStart = (baseoff + namebase)
UnkStart = (baseoff + unkbase)
/*
fseek f UnkStart#seek_set
MeshCount2 = readlong f
for a = 1 to MeshCount2 Do (
unk03 = readlong f
)
FileNameSize = readlong f
MeshFile = ReadFixedUString f FileNameSize
*/
/*
fseek f NameStart#seek_set
MeshName_Array = #()
for a = 1 to MeshCount Do (
MeshNameSize = readlong f
MeshName = ReadFixedUString f MeshNameSize
append MeshName_Array MeshName
test = readshort f
if test != -1 do (
fseek f -2#seek_cur
)
fseek f 0x90#seek_cur
print MeshName
)
print MeshName_Array
*/
for a = 1 to MeshCount Do (
Vert_array = #()
UV_array = #()
Normal_array = #()
Face_array = #()
fseek f (VertStart + Mesh_Info_Array[a].VertPos)#seek_set
for b = 1 to Mesh_Info_Array[a].VertCount Do (
if Mesh_Info_Array[a].vertsize == 40 do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
unk10 = readfloat f
unk11 = readfloat f
unk12 = readfloat f
unk13 = readfloat f
unk13 = readfloat f
tu = ReadHalfFloat f
tv = ReadHalfFloat f * -1
unk13 = readfloat f

append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
if Mesh_Info_Array[a].vertsize == 36 do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
unk10 = readfloat f
unk11 = readfloat f
unk12 = readfloat f
unk13 = readfloat f
unk13 = readfloat f
tu = ReadHalfFloat f
tv = ReadHalfFloat f * -1
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
if Mesh_Info_Array[a].vertsize == 32 do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
unk10 = readfloat f
unk11 = readfloat f
unk12 = readfloat f
unk13 = readfloat f
tu = ReadHalfFloat f
tv = ReadHalfFloat f * -1
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
if Mesh_Info_Array[a].vertsize == 28 do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
unk10 = readfloat f
unk11 = readfloat f
unk13 = readfloat f
tu = ReadHalfFloat f
tv = ReadHalfFloat f * -1
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
if Mesh_Info_Array[a].vertsize == 24 do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
unk10 = readfloat f
unk11 = readfloat f
tu = ReadHalfFloat f
tv = ReadHalfFloat f * -1
append Vert_array [vx,vy,vz]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
	
)
fseek f (FaceStart + (Mesh_Info_Array[a].FacePos * 2))#seek_set
for b = 1 to Mesh_Info_Array[a].FaceCount / 3 do (
f1 = (readshort f) + 1
f2 = (readshort f) + 1
f3 = (readshort f) + 1
append Face_array [f1,f2,f3]
)

msh = mesh vertices:Vert_array faces:Face_array name:(a as string)
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]

)

fclose f

```
## Post #10
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-03-14T10:30:04+00:00
- Post Title: Dragon Age 2 (PC)

This script for 3dmax? or extract?
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-14T11:00:40+00:00
- Post Title: Dragon Age 2 (PC)

> Reply from logansan25
>
> This script for 3dmax? or extract?
Max
## Post #12
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-14T18:49:49+00:00
- Post Title: Dragon Age 2 (PC)

Chroxx - you rock.

I hope you don't mind, I ported your script to Blender 2.5.6 , for those without 3DS Max.

Thanks for all your hard work, I dunno how you figure this stuff out.

NB: Updated with fix for problem affecting certain models.

Put the code into a file with a .py extension (I used "io_import_dragon_age_2_msh.py"), then add it using the Add On tab of the User Preferences.
fs


Look later in thread for updated code
## Post #13
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-14T22:02:55+00:00
- Post Title: Dragon Age 2 (PC)

Python script that will convert .msh to .obj file for those of you who don't like either 3DS Max or Blender, or for those who want to do batch conversions:

```

import os
import sys
import string
import math
import re
from string import *
from struct import *
from math import *

LONGSIZE = 4
FLOATSIZE = 4
HALFFLOATSIZE = 2
SHORTSIZE = 2

def unpack_list(list_of_tuples):
	l = []
	for t in list_of_tuples:
		l.extend(t)
	return l

def halfToFloatPrivate(h):
	s = int((h >> 15) & 0x00000001)		# sign
	e = int((h >> 10) & 0x0000001f)		# exponent
	f = int(h &			0x000003ff)		# fraction

	if e == 0:
		if f == 0:
			return int(s << 31)
		else:
			while not (f & 0x00000400):
				f <<= 1
				e -= 1
			e += 1
			f &= ~0x00000400
	elif e == 31:
		if f == 0:
			return int((s << 31) | 0x7f800000)
		else:
			return int((s << 31) | 0x7f800000 | (f << 13))

	e = e + (127 -15)
	f = f << 13

	return int((s << 31) | (e << 23) | f)

def halfToFloat(h):
	result = halfToFloatPrivate(h)
	str = pack('I',result)
	f = unpack('f', str)
	return f[0]
	
def mshImport(infile):

	print ("Converting file: ", infile)
	
	mshfile = open(infile,'rb')
	
	objPath = infile.replace(".msh", ".obj")
	print("\toutput file: " + objPath)
	objfile = open(objPath,'w')

	basename = os.path.basename(infile)
	# basename = os.path.splitext(infile)[0]		
	
	
	mshfile.seek(0x1A0)
	baseoff = 0x1A0
	

	namebase, garbage, unkbase, vertbase, facebase, garbage1, garbage2, meshcount = unpack('<8l', mshfile.read(8*LONGSIZE))

	vertSizeArray = []
	vertCountArray = []
	faceCountArray = []
	vertPosArray = []
	facePosArray = []
	
	for i in range(meshcount):
		float01, float02, float03, float04, float11, float12, float13, float14, float21, float22, float23, float34 = unpack('<12f', mshfile.read(12*FLOATSIZE))
		unk01, vertSize, vertCount, faceCount, vertPos, facePos, unk2, long01, long02, long03, long04, vertCount2 = unpack('<12l', mshfile.read(12*LONGSIZE))
		vertSizeArray.append(vertSize)
		vertCountArray.append(vertCount)
		faceCountArray.append(faceCount)
		vertPosArray.append(vertPos)
		facePosArray.append(facePos)
	
	faceStart = baseoff + facebase + 4
	vertStart = baseoff + vertbase + 4
	nameStart = baseoff + namebase
	unkStart = baseoff + unkbase
	
	vertexOffset = 1
	
	for a in range(meshcount):
		objfile.write("o " + basename + str(a) + "\n")
		vertArray = []
		uvArray = []
		normalArray = []
		faceArray = []
		mshfile.seek(vertStart + vertPosArray[a])
		for b in range(vertCountArray[a]):
			data = mshfile.read(3*FLOATSIZE)
			vx, vy, vz = unpack('<3f', data)
			bytesOfUnknown = (vertSizeArray[a] - 16)
			unknown = mshfile.read(bytesOfUnknown)
			tu_h = unpack('H', mshfile.read(HALFFLOATSIZE))
			tv_h = unpack('H', mshfile.read(HALFFLOATSIZE))
			tu = halfToFloat(tu_h[0])
			tv = halfToFloat(tv_h[0])
			vertArray.extend([(vx, vy, vz)])
			uvArray.extend([(tu, tv)])
	
		mshfile.seek(faceStart + facePosArray[a] * 2)
		faceLen = faceCountArray[a]
		
		for i in range(len(vertArray)):
			objfile.write("v " + str(vertArray[i][0]) + " " + str(vertArray[i][1]) + " " + str(vertArray[i][2]) + "\n")
			
		for i in range(len(uvArray)):
			objfile.write("vt " + str(uvArray[i][0]) + " " + str(uvArray[i][1]) + "\n")
		
		if (faceLen > 0):
			faceLen = faceLen / 3
		else:
			faceLen = 0
		
		for b in range(int(faceLen)):
			f1, f2, f3 = unpack('<3h', mshfile.read(3*SHORTSIZE))
			if (f1 < len(vertArray) and f2 < len(vertArray) and f3 < len(vertArray)):
				faceArray.extend([(f1, f2, f3)])

		for i in range(len(faceArray)):
			objfile.write("f " + str(faceArray[i][0] + vertexOffset) + "/" + str(faceArray[i][0] + vertexOffset) + " " + str(faceArray[i][1] + vertexOffset) + "/" + str(faceArray[i][1] + vertexOffset) + " " + str(faceArray[i][2] + vertexOffset) + "/" + str(faceArray[i][2] + vertexOffset) + "\n")
			
		vertexOffset = vertexOffset + (len(vertArray))
			

for grp in sys.argv[1:]:
	mshImport(grp)

```
## Post #14
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-03-14T22:22:38+00:00
- Post Title: Dragon Age 2 (PC)

Who use this phyton? I am a noob in phyton!
## Post #15
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-14T22:47:03+00:00
- Post Title: Dragon Age 2 (PC)

Actually, what I need to do first, before putting it into blender/max?
## Post #16
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-14T22:59:48+00:00
- Post Title: Re: Dragon Age 2 (PC)

Check this thread: [viewtopic.php?f=10&t=6117&hilit=dragon+age+2](http://forum.xentax.com/viewtopic.php?f=10&t=6117&hilit=dragon+age+2)

It contains a QuickBMS for extracting files from the Dragon Age 2 .erf files

It will expand a bunch of numbered files, and then a subfolder called output that will have the named .msh files.

The texture files are .dds images.  Using any of the scripts above, you can import the .msh file into a 3D program. It will not have its armature, and you'll have to manually find the textures if you want those.

There is currently no way to get the changes back into the game, though I would imagine there will be at some point.
## Post #17
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-15T03:56:17+00:00
- Post Title: Re: Dragon Age 2 (PC)

Revised Script.

I found why certain models (mostly hair) wouldn't load - they had a vertSize of 40, which wasn't handled by any of the code. I've replaced the if statement with new code that calculates the number of unknown bytes between the vertex position and the texture coordinates, and it should now load every data model from Dragon Age 2.

```
	"name": "Import Dragon Age 2 Mesh files (.msh)",
	"author": "",
	"version": (2, 0),
	"blender": (2, 5, 6),
	"api": 31847,
	"location": "File > Import ",
	"description": "Import Dragon Age 2 Mes (.msh)",
	"warning": "",
	"wiki_url": "",
	"tracker_url": "",
	"category": "Import-Export"}

"""
Version': '1.0' 

This is a straight port of the 3DS Max Script from this forum
posting:

http://forum.xentax.com/viewtopic.php?f=16&t=6119&hilit=dragon+age+2

This version is based on the script posted with this timestamp

Posted: Mon Mar 14, 2011 3:22 am 

All credit to chrrox for figuring the format out.

"""

import bpy
import mathutils
import os
import sys
import string
import math
import re
from string import *
from struct import *
from math import *
import mathutils
from bpy.props import *


DEBUGLOG = False
LONGSIZE = 4
FLOATSIZE = 4
HALFFLOATSIZE = 2
SHORTSIZE = 2

def unpack_list(list_of_tuples):
	l = []
	for t in list_of_tuples:
		l.extend(t)
	return l

def halfToFloatPrivate(h):
	s = int((h >> 15) & 0x00000001)		# sign
	e = int((h >> 10) & 0x0000001f)		# exponent
	f = int(h &			0x000003ff)		# fraction

	if e == 0:
		if f == 0:
			return int(s << 31)
		else:
			while not (f & 0x00000400):
				f <<= 1
				e -= 1
			e += 1
			f &= ~0x00000400
	elif e == 31:
		if f == 0:
			return int((s << 31) | 0x7f800000)
		else:
			return int((s << 31) | 0x7f800000 | (f << 13))

	e = e + (127 -15)
	f = f << 13

	return int((s << 31) | (e << 23) | f)

def halfToFloat(h):
	result = halfToFloatPrivate(h)
	str = pack('I',result)
	f = unpack('f', str)
	return f[0]
	
def mshImport(infile):
	global DEBUGLOG
	print ("--------------------------------------------------")
	print ("---------SCRIPT EXECUTING PYTHON IMPORTER---------")
	print ("--------------------------------------------------")
	print ("Importing file: ", infile)
	
	mshfile = open(infile,'rb')
	if (DEBUGLOG):
		logpath = infile.replace(".msh", ".txt")
		print("logpath:",logpath)
		logf = open(logpath,'w')
		
	def printlog(strdata):
		if (DEBUGLOG):
			logf.write(strdata + "\n")

	basename = os.path.basename(infile)
	# basename = os.path.splitext(infile)[0]		
	
	
	printlog("basename:" + basename)
	
	mshfile.seek(0x1A0)
	baseoff = 0x1A0
	

	namebase, garbage, unkbase, vertbase, facebase, garbage1, garbage2, meshcount = unpack('<8l', mshfile.read(8*LONGSIZE))

	printlog("baseoff: " + str(baseoff))
	printlog("unkbase: " + str(unkbase))
	printlog("vertbase: " + str(vertbase))
	printlog("facebase: " + str(facebase))
	printlog("meshcount: " + str(meshcount))
	
	vertSizeArray = []
	vertCountArray = []
	faceCountArray = []
	vertPosArray = []
	facePosArray = []
	
	for i in range(meshcount):
		printlog("assessing mesh " + str(i))
		float01, float02, float03, float04, float11, float12, float13, float14, float21, float22, float23, float34 = unpack('<12f', mshfile.read(12*FLOATSIZE))
		unk01, vertSize, vertCount, faceCount, vertPos, facePos, unk2, long01, long02, long03, long04, vertCount2 = unpack('<12l', mshfile.read(12*LONGSIZE))
		printlog("\tvertsize: " + str(vertSize))
		printlog("\tvertCount: " + str(vertCount))
		printlog("\tfaceCount: " + str(faceCount))
		printlog("\tvertPos: " + str(vertPos))
		printlog("\tfacePos: " + str(facePos))
		vertSizeArray.append(vertSize)
		vertCountArray.append(vertCount)
		faceCountArray.append(faceCount)
		vertPosArray.append(vertPos)
		facePosArray.append(facePos)
	
	faceStart = baseoff + facebase + 4
	vertStart = baseoff + vertbase + 4
	nameStart = baseoff + namebase
	unkStart = baseoff + unkbase
	
	if (DEBUGLOG):
		printlog("faceStart: " + str(faceStart))
		printlog("vertStart: " + str(vertStart))
		printlog("nameStart: " + str(nameStart))
		printlog("unkStart: " + str(unkStart))
	
	for a in range(meshcount):
		me_ob = bpy.data.meshes.new(basename + str(a))
		printlog(("New Mesh = " + me_ob.name))
		vertArray = []
		uvArray = []
		normalArray = []
		faceArray = []
		printlog("===Offset = " + str(vertStart + vertPosArray[a]))
		printlog("===vertStrt = " + str(vertStart))
		printlog("===vertPos[a] = " + str(vertPosArray[a]))
		mshfile.seek(vertStart + vertPosArray[a])
		for b in range(vertCountArray[a]):
			data = mshfile.read(3*FLOATSIZE)
			vx, vy, vz = unpack('<3f', data)
			bytesOfUnknown = (vertSizeArray[a] - 16)
			unknown = mshfile.read(bytesOfUnknown)
			tu_h = unpack('H', mshfile.read(HALFFLOATSIZE))
			tv_h = unpack('H', mshfile.read(HALFFLOATSIZE))
			tu = halfToFloat(tu_h[0])
			tv = halfToFloat(tv_h[0])
			vertArray.extend([(vx, vy, vz)])
			uvArray.extend([(tu, tv)])
	
		printlog("facePosArray: " + str(facePosArray[a]))
		mshfile.seek(faceStart + facePosArray[a] * 2)
		faceLen = faceCountArray[a]
		
		printlog("faceCountArray length: " + str(faceLen))
		
		if (faceLen > 0):
			faceLen = faceLen / 3
		else:
			faceLen = 0
		printlog("facelen: " + str(faceLen))
		
		faceUVArray = []
		
		for b in range(int(faceLen)):
			f1, f2, f3 = unpack('<3h', mshfile.read(3*SHORTSIZE))
			if (f1 < len(vertArray) and f2 < len(vertArray) and f3 < len(vertArray)):
				faceArray.extend([f1, f2, f3, 0])
				faceUVArray.extend([(uvArray[f1], uvArray[f2], uvArray[f3])])
			#printlog("Adding array:" + str(f1) + ", " + str(f2) + ", " + str(f3))
			
		printlog("vertArray length: " + str(len(vertArray)))
		printlog("faceArray length: " + str(len(faceArray)))
		me_ob.vertices.add(len(vertArray))
		me_ob.faces.add(len(faceArray)//4)
		me_ob.vertices.foreach_set("co", unpack_list(vertArray))
		me_ob.faces.foreach_set("vertices_raw", faceArray)
		me_ob.faces.foreach_set("use_smooth", [False] * len(me_ob.faces))
		
		texture = []
		texturename = basename + "_tex_" + str(a)
		if (len(faceUVArray) > 0):
			uvtex = me_ob.uv_textures.new() #add one uv texture
			uvtex.name = "Imported UV"
			for i, face in enumerate(me_ob.faces):
				blender_tface= uvtex.data[i] #face
				blender_tface.uv1 = faceUVArray[i][0] #uv = (0,0)
				blender_tface.uv2 = faceUVArray[i][1] #uv = (0,0)
				blender_tface.uv3 = faceUVArray[i][2] #uv = (0,0)
			texture.append(uvtex)
		
		materialname = "mat"
		materials = []

		matdata = bpy.data.materials.new(materialname)
		matdata.diffuse_color=(float(0.04),float(0.08),float(0.44))#blue color
		
		texdata = None
		texIndex = len(bpy.data.textures) - 1
		if (texIndex >= 0):
			texdata = bpy.data.textures[len(bpy.data.textures)-1]
			if (texdata != None):
				#print(texdata.name)
				#print(dir(texdata))
				texdata.name = "texturelist1"
				matdata.active_texture = texdata
		materials.append(matdata)
		for material in materials:
			#add material to the mesh list of materials
			me_ob.materials.append(material)
			
		# me_ob.uv_textures.new(basename + "_uv_" + str(i))
		# uvtex = me_ob.uv_textures[0]
		# for n,tf in enumerate(uvArray):
		# 	datum = uvtex.data[n]
		# 	datum.uv1 = tf[0]
		# 	datum.uv2 = tf[1]
		# 	datum.uv3 = tf[2]
		# 
		# uvtex.foreach_set("co", unpack_list(uvArray))
		# me_ob.uv_textures.foreach_set("co", unpack_list(uvArray))
		me_ob.update()
		
		obmesh = bpy.data.objects.new(basename,me_ob)
		bpy.context.scene.objects.link(obmesh)
		bpy.context.scene.update()
	
def getInputFilename(filename):
	checktype = filename.split('\\')[-1].split('.')[1]
	print ("------------",filename)
	if checktype.upper() != 'MSH':
		print ("  Selected file = ",filename)
		raise (IOError, "The selected input file is not a *.msh file")
	mshImport(filename)

class IMPORT_OT_msh(bpy.types.Operator):
	'''Load a Dragon Age 2 Mesh File'''
	bl_idname = "import_scene.msh"
	bl_label = "Import MSH"

	# List of operator properties, the attributes will be assigned
	# to the class instance from the operator settings before calling.
	filepath = StringProperty(name="File Path", description="Filepath used for importing the OBJ file", maxlen= 1024, default= "")

	def execute(self, context):
		getInputFilename(self.filepath)
		return {'FINISHED'}

	def invoke(self, context, event):
		wm = context.window_manager
		wm.fileselect_add(self)
		return {'RUNNING_MODAL'}


def menu_func(self, context):
	self.layout.operator(IMPORT_OT_msh.bl_idname, text="Dragon Age 2 Mesh (.msh)")


def register():
	bpy.types.INFO_MT_file_import.append(menu_func)
	
def unregister():
	bpy.types.INFO_MT_file_import.remove(menu_func)

if __name__ == "__main__":
    register()

```


Here's the desire demon imported - I had to manually load the image and body texture (face diffuse = 16511.dds, body diffuse = 9902.dds, eyeball diffuse = 16510.dds - there are normal maps also, but they don't appear to be tangent space normal maps or object space normal maps, so not sure how to use them yet).
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-15T04:12:27+00:00
- Post Title: Re: Dragon Age 2 (PC)

Find anything that looks like bones in any of the files that's why i got bored with this game i cant finish the importer.
## Post #19
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-15T04:23:32+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from chrrox
>
> Find anything that looks like bones in any of the files that's why i got bored with this game i cant finish the importer.

I'm guessing they might be in the .mmh file, or one of the other ones, but there's no easy way to match up the named mesh files with the numbered mmx files. But no, I haven't seen anything that looked like bones yet, though most of my time porting the stuff you figured out. I don't have a lot of experience reverse engineering 3D data formats..
## Post #20
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-15T04:51:04+00:00
- Post Title: Re: Dragon Age 2 (PC)

Hi guys, have you ever thought doing converter, with UI?, with just a click of a button and not using any command to convert, just asking
## Post #21
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-03-15T04:54:03+00:00
- Post Title: Re: Dragon Age 2 (PC)

This Script I found on the Dragon Age Forums

Although, it is for Dragon Age: Origins maybe it will contain some useful insight into the .mmh format for DA 2.


[http://hotfile.com/dl/110281794/5ccda19/Readme.pdf.html](http://hotfile.com/dl/110281794/5ccda19/Readme.pdf.html)   (Here's the .pdf also for explanation of format).

Also, Fantastic work by both  Chrrox and figuresculptor 

Edit: 

This is the Latest Dragon Age: Origins Importer/Exporter by Author Eshme and found on the Dragon Age Nexus

[http://hotfile.com/dl/110283196/8ff46a6 ... 42.7z.html](http://hotfile.com/dl/110283196/8ff46a6/Import_Export_V5-42-895-5-42.7z.html)
[DABoneCreator2.00.7z](https://xentaxbackup.github.io/file/4068_DABoneCreator2.00.7z)
## Post #22
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-15T05:16:45+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from sirew
>
> Hi guys, have you ever thought doing converter, with UI?, with just a click of a button and not using any command to convert, just asking

Well, 3DS Max and Blender both provide a better UI than I'm likely to come up with  

Honestly, I haven't given it any thought myself. For one or a few files, loading them into a 3D program is the easiest way for me to work because that's where I will edit or convert them. If I'm going to be doing multiple files, I prefer the command line. I can do something like:

find. | grep 'msh$' | xargs -I@ python da2obj.py @

and it'll convert a whole directory for me., Much faster than booting a GUI converter.

The other reason you don't want me writing a GUI is because (deep dark secret here) I work primarily on a Mac. I boot into Windows for some games, but for day-to-day stuff, I'm in OS X.

There is a pretty good Windows GUI program out there called something like 3D Object Converter - and the author is pretty good about following these boards and adding new game formats, might be worth checking it out, though I doubt the author's added DA2 yet since Chrrox just posted the file format recently.
## Post #23
- Username: greywaste
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 30, 2010 5:10 am
- Post datetime: 2011-03-15T17:38:13+00:00
- Post Title: Re: Dragon Age 2 (PC)

When I was taking a peek at some of the models, I cleared the folder of all files apart from .msh and .dds to make it easier to browse the textures, I noticed the .anb files were only about (+/-) 150, Maybe these have skeleton info since so many of the objects were statics?  Anyway though, figuring which one goes with which mesh : /
## Post #24
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-16T16:48:41+00:00
- Post Title: Re: Dragon Age 2 (PC)

Normal Maps

It turns out that the orange normal maps used by Dragon Age 2 are just run-of-the-mill tangent space normal maps, but they've been byte swapped. Instead of being in RGBA byte order. They appear to be in BGXR, where X is an unused value of 0 (tangent space normal map uses 3 values, so alpha is unneeded). Converting an orange normal map to a standard purple tangent space normal map is just a matter of swapping the bytes around. Here's the desire demon's body rendered with the converted alpha map. Notice the hint of abdominal muscles - those aren't in the model, they're coming from the normal map.



I'm attaching a converter as a binary for Mac OS X. For Windows, I'm attaching the source code - somebody else will have to compile it, as I don't have a compiler installed under Windows. It requires libpng, but otherwise, this is straight, platform agnostic C that should compile fine as a Windows command line program.

```
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <stdarg.h>

#define PNG_DEBUG 3

// Depending on platform, you may need to change the include
// #include <png.h>
#include "/usr/X11/include/png.h"

void abort_(const char * s, ...)
{
    va_list args;
    va_start(args, s);
    vfprintf(stderr, s, args);
    fprintf(stderr, "\n");
    va_end(args);
    abort();
}

int x, y;

int width, height;
png_byte color_type;
png_byte bit_depth;

png_structp png_ptr;
png_infop info_ptr;
int number_of_passes;
png_bytep * row_pointers;

void read_png(char* file_name)
{
    char header[8]; 
    FILE *fp = fopen(file_name, "rb");
    if (!fp)
        abort_("[read_png_file] File %s could not be opened for reading", file_name);
    fread(header, 1, 8, fp);
    if (png_sig_cmp((png_bytep)header, 0, 8))
        abort_("[read_png_file] File %s is not recognized as a PNG file", file_name);
    
    png_ptr = png_create_read_struct(PNG_LIBPNG_VER_STRING, NULL, NULL, NULL);
    
    if (!png_ptr)
        abort_("[read_png_file] png_create_read_struct failed");
    
    info_ptr = png_create_info_struct(png_ptr);
    if (!info_ptr)
        abort_("[read_png_file] png_create_info_struct failed");
    
    if (setjmp(png_jmpbuf(png_ptr)))
        abort_("[read_png_file] Error during init_io");
    
    png_init_io(png_ptr, fp);
    png_set_sig_bytes(png_ptr, 8);
    
    png_read_info(png_ptr, info_ptr);
    
    width = (int)png_get_image_width(png_ptr, info_ptr);
    height = (int)png_get_image_height(png_ptr, info_ptr);
    color_type = png_get_color_type(png_ptr, info_ptr);
    bit_depth = png_get_bit_depth(png_ptr, info_ptr);
    
    number_of_passes = png_set_interlace_handling(png_ptr);
    png_read_update_info(png_ptr, info_ptr);
    
    if (setjmp(png_jmpbuf(png_ptr)))
        abort_("[read_png_file] Error during read_image");
    
    row_pointers = (png_bytep*) malloc(sizeof(png_bytep) * height);
    for (y=0; y<height; y++)
        row_pointers[y] = (png_byte*) malloc(png_get_rowbytes(png_ptr,info_ptr));
    
    png_read_image(png_ptr, row_pointers);
    
    fclose(fp);
}


void write_png(char* file_name)
{
    FILE *fp = fopen(file_name, "wb");
    if (!fp)
        abort_("[write_png_file] File %s could not be opened for writing", file_name);
    
    png_ptr = png_create_write_struct(PNG_LIBPNG_VER_STRING, NULL, NULL, NULL);
    
    if (!png_ptr)
        abort_("[write_png_file] png_create_write_struct failed");
    
    info_ptr = png_create_info_struct(png_ptr);
    if (!info_ptr)
        abort_("[write_png_file] png_create_info_struct failed");
    
    if (setjmp(png_jmpbuf(png_ptr)))
        abort_("[write_png_file] Error during init_io");
    
    png_init_io(png_ptr, fp);

    if (setjmp(png_jmpbuf(png_ptr)))
        abort_("[write_png_file] Error during writing header");
    
    png_set_IHDR(png_ptr, info_ptr, width, height,
                 bit_depth, color_type, PNG_INTERLACE_NONE,
                 PNG_COMPRESSION_TYPE_BASE, PNG_FILTER_TYPE_BASE);
    
    png_write_info(png_ptr, info_ptr);
    if (setjmp(png_jmpbuf(png_ptr)))
        abort_("[write_png_file] Error during writing bytes");
    
    png_write_image(png_ptr, row_pointers);
    if (setjmp(png_jmpbuf(png_ptr)))
        abort_("[write_png_file] Error during end of write");
    
    png_write_end(png_ptr, NULL);
    
    for (y=0; y<height; y++)
        free(row_pointers[y]);
    free(row_pointers);
    
    fclose(fp);
}


void process_dragon_age_normal_map(void)
{
    
    for (y=0; y<height; y++) 
    {
        png_byte* row = row_pointers[y];
        for (x=0; x<width; x++) 
        {
            png_byte* ptr = &(row[x*4]);
//            printf("Pixel at position [ %d - %d ] has RGBA values: %d - %d - %d - %d\n",
//                   x, y, ptr[0], ptr[1], ptr[2], ptr[3]);
            
            png_byte tmp = ptr[2];
            ptr[2] = ptr[0];
            ptr[0] = ptr[3];
            ptr[3] = 255 - tmp;
        }
    }
}


int main(int argc, char **argv)
{
    if (argc != 3)
        abort_("Usage: danorm <file_in> <file_out>");
    
    read_png(argv[1]);
    process_dragon_age_normal_map();
    write_png(argv[2]);
    
    return 0;
}

```

[danorm_mac_os_x.zip](https://xentaxbackup.github.io/file/4073_danorm_mac_os_x.zip)
## Post #25
- Username: codo85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 19, 2011 10:10 pm
- Post datetime: 2011-03-19T20:46:28+00:00
- Post Title: Re: Dragon Age 2 (PC)

Hi guys, can somebody please explain how can I use figuresculptor's port to blender of chrrox's script?
I mean, I save the text in a .py file... and then?
I want to import DA2 models in blender, but Dragon Age Tools works only with DA:O models, and I don't know how to replace its scripts with the one posted in this thread.

Thanks in advance!
## Post #26
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-19T21:09:52+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from codo85
>
> Hi guys, can somebody please explain how can I use figuresculptor's port to blender of chrrox's script?
I mean, I save the text in a .py file... and then?

1) Save script to a text file. You may have to convert spaces to tabs (four spaces = 1 tab) depending on your version of Python. Make sure it has a .py extension. (if you have problems, I can upload the script in a zip file)
2) Launch Blender 2.56b
3) Go to the File menu and select "User Preferences"
4) Navigate to the Add-Ons tab
5) Click the "Install Add-On…" button at the bottom
6) Select the file where you saved the script
7) On the left side, select "Import-Export" to filter the sripts
 Look for the one that says "Import-Export: Import Dragon Age 2 Mesh files (.msh) and click the check-box on the right side so it's checked
9) Close the user preferences window
10) Type ctrl-u to save the preference changes
11) Select File menu, Import submenu, Dragon Age 2 Mesh (.msh)
12) Find the file you want to import
13) Profit!
## Post #27
- Username: codo85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 19, 2011 10:10 pm
- Post datetime: 2011-03-19T22:35:17+00:00
- Post Title: Re: Dragon Age 2 (PC)

Awesome man, awesome!
I could import several DA2 models and edit them with no problems.
Now we have to wait for a script to export the models in .msh format, so that we can pack them back in .erf files and see them in game, am I right?
## Post #28
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-19T23:07:16+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from codo85
>
> Now we have to wait for a script to export the models in .msh format, so that we can pack them back in .erf files and see them in game, am I right?

Well, somebody needs to figure out how to extract the bones and which vertices are attached to which bones, and THEN we need to be able to get the data back into .erf files (which I think is now possible - the v3.0 erf file seems to be laid out here: [http://social.bioware.com/wiki/datoolset/index.php/ERF](http://social.bioware.com/wiki/datoolset/index.php/ERF).

Over at Dragon Age Nexus, tazpn appears to have figured out the file format changes for DA2: [http://social.bioware.com/project/4253/#details](http://social.bioware.com/project/4253/#details) However, I'm unable to get the erf extraction to work - it doesn't seem to do anything, and when I try to convert a mesh, I get an error (possibly from not having the .mmh available). His source code is available, so if I had time, I'd look through is code and see where the bones are, but it will probably be a few more weeks before I have that kind of time to spend on this stuff again.

It looks like it's possible to create modified meshes now, but since I can't get tazpn's tool to work, I can't confirm it, and I haven't seen any body creating mesh mods yet, so not sure where that leaves us.
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-19T23:48:20+00:00
- Post Title: Re: Dragon Age 2 (PC)

if someone sends me a bone file ill look at the format no problem
## Post #30
- Username: codo85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 19, 2011 10:10 pm
- Post datetime: 2011-03-19T23:49:26+00:00
- Post Title: Re: Dragon Age 2 (PC)

Umh... I fear I'm missing something...
This is my naive approach to the matter.
My plan was to extract the different files (.mmh, .msh and .phy), edit them and pack them back in .erf.
Extracting the files from .erf is easy with GFF editor.
Packing the files back is even easier with Erf packer.
To edit the models I think I have to import the .msh in blender with the script you posted and, when the editing is finished, to get another .msh file as output. In order to do this I think I need an export script, which is the only thing we're lacking... or not?
## Post #31
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-20T00:45:16+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from codo85
>
> Umh... I fear I'm missing something...
This is my naive approach to the matter.

What you're missing is that a mesh has to be tied to its armature. Every vertex in the mesh has to be specified as being part of certain bones, or the character will not animate correctly. That means, if you add any vertices, or move them in a way that would require a different bone influence. That data is not currently imported into blender, and therefore can't be changed. If all you do is tweak the vertices of the existing mesh a little without adding any and without moving any very far, then your approach might work, otherwise, it's likely the character won't animate correctly.

Even if we wrote an exporter based on what we know now, it probably wouldn't work, as there is unmapped vertex data in some of the models - probably normals, binormals and tangents (used which can all be calculated in 3DS Max or Blender when needed, but stored in game files because they are too slow to calculate at runtime. Until we know which bits of unknown data are what, the exporter would be failing to provide certain data that is needed.

As I said, though, I think tazpn over at Dragon Age Nexus has figured out what goes where, but he hasn't documented it, so right now, it means either more reverse engineering or digging through tazpn's fairly complex code, neither of which I have the time for at the moment.  But, if nobody else does it before I have time, I'll look for a solution when I can.
## Post #32
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-20T01:22:53+00:00
- Post Title: Re: Dragon Age 2 (PC)

its easy enough to figure out the vertex structure but i dont have any bones to put to a model what files are the bones in?
## Post #33
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-20T03:37:48+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from chrrox
>
> its easy enough to figure out the vertex structure but i dont have any bones to put to a model what files are the bones in?

From briefly looking at tazpn's code, it looks like they're stored in the .mmh file, or at least their location in another file is stored there. I haven't had time to go very extensively into the code.
## Post #34
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-20T16:13:34+00:00
- Post Title: Re: Dragon Age 2 (PC)

which script is for blender?, because, it confusing me which is it is :d
## Post #35
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-20T16:30:31+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from sirew
>
> which script is for blender?, because, it confusing me which is it is :d

This one: [viewtopic.php?p=50958#p50958](http://forum.xentax.com/viewtopic.php?p=50958#p50958)
## Post #36
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-20T18:28:39+00:00
- Post Title: Re: Dragon Age 2 (PC)

Couple of things learned today. 

pyGFF can extract the DA2 ERF files, and it has a database of hashes and files, so it's possible to extract the ERF file into the appropriate hierarchy structure, restoring the proper names needed for overriding. There are some files that aren't mapped, but it looks like all the .msh, .mmh, and .dds files are, and those are what we care about. I extracted artpf.erf and now have the mmh, msh, and dds files with the appropriate names and in the appropriate folders. At very least, this makes it hugely easier to find the correct texture for a given model.

gff4editor is available from DA Nexus: [http://social.bioware.com/project/1936/](http://social.bioware.com/project/1936/)

Poking around the code for pyGFF has been very enlightening in terms of the file format, and the source contains a pretty complete list of the field types used in the .msh and .mhh files.

The bones definitely ARE in the .mmh file, as is a reference to the corresponding .msh file and a list of the meshes in the .msh file, including the name of each mesh (which I assume will be needed when it comes time to write an exporter). I've made some progress on finding the actual bone data, but it's slow going. I've now got the root node of the skeleton and am working on how to parse out child lists from GFF files. Still not sure where the bone indices are stored - whether they're in the .mmh or .msh file. At very least, the .msh file stores a list of the bones it uses, and I'm guessing the bone index is one of the bits of currently unmapped vertex data in the .msh file.

Once I'm able to iterate down into child nodes, I should be able to figure out how to import the skeleton since I know what bone index fields look like, thanks to pyGFF.
## Post #37
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-21T07:34:04+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from figuresculptor
>
> codo85 wrote:Hi guys, can somebody please explain how can I use figuresculptor's port to blender of chrrox's script?
I mean, I save the text in a .py file... and then?

1) Save script to a text file. You may have to convert spaces to tabs (four spaces = 1 tab) depending on your version of Python. Make sure it has a .py extension. (if you have problems, I can upload the script in a zip file)
2) Launch Blender 2.56b
3) Go to the File menu and select "User Preferences"
4) Navigate to the Add-Ons tab
5) Click the "Install Add-On…" button at the bottom
6) Select the file where you saved the script
7) On the left side, select "Import-Export" to filter the sripts
 Look for the one that says "Import-Export: Import Dragon Age 2 Mesh files (.msh) and click the check-box on the right side so it's checked
9) Close the user preferences window
10) Type ctrl-u to save the preference changes
11) Select File menu, Import submenu, Dragon Age 2 Mesh (.msh)
12) Find the file you want to import
13) Profit!

HI, I'm using blender 2.6.2 and I didn't see any file menu that have install add-on, hope some one can help
## Post #38
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-22T12:14:14+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from figuresculptor
>
> pyGFF can extract the DA2 ERF files.
tell me how to unpack *.erf from da2 with structure and names.
## Post #39
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-22T14:17:23+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Tosyk
>
> tell me how to unpack *.erf from da2 with structure and names.

Here you go:

1 If you don't already have wxPython installed, download it from wxpython.org and install it
2 Download the latest filename hash database at [http://www.sendspace.com/file/uitq9g](http://www.sendspace.com/file/uitq9g)
3 Download the latest version of pyGFF at [http://social.bioware.com/project/1936/](http://social.bioware.com/project/1936/)
4 Copy fnvhashes.sqlite into the  gff4editor-0.5.2b folder, replacing the existing file
5 Launch the Editor.exe application that's inside the gff4editor-0.5.2b folder
6 From the File menu, select "Export All"
7 Select the erf file to extract
8 Select destination to extract to
9 Profit!
## Post #40
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-22T14:34:51+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from figuresculptor
>
> Tosyk wrote:tell me how to unpack *.erf from da2 with structure and names.

Here you go:

1 If you don't already have wxPython installed, download it from wxpython.org and install it
2 Download the latest filename hash database at http://www.sendspace.com/file/uitq9g
3 Download the latest version of pyGFF at http://social.bioware.com/project/1936/
4 Copy fnvhashes.sqlite into the  gff4editor-0.5.2b folder, replacing the existing file
5 Launch the Editor.exe application that's inside the gff4editor-0.5.2b folder
6 From the File menu, select "Export All"
7 Select the erf file to extract
8 Select destination to extract to
9 Profit!

thanks man, looking for second only, now everything is working
## Post #41
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2011-03-23T02:13:10+00:00
- Post Title: Re: Dragon Age 2 (PC)

Love the script.

For some reason the hair mesh I exported and imported with Tzpans tools didn't save the UV map, allthough all the other meshes had it intact, buuut the script actually made it.
Saved me alot of fustration, now I'll just have to figure out the akwardly mapped channels in the dds files.
## Post #42
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-23T02:44:38+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from bugmenotty
>
> For some reason the hair mesh I exported and imported with Tzpans tools didn't save the UV map, allthough all the other meshes had it intact, buuut the script actually made it.

I noticed this too, and so far only with hair. I honestly think the UV data just isn't there for models with a vertex size of 40 (which seems to be used exclusively for hair models). I'm not sure how they're doing hair in-game, but I've looked at the unknown vertex data in the hair models, and none of it looks like UV data. Plus, the data we're pulling the UVs from actually do contain valid UV data, it's just that every vertex has the same value of (1.0, 0.0). None of the other unused data fields fall consistently between 0.0 and 1.0.

So, long story short, I think they're doing something funky with the hair, but I have no idea what it is.
## Post #43
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2011-03-24T01:29:43+00:00
- Post Title: Re: Dragon Age 2 (PC)

I'm confused.

I ment I actually did get the UV with the hair mesh, by using the script. Instead of tzpans exporter.
I've also toyed around with the hair texture dds, wich seems to be shared between all hair meshes in the game.
It's rather funky, and I can't make much out of it. Seems to have 4 diffrent channels with diffrent maps in each one. Spec, diffuse, normal and opacity. 
The diffuse layer, if that's what it is, is grey and colorless, wich makes somewhat sense considering how you are able to swap around colors igame, so maybe it just uses some blending mode, heck if I know.

Mostly speculation, but it's the best I can make of it.

Quick render [](http://img405.imageshack.us/img405/953/headxb.jpg)
## Post #44
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-24T01:58:23+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from bugmenotty
>
> I ment I actually did get the UV with the hair mesh, by using the script. Instead of tzpans exporter.

That's interesting. I don't get UVs for 90% of the hair meshes with the script. A few of them I do, but not for most of them.
## Post #45
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-26T12:38:42+00:00
- Post Title: Re: Dragon Age 2 (PC)

Blender249 armature importer for .mmh files from Dragon age 2.
[mmh.blend.zip](https://xentaxbackup.github.io/file/4108_mmh.blend.zip)
## Post #46
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-03-26T13:20:07+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Szkaradek123
>
> Blender249 armature importer for .mmh files from Dragon age 2.

Awesome work! This script works beautifully!

I hope you don't mind if I add this functionality to the 2.5.x mesh import script in the thread. I'll make sure to give you full credit, I just find it hard to work in 2.49 these days after having jumped to 2.5 full time quite a while ago.
## Post #47
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-26T21:38:17+00:00
- Post Title: Re: Dragon Age 2 (PC)

Update for importer:
 - add import geometry with weighting and uv-mapping (*.msh)
[import-dragon-age-2-2011-03-26.zip](https://xentaxbackup.github.io/file/4113_import-dragon-age-2-2011-03-26.zip)
## Post #48
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-27T02:46:08+00:00
- Post Title: Re: Dragon Age 2 (PC)

[Subject: Dragon Age 2 (PC)](http://forum.xentax.com/viewtopic.php?p=51691#p51691)

> Reply from Szkaradek123
>
> Update for importer:
 - add import geometry with weighting and uv-mapping (*.msh)
thanks Szkaradek123, and also thanks figuresculptor for your researches, but blender 2.49b is more native for me.
## Post #49
- Username: Erik24
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 22, 2011 7:23 am
- Post datetime: 2011-03-27T17:34:44+00:00
- Post Title: Re: Dragon Age 2 (PC)

update 3d max script?
## Post #50
- Username: fonglee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 03, 2011 3:08 am
- Post datetime: 2011-04-02T19:58:38+00:00
- Post Title: Re: Dragon Age 2 (PC)

Thanks very much for the importer script, it works perfectly   but is there any chance you can make an exporter or replacer? The reason I ask is simple, I wish to mod the meshes for use in game, and while the importer will make modding the mesh possible, I have no way currently to put them back into the game. 

Edit: never mind my question about an exporter, just read the rest of the pages and see that you guys are working on it already...my bad...
## Post #51
- Username: CountVirgo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 03, 2011 6:19 am
- Post datetime: 2011-04-02T23:56:40+00:00
- Post Title: Re: Dragon Age 2 (PC)

Apologies for what is undoubtedly a noobish question (I have only been playing about with Blender for a week or so now), however I would much appreciate it if someone could answer it 

I have quite happily managed to extract the .msh files, and then import them into blender using figuresculptor's script and am trying to do exactly the same thing as in [that post](http://forum.xentax.com/viewtopic.php?p=50958#p50958) (import the msh & texture the Desire Demon).

Importing the .msh went just fine (as shown below), my problem is I can not work out how to add the .dds texture to the mesh.
I have googled it (adding the dds to a blender mesh) to no avail... so would much appreciate some pointers (or a link to a tutorial if there is one)!

Thanks in advance 

Edit: I am using Blender 2.56 Beta.
[Desire.png](https://xentaxbackup.github.io/file/4154_Desire.png)
## Post #52
- Username: daywalker03
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 03, 2011 8:13 am
- Post datetime: 2011-04-03T01:03:32+00:00
- Post Title: Re: Dragon Age 2 (PC)

chrrox: I see you've got the import script mostly working; the only thing that would be nice is a way to scale it up to a manageable working size. Any progress on an export converter for this?
## Post #53
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-03T01:48:06+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from CountVirgo
>
> Importing the .msh went just fine (as shown below), my problem is I can not work out how to add the .dds texture to the mesh.
I have googled it (adding the dds to a blender mesh) to no avail... so would much appreciate some pointers (or a link to a tutorial if there is one)!

Okay, so, yeah. This is not exactly a straightforward process. A week with Blender is just enough time to get frustrated  You might want to look at Szkaradek123's script. It works with the older Blender 2.49b, but it does import the textures and armature, not just the mesh, and once you've imported and saved, you can open the file in Blender 2.56 no problem.

If you're feeling brave, the way you add textures is as follows:

1) Right-click on the object to select it and and hit tab to go into edit mode (tab - so it's showing vertices)
2) In the properties view, select the material tab (fourth from the right, icon is a checkered sphere):



Screen shot 2011-04-02 at 9.10.30 PM.png (24.72 KiB) Viewed 414 times


3) There should be at least one material. Each one will correspond to parts of the model that use the same tetxure map(s). So, for example, the head might have two textures, one for the eyes and one for the rest of the head. Select one and hit the "Select" button on the material tab. This should select all of the vertices and give you an idea about which texture you should be using. If there's only one (which is true for most bodies), you could have just pressed the A key to select all the vertices, but wanted you to see the materials tab - this is where you specify base color, shininess (specularity), transparency, etc.
4) Now, click the texture tab (third from the right, icon is a checkered square. There should be a list of textures with red checkerboards with no names. Those are the textures for the currently selected material, and if they have no name, they're just an empty slot waiting for a texture. The material and texture tabs work together - the texture changes here affect the currently selected material in the materials tab. 
5) Single-click the top empty item in the list of textures and then click the "+ New" button to create a new texture. Optionally, you might want to rename the newly created Texture from "Texture" to "Diffuse" because this texture channel is going to hold our diffuse texture (the main texture with colors)
6) Change the Type of the new Texture from "Clouds" to "Image or Movie"
7) Look down for the section called Image, and hit the "Open" button. Find the appropriate .dds file in your file system and select it. In your case, you want cn_bdy_suca_0d.dds for the body.
 After you select the image, it should add some new fields to the Image section. Look for a checkbox called "Premultiply" and check-it. DA2 maps that use alpha use premultiplied alpha, so you need to select this for things like hair to look right.
9) In the Image Sampling section, make sure under Alpha:, the "Use" checkbox is checked. If not, check it. Not all textures in DA2 use alpha, but many do, and I believe the Desire Demon is one that does.
10) Go down further to the Mapping section (click the disclosure triangle if it's not visible) and change the Coordinates from "Generated" to "UV", then in the new Layer field that comes up, click and select UVTex (or whatever it's called - there should only be one UV coordinate layer)

Now you've got the base texture added. If you add some lights and setup the camera, you should be able to render. Switching your 3D view to "textured" mode probably won't show this new texture, however - this is for the rendered object, there's actually a different place to set it up, which I'll identify in a moment, but I'll tell you how to add the normal map to get the fine details first

Unfortunately, Dragon Age 2 uses byte-swapped normal maps. There's source code earlier in this thread that will create a program to process a normal map. The normal map in your case is cn_bdy_suca_0n.dds for the body (n for normal, see how that works?) The conversion sript works on .png images. So, you need to convert from .dds to .png  (You can open it in Blender and save as a PNG), then byte swap the png with the program, which will create a purple tangent-space normal map out of the byte-swapped gold normal map from the game. You don't have to convert back to dds for Blender, it's happy to use png images.

Once you've converted to a purple tangent-space normal map, you select the second texture in the list (the first empty one) and repeat the steps above, only selecting the normal map. Then, there's a few extra steps you have to take to tell Blender this is a normal map, not a diffuse map, including

1) Under the Image Sampling section, click "Normal Map" and make sure "Tangent" is selected.
2) Scroll down to the "Influence" section. Unclick the "Color" checkbox under the Diffuse: section and then and click the "Normal" checkbox under the Geometry section.

Now your renders should pick up some of the fine details like wrinkles and folds.

DA2 files commonly have several other types of image maps. You don't need them, but they'll give extra oomph. The cn_body_suca_0s.dds is a specularity map. It defines what parts of the model reflect more light. This will make jewelry and weapons reflect light from your light sources more realistically. The process for adding a specularity map is the same as the diffuse texture, except uncheck "Color" in the "Influence" section and check "Intensity" and "Color" under the Specular: section.

I'm not 100% sure what the other two are. I think the one that ends in "e" (cn_body_suca_0s.dds) is an emission map - it defines parts of the model that actually emit light. If I'm right about this (and I'm not sure I am), it would be used for things like glowing eyes.

I have no idea what the map that ends in "t" is (cn_body_suca_0t.dds). It seems to hold some kind of pattern (a checkerboard in the case of the desire demon) and I honestly haven't a clue what it's for.

Finally, if you want the texture to show up when displaying the 3D view in Textured mode, you'll need to convert one of the panes (not the 3D view) into a UV/Image editor. If the selected object is in Edit mode and there are vertices selected, you should see a graphical representation of the UV coordinates in the UV/Image editor. Now, in the bottom of the UI/Image editor, look for the "+ New" button, but don't press it. Instead, hit the little image icon right to the left of it and select cn_body_suca_0d.dds. That should overlay your UV coordinates over the diffuse texture. Now the textured mode should work. Textured mode doesn't work well with multi-texture models. I rarely work in texture mode anyway.

Hope that helps.
## Post #54
- Username: daywalker03
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 03, 2011 8:13 am
- Post datetime: 2011-04-03T02:10:32+00:00
- Post Title: Re: Dragon Age 2 (PC)

figuresculpter: the *_t.dds files are tint maps, which determine if a given model can have its color changed when used as a base model for an item.
## Post #55
- Username: lpss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 02, 2011 11:51 pm
- Post datetime: 2011-04-03T18:20:46+00:00
- Post Title: Re: Dragon Age 2 (PC)

I can't seem to export the hair and beard meshes with the UV maps. Is there any workaround for this?
## Post #56
- Username: CountVirgo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 03, 2011 6:19 am
- Post datetime: 2011-04-03T23:34:43+00:00
- Post Title: Re: Dragon Age 2 (PC)

figuresculptor - Thank you for the reply, very much appreciated 

As for using Szkaradek123's script, I tried that and imported the MSH/MMH just fine but could not figure out the texture part, I selected the directory, clicked re-load textures and it didn't seem to do anything - I really dislike Blender 2.49b's GUI too, so i'll probably just stick with doing it the long way for now
## Post #57
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-04T00:13:40+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from CountVirgo
>
> figuresculptor - Thank you for the reply, very much appreciated

You're welcome.

> Reply from CountVirgo
>
> I really dislike Blender 2.49b's GUI too, so i'll probably just stick with doing it the long way for now

yeah, I feel the same way, but I've been using Blender long enough that it's not really an issue for me. I remember what it's like trying to learn this beast, though, so thought I'd make the suggestion.
## Post #58
- Username: CountVirgo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 03, 2011 6:19 am
- Post datetime: 2011-04-04T00:57:54+00:00
- Post Title: Re: Dragon Age 2 (PC)

figuresculptor - I'm so close now, it's just the last step that has me stumped.

Everything else has gone fine, I've selected the object, gone into edit mode, added the Diffuse and Normal maps (thanks for the Normal map converter too!) go to the UV/Image Editor, select the cn_bdy_0d.dds file, and the selected vertices look like they are a flipped version of the Diffuse map.

Any idea where I went wrong? I've attached a picture to show what I mean.
Also [this is is a zipped version of my .blend file](http://cl.ly/2n1e1I423z0W1t1u012U) if you want to take a look yourself.
[Desire.png](https://xentaxbackup.github.io/file/4161_Desire.png)
## Post #59
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-04T01:04:57+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from CountVirgo
>
> Any idea where I went wrong? I've attached a picture to show what I mean.
Also this is is a zipped version of my .blend file if you want to take a look yourself.

Oh, my bad - I forgot that the UV coordinates are flipped on the Y axis. In the UV Image editor, under the UV file menu, look for the Mirror option, and the "Y Axis" suboption (I'm not at my computer, so can't verify the exact names). That will flip the UVs on the Y axis. You might need to tweak them a tiny bit once you flips them, but mirroring on the Y should take care of 99% of the problem.
## Post #60
- Username: CountVirgo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 03, 2011 6:19 am
- Post datetime: 2011-04-04T02:39:03+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from figuresculptor
>
> Oh, my bad - I forgot that the UV coordinates are flipped on the Y axis. In the UV Image editor, under the UV file menu, look for the Mirror option, and the "Y Axis" suboption (I'm not at my computer, so can't verify the exact names). That will flip the UVs on the Y axis. You might need to tweak them a tiny bit once you flips them, but mirroring on the Y should take care of 99% of the problem.
Great, got it - Thanks.

In case any other Blender noobs have been following this and do not understand the last bit:

1) Select Mesh in 3D mode (right click) press Tab to enter Edit mode.
2) Switch to the UV/Image Editor
3) Press A to select all.
4) UVs -> Mirror -> Click "Y Axis", the UV coordinates will be flipped.
5) Click the button just to the left of + New (it has a picture of an image on it)
6) Select the Diffusion map (the one ending in _0d.dds)
7) Switch back to 3D View
8) Press Tab to deselect the mesh
9) Change viewport shading to Textured
10) Enjoy the fully textured model!

:)
## Post #61
- Username: lpss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 02, 2011 11:51 pm
- Post datetime: 2011-04-04T02:47:32+00:00
- Post Title: Re: Dragon Age 2 (PC)

I still can't get the hair/beard meshes with UV maps on Blender... 
 Does anyone know a way to do it? I'm using the Blender 2.49 script as I already had Blender 2.49
## Post #62
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-05T23:27:04+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from lpss
>
> I still can't get the hair/beard meshes with UV maps on Blender... 
 Does anyone know a way to do it? I'm using the Blender 2.49 script as I already had Blender 2.49

lpss:

The same problem exists with the 2.5.6 script - I've actually combed through the beard and hair, and it just looks like all the UVs are set to 0,0 or 1,0.  I've looked through the vertex data for other potential UV data, and found nothing. I'm not sure what's going on with the hair or beards, but it's not anything you're doing - it is the script.
## Post #63
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-05T23:35:46+00:00
- Post Title: Re: Dragon Age 2 (PC)

Blender 2.57, which is the Release Candidate for the 2.5 branch, was posted a few days ago… and broke compatibility with most scripts.

I've updated my 2.56 script to work with 2.57. I haven't had time to add the armature parsing yet, but I did add an option to rotate the object to face front.

NB: For some reason, this isn't working correctly as an addon right now. If you open the script in Blender and run it, it will add a menu item. When I've figured out why it doesn't work as an addon, I'll post the fixed version.


```
	"name": "Import Dragon Age 2 Mesh files (.msh)",
	"author": "FigureSculptor",
	"version": (2, 1),
	"blender": (2, 5, 7),
	"api": 35622,
	"location": "File > Import ",
	"description": "Import Dragon Age 2 Mes (.msh)",
	"warning": "",
	"wiki_url": "",
	"tracker_url": "",
	"category": "Import-Export"}

"""
Version': '1.0' 

This is a straight port of the 3DS Max Script from this forum
posting:

http://forum.xentax.com/viewtopic.php?f=16&t=6119&hilit=dragon+age+2

This version is based on the script posted with this timestamp

Posted: Mon Mar 14, 2011 3:22 am 

All credit to chrrox for figuring the format out.

"""

import bpy
import mathutils
import os
import sys
import string
import math
import re
from string import *
from struct import *
from math import *
import mathutils
from bpy.props import *


DEBUGLOG = False
LONGSIZE = 4
FLOATSIZE = 4
HALFFLOATSIZE = 2
SHORTSIZE = 2

def unpack_list(list_of_tuples):
	l = []
	for t in list_of_tuples:
		l.extend(t)
	return l

def halfToFloatPrivate(h):
	s = int((h >> 15) & 0x00000001)		# sign
	e = int((h >> 10) & 0x0000001f)		# exponent
	f = int(h &			0x000003ff)		# fraction

	if e == 0:
		if f == 0:
			return int(s << 31)
		else:
			while not (f & 0x00000400):
				f <<= 1
				e -= 1
			e += 1
			f &= ~0x00000400
	elif e == 31:
		if f == 0:
			return int((s << 31) | 0x7f800000)
		else:
			return int((s << 31) | 0x7f800000 | (f << 13))

	e = e + (127 -15)
	f = f << 13

	return int((s << 31) | (e << 23) | f)

def halfToFloat(h):
	result = halfToFloatPrivate(h)
	str = pack('I',result)
	f = unpack('f', str)
	return f[0]
	
def mshImport(infile, props):
	global DEBUGLOG
	print ("--------------------------------------------------")
	print ("---------SCRIPT EXECUTING PYTHON IMPORTER---------")
	print ("--------------------------------------------------")
	print ("Importing file: ", infile)
	
	mshfile = open(infile,'rb')
	if (DEBUGLOG):
		logpath = infile.replace(".msh", ".txt")
		print("logpath:",logpath)
		logf = open(logpath,'w')
		
	def printlog(strdata):
		if (DEBUGLOG):
			logf.write(strdata + "\n")

	basename = os.path.basename(infile)	
	
	printlog("basename:" + basename)
	
	mshfile.seek(0x1A0)
	baseoff = 0x1A0
	

	namebase, garbage, unkbase, vertbase, facebase, garbage1, garbage2, meshcount = unpack('<8l', mshfile.read(8*LONGSIZE))

	printlog("baseoff: " + str(baseoff))
	printlog("unkbase: " + str(unkbase))
	printlog("vertbase: " + str(vertbase))
	printlog("facebase: " + str(facebase))
	printlog("meshcount: " + str(meshcount))
	
	vertSizeArray = []
	vertCountArray = []
	faceCountArray = []
	vertPosArray = []
	facePosArray = []
	
	for i in range(meshcount):
		printlog("assessing mesh " + str(i))
		float01, float02, float03, float04, float11, float12, float13, float14, float21, float22, float23, float34 = unpack('<12f', mshfile.read(12*FLOATSIZE))
		unk01, vertSize, vertCount, faceCount, vertPos, facePos, unk2, long01, long02, long03, long04, vertCount2 = unpack('<12l', mshfile.read(12*LONGSIZE))
		printlog("\tvertsize: " + str(vertSize))
		printlog("\tvertCount: " + str(vertCount))
		printlog("\tfaceCount: " + str(faceCount))
		printlog("\tvertPos: " + str(vertPos))
		printlog("\tfacePos: " + str(facePos))
		vertSizeArray.append(vertSize)
		vertCountArray.append(vertCount)
		faceCountArray.append(faceCount)
		vertPosArray.append(vertPos)
		facePosArray.append(facePos)
	
	faceStart = baseoff + facebase + 4
	vertStart = baseoff + vertbase + 4
	nameStart = baseoff + namebase
	unkStart = baseoff + unkbase
	
	if (DEBUGLOG):
		printlog("faceStart: " + str(faceStart))
		printlog("vertStart: " + str(vertStart))
		printlog("nameStart: " + str(nameStart))
		printlog("unkStart: " + str(unkStart))
	
	for a in range(meshcount):
		me_ob = bpy.data.meshes.new(basename + str(a))
		printlog(("New Mesh = " + me_ob.name))
		vertArray = []
		uvArray = []
		normalArray = []
		faceArray = []
		printlog("===Offset = " + str(vertStart + vertPosArray[a]))
		printlog("===vertStrt = " + str(vertStart))
		printlog("===vertPos[a] = " + str(vertPosArray[a]))
		mshfile.seek(vertStart + vertPosArray[a])
		for b in range(vertCountArray[a]):
			data = mshfile.read(3*FLOATSIZE)
			vx, vy, vz = unpack('<3f', data)
			bytesOfUnknown = (vertSizeArray[a] - 16)
			unknown = mshfile.read(bytesOfUnknown)
			tu_h = unpack('H', mshfile.read(HALFFLOATSIZE))
			tv_h = unpack('H', mshfile.read(HALFFLOATSIZE))
			tu = halfToFloat(tu_h[0])
			tv = halfToFloat(tv_h[0])
			vertArray.extend([(vx, vy, vz)])
			uvArray.extend([(tu, tv)])
	
		printlog("facePosArray: " + str(facePosArray[a]))
		mshfile.seek(faceStart + facePosArray[a] * 2)
		faceLen = faceCountArray[a]
		
		printlog("faceCountArray length: " + str(faceLen))
		
		if (faceLen > 0):
			faceLen = faceLen / 3
		else:
			faceLen = 0
		printlog("facelen: " + str(faceLen))
		
		faceUVArray = []
		
		for b in range(int(faceLen)):
			f1, f2, f3 = unpack('<3h', mshfile.read(3*SHORTSIZE))
			if (f1 < len(vertArray) and f2 < len(vertArray) and f3 < len(vertArray)):
				faceArray.extend([f1, f2, f3, 0])
				faceUVArray.extend([(uvArray[f1], uvArray[f2], uvArray[f3])])
			#printlog("Adding array:" + str(f1) + ", " + str(f2) + ", " + str(f3))
			
		printlog("vertArray length: " + str(len(vertArray)))
		printlog("faceArray length: " + str(len(faceArray)))
		me_ob.vertices.add(len(vertArray))
		me_ob.faces.add(len(faceArray)//4)
		me_ob.vertices.foreach_set("co", unpack_list(vertArray))
		me_ob.faces.foreach_set("vertices_raw", faceArray)
		me_ob.faces.foreach_set("use_smooth", [False] * len(me_ob.faces))
		
		texture = []
		texturename = basename + "_tex_" + str(a)
		if (len(faceUVArray) > 0):
			uvtex = me_ob.uv_textures.new() #add one uv texture
			uvtex.name = "Imported UV"
			for i, face in enumerate(me_ob.faces):
				blender_tface= uvtex.data[i] #face
				blender_tface.uv1 = faceUVArray[i][0] #uv = (0,0)
				blender_tface.uv2 = faceUVArray[i][1] #uv = (0,0)
				blender_tface.uv3 = faceUVArray[i][2] #uv = (0,0)
			texture.append(uvtex)
		
		materialname = "mat"
		materials = []

		matdata = bpy.data.materials.new(materialname)
		matdata.diffuse_color=(float(0.04),float(0.08),float(0.44))#blue color
		
		texdata = None
		texIndex = len(bpy.data.textures) - 1
		if (texIndex >= 0):
			texdata = bpy.data.textures[len(bpy.data.textures)-1]
			if (texdata != None):
				texdata.name = "texturelist1"
				matdata.active_texture = texdata
		materials.append(matdata)
		for material in materials:
			#add material to the mesh list of materials
			me_ob.materials.append(material)
			
		me_ob.update()
		
		obmesh = bpy.data.objects.new(basename,me_ob)
		bpy.context.scene.objects.link(obmesh)
		if props.rotate_z_180:
			mat_z180 = mathutils.Matrix.Rotation(math.pi, 4, 'Z')
			me_ob.transform(mat_z180)
		bpy.context.scene.update()
	
def getInputFilename(filename, props):
	checktype = filename.split('\\')[-1].split('.')[1]
	print ("------------",filename)
	if checktype.upper() != 'MSH':
		print ("  Selected file = ",filename)
		raise (IOError, "The selected input file is not a *.msh file")
	mshImport(filename, props)

class IMPORT_OT_dragonage_mesh(bpy.types.Operator):
	'''Import from Dragon Age Mesh file (.msh)'''
	bl_idname = "import_scene.dragonage_msh"
	bl_description = 'Import from Dragon Age mesh file (.msh)'
	bl_label = "Import Dragon Age Mesh"
	bl_space_type = "PROPERTIES"
	bl_region_type = "WINDOW"
	
	rotate_z_180 = BoolProperty(name="Rotate Z 180",
							description="Rotate 180 degrees around Z so model faces front.",
							default=True)


	# List of operator properties, the attributes will be assigned
	# to the class instance from the operator settings before calling.
	filepath = StringProperty(name="File Path", description="Filepath used for importing the MSH file", maxlen= 1024, default= "", subtype='FILE_PATH')

	def execute(self, context):
		props = self.properties
		getInputFilename(self.filepath, props)
		return {'FINISHED'}

	def invoke(self, context, event):
		wm = context.window_manager
		wm.fileselect_add(self)
		return {'RUNNING_MODAL'}

def menu_func(self, context):
	self.layout.operator(IMPORT_OT_dragonage_mesh.bl_idname, text="Dragon Age 2 Mesh (.msh)")


def register():
	bpy.utils.register_module(__name__)

	bpy.types.INFO_MT_file_import.append(menu_func)


def unregister():
	bpy.utils.unregister_module(__name__)
	bpy.types.INFO_MT_file_import.remove(menu_func)


if __name__ == "__main__":
	register()

```
## Post #64
- Username: lpss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 02, 2011 11:51 pm
- Post datetime: 2011-04-05T23:39:08+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from figuresculptor
>
> lpss wrote:I still can't get the hair/beard meshes with UV maps on Blender... 
 Does anyone know a way to do it? I'm using the Blender 2.49 script as I already had Blender 2.49

lpss:

The same problem exists with the 2.5.6 script - I've actually combed through the beard and hair, and it just looks like all the UVs are set to 0,0 or 1,0.  I've looked through the vertex data for other potential UV data, and found nothing. I'm not sure what's going on with the hair or beards, but it's not anything you're doing - it is the script.
Thanks, figuresculptor! I hope you guys find the UV maps soon.
## Post #65
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-05T23:45:45+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from lpss
>
> Thanks, figuresculptor! I hope you guys find the UV maps soon.

We have… for everything else. I honestly think they're doing something weird at runtime with the hair and beards, so I'm not sure we're ever going to find them.
## Post #66
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-07T04:17:03+00:00
- Post Title: Re: Dragon Age 2 (PC)

Update for Blender249 importer:
- add uv-mapping for hair and beards.
[import-dragon-age-2.zip](https://xentaxbackup.github.io/file/4171_import-dragon-age-2.zip)
## Post #67
- Username: lpss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 02, 2011 11:51 pm
- Post datetime: 2011-04-07T19:31:36+00:00
- Post Title: Re: Dragon Age 2 (PC)

You rock, dude!
## Post #68
- Username: bullet333
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 07, 2011 10:41 pm
- Post datetime: 2011-05-07T19:01:57+00:00
- Post Title: Re: Dragon Age 2 (PC)

I got the script to work in 3ds max, but I'm having a lot of trouble finding the face and hair textures.  Can someone please help me out?

Oh and I'm also trying to get the Blender script to work as well, but I'm a noob and don't know how to create that .py file you guys are talking about.  I've tried using those .blend files, but it just doesn't give me the option to import .msh files.
## Post #69
- Username: superchickensoup
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 13, 2011 8:32 pm
- Post datetime: 2011-05-13T13:22:49+00:00
- Post Title: Re: Dragon Age 2 (PC)

Hi, is it possible for anyone to e-mail me a obj of flemeth from da2. I just need the mesh and textures. Im building a high poly version and need the mesh for referance.
I managed to extract the msh files but could not find flemeth's model.
You can see my work Here
[http://www.airflow3d.com](http://www.airflow3d.com)
Any help would be appc.

E-mail
robangol @ [g00glem@il.com](mailto:g00glem@il.com)
superchickensoup @ [g00glem@il.com](mailto:g00glem@il.com)

Huge thanks.
## Post #70
- Username: anzolino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:34 pm
- Post datetime: 2011-05-22T12:48:38+00:00
- Post Title: Re: Dragon Age 2 (PC)

Hi guys,
thanks a lot for your great work. It works really fine.

But (there is always a but... ;o)) now I've got the export problem. I didn't find a solution to export the mesh (i.e. as fbx) and to convert the exported file. The model doesn't appear in the game (DA2). So my question to the experts: exists a solution for direct  model exporting to a DA2 msh file? 

So long 
anzolino
## Post #71
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-05-22T13:09:13+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from anzolino
>
> I didn't find a solution to export the mesh (i.e. as fbx) and to convert the exported file. The model doesn't appear in the game (DA2). So my question to the experts: exists a solution for direct  model exporting to a DA2 msh file?

The DA2 tools should allow you to convert from an OBJ, DAE, or FBX file to a Mesh. There's also the old IOTools for Blender that contains a .msh exporter, but I don't believe it's been updated for DA2.

I believe that PyGFF also has tools for converting and packaging files. I've only used it to import objects, but it may be able to get objects back in the game. [http://social.bioware.com/project/1936/](http://social.bioware.com/project/1936/)
## Post #72
- Username: anzolino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:34 pm
- Post datetime: 2011-05-22T13:55:29+00:00
- Post Title: Re: Dragon Age 2 (PC)

Yes, the IO Tools does'nt work. 
I've tried the DA2 Tools to convert the FBX to MSH and also to convert to XML for compiling with the DAO ResourceBuild processors. I'm also using the PyGFF for attribute changes etc. I will test if PyGFF can convert too. 
Maybe I miss something else.
## Post #73
- Username: anzolino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:34 pm
- Post datetime: 2011-05-23T19:31:02+00:00
- Post Title: Re: Dragon Age 2 (PC)

I've heard from others that the DA2Tools also doesn't work. I didn't found any convert options in pyGFF. So it seems there don't exists a convert solution
## Post #74
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2011-06-08T13:19:18+00:00
- Post Title: Re: Dragon Age 2 (PC)

thanks so much for this importer guys
## Post #75
- Username: trumpdog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 11:28 am
- Post datetime: 2011-06-16T22:32:12+00:00
- Post Title: Re: Dragon Age 2 (PC)

There is one import/export script for lightwave 3d here [http://social.bioware.com/project/2246/](http://social.bioware.com/project/2246/)
I dont know anything about it or the capabilities of the plug in. All i know is that everything done to the model has to be done in Lightwave, for example....you cant do anything in blender and export it to lightwave format or it loses its weighting and some other stuff upon import to lightwave. IMHO lightwave kinda sucks.....Havent had a successful export yet since i dont know how to use it.
## Post #76
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2011-06-21T08:25:45+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from trumpdog
>
> There is one import/export script for lightwave 3d here http://social.bioware.com/project/2246/
I dont know anything about it or the capabilities of the plug in. All i know is that everything done to the model has to be done in Lightwave, for example....you cant do anything in blender and export it to lightwave format or it loses its weighting and some other stuff upon import to lightwave. IMHO lightwave kinda sucks.....Havent had a successful export yet since i dont know how to use it.

from what i've seen, i think it only works with Origins not DA2. unfortunately.
## Post #77
- Username: anzolino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:34 pm
- Post datetime: 2011-06-22T08:07:52+00:00
- Post Title: Re: Dragon Age 2 (PC)

The lightwave plugin works for DA2. But this is the only one, no blender or max export is possible.
## Post #78
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-06-22T13:44:16+00:00
- Post Title: Re: Dragon Age 2 (PC)

well, i extracted the models, but ive got like 15000 textures in the folder, anyone figured how to choose the right ones yet?
## Post #79
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2011-06-23T09:14:33+00:00
- Post Title: Re: Dragon Age 2 (PC)

Ok. I wanted to share with u guys what i've been trying to do for a few days now, and maybe someone can use my experience to import a model into DA2 correctly. 
Thanks to chroxx and figuresculptor and their awesome script i imported a DA2 model and its bones into Blender successfully. After getting the model to look the way i wanted it to i exported the mesh and the bones as an FBX file so i can convert it using  tazpn's DA2 Command Line Tools [http://social.bioware.com/project/4253/](http://social.bioware.com/project/4253/). By converting the FBX i got two XML files, an MMH and a MSH one. So far so good.
Viewing those two XMLs i noticed that all the information transferred perfectly except for the number of bones that the model actually uses and which bones it uses. The info is there but its just not correct (says that the model is using far more bones than it actually does). Anyways, per tazpn's instructions i used the GraphicsProcessorMMH.exe and the GraphicsProcessorMSH.exe from the Origins toolset to compile those two XMLs. What i got was an MMH, PHY and a MSH file. Everything still seemed fine.
Using tazpn's View Scene command tool i inspected the .mmh and the .msh. And this is where the problems begin. 
During the compiling some info got lost, specifically the bone info, and the actual mesh got all messed up and deformed. I'm guessing this happens cause of the way that the XMLs are compiled and compressed into .mmh, .phy and .msh files. and a different way that the Origins GraphicsProcessor handles those files from the DA2 GraphicsProcessor. After some manual editing of the files in the PyGff editor (correcting filepaths and adding lost info) i did get the model to show ingame all pretty and textured, although deformed and all over the place lol. 
So the main order of business now would be to make sure that the bone info transfers correctly from Blender and that it doesn't get lost during the converting and the compiling. And of course there's that matter of the mesh getting all messed up. But we are a lot closer than we were.
And hey, maybe Bioware will feel sorry for us and release the DA2 toolset.
## Post #80
- Username: codo85
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 19, 2011 10:10 pm
- Post datetime: 2011-06-25T16:24:13+00:00
- Post Title: Re: Dragon Age 2 (PC)

Hi again!

Is now possible to import, edit and export DA2 models?
I was trying the Lighwave plugin, and I get the .mmh.xml and the .msh.xml files. But if I drag and drop them over GraphicsProcessorMMH.exe and GraphicsProcessorMSH.exe nothing happens.

This is what I do:
- extract the original .mmh, .msh and .phy files;
- load the .msh file in Lighwave;
- edit;
- launch the plugin command to export it as html.

So I get the two .xml files, but I can't get any further. Any help?
## Post #81
- Username: anzolino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:34 pm
- Post datetime: 2011-06-25T17:21:00+00:00
- Post Title: Re: Dragon Age 2 (PC)

@ codo85: 
You can ask at [thenexusforums.com: Dragon Age 2 Modding](http://www.thenexusforums.com/index.php?c=366,369), there are people using lightwave. 

@ OriginOfWaves:
Thanks for your description but I made this experiences 1 month ago and so far there are no solutions. So, we are not closer and there is no relief and no hope for a toolset
## Post #82
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2011-06-27T10:02:10+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from codo85
>
> Hi again!

Is now possible to import, edit and export DA2 models?
I was trying the Lighwave plugin, and I get the .mmh.xml and the .msh.xml files. But if I drag and drop them over GraphicsProcessorMMH.exe and GraphicsProcessorMSH.exe nothing happens.

This is what I do:
- extract the original .mmh, .msh and .phy files;
- load the .msh file in Lighwave;
- edit;
- launch the plugin command to export it as html.

So I get the two .xml files, but I can't get any further. Any help?

GraphicsProcessorMMH.exe and GraphicsProcessorMSH.exe work as command line tools. so u need a command line.
the easiest way is to copy the .xml files to their location and then use this command lines:
GraphicsProcessorMMH.exe example.mmh.xml
GraphicsProcessorMSH.exe -platform pc mmdtogff example.msh.xml
just replace example with the names of your files.

@anzolino:
that's sad to hear. but we got to be optimistic about it.


OK. BIG NEWS GUYS. A SUCCESSFUL EXPORT, EDIT AND IMPORT BACK INTO THE GAME WITH THE LIGHTWAVE PLUGIN.
U CAN FIND THE DETAILS HERE [http://social.bioware.com/forum/1/topic ... /7371609/1](http://social.bioware.com/forum/1/topic/307/index/7371609/1).
THANKS TO tmp7704 for his Lightwave plugin AND ishmaeltheforsaken FOR HER WORK.
## Post #83
- Username: J4N3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 05, 2011 6:45 am
- Post datetime: 2011-08-05T17:15:15+00:00
- Post Title: Re: Dragon Age 2 (PC)

all this has helped me to extract the files but I am working with 3DS Max and I was wondering if I missed an updated import script or something. do i understand it correctly that importing the bones and all into Max still doesn't work?
## Post #84
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-05T22:12:42+00:00
- Post Title: Re: Dragon Age 2 (PC)

I take a view of all this abouth mod Dragon Age II and its very good (i expert in Moding Mu Online and Ran Online thinks), the real trouble its the important information and skill to do this its missing in thousand and thousands of trash posts, the one i rescue its the programs necesary to mod:

Insanity's ReadMe Generator
pyGFF
Lightwave 10
ERFv3 Packer

But another think i found its nothing news to inject new armors models in the game, i see something boy (ishmaeltheforsaken) are deleted something vertexs from original armors and edited the texture files but nothing abouth exported sucefully a new complete diferent item inside of the game, maybe i not have luck and need search more, but this its all i found.
If you can Provide a full guide abouth how extract, edit and inject armor inside of the game maybe i can put armors like this inside of the game:
## Post #85
- Username: tinnycan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 25, 2011 7:33 pm
- Post datetime: 2011-08-25T15:37:46+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Rimbros
>
> I take a view of all this abouth mod Dragon Age II and its very good (i expert in Moding Mu Online and Ran Online thinks), the real trouble its the important information and skill to do this its missing in thousand and thousands of trash posts, the one i rescue its the programs necesary to mod:

Insanity's ReadMe Generator
pyGFF
Lightwave 10
ERFv3 Packer

But another think i found its nothing news to inject new armors models in the game, i see something boy (ishmaeltheforsaken) are deleted something vertexs from original armors and edited the texture files but nothing abouth exported sucefully a new complete diferent item inside of the game, maybe i not have luck and need search more, but this its all i found.
If you can Provide a full guide abouth how extract, edit and inject armor inside of the game maybe i can put armors like this inside of the game:

I would wait, currently it is very difficult to implement new meshes in the game. As far as I can tell, you can only modify existing meshes. If you import, everything goes to hell and doesn't work. I'd wait until better tools are released although all signs point to no official support, as they encrytped their new DLC.
## Post #86
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-26T19:13:21+00:00
- Post Title: Re: Dragon Age 2 (PC)

how the hell do you find the right textures?
there are thousands
## Post #87
- Username: AnotherChris
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 22, 2012 1:18 am
- Post datetime: 2012-01-22T00:44:07+00:00
- Post Title: Re: Dragon Age 2 (PC)

Being new, I hate to gravedig a thread but it seemed better than starting a new one. I have a question that I'm very much hoping someone can help with. I'm using the LW plugin (with LW 9.0) and I'm having trouble getting the textures applied properly. I found them no problem, but can't get them on the models. Eventually I'm planning to retexture some things, but first I need to solve my major deficiency with getting them on. I'd appreciate any pointers anyone can offer. Thanks!

Edit: Stupid user is stupid. Problem solved.
## Post #88
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-05-03T22:22:42+00:00
- Post Title: Re: Dragon Age 2 (PC)

So sorry to bring up an old thread but is there a way to import a DA2 model in blender 2.49b with armature intact?

Edit ... sorry I meant the script here

> Reply from Szkaradek123
>
> Update for Blender249 importer:
- add uv-mapping for hair and beards.

The UVs on the hair mesh work but the armature gets "blown up" and errors.
## Post #89
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-05-07T22:35:01+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from artworkplay
>
> So sorry to bring up an old thread but is there a way to import a DA2 model in blender 2.49b with armature intact?

Edit ... sorry I meant the script here
Szkaradek123 wrote:Update for Blender249 importer:
- add uv-mapping for hair and beards.

The UVs on the hair mesh work but the armature gets "blown up" and errors.

Vertex groups are numeric while armature has named groups.
There has to be a working blender version somewhere?
## Post #90
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-06-28T09:27:03+00:00
- Post Title: Re: Dragon Age 2 (PC)

I too am interested to know if there has been any progress on this
## Post #91
- Username: Demon20
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 08, 2012 3:16 pm
- Post datetime: 2012-07-30T03:28:22+00:00
- Post Title: Re: Dragon Age 2 (PC)

Hi

I work with XNA Lara. I usually work with models I download from the internet.

Unfortunately, there is still little models that I like and need.

I use Blender 249 and 249.2.

I've downloaded the "import-dragon-age-2-2011-03-26" script that should import mhh and msh files, but I encounter many problems with it.

I cannot create a proper file for XNA Lara. For example: I wanted to import the Templar set but its bones look different than the ones in the model. After the import to XNA Lara I can only turn the set around because of the bones mismatching the model.

The other problem I try to tackle is the error with statues. After the import of the Andrasta statue it does not have the UV and I'm getting the error. I have the texture but it lacks the UV. Can you tell me how to make the UV using a proper texture?

I'm doing it for the first time and I don't know how to do it. Maybe one of you will help?

Do you know how to process the Mor file to extract textures, models, bones, etc.? Other way they cannot be imported with the Blender script.

I worked with it for over a week. Please help.

[More information](http://social.bioware.com/forum/1/topic/307/index/13100950)
## Post #92
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-07-30T06:47:16+00:00
- Post Title: Re: Dragon Age 2 (PC)

what are you doing to extract the models?
## Post #93
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2012-07-30T12:46:17+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Demon20
>
> Hi

I work with XNA Lara. I usually work with models I download from the internet.

Unfortunately, there is still little models that I like and need.

I use Blender 249 and 249.2.

There's a script in this thread that I wrote for 2.5+. It's not perfect - it doesn't handle some of the texture map settings correctly - but it does get the mesh and bones right. You might want to try using it. You can save the file from Blender 2.63a and will be able to open it in 2.49 to continue your work. Can't say I get the resistance to move off of 2.49, but if it's where you're comfortable working, that should get you there.
## Post #94
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-07-30T13:06:14+00:00
- Post Title: Re: Dragon Age 2 (PC)

is there a 3ds max script? for which version?
## Post #95
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2012-07-30T13:08:22+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Devilot
>
> is there a 3ds max script? for which version?

I believe Chrrox's MaxScript is on the first page or two of this thread. I don't know what version it's for, though.
## Post #96
- Username: Demon20
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 08, 2012 3:16 pm
- Post datetime: 2012-07-30T15:22:32+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Devilot
>
> what are you doing to extract the models?
[http://social.bioware.com/project/1936/](http://social.bioware.com/project/1936/)

I use this program.

> Reply from figuresculptor
>
> Demon20 wrote:Hi

I work with XNA Lara. I usually work with models I download from the internet.

Unfortunately, there is still little models that I like and need.

I use Blender 249 and 249.2.

There's a script in this thread that I wrote for 2.5+. It's not perfect - it doesn't handle some of the texture map settings correctly - but it does get the mesh and bones right. You might want to try using it. You can save the file from Blender 2.63a and will be able to open it in 2.49 to continue your work. Can't say I get the resistance to move off of 2.49, but if it's where you're comfortable working, that should get you there.

Which version of the script I use?

I have blender 2.63. I opened the file import-dragon-age-2-2011-03-26

and pops up an error.
## Post #97
- Username: maymay1588
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 01, 2012 8:21 pm
- Post datetime: 2012-08-07T21:43:07+00:00
- Post Title: Re: Dragon Age 2 (PC)

> Reply from Demon20
>
> Devilot wrote:what are you doing to extract the models?
http://social.bioware.com/project/1936/

I use this program.
figuresculptor wrote:Demon20 wrote:Hi

I work with XNA Lara. I usually work with models I download from the internet.

Unfortunately, there is still little models that I like and need.

I use Blender 249 and 249.2.

There's a script in this thread that I wrote for 2.5+. It's not perfect - it doesn't handle some of the texture map settings correctly - but it does get the mesh and bones right. You might want to try using it. You can save the file from Blender 2.63a and will be able to open it in 2.49 to continue your work. Can't say I get the resistance to move off of 2.49, but if it's where you're comfortable working, that should get you there.

Which version of the script I use?

I have blender 2.63. I opened the file import-dragon-age-2-2011-03-26

and pops up an error.

My advice is to just download and install Blender 2.49 beta, it is the only version so far I managed to get it to work on. Also, thanks for all the hard work on the scripts; everything is working so far, but tazpn's command tool is refusing to work for me after combing through all the forums on it and convert the .xml files to .msh and .mmh. Has anyone found a successful tutorial on how to use it? I keep getting a fail to open error.

Edit: Nevermind, figured that out. Now onto attempting to get a custom hair into DA2 without it crashing on me when I move to it on the slider.
## Post #98
- Username: karmalade
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 12, 2012 12:24 pm
- Post datetime: 2012-08-13T02:22:01+00:00
- Post Title: Re: Dragon Age 2 (PC)

More necromancy incoming...

I've been trying to get Chroxx' script to work for gmax, but every time I try to import a DA2 model, it pops up with this error:


Can anyone help this noob get the script fixed? Thanks!

EDIT: Just in case a future noob looking to modify DA2 models in gmax finds this by googling as I did...

Chroxx' script does not work in gmax. My *guess* is that the hexasint function(?) was introduced into max after gmax was discontinued. (Maybe someone more knowledgeable than I am can confirm or deny my theory.) I had to use Tazpn's DA2Tools to convert the model into an OBJ and install a plugin into gmax that allowed me to import OBJ resources.
## Post #99
- Username: blackadder
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 13, 2012 5:06 pm
- Post datetime: 2012-08-28T03:35:55+00:00
- Post Title: Re: Dragon Age 2 (PC)

Is anyone still working on the blender 249 scripts ? Szkaradek123 did a fantastic job, but it's too bad we can't get one that gets both the UV for hair and correct armatures... I wish I could do it.
## Post #100
- Username: Demon20
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 08, 2012 3:16 pm
- Post datetime: 2012-09-01T18:58:57+00:00
- Post Title: Re: Dragon Age 2 (PC)

Can you explain for me how to add bones to a model?

To match them. Because I have bones but they don't fit, and I can only turn the model around. I can't move its arms, legs, nor head.

[http://www.speedyshare.com/u9WYZ/czarownik2222.rar](http://www.speedyshare.com/u9WYZ/czarownik2222.rar)

My model.
## Post #101
- Username: rhaehf2004
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 18, 2011 7:02 pm
- Post datetime: 2012-11-03T08:29:32+00:00
- Post Title: Re: Dragon Age 2 (PC)

How to import 3ds max

Except without the blender?
## Post #102
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2014-09-28T11:18:01+00:00
- Post Title: Re: Dragon Age 2 (PC)

Sorry for the extreme necro, but has anyone found a currently workable way to import DA2 meshes into 3DS Max without the .msh files throwing the dreaded Vertex Declarator is in unsupported format error?

I don't use Blender anymore (I used to bake shadows with it though, like 3 years ago), but apparently, there's a way to import the models in Blender without the error? Am I understanding this correctly?

Sorry, I'm a noob with keeping up with all these programs.

[EDIT] Ohhhh....Okay, I just loaded up Chrrox's script into 3DS Max, instead of using that Nexus Mods one, and I think my problem is that I was busy trying to load really sucky .msh files. It works. The meshes are just uber tiny, with no textures.   

It's progress though!
## Post #103
- Username: Zapal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 02, 2015 4:25 am
- Post datetime: 2015-10-05T08:58:17+00:00
- Post Title: Re: Dragon Age 2 (PC)

friends, I'm willing to pay some money to the guy who will finalize Chrrox's script for 3DS Max to import animations. Very need!
