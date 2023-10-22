## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-13T22:10:44+00:00
- Post Title: King of Route 66 .MDL files

Hey there,
I hope this is a rather quick one since .mdl seens to be a common format. I tried with half life mdl converter but it replied an error. so i was hoping that there is maybe a different converter that you guys are aware of. I attached a couple .mdl files. I kindly ask anyone to give it a quick try and hopefully get a nice result 
Regards

P.S.:
I found a code to unlock a debug menu that lets you play some funny test-animations   
[https://www.youtube.com/watch?v=LspLQaXDnrc&t=11s](https://www.youtube.com/watch?v=LspLQaXDnrc&t=11s)
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-14T11:10:32+00:00
- Post Title: King of Route 66 .MDL files

Sorry.....this time WITH THE ACTUAL FILES in attatchment :-p


 ARIZONA_ARI_BODY.zip
Arizona Queen Body (202.72 KiB) Downloaded 41 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-14T15:05:54+00:00
- Post Title: King of Route 66 .MDL files

> Reply from Henchman800 ↑Mon Oct 14, 2019 6:10 am at Mon Oct 14, 2019 6:10 am
>
> 
I hope this is a rather quick one since .mdl seens to be a common format.
I'm afraid mdl is not A format. It's just the abbr of "model" and it seems that a lot of devs prefer to use that extension.
Also this format doesn't seem to be easy. Indices in the file don't fit in with the vertices. Generated implicit tristrip indices seem to do the trick though with some wrong faces.



implicitStrips.jpg (31.17 KiB) Viewed 378 times



Noesis code for testing:

```
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("ARIZONA_ARI_BODY.mdl", ".mdl")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def noepyCheckType(data):
	if len(data) < 0x80:
		return 0
	bs = NoeBitStream(data)
	Magic = bs.readInt()
	if Magic != 0x20:
		return 0
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	bs.seek(0x2B90, NOESEEK_ABS)
	meshCount = 8
	vCntList = []
	for i in range(0, meshCount):
		vCntList.append( bs.readInt() )
		bs.seek(0x1C, NOESEEK_REL)
	bs.seek(0x159F0, NOESEEK_ABS)
	meshes = []
	for i in range(0, meshCount):
		Vcount = vCntList[i]
		Positions = []
		for j in range(0, Vcount):
			Positions.append(NoeVec3.fromBytes(bs.readBytes(12)))
			bs.seek(4, NOESEEK_REL)
		i1 = 0
		i2 = 0
		i3 = 0
		idx = 0
		PolygonIndex = []
		while i1 + 2 < Vcount:
			i3 = i2 % 2
			PolygonIndex.append( idx + i3 )
			PolygonIndex.append( idx + 1 - i3 )
			PolygonIndex.append( idx + 2 )
			i1 += 1
			i2 += 1
			idx += 1
		mesh = NoeMesh(PolygonIndex, Positions, 'mesh%d'%i)
		meshes.append(mesh)
	mdl = NoeModel(meshes)
	mdlList.append(mdl)
	
	return 1

```
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-14T17:33:16+00:00
- Post Title: King of Route 66 .MDL files

Wow! Thanks for the fast reply. Hmmm it seems like you are right and we are facing something copletely individual here.
Did you have the other files aswell or was this just the comeout of the body file i attacheted?
Thx for the noesis test script!

Edit: I tested a little and only her body seems to work with that script

Here are all her .mdl files:
[https://cdn.discordapp.com/attachments/ ... _Queen.zip](https://cdn.discordapp.com/attachments/371763268848582656/633358261344796723/Arizona_Queen.zip)


I also tried to clean up that mesh a little
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-15T04:40:32+00:00
- Post Title: King of Route 66 .MDL files

> Reply from Henchman800 ↑Tue Oct 15, 2019 1:33 am at Tue Oct 15, 2019 1:33 am
>
> Here are all her .mdl files
The byte-flags following the position data block do not match with the situations whether a face should be discarded either. So looks like you have to clean up the meshes manually. 



face.jpg (16.5 KiB) Viewed 360 times



But before importing the files, better unpack them first. Here's the QuickBMS script to unpack the mdl container:

```
do
	math i + 1
	get Offset[i] long
while Offset[i] != 0
get Offset[i] asize
math Cnt = i
get ArcName basename
for i = 0 < Cnt
	math i + 1
	math Size = Offset[i]
	math i - 1
	math Size - Offset[i]
	goto Offset[i]
	getdstring Ext 4
	if Ext == "P2IG"
		goto 0xC 0 SEEK_CUR
		getdstring TextureName 8
		string Name p "%s/%s%d.%s" ArcName TextureName i Ext
	else
		string Name p "%s/%s.%s" ArcName ArcName Ext
	endif
	log Name Offset[i] Size
next i

```

Don't know what you can do with these "P2IG" files since the meshes don't have UVs either.  

Here's the Noesis script compatible with all unpacked  *.TMB files.

```
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("King of Route 66", ".tmb")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def noepyCheckType(data):
	if len(data) < 0x80:
		return 0
	bs = NoeBitStream(data)
	Magic = bs.readInt()
	if Magic != 0x20424D54: # "TMB "
		return 0
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	bs.seek(0x10, NOESEEK_ABS)
	mtlCnt = bs.readInt()
	mtlOffset = bs.readInt()
	unkCnt = bs.readInt()
	unkOffset = bs.readInt()
	boneCnt = bs.readInt()
	boneOffset = bs.readInt()
	unknown = bs.readInt()
	
	entryOffset = bs.readInt()
	meshCount = bs.readInt()
	structedVertOffset = bs.readInt()
	structedVCnt = bs.readInt()
	PosOffset = bs.readInt()
	VSize = bs.readInt()
	FlagOffset = bs.readInt()
	FlagSize = bs.readInt()
	NormOffset = bs.readInt()
	NormSize = bs.readInt()
	IdxOffset = bs.readInt()
	IdxSize = bs.readInt()
	
	bs.seek(entryOffset*0x10, NOESEEK_ABS)
	vCntList = []
	noesis.logPopup()
	for i in range(0, meshCount):
		vCntList.append( bs.readInt() )
		bs.seek(0x1C, NOESEEK_REL)
	PosOffset *= 0x10
	bs.seek(FlagOffset*0x10, NOESEEK_ABS)
	flag = bs.readBytes(FlagSize)
	NormOffset *= 0x10
	meshes = []
	for i in range(0, meshCount):
		Vcount = vCntList[i]
		Positions = []
		bs.seek(PosOffset, NOESEEK_ABS)
		for j in range(0, Vcount):
			Positions.append(NoeVec3.fromBytes(bs.readBytes(12)))
			bs.seek(4, NOESEEK_REL)
		PosOffset = bs.tell()
		Normals = []
		bs.seek(NormOffset, NOESEEK_ABS)
		for j in range(0, Vcount):
			Normals.append(NoeVec3.fromBytes(bs.readBytes(12)))
			bs.seek(4, NOESEEK_REL)
		NormOffset = bs.tell()
		i1 = 0
		i2 = 0
		i3 = 0
		PolygonIndex = []
		while i1 + 2 < Vcount:
			i3 = i2 % 2
			PolygonIndex.append( i1 + i3 )
			PolygonIndex.append( i1 + 1 - i3 )
			PolygonIndex.append( i1 + 2 )
			i1 += 1
			i2 += 1
		mesh = NoeMesh(PolygonIndex, Positions, 'mesh%d'%i)
		mesh.setNormals(Normals)
		meshes.append(mesh)
	mdl = NoeModel(meshes)
	mdlList.append(mdl)
	
	return 1

```
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-16T23:58:50+00:00
- Post Title: King of Route 66 .MDL files

Thank you man!
Ill check this Scripts out in the Weekend. Im pretty busy right now

EDIT:
Ok...I gave it a try, but the quickbms script wouldnt work for me :-/

I get this warning. When i checked, no tmb files were exported. Do I use a too old version of QuickBMS? I got 0.5.16c

I attached a simple model:


 PROPERTY_pizza.zip
(10.15 KiB) Downloaded 17 times


Its a price you can win ingame so it should be just a stack of pizza.....maybe a simpler model makes researching easier
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-02-22T11:08:13+00:00
- Post Title: King of Route 66 .MDL files

OK,
so i looked into this a bit again.

general info:
the game is a co-production between sega am2 and tose
originally a naomi2 arcade game ported to ps2 and added a bunch more stuff
naomi mod tools that work for 18 wheelers american pro-trucker dreamcast version dont work for this game

models:
there seems to be 2 types of .tmb files:
-regular .tmb
-.tmb files extracted from .mdl containers

extracted .tmb files can be extracted with the above noesis script.
here is ironbulls trailer with the .mdl and extracted .tmb file:

DOWNLOAD FILES:
[https://cdn.discordapp.com/attachments/ ... _ibtrl.zip](https://cdn.discordapp.com/attachments/553220665692651542/945632757403516938/PROPERTY_CAR_ibtrl.zip)

however the truck for ironbull is in a different folder as a single .tmb file and cant be opened with the noesis script.
here are 2 files for what i assume are the cockpit and outside shell of the truck. it also includes a different trailer file.


 ironbull_truck.zip
.tmb files for iron bulls truck (66.39 KiB) Downloaded 15 times



> Reply from Bigchillghost ↑Tue Oct 15, 2019 12:40 pm at Tue Oct 15, 2019 12:40 pm
>
> 
But before importing the files, better unpack them first. Here's the QuickBMS script to unpack the mdl container:
Code: Select allset i long -1
do
	math i + 1
	get Offset[i] long
while Offset[i] != 0
get Offset[i] asize
math Cnt = i
get ArcName basename
for i = 0 < Cnt
	math i + 1
	math Size = Offset[i]
	math i - 1
	math Size - Offset[i]
	goto Offset[i]
	getdstring Ext 4
	if Ext == "P2IG"
		goto 0xC 0 SEEK_CUR
		getdstring TextureName 8
		string Name p "%s/%s%d.%s" ArcName TextureName i Ext
	else
		string Name p "%s/%s.%s" ArcName ArcName Ext
	endif
	log Name Offset[i] Size
next i

Don't know what you can do with these "P2IG" files since the meshes don't have UVs either.  

Here's the Noesis script compatible with all unpacked  *.TMB files.
Code: Select allimport rapi
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("King of Route 66", ".tmb")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def noepyCheckType(data):
	if len(data) < 0x80:
		return 0
	bs = NoeBitStream(data)
	Magic = bs.readInt()
	if Magic != 0x20424D54: # "TMB "
		return 0
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	bs = NoeBitStream(data)
	bs.seek(0x10, NOESEEK_ABS)
	mtlCnt = bs.readInt()
	mtlOffset = bs.readInt()
	unkCnt = bs.readInt()
	unkOffset = bs.readInt()
	boneCnt = bs.readInt()
	boneOffset = bs.readInt()
	unknown = bs.readInt()
	
	entryOffset = bs.readInt()
	meshCount = bs.readInt()
	structedVertOffset = bs.readInt()
	structedVCnt = bs.readInt()
	PosOffset = bs.readInt()
	VSize = bs.readInt()
	FlagOffset = bs.readInt()
	FlagSize = bs.readInt()
	NormOffset = bs.readInt()
	NormSize = bs.readInt()
	IdxOffset = bs.readInt()
	IdxSize = bs.readInt()
	
	bs.seek(entryOffset*0x10, NOESEEK_ABS)
	vCntList = []
	noesis.logPopup()
	for i in range(0, meshCount):
		vCntList.append( bs.readInt() )
		bs.seek(0x1C, NOESEEK_REL)
	PosOffset *= 0x10
	bs.seek(FlagOffset*0x10, NOESEEK_ABS)
	flag = bs.readBytes(FlagSize)
	NormOffset *= 0x10
	meshes = []
	for i in range(0, meshCount):
		Vcount = vCntList[i]
		Positions = []
		bs.seek(PosOffset, NOESEEK_ABS)
		for j in range(0, Vcount):
			Positions.append(NoeVec3.fromBytes(bs.readBytes(12)))
			bs.seek(4, NOESEEK_REL)
		PosOffset = bs.tell()
		Normals = []
		bs.seek(NormOffset, NOESEEK_ABS)
		for j in range(0, Vcount):
			Normals.append(NoeVec3.fromBytes(bs.readBytes(12)))
			bs.seek(4, NOESEEK_REL)
		NormOffset = bs.tell()
		i1 = 0
		i2 = 0
		i3 = 0
		PolygonIndex = []
		while i1 + 2 < Vcount:
			i3 = i2 % 2
			PolygonIndex.append( i1 + i3 )
			PolygonIndex.append( i1 + 1 - i3 )
			PolygonIndex.append( i1 + 2 )
			i1 += 1
			i2 += 1
		mesh = NoeMesh(PolygonIndex, Positions, 'mesh%d'%i)
		mesh.setNormals(Normals)
		meshes.append(mesh)
	mdl = NoeModel(meshes)
	mdlList.append(mdl)
	
	return 1

And thank you so much @Bigchillghost for making these scripts!
i would love to add more detail to the exported trucks and mod them into snowrunner!
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-03-09T22:56:06+00:00
- Post Title: King of Route 66 .MDL files

I managed to rip a few models via pcsx2 and Ninjaripper.

However they come with messed up uvs and distortion on the z-axis because ps2...

I found Out that .tex Texture files and the ones extracted from .mdl and .bin are all "p21g" Files.

...yeah and .tmb being model files of course
## Post #9
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-12-03T10:52:42+00:00
- Post Title: King of Route 66 .MDL files

This might be the one!

[https://shader.tistory.com/m/37](https://shader.tistory.com/m/37)

Far from Home atm.
I will Check next week when on my PC again.
But Things Look promising.
Enjoy your Weekend yall
## Post #10
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-12-10T05:23:46+00:00
- Post Title: King of Route 66 .MDL files

I gave it a go in 3ds max's maxscript and was able to import the mesh without those spiky faces



```
	3ds max's MaxScript for Importing mdl / tmb from king of route 66 on ps2

	written by mariokart64n
	dec 9 2022
	
	Script written around a dozen file samples uploaded here
	https://forum.xentax.com/viewtopic.php?p=156970#p156970

	notes:
		I was curious about the face drawing since others seemed to have issue with it.
		Looks as if the faces are written after the vertices as an array of bytes.
		when a 0 is read the face is saved, where if theres a 1 then you skip basically.
		The other component to this was to read the mesh table to get the proper submeshes
		out of the vertex buffer.. kind of standard stuff.
		
		Only issue is there isn't much to the mesh table, it links into an object table
		that builds bones which I was unable to resolve. But I was able to get the mesh
		to import correctly so I was happy enough with that.
		
		Script was only tested on the samples of Arizona, so theres a high chance the
		script won't work on anything.
		
		
*/
clearListener()

try(destroyDialog iu_king_of_route_66_mdl)catch(iu_king_of_route_66_mdl)
rollout iu_king_of_route_66_mdl "MDL" (
		
	struct fmtTMB_Entry_0x01 ( -- 96 bytes, material
		/*float[4]*/       	unk115 = #(0.0, 0.0, 0.0, 1.0), -- Diffuse Colour (RGBA)
		/*float[4]*/       	unk116 = #(1.0, 1.0, 1.0, 1.0), -- Ambient Colour (RGBA)
		/*float[4]*/       	unk117 = #(0.0, 0.0, 0.0, 1.0), -- Emissive Colour (RGBA)
		/*float[4]*/       	unk118 = #(1.0, 1.0, 1.0, 0.0), -- Specular Colour (RGBA)
		/*uint32_t*/       	unk119 = 0, -- Specular Power?
		/*uint16_t*/       	unk120 = 0,
		/*uint16_t*/       	unk121 = 0,
		/*uint16_t*/       	unk122 = 0,
		/*uint16_t*/       	unk123 = 0,
		/*uint32_t*/       	unk124 = 0,
		/*uint32_t*/       	unk125 = 0,
		/*uint32_t*/       	unk126 = 0,
		/*uint32_t*/       	unk127 = 0,
		/*uint32_t*/       	unk128 = 0,
		fn read &f = (
			unk115 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			unk116 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			unk117 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			unk118 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			unk119 = readLong f #unsigned
			unk120 = readShort f #unsigned
			unk121 = readShort f #unsigned
			unk122 = readShort f #unsigned
			unk123 = readShort f #unsigned
			unk124 = readLong f #unsigned
			unk125 = readLong f #unsigned
			unk126 = readLong f #unsigned
			unk127 = readLong f #unsigned
			unk128 = readLong f #unsigned
			)
		)
	
	struct fmtTMB_Entry_0x02 ( -- 240 bytes, object?
		
		/*char[32]*/               	name3 = "",
		/*float[4][4]*/           	unk131 = #( -- Transform
										#(1.0, 0.0, 0.0, 0.0), 
										#(0.0, 1.0, 0.0, 0.0), 
										#(0.0, 0.0, 1.0, 0.0), 
										#(0.0, 0.0, 0.0, 1.0)
										),
		/*uint32_t*/               	unk0132 = 0.0,
		/*uint32_t*/               	unk0133 = 0.0,
		/*uint32_t*/               	unk0134 = 0.0,
		/*uint32_t*/               	unk0135 = 0.0,
		/*uint32_t*/               	unk0136 = 0.0,
		/*uint32_t*/               	unk0137 = 0.0,
		/*uint32_t*/               	unk0138 = 0.0,
		/*uint32_t*/               	unk0139 = 0.0,
		/*uint32_t*/               	unk0140 = 0.0,
		/*uint32_t*/               	unk0141 = 0.0,
		/*uint32_t*/               	unk0142 = 0.0,
		/*uint32_t*/               	unk0143 = 0.0,
		/*uint32_t*/               	unk0144 = 0.0,
		/*uint32_t*/               	unk0145 = 0.0,
		/*uint32_t*/               	unk0146 = 0.0,
		/*uint32_t*/               	unk0147 = 0.0,
		/*uint32_t*/               	unk0148 = 0.0,
		/*uint32_t*/               	unk0149 = 0.0,
		/*uint32_t*/               	unk0150 = 0.0,
		/*uint32_t*/               	unk0151 = 0.0,
		/*uint32_t*/               	unk0152 = 0.0,
		/*uint32_t*/               	unk0153 = 0.0,
		/*uint32_t*/               	unk0154 = 0.0,
		/*uint32_t*/               	unk0155 = 0.0,
		/*uint32_t*/               	unk0156 = 0.0,
		/*uint32_t*/               	unk0157 = 0.0,
		/*uint32_t*/               	unk0158 = 0.0,
		/*uint32_t*/               	unk0159 = 0.0,
		/*uint32_t*/               	unk0160 = 0.0,
		/*uint32_t*/               	unk0161 = 0.0,
		/*uint32_t*/               	unk0162 = 0.0,
		/*uint32_t*/               	unk0163 = 0.0,
		/*int32_t*/               	unk0164 = -1,
		/*int32_t*/               	unk0165 = -1, -- -1 parent?
		/*int32_t*/               	unk0166 = -1, -- -1 index?
		/*uint32_t*/               	unk0167 = 0, -- padding probably
		
		fn readFixedString &f len = (
			str = ""
			local p = ftell f + len
			local i = 1
			local b = 1
			for i = 1 to len do (
				b = readByte f #unsigned
				if b > 0 then (
					str += bit.IntAsChar b
					)
				else (
					exit
					)
				)
			fseek f p #seek_set
			str
			),
		
		fn read &f = (
			name3 = readFixedString &f 32
			
			-- matrix?
			unk131 = #(
				#(readFloat f, readFloat f, readFloat f, readFloat f), -- 1 0 0 0
				#(readFloat f, readFloat f, readFloat f, readFloat f), -- 0 1 0 0
				#(readFloat f, readFloat f, readFloat f, readFloat f), -- 0 0 1 0
				#(readFloat f, readFloat f, readFloat f, readFloat f)  -- 0 0 0 1
				)
			
			unk0132 = readFloat f
			unk0133 = readFloat f
			unk0134 = readFloat f
			unk0135 = readFloat f -- 1.0
			
			-- empty
			unk0136 = readFloat f
			unk0137 = readFloat f
			unk0138 = readFloat f
			unk0139 = readFloat f
			unk0140 = readFloat f
			unk0141 = readFloat f
			unk0142 = readFloat f
			unk0143 = readFloat f
			unk0144 = readFloat f
			unk0145 = readFloat f
			unk0146 = readFloat f
			unk0147 = readFloat f
			unk0148 = readFloat f
			unk0149 = readFloat f
			unk0150 = readFloat f
			unk0151 = readFloat f
			
			-- transform?
			unk0152 = readFloat f
			unk0153 = readFloat f
			unk0154 = readFloat f
			unk0155 = readFloat f
			
			unk0156 = readFloat f
			unk0157 = readFloat f
			unk0158 = readFloat f
			unk0159 = readFloat f
			
			unk0160 = readFloat f
			unk0161 = readFloat f
			unk0162 = readFloat f
			unk0163 = readFloat f -- 1.0
			
			unk0164 = readLong f #signed
			unk0165 = readLong f #signed -- -1
			unk0166 = readLong f #signed -- -1
			unk0167 = readLong f #unsigned
			)
		)
	
	struct fmtTMB_Entry_0x03 ( -- 48 bytes, ??
		unk080 = 0,
		unk081 = 0,
		unk082 = 0,
		unk083 = 0.0,
		unk084 = 0.0,
		unk085 = 0.0,
		unk086 = 0.0,
		unk087 = 0.0,
		unk088 = 0,
		unk089 = 0,
		unk090 = 0,
		unk091 = 0,
		fn read &f = (
			unk080 = readLong f #unsigned
			unk081 = readLong f #unsigned
			unk082 = readLong f #unsigned
			unk083 = readFloat f
			unk084 = readFloat f
			unk085 = readFloat f
			unk086 = readFloat f
			unk087 = readFloat f
			unk088 = readLong f #unsigned
			unk089 = readLong f #unsigned
			unk090 = readLong f #unsigned
			unk091 = readLong f #unsigned
			)
		)
	
	struct fmtTMB_Entry_0x04 ( -- 32 bytes, mesh info? verts counts etc
		/*uint32_t*/               	unk0168 = 0,
		/*uint32_t*/               	unk0169 = 0, -- 3
		/*uint32_t*/               	unk0170 = 0,
		/*uint32_t*/               	unk0171 = 0,
		/*uint32_t*/               	unk0172 = 0,
		/*uint32_t*/               	unk0173 = 0,
		/*uint32_t*/               	unk0174 = 0,
		/*uint32_t*/               	unk0175 = 0, -- 0, probably padding
		fn read &f = (
			
			unk0168 = readLong f #unsigned
			unk0169 = readLong f #unsigned -- 3
			
			unk0170 = readLong f #unsigned
			unk0171 = readLong f #unsigned
			unk0172 = readLong f #unsigned
			unk0173 = readLong f #unsigned
			unk0174 = readLong f #unsigned
			unk0175 = readLong f #unsigned
			),
		
		fn repr = (
			format "%\t%\t%\t%\t%\t%\t%\t%\n" \
				unk0168 unk0169 unk0170 unk0171 \
				unk0172 unk0173 unk0174 unk0175
			)
		
		)
	
	struct fmtTMB_Entry_0x05 ( -- 32 bytes, vertex position, normal
		/*
			vertices are in world space, yay no need to transform them
		*/
		/*float[4]*/               	unk0180 = #(0.0, 0.0, 0.0, 1.0), -- Position
		/*float[4]*/               	unk0181 = #(0.0, 0.0, 0.0, 1.0), -- Normal
		fn read &f = (
			unk0180 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			unk0181 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			)
		
		)
	
	struct fmtTMB_Entry_0x06 ( -- 16 bytes, Vertex Positions Again lol
		/*float[4]*/               	unk0191 = #(0.0, 0.0, 0.0, 0.0), -- Position
		fn read &f = (
			unk0191 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			)
		)
	
	--struct fmtTMB_Entry_0x07 (uint8_t b) -- weird boolean table

	struct fmtTMB_Entry_0x08 ( -- 16 bytes, Normals Again
		/*float[4]*/               	unk0192 = #(0.0, 0.0, 0.0, 0.0),
		fn read &f = (
			unk0192 = #(readFloat f, readFloat f, readFloat f, readFloat f)
			)
		)
	
	struct fmtTMB_Entry_0x0B (
		/*uint32_t*/               	type = 0,
		/*uint32_t*/               	unk0200 = #(),
		fn read &f = (
			/*
			need to review more samples,
			
			looks like its an array of ints,
			and it the int is bitmasked with 0x80
			then you start reading a new array to
			stream into..
			
			however theres some ints and floats so
			i had figured there was a type specifier
			but i'm unsure...
			
			i'll have to look at smaller samples to
			quantify the patterns in the stream..
			
			*/
			)
		)
	
	--struct fmtTMB_Entry_0x0C ()
	
	struct fmtTMB_Table3_Entry ( -- 32 bytes
		/*uint32_t*/       	unk0181 = 0, -- vertex size
		/*uint32_t*/       	unk0182 = 0, -- 3
		/*uint32_t*/       	unk0183 = 0, -- index?
		/*uint32_t*/       	unk0184 = 0, -- 1.) vertex position
		/*uint32_t*/       	unk0185 = 0, -- 2.) ? position
		/*uint32_t*/       	unk0186 = 0, -- 3.) normal position
		/*uint32_t*/       	unk0187 = 0, -- 4.) ? position
		/*uint32_t*/       	unk0188 = 0, -- 5.) ? position
		fn read_table3_entry &f = (
			unk0181 = readLong f #unsigned
			unk0182 = readLong f #unsigned
			unk0183 = readLong f #unsigned
			unk0184 = readLong f #unsigned
			unk0185 = readLong f #unsigned
			unk0186 = readLong f #unsigned
			unk0187 = readLong f #unsigned
			unk0188 = readLong f #unsigned
			)
		)
	
	struct fmtTMB_Addr ( -- 8 bytes
		/*uint32_t*/       	addr = 0, -- multiply by 16
		/*uint32_t*/       	count = 0,
		fn read &f = (
			addr = readLong f #unsigned
			count = readLong f #unsigned
			)
		)
	
	struct fmtTMB (
		/*uint32_t*/               	type = 0x20424D54,
		/*uint32_t*/               	unk101 = 0,
		/*float*/                  	unk102 = 0.0,
		/*fmtTMB_Addr[13]*/     	addrs = #(),
		
		/*char[64]*/               	textures = #(),
		/*fmtTMB_Entry_0x01[]*/    	boneArray = #(),
		/*fmtTMB_Entry_0x02[]*/    	objArray = #(),
		/*fmtTMB_Entry_0x03[]*/    	mshArray = #(),
		--0x04
		/*fmtTMB_Entry_0x05[]*/    	vertArray = #(),
		/*fmtTMB_Entry_0x06[]*/    	unk0190Array = #(),
		/*uint8_t[]*/             	flagArray = #(),
		/*fmtTMB_Entry_0x08[]*/    	unk0193Array = #(),
		/*uint16_t[]*/            	unk0195Array = #(),
		fn readFixedString &f len = (
			str = ""
			local p = ftell f + len
			local i = 1
			local b = 1
			for i = 1 to len do (
				b = readByte f #unsigned
				if b > 0 then (
					str += bit.IntAsChar b
					)
				else (
					exit
					)
				)
			fseek f p #seek_set
			str
			),
		
		fn readFaces pos count = (
			
			local Face_array = #()	
			if count > 0 do (
				local face = #(1, 2, 3)
				local counter = 1
				local j = 1
				for j = 1 to flagArray.count do (
					
					face = #(face[2], face[3], counter)
					
					if face[1] > count or face[2] > count or face[3] > count do (
						exit
						)
					
					counter += 1
					
					if flagArray[j + pos] == 0 then (
						if bit.and j 1 then (
							append Face_array [face[1], face[2], face[3]]
							)
						else (
							append Face_array [face[1], face[3], face[2]]
							)
						)
					)
				)
			Face_array
			),
		
		fn read &f = (
			
			-- get start of file
			local pos = ftell f
			
			-- Read header
			type = readLong f #unsigned
			unk101 = readLong f #unsigned
			unk102 = readFloat f
			
			-- Read Block Table
			addrs = #()
			local num_addrs = 13
			addrs[num_addrs] = fmtTMB_Addr()
			
			local i = 1
			local x = 0
			local j = 1
			textures = #()
			boneArray = #()
			objArray = #()
			mshArray = #()
			vertArray = #()
			unk0190Array = #()
			flagArray = #()
			unk0193Array = #()
			unk0195Array = #()
			for i = 1 to num_addrs do (
				
				-- deduct 1, only required for maxscript
				x = i - 1
				
				-- seek to table entry
				fseek f (pos + 12 + (x * 8)) #seek_set
				
				-- Init Array Element
				addrs[i] = fmtTMB_Addr()
				
				-- Read Entry
				addrs[i].read(&f)
				
				-- Skip if address is null
				if addrs[i].addr == 0 do continue
				
				-- Read Block
				fseek f (pos + (addrs[i].addr * 16)) #seek_set
				case x of (
					0x00: ( -- Texture Names
						if addrs[i].count > 0 do (
							textures[addrs[i].count] = ""
							for j = 1 to addrs[i].count do (
								textures[j] = readFixedString f 64
								)
							)
						)
					0x01: ( -- Bones, Probably...
						if addrs[i].count > 0 do (
							boneArray[addrs[i].count] = fmtTMB_Entry_0x01()
							for j = 1 to addrs[i].count do (
								boneArray[j] = fmtTMB_Entry_0x01()
								boneArray[j].read(&f)
								)
							)
						)
					0x02: ( -- Object
						if addrs[i].count > 0 do (
							objArray[addrs[i].count] = fmtTMB_Entry_0x02()
							for j = 1 to addrs[i].count do (
								objArray[j] = fmtTMB_Entry_0x02()
								objArray[j].read(&f)
								)
							)
						)
					0x03: (
						-- need to examine other samples
						)
					0x04: ( -- Mesh Info
						if addrs[i].count > 0 do (
							mshArray[addrs[i].count] = fmtTMB_Entry_0x04()
							for j = 1 to addrs[i].count do (
								mshArray[j] = fmtTMB_Entry_0x04()
								mshArray[j].read(&f)
								--mshArray[j].repr()
								)
							)
						)
					0x05: ( -- Vertex Positions, hm maybe this used for lookup
						if addrs[i].count > 0 do (
							vertArray[addrs[i].count] = fmtTMB_Entry_0x05()
							for j = 1 to addrs[i].count do (
								vertArray[j] = fmtTMB_Entry_0x05()
								vertArray[j].read(&f)
								)	
							)
						
						
						)
					0x06: ( -- Vertices Again
						
						local count = (addrs[i].count / 16) as integer
						if addrs[i].count > 0 do (
							unk0190Array[count] = fmtTMB_Entry_0x06()
							for j = 1 to count do (
								unk0190Array[j] = fmtTMB_Entry_0x06()
								unk0190Array[j].read(&f)
								)
							)
						)
					0x07: ( -- Faces
						
						flagArray = #()
						local count = addrs[i].count
						if count > 0 do (
							flagArray[count] = 0
							for j = 1 to count do (
								flagArray[j] = readbyte f #unsigned
								)
							
							)
						
						)
					0x08: ( -- Normals Again
						local count = (addrs[i].count / 16) as integer
						if addrs[i].count > 0 do (
							unk0193Array[count] = fmtTMB_Entry_0x08()
							for j = 1 to count do (
								unk0193Array[j] = fmtTMB_Entry_0x08()
								unk0193Array[j].read(&f)
								)
							)
						)
					0x09: ( -- texture corrdinates maybe??
						local count = (addrs[i].count / 4) as integer
						if addrs[i].count > 0 do (
							unk0195Array[count] = [0.0, 0.0, 0.0]
							for j = 1 to count do (
								unk0195Array[j] = [readShort f #unsigned, readShort f #unsigned, 0.0] / 1024.0
								)
							)
						)
					0x0A: (
						-- not present in my sample, need to review more samples
						)
					0x0B: ( -- some sort of data stream
						--fmtTMB_Entry_0x0B()
						)
					0x0C: (
						-- need to examine more samples, not alot data is present at this block
						)
					)
				)
			),
		
		fn build clearScene:false mscale:3.937007874015748031496 buildBones:false = (
			
			-- ClearScene
			if clearScene do (delete $*)
			
			
			-- Loop Through object
			local o = undefined
			local t = matrix3 1
			local d = undefined
			local msh = undefined
			local bnsArray = #()
			local vertices = #()
			local tvertices = #()
			local faceArray = #()
			local faceStart = 0
			local j = 1
			local v = 1
			local uvStart = 0
			
			for j = 1 to mshArray.count do (
				-- Mesh
				
				vertices = #()
				faceArray = #()
				
				-- if no vertices, then SKIP
				if mshArray[j].unk0168 == 0 do continue
				
				-- Read Faces
				faceArray = readFaces faceStart mshArray[j].unk0168
				faceStart += (mshArray[j].unk0168 + (mod (16-(mod mshArray[j].unk0168 16)) 16))
				
				
				-- Read Vertices
				vertices = #()
				tvertices = #()
				vertices[mshArray[j].unk0168] = [0.0, 0.0, 0.0]
				tvertices[mshArray[j].unk0168] = [0.0, 0.0, 0.0]
				
				for v = (mshArray[j].unk0171 + 1) to (mshArray[j].unk0171 + mshArray[j].unk0168) do (
					vertices[v - mshArray[j].unk0171] = [unk0190Array[v].unk0191[1], -unk0190Array[v].unk0191[3], unk0190Array[v].unk0191[2]] * mscale
					)
				
				
				for v = 1 to mshArray[j].unk0168 do (
					tvertices[v] = try([unk0195Array[v + uvStart][1], unk0195Array[v + uvStart][2], 0.0])catch([0.0, 0.0, 0.0])
					)
					
					
				uvStart += (((mshArray[j].unk0168 * 4) + (mod (16-(mod (mshArray[j].unk0168 * 4) 16)) 16)) / 4.0) as integer
				
				
				-- Build Mesh
				msh = mesh vertices:vertices faces:faceArray tverts:tvertices
				buildTVFaces msh
				for v = 1 to faceArray.count do (setTVFace msh v faceArray[v])
				
				msh.backfacecull = on
				msh.displayByLayer = false
				msh.wirecolor = random (color 0 0 0) (color 255 255 255)
				for v = 1 to faceArray.count do setFaceSmoothGroup msh v 1
				
				--msh.transform = t
				--append mdls msh
				)
			
			
			
			if buildBones do (
				-- Build Bones
				for o in objArray do (
					
					-- Bone
					d = Dummy name:o.name3 boxSize:[0.25, 0.25, 0.25] transform:(
						matrix3 \
							([o.unk131[1][1], o.unk131[1][2], o.unk131[1][3]] + o.unk131[1][4]) \
							([o.unk131[2][1], o.unk131[2][2], o.unk131[2][3]] + o.unk131[2][4]) \
							([o.unk131[3][1], o.unk131[3][2], o.unk131[3][3]] + o.unk131[3][4]) \
							([o.unk131[4][1], o.unk131[4][2], o.unk131[4][3]] * mscale * o.unk131[4][4])
						)
					d.showLinks = d.showLinksOnly = true
					append bnsArray d
					)
				
				local i = 1
				local par = 1
				local pos = [0.0, 0.0, 0.0]
				for i = 1 to bnsArray.count do (
					
					
					par = objArray[i].unk0166 + 1
					if par > 0 do (
						t = bnsArray[i].transform
						pos = bnsArray[i].position
						while par > 0 do (
							t *= bnsArray[par].transform 
							pos += bnsArray[par].position
							
							
							par = objArray[par].unk0166 + 1
							exit
							)
						bnsArray[i].transform = t
						--bnsArray[i].position = pos
						
						bnsArray[i].parent = bnsArray[objArray[i].unk0166 + 1] 
						)
					
					
					
					)
				)
			

			)
		
		)
	
	struct fmtP2IG (
		/*uint32_t*/       	type = 0x47493250, -- P2IG
		/*uint32_t*/       	unk001 = 0,
		/*uint32_t*/       	unk002 = 0,
		/*uint16_t*/       	unk003 = 0,
		/*uint16_t*/       	unk004 = 0,
		/*char[8]*/       	name = "",
		/*uint32_t*/       	unk005 = 0,
		/*uint32_t*/       	unk006 = 0,
		/*uint16_t*/       	unk007 = 0, -- width
		/*uint16_t*/       	unk008 = 0, -- length
		/*uint32_t*/       	unk009 = 0, -- type 0x13 = 8bit, 0x14 = 4bit?
		/*uint32_t*/       	unk010 = 0,
		/*uint32_t*/       	unk011 = 0,
		/*uint32_t*/       	unk012 = 0,
		/*uint32_t*/       	unk013 = 0,
		/*uint32_t*/       	unk014 = 0,
		/*uint32_t*/       	unk015 = 0,
		/*uint32_t*/       	unk016 = 0, -- pal pos
		/*uint32_t*/       	unk017 = 0, -- pal size
		/*uint32_t*/       	unk018 = 0, -- img pos
		/*uint32_t*/       	unk019 = 0, -- img size
		/*uint32_t*/       	unk020 = 0,
		/*uint32_t*/       	unk021 = 0,
		/*uint32_t*/       	unk022 = 0,
		/*uint32_t*/       	unk023 = 0,
		/*uint32_t*/       	unk024 = 0,
		/*uint32_t*/       	unk025 = 0,
		/*uint32_t*/       	unk026 = 0,
		/*uint32_t*/       	unk027 = 0,
		/*uint32_t*/       	unk028 = 0,
		/*uint32_t*/       	unk029 = 0,
		/*uint32_t*/       	unk030 = 0,
		/*uint32_t*/       	unk031 = 0,
		/*uint8_t[4][]*/   	pal = #(),
		/*uint8_t[]*/    	img = #(),
		
		/*
			ps2 unswizzle code courtesy of TopazTK,
			while I was working on soul calibur 3
			
			https://forum.xentax.com/viewtopic.php?t=22497
		*/
		
		fn BoolSwitch input = (
			if Input == 0 then (
				input+=1
				)
			else if input == 1 do (
				input-=1
				)
			),
		
		fn QImage_IMGD_Parse8 &data &colors width height = (
			local i = 1, x = 1, y = 1, OutputIMG = #(), pixel = 1
			local i = 1, index = 0, remainder = 0, indexes = #()
			
			indexes[data.count] = 0
			for i = 1 to data.count do (
				index = data[i]
				
				remainder = mod index 32
				
				if remainder > 7 and remainder < 16 then (
					indexes[i] = (index + 8)
					)
				else if remainder > 15 and remainder < 24 then (
					indexes[i] = (Index - 8)
					)
				else (
					indexes[i] = index
					)
				)
			
			OutputIMG[width * height] = white
			
			for y = 1 to height do (
				for x = 1 to width do (
					i = indexes[pixel] + 1
					OutputIMG[pixel] = colors[i]
					pixel+=1
					)
				)
			
			OutputIMG
			),
		
		fn QImage_IMGD_Decode8 &pixels &Width =  (
			local PixelList = #()
			
			local TrueX = 0
			local TrueY = 0
			
			local BoolY = 0
			local BoolPixel = 0
			local p = 0, x = 0, y = 0
			
			local TruePixel = 0
			local cp = 0, a = 0
			
			PixelList[pixels.count] = white
			for p = 1 to pixels.count do (PixelList[p] = white)
			
			for p = 0 to (pixels.count - 1) do (
				if p != 0 do (
					if (mod p (Width * 2)) == 0 then (
						case BoolY of (
							0: (
								TrueY += 1
								)
							1: (
								TrueY += 3
								BoolPixel = BoolSwitch(BoolPixel)
								)
							)
						
						TrueX = 0
						BoolY = BoolSwitch(BoolY)
						)
					else if (mod p 32) == 0 do (
						TrueX += 16
						)
					)
				
				x = TrueX
				y = TrueY
				
				TruePixel = mod p 16
				cp = mod (p / 16) 2
				
				if BoolPixel == 1 do (
					cp = BoolSwitch(cp)
					)
				
				case cp of (
					0: (
						x = TrueX + ((mod TruePixel 4) * 4) + (TruePixel / 4)
						)
					1: (
						a = 4
						if (mod TruePixel 4) >= 2 do (
							a = 12
							)
						x = TrueX + (a - ((mod TruePixel 2) * 4)) + (TruePixel / 4)
						)
					)
				
				if mod p 2 == 1 do (
					y = TrueY + 2
					)
				PixelList[(y * Width) + x + 1] = pixels[p + 1]
				)
			PixelList
			),
		
		fn readFixedString &f len = (
			str = ""
			local p = ftell f + len
			local i = 1
			local b = 1
			for i = 1 to len do (
				b = readByte f #unsigned
				if b > 0 then (
					str += bit.IntAsChar b
					)
				else (
					exit
					)
				)
			fseek f p #seek_set
			str
			),
		
		fn read &f = (
			
			type = readLong f #unsigned
			unk001 = readLong f #unsigned
			unk002 = readLong f #unsigned
			unk003 = readShort f #unsigned
			unk004 = readShort f #unsigned
			name = readFixedString &f 8
			unk005 = readLong f #unsigned
			unk006 = readLong f #unsigned
			unk007 = readShort f #unsigned
			unk008 = readShort f #unsigned
			unk009 = readLong f #unsigned
			unk010 = readLong f #unsigned
			unk011 = readLong f #unsigned
			unk012 = readLong f #unsigned
			unk013 = readLong f #unsigned
			unk014 = readLong f #unsigned
			unk015 = readLong f #unsigned
			unk016 = readLong f #unsigned
			unk017 = readLong f #unsigned
			unk018 = readLong f #unsigned
			unk019 = readLong f #unsigned
			unk020 = readLong f #unsigned
			unk021 = readLong f #unsigned
			unk022 = readLong f #unsigned
			unk023 = readLong f #unsigned
			unk024 = readLong f #unsigned
			unk025 = readLong f #unsigned
			unk026 = readLong f #unsigned
			unk027 = readLong f #unsigned
			unk028 = readLong f #unsigned
			unk029 = readLong f #unsigned
			unk030 = readLong f #unsigned
			unk031 = readLong f #unsigned
			
			-- Read Image Data
			local i = 1
			local count = unk017 / 4
			img = #()
			pal = #()
			if count > 0 do (
				fseek f unk016 #seek_set
				pal[count] = color 0 0 0 255
				for i = 1 to count do (
					pal[i] = color (readByte f #unsigned) (readByte f #unsigned) (readByte f #unsigned) (readByte f #unsigned)
					)
				fseek f unk018 #seek_set
				if unk019 > 0 do (
					img[unk019] = 0
					for i = 1 to unk019 do (
						img[i] = readByte f #unsigned
						)
					)
				)
			
			),
		
		fn correctGamma &c gamma:2.2 = (
			local p = color \
				((pow (c.red / 255) gamma) * 255) \
				((pow (c.green / 255) gamma) * 255) \
				((pow (c.blue / 255) gamma) * 255) \
				((pow (c.a / 255) gamma) * 255)
			p
			),
		
		fn build = (
			
			local width = unk007
			local height = unk008
			
			local b = bitmap width height color:white
			
			if width > 0 and img.count > 0 do (
				local p = #()
				local c = #()
				local x = 0
				local y = 0
				local i = 0
				
				
				c = QImage_IMGD_Parse8 img pal width height
				
				c = QImage_IMGD_Decode8 c width
				
				p[width] = color 0 0 0 255
				
				
				for y = 1 to height do (
					
					
					for x = 1 to width do (
						
						
						p[x] = correctGamma c[i+=1]
						)
					setPixels b [0, y - 1] p
					
					)
				
				
				)
			
			
			display b
			
			)
		
		)
	
	struct fmtMDL_Asset (
		/*
			this is just an intermediate between the different assets
		*/
		
		/*uint32_t*/   	type = 0,
		/*fmtTMB*/     	model = undefined,
		/*fmtP2IG*/ 	texture = undefined,
		
		fn read &f &fsize = (
			
			/*
				I include the asset size in the param 'fsize'
				as a precaution since the mdl acts as a file
				container.
			*/
			
			local pos = ftell f -- log current cursor position
			
			type = readLong f #unsigned
			fseek f pos #seek_set -- restore cursor position to start of asset
			
			case type of (
				0x20424D54: ( -- TMB (Model)
					model = fmtTMB()
					model.read(&f)
					model.build()
					)
				0x47493250: ( -- P2IG (Texture)
					texture = fmtP2IG()
					texture.read(&f) -- has paring issue
					--texture.build() -- code from sc3 still needs to be adopted
					)
				default: (
					format "Assest Unsupported {0x%}\n" (bit.IntAsHex(type as integer))
					)
				)
			)
		
		)
		
	struct fmtMDL (
		
		/*uint32_t[]*/         	addrs = #(), -- address table is padded to 16bytes
		/*fmtMDL_Asset[]*/  	asset = #(), -- being ps2 assets are probably padded to 16 as well
		
		fn read &f = (
			
			-- Reset Arrays
			addrs = #()
			asset = #()
			
			-- Get File Size
			local pos = ftell f
			fseek f 0 #seek_end
			local fsize = ftell f
			fseek f pos #seek_set
			
			-- Read Address Table
			local addr = 0
			local eariest_addr = fsize
			while ftell f < eariest_addr do (
				
				-- Read Address
				addr = readLong f #unsigned
				
				-- Exit if addr is 0
				if addr == 0 do exit
				
				-- Log Address
				append addrs addr
				
				-- Log addr if its smaller then last addr
				if addr < eariest_addr do (
					eariest_addr = addr
					)
				
				)
			
			-- Get asset count from number of valid addresses
			local count = addrs.count
			if count > 0 do (
				local i = 1
				
				-- Generate a list of unique address, so calculate blocks sizes
				local index = 0
				local sizes = #(fsize) -- include the full size to start
				for i = 1 to count do (
					-- Search sizes array for the address
					index = findItem sizes addrs[i]
					
					-- Not in sizes array, so append address to it.
					if index == 0 do (
						append sizes addrs[i]
						)
					)
				
				-- Sort sizes Array
				sort sizes
				
				-- Dimension Asset Array
				asset[count] = fmtMDL_Asset()
				
				-- Process Each Asset
				for i = 1 to count do (
					
					-- Search for ordered address in the sizes array
					index = (findItem sizes addrs[i]) + 1 -- index up to the next address
					
					--  Initialize Array Element
					asset[i] = fmtMDL_Asset()
					
					-- Read Asset
					fseek f addrs[i] #seek_set -- set cursor at start of asset
					asset[i].read &f sizes[index] -- sizes[index] specifies the length of the asset
					)
				)
			)
		)
	
	button btn_open "Import"
	checkbox chk_batch "batch"
	checkbox chk_clear "clear scene"
	group "about" (
		label lbl_about "by mariokart64n"
		label lbl_date "Released: Dec 9 2022"
		)
	
	
	fn read file = (
		if file != undefined and file != "" do (
			
			local f = try(fopen file "rb")catch(undefined)
			if f != undefined then (
				
				local pos = ftell f
				
				local filetype = readLong f #unsigned
				fseek f pos #seek_set
				case filetype of (
					0x20424D54: ( -- TMB
						format "TMB File\n"
						tmb = fmtTMB()
						tmb.read(&f)
						with undo off with redraw off tmb.build()
						)
					default: ( -- Try MDL
						format "MDL File\n"
						mdl = fmtMDL()
						with undo off with redraw off mdl.read(&f)
						)
					)
				
				fclose f
				{% raw %}
                ) else (format "Failed to open file {%}\n" file)
                {% endraw %}
			)
		)
	
	
	fn batch folder = (
		if folder != undefined and folder != "" do (
			
			if folder.count > 0 and subString folder folder.count 1 != "\\" do (
				folder += "\\"
				)
			
			local files = getFiles (folder + "*.*")
			local file = ""
			for file in files do (
				
				if matchPattern file pattern:"*.tmb" then (
					read(file)
					)
				else if matchPattern file pattern:"*.mdl" then (
					read(file)
					
					)
				
				)
			)
		)
	
	on btn_open pressed do (
		if chk_clear.checked do (delete $*)
		if chk_batch.checked then (
			batch(getSavePath())
			)
		else (
			read(getOpenFileName caption:"Open A File:" types:"King of Route 66 mdl (*.mdl)|*.mdl;*.tmb|All|*.*|")
			)
		
		)
	
	)

createDialog iu_king_of_route_66_mdl

```

[tmb_imp__by_mariokart64n.zip](https://xentaxbackup.github.io/file/23117_tmb_imp__by_mariokart64n.zip)
## Post #11
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-12-14T18:36:10+00:00
- Post Title: King of Route 66 .MDL files

> Reply from mariokart64n ↑Sat Dec 10, 2022 1:23 pm at Sat Dec 10, 2022 1:23 pm
>
> 
I gave it a go in 3ds max's maxscript and was able to import the mesh without those spiky faces

OMG wow!
i gotta try that...have no 3dsmax though. does it work on any version/trial version?
thank you so much man!

EDIT:

i get this error with any file ive tried so far.
running a trial version of 3dsmax2013

EDIT 2:

> Reply from mariokart64n ↑Sat Dec 10, 2022 1:23 pm at Sat Dec 10, 2022 1:23 pm
>
>
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-12-15T02:16:19+00:00
- Post Title: King of Route 66 .MDL files

I'm running the latest version, 3ds max 2023 so it's possible some things are not compatible with the older version of 3dsmax.

To resolve the booleanClass error, simply alter the return value in the conditional if statement to a boolean:

```

```


change to 

```

```
## Post #13
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-12-15T12:34:22+00:00
- Post Title: King of Route 66 .MDL files

> Reply from mariokart64n ↑Thu Dec 15, 2022 10:16 am at Thu Dec 15, 2022 10:16 am
>
> 
To resolve the booleanClass error, simply alter the return value in the conditional if statement to a boolean:
Code: Select allif bit.and j 1 then (


change to 
Code: Select allif bit.and j 1 > 0 then (

That solved the issue! thanks for the help
Character models load fine now: (3dsmax2013)


but i get this error when im trying to load a truck or other static .tmb files:

heres two of the static files where i got this error:


 IronBull_Truck.zip
Truck & Trailer (44.2 KiB) Downloaded 14 times


EDIT:
the uvs for the top half of the face are alright, while some others on his face or chest go a little nuts:
## Post #14
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-01-02T15:50:54+00:00
- Post Title: King of Route 66 .MDL files

> Reply from Henchman800 ↑Thu Dec 15, 2022 8:34 pm at Thu Dec 15, 2022 8:34 pm
>
> 
the uvs for the top half of the face are alright, while some others on his face or chest go a little nuts:

went back on trying a few more .mdl files and the uv problem appears in every mesh, also in "original"  arizona model.

but i was able to rip all character textures by now:
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-01-03T06:47:46+00:00
- Post Title: King of Route 66 .MDL files

I'm running 3dsmax 2023, and I notice that the UV's work but do become corrupt when I try to edit them. So maybe a bug in 3dsmax2023? but I exported it to Blender and the UV's are fine.
## Post #16
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-01-03T08:45:15+00:00
- Post Title: Re: King of Route 66 .MDL files

> Reply from mariokart64n ↑Tue Jan 03, 2023 2:47 pm at Tue Jan 03, 2023 2:47 pm
>
> 
So maybe a bug in 3dsmax2023? but I exported it to Blender and the UV's are fine.

Ohhh damn!
I need to Upgrade then...
When i exported them and imported them Back into Blender the uvs were messed up...
Imma try it with max2033 then.
Btw...how did U Grab the textures? ^^
I got them through Ninja ripper
## Post #17
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-01-03T16:06:01+00:00
- Post Title: Re: King of Route 66 .MDL files

I exported almost every 3d-character from the game:


> Reply from mariokart64n ↑Tue Jan 03, 2023 2:47 pm at Tue Jan 03, 2023 2:47 pm
>
> 
...and I notice that the UV's work but do become corrupt when I try to edit them. So maybe a bug in 3dsmax2023?

Highway cat and most of the queens dont seem to have the uv problem. however, the other 4 main characters next to highway cat have all heavy messed up uvs.


luna queen, danny edge, and mr. crown are only available as selection screen models and dont seem to import at all. (although i remember it working with the older version of 3ds max but had completely messed up uvs):

their files can be found here:
[https://cdn.discordapp.com/attachments/ ... _KOR66.zip](https://cdn.discordapp.com/attachments/553220665692651542/1059864480793768117/Error_KOR66.zip)

and here is iron bulls model ( one of the main characters with messed up uvs):
[https://cdn.discordapp.com/attachments/ ... n_Bull.zip](https://cdn.discordapp.com/attachments/553220665692651542/1059864921120198726/Iron_Bull.zip)

thank you for all the work you've put into this

EDIT:
nevermind the luna queen etc character selection screen models. i found the 3 models in better quality inside of a prototype of the game...the uvs for these 3 seem alright, though.
## Post #18
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-01-04T03:03:31+00:00
- Post Title: Re: King of Route 66 .MDL files

yeah I used texMod, but it won't work unless the texture is in view, otherwise the game seems to cull the geometry out of view and thus I can't capture the textures with texMod.

any other DX dumper like NinjaRipper I imagine will suffer from the same pitfalls sadly. I know dumping the textures suck but I don't have enough experience with PS2 textures. I revisited it last night and wasn't able to get anywhere with it.

the 3 models do crash the program but I didn't look much further into it being you snatched them from the prototype any hows

I did however port the script into blender, you can multi select MDL's and import all at once. 

```
    3ds max's MaxScript for Importing mdl / tmb from king of route 66 on ps2

    written by mariokart64n
    dec 9 2022
    
    Script written around a dozen file samples uploaded here
    https://forum.xentax.com/viewtopic.php?p=156970#p156970

    notes:
        I was curious about the face drawing since others seemed to have issue with it.
        Looks as if the faces are written after the vertices as an array of bytes.
        when a 0 is read the face is saved, where if theres a 1:you skip basically.
        The other component to this was to read the mesh table to get the proper submeshes
        out of the vertex buffer.. kind of standard stuff.
        
        Only issue is there isn't much to the mesh table, it links into an object table
        that builds bones which I was unable to resolve. But I was able to get the mesh
        to import correctly so I was happy enough with that.
        
        Script was only tested on the samples of Arizona, so theres a high chance the
        script won't work on anything.
        
        
'''

useOpenDialog = True


from pathlib import Path  # Needed for os stuff
import random
import struct  # Needed for Binary Reader
import bpy
import mathutils  # this i'm guessing is a branch of the bpy module specifically for math operations

signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function

class bit:
    def And(integer1, integer2): return (integer1 & integer2)
    def IntAsChar(integer): return chr(int(integer))

class matrix3:
    row1 = [1.0, 0.0, 0.0]
    row2 = [0.0, 1.0, 0.0]
    row3 = [0.0, 0.0, 1.0]
    row4 = [0.0, 0.0, 0.0]

    def __init__(self, rowA=[1.0, 0.0, 0.0], rowB=[0.0, 1.0, 0.0], rowC=[0.0, 0.0, 1.0], rowD=[0.0, 0.0, 0.0]):
        if rowA == 0:
            self.row1 = [0.0, 0.0, 0.0]
            self.row2 = [0.0, 0.0, 0.0]
            self.row3 = [0.0, 0.0, 0.0]

        elif rowA == 1:
            self.row1 = [1.0, 0.0, 0.0]
            self.row2 = [0.0, 1.0, 0.0]
            self.row3 = [0.0, 0.0, 1.0]
            self.row4 = [0.0, 0.0, 0.0]
        else:
            self.row1 = rowA
            self.row2 = rowB
            self.row3 = rowC
            self.row4 = rowD

    def __repr__(self):
        return (
                "matrix3([" + str(self.row1[0]) +
                ", " + str(self.row1[1]) +
                ", " + str(self.row1[2]) +
                "], [" + str(self.row2[0]) +
                ", " + str(self.row2[1]) +
                ", " + str(self.row2[2]) +
                "], [" + str(self.row3[0]) +
                ", " + str(self.row3[1]) +
                ", " + str(self.row3[2]) +
                "], [" + str(self.row4[0]) +
                ", " + str(self.row4[1]) +
                ", " + str(self.row4[2]) + "])"
        )


def findItem(array, value):
    index = -1
    try: index = array.index(value)
    except: pass
    return index


def append(array, value):
    array.append(value)
    return None

class fopen:
    little_endian = True
    file = ""
    mode = 'rb'
    data = bytearray()
    size = 0
    pos = 0
    isGood = False

    def __init__(self, filename=None, mode='rb', isLittleEndian=True):
        if mode == 'rb':
            if filename != None and Path(filename).is_file():
                self.data = open(filename, mode).read()
                self.size = len(self.data)
                self.pos = 0
                self.mode = mode
                self.file = filename
                self.little_endian = isLittleEndian
                self.isGood = True
        else:
            self.file = filename
            self.mode = mode
            self.data = bytearray()
            self.pos = 0
            self.size = 0
            self.little_endian = isLittleEndian
            self.isGood = False

        pass

    # def __del__(self):
    #    self.flush()

    def resize(self, dataSize=0):
        if dataSize > 0:
            self.data = bytearray(dataSize)
        else:
            self.data = bytearray()
        self.pos = 0
        self.size = dataSize
        self.isGood = False
        return None

    def flush(self):
        if self.file != "" and not self.isGood and len(self.data) > 0:
            self.isGood = True
            s = open(self.file, 'w+b')
            s.write(self.data)
            s.close()

    def read_and_unpack(self, unpack, size):
        value = 0
        if self.size > 0 and self.pos + size <= self.size:
            value = struct.unpack_from(unpack, self.data, self.pos)[0]
            self.pos += size
        return value

    def pack_and_write(self, pack, size, value):
        if self.pos + size > self.size:
            self.data.extend(b'\x00' * ((self.pos + size) - self.size))
            self.size = self.pos + size
        try:
            struct.pack_into(pack, self.data, self.pos, value)
        except:
            # print('Pos:\t%i / %i (buf:%i) [val:%i:%i:%s]' % (self.pos, self.size, len(self.data), value, size, pack))
            pass
        self.pos += size
        return None

    def set_pointer(self, offset):
        self.pos = offset
        return None

    def set_endian(self, isLittle=True):
        self.little_endian = isLittle
        return isLittle


def fclose(bitStream=fopen()):
    bitStream.flush()
    bitStream.isGood = False


def fseek(bitStream=fopen(), offset=0, dir=0):
    if dir == 0:
        bitStream.set_pointer(offset)
    elif dir == 1:
        bitStream.set_pointer(bitStream.pos + offset)
    elif dir == 2:
        bitStream.set_pointer(bitStream.pos - offset)
    return None


def ftell(bitStream=fopen()):
    return bitStream.pos


def readByte(bitStream=fopen(), isSigned=0):
    fmt = 'b' if isSigned == 0 else 'B'
    return (bitStream.read_and_unpack(fmt, 1))


def readShort(bitStream=fopen(), isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'h' if isSigned == 0 else 'H'
    return (bitStream.read_and_unpack(fmt, 2))


def readLong(bitStream=fopen(), isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'i' if isSigned == 0 else 'I'
    return (bitStream.read_and_unpack(fmt, 4))

def readFloat(bitStream=fopen()):
    fmt = '>f' if not bitStream.little_endian else '<f'
    return (bitStream.read_and_unpack(fmt, 4))


def mesh_validate(vertices=[], faces=[]):
    # basic face index check
    # blender will crash if the mesh data is bad

    # Check an Array was given
    result = (type(faces).__name__ == "tuple" or type(faces).__name__ == "list")
    if result == True:

        # Check the the array is Not empty
        if len(faces) > 0:

            # check that the face is a vector
            if (type(faces[0]).__name__ == "tuple" or type(faces[0]).__name__ == "list"):

                # Calculate the Max face index from supplied vertices
                face_min = 0
                face_max = len(vertices) - 1

                # Check face indeices
                for face in faces:
                    for side in face:

                        # Check face index is in range
                        if side < face_min and side > face_max:
                            print("MeshValidation: \tFace Index Out of Range:\t[%i / %i]" % (side, face_max))
                            result = False
                            break
            else:
                print("MeshValidation: \tFace In Array is Invalid")
                result = False
        else:
            print("MeshValidation: \tFace Array is Empty")
    else:
        print("MeshValidation: \tArray Invalid")
        result = False
    return result


def mesh(
        vertices=[],
        faces=[],
        materialIDs=[],
        tverts=[],
        normals=[],
        colours=[],
        materials=[],
        mscale=1.0,
        flipAxis=False,
        obj_name="Object",
        lay_name='',
        position=(0.0, 0.0, 0.0)
        ):
    #
    # This function is pretty, ugly
    # imports the mesh into blender
    #
    # Clear Any Object Selections
    # for o in bpy.context.selected_objects: o.select = False
    bpy.context.view_layer.objects.active = None

    # Get Collection (Layers)
    if lay_name != '':
        # make collection
        layer = bpy.data.collections.get(lay_name)
        if layer == None:
            layer = bpy.data.collections.new(lay_name)
            bpy.context.scene.collection.children.link(layer)
    else:
        if len(bpy.data.collections) == 0:
            layer = bpy.data.collections.new("Collection")
            bpy.context.scene.collection.children.link(layer)
        else:
            try:
                layer = bpy.data.collections[bpy.context.view_layer.active_layer_collection.name]
            except:
                layer = bpy.data.collections[0]

    # make mesh
    msh = bpy.data.meshes.new('Mesh')

    # msh.name = msh.name.replace(".", "_")

    # Apply vertex scaling
    # mscale *= bpy.context.scene.unit_settings.scale_length
    vertArray = []
    if len(vertices) > 0:
        vertArray = [[float] * 3] * len(vertices)
        if flipAxis:
            for v in range(0, len(vertices)):
                vertArray[v] = (
                    vertices[v][0] * mscale,
                    -vertices[v][2] * mscale,
                    vertices[v][1] * mscale
                )
        else:
            for v in range(0, len(vertices)):
                vertArray[v] = (
                    vertices[v][0] * mscale,
                    vertices[v][1] * mscale,
                    vertices[v][2] * mscale
                )

    # assign data from arrays
    if not mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None

    msh.from_pydata(vertArray, [], faces)

    # set surface to smooth
    msh.polygons.foreach_set("use_smooth", [True] * len(msh.polygons))

    # Set Normals
    if len(faces) > 0:
        if len(normals) > 0:
            msh.use_auto_smooth = True
            if len(normals) == (len(faces) * 3):
                msh.normals_split_custom_set(normals)
            else:
                normArray = [[float] * 3] * (len(faces) * 3)
                if flipAxis:
                    for i in range(0, len(faces)):
                        for v in range(0, 3):
                            normArray[(i * 3) + v] = (
                                [normals[faces[i][v]][0],
                                 -normals[faces[i][v]][2],
                                 normals[faces[i][v]][1]]
                            )
                else:
                    for i in range(0, len(faces)):
                        for v in range(0, 3):
                            normArray[(i * 3) + v] = (
                                [normals[faces[i][v]][0],
                                 normals[faces[i][v]][1],
                                 normals[faces[i][v]][2]]
                            )
                msh.normals_split_custom_set(normArray)

        # create texture corrdinates
        # print("tverts ", len(tverts))
        # this is just a hack, i just add all the UVs into the same space <<<
        if len(tverts) > 0:
            uvw = msh.uv_layers.new()
            # if len(tverts) == (len(faces) * 3):
            #    for v in range(0, len(faces) * 3):
            #        msh.uv_layers[uvw.name].data[v].uv = tverts[v]
            # else:
            uvwArray = [[float] * 2] * len(tverts[0])
            for i in range(0, len(tverts[0])):
                uvwArray[i] = [0.0, 0.0]

            for v in range(0, len(tverts[0])):
                for i in range(0, len(tverts)):
                    uvwArray[v][0] += tverts[i][v][0]
                    uvwArray[v][1] += 1.0 - tverts[i][v][1]

            for i in range(0, len(faces)):
                for v in range(0, 3):
                    msh.uv_layers[uvw.name].data[(i * 3) + v].uv = (
                        uvwArray[faces[i][v]][0],
                        uvwArray[faces[i][v]][1]
                    )

        # create vertex colours
        if len(colours) > 0:
            col = msh.vertex_colors.new()
            if len(colours) == (len(faces) * 3):
                for v in range(0, len(faces) * 3):
                    msh.vertex_colors[col.name].data[v].color = colours[v]
            else:
                colArray = [[float] * 4] * (len(faces) * 3)
                for i in range(0, len(faces)):
                    for v in range(0, 3):
                        msh.vertex_colors[col.name].data[(i * 3) + v].color = colours[faces[i][v]]
        else:
            # Use colours to make a random display
            col = msh.vertex_colors.new()
            random_col = random.uniform(0.0, 1.0), random.uniform(0.0, 1.0), random.uniform(0.0, 1.0), 1.0
            for v in range(0, len(faces) * 3):
                msh.vertex_colors[col.name].data[v].color = random_col

    # Create Face Maps?
    # msh.face_maps.new()

    # Check mesh is Valid
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # an additional or a replacement valatiation function
    # would be required

    if msh.validate(clean_customdata=False):
        print("Warning, Blender Deleted (" + obj_name + "), reason unspecified, likely empty")

    # Update Mesh
    msh.update()

    # Assign Mesh to Object
    obj = bpy.data.objects.new(obj_name, msh)
    obj.location = position
    # obj.name = obj.name.replace(".", "_")

    for i in range(0, len(materials)):
        if len(obj.material_slots) < (i + 1):
            # if there is no slot then we append to create the slot and assign
            if type(materials[i]).__name__ == 'StandardMaterial':
                obj.data.materials.append(materials[i].data)
            else:
                obj.data.materials.append(materials[i])
        else:
            # we always want the material in slot[0]
            if type(materials[i]).__name__ == 'StandardMaterial':
                obj.material_slots[0].material = materials[i].data
            else:
                obj.material_slots[0].material = materials[i]
        # obj.active_material = obj.material_slots[i].material

    if len(materialIDs) == len(obj.data.polygons):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i]
            if materialIDs[i] > len(materialIDs):
                materialIDs[i] = materialIDs[i] % len(materialIDs)

    elif len(materialIDs) > 0:
        print("Error:\tMaterial Index Out of Range")

    layer.objects.link(obj)
    
    # Assign Material ID's
    bpy.context.view_layer.objects.active = obj
    bpy.ops.object.mode_set(mode='EDIT', toggle=False)
    bpy.context.tool_settings.mesh_select_mode = [False, False, True]

    bpy.ops.object.mode_set(mode='OBJECT')
    return obj


def deleteScene(include=[]):
    if len(include) > 0:
        # Exit and Interactions
        if bpy.context.view_layer.objects.active != None:
            bpy.ops.object.mode_set(mode='OBJECT')

        # Select All
        bpy.ops.object.select_all(action='SELECT')

        # Loop Through Each Selection
        for o in bpy.context.view_layer.objects.selected:
            for t in include:
                if o.type == t:
                    bpy.data.objects.remove(o, do_unlink=True)
                    break

        # De-Select All
        bpy.ops.object.select_all(action='DESELECT')
    return None


class fmtTMB_Entry_0x01:  # 96 bytes, material
    '''float[4]'''
    unk115 = [0.0, 0.0, 0.0, 1.0] # Diffuse Colour RGBA
    
    '''float[4]'''
    unk116 = [1.0, 1.0, 1.0, 1.0] # Ambient Colour RGBA
    
    '''float[4]'''
    unk117 = [0.0, 0.0, 0.0, 1.0] # Emissive Colour RGBA
    
    '''float[4]'''
    unk118 = [1.0, 1.0, 1.0, 0.0] # Specular Colour RGBA
    
    '''uint32_t'''
    unk119 = 0 # Specular Power?
    
    '''uint16_t'''
    unk120 = 0
    
    '''uint16_t'''
    unk121 = 0
    
    '''uint16_t'''
    unk122 = 0
    
    '''uint16_t'''
    unk123 = 0
    
    '''uint32_t'''
    unk124 = 0
    
    '''uint32_t'''
    unk125 = 0
    
    '''uint32_t'''
    unk126 = 0
    
    '''uint32_t'''
    unk127 = 0
    
    '''uint32_t'''
    unk128 = 0
    
    def read (self, f = fopen()):
        self.unk115 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk116 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk117 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk118 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk119 = readLong(f, unsigned)
        self.unk120 = readShort(f, unsigned)
        self.unk121 = readShort(f, unsigned)
        self.unk122 = readShort(f, unsigned)
        self.unk123 = readShort(f, unsigned)
        self.unk124 = readLong(f, unsigned)
        self.unk125 = readLong(f, unsigned)
        self.unk126 = readLong(f, unsigned)
        self.unk127 = readLong(f, unsigned)
        self.unk128 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Entry_0x02:  # 240 bytes, object?
    
    '''char[32]'''
    name3 = ""
    
    '''float[4][4]'''
    unk131 = [  # Transform
        [1.0, 0.0, 0.0, 0.0],
        [0.0, 1.0, 0.0, 0.0],
        [0.0, 0.0, 1.0, 0.0],
        [0.0, 0.0, 0.0, 1.0]
        ]
    
    '''uint32_t'''
    unk0132 = 0.0
    
    '''uint32_t'''
    unk0133 = 0.0
    
    '''uint32_t'''
    unk0134 = 0.0
    
    '''uint32_t'''
    unk0135 = 0.0
    
    '''uint32_t'''
    unk0136 = 0.0
    
    '''uint32_t'''
    unk0137 = 0.0
    
    '''uint32_t'''
    unk0138 = 0.0
    
    '''uint32_t'''
    unk0139 = 0.0
    
    '''uint32_t'''
    unk0140 = 0.0
    
    '''uint32_t'''
    unk0141 = 0.0
    
    '''uint32_t'''
    unk0142 = 0.0
    
    '''uint32_t'''
    unk0143 = 0.0
    
    '''uint32_t'''
    unk0144 = 0.0
    
    '''uint32_t'''
    unk0145 = 0.0
    
    '''uint32_t'''
    unk0146 = 0.0
    
    '''uint32_t'''
    unk0147 = 0.0
    
    '''uint32_t'''
    unk0148 = 0.0
    
    '''uint32_t'''
    unk0149 = 0.0
    
    '''uint32_t'''
    unk0150 = 0.0
    
    '''uint32_t'''
    unk0151 = 0.0
    
    '''uint32_t'''
    unk0152 = 0.0
    
    '''uint32_t'''
    unk0153 = 0.0
    
    '''uint32_t'''
    unk0154 = 0.0
    
    '''uint32_t'''
    unk0155 = 0.0
    
    '''uint32_t'''
    unk0156 = 0.0
    
    '''uint32_t'''
    unk0157 = 0.0
    
    '''uint32_t'''
    unk0158 = 0.0
    
    '''uint32_t'''
    unk0159 = 0.0
    
    '''uint32_t'''
    unk0160 = 0.0
    
    '''uint32_t'''
    unk0161 = 0.0
    
    '''uint32_t'''
    unk0162 = 0.0
    
    '''uint32_t'''
    unk0163 = 0.0
    
    '''int32_t'''
    unk0164 = -1
    
    '''int32_t'''
    unk0165 = -1 # -1 parent?
    
    '''int32_t'''
    unk0166 = -1 # -1 index?
    
    '''uint32_t'''
    unk0167 = 0 # padding probably
    
    def readFixedString (self, f = fopen(), len = 0):
        str = ""
        p = ftell(f) + len
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0:
                str += bit.IntAsChar(b)
            else: break
        fseek(f,p, seek_set)
        return str
        
    
    def read (self, f = fopen()):
        self.name3 = self.readFixedString(f, 32)
        
        # matrix?
        self.unk131 = [
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)], # 1 0 0 0
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)], # 0 1 0 0
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)], # 0 0 1 0
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]  # 0 0 0 1
            ]
        
        self.unk0132 = readFloat(f)
        self.unk0133 = readFloat(f)
        self.unk0134 = readFloat(f)
        self.unk0135 = readFloat(f) # 1.0
        
        # empty
        self.unk0136 = readFloat(f)
        self.unk0137 = readFloat(f)
        self.unk0138 = readFloat(f)
        self.unk0139 = readFloat(f)
        self.unk0140 = readFloat(f)
        self.unk0141 = readFloat(f)
        self.unk0142 = readFloat(f)
        self.unk0143 = readFloat(f)
        self.unk0144 = readFloat(f)
        self.unk0145 = readFloat(f)
        self.unk0146 = readFloat(f)
        self.unk0147 = readFloat(f)
        self.unk0148 = readFloat(f)
        self.unk0149 = readFloat(f)
        self.unk0150 = readFloat(f)
        self.unk0151 = readFloat(f)
        
        # transform?
        self.unk0152 = readFloat(f)
        self.unk0153 = readFloat(f)
        self.unk0154 = readFloat(f)
        self.unk0155 = readFloat(f)
        
        self.unk0156 = readFloat(f)
        self.unk0157 = readFloat(f)
        self.unk0158 = readFloat(f)
        self.unk0159 = readFloat(f)
        
        self.unk0160 = readFloat(f)
        self.unk0161 = readFloat(f)
        self.unk0162 = readFloat(f)
        self.unk0163 = readFloat(f) # 1.0
        
        self.unk0164 = readLong(f, signed)
        self.unk0165 = readLong(f, signed) # -1
        self.unk0166 = readLong(f, signed) # -1
        self.unk0167 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Entry_0x03:  # 48 bytes, ??
    unk080 = 0
    unk081 = 0
    unk082 = 0
    unk083 = 0.0
    unk084 = 0.0
    unk085 = 0.0
    unk086 = 0.0
    unk087 = 0.0
    unk088 = 0
    unk089 = 0
    unk090 = 0
    unk091 = 0
    def read (self, f = fopen()):
        self.unk080 = readLong(f, unsigned)
        self.unk081 = readLong(f, unsigned)
        self.unk082 = readLong(f, unsigned)
        self.unk083 = readFloat(f)
        self.unk084 = readFloat(f)
        self.unk085 = readFloat(f)
        self.unk086 = readFloat(f)
        self.unk087 = readFloat(f)
        self.unk088 = readLong(f, unsigned)
        self.unk089 = readLong(f, unsigned)
        self.unk090 = readLong(f, unsigned)
        self.unk091 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Entry_0x04:  # 32 bytes, mesh info? verts counts etc
    '''uint32_t'''
    unk0168 = 0
    
    '''uint32_t'''
    unk0169 = 0 # 3
    
    '''uint32_t'''
    unk0170 = 0
    
    '''uint32_t'''
    unk0171 = 0
    
    '''uint32_t'''
    unk0172 = 0
    
    '''uint32_t'''
    unk0173 = 0
    
    '''uint32_t'''
    unk0174 = 0
    
    '''uint32_t'''
    unk0175 = 0 # 0 probably padding
    
    def read (self, f = fopen()):
        self.unk0168 = readLong(f, unsigned)
        self.unk0169 = readLong(f, unsigned) # 3
        self.unk0170 = readLong(f, unsigned)
        self.unk0171 = readLong(f, unsigned)
        self.unk0172 = readLong(f, unsigned)
        self.unk0173 = readLong(f, unsigned)
        self.unk0174 = readLong(f, unsigned)
        self.unk0175 = readLong(f, unsigned)
        return None
        
    
    
    

class fmtTMB_Entry_0x05:  # 32 bytes, vertex position, normal
    '''
        vertices are in world space, yay no need to transform them
    '''
    '''float[4]'''
    unk0180 = [0.0, 0.0, 0.0, 1.0] # Position
    
    '''float[4]'''
    unk0181 = [0.0, 0.0, 0.0, 1.0] # Normal
    
    def read (self, f = fopen()):
        self.unk0180 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk0181 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        return None
        
    
    

class fmtTMB_Entry_0x06:  # 16 bytes, Vertex Positions Again lol
    '''float[4]'''
    unk0191 = [0.0, 0.0, 0.0, 0.0] # Position
    
    def read (self, f = fopen()):
        self.unk0191 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        return None
        
    

#class fmtTMB_Entry_0x07 uint8_t b # weird boolean table

class fmtTMB_Entry_0x08:  # 16 bytes, Normals Again
    '''float[4]'''
    unk0192 = [0.0, 0.0, 0.0, 0.0]
    
    def read (self, f = fopen()):
        self.unk0192 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        return None
        
    

class fmtTMB_Entry_0x0B:
    '''uint32_t'''
    type = 0
    
    '''uint32_t'''
    unk0200 = []
    
    def read (self, f = fopen()):
        '''
        need to review more samples,
        
        looks like its an array of ints,
        and it the int is bitmasked with 0x80
        then you start reading a new array to
        stream into..
        
        however theres some ints and floats so
        i had figured there was a type specifier
        but i'm unsure...
        
        i'll have to look at smaller samples to
        quantify the patterns in the stream..
        
        '''
        return None
        
    

#class fmtTMB_Entry_0x0C 

class fmtTMB_Table3_Entry:  # 32 bytes
    '''uint32_t'''
    unk0181 = 0 # vertex size
    
    '''uint32_t'''
    unk0182 = 0 # 3
    
    '''uint32_t'''
    unk0183 = 0 # index?
    
    '''uint32_t'''
    unk0184 = 0 # 1. vertex position
    
    '''uint32_t'''
    unk0185 = 0 # 2. ? position
    
    '''uint32_t'''
    unk0186 = 0 # 3. normal position
    
    '''uint32_t'''
    unk0187 = 0 # 4. ? position
    
    '''uint32_t'''
    unk0188 = 0 # 5. ? position
    
    def read_table3_entry (self, f = fopen()):
        self.unk0181 = readLong(f, unsigned)
        self.unk0182 = readLong(f, unsigned)
        self.unk0183 = readLong(f, unsigned)
        self.unk0184 = readLong(f, unsigned)
        self.unk0185 = readLong(f, unsigned)
        self.unk0186 = readLong(f, unsigned)
        self.unk0187 = readLong(f, unsigned)
        self.unk0188 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Addr:  # 8 bytes
    '''uint32_t'''
    addr = 0 # multiply by 16
    
    '''uint32_t'''
    count = 0
    
    def read (self, f = fopen()):
        self.addr = readLong(f, unsigned)
        self.count = readLong(f, unsigned)
        return None
        
    

class fmtTMB:
    '''uint32_t'''
    type = 0x20424D54
    
    '''uint32_t'''
    unk101 = 0
    
    '''float'''
    unk102 = 0.0
    
    '''fmtTMB_Addr[13]'''
    addrs = []
    
    '''char[64]'''
    textures = []
    
    '''fmtTMB_Entry_0x01[]'''
    boneArray = []
    
    '''fmtTMB_Entry_0x02[]'''
    objArray = []
    
    '''fmtTMB_Entry_0x03[]'''
    mshArray = []
    
    #0x04
    '''fmtTMB_Entry_0x05[]'''
    vertArray = []
    
    '''fmtTMB_Entry_0x06[]'''
    unk0190Array = []
    
    '''uint8_t[]'''
    flagArray = []
    
    '''fmtTMB_Entry_0x08[]'''
    unk0193Array = []
    
    '''uint16_t[]'''
    unk0195Array = []
    
    def readFixedString (self, f = fopen(), len = 0):
        str = ""
        p = ftell(f) + len
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0:
                str += bit.IntAsChar(b)
            else: break
        fseek(f,p, seek_set)
        return str
        
    
    def readFaces(self, pos = 0, count = 0):
        Face_array = []	
        if count > 0:
            face = [0, 1, 2]
            counter = 0
            j = 1
            for j in range(0, len(self.flagArray)):
                face = [face[1], face[2], counter]
                if face[0] >= count or face[1] >= count or face[2] >= count:
                    break
                counter += 1
                if self.flagArray[j + pos] == 0:
                    if bit.And(j, 1):
                        append(Face_array, [face[0], face[2], face[1]])
                    else:
                        append(Face_array, [face[0], face[1], face[2]])
        return Face_array
        
    
    def read (self, f = fopen()):
        
        # get start of file
        pos = ftell(f)
        
        # Read header
        self.type = readLong(f, unsigned)
        self.unk101 = readLong(f, unsigned)
        self.unk102 = readFloat(f)
        
        # Read Block Table
        self.addrs = []
        self.num_addrs = 13
        self.addrs = [fmtTMB_Addr] * self.num_addrs
        
        
        
        
        self.textures = []
        self.boneArray = []
        self.objArray = []
        self.mshArray = []
        self.vertArray = []
        self.unk0190Array = []
        self.flagArray = []
        self.unk0193Array = []
        self.unk0195Array = []
        for i in range(0, self.num_addrs):
            
            
            # seek to table entry
            fseek(f, pos + 12 + i * 8, seek_set)
            
            # Init Array Element
            self.addrs[i] = fmtTMB_Addr()
            
            # Read Entry
            self.addrs[i].read(f)
            
            # Skip if address is null
            if self.addrs[i].addr == 0: continue
            
            # Read Block
            fseek(f,pos + self.addrs[i].addr * 16, seek_set)
            count = self.addrs[i].count
            if count > 0:
                    
                if i == 0x00: # Texture Names
                    self.textures = [str] * count
                    for j in range(0, count):
                        self.textures[j] = self.readFixedString(f, 64)
                        
                        
                    
                elif i == 0x01:  # Bones, Probably...
                    self.boneArray = [fmtTMB_Entry_0x01] * count
                    for j in range(0, count):
                        self.boneArray[j] = fmtTMB_Entry_0x01()
                        self.boneArray[j].read(f)
                            
                        
                    
                elif i == 0x02:  # Object
                    self.objArray = [fmtTMB_Entry_0x02] * count
                    for j in range(0, count):
                        self.objArray[j] = fmtTMB_Entry_0x02()
                        self.objArray[j].read(f)
                            
                        
                    
                elif i == 0x03: 
                    # need to examine other samples
                    pass
                    
                elif i == 0x04:  # Mesh Info
                    self.mshArray = [fmtTMB_Entry_0x04] * count
                    for j in range(0, count):
                        self.mshArray[j] = fmtTMB_Entry_0x04()
                        self.mshArray[j].read(f)
                        #self.mshArray[j].repr
                            
                        
                    
                elif i == 0x05:  # Vertex Positions, hm maybe this used for lookup
                    self.vertArray = [fmtTMB_Entry_0x05] * count
                    for j in range(0, count):
                        self.vertArray[j] = fmtTMB_Entry_0x05()
                        self.vertArray[j].read(f)
                                
                        
                    
                    
                    
                elif i == 0x06:  # Vertices Again
                    
                    count = int(count / 16)
                    if count > 0:
                        self.unk0190Array = [fmtTMB_Entry_0x06] * count
                        for j in range(0, count):
                            self.unk0190Array[j] = fmtTMB_Entry_0x06()
                            self.unk0190Array[j].read(f)
                            
                        
                    
                elif i == 0x07:  # Faces
                    
                    self.flagArray = []
                    self.flagArray = [int] * count
                    for j in range(0, count):
                        self.flagArray[j] = readByte(f, unsigned)
                            
                        
                        
                    
                    
                elif i == 0x08:  # Normals Again
                    count = int(count / 16)
                    if count > 0:
                        self.unk0193Array = [fmtTMB_Entry_0x08] * count
                        for j in range(0, count):
                            self.unk0193Array[j] = fmtTMB_Entry_0x08()
                            self.unk0193Array[j].read(f)
                            
                        
                    
                elif i == 0x09:  # texture corrdinates maybe??
                    count = int(count / 4.0)
                    if count > 0:
                        self.unk0195Array = [[float] * 3] * count
                        for j in range(0, count):
                            self.unk0195Array[j] = [readShort(f, unsigned) / 1024.0, readShort(f, unsigned) / 1024.0, 0.0]
                            
                        
                    
                elif i == 0x0A: 
                    # not present in my sample, need to review more samples
                    pass
                    
                elif i == 0x0B:  # some sort of data stream
                    #fmtTMB_Entry_0x0B
                    pass
                    
                elif i == 0x0C: 
                    # need to examine more samples, not alot data is present at this block
                    pass
            
        return None
                
            
            
        
    
    def build (self, clear_scene = False, mscale = 0.1, buildBones = False):
        
        # ClearScene
        if clear_scene == True: deleteScene(['MESH', 'ARMATURE'])
        
        
        # Loop Through object
        o = None
        t = matrix3(1)
        d = None
        msh = None
        bnsArray = []
        vertices = []
        tvertices = []
        faceArray = []
        faceStart = 0
        j = 1
        v = 1
        uvStart = 0
        for j in range(0, len(self.mshArray)):
            # Mesh
            
            vertices = []
            faceArray = []
            
            # if no vertices,:SKIP
            if self.mshArray[j].unk0168 == 0: continue
            
            # Read Faces
            faceArray = self.readFaces(faceStart, self.mshArray[j].unk0168)
            faceStart += (self.mshArray[j].unk0168 + ((16-(self.mshArray[j].unk0168 % 16)) % 16))
            
            
            # Read Vertices
            vertices = []
            tvertices = []
            vertices = [[float] * 3] * self.mshArray[j].unk0168
            tvertices = [[float] * 3] * self.mshArray[j].unk0168
            
            vp = self.mshArray[j].unk0171 + self.mshArray[j].unk0168 - self.mshArray[j].unk0171
            for v in range(self.mshArray[j].unk0171,  self.mshArray[j].unk0171 + self.mshArray[j].unk0168):
                vertices[v - self.mshArray[j].unk0171] = [self.unk0190Array[v].unk0191[0] * mscale, -self.unk0190Array[v].unk0191[2] * mscale, self.unk0190Array[v].unk0191[1] * mscale]
                
            
            for v in range(0, vp):
                vt = (v + uvStart) % self.mshArray[j].unk0168
                tvertices[v] = [self.unk0195Array[vt][0], self.unk0195Array[vt][1], 0.0]
                
                
                
            uvStart += int(((self.mshArray[j].unk0168 * 4) + ((16-((self.mshArray[j].unk0168 * 4) % 16)) % 16)) / 4.0)
            
            
            # Build Mesh
            msh = mesh(
                vertices=vertices,
                faces=faceArray,
                tverts=[tvertices]
                )
            
            #msh.transform = t
            #append(mdls msh
            
        
        
        
        if buildBones:
            # Build Bones
            for o in self.objArray:
                
                # Bone
                '''
                d = Dummy name:o.name3 boxSize:[0.25, 0.25, 0.25] transform:
                    matrix3 \
                        [o.unk131[1][1], o.unk131[1][2], o.unk131[1][3]] + o.unk131[1][4] \
                        [o.unk131[2][1], o.unk131[2][2], o.unk131[2][3]] + o.unk131[2][4] \
                        [o.unk131[3][1], o.unk131[3][2], o.unk131[3][3]] + o.unk131[3][4] \
                        [o.unk131[4][1], o.unk131[4][2], o.unk131[4][3]] * mscale * o.unk131[4][4]
                    
                d.showLinks = d.showLinksOnly = True
                append(bnsArray d
                '''
            
            i = 1
            par = 1
            pos = [0.0, 0.0, 0.0]
            for i in range(0, len(bnsArray)):
                
                
                par = self.objArray[i].unk0166
                if par > -1:
                    t = bnsArray[i].transform
                    pos = bnsArray[i].position
                    while par > -1:
                        t *= bnsArray[par].transform 
                        pos += bnsArray[par].position
                        
                        
                        par = self.objArray[par].unk0166
                        break
                        
                    bnsArray[i].transform = t
                    #bnsArray[i].position = pos
                    
                    bnsArray[i].parent = bnsArray[self.objArray[i].unk0166] 
        return None
                    
                
                
                

class fmtP2IG:
    '''uint32_t'''
    type = 0x47493250 # P2IG
    
    '''uint32_t'''
    unk001 = 0
    
    '''uint32_t'''
    unk002 = 0
    
    '''uint16_t'''
    unk003 = 0
    
    '''uint16_t'''
    unk004 = 0
    
    '''char[8]'''
    name = ""
    
    '''uint32_t'''
    unk005 = 0
    
    '''uint32_t'''
    unk006 = 0
    
    '''uint16_t'''
    unk007 = 0 # width
    
    '''uint16_t'''
    unk008 = 0 # length
    
    '''uint32_t'''
    unk009 = 0 # type 0x13 = 8bit 0x14 = 4bit?
    
    '''uint32_t'''
    unk010 = 0
    
    '''uint32_t'''
    unk011 = 0
    
    '''uint32_t'''
    unk012 = 0
    
    '''uint32_t'''
    unk013 = 0
    
    '''uint32_t'''
    unk014 = 0
    
    '''uint32_t'''
    unk015 = 0
    
    '''uint32_t'''
    unk016 = 0 # pal pos
    
    '''uint32_t'''
    unk017 = 0 # pal size
    
    '''uint32_t'''
    unk018 = 0 # img pos
    
    '''uint32_t'''
    unk019 = 0 # img size
    
    '''uint32_t'''
    unk020 = 0
    
    '''uint32_t'''
    unk021 = 0
    
    '''uint32_t'''
    unk022 = 0
    
    '''uint32_t'''
    unk023 = 0
    
    '''uint32_t'''
    unk024 = 0
    
    '''uint32_t'''
    unk025 = 0
    
    '''uint32_t'''
    unk026 = 0
    
    '''uint32_t'''
    unk027 = 0
    
    '''uint32_t'''
    unk028 = 0
    
    '''uint32_t'''
    unk029 = 0
    
    '''uint32_t'''
    unk030 = 0
    
    '''uint32_t'''
    unk031 = 0
    
    '''uint8_t[4][]'''
    pal = []
    
    '''uint8_t[]'''
    img = []
    
    '''
        ps2 unswizzle code courtesy of TopazTK,
        while I was working on soul calibur 3
        
        https://forum.xentax.com/viewtopic.php?t=22497
    '''
    
    def readFixedString (self, f = fopen(), len = 0):
        str = ""
        p = ftell(f) + len
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0:
                str += bit.IntAsChar(b)
            else: break
        fseek(f, p, seek_set)
        return str
        
    
    def read (self, f = fopen()):
        
        self.type = readLong(f, unsigned)
        self.unk001 = readLong(f, unsigned)
        self.unk002 = readLong(f, unsigned)
        self.unk003 = readShort(f, unsigned)
        self.unk004 = readShort(f, unsigned)
        self.name = self.readFixedString(f, 8)
        self.unk005 = readLong(f, unsigned)
        self.unk006 = readLong(f, unsigned)
        self.unk007 = readShort(f, unsigned)
        self.unk008 = readShort(f, unsigned)
        self.unk009 = readLong(f, unsigned)
        self.unk010 = readLong(f, unsigned)
        self.unk011 = readLong(f, unsigned)
        self.unk012 = readLong(f, unsigned)
        self.unk013 = readLong(f, unsigned)
        self.unk014 = readLong(f, unsigned)
        self.unk015 = readLong(f, unsigned)
        self.unk016 = readLong(f, unsigned)
        self.unk017 = readLong(f, unsigned)
        self.unk018 = readLong(f, unsigned)
        self.unk019 = readLong(f, unsigned)
        self.unk020 = readLong(f, unsigned)
        self.unk021 = readLong(f, unsigned)
        self.unk022 = readLong(f, unsigned)
        self.unk023 = readLong(f, unsigned)
        self.unk024 = readLong(f, unsigned)
        self.unk025 = readLong(f, unsigned)
        self.unk026 = readLong(f, unsigned)
        self.unk027 = readLong(f, unsigned)
        self.unk028 = readLong(f, unsigned)
        self.unk029 = readLong(f, unsigned)
        self.unk030 = readLong(f, unsigned)
        self.unk031 = readLong(f, unsigned)
        
        # Read Image Data
        count = int(self.unk017 / 4.0)
        self.img = []
        self.pal = []
        if count > 0:
            fseek(f, self.unk016, seek_set)
            
            for i in range(0, count):
                self.pal.append([readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned)])
                
            fseek(f, self.unk018, seek_set)
            if self.unk019 > 0:
                self.img = [int] * self.unk019
                for i in range(0, self.unk019):
                    self.img[i] = readByte(f, unsigned)
        return None
    

class fmtMDL_Asset:
    '''
        this is just an intermediate between the different assets
    '''
    
    '''uint32_t'''
    type = 0
    
    '''fmtTMB'''
    model = None
    
    '''fmtP2IG'''
    texture = None
    
    def read (self, f = fopen(), fsize = 0):
        
        '''
            I include the asset size in the param 'fsize'
            as a precaution since the mdl acts as a file
            container.
        '''
        
        pos = ftell(f) # log current cursor position
        
        self.type = readLong(f, unsigned)
        fseek(f, pos, seek_set) # restore cursor position to start of asset
        
    
        if self.type == 0x20424D54:  # TMB (Model)
            self.model = fmtTMB()
            self.model.read(f)
            self.model.build()
        elif self.type == 0x47493250: # P2IG (Texture)
            self.texture = fmtP2IG()
            self.texture.read(f) # has paring issue
            #self.texture.build() # code from sc3 still needs to be adopted
            pass
        else: 
            print("Assest Unsupported")
        return None
            
            
        
    
    
    
class fmtMDL:
    
    '''uint32_t[]'''
    addrs = [], # address table is padded to 16bytes
    
    '''fmtMDL_Asset[]'''
    asset = [], # being ps2 self.assets are probably padded to 16 as well
    
    def read (self, f = fopen()):
        
        # Reset Arrays
        self.addrs = []
        self.asset = []
        
        # Get File Size
        pos = ftell(f)
        fsize = f.size
        fseek(f, pos, seek_set)
        
        # Read Address Table
        addr = 0
        eariest_addr = fsize
        while ftell(f) < eariest_addr:
            
            # Read Address
            addr = readLong(f, unsigned)
            
            # break if addr is 0
            if addr == 0: break
            
            # Log Address
            self.addrs.append(addr)
            
            # Log addr if its smaller:last addr
            if addr < eariest_addr:
                eariest_addr = addr
                
            
        
        # Get self.asset count from number of valid addresses
        count = len(self.addrs)
        if count > 0:
            
            # Generate a list of unique address, so calculate blocks sizes
            index = -1
            sizes = [fsize] #include the full size to start
            for i in range(0, count):
                # Search sizes array for the address
                index = findItem(sizes, self.addrs[i])
                
                # Not in sizes array, so append(address to it.
                if index == -1:
                    sizes.append(self.addrs[i])
                    
                
            
            # Sort sizes Array
            sizes.sort()
            
            # Dimension Asset Array
            self.asset = [fmtMDL_Asset] * count
            
            # Process Each Asset
            for i in range(0, count):
                
                # Search for ordered address in the sizes array
                index = findItem(sizes, self.addrs[i]) # index up to the next address
                
                #  Initialize Array Element
                self.asset[i] = fmtMDL_Asset()
                
                # Read Asset
                fseek(f, self.addrs[i], seek_set) # set cursor at start of self.asset
                self.asset[i].read(f, sizes[index]) # sizes[index] specifies the length of the self.asset
        return None
                
            
        
def read (file, mscale = 0.1):
    if file != None and file != "":
        
        f = fopen(file, "rb")
        if f != None:
            
            pos = ftell(f)
            
            filetype = readLong(f, unsigned)
            fseek(f, pos, seek_set)
            
            if filetype == 0x20424D54:  # TMB
                tmb = fmtTMB()
                tmb.read(f)
                tmb.build(mscale=mscale)
                
            else:  # Try MDL
                mdl = fmtMDL()
                mdl.read(f)
                
            
            
            fclose(f)
        else: print("Failed to open file")
        
    return None
    


# Callback when file(s) are selected

def kor66tmb_callback(fpath="", files=[], clearScene=True, mscale=0.1):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read (fpath + file.name, mscale)
    if len(files) > 0:
        #messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def kor66tmb(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_kor66tmb"):  # print(bpy.ops.importhelper.kor66tmb.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_kor66tmb').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_kor66tmb'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_kor66tmb(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.kor66tmb"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.mdl;*.tmb', options={'HIDDEN'}, subtype='FILE_PATH')

        # Variables
        filepath: bpy.props.StringProperty(subtype="FILE_PATH")  # full path of selected item (path+filename)
        filename: bpy.props.StringProperty(subtype="FILE_NAME")  # name of selected item
        directory: bpy.props.StringProperty(subtype="FILE_PATH")  # directory of the selected item
        files: bpy.props.CollectionProperty(
            type=bpy.types.OperatorFileListElement)  # a collection containing all the selected items f filenames

        # Controls
        my_int1: bpy.props.IntProperty(name="Some Integer", description="Tooltip")
        my_float1: bpy.props.FloatProperty(name="Scale", default=0.1, description="Changes Scale of the imported Mesh")
        # my_float2: bpy.props.FloatProperty(name="Some Float point", default = 0.25, min = -0.25, max = 0.5)
        my_bool1: bpy.props.BoolProperty(name="Clear Scene", default=True, description="Deletes everything in the scene prior to importing")

        # Runs when this class OPENS
        def invoke(self, context, event):

            # Retrieve Settings
            try: self.filepath = bpy.types.Scene.kor66tmb_filepath
            except: bpy.types.Scene.kor66tmb_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.kor66tmb_directory
            except: bpy.types.Scene.kor66tmb_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.kor66tmb_my_float1
            except: bpy.types.Scene.kor66tmb_my_float1 = bpy.props.FloatProperty(default=0.1)

            try: self.my_bool1 = bpy.types.Scene.kor66tmb_my_bool1
            except: bpy.types.Scene.kor66tmb_my_bool1 = bpy.props.BoolProperty(default=False)
            

            # Open File Browser
            # Set Properties of the File Browser
            context.window_manager.fileselect_add(self)
            context.area.tag_redraw()

            return {'RUNNING_MODAL'}

        # Runs when this Window is CANCELLED
        def cancel(self, context):
            print("run bitch")

        # Runs when the class EXITS
        def execute(self, context):

            # Save Settings
            bpy.types.Scene.kor66tmb_filepath = self.filepath
            bpy.types.Scene.kor66tmb_directory = self.directory
            bpy.types.Scene.kor66tmb_my_float1 = self.my_float1
            bpy.types.Scene.kor66tmb_my_bool1 = self.my_bool1

            # Run Callback
            kor66tmb_callback(
                self.directory,
                self.files,
                self.my_bool1,
                self.my_float1
                )

            return {"FINISHED"}

            # Window Settings

        def draw(self, context):

            self.layout.row().label(text="Import Settings")

            self.layout.separator()
            self.layout.row().prop(self, "my_bool1")
            self.layout.row().prop(self, "my_float1")

            self.layout.separator()

            col = self.layout.row()
            col.alignment = 'RIGHT'
            col.label(text="  Author:", icon='QUESTION')
            col.alignment = 'LEFT'
            col.label(text="mariokart64n")

            col = self.layout.row()
            col.alignment = 'RIGHT'
            col.label(text="Release:", icon='GRIP')
            col.alignment = 'LEFT'
            col.label(text="January 3, 2023")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.kor66tmb", text="King of Route 66 (*.mdl, *.tmb)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_kor66tmb)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_kor66tmb.menu_func_import)

    # Assign Shortcut key
    # bpy.context.window_manager.keyconfigs.active.keymaps["Window"].keymap_items.new('bpy.ops.text.run_script()', 'E', 'PRESS', ctrl=True, shift=False, repeat=False)

    # Call ImportHelper
    bpy.ops.importhelper.kor66tmb('INVOKE_DEFAULT')


# END OF MAIN FUNCTION ##############################################################


if not useOpenDialog:

    deleteScene(['MESH', 'ARMATURE'])
    
    read (
        "E:\\BackUp\\MyCloud4100\\Coding\\Maxscripts\\File IO\\King of Route 66, The (USA)\\ARIZONA_ARI_BODY\\ARIZONA_ARI_BODY.mdl"
        )
else: kor66tmb(True)


```

Code also on my [github](https://github.com/coreynguyen/bpy_king_of_route_66)
## Post #19
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-01-04T10:10:00+00:00
- Post Title: Re: King of Route 66 .MDL files

> Reply from mariokart64n ↑Wed Jan 04, 2023 11:03 am at Wed Jan 04, 2023 11:03 am
>
> 
I did however port the script into blender, you can multi select MDL's and import all at once.

Thank you for the blender script! it makes things alot easier for me for sure! import works like a charm!
however, the before slightly messed up uvs from texas queen are now really messed up:


great to see that texmod does not give you these half transparent results (like ninja ripper)...they really become a pain when dealing with textures with actual transparency.

at least somebody discovered a hidden debug menu in the game that can be activated by "L3" in the main menu once the file is placed with the correct Game-ID in you pcsx2 cheats folder:


 KOR66_Debug.zip
Cheat Code pnach for hidden Debug Menu (281 Bytes) Downloaded 14 times



under puppet test you will be able to view every characters ingame model
## Post #20
- Username: AndrewAbdullah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 10, 2023 5:10 pm
- Post datetime: 2023-01-10T09:14:51+00:00
- Post Title: Re: King of Route 66 .MDL files

> Reply from mariokart64n ↑Wed Jan 04, 2023 11:03 am at Wed Jan 04, 2023 11:03 am
>
> 
yeah I used texMod, but it won't work unless the texture is in view, otherwise the game seems to cull the geometry out of view and thus I can't capture the textures with texMod.

any other DX dumper like NinjaRipper I imagine will suffer from the same pitfalls sadly. I know dumping the textures suck but I don't have enough experience with PS2 textures. I revisited it last night and wasn't able to get anywhere with it.

the 3 models do crash the program but I didn't look much further into it being you snatched them from the prototype any hows

I did however port the script into blender, you can multi select MDL's and import all at once. 
Code: Select all'''
    3ds max's MaxScript for Importing mdl / tmb from king of route 66 on ps2

    written by mariokart64n
    dec 9 2022
    
    Script written around a dozen file samples uploaded here
    https://forum.xentax.com/viewtopic.php?p=156970#p156970

    notes:
        I was curious about the face drawing since others seemed to have issue with it.
        Looks as if the faces are written after the vertices as an array of bytes.
        when a 0 is read the face is saved, where if theres a 1:you skip basically.
        The other component to this was to read the mesh table to get the proper submeshes
        out of the vertex buffer.. kind of standard stuff.
        
        Only issue is there isn't much to the mesh table, it links into an object table
        that builds bones which I was unable to resolve. But I was able to get the mesh
        to import correctly so I was happy enough with that.
        
        Script was only tested on the samples of Arizona, so theres a high chance the
        script won't work on anything.
        
        
'''

useOpenDialog = True


from pathlib import Path  # Needed for os stuff
import random
import struct  # Needed for Binary Reader
import bpy
import mathutils  # this i'm guessing is a branch of the bpy module specifically for math operations

signed, unsigned = 0, 1  # Enums for read function
seek_set, seek_cur, seek_end = 0, 1, 2  # Enums for seek function

class bit:
    def And(integer1, integer2): return (integer1 & integer2)
    def IntAsChar(integer): return chr(int(integer))

class matrix3:
    row1 = [1.0, 0.0, 0.0]
    row2 = [0.0, 1.0, 0.0]
    row3 = [0.0, 0.0, 1.0]
    row4 = [0.0, 0.0, 0.0]

    def __init__(self, rowA=[1.0, 0.0, 0.0], rowB=[0.0, 1.0, 0.0], rowC=[0.0, 0.0, 1.0], rowD=[0.0, 0.0, 0.0]):
        if rowA == 0:
            self.row1 = [0.0, 0.0, 0.0]
            self.row2 = [0.0, 0.0, 0.0]
            self.row3 = [0.0, 0.0, 0.0]

        elif rowA == 1:
            self.row1 = [1.0, 0.0, 0.0]
            self.row2 = [0.0, 1.0, 0.0]
            self.row3 = [0.0, 0.0, 1.0]
            self.row4 = [0.0, 0.0, 0.0]
        else:
            self.row1 = rowA
            self.row2 = rowB
            self.row3 = rowC
            self.row4 = rowD

    def __repr__(self):
        return (
                "matrix3([" + str(self.row1[0]) +
                ", " + str(self.row1[1]) +
                ", " + str(self.row1[2]) +
                "], [" + str(self.row2[0]) +
                ", " + str(self.row2[1]) +
                ", " + str(self.row2[2]) +
                "], [" + str(self.row3[0]) +
                ", " + str(self.row3[1]) +
                ", " + str(self.row3[2]) +
                "], [" + str(self.row4[0]) +
                ", " + str(self.row4[1]) +
                ", " + str(self.row4[2]) + "])"
        )


def findItem(array, value):
    index = -1
    try: index = array.index(value)
    except: pass
    return index


def append(array, value):
    array.append(value)
    return None

class fopen:
    little_endian = True
    file = ""
    mode = 'rb'
    data = bytearray()
    size = 0
    pos = 0
    isGood = False

    def __init__(self, filename=None, mode='rb', isLittleEndian=True):
        if mode == 'rb':
            if filename != None and Path(filename).is_file():
                self.data = open(filename, mode).read()
                self.size = len(self.data)
                self.pos = 0
                self.mode = mode
                self.file = filename
                self.little_endian = isLittleEndian
                self.isGood = True
        else:
            self.file = filename
            self.mode = mode
            self.data = bytearray()
            self.pos = 0
            self.size = 0
            self.little_endian = isLittleEndian
            self.isGood = False

        pass

    # def __del__(self):
    #    self.flush()

    def resize(self, dataSize=0):
        if dataSize > 0:
            self.data = bytearray(dataSize)
        else:
            self.data = bytearray()
        self.pos = 0
        self.size = dataSize
        self.isGood = False
        return None

    def flush(self):
        if self.file != "" and not self.isGood and len(self.data) > 0:
            self.isGood = True
            s = open(self.file, 'w+b')
            s.write(self.data)
            s.close()

    def read_and_unpack(self, unpack, size):
        value = 0
        if self.size > 0 and self.pos + size <= self.size:
            value = struct.unpack_from(unpack, self.data, self.pos)[0]
            self.pos += size
        return value

    def pack_and_write(self, pack, size, value):
        if self.pos + size > self.size:
            self.data.extend(b'\x00' * ((self.pos + size) - self.size))
            self.size = self.pos + size
        try:
            struct.pack_into(pack, self.data, self.pos, value)
        except:
            # print('Pos:\t%i / %i (buf:%i) [val:%i:%i:%s]' % (self.pos, self.size, len(self.data), value, size, pack))
            pass
        self.pos += size
        return None

    def set_pointer(self, offset):
        self.pos = offset
        return None

    def set_endian(self, isLittle=True):
        self.little_endian = isLittle
        return isLittle


def fclose(bitStream=fopen()):
    bitStream.flush()
    bitStream.isGood = False


def fseek(bitStream=fopen(), offset=0, dir=0):
    if dir == 0:
        bitStream.set_pointer(offset)
    elif dir == 1:
        bitStream.set_pointer(bitStream.pos + offset)
    elif dir == 2:
        bitStream.set_pointer(bitStream.pos - offset)
    return None


def ftell(bitStream=fopen()):
    return bitStream.pos


def readByte(bitStream=fopen(), isSigned=0):
    fmt = 'b' if isSigned == 0 else 'B'
    return (bitStream.read_and_unpack(fmt, 1))


def readShort(bitStream=fopen(), isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'h' if isSigned == 0 else 'H'
    return (bitStream.read_and_unpack(fmt, 2))


def readLong(bitStream=fopen(), isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'i' if isSigned == 0 else 'I'
    return (bitStream.read_and_unpack(fmt, 4))

def readFloat(bitStream=fopen()):
    fmt = '>f' if not bitStream.little_endian else '<f'
    return (bitStream.read_and_unpack(fmt, 4))


def mesh_validate(vertices=[], faces=[]):
    # basic face index check
    # blender will crash if the mesh data is bad

    # Check an Array was given
    result = (type(faces).__name__ == "tuple" or type(faces).__name__ == "list")
    if result == True:

        # Check the the array is Not empty
        if len(faces) > 0:

            # check that the face is a vector
            if (type(faces[0]).__name__ == "tuple" or type(faces[0]).__name__ == "list"):

                # Calculate the Max face index from supplied vertices
                face_min = 0
                face_max = len(vertices) - 1

                # Check face indeices
                for face in faces:
                    for side in face:

                        # Check face index is in range
                        if side < face_min and side > face_max:
                            print("MeshValidation: \tFace Index Out of Range:\t[%i / %i]" % (side, face_max))
                            result = False
                            break
            else:
                print("MeshValidation: \tFace In Array is Invalid")
                result = False
        else:
            print("MeshValidation: \tFace Array is Empty")
    else:
        print("MeshValidation: \tArray Invalid")
        result = False
    return result


def mesh(
        vertices=[],
        faces=[],
        materialIDs=[],
        tverts=[],
        normals=[],
        colours=[],
        materials=[],
        mscale=1.0,
        flipAxis=False,
        obj_name="Object",
        lay_name='',
        position=(0.0, 0.0, 0.0)
        ):
    #
    # This function is pretty, ugly
    # imports the mesh into blender
    #
    # Clear Any Object Selections
    # for o in bpy.context.selected_objects: o.select = False
    bpy.context.view_layer.objects.active = None

    # Get Collection (Layers)
    if lay_name != '':
        # make collection
        layer = bpy.data.collections.get(lay_name)
        if layer == None:
            layer = bpy.data.collections.new(lay_name)
            bpy.context.scene.collection.children.link(layer)
    else:
        if len(bpy.data.collections) == 0:
            layer = bpy.data.collections.new("Collection")
            bpy.context.scene.collection.children.link(layer)
        else:
            try:
                layer = bpy.data.collections[bpy.context.view_layer.active_layer_collection.name]
            except:
                layer = bpy.data.collections[0]

    # make mesh
    msh = bpy.data.meshes.new('Mesh')

    # msh.name = msh.name.replace(".", "_")

    # Apply vertex scaling
    # mscale *= bpy.context.scene.unit_settings.scale_length
    vertArray = []
    if len(vertices) > 0:
        vertArray = [[float] * 3] * len(vertices)
        if flipAxis:
            for v in range(0, len(vertices)):
                vertArray[v] = (
                    vertices[v][0] * mscale,
                    -vertices[v][2] * mscale,
                    vertices[v][1] * mscale
                )
        else:
            for v in range(0, len(vertices)):
                vertArray[v] = (
                    vertices[v][0] * mscale,
                    vertices[v][1] * mscale,
                    vertices[v][2] * mscale
                )

    # assign data from arrays
    if not mesh_validate(vertArray, faces):
        # Erase Mesh
        msh.user_clear()
        bpy.data.meshes.remove(msh)
        print("Mesh Deleted!")
        return None

    msh.from_pydata(vertArray, [], faces)

    # set surface to smooth
    msh.polygons.foreach_set("use_smooth", [True] * len(msh.polygons))

    # Set Normals
    if len(faces) > 0:
        if len(normals) > 0:
            msh.use_auto_smooth = True
            if len(normals) == (len(faces) * 3):
                msh.normals_split_custom_set(normals)
            else:
                normArray = [[float] * 3] * (len(faces) * 3)
                if flipAxis:
                    for i in range(0, len(faces)):
                        for v in range(0, 3):
                            normArray[(i * 3) + v] = (
                                [normals[faces[i][v]][0],
                                 -normals[faces[i][v]][2],
                                 normals[faces[i][v]][1]]
                            )
                else:
                    for i in range(0, len(faces)):
                        for v in range(0, 3):
                            normArray[(i * 3) + v] = (
                                [normals[faces[i][v]][0],
                                 normals[faces[i][v]][1],
                                 normals[faces[i][v]][2]]
                            )
                msh.normals_split_custom_set(normArray)

        # create texture corrdinates
        # print("tverts ", len(tverts))
        # this is just a hack, i just add all the UVs into the same space <<<
        if len(tverts) > 0:
            uvw = msh.uv_layers.new()
            # if len(tverts) == (len(faces) * 3):
            #    for v in range(0, len(faces) * 3):
            #        msh.uv_layers[uvw.name].data[v].uv = tverts[v]
            # else:
            uvwArray = [[float] * 2] * len(tverts[0])
            for i in range(0, len(tverts[0])):
                uvwArray[i] = [0.0, 0.0]

            for v in range(0, len(tverts[0])):
                for i in range(0, len(tverts)):
                    uvwArray[v][0] += tverts[i][v][0]
                    uvwArray[v][1] += 1.0 - tverts[i][v][1]

            for i in range(0, len(faces)):
                for v in range(0, 3):
                    msh.uv_layers[uvw.name].data[(i * 3) + v].uv = (
                        uvwArray[faces[i][v]][0],
                        uvwArray[faces[i][v]][1]
                    )

        # create vertex colours
        if len(colours) > 0:
            col = msh.vertex_colors.new()
            if len(colours) == (len(faces) * 3):
                for v in range(0, len(faces) * 3):
                    msh.vertex_colors[col.name].data[v].color = colours[v]
            else:
                colArray = [[float] * 4] * (len(faces) * 3)
                for i in range(0, len(faces)):
                    for v in range(0, 3):
                        msh.vertex_colors[col.name].data[(i * 3) + v].color = colours[faces[i][v]]
        else:
            # Use colours to make a random display
            col = msh.vertex_colors.new()
            random_col = random.uniform(0.0, 1.0), random.uniform(0.0, 1.0), random.uniform(0.0, 1.0), 1.0
            for v in range(0, len(faces) * 3):
                msh.vertex_colors[col.name].data[v].color = random_col

    # Create Face Maps?
    # msh.face_maps.new()

    # Check mesh is Valid
    # Without this blender may crash!!! lulz
    # However the check will throw false positives so
    # an additional or a replacement valatiation function
    # would be required

    if msh.validate(clean_customdata=False):
        print("Warning, Blender Deleted (" + obj_name + "), reason unspecified, likely empty")

    # Update Mesh
    msh.update()

    # Assign Mesh to Object
    obj = bpy.data.objects.new(obj_name, msh)
    obj.location = position
    # obj.name = obj.name.replace(".", "_")

    for i in range(0, len(materials)):
        if len(obj.material_slots) < (i + 1):
            # if there is no slot then we append to create the slot and assign
            if type(materials[i]).__name__ == 'StandardMaterial':
                obj.data.materials.append(materials[i].data)
            else:
                obj.data.materials.append(materials[i])
        else:
            # we always want the material in slot[0]
            if type(materials[i]).__name__ == 'StandardMaterial':
                obj.material_slots[0].material = materials[i].data
            else:
                obj.material_slots[0].material = materials[i]
        # obj.active_material = obj.material_slots[i].material

    if len(materialIDs) == len(obj.data.polygons):
        for i in range(0, len(materialIDs)):
            obj.data.polygons[i].material_index = materialIDs[i]
            if materialIDs[i] > len(materialIDs):
                materialIDs[i] = materialIDs[i] % len(materialIDs)

    elif len(materialIDs) > 0:
        print("Error:\tMaterial Index Out of Range")

    layer.objects.link(obj)
    
    # Assign Material ID's
    bpy.context.view_layer.objects.active = obj
    bpy.ops.object.mode_set(mode='EDIT', toggle=False)
    bpy.context.tool_settings.mesh_select_mode = [False, False, True]

    bpy.ops.object.mode_set(mode='OBJECT')
    return obj


def deleteScene(include=[]):
    if len(include) > 0:
        # Exit and Interactions
        if bpy.context.view_layer.objects.active != None:
            bpy.ops.object.mode_set(mode='OBJECT')

        # Select All
        bpy.ops.object.select_all(action='SELECT')

        # Loop Through Each Selection
        for o in bpy.context.view_layer.objects.selected:
            for t in include:
                if o.type == t:
                    bpy.data.objects.remove(o, do_unlink=True)
                    break

        # De-Select All
        bpy.ops.object.select_all(action='DESELECT')
    return None


class fmtTMB_Entry_0x01:  # 96 bytes, material
    '''float[4]'''
    unk115 = [0.0, 0.0, 0.0, 1.0] # Diffuse Colour RGBA
    
    '''float[4]'''
    unk116 = [1.0, 1.0, 1.0, 1.0] # Ambient Colour RGBA
    
    '''float[4]'''
    unk117 = [0.0, 0.0, 0.0, 1.0] # Emissive Colour RGBA
    
    '''float[4]'''
    unk118 = [1.0, 1.0, 1.0, 0.0] # Specular Colour RGBA
    
    '''uint32_t'''
    unk119 = 0 # Specular Power?
    
    '''uint16_t'''
    unk120 = 0
    
    '''uint16_t'''
    unk121 = 0
    
    '''uint16_t'''
    unk122 = 0
    
    '''uint16_t'''
    unk123 = 0
    
    '''uint32_t'''
    unk124 = 0
    
    '''uint32_t'''
    unk125 = 0
    
    '''uint32_t'''
    unk126 = 0
    
    '''uint32_t'''
    unk127 = 0
    
    '''uint32_t'''
    unk128 = 0
    
    def read (self, f = fopen()):
        self.unk115 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk116 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk117 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk118 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk119 = readLong(f, unsigned)
        self.unk120 = readShort(f, unsigned)
        self.unk121 = readShort(f, unsigned)
        self.unk122 = readShort(f, unsigned)
        self.unk123 = readShort(f, unsigned)
        self.unk124 = readLong(f, unsigned)
        self.unk125 = readLong(f, unsigned)
        self.unk126 = readLong(f, unsigned)
        self.unk127 = readLong(f, unsigned)
        self.unk128 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Entry_0x02:  # 240 bytes, object?
    
    '''char[32]'''
    name3 = ""
    
    '''float[4][4]'''
    unk131 = [  # Transform
        [1.0, 0.0, 0.0, 0.0],
        [0.0, 1.0, 0.0, 0.0],
        [0.0, 0.0, 1.0, 0.0],
        [0.0, 0.0, 0.0, 1.0]
        ]
    
    '''uint32_t'''
    unk0132 = 0.0
    
    '''uint32_t'''
    unk0133 = 0.0
    
    '''uint32_t'''
    unk0134 = 0.0
    
    '''uint32_t'''
    unk0135 = 0.0
    
    '''uint32_t'''
    unk0136 = 0.0
    
    '''uint32_t'''
    unk0137 = 0.0
    
    '''uint32_t'''
    unk0138 = 0.0
    
    '''uint32_t'''
    unk0139 = 0.0
    
    '''uint32_t'''
    unk0140 = 0.0
    
    '''uint32_t'''
    unk0141 = 0.0
    
    '''uint32_t'''
    unk0142 = 0.0
    
    '''uint32_t'''
    unk0143 = 0.0
    
    '''uint32_t'''
    unk0144 = 0.0
    
    '''uint32_t'''
    unk0145 = 0.0
    
    '''uint32_t'''
    unk0146 = 0.0
    
    '''uint32_t'''
    unk0147 = 0.0
    
    '''uint32_t'''
    unk0148 = 0.0
    
    '''uint32_t'''
    unk0149 = 0.0
    
    '''uint32_t'''
    unk0150 = 0.0
    
    '''uint32_t'''
    unk0151 = 0.0
    
    '''uint32_t'''
    unk0152 = 0.0
    
    '''uint32_t'''
    unk0153 = 0.0
    
    '''uint32_t'''
    unk0154 = 0.0
    
    '''uint32_t'''
    unk0155 = 0.0
    
    '''uint32_t'''
    unk0156 = 0.0
    
    '''uint32_t'''
    unk0157 = 0.0
    
    '''uint32_t'''
    unk0158 = 0.0
    
    '''uint32_t'''
    unk0159 = 0.0
    
    '''uint32_t'''
    unk0160 = 0.0
    
    '''uint32_t'''
    unk0161 = 0.0
    
    '''uint32_t'''
    unk0162 = 0.0
    
    '''uint32_t'''
    unk0163 = 0.0
    
    '''int32_t'''
    unk0164 = -1
    
    '''int32_t'''
    unk0165 = -1 # -1 parent?
    
    '''int32_t'''
    unk0166 = -1 # -1 index?
    
    '''uint32_t'''
    unk0167 = 0 # padding probably
    
    def readFixedString (self, f = fopen(), len = 0):
        str = ""
        p = ftell(f) + len
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0:
                str += bit.IntAsChar(b)
            else: break
        fseek(f,p, seek_set)
        return str
        
    
    def read (self, f = fopen()):
        self.name3 = self.readFixedString(f, 32)
        
        # matrix?
        self.unk131 = [
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)], # 1 0 0 0
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)], # 0 1 0 0
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)], # 0 0 1 0
            [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]  # 0 0 0 1
            ]
        
        self.unk0132 = readFloat(f)
        self.unk0133 = readFloat(f)
        self.unk0134 = readFloat(f)
        self.unk0135 = readFloat(f) # 1.0
        
        # empty
        self.unk0136 = readFloat(f)
        self.unk0137 = readFloat(f)
        self.unk0138 = readFloat(f)
        self.unk0139 = readFloat(f)
        self.unk0140 = readFloat(f)
        self.unk0141 = readFloat(f)
        self.unk0142 = readFloat(f)
        self.unk0143 = readFloat(f)
        self.unk0144 = readFloat(f)
        self.unk0145 = readFloat(f)
        self.unk0146 = readFloat(f)
        self.unk0147 = readFloat(f)
        self.unk0148 = readFloat(f)
        self.unk0149 = readFloat(f)
        self.unk0150 = readFloat(f)
        self.unk0151 = readFloat(f)
        
        # transform?
        self.unk0152 = readFloat(f)
        self.unk0153 = readFloat(f)
        self.unk0154 = readFloat(f)
        self.unk0155 = readFloat(f)
        
        self.unk0156 = readFloat(f)
        self.unk0157 = readFloat(f)
        self.unk0158 = readFloat(f)
        self.unk0159 = readFloat(f)
        
        self.unk0160 = readFloat(f)
        self.unk0161 = readFloat(f)
        self.unk0162 = readFloat(f)
        self.unk0163 = readFloat(f) # 1.0
        
        self.unk0164 = readLong(f, signed)
        self.unk0165 = readLong(f, signed) # -1
        self.unk0166 = readLong(f, signed) # -1
        self.unk0167 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Entry_0x03:  # 48 bytes, ??
    unk080 = 0
    unk081 = 0
    unk082 = 0
    unk083 = 0.0
    unk084 = 0.0
    unk085 = 0.0
    unk086 = 0.0
    unk087 = 0.0
    unk088 = 0
    unk089 = 0
    unk090 = 0
    unk091 = 0
    def read (self, f = fopen()):
        self.unk080 = readLong(f, unsigned)
        self.unk081 = readLong(f, unsigned)
        self.unk082 = readLong(f, unsigned)
        self.unk083 = readFloat(f)
        self.unk084 = readFloat(f)
        self.unk085 = readFloat(f)
        self.unk086 = readFloat(f)
        self.unk087 = readFloat(f)
        self.unk088 = readLong(f, unsigned)
        self.unk089 = readLong(f, unsigned)
        self.unk090 = readLong(f, unsigned)
        self.unk091 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Entry_0x04:  # 32 bytes, mesh info? verts counts etc
    '''uint32_t'''
    unk0168 = 0
    
    '''uint32_t'''
    unk0169 = 0 # 3
    
    '''uint32_t'''
    unk0170 = 0
    
    '''uint32_t'''
    unk0171 = 0
    
    '''uint32_t'''
    unk0172 = 0
    
    '''uint32_t'''
    unk0173 = 0
    
    '''uint32_t'''
    unk0174 = 0
    
    '''uint32_t'''
    unk0175 = 0 # 0 probably padding
    
    def read (self, f = fopen()):
        self.unk0168 = readLong(f, unsigned)
        self.unk0169 = readLong(f, unsigned) # 3
        self.unk0170 = readLong(f, unsigned)
        self.unk0171 = readLong(f, unsigned)
        self.unk0172 = readLong(f, unsigned)
        self.unk0173 = readLong(f, unsigned)
        self.unk0174 = readLong(f, unsigned)
        self.unk0175 = readLong(f, unsigned)
        return None
        
    
    
    

class fmtTMB_Entry_0x05:  # 32 bytes, vertex position, normal
    '''
        vertices are in world space, yay no need to transform them
    '''
    '''float[4]'''
    unk0180 = [0.0, 0.0, 0.0, 1.0] # Position
    
    '''float[4]'''
    unk0181 = [0.0, 0.0, 0.0, 1.0] # Normal
    
    def read (self, f = fopen()):
        self.unk0180 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        self.unk0181 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        return None
        
    
    

class fmtTMB_Entry_0x06:  # 16 bytes, Vertex Positions Again lol
    '''float[4]'''
    unk0191 = [0.0, 0.0, 0.0, 0.0] # Position
    
    def read (self, f = fopen()):
        self.unk0191 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        return None
        
    

#class fmtTMB_Entry_0x07 uint8_t b # weird boolean table

class fmtTMB_Entry_0x08:  # 16 bytes, Normals Again
    '''float[4]'''
    unk0192 = [0.0, 0.0, 0.0, 0.0]
    
    def read (self, f = fopen()):
        self.unk0192 = [readFloat(f), readFloat(f), readFloat(f), readFloat(f)]
        return None
        
    

class fmtTMB_Entry_0x0B:
    '''uint32_t'''
    type = 0
    
    '''uint32_t'''
    unk0200 = []
    
    def read (self, f = fopen()):
        '''
        need to review more samples,
        
        looks like its an array of ints,
        and it the int is bitmasked with 0x80
        then you start reading a new array to
        stream into..
        
        however theres some ints and floats so
        i had figured there was a type specifier
        but i'm unsure...
        
        i'll have to look at smaller samples to
        quantify the patterns in the stream..
        
        '''
        return None
        
    

#class fmtTMB_Entry_0x0C 

class fmtTMB_Table3_Entry:  # 32 bytes
    '''uint32_t'''
    unk0181 = 0 # vertex size
    
    '''uint32_t'''
    unk0182 = 0 # 3
    
    '''uint32_t'''
    unk0183 = 0 # index?
    
    '''uint32_t'''
    unk0184 = 0 # 1. vertex position
    
    '''uint32_t'''
    unk0185 = 0 # 2. ? position
    
    '''uint32_t'''
    unk0186 = 0 # 3. normal position
    
    '''uint32_t'''
    unk0187 = 0 # 4. ? position
    
    '''uint32_t'''
    unk0188 = 0 # 5. ? position
    
    def read_table3_entry (self, f = fopen()):
        self.unk0181 = readLong(f, unsigned)
        self.unk0182 = readLong(f, unsigned)
        self.unk0183 = readLong(f, unsigned)
        self.unk0184 = readLong(f, unsigned)
        self.unk0185 = readLong(f, unsigned)
        self.unk0186 = readLong(f, unsigned)
        self.unk0187 = readLong(f, unsigned)
        self.unk0188 = readLong(f, unsigned)
        return None
        
    

class fmtTMB_Addr:  # 8 bytes
    '''uint32_t'''
    addr = 0 # multiply by 16
    
    '''uint32_t'''
    count = 0
    
    def read (self, f = fopen()):
        self.addr = readLong(f, unsigned)
        self.count = readLong(f, unsigned)
        return None
        
    

class fmtTMB:
    '''uint32_t'''
    type = 0x20424D54
    
    '''uint32_t'''
    unk101 = 0
    
    '''float'''
    unk102 = 0.0
    
    '''fmtTMB_Addr[13]'''
    addrs = []
    
    '''char[64]'''
    textures = []
    
    '''fmtTMB_Entry_0x01[]'''
    boneArray = []
    
    '''fmtTMB_Entry_0x02[]'''
    objArray = []
    
    '''fmtTMB_Entry_0x03[]'''
    mshArray = []
    
    #0x04
    '''fmtTMB_Entry_0x05[]'''
    vertArray = []
    
    '''fmtTMB_Entry_0x06[]'''
    unk0190Array = []
    
    '''uint8_t[]'''
    flagArray = []
    
    '''fmtTMB_Entry_0x08[]'''
    unk0193Array = []
    
    '''uint16_t[]'''
    unk0195Array = []
    
    def readFixedString (self, f = fopen(), len = 0):
        str = ""
        p = ftell(f) + len
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0:
                str += bit.IntAsChar(b)
            else: break
        fseek(f,p, seek_set)
        return str
        
    
    def readFaces(self, pos = 0, count = 0):
        Face_array = []	
        if count > 0:
            face = [0, 1, 2]
            counter = 0
            j = 1
            for j in range(0, len(self.flagArray)):
                face = [face[1], face[2], counter]
                if face[0] >= count or face[1] >= count or face[2] >= count:
                    break
                counter += 1
                if self.flagArray[j + pos] == 0:
                    if bit.And(j, 1):
                        append(Face_array, [face[0], face[2], face[1]])
                    else:
                        append(Face_array, [face[0], face[1], face[2]])
        return Face_array
        
    
    def read (self, f = fopen()):
        
        # get start of file
        pos = ftell(f)
        
        # Read header
        self.type = readLong(f, unsigned)
        self.unk101 = readLong(f, unsigned)
        self.unk102 = readFloat(f)
        
        # Read Block Table
        self.addrs = []
        self.num_addrs = 13
        self.addrs = [fmtTMB_Addr] * self.num_addrs
        
        
        
        
        self.textures = []
        self.boneArray = []
        self.objArray = []
        self.mshArray = []
        self.vertArray = []
        self.unk0190Array = []
        self.flagArray = []
        self.unk0193Array = []
        self.unk0195Array = []
        for i in range(0, self.num_addrs):
            
            
            # seek to table entry
            fseek(f, pos + 12 + i * 8, seek_set)
            
            # Init Array Element
            self.addrs[i] = fmtTMB_Addr()
            
            # Read Entry
            self.addrs[i].read(f)
            
            # Skip if address is null
            if self.addrs[i].addr == 0: continue
            
            # Read Block
            fseek(f,pos + self.addrs[i].addr * 16, seek_set)
            count = self.addrs[i].count
            if count > 0:
                    
                if i == 0x00: # Texture Names
                    self.textures = [str] * count
                    for j in range(0, count):
                        self.textures[j] = self.readFixedString(f, 64)
                        
                        
                    
                elif i == 0x01:  # Bones, Probably...
                    self.boneArray = [fmtTMB_Entry_0x01] * count
                    for j in range(0, count):
                        self.boneArray[j] = fmtTMB_Entry_0x01()
                        self.boneArray[j].read(f)
                            
                        
                    
                elif i == 0x02:  # Object
                    self.objArray = [fmtTMB_Entry_0x02] * count
                    for j in range(0, count):
                        self.objArray[j] = fmtTMB_Entry_0x02()
                        self.objArray[j].read(f)
                            
                        
                    
                elif i == 0x03: 
                    # need to examine other samples
                    pass
                    
                elif i == 0x04:  # Mesh Info
                    self.mshArray = [fmtTMB_Entry_0x04] * count
                    for j in range(0, count):
                        self.mshArray[j] = fmtTMB_Entry_0x04()
                        self.mshArray[j].read(f)
                        #self.mshArray[j].repr
                            
                        
                    
                elif i == 0x05:  # Vertex Positions, hm maybe this used for lookup
                    self.vertArray = [fmtTMB_Entry_0x05] * count
                    for j in range(0, count):
                        self.vertArray[j] = fmtTMB_Entry_0x05()
                        self.vertArray[j].read(f)
                                
                        
                    
                    
                    
                elif i == 0x06:  # Vertices Again
                    
                    count = int(count / 16)
                    if count > 0:
                        self.unk0190Array = [fmtTMB_Entry_0x06] * count
                        for j in range(0, count):
                            self.unk0190Array[j] = fmtTMB_Entry_0x06()
                            self.unk0190Array[j].read(f)
                            
                        
                    
                elif i == 0x07:  # Faces
                    
                    self.flagArray = []
                    self.flagArray = [int] * count
                    for j in range(0, count):
                        self.flagArray[j] = readByte(f, unsigned)
                            
                        
                        
                    
                    
                elif i == 0x08:  # Normals Again
                    count = int(count / 16)
                    if count > 0:
                        self.unk0193Array = [fmtTMB_Entry_0x08] * count
                        for j in range(0, count):
                            self.unk0193Array[j] = fmtTMB_Entry_0x08()
                            self.unk0193Array[j].read(f)
                            
                        
                    
                elif i == 0x09:  # texture corrdinates maybe??
                    count = int(count / 4.0)
                    if count > 0:
                        self.unk0195Array = [[float] * 3] * count
                        for j in range(0, count):
                            self.unk0195Array[j] = [readShort(f, unsigned) / 1024.0, readShort(f, unsigned) / 1024.0, 0.0]
                            
                        
                    
                elif i == 0x0A: 
                    # not present in my sample, need to review more samples
                    pass
                    
                elif i == 0x0B:  # some sort of data stream
                    #fmtTMB_Entry_0x0B
                    pass
                    
                elif i == 0x0C: 
                    # need to examine more samples, not alot data is present at this block
                    pass
            
        return None
                
            
            
        
    
    def build (self, clear_scene = False, mscale = 0.1, buildBones = False):
        
        # ClearScene
        if clear_scene == True: deleteScene(['MESH', 'ARMATURE'])
        
        
        # Loop Through object
        o = None
        t = matrix3(1)
        d = None
        msh = None
        bnsArray = []
        vertices = []
        tvertices = []
        faceArray = []
        faceStart = 0
        j = 1
        v = 1
        uvStart = 0
        for j in range(0, len(self.mshArray)):
            # Mesh
            
            vertices = []
            faceArray = []
            
            # if no vertices,:SKIP
            if self.mshArray[j].unk0168 == 0: continue
            
            # Read Faces
            faceArray = self.readFaces(faceStart, self.mshArray[j].unk0168)
            faceStart += (self.mshArray[j].unk0168 + ((16-(self.mshArray[j].unk0168 % 16)) % 16))
            
            
            # Read Vertices
            vertices = []
            tvertices = []
            vertices = [[float] * 3] * self.mshArray[j].unk0168
            tvertices = [[float] * 3] * self.mshArray[j].unk0168
            
            vp = self.mshArray[j].unk0171 + self.mshArray[j].unk0168 - self.mshArray[j].unk0171
            for v in range(self.mshArray[j].unk0171,  self.mshArray[j].unk0171 + self.mshArray[j].unk0168):
                vertices[v - self.mshArray[j].unk0171] = [self.unk0190Array[v].unk0191[0] * mscale, -self.unk0190Array[v].unk0191[2] * mscale, self.unk0190Array[v].unk0191[1] * mscale]
                
            
            for v in range(0, vp):
                vt = (v + uvStart) % self.mshArray[j].unk0168
                tvertices[v] = [self.unk0195Array[vt][0], self.unk0195Array[vt][1], 0.0]
                
                
                
            uvStart += int(((self.mshArray[j].unk0168 * 4) + ((16-((self.mshArray[j].unk0168 * 4) % 16)) % 16)) / 4.0)
            
            
            # Build Mesh
            msh = mesh(
                vertices=vertices,
                faces=faceArray,
                tverts=[tvertices]
                )
            
            #msh.transform = t
            #append(mdls msh
            
        
        
        
        if buildBones:
            # Build Bones
            for o in self.objArray:
                
                # Bone
                '''
                d = Dummy name:o.name3 boxSize:[0.25, 0.25, 0.25] transform:
                    matrix3 \
                        [o.unk131[1][1], o.unk131[1][2], o.unk131[1][3]] + o.unk131[1][4] \
                        [o.unk131[2][1], o.unk131[2][2], o.unk131[2][3]] + o.unk131[2][4] \
                        [o.unk131[3][1], o.unk131[3][2], o.unk131[3][3]] + o.unk131[3][4] \
                        [o.unk131[4][1], o.unk131[4][2], o.unk131[4][3]] * mscale * o.unk131[4][4]
                    
                d.showLinks = d.showLinksOnly = True
                append(bnsArray d
                '''
            
            i = 1
            par = 1
            pos = [0.0, 0.0, 0.0]
            for i in range(0, len(bnsArray)):
                
                
                par = self.objArray[i].unk0166
                if par > -1:
                    t = bnsArray[i].transform
                    pos = bnsArray[i].position
                    while par > -1:
                        t *= bnsArray[par].transform 
                        pos += bnsArray[par].position
                        
                        
                        par = self.objArray[par].unk0166
                        break
                        
                    bnsArray[i].transform = t
                    #bnsArray[i].position = pos
                    
                    bnsArray[i].parent = bnsArray[self.objArray[i].unk0166] 
        return None
                    
                
                
                

class fmtP2IG:
    '''uint32_t'''
    type = 0x47493250 # P2IG
    
    '''uint32_t'''
    unk001 = 0
    
    '''uint32_t'''
    unk002 = 0
    
    '''uint16_t'''
    unk003 = 0
    
    '''uint16_t'''
    unk004 = 0
    
    '''char[8]'''
    name = ""
    
    '''uint32_t'''
    unk005 = 0
    
    '''uint32_t'''
    unk006 = 0
    
    '''uint16_t'''
    unk007 = 0 # width
    
    '''uint16_t'''
    unk008 = 0 # length
    
    '''uint32_t'''
    unk009 = 0 # type 0x13 = 8bit 0x14 = 4bit?
    
    '''uint32_t'''
    unk010 = 0
    
    '''uint32_t'''
    unk011 = 0
    
    '''uint32_t'''
    unk012 = 0
    
    '''uint32_t'''
    unk013 = 0
    
    '''uint32_t'''
    unk014 = 0
    
    '''uint32_t'''
    unk015 = 0
    
    '''uint32_t'''
    unk016 = 0 # pal pos
    
    '''uint32_t'''
    unk017 = 0 # pal size
    
    '''uint32_t'''
    unk018 = 0 # img pos
    
    '''uint32_t'''
    unk019 = 0 # img size
    
    '''uint32_t'''
    unk020 = 0
    
    '''uint32_t'''
    unk021 = 0
    
    '''uint32_t'''
    unk022 = 0
    
    '''uint32_t'''
    unk023 = 0
    
    '''uint32_t'''
    unk024 = 0
    
    '''uint32_t'''
    unk025 = 0
    
    '''uint32_t'''
    unk026 = 0
    
    '''uint32_t'''
    unk027 = 0
    
    '''uint32_t'''
    unk028 = 0
    
    '''uint32_t'''
    unk029 = 0
    
    '''uint32_t'''
    unk030 = 0
    
    '''uint32_t'''
    unk031 = 0
    
    '''uint8_t[4][]'''
    pal = []
    
    '''uint8_t[]'''
    img = []
    
    '''
        ps2 unswizzle code courtesy of TopazTK,
        while I was working on soul calibur 3
        
        https://forum.xentax.com/viewtopic.php?t=22497
    '''
    
    def readFixedString (self, f = fopen(), len = 0):
        str = ""
        p = ftell(f) + len
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0:
                str += bit.IntAsChar(b)
            else: break
        fseek(f, p, seek_set)
        return str
        
    
    def read (self, f = fopen()):
        
        self.type = readLong(f, unsigned)
        self.unk001 = readLong(f, unsigned)
        self.unk002 = readLong(f, unsigned)
        self.unk003 = readShort(f, unsigned)
        self.unk004 = readShort(f, unsigned)
        self.name = self.readFixedString(f, 8)
        self.unk005 = readLong(f, unsigned)
        self.unk006 = readLong(f, unsigned)
        self.unk007 = readShort(f, unsigned)
        self.unk008 = readShort(f, unsigned)
        self.unk009 = readLong(f, unsigned)
        self.unk010 = readLong(f, unsigned)
        self.unk011 = readLong(f, unsigned)
        self.unk012 = readLong(f, unsigned)
        self.unk013 = readLong(f, unsigned)
        self.unk014 = readLong(f, unsigned)
        self.unk015 = readLong(f, unsigned)
        self.unk016 = readLong(f, unsigned)
        self.unk017 = readLong(f, unsigned)
        self.unk018 = readLong(f, unsigned)
        self.unk019 = readLong(f, unsigned)
        self.unk020 = readLong(f, unsigned)
        self.unk021 = readLong(f, unsigned)
        self.unk022 = readLong(f, unsigned)
        self.unk023 = readLong(f, unsigned)
        self.unk024 = readLong(f, unsigned)
        self.unk025 = readLong(f, unsigned)
        self.unk026 = readLong(f, unsigned)
        self.unk027 = readLong(f, unsigned)
        self.unk028 = readLong(f, unsigned)
        self.unk029 = readLong(f, unsigned)
        self.unk030 = readLong(f, unsigned)
        self.unk031 = readLong(f, unsigned)
        
        # Read Image Data
        count = int(self.unk017 / 4.0)
        self.img = []
        self.pal = []
        if count > 0:
            fseek(f, self.unk016, seek_set)
            
            for i in range(0, count):
                self.pal.append([readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned)])
                
            fseek(f, self.unk018, seek_set)
            if self.unk019 > 0:
                self.img = [int] * self.unk019
                for i in range(0, self.unk019):
                    self.img[i] = readByte(f, unsigned)
        return None
    

class fmtMDL_Asset:
    '''
        this is just an intermediate between the different assets
    '''
    
    '''uint32_t'''
    type = 0
    
    '''fmtTMB'''
    model = None
    
    '''fmtP2IG'''
    texture = None
    
    def read (self, f = fopen(), fsize = 0):
        
        '''
            I include the asset size in the param 'fsize'
            as a precaution since the mdl acts as a file
            container.
        '''
        
        pos = ftell(f) # log current cursor position
        
        self.type = readLong(f, unsigned)
        fseek(f, pos, seek_set) # restore cursor position to start of asset
        
    
        if self.type == 0x20424D54:  # TMB (Model)
            self.model = fmtTMB()
            self.model.read(f)
            self.model.build()
        elif self.type == 0x47493250: # P2IG (Texture)
            self.texture = fmtP2IG()
            self.texture.read(f) # has paring issue
            #self.texture.build() # code from sc3 still needs to be adopted
            pass
        else: 
            print("Assest Unsupported")
        return None
            
            
        
    
    
    
class fmtMDL:
    
    '''uint32_t[]'''
    addrs = [], # address table is padded to 16bytes
    
    '''fmtMDL_Asset[]'''
    asset = [], # being ps2 self.assets are probably padded to 16 as well
    
    def read (self, f = fopen()):
        
        # Reset Arrays
        self.addrs = []
        self.asset = []
        
        # Get File Size
        pos = ftell(f)
        fsize = f.size
        fseek(f, pos, seek_set)
        
        # Read Address Table
        addr = 0
        eariest_addr = fsize
        while ftell(f) < eariest_addr:
            
            # Read Address
            addr = readLong(f, unsigned)
            
            # break if addr is 0
            if addr == 0: break
            
            # Log Address
            self.addrs.append(addr)
            
            # Log addr if its smaller:last addr
            if addr < eariest_addr:
                eariest_addr = addr
                
            
        
        # Get self.asset count from number of valid addresses
        count = len(self.addrs)
        if count > 0:
            
            # Generate a list of unique address, so calculate blocks sizes
            index = -1
            sizes = [fsize] #include the full size to start
            for i in range(0, count):
                # Search sizes array for the address
                index = findItem(sizes, self.addrs[i])
                
                # Not in sizes array, so append(address to it.
                if index == -1:
                    sizes.append(self.addrs[i])
                    
                
            
            # Sort sizes Array
            sizes.sort()
            
            # Dimension Asset Array
            self.asset = [fmtMDL_Asset] * count
            
            # Process Each Asset
            for i in range(0, count):
                
                # Search for ordered address in the sizes array
                index = findItem(sizes, self.addrs[i]) # index up to the next address
                
                #  Initialize Array Element
                self.asset[i] = fmtMDL_Asset()
                
                # Read Asset
                fseek(f, self.addrs[i], seek_set) # set cursor at start of self.asset
                self.asset[i].read(f, sizes[index]) # sizes[index] specifies the length of the self.asset
        return None
                
            
        
def read (file, mscale = 0.1):
    if file != None and file != "":
        
        f = fopen(file, "rb")
        if f != None:
            
            pos = ftell(f)
            
            filetype = readLong(f, unsigned)
            fseek(f, pos, seek_set)
            
            if filetype == 0x20424D54:  # TMB
                tmb = fmtTMB()
                tmb.read(f)
                tmb.build(mscale=mscale)
                
            else:  # Try MDL
                mdl = fmtMDL()
                mdl.read(f)
                
            
            
            fclose(f)
        else: print("Failed to open file")
        
    return None
    


# Callback when file(s) are selected

def kor66tmb_callback(fpath="", files=[], clearScene=True, mscale=0.1):
    if len(files) > 0 and clearScene: deleteScene(['MESH', 'ARMATURE'])
    for file in files:
        read (fpath + file.name, mscale)
    if len(files) > 0:
        #messageBox("Done!")
        return True
    else:
        return False


# Wrapper that Invokes FileSelector to open files from blender
def kor66tmb(reload=False):
    # Un-Register Operator
    if reload and hasattr(bpy.types, "IMPORTHELPER_OT_kor66tmb"):  # print(bpy.ops.importhelper.kor66tmb.idname())

        try:
            bpy.types.TOPBAR_MT_file_import.remove(
                bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_kor66tmb').menu_func_import)
        except:
            print("Failed to Unregister2")

        try:
            bpy.utils.unregister_class(bpy.types.Operator.bl_rna_get_subclass_py('IMPORTHELPER_OT_kor66tmb'))
        except:
            print("Failed to Unregister1")

    # Define Operator
    class ImportHelper_kor66tmb(bpy.types.Operator):

        # Operator Path
        bl_idname = "importhelper.kor66tmb"
        bl_label = "Select File"

        # Operator Properties
        # filter_glob: bpy.props.StringProperty(default='*.jpg;*.jpeg;*.png;*.tif;*.tiff;*.bmp', options={'HIDDEN'})
        filter_glob: bpy.props.StringProperty(default='*.mdl;*.tmb', options={'HIDDEN'}, subtype='FILE_PATH')

        # Variables
        filepath: bpy.props.StringProperty(subtype="FILE_PATH")  # full path of selected item (path+filename)
        filename: bpy.props.StringProperty(subtype="FILE_NAME")  # name of selected item
        directory: bpy.props.StringProperty(subtype="FILE_PATH")  # directory of the selected item
        files: bpy.props.CollectionProperty(
            type=bpy.types.OperatorFileListElement)  # a collection containing all the selected items f filenames

        # Controls
        my_int1: bpy.props.IntProperty(name="Some Integer", description="Tooltip")
        my_float1: bpy.props.FloatProperty(name="Scale", default=0.1, description="Changes Scale of the imported Mesh")
        # my_float2: bpy.props.FloatProperty(name="Some Float point", default = 0.25, min = -0.25, max = 0.5)
        my_bool1: bpy.props.BoolProperty(name="Clear Scene", default=True, description="Deletes everything in the scene prior to importing")

        # Runs when this class OPENS
        def invoke(self, context, event):

            # Retrieve Settings
            try: self.filepath = bpy.types.Scene.kor66tmb_filepath
            except: bpy.types.Scene.kor66tmb_filepath = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.directory = bpy.types.Scene.kor66tmb_directory
            except: bpy.types.Scene.kor66tmb_directory = bpy.props.StringProperty(subtype="FILE_PATH")

            try: self.my_float1 = bpy.types.Scene.kor66tmb_my_float1
            except: bpy.types.Scene.kor66tmb_my_float1 = bpy.props.FloatProperty(default=0.1)

            try: self.my_bool1 = bpy.types.Scene.kor66tmb_my_bool1
            except: bpy.types.Scene.kor66tmb_my_bool1 = bpy.props.BoolProperty(default=False)
            

            # Open File Browser
            # Set Properties of the File Browser
            context.window_manager.fileselect_add(self)
            context.area.tag_redraw()

            return {'RUNNING_MODAL'}

        # Runs when this Window is CANCELLED
        def cancel(self, context):
            print("run bitch")

        # Runs when the class EXITS
        def execute(self, context):

            # Save Settings
            bpy.types.Scene.kor66tmb_filepath = self.filepath
            bpy.types.Scene.kor66tmb_directory = self.directory
            bpy.types.Scene.kor66tmb_my_float1 = self.my_float1
            bpy.types.Scene.kor66tmb_my_bool1 = self.my_bool1

            # Run Callback
            kor66tmb_callback(
                self.directory,
                self.files,
                self.my_bool1,
                self.my_float1
                )

            return {"FINISHED"}

            # Window Settings

        def draw(self, context):

            self.layout.row().label(text="Import Settings")

            self.layout.separator()
            self.layout.row().prop(self, "my_bool1")
            self.layout.row().prop(self, "my_float1")

            self.layout.separator()

            col = self.layout.row()
            col.alignment = 'RIGHT'
            col.label(text="  Author:", icon='QUESTION')
            col.alignment = 'LEFT'
            col.label(text="mariokart64n")

            col = self.layout.row()
            col.alignment = 'RIGHT'
            col.label(text="Release:", icon='GRIP')
            col.alignment = 'LEFT'
            col.label(text="January 3, 2023")

        def menu_func_import(self, context):
            self.layout.operator("importhelper.kor66tmb", text="King of Route 66 (*.mdl, *.tmb)")

    # Register Operator
    bpy.utils.register_class(ImportHelper_kor66tmb)
    bpy.types.TOPBAR_MT_file_import.append(ImportHelper_kor66tmb.menu_func_import)

    # Assign Shortcut key
    # bpy.context.window_manager.keyconfigs.active.keymaps["Window"].keymap_items.new('bpy.ops.text.run_script()', 'E', 'PRESS', ctrl=True, shift=False, repeat=False)

    # Call ImportHelper
    bpy.ops.importhelper.kor66tmb('INVOKE_DEFAULT')


# END OF MAIN FUNCTION ##############################################################


if not useOpenDialog:

    deleteScene(['MESH', 'ARMATURE'])
    
    read (
        "E:\\BackUp\\MyCloud4100\\Coding\\Maxscripts\\File IO\\King of Route 66, The (USA)\\ARIZONA_ARI_BODY\\ARIZONA_ARI_BODY.mdl"
        )
else: kor66tmb(True)


Code also on my github
Thanks, I will keep that in my mind. When I stumbled onto your post by chance, I was hunting for this website: https://letsgradeit.com/review/customwritings/. I am searching for internet guidance since I am not very good at writing essays. This website assisted me in finding the best essay writing services when I searched for that website on Google.

Thanks, I will keep that in my mind.
## Post #21
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-01-11T13:00:33+00:00
- Post Title: Re: King of Route 66 .MDL files

> Reply from AndrewAbdullah ↑Tue Jan 10, 2023 5:14 pm at Tue Jan 10, 2023 5:14 pm
>
> 
Thanks, I will keep that in my mind.

Although blender is my software of choice, i had better results with the max-script.
almost every uv map exports fine except for the 5 main characters.
Ninja ripper will get you all of the textures if you try for severyl rips.
use the cheat file for the debug menu in pcsx2 so you can just render every character there instead of moving to different parts in the game.

EDIT: highway cat rips without a problem. so its just texas hawk, iron bull, soul man and ichiban and some rectangle textures it seems:
## Post #22
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-01-19T11:22:02+00:00
- Post Title: Re: King of Route 66 .MDL files

Is there a known way how to tackle Alpha Channels Like that?
I found that setting transparency threshold to 0.1 seems to Displays Most textures correctly.

I also found Out that the game was based on crazy Taxi....so the .MdL Files might be similar to kor66 ones
