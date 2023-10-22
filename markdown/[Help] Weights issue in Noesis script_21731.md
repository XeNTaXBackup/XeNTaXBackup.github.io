## Post #1
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-10T13:46:18+00:00
- Post Title: [Help] Weights issue in Noesis script

Hi everyone,
After months giving up, I decide to fight again with the boneWeight and animation in Noesis.
Mesh and bone are loaded correctly (or as I think so) but bone weight isn't.
There are 3 issues:
I do not know how to use functions for bone weight in Noesis in my case.
Why is there a 4x4 Mat for parent bone under each 4x4 Mat for each bone, or maybe I missunderstand about its role. See below for reference.
How to test for the weight and bone when I have no animation file, is it anyway to create a simple animation for testing purpose?
Hope someone could help or give hints. Many thanks.
Here is the file structure:

> Reply from Ninja ↑Sat Feb 18, 2012 2:35 pm at Sat Feb 18, 2012 2:35 pm
>
> 
...
edit 2. the ksword3d models look static - very simple, vertices 3 floats, normals 3 floats, UV 2 floats + 1 long, triangle strips?
I add structure of bone as below:

```
After jumping to bone offset
number of bones 4 bytes
char bone-name 30 bytes
char parent-bone-name 30 bytes
int number of child bones 4 bytes
char child-bone-name[] 30 bytes
float transform-matrix[4][4] 64 bytes //need to be inversed
float parent bone transform-matrix[4][4] 64 bytes //need to be inversed
int number of vertex connected to this bone 4 bytes 
int vertex id[] 4 bytes 
float weight[] 4 bytes // weighting information corresponding to vertex id
```

