## Post #1
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-22T08:41:14+00:00
- Post Title: How do normals work?

I mean, I know they usualy weight 3 floats but I have no idea what's their purpose. Actualy I kind of know what they do, but not how they do it, and that's what I need to know. Like whats the purpose of each float that compose the normal.

I'm getting an error in noesis that looks like this:
WARNING: Size of normal list does not match positions, ignoring normals.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-22T12:17:41+00:00
- Post Title: How do normals work?

> Reply from Repeperilka
>
> I mean, I know they usualy weight 3 floats but I have no idea what's their purpose. Actualy I kind of know what they do, but not how they do it, and that's what I need to know. Like whats the purpose of each float that compose the normal.
Normals are unit vectors of which the square sum of the 3 coords equal to 1.0. And if you treat their coords as the ones of vertexes, you'll see them all distributing on the Unit Ball. Usually the normal vector of a vertex equals to the average of all the normal vectors of the faces this vert belongs to, but that's not always applicable for game models.

> Reply from Repeperilka
>
> I'm getting an error in noesis that looks like this:
WARNING: Size of normal list does not match positions, ignoring normals.
Usually for game models the amount of vertexes of positions will equal to the ones of the normal vectors, and of the texcoords(UVs).
But you can optimize them by removing the copies of the same object, which'll result in different counts for positions/normals/UVs. Guess that's what your problem is about.
## Post #3
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-22T12:56:32+00:00
- Post Title: How do normals work?

> Reply from Bigchillghost
>
> Usually for game models the amount of vertexes of positions will equal to the ones of the normal vectors, and of the texcoords(UVs).
But you can optimize them by removing the copies of the same object, which'll result in different counts for positions/normals/UVs. Guess that's what your problem is about.
Hmm, it is probably a problem with my script because i've just made some debugging and this is what i am facing:

```
3
35
------Object14------
vertex count = 1668
face index count = 5325
normals count = 1668
uv's count = 1668
------Object16------
vertex count = 265
face index count = 666
normals count = 265
uv's count = 265
------Object17------
vertex count = 362
face index count = 777
normals count = 362
uv's count = 362
------Object28------
vertex count = 891
face index count = 2742
normals count = 891
uv's count = 891
------Object34------
vertex count = 274
face index count = 651
normals count = 274
uv's count = 274
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
Generating normals for 1668 vertices...
Generating normals for 265 vertices...
Generating normals for 362 vertices...
Generating normals for 891 vertices...
Generating normals for 274 vertices...
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\LARRYCOOL\\14'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\LARRYCOOL\\16'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\LARRYCOOL\\17'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\LARRYCOOL\\28'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\LARRYCOOL\\34'...Failed.
```


The uv's, normals and vertex arrays have the same length, and I've checked the uv's with ModelResearcher and they are good.

> Reply from Bigchillghost
>
> Normals are unit vectors of which the square sum of the 3 coords equal to 1.0. And if you treat their coords as the ones of vertexes, you'll see them all distributing on the Unit Ball. Usually the normal vector of a vertex equals to the average of all the normal vectors of the faces this vert belongs to, but that's not always applicable for game models.

So, (vn1 + vn2 + vn3)^2 = 1.0? (I am not very good at math nor english)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-22T13:19:00+00:00
- Post Title: How do normals work?

> Reply from Repeperilka
>
> and I've checked the uv's with ModelResearcher and they are good.
Then you must have made some mistakes with your code. You'll need to post your script to reveal your issues.

> Reply from Repeperilka
>
> So, (vn1 + vn2 + vn3)^2 = 1.0?
Nop. It's vnx^2 + vny^2 + vnz^2 = 1.0.
## Post #5
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-22T13:34:55+00:00
- Post Title: How do normals work?

