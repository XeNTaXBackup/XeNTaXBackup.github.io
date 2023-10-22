## Post #1
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-13T16:23:02+00:00
- Post Title: Sudden Attack - Noesis Script Creation

So I've been working on a Noesis script for Sudden Attack (I saw AceWell edited a script for it previously on zenhax, but it doesn't work for every model so I wanted to do it so most of them worked, and also so it gives me experience with Noesis scripts) and I have used the video tutorial that mariokart64n had explaining how he made a script for a Monopoly model. However this tutorial doesn't cover UVs or possibly submeshes (the file I originally tested this on has no submeshes, but there are other files that do), so I was wondering if someone could assist me on how I would get them working?
I looked at AceWell's edited script and tried to edit some lines in there to see if UVs work in my script, I'm really not sure I added them correctly or even wrote in the numbers where needed correctly.

Below is the script I have in progress:

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Sudden Attack", ".ltb")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	noesis.logPopup()
	return 1

def noepyCheckType(data):
    return 1
	
class ltb_format:
	def __init__(self, data):
		self.vertex_count = 0
		self.face_count = 0
		self.vertArray = []
		self.faceArray = []
		self.setUVs = []
	def ReadFromFile(self, f):
		f.seek(0xA9, NOESEEK_ABS)
		self.vertex_count = f.readUInt()
		self.face_count = f.readUInt()
		self.vertArray = [ NoeVec3() ] * self.vertex_count
		self.faceArray = [ 0 ] * (self.face_count * 3)
		#vertBuff = f.readBytes(self.vertex_count * 0x44)
		#rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 0)
		#rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 20)
		#rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 36)
		#faceBuff = f.readBytes(self.face_count * 2)
		f.seek(0xCB, NOESEEK_ABS)
		for i in range(0, self.vertex_count):
			f.seek(0xCB + (i * 68)), NOESEEK_ABS
			self.vertArray[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
		f.seek(0xCB + (self.vertex_count * 68), NOESEEK_ABS)
		for i in range(0, self.face_count * 3):
			self.faceArray[i] = f.readUShort()
		print(f.tell())
	
def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	f = NoeBitStream(data)
	ltb = ltb_format(data)
	ltb.ReadFromFile(f)
	msh = NoeMesh ([], [], "mesh0", "mat0")
	msh.setIndices(ltb.faceArray)
	msh.setPositions(ltb.vertArray)
	mdlList.append(NoeModel([msh], [], []))
	return 1
```


The # parts are the lines I tried to add in to have UVs work which are most likely wrong. The mesh loads correctly, it just doesn't have any UVs.
I also have used hex2obj on these models before so I kind of know the basics of the files, I just don't know how to interpret that into a Noesis script.
I have uploaded two samples, hyuna_s1 is the file I began with for the script, chorong is a file that has multiple meshes. [https://1drv.ms/u/s!AoEEkLgybKv7hEhbCrI5kXH75i13](https://1drv.ms/u/s!AoEEkLgybKv7hEhbCrI5kXH75i13)
I would also like to try and get bones/weights at some point but I don't want to get ahead of myself yet.
Thanks to anyone that helps.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-16T03:51:03+00:00
- Post Title: Sudden Attack - Noesis Script Creation

A working script for ltb (except for meshtype 8, vstride 68) was from finale00, so I guess, it would be nice to mention him.

> Reply from TRDaz
>
> 
The # parts are the lines I tried to add in to have UVs work which are most likely wrong. The mesh loads correctly, it just doesn't have any UVs.
Introduce an additional meshtype 8 and you're done (named it '8', just a wild guess; obviously detected as 4 by fmt_ZuOnline_ltb.py):

```
            vertBuff = self.inFile.readBytes(numVerts * 68)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 24)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 36)
