## Post #1
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2021-04-01T01:17:35+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

Hello
I need help with mdx files. Do not confuse with warcraft files.
They are ps4. Used in ps4 themes.
I tried everything. I used gmotool to extract it with noesis but it didn't work.
I tried to convert the file to mds (text format) but still can't convert the files to fbx.

mdx header is "XDM.00.1MSP" here is an example of a file.


the header of the mds file is ".MDS 1.00"

[MDX MDS Files.rar](https://xentaxbackup.github.io/file/19820_MDX MDS Files.rar)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-01T13:02:30+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

only mesh and texture.
the texture should be in the same folder as the model

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("mesh MDS", ".MDS")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    
    noesis.logPopup()
    return 1

NOEPY_HEADER = ".MDS"

def noepyCheckType(data):
    bs = NoeBitStream(data)
    if len(data) < 4:
        return 0
    if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
        return 0
    return 1
	
def noepyLoadModel(data, mdlList):
    m = CreateModel()
    
    mdl = NoeModel([],[],[])
    mdl.setMeshes(m.MeshList)
    mdl.setModelMaterials(NoeModelMaterials([], m.matList))
    mdlList.append(mdl)
    return 1

class CreateModel:
    def __init__(self):
        self.p = ParseFile()

        self.MeshList = []
        self.matList = []
        #function
        self.CreateMaterial()
        self.CreateMesh()

    def CreateMesh(self):
        for part in self.p.Parts:
            for msh in part.Meshes:
                mesh = NoeMesh([],[],msh.Name+"_"+part.Name, msh.SetMaterial)
                mesh.setIndices(msh.Indices)
                for array in part.Arrays:
                    if msh.SetArrays in array.Name:
                        mesh.setPositions(array.POSITION)
                        mesh.setNormals(array.NORMAL)
                    #Scale and Translate UVs
                        for mat in self.matList:
                            if msh.SetMaterial in mat.name:
                                for tx in self.p.Textures:
                                    if tx.FileName in mat.texName.split('\\')[-1]:
                                        for i in range(0,len(array.TEXCOORD)):
                                            array.TEXCOORD[i] += tx.UVTranslate
                                            array.TEXCOORD[i] *= tx.UVScale
                    #-end
                        mesh.setUVs(array.TEXCOORD)
                self.MeshList.append(mesh)

    def CreateMaterial(self):
        matName = ""
        TxName = ""
        
        for mat in self.p.Materials:
            matName = mat.Name
            for layer in mat.Layers:
                for tx in self.p.Textures:
                    if layer.SetTexture in tx.Name:
                        TxName = tx.FileName
                diffTex = ""
                if not not TxName:
                    basepath = rapi.getDirForFilePath(rapi.getInputName())
                    diffTex = basepath + TxName
                material = NoeMaterial(matName, diffTex)
                self.matList.append(material)

class ParseFile: 
    def __init__(self):
        dirPath = rapi.getDirForFilePath(rapi.getInputName())
        filename = rapi.getLocalFileName(rapi.getInputName())
        f =  open(dirPath + filename).read().splitlines()
        
        self.Parts = []
        self.Materials = []
        self.Textures = []
        
        for i in range(0,len(f)):
            if "Part" in f[i].split():
                arr = []
                bracket = 0
                for q in range(i,len(f)):
                    if "{" in f[q]:
                        bracket += 1
                    if "}" in f[q]:
                        bracket -= 1
                    if bracket==0:
                        break
                    else:
                        arr.append(f[q])
                self.Parts.append(Part(arr))
                
            if "Texture" in f[i].split():
                arr = []
                for q in range(i,len(f)):
                    if "}" in f[q]:
                        break
                    else:
                        arr.append(f[q])
                self.Textures.append(Texture(arr))
                
            if "Material" in f[i].split():
                arr = []
                for q in range(i,len(f)):
                    if "}" in f[q]:
                        break
                    else:
                        arr.append(f[q])
                self.Materials.append(Material(arr))

class Part:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Meshes = []
        self.Arrays = []
        #Parsing Part
        self.ParsePart(arr)
        
    def ParsePart(self,arr):
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "Mesh" in split:
                arr0 = []
                for q in range(i,len(arr)):
                    if "}" in arr[q]:
                        break
                    else:
                        arr0.append(arr[q])
                self.Meshes.append(Mesh(arr0))
            if "Arrays" in split:
                arr0 = []
                for q in range(i,len(arr)):
                    if "}" in arr[q]:
                        break
                    else:
                        arr0.append(arr[q])
                self.Arrays.append(Array(arr0))

class Mesh:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.SetMaterial = ""
        self.SetArrays = ""
        self.Indices = []
        #Parsing Mesh
        self.ParseMesh(arr)
        
    def ParseMesh(self,arr):
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "SetArrays" in split:
                self.SetArrays = arr[i].split('"')[1] 
            if "DrawArrays" in split:
                self.Indices = [int(x) for x in split[4:]]
            if "SetMaterial" in split:
                self.SetMaterial = arr[i].split('"')[1] 

class Array:
    def __init__(self,arr):
        self.Name = arr[0].split()[1].replace('"','')
        self.POSITION = []
        self.NORMAL = []
        self.TEXCOORD = []
        #Parsing Array
        self.ParseArray(arr)
        
    def ParseArray(self,arr):
        Header = arr[0].split()[2]
        for i in arr[1:]:
            split = i.split()
            if "POSITION" in Header:
                self.POSITION.append(NoeVec3([float(x) for x in split[:3]]))
            if "NORMAL" in Header:
                self.NORMAL.append(NoeVec3([float(x) for x in split[3:6]]))
            if "TEXCOORD" in Header:
                self.TEXCOORD.append(NoeVec3([float(x) for x in split[6:8]+[0]]))

class Material:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Layers = []
        
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "Layer" in split:
                arr0 = []
                for q in range(i,len(arr)):
                    if "}" in arr[q]:
                        break
                    else:
                        arr0.append(arr[q])
                self.Layers.append(Layer(arr0))

class Layer:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.SetTexture = ""
        
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "SetTexture" in split:
                self.SetTexture = arr[i].split('"')[1]

class Texture:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.FileName = ""
        self.UVTranslate = NoeVec3((0,0,0))
        self.UVScale = NoeVec3((1,1,0))
    
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "FileName" in split:
                self.FileName = arr[i].split('"')[1]
            if "UVTranslate" in split:
                self.UVTranslate = NoeVec3([float(x) for x in split[1:]+[0]])
            if "UVScale" in split:
                self.UVScale =  NoeVec3([float(x) for x in split[1:]+[0]])
```

[111.png](https://xentaxbackup.github.io/file/19880_111.png)
## Post #3
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2021-04-01T13:25:14+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

the model looks like this in a ps4 mdx file viewer:





has animation, the model scrolls up.

edit: here the DDS File: [https://www.mediafire.com/file/wdrbssjk ... t.dds/file](https://www.mediafire.com/file/wdrbssjkfyluc8o/koma_hight.dds/file)
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-01T23:49:00+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

I'll take a look in my free time
## Post #5
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2021-04-02T01:02:11+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

Good job!

but the animation is missing.

Here is an example of the animation (sorry for the bad quality):

[https://drive.google.com/file/d/1SB2S3x ... sp=sharing](https://drive.google.com/file/d/1SB2S3xgfVxb_QOgDazxmv4GTU0HoZgJo/view?usp=sharing)
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-02T17:51:59+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

can you provide tools to convert mdx>mds
## Post #7
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2021-04-03T01:10:20+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

Done!
look at private messages
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-05T08:44:59+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

ok
## Post #9
- Username: RevanCrow
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 18, 2020 9:42 pm
- Post datetime: 2021-04-05T11:16:03+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

Can you share the plugin with me to see if I can do something?
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-06T20:32:35+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

look at private messages
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-09T17:53:02+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

solved a problem:

```
import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("test mds", ".MDS")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel)
   #noesis.logPopup()
   return 1