```

def registerNoesisTypes():
	handle = noesis.register("Leisure Suit Larry", ".WGG")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)

	noesis.logPopup()
	return 1
	
def noepyCheckType(data):
	if len(data) < 8:
		return 0
	j = NoeBitStream(data)
	if j.readUInt() != 0x49535648:
		return 0
	return 1
	
def noepyLoadModel(data, mdlList):
	f = NoeBitStream(data)
	#start positions
	VertexStart = []
	f.seek(0x24, NOESEEK_ABS)
	TableStart = f.readUInt()
	NumberOfChunks = f.readUInt()
	StartChunkPos = f.readUInt() + 0x58
	f.seek(0x4, NOESEEK_REL)
	FacesStart = f.readUInt() + 0x8
	StartPosition = 0x58
	for i in range(0, NumberOfChunks):
		f.seek(StartChunkPos + 0x4, NOESEEK_ABS)
		vertCount = f.readUInt()
		f.seek(0x30, NOESEEK_REL)
		vertSize = f.readUInt()
		VertexStart.append(Chunk(vertSize, f.tell()))
		StartChunkPos = f.tell() + vertCount * vertSize
	print(len(VertexStart))
	
	#objects
	f.seek(StartPosition + TableStart + 0x8, NOESEEK_ABS)
	ObjectsCount = f.readUInt()
	f.seek(StartPosition, NOESEEK_ABS)
	Objects = []
	for i in range(0, ObjectsCount):
		Objects.append(f.readBytes(8).decode("ASCII").rstrip("\0"))
		f.seek(0x8, NOESEEK_REL)
	#table
	f.seek(StartPosition + TableStart, NOESEEK_ABS)
	NumberOfEntries = f.readUInt()
	f.seek(0x14, NOESEEK_REL)
	StartEntries = f.tell()
	Entries = []
	for i in range(0, NumberOfEntries):
		chunk = f.readUShort()
		f.seek(0xA, NOESEEK_REL)
		nVert = f.readUShort()
		f.seek(0x2, NOESEEK_REL)
		nFac = f.readUShort()
		f.seek(0x2, NOESEEK_REL)
		fac = f.readUShort()
		f.seek(0x4, NOESEEK_REL)
		vert = f.readUShort()
		f.seek(0x2, NOESEEK_REL)
		index = f.readUShort()
		f.seek(0x8, NOESEEK_REL)
		Entries.append(Entry(chunk, vert, fac, nVert, nFac, index))
	print(len(Entries))
	#objects
	Meshes = []
	FinalObjects = 0
	vertex = []
	faces = []
	normals = []
	uv = []
	for i in range(0, len(Entries)):
		LastVert = len(vertex)
		#Vertices
		pos = VertexStart[Entries[i].nChunk].startPosition + Entries[i].nVertex * VertexStart[Entries[i].nChunk].entrySize
		f.seek(pos, NOESEEK_ABS)
		if VertexStart[Entries[i].nChunk].entrySize == 40:
			for e in range (0, Entries[i].vertexCount):
				vertex.append (NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				f.seek(0x8, NOESEEK_REL)
				normals.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				uv.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				f.seek(-0x4, NOESEEK_REL)
		elif VertexStart[Entries[i].nChunk].entrySize == 36:
			for e in range (0, Entries[i].vertexCount):
				vertex.append (NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				f.seek(0x4, NOESEEK_REL)
				normals.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				uv.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				f.seek(-0x4, NOESEEK_REL)
		elif VertexStart[Entries[i].nChunk].entrySize == 32:
			for e in range (0, Entries[i].vertexCount):
				vertex.append (NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				normals.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				uv.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
				f.seek(-0x4, NOESEEK_REL)
		#Faces
		pos = FacesStart + StartPosition + Entries[i].nFaces * 2
		f.seek(pos, NOESEEK_ABS)
		for e in range (0, Entries[i].facesCount):
			faces.append(f.readUShort() + LastVert)
		#setup1
		if (FinalObjects < Entries[i].objIndex):
			Meshes.append(NoeMesh (faces, vertex, str(i), str(i)))
			Meshes[FinalObjects].normals.append(normals)
			Meshes[FinalObjects].uvs.append(uv)
			print("------Object" + str(i) + "------")
			print("vertex count = " + str(len(vertex)))
			print ("face index count = " + str(len(faces)))
			print("normals count = " + str(len(normals)))
			print("uv's count = " + str(len(uv)))
			faces = []
			vertex = []
			normals = []
			uv = []
			FinalObjects = FinalObjects + 1
		
		#setup2
		#print(len(normals))
		#print(len(vertex))
		#Meshes.append(NoeMesh (faces, vertex, "Hola" + str(i), ""))
		#Meshes[i].normals.append(normals)
		#normals = []
		#vertex = []
		#faces = []
		#uv = []
	
	mdlList.append(NoeModel(Meshes, [], []))
	return 1
	
class Entry:
	nChunk = 0
	vertexCount = 0
	facesCount = 0
	nVertex = 0
	nFaces = 0
	objIndex = 0
	def __init__(self, chunk, vert, fac, nVert, nFac, index):
		self.nChunk = chunk
		self.vertexCount = vert
		self.facesCount = fac
		self.nVertex = nVert
		self.nFaces = nFac
		self.objIndex = index

class Chunk:
	startPosition = 0
	entrySize = 0
	def __init__(self, size, start):
		self.entrySize = size
		self.startPosition = start
```


