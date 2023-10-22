## Post #1
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-24T18:45:20+00:00
- Post Title: Total War: Warhammer, Noesis script

Hi,

In order to learn how to write scripts in noesis i decided to take zaramot,Total War: Warhammer II script and convert it to noesis.
i have encountered 2 issues i could use help with.

1. Warhammer has 2 files .ANIM files to get the skeleton and .V2 to get mesh data
i have a working script to import the .ANIM files but dont know how to import in noesis 2 files at the same time (.ANIM, . V2) to run them both together.
if anyone could refer me to an existing script which does this that would be great.

2. my second issue is in the .V2 script, when trying to bind the vertices i dont get the correct data, verts are in half floats, but noesis offers only 
BYTE, SHORT, FLOAT
i tried using SHORT or FLOAT but both give me odd  shapes, using  a python script i wrote i exported the data to .obj and the mesh loads correctly
so i dont think i have the wrong data

this is the code i used to bind the vertices 

```
rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 0)
```

if there is any way to print out the verts used (not vertbuffer) to validate my data?

Edit:
This is the full working script - supports skinned and static mesh with uv, and loads all textures as long as they are in the same folder.
loading mesh works for TWH1 + TWH2, skeleton works for TWH2, for TWH1 i have issue i couldn't resolve where skeleton loads rotated and misaligned on X- axis
[fmt_WarhammerTotalWar.rar](https://xentaxbackup.github.io/file/16897_fmt_WarhammerTotalWar.rar)
## Post #2
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-25T04:40:54+00:00
- Post Title: Total War: Warhammer, Noesis script

this is the script i am using for the mesh: (didnt add face data until i can get the verts correct)

```
import noesis
import rapi

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("Warhammer Total War 2", ".rigid_model_v2")
    noesis.logPopup() # activates debug console
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    return 1
    
def noepyLoadModel(data, mdlList):

    ctx = rapi.rpgCreateContext()
    f = NoeBitStream(data, NOE_LITTLEENDIAN)
    
    EndPos = len(data)
    
    Magic = noeStrFromBytes(f.readBytes(4), "ASCII")
    print(Magic)
    if Magic != "RMV2":
        print("worng file format")
    
    MeshCount = f.readInt()
    LodCount = f.readInt()

    f.seek(140,0) # seek 0x8c from start of file
    
    for i in range(LodCount):
        f.seek(28,1)
    
    Pos = f.tell()
    
    j = 0
    s = 0
    
    # get vertex, uv data
    #read first mesh for now
    while s < 1: # read until end of file

        id = f.readUInt() # I read unsigned int 
        LodStart = f.readUInt()
        VertexStart = f.readUInt()
        VertexCount = f.readUInt()
        FaceStart = f.readUInt()
        FaceCount = f.readUInt() 

        #can skip following data need to (seek 24,1)
        BBX1 = f.readFloat() 
        BBY1 = f.readFloat()
        BBZ1 = f.readFloat()

        BBX2 = f.readFloat()
        BBY2 = f.readFloat()
        BBZ2 = f.readFloat()

        MatType = f.readString() # read string of unknown size - need to check might need seek -1
   
        Unk1 = f.readFloat()
        Unk2 = f.readFloat()

        f.seek(12,1)

        Vtype = f.readShort() # h read short

        ModelName = noeStrFromBytes(f.readBytes(32), "ASCII") # read string of known size   
        MaterialName = noeStrFromBytes(f.readBytes(514), "ASCII")
    
        for i in range(0,3):
            f.seek(52,1)
   
        FFFF = f.readInt64() #  read long long
        
        BoneCount = f.readUInt()
        MatsCount = f.readUInt()
        f.seek(8,1)
        Unk4 = f.readUInt()

        f.seek(128,1)

        for i in range(0,BoneCount):
            f.seek(84,1)

        for i in range(0,MatsCount):
            f.seek(260,1)
    
        Unk4 = f.readUInt()
        LODCount = f.readUInt()

        PosV = f.tell()
        
        print(PosV)
        print(VertexCount)
        
        if Vtype == 4:
            VertBuff = f.readBytes(VertexCount * 32)           
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 0) # vertex
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 20) # uv
        if Vtype == 3:
            VertBuff = f.readBytes(VertexCount * 28)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 28, 0)
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 28, 16)

        rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertexCount, noesis.RPGEO_POINTS, 1)
        mdl = rapi.rpgConstructModel()
        mdlList.append(mdl)
        
        
        #need to convert to noesis       
        # get faces array
        #faceArray.append([])
        #for i in range(int(FaceCount/3)):           
            #f1 = f.readShort()
            #f2 = f.readShort()
            #f3 = f.readShort()
            #faceArray[s].append((f1,f2,f3))
            
        Pos = f.tell()
        s += 1
            
    rapi.rpgClearBufferBinds()
    return 1 
```


link to sample file:
[https://drive.google.com/open?id=1hV7lz ... eIEiGwAjRd](https://drive.google.com/open?id=1hV7lzuFbwDoLzSw-aHUk3-eIEiGwAjRd)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-25T06:58:48+00:00
- Post Title: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Wed Sep 25, 2019 2:45 am at Wed Sep 25, 2019 2:45 am
>
> dont know how to import in noesis 2 files at the same time (.ANIM, . V2) to run them both together.
Use the following workflow to open another source data file:

```
if animFile == None:
	return 0
animBS = NoeBitStream(animFile)

```


> Reply from jayn23 ↑Wed Sep 25, 2019 2:45 am at Wed Sep 25, 2019 2:45 am
>
> but noesis offers only BYTE, SHORT, FLOAT
There is actually a readHalfFloat() method in the NoeBitStream class. Also a RPGEODATA_HALFFLOAT constant available.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-09-25T07:07:01+00:00
- Post Title: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Wed Sep 25, 2019 2:45 am at Wed Sep 25, 2019 2:45 am
>
> 
2. my second issue is in the .V2 script, when trying to bind the vertices i dont get the correct data, verts are in half floats, but noesis offers only 
BYTE, SHORT, FLOAT
RPGEODATA_HALFFLOAT seems to still work fine when
i tried in this basic script with hardcoded values.  

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Warhammer Total War 2", ".rigid_model_v2")
    noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
    #noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    FIOffset = 0x25fd4
    FCount = 23229
    VOffset = 0xdb4
    VBytes = 32
    VCount = 4753
    bs.seek(FIOffset)
    IBuf = bs.readBytes(FCount * 2)
    bs.seek(VOffset)
    VBuf = bs.readBytes(VCount * VBytes)
    rapi.rpgBindPositionBufferOfs(VBuf, noesis.RPGEODATA_HALFFLOAT, VBytes, 0)
    rapi.rpgBindUV1BufferOfs(VBuf, noesis.RPGEODATA_HALFFLOAT, VBytes, 20)
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE, 1)
    mdl = rapi.rpgConstructModel()                                                          
    mdlList.append(mdl)
    rapi.rpgClearBufferBinds()
    return 1
```




test.png (47.57 KiB) Viewed 1222 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-25T08:28:04+00:00
- Post Title: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Wed Sep 25, 2019 12:40 pm at Wed Sep 25, 2019 12:40 pm
>
> 
this is the script i am using for the mesh: (didnt add face data until i can get the verts correct)
Code: Select allfrom inc_noesis import *
import noesis
import rapi

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("Warhammer Total War 2", ".rigid_model_v2")
    noesis.logPopup() # activates debug console
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    return 1
    
def noepyLoadModel(data, mdlList):

    ctx = rapi.rpgCreateContext()
    f = NoeBitStream(data, NOE_LITTLEENDIAN)
    
    EndPos = len(data)
    
    Magic = noeStrFromBytes(f.readBytes(4), "ASCII")
    print(Magic)
    if Magic != "RMV2":
        print("worng file format")
    
    MeshCount = f.readInt()
    LodCount = f.readInt()

    f.seek(140,0) # seek 0x8c from start of file
    
    for i in range(LodCount):
        f.seek(28,1)
    
    Pos = f.tell()
    
    j = 0
    s = 0
    
    # get vertex, uv data
    #read first mesh for now
    while s < 1: # read until end of file

        id = f.readUInt() # I read unsigned int 
        LodStart = f.readUInt()
        VertexStart = f.readUInt()
        VertexCount = f.readUInt()
        FaceStart = f.readUInt()
        FaceCount = f.readUInt() 

        #can skip following data need to (seek 24,1)
        BBX1 = f.readFloat() 
        BBY1 = f.readFloat()
        BBZ1 = f.readFloat()

        BBX2 = f.readFloat()
        BBY2 = f.readFloat()
        BBZ2 = f.readFloat()

        MatType = f.readString() # read string of unknown size - need to check might need seek -1
   
        Unk1 = f.readFloat()
        Unk2 = f.readFloat()

        f.seek(12,1)

        Vtype = f.readShort() # h read short

        ModelName = noeStrFromBytes(f.readBytes(32), "ASCII") # read string of known size   
        MaterialName = noeStrFromBytes(f.readBytes(514), "ASCII")
    
        for i in range(0,3):
            f.seek(52,1)
   
        FFFF = f.readInt64() #  read long long
        
        BoneCount = f.readUInt()
        MatsCount = f.readUInt()
        f.seek(8,1)
        Unk4 = f.readUInt()

        f.seek(128,1)

        for i in range(0,BoneCount):
            f.seek(84,1)

        for i in range(0,MatsCount):
            f.seek(260,1)
    
        Unk4 = f.readUInt()
        LODCount = f.readUInt()

        PosV = f.tell()
        
        print(PosV)
        print(VertexCount)
        
        if Vtype == 4:
            VertBuff = f.readBytes(VertexCount * 32)           
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 0) # vertex
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 20) # uv
        if Vtype == 3:
            VertBuff = f.readBytes(VertexCount * 28)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 28, 0)
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 28, 16)

        rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertexCount, noesis.RPGEO_POINTS, 1)
        mdl = rapi.rpgConstructModel()
        mdlList.append(mdl)
        
        
        #need to convert to noesis       
        # get faces array
        #faceArray.append([])
        #for i in range(int(FaceCount/3)):           
            #f1 = f.readShort()
            #f2 = f.readShort()
            #f3 = f.readShort()
            #faceArray[s].append((f1,f2,f3))
            
        Pos = f.tell()
        s += 1
            
    rapi.rpgClearBufferBinds()
    returnI wonder how you get this script to run? Which Noesis version do you use?
I always get a Type error (Noesis debug output):

```
RMV2
201810 3256 4753 155352 23229
-0.738558828830719 -0.0019068646943196654 -2.2086567878723145
0.7385584712028503 2.200343370437622 0.940676212310791 default_dry
bst_centigor_body_01 variantmeshes/wh_variantmodels/ce1/bst/bst_centigor/tex/
-1 12 5
Unk4 1
0 1
0xdb4
4753
0x25fd4
```

TypeError: an integer is required
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-09-25T09:16:35+00:00
- Post Title: Total War: Warhammer, Noesis script

> Reply from shakotay2 ↑Wed Sep 25, 2019 4:28 pm at Wed Sep 25, 2019 4:28 pm
>
> 
I wonder how you get this script to run? Which Noesis version do you use?
I always get a Type error (Noesis debug output):
i think is because his script is posted with incomplete last line:
return should be return 1
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-25T09:29:21+00:00
- Post Title: Total War: Warhammer, Noesis script

Ace, you're simply the best! ("better than all the rest"  , A chance is going to come, Tina Turner)
.
not as nice as your's (how did you smooth it? edit: well, see, I missed another "1"  ):
.



bst_centigor_body_01-rigid_model_v2-Noesis-py.jpg (159.74 KiB) Viewed 1193 times
## Post #8
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-25T18:18:53+00:00
- Post Title: Total War: Warhammer, Noesis script

Hi 

thanks guys for all your help, i got it working 

now i just need to add the weight data, and combine it with the .ANIM script
for the weight data i couldn't find anything similar to "rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 0)" 
so i just store it an an array that i create? or is there some class or function that is already built in?

> animFile = rapi.loadIntoByteArray(animFileName)
>
> if animFile == None:
>
> 	return 0
>
> animBS = NoeBitStream(animFile)
i am not sure i understand what to do with this?
i understand the code where i would load a second file, but how do i choose the file that needs loading?
for the first file you just double click a file and that's the file noesis loads, how do you get noesis  to ask to open/choose the second file?

> i think is because his script is posted with incomplete last line:
>
> return should be return 1
my bad    fixed

thanks again really appreciate the help
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-25T18:53:47+00:00
- Post Title: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Thu Sep 26, 2019 2:18 am at Thu Sep 26, 2019 2:18 am
>
> how do you get noesis it to ask to open/choose the second file?try out something like this:

```
if (rapi.checkFileExists(texFileName)):
	cprTexData = rapi.loadIntoByteArray(texFileName)
```

(It's from fmt_bulletwitch_cpr.py.)

btw: didn't test it; hope, rapi.getInputName() will open a file browser...
but if so I wouldn't know why should one check, whether the "FileExists"?

Makes sense in case the files (mesh/anim) share the same basename, so you loaded the mesh (bubba.msh), cut of its extension, add ".ani"
and then you had to check whether bubba.ani exists.

edit: well, all the time I felt I must have a deja vue but my brain is empty (as always),
then loadPairedFile was coming into mind.

You might check this post/similar problem:

> Reply from tainhx ↑Sat Mar 16, 2019 3:05 pm at Sat Mar 16, 2019 3:05 pm
>
> 

```
    fileExt = filePath.split('.')[-1]  # get file extesion

    boneData = rapi.loadPairedFile("YulgangVN - BON", ".bon")
    aniData = rapi.loadPairedFile("YulgangVN - Ani", ".ani")

```
## Post #10
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-25T20:48:37+00:00
- Post Title: Total War: Warhammer, Noesis script

i found a work around in an old script  fmt_C9_r3cm.py basically what i did:

```
    fileList = [file for file in os.listdir(dirPath) if file.lower().endswith(".anim")]
    for file in fileList:
        filename, ext = os.path.splitext(file)
        bs = open(dirPath + file, 'rb')
        bs_data = bs.read()

bones = skeleton_data(bs_data)
```

for this to work mesh and skeleton files must be in the same directory and no other . anim files in folder, i am going to try the "rapi.loadPairedFile" sound like exactly what i am looking for.

for now what i am getting is...interesting
my mesh and skeleton dont Quite match up in size   
i guess i need to work an my weight implementation.



model.JPG (148.31 KiB) Viewed 1156 times
## Post #11
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-27T07:45:19+00:00
- Post Title: Total War: Warhammer, Noesis script

> then loadPairedFile was coming into mind.
worked perfectly thanks for that. 

just one more issue i could some help with,
 bindings the weights to skeleton/mesh - i dont understand the syntax that is needed:

```
from math import *
from inc_noesis import *



def registerNoesisTypes():
    handle = noesis.register("Warhammer Total War 2", ".anim;.rigid_model_v2")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    # noesis.setHandlerWriteModel(handle, noepyWriteModel)
    # noesis.setHandlerWriteAnim(handle, noepyWriteAnim)

    noesis.logPopup()
    return 1


def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    return 1



#load the skeleton data
def Skeleton(data):
    bs = NoeBitStream(data, NOE_LITTLEENDIAN)
    bs.seek(12,0)
    SkelNameSize = bs.readShort()   
    SkelName = bs.readString()
    print(SkelName)
    bs.seek(-1,1) # for some reason read string is reading 1 byte extra
    Check = bs.readUInt()
    print(Check)
    
    if Check == 0:
        bs.seek(4,1)
    
    if Check != 0:
        bs.seek(0,1)
    
    BoneCount = bs.readUInt()
    print(BoneCount)
    
    parent_arr = []
    BoneNameArray = []
    
    for i in range(BoneCount):
        BNameSize = bs.readShort()
        BoneName = noeStrFromBytes(bs.readBytes(BNameSize), "ASCII")
        BoneParent = bs.readInt()
        parent_arr.append(BoneParent) #parr in maxscript
        BoneNameArray.append(BoneName)
        
 
    BMapArray = []
    bones = []
    
    for i in range(BoneCount):
        BoneId = bs.readUInt() + 1 # need t ocheck if i need this + 1
        BMapArray.append(BoneId)
        
    #dont think i need this
    for i in range(BoneCount):
        BoneId = bs.readUInt()
        
    if Check == 0:
        bs.seek(8,1)
        
    #dont think i need this, can skip?
    BoneCount1 = bs.readInt()
    BoneCount2 = bs.readInt()    
    Count = bs.readInt()
    
    translation_arr = []
    rotation_arr = []
    Quat = [0]*4
    
    for i in range(BoneCount):
        Tran = NoeVec3.fromBytes(bs.readBytes(12)) 
        translation_arr.append(Tran) # in maxscript * 100 to make bigger
    #print(translation_arr)
  
    for i in range(BoneCount): 
        #a = bs.tell()
        #print(a)
        b11 = bs.readShort()
        b12 = bs.readShort()
        b13 = bs.readShort()
        b14 = bs.readShort()
        #print("b14 = ", b14)
        Rot = NoeQuat((b11,b12,b13,b14))
        #print("Rot = ", Rot)
        Rot = Rot.normalize()
        boneMat = Rot.toMat43(transposed = 1)
        boneMat[3] = translation_arr[i]
        #print("Norm = ", Rot)
        #print("boneMat = ", boneMat)
        bones.append( NoeBone(i, BoneNameArray[i], boneMat, None, parent_arr[i]) )
        


    # Converting local matrix to world space
    for i in range(0, BoneCount):
        j = bones[i].parentIndex
        #print("j = ", j)
        if j != -1:
            bones[i].setMatrix(bones[i].getMatrix().__mul__(bones[j].getMatrix()))

    return bones


#load mesh data
def Mesh(data):
    weights = []
    boneids = []

    f = NoeBitStream(data, NOE_LITTLEENDIAN)
    
    EndPos = len(data)
    
    Magic = noeStrFromBytes(f.readBytes(4), "ASCII")
    print(Magic)
    if Magic != "RMV2":
        print("worng file format")
    
    MeshCount = f.readInt()
    LodCount = f.readInt()

    f.seek(140,0) # seek 0x8c from start of file
    
    for i in range(LodCount):
        f.seek(28,1)
    
    Pos = f.tell()
    
    j = 0
    s = 0
    
    # get vertex, weight, uv data
    #read first mesh for now
    while s < (MeshCount + LodCount): # read until end of file

        id = f.readUInt() # I read unsigned int 
        LodStart = f.readUInt()
        VertexStart = f.readUInt()
        VertexCount = f.readUInt()
        FaceStart = f.readUInt()
        FaceCount = f.readUInt() #  facecount/3 
        print("face count = ",FaceCount/3)
        print("VertexCount = ",VertexCount)
        print("\n")

        #can skip following data need to (seek 24,1)
        BBX1 = f.readFloat() 
        BBY1 = f.readFloat()
        BBZ1 = f.readFloat()

        BBX2 = f.readFloat()
        BBY2 = f.readFloat()
        BBZ2 = f.readFloat()

        MatType = f.readString() # read string of unknown size - need to check might need seek -1
   
        Unk1 = f.readFloat()
        Unk2 = f.readFloat()

        f.seek(12,1)

        Vtype = f.readShort() # h read short

        ModelName = noeStrFromBytes(f.readBytes(32), "ASCII") # read string of known size   
        MaterialName = noeStrFromBytes(f.readBytes(514), "ASCII")
    
        for i in range(0,3):
            f.seek(52,1)
   
        FFFF = f.readInt64() #  read long long
        
        BoneCount = f.readUInt()
        MatsCount = f.readUInt()
        f.seek(8,1)
        Unk4 = f.readUInt()

        f.seek(128,1)

        for i in range(0,BoneCount):
            f.seek(84,1)

        for i in range(0,MatsCount):
            f.seek(260,1)
    
        Unk4 = f.readUInt()
        LODCount = f.readUInt()

        PosV = f.tell()
        
        #get weight data
        if Vtype == 4:
            for i in range(VertexCount):

                weights.append([])
                boneids.append([])
                
                f.seek(8,1)
                bone1 = f.readUByte()
                bone2 = f.readUByte()
                bone3 = f.readUByte()
                bone4 = f.readUByte()
                
                weight1 = f.readUByte()
                weight2 = f.readUByte()
                weight3 = f.readUByte()
                weight4 = f.readUByte()
                
                f.seek(16,1)
                
                maxweight = 0

                if weight1 != 0:
                    maxweight = maxweight + weight1
                if weight2 != 0:
                    maxweight = maxweight + weight2
                if weight3 != 0:
                    maxweight = maxweight + weight3
                if weight4 != 0:
                    maxweight = maxweight + weight4
                    
                if maxweight != 0 and weight1 != 0:
                        w1 = float(weight1)
                        boneids[j].append(bone1)
                        weights[j].append(w1/255.0)

                if maxweight != 0 and weight2 != 0 :
                        w2 = float(weight2)
                        boneids[j].append(bone2)
                        weights[j].append(w2/255.0)

                if maxweight != 0 and weight3 != 0:
                        w3 = float(weight3)
                        boneids[j].append(bone3)
                        weights[j].append(w3/255.0)

                if maxweight != 0 and weight4 != 0:
                        w4 = float(weight4)
                        boneids[j].append(bone4)
                        weights[j].append(w4/255.0) 

                        
        if Vtype == 3:

            for i in range(VertexCount):
            
                weights.append([])
                boneids.append([])
                
                f.seek(8,1)
                bone1 = f.readUByte()
                bone2 = f.readUByte()
                
                weight1 = f.readUByte()
                weight2 = 1 - (weight1/255.0)
                #print(weight1)

                
                f.seek(17,1)
                
                maxweight = 0

                if weight1 != 0:
                    maxweight = maxweight + weight1
                if weight2 != 0:
                    maxweight = maxweight + weight2

                    
                if maxweight != 0 and weight1 != 0:
                        w1 = float(weight1)
                        boneids[j].append(bone1)
                        weights[j].append(w1/255.0)

                if maxweight != 0 and weight2 != 0 :
                        w2 = float(weight2)
                        boneids[j].append(bone2)
                        weights[j].append(w2)
                        

     
        # go back to start of vertex block
        f.seek(PosV,0)
        print(Vtype)
        if Vtype == 4:
            VertBuff = f.readBytes(VertexCount * 32)           
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 0) # vertex
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 20) # uv
            #rapi.rpgBindBoneIndexBuffer(VertBuff, noesis.RPGEODATA_INT, 4*boneids[j], weights[j])
            #rapi.rpgBindBoneWeightBuffer(VertBuff, noesis.RPGEODATA_FLOAT, len(weights[j]), weights[j])
        if Vtype == 3:
            VertBuff = f.readBytes(VertexCount * 28)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 28, 0)
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 28, 16)
            #rapi.rpgBindBoneIndexBuffer(VertBuff, noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
            #rapi.rpgBindBoneWeightBuffer(VertBuff, noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)
        
            
        FaceBuff = f.readBytes(FaceCount * 2)

        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertexCount, noesis.RPGEO_POINTS, 1)
        rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FaceCount, noesis.RPGEO_TRIANGLE, 1)


        s += 1
   
   
