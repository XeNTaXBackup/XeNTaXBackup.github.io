## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-19T22:12:30+00:00
- Post Title: scarlet legacy fail import with noesis

I was surfing on the net and i founded this game [Scarlet Legacy](http://scarletlegacy.gamescampus.com/)

i try to search on xentax about this game and Ta-Dan i've found the plugin for noesis ( thanks to finale 00) [https://www.dropbox.com/sh/7stlpd4qvkq3 ... acy_bsm.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/ES4kHbgLop/fmt_scarletLegacy_bsm.py)

Ok, i download it, i put it into plugins's folder and i run Noesis.

But an error appear and it  said:
 bla bla bla Scarlet Legacy.py line 4, in <module> from sanae3D.Sanae import SanaeObject
ImportError: No module named Sanae3D.Sanae

ok, i tried to search about this Sanae3D...sorry but  i understand NOTHING about this sanae3D...

Someone knows HOW can I import Scarlet Legacy model into noesis?
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-19T22:41:28+00:00
- Post Title: scarlet legacy fail import with noesis

> Reply from Drawing
>
> I was surfing on the net and i founded this game Scarlet Legacy

i try to search on xentax about this game and Ta-Dan i've found the plugin for noesis ( thanks to finale 00) https://www.dropbox.com/sh/7stlpd4qvkq3 ... acy_bsm.py

Ok, i download it, i put it into plugins's folder and i run Noesis.

But an error appear and it  said:
 bla bla bla Scarlet Legacy.py line 4, in <module> from sanae3D.Sanae import SanaeObject
ImportError: No module named Sanae3D.Sanae

ok, i tried to search about this Sanae3D...sorry but  i understand NOTHING about this sanae3D...

Someone knows HOW can I import Scarlet Legacy model into noesis?

You have to have sanae3d inside your python scripts if it's finale's script. If not, you won't be able to run it.

Download it from here:

[https://www.dropbox.com/s/7stlpd4qvkq3096](https://www.dropbox.com/s/7stlpd4qvkq3096)

See ya.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-19T23:22:24+00:00
- Post Title: scarlet legacy fail import with noesis

I forgot to remove that package dependency from my test code lol
Usually I use it for convenience testing and then take it out when I move to a different format.

I've updated it by removing that dependency
Don't have the game on the computer anymore though so I couldn't test whether it works or not.
## Post #4
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-20T20:54:08+00:00
- Post Title: scarlet legacy fail import with noesis

I tried to import some bsm files but another error appear...



I've upload some bsm file, so you can try the script without download the game...

Here the samples [http://depositfiles.com/files/ulit6vev3](http://depositfiles.com/files/ulit6vev3)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T21:17:20+00:00
- Post Title: scarlet legacy fail import with noesis

Looks like one of my earlier scripts where I was still using methods like those. Guess I have to go through the entire script to make it less dependent on my test package.
## Post #6
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-20T21:55:13+00:00
- Post Title: scarlet legacy fail import with noesis

oh... and will you do it?

Please xD
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T22:56:52+00:00
- Post Title: scarlet legacy fail import with noesis

DF isn't working for me upload it to mediafire or dropbox or something.
And never use DF.

EDIT: I have updated the script. Turns out I didn't delete the game yet lol
I think the normals and UV's are half-floats, but I'll need some textures to verify.

The decompression script available is kind of weird in the sense that it chops off the first integer in the resulting file.
The plugin automatically decompresses a compressed file, so you don't need to bother decompressing it separately.

I'm also going to write a texture plugin that will load compressed texture files ("GRO" idstring)
## Post #8
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-21T09:21:07+00:00
- Post Title: scarlet legacy fail import with noesis

Well i've tryed your plugin and now he works sometimes.
Infact when i load some bsm appear an error that said:

bla bla bla line 52, in neopyLoadModel
mdl = rapi.rpgConstructModel()
RuntimeError : Failed to construct model fromrpgeo context
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-21T17:39:14+00:00
- Post Title: scarlet legacy fail import with noesis

Which ones.
## Post #10
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-21T18:12:00+00:00
- Post Title: scarlet legacy fail import with noesis

with some files, some part of armor and some weapon estract from weapon pak
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-21T18:14:56+00:00
- Post Title: scarlet legacy fail import with noesis

You should give the names.
## Post #12
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-22T19:40:54+00:00
- Post Title: scarlet legacy fail import with noesis

Some samples:
PTD1_010_Body2.bsm
STD1_002_Weapon.bsm
## Post #13
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-24T10:02:36+00:00
- Post Title: scarlet legacy fail import with noesis

news?
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-24T16:08:21+00:00
- Post Title: scarlet legacy fail import with noesis

Send me the files I can't find them lol
## Post #15
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-25T17:29:51+00:00
- Post Title: scarlet legacy fail import with noesis

Ok don't worry  it was my mistake...
I've seen that you have upload the py for the textures... But i don't know why but noesis don't load correctly the model texturated...
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-25T19:24:22+00:00
- Post Title: Re: scarlet legacy fail import with noesis

There are some issues with textures because I don't know where the material library is.
## Post #17
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-26T10:02:16+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Ok, thanks for the support ^^
sorry xD but i've another question...
Seeing in your noesis plugin, i saw that also in ValkyrieSky,VoyageCenturyOnline,Travia2,talesOfFantasy and silkroad py there is the line sanae3d.sanae... The same of the first py of scarlet legacy... Can you tell me how can i resolve the problem? What i've to delete in there py plugin ?
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-26T16:41:46+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Start by deleting the import line.
Then replace all references to `SanaeObject` with `Object`.

Then open Sanae.py, go to the `__init__` method and copy the thing over to the plugin's `__init__` method.

Look for any references to `read_string` and replace it with `noeStrFromBytes(...)`, and type in the appropriate call to read that many number of bytes.

There are probably other references to SanaeObject methods which will need to be replaced.
## Post #19
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-26T19:55:41+00:00
- Post Title: Re: scarlet legacy fail import with noesis

this is your plugin
[https://www.dropbox.com/sh/7stlpd4qvkq3 ... oad_bms.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/J15ZjCGCe1/fmt_silkroad_bms.py)

and this is what i've done ... i don't know if it's correct but when i load bsm file from silkroad i've an error the error is:
-Line 62, in noepyLoadModel load single_model(data, mdlList)
-Line 49, in load single model parser = SanaeParser(data)
-Line 68, in __init__ super(sanaeParser, self).__init__(self,data)
TypeError: object.__init__() takes no parameters)

```
import noesis
import rapi
import os

MODE = 0

def registerNoesisTypes():
    handle = noesis.register("Silkroad Online", ".bms")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    noesis.logPopup()

    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    
    if len(data) < 12:
        return 0
    bs = NoeBitStream(data)
    if bs.readBytes(12).decode("ASCII") != "JMXVBMS 0110":
        return 0
    return 1

def load_all_models(mdlList):
    '''Load all models'''

    #carry over from previous models
    matList = []
    texList = []

    dirPath = rapi.getDirForFilePath(rapi.getInputName())
    fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".bms")]
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
       
        super(SanaeParser, self).__init__(self, data)
        
    def read_name(self):
        
        return self.noeStrFromBytes(self.inFile.readUInt())
    
    def parse_vertices(self, numVerts, vertType):
        
        if vertType == 0:
            vertBuff = self.inFile.readBytes(44*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 24)            
        elif vertType == 1024:
            vertBuff = self.inFile.readBytes(52*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 24)
            
    def parse_faces(self, numIdx):
        
        idxBuff = self.inFile.readBytes(2*numIdx)
        rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
        
    def parse_bones(self, numBones, numVerts):
        
        for i in range(numBones):
            boneName = self.read_name()
        if numBones:
            for i in range(numVerts):
                b1 = self.inFile.readByte()
                w1 = self.inFile.readUShort()
                b2 = self.inFile.readByte()
                w2 = self.inFile.readUShort()
                
    def load_texture(self, matName):
        
        #texPath, ext = os.path.splitext(self.abspath.replace("mesh", "mtrl"))
        #f = open(texPath + ".ddj")
        try:
            f = open(self.basename + ".ddj", 'rb')
            f.seek(20)
            tex = rapi.loadTexByHandler(f.read(), ".dds")
            if tex is not None:
                tex.name = matName
                self.texList.append(tex)           
                
            material = NoeMaterial(matName, matName)
            self.matList.append(material)             
        except:
            pass        

    def parse_file(self):
        
        idstring = self.inFile.readBytes(12)
        offVerts, offBones, offFaces, unkOff1, unkOff2, ofsbbox, unkOff4, \
                 unk1, unk2, unkOff5, unk3, unk4, unk5, vertType, unk7 \
                 = self.inFile.read('15L')
        meshName = self.read_name()
        matName = self.read_name()
        
        self.inFile.readUInt()
        
        self.inFile.seek(offVerts)
        numVerts = self.inFile.readUInt()
        self.parse_vertices(numVerts, vertType)
        
        self.inFile.seek(offBones)
        numBones = self.inFile.readUInt()
        self.parse_bones(numBones, numVerts)
        
        self.inFile.seek(offFaces)
        numFaces = self.inFile.readUInt()
        
        rapi.rpgSetMaterial(matName)
        self.parse_faces(numFaces*3)

        self.load_texture(matName)
```
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-26T22:30:38+00:00
- Post Title: Re: scarlet legacy fail import with noesis

You have to replace the __init__ method completely with the one in the former superclass (SanaeObject)
## Post #21
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-27T15:24:57+00:00
- Post Title: Re: scarlet legacy fail import with noesis

i'm not english, i don't understand everything >.< can u give me an example?
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-27T17:16:42+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Copy

```
self.animList = []
self.texList = []
self.matList = []
self.boneList = []

```


Replace in plugin

```

```
## Post #23
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-28T17:41:42+00:00
- Post Title: Re: scarlet legacy fail import with noesis

this is the new code

```
import noesis
import rapi
import os

MODE = 0

def registerNoesisTypes():
    handle = noesis.register("Silkroad Online", ".bms")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    noesis.logPopup()

    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    
    if len(data) < 12:
        return 0
    bs = NoeBitStream(data)
    if bs.readBytes(12).decode("ASCII") != "JMXVBMS 0110":
        return 0
    return 1

def load_all_models(mdlList):
    '''Load all models'''

    #carry over from previous models
    matList = []
    texList = []

    dirPath = rapi.getDirForFilePath(rapi.getInputName())
    fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".bms")]
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
       
        super(SanaeParser, self).__init__(data)
        
                                self.inFile = NoeBitStream(data)
                                self.meshList = []
                                self.uvList = []
                                self.normList = []
                                self.vertList = []
                                self.idxList = []
                                self.animList = []
                                self.texList = []
                                self.matList = []
                                self.boneList = []
                                self.abspath = self._abspath()
                                self.dirpath = self._dirpath()
                                self.basename = self._basename()
                                self.filename = self._filename()        
    
    def read_name(self):
        
        return self.noeStrFromBytes(self.inFile.readUInt())
    
    def parse_vertices(self, numVerts, vertType):
        
        if vertType == 0:
            vertBuff = self.inFile.readBytes(44*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 24)            
        elif vertType == 1024:
            vertBuff = self.inFile.readBytes(52*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 24)
            
    def parse_faces(self, numIdx):
        
        idxBuff = self.inFile.readBytes(2*numIdx)
        rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
        
    def parse_bones(self, numBones, numVerts):
        
        for i in range(numBones):
            boneName = self.read_name()
        if numBones:
            for i in range(numVerts):
                b1 = self.inFile.readByte()
                w1 = self.inFile.readUShort()
                b2 = self.inFile.readByte()
                w2 = self.inFile.readUShort()
                
    def load_texture(self, matName):
        
        #texPath, ext = os.path.splitext(self.abspath.replace("mesh", "mtrl"))
        #f = open(texPath + ".ddj")
        try:
            f = open(self.basename + ".ddj", 'rb')
            f.seek(20)
            tex = rapi.loadTexByHandler(f.read(), ".dds")
            if tex is not None:
                tex.name = matName
                self.texList.append(tex)           
                
            material = NoeMaterial(matName, matName)
            self.matList.append(material)             
        except:
            pass        

    def parse_file(self):
        
        idstring = self.inFile.readBytes(12)
        offVerts, offBones, offFaces, unkOff1, unkOff2, ofsbbox, unkOff4, \
                 unk1, unk2, unkOff5, unk3, unk4, unk5, vertType, unk7 \
                 = self.inFile.read('15L')
        meshName = self.read_name()
        matName = self.read_name()
        
        self.inFile.readUInt()
        
        self.inFile.seek(offVerts)
        numVerts = self.inFile.readUInt()
        self.parse_vertices(numVerts, vertType)
        
        self.inFile.seek(offBones)
        numBones = self.inFile.readUInt()
        self.parse_bones(numBones, numVerts)
        
        self.inFile.seek(offFaces)
        numFaces = self.inFile.readUInt()
        
        rapi.rpgSetMaterial(matName)
        self.parse_faces(numFaces*3)

        self.load_texture(matName)
```


but i don't know why but appear an error when i launch noesis:
silkroad py
line 70 
self.inFile = NoeBitStream(data)
^
IndentationError: unexpected indent

I don't know what to do >.<
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-28T17:48:40+00:00
- Post Title: Re: scarlet legacy fail import with noesis

One issue with python is that all whitespace must be consistent. Either you use spaces, or you use tabs, but not both. And the amount of spacing must be exactly as expected.

You're supposed to delete the super call as well since you're no longer using it.
## Post #25
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-28T18:18:54+00:00
- Post Title: Re: scarlet legacy fail import with noesis

so... what i've to delete?
Sorry but i'm a noob in programming language
## Post #26
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-28T23:25:24+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Just delete the line that says super.
## Post #27
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-29T17:25:34+00:00
- Post Title: Re: scarlet legacy fail import with noesis

I deleted the line says :<<super(SanaeParser, self).__init__(data)>>

but another error appear D:

line 78, __init__
self.adspath = self.:abspath()
AttibuteError: 'SanaeParser' object has no attribute '_abspath'
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-29T17:32:02+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Most of them you don't need. I've only used matList and texList cause that's all I did.
The paths are not important either for the most part.
## Post #29
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-30T12:50:19+00:00
- Post Title: Re: scarlet legacy fail import with noesis

```
self.animList = []
self.texList = []
self.matList = []
self.boneList = []
```


so do i have to delete "self.inFile = NoeBitStream(data),self.animList = []and self.boneList = []" ?
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-30T14:57:38+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Try it out...? Your computer isn't going to explode if it doesn't work.
## Post #31
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-30T17:21:09+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Infact i've tryed ^^ but when i load a model:

-Line 62,in noepyLoadModel 
load_single_model(data, mdlList)

-Line 50, in load_single_model 
parser.parser_file()

-Line 124, in parse_file
idstring = self.inFile.readyBytes(12)
AttributeError: 'SanaeParser' object has no attribute 'inFile'
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-30T17:29:54+00:00
- Post Title: Re: scarlet legacy fail import with noesis

That means it is expecting an attribute called self.inFile, which you probably deleted.
So you shouldn't delete it.
## Post #33
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-06-30T18:57:19+00:00
- Post Title: Re: scarlet legacy fail import with noesis

This is your py now:

```
import noesis
import rapi
import os

MODE = 0

def registerNoesisTypes():
    handle = noesis.register("Silkroad Online", ".bms")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    noesis.logPopup()

    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    
    if len(data) < 12:
        return 0
    bs = NoeBitStream(data)
    if bs.readBytes(12).decode("ASCII") != "JMXVBMS 0110":
        return 0
    return 1

def load_all_models(mdlList):
    '''Load all models'''

    #carry over from previous models
    matList = []
    texList = []

    dirPath = rapi.getDirForFilePath(rapi.getInputName())
    fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".bms")]
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
        
        self.inFile = NoeBitStream(data)
        self.texList = []
        self.matList = []
        
              
    def read_name(self):
        
        return self.noeStrFromBytes(self.inFile.readUInt())
    
    def parse_vertices(self, numVerts, vertType):
        
        if vertType == 0:
            vertBuff = self.inFile.readBytes(44*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 24)            
        elif vertType == 1024:
            vertBuff = self.inFile.readBytes(52*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 24)
            
    def parse_faces(self, numIdx):
        
        idxBuff = self.inFile.readBytes(2*numIdx)
        rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
        
    def parse_bones(self, numBones, numVerts):
        
        for i in range(numBones):
            boneName = self.read_name()
        if numBones:
            for i in range(numVerts):
                b1 = self.inFile.readByte()
                w1 = self.inFile.readUShort()
                b2 = self.inFile.readByte()
                w2 = self.inFile.readUShort()
                
    def load_texture(self, matName):
        
        #texPath, ext = os.path.splitext(self.abspath.replace("mesh", "mtrl"))
        #f = open(texPath + ".ddj")
        try:
            f = open(self.basename + ".ddj", 'rb')
            f.seek(20)
            tex = rapi.loadTexByHandler(f.read(), ".dds")
            if tex is not None:
                tex.name = matName
                self.texList.append(tex)           
                
            material = NoeMaterial(matName, matName)
            self.matList.append(material)             
        except:
            pass        

    def parse_file(self):
        
        idstring = self.inFile.readBytes(12)
        offVerts, offBones, offFaces, unkOff1, unkOff2, ofsbbox, unkOff4, \
                 unk1, unk2, unkOff5, unk3, unk4, unk5, vertType, unk7 \
                 = self.inFile.read('15L')
        meshName = self.read_name()
        matName = self.read_name()
        
        self.inFile.readUInt()
        
        self.inFile.seek(offVerts)
        numVerts = self.inFile.readUInt()
        self.parse_vertices(numVerts, vertType)
        
        self.inFile.seek(offBones)
        numBones = self.inFile.readUInt()
        self.parse_bones(numBones, numVerts)
        
        self.inFile.seek(offFaces)
        numFaces = self.inFile.readUInt()
        
        rapi.rpgSetMaterial(matName)
        self.parse_faces(numFaces*3)

        self.load_texture(matName)
```


I added the line "self.inFile = NoeBitStream(data)" that before i had deleted but now the plugin said:

-Line 62,in noepyLoadModel 
load_single_model(data, mdlList)

-Line 50, in load_single_model 
parser.parser_file()

-Line 129, in parse_file
meshName = self.read_name()

-line 75, in read_name
return self.noeStrFromBytes(self.inFile.readUint())

AttributeError: ' SanaeParser' object has no attribute 'noeStrFromBytes'
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-30T19:40:12+00:00
- Post Title: Re: scarlet legacy fail import with noesis

noeStrFromBytes is part of inc_noesis, so you don't need self.
## Post #35
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-07-01T08:52:18+00:00
- Post Title: Re: scarlet legacy fail import with noesis

this is the line:

```
return self.noeStrFromBytes(self.inFile.readUInt())
```


What self do i've to delete?
## Post #36
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-01T14:05:13+00:00
- Post Title: Re: scarlet legacy fail import with noesis

I'm guessing it has to be 

```

```


That is if the self.inFile.readUInt() is the length of the namestring.
## Post #37
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-07-01T14:52:53+00:00
- Post Title: Re: scarlet legacy fail import with noesis

Yeeeeeeeeeeeeeah! 
Thanks to both! Thanks a lot !

This is the noesis py importer for silkroad if someone had needed it

```
import noesis
import rapi
import os

MODE = 0

def registerNoesisTypes():
    handle = noesis.register("Silkroad Online", ".bms")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    noesis.logPopup()

    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    
    if len(data) < 12:
        return 0
    bs = NoeBitStream(data)
    if bs.readBytes(12).decode("ASCII") != "JMXVBMS 0110":
        return 0
    return 1

def load_all_models(mdlList):
    '''Load all models'''

    #carry over from previous models
    matList = []
    texList = []

    dirPath = rapi.getDirForFilePath(rapi.getInputName())
    fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".bms")]
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
        
        self.inFile = NoeBitStream(data)
        self.texList = []
        self.matList = []
        
              
    def read_name(self):
        
        return noeStrFromBytes(self.inFile.readBytes(self.inFile.readUInt()))
    
    def parse_vertices(self, numVerts, vertType):
        
        if vertType == 0:
            vertBuff = self.inFile.readBytes(44*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 44, 24)            
        elif vertType == 1024:
            vertBuff = self.inFile.readBytes(52*numVerts)
            rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 0)
            rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 12)
            rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 52, 24)
            
    def parse_faces(self, numIdx):
        
        idxBuff = self.inFile.readBytes(2*numIdx)
        rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)
        
    def parse_bones(self, numBones, numVerts):
        
        for i in range(numBones):
            boneName = self.read_name()
        if numBones:
            for i in range(numVerts):
                b1 = self.inFile.readByte()
                w1 = self.inFile.readUShort()
                b2 = self.inFile.readByte()
                w2 = self.inFile.readUShort()
                
    def load_texture(self, matName):
        
        #texPath, ext = os.path.splitext(self.abspath.replace("mesh", "mtrl"))
        #f = open(texPath + ".ddj")
        try:
            f = open(self.basename + ".ddj", 'rb')
            f.seek(20)
            tex = rapi.loadTexByHandler(f.read(), ".dds")
            if tex is not None:
                tex.name = matName
                self.texList.append(tex)           
                
            material = NoeMaterial(matName, matName)
            self.matList.append(material)             
        except:
            pass        

    def parse_file(self):
        
        idstring = self.inFile.readBytes(12)
        offVerts, offBones, offFaces, unkOff1, unkOff2, ofsbbox, unkOff4, \
                 unk1, unk2, unkOff5, unk3, unk4, unk5, vertType, unk7 \
                 = self.inFile.read('15L')
        meshName = self.read_name()
        matName = self.read_name()
        
        self.inFile.readUInt()
        
        self.inFile.seek(offVerts)
        numVerts = self.inFile.readUInt()
        self.parse_vertices(numVerts, vertType)
        
        self.inFile.seek(offBones)
        numBones = self.inFile.readUInt()
        self.parse_bones(numBones, numVerts)
        
        self.inFile.seek(offFaces)
        numFaces = self.inFile.readUInt()
        
        rapi.rpgSetMaterial(matName)
        self.parse_faces(numFaces*3)

        self.load_texture(matName)
```
