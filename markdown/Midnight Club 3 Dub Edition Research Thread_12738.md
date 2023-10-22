## Post #1
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-02T06:49:12+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

*Moved from Models section*

So, I have been looking through these forums for the past few years on how to extract multiple models from multiple games, it has helped me alot. Especially with my GTA Modding career   

anyway one of the games I have been wanting to extract things from was Midnight club 3... I know there were threads on this site about it back in the mid 2000's but it seems that no one has put really any effort into researching the files other than for the music...

I was wondering if we can get some research into the file formats that are used... I actually conducted some myself, but Im not really smart enough to reverse engineer files... 

so far I was able to extract everything from the main archive on the PSP version and have seperated the cities by folder...

Here is the Atlanta city folder



The folders regarding the time and weather cycles contain a single file: global_lighting.gt
which is made up of these lines of code

```
	color: 0.232352 0.357612 0.548000
}
directional {
	color: 0.936000 0.668901 0.089856
	direction: -0.889713 -0.450294 0.075142
}

```


then you have the .graph files which contains co-ordinates for the textures aswell as the map itself (Really long file)

```
MaxExtents 609.999695	10.814615	946.128052 
Graphs 1
{
	Graph a_graph
	{
		VertexArray 931
		{
			-733.138123	0.149985	224.996307 
			-736.299561	0.149987	228.158539 
			-637.677734	0.149985	326.820007 
			-634.482117	0.150000	323.624847 
			-715.106934	0.149985	206.965118 
			-718.288879	0.149985	210.147095 
			-619.646545	0.149985	308.788818 
			... 
```

then you have the .occlude file which is pretty obvious what it has...

```
num_geoms: 340
num_primitives: 30

;|occluders|boxOccluders|box_0	[0]
verts: 8
activate: 40
sphere: -409.6565552 -36.6345892 424.0878754 129.0808293
-418.4957275	-100	503.6173706
-330.1471558	-100	415.2690735
-418.4957275	26.73082161	503.6173706
-330.1471558	26.73082161	415.2690735
-489.1659546	26.73082161	432.8664551
-401.072937	26.73082161	344.5583801
-489.1659546	-100	432.8664551
-401.072937	-100	344.5583801
edges: 12
```


then there are the .ait files... which contain paths and object placement coords

.ait

```
{
Node 737
	{
		Position -437.101379	-0.000001	-900.352417 
		Normal -0.708640	0.000000	-0.705570 
	}
Node 738
	{
		Position -513.089905	-0.000001	-976.011719 
		Normal -0.708640	0.000000	-0.705570 
	}
Node 739
	{
		Position -386.044067	0.281514	-432.800873 
		Normal 0.708955	-0.002212	-0.705250 
	}
Node 740
	{
		Position -318.834564	0.071816	-499.659149 
		Normal 0.708955	-0.002212	-0.705250 
	}
Node 741
	{
		Position -313.560181	0.150000	-78.123131 
		Normal -0.032571	0.000000	0.999469 
	}
Node 742
	{
		Position -316.227448	0.150000	3.723971 
		Normal -0.032571	0.000000	0.999469 
	}
Node 743
	{
		Position -415.321320	0.150000	-130.042221 
		Normal -0.002003	0.000000	-0.999998 
	}
Node 744
	{
		Position -415.543762	0.150000	-241.106598 
		Normal -0.002003	0.000000	-0.999998 
	}
```


I have not been able to access the .aib files... nor do I have the experience to check em with a hex editor...

the texture folder just has a_shared_particle.tex

anyway moving on...

Here is what is in the props folder...



I have yet to open any of them due to being unfamiliar with the psppck file architecture...

same for the cities themselves




if anyones interested in looking at the psppck files, I can upload one of them (as long as its not against the rules, which I doubt but its always good to be safe and check)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-02T10:21:03+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

As the extension .psppck would imply, I believe it's some kind of a package which holds both the model and the textures for that model.