NOEPY_HEADER = ".MDS"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

def noepyLoadModel(data, mdlList):
    s = CreateSkl()
    
    mdl = NoeModel([],[],[])
    mdl.setBones(s.boneList)
    mdlList.append(mdl)
    return 1

class CreateSkl:
    def __init__(self):
        self.p = ParseFile()
        self.boneList = []
        #function
        self.CreateBones()
        
    def GetParentIndex (self,parentName, arr):
        for i,bone in enumerate(arr):
            if bone.Name == parentName:
                return i
        return -1 
    
    def CreateBones(self): 
        for bone in self.p.Bones:
            self.boneList.append(NoeBone(len(self.boneList),bone.Name,bone.Mat43,None,self.GetParentIndex(bone.ParentBone,self.p.Bones)))

        for bone in self.boneList:
            pIndex = bone.parentIndex
            if pIndex != -1:
                bone.setMatrix(bone.getMatrix() * self.boneList[pIndex].getMatrix())
                

                        
class ParseFile:
    def __init__(self):
        dirPath = rapi.getDirForFilePath(rapi.getInputName())
        filename = rapi.getLocalFileName(rapi.getInputName())
        f =  open(dirPath + filename).read().splitlines()
        
        self.Bones = []

        for i in range(0,len(f)):
            if "Bone" in f[i].split():
                arr = []
                for q in range(i,len(f)):
                    if "}" in f[q]:
                        break
                    else:
                        arr.append(f[q])
                self.Bones.append(Bone(arr))
   