def noepyLoadModel(data, mdlList):
        ctx = rapi.rpgCreateContext()
        filePath = rapi.getInputName()   # get file path
        #fileExt = filePath.split('.')[-1]  # get file extesion

        skel_data = rapi.loadPairedFile("template - 1", ".anim")
        mesh_data = rapi.loadPairedFile("template - 2", ".rigid_model_v2")
                
        bones = Skeleton(skel_data) # get skeleton data
        Mesh(mesh_data) # get mesh data
        
        mdl = rapi.rpgConstructModel()
        #when i want to load only skeleton
        #mdl = NoeModel()        
        mdl.setBones(bones)
        mdlList.append(mdl)
        
        rapi.rpgClearBufferBinds()
         
        return 1                     
```


i found in a script the following lines to bind verts to bone by i dont understand what goes in every part (1%,2%,3% etc..) :
 rapi.rpgBindBoneIndexBuffer(VertBuff, noesis.RPGEODATA_INT, 1%, 2%)
 rapi.rpgBindBoneWeightBuffer(VertBuff, noesis.RPGEODATA_FLOAT, 3%, 4%)

currently i have boneids[] and coresponding weights[] arrays

thanks in advance for you help

heres a smaple of the .anim file used:
[https://drive.google.com/open?id=1Jm1Ox ... XrgDnLAPOG](https://drive.google.com/open?id=1Jm1Ox-PIiF2HIkaMEjD5P7XrgDnLAPOG)

on the bright side i got my size issue fixed   


Capture.JPG (78.07 KiB) Viewed 1146 times
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-27T08:44:47+00:00
- Post Title: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Fri Sep 27, 2019 3:45 pm at Fri Sep 27, 2019 3:45 pm
>
> 
then loadPairedFile was coming into mind.
worked perfectly thanks for that. 

just one more issue i could some help with,
 bindings the weights to skeleton/mesh - i dont understand the syntax that is needed:

i found in a script the following lines to bind verts to bone by i dont understand what goes in every part (1%,2%,3% etc..) :
 rapi.rpgBindBoneIndexBuffer(VertBuff, noesis.RPGEODATA_INT, 1%, 2%)
 rapi.rpgBindBoneWeightBuffer(VertBuff, noesis.RPGEODATA_FLOAT, 3%, 4%)look at pluginsource\pluginshare.h which comes with Noesis:
void (*rpgBindBoneIndexBuffer)(void *data, rpgeoDataType_e dataType, int stride, int numWeightsPerVert);
void (*rpgBindBoneWeightBuffer)(void *data, rpgeoDataType_e dataType, int stride, int numWeightsPerVert);

(numWeightsPerVert is usually 4, sometimes 3 only)
## Post #13
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-27T11:15:00+00:00
- Post Title: Total War: Warhammer, Noesis script

Thanks a lot i got it working now   

once i get some small bugs sorted out ill post the finished script for anyone who might want to use it
## Post #14
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-28T19:38:41+00:00
- Post Title: Total War: Warhammer, Noesis script

for anyone who is interested
Here is my finished script for Total War: Warhammer II, i have only tested it on 2 different models so i hope it works for the rest

Edit: 
added support to static mesh, due to issue with static mesh and me being to lazy to try to fix it i now load only load mesh without lower res meshes

```
# Based on maxscript by Zaramot
# Thanks for all the help on the xentax fourm 

