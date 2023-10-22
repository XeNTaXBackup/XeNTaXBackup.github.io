## Post #1
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2015-05-20T16:10:10+00:00
- Post Title: Help with a3x Format needed

I've got an addon model for the Aras 360 Accident Reconstruction software that I'm trying to get the mesh out from. I'm a model builder and have some experience with 3D modelling and printing, but when it comes to reverse engineering I'm still a complete noob and many threads and tutorials here have been very helpful so far. I'm only trying to get the mesh imported to Noesis, I don't care for textures or anything else.

Here's the file: [http://www.mediafire.com/download/mvk9j ... n_1973.a3x](http://www.mediafire.com/download/mvk9jybdb6sqg58/Buick_Centurion_1973.a3x)

So far I've found the Vert Count at 0xF4 and the vertices starting at 0xF8 stored in Little Endian Floats together with the normals. The Face Count for this file can be found at 0x1A50FC and the Face Indexes start right after that together with what I think is UV data (?). I've tried writing a Python importer and thanks to chrrox' tutorial I believe I managed to get the basics going. Not elegant of course, but I can get the vertices into Noesis if I leave the Face data untouched. What I can't get my head around is the Face Indexes bundled together with the other data. I've been trying a few things and been on Google to understand better but the logic still eludes me. I think there might be a simple solution if you know what you're doing but with Python I'm just not there yet. It's only one mesh and I'm not sure if I'm even gonna use it, but it puzzles me. So before I spend too much time trying to figure it all out by myself maybe someone might have a quick look and steer me in the right direction.

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Aras 360", ".a3x")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "a3x"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 8:
      return 0
   if bs.readBytes(8).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   bs.seek(0xf4, NOESEEK_ABS) 
   VCount = bs.read("i")
   print(VCount)
   pos = bs.tell()
   print(pos)
   bs.seek(0x1a50fc, NOESEEK_ABS) 
   FCount = bs.read("i")
   print(FCount)
   pos = bs.tell()
   print(pos)
   bs.seek(0xf8, NOESEEK_ABS) 

   VertBuff = bs.readBytes(VCount[0] * 0x18)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 24, 0)
   rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 24, 12)
   rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
   pos = bs.tell()
   print(pos)

   bs.seek(0x1a5100, NOESEEK_ABS) 

   FaceBuff = bs.readBytes(FCount[0] * 0x18)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 24, 0)
   rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 24, 12)
   rapi.rpgCommitTriangles(VertBuff, noesis.RPGEODATA_USHORT, FCount[0], noesis.RPGEO_TRIANGLE_STRIP, 1)
   pos = bs.tell()
   print(pos)


   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
   
   rapi.rpgClearBufferBinds()   
   return 1
```
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-20T18:39:35+00:00
- Post Title: Help with a3x Format needed

I could be wrong, but I don't see any UV data near the face indices. Each face structure is 24 bytes, and I think the remaining data is more likely to be material IDs or something like that. So I wrote a script for 3DS Max that's capable of loading the mesh, but I haven't tried finding the UVs yet.
## Post #3
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2015-05-20T19:28:03+00:00
- Post Title: Help with a3x Format needed

Wow, that was fast and very helpful! Your script works like a charm.


> Reply from barti
>
>  Each face structure is 24 bytes, and I think the remaining data is more likely to be material IDs or something like that.

That was my initial thought too but I just didn't get it to work and changed my suspicions. It's good that I posted here then and got a sensible reply. Now I know that it was my lacking Python skills, and not so much a lack of understanding the file structure.

Now that there's a script, here's the link to the Aras model exchange page: [http://www.aras360.com/downloads/model-exchange.html](http://www.aras360.com/downloads/model-exchange.html)
It's not much, but maybe of some use to someone.

And... not to forget, thanks, barti!
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-20T20:18:19+00:00
- Post Title: Help with a3x Format needed

You're welcome   

Also I have the file format mostly figured out at this point - there are no UVs, but there are colors and parts. Two of the values after fa, fb and fc are the material ID and part ID respectively.
I'm still trying to figure out how to read the colors, since they're looking pretty funky right now. Also the script is quite bloated and I'm working on optimizing it.
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-21T08:05:29+00:00
- Post Title: Help with a3x Format needed

Colors are fixed now:


But this format still has an annoying design problem I'll never understand - there's lots of redundant vertices, so the mesh can't be smoothed correctly.

I know that you can use Weld with a very low threshold to remedy this in some way, but it completely butchers the normals in many cases.

If someone knows of an algorithm to get rid of the redundant vertices, let me know.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-21T08:43:03+00:00
- Post Title: Help with a3x Format needed

> Reply from barti
>
> If someone knows of an algorithm to get rid of the redundant vertices, let me know.don't know about an algo.
Maybe dividing up in submeshes can help:



Buick_Centurion_1973_submeshes.JPG (61.61 KiB) Viewed 64 times


(First I thought it's just the different LODs, but seems it's not.)

(hex2obj creates a submesh every 500 faces but one might fiddle around to get better "cuts")

btw: nice finding with the colors
## Post #7
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2015-05-21T12:51:57+00:00
- Post Title: Help with a3x Format needed

It's a bit of a relief to see that you guys are finding the same "weirdness" in the file. The data seemed all pretty straight forward from the looks of it. I've actually begun analyzing the file using hex to obj, but I had an old version, so I butchered it into "submeshes" to get the facecount down. Now I've got a bit of a better understanding what was going on. It's all new to me, but it's good to see that I wasn't completely off track.

By the way, shakotay, in your tutorial it says 0x3981 - 0xE84 = 0x2B39 at some point. If you've got a bit of experience it's easy to spot the error, but for a beginner that might be impossible to understand.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-21T13:26:12+00:00
- Post Title: Help with a3x Format needed

> Reply from barreiros
>
> By the way, shakotay, in your tutorial it says 0x3981 - 0xE84 = 0x2B39 at some point. If you've got a bit of experience it's easy to spot the error, but for a beginner that might be impossible to understand.thank you very much for reporting. Yeah, it's 0xE48.

Would give you 3 thx if I could.  

What tells me this about my tutorial? 
a) nobody is reading it
or
b) I confused hundreds of trustful beginners. What a shame!
## Post #9
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2015-05-21T17:45:01+00:00
- Post Title: Help with a3x Format needed

Well, you've got one reader now for sure. I think it's a cool tool for beginners because it does not just show you what a number represents but what that number actually does. With scripting you can build in errors without noticing while getting the numbers right. With HextoObj you get an immediate response if your numbers are right. That's how I learned the basics, but maybe should have picked a smaller file to begin with.

Anyway, I'm quite satisfied right now, had that file for a year now and it always intrigued me, now I know what's in it. Maybe I'll try to get my Noesis importer going to learn the basics of Python better. Also tried to load an older file with the maxscript and it doesn't work, the structure seems similar though. There's a bit to do and much to learn for me. Anybody want to stick around that's fine, of course, but the intial request hast been fulfilled. So thanks again, I probably would't have gotten there without the information here and generally in this forum.
## Post #10
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-21T19:38:03+00:00
- Post Title: Help with a3x Format needed

I've decided to release what I have so far. This script will load the mesh with colors, separate them into parts etc. but the smoothing problem still remains.
It's mostly a straightforward format, with a chunk-like structure. But it's not a polished script, and some guesswork involved based on just one mesh, so that may be why it doesn't load every mesh.

```