class Bone:
    def __init__(self,arr):
        self.Name = ""
        self.ParentBone = ""
        self.Mat43 = NoeMat43()
        self.BlendBones = []
        #function
        self.ParseBone(arr)
        
    def ParseBone(self,arr):
        self.Name = arr[0].split('"')[1]
        Translate = NoeVec3((0,0,0))
        Rotate = NoeQuat((0,0,0,0))
        Scale = NoeVec3((1,1,1))
        
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "ParentBone" in split:
                self.ParentBone = arr[i].split('"')[1]
            if "Translate" in split:
                Translate = NoeVec3([float(x) for x in arr[i].replace('Translate','').split()])
            if "Rotate" in split:
                #Rotate = NoeQuat([float(x) for x in reversed(arr[i].replace('Rotate','').split())])
                Rotate = NoeQuat([float(x) for x in arr[i].replace('Rotate','').split()])
            if "Scale" in split:
                Scale = NoeVec3([float(x) for x in arr[i].replace('Scale','').split()])
            if "BlendBone" in split:
                self.BlendBones.append(BlendBone(arr[i:i+5]))
                
        mat = Rotate.toMat43()
        mat[3] = Translate
        #mat[0][0] = Scale[0]
        #mat[1][1] = Scale[1]
        #mat[2][2] = Scale[2]
        self.Mat43 = mat.transpose()
        
class BlendBone:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Mat43 = NoeMat43()
        
        for i,line in enumerate(arr[1:]):
             self.Mat43[i] = [float(x) for x in line.replace('\\','').split()[:3]]
