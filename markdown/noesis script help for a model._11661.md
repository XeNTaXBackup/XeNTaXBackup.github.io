## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-05T04:19:14+00:00
- Post Title: noesis script help for a model.

2
Bip01 L Calf
Bip01 L Foot

1
Bip01 L Foot
300 bytes of filler data for empty.

Im not sure how to use that with noesis.


Then there are those 3 matrices in the beginning -  why 3? i assumed the names - as of what they might be - any ideas?


And for third and major issue - i cant get all 16 to load - if i set range to 1 first one loads fine, else i get the 
"number of indices must be evenly divisible by 3"



and then the x1/2 values  - seem to be floats - one with positive values, other with negative.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-05T10:57:03+00:00
- Post Title: noesis script help for a model.

What game is it?
Also i need to see a sample.
## Post #3
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-05T14:07:45+00:00
- Post Title: noesis script help for a model.

[https://mega.co.nz/#!TFJyxToS!oxacv0yxp ... XzERq6BNbU](https://mega.co.nz/#!TFJyxToS!oxacv0yxp4wL0dhR_wAiLr5jggLtwsVsnXzERq6BNbU)

loop works - missed for for bones lol.


However - why 3 matrices in the beginning -  usually 1 would be for transform, what about other two?

Also... how ot load/import the bone parenting in noesis and any ideas about the x1 x2 area values?


also - since i do it all in the 1  call, it overlaps uv maps and data view only shows mesh0 - anso positions are off.
## Post #4
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-05T16:07:17+00:00
- Post Title: noesis script help for a model.

```
import noesis
import rapi
import os
import struct

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("RFOnline", ".msh")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    if len(data) < 2:
        return 0
    try:
        bs = NoeBitStream(data)
        idstring = noeStrFromBytes(bs.readBytes(6))
        if idstring != "MESH08":
            bs.seek(0)
            return 0
        return 1
    except:
        return 0
    
def get_type(data):
    '''Check mesh format'''
    
    bs = NoeBitStream(data)
    string = bs.readBytes(6)
    try:
        if noeStrFromBytes(string) == "MESH08":
            return 1
        return 0
    except:
        return 0 

def noepyLoadModel(data, mdlList):
    '''Load the model'''
    
    ctx = rapi.rpgCreateContext()
    load_single_model(data, mdlList)
    return 1
    
def load_single_model(data, mdlList):
    '''Loads a single model.'''
    
    modelType = get_type(data)
    if modelType == 1:
        parser = M8Parser(data)          
        parser.parse_file()  
        mdl = rapi.rpgConstructModel()
        mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
        mdl.setBones(parser.boneList)
        mdl.setAnims(parser.animList)
        mdlList.append(mdl)     

class M8Parser(object):
    '''Type MESH08 parser'''
    
    def __init__(self, data):
        
        self.inFile = NoeBitStream(data)
        self.animList = []
        self.texList = []
        self.matList = []
        self.boneList = []
                
    def parse_file(self):
        idstring = self.inFile.readBytes(6)
        numMesh = self.inFile.readUShort()
        self.parse_mesh(numMesh)
        
    def parse_vertices(self, numVerts):
        
        vertBuff = self.inFile.readBytes(numVerts*64)
        rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 0)
        rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 32)
        rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 44)
        
    def build_mesh(self,numFace,faceList,worldMatrix,viewMatrix,projectionMatrix,texture):
        rapi.rpgSetTransform(worldMatrix)
        rapi.rpgSetTransform(viewMatrix)
        rapi.rpgSetTransform(projectionMatrix)
        rapi.rpgSetMaterial(texture)
        material = NoeMaterial(texture,texture)
        self.matList.append(material)
        rapi.rpgCommitTriangles(faceList, noesis.RPGEODATA_USHORT, numFace, noesis.RPGEO_TRIANGLE, 1)   

    def parse_faces(self,numFace):
        faceList = self.inFile.readBytes(numFace*2)
        return faceList
    
    def parse_mesh(self,numMesh):
        for i in range(numMesh):
            objectName = self.read_name(100)
            objectGroup = self.read_name(100)
            worldMatrix = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
            viewMatrix = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
            projectionMatrix = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
            bonesnames = self.inFile.readUShort()
            faces = self.inFile.readUShort()
            bonelink = self.inFile.readUShort()
            texture = os.path.basename(self.read_name(204))
            x1 = NoeVec3.fromBytes(self.inFile.readBytes(12))
            x2 = NoeVec3.fromBytes(self.inFile.readBytes(12))
            #rapi.rpgSetPosScaleBias(x1,x2)
            self.inFile.seek(67, 1)            
            
            numVerts = self.inFile.readUShort()
            if numVerts > 0:
                self.parse_vertices(numVerts)   
            numFace = self.inFile.readUShort()
            if numFace > 0:
                faceList = self.parse_faces(numFace)
                self.build_mesh(numFace,faceList,worldMatrix,viewMatrix,projectionMatrix,texture)
    
               
            numBone = self.inFile.readUShort()
            if numBone > 0:
                for i in range(numBone):
                    idx = self.inFile.readBytes(4)
                    bonename = self.read_name(100)
                    bonedata = self.read_name(300)
            
    def read_name(self, n):
        
        string = self.inFile.readBytes(n)
        try:
            return noeStrFromBytes(string)
        except:
            return ""             

```


This is where i got. Getting really stuck now - lack of experience with it i guess.
1. Bones are basically ignored now - not sure how to format and use them
2. Some unknown data: x1/x2 and the 67 skipped bytes
3. 3 matrices ? for what?
4. it doesn't load all the model sections  separately if i look at the data view.
5. ignored object name etc - not used.
6. most model parts don't seem to align properly and don't fit together.
## Post #5
- Username: djmauro
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-05T16:13:22+00:00
- Post Title: noesis script help for a model.

> This is where i got. Getting really stuck now - lack of experience with it i guess.
>
> 1. Bones are basically ignored now - not sure how to format and use them
>
> 2. Some unknown data: x1/x2 and the 67 skipped bytes
>
> 3. 3 matrices ? for what?
>
> 4. it doesn't load all the model sections separately if i look at the data view.
>
> 5. ignored object name etc - not used.
>
> 6. most model parts don't seem to align properly and don't fit together.

3 - look at my black desert script for ideas.
most likely different coordinate systems.
like this
				boneMtxLocal   = NoeMat44.fromBytes(bs.readBytes(64)).toMat43()
				boneMtxWorld   = NoeMat44.fromBytes(bs.readBytes(64)).toMat43()

4 - change the mesh piece names or materials to have noesis split them.
rapi.rpgSetName() in between each triangle commit.

6 they are most likely needing to be positioned on top of a bone.
## Post #6
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-05T17:54:27+00:00
- Post Title: noesis script help for a model.

for names i see two options:
            objectName = self.read_name(100)
            objectGroup = self.read_name(100)

the 2nd one seems to be a link to some group or bone ( its a fact that its a custom 3dsmax exported format - bone names already hint at that).

Is there anything to do with that, or its too custom models specific?

On most part you can see it linked to NULL - but sometimes its a bone name ( and the no 3d data model sections, for particle effec use etc - can also have various names like W00).


Does this kind of file structure remind any common 3d formats ( with the vertex-norlal-uv and then face and bone layout)?

With the rpgSetName set - it still only actually seems to have 9 total models listed -  but there is a total on 32 on the example mesh.

its skipping all the defined models without vertices/faces/bones. Even tho i removed the > 0 part so it would actually parse if its 0.

EDIT:

Looks like the 2nd 100 bytes after name is the bone link.

And unfortunately noesis groups all the nodes with same name.

The bones are in a separate file - so the link makes sense. but the high number of bone values at the end of the model block for main sections doesn't make sense now.

The bone file:
[https://mega.co.nz/#!TFJyxToS!oxacv0yxp ... XzERq6BNbU](https://mega.co.nz/#!TFJyxToS!oxacv0yxp4wL0dhR_wAiLr5jggLtwsVsnXzERq6BNbU)

spend another 10 on it today as well and iv made no real progress. guess i lack experience with 3d formats and noesis+python.

Perhaps someone with a bit more experience notices something that could be done here.
## Post #7
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2014-07-05T23:31:09+00:00
- Post Title: noesis script help for a model.

After more testing - i decided to look for a  simpler model.

Found one.
Then stripped it of all the extra model sections that has 0 vertex data ( used to link particle effects etc).
Removed the values x1/x2 (00 bytes).
It has no bone section at the end ( 0 bones listed).

Then removed the 3x 2 byte values before texture name.
Edited texture name ( it needs drive name, folder and then texture name to work in the game).
Removed 1st and 2nd matrix - they had no impact ingame.
2nd matrix did affect the model - kept that one.
Changed the first mesh name value - it can be anything so no problems there.
2nd 100 bytes after mesh value however link to a bone ( and therefor allow me to hold it - weapons use  general common bones).

[https://mega.co.nz/#!7Y4HGKYI!y-6cdQJU- ... 4BKQoCGplE](https://mega.co.nz/#!7Y4HGKYI!y-6cdQJU-HTGR-WQ4BhrSHTli0w2HRx2L4BKQoCGplE)


now all there is for basic model to work:
modelname
bonename
1 matrix
dds name
vertex list ( vertex xyzw, normal xwzw, uv x4) and facelist.

So has anyone any ideas if there are some existign formats that would be similar to this( and therefor would make it a lot easier to convert) ?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-08T22:23:40+00:00
- Post Title: noesis script help for a model.

> Reply from djmauro
>
> 
2nd matrix did affect the model - kept that one.
[...]
So has anyone any ideas if there are some existign formats that would be similar to this[...] ?Nope, I don't have.

From your example2.mesh talking about the 2nd matrix (viewMatrix from your Noesis script) which is
((0.7660925388336182, 0.6428085565567017, 0.0004932102747261524), 
(-0.6428134441375732, 0.7660914659500122, 0.0006608788389712572), 
(1.0540243238210678e-05, -0.0007995516061782837, 0.9999963641166687)
(rotation part)
This is a heading and a bank angle of zero and an attitude of -40 degrees:
[](http://www.pic-upload.de/view-23830049/angle.jpg.html)

Since you said the viewMatrix affects the model you seem to have changed the values and written them back into the game?
But from your other thread about transform matrices, seems you don't know how to change the matrix?

Here's a link for calculating the matrix from heading, attitude, bank  (yaw, pitch, roll).
[http://www.euclideanspace.com/maths/geo ... /index.htm](http://www.euclideanspace.com/maths/geometry/rotations/conversions/eulerToMatrix/program/index.htm)
(low precision only but you can find c code on euclidianspace.com which will provide higher one)

The matrix values have to be converted to IEEE754 before writing them back into the msh file.