This is a post i made because i did not know how was the information stored in the file, there is a link to the file for if you want to have it: [viewtopic.php?f=10&t=19163](http://forum.xentax.com/viewtopic.php?f=10&t=19163)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-22T13:53:06+00:00
- Post Title: How do normals work?

```
normals.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
```

It should be 
```
normals.append(NoeVec3([f.readFloat(), f.readFloat(), f.readFloat()]))
```

or simply use 
```
normals.append(NoeVec3.fromBytes(bs.readBytes(12)))
```


```
uv.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
```

For most of the cases game models don't have the w component while there's no vec2 concept in Noesis, so you need to do it
like

```
uv.append(NoeVec3([f.readFloat(), f.readFloat(), 0]))
```
## Post #7
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-22T14:35:39+00:00
- Post Title: How do normals work?

I tried every combination possible with the things you told me, and i still get the same warning prompts.

```
3
45
------Object23------
vertex count = 2067
1st vert = (0.07027500867843628, 0.07789701223373413, 0.16757899522781372)
face index count = 7437
1st face = 0
normals count = 2067
1st normal = (0.6937000751495361, 0.6547720432281494, 0.300091028213501)
uv's count = 2067
1st uv = [0.4456320106983185, 0.38781505823135376, 0]
------Object28------
vertex count = 407
1st vert = (0.018630001693964005, 0.05230500549077988, 0.46636101603507996)
face index count = 1371
1st face = 0
normals count = 407
1st normal = (0.49452102184295654, 0.07861600816249847, 0.865602970123291)
uv's count = 407
1st uv = [0.4007430076599121, 0.04190700128674507, 0]
------Object34------
vertex count = 326
1st vert = (0.1076200008392334, -0.1154480054974556, 0.39223504066467285)
face index count = 1011
1st face = 0
normals count = 326
1st normal = (0.6704729795455933, -0.35633304715156555, 0.6507640480995178)
uv's count = 326
1st uv = [0.22328200936317444, 0.4489409923553467, 0]
------Object36------
vertex count = 150
1st vert = (0.02080800198018551, -0.10414400696754456, 0.46253401041030884)
face index count = 597
1st face = 0
normals count = 150
1st normal = (0.5784180164337158, -0.24716001749038696, 0.777396023273468)
uv's count = 150
1st uv = [0.4647040069103241, 0.04448600485920906, 0]
------Object39------
vertex count = 121
1st vert = (-0.08317900449037552, -0.051423002034425735, 0.12147300690412521)
face index count = 468
1st face = 0
normals count = 121
1st normal = (-0.7651110291481018, -0.15395501255989075, 0.6252229809761047)
uv's count = 121
1st uv = [0.9215329885482788, 0.7528210282325745, 0]
------Object42------
vertex count = 256
1st vert = (-0.0910470113158226, -0.02799900248646736, 0.08261200040578842)
face index count = 801
1st face = 0
normals count = 256
1st normal = (-0.9300490617752075, 0.08480000495910645, 0.35751602053642273)
uv's count = 256
1st uv = [0.9501460790634155, 0.07912901043891907, 0]
------Object44------
vertex count = 131
1st vert = (0.06489300727844238, -0.1863820105791092, -0.8974469900131226)
face index count = 213
1st face = 0
normals count = 131
1st normal = (0.12117300927639008, -0.6720520257949829, 0.730522096157074)
uv's count = 131
1st uv = [0.9698180556297302, 0.4650510251522064, 0]
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
WARNING: Size of normal list does not match positions, ignoring normals.
WARNING: Size of uv list does not match positions, ignoring uv's.
Generating normals for 2067 vertices...
Generating normals for 407 vertices...
Generating normals for 326 vertices...
Generating normals for 150 vertices...
Generating normals for 121 vertices...
Generating normals for 256 vertices...
Generating normals for 131 vertices...
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\23'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\28'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\34'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\36'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\39'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\42'...Failed.
Reading 'C:\Users\aleja\OneDrive\Escritorio\Larry Extract\out\GIRL\GIRLACTR\\44'...Failed.
```


It keep saying "Url of the archive...Failed" even though noesis is showing me the 3d model perfectly (with fucked up normals, of course)

Edit: i just aded a print with the first entry of every array
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-22T17:58:36+00:00
- Post Title: How do normals work?

I am not really proficient in Python/Noesis but these lines probably insert the whole normal/uv array as a single object.

```
Meshes[FinalObjects].uvs.append(uv)
```

Try

```
Meshes[FinalObjects].setUVs(uv)
```
## Post #9
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-22T19:30:27+00:00
- Post Title: How do normals work?

It worked! I have to admit that i did not think this was going to work, but it did!

Thank you both, very much indeed!