from os.path import *
from math import *
from inc_noesis import *


def registerNoesisTypes():
    handle = noesis.register("Warhammer Total War 2", ".anim;.rigid_model_v2")    
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #opens debug consle
    #noesis.logPopup()
    return 1


def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    #I preform my check while reading mesh data
    return 1


#load skeleton data
def Skeleton(data):
    bs = NoeBitStream(data, NOE_LITTLEENDIAN)
    bs.seek(12,0)
    SkelNameSize = bs.readShort()   
    SkelName = bs.readString()
    print(SkelName)
    bs.seek(-1,1) # for some reason read string is reading 1 byte extra
    Check = bs.readUInt()
    print(Check)
    
    if Check == 0:
        bs.seek(4,1)
    
    if Check != 0:
        bs.seek(0,1)
    
    BoneCount = bs.readUInt()
    print(BoneCount)
    
    parent_arr = []
    BoneNameArray = []
    
    for i in range(BoneCount):
        BNameSize = bs.readShort()
        BoneName = noeStrFromBytes(bs.readBytes(BNameSize), "ASCII")
        BoneParent = bs.readInt()
        parent_arr.append(BoneParent) 
        BoneNameArray.append(BoneName)
        
 
    BMapArray = []
    bones = []
    
    for i in range(BoneCount):
        BoneId = bs.readUInt() #in maxscript has +1, dont think i need it
        BMapArray.append(BoneId)
        
    #dont think i need this
    for i in range(BoneCount):
        BoneId = bs.readUInt()
        
    if Check == 0:
        bs.seek(8,1)
        
    #dont think i need this, can skip?
    BoneCount1 = bs.readInt()
    BoneCount2 = bs.readInt()    
    Count = bs.readInt()
    
    translation_arr = []
    rotation_arr = []
    Quat = [0]*4
    
    for i in range(BoneCount):
        Tran = NoeVec3.fromBytes(bs.readBytes(12)) 
        translation_arr.append(Tran) 
  
    for i in range(BoneCount): 
        b11 = bs.readShort()
        b12 = bs.readShort()
        b13 = bs.readShort()
        b14 = bs.readShort()
        Rot = NoeQuat((b11,b12,b13,b14))
        Rot = Rot.normalize()
        boneMat = Rot.toMat43(transposed = 1)
        boneMat[3] = translation_arr[i]
        bones.append( NoeBone(i, BoneNameArray[i], boneMat, None, parent_arr[i]) )
        
    # Converting local matrix to world space
    for i in range(0, BoneCount):
        j = bones[i].parentIndex
        #print("j = ", j)
        if j != -1:
            bones[i].setMatrix(bones[i].getMatrix().__mul__(bones[j].getMatrix()))

    return bones


