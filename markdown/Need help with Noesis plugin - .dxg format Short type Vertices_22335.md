## Post #1
- Username: Descatal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 21, 2016 11:49 am
- Post datetime: 2020-06-30T04:30:20+00:00
- Post Title: Need help with Noesis plugin - .dxg format Short type Vertices

I need help in fixing the Noesis Plugin for the case of .dxg models using Short instead of Float Vertices. 
Using the normal Plugin I can view most of the aisp@ce dxg models after applying shakotay2's patch to the script, but unfortunately the model I want is still messed up.

Upon more investigations I found out the Vertices have different data type. 
Here's an example of normal float type data:
[https://imgur.com/ky4li5S](https://imgur.com/ky4li5S)

Here's an example of suspected short type data:
[https://imgur.com/7tx2ZAy](https://imgur.com/7tx2ZAy)

From the script, the default vertBuff, normBuff and UVBuff sizes are calculated assuming the types are float

```
        #indices
        self.parse_indices(mesh.numVerts, mesh)
        mesh.idxBuff = self.parse_faces(mesh.numFaces * 3)
        self.inFile.seek(startofverts)
        mesh.vertBuff = self.inFile.readBytes(numCoords * 12)
        mesh.normBuff = self.inFile.readBytes(numNorms * 12)
        mesh.uvBuff = self.inFile.readBytes(numUV * 8)   

```


and if you look in build_mesh()

```
            posIdx, normIdx, uvIdx = mesh.posList[i], mesh.normList[i], mesh.uvList[i]
            vertBuff = b''.join([vertBuff, mesh.vertBuff[posIdx * 12 : (posIdx+1) * 12]])
            normBuff = b''.join([normBuff, mesh.normBuff[normIdx * 12 : (normIdx+1) * 12]])
            uvBuff = b''.join([uvBuff, mesh.uvBuff[uvIdx * 8 : (uvIdx+1) * 8]])
            
        rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_FLOAT, 12)
        rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_FLOAT, 12)
        rapi.rpgBindUV1Buffer(uvBuff, noesis.RPGEODATA_FLOAT, 8)

```


You can see that the RPGEODATA used for each rpgBind is FLOAT type. 

I did the obvious and tried to change the Buffer size alongside RPGEODATA_FLOAT to RPGEODATA_SHORT, but the models still has messed up mesh.

Here's what I changed for each Buff:

```
        mesh.normBuff = self.inFile.readBytes(numNorms * 6)
        mesh.uvBuff = self.inFile.readBytes(numUV * 4)   

```


and in build_mesh()

```
            posIdx, normIdx, uvIdx = mesh.posList[i], mesh.normList[i], mesh.uvList[i]
            vertBuff = b''.join([vertBuff, mesh.vertBuff[posIdx * 6 : (posIdx+1) * 6]])
            normBuff = b''.join([normBuff, mesh.normBuff[normIdx * 6 : (normIdx+1) * 6]])
            uvBuff = b''.join([uvBuff, mesh.uvBuff[uvIdx * 4 : (uvIdx+1) * 4]])
            
        rapi.rpgBindPositionBuffer(vertBuff, noesis.RPGEODATA_SHORT, 6)
        rapi.rpgBindNormalBuffer(normBuff, noesis.RPGEODATA_SHORT, 6)
        rapi.rpgBindUV1Buffer(uvBuff, noesis.RPGEODATA_SHORT, 4)

```


The logic here is that since Float XYZ take 12 bytes, a Short XYZ will only take 6 bytes. I have also tried using HALFFLOAT but still failed.

I will attach both version of the dxg model files w/ the script here:
202201_0_01_000.dxg - Float Type
202201_0_02_000.dxg - Short Type
Also, there's a memo on the dxg format done by some Japanese modder. You will need to use wordpad++ to parse the Japanese comments. I could translate the comments if you like.


 dxg model.zip
(107.02 KiB) Downloaded 20 times




May I ask what am I doing wrong? Any help would be appreciated, and thanks in advance.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-30T08:03:57+00:00
- Post Title: Need help with Noesis plugin - .dxg format Short type Vertices

> Reply from Descatal ↑Tue Jun 30, 2020 12:30 pm at Tue Jun 30, 2020 12:30 pm
>
> 
I need help in fixing the Noesis Plugin for the case of .dxg models using Short instead of Float Vertices. 
Using the normal Plugin I can view most of the aisp@ce dxg models after applying shakotay2's patch to the script, but unfortunately the model I want is still messed up.Well, I'm not sure whether there's submeshes using shorts in 202201_0_02_000.dxg. Did you find the float submesh (start of float vertices at 0x49D4)?
.



202201_0_02_000.png (43.71 KiB) Viewed 125 times



In case you did not you need to care for startofverts  explained here:

> Reply from shakotay2 ↑Wed May 25, 2016 6:29 pm at Wed May 25, 2016 6:29 pm
>
> 
and find out how to skip the bone data sections. You have to  sum up the offsets/sizes (DWORD, 10 bytes before the first FFFF of each shorts blocks):
0x2b78, 47c,2ce,31c,48e,3c0,3cc,2aa,382,B4 -> 0x4944, plus "starting" offset: 0x68, plus 10x4 for size of offsets  to get the 0x49D4.

(In case you did: the shorts you mentioned maybe part of facial animation data, whatever.)
## Post #3
- Username: Descatal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 21, 2016 11:49 am
- Post datetime: 2020-06-30T11:26:19+00:00
- Post Title: Need help with Noesis plugin - .dxg format Short type Vertices

Thanks for the reply. I did not consider those, so pointing to the correct start offset fixed it. Thank you. 

As for the mesh, is there any reason why it is "missing" a few sections?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-30T12:44:53+00:00
- Post Title: Need help with Noesis plugin - .dxg format Short type Vertices

From the point cloud it looks complete using 651 vertices:
.



face.png (10 KiB) Viewed 106 times



You'll need to dig into the script to see how the faces are built.
## Post #5
- Username: Descatal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 21, 2016 11:49 am
- Post datetime: 2020-07-01T02:25:56+00:00
- Post Title: Need help with Noesis plugin - .dxg format Short type Vertices

Sorry I am not very well versed in 3D stuff, but what I can understand is that the number of vertex is stored in the numCoords variable and used to calculate the vertBuff size. I tried to do the calculations myself but the buffer stops halfway through the sea of float vertices. 

```
        self.inFile.read('4L')
        meshSize = self.inFile.readUInt()
        numCoords, numNorms, numUV, null = self.inFile.read('4H')
        self.inFile.read('2L')
        mesh.numVerts, mesh.numFaces = self.inFile.read('2H')
        self.inFile.read('2L')
        sectionSize = self.inFile.readUInt()
        #offs= self.inFile.tell()
        #startofverts= sectionSize+offs        

        #indices
        self.parse_indices(mesh.numVerts, mesh)
        mesh.idxBuff = self.parse_faces(mesh.numFaces * 3)
        self.inFile.seek(0x49D4)
        mesh.vertBuff = self.inFile.readBytes(numCoords * 12)
        mesh.normBuff = self.inFile.readBytes(numNorms * 12)
        mesh.uvBuff = self.inFile.readBytes(numUV * 8)   

```


May I see the values you put into MeshExtractor? Thanks for helping again
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-01T07:00:56+00:00
- Post Title: Need help with Noesis plugin - .dxg format Short type Vertices

202201_0_02_000-dxg.png (33.12 KiB) Viewed 90 times