```

The uv offset 36 is in your addition (commented out, though), so dunno how you confused yourself?

> I also have used hex2obj on these models before so I kind of know the basics of the files, I just don't know how to interpret that into a Noesis script.making a vstride map is the base of all, normals in green rectangle:
(see AceWell used 20 as normals offset, so you've to check in blender for example which are the correct ones)



hyuna_H2O.JPG (75.03 KiB) Viewed 568 times



btw: this is the submeshes log of hyuna from the patched ZuOnline script:
Detected file type: LithTech
bones: 27, meshes: 1
parse mesh: 0x62
name: body, subMeshes: 5
parse submesh, count: 0x88 , 5
meshtype:  8
parse vertices, count: 0xcb , 7088
parse faces, count: 0x75b8b , 27135
0
meshtype:  8
parse vertices, count: 0x83128 , 5799
parse faces, count: 0xe3584 , 21399
0
meshtype:  8
parse vertices, count: 0xede2d , 4621
parse faces, count: 0x13a9a1 , 15378
0
meshtype:  8
parse vertices, count: 0x142358 , 3145
parse faces, count: 0x1766bc , 9159
0
meshtype:  8
parse vertices, count: 0x17afdd , 3145
parse faces, count: 0x1af341 , 9159
0
-----------------------

ChoRong is more complicated:
Detected file type: LithTech
bones: 27, meshes: 3
parse mesh: 0x62
name: ChoRong_face, subMeshes: 5
parse submesh, count: 0x90 , 5
parse vertices, count: 0xd3 , 1397
parse faces, count: 0xc547 , 7800
0
parse vertices, count: 0x1028d , 1034
parse faces, count: 0x193f5 , 5748
0
parse vertices, count: 0x1c133 , 622
parse faces, count: 0x218ab , 3348
0
parse vertices, count: 0x23329 , 226
parse faces, count: 0x252f1 , 1161
0
parse vertices, count: 0x25c59 , 123
parse faces, count: 0x26da5 , 552
0
name: ChoRong_hair, subMeshes: 5
parse submesh, count: 0x27242 , 5
parse vertices, count: 0x27285 , 452
parse faces, count: 0x2b215 , 1992
parse vertices, count: 0x2c207 , 340
parse faces, count: 0x2f1d7 , 1419
parse vertices, count: 0x2fd4f , 265
parse faces, count: 0x32293 , 1044
parse vertices, count: 0x32b1d , 191
parse faces, count: 0x345f9 , 678
parse vertices, count: 0x34ba7 , 144
parse faces, count: 0x35fe7 , 474
name: ChoRong_body, subMeshes: 5
parse submesh, count: 0x363e8 , 5
parse vertices, count: 0x3642b , 4197
parse faces, count: 0x63587 , 15099
parse vertices, count: 0x6acf7 , 3307
parse faces, count: 0x8e55b , 11466
parse vertices, count: 0x940a5 , 2749
parse faces, count: 0xb1921 , 8949
parse vertices, count: 0xb60f1 , 1485
parse faces, count: 0xc602d , 4080
parse vertices, count: 0xc81b7 , 1332
parse faces, count: 0xd66a7 , 3597
## Post #3
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-16T08:40:46+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Thank you for your help, I should have mentioned finale00, sorry about that.

However I have tried to do adding the meshtype, but the script keeps saying it is invalid syntax and I can't see any other mention of meshtype in the other scripts that could make it work. Any idea why? Sorry if I sound stupid lol.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-16T10:15:41+00:00
- Post Title: Sudden Attack - Noesis Script Creation

I've added this in finale00's Zuonline script:
in
 def parse_vertices(self, numVerts, meshType):

```
            vertBuff = self.inFile.readBytes(numVerts * 68)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 20)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 68, 36)
        else:
            print("unknown meshType: %d" %meshType)
```

in
    def parse_submesh(self, numSubmesh):

```
            if sectionSize:
                start = self.inFile.tell()
                numVerts = self.inFile.readUInt()
                numIdx = self.inFile.readUInt() * 3
                meshType = self.inFile.readUInt()
                # nonsense patch by me:D
                if numVerts == 7088:
                    meshType = 8
                if numVerts == 5799:
                    meshType = 8
                if numVerts == 4621:
                    meshType = 8
                if numVerts == 3145:
                    meshType = 8
```
This is very sloppy, and works for hyuna only, it's cause I don't like python  

btw; great, that you care for coding now!
## Post #5
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-16T21:19:02+00:00
- Post Title: Sudden Attack - Noesis Script Creation

I see, I've tried to add this into my own script, and there are no errors (there used to be with invalid syntax but not anymore) but the UVs still don't seem to load? I'm not really sure why.
If I am unable to get this to work I may just edit the current scripts as you have been doing to try and increase my knowledge before attempting a full script of my own.

Haha, I've cared for coding for a while, I just never had much knowledge in that until recently and since I've used hex2obj (thanks for the program and your tutorial with it, without that I wouldn't be trying any of this now lol.)

EDIT: I just re-tested the script since I actually missed out the "meshType = 8" coding, and that just gives me:
## Post #6
- Username: mariokart64n
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-16T21:53:19+00:00
- Post Title: Sudden Attack - Noesis Script Creation

if meshtype == 8:
## Post #7
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-16T22:03:38+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Oh thanks that fixed the invalid syntax, it still doesn't seem to load up UVs though which is weird.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-16T22:27:00+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Is #rapi.rpgBindUV1BufferOfs() still commented out in your code?
delete the # then (which disables the line from being "executed", so it's just a comment)

I'd suggest to read chrrox' Noesis tutorial to gain more understanding
otherwise you'll fall from one trouble into the other, I guess.

did you follow mariokart64n's tutorial?
" msh.setIndices(ltb.faceArray)"
"  msh.setPositions(ltb.vertArray)"
is a little bit uncommon to me (doesn't seem to be part of the rapi.rpg interface)

You might be required to use self.setUVs([]) to get the uvs.
## Post #9
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2017-03-17T02:13:17+00:00
- Post Title: Sudden Attack - Noesis Script Creation

mariokart64n's tutorial uses the more manual means of constructing a mesh, which probably does seem more familiar to someone coming from Max. But it's actually much slower to do things that way - using the rpg interface is generally recommended for performance reasons. (and it's usually more convenient, once you understand the interface)
## Post #10
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2017-03-17T04:48:30+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Once I get more comfortable with python and the noesis module I'll try out rapi, it seems the easiest way to read buffers 

@ TRDaz
The two file samples you posted have two different vertex structures, and I failed to locate a vertex definition for them.
I think you need to look at a few samples and look for a vertex type id, which you will then need to study and map for each id.

Here is a video I did working with your script, sorry the video is in real time and is an hour long.   

[https://youtu.be/fhESPMNrtu8](https://youtu.be/fhESPMNrtu8)



This is my take on the script, but it is still a work in progress

```

def registerNoesisTypes():
	handle = noesis.register("Sudden Attack", ".ltb")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	noesis.logPopup()
	return 1

def noepyCheckType(data):
	return 1

