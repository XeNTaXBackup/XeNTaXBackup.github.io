## Post #1
- Username: photojoe
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 27, 2016 6:49 am
- Post datetime: 2021-05-15T17:31:21+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

I keep getting a failed to construct RPGEO Context in line 35, it's a call to noepyloadmodel. I attached the meshes that it won't view/convert.



```
import noesis
import rapi
import os

def registerNoesisTypes():
    '''Register the plugin'''
    
    handle = noesis.register("Zu Online", ".ltb")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin.'''
    
    if len(data) < 9:
        return 0
    try:
        bs = NoeBitStream(data)
        ver1 = bs.readShort()
        ver2 = bs.readShort()
        if ver1 != 1 or ver2 != 9:
            return 0
        return 1
    except:
        return 0

def noepyLoadModel(data, mdlList):
    '''Load the model'''
    
    ctx = rapi.rpgCreateContext()
    parser = ZuOnline_LTB(data)
    parser.parse_file()
    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)
    mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
    mdlList.append(mdl)
    return 1

class ZuOnline_LTB(object):
    
    def __init__(self, data):    
        self.inFile = NoeBitStream(data)
        self.animList = []
        self.texList = []
        self.matList = []
        self.boneList = []
        self.dirpath = rapi.getDirForFilePath(rapi.getInputName())
        self.texpath = self.dirpath + "texture\\"
        
    def basename(self):
        '''Returns the filename without extension'''
        
        filename = rapi.getLocalFileName(rapi.getInputName())
        basename, ext = os.path.splitext(filename)
        return basename    
        
    def read_name(self):
        
        string = self.inFile.readBytes(self.inFile.readUShort())
        try:
            return noeStrFromBytes(string)
        except:
            return string
            
    def parse_vertices(self, numVerts, meshType):
        
        print (self.inFile.tell())
        if meshType == 1:
            vertBuff = self.inFile.readBytes(numVerts * 32)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 24)
        elif meshType == 2:
            vertBuff = self.inFile.readBytes(numVerts * 36)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 16)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 28)
        elif meshType == 3:
            vertBuff = self.inFile.readBytes(numVerts * 40)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 20)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 32)
        elif meshType == 4:
            vertBuff = self.inFile.readBytes(numVerts * 44)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 24)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 36)
        else:
            print("unknown meshType: %d" %meshType)        

    def parse_faces(self, numIdx):
        
        return self.inFile.readBytes(numIdx * 2)
    
    def parse_unk(self):
        
        count = self.inFile.readUInt()
        self.inFile.seek(count*12, 1)
        
    def create_material(self, matNum):
        
        matName = "material[%d]" %matNum
        if matNum == 1:
            texName = self.texpath + self.basename() + ".dtx"
        elif matNum == 2:
            texName = self.texpath + self.basename() + "_a.dtx" 
        elif matNum == 3:
            texName = self.texpath + self.basename() + "_b.dtx"
        elif matNum == 4:
            texName = self.texpath + self.basename() + "_c.dtx"
        elif matNum == 5:
            texName = self.texpath + self.basename() + "_a.dtx"
        elif matNum == 6:
            texName = self.texpath + self.basename() + "_a.dtx"
        else:
            print(matNum)
            texName = ""
        
        material = NoeMaterial(matName, texName)
        self.matList.append(material)
        return matName
    
    def parse_submesh(self, numSubmesh):
        
        print (self.inFile.tell())
        for i in range(numSubmesh):
            self.inFile.readUInt()
            matNum = self.inFile.readUInt()
            self.inFile.read('4L')
            self.inFile.readByte()
            unk1 = self.inFile.readUInt()
            sectionSize = self.inFile.readUInt()
            
            #sectionSize could be 0
            if sectionSize:
                start = self.inFile.tell()
                numVerts = self.inFile.readUInt()
                numIdx = self.inFile.readUInt() * 3
                meshType = self.inFile.readUInt()
                self.inFile.read('5L')
       
                if unk1 == 4:
                    self.inFile.readUInt()
                elif unk1 == 5:
                    self.inFile.readUShort()
                
                self.parse_vertices(numVerts, meshType)
                idxBuff = self.parse_faces(numIdx)
                
                #just seeking past unknowns rather than parse the unknown
                curr = self.inFile.tell() - start
                remain = sectionSize - curr
                self.inFile.seek(remain, 1)
    
                unk2 = self.inFile.readByte()
                self.inFile.seek(unk2, 1)
                
                
                matName = self.create_material(matNum)
                #rapi.rpgSetMaterial(matName)
                #rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
    
    def parse_mesh(self, numMesh):
        
        for i in range(numMesh):
            meshName = self.read_name()
            numSubmesh = self.inFile.readUInt()
            for j in range(numSubmesh):
                self.inFile.readFloat()
            self.inFile.read('2L')
            self.parse_submesh(numSubmesh)
            
    def parse_file(self):
        
        self.inFile.read('2H')
        self.inFile.read('4L')
        version = self.inFile.readUInt()
        self.inFile.read('2L')
        numBones = self.inFile.readUInt()
        self.inFile.read('10L')
        self.inFile.read('2H') #large number
        self.inFile.readUInt()
        self.read_name()
        self.inFile.readFloat()
        self.inFile.readUInt()
        numMesh = self.inFile.readUInt()
        self.parse_mesh(numMesh)

```