#load mesh data
def Mesh(data):

    f = NoeBitStream(data, NOE_LITTLEENDIAN)
    
    EndPos = len(data)
    
    Magic = noeStrFromBytes(f.readBytes(4), "ASCII")
    print(Magic)
    if Magic != "RMV2":
        print("worng file format")
    
    MeshCount = f.readInt()
    LodCount = f.readInt()

    f.seek(140,0) # seek 0x8c from start of file
    
    for i in range(LodCount):
        f.seek(28,1)
    
    Pos = f.tell()
    
    j = 0
    s = 0
    
    # get vertex, weight, uv data
    while s < (LodCount):

        id = f.readUInt() # read unsigned int 
        LodStart = f.readUInt()
        VertexStart = f.readUInt()
        VertexCount = f.readUInt()
        FaceStart = f.readUInt()
        FaceCount = f.readUInt() #  facecount/3 = number of tris
        print("face count = ",FaceCount/3)
        print("VertexCount = ",VertexCount)

        f.seek(24,1)

        MatType = f.readString() # read string of unknown size 
   
        Unk1 = f.readFloat()
        Unk2 = f.readFloat()

        f.seek(12,1)

        Vtype = f.readShort()

        ModelName = noeStrFromBytes(f.readBytes(32), "ASCII") # read string of known size 
        print("ModelName = ", ModelName)
        PosV = f.tell()
        print("PosV == ", PosV)
        MaterialName = noeStrFromBytes(f.readBytes(510), "ASCII") #should be 514 but noesis has some bug at byte 512 so i skip it with seek instaed
        print("MaterialName = ", MaterialName)
        f.seek(4,1)
    
        for i in range(0,3):
            f.seek(52,1)
   
        FFFF = f.readInt64() #  read long long
        
        BoneCount = f.readUInt()
        MatsCount = f.readUInt()
        f.seek(8,1)
        Unk4 = f.readUInt()

        f.seek(128,1)

        for i in range(0,BoneCount):
            f.seek(84,1)

        for i in range(0,MatsCount):
            f.seek(260,1)
    
        Unk4 = f.readUInt()
        LODCount = f.readUInt()

        PosV = f.tell()
            
        print(Vtype)
        if Vtype == 0:
            VertBuff = f.readBytes(VertexCount * 32)           
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 0) # bind vertex
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 8) # bind uv
            
        if Vtype == 4:
            VertBuff = f.readBytes(VertexCount * 32)           
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 0) # bind vertex
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 20) # bind uv
            #rapi.rpgBindBoneIndexBufferOfs  (Data Buffer, noesis.RPGEODATA_TYPE,siz of each vertex buffer, boneIndex Offset, num_of_weights)            
            rapi.rpgBindBoneIndexBufferOfs  (VertBuff, noesis.RPGEODATA_UBYTE, 32, 8, 4) 
            #rapi.rpgBindBoneWeightBufferOfs (Data Buffer, noesis.RPGEODATA_TYPE, siz of each vertex buffer,boneWeight Offset, num_of_weights)
            rapi.rpgBindBoneWeightBufferOfs (VertBuff, noesis.RPGEODATA_UBYTE, 32, 12, 4)

        if Vtype == 3:
            VertBuff = f.readBytes(VertexCount * 28)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 28, 0)
            rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 28, 16)
            rapi.rpgBindBoneIndexBufferOfs  (VertBuff, noesis.RPGEODATA_UBYTE, 28, 8, 1)
            rapi.rpgBindBoneWeightBufferOfs (VertBuff, noesis.RPGEODATA_UBYTE, 28, 10, 1)
        
            
        FaceBuff = f.readBytes(FaceCount * 2)
        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertexCount, noesis.RPGEO_POINTS, 1)
        rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FaceCount, noesis.RPGEO_TRIANGLE, 1) #bind polygons

        s += 1
   
   
def noepyLoadModel(data, mdlList):
        typecheck = 0
        ctx = rapi.rpgCreateContext()
        
        try:
            skel_data = rapi.loadPairedFile("skel_file- 1", ".anim")
            mesh_data = rapi.loadPairedFile("mesh_file - 2", ".rigid_model_v2")
        except:
            mesh_data = rapi.loadPairedFile("mesh_file - 2", ".rigid_model_v2")
            typecheck = 1
        
        if typecheck == 0:
            bones = Skeleton(skel_data) # get skeleton data
        Mesh(mesh_data) # get mesh data
        
        mdl = rapi.rpgConstructModel()
        #when i want to load only skeleton
        #mdl = NoeModel()
        if typecheck == 0:
            mdl.setBones(bones)
        mdlList.append(mdl)
        
        rapi.rpgClearBufferBinds()
         
        return 1                     
```
## Post #15
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-09T20:31:01+00:00
- Post Title: Total War: Warhammer, Noesis script

Hi,

to continue learning 3d models and noesis i made a script from scratch (not based on anyone's existing scripts) for Total War: Warhammer 1,
figured the structure would be very similar so it wouldn't be very hard and it was (.anim from total war 2 was exactly the same).
** i took a look again to find the differences with tww2 script for . V2 rigid files hoping to find the answer there and apparently they are identical , so basicly i rewrote the same script   , just this time i analyzed the hex data on my own and added texture support **

i do have 1 issue i haven't been able to figure out and was hoping you could point me in the right direction.
as you can  see in the picture my mesh and skeleton are loading misaligned, the skeleton is rotated 180 deg from the mesh,
i tried playing with the quats, randomly adding a (-) sign and got it rotated correctly but then the translation on X axis is slightly off.



rotatedv1.jpg (221.52 KiB) Viewed 1072 times



since i am reading the data from a file i dont understand why i have this mismatch and would appreciate any insight i could get.
here is a link to sample files.
[https://drive.google.com/open?id=1fnZeq ... lf94eOAZ5y](https://drive.google.com/open?id=1fnZequbRurE4up9BO7VIrhlf94eOAZ5y)
the folder also contains my script
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-12T17:49:01+00:00
- Post Title: Re: Noesis script help

> Reply from jayn23 ↑Thu Oct 10, 2019 4:31 am at Thu Oct 10, 2019 4:31 am
>
> as you can  see in the picture my mesh and skeleton are loading misaligned, the skeleton is rotated 180 deg from the mesh,
i tried playing with the quats, randomly adding a (-) sign and got it rotated correctly but then the translation on X axis is slightly off.Why not leave the skeleton as is and rotate or mirror the mesh instead? (Not sure whether this will make a difference but you never know...  )
## Post #17
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-12T17:58:48+00:00
- Post Title: Re: Noesis script help

That was my first thought as well (before i know the x axis is also misaligned)
but to be honest i dont really know how to do that , if i could i would just add a (-) to all x coordinate of each vert.
but since is all loaded with " rapi.rpgBindPositionBufferOfs" i dont know how manipulate the data

how would i mirror the mesh? that might work
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-12T19:22:08+00:00
- Post Title: Re: Noesis script help

yeah, forgot that it's Noesis.  
Treating mesh and skeleton separated? (just for a test, of course, whether it cures the misalignment.)
Exported as smd, cut of the mesh.
Exported as obj, x-mirrored in blender for example. Exported as smd and adding the mesh(es) to the skeleton data.
(yeah, horrible workaround, but that's me.  )

btw:

> Reply from jayn23 ↑Thu Oct 10, 2019 4:31 am at Thu Oct 10, 2019 4:31 am
>
> randomly adding a (-) signwhich one was it?
(Rot = NoeQuat((-b11,-b12,b13,b14)))
.
well, forget what I said...  
.



blender G Z 1.png (239.59 KiB) Viewed 293 times


Imported skel and mesh to blender, rotated skel x -90°(iirc)
transformed mesh z 1
nearly fits
## Post #19
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-12T19:46:57+00:00
- Post Title: Re: Noesis script help

> Rot = NoeQuat((-b11,-b12,b13,b14))
actually this is what gave me the rotated skeleton adding (-) to b11 and b12, and yes i checked nearly every combination possible until i found this just hopeful thinking   

i exported the mesh + skeleton as FBX , imported to 3dsmax deleted the skin and mirrored the mesh, sadly i still have the same misalignment, since it seems to be the same size misalignment for all meshes, if i could manipulate the data i could probably just estimate the correct position and change all vertex coordinate accordingly (for example x - 0.13).

but that's to much of a hassle so i think ill just live with it as is 
thanks for all the help

ok seems that i was mistaken to my eye they looked the same but now when i checked the misalignment is not exactly the same for all meshes (close but not the same) so scratch this idea...

i updated my first post with the finished script - added support for loading all textures as long as they are in the same directory
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-17T20:08:54+00:00
- Post Title: Re: Noesis script help

Hi jayn23,
how is it going? Had a look at your script and guess you'll try out anims sooner or later.
Don't have the time for some research but here's how you can easily test your weightings in Noesis (in case you didn't know):

```
            mdl.setBones(bones)
        #this is an example of how to use procedural animations to test your weighting
        panims = [NoeProceduralAnim("wing_right_0", -30.0, 1, 0.1), NoeProceduralAnim("wing_left_0", 30.0, 1, 0.1)]
        anims = rapi.createProceduralAnim(bones, panims, 100)
        mdl.setAnims(anims)
        mdlList.append(mdl)

