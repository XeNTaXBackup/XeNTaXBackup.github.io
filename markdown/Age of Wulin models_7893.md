## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-19T19:24:56+00:00
- Post Title: Age of Wulin models

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-12-20T14:57:05+00:00
- Post Title: Age of Wulin models

nice one finale, thanks a lot to you and aluigi for unpacker
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-02T17:35:39+00:00
- Post Title: Age of Wulin models

There are different mesh types and different vertex types.

The first four bytes are the idstring XVAM.
Then the 5th byte might be a 1 or a 2. The mesh follows a different struct depending on the value.
So far I think 1 means unskinned while 2 is skinned.

After each mesh name, there's an integer, and then another 4 bytes. This seems to determine the size of the vertex (32 bytes, 36 bytes, or 56 bytes).

I don't have all of the files with me so I'm not sure if there's more values to look at it, but so far I've managed to parse geometry from files that only have one mesh.

Bones are there in the XMOD, but I can't seem to find any bone transforms.
And I don't have the entire game with me so maybe I might have left that those somewhere else...
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-03T07:54:31+00:00
- Post Title: Age of Wulin models

So I've found 7 vertex types so far: 24, 32, 36, 40, 44, 56, 64 bytes.
There is some flag that determines whether the model has bones/weights or not.
There is some flag that determines what kinds of textures the model uses (diffuse, specular, and/or normal)

Depending on some flags, the material section will have varying amount of floats (I guess these are related to the material, depending on what is actually used)

The real problem is what each value means, and which combination results in what.
Looking at a single value is not enough to determine things like vertSize.

The format is something like

```
Model information including 4 special bytes

numMesh {
   Mesh information { (with 4 special bytes)
       vertices
       indices
       weights (maybe)
       bones (maybe)
       Material
   }
}

```


This is a portion of the table that I put together while searching for patterns amongst those "special bytes"
vb1 to vb4 are the bytes in the model header. mb1 to mb4 are the bytes in each mesh. Note that vb and mb values are in hex, while vertSize is in decimal (cause I typed that one)



The flag I called "mb2" takes on values 0x4, 0x14, 0x54, 0x74, and 0x94. And 0x15 for some reason.
0x4 means there are no textures.
0x14 means there is a diffuse texturemap.
0x54 means there is a diffuse and also specular texturemaps
0x74 means there is diffuse, specular, and normal texturemaps.
0x94 has diffuse and specular, but then followed by two integer 0's.



Certain combinations of bytes guarantee certain pieces of information, so the parser code is basically full of conditional statements checking a bunch of these combinations that I've come across. And I've only looked at the outfits! Haven't even touched the items and weapons and decorations.

But ok, at the very least the models aren't faceless anymore...
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-05T08:34:57+00:00
- Post Title: Age of Wulin models

Well, this is quite fortunate.
I was looking through the gm2 files and found some text files that the devs probably left behind. Although there are only 5 and in the same folder (among the hundreds of folders).