[MODELS.zip](https://xentaxbackup.github.io/file/20135_MODELS.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-15T20:15:19+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

Why do you think this script could load Tron 2.0 .ltb files? (Try search "Lithtech" ltb, maybe you'll get some valid info.)
For both ltbs you provided the numMesh count is 0 with this script.

Use script from here:

> Reply from mariokart64n ↑Mon Jun 22, 2020 2:09 am at Mon Jun 22, 2020 2:09 am
>
> 
Will load the seeker at least.

(For Kernel_Death.ltb we get an error, as the name tells.  )
## Post #3
- Username: photojoe
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 27, 2016 6:49 am
- Post datetime: 2021-05-15T20:35:08+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

Because it works on all but those post meshes, the LTB files are Lilthtech Game engine mesh files.
However I do not understand why it glitches out on some but not all.

Tried this script and did the same thing, threw the error on the files in that zip I posted, but everything else works.

```
import noesis
import rapi
import os

def registerNoesisTypes():
    '''Register the plugin'''

    handle = noesis.register("Zu Online", ".ltb")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin.'''
    
    if len(data) < 9:
        return 0
    try:
        bs = NoeBitStream(data)
        ver1 = bs.readShort()
        ver2 = bs.readShort()
        if ver1 != 1 or ver2 != 9:
            return 0
        return 1
    except:
        return 0

def noepyLoadModel(data, mdlList):
    '''Load the model'''
    
    ctx = rapi.rpgCreateContext()
    parser = ZuOnline_LTB(data)
    parser.parse_file()
    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)
    mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
    mdlList.append(mdl)
    return 1

class ZuOnline_LTB(object):
    
    def __init__(self, data):    
        self.inFile = NoeBitStream(data)
        self.animList = []
        self.texList = []
        self.matList = []
        self.boneList = []
        self.dirpath = rapi.getDirForFilePath(rapi.getInputName())
        self.texpath = self.dirpath + "texture\\"
        
    def basename(self):
        '''Returns the filename without extension'''
        
        filename = rapi.getLocalFileName(rapi.getInputName())
        basename, ext = os.path.splitext(filename)
        return basename    
        
    def read_name(self):
        
        string = self.inFile.readBytes(self.inFile.readUShort())
        try:
            return noeStrFromBytes(string)
        except:
            return string
            
    def parse_vertices(self, numVerts, meshType):
        
        print (self.inFile.tell())
        if meshType == 1:
            vertBuff = self.inFile.readBytes(numVerts * 32)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 24)
        elif meshType == 2:
            vertBuff = self.inFile.readBytes(numVerts * 36)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 16)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 36, 28)
        elif meshType == 3:
            vertBuff = self.inFile.readBytes(numVerts * 40)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 20)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 40, 32)
        elif meshType == 4:
            vertBuff = self.inFile.readBytes(numVerts * 44)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 24)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 36)
        else:
            print("unknown meshType: %d" %meshType)        

    def parse_faces(self, numIdx):
        
        return self.inFile.readBytes(numIdx * 2)
    
    def parse_unk(self):
        
        count = self.inFile.readUInt()
        self.inFile.seek(count*12, 1)
        
    def create_material(self, matNum):
        
        matName = "material[%d]" %matNum
        if matNum == 1:
            texName = self.texpath + self.basename() + ".dtx"
        elif matNum == 2:
            texName = self.texpath + self.basename() + "_a.dtx" 
        elif matNum == 3:
            texName = self.texpath + self.basename() + "_b.dtx"
        elif matNum == 4:
            texName = self.texpath + self.basename() + "_c.dtx"
        elif matNum == 5:
            texName = self.texpath + self.basename() + "_a.dtx"
        elif matNum == 6:
            texName = self.texpath + self.basename() + "_a.dtx"
        else:
            print(matNum)
            texName = ""
        
        material = NoeMaterial(matName, texName)
        self.matList.append(material)
        return matName
    
    def parse_submesh(self, numSubmesh):
        
        print (self.inFile.tell())
        for i in range(numSubmesh):
            self.inFile.readUInt()
            matNum = self.inFile.readUInt()
            self.inFile.read('4L')
            self.inFile.readByte()
            unk1 = self.inFile.readUInt()
            sectionSize = self.inFile.readUInt()
            
            #sectionSize could be 0
            if sectionSize:
                start = self.inFile.tell()
                numVerts = self.inFile.readUInt()
                numIdx = self.inFile.readUInt() * 3
                meshType = self.inFile.readUInt()
                self.inFile.read('5L')
       
                if unk1 == 4:
                    self.inFile.readUInt()
                elif unk1 == 5:
                    self.inFile.readUShort()
                
                self.parse_vertices(numVerts, meshType)
                idxBuff = self.parse_faces(numIdx)
                
                #just seeking past unknowns rather than parse the unknown
                curr = self.inFile.tell() - start
                remain = sectionSize - curr
                self.inFile.seek(remain, 1)
    
                unk2 = self.inFile.readByte()
                self.inFile.seek(unk2, 1)
                
                
                matName = self.create_material(matNum)
                #rapi.rpgSetMaterial(matName)
                #rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
    
    def parse_mesh(self, numMesh):
        
        for i in range(numMesh):
            meshName = self.read_name()
            numSubmesh = self.inFile.readUInt()
            for j in range(numSubmesh):
                self.inFile.readFloat()
            self.inFile.read('2L')
            self.parse_submesh(numSubmesh)
            
    def parse_file(self):
        
        self.inFile.read('2H')
        self.inFile.read('4L')
        version = self.inFile.readUInt()
        self.inFile.read('2L')
        numBones = self.inFile.readUInt()
        self.inFile.read('10L')
        self.inFile.read('2H') #large number
        self.inFile.readUInt()
        self.read_name()
        self.inFile.readFloat()
        self.inFile.readUInt()
        numMesh = self.inFile.readUInt()
        self.parse_mesh(numMesh)
```
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-15T20:51:07+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

why do you post the same script again?
## Post #5
- Username: photojoe
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 27, 2016 6:49 am
- Post datetime: 2021-05-15T21:17:14+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

One was dedicated to Lilithtech, this one was Zu-Online script for ltb files, their identical but I thought maybe I missed something that you could point out.

There is no difference i can see between the two, and you ask if the ZuOnline could handle it. When you said the Seeker would load for you, I was surprised as that file didn't work on my side
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-15T21:29:11+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

> Reply from photojoe ↑Sun May 16, 2021 5:17 am at Sun May 16, 2021 5:17 am
>
> When you said the Seeker would load for you, I was surprised as that file didn't work on my sideThe Seeker is loaded by the script from mariokart64n whose post I linked to. 
In this post, click on the up-arrow.

> Reply from shakotay2 ↑Sun May 16, 2021 4:15 am at Sun May 16, 2021 4:15 am
>
> 
.



Seeker.png (60.34 KiB) Viewed 59 times
## Post #7
- Username: photojoe
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 27, 2016 6:49 am
- Post datetime: 2021-05-16T13:28:02+00:00
- Post Title: Tron 2.0 Noesis Conversion not working

Got it, didn't see the link originally must of blew past it. Thanks.

I have the seeker, but the Mesh files still throw an error.