```




3333.png (24.48 KiB) Viewed 302 times
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-06T17:30:33+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

I leave it here
connected everything. but of course it doesn't work as it should)))
incorrectly loads the positions of the mesh relative to the bones and the problem with animations ...
I'm confused myself and can't figure out what's wrong

warring !!
a lot of cycles, the script is slow

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("mesh MDS", ".MDS")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    
    noesis.logPopup()
    return 1

NOEPY_HEADER = ".MDS 1.00"

def noepyCheckType(data):
    if NOEPY_HEADER in data.decode().split('\n')[0]:
        return 1
    else:
        return 0
	
def noepyLoadModel(data, mdlList):
    file = data.decode().split('\n')
    m = CreateModel(file)
    mdl = NoeModel([],[],[])
    mdl.setMeshes(m.MeshList)
    mdl.setBones(m.boneList)
    mdl.setAnims(m.animList)
    mdl.setModelMaterials(NoeModelMaterials([], m.matList))
    mdlList.append(mdl)
    return 1
    
def FindBracket(arr):
    bracket = 0
    for i,line in enumerate(arr):
        if '{' in line:
            bracket += 1
        if '}' in line:
            bracket -= 1
        if bracket==0:
            return arr[:i]
            break

class CreateModel:
    def __init__(self,f):
        self.p = ParseFile(f)

        self.boneList = []
        self.MeshList = []
        self.matList = []
        self.animList = []
        #function
        self.CreateBones()
        self.CreateMaterial()
        self.CreateMesh()
        self.CreateAnims()
    
    def GetBoneIndex (self,BoneName):
        index = 0
        for i, item in enumerate(self.p.Bones):
            if BoneName in item.Name:
                index = i
                break
        return index

    def GetParentIndex (self,parentName, arr):
        for i,bone in enumerate(arr):
            if bone.Name == parentName:
                return i
        return -1 
    
    def CreateBones(self): 
        for i,bone in enumerate(self.p.Bones):
            self.boneList.append(NoeBone(i,bone.Name,bone.Mat43,None,self.GetParentIndex(bone.ParentBone,self.p.Bones)))

        for bone in self.boneList:
            pIndex = bone.parentIndex
            if pIndex != -1:
                bone.setMatrix(bone.getMatrix() * self.boneList[pIndex].getMatrix())

    def CreateMesh(self):
        for part in self.p.Parts:
            for msh in part.Meshes:
                mesh = NoeMesh([],[],msh.Name+"_"+part.Name, msh.SetMaterial)
                #---
                myPosition = []
                myNormals = []
                myUV = []
                myboWe = []
                myboId = []
                bWeList = []
                alone = list(set(msh.Indices))
                for m in alone:
                    for i in range(0, len(msh.Indices)):
                        if m == msh.Indices[i]:
                            msh.Indices[i] = alone.index(m)
                #---
                if part.Name in [x.DrawPart for x in self.p.Bones if not x.BlendBones]:
                    for a in part.Arrays:
                        a.WEIGHT = [[1.0]]*len(a.POSITION)
                        a.INDICES = [[0]]*len(a.POSITION)

                mesh.setIndices(msh.Indices)
                for array in part.Arrays:
                    if msh.SetArrays in array.Name:
                        #---
                        if array.POSITION:
                            for m in alone: myPosition.append(array.POSITION[int(m)])
                        if array.NORMAL:
                            for m in alone: myNormals.append(array.NORMAL[int(m)])
                        if array.TEXCOORD:
                            for m in alone: myUV.append(array.TEXCOORD[int(m)])
                        if array.WEIGHT:
                            for m in alone: myboWe.append(array.WEIGHT[int(m)])
                            if array.INDICES:
                                for m in alone: myboId.append(array.INDICES[int(m)])
                        #---
                    #Scale and Translate UVs
                        for mat in self.matList:
                            if msh.SetMaterial in mat.name:
                                for tx in self.p.Textures:
                                    if tx.FileName in mat.texName.split('\\')[-1]:
                                        for i in range(0,len(myUV)):
                                            myUV[i] += tx.UVTranslate
                                            myUV[i] *= tx.UVScale
                    #-end
                #FIX WEIGHT INDICES
                
                if self.p.Bones:
                    bone = []
                    try:
                        bone =  [x for x in self.p.Bones if part.Name in x.Name][0]
                    except:
                        bone = self.p.Bones[0]
                    if bone.BlendBones:
                        realbonesId = [self.GetBoneIndex (x.Name) for x in bone.BlendBones]
                        for i in range (0,len(msh.BlendIndices)):
                            msh.BlendIndices[i] = realbonesId[msh.BlendIndices[i]]
                        if not msh.BlendIndices:
                            for x in realbonesId: msh.BlendIndices.append(x)
                        for i in range (0,len(myboId)):
                            for q in range (0,len(myboId[i])):
                                myboId[i][q] = msh.BlendIndices[myboId[i][q]]
                    else:
                        if myboId:
                            realboneId = self.GetBoneIndex (bone.Name)
                            myboId = [[realboneId]]*len(myboId)

                    if myboId and myboWe:
                        for j in range (0,len(myboId)):
                            bWeList.append(NoeVertWeight(myboId[j], myboWe[j]))
                #END FIX WEIGHT INDICES
                if bWeList:
                    mesh.setWeights(bWeList)
                mesh.setUVs(myUV)
                mesh.setPositions(myPosition)
                mesh.setNormals(myNormals)
                self.MeshList.append(mesh)

    def CreateMaterial(self):
        matName = ""
        TxName = ""
        
        for mat in self.p.Materials:
            matName = mat.Name
            if mat.Layers:
                for layer in mat.Layers:
                    for tx in self.p.Textures:
                        if layer.SetTexture in tx.Name:
                            TxName = tx.FileName
                    diffTex = ""
                    if not not TxName:
                        basepath = rapi.getDirForFilePath(rapi.getInputName())
                        diffTex = basepath + TxName
                    if diffTex:
                        material = NoeMaterial(matName, diffTex)
                    self.matList.append(material)
            else:
                self.matList.append(NoeMaterial(matName,""))

    def CreateAnims(self):
        for motion in self.p.Motions:
            oneVec3 = NoeVec3((1,1,1))
            frameCount = motion.Frame+1
            frameRate = motion.FrameRate
            MotionMatrix = []

            for frame in range(0,frameCount):
                FrameMatrix = []
 
                for bone in self.p.Bones:
                    mat = bone.Mat43*1
                    FrameMatrix.append(mat)
                MotionMatrix.append(FrameMatrix)
            
            for anim in motion.Animates:
                for i,bone in enumerate(self.p.Bones):
                    if anim.BoneName == bone.Name:  
                        for curve in motion.FCurves:
                            if anim.Curve == curve.Name:
                                for frameCurve in curve.ArrFrame:
                                    numF = frameCurve[0]
                                    if anim.Type == "Translate":
                                        MotionMatrix[numF][i][3] = (oneVec3/bone.Scale)*NoeVec3(frameCurve[1:])
                                    if anim.Type == "Rotate":
                                        rot = NoeQuat(frameCurve[1:])
                                        pos = MotionMatrix[numF][i][3]
                                        mat43 = rot.toMat43()
                                        mat43[3] = pos
                                        MotionMatrix[numF][i] = mat43.transpose()
                                    if anim.Type == "Scale":
                                        scl = frameCurve[1:]
                                        MotionMatrix[numF][i][0][0] = scl[0]
                                        MotionMatrix[numF][i][1][1] = scl[1]
                                        MotionMatrix[numF][i][2][2] = scl[2]
                                break    
            newMotionMatrix = []
            for mat in MotionMatrix:
                newMotionMatrix += mat
            noeAnim = NoeAnim(motion.Name, self.boneList, frameCount, newMotionMatrix, frameRate)
            self.animList.append(noeAnim)

class ParseFile: 
    def __init__(self,f):
        
        self.WeightedCenters = []
        self.Bones = []
        self.Motions = []
        self.Parts = []
        self.Materials = []
        self.Textures = []

        for i in range(0,len(f)):
            if "WeightedCenter" in f[i].split():
                self.WeightedCenters.append(WeightedCenter(f[i]))
            if "Bone" in f[i].split():
                self.Bones.append(Bone(FindBracket(f[i:])))
            if "Part" in f[i].split():
                self.Parts.append(Part(FindBracket(f[i:])))
            if "Texture" in f[i].split():
                self.Textures.append(Texture(FindBracket(f[i:])))
            if "Material" in f[i].split():
                self.Materials.append(Material(FindBracket(f[i:])))
            if 'Motion' in f[i].split():
                self.Motions.append(Motion(FindBracket(f[i:])))

class Part:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Meshes = []
        self.Arrays = []
        #Parsing Part
        self.ParsePart(arr)
        
    def ParsePart(self,arr):
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "Mesh" in split:
                self.Meshes.append(Mesh(FindBracket(arr[i:])))
            if "Arrays" in split:
                self.Arrays.append(Array(FindBracket(arr[i:])))

class Mesh:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.SetMaterial = ""
        self.SetArrays = ""
        self.Indices = []
        self.BlendIndices = []
        #Parsing Mesh
        self.ParseMesh(arr)
        
    def ParseMesh(self,arr):
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "SetArrays" in split:
                self.SetArrays = arr[i].split('"')[1] 
            if "DrawArrays" in split:
                self.Indices = [int(x) for x in split[4:]]
            if "SetMaterial" in split:
                self.SetMaterial = arr[i].split('"')[1] 
            if "BlendIndices" in split:
                self.BlendIndices = [int(x) for x in split[2:]]

class Array:
    def __init__(self,arr):
        self.Name = arr[0].split()[1].replace('"','')
        self.POSITION = []
        self.NORMAL = []
        self.TEXCOORD = []
        self.WEIGHT = []
        self.INDICES = []
        #Parsing Array
        self.ParseArray(arr)
        
    def ParseArray(self,arr):
        Header = arr[0].split()[2].split('|')
        count = 0
        
        for i in arr[1:]:
            split = i.split() 
            if "POSITION" in Header:
                self.POSITION.append(NoeVec3([float(x) for x in split[count:count+3]]))
                count +=3
            if "NORMAL" in Header:
                self.NORMAL.append(NoeVec3([float(x) for x in split[count:count+3]]))
                if "NORMAL2" in Header:
                    count +=6
                else:
                    count +=3
            if "COLOR" in Header:
                count +=4
            if "TEXCOORD" in Header:
                self.TEXCOORD.append(NoeVec3([float(x) for x in split[count:count+2]+[0]]))
                count +=2
            if "WEIGHT" in [x.rstrip('0123456789') for x in Header]:
                num = 0
                try: num = int(Header[[Header.index(x) for x in Header if "WEIGHT" in x.rstrip('0123456789')][0]].replace("WEIGHT",""))
                except: num = 1
                self.WEIGHT.append([float(x) for x in split[count:count+num]])
                count +=num
                if "INDICES" in Header:
                    self.INDICES.append([int(x) for x in split[count:count+num]])
                    count +=num
                else:
                    self.INDICES.append([int(x) for x in range(0,num)])
                    count +=num
            count = 0

class Material:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Layers = []
        
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "Layer" in split:
                self.Layers.append(Layer(FindBracket(arr[i:])))

class Layer:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.SetTexture = ""
        
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "SetTexture" in split:
                self.SetTexture = arr[i].split('"')[1]

class Texture:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.FileName = ""
        self.UVTranslate = NoeVec3((0,0,0))
        self.UVScale = NoeVec3((1,1,0))
    
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "FileName" in split:
                self.FileName = arr[i].split('"')[1]
            if "UVTranslate" in split:
                self.UVTranslate = NoeVec3([float(x) for x in split[1:]+[0]])
            if "UVScale" in split:
                self.UVScale =  NoeVec3([float(x) for x in split[1:]+[0]])
                
class Bone:
    def __init__(self,arr):
        self.Name = ""
        self.ParentBone = ""
        self.DrawPart = ""
        self.Mat43 = NoeMat43()
        self.Scale = NoeVec3((1,1,1))
        self.BlendBones = []
        #function
        self.ParseBone(arr)
        
    def ParseBone(self,arr):
        self.Name = arr[0].split('"')[1]
        Translate = NoeVec3()
        Rotate = NoeQuat()
        #Scale = NoeVec3((1,1,1))
        
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "ParentBone" in split:
                self.ParentBone = arr[i].split('"')[1]
            if "Translate" in split:
                Translate = NoeVec3([round(float(x),4) for x in arr[i].replace('Translate','').split()])
            if "Rotate" in split:
                Rotate = NoeQuat([float(x) for x in arr[i].replace('Rotate','').split()])
            if "Scale" in split:
                self.Scale = NoeVec3([float(x) for x in arr[i].replace('Scale','').split()])
            if "BlendBone" in split:
                self.BlendBones.append(BlendBone(arr[i:i+5]))
            if "DrawPart" in split:
                self.DrawPart = arr[i].split('"')[1]
                
        mat = Rotate.toMat43()
        mat[3] = Translate
        #mat[0][0] = Scale[0]
        #mat[1][1] = Scale[1]
        #mat[2][2] = Scale[2]
        self.Mat43 = mat.transpose()
        
class BlendBone:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Mat43 = NoeMat43()
        
        for i,line in enumerate(arr[1:]):
             self.Mat43[i] = [float(x) for x in line.replace('\\','').split()[:3]]

class WeightedCenter:
    def __init__(self,line):
        self.Value = NoeQuat([float(x) for x in line.split()[2:]])
        self.index = line.split()[1]
        
class Motion:
    def __init__(self,arr):
        self.Name = arr[0].split('"')[1]
        self.Start = 0
        self.Frame = 0
        self.FrameRate = 0.0
        self.Animates = []
        self.FCurves = []
        #Parsing motions
        self.ParseMotion(arr)
        
    def ParseMotion(self,arr):
        for i in range(0,len(arr)):
            split = arr[i].split()
            if "FrameLoop" in split:
                self.Start = int(float(split[1]))
                self.Frame = int(float(split[2]))
                if self.Start==0:
                    self.Frame += 1
            if "FrameRate" in split:
                self.FrameRate = float(split[1])
            if "Animate" in split:
                self.Animates.append(Animate(arr[i]))
            if "FCurve" in split:
                self.FCurves.append(FCurve(FindBracket(arr[i:]),self.Frame,self.Start))

class Animate:
    def __init__(self,line):
        self.BoneName = line.split('"')[1].split('::')[1]
        self.Type = line.split()[2]
        self.CountCurve = line.split()[3]
        self.Curve = line.split()[4].replace('"','')

class FCurve:
    def __init__(self,arr,count,start):
        split = arr[0].split()
        self.Name = split[1].replace('"','')
        self.Type = split[2]
        self.Unknow = split[3]
        self.Vec = split[4]
        self.Count = split[5]
        self.ArrFrame = []

        for i in arr[1:]:
            #self.ArrFrame.append([round(float(x),4) for x in i.split()])
            self.ArrFrame.append(i)
        
        new = [-1]*count#[-1 for i in range(count)]

        if len(self.ArrFrame) == 1:
            item = [round(float(x),6) for x in self.ArrFrame[0].split()[1:]]
            new = [item*1 for i in range(count)]
        else:
            for line in self.ArrFrame:
                i = int(float(line.split()[0]))#-1
                if start>0:
                    i-=1
                new[i] = [float(x) for x in line.split()[1:]]

            if new[-1] == -1:
                for i in reversed(new):
                    if i != -1:
                        new[-1] = i*1
                        break
                        
            if new[0] == -1:
                for i in new:
                    if i != -1:
                        new[0] = i*1
                        break

            for i,arr in enumerate(new):
                if arr == -1:
                    c = i+1
                    while c < count:
                        if new[c] != -1:
                            break
                        else:
                            c += 1
                    if c-i>0:
                        n = [self.linspace(new[i-1][x],new[c][x],(c-i)+2)[1:-1] for x in range(len(new[0]))]
                        for q in range(i,c):
                            new[q]=[n[x][abs(q-i)] for x in range(len(n))]
                    else:
                        new[i] = [self.linspace(new[i-1][x],new[i+1][x],3)[1:-1][0] for x in range(len(new[0]))]
                #new[i].insert(0, i+1)
        print(self.Name)   
        for i,item in enumerate(new):
            new[i].insert(0, i+1)
            print(new[i])
        self.ArrFrame = new
        
    def linspace(self, a, b, n=100):
        if n < 2:
            return b
        diff = (float(b) - a)/(n - 1)
        return [round(diff * i + a,6)  for i in range(n)]
```