```




DragonFly.png (38.71 KiB) Viewed 280 times
## Post #21
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-17T22:37:10+00:00
- Post Title: Re: Noesis script help

Hi shakotay2,

Thanks alot this is pretty cool   
yeah i want to start with animation but there are far less examples on the forum with working animation script - still looking for an easy to understand one  

last few days i got distracted trying to analyze a very old game i was interested in the past Forgotten Realms: Demon Stone just finished my noesis script for it an hour ago just mesh,uv and normals cant figure out anything else at the moment...

if you happen to think of working script with animation with a easy to understand format or can refer me to a tutorial somewhere that would be awesome.

Edit:
found this topic
[viewtopic.php?f=16&t=11776&hilit=animation](https://forum.xentax.com/viewtopic.php?f=16&t=11776&hilit=animation) - i am going to try and recreate it in noesis as soon as  i have some spare time

Thanks again for this,
## Post #22
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2019-10-18T14:43:51+00:00
- Post Title: Re: Noesis script help

Hi shakotay2 and jayn23,
Two of you save me a lot of time since what I am facing is definitely resolved in this post (although my models are from another game). I think I will come back to research model after 1 hopeless week.
Thanks and nice weekend.
## Post #23
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-19T21:00:59+00:00
- Post Title: Re: Noesis script help

> Hi shakotay2 and jayn23,
>
> Two of you save me a lot of time since what I am facing is definitely resolved in this post (although my models are from another game). I think I will come back to research model after 1 hopeless week.
>
> Thanks and nice weekend.

I am happy you found this thread helpful
## Post #24
- Username: Morgengrat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 24, 2019 3:08 pm
- Post datetime: 2019-12-26T23:52:52+00:00
- Post Title: Re: Noesis script help

Thank you for your hard work for making those scripts! 
As someone who never worked with models or 3D im a bit confused about how to make those work. 
Basically, I have 3DMax 2013 and trying to import Buildings from WH2 to it. The thing is, I don't even know where to place the script, and what exact files should be imported from WH2 folder to 3Dmax. Could anyone link a guide or give a small tutorial for those like me, please?
## Post #25
- Username: Zeratul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 23, 2019 7:22 pm
- Post datetime: 2020-01-13T16:20:31+00:00
- Post Title: Re: Noesis script help

> Reply from jayn23 ↑Fri Oct 18, 2019 6:37 am at Fri Oct 18, 2019 6:37 am
>
> 
Hi shakotay2,

Thanks alot this is pretty cool   
yeah i want to start with animation but there are far less examples on the forum with working animation script - still looking for an easy to understand one  

last few days i got distracted trying to analyze a very old game i was interested in the past Forgotten Realms: Demon Stone just finished my noesis script for it an hour ago just mesh,uv and normals cant figure out anything else at the moment...

if you happen to think of working script with animation with a easy to understand format or can refer me to a tutorial somewhere that would be awesome.

Edit:
found this topic
viewtopic.php?f=16&t=11776&hilit=animation - i am going to try and recreate it in noesis as soon as  i have some spare time

Thanks again for this,

Did you get a chance to look at the animations? I have to confess my skills are very poor in coding and reading codes, all I have to base my knowledge on are a few macros and VB scripts that I used in excel and some knowledge in SQL...

I honestly haven't gotten to the level of trying to decode the hexfiles for the animations, or read the data from them and trying to identify the patterns...but I was lucky enough to stumble upon a source that contains some of the animation files converted to DAE format, which I could then read a bit and try to understand the structure from...

I went on a bit trying to compare the info I found in those files and the skeleton files, trying to get the info for the frames from them, in order to try and find a way to scripting this data into keyframes through a noesis script or max script....but then I gave up after a while cause I got consumed in work 

I have some free time up again, and I'm getting back into looking at it, but if you have any information that might help please let me know
## Post #26
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-01-13T18:53:38+00:00
- Post Title: Re: Noesis script help

To be honest i didnt try to figure out the animations for this game, but since working on this script i have gotten a bit more experience with animation from games i tried working on.

> I was lucky enough to stumble upon a source that contains some of the animation files converted to DAE format, which I could then read a bit and try to understand the structure from.
if your interested in help post the source and DAE files here and i can try to help  
it would be awesome if i could make this script complete with animation support
## Post #27
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2020-01-14T02:56:20+00:00
- Post Title: Re: Noesis script help

If you guys need an example for the animation formats I have a maxscript you can look at for your noesis script. Out of curiosity I'd also like to see the source of the dae files.

 Total Warhammer Scripts.zip
(7.26 KiB) Downloaded 52 times
## Post #28
- Username: Zeratul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 23, 2019 7:22 pm
- Post datetime: 2020-01-14T06:14:12+00:00
- Post Title: Re: Noesis script help

Sure, I found them as I was looking for an answer into the animations, and found this link in the forums which lead me to it, it contains tons of models and converted assets:

Hey man, here's the source I found:
[https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ](https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ)

found it while looking in this post:
[viewtopic.php?t=18795&start=15](https://forum.xentax.com/viewtopic.php?t=18795&start=15)

All credit goes to:
09williamsad
[memberlist.php?mode=viewprofile&u=55016](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=55016)
## Post #29
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-01-14T10:44:55+00:00
- Post Title: Re: Noesis script help

> Reply from killercracker ↑Tue Jan 14, 2020 10:56 am at Tue Jan 14, 2020 10:56 am
>
> 
If you guys need an example for the animation formats I have a maxscript you can look at for your noesis script. Out of curiosity I'd also like to see the source of the dae files.Total Warhammer Scripts.zip

killercracker, Thanks  for the script, i am sure it will be a great help
your script for Perfect world animation(stck) and help from shakotay were my first introduction to animation in general so thanks for that as well   

> Sure, I found them as I was looking for an answer into the animations, and found this link in the forums which lead me to it, it contains tons of models and converted assets:
>
> 
>
> Hey man, here's the source I found:
>
> https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ
>
> 
>
> found it while looking in this post:
>
> viewtopic.php?t=18795&start=15

thanks for the links ill take a look at them when i get home from work.
## Post #30
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-01-16T21:26:23+00:00
- Post Title: Re: Noesis script help

Just a small update:

Thanks to the maxscript it has been very easy to understand the format, and write a script.
unfortunately i am having problems with the noesis script not showing the animation correctly - not sure what i am doing wrong but if i cant figure it out in the next few days ill post what i have and hope for some help
## Post #31
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-01-18T21:55:08+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

I finally got it working   
took me quite a while, i was trying the use key-framed animation that didnt work, then i found there is a framed option,
then i found that my translation were wrong, all in all took me a long time to figure it out but i am pretty happy now lol 

here is the script with support for textures, skeleton and animation and static mesh -- animation has only been tested with 1 rig so if any issues are found please let me know and i will try to fix them.

Edit:
Script is updated to support another type of animation found thanks so some users who managed to test dozens of them and point out what wasnt working 


 fmt_WarhammerTotalWarV3.rar
(3.58 KiB) Downloaded 205 times
## Post #32
- Username: Zeratul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 23, 2019 7:22 pm
- Post datetime: 2020-01-21T19:29:15+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Wow....good job man, I haven't been able to check it yet, but I'm getting back home tomorrow and will check it out...

I have been scratching my head for months and you guys just came to the rescue...thanks for all the efforts
## Post #33
- Username: Julcab
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 03, 2020 5:15 am
- Post datetime: 2020-02-02T21:25:41+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Thanks! I'm currently embarked on a project of mirroring models and creating Lizardmen into the old WC3 game, as a custom game within (old, physical copy)
Your script is unvaluable to me! Greetings from Spain!
## Post #34
- Username: Julcab
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 03, 2020 5:15 am
- Post datetime: 2020-02-02T21:30:10+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Unfortunately it seems like it cannot be downloaded somehow...
## Post #35
- Username: Julcab
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 03, 2020 5:15 am
- Post datetime: 2020-02-02T21:31:39+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

> Reply from Julcab ↑Mon Feb 03, 2020 5:30 am at Mon Feb 03, 2020 5:30 am
>
> 
Unfortunately it seems like it cannot be downloaded somehow...

Actually, I meant that I could download it, but couldn't extract it
## Post #36
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-03T09:11:05+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

> Actually, I meant that I could download it, but couldn't extract it

i dont really understand what the problem is? if you are getting some error please post it
## Post #37
- Username: Drawnin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 07, 2020 4:36 pm
- Post datetime: 2020-02-07T09:52:03+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

I got it working, but how can we separate lods to export? I exported a model to FBX, and it works... but all lods are in the same 3D object and they're hard to separate manually...
## Post #38
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2020-02-08T17:35:19+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Amazing work man, amazing script, but sadly the script don't separate the lods from the meshes, if you can update this, the script will be perfect 10\10
## Post #39
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-09T00:04:04+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

> I got it working, but how can we separate lods to export? I exported a model to FBX, and it works... but all lods are in the same 3D object and they're hard to separate manually...

> Amazing work man, amazing script, but sadly the script don't separate the lods from the meshes, if you can update this, the script will be perfect 10\10

Thanks 

i dont remember why i didnt separate them originally  , i am guessing i didnt know how to distinguish from lod to a different mesh stored in the 
file but i will take a look again and see if i can figure something out

edit:
added a link to a only mesh script, it loads first mesh, than first + second etc.. so you can export only then mesh you need without the lods
[fmt_WarhammerTotalWar - no skin.rar](https://xentaxbackup.github.io/file/17480_fmt_WarhammerTotalWar - no skin.rar)
## Post #40
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-09T22:25:30+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Ok so i came up with an easy solution, hope this works for you,
i made it so it loads first mesh, then 1 and 2 etc..
so if you only need the first 3 mesh's then you simply scroll to third option (as seen in gif below) and then export from preview, i know its not perfect but it a hell of a lot better 
than manually separating the lods from other meshs  

animations work only for Total War: Warhammer 2

[fmt_WarhammerTotalWarV4.rar](https://xentaxbackup.github.io/file/17479_fmt_WarhammerTotalWarV4.rar)
## Post #41
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2020-02-09T23:22:29+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Thanks Alot man, it work perfectly
## Post #42
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-10T12:32:41+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Hi, I haven't been able to successfully export Weapons and props from Warhammer 2. I found the py script that was supposed to work but when I open the FBX with blender I get was seems like an almost empty file :/

Any help would be appreciated
## Post #43
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-10T12:57:38+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

> Reply from tasanhalas ↑Mon Feb 10, 2020 8:32 pm at Mon Feb 10, 2020 8:32 pm
>
> 
Hi, I haven't been able to successfully export Weapons and props from Warhammer 2. I found the py script that was supposed to work but when I open the FBX with blender I get was seems like an almost empty file :/

Any help would be appreciated

Jayn23 just a post above attached NO SKIN script, you could use it for any static model. Though, here are your weapons - exported using same NO SKIN plugin, just try it and you will have what you may need in a future.
[weapons.7z](https://xentaxbackup.github.io/file/17481_weapons.7z)
## Post #44
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-03-17T17:47:16+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Hi!
May I asking someone for priests (knights) and dragons models?
Especially priests/
Thanks!
## Post #45
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-18T08:24:36+00:00
- Post Title: Re: Total War: Warhammer, Noesis script help

Hi all. First thanks a lot, this script work fine in a lot of situation, but i hit one, where it has problems:
I am trying to export Grombrindal, and appears it has no body. But i am sure that there is body in original mesh.

```
 dwf_grombrindal_body            variantmeshes/wh_variantmodels/hu3/dwf/dwf_grombrindal/tex/