It is a pretty simple file, but it makes some things quite clear (although even if I know what the data represents, I still don't know what it actually does lol)

Example:

> objects' numbers: 4
>
> {
>
> object0's name: Huotan0903
>
> object1's name: Huotan0900
>
> object2's name: Huotan0901
>
> object3's name: Huotan0902
>
> }
>
> textures' numbers: 4
>
> {
>
> texture0's name: gybaitan001gh.dds
>
> texture1's name: sst001_dqg.dds
>
> texture2's name: jyhuotanhww005.dds
>
> texture3's name: jyhuotanhww004.dds
>
> }
>
> materials' numbers: 4
>
> triangles' numbers: 2630, vertices' numbers: 2563
>
> 2-sided triangles' numbers: 325
>
> bbox_size: 4.820763,3.562109,3.108685, radius: 3.285993
>
> traverses/vertex: 101.595947, max depth: 69

```

#A single model may contain multiple meshes.

#Each mesh defines the number of vertices and faces that make up the mesh.

#The index and vertex buffers follow afterwards, for all of the meshes
#(so you need to store the individual numbers somewhere when you parse it)

#You need to know the total number of faces and vertices.

#The size of the vertex is determined by vertSectionSize / totalVertex, where the section size is given to you
#before you start parsing the vertices

Basic idea of the format

Header
Material/Mesh names

Material 1
Material 2
...

Mesh 1
Mesh 2
...

All indices
All vertices

==========================================================

struct Header {
	char[4] idstring "60.1"
	dword
	dword matSectionSize
	dword numNames
	dword numMat
	dword numMesh
	dword
	dword
	dword
	dword total Faces
	dword
}

struct unkStruct {
	dword[2]
	float[3]
	dword[6]
	dword[3]
}

struct Vertex {
	// standard vertex info.
	// Varies depending on the size of the vertex
}

struct Mesh {
	
	dword[3]
	float[4]
	dword
	dword numFaces
	dword
	dword numVerts
	byte[64] just_skip_it
}

struct File {
	Header
	float_3 bboxMin
	float_3 bboxMax // or maybe the other way around
	float radius
	
	numName {
		string_0 name // null-terminated strings
		// usually matName, texName, ?, meshName but sometimes different...
	}
	
        dword 
	############
	dword[??] integers // see below
	############
	
	numMesh unkStruct // I don't know
	numMesh Mesh 
	
	word[TotalFaces * 3] indices
	dword ???
	dword vertSectionSize
	totalVerts Vertex
}

```


For the ############# section, I just wrote this

```
   dword[4*numMesh]
else
   dword[3*numMat]

```


Still not perfect with some files, but at least it renders most of them properly.
Now to figure out how the names (mats, tex, meshes) work...

Here's a temple



The entire map can be built just by loading up all of the models into one scene (although it will take some time...)
[gm2.7z](https://xentaxbackup.github.io/file/4955_gm2.7z)
## Post #6
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2012-04-27T05:10:25+00:00
- Post Title: Age of Wulin models

flip model ?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-27T08:35:40+00:00
- Post Title: Age of Wulin models

Ya, for some reason all of the models I view are flipped.
For EVERY game I've tried lol

I don't know why.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-27T12:06:58+00:00
- Post Title: Age of Wulin models

Probably lhs rhs thing.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-27T15:39:13+00:00
- Post Title: Age of Wulin models

Hmm well I do remember seeing something about some left-hand right-hand coordinate system but don't know how I should be changing how I draw the model lol
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-27T16:00:45+00:00
- Post Title: Age of Wulin models

when parsing, negate one of the x, y, or z coordinates. typically z. noesis is opengl and RHCS. directx is LHCS. depends on the rendering api.
## Post #11
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2012-05-30T03:32:05+00:00
- Post Title: Age of Wulin models

i open gm2 is err, please hlep , thanks
[err.jpg](https://xentaxbackup.github.io/file/5471_err.jpg)
## Post #12
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2012-05-30T03:38:29+00:00
- Post Title: Age of Wulin models

huotan09.gm2 is ok ...
[err2.jpg](https://xentaxbackup.github.io/file/5472_err2.jpg)
## Post #13
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2012-05-30T04:01:24+00:00
- Post Title: Age of Wulin models

[err3.jpg](https://xentaxbackup.github.io/file/5473_err3.jpg)
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-05-30T15:27:11+00:00
- Post Title: Age of Wulin models

Fatduck has support for this game in his max importer.

[viewtopic.php?f=33&t=7901](http://forum.xentax.com/viewtopic.php?f=33&t=7901)
## Post #15
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2012-05-31T10:08:43+00:00
- Post Title: Age of Wulin models

> Reply from finale00
>
> Fatduck has support for this game in his max importer.

viewtopic.php?f=33&t=7901

  where ... 
[thx.jpg](https://xentaxbackup.github.io/file/5477_thx.jpg)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-05-31T18:16:09+00:00
- Post Title: Re: Age of Wulin models

Oh, looks like it disappeared. I saw it in a screenshot but looks like he removed it lol
## Post #17
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2012-06-09T02:42:15+00:00
- Post Title: Re: Age of Wulin models

> Reply from finale00
>
> Oh, looks like it disappeared. I saw it in a screenshot but looks like he removed it lol

Thank you for your help ...
## Post #18
- Username: ridack
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Aug 01, 2013 9:26 am
- Post datetime: 2013-08-09T03:25:56+00:00
- Post Title: Re: Age of Wulin models

i try to open GM2 file ([http://www.mediafire.com/download/wwno9 ... lone099.7z](http://www.mediafire.com/download/wwno9m67wn2vkhc/clone099.7z))
 with this plugin : [https://www.dropbox.com/sh/7stlpd4qvkq3 ... lin_gm2.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/KUKlbCpXGO/fmt_AgeOfWulin_gm2.py)
BUT he say me this error 
[](http://grabilla.com/03808-85fb18bb-9b3b-4678-bc38-23f47da764f5.html)

WHY?
how to repair the plugin?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-09T11:40:44+00:00
- Post Title: Re: Age of Wulin models

> Reply from ridack
>
> how to repair the plugin?Understand models. Learn python scripting. Understand Noesis.  

Or just wait for finale00.

I had a try but got a funny model only: [](http://www.pic-upload.de/view-20349467/funny.jpg.html)

You might have a look at the slightly changed script; be informed that I also tested vertSize = 48, 56 and 64 for wuguancs.gm2 (because it's calculated to 13 from the model data).

edit: ok, looks like 44 is correct. But then you need an offset of +8 (val = self.inFile.read('2L') ) to get an idea of a house.

(sorry, finale00, if I ruined  your code, it was just for a test):

```
import noesis
import rapi
#from Sanae3D.Sanae import SanaeObject
import os

MODE = 0

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("Age of Wulin", ".gm2")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    return 1

def load_all_models(mdlList):
    '''Load all models'''

    #carry over from previous models
    matList = []
    texList = []

    dirPath = rapi.getDirForFilePath(rapi.getInputName())
    fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".gm2")]
    for file in fileList:
        f = open(dirPath + file, 'rb')
        data2 = f.read()
        parser = SanaeParser(data2)
        parser.parse_file()
        matList.extend(parser.matList)
        texList.extend(parser.texList)
        mdl = rapi.rpgConstructModel()
    mdl.setModelMaterials(NoeModelMaterials(texList, matList))
    mdlList.append(mdl)    
    
def load_single_model(data, mdlList):
    '''Loads a single model. For testing purposes'''
    
    parser = SanaeParser(data)
    parser.parse_file()
    mdl = rapi.rpgConstructModel()
    mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
    mdlList.append(mdl)       

def noepyLoadModel(data, mdlList):
    '''Load the model'''
    
    ctx = rapi.rpgCreateContext()
    if MODE == 1:
        load_all_models(mdlList)
    else:
        load_single_model(data, mdlList)
    return 1

class SanaeParser(object):
    
    def __init__(self, data):    
        '''Initialize some data. Refer to Sanae.py to see what is already
        initialized'''
        self.inFile = NoeBitStream(data)
        
        #super(SanaeParser, self).__init__(data)
        self.meshes = []
        self.vertBuffs = []
        self.idxBuffs = []
        self.materials = []
        self.matList = []
        self.texList = []

    #def readBytes(self, n):
        
        #return self.inFile.readBytes(n)
        
    def read_name(self):
        
        return self.inFile.readString()
    
    def build_mesh(self, vertSize):
        
        for i in range(len(self.vertBuffs)):
            vertBuff, numVerts = self.vertBuffs[i]
            idxBuff, numIdx = self.idxBuffs[i]
            print("--- %d numIdx ---" %numIdx)
            matName = self.materials[i]

            if vertSize == 32:
                rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 0)
                rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 12)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 24)
            elif vertSize == 36:
                rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 0)
                rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 12)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 28)
            elif vertSize == 44:
                rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
                rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 12)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 36)
            elif vertSize == 56:
                rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 56, 0)
                rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 56, 12)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 56, 48)
            elif vertSize == 52:
                rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 0)
                rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 12)
                rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 44)

            else:         # Noesis will complain "Failed to construct..."
                print("vertSize mismatch!")
                return

            rapi.rpgSetMaterial(matName)
            rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
    
    def parse_faces(self):
        
        for i in range(len(self.meshes)):
            numIdx = self.meshes[i][1] * 3
            #print("SM %d, %d numIdx" %(i, numIdx))
            idxBuff = self.inFile.readBytes(numIdx * 2)
            self.idxBuffs.append([idxBuff, numIdx])
    
    def parse_vertices(self, vertSize):
        
        for i in range(len(self.meshes)):
            x = self.inFile.tell()
            numVerts = self.meshes[i][0]
            print("0x%x: start vertsBlock (%d verts)" %(x, numVerts))
            vertBuff = self.inFile.readBytes(vertSize*numVerts)
            self.vertBuffs.append([vertBuff, numVerts])
        x = self.inFile.tell()
        print("0x%x: end" %x)

            
    def parse_materials(self, numMat):
        
        for i in range(numMat):
            matName = self.read_name()
            texName = self.read_name()
            print(self.read_name())	# bmp name   ->  comment line out for huotan09 and 13!!
            unk = self.read_name()
            #print("(%s)" %unk)
            if not unk:
                meshName = self.read_name()
            else:
                meshName = unk
            #self.materials.append([meshName, matName, texName])
            print("mat tex: %s %s" %(matName, texName))
            self.materials.append(matName)
         
            material = NoeMaterial(matName, texName)
            self.matList.append(material)
            
    def parse_file(self):
        '''Main parser method'''
        
        #idstring = self.read_string(4)
        idstring = noeStrFromBytes(self.inFile.readBytes(4))
        print("id string %s " %(idstring))

        v1 = self.inFile.readUInt()
        v2 = self.inFile.readUInt()
        numName = self.inFile.readUInt()
        numMat = self.inFile.readUInt()
        numMesh = self.inFile.readUInt()
        print("%d names, %d materials, %d meshes" %(numName, numMat, numMesh))
        v6 = self.inFile.readUInt()
        v7 = self.inFile.readUInt()
        v8 = self.inFile.readUInt()
        v9 = self.inFile.readUInt() #total faces
        v10 = self.inFile.readUInt()
        print("v6 %d, v7 %d, v8 %d, v9 %d, v10 %d" %(v6, v7, v8, v9, v10))
        
        bboxMin = self.inFile.read('3f')
        bboxMax = self.inFile.read('3f')
        radius  = self.inFile.readFloat()
        #print("radius %f" %(radius))
        
        #if numName % 4 == 0:
        self.parse_materials(numMesh)    #was (numMat) before
            
        self.inFile.readUInt()      
        if numMesh == numMat:
            self.inFile.read('%dL' %numMesh*4)
        else:
            self.inFile.read('%dL' %numMat*3)

        #loop?
        for i in range(numMesh): #numMat or v8
            val = self.inFile.read('2L')
            #print("%d %d" %(val[0], val[1]))
            fval = self.inFile.read('3f')
            #print("%f %f %f" %(fval[0], fval[1], fval[2]))
            self.inFile.read('6L')
            self.inFile.read('3l') # usually -1's
        #end loop
        totalVerts = 0
        for i in range(numMesh):
            x = self.inFile.tell()
            self.inFile.read('3L')
            self.inFile.read('4f')
            self.inFile.readUInt() #null
            numFaces = self.inFile.readUInt() #numIdx for obj
            self.inFile.readUInt()
            numVerts = self.inFile.readUInt() #total verts
            self.inFile.seek(64, 1)
            print("0x%x: SM %d, %d verts, %d faces" %(x, i, numVerts, numFaces))
            totalVerts += numVerts
            self.meshes.append([numVerts, numFaces])

        x = self.inFile.tell()
        print("vertsCnt= %d, 0x%x: start faces" %(totalVerts, x))        
        self.parse_faces()
        x = self.inFile.tell()
        print("0x%x: end faces" %x)
        self.inFile.readUInt()
        sectSize = self.inFile.readUInt()
        vertSize = sectSize // totalVerts
        if vertSize == 13:		# for wuguancs.gm2
            vertSize = 44
        print("sectSize %d, vertSize %d" %(sectSize, vertSize))
        val = self.inFile.read('2L')     # just skip 8 bytes  for wuguancs.gm2 only! 
        self.parse_vertices(vertSize)
        self.build_mesh(vertSize)
        
        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, totalVerts, noesis.RPGEO_POINTS, 1)
```
## Post #20
- Username: ridack
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Aug 01, 2013 9:26 am
- Post datetime: 2013-08-10T19:06:34+00:00
- Post Title: Re: Age of Wulin models

i have test your script python noesis it import mesh bug how fix it?

screen :
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-10T22:57:44+00:00
- Post Title: Re: Age of Wulin models

It's not my script - it's finale00's work. I just tried to patch it for wuguancs.gm2.

This is the second submesh:
[](http://www.pic-upload.de/view-20366942/Submesh1.jpg.html)

```
# 1.    0x10cb:
f 139/139 140/140 141/141 
f 141/141 142/142 139/139 
f 162/162 170/170 169/169 
f 169/169 163/163 162/162 
f 161/161 162/162 163/163 
f 163/163 164/164 161/161 
f 136/136 144/144 143/143 
f 143/143 137/137 136/136 
f 135/135 136/136 137/137 
f 137/137 138/138 135/135 
f 57/57 58/58 59/59 
f 59/59 60/60 57/57 
f 61/61 57/57 60/60 
f 60/60 62/62 61/61 
f 61/61 62/62 63/63 
f 63/63 64/64 61/61 
f 64/64 63/63 65/65 
f 65/65 66/66 64/64 
f 67/67 66/66 65/65 
f 65/65 68/68 67/67 
f 125/125 67/67 68/68 
f 68/68 126/126 125/125 
f 86/86 128/128 127/127 
f 127/127 85/85 86/86 
f 83/83 86/86 85/85 
f 85/85 84/84 83/83 
f 83/83 84/84 81/81 
f 81/81 82/82 83/83 
f 82/82 81/81 119/119 
f 119/119 120/120 82/82 
f 118/118 120/120 119/119 
f 119/119 115/115 118/118 
f 117/117 118/118 115/115 
f 115/115 116/116 117/117 
f 106/106 124/124 123/123 
f 123/123 105/105 106/106 
f 103/103 106/106 105/105 
f 105/105 104/104 103/103 
f 103/103 104/104 102/102 
f 102/102 101/101 103/103 
f 101/101 102/102 99/99 
f 99/99 100/100 101/101 
f 98/98 100/100 99/99 
f 99/99 95/95 98/98 
f 97/97 98/98 95/95 
f 95/95 96/96 97/97 
f 77/77 78/78 79/79 
f 79/79 80/80 77/77 
f 41/41 77/77 80/80 
f 80/80 42/42 41/41 
f 41/41 42/42 43/43 
f 43/43 44/44 41/41 
f 44/44 43/43 45/45 
f 45/45 46/46 44/44 
f 47/47 46/46 45/45 
f 45/45 48/48 47/47 
f 121/121 47/47 48/48 
f 48/48 122/122 121/121 
f 37/37 38/38 39/39 
f 39/39 40/40 37/37 
f 37/37 40/40 22/22 
f 22/22 21/21 37/37 
f 21/21 22/22 2/2 
f 2/2 1/1 21/21 
f 1/1 2/2 3/3 
f 3/3 4/4 1/1 
f 18/18 4/4 3/3 
f 3/3 19/19 18/18 
f 17/17 18/18 19/19 
f 19/19 20/20 17/17 
f 31/31 17/17 20/20 
f 20/20 32/32 31/31 
f 31/31 32/32 29/29 
f 29/29 30/30 31/31 
f 171/171 172/172 173/173 
f 173/173 174/174 171/171 
f 174/174 173/173 175/175 
f 175/175 176/176 174/174 
f 176/176 175/175 177/177 
f 177/177 178/178 176/176 
f 165/165 166/166 167/167 
f 167/167 168/168 165/165 
f 145/145 146/146 147/147 
f 147/147 148/148 145/145 
f 148/148 147/147 149/149 
f 149/149 150/150 148/148 
f 150/150 149/149 151/151 
f 151/151 152/152 150/150 
f 187/187 188/188 189/189 
f 189/189 190/190 187/187 
f 190/190 189/189 191/191 
f 191/191 192/192 190/190 
f 129/129 130/130 131/131 
f 131/131 132/132 129/129 
f 133/133 129/129 132/132 
f 132/132 134/134 133/133 
f 7/7 8/8 5/5 
f 5/5 6/6 7/7 
f 33/33 7/7 6/6 
f 6/6 34/34 33/33 
f 33/33 34/34 26/26 
f 26/26 25/25 33/33 
f 25/25 26/26 23/23 
f 23/23 24/24 25/25 
f 24/24 23/23 9/9 
f 9/9 12/12 24/24 
f 11/11 12/12 9/9 
f 9/9 10/10 11/11 
f 27/27 11/11 10/10 
f 10/10 28/28 27/27 
f 35/35 27/27 28/28 
f 28/28 36/36 35/35 
f 35/35 36/36 13/13 
f 13/13 16/16 35/35 
f 15/15 16/16 13/13 
f 13/13 14/14 15/15 
f 185/185 186/186 184/184 
f 184/184 183/183 185/185 
f 183/183 184/184 182/182 
f 182/182 181/181 183/183 
f 181/181 182/182 179/179 
f 179/179 180/180 181/181 
f 153/153 154/154 155/155 
f 155/155 156/156 153/153 
f 156/156 155/155 157/157 
f 157/157 158/158 156/156 
f 158/158 157/157 159/159 
f 159/159 160/160 158/158 
f 107/107 108/108 109/109 
f 109/109 110/110 107/107 
f 110/110 109/109 111/111 
f 111/111 112/112 110/110 
f 112/112 111/111 113/113 
f 113/113 114/114 112/112 
f 87/87 88/88 89/89 
f 89/89 90/90 87/87 
f 90/90 89/89 91/91 
f 91/91 92/92 90/90 
f 92/92 91/91 93/93 
f 93/93 94/94 92/92 
f 69/69 70/70 71/71 
f 71/71 72/72 69/69 
f 72/72 71/71 73/73 
f 73/73 74/74 72/72 
f 74/74 73/73 75/75 
f 75/75 76/76 74/74 
f 49/49 50/50 51/51 
f 51/51 52/52 49/49 
f 52/52 51/51 53/53 
f 53/53 54/54 52/52 
f 54/54 53/53 55/55 
f 55/55 56/56 54/54 
#   145b:
# face index min/max: 1 / 192

v  -9.373561 9.910271 -1.447659
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.126903 0.299193
vt 0.013752 0.958846 
v  -9.770417 9.910270 -1.160959
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.040363 0.299076
vt 0.155479 0.905387 
v  -9.837403 9.910270 -1.160878
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.040321 0.267961
vt 0.167970 0.905372 
v  -9.837403 9.910271 -1.283520
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.127071 0.267961
vt 0.167970 0.928240 
v  -9.770419 9.910271 -1.283554
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.127088 0.299079
vt 0.155480 0.928247 
v  -9.373561 9.910270 -1.160959
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.302015 0.299763
vt 0.726912 0.508893 
v  -9.373473 9.910270 -1.101531
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.302060 0.268645
vt 0.726928 0.519974 
v  -9.493724 9.910270 -1.101531
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.243736 0.268645
vt 0.704506 0.519974 
v  -9.493707 9.910270 -1.160959
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.243744 0.299763
vt 0.704509 0.508893 
v  -9.770417 9.910271 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.300928 0.299609
vt 0.824195 0.687479 
v  -9.770539 9.910271 -1.633705
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.300991 0.268491
vt 0.824172 0.676404 
v  -9.650290 9.910271 -1.633705
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.243100 0.268491
vt 0.846594 0.676404 
v  -9.650273 9.910271 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.243092 0.299609
vt 0.846597 0.687479 
v  -9.837403 9.947912 -1.101531
vn  0.000000 -0.000006 1.000000
#  -1.003922 0.040097 0.000979
vt 0.455472 0.994393 
v  -9.770539 9.910270 -1.101531
vn  0.000000 -0.000006 1.000000
#  -1.003922 0.067508 0.034104
vt 0.448453 0.981925 
v  -9.493724 9.910270 -1.101531
vn  0.000000 -0.000006 1.000000
#  -1.003922 0.245405 0.030824
vt 0.448453 0.930310 
v  -9.373473 9.910270 -1.101531
vn  0.000000 -0.000006 1.000000
#  -1.003922 0.311478 0.026718
vt 0.448453 0.907888 
v  -9.310534 9.947912 -1.101531
vn  0.000000 -0.000001 1.000000
#  -1.003922 0.347398 0.000708
vt 0.455472 0.896152 
v  -9.310534 9.910271 -1.283520
vn  1.000000 -0.000004 -0.000001
#  -1.003922 0.139399 0.030798
vt 0.294973 0.960902 
v  -9.310534 9.910271 -1.447625
vn  1.000000 -0.000004 -0.000001
#  -1.003922 0.248684 0.030768
vt 0.294974 0.930303 
v  -9.310534 9.947912 -1.633705
vn  1.000000 -0.000004 -0.000001
#  -1.003922 0.348108 0.000708
vt 0.301992 0.895606 
v  -9.310534 9.947912 -1.101531
vn  1.000000 0.000001 -0.000000
#  -1.003922 0.040149 0.000640
vt 0.301992 0.994836 
v  -9.373473 9.910271 -1.633705
vn  0.000000 -0.000000 -1.000000
#  -1.003922 0.067167 0.034112
vt 0.141494 0.645371 
v  -9.493724 9.910271 -1.633705
vn  0.000000 -0.000000 -1.000000
#  -1.003922 0.142589 0.030844
vt 0.141494 0.622949 
v  -9.310534 9.947912 -1.633705
vn  0.000000 -0.000000 -1.000000
#  -1.003922 0.040303 0.000666
vt 0.148513 0.657107 
v  -9.837403 9.910271 -1.574329
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.067035 0.034084
vt 0.141494 0.871364 
v  -9.837403 9.910271 -1.447624
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.139107 0.030810
vt 0.141494 0.847738 
v  -9.837403 9.947912 -1.633705
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.040331 0.000928
vt 0.148513 0.882435 
v  -9.373561 9.941600 -1.574307
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.067516 0.225300
vt 0.475085 0.395921 
v  -9.373561 9.941599 -1.160959
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.319109 0.225300
vt 0.552159 0.395921 
v  -9.770417 9.941599 -1.160959
vn  -0.000000 -1.000000 -0.000001
#  -1.003922 0.319109 0.038015
vt 0.552159 0.469920 
v  -9.770417 9.941600 -1.574307
vn  0.000000 -1.000000 -0.000001
#  -1.003922 0.067516 0.038015
vt 0.475085 0.469920 
v  -9.291738 9.662910 -1.084562
vn  -0.034184 0.057156 0.997780
#  -1.003922 0.000311 0.110747
vt 0.402330 0.892647 
v  -9.310534 9.947912 -1.101531
vn  -0.034184 0.057156 0.997780
#  -1.003922 0.000311 0.002743
vt 0.455472 0.896152 
v  -9.373473 9.910270 -1.101531
vn  -0.034184 0.057156 0.997780
#  -1.003922 0.034871 0.002743
vt 0.448453 0.907888 
v  -9.359233 9.662820 -1.084562
vn  -0.000092 0.068412 0.997657
#  -1.003922 0.034871 0.101447
vt 0.402313 0.905232 
v  -9.359233 9.662820 -1.084562
vn  -0.998353 -0.057352 0.001474
#  -1.003922 0.000311 0.099818
vt 0.798940 0.389813 
v  -9.373473 9.910270 -1.101531
vn  -0.998353 -0.057352 0.001474
#  -1.003922 0.000311 0.002743
vt 0.845080 0.392978 
v  -9.373561 9.910270 -1.160959
vn  -0.998353 -0.057352 0.001474
#  -1.003922 0.034871 0.002743
vt 0.845080 0.404059 
v  -9.359326 9.662820 -1.143420
vn  -0.998355 -0.057318 0.001585
#  -1.003922 0.034871 0.099818
vt 0.798940 0.400788 
v  -9.359326 9.662820 -1.143420
vn  0.001283 -0.070627 -0.997502
#  -1.003922 0.034871 0.099818
vt 0.827199 0.527105 
v  -9.373561 9.910270 -1.160959
vn  0.001283 -0.070627 -0.997502
#  -1.003922 0.034871 0.002743
vt 0.873339 0.524451 
v  -9.310534 9.910270 -1.160878
vn  0.001283 -0.070627 -0.997502
#  -1.003922 0.000311 0.002743
vt 0.873339 0.536203 
v  -9.291738 9.662820 -1.143340
vn  0.001186 -0.070608 -0.997503
#  -1.003922 0.000311 0.099818
vt 0.827199 0.539708 
v  -9.291738 9.662910 -1.084562
vn  0.997128 0.075736 -0.000117
#  -1.003922 0.000311 0.110694
vt 0.248850 0.998000 
v  -9.291738 9.662820 -1.143340
vn  0.997128 0.075736 -0.000117
#  -1.003922 0.034871 0.102344
vt 0.248833 0.987040 
v  -9.310534 9.910270 -1.160878
vn  0.997128 0.075736 -0.000117
#  -1.003922 0.034871 0.002743
vt 0.294973 0.983770 
v  -9.310534 9.947912 -1.101531
vn  0.997180 0.063374 -0.040197
#  -1.003922 0.000311 0.002743
vt 0.301992 0.994836 
v  -9.856748 9.662911 -1.650342
vn  0.031580 0.056109 -0.997925
#  -1.003922 0.000311 0.110700
vt 0.095371 0.555259 
v  -9.837403 9.947912 -1.633705
vn  0.031580 0.056109 -0.997925
#  -1.003922 0.000311 0.002743
vt 0.148513 0.558866 
v  -9.770539 9.910271 -1.633705
vn  0.031580 0.056109 -0.997925
#  -1.003922 0.034871 0.002743
vt 0.141494 0.571333 
v  -9.785043 9.662820 -1.650342
vn  0.000082 0.067075 -0.997748
#  -1.003922 0.034871 0.101399
vt 0.095354 0.568629 
v  -9.785043 9.662820 -1.650342
vn  0.998293 -0.058374 -0.002052
#  -1.003922 0.000311 0.099818
vt 0.798940 0.367658 
v  -9.770539 9.910271 -1.633705
vn  0.998293 -0.058374 -0.002052
#  -1.003922 0.000311 0.002743
vt 0.845080 0.370760 
v  -9.770417 9.910271 -1.574307
vn  0.998293 -0.058374 -0.002052
#  -1.003922 0.034871 0.002743
vt 0.845080 0.381835 
v  -9.784913 9.662820 -1.591617
vn  0.998295 -0.058327 -0.002205
#  -1.003922 0.034871 0.099818
vt 0.798940 0.378608 
v  -9.784913 9.662820 -1.591617
vn  -0.000323 -0.069764 0.997563
#  -1.003922 0.034871 0.099818
vt 0.827199 0.549377 
v  -9.770417 9.910271 -1.574307
vn  -0.000323 -0.069764 0.997563
#  -1.003922 0.034871 0.002743
vt 0.873339 0.546674 
v  -9.837403 9.910271 -1.574329
vn  -0.000323 -0.069764 0.997563
#  -1.003922 0.000311 0.002743
vt 0.873339 0.559165 
v  -9.856748 9.662820 -1.591639
vn  -0.000298 -0.069758 0.997564
#  -1.003922 0.000311 0.099818
vt 0.827199 0.562772 
v  -9.856748 9.662911 -1.650342
vn  -0.996959 0.077928 0.000121
#  -1.003922 0.000311 0.110695
vt 0.095371 0.885537 
v  -9.856748 9.662820 -1.591639
vn  -0.996959 0.077928 0.000121
#  -1.003922 0.034871 0.102345
vt 0.095354 0.874591 
v  -9.837403 9.910271 -1.574329
vn  -0.996959 0.077928 0.000121
#  -1.003922 0.034871 0.002743
vt 0.141494 0.871364 
v  -9.837403 9.947912 -1.633705
vn  -0.997011 0.065257 0.041370
#  -1.003922 0.000311 0.002743
vt 0.148513 0.882435 
v  -9.856748 9.662910 -1.084561
vn  -0.997014 0.065209 -0.041361
#  -1.003922 0.000311 0.110781
vt 0.095371 0.780041 
v  -9.837403 9.947912 -1.101531
vn  -0.997014 0.065209 -0.041361
#  -1.003922 0.000311 0.002743
vt 0.148513 0.783205 
v  -9.837403 9.910270 -1.160878
vn  -0.997014 0.065209 -0.041361
#  -1.003922 0.034871 0.002743
vt 0.141494 0.794271 
v  -9.856748 9.662820 -1.143339
vn  -0.996959 0.077928 -0.000121
#  -1.003922 0.034871 0.101492
vt 0.095354 0.791000 
v  -9.856748 9.662820 -1.143339
vn  -0.001207 -0.070605 -0.997504
#  -1.003922 0.000311 0.099818
vt 0.652479 0.411025 
v  -9.837403 9.910270 -1.160878
vn  -0.001207 -0.070605 -0.997504
#  -1.003922 0.000311 0.002743
vt 0.698619 0.414632 
v  -9.770417 9.910270 -1.160959
vn  -0.001207 -0.070605 -0.997504
#  -1.003922 0.034871 0.002743
vt 0.698619 0.427122 
v  -9.784913 9.662820 -1.143420
vn  -0.001126 -0.070633 -0.997502
#  -1.003922 0.034871 0.099818
vt 0.652479 0.424419 
v  -9.784913 9.662820 -1.143420
vn  0.998295 -0.058336 0.002051
#  -1.003922 0.034871 0.099818
vt 0.945400 0.416147 
v  -9.770417 9.910270 -1.160959
vn  0.998295 -0.058336 0.002051
#  -1.003922 0.034871 0.002743
vt 0.991540 0.412877 
v  -9.770539 9.910270 -1.101531
vn  0.998295 -0.058336 0.002051
#  -1.003922 0.000311 0.002743
vt 0.991540 0.423958 
v  -9.785043 9.662820 -1.084561
vn  0.998293 -0.058361 0.002200
#  -1.003922 0.000311 0.099818
vt 0.945400 0.427122 
v  -9.856748 9.662910 -1.084561
vn  0.000087 0.068413 0.997657
#  -1.003922 0.000311 0.110624
vt 0.402330 0.998000 
v  -9.785043 9.662820 -1.084561
vn  0.000087 0.068413 0.997657
#  -1.003922 0.034871 0.102280
vt 0.402313 0.984630 
v  -9.770539 9.910270 -1.101531
vn  0.000087 0.068413 0.997657
#  -1.003922 0.034871 0.002743
vt 0.448453 0.981925 
v  -9.837403 9.947912 -1.101531
vn  0.032220 0.057227 0.997841
#  -1.003922 0.000311 0.002743
vt 0.455472 0.994393 
v  -9.310534 9.910271 -1.574330
vn  0.997128 0.075736 0.000117
#  -1.003922 0.034871 0.002743
vt 0.294974 0.906677 
v  -9.291738 9.662820 -1.591639
vn  0.997128 0.075736 0.000117
#  -1.003922 0.034871 0.101493
vt 0.248834 0.903449 
v  -9.291738 9.662911 -1.650342
vn  0.997128 0.075736 0.000117
#  -1.003922 0.000311 0.110782
vt 0.248850 0.892503 
v  -9.310534 9.947912 -1.633705
vn  0.997177 0.063421 0.040207
#  -1.003922 0.000311 0.002743
vt 0.301992 0.895606 
v  -9.291738 9.662820 -1.591639
vn  0.000355 -0.069753 0.997564
#  -1.003922 0.000311 0.099818
vt 0.798940 0.411865 
v  -9.310534 9.910271 -1.574330
vn  0.000355 -0.069753 0.997564
#  -1.003922 0.000311 0.002743
vt 0.845080 0.415370 
v  -9.373561 9.910271 -1.574307
vn  0.000355 -0.069753 0.997564
#  -1.003922 0.034871 0.002743
vt 0.845080 0.427122 
v  -9.359326 9.662820 -1.591617
vn  0.000320 -0.069764 0.997563
#  -1.003922 0.034871 0.099818
vt 0.798940 0.424468 
v  -9.359326 9.662820 -1.591617
vn  -0.998354 -0.057327 -0.001475
#  -1.003922 0.034871 0.099818
vt 0.652479 0.349674 
v  -9.373561 9.910271 -1.574307
vn  -0.998354 -0.057327 -0.001475
#  -1.003922 0.034871 0.002743
vt 0.698619 0.346446 
v  -9.373473 9.910271 -1.633705
vn  -0.998354 -0.057327 -0.001475
#  -1.003922 0.000311 0.002743
vt 0.698619 0.357522 
v  -9.359233 9.662820 -1.650342
vn  -0.998353 -0.057346 -0.001589
#  -1.003922 0.000311 0.099818
vt 0.652479 0.360624 
v  -9.291738 9.662911 -1.650342
vn  -0.000087 0.067077 -0.997748
#  -1.003922 0.000311 0.110655
vt 0.095371 0.660612 
v  -9.359233 9.662820 -1.650342
vn  -0.000087 0.067077 -0.997748
#  -1.003922 0.034871 0.102318
vt 0.095354 0.648026 
v  -9.373473 9.910271 -1.633705
vn  -0.000087 0.067077 -0.997748
#  -1.003922 0.034871 0.002743
vt 0.141494 0.645371 
v  -9.310534 9.947912 -1.633705
vn  -0.033515 0.056039 -0.997866
#  -1.003922 0.000311 0.002743
vt 0.148513 0.657107 
v  -9.373561 9.910271 -1.447659
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.129196 0.290283
vt 0.944452 0.319135 
v  -9.373561 9.941600 -1.574307
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.038961 0.263081
vt 0.920837 0.324977 
v  -9.373561 9.910271 -1.574307
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.038968 0.294598
vt 0.920837 0.319135 
v  -9.770417 9.941599 -1.160959
vn  -0.000001 0.000002 -1.000000
#  -1.003922 0.346793 0.262909
vt 0.726889 0.503669 
v  -9.373561 9.941599 -1.160959
vn  -0.000001 0.000002 -1.000000
#  -1.003922 0.038974 0.263025
vt 0.652891 0.503669 
v  -9.493707 9.910270 -1.160959
vn  -0.000001 0.000002 -1.000000
#  -1.003922 0.129249 0.290226
vt 0.675293 0.497827 
v  -9.650273 9.910270 -1.160959
vn  0.000000 0.000008 -1.000000
#  -1.003922 0.256440 0.290190
vt 0.704487 0.497827 
v  -9.770417 9.910271 -1.574307
vn  1.000000 0.000000 0.000015
#  -1.003922 0.347119 0.294890
vt 0.997626 0.574848 
v  -9.770417 9.941600 -1.574307
vn  1.000000 0.000000 0.000015
#  -1.003922 0.346974 0.262983
vt 0.997626 0.580690 
v  -9.770419 9.910271 -1.447659
vn  1.000000 0.000000 0.000015
#  -1.003922 0.256557 0.289787
vt 0.974010 0.574848 
v  -9.373561 9.910271 -1.574307
vn  0.000000 0.000000 1.000000
#  -1.003922 0.347037 0.294842
vt 0.977747 0.176389 
v  -9.373561 9.941600 -1.574307
vn  0.000000 0.000000 1.000000
#  -1.003922 0.347127 0.262754
vt 0.977747 0.182231 
v  -9.493707 9.910271 -1.574307
vn  0.000000 0.000000 1.000000
#  -1.003922 0.256636 0.290198
vt 0.955344 0.176389 
v  -9.770419 9.910271 -1.447659
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.261085 0.299079
vt 0.155480 0.958846 
v  -9.837403 9.910271 -1.447624
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.261067 0.267961
vt 0.167970 0.958839 
v  -9.837403 9.910271 -1.574329
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.347991 0.267962
vt 0.167970 0.982465 
v  -9.770417 9.910271 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.347987 0.299079
vt 0.155479 0.982461 
v  -9.373561 9.910271 -1.283554
vn  0.000000 -1.000000 -0.000001
#  -1.003922 0.260901 0.299193
vt 0.013752 0.928246 
v  -9.310534 9.910271 -1.283520
vn  0.000000 -1.000000 -0.000001
#  -1.003922 0.260919 0.268076
vt 0.002000 0.928240 
v  -9.310534 9.910270 -1.160878
vn  0.000000 -1.000000 -0.000001
#  -1.003922 0.347600 0.268082
vt 0.002000 0.905372 
v  -9.373561 9.910270 -1.160959
vn  0.000000 -1.000000 -0.000001
#  -1.003922 0.347589 0.299193
vt 0.013752 0.905387 
v  -9.770419 9.901122 -1.430594
vn  -0.000000 -1.000000 -0.000002
#  -1.003922 0.251980 0.299078
vt 0.155480 0.955664 
v  -9.770419 9.901122 -1.300614
vn  -0.000000 -1.000000 -0.000002
#  -1.003922 0.136194 0.299078
vt 0.155480 0.931428 
v  -9.837403 9.901122 -1.300584
vn  -0.000000 -1.000000 -0.000002
#  -1.003922 0.136179 0.267961
vt 0.167970 0.931422 
v  -9.837403 9.901122 -1.430564
vn  -0.000000 -1.000000 -0.000002
#  -1.003922 0.251965 0.267961
vt 0.167970 0.955658 
v  -9.373561 9.901122 -1.300614
vn  0.000000 -1.000000 -0.000002
#  -1.003922 0.251794 0.299193
vt 0.013752 0.931427 
v  -9.373561 9.901122 -1.430594
vn  0.000000 -1.000000 -0.000002
#  -1.003922 0.136009 0.299193
vt 0.013752 0.955664 
v  -9.310534 9.901122 -1.430564
vn  0.000000 -1.000000 -0.000002
#  -1.003922 0.136024 0.268075
vt 0.002000 0.955658 
v  -9.310534 9.901122 -1.300585
vn  0.000000 -1.000000 -0.000002
#  -1.003922 0.251809 0.268075
vt 0.002000 0.931422 
v  -9.837403 9.901122 -1.300584
vn  0.000211 -0.881293 0.472570
#  -1.003922 0.136179 0.267961
vt 0.167970 0.931422 
v  -9.770419 9.901122 -1.300614
vn  0.000211 -0.881293 0.472570
#  -1.003922 0.136194 0.299078
vt 0.155480 0.931428 
v  -9.770419 9.910271 -1.283554
vn  0.000211 -0.881293 0.472570
#  -1.003922 0.127088 0.299079
vt 0.155480 0.928247 
v  -9.837403 9.910271 -1.283520
vn  0.000243 -0.881345 0.472473
#  -1.003922 0.127071 0.267961
vt 0.167970 0.928240 
v  -9.837403 9.901122 -1.430564
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.100602 0.033475
vt 0.139788 0.844557 
v  -9.837403 9.901122 -1.300584
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.266286 0.032778
vt 0.139788 0.820321 
v  -9.837403 9.910271 -1.283520
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.278018 0.024774
vt 0.141494 0.817139 
v  -9.837403 9.910271 -1.447624
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.086945 0.024177
vt 0.141494 0.847738 
v  -9.770419 9.901122 -1.430594
vn  -0.000212 -0.881301 -0.472555
#  -1.003922 0.251980 0.299078
vt 0.155480 0.955664 
v  -9.837403 9.901122 -1.430564
vn  -0.000212 -0.881301 -0.472555
#  -1.003922 0.251965 0.267961
vt 0.167970 0.955658 
v  -9.837403 9.910271 -1.447624
vn  -0.000212 -0.881301 -0.472555
#  -1.003922 0.261067 0.267961
vt 0.167970 0.958839 
v  -9.770419 9.910271 -1.447659
vn  -0.000242 -0.881351 -0.472463
#  -1.003922 0.261085 0.299079
vt 0.155480 0.958846 
v  -9.770419 9.901122 -1.300614
vn  1.000000 -0.000002 -0.000001
#  -1.003922 0.116346 0.295005
vt 0.946592 0.573142 
v  -9.770419 9.901122 -1.430594
vn  1.000000 -0.000002 -0.000001
#  -1.003922 0.269312 0.294594
vt 0.970828 0.573142 
v  -9.770419 9.910271 -1.447659
vn  1.000000 -0.000002 -0.000001
#  -1.003922 0.283067 0.286555
vt 0.974010 0.574848 
v  -9.770419 9.910271 -1.283554
vn  1.000000 0.000001 -0.000001
#  -1.003922 0.100930 0.286053
vt 0.943411 0.574848 
v  -9.310534 9.901122 -1.430564
vn  0.000222 -0.881348 -0.472468
#  -1.003922 0.136024 0.268075
vt 0.002000 0.955658 
v  -9.373561 9.901122 -1.430594
vn  0.000222 -0.881348 -0.472468
#  -1.003922 0.136009 0.299193
vt 0.013752 0.955664 
v  -9.373561 9.910271 -1.447659
vn  0.000222 -0.881348 -0.472468
#  -1.003922 0.126903 0.299193
vt 0.013752 0.958846 
v  -9.310534 9.910271 -1.447625
vn  0.000254 -0.881298 -0.472560
#  -1.003922 0.126920 0.268075
vt 0.002000 0.958839 
v  -9.310534 9.901122 -1.300585
vn  1.000000 -0.000002 -0.000001
#  -1.003922 0.101174 0.033475
vt 0.293268 0.957720 
v  -9.310534 9.901122 -1.430564
vn  1.000000 -0.000002 -0.000001
#  -1.003922 0.266687 0.032889
vt 0.293268 0.933484 
v  -9.310534 9.910271 -1.447625
vn  1.000000 -0.000002 -0.000001
#  -1.003922 0.278536 0.024774
vt 0.294974 0.930303 
v  -9.310534 9.910271 -1.283520
vn  1.000000 0.000001 -0.000001
#  -1.003922 0.087328 0.024089
vt 0.294973 0.960902 
v  -9.373561 9.901122 -1.300614
vn  -0.000222 -0.881345 0.472473
#  -1.003922 0.251794 0.299193
vt 0.013752 0.931427 
v  -9.310534 9.901122 -1.300585
vn  -0.000222 -0.881345 0.472473
#  -1.003922 0.251809 0.268075
vt 0.002000 0.931422 
v  -9.310534 9.910271 -1.283520
vn  -0.000222 -0.881345 0.472473
#  -1.003922 0.260919 0.268076
vt 0.002000 0.928240 
v  -9.373561 9.910271 -1.283554
vn  -0.000254 -0.881296 0.472565
#  -1.003922 0.260901 0.299193
vt 0.013752 0.928246 
v  -9.373561 9.901122 -1.430594
vn  -1.000000 -0.000002 0.000001
#  -1.003922 0.115799 0.295005
vt 0.947634 0.317429 
v  -9.373561 9.901122 -1.300614
vn  -1.000000 -0.000002 0.000001
#  -1.003922 0.268903 0.294517
vt 0.971871 0.317429 
v  -9.373561 9.910271 -1.283554
vn  -1.000000 -0.000002 0.000001
#  -1.003922 0.282551 0.286555
vt 0.975052 0.319135 
v  -9.373561 9.910271 -1.447659
vn  -1.000000 0.000001 0.000001
#  -1.003922 0.100529 0.286117
vt 0.944452 0.319135 
v  -9.373561 9.910270 -1.160959
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.346699 0.294890
vt 0.997911 0.319135 
v  -9.373561 9.941599 -1.160959
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.346691 0.262814
vt 0.997911 0.324977 
v  -9.373561 9.910271 -1.283554
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.256283 0.290249
vt 0.975052 0.319135 
v  -9.373561 9.941599 -1.160959
vn  -1.000000 0.000001 0.000000
#  -1.003922 0.346646 0.263123
vt 0.997911 0.324977 
v  -9.837403 9.910270 -1.160878
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.319796 0.034640
vt 0.141494 0.794271 
v  -9.837403 9.947912 -1.101531
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.348047 0.000345
vt 0.148513 0.783205 
v  -9.837403 9.910271 -1.283520
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.248211 0.030166
vt 0.141494 0.817139 
v  -9.837403 9.947912 -1.101531
vn  -1.000000 0.000000 0.000000
#  -1.003922 0.347935 0.000708
vt 0.148513 0.783205 
v  -9.770417 9.941599 -1.160959
vn  1.000000 -0.000062 -0.000000
#  -1.003922 0.039321 0.263082
vt 0.920552 0.580690 
v  -9.770419 9.910271 -1.283554
vn  1.000000 -0.000058 -0.000001
#  -1.003922 0.129580 0.290272
vt 0.943411 0.574848 
v  -9.770417 9.910270 -1.160959
vn  1.000000 -0.000000 -0.000016
#  -1.003922 0.039386 0.294578
vt 0.920552 0.574848 
v  -9.310534 9.910270 -1.160878
vn  1.000000 0.000000 0.000000
#  -1.003922 0.067357 0.034069
vt 0.294973 0.983770 
v  -9.310534 9.947912 -1.101531
vn  1.000000 0.000000 0.000000
#  -1.003922 0.041105 0.001153
vt 0.301992 0.994836 
v  -9.310534 9.910271 -1.574330
vn  1.000000 0.000000 0.000000
#  -1.003922 0.320071 0.034710
vt 0.294974 0.906677 
v  -9.310534 9.947912 -1.633705
vn  1.000000 0.000000 0.000000
#  -1.003922 0.351383 0.000548
vt 0.301992 0.895606 
v  -9.650273 9.910270 -1.160959
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.166846 0.299763
vt 0.675316 0.508893 
v  -9.650290 9.910270 -1.101531
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.166836 0.268645
vt 0.675312 0.519974 
v  -9.770539 9.910270 -1.101531
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.108535 0.268645
vt 0.652891 0.519974 
v  -9.770417 9.910270 -1.160959
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.108595 0.299763
vt 0.652913 0.508893 
v  -9.493707 9.910271 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.166735 0.299609
vt 0.875791 0.687479 
v  -9.493724 9.910271 -1.633705
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.166743 0.268491
vt 0.875788 0.676404 
v  -9.373473 9.910271 -1.633705
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.108830 0.268491
vt 0.898210 0.676404 
v  -9.373561 9.910271 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.108872 0.299609
vt 0.898194 0.687479 
v  -9.635522 9.901602 -1.160959
vn  0.000000 -1.000000 0.000002
#  -1.003922 0.174090 0.299763
vt 0.678066 0.508893 
v  -9.508458 9.901602 -1.160959
vn  0.000000 -1.000000 0.000002
#  -1.003922 0.236498 0.299763
vt 0.701759 0.508893 
v  -9.508475 9.901602 -1.101531
vn  0.000000 -1.000000 0.000002
#  -1.003922 0.236491 0.268645
vt 0.701756 0.519974 
v  -9.635535 9.901602 -1.101531
vn  0.000000 -1.000000 0.000002
#  -1.003922 0.174083 0.268645
vt 0.678064 0.519974 
v  -9.508458 9.901603 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.173930 0.299609
vt 0.873041 0.687479 
v  -9.635522 9.901603 -1.574307
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.235898 0.299609
vt 0.849348 0.687479 
v  -9.635537 9.901603 -1.633705
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.235905 0.268491
vt 0.849345 0.676404 
v  -9.508475 9.901603 -1.633705
vn  0.000000 -1.000000 0.000000
#  -1.003922 0.173937 0.268491
vt 0.873037 0.676404 
v  -9.508475 9.901602 -1.101531
vn  0.506613 -0.862173 0.000148
#  -1.003922 0.236491 0.268645
vt 0.701756 0.519974 
v  -9.508458 9.901602 -1.160959
vn  0.506613 -0.862173 0.000148
#  -1.003922 0.236498 0.299763
vt 0.701759 0.508893 
v  -9.493707 9.910270 -1.160959
vn  0.506613 -0.862173 0.000148
#  -1.003922 0.243744 0.299763
vt 0.704509 0.508893 
v  -9.493724 9.910270 -1.101531
vn  0.506608 -0.862176 0.000146
#  -1.003922 0.243736 0.268645
vt 0.704506 0.519974 
#   20c71:
```


(btw yes, it should be f 139/139/139 140/140/140 141/141/141 for the normals but this shouldn't do any harm.)

These are the submesh params of wuguancs,gm2:
vertsCnt= 29485
SM  start faces
 0 0xbeb (624 face ind)
 1 0x10cb (456 face ind)
 2 0x145b (378 face ind)
 3 0x174f (1824 face ind)
 4 0x258f (3600 face ind)
 5 0x41af (1290 face ind)
 6 0x4bc3 (2160 face ind)
 7 0x5ca3 (1200 face ind)
 8 0x6603 (6087 face ind)
 9 0x9591 (27720 face ind)
 10 0x16e21 (1152 face ind)
 11 0x17721 (8742 face ind)
0x1bb6d: end faces

sectSize 395252, vertSize 44 (forced)
SM  start vertsBlock
 0 0x1bb75 (279 verts)
 1 0x1eb69 (192 verts)
 2 0x20c69 (224 verts)
 3 0x232e9 (1181 verts)
 4 0x2fde5 (1803 verts)
 5 0x433c9 (723 verts)
 6 0x4b00d (828 verts)
 7 0x53e5d (800 verts)
 8 0x5c7dd (3711 verts)
 9 0x845b1 (14696 verts)
 10 0x122391 (361 verts)
 11 0x12619d (4687 verts)
0x158731: end

One problem: sectSize / vertsCnt = 13, not 44

edit: well, there's something special with wuguancs. At vertex no 8983 the vertex block size changes from 44 to 52. (Somewhat strange that this happens in the midst of submesh 8 but: okaay.) 

So here we go: sectSize 1 = 8983 * 44 = 395252 = 0x607F4
sectSize 2 = (29485 - 8983) * 52 = 1066104 = 0x104478

Start of vertices: 0x1BB7D (+ 0x607F4 + 0x104478 -1 = 0x1807E8) -> end of file

face indices for submesh 11 from 0x17721 to 1BB6D (=> size = 8742*2 = 0x444C)

I don't see any error here but the submesh still looking weird. Although the structures can be recognized. Looks like only an offset is missing.

But an offset would upset my previous calculations. So I don't have a clue what's going wrong here.

[](http://www.pic-upload.de/view-20368539/wuguancs_SM11.jpg.html)


The script is working for other gm2 than wuguancs if you comment the "+8 offset line".
It's only required for wuguancs.
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-08-17T00:44:55+00:00
- Post Title: Re: Age of Wulin models

The gm2 format there are many unknowns I didn't figure out. Probably one of them determines when to offset or not.
## Post #23
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-08-18T12:41:21+00:00
- Post Title: Re: Age of Wulin models

i cannot figure out how animation key made of ...
here it is what i researched until now.

```
// 010 Editor v3.1 Binary Template
//
// File     : AgeOfWulinTemplateXSKT.bt
// Author   : MrMoonKr
// Revision : 0.1
// Purpose  : Age of Wulin online xskt file analyze
// Changes  :  
//
// ( 2013/08/18/Sun )
//          : struggle with animation key type
// ( 2013/08/12/Mon )
//          : start
//
//////////////////////////////////////////////////////////////////////////


//------------------------------------------------------------------------

#include "CommonTemplate.bt"


//------------------------------------------------------------------------

typedef struct tagXSKTTransform
{
    CCVector3           mTrans ;
    CCVector4           mRot ;
    CCVector3           mScale ;

} XSKTTransform ;

//------------------------------------------------------------------------

typedef struct
{
    float               mTime ;
    uint16              mPadding ;
    CCVector3           mKey ;

} XSKTKey1 ;

typedef struct
{
    uint16              x , y, z ;

} XSKTKey2 ;

//------------------------------------------------------------------------

typedef struct ( uint32 keyCount )
{
    CCString            mName ;
    uint32              mAnimType ;         ///< 3, 4
    uint32              mKeyType ;          ///< 0, 2

    switch ( mAnimType )
    {
    case 4 : // dynamic
        {
            uint32          mOne ;
            
            XSKTTransform   mTM ;
    
            if ( mKeyType == 0 ) 
            {
                XSKTKey2    mKeyArray[ mKeyCount ]  ;
            }
            else if ( mKeyType == 2 )
            {
                XSKTKey1    mKeyArray[ keyCount ] ;
            }
            else
            {
                Assert( "Unknown key type found \n" ) ;
            }
        }
        break;
    case 3 : // static
        {
            XSKTTransform   mTM ;
        }
        break;
    }
    
    uint32              mChildren ;

} XSKTBone < read = ReadXSKTBone > ;

string ReadXSKTBone( XSKTBone& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( Type : %d , %d )( Name : %s )( Children : %d )" ,
        data.mAnimType ,
        data.mKeyType ,
        data.mName.mString ,
        data.mChildren
        ) ;
    return s ;
}

//------------------------------------------------------------------------

/**
    Archive Header
*/
typedef struct tagXSKTHeader
{
    char                mFourCC[4] ;
    uint32              m05100000 ;         ///< 05 10 00 00
    uint32              m06000000 ;         ///< 6
    CCString            mFileName ;
    uint32              mZero ;
    uint32              mKeyCount ;
    float               mFPS ;              ///< 30
    CCVector3           mMin ;
    CCVector3           mMax ;
    uint32              mOne ;
  
    while ( !FEof() )
    {
        XSKTBone        mBoneArray( mKeyCount ) ;
    }

} XSKTHeader < bgcolor = cLtGray , read = ReadXSKTHeader > ;

string ReadXSKTHeader( XSKTHeader& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( Type : %s )" ,
        data.mFourCC 
        ) ;
    return s ;
}


//////////////////////////////////////////////////////////////////////////

LittleEndian() ;
//BigEndian() ;

XSKTHeader              gHeader ;



```
## Post #24
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-12-01T19:50:03+00:00
- Post Title: Re: Age of Wulin models

i looking for extract sound someone know how extract package plz
## Post #25
- Username: shadowof047
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 09, 2012 5:17 pm
- Post datetime: 2014-04-22T15:16:22+00:00
- Post Title: Re: Age of Wulin models

Where should i put the Sanae.py  file ? i try putting it in "noesis\plugins\python"  , but it still gives me this error :

from Sanae3D.Sanae import SanaeObject
ImportError: No Module named Sanae

Thanks.
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-22T16:04:43+00:00
- Post Title: Re: Age of Wulin models

> Reply from shadowof047
>
> Where should i put the Sanae.py  file ? i try putting it in "noesis\plugins\python"  , but it still gives me this error :

from Sanae3D.Sanae import SanaeObject
ImportError: No Module named Sanae

Thanks.I've a Sanae3D subfolder (in the folder ..\plugins\python)
where the Sanae.py and StructReader.py reside.

If that doesn't work you might try out the modified fmt_AgeOfWulin_gm2.py
(view post of Fri Aug 09, 2013 12:40 pm)
Iirc it works without Sanae.py.
## Post #27
- Username: shadowof047
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 09, 2012 5:17 pm
- Post datetime: 2014-04-22T17:47:11+00:00
- Post Title: Re: Age of Wulin models

> Reply from shakotay2
>
> I've a Sanae3D subfolder (in the folder ..\plugins\python)
where the Sanae.py and StructReader.py reside.

If that doesn't work you might try out the modified fmt_AgeOfWulin_gm2.py
(view post of Fri Aug 09, 2013 12:40 pm)
Iirc it works without Sanae.py.

Thank you for the fast reply,i really appreciate it. 
i put the " Sanae.py " into \plugins\python\Sanae3D "  folder as you instructed, and the previous error is gone . but now it gives a whole new errors as shown in this screenshot. you can also see inside of the Sanae3D folder. Is there a way to fix this ?



Also i tried the modified Script.It doesnt give me any errors when starting Noesis , but when previewing most of the meshes it gives different errors, and on the meshes it doesnt give errors, it shows nothing most of the time. sorry i'm a noob in programming and the only language i'm a lil bit familiar with, is c++ .

Thanks again
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-22T18:55:58+00:00
- Post Title: Re: Age of Wulin models

> Reply from shadowof047
>
> Is there a way to fix this ?It's finale00's script. Maybe he can help you.

(Guess due to this problem I modified the script to work without sanae.py.)


> Also i tried the modified Script.It doesnt give me any errors when starting Noesis , but when previewing most of the meshes it gives different errors, and on the meshes it doesnt give errors, it shows nothing most of the time.
If you comment out the 2nd line in the following code snippet from the modified script with an '#'
it should work for more models.

```
        #val = self.inFile.read('2L')     # just skip 8 bytes  for wuguancs.gm2 only!
        self.parse_vertices(vertSize)

```


For  huotan09 and 13 another line in the code has to be commented out.

(Keep in mind that my patch aimed to get wuguancs.gm2 loaded.
 finale00's original script was working fine with most of the other models.)
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-04-22T19:49:22+00:00
- Post Title: Re: Age of Wulin models

It looks like you have an old version of the library. Especially that engine.py thing I don't even remember what that is. And it looks like it's using python2 syntax, so presumably that is the one that I was using when I first started with metaseq conversion.

The latest version just has a single sanae.py file inside the Sanae3D folder and is written to use Noesis API.
## Post #30
- Username: shadowof047
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 09, 2012 5:17 pm
- Post datetime: 2014-04-22T21:39:10+00:00
- Post Title: Re: Age of Wulin models

Thanks again Shak-otay   

But the original script doesnt run for me at all .

After the edits and posting at the  [http://www.himeworks.com/noesis-plugins/](http://www.himeworks.com/noesis-plugins/)      xTsukiHime told me to add some parentheses , i added  those to 5-6 lines through the script , now the error changed :



I think i miss some kind of standard libraries for python ? this is where is the thread i downloaded Sane3D from :

[viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)    and i'm editing the script with word.

If i am indeed missing standard libraries , installing python will do the trick ?

Thanks in advance 

*************************************************************************
Edit : i saw finale00 post right after i posted this ,  where can i get the latest sanae.py please ? thanks.
I've got the "sanae" from your Thread.  [viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-04-22T23:10:15+00:00
- Post Title: Re: Age of Wulin models

It's in my dropbox. That topic is something completely different.
## Post #32
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-06-17T22:13:39+00:00
- Post Title: Re: Age of Wulin models

Please help,  i need tool or Script to unpack Age of Wulin client to open in noesis!
## Post #33
- Username: thaicuong2909
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 17, 2021 9:20 pm
- Post datetime: 2021-05-23T10:13:55+00:00
- Post Title: Re: Age of Wulin models

Oh, i followed this thread, i using Noesis 4442 and plugin AgeOfWulin.xmod and sanae.
But it err when open and can not view xmod file or xskt file.
Some one can help edit plugin or some script can import to 3ds max, please
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-23T11:19:08+00:00
- Post Title: Re: Age of Wulin models

I wouldn't bet on it that someone will care for the plugin or write a script.

But you might have a look here:
.

> Reply from shakotay2 ↑Sun May 23, 2021 7:15 pm at Sun May 23, 2021 7:15 pm
>
>