Interestingly, the models for traffic cars in vehicle folder are stored in a plaintext format (here's part of the va_cranetruck_sh\whl0_h.mesh file):

```
	Skinned 0 
	PosSkin 0 
	Pos 24 { 
		-0.150614	0.475711	0.475832 
		-0.150613	0.475711	-0.475831 
		-0.150613	-0.475941	-0.475832 
		-0.150613	-0.475941	0.475832 
		0.150614	0.475711	-0.475831 
		0.150613	0.475711	0.475832 
		0.150614	-0.475942	0.475831 
		0.150614	-0.475941	-0.475832 
		0.150342	0.000702	-0.474956 
		-0.149259	-0.335341	-0.335766 
		-0.149259	0.000702	-0.474956 
		0.150342	-0.335341	-0.335766 
		-0.149260	-0.474536	0.000283 
		0.150342	-0.474536	0.000283 
		-0.149260	-0.335341	0.336325 
		0.150342	-0.335341	0.336325 
		-0.149260	0.000705	0.475514 
		0.150342	0.000706	0.475513 
		-0.149260	0.336747	0.336324 
		0.150342	0.336748	0.336323 
		-0.149260	0.475941	0.000286 
		0.150342	0.475942	0.000285 
		-0.149260	0.336751	-0.335778 
		0.150342	0.336751	-0.335778 
	}

	Nrm 18 { 
		-1.000000	0.000000	0.000000 
		1.000000	0.000000	0.000000 
...
```
## Post #3
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-04T06:31:18+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

sorry I got distracted trying to fix some model errors while extracting the cities from Driver 2...

right now im trying out a couple texture converters for the .tex files 



and yea, I noticed that too, although I didnt really go through it in greater detail lol... Is there any way we can load the mesh file up into 3DSMax?

actually I will try that and post an update if it works or not
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-04T12:02:33+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

The texture format is more or less the same as in previous games by Angel Studios / Rockstar San Diego. I'm working on a Python plugin for Noesis for importing them. The whole format is documented here: [http://mm2kiwi.apan.is-a-geek.com/index.php?title=TEX](http://mm2kiwi.apan.is-a-geek.com/index.php?title=TEX)



I'll mess around with the model formats later.
## Post #5
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-07T06:09:39+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

> Reply from barti
>
> The texture format is more or less the same as in previous games by Angel Studios / Rockstar San Diego. I'm working on a Python plugin for Noesis for importing them. The whole format is documented here: http://mm2kiwi.apan.is-a-geek.com/index.php?title=TEX



I'll mess around with the model formats later.
alright, I found this earlier which pertains to a program that would be used to read tex files aswell... but anyway let me know how it goes... 
[http://forum.mm2c.com/viewtopic.php?t=1 ... d9f080313c](http://forum.mm2c.com/viewtopic.php?t=1868&postdays=0&postorder=asc&start=15&sid=021da4a34f35e9916a1c14d9f080313c)

also here is the atlanta_dawn_clear.parfileio file I was looking through...

```
parFileIO {
  fog_color 0.173510	0.189537	0.221654 
  fog_start 0.000000 
  fog_end 831.142150 
  fog_threshold 0.000000 
  fog_clamp 0.467000
  lightfog_scale 0.999922 
  indoor_fog_color 0.173510	0.189537	0.221654 
  indoor_fog_start 0.000000 
  indoor_fog_end 831.142150 
  indoor_fog_threshold 0.000000 
  indoor_fog_clamp 0.467800 
  mAmbientTweakRadius 20.000000 
  mAmbientTweakConstant 0.100000 
  mAmbientVehicleModifier 0.839981 
  refl_bk_color 0.000000	0.000000	0.000000	1.000000 
  refl_dist 400.000000 
  light_glow_intensity 0.699909 
  light_glow_size 1.399932 
  flare_on 1 
  flare_intensiry 0.500000 
  flare_size 0.899917 
  flare_distance 1500.000000 
  m_staticLightYOffset 0.449999 
  m_staticLightColor 0.4050000	0.428000	0.440000
  m_ambientScale 0.100 
  mAmbientLight 0.499184	0.499185	0.500122	1.000000 
  mDirectionalRot -157.000000 
  mDirectionalElevation 163.000000 
  mDirectionalLightColor 0.850057	0.641960	0.238247	1.000000 
  m_skylightRot 0.000000 
  m_skylightElevation 90.000000 
  m_drawSkylightPos 0 
  m_skylightColor 0.200000	0.200000	0.229967	1.000000 
  m_useSkylight 0 
  mLightAttenuation 1.000000 
  mLightFalloff 1.000000 
  m_roadShiniess 0.609979 
  m_reflectedObjectColorMod 0.468750	0.468750	0.468750	1.000000 
  m_reflectionWidthMod 3.634041 
  m_reflectionHeightMod 0.479997 
  m_globalLightMod 0.299990 
  Brightness 0.448
  Hue 1.000000 
  Saturation 0.799967 
  Value 1.048
}

```


aswell as atlanta_dawn_clear_hdrparam0.mcfbglowparams

```
mcFbGlowParams {
  m_minLevels 0.452937	0.453142	0.454061	0.000000 
  m_addSmooth 1 
  m_blurRadius 20 
  m_numGaussians 2 
  radius_scale0 0.179998 
  amp0 0.129997 
  radius_scale1 4.500000 
  amp1 0.739998 
  m_baseAtten 1.000000 
  m_horizAlpha 0.124997 
  m_vertAlpha 0.200000 
  m_useFbAlpha 1 
}

```
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-07T10:25:45+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

Alright, here's my Python script. It works just fine with Midnight Club 3, as well as Midtown Madness 2 and Midnight Club Street Racing. I tried to add Midnight Club 2 support as well, but it's not fully functional yet.
Save it as "tex_angelstudios_tex.py" and put it in the "plugins/pyton" folder in Noesis.

```
# Reference from http://mm2kiwi.apan.is-a-geek.com/index.php?title=TEX
# and http://forum.xentax.com/viewtopic.php?f=10&p=9670

from inc_noesis import *

import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Midtown Madness / Midnight Club", ".tex")
	noesis.setHandlerTypeCheck(handle, texCheckType)
	noesis.setHandlerLoadRGBA(handle, texLoadRGBA)
	return 1

def texCheckType(data):
	return 1

def texLoadRGBA(data, texList):
	tex = AGETexture(NoeBitStream(data))
	texList.append(tex.parseTexture())
	return 1

class AGETexture:

	def __init__(self, reader):
		self.reader = reader

	def parseTexture(self):
		texWidth   = self.reader.readUShort()
		texHeight  = self.reader.readUShort()
		texType    = self.reader.readShort()
		texMips    = self.reader.readShort()
		texUnknown = self.reader.readShort()
		texFlag1   = self.reader.readUByte()
		texFlag2   = self.reader.readUByte()
		texFlag3   = self.reader.readUByte()
		texFlag4   = self.reader.readUByte()
				
		if texType == 1: # P8
			palMap = self.reader.readBytes(256*4)
			pixMap = self.reader.readBytes(texWidth * texHeight)
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 8, "b8g8r8p8")
		if texType == 14: # PA8
			palMap = self.reader.readBytes(256*4)
			pixMap = self.reader.readBytes(texWidth * texHeight)
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 8, "b8g8r8a8")
		if texType == 15: # P4_MC
			palMap = self.reader.readBytes(16*4)
			pixMap = self.reader.readBytes(int(texWidth * texHeight / 2))
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 4, "b8g8r8p8")
		if texType == 16: # PA4_MC
			palMap = self.reader.readBytes(16*4)
			pixMap = self.reader.readBytes(int(texWidth * texHeight / 2))
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 4, "b8g8r8a8")
		if texType == 17: # RGB888
			pixMap = self.reader.readBytes(texWidth * texHeight * 3)
			pixData = rapi.imageDecodeRaw(pixMap, texWidth, texHeight, "r8g8b8")
		if texType == 18: # RGBA8888
			pixMap = self.reader.readBytes(texWidth * texHeight * 4)
			pixData = rapi.imageDecodeRaw(pixMap, texWidth, texHeight, "r8g8b8a8")
		# Midnight Club 2 support (textype 26 not fully functional)
		if texType == 22: # DXT1
			pixMap = self.reader.readBytes(int(texWidth * texHeight * 4 / 8))
			pixData = rapi.imageDecodeDXT(pixMap, texWidth, texHeight, noesis.NOESISTEX_DXT1)
		if texType == 26: # DXT5
			pixMap = self.reader.readBytes(int(texWidth * texHeight * 4 / 4))
			pixData = rapi.imageDecodeDXT(pixMap, texWidth, texHeight, noesis.NOESISTEX_DXT5)
			
		pixData = rapi.imageFlipRGBA32(pixData, texWidth, texHeight, 0, 1)
		return NoeTexture("tex", texWidth, texHeight, pixData, noesis.NOESISTEX_RGBA32)
```
## Post #7
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-08T22:45:00+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

python script works beautifully on my end lol

just bought the remixed version of Midnight Club 3 on PSN and am going to try to get the files by using my friends modded PS3... 

how is the model extraction going?
## Post #8
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-10T11:17:29+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

.mesh extraction is coming along nicely:


But I couldn't make anything out of the .psppck files. Maybe they're compressed - I tried aluigi's compression scanner and it didn't find anything interesting.
## Post #9
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-13T02:42:52+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

> Reply from barti
>
> .mesh extraction is coming along nicely:


But I couldn't make anything out of the .psppck files. Maybe they're compressed - I tried aluigi's compression scanner and it didn't find anything interesting.
yea I think the psppck files are compressed... maybe with a similar structure to a normal pck file... 

*Edit* I can pretty much confirm thay psppck is just a compressed pck file



I got the files from Dub Edition Remix for PS2 and am extracting everything in the dats with Iripper



anyway, keep up the good work
## Post #10
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-04-14T22:32:56+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

As I don't have as much time to work on the .mesh files as I'd like, here's the MaxScript I wrote a few days ago. It doesn't support automatic texturing, or positioning of objects - it's definitely possible to do that manually though. Feel free to modify it, etc.

```
if g != undefined then
(
	Vertex_Array = #()
	Normals_Array = #()
	UV_Array = #()
	UV2_Array = #()
	Colors_Array = #()
	Adjuncts_Array = #()
	Face_Array = #()
	MatID_Array = #()
	
	f = openFile g
	
	skipToString f "Pos "
	numVerts = readValue f
	readline f
	
	for i = 1 to numVerts do
	(
		verts = filterstring (readline f) " \t"
		append Vertex_Array [-verts[1] as float, verts[3] as float, verts[2] as float]
	)
	
	skiptostring f "Nrm "
	numNorms = readValue f
	readline f
	
	for i = 1 to numNorms do
	(
		norms = filterstring (readline f) " \t"
		append Normals_Array [-norms[1] as float, norms[3] as float, norms[2] as float]
	)
	
	skiptostring f "Cpv "
	numColors = readValue f
	readline f
	
	for i = 1 to numColors do
	(
		colors = filterstring (readline f) " \t"
		append Colors_Array [colors[1] as float, colors[2] as float, colors[3] as float, colors[4] as float]
	)
	
	skiptostring f "Tex0 "
	numUVs = readValue f
	readline f
	
	for i = 1 to numUVs do
	(
		uvs = filterstring (readline f) " \t"
		append UV_Array [uvs[1] as float, uvs[2] as float,0]
	)
	
	skiptostring f "Tex1 "
	numUV2s = readValue f
	
	if numUV2s > 0 do
	(
		for i = 1 to numUV2s do
		(
			uvs = filterstring (readline f) " \t"
			append UV2_Array [uvs[1] as float, uvs[2] as float,0]
		)
	)
	
	skiptostring f "Adj "
	numAdjs = readValue f
	readline f
	
	for i = 1 to numAdjs do
	(
		pos = filterstring (readline f) " \t"
		nrm = filterstring (readline f) " \t"
		c0 = filterstring (readline f) " \t"
		t0 = filterstring (readline f) " \t"
		append Adjuncts_Array [1+pos[2] as number,1+nrm[2] as number,1+c0[2] as number,1+t0[2] as number]
	)
	
	skiptostring f "Mtl "
	numMats = readValue f
	
	for i = 1 to numMats do
	(
		skiptostring f "Name "
		matName = readValue f
		
		skiptostring f "Prim "
		numPrims = readValue f
		
		for j = 1 to numPrims do
		(
			skiptostring f "Type "
			primType = readline f
			skiptostring f "Idx "
			numIndices = readValue f
			skiptostring f "{ "
			
			local tristrip = #()
			for k = 1 to numIndices do append tristrip (readValue f)
			
			case primtype of
			(
				default: print "Unsupported primtype " + primType + ". Contact me."
				"TRISTRIP":
				(
					for j=1 to tristrip.count - 2 do
					(
					   fa = tristrip[j]
					   fb = tristrip[j+1]
					   fc = tristrip[j+2]
					   if ((fa!=fb) and (fa!=fc) and (fc!=fb)) do
					   (
						  if mod j 2 == 0  then append Face_Array [fc+1,fb+1,fa+1]
						  else append Face_Array [fb+1,fc+1,fa+1]
						  
						  append MatID_Array i
					   )
					)
				)
				"TRISTRIP2":
				(
					for j=1 to tristrip.count - 2 do
					(
					   fa = tristrip[j]
					   fb = tristrip[j+1]
					   fc = tristrip[j+2]
					   if ((fa!=fb) and (fa!=fc) and (fc!=fb)) do
					   (
						  if mod j 2 == 0  then append Face_Array [fb+1,fc+1,fa+1]
						  else append Face_Array [fc+1,fb+1,fa+1]
						  
						  append MatID_Array i
					   )
					)
				)
			)
		)
	)
	
	msh = mesh name:(getFilenameFile g)
	
	setNumVerts msh Adjuncts_Array.count
	setNumTVerts msh Adjuncts_Array.count
	setNumCPVVerts msh Adjuncts_Array.count
	setNumFaces msh Face_Array.count
	buildTVFaces msh
	
	for i = 1 to Face_Array.count do
	(
		setFace msh i Face_Array[i]
		setTVFace msh i Face_Array[i]
	)
	meshop.setMapSupport msh 0 true
	meshop.setMapSupport msh 1 true
	
	for i = 1 to Adjuncts_Array.count do
	(
		setvert msh i Vertex_Array[Adjuncts_Array[i][1]]
		setNormal msh i Normals_Array[Adjuncts_Array[i][2]]
		setVertColor msh i Colors_Array[Adjuncts_Array[i][3]]
		setTVert msh i UV_Array[Adjuncts_Array[i][4]]
	)
	
	for i = 1 to Face_Array.count do
	(
		setFaceMatID msh i (MatID_Array[i])
	)
	update msh
)

```
## Post #11
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-21T16:37:29+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

sorry for the long break without a reply, I got stuck studying for a test today aswell as spent time with my family...

anyway im still here and I will be taking a look at this later on today
## Post #12
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-04-28T09:22:36+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

ok so I wanted to test something out and I was able to replace some of the ingame tracks with my own music...

also I was searching through the files and figured out where the text strings were stored for menus and dialog...



they are stored in strtbl files which I assume are similar to GTA's GXT file...



I tried opening with Hex Workshop and this is what I got...
## Post #13
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2016-03-28T16:50:56+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

That's impressive work! The script works flawless~ Shame that there isn't support for multiple materials and object positioning yet 

Would anyone look into the compressed pck files in MCLA?
## Post #14
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2016-06-23T11:05:43+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

> Reply from RacingFreak
>
> That's impressive work! The script works flawless~ Shame that there isn't support for multiple materials and object positioning yet 

Would anyone look into the compressed pck files in MCLA?
dont got it. Just wanted the MC3 maps since I have the game and the maps are in a similar design to what a GTA map would look like
## Post #15
- Username: deadly202
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 09, 2016 8:30 am
- Post datetime: 2016-10-09T00:55:42+00:00
- Post Title: Midnight Club 3 Dub Edition Research Thread

I can't seem to extract the assets file properly in MC3, ps2 version with iripper. I checked the files with with hxd and they're all blank files (most of them). I then tried Game Extractor and it seems to work but the filenames and folders are messed up. Is there something i missed or forgot to do?
## Post #16
- Username: blenderbach
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 05, 2017 12:57 pm
- Post datetime: 2017-08-06T17:07:56+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from barti
>
> .mesh extraction is coming along nicely:


But I couldn't make anything out of the .psppck files. Maybe they're compressed - I tried aluigi's compression scanner and it didn't find anything interesting.

By the way could you please send me all the files you extracted from the dat file please? I also wrote the same thing as a private message so please help me.
## Post #17
- Username: Spade115
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 29, 2019 4:21 am
- Post datetime: 2019-09-28T20:25:09+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Hi, signed up to this group because of this post. I was looking at trying to find the Vehicle codes rendering for Midnight Club 3 and a few other games. Reading this thread you all do some amazing work with the coding 0.0 real cool and awesome to see it can be done
## Post #18
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-10-30T03:04:37+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

I thought by now this place would be filled with like, how to rip the map or things like that...
## Post #19
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-12-04T23:04:24+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Nvm i got some news!

San Diego WIP!



And the Nissan Skyline too!



Here another one using solid materials as in none but a general view of the model 




As for how i got these, is a Burnout 3 and revenge situation of ripping, what do i mean? Well, xbox og version, Model researcher and some Hex knowledge!, is quite hard to understand but it took me a while to figure out, also cuz a friend called Xenn helped me in this, without that guy i wouldn't be here with San Diego and other cars that i have in my list to do but not done yet
## Post #20
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-12-04T23:19:26+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

I wanna add a note to this!, as for the maps, they use some weird type of mapping, is like GTA type of mapping, the coordinates of all the models are in the .xbck file (Xbox format i assume), but thing is idk how to like decode that or see what is the position alongside the rotation and general scaling, Another thing is about textures which.... using TextureFinder din't help cuz, thing is, the textures are up at the start but they have no actual names, so i needed to came up with some ideas in that or like names for em, also ofc, props are separated as in they are in another file 

[http://www.mediafire.com/file/255jb0r66 ... s.rar/file](http://www.mediafire.com/file/255jb0r66o8sggm/San+Diego+Files.rar/file)


Here a link of the files of san diego!

or well the .xbck files that is needed or what i think is enough to show, another thing to point out is that there is like multiple copys of san diego with ones having names like

sd_midnight_cloudy
sd_midnight_rainy
sd_midnight_clear
sd_dawn_clear

and more in the line

only tools would be texturefinder and Model researcher as the main prioritys

forgot to say this! this goes the same case with the cars!
## Post #21
- Username: darkvaytor
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 22, 2020 6:42 am
- Post datetime: 2020-12-22T19:25:31+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from Ness ↑Sat Dec 05, 2020 7:04 am at Sat Dec 05, 2020 7:04 am
>
> 
Nvm i got some news!

San Diego WIP!



And the Nissan Skyline too!



Here another one using solid materials as in none but a general view of the model 




As for how i got these, is a Burnout 3 and revenge situation of ripping, what do i mean? Well, xbox og version, Model researcher and some Hex knowledge!, is quite hard to understand but it took me a while to figure out, also cuz a friend called Xenn helped me in this, without that guy i wouldn't be here with San Diego and other cars that i have in my list to do but not done yet

Which file(s) and what parameters in modelResearcher did you use to get the model for the skyline? I want to extract some other cars, if it worked for the skyline then something similar may work for all the other vehicle models.
## Post #22
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2020-12-23T07:38:05+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from darkvaytor ↑Wed Dec 23, 2020 3:25 am at Wed Dec 23, 2020 3:25 am
>
> 
Ness wrote: ↑Sat Dec 05, 2020 7:04 am
Nvm i got some news!

San Diego WIP!



And the Nissan Skyline too!



Here another one using solid materials as in none but a general view of the model 




As for how i got these, is a Burnout 3 and revenge situation of ripping, what do i mean? Well, xbox og version, Model researcher and some Hex knowledge!, is quite hard to understand but it took me a while to figure out, also cuz a friend called Xenn helped me in this, without that guy i wouldn't be here with San Diego and other cars that i have in my list to do but not done yet


Which file(s) and what parameters in modelResearcher did you use to get the model for the skyline? I want to extract some other cars, if it worked for the skyline then something similar may work for all the other vehicle models.

as for yer question, is kinda hard to say, but what the friend that told me about it that is called Xenn,showed me that is was like this, and there's a lot to cover!
aside of Model Researcher you will want things like TextureFinder too for the textures in here, which, MC3 only uses like the Misc and some other extra materials around
and i will say, get a program like HxD or any hex viewer so you can search nodes and other things




every car will have this thing Called Shell as their base, if they have _h is cuz that means the highest LOD, and if you search that shell node again you will get the same thing some offsets later but with _m, that being the medium LOD, which you will go with the h LOD instead, note that those CD CD CD CD are important to remember cuz, after that row, the next offset down it? is where the vertices begin





See the last CD CD? after that last CD CD you get the vertices start, as for uvs you always add a +14, so the offset of vertices of 0x174210 becomes 0x174224

The Padding in UVs are 20, vertices is always 16, note that, to know when you reached the last vertex you will see and spot a dot in the middle of the viewer, which, that means ya reached the limit!, so if i put 2003 count in the vertices a dot will be shown in the center, and after that you gotta -1 that and make it 2002, same with uvs

as for faces?



Here, they are after some rows of code ahead, you might get MR just throwing errors but, is just a keep adding up a number till it shows up and works, in other words if you are at 0x181d10 then the last one alongside the 0 make it higher till it gets the correct start of the faces, this time being 0x181db0




First model being the base of the headlights!



here uvs!, note that for me is flipped so when it exports it will look like that in blender, autodesk, or any 3d program of yer choice



it should look like this, oh! also as for textures those are actually upside down too which, you can fix em with just flipping em vertically to make em look fine again, another thing being is... there is no clear way of how this game stops loading certain model to load other, what i mean is, next you will get is the headlights itself but, another part, in other words, they are separated in the set in materials so, every split you see? is a new set of the model being loaded in, so the headlights stopped at 280 count of faces, and if i make it up to 281



you will get a stretched uv, that means, a new set of polys are loading with their own material set there, and that means, next set that you get? is the new offset, so that will be 0x181fe0, remember, use this properly and take this as a type of how to do it

that's all i will say in this for now, if you want dm me and i tell you in somewhere like discord the whole process, imma leave some extra notes about the cars here now too which are, indentifying things like, bumpers, skirts, tailights, spoilers, hoods, etc

tk_tk_lod_tk_h = Trunk
tk_tk_lod_tk_h_h_decal_tk = Trunk badge (For things like the DUB logo you can buy in the game)
tk_splr_splr_stk_sky02_splr_stk_sky02 = Spoiler (depending of the car file you choose you will get a different name, like if it was idk the eclipse, instead of sky02 you would see something like splr_stk_eclipse)
Speaking of spoilers, after that, you will get a row of new spoilers, those being the custom spoilers you can buy in the game, and after you get the last spoiler ripped, you will get hoods, and so on
hd_hd_stk_sky02_hd = Hood
ss_ss_stk_sky02_ss_stk_sky02 = Skirts
bumf_bumf_stk_sky02_bumf_stk_sky02 = Front Bumper
bumr_bumr_stk_sky02_bumr = Rear Bumper
tl_tl_stk_sky02_tl_stk_sky02 = Tailights
lodgroup_hlod_hl_glass = Headlight Glass
lodgroup_hlod_windows = Windows
lodgroup_hlod_interior = The interior of the car
lodgroup_hlod_decals = Decals of the car

Note that, the sky02 is just the node and main name of what car is in the file, other cars will change that ofc

another note, things like, exhausts, rims, brakes, and more are in other files that do the same things to rip em, but they kinda use different paddings, again, possible to rip but it can be confusing
## Post #23
- Username: darkvaytor
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 22, 2020 6:42 am
- Post datetime: 2020-12-25T23:28:49+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Thanks to the info from Ness I was able to write a python script that can convert most of the .mesh.xbck files to obj files and does it without artifacts by figuring out what some parts of the headers mean. I'll get around to making a script for the base models of the cars eventually.
[https://github.com/TahmidAlam-git/MC3_extraction_tools](https://github.com/TahmidAlam-git/MC3_extraction_tools)

```
import os
import sys
import math
import struct


def convert(fname):

    '''
    example: vroot_bmpf_bone_bumpf_stk_350z_bumpf_stk_350z_geo.mesh.xbck
    nissan 350z stock front bumper mesh, beginning header
    header part 1
    always useless starting 8 lines
    00 9A 9E 82 16 00 00 00 01 00 00 00 B0 3F 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    header part 2
    70 B6 5D 00 00 00 71 1C 09 00 00 00 20 9A 9E 82
                            ^^ ^^ ^^ ^^
    how many numbers there are at the end of this part of the header(before the multi CD padding)
    This also means how many pieces the model is split up into (useful for faces)
    44 9A 9E 82 00 00 00 00 1C 9B 9E 82 E0 D2 9E 82 <= always skip
    17 00 05 00 05 00 14 00 18 00 01 00 13 00 05 00 <= 8 numbers here
    19 00 CD CD CD CD CD CD CD CD CD CD CD CD CD CD <= 1 number here, 9 total
    header part 3
    09 00 00 00 <= value represents how many "sets" there are
    sets are 24 bytes long, ends with CD CD
    70 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    7C D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    88 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    94 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    A0 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    AC D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    B8 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    C4 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    D0 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    header part 4
    last part of header always ends with 4 00, + CD padding if neeeded
    01 00 00 00 30 9B 9E 02 00 00 00 00 CD CD CD CD CD CD CD CD
    '''


    hfile = open(fname, "rb")

    l_len = 16

    # header part 1
    hfile.read(8 * l_len)

    # header part 2
    hfile.read(8)
    pieces = int.from_bytes(hfile.read(4), byteorder='little')
    hfile.read(4)
    hfile.read(l_len + math.ceil(pieces / 8) * l_len)

    # header part 3
    sets_num = int.from_bytes(hfile.read(4), byteorder='little')
    hfile.read(sets_num * 24)

    # header part 4
    hfile.read(12)
    if hfile.tell() % 16 != 0:
        hfile.read(16 - (hfile.tell() % 16))

    vertices = []
    faces = []
    UVs = []

    # TODO: find the amount of vertices from header
    # get the vertices and UVs
    while 1:
        x = struct.unpack('f', hfile.read(4))[0]
        y = struct.unpack('f', hfile.read(4))[0]
        z = struct.unpack('f', hfile.read(4))[0]

        if float(format(x, '.4f')) == float(format(y, '.4f')) == float(format(z, '.4f')) == 0.0000:
            hfile.seek(-12, 1)
            break

        vertices.append((x, y, z))

        hfile.read(8)

        uva = struct.unpack('f', hfile.read(4))[0]
        uvb = struct.unpack('f', hfile.read(4))[0]
        UVs.append((uva, uvb))


    '''
    faces header example
    the model is split up into multiple pieces
    
                                       offset + amount
    01 00 00 00 00 00 1E 00 00 00 00 00 : 000 + 030
    01 00 00 00 1E 00 97 00 00 00 00 00 : 030 + 151
    01 00 00 00 B5 00 68 00 00 00 00 00 : 181 + 104
    01 00 00 00 1D 01 90 00 00 00 00 00 : 285 + 144
    01 00 00 00 AD 01 13 00 00 00 00 00 : 429 + 019
    01 00 00 00 C0 01 40 01 00 00 00 00 : 448 + 320 
    01 00 00 00 00 03 1B 00 00 00 00 00 : 768 + 027
    01 00 00 00 1B 03 4E 01 00 00 00 00 : 795 + 334
    01 00 00 00 69 04 91 00 00 00 00 00 : 1129 + 145
    CD CD CD CD
    '''

    # Get the ranges for the pieces of the models
    model_ranges = []
    for x in range(pieces):
        hfile.read(4)
        model_ranges.append((int.from_bytes(hfile.read(2), byteorder='little'),
                            int.from_bytes(hfile.read(2), byteorder='little')))
        hfile.read(4)


    # Skip CDs
    if hfile.tell() % 16 != 0:
        hfile.read(16 - (hfile.tell() % 16))

    # Get shorts of the faces
    shorts = []
    for x in range(model_ranges[-1][0] + model_ranges[-1][1]):
        shorts.append(int.from_bytes(hfile.read(2), byteorder='little') + 1)

    # Get the faces
    for piece in model_ranges:
        forward = True
        for x in range(piece[0] + 2, piece[0] + piece[1]):

            if forward:
                faces.append((shorts[x - 2], shorts[x - 1], shorts[x - 0]))
                forward = False
            else:
                faces.append((shorts[x], shorts[x - 1], shorts[x - 2]))
                forward = True

    hfile.close()

    # Make obj file
    if os.path.exists("./" + fname + '.obj'):
        os.remove("./" + fname + '.obj')

    obj = open(fname + '.obj', 'a')

    for vert in vertices:
        obj.write('v ' + str(vert[0]) + ' ' + str(vert[1]) + ' ' + str(vert[2]) + '\n')

    obj.write('\n')

    for uv in UVs:
        obj.write('vt ' + str(uv[0]) + ' ' + str(uv[1]) + '\n')

    obj.write('\n')

    for f in faces:
        obj.write('f ' + str(f[0]) + ' ' + str(f[1]) + ' ' + str(f[2]) + '\n')

    obj.close()



if len(sys.argv) >= 2 and sys.argv[-1].endswith("mesh.xbck"):
    convert(sys.argv[-1])
else:
    print("invalid file")
```



Edit: Updated the git repo, there is now a .exe that will convert ALL models of a vehicle to obj files, meaning both the base model and customization parts.

Edit 2: now added support to extract models from the .xbck map files for San Diego
## Post #24
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2021-01-01T09:32:07+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from darkvaytor ↑Sat Dec 26, 2020 7:28 am at Sat Dec 26, 2020 7:28 am
>
> 
Thanks to the info from Ness I was able to write a python script that can convert most of the .mesh.xbck files to obj files and does it without artifacts by figuring out what some parts of the headers mean. I'll get around to making a script for the base models of the cars eventually.
https://github.com/TahmidAlam-git/MC3_extraction_tools
Code: Select all#!/usr/bin/python3
import os
import sys
import math
import struct


def convert(fname):

    '''
    example: vroot_bmpf_bone_bumpf_stk_350z_bumpf_stk_350z_geo.mesh.xbck
    nissan 350z stock front bumper mesh, beginning header
    header part 1
    always useless starting 8 lines
    00 9A 9E 82 16 00 00 00 01 00 00 00 B0 3F 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
    header part 2
    70 B6 5D 00 00 00 71 1C 09 00 00 00 20 9A 9E 82
                            ^^ ^^ ^^ ^^
    how many numbers there are at the end of this part of the header(before the multi CD padding)
    This also means how many pieces the model is split up into (useful for faces)
    44 9A 9E 82 00 00 00 00 1C 9B 9E 82 E0 D2 9E 82 <= always skip
    17 00 05 00 05 00 14 00 18 00 01 00 13 00 05 00 <= 8 numbers here
    19 00 CD CD CD CD CD CD CD CD CD CD CD CD CD CD <= 1 number here, 9 total
    header part 3
    09 00 00 00 <= value represents how many "sets" there are
    sets are 24 bytes long, ends with CD CD
    70 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    7C D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    88 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    94 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    A0 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    AC D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    B8 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    C4 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    D0 D2 9E 82 C1 5E 80 00 59 00 1C 00 02 4A 04 00
    00 00 00 00 01 00 CD CD
    header part 4
    last part of header always ends with 4 00, + CD padding if neeeded
    01 00 00 00 30 9B 9E 02 00 00 00 00 CD CD CD CD CD CD CD CD
    '''


    hfile = open(fname, "rb")

    l_len = 16

    # header part 1
    hfile.read(8 * l_len)

    # header part 2
    hfile.read(8)
    pieces = int.from_bytes(hfile.read(4), byteorder='little')
    hfile.read(4)
    hfile.read(l_len + math.ceil(pieces / 8) * l_len)

    # header part 3
    sets_num = int.from_bytes(hfile.read(4), byteorder='little')
    hfile.read(sets_num * 24)

    # header part 4
    hfile.read(12)
    if hfile.tell() % 16 != 0:
        hfile.read(16 - (hfile.tell() % 16))

    vertices = []
    faces = []
    UVs = []

    # TODO: find the amount of vertices from header
    # get the vertices and UVs
    while 1:
        x = struct.unpack('f', hfile.read(4))[0]
        y = struct.unpack('f', hfile.read(4))[0]
        z = struct.unpack('f', hfile.read(4))[0]

        if float(format(x, '.4f')) == float(format(y, '.4f')) == float(format(z, '.4f')) == 0.0000:
            hfile.seek(-12, 1)
            break

        vertices.append((x, y, z))

        hfile.read(8)

        uva = struct.unpack('f', hfile.read(4))[0]
        uvb = struct.unpack('f', hfile.read(4))[0]
        UVs.append((uva, uvb))


    '''
    faces header example
    the model is split up into multiple pieces
    
                                       offset + amount
    01 00 00 00 00 00 1E 00 00 00 00 00 : 000 + 030
    01 00 00 00 1E 00 97 00 00 00 00 00 : 030 + 151
    01 00 00 00 B5 00 68 00 00 00 00 00 : 181 + 104
    01 00 00 00 1D 01 90 00 00 00 00 00 : 285 + 144
    01 00 00 00 AD 01 13 00 00 00 00 00 : 429 + 019
    01 00 00 00 C0 01 40 01 00 00 00 00 : 448 + 320 
    01 00 00 00 00 03 1B 00 00 00 00 00 : 768 + 027
    01 00 00 00 1B 03 4E 01 00 00 00 00 : 795 + 334
    01 00 00 00 69 04 91 00 00 00 00 00 : 1129 + 145
    CD CD CD CD
    '''

    # Get the ranges for the pieces of the models
    model_ranges = []
    for x in range(pieces):
        hfile.read(4)
        model_ranges.append((int.from_bytes(hfile.read(2), byteorder='little'),
                            int.from_bytes(hfile.read(2), byteorder='little')))
        hfile.read(4)


    # Skip CDs
    if hfile.tell() % 16 != 0:
        hfile.read(16 - (hfile.tell() % 16))

    # Get shorts of the faces
    shorts = []
    for x in range(model_ranges[-1][0] + model_ranges[-1][1]):
        shorts.append(int.from_bytes(hfile.read(2), byteorder='little') + 1)

    # Get the faces
    for piece in model_ranges:
        forward = True
        for x in range(piece[0] + 2, piece[0] + piece[1]):

            if forward:
                faces.append((shorts[x - 2], shorts[x - 1], shorts[x - 0]))
                forward = False
            else:
                faces.append((shorts[x], shorts[x - 1], shorts[x - 2]))
                forward = True

    hfile.close()

    # Make obj file
    if os.path.exists("./" + fname + '.obj'):
        os.remove("./" + fname + '.obj')

    obj = open(fname + '.obj', 'a')

    for vert in vertices:
        obj.write('v ' + str(vert[0]) + ' ' + str(vert[1]) + ' ' + str(vert[2]) + '\n')

    obj.write('\n')

    for uv in UVs:
        obj.write('vt ' + str(uv[0]) + ' ' + str(uv[1]) + '\n')

    obj.write('\n')

    for f in faces:
        obj.write('f ' + str(f[0]) + ' ' + str(f[1]) + ' ' + str(f[2]) + '\n')

    obj.close()



if len(sys.argv) >= 2 and sys.argv[-1].endswith("mesh.xbck"):
    convert(sys.argv[-1])
else:
    print("invalid file")


Edit: Updated the git repo, there is now a .exe that will convert ALL models of a vehicle to obj files, meaning both the base model and customization parts.

Edit 2: now added support to extract models from the .xbck map files for San Diego

What a good day to be alive, note that same goes with others like Atlanta and Detroit too, just i din't check those yet myself

as for the maps too doe, i do know or guess that, between the vertices and uvs with the faces there should be some positionating code between it, cuz, i noticed that some use like a long set of CD CD there, which that means like a duplicate is found and also as a type of way to say positionate it here and rotations and scaling and all of that, issue is, idk what is what
## Post #25
- Username: darkvaytor
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 22, 2020 6:42 am
- Post datetime: 2021-01-01T20:43:48+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from Ness ↑Fri Jan 01, 2021 5:32 pm at Fri Jan 01, 2021 5:32 pm
>
> 

What a good day to be alive, note that same goes with others like Atlanta and Detroit too, just i din't check those yet myself

as for the maps too doe, i do know or guess that, between the vertices and uvs with the faces there should be some positionating code between it, cuz, i noticed that some use like a long set of CD CD there, which that means like a duplicate is found and also as a type of way to say positionate it here and rotations and scaling and all of that, issue is, idk what is what

Yeah I've noticed that as well, I'm not sure yet because I haven't tested it but this is what I think so far

```
01 00 00 00 C8 D4 D6 81 
            ^^^^^^^^^^^
            not sure what is means yet

header
01 00 00 00 E0 D4 D6 01 00 00 00 00 CD CD CD CD CD CD CD CD CD CD CD CD 
      ^^^^^ ^^^^^ ^^^^^
     |z pos|x pos|y pos|

For the below, each ###FF is "rotation" for each vertex in the model for (x,y,z), I believe this is the case because the number of ###FF is the same as the number of vertices.
15 12 10 FF 15 12 10 FF 15 12 10 FF 15 12 10 FF 
15 12 10 FF 15 12 10 FF 15 12 10 FF 15 12 10 FF 
15 12 10 FF 15 12 10 FF E8 EB FF FF D9 F1 FF FF 
A5 B7 C1 FF 2E 29 25 FF 5E 64 66 FF 37 39 39 FF 
2E 29 25 FF DF E6 FF FF 63 70 75 FF D5 F1 FF FF
```
## Post #26
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2021-01-01T21:16:15+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from darkvaytor ↑Sat Jan 02, 2021 4:43 am at Sat Jan 02, 2021 4:43 am
>
> 
Ness wrote: ↑Fri Jan 01, 2021 5:32 pm

What a good day to be alive, note that same goes with others like Atlanta and Detroit too, just i din't check those yet myself

as for the maps too doe, i do know or guess that, between the vertices and uvs with the faces there should be some positionating code between it, cuz, i noticed that some use like a long set of CD CD there, which that means like a duplicate is found and also as a type of way to say positionate it here and rotations and scaling and all of that, issue is, idk what is what


Yeah I've noticed that as well, I'm not sure yet because I haven't tested it but this is what I think so far
Code: Select allheader
01 00 00 00 C8 D4 D6 81 
            ^^^^^^^^^^^
            not sure what is means yet

header
01 00 00 00 E0 D4 D6 01 00 00 00 00 CD CD CD CD CD CD CD CD CD CD CD CD 
      ^^^^^ ^^^^^ ^^^^^
     |z pos|x pos|y pos|

For the below, each ###FF is "rotation" for each vertex in the model for (x,y,z), I believe this is the case because the number of ###FF is the same as the number of vertices.
15 12 10 FF 15 12 10 FF 15 12 10 FF 15 12 10 FF 
15 12 10 FF 15 12 10 FF 15 12 10 FF 15 12 10 FF 
15 12 10 FF 15 12 10 FF E8 EB FF FF D9 F1 FF FF 
A5 B7 C1 FF 2E 29 25 FF 5E 64 66 FF 37 39 39 FF 
2E 29 25 FF DF E6 FF FF 63 70 75 FF D5 F1 FF FF

interesting, by far this might help in rebuilding the map or like, if i think about like fixing the positions, then this might come in handy, but tbh, i only need mostly the scaling in this situation cuz, i know in certain areas parts of the road change scaling or like are let's say 1.050 of scaling in the Y section, ya know what i mean, idk if GTA ever did that or like ever did change of scalings, considering that this game is just kinda like GTA in terms of how they make their maps, but they don't use an IDE and IPL thing, but seems like that is already built inside the xbck of the map, just that we gotta figure out how to decode this stuff, tbh if is possible, i will start ripping Or Tokyo Or detroit or atlanta and i will try that myself when ya get the Postionating, rotation and Scaling ripped, another thing i do wonder doe, if is possible to figure out the real names of the textures inside the xbck?, also cuz those begin first always, but, they don't have any names when i see HxD, maybe they do the same thing of the Postions rotations and scaling but in a different way, so far i just decided to call some things things like from burnout or like, if is a grass texture, i will call it SD_Grass1, as in  SanDiego_Grass and the number being the different texture of the grass that i will get

i still wish i knew how to decode all of that or like understand what things mean what, at least getting to model rip is one step closer to getting all of this decrypted and in our hands
## Post #27
- Username: blenderbach
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 05, 2017 12:57 pm
- Post datetime: 2021-01-02T16:19:17+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Apparently, upon downloading the Executable, it says it's a Trojan Virus. Is it really a virus?
## Post #28
- Username: darkvaytor
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 22, 2020 6:42 am
- Post datetime: 2021-01-02T18:13:36+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from blenderbach ↑Sun Jan 03, 2021 12:19 am at Sun Jan 03, 2021 12:19 am
>
> 
Apparently, upon downloading the Executable, it says it's a Trojan Virus. Is it really a virus?

It probably says that because it's an unsigned executable, not a trojan virus. Also, download the latest version, the last version I had up actually ended up breaking the program.
## Post #29
- Username: blenderbach
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 05, 2017 12:57 pm
- Post datetime: 2021-01-23T03:33:23+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

New Information from Blender Bach!
This is awesome!
I have Extracted the ASSETS.DAT file from Midnight Club 3 DUB Edition REMIX.
Today, I was roaming around, and came across a file called "errlog.txt" located in ASSETS.DAT/vehicle

In the file you can see this 

This is an error log created by Rockstar back when they were making the game! 
In here we can see that the textures were originally .JPGs and .TIFs! 
They were then converted to the .TEX format.

We also see that the 3D Models were originally .MBs which is a Maya Binary Project File (3D Model)
Then they were converted to the .MESH format.

Another text file located in ASSETS.DAT called "xboxrscdone.txt" contained some other very interesting info 

In it, we can see the directories of the folders that were used back when the game was being made.

Yet another text file in the same location by the name "vehiclesexported.txt" had some more info


All files are attached in this message! 
(https://cdn.discordapp.com/attachments/ ... errlog.txt)
(https://cdn.discordapp.com/attachments/ ... scdone.txt)
(https://cdn.discordapp.com/attachments/ ... ported.txt)

Hopefully this helps!   
 -Blender Bach The CGI Guy
## Post #30
- Username: murilofreitasg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 08, 2021 11:12 pm
- Post datetime: 2021-02-08T16:55:27+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from barti ↑Tue Apr 07, 2015 6:25 pm at Tue Apr 07, 2015 6:25 pm
>
> 
Alright, here's my Python script. It works just fine with Midnight Club 3, as well as Midtown Madness 2 and Midnight Club Street Racing. I tried to add Midnight Club 2 support as well, but it's not fully functional yet.
Save it as "tex_angelstudios_tex.py" and put it in the "plugins/pyton" folder in Noesis.
Code: Select all# Midtown Madness / Midnight Club .TEX
# Reference from http://mm2kiwi.apan.is-a-geek.com/index.php?title=TEX
# and http://forum.xentax.com/viewtopic.php?f=10&p=9670

from inc_noesis import *

import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Midtown Madness / Midnight Club", ".tex")
	noesis.setHandlerTypeCheck(handle, texCheckType)
	noesis.setHandlerLoadRGBA(handle, texLoadRGBA)
	return 1

def texCheckType(data):
	return 1

def texLoadRGBA(data, texList):
	tex = AGETexture(NoeBitStream(data))
	texList.append(tex.parseTexture())
	return 1

class AGETexture:

	def __init__(self, reader):
		self.reader = reader

	def parseTexture(self):
		texWidth   = self.reader.readUShort()
		texHeight  = self.reader.readUShort()
		texType    = self.reader.readShort()
		texMips    = self.reader.readShort()
		texUnknown = self.reader.readShort()
		texFlag1   = self.reader.readUByte()
		texFlag2   = self.reader.readUByte()
		texFlag3   = self.reader.readUByte()
		texFlag4   = self.reader.readUByte()
				
		if texType == 1: # P8
			palMap = self.reader.readBytes(256*4)
			pixMap = self.reader.readBytes(texWidth * texHeight)
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 8, "b8g8r8p8")
		if texType == 14: # PA8
			palMap = self.reader.readBytes(256*4)
			pixMap = self.reader.readBytes(texWidth * texHeight)
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 8, "b8g8r8a8")
		if texType == 15: # P4_MC
			palMap = self.reader.readBytes(16*4)
			pixMap = self.reader.readBytes(int(texWidth * texHeight / 2))
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 4, "b8g8r8p8")
		if texType == 16: # PA4_MC
			palMap = self.reader.readBytes(16*4)
			pixMap = self.reader.readBytes(int(texWidth * texHeight / 2))
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 4, "b8g8r8a8")
		if texType == 17: # RGB888
			pixMap = self.reader.readBytes(texWidth * texHeight * 3)
			pixData = rapi.imageDecodeRaw(pixMap, texWidth, texHeight, "r8g8b8")
		if texType == 18: # RGBA8888
			pixMap = self.reader.readBytes(texWidth * texHeight * 4)
			pixData = rapi.imageDecodeRaw(pixMap, texWidth, texHeight, "r8g8b8a8")
		# Midnight Club 2 support (textype 26 not fully functional)
		if texType == 22: # DXT1
			pixMap = self.reader.readBytes(int(texWidth * texHeight * 4 / 8))
			pixData = rapi.imageDecodeDXT(pixMap, texWidth, texHeight, noesis.NOESISTEX_DXT1)
		if texType == 26: # DXT5
			pixMap = self.reader.readBytes(int(texWidth * texHeight * 4 / 4))
			pixData = rapi.imageDecodeDXT(pixMap, texWidth, texHeight, noesis.NOESISTEX_DXT5)
			
		pixData = rapi.imageFlipRGBA32(pixData, texWidth, texHeight, 0, 1)
		return NoeTexture("tex", texWidth, texHeight, pixData, noesis.NOESISTEX_RGBA32)

Every time i try to use the script this message appears to me, can you help me solve it? I'm working on a hud mod to use the textures but this is complicating me
## Post #31
- Username: danny19901
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 14, 2021 8:33 am
- Post datetime: 2021-04-14T00:46:55+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

I just signed up after finding this thread & Forum im currently working on a few things for this game 1ST is a HD Texture Mod as PCSX2-EX supports Texture dumping & Replacing 

After Dumping nearly 5000 Textures i took a different approach and found Textures.DAT assuming the Textures where in there my issue i have is i found .PPF & .IAN files in the extraction 

Going a huge guess these .PPF files are possibly the Sky Boxes 
with HUDMAP also

these .IAN files are in the cutscenes im assuming Race start and few little in game stuff as files are tiny 

anyway does anyone have a list of tools they recommend right now the textures are getting AI Upscaled for PCSX2 and when done im happy enough to share but i guarentee the textures ive dumped so far won't be all of them as i was dumping with PCSX2 to begin with

Hopefully one day can make a PC Port of the game 

(These are from Midnight Club 3 Dub Edition Remix PS2)
## Post #32
- Username: blenderbach
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 05, 2017 12:57 pm
- Post datetime: 2021-07-31T03:01:18+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from murilofreitasg ↑Tue Feb 09, 2021 12:55 am at Tue Feb 09, 2021 12:55 am
>
> 
barti wrote: ↑Tue Apr 07, 2015 6:25 pm
Alright, here's my Python script. It works just fine with Midnight Club 3, as well as Midtown Madness 2 and Midnight Club Street Racing. I tried to add Midnight Club 2 support as well, but it's not fully functional yet.
Save it as "tex_angelstudios_tex.py" and put it in the "plugins/pyton" folder in Noesis.
Code: Select all# Midtown Madness / Midnight Club .TEX
# Reference from http://mm2kiwi.apan.is-a-geek.com/index.php?title=TEX
# and http://forum.xentax.com/viewtopic.php?f=10&p=9670

from inc_noesis import *

import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Midtown Madness / Midnight Club", ".tex")
	noesis.setHandlerTypeCheck(handle, texCheckType)
	noesis.setHandlerLoadRGBA(handle, texLoadRGBA)
	return 1

def texCheckType(data):
	return 1

def texLoadRGBA(data, texList):
	tex = AGETexture(NoeBitStream(data))
	texList.append(tex.parseTexture())
	return 1

class AGETexture:

	def __init__(self, reader):
		self.reader = reader

	def parseTexture(self):
		texWidth   = self.reader.readUShort()
		texHeight  = self.reader.readUShort()
		texType    = self.reader.readShort()
		texMips    = self.reader.readShort()
		texUnknown = self.reader.readShort()
		texFlag1   = self.reader.readUByte()
		texFlag2   = self.reader.readUByte()
		texFlag3   = self.reader.readUByte()
		texFlag4   = self.reader.readUByte()
				
		if texType == 1: # P8
			palMap = self.reader.readBytes(256*4)
			pixMap = self.reader.readBytes(texWidth * texHeight)
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 8, "b8g8r8p8")
		if texType == 14: # PA8
			palMap = self.reader.readBytes(256*4)
			pixMap = self.reader.readBytes(texWidth * texHeight)
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 8, "b8g8r8a8")
		if texType == 15: # P4_MC
			palMap = self.reader.readBytes(16*4)
			pixMap = self.reader.readBytes(int(texWidth * texHeight / 2))
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 4, "b8g8r8p8")
		if texType == 16: # PA4_MC
			palMap = self.reader.readBytes(16*4)
			pixMap = self.reader.readBytes(int(texWidth * texHeight / 2))
			pixData = rapi.imageDecodeRawPal(pixMap, palMap, texWidth, texHeight, 4, "b8g8r8a8")
		if texType == 17: # RGB888
			pixMap = self.reader.readBytes(texWidth * texHeight * 3)
			pixData = rapi.imageDecodeRaw(pixMap, texWidth, texHeight, "r8g8b8")
		if texType == 18: # RGBA8888
			pixMap = self.reader.readBytes(texWidth * texHeight * 4)
			pixData = rapi.imageDecodeRaw(pixMap, texWidth, texHeight, "r8g8b8a8")
		# Midnight Club 2 support (textype 26 not fully functional)
		if texType == 22: # DXT1
			pixMap = self.reader.readBytes(int(texWidth * texHeight * 4 / 8))
			pixData = rapi.imageDecodeDXT(pixMap, texWidth, texHeight, noesis.NOESISTEX_DXT1)
		if texType == 26: # DXT5
			pixMap = self.reader.readBytes(int(texWidth * texHeight * 4 / 4))
			pixData = rapi.imageDecodeDXT(pixMap, texWidth, texHeight, noesis.NOESISTEX_DXT5)
			
		pixData = rapi.imageFlipRGBA32(pixData, texWidth, texHeight, 0, 1)
		return NoeTexture("tex", texWidth, texHeight, pixData, noesis.NOESISTEX_RGBA32)


