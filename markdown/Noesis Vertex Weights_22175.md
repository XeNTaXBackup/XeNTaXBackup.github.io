## Post #1
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2020-05-19T18:45:22+00:00
- Post Title: Noesis: Vertex Weights

Hey, I'm trying to create a plugin to import lithtech abc. I could only import bones and meshes for now. I'm currently working with vertex weights, but I'm having some problems. I did some research and came to the conclusion that I have to use rpgBindBoneIndexBuffer and rpgBindBoneWeightBuffer to "add" the weights, I might be mistaken.

The simplified structure of the model vertex is as follows (full structure can be found in [this link](https://web.archive.org/web/20080605043638/http://bop-mod.com:80/download/docs/ABC-Format-v6.html))

```
------
WeightCount # uint16 (2 bytes)
Unknown # uint16 (2 bytes)

# array of weights
Weights[WeightCount]
	- NodeIndex # uint32 (4 bytes)
	- Location # Vector (12 bytes)
	- Bias # float (4 bytes)
# end of the array

Position # Vector (12 bytes)
Normal # Vector (12 bytes)
```


I created a class to vertex and weight

```
    def __init__(self):
        self.weights = []
        self.location = NoeVec3()
        self.normal = NoeVec3()

class AbcWeight(object):
    def __init__(self):
        self.nodeIndex = 0
        self.location = NoeVec3()
        self.bias = 0.0

```


and I read the data as follows

```
    vertex = AbcVertex()
    bs = self.bs
    weightCount = bs.readUShort()
    unknown = bs.readUShort()
    vertex.weights = [self.loadWeight() for _ in range(weightCount)]
    vertex.location = NoeVec3.fromBytes(bs.readBytes(12))
    vertex.normal = NoeVec3.fromBytes(bs.readBytes(12))
    return vertex

def loadWeight(self):
    weight = AbcWeight()
    bs = self.bs
    weight.nodeIndex = bs.readUInt()
    weight.location = NoeVec3.fromBytes(bs.readBytes(12))
    weight.bias = bs.readFloat()
    return weight

```


Until here everything is working, the problem is that I'm not able to assign the weights to the model. Assuming that my guess about rpgBindBoneIndexBuffer and rpgBindBoneWeightBuffer is right, I did it as follows

```
for vertex in lod.vertices: # lod.vertices is a list of AbcVertex objects
    bidx = []
    bwgt = []
    for weight in vertex.weights:
        bidx.append(weight.nodeIndex)
        bwgt.append(weight.bias)
    vwList.append(NoeVertWeight(bidx, bwgt))

fw = NoeFlatWeights(vwList)
rapi.rpgBindBoneIndexBuffer(fw.flatW[:fw.weightValOfs], noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
rapi.rpgBindBoneWeightBuffer(fw.flatW[fw.weightValOfs:], noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)

```


but I'm getting this error

```

```


I searched for the error, but I couldn't find anything that is relevant. Does anyone know what am I doing wrong? Thanks in advance
## Post #2
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-19T18:57:05+00:00
- Post Title: Noesis: Vertex Weights

Hi,

Upload a sample file and ill see if i can help you
## Post #3
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2020-05-19T19:07:50+00:00
- Post Title: Noesis: Vertex Weights

Sure. I also have the lta model of this sample file, it can be opened in any text editor
[https://www.mediafire.com/file/ex58nvpi ... s.rar/file](https://www.mediafire.com/file/ex58nvpii2jvgcv/sample_files.rar/file)
## Post #4
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-19T20:02:42+00:00
- Post Title: Noesis: Vertex Weights

I just noticed you didn't post you full script only parts of it,

can you post entire script please, i dont feel like writing the whole thing from scratch just to test if weights are working   

i have always used a different set for weights and bone index:

```
rapi.rpgBindBoneWeightBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 16, 0, 4)
```


if you continue to get same error check the following things:
1. the bone index buffer you provided might be to small
2. you are using the wrong type (INT,SHORT etc..)
3. number of total bytes used is wrong or number of bone index is wrong.
## Post #5
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2020-05-19T20:09:05+00:00
- Post Title: Noesis: Vertex Weights

The script:

```
import os

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
    handle = noesis.register("LithTech ABC", ".abc")
    noesis.setHandlerTypeCheck(handle, abcCheckType)
    noesis.setHandlerLoadModel(handle, abcLoadModel)

    noesis.logPopup()
    return 1

#check if it's this type based on the data
def abcCheckType(data):
    abc = AbcFile(NoeBitStream(data))
    return abc.loadHeader()

#read it
def abcLoadModel(data, mdlList):
    abc = AbcFile(NoeBitStream(data))
    model = abc.loadData()
    model = abcConstructModelFromAbc(model)
    if model is not None:
        mdlList.append(model)
        return 1
    return 0

def nodeIterator(nodes, nit=None, parent=None):
    if nit is None:
        nit = iter(nodes)
    node = next(nit)
    yield(node, parent)
    for i in range(node.childCount):
        for j in nodeIterator(nodes, nit, node):
            yield j

def buildUndirectedTree(nodes):
    for (node, parent) in nodeIterator(nodes):
        node.parent = parent
        node.children = []
        if parent is not None:
            parent.children.append(node)

def abcConstructModelFromAbc(abc):
    rapi.rpgCreateContext()

    for piece in abc.pieces:
        for lod_index, lod in enumerate(piece.lods):
            meshName = "%s.LOD%d" % (piece.name, lod_index)
            positions = bytes()
            normals = bytes()
            uvs = bytes()
            triangles = bytes()
            
            trianglesCount = 0
            for face in lod.faces:
                for vertex in face.vertices:
                    positions += struct.pack('3f', *lod.vertices[vertex.vertexIndex].location)
                    normals += struct.pack('3f', *lod.vertices[vertex.vertexIndex].normal)
                    uvs += struct.pack('2f', *vertex.texcoord.xy)
                    triangles += struct.pack('H', trianglesCount)
                    trianglesCount += 1

            vwList = []
            for vertex in lod.vertices:
                bidx = []
                bwgt = []
                for weight in vertex.weights:
                    bidx.append(weight.nodeIndex)
                    bwgt.append(weight.bias)
                vwList.append(NoeVertWeight(bidx, bwgt))
            fw = NoeFlatWeights(vwList)

            rapi.rpgSetName(meshName)
            rapi.rpgBindPositionBuffer(positions, noesis.RPGEODATA_FLOAT, 12)
            rapi.rpgBindNormalBuffer(normals, noesis.RPGEODATA_FLOAT, 12)
            rapi.rpgBindUV1Buffer(uvs, noesis.RPGEODATA_FLOAT, 8)
            #rapi.rpgBindBoneIndexBuffer(fw.flatW[:fw.weightValOfs], noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
            #rapi.rpgBindBoneWeightBuffer(fw.flatW[fw.weightValOfs:], noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)

            material = NoeMaterial(meshName, abc.fileName)
            material.setDefaultBlend(0)
            abc.materials.append(material)

            rapi.rpgSetMaterial(meshName)
            rapi.rpgCommitTriangles(triangles, noesis.RPGEODATA_USHORT, trianglesCount, noesis.RPGEO_TRIANGLE, 1)
            rapi.rpgClearBufferBinds()

    model = rapi.rpgConstructModel()
    model.setModelMaterials(NoeModelMaterials(abc.textures, abc.materials))

    noeBones = []
    for node in abc.nodes:
        if node.parent is not None:
            noeBones.append(NoeBone(node.index, node.name, node.matrix, node.parent.name, node.parent.index))
        else:
            noeBones.append(NoeBone(node.index, node.name, node.matrix))
    model.setBones(noeBones)

    return model

def abcStrFromBytes(data):
    try:
        str = noeStrFromBytes(data)
    except:
        print("WARNING: Non-ASCII string data:", data)
        str = "not_an_ascii_string"
    return str

class AbcModel(object):
    def __init__(self):
        self.pieces = []
        self.materials = []
        self.textures = []
        self.nodes = []
        self.animations = []
        self.fileName = ''

class AbcPiece(object):
    def __init__(self):
        self.name = ''
        self.lods = []

class AbcNode(object):
    def __init__(self):
        self.index = 0
        self.name = ''
        self.matrix = NoeMat43()
        self.flags = 0
        self.childCount = 0

class AbcLod(object):
    def __init__(self):
        self.faces = []
        self.vertices = []

class AbcFace(object):
    def __init__(self):
        self.vertices = []

class AbcFaceVertex(object):
    def __init__(self):
        self.texcoord = NoeVec3()
        self.vertexIndex = 0

class AbcVertex(object):
    def __init__(self):
        self.weights = []
        self.location = NoeVec3()
        self.normal = NoeVec3()

class AbcWeight(object):
    def __init__(self):
        self.nodeIndex = 0
        self.location = NoeVec3()
        self.bias = 0.0

class AbcFile(object):
    def __init__(self, bs):
        self.bs = bs
        self.nodeCount = 0
        self.lodCount = 0
    
    def loadHeader(self):
        bs = self.bs
        strLen = bs.readUShort()
        headerString = abcStrFromBytes(bs.readBytes(strLen))
        return headerString == 'Header'

    def loadData(self):
        bs = self.bs
        model = AbcModel()
        inputName = rapi.getLocalFileName(rapi.getInputName())
        fileName, fileExt = os.path.splitext(inputName)
        model.fileName = fileName
        nextSectionOffset = 0
        while nextSectionOffset != -1:
            bs.seek(nextSectionOffset)
            strLen = bs.readUShort()
            sectionName = abcStrFromBytes(bs.readBytes(strLen))
            nextSectionOffset = bs.readInt()

            if sectionName == 'Header':
                bs.seek(12, 1)
                self.nodeCount = bs.readUInt()
                bs.seek(20, 1)
                self.lodCount = bs.readUInt()
            elif sectionName == 'Pieces':
                weightCount, piecesCount = bs.read('2L')
                model.pieces = [self.loadPiece() for _ in range(piecesCount)]
            elif sectionName == 'Nodes':
                model.nodes = [self.loadNode() for _ in range(self.nodeCount)]
                buildUndirectedTree(model.nodes)

        return model

    def loadPiece(self):
        piece = AbcPiece()
        bs = self.bs
        bs.seek(16, 1)
        strLen = bs.readUShort()
        piece.name = abcStrFromBytes(bs.readBytes(strLen))
        piece.lods = [self.loadLod() for _ in range(self.lodCount)]
        return piece

    def loadNode(self):
        node = AbcNode()
        bs = self.bs
        strLen = bs.readUShort()
        node.name = abcStrFromBytes(bs.readBytes(strLen))
        node.index = bs.readUShort()
        node.flags = bs.readByte()
        node.matrix = NoeMat44.fromBytes(bs.readBytes(64)).transpose().toMat43()
        node.childCount = bs.readUInt()
        return node

    def loadLod(self):
        lod = AbcLod()
        bs = self.bs
        faceCount = bs.readUInt()
        lod.faces = [self.loadFace() for _ in range(faceCount)]
        vertexCount = bs.readUInt()
        lod.vertices = [self.loadVertex() for _ in range(vertexCount)]
        return lod

    def loadFace(self):
        face = AbcFace()
        face.vertices = [self.loadFaceVertex() for _ in range(3)]
        return face

    def loadFaceVertex(self):
        vertex = AbcFaceVertex()
        bs = self.bs
        vertex.texcoord.xy = bs.read('2f')
        vertex.vertexIndex = bs.readUShort()
        return vertex

    def loadVertex(self):
        vertex = AbcVertex()
        bs = self.bs
        weightCount = bs.readUShort()
        unknown = bs.readUShort()
        vertex.weights = [self.loadWeight() for _ in range(weightCount)]
        vertex.location = NoeVec3.fromBytes(bs.readBytes(12))
        vertex.normal = NoeVec3.fromBytes(bs.readBytes(12))
        return vertex

    def loadWeight(self):
        weight = AbcWeight()
        bs = self.bs
        weight.nodeIndex = bs.readUInt()
        weight.location = NoeVec3.fromBytes(bs.readBytes(12))
        weight.bias = bs.readFloat()
        return weight

```
## Post #6
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-20T08:55:33+00:00
- Post Title: Noesis: Vertex Weights

hI,

I finally had some time to look at the code, a bit hard to follow all those function, everything looks good.
i am not sure what the problem is  

if i have time later today or tomorrow ill try writing it as noemesh() so we can print out everything easily and hopefully find a solution

can you please check something that seems off to me,
first mesh has 274 weights, mesh has 993 vertices  
second mesh has 1250 weights, mesh has 3660 vertices  
each vert should have a weight, could be 1 weight per vert could be 4 etc..

tell me if i am missing something here
## Post #7
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-20T12:49:19+00:00
- Post Title: Noesis: Vertex Weights

I got it working   

> can you please check something that seems off to me,
>
> first mesh has 274 weights, mesh has 993 vertices
>
> second mesh has 1250 weights, mesh has 3660 vertices
>
> each vert should have a weight, could be 1 weight per vert could be 4 etc..

this was the key, i got it working with a messy noemesh script, ill fix code back to rapi and post it later today.
basically you were reading the vertices and face data wrong.

```
                for vertex in face.vertices:
                    positions += struct.pack('3f', *lod.vertices[vertex.vertexIndex].location)
                    normals += struct.pack('3f', *lod.vertices[vertex.vertexIndex].normal)
                    uvs += struct.pack('2f', *vertex.texcoord.xy)
                    triangles += struct.pack('H', trianglesCount)
                    trianglesCount += 1
```


this section is the problem
vertex.vertexIndex is you face index
## Post #8
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2020-05-20T15:31:44+00:00
- Post Title: Noesis: Vertex Weights

> Reply from jayn23 ↑Wed May 20, 2020 4:55 pm at Wed May 20, 2020 4:55 pm
>
> 
first mesh has 274 weights, mesh has 993 vertices  
second mesh has 1250 weights, mesh has 3660 vertices  
each vert should have a weight, could be 1 weight per vert could be 4 etc..

tell me if i am missing something here

I have a tool that shows details of the model. According to the tool, the first mesh of that model, which is "Pulse_Rifle_3d", has 331 triangles (faces) and 274 vertices, each vertex has 1 weight. The second mesh, which is "thumb", has 1220 triangles and 625 vertices. Of these 625 vertices, some have 2 weights, while others have only 1 weight. You can see the weights in the "weightsets" section (without quotes) in the LTA file I sent you.

For some reason, my script triples the number of vertices. From 274 vertices in the first mesh, it goes to 993 and from 1220 in the second mesh, it goes to 3660. I don't know if this is a bug or it's working correctly.

> Reply from jayn23 ↑Wed May 20, 2020 8:49 pm at Wed May 20, 2020 8:49 pm
>
> 
I got it working   
can you please check something that seems off to me,
first mesh has 274 weights, mesh has 993 vertices
second mesh has 1250 weights, mesh has 3660 vertices
each vert should have a weight, could be 1 weight per vert could be 4 etc..

this was the key, i got it working with a messy noemesh script, ill fix code back to rapi and post it later today.
basically you were reading the vertices and face data wrong.
Code: Select all            for face in lod.faces:
                for vertex in face.vertices:
                    positions += struct.pack('3f', *lod.vertices[vertex.vertexIndex].location)
                    normals += struct.pack('3f', *lod.vertices[vertex.vertexIndex].normal)
                    uvs += struct.pack('2f', *vertex.texcoord.xy)
                    triangles += struct.pack('H', trianglesCount)
                    trianglesCount += 1

this section is the problem
vertex.vertexIndex is you face index

Okay! Take your time
## Post #9
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-20T18:29:44+00:00
- Post Title: Noesis: Vertex Weights

Heres the working script, back in rapi format
Checked it in 3dsmax - weights look good.

i think you should take a look at uvs, they dont look good - iv had enough of this format not even going to try  
[fmt_LithTech.rar](https://xentaxbackup.github.io/file/18181_fmt_LithTech.rar)
## Post #10
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2020-05-21T01:27:06+00:00
- Post Title: Noesis: Vertex Weights

Hey, thank you much! It's working just fine now
