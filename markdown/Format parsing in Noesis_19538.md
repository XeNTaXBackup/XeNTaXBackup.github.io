## Post #1
- Username: DrAwesomeXD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 10, 2017 3:38 am
- Post datetime: 2019-02-20T21:49:57+00:00
- Post Title: Format parsing in Noesis

So I reversed the 3D-models of a game. Converting the format to OBJ was no big deal.
But I'd like to import the format directly into Noesis.

I don't get how to import a model that has a vertex-list and a uv-list of different sizes.
My format looks like this (in pseudo-code):

```
vertex-list: list of (float, float, float), length is vertexCount
normalCount: integer
normal-list: list of (float, float, float), length is normalCount

uvCount: integer
uv-list: list of (short, float, float), length is uvCount
the short is a vertex-index that defines the uv's corresponding vertex.
This way, a vertex can have multiple uv-coordinates that map to it.

faceCount: integer
face-list: list of (short, short, short), length is faceCount
the list consists of uv-indececs. To get the corresponding vertex, we look at the short in the uv-list entry.

```


My problem with the Noesis-API is that it seems to expect the list of vertices and list of uv-coords to match in size. At least, when using the NoeMesh-Object. I could technically just expand the vertex-list and duplicate lots of vertices. But is that really an ideal solution?
Here's a code-snippet of my Noesis import-function in python:

```
def smdLoadModel(data, mdlList):
        bs = NoeBitStream(data)
        
        .....some unimportant stuff inbetween....
        
        triList = []
	posList = []
	numPos = bs.readInt()
	print("Num Verts: " + str(numPos))
	for i in range(0, numPos):
		posList.append(NoeVec3.fromBytes(bs.readBytes(12)))


	mesh = NoeMesh(triList, posList, meshName)

	numNrm = bs.readInt()
	print("Num Normals: "+str(numNrm))
	for j in range(0, numNrm):
		mesh.normals.append(NoeVec3.fromBytes(bs.readBytes(12)))

	numUVs = bs.readInt()
	print("Num UVs: "+str(numUVs))
        #The "slightly tricky part". 
	uvToVertexMap =[]
	for j in range(0, numUVs):
		uvToVertexMap.append(bs.readShort())
	        
	        #Useless right now, because vertices and uvs don't match.....
		mesh.uvs.append(NoeVec3((bs.readFloat(), bs.readFloat(), 0)))


        #Now we can access a vertex through a uv-coord by using uvToVertexMap[uv-index]
        
	numTris = bs.readInt()
	print("Num Tris: "+str(numTris))
	for i in range(0, numTris):

		triList.append(uvToVertexMap[bs.readShort()])
		triList.append(uvToVertexMap[bs.readShort()])
		triList.append(uvToVertexMap[bs.readShort()])

	meshes.append(mesh)

	mdl = NoeModel(meshes)
	mdlList.append(mdl)
	return 1


```


I attached a sample model (xa10010.smd). Important stuff starts at 0x34D.
I would be very grateful for any help.
[xa10010.rar](https://xentaxbackup.github.io/file/15760_xa10010.rar)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-21T04:55:05+00:00
- Post Title: Format parsing in Noesis

Any model should have the same amount of positions, normals and texture coordinates, but these data can be optimized by means of mapping information.
If you're exporting the data to a certain 3D format, you may just preserve the data optimization to save some space. But if you're dealing with the API you must convert the data to meet with the specification, i.e., remove the optimization contrarily. 
In your case since UVs could have seams the amount of texcoords are definitely greater than the one of positions. So the only solution I see is that you recreate the position list based on the uv-to-pos mapping indices.