class geometry:
	def __init__(self):
		self.positions = [NoeVec3((0.0, 0.0, 0.0))]
		self.normals = [NoeVec3((0.0, 0.0, 0.0))]
		self.texcoord = [NoeVec3((0.0, 0.0, 0.0))]
		self.indices = [0]
	def sizeArrays(self, vertex_count, face_count):
		self.positions = [NoeVec3((0.0, 0.0, 0.0))] * vertex_count
		self.normals = [NoeVec3((0.0, 0.0, 0.0))] * vertex_count
		self.texcoord = [NoeVec3((0.0, 0.0, 0.0))] * vertex_count
		self.indicies = [0] * face_count

class ltb_format:
	def __init__(self):
		self.vertex_count = 0
		self.face_count = 0
	def ReadFromFile(self, f, g):
		f.seek(0x62, NOESEEK_ABS)
		f.seek(f.readUShort(), NOESEEK_REL)
		f.seek(0x41, NOESEEK_REL)
		self.vertex_count = f.readUInt()
		self.face_count = f.readUInt()
		unk01 = f.readUInt()
		f.seek(0x16, NOESEEK_REL)
		print("Vertex Count: " + str(self.vertex_count))
		print("Face Count: " + str(self.face_count))
		g.sizeArrays(self.vertex_count, self.face_count * 3)
		vertex_addr = f.tell()
		vertex_stride = 68
		if unk01 == 0x04:
			vertex_stride = 68
		elif unk01 == 0x02:
			vertex_stride = 36
		print("Vert Addr: " + str(f.tell()))
		for i in range(0, self.vertex_count):
			f.seek(vertex_addr + (i * vertex_stride), NOESEEK_ABS)
			g.positions[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
			f.seek(12, NOESEEK_REL)
			g.normals[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
			g.texcoord[i] = NoeVec3((f.readFloat(), f.readFloat(), 0))
		f.seek(vertex_addr + (vertex_stride * self.vertex_count), NOESEEK_ABS)
		print("face Addr: " + str(f.tell()))
		for i in range(0, self.face_count * 3):
			g.indicies[i] = f.readUShort()
		print(f.tell())

def noepyLoadModel(data, mdlList):
	g = geometry()
	f = NoeBitStream(data)
	ltb = ltb_format()
	ltb.ReadFromFile(f, g)
	msh = NoeMesh([], [], "mesh0", "mat0")
	msh.setPositions(g.positions)
	msh.setNormals(g.normals)
	msh.setUVs(g.texcoord)
	msh.setIndices(g.indicies)
	mdlList.append(NoeModel([msh], [], []))
	return 1

```
## Post #11
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-17T09:42:42+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Thank you for everyone's help!
Chrrox spoke to me yesterday about working with the normal way of writing scripts and how to understand some information in the header, but the video you have made will help me, so thanks!
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-18T09:51:15+00:00
- Post Title: Sudden Attack - Noesis Script Creation

i'm not so sure this format is a good one to learn with, when you look at enough sample you see the "meshType"
can be the same but have different vertex strides in different models, i think the "meshType" variable may either be
completely wrong or partially correct, this crucial part needs further examination.
example: 
the meshType 4 in hyuna_s1.ltb has a 68 byte stride
the meshType 4 in chorong.ltb has a 44 byte stride

since the indices seem consistent i guess you could subtract that buffer and submesh/LOD header
from the "sectionsize" then divide that remainder by the number of vertices to get the stride. 

finale00's ZuOnline script can already read all submeshes and LODs in the chorong.ltb sample but they are clumped together
[http://himeworks.com/redirect.php?type= ... Online_ltb](http://himeworks.com/redirect.php?type=noesis&name=ZuOnline_ltb)
the modified wolfteam_ltb.py script i attached here works with your hyuna_s1.ltb sample 
[http://zenhax.com/viewtopic.php?f=5&t=2777](http://zenhax.com/viewtopic.php?f=5&t=2777)


i made a newbified version of mariokart64n's script that does the exact same thing, no classes or multi functions here,
as a hobby i will avoid that at all cost unless i am being paid to write python code, in only that case will i embrace it.  
the script reads only the first submesh and first LOD of both your samples the same as his.  

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Sudden Attack", ".ltb")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

def noepyCheckType(data):
    return 1

def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    bs.seek(0x62, NOESEEK_ABS)
    meshNamesize = bs.readUShort()
    meshName = bs.readBytes(meshNamesize).decode("ASCII")
    #rapi.rpgSetName(meshName)
    numLODs = bs.readUInt()
    bs.seek(0x39, NOESEEK_REL) 
    sectionSize = bs.readUInt()
    vertex_count = bs.readUInt()   
    face_count = bs.readUInt() * 3  
    meshType = bs.readUInt()
    if meshType == 2:
        vertex_stride = 36
    elif meshType == 4:
        vertex_stride = 68                       
    bs.seek(0x16, NOESEEK_REL)
    VertexBuffer = bs.readBytes(vertex_count * vertex_stride)
    if meshType == 2:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, vertex_stride, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, vertex_stride, 16) #??
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, vertex_stride, 28)
    elif meshType == 4:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, vertex_stride, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, vertex_stride, 24) 
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, vertex_stride, 36)
    else:
        print("This mesh not yet supported")
    FaceBuffer = bs.readBytes(face_count * 2)
    rapi.rpgCommitTriangles(FaceBuffer, noesis.RPGEODATA_USHORT, face_count, noesis.RPGEO_TRIANGLE, 1)
    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)
    rapi.rpgClearBufferBinds()   
    return 1
```
## Post #13
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-18T23:57:54+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Thanks for this AceWell! It has helped me improve my script and it now works with more files than previously, it still needs some adjusting to work with others but all of this will help me.
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-19T11:39:03+00:00
- Post Title: Sudden Attack - Noesis Script Creation

i've been wanting to newbify and universally extending that ZuOnline script for SA for a while now  
and this thread has renewed my interest in it, here is the result. 


 fmt_SuddenAttack_ltb.zip
(1.05 KiB) Downloaded 111 times



it now has universal stride checking with the math i mentioned previously and supports all 8 known vertex stride types. 

```
vertex_stride = (sectionSize - 0x32 - (face_count * 2)) // vertex_count
```

it reads and draws all LODs and names each appropriately so you can identify and delete what you don't want later.
you may need to play around with the normals position to get them just right though.
try it out on more samples and see how it goes.
## Post #15
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-19T12:46:08+00:00
- Post Title: Sudden Attack - Noesis Script Creation

Most samples seem to work with this vertex stride method, however there are a few that don't, these are two that give an error:
[https://1drv.ms/u/s!AoEEkLgybKv7hEn_fefVTVVVBS7l](https://1drv.ms/u/s!AoEEkLgybKv7hEn_fefVTVVVBS7l)

So far all of this is helping understand it better though
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-19T17:20:25+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

okay i updated the script with a quick fix, it may or may not break other models, if it does just comment out lines 34-37 and shift+tab line 38.   
the stride was 1 byte off and the submesh headers had an extra 2 bytes in the last 2 samples.
## Post #17
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-19T18:09:55+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

Works great  Thanks!
## Post #18
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2017-03-23T14:15:37+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

> Reply from shakotay2
>
> Is #rapi.rpgBindUV1BufferOfs() still commented out in your code?
delete the # then (which disables the line from being "executed", so it's just a comment)

I'd suggest to read chrrox' Noesis tutorial to gain more understanding
otherwise you'll fall from one trouble into the other, I guess.

did you follow mariokart64n's tutorial?
" msh.setIndices(ltb.faceArray)"
"  msh.setPositions(ltb.vertArray)"
is a little bit uncommon to me (doesn't seem to be part of the rapi.rpg interface)

You might be required to use self.setUVs([]) to get the uvs.

QuickBMS can not extract .rez  How could I extract it，plz.
## Post #19
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-02-24T20:31:30+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

> Reply from Acewell ↑Mon Mar 20, 2017 1:20 am at Mon Mar 20, 2017 1:20 am
>
> 
okay i updated the script with a quick fix, it may or may not break other models, if it does just comment out lines 34-37 and shift+tab line 38.   
the stride was 1 byte off and the submesh headers had an extra 2 bytes in the last 2 samples.

Hey Acewell, I know this is an old post, I wanted to thank you for your work on the script! seriously it's awesome, there are Kpop stars in the sudden attack files and I really wanted to get the models.
but I've run into a bit of a problem. I followed your directions on commenting your script and then none of the models will open, the script compiles and works but none of the models open any more. are you sure you got the right lines to comment out there?
here is an example of one of the files that does not work with your script. 
i managed to get all the files from the game even tho it's shut down for some reason you can download it on the korean site. 
thank you in advance if you can offer any help with this.
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-25T07:44:28+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

> Reply from Xr79 ↑Mon Feb 25, 2019 4:31 am at Mon Feb 25, 2019 4:31 am
>
> are you sure you got the right lines to comment out there?
that is a question you should probably ask yourself.   

> here is an example of one of the files that does not work with your script.
i can't see invisible samples, maybe you forgot to link it?
i don't really think there is much more i can do with this game model format.

i don't do much with model scripts any more anyway because i have 
a large backlog of texture samples from many other topics to examine
and i plan to get most of them out of the way this year.
## Post #21
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-02-25T20:32:06+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

> Reply from Acewell ↑Mon Feb 25, 2019 3:44 pm at Mon Feb 25, 2019 3:44 pm
>
> 
Xr79 wrote: ↑Mon Feb 25, 2019 4:31 amare you sure you got the right lines to comment out there?
that is a question you should probably ask yourself.   
here is an example of one of the files that does not work with your script.
i can't see invisible samples, maybe you forgot to link it?
i don't really think there is much more i can do with this game model format.

i don't do much with model scripts any more anyway because i have 
a large backlog of texture samples from many other topics to examine
and i plan to get most of them out of the way this year.

If I'm being honest I wasn't expecting you to take the time to message me back, I thought it was just a shot in the dark. there was a problem sharing the sample, it's to big and all my online store are full right now.
but maybe you could show what lines to comment out? I did 34-37 and shift tabbed 38 like you said to, but it didn't work. I use note pad ++

34            if vertex_stride == 31:
35               vertex_stride = 32
36               bs.seek(0x18, NOESEEK_REL)
37            else:
38                bs.seek(0x16, NOESEEK_REL)
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-26T04:15:09+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

yes those are the correct lines.   
when i say comment them they will result to look like this:

```
    # vertex_stride = 32
    # bs.seek(0x18, NOESEEK_REL)
# else:
bs.seek(0x16, NOESEEK_REL)
```

the indent of line 38 is critical, this might be where it breaks for you. 
line 38 should be indented the same as line 33.
if it still doesn't work with your sample then it just doesn't work.
there is no guarantee the script works with all game samples.
## Post #23
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-06-21T18:09:32+00:00
- Post Title: Re: Sudden Attack - Noesis Script Creation

I was contacted about adding bone and weight support for the Noesis python plugin for sudden attack.

I started by examining my old python script, and any other scripts written by others to determine if my involvement was required.

From what I discovered there are many scripts from several people; me, TRDaz, Acewell, finale00, zaramot, shakotay2, and possibly more in circulation

All of the previous scripts suffer from a range of problems;
- Incomplete Parsing of the file Header (Address of vertex buffer sometimes incorrect)
- Incomplete Reading of the vertex data (Doesn't read the bones or the weights)
- Lack of Vertex Type detection (resulted in many 'variant' versions of the scripts to work with each ltb model.)

As far as I understand .ltb likely stands for "Lith Tech Binary" and is used in a wide range of games using the LithTech Engine including the LithTech Jupiter Engine.

Technically this Topic for "Sudden Attack" should belong in this other Topic discussing and dealing with Lith Tech Engine models in general
[viewtopic.php?f=16&t=7230](https://forum.xentax.com/viewtopic.php?f=16&t=7230)

However the samples that were provided to me were exclusively from Sudden Attack so i will drop my update here;

This is a Noesis Python Plugin for Sudden Attack
(has also been tested with the samples posted in this Topic by others)

Supports:
- Improved Reading and detection of file header and vertex definitions
- Mesh, Bones, Weights

Not Supported
-Materials
***see dtx script to unpack textures: [viewtopic.php?p=164339#p164339](https://forum.xentax.com/viewtopic.php?p=164339#p164339)



```
#
#	Read Mesh from Lith Tech Binary
#	
#	Author:	mariokart64n
#	Date:		June 20 2020
#	Source:	https://forum.xentax.com/viewtopic.php?f=16&t=15997
#

showConsole = False
NOEPY_HEADER = 0x00090001  # LTB

from inc_noesis import *

class ltb_unk032:		# 112bytes
	name_length = 0
	name = ""
	unk100 = 0
	unk101 = 0.0
	unk102 = 0.0
	unk103 = 0.0
	unk104 = 0.0
	unk105 = 0.0
	unk106 = 0.0
	unk107 = 0.0
	unk108 = 0.0
	unk109 = 0.0
	unk110 = 0.0
	unk111 = 0.0
	unk112 = 0.0
	unk113 = 0.0
	unk114 = 0.0
	unk115 = 0.0
	unk116 = 0.0
	unk117 = 0.0
	unk118 = 0.0
	unk119 = 0.0
	unk120 = 0.0
	unk121 = 0.0
	unk122 = 0.0
	unk123 = 0.0
	unk124 = 0.0
	unk125 = 0.0
	unk126 = 0.0
	unk127 = 0.0
	def read_unk032(self, f=NoeBitStream()):
		self.name_length = f.readUShort()
		self.name = f.readBytes(name_length).decode("UTF-8").rstrip("\0")
		self.unk100 = f.readUInt()
		self.unk101 = f.readFloat()
		self.unk102 = f.readFloat()
		self.unk103 = f.readFloat()
		self.unk104 = f.readFloat()
		self.unk105 = f.readFloat()
		self.unk106 = f.readFloat()
		self.unk107 = f.readFloat()
		self.unk108 = f.readFloat()
		self.unk109 = f.readFloat()
		self.unk110 = f.readFloat()
		self.unk111 = f.readFloat()
		self.unk112 = f.readFloat()
		self.unk113 = f.readFloat()
		self.unk114 = f.readFloat()
		self.unk115 = f.readFloat()
		self.unk116 = f.readFloat()
		self.unk117 = f.readFloat()
		self.unk118 = f.readFloat()
		self.unk119 = f.readFloat()
		self.unk120 = f.readFloat()
		self.unk121 = f.readFloat()
		self.unk122 = f.readFloat()
		self.unk123 = f.readFloat()
		self.unk124 = f.readFloat()
		self.unk125 = f.readFloat()
		self.unk126 = f.readFloat()
		self.unk127 = f.readFloat()
		

class ltb_node:
	node_name_length = 0
	node_name = ""
	index = 0
	unk091 = 0
	unk092 = 0
	matrix = []
	childCount = 0
	children = []
	parent = -1
	def read_node(self, f=NoeBitStream()):
		self.node_name_length = f.readUShort()
		self.node_name = f.readBytes(self.node_name_length).decode("UTF-8").rstrip("\0")
		self.index = f.readUByte()
		self.unk091 = f.readUByte()
		self.unk092 = f.readUByte()
		self.matrix = [
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()
			]
		self.childCount = f.readUInt()
		

class ltb_vert:
	position = []
	normal = []
	weights = []
	texcoord = []
	binormal = []
	tangent = []
	

class ltb_unk061:
	vert_pos = 0
	vert_count = 0
	unk072 = 0			# 4 bone indices
	unk073 = 0
	unk074 = 0
	unk075 = 0
	face_count = 0		# 3 times face count?
	def read_unk061(self, f=NoeBitStream()):
		self.vert_pos = f.readUShort()
		self.vert_count = f.readUShort()
		self.unk072 = f.readUByte()
		self.unk073 = f.readUByte()
		self.unk074 = f.readUByte()
		self.unk075 = f.readUByte()
		if self.unk072 == 0xFF:
			self.unk072 = 0
		if self.unk073 == 0xFF:
			self.unk073 = 0
		if self.unk074 == 0xFF:
			self.unk074 = 0
		if self.unk075 == 0xFF:
			self.unk075 = 0
		self.face_count = f.readUInt()
		
	

class ltb_geo:
	unk038 = 0
	unk039 = 0
	unk041 = 0
	unk042 = 0
	unk043 = 0
	unk044 = 0
	unk045 = 0
	unk046 = 0
	unk047 = 0		# addr to small table
	vertex_count = 0
	face_count = 0
	unk050 = 0		# Vertex Format?
	unk040 = 0		# Vertex Format?
	unk051 = []
	unk052 = 0
	unk053 = 0
	unk054 = 0
	unk055 = 0
	unk056 = 0
	unk057 = 0
	verts = ltb_vert()
	faces = []
	unk060 = 0		# mesh table? or bone palette?
	unk061 = []		# mesh table? or bone palette?
	unk062 = 0
	unk063 = []
	
	def guessTableAddr(self, limit, faceCount, f=NoeBitStream()):
		pos = f.tell()
		c = 0
		i = 1
		p = ltb_unk061()
		c = pos
		stop = False
		f.seek(-4, NOESEEK_REL)
		if f.readUInt() > 0:
			while i < limit and stop == False:
				f.seek((pos - (i * 0x0C) - 0x04), NOESEEK_ABS)
				if f.readUInt() == i:
					p.read_unk061(f)
					if p.face_count <= faceCount:
						c = f.tell() - 0x10
						stop = True
				i = i + 1
		f.seek(pos, NOESEEK_ABS)
		return c
	
	def read_geo(self, f=NoeBitStream()):
		i = 1
		ii = 1
		self.verts = ltb_vert()
		weight = []
		boneid = []
		vertex_addr = 0
		vertex_stride = 0
		unk040_addr = 0
		unk60_addr = 0
		self.unk038 = f.readUInt()
		self.unk039 = f.readUInt()
		self.unk041 = f.readUInt()
		self.unk042 = f.readUInt()
		self.unk043 = f.readUInt()
		self.unk044 = f.readUInt()
		self.unk045 = f.readUByte()
		self.unk046 = f.readUInt()
		self.unk047 = f.readUInt()
		unk040_addr = f.tell() + self.unk047
		self.vertex_count = f.readUInt()
		self.face_count = f.readUInt()
		self.unk050 = f.readUInt()
		self.unk040 = f.readUByte()
		
		if self.unk040 > 0:
			self.unk051 = [int] * self.unk040
		
		for i in range(0, self.unk040):
			self.unk051[i] = f.readUByte()
			
		self.unk052 = f.readUShort()
		self.unk053 = f.readUShort()
		self.unk054 = f.readUShort()
		self.unk055 = f.readUInt()
		self.unk056 = f.readUInt()
		self.unk057 = f.readUInt()
		vertex_addr = f.tell()
		f.seek(unk040_addr, NOESEEK_ABS)
		unk60_addr = self.guessTableAddr(((unk040_addr - vertex_addr) / 12), (self.face_count * 3), f)
		vertex_stride = int((unk60_addr - vertex_addr - (self.face_count * 6)) / self.vertex_count)
		vertex_stride += int((2 - (vertex_stride % 2)) % 2)
		vertex_addr = unk60_addr - (self.face_count * 6) - (self.vertex_count * vertex_stride)
		
		
		if self.vertex_count > 0:
			self.verts.position = [NoeVec3] * self.vertex_count
			self.verts.weights = [NoeVertWeight] * self.vertex_count
			self.verts.normal = [NoeVec3] * self.vertex_count
			self.verts.texcoord = [NoeVec3] * self.vertex_count
			self.verts.binormal = [NoeVec3] * self.vertex_count
			self.verts.tangent = [NoeVec3] * self.vertex_count
			
		
		for i in range(0, self.vertex_count):
			f.seek((vertex_addr + (i * vertex_stride)), NOESEEK_ABS)
			self.verts.position[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
			self.verts.normal[i] = NoeVec3((0.0, 0.0, 0.0))
			self.verts.texcoord[i] = NoeVec3((0.0, 0.0, 0.0))
			self.verts.binormal[i] = NoeVec3((0.0, 0.0, 0.0))
			self.verts.tangent[i] = NoeVec3((0.0, 0.0, 0.0))
			weight = [1.0, 0.0, 0.0, 0.0]
			boneid = [0, 0, 0, 0]
			
			
			if vertex_stride == 32:
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				
			elif vertex_stride == 36:
				weight = [f.readFloat(), 0.0, 0.0, 0.0]
				weight[1] = 1.0 - weight[0]
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				
			elif vertex_stride == 40:
				weight = [f.readFloat(), f.readFloat(), 0.0, 0.0]
				weight[2] = 1.0 - (weight[0] + weight[1])
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				
			elif vertex_stride == 44:
				weight = [f.readFloat(), f.readFloat(), f.readFloat(), 0.0]
				weight[3] = 1.0 - (weight[0] + weight[1] + weight[2])
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				
			elif vertex_stride == 56:
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				self.verts.binormal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.tangent[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				
			elif vertex_stride == 60:
				weight = [f.readFloat(), 0.0, 0.0, 0.0]
				weight[1] = 1.0 - weight[0]
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				self.verts.binormal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.tangent[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				
			elif vertex_stride == 64:
				weight = [f.readFloat(), f.readFloat(), 0.0, 0.0]
				weight[2] = 1.0 - (weight[0] + weight[1])
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				self.verts.binormal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.tangent[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				
			elif vertex_stride == 68:
				weight = [f.readFloat(), f.readFloat(), f.readFloat(), 0.0]
				weight[3] = 1.0 - (weight[0] + weight[1] + weight[2])
				self.verts.normal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.texcoord[i] = NoeVec3((f.readFloat(), 1.0 - f.readFloat(), 0))
				self.verts.binormal[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				self.verts.tangent[i] = NoeVec3((f.readFloat(), f.readFloat(), f.readFloat()))
				
			self.verts.weights[i] = NoeVertWeight(boneid, weight)
		
		f.seek((vertex_addr + (self.vertex_count * vertex_stride)), NOESEEK_ABS)
		
		if self.face_count > 0:
			self.faces = [int] * (self.face_count * 3)
		
		for i in range(0, self.face_count * 3):
			self.faces[i] = f.readUShort()
		
		if unk60_addr < unk040_addr:
			f.seek(unk60_addr, NOESEEK_ABS)
			self.unk060 = f.readUInt()
			
			if self.unk060 > 0:
				self.unk061 = [ltb_unk061] * self.unk060
			
			for i in range(0, self.unk060):
				self.unk061[i] = ltb_unk061()
				self.unk061[i].read_unk061(f)
				for ii in range(0, self.unk061[i].vert_count):
					self.verts.weights[ii + self.unk061[i].vert_pos].indices = [self.unk061[i].unk072, self.unk061[i].unk073, self.unk061[i].unk074, self.unk061[i].unk075]
					
		
		if self.unk047 > 0:
			f.seek(unk040_addr, NOESEEK_ABS)
			self.unk062 = f.readUByte()
			self.unk063 = [int] * self.unk062
			for i in range(0, self.unk062):
				self.unk063[i] = f.readUByte()
				
			
		
	

class ltb_mesh:
	mesh_name_length = 0
	mesh_name = ""
	lod_count = 0
	unk031 = []
	unk036 = 0
	unk037 = 0
	lods = []
	def read_mesh(self, f=NoeBitStream()):
		i = 1
		m = 1
		
		self.mesh_name_length = f.readUShort()
		self.mesh_name = f.readBytes(self.mesh_name_length).decode("UTF-8").rstrip("\0")
		self.lod_count = f.readUInt()
		
		if self.lod_count > 0:
			self.unk031 = [float] * self.lod_count
		
		for i in range(0, self.lod_count):
			self.unk031[i] = f.readFloat()
			
		self.unk036 = f.readUInt()
		self.unk037 = f.readUInt()
		self.lods = [ltb_geo] * self.lod_count
		
		for m in range(0, self.lod_count):
			self.lods[m] = ltb_geo()
			self.lods[m].read_geo(f)
			
		
		

class ltb_file:
	unk001 = 0
	unk002 = 0
	unk003 = 0
	unk004 = 0
	unk005 = 0
	unk006 = 0
	unk007 = 0
	unk008 = 0
	unk009 = 0
	node_count = 0
	mesh_count = 0
	unk012 = 0
	total_face_count = 0
	unk014 = 0
	unk015 = 0
	total_lod_count = 0
	unk017 = 0
	unk018 = 0
	unk019 = 0
	unk020 = 0
	unk021 = 0
	unk022 = 0
	unk057 = 0
	unk058 = ""
	unk023 = 0.0
	unk024 = 0
	unk025 = []
	unk026 = 0
	unk027 = 0
	meshs  = []
	nodes = []
	
	def read_ltb(self, f=NoeBitStream()):
		i = 1
		ii = 1
		self.unk001 = f.readUShort()
		self.unk002 = f.readUShort()
		self.unk003 = f.readUInt()
		self.unk004 = f.readUInt()
		self.unk005 = f.readUInt()
		self.unk006 = f.readUInt()
		self.unk007 = f.readUInt()
		self.unk008 = f.readUInt()
		self.unk009 = f.readUInt()
		self.node_count = f.readUInt()
		self.mesh_count = f.readUInt()
		self.unk012 = f.readUInt()
		self.total_face_count = f.readUInt()
		self.unk014 = f.readUInt()
		self.unk015 = f.readUInt()
		self.total_lod_count = f.readUInt()
		self.unk017 = f.readUInt()
		self.unk018 = f.readUInt()
		self.unk019 = f.readUInt()
		self.unk020 = f.readUInt()
		self.unk021 = f.readUInt()
		self.unk022 = f.readUInt()
		self.unk057 = f.readUShort()
		self.unk058 = f.readBytes(self.unk057).decode("UTF-8").rstrip("\0")
		self.unk023 = f.readFloat()
		self.unk024 = f.readUInt()
		
		if self.unk024 > 0:	# 64bytes, looks like a matrix
			self.unk025 = [[float], [float], [float], [float], [float], [float], [float], [float], [float], [float], [float], [float], [float], [float], [float], [float]] * self.unk024
		
		for i in range(0, self.unk024):
			self.unk025[i] = [
				0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 
				0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0
				]
			for ii in range(0, 16):
				self.unk025[i][ii] = f.readFloat()
				
			
		
		
		self.unk026 = f.readUShort()
		self.unk027 = f.readUShort()
		
		self.meshs = [ltb_mesh] * self.mesh_count
		for i in range(0, self.mesh_count):
			self.meshs[i] = ltb_mesh()
			self.meshs[i].read_mesh(f)
			
		
		self.nodes = [ltb_node] * self.node_count
		for i in range(0, self.node_count):
			self.nodes[i] = ltb_node()
			self.nodes[i].read_node(f)
			
	
	def getChildren(self, i):
		c = 0
		p = i
		x = 0
		if i < self.node_count:
			self.nodes[i].children = []
			for c in range(0, self.nodes[i].childCount):
				p = p + 1
				self.nodes[i].children.append(p)
				if p <= self.node_count:
					p = self.getChildren(p)
		return p
	
	def getParent(self):
		for i in range(0, self.node_count):
			self.nodes[i].parent = -1
			for ii in range(0, self.node_count):
				if ii != i and self.nodes[i].parent == -1:
					for iii in range(0, len(self.nodes[ii].children)):
						if self.nodes[ii].children[iii] == int(i):
							self.nodes[i].parent = ii
	
	def create_bone_list(self):
		# generate the parents from the child counts
		self.getChildren(0)
		self.getParent()
		
		BoneList = []
		BoneMatrix43 = NoeMat43()
		BoneMatrix44 = NoeMat44()
		BoneName = ""
		ParentName = ""
		i = 0
		NumBones = self.node_count
		if NumBones > 0:
			BoneList = [NoeBone] * NumBones
			for i in range(0, NumBones):
				BoneMatrix44 = NoeMat44((
					NoeVec4((self.nodes[i].matrix[0], self.nodes[i].matrix[4], self.nodes[i].matrix[8], self.nodes[i].matrix[12])),
					NoeVec4((self.nodes[i].matrix[1], self.nodes[i].matrix[5], self.nodes[i].matrix[9], self.nodes[i].matrix[13])),
					NoeVec4((self.nodes[i].matrix[2], self.nodes[i].matrix[6], self.nodes[i].matrix[10], self.nodes[i].matrix[14])),
					NoeVec4((self.nodes[i].matrix[3], self.nodes[i].matrix[7], self.nodes[i].matrix[11], self.nodes[i].matrix[15]))
					))
				
				BoneMatrix43 = BoneMatrix44.toMat43()
				#BoneMatrix43 = BoneMatrix43.inverse()
				
				BoneName = "bone%03i" % i
				ParentName = "bone%03i" % self.nodes[i].parent
				
				if self.nodes[i].node_name != "":
					BoneName = self.nodes[i].node_name
				
				if self.nodes[i].parent > -1 and self.nodes[i].parent < NumBones:
					if self.nodes[self.nodes[i].parent].node_name != "":
						ParentName = self.nodes[self.nodes[i].parent].node_name
					
					BoneList[i] = (NoeBone(i, BoneName, BoneMatrix43, ParentName, self.nodes[i].parent))
					#BoneList[i] = (NoeBone(i, self.nodes[i].node_name, BoneMatrix43, None, -1))
				else:
					BoneList[i] = (NoeBone(i, self.nodes[i].node_name, BoneMatrix43, None, -1))
		return BoneList
	
	def create_mesh_list(self, f = NoeBitStream()):
		mshList = []
		
		if self.mesh_count > 0:
			mshList = [NoeMesh] * self.mesh_count
		
		for i in range(0, self.mesh_count):
			mshList[i] = NoeMesh(self.meshs[i].lods[0].faces, self.meshs[i].lods[0].verts.position, self.meshs[i].mesh_name)
			#mshList[i].setIndices(self.meshs[i].lods[0].faces)
			#mshList[i].setPositions(self.meshs[i].lods[0].verts.position)
			mshList[i].setNormals(self.meshs[i].lods[0].verts.normal)
			mshList[i].setUVs(self.meshs[i].lods[0].verts.texcoord, 0)
			mshList[i].setWeights(self.meshs[i].lods[0].verts.weights)
		return mshList

def noepyLoadModel(data, mdlList):
	f = NoeBitStream(data)
	if f.readUInt() != NOEPY_HEADER:
		return 0
	
	#  Check if there is a texture library
	#filename = rapi.getInputName()
	#filename = filename[:-3] + {'LTB': 'DTX'}[filename[-3:].upper()]
	#if rapi.checkFileExists(filename):
	#	t = NoeBitStream(rapi.loadIntoByteArray(filename))
	
	
	f.seek(0x00, NOESEEK_ABS)
	ltb = ltb_file()
	ltb.read_ltb(f)
	
	BoneList = []
	MeshList = []
	
	BoneList = ltb.create_bone_list()
	MeshList = ltb.create_mesh_list(f)
	
	mdl = NoeModel()
	
	mdl.setBones(BoneList)
	mdl.setMeshes(MeshList)
	
	mdlList.append(mdl)
	return 1

def noepyCheckType(data):
	if len(data) < 8:
		return 0
	f = NoeBitStream(data)
	if f.readUInt() != NOEPY_HEADER:
		return 0
	return 1


def registerNoesisTypes():
	if showConsole == True:
		noesis.logPopup()
		for i in range(0, 30): print("\n")
	handle = noesis.register("Lith Tech Binary (PC)", ".ltb")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1

```

[fmt_LithTechBinary_ltb.zip](https://xentaxbackup.github.io/file/18363_fmt_LithTechBinary_ltb.zip)