Here is the code:
[https://pastebin.com/vTbzXe8A](https://pastebin.com/vTbzXe8A)
And sample file:
[https://drive.google.com/file/d/14G-9xR ... nnPoB/view](https://drive.google.com/file/d/14G-9xR_QSdagUPpa5hV7VF5HGQDnnPoB/view)
## Post #2
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-11T19:54:09+00:00
- Post Title: [Help] Weights issue in Noesis script

I took a very quick look at your script and your weight list and vertex number should be equal, but vert number is 569 while weight list length is 1.
its probably some small mistake in the code, ill try and take a better look later.

Another problem i think you have is you are phrasing mesh then skeleton but weight are in the skeleton section, so you basically read the weights once the mesh is already defied, i dont think it will work like that.

try using NoeMesh() and NoeModel() - that way you can insert all the data at the end

edit:
just from a few prints, one mistake is what you are appending to bidx which should hold bone ID and you are appending vert ID.
## Post #3
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-12T13:22:18+00:00
- Post Title: [Help] Weights issue in Noesis script

> Reply from jayn23 ↑Wed Feb 12, 2020 3:54 am at Wed Feb 12, 2020 3:54 am
>
> 
I took a very quick look at your script and your weight list and vertex number should be equal, but vert number is 569 while weight list length is 1.
its probably some small mistake in the code, ill try and take a better look later.

Another problem i think you have is you are phrasing mesh then skeleton but weight are in the skeleton section, so you basically read the weights once the mesh is already defied, i dont think it will work like that.

try using NoeMesh() and NoeModel() - that way you can insert all the data at the end

Hi jayn23,
You are right, I think I should try to re-write the script with NoeMesh() and NoeModel() - not sure how to write, but will update here soon   .

> Reply from jayn23 ↑Wed Feb 12, 2020 3:54 am at Wed Feb 12, 2020 3:54 am
>
> 
edit:
just from a few prints, one mistake is what you are appending to bidx which should hold bone ID and you are appending vert ID.
Currently, I am trying to reshape the weighting data to create Buffers for rpgBindBoneIndexBuffer and rpgBindBoneWeightBuffer., since the file structure looks like figures no.1 while the functions require the figure no. 2. Honestly, I am in trouble with this step since I do not know much about Python. Do you have any hints for this, or we should have another method that get rid of rpgBindBoneIndexBuffer  and rpgBindBoneWeightBuffer. Thanks.


Figure no. 1


Figure no. 2
## Post #4
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-12T19:18:44+00:00
- Post Title: [Help] Weights issue in Noesis script

> Currently, I am trying to reshape the weighting data to create Buffers for rpgBindBoneIndexBuffer and rpgBindBoneWeightBuffer., since the file structure looks like figures no.1 while the functions require the figure no. 2. Honestly, I am in trouble with this step since I do not know much about Python. Do you have any hints for this, or we should have another method that get rid of rpgBindBoneIndexBuffer and rpgBindBoneWeightBuffer. Thanks.

here is a working code with weights applied correctly - tested it in 3ds max, and i am using  NoeMesh() and NoeModel() so you can learn how to use them    

```
from math import *
from inc_noesis import *

class FileData:

    def __init__(self):
        self.BoneID = []
        self.Weights = []
        
def registerNoesisTypes():
    handle = noesis.register("unk game", ".ksw")    
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #opens debug consle
    #noesis.logPopup()
    return 1


def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    #I preform my check while reading mesh data
    return 1


def noepyLoadModel(data, mdlList): 
     meshName = "test"
     Positions = []
     Normals = []
     UV = []
     PolygonIndex = []
     meshes = []
     VertData = []
     
     bs = NoeBitStream(data, NOE_LITTLEENDIAN)
     bs.seek(140,0)
     numMesh = bs.readInt()
     print("numMesh",numMesh)
     numVerts = bs.readInt()
     print("numVerts",numVerts)
     numFace = bs.readInt()
     print("numFace",numFace)
     unk1 = bs.readInt()
     vertOff = bs.readInt()
     normOff = bs.readInt()
     unk2 = bs.readInt()
     UVOff = bs.readInt()
     unk3 = bs.readInt()
     unk4 = bs.readInt()
     faceoff = bs.readInt()
     unk5 = bs.readInt()
     boneOff = bs.readInt()
     print("boneOff",boneOff)
     
     bs.seek(vertOff,0)
     for i in range(numVerts):
        vx = bs.readFloat()
        vy = bs.readFloat()
        vz = bs.readFloat()
        VertData.append(FileData())
        Positions.append(NoeVec3([vx,vy,vz]))
            
     bs.seek(normOff,0)
     for i in range(numVerts):
        nx = bs.readFloat()
        ny = bs.readFloat()
        nz = bs.readFloat()
        #print(str(nx ) + str(ny ) + str(nz))
        Normals.append(NoeVec3([nx,ny,nz]))
 
     bs.seek(UVOff,0)
     for i in range(numVerts):     
        tu = bs.readFloat()
        tv = bs.readFloat()
        UV.append(NoeVec3([tu,tv,0.0])) 
            
     bs.seek(faceoff,0)
     for j in range(numFace*3):
        PolygonIndex.append(bs.readInt())
            
     boneList = []
     
     bs.seek(boneOff,0)
     boneCount = bs.readUInt()
      
    # read bones loop
     for i in range(boneCount):
        # read bone name
        boneName = bs.readBytes(30).decode('utf-8', 'ignore').replace('\x00','').replace('\xCD','')
        # read parent name of the current bone
        parentBoneName = bs.readBytes(30).decode('utf-8', 'ignore').replace('\x00','').replace('\xCD','')
        # read the number of child bone
        numChildren = bs.readUInt()
        # read child bone name
        for j in range(numChildren):
            childBoneName = bs.readBytes(30).decode('utf-8', 'ignore').replace('\x00','').replace('\xCD','')
        # read 4x4 bone matrix
        boneMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        boneMat43 = boneMat.toMat43().inverse()
        # read 4x4 parent bone matrix
        parentMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        parentMat43 = parentMat.toMat43().inverse()
        # read the number of vertices deformed by this bone
        numVertices = bs.readUInt()
        if numVertices > 0:
            weightList = []
            VertexList = []
            weights = []
            # read vertex IDs
            for j in range(numVertices):
                vertexID = bs.readUInt()
                VertData[vertexID].BoneID.append(i)
                VertexList.append(vertexID)
            # read weights correspondent to vertex IDs
            for j in range(numVertices):
                weight = bs.readFloat()
                VertData[VertexList[j]].Weights.append(weight)
                weights.append(weight)
 
        # set bones for Noesis to display      
        boneList.append(NoeBone(i, boneName, boneMat43, parentBoneName, parentIndex = -1)) 
       
     for k in range(numVerts):
        weightList.append(NoeVertWeight(VertData[k].BoneID, VertData[k].Weights))
        
     a = len(weightList)
     print("len weight =", a)  
     mesh = NoeMesh(PolygonIndex, Positions, meshName)
     mesh.setWeights(weightList)
     mesh.setNormals(Normals)
     mesh.setUVs(UV)
     meshes.append(mesh)
     mdl = NoeModel(meshes)   
     mdl.setBones(boneList) 
     mdlList.append(mdl)
     
     return 1
            
        
```
## Post #5
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-13T15:55:21+00:00
- Post Title: [Help] Weights issue in Noesis script

Yeah, it works correctly, thanks so much jayn23.
I think it's time for researching animation. File structure is below, I think my code is ok except matrices part or may be the parameters for NoeAnim. I also get a warning every time load file:

> WARNING: Number of frame matrices should be at least numBones*numFrames
Attached is example of animation files which should work for the previous model.
Hope you could take a look on this. Thanks again.
[https://pastebin.com/4ga09TG8](https://pastebin.com/4ga09TG8)

```
unk1 4 bytes // 00 00 00 00
numAnim 4 bytes //Uint
frameRate 4 bytes //Uint
animName 30 bytes //string
numBones 4 bytes //Uint
numFrames 4 bytes //Uint
unk2 4 bytes // float 33 or 60
boneNames [] 30 *  numBones bytes // string
boneMatrices [] 64 * numBones * numFrames bytes // 4x4 matrices, may be not need to invert
4 bytes // end of file

```

[MIN.rar](https://xentaxbackup.github.io/file/17498_MIN.rar)
## Post #6
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-13T23:57:08+00:00
- Post Title: [Help] Weights issue in Noesis script

Hi,

I believe i found the problem:
in the code below you are building a new bonelist that is not equal to your skeleton bonelist - i think this is incorrect, the animation looks at the entire skeleton, in this case it has 62 bones while animation and your new list "animBones"is using only 51 (the one that i looked at), this leads WARNING: Number of frame matrices should be at least numBones*numFrames

what you need is use the skeleton bonelist and for animFrameMats is to do is per frame and bone name apply the new matrices to bones that are used, for the others that are static insert the matrix from you skeleton bone list (per frame)

i hope this was clear enough if not ill try to explain better.

```
        animBoneName = aniF.readBytes(30).decode('ascii', 'ignore').replace('\x00','').replace('\xCD','')
        for j in range(len(boneList)):
            if animBoneName == boneList[j].name:
                animBones.append(boneList[j])
```
## Post #7
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-14T17:17:05+00:00
- Post Title: [Help] Weights issue in Noesis script

> Reply from jayn23 ↑Fri Feb 14, 2020 7:57 am at Fri Feb 14, 2020 7:57 am
>
> 
what you need is use the skeleton bonelist and for animFrameMats is to do is per frame and bone name apply the new matrices to bones that are used, for the others that are static insert the matrix from you skeleton bone list (per frame)
Hello,
I could understand your words but I am in trouble with the algorithm. In my mind, the code should be something like this:

```
animBones = list of bone names in the .MIN file
animMat =  list of matrices in the .MIN file
trueMat = [NoeMat43()] * numFrames * len(bones
for i in range(numFrames):
    for j in range(len(bones)):
        if bones[j].name is in [all elements of animBones[].name]:
             trueMat = bones[j].getMatrix().__mul__(current matrix of current animBones at current frame)
        else:
             trueMat = bones[j].getMatrix()
anim = NoeAnim(animName, bones , numFrames, trueMat , frameRate)
```


Is my thought correct? Hope you could help me to transfer to python script if the algorithm is ok. I have been trying for 2 hours but it seems not work as I expected .

updated:
Here is my current code, but it still not work, with an error "IndexError: list index out of range" at line "if boneList[j].name in [animBones[k].name for k in range(numBones)]:":
A full version is at [https://pastebin.com/cvSzKLRP](https://pastebin.com/cvSzKLRP)

```
     anims = rapi.loadPairedFile("JX2 ani", ".min")
     aniF = NoeBitStream(anims)
     signature = aniF.readBytes(8)
     numAnims = aniF.readUInt()
     print('numAnims: ', numAnims)
     frameRate = aniF.readUInt()
     print('frameRate: ', frameRate)
     #animName may not be read correctly since it is Chinese string when using ascii or utf-8, 
     animName = aniF.readBytes(30).decode('ascii', 'ignore').replace('\x00','').replace('\xCD','')
     print('animName: ', animName)
     numBones = aniF.readUInt()
     print('numBones: ', numBones)
     numFrames = aniF.readUInt()
     print('numFrames: ', numFrames)
     unk6 = aniF.readBytes(4)
     animBones = []
     idBones = [-1] * len(boneList)
     for i in range(numBones):
        animBoneName = aniF.readBytes(30).decode('ascii', 'ignore').replace('\x00','').replace('\xCD','')
        for j in range(len(boneList)):
            if animBoneName == boneList[j].name:
                animBones.append(boneList[j])
                idBones[j] = i
     animFrameMats = []
     numMats = numBones * numFrames
     print('numMats: ', numMats)
     for i in range(numMats):
        frameMat44 = NoeMat44.fromBytes(aniF.readBytes(64))
        frameMat43 = frameMat44.toMat43()
        animFrameMats.append(frameMat43)
     trueFrameMats = [NoeMat43()] * numFrames * len(boneList)
     # for i in range(numFrames):
        # for j in range(len(boneList)):
            # trueFrameMats.append(boneList[j].getMatrix())
     for i in range(numFrames):
        for j in range(len(boneList)):
            curId = (i + 1) * (j + 1) - 1
            if boneList[j].name in [animBones[k].name for k in range(numBones)]:
                if idBones[j] != -1:
                    trueFrameMats[curId] = boneList[j].getMatrix().__mul__(animFrameMats[(i + 1) * (idBones[j] + 1) - 1])
                else:
                    print('Error: idBones[', j, '] is = -1')
            else:
                trueFrameMats[curId] = boneList[j].getMatrix()
     #print(len(trueFrameMats))
     anim = NoeAnim(animName, boneList, numFrames, animFrameMats, frameRate)
     #print(anim.__repr__())
     animList = []
     animList.append(anim)

```
## Post #8
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-15T08:51:44+00:00
- Post Title: [Help] Weights issue in Noesis script

Hi,
Here is my current script, although it still not work correctly, I think there are some errors in the appending framematrix but have no clue how to fix them. Keep trying now    .
Updated part is from line 129.
[https://pastebin.com/cP9G8LBC](https://pastebin.com/cP9G8LBC)

Also, some animations may have more bones than in the model's skeleton, or vise versa. It may not affect the result, as if a bone in MIN file do not exist in skeleton, we just ignore it. If a bone in the skeleton does not exist in the MIN file, we use its original matrix for each frame. It's my thought, but the script somehow still not work   

Hope jayn23 or someone could take a glance.
Many thanks.
## Post #9
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-15T16:31:58+00:00
- Post Title: [Help] Weights issue in Noesis script

Sorry haven't been near my computer for the past day,

ill try and write the code see if it works, i did something slimier in my total war warhammer script.

> Also, some animations may have more bones than in the model's skeleton, or vise versa. It may not affect the result, as if a bone in MIN file do not exist in skeleton, we just ignore it. If a bone in the skeleton does not exist in the MIN file, we use its original matrix for each frame. It's my thought, but the script somehow still not work

this sounds weird, i have never seen an animation file that has more bones than the skeleton
## Post #10
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-15T18:07:53+00:00
- Post Title: [Help] Weights issue in Noesis script

> Reply from jayn23 ↑Sun Feb 16, 2020 12:31 am at Sun Feb 16, 2020 12:31 am
>
> 
this sounds weird, i have never seen an animation file that has more bones than the skeleton

Yes, and I think it's because there are 4 class of characters in the game that models are extracted, and some animations are only used for a specific class (which has more bones than others). I think we just ignore the animBone that not in the skeleton and see if the script work. Thanks in advance and nice weekend.
## Post #11
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-15T21:31:51+00:00
- Post Title: [Help] Weights issue in Noesis script

So the animation i am getting is horrible so its incorrect.

edit:
didn't think about it until now, but animation matrix in noesis is assumed to be in local space while the matrix in the bonelist and possibly the animation as well are in world space. so they need to be converted before we apply them, that is probably at least 1 part of the problem.

ill post my code, but to be clear the animation is a mess   
(no conversion world to local done)

```
     anims = rapi.loadPairedFile("JX2 ani", ".min")
     aniF = NoeBitStream(anims)
     signature = aniF.readBytes(8)
     numAnims = aniF.readUInt()
     print('numAnims: ', numAnims)
     frameRate = aniF.readUInt()
     print('frameRate: ', frameRate)
     #animName may not be read correctly since it is Chinese string when using ascii or utf-8,
     animName = aniF.readBytes(30).decode('ascii', 'ignore').replace('\x00','').replace('\xCD','')
     print('animName: ', animName)
     numBones = aniF.readUInt()
     print('numBones: ', numBones)
     numFrames = aniF.readUInt()
     print('numFrames: ', numFrames)
     unk6 = aniF.readBytes(4)
     
     animBones = []
     animFrameMats = []
     
     MatIndex = []  
     MatIndex2 = []
     
     for i in range(numBones):    
        animBoneName = aniF.readBytes(30).decode('ascii', 'ignore').replace('\x00','').replace('\xCD','')
        #print(animBoneName)
        for j in range(len(boneList)):
            if animBoneName == boneList[j].name:
                MatIndex.append(j)
                MatIndex2.append(i)
                #print(boneList[j].name)
                #print("boneList[j].index",boneList[j].index)
                break

     for i in range(numFrames):
     
        TempMat = []
        
        for j in range(len(boneList)):
            TempMat.append(boneList[j].getMatrix()) 
            
        for k in range(len(MatIndex)):
            frameMat44 = NoeMat44.fromBytes(aniF.readBytes(64))
            frameMat43 = frameMat44.toMat43() 
            frameMat43 = frameMat43.inverse()
            if k in MatIndex2:
                print(k)
                TempMat[MatIndex[k]] = frameMat43
            
        animFrameMats += TempMat

     anim = NoeAnim(animName, boneList, numFrames, animFrameMats, frameRate)
     #print(anim.__repr__())
     animList = []
     animList.append(anim)
```
## Post #12
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-16T09:33:49+00:00
- Post Title: [Help] Weights issue in Noesis script

> Reply from jayn23 ↑Sun Feb 16, 2020 5:31 am at Sun Feb 16, 2020 5:31 am
>
> 
didn't think about it until now, but animation matrix in noesis is assumed to be in local space while the matrix in the bonelist and possibly the animation as well are in world space. so they need to be converted before we apply them, that is probably at least 1 part of the problem.
In the model file (.ksw), there is another matrix below every bone matrix, do you think it will be useful in our case? We are currently not using it but somehow the skeleton still looks ok  

```
        boneMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        boneMat43 = boneMat.toMat43().inverse()
        # read 4x4 parent bone matrix
        parentMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        parentMat43 = parentMat.toMat43().inverse()
```

I am not clear about converting from world space to local space. Do you mean we need to convert both matrices in boneList and animation, or only the animation?
If trying to reconstruct matrices of boneList: boneMat43 = boneMat43.__mul__(parentMat43.inverse()) or boneMat43 = boneMat43.__mul__(parentMat43), the skeleton is so weird as images below.


Hope to hear interesting hints from you.
## Post #13
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-16T12:47:05+00:00
- Post Title: [Help] Weights issue in Noesis script

> I am not clear about converting from world space to local space. Do you mean we need to convert both matrices in boneList and animation, or only the animation?
>
> If trying to reconstruct matrices of boneList: boneMat43 = boneMat43.__mul__(parentMat43.inverse()) or boneMat43 = boneMat43.__mul__(parentMat43), the skeleton is so weird as images below.

you need to convert only the animation matrix to local space, the bonelist is expected to be in world space,
here is a link to a thraed where they convert from world to local space, MrAdults is the creator of noesis so he knows what he is talking about 
[viewtopic.php?f=16&t=15065](https://forum.xentax.com/viewtopic.php?f=16&t=15065)

> there is another matrix below every bone matrix, do you think it will be useful in our case? We are currently not using it but somehow the skeleton still looks ok
i have seen some games that include both world and local space matrix, you say both matrix work without doing any conversion on either of them? hmmm
## Post #14
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-16T13:09:56+00:00
- Post Title: [Help] Weights issue in Noesis script

> you need to convert only the animation matrix to local space, the bonelist is expected to be in world space,
>
> here is a link to a thraed where they convert from world to local space, MrAdults is the creator of noesis so he knows what he is talking about 
>
> viewtopic.php?f=16&t=15065
Thanks, I will spend time for this thread. 

> i have seen some games that include both world and local space matrix, you say both matrix work without doing any conversion on either of them? hmmm
No, as you see in the script, I mean we append only the boneMat43 to the boneList while there is nothing to do with parentMat43. The latter is named "parentMat43" just because I guess so (and not sure   ). I wonder how could we check if boneMat43 is the worldspace matrix and parentMat43  is the localspace matrix (and not the matrix of parent bone like I guess)? Anyway, I could not thank enough for your help, and I will update here soon about my work.

```
        boneMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        boneMat43 = boneMat.toMat43().inverse()
        # read 4x4 parent bone matrix
        parentMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        parentMat43 = parentMat.toMat43().inverse()
```
## Post #15
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-16T14:14:34+00:00
- Post Title: [Help] Weights issue in Noesis script

> you need to convert only the animation matrix to local space, the bonelist is expected to be in world space,
>
> here is a link to a thraed where they convert from world to local space, MrAdults is the creator of noesis so he knows what he is talking about 
>
> viewtopic.php?f=16&t=15065
I try to mimic the script in the thread provided. Unfortunately, the result is still a mess   . Could you help to take a glance if I need to modify something? Here is the full version: [https://pastebin.com/eWxmzYZj](https://pastebin.com/eWxmzYZj)

```
        TempMat = []
            
        for j in range(len(boneList)):
            TempMat.append(boneList[j].getMatrix()) 
            
        for k in range(len(MatIndex)):
            frameMat44 = NoeMat44.fromBytes(aniF.readBytes(64))
            frameMat43 = frameMat44.toMat43() 
            frameMat43 = frameMat43.inverse()
            if k in MatIndex2:
                # print(k)
                TempMat[MatIndex[k]] =  TempMat[MatIndex[k]] * frameMat43
                # check if current bone have parent
                if boneList[MatIndex[k]].parentName != 'Scene Root':
                    # get index of the parentBone in boneList 
                    x = [boneList[y].name for y in range(boneCount)].index(boneList[MatIndex[k]].parentName)
                    TempMat[MatIndex[k]] = TempMat[MatIndex[k]] * TempMat[x].inverse()
            
        animFrameMats += TempMat

     anim = NoeAnim(animName, boneList, numFrames, animFrameMats, frameRate)
     animList = []
     animList.append(anim)
```
## Post #16
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-16T21:12:43+00:00
- Post Title: Re: [Help] Weights issue in Noesis script

> I try to mimic the script in the thread provided. Unfortunately, the result is still a mess  . Could you help to take a glance if I need to modify something? Here is the full version:

unfortunately i am not sure where the problem is, my TempMat is in world space so i guess that should be converted as well, but when i tried converting it didn't work for me, maybe someone with a bit more experience can step in and help us?
## Post #17
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-17T09:12:46+00:00
- Post Title: Re: [Help] Weights issue in Noesis script

Yes, hope someone could help us a hand. Also, do you have any idea about the matrix (parentMat) below every bone matrix? We are currently not using it. Hope to hear your advise.

```
        boneMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        boneMat43 = boneMat.toMat43().inverse()
        # read 4x4 parent bone matrix
        parentMat = NoeMat44.fromBytes( bs.readBytes(0x40), NOE_LITTLEENDIAN )
        # convert and inverse to 4x3 matrix
        parentMat43 = parentMat.toMat43().inverse()
```

I had thought it is the maxtrix of parent bone so I named it parentMat, but it seem not true.
## Post #18
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-17T22:08:06+00:00
- Post Title: Re: [Help] Weights issue in Noesis script

well i tried something very simple to check if the extra matrix is the locale space:

i extracted the skeleton to collada (.dae) which stores the matrix in locale space as far as i know, printed out the matrix in noesis and compared
they were not the same. so still no clue, but if its not the locale space it not very helpful anyway.
## Post #19
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-22T17:20:25+00:00
- Post Title: Re: [Help] Weights issue in Noesis script

Hi jayn23,
I still could not know how the matrices in animation files work, but I could now found the animation file that has the same numbers of bone with the model. So, hope you could try again if your algorithm work. In game, this is a fox being jump and bite.

To be honest, I have tried to read about matrices in 3D graphics, DirectX (the game use DirectX), local space and world space but still have no clue T.T.
Also, here is my curent script (new lines added but still not work): [https://pastebin.com/4sgQwuJR](https://pastebin.com/4sgQwuJR)

Kindly refer to the attachments
Example file has 5 animations inside and model has 41 bones.
[003.rar](https://xentaxbackup.github.io/file/17543_003.rar)