Every time i try to use the script this message appears to me, can you help me solve it? I'm working on a hud mod to use the textures but this is complicating me

My apologies for the late response! The reason it is not working is because you used "iRipper" to rip the .dat files. It turns out that iRipper doesn't really work! It completely corrupts the data, therefore, the script cannot read the .tex files as they are corrupted. You must extract the dat files using "ar_extract" Here's the link. [https://cdn.discordapp.com/attachments/ ... xtract.exe](https://cdn.discordapp.com/attachments/794784418106703873/794811236322770964/ar_extract.exe)

Also, I already extracted every single Midnight Club 1 (Street Racing), Midnight Club 2, and Midnight Club 3/DUB Edition Remix Texture! I will be soon uploading them to "Archive.org"
## Post #33
- Username: MidnightClub3 Freak
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 3:59 am
- Post datetime: 2021-09-04T20:06:47+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

hey! its so amazing things you are guys doing here. Im 3d printing cars from games but i cant open .PCK or .MESH in blende 2:79B.

can anyone pleeeaaasseee help me? thank you!!
## Post #34
- Username: darkvaytor
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 22, 2020 6:42 am
- Post datetime: 2021-09-08T17:22:28+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from MidnightClub3 Freak ↑Sun Sep 05, 2021 4:06 am at Sun Sep 05, 2021 4:06 am
>
> 
hey! its so amazing things you are guys doing here. Im 3d printing cars from games but i cant open .PCK or .MESH in blende 2:79B.

can anyone pleeeaaasseee help me? thank you!!

kind of a mess to setup and extract but I can do it for you if you'd like. Any car(s) you'd like in particular? (can't do bikes or police cars as of now)
## Post #35
- Username: blenderbach
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 05, 2017 12:57 pm
- Post datetime: 2021-12-04T06:18:36+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

I have already extracted all the busses!
## Post #36
- Username: MidnightClub3 Freak
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 3:59 am
- Post datetime: 2021-12-31T15:53:42+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

That would be amazing!! I only want cars. Can i contact you on Facebook or somewhere where is easier to text? XD

@darkvaytor
## Post #37
- Username: darkvaytor
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 22, 2020 6:42 am
- Post datetime: 2022-04-16T21:56:28+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from MidnightClub3 Freak ↑Fri Dec 31, 2021 11:53 pm at Fri Dec 31, 2021 11:53 pm
>
> 
That would be amazing!! I only want cars. Can i contact you on Facebook or somewhere where is easier to text? XD

@darkvaytor

Apologies for such a long wait, I wanted to make a script to extract all vehicles, but it was taking too long. Of the cars I was able to extract, at least 95% of their parts should be extracted correctly. I only did some basic checks to make sure the models were fine, so if there's something wrong let me know. [https://mega.nz/file/f35EUD7b#KUKVq_Y5S ... zee5yaxs24](https://mega.nz/file/f35EUD7b#KUKVq_Y5Sw_ztnw1v9qiGh-z9nyTK-wAqzee5yaxs24)
## Post #38
- Username: Zanza
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 20, 2022 11:56 pm
- Post datetime: 2022-04-20T15:59:50+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Can you take out the vinyls too? I need a pair of the Graphix class
## Post #39
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2022-04-23T10:28:08+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

How to extract/convert files in .pck format?
There are many with this extension. It's confusing.
## Post #40
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2022-04-23T10:37:18+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Also, I already extracted every single Midnight Club 1 (Street Racing), Midnight Club 2, and Midnight Club 3/DUB Edition Remix Texture! I will be soon uploading them to "Archive.org" Can't find it. Too bad. People say lots of things when the day is long.
## Post #41
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2022-05-11T12:45:23+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from Zanza ↑Wed Apr 20, 2022 11:59 pm at Wed Apr 20, 2022 11:59 pm
>
> 
Can you take out the vinyls too? I need a pair of the Graphix class

You need to extract the files (assets.dat). Not sure, but I think vinyls can be extracted with similar methods.
Check this video (you can watch without sound, as there is nothing being said):
[https://m.youtube.com/watch?v=LD7Ts6uV8ZE](https://m.youtube.com/watch?v=LD7Ts6uV8ZE)

Also, player vehicles use shared textures.
## Post #42
- Username: busbycm2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 19, 2022 12:18 am
- Post datetime: 2022-05-18T16:20:37+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Sorry if this in the wrong spot.  I am looking for help with someone who may know how to mod Midnight Club 3 Dub  Edition Remix to allow 16 players on LAN instead of 8. Email me [busbycm2@yahoo.com](mailto:busbycm2@yahoo.com).  Thanks!
## Post #43
- Username: Drake1234
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 03, 2022 3:02 am
- Post datetime: 2022-06-07T11:20:16+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from tempaccount555 ↑Wed May 11, 2022 8:45 pm at Wed May 11, 2022 8:45 pm
>
> 
Zanza wrote: ↑Wed Apr 20, 2022 11:59 pm
Can you take out the vinyls too? I need a pair of the Graphix class


You need to extract the files (assets.dat). Not sure, but I think vinyls can be extracted with similar methods.
Check this video (you can watch without sound, as there is nothing being said):
https://m.youtube.com/watch?v=LD7Ts6uV8ZE

Also, player vehicles use shared textures.
Can I get the 1999 Dodge Charger R/T Concept? The file you gave doesn't have it.
## Post #44
- Username: HibbySkippy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 10, 2022 3:07 am
- Post datetime: 2022-06-09T19:11:15+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from darkvaytor ↑Sun Apr 17, 2022 5:56 am at Sun Apr 17, 2022 5:56 am
>
> 
MidnightClub3 Freak wrote: ↑Fri Dec 31, 2021 11:53 pm
That would be amazing!! I only want cars. Can i contact you on Facebook or somewhere where is easier to text? XD

@darkvaytor


Apologies for such a long wait, I wanted to make a script to extract all vehicles, but it was taking too long. Of the cars I was able to extract, at least 95% of their parts should be extracted correctly. I only did some basic checks to make sure the models were fine, so if there's something wrong let me know. https://mega.nz/file/f35EUD7b#KUKVq_Y5S ... zee5yaxs24

Hi, I just joined this thread. Is it possible for me to ask for models in the Remix version of the game, as there are some extra cars that are not included in the normal version? I would love to use the model of Nissan Sport Concept but couldn't find a way to export it out.
## Post #45
- Username: RaxxyRax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 01, 2022 8:22 pm
- Post datetime: 2022-07-01T14:08:10+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

Hi everyone

So I've been trying to extract the "complete" assets from the xbck files, in particular the ones related to the cars' 3d models and the city models, ideally complete with UVs, textures and world position, and although I've made some progress I could definitely need some tips. (if you wanna team up feel free to hmu on Discord @"big yeet#9631" or otherwise - next step will be decompiling it with Ghidra and porting it to Unreal Engine) 

For instance, as for the good news I noticed that textures are stored directly into the xbck files with a DXT3 compression. Here's an example with sd_dawn_clear.xbck.



However when looking into cars files with an hex editor to see if I could make a script, they seemed to have a different structure from the car parts files that the available scripts support AFAIK (no wonder why they didn't work) and I couldn't find a way to get the coordinates and size of the stored textures:



The map files are also yet different from both, although there is the number present in the part files but I'm not sure what it could represent since there is no CD delimitation. They also store all the textures in the beginning so I need to figure out how each mesh file is assigned to which texture and how their "texture lookup" function works.



Also as for car files and ModelResearcher, frankly I wonder how the Mudkip guy managed to do it (doubt he would still be active in here after all this time) cause when I tried using his method with a different car I could only get the vertices, but faces and UVs were a no-go. Also I couldn't find anything about rims anywhere (stock or not)
## Post #46
- Username: MatiTheMudkip
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jan 23, 2018 4:35 am
- Post datetime: 2022-07-20T08:44:37+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from RaxxyRax ↑Fri Jul 01, 2022 10:08 pm at Fri Jul 01, 2022 10:08 pm
>
> 
Hi everyone

So I've been trying to extract the "complete" assets from the xbck files, in particular the ones related to the cars' 3d models and the city models, ideally complete with UVs, textures and world position, and although I've made some progress I could definitely need some tips. (if you wanna team up feel free to hmu on Discord @"big yeet#9631" or otherwise - next step will be decompiling it with Ghidra and porting it to Unreal Engine) 

For instance, as for the good news I noticed that textures are stored directly into the xbck files with a DXT3 compression. Here's an example with sd_dawn_clear.xbck.



However when looking into cars files with an hex editor to see if I could make a script, they seemed to have a different structure from the car parts files that the available scripts support AFAIK (no wonder why they didn't work) and I couldn't find a way to get the coordinates and size of the stored textures:



The map files are also yet different from both, although there is the number present in the part files but I'm not sure what it could represent since there is no CD delimitation. They also store all the textures in the beginning so I need to figure out how each mesh file is assigned to which texture and how their "texture lookup" function works.



Also as for car files and ModelResearcher, frankly I wonder how the Mudkip guy managed to do it (doubt he would still be active in here after all this time) cause when I tried using his method with a different car I could only get the vertices, but faces and UVs were a no-go. Also I couldn't find anything about rims anywhere (stock or not)

Funny timing, and been a while, tho i learned this from a dude called Xenn that knew how to rip these, and so far i only got as far as, as for things like the map, only the models and assigning the textures by looking at the models ingame, but even then still struggling to see how positions, rotation and scaling works in these files, as for car models it's been a while since i did those but is rather simple and you get the hang of it if ya get to see how is done
## Post #47
- Username: DeathWrench
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 09, 2021 5:23 pm
- Post datetime: 2023-01-04T07:25:13+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

I recently found out that the soundtracks for both [Remix](https://nfssoundtrack.com/3dubremix/) and [Dub Edition](https://nfssoundtrack.com/3dub/) are different with Remix having a lot of songs missing. Curious whether or not these songs from Dub Edition can be modded back into Remix somehow.
## Post #48
- Username: MidnightClub3 Freak
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 3:59 am
- Post datetime: 2023-04-09T18:46:44+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

> Reply from darkvaytor ↑Thu Sep 09, 2021 1:22 am at Thu Sep 09, 2021 1:22 am
>
> 
MidnightClub3 Freak wrote: ↑Sun Sep 05, 2021 4:06 am
hey! its so amazing things you are guys doing here. Im 3d printing cars from games but i cant open .PCK or .MESH in blende 2:79B.

can anyone pleeeaaasseee help me? thank you!!


kind of a mess to setup and extract but I can do it for you if you'd like. Any car(s) you'd like in particular? (can't do bikes or police cars as of now)

Hello. Havent been here like year. Thank you alot if you can do it for me :') can you text me on instagram. Because notifications     IG: _shadeless
## Post #49
- Username: icxcone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 11, 2023 2:00 am
- Post datetime: 2023-10-12T09:58:23+00:00
- Post Title: Re: Midnight Club 3 Dub Edition Research Thread

What save edited texture .dds as?    "DXT5 = ARGB 8 bpp | interpolated alpha" or "DXT5_NM XY 8 bpp | using DXT5"??? help i want vouge tires.