fn readUnicodeStr bstrm len =
(
	str = ""
	for x = 1 to len do str += bit.intasChar(readshort bstrm #unsigned)
	return str
)

if fA3X != undefined then
(
	f = fopen fA3X "rb"
	clearlistener()
	
	fArr=#()
	nArr=#()
	vArr=#()
	tArr=#()
	mArr=#()
	
	fseek f 0xF4 #seek_set
	vertCount = readlong f
	
	for i = 1 to vertCount do
	(
		vx = readfloat f
		vy = readfloat f
		vz = readfloat f
		nx = readfloat f
		ny = readfloat f
		nz = readfloat f
		
		append vArr [vx,vy,vz]
		append nArr [nx,ny,nz]
	)
	
	unk = readlong f
	unk = readlong f
	unk = readlong f
	unk = readlong f
	structSize = readlong f
	faceCount = readlong f
	
	for i = 1 to faceCount do
	(
		fa = readlong f
		fb = readlong f
		fc = readlong f
		matID  = readlong f
		partID = readlong f
		unk = readlong f
		
		if fArr[partID+1] == undefined do fArr[partID+1] = #()
		if mArr[partID+1] == undefined do mArr[partID+1] = #()
		append fArr[partID+1] [fa+1,fb+1,fc+1]
		append mArr[partID+1] (matID+1)
	)

	unk = readlong f
	unk = readlong f
	unk = readlong f
	unk = readlong f
	structSize = readlong f
	colorCount = readlong f
	
	mm = multimaterial numsubs:colorCount
	
	for i = 1 to colorCount do
	(
		mm[i] = standard showInViewport:true Name:(i as string)
		
		fseek f 16 #seek_cur
		--mm[i].ambient  = Color (255*readfloat f) (255*readfloat f) (255*readfloat f) (255*readfloat f)
		
		cx = readfloat f; cy = readfloat f; cz = readfloat f; cw = readfloat f
		mm[i].diffuse  = Color (255*cx) (255*cy) (255*cz) (255*cw)
		
		fseek f 16 #seek_cur
		--mm[i].specular = Color (255*readfloat f) (255*readfloat f) (255*readfloat f) (255*readfloat f)
		
		fseek f 20 #seek_cur
	)
	
	unk = readlong f
	unk = readlong f
	unk = readlong f
	unk = readlong f
	structSize = readlong f
	partsCount = readlong f
	
	for i = 1 to partsCount do
	(
		unk = readlong f
		partName = readUnicodeStr f ((structSize-4)/2)
		
		msh = mesh vertices:vArr faces:fArr[i] name:partName
		meshop.deleteIsoVerts msh -- load all vertices and remove those unused by part, somewhat inefficient but I can't think of a better way right now
		centerPivot msh
		msh.material = mm
		
		for j = 1 to fArr[i].count do setFaceMatID msh j mArr[i][j]
	)
	
	fclose f
)
else
(
	clearlistener()
	messageBox "No file was selected." title:"A3X Importer"
)
```