```
## Post #46
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-18T08:37:06+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hi,

If i had to guess this looks like a texturing issue ,
Try loading without textures (make sure no textures are in folder)
if that does not work upload sample
## Post #47
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-18T08:45:50+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

I opened it in blender, and i see veird results, but still no body part:

And without texture it looks the same.
I attached exported fbx. Thank you for help
## Post #48
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-18T08:54:35+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

I dont see any attachment, but any way  i would need the original file, not exported FBX in order to t/s

Edit:
by the way is this from Total warhammer 1 or  2?
because animation was tested only on Total warhammer 2, try loading without animation as well
## Post #49
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-18T08:58:42+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Oh sorry, it was to big, and i did notice warning
[Here link](https://drive.google.com/open?id=1JuMgkjEC2nBE-JY1he8mYwAZ8fN0arFo) to my google drive, a added there original file with textures and animations. It is warhammer 2.
## Post #50
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-18T11:08:52+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Well it really was not loading all meshes, there is a inconsistency between meshes for static and skinned so i set it to load the smaller number of meshes (LOD vs Meshcount) which always worked until this sample.

in order to solve this is i added a attribute called "DEBUG = 0"  in line 10 of the code, when its set to 0 it will load minimum mesh count which works for static and most of the time skinned mesh.
if you think (like in this case you are missing meshes) change code to  "DEBUG = 1", and it will load according to mesh count.



I also made some QoL changes to code:
1. first you double click on mesh file only (1 less click than before), then asked to choose skeleton file and the then animation.
you can cancel after mesh and you will get only mesh, cancel when animation is requested and get mesh with skeleton or load all three.

2. Since last time i posted my script i learned how to  load each mesh seperatly with a uniqe name, so now in order to allow you to choose high poly mesh without LOD i made it so all meshes are loaded but each has its own name and can very easily be deselected in noesis or any other program.


[fmt_WarhammerTotalWarFinale.rar](https://xentaxbackup.github.io/file/18162_fmt_WarhammerTotalWarFinale.rar)
## Post #51
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-18T11:37:55+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Wow, thank you a lot. It works.
Also i wonder what is workflow for models stored in few different files.
## Post #52
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-22T11:06:09+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hi jayn23, i have one question.
There are few bones in sceleton, called be_prop_[n], they are placeholders for weapons and other stuff, that can be attached to model, and as i understand script dosn't put them into right place, can you check it please
## Post #53
- Username: Slava
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 06, 2020 6:37 am
- Post datetime: 2020-05-22T16:51:10+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Excuse me, dear sir!
But how can I correct python script to open *.rigid_model_v2 from total war saga, because now it has an error. 
Apparently due to an attempt to load textures.
The error itself - 
Do you have any ideas how to remove tex call from script?
Thanks in advance!
## Post #54
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-23T19:38:35+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> There are few bones in sceleton, called be_prop_[n], they are placeholders for weapons and other stuff, that can be attached to model, and as i understand script dosn't put them into right place, can you check it please

Hi, sorry but what you are asking for isn't in the scope of the script, if  weapons  model was included in the file i could easily do it, but if you are loading a  weapon mesh there is no way for me or the script to know what you are loading and to which prop_[n] bone to attach to, this is handled by game engine and game scripts.
on the bright side what you are asking to do is very easily achieved, in 3ds max you would just load the weapon mesh add a skin modifier and bind all vertex to the wanted prop_[n] bone  and done!!!.

> Excuse me, dear sir!
>
> But how can I correct python script to open *.rigid_model_v2 from total war saga, because now it has an error.
>
> Apparently due to an attempt to load textures.

Please upload a sample file, so i can look - i dont think its texture related.
## Post #55
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-23T20:53:40+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Hi, sorry but what you are asking for isn't in the scope of the script, if weapons model was included in the file i could easily do it, but if you are loading a weapon mesh there is no way for me or the script to know what you are loading and to which prop_[n] bone to attach to, this is handled by game engine and game scripts.
>
> on the bright side what you are asking to do is very easily achieved, in 3ds max you would just load the weapon mesh add a skin modifier and bind all vertex to the wanted prop_[n] bone and done!!!.
I mean different thing, I am not asking to add weapon to the model. I just suspect that prop bones located in wrong places. In all models I extracted they were located beneath all skeleton, all weapons attached to prop_1 or prop_2, and I expect them to be near model hands, but they are not there. Probably it is the way it should be, but I really doubt.
I attach screenshot:

As you can see:
a.Those bones not connected to anything except animroot
b.They located in strange place

Just in case, [link to model](https://drive.google.com/open?id=12OiAgrsBXnPspj5r_couQQIpRS00KD1i)
## Post #56
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-23T21:48:54+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

I have a very limited supply of samples, but i took a look at them,

You are a probably right about prop[n] bones being attachment for weapons since centaur had them but griffin and dragon did not. 
i took a look at attack animation for centaur and prop bones were moving in a way that seems correct for a weapon, what i am saying is it dosent matter where the bone is located as long as the animation is moving it correctly.

try using an attack animation and see how the bones move
## Post #57
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-05-23T22:27:42+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

I checked [other model](https://drive.google.com/open?id=1EljLgG-TaHctnJtzvGGVNv7nllC2OoUo): 

And it works perfectly, axe works great with all animation, and compared to mazdamundi all prop bones has child, called be_prop_[n]_end

And one more addition, all models i exported with this script, are mirrored against x
## Post #58
- Username: Slava
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 06, 2020 6:37 am
- Post datetime: 2020-05-23T23:35:15+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Excuse me, dear sir!
>
> But how can I correct python script to open *.rigid_model_v2 from total war saga, because now it has an error.
>
> Apparently due to an attempt to load textures.
>
> 
>
> Please upload a sample file, so i can look - i dont think its texture related.

Thank you!
FILE: [http://www.mediafire.com/file/ql3jp3k7j ... 1.zip/file](http://www.mediafire.com/file/ql3jp3k7jb8xgrq/vik_shield_clonoura_01.zip/file)
## Post #59
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-24T19:14:29+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Thank you!
>
> FILE: http://www.mediafire.com/file/ql3jp3k7j ... 1.zip/file

heres a modified script that opens your sample, i missed the fact that its from total war saga and not warhammer,
i suggest you open a new thread for that game here.

Formats are very slimier but still different so one script wont work for both and  it will just be confusing here.

> And one more addition, all models i exported with this script, are mirrored against x
probably right hand vs left hand cord system, i googled how to swap from cords but when i applied the swap it worked for skeleton it also changed the up direction of the skeleton making it incompatible  with the mesh.

i am not going to put any more time in to this sorry, just dont think its important enough.
[fmt_TotalWarSaga - no skin.rar](https://xentaxbackup.github.io/file/18205_fmt_TotalWarSaga - no skin.rar)
## Post #60
- Username: Slava
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 06, 2020 6:37 am
- Post datetime: 2020-05-24T19:36:58+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Mon May 25, 2020 3:14 am at Mon May 25, 2020 3:14 am
>
> 
heres a modified script that opens your sample, i missed the fact that its from total war saga and not warhammer,
i suggest you open a new thread for that game here.
Formats are very slimier but still different so one script wont work for both and  it will just be confusing here.

All is work perfectly!
Amazingly, you fixed it so fast! You are a true master of scripting! I am very grateful to you for your help! And I sincerely wish you and family health up to the 5th generation!
## Post #61
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-06-01T12:47:43+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hi, i still have problems with some animations:
As i understand in this game they have some "docking system", it is something like additional animations, that adds some extra anmations to existing one. I [attach example](https://drive.google.com/drive/folders/12OiAgrsBXnPspj5r_couQQIpRS00KD1i?usp=sharing).
I tryed to convert it with noesis script, but it seems like it plays some animation, but nothing happenes.
And it is not only skeleton with succh issues, for example all [humanoid01](https://drive.google.com/drive/folders/1PHlyBYw_KkhMdwdRWNtykOXigx_86Kxv?usp=sharing) has same system. As i understand this additional "docking" used to change finger grip for weapons. Any ideas, how to convert this additional animation?
## Post #62
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-02T18:43:04+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Hi, i still have problems with some animations:
>
> As i understand in this game they have some "docking system", it is something like additional animations, that adds some extra anmations to existing one. I attach example.
>
> I tryed to convert it with noesis script, but it seems like it plays some animation, but nothing happenes.
>
> And it is not only skeleton with succh issues, for example all humanoid01 has same system. As i understand this additional "docking" used to change finger grip for weapons. Any ideas, how to convert this additional animation?

i dont know anything about this but i will try to take a look once i am done with current project i am working on, i am pretty close to the finish line so hopefully it wont be long .
## Post #63
- Username: Angmarec
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 16, 2020 7:18 pm
- Post datetime: 2020-06-02T18:46:01+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> i dont know anything about this but i will try to take a look once i am done with current project i am working on, i am pretty close to the finish line so hopefully it wont be long .
Thank you so much for help, no rush, good luck with your project. 

And additional small question: i tryed to export few buildings, and rebuild some prefabs, and it came out that after conversion models have different pivot point(now it is in geometrical center of the model). And when i used coordinates from prefab files, they don't match, this is Noesis specific issue, or export script has such functionality?
Original (from Terry CA map editor):

After conversion:
## Post #64
- Username: mnan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 12, 2020 2:06 am
- Post datetime: 2020-10-24T09:00:46+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hi everyone!

Complete novice here, but I'm trying my hand at Noesis to fiddle with TWH2 files.
This script is a godsend, of course, but I was thinking:

since there's a lot of multi-part models in TWH2, is there a way to load multiple meshes on a single skeleton, and export the whole thing as a single mesh+skeleton directly from Noesis? Or is that a thing that I do with the exported fbx files on another software?
## Post #65
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-25T11:40:44+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> since there's a lot of multi-part models in TWH2, is there a way to load multiple meshes on a single skeleton, and export the whole thing as a single mesh+skeleton directly from Noesis? Or is that a thing that I do with the exported fbx files on another software?

Try this:
Answer given by  Joschka on my gr2 thread

> Depending on how the script is made you may want to try this : https://github.com/RoadTrain/noesis-plu ... elmerge.py
>
> 
>
> Put it in the plugins folder
>
> Then right click on the file and choose merge
>
> It'll load all the files with the same extension that are next to it
>
> Check the bone merging options in the script to avoid having duplicates if relevant

I guess i could add this eventually (need to add it to my gr2 script as well) but i have so little free time lately i rather spend it playing or watching TV shows, i haven't opened visual studio in over 2 months but i will sooner or later
## Post #66
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2020-12-27T08:14:26+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Mon May 18, 2020 7:08 pm at Mon May 18, 2020 7:08 pm
>
> 
Well it really was not loading all meshes, there is a inconsistency between meshes for static and skinned so i set it to load the smaller number of meshes (LOD vs Meshcount) which always worked until this sample.

in order to solve this is i added a attribute called "DEBUG = 0"  in line 10 of the code, when its set to 0 it will load minimum mesh count which works for static and most of the time skinned mesh.
if you think (like in this case you are missing meshes) change code to  "DEBUG = 1", and it will load according to mesh count.



I also made some QoL changes to code:
1. first you double click on mesh file only (1 less click than before), then asked to choose skeleton file and the then animation.
you can cancel after mesh and you will get only mesh, cancel when animation is requested and get mesh with skeleton or load all three.

2. Since last time i posted my script i learned how to  load each mesh seperatly with a uniqe name, so now in order to allow you to choose high poly mesh without LOD i made it so all meshes are loaded but each has its own name and can very easily be deselected in noesis or any other program.
Hey how can I open multiple files, I only can open part of the model, like only body or head sepratly, how can I open lets say full centigor model head and body weapons etc in noesis ? and thanks alot for this script !
## Post #67
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-12-27T21:53:03+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

using the current noesis script you cant load multiple files.
you can try using method i already linked above which allows to combine multiple meshes and skeleton, not sure about animations..
i dont have planes to add support for this in my noesis script currently.
## Post #68
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2020-12-28T14:24:37+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

understandable, you already did enough in this amazing script. thanks alot !
## Post #69
- Username: mnan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 12, 2020 2:06 am
- Post datetime: 2021-01-30T12:08:15+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Mon Dec 28, 2020 5:53 am at Mon Dec 28, 2020 5:53 am
>
> 
using the current noesis script you cant load multiple files.
you can try using method i already linked above which allows to combine multiple meshes and skeleton, not sure about animations..
i dont have planes to add support for this in my noesis script currently.

It actually works pretty well with both skeletons AND animations.
It loads and attach every iteration of the .anim files to the mesh, though, so while you are "assembling" the mesh by opening (in order)
1- the skeleton file 
2- the mesh file
3- the animation file
remember to only load the skeleton .anim and the animation .anim files with the first mesh, and cancel the others, otherwise you will find yourself with a .fbx with three skeletons in it. If you only do it once, the whole mesh will be linked to the single skeleton loaded.
So you will have to go like this:
RIGHT CLICK ON THE FIRST MESH FILE IN NOESIS AND SELECT MODEL MERGER
OPEN SKELETON 1
OPEN MESH 1
OPEN ANIMATION 1
SKIP SKELETON 2
OPEN MESH 2
SKIP ANIMATION 2
[...]

The only thing is that the file merger will only load one "version" of the model and no sub-models, so you can't cycle between sub-models. It's not that much of an issue in general, but with some models the only sub-models that is loaded is a pretty partial one (like, I dunno, Grimgor, whose first submodel is just a head, with the other two being different poly-counts of the whole body).
## Post #70
- Username: mnan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 12, 2020 2:06 am
- Post datetime: 2022-02-18T19:40:33+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

AAAAAAAAlright, who's gonna fiddle with the TWW2 script to make it work with TWW3?
## Post #71
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-02-21T16:19:50+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from mnan ↑Sat Feb 19, 2022 3:40 am at Sat Feb 19, 2022 3:40 am
>
> 
AAAAAAAAlright, who's gonna fiddle with the TWW2 script to make it work with TWW3?

I tool a look at samples posted on the other post, so far i have figured out the skeleton format - no major changes there,
Still havent figured out the mesh format - i am kinda rusty not doing any RE for the past 8 months or so but ill figure it out...

can you please post 2-3 samples of models with animations and textures - so i can check everything is working correctly.
## Post #72
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-02-21T17:04:24+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Tue Feb 22, 2022 12:19 am at Tue Feb 22, 2022 12:19 am
>
> 
can you please post 2-3 samples of models with animations and textures - so i can check everything is working correctly.
Animation and models with textures added to my sample link.
[https://mega.nz/folder/7GxkBT4K#UcK6KQlduUnOplekkr0vWA](https://mega.nz/folder/7GxkBT4K#UcK6KQlduUnOplekkr0vWA)
## Post #73
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-02-28T19:47:35+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

As promised a updated script supporting Total War: Warhammer III (in addition to I + II),

Currently new mesh and skeleton formats are supported, many of the models and animations are in the old format and will still load, if you try loading an aniamtion from new version nothing will happen  -  in debug console in will say that aniamtion version is unsupported.

Huge thanks to zaramot, i was having distorted mesh issues with the new format and he helped me out.

very little testing has been done so please report any issues you might encounter. 


[fmt_WarhammerTotalWar_III.rar](https://xentaxbackup.github.io/file/21865_fmt_WarhammerTotalWar_III.rar)
## Post #74
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-03-01T17:35:37+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Outstanding!  Testing now
## Post #75
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-03T20:04:58+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Done some batch testing of the new noesis script with Total War Warhammer 3.
In the attached zip is a list of the models that did not output a fbx and a index for determing skeleton based on model path.
2637 of the 18221 models did not convert, mostly vfx, rigid models and terrain.
[TWW3 Skeleton index and models that did not convert.zip](https://xentaxbackup.github.io/file/21874_TWW3 Skeleton index and models that did not convert.zip)
## Post #76
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-04T20:12:33+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Converted and raw models for Total War Warhammer 3 now in my archive.
I am not allowed to post it here, but if you google my username you should find it
## Post #77
- Username: Ragnarr1313
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 07, 2022 9:11 pm
- Post datetime: 2022-03-07T13:45:51+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Has anyone been able to get the script to work with the flesh hounds? I seem to be able to get the other Khorne Daemons, but only one of the heads for the flesh hounds looks correct. all the other heads and bodies all look like they are jagged crystal like things.
## Post #78
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-03-07T20:21:22+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from Ragnarr1313 ↑Mon Mar 07, 2022 9:45 pm at Mon Mar 07, 2022 9:45 pm
>
> 
Has anyone been able to get the script to work with the flesh hounds? I seem to be able to get the other Khorne Daemons, but only one of the heads for the flesh hounds looks correct. all the other heads and bodies all look like they are jagged crystal like things.

Post samples i will take a look
## Post #79
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-07T20:29:30+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Tue Mar 08, 2022 4:21 am at Tue Mar 08, 2022 4:21 am
>
> 
Post samples i will take a look
Was curious, so I took a look.
For the flesh hound, the geometry seems to have collapsed inwards.

[dae_fleshhound - bc4.7z](https://xentaxbackup.github.io/file/21899_dae_fleshhound - bc4.7z)
## Post #80
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-03-07T20:47:40+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Well the fix is pretty easy,
for some reason the file header is of a version 7 (warhammer total war II format ) while the actual mesh format is 
version 8 (warhammer total war III).





Edit:
Here is an updated script - with a workaround that should work for all models.
it would be great if you could check both Total War II and Total War III - to make sure my changes didnt ruin support for older games
[fmt_WarhammerTotalWar_III.rar](https://xentaxbackup.github.io/file/21900_fmt_WarhammerTotalWar_III.rar)
## Post #81
- Username: mnan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 12, 2020 2:06 am
- Post datetime: 2022-03-08T16:01:26+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Tue Mar 08, 2022 4:47 am at Tue Mar 08, 2022 4:47 am
>
> 
it would be great if you could check both Total War II and Total War III - to make sure my changes didnt ruin support for older games

Doesn't TWWIII contain everything that was in TWII anyway?
## Post #82
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-03-08T21:39:04+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from mnan ↑Wed Mar 09, 2022 12:01 am at Wed Mar 09, 2022 12:01 am
>
> 
Doesn't TWWIII contain everything that was in TWII anyway?

Well i dont know about everything but it does have alot of TWWII meshes/animations - i changed something based on a educated assumation without much testing, thats why i was hoping for more testing.
## Post #83
- Username: Ragnarr1313
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 07, 2022 9:11 pm
- Post datetime: 2022-03-09T05:01:31+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from jayn23 ↑Tue Mar 08, 2022 4:47 am at Tue Mar 08, 2022 4:47 am
>
> 
Well the fix is pretty easy,
for some reason the file header is of a version 7 (warhammer total war II format ) while the actual mesh format is 
version 8 (warhammer total war III).





Edit:
Here is an updated script - with a workaround that should work for all models.
it would be great if you could check both Total War II and Total War III - to make sure my changes didnt ruin support for older games


Great, thank you. 

Ignore the last message, I figured out what I was doing wrong. lol. 

Thanks again.
## Post #84
- Username: Adam69420
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 24, 2022 3:37 am
- Post datetime: 2022-03-30T14:41:55+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

hi, is there a complete plugin? if yes can u please reupload it
## Post #85
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2022-04-01T06:41:42+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Is the Warhammer 3 anims still going to be worked on for future versions of the script?
## Post #86
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-05-28T18:44:28+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from CairnTrenz ↑Fri Apr 01, 2022 2:41 pm at Fri Apr 01, 2022 2:41 pm
>
> 
Is the Warhammer 3 anims still going to be worked on for future versions of the script?

Sorry i am not working on animation at the moment,
## Post #87
- Username: Disinformed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 15, 2022 1:50 am
- Post datetime: 2022-06-14T19:07:20+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Apologies up front for being new to this. I'm just looking for some clarification as to what's the proper workflow for using V4 of the script (in WH2). When I double-click an .anim file in Noesis it prompts me to 1) select a .anim file for the skeleton (I might be starting off wrong right here - is it looking for just any .anim file that uses the skeleton, or is there a base skeletal definition .anim file I'm unaware of that it wants?), 2) Select a static mesh file (this seems straightforward, no?), and 3) Select a .anim file again. I'm not sure what it's looking for in each of the 2 distinct .anim requests. Can anyone clarify? 

Specific example: I'm working on Alastair. I'm first selecting "hu1c_2ha_attack_01.anim", a 2H Axe animation, then "hef_alastair_01.rigid_model_v2". After this, on the second .anim request, I have tried selecting "hu1c_2ha_attack_01.anim" again along with several others, and am getting gyrating vertex salad. (I *feel* like I'm missing a basic skeleton reference, but don't know what it would be called or where to find it in the .pack files.)

Thanks!
## Post #88
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2022-06-19T17:26:01+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from Disinformed ↑Wed Jun 15, 2022 3:07 am at Wed Jun 15, 2022 3:07 am
>
> 
Apologies up front for being new to this. I'm just looking for some clarification as to what's the proper workflow for using V4 of the script (in WH2). When I double-click an .anim file in Noesis it prompts me to 1) select a .anim file for the skeleton (I might be starting off wrong right here - is it looking for just any .anim file that uses the skeleton, or is there a base skeletal definition .anim file I'm unaware of that it wants?), 2) Select a static mesh file (this seems straightforward, no?), and 3) Select a .anim file again. I'm not sure what it's looking for in each of the 2 distinct .anim requests. Can anyone clarify? 

Specific example: I'm working on Alastair. I'm first selecting "hu1c_2ha_attack_01.anim", a 2H Axe animation, then "hef_alastair_01.rigid_model_v2". After this, on the second .anim request, I have tried selecting "hu1c_2ha_attack_01.anim" again along with several others, and am getting gyrating vertex salad. (I *feel* like I'm missing a basic skeleton reference, but don't know what it would be called or where to find it in the .pack files.)

Thanks!

This is the process that has worked well for se so far:
1. in noesis, select the .rigid_model_v2 for Alastair, not the anim file (why would you ever start with the animation?)
2. now select the proper skeleton .anim file, in this case sounds like it will be the standard hu1c skeleton
3. now to apply the animation, select hu1c_2ha_attack_01.anim on the second file query

However, WH3 animations dont seem to be supported right now and are not actively worked on if I understand correctly. Just cancel the last file input for now.

Most important of all, in order to not get spikey vertex explosions you need to make sure the old script is not in the noesis python folder anymore, only the newest one! Delete the old stuff.
## Post #89
- Username: kaiguy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 19, 2022 6:51 pm
- Post datetime: 2022-07-19T11:08:34+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hey all! I'm equally new to this and I'm running into an issue when trying to export modded meshes. Every time I attempt (regardless of what meager changes in Python I can muster), this happens:

Traceback (most recent call last):
  File "Noesis\plugins\python\fmt_WarhammerTotalWar_III.py", line 433, in noepyLoadModel
    texList, matList = Mesh(data, mdlList)
  File "Noesis\plugins\python\fmt_WarhammerTotalWar_III.py", line 332, in Mesh
    MaterialName = ReadStringKnown(f, 514)
  File "Noesis\plugins\python\fmt_WarhammerTotalWar_III.py", line 23, in ReadStringKnown
    return Name
UnboundLocalError: local variable 'Name' referenced before assignment

A bit of code tweaking then got me this error instead:
Traceback (most recent call last):
  File "Noesis\plugins\python\fmt_WarhammerTotalWar_III.py", line 433, in noepyLoadModel
    texList, matList = Mesh(data, mdlList)
  File "Noesis\plugins\python\fmt_WarhammerTotalWar_III.py", line 332, in Mesh
    MaterialName = ReadStringKnown(f, 514)
TypeError: object of type 'int' has no len()

Does anyone have any ideas on what might be going on? Thank you!
## Post #90
- Username: serraphiel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 12, 2022 9:58 pm
- Post datetime: 2022-08-13T02:04:11+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hi,

Is there any news of the animations? we are not able to extract them yet...
## Post #91
- Username: serraphiel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 12, 2022 9:58 pm
- Post datetime: 2022-08-22T13:29:59+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

So quiet here....  anyone ?
## Post #92
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-22T15:03:11+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

> Reply from serraphiel ↑Sat Aug 13, 2022 10:04 am at Sat Aug 13, 2022 10:04 am
>
> 
Hi,

Is there any news of the animations? we are not able to extract them yet...When scrolling through the thread I read this:

> Reply from Angmarec ↑Sun May 24, 2020 6:27 am at Sun May 24, 2020 6:27 am
>
> And it works perfectly, axe works great with all animation, and compared to mazdamundi all prop bones has child, called be_prop_[n]_end
## Post #93
- Username: serraphiel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 12, 2022 9:58 pm
- Post datetime: 2022-08-23T04:36:42+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hi,

Thank you for replying. 

That was for total war warhammer 2. 

The script for total war warhammer 3 is not yet ready. Just spoke with the creator of the script, he is still busy at the momment.
## Post #94
- Username: OhManTFE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 11, 2022 11:11 pm
- Post datetime: 2022-10-11T15:24:22+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Please creator, I beg you to expedite the animation script.

Animation saves a HUGE amount of time because I can 3d print the model mid-animation instead of having to pose it myself, which is a nigh impossible task for me considering I am an amateur on Blender and have no professional experience in animation, skeletons, anything.

Many thanks for sacrificing your time for all of us!
## Post #95
- Username: lijundacom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 06, 2023 10:50 pm
- Post datetime: 2023-02-06T15:30:55+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hello, i am a newer for noesis, and i'm not good at English.
 I want to extract a 'bamboo tree' model in Total War Three Kindoms。The "fmt_WarhammerTotalWar_III.py" can't do this. Will you help me to write a new noesis script? 
Thank you.


 bamboo.7z
(121.42 KiB) Downloaded 22 times
## Post #96
- Username: juggalojes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 14, 2023 6:44 am
- Post datetime: 2023-04-13T22:58:07+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

is it possible for anyone here to extract greenskin units like the goblin great shaman so that i can use it for blender? i want some of these greenskin units to be ported somewhere like Gmod or SFM. send me the a zip file if possible
## Post #97
- Username: Mannfred17
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 28, 2023 4:06 am
- Post datetime: 2023-08-27T21:43:45+00:00
- Post Title: Re: Total War: Warhammer, Noesis script

Hello,

Do you have any idea why the rendering is so untidy?