[file3D.zip](https://drive.google.com/file/d/101xcvd6dOYax1oSPGMfsyvLF8DEa7G1V/view?usp=sharing)
[1.png](https://xentaxbackup.github.io/file/21344_1.png)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-06T21:30:21+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

> Reply from Durik256 ↑Tue Dec 07, 2021 1:30 am at Tue Dec 07, 2021 1:30 am
>
> incorrectly loads the positions of the mesh relative to the bones and the problem with animations ...
I'm confused myself and can't figure out what's wrong  (Nice going, though.  )
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-06T22:55:21+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

i gave up
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-06T23:01:21+00:00
- Post Title: Convert MDX/MDS from PS4 Themes to FBX

Don't do! You're on a very good way!  
(Sooner or later you will finish this, I'm pretty sure.  )

btw: very interesting,
for curve in motion.FCurves:

Only script I recall using "for fcurve in action.fcurves:" is mot_importer.py (Fate estella?)

It is using "keyframe_point.interpolation = 'LINEAR'"
I've to check this, may help me with another problem.

So, thanks for your script. And this "side effect".
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-21T00:21:49+00:00
- Post Title: Re: Convert MDX/MDS from PS4 Themes to FBX

> Reply from shakotay2 ↑Tue Dec 07, 2021 7:01 am at Tue Dec 07, 2021 7:01 am
>
> 
Don't do! You're on a very good way!
you are a good motivator 

> Reply from shakotay2 ↑Tue Dec 07, 2021 7:01 am at Tue Dec 07, 2021 7:01 am
>
> 
'LINEAR'"
I didn't know then that Noesis had Vec3.lerp and Quat.slerp. 

After a long time decided to take a look at my first plugin.
Apart from the incorrect spherical linear interpolation. I made a mistake in parsing the name "curve" because of which all the bones with a space in the name did not receive a matrix.  


Now all animations play correctly.
It remains to solve the problem with the positioning of the mesh.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-21T07:42:30+00:00
- Post Title: Re: Convert MDX/MDS from PS4 Themes to FBX

> Reply from Durik256 ↑Fri Jan 21, 2022 8:21 am at Fri Jan 21, 2022 8:21 am
>
> 
shakotay2 wrote: ↑Tue Dec 07, 2021 7:01 am
Don't do! You're on a very good way! 

you are a good motivatorWell, to be honest, guess I'm good in recognizing people I can profit from.  
(And I felt you might have that spirit/intuition I always missed or had partially only.  )
## Post #18
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-23T21:27:07+00:00
- Post Title: Re: Convert MDX/MDS from PS4 Themes to FBX

how to use "BlendBones"?
i multiply blendbone matrix by vertex then multiply by bone matrix.
this works if the vertex is affected by 1 bone, but if there are more than that it's a mess.
[Files.zip](https://drive.google.com/file/d/1o6Qeaix6IcYsSwOp8pF8WwFSARlfwihm/view?usp=sharing)

[fmt_mds.zip](https://xentaxbackup.github.io/file/22103_fmt_mds.zip)
## Post #19
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-31T06:28:51+00:00
- Post Title: Re: Convert MDX/MDS from PS4 Themes to FBX

just a quick edit of my old script from the previous post.

[fmt_mds.zip](https://xentaxbackup.github.io/file/23368_fmt_mds.zip)
