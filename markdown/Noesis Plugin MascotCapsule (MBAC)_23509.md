## Post #1
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-02-24T22:15:26+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

(.MBAC) 3d model in J2ME 
Hello everyone 
I wanted to make a plugin for Noesis ([adapt a ready-made solution](https://github.com/j2me-preservation/MascotCapsule)). 
But I am not familiar with python. (I working with C#) So nothing came out 
So, can someone help?

I attach an archive with scripts and a file
[here's another description of the format](https://github.com/j2me-preservation/MascotCapsule/blob/master/Format_Descriptions/MBAC.md)
[Files.zip](https://xentaxbackup.github.io/file/19597_Files.zip)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-04T23:22:58+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

more models
[models.zip](https://xentaxbackup.github.io/file/21564_models.zip)
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-06T02:18:10+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

models are already loaded but only with triangular faces, square faces give an error...
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T15:02:08+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

> Reply from Durik256 ↑Sat Mar 06, 2021 10:18 am at Sat Mar 06, 2021 10:18 am
>
> 
models are already loaded but only with triangular faces, square faces give an error...You could use
rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_UINT, numIdx, noesis.RPGEO_QUAD, 1)

But as you can see it's the "latest Noesis style" (rapi interface) while you seem to use the old one.

Read here (answer from  MrAdults):
[viewtopic.php?f=16&t=15997&p=128710&hil ... ns#p128710](https://forum.xentax.com/viewtopic.php?f=16&t=15997&p=128710&hilit=msh.setPositions#p128710)
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-06T22:21:09+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

Thanks for your answer, I will certainly study what you provided and try to redo everything with rapi.
But I decided for the time being in my own way)  

```
            a, b, c, d = face
            indices +=[c, b, a, d, b, c]

```




2.png (33.33 KiB) Viewed 101 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-07T07:00:57+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

> Reply from Durik256 ↑Sun Mar 07, 2021 6:21 am at Sun Mar 07, 2021 6:21 am
>
> 
Oh, thanks for your answer, I will certainly study what you provided and try to redo everything with rapi.
But I decided for the time being in my own way)

> Reply from MrAdults ↑Fri Mar 17, 2017 10:13 am at Fri Mar 17, 2017 10:13 am
>
> 
mariokart64n's tutorial uses the more manual means of constructing a mesh, which probably does seem more familiar to someone coming from Max.

So you need to choose the way which fits best for you.  

I can't help you with "old style", though. Also rapi is not my preferred way and, to be honest, I hate python generally.  

Usually I do I with 'C', view my Make_obj project (with C source), if interested:

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 

btw: feel free to convert that project to C#. (If you will do so I'd please you to make it available for others.)
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-13T01:43:36+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

support for bones and weights:

```
import noesis
import rapi
from mascotcapsule import Figure

def registerNoesisTypes():
   handle = noesis.register("MascotCapsule contains geometry data", ".mbac")
   noesis.setHandlerTypeCheck(handle, mbacCheckType)
   noesis.setHandlerLoadModel(handle, mbacLoadModel)
   noesis.logPopup()
   return 1

NOEPY_HEADER = "MB"

def mbacCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 2:
      return 0
   if bs.readBytes(2).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

def mbacLoadModel(data, mdlList):
   dirPath = rapi.getDirForFilePath(rapi.getInputName())
   filename = rapi.getLocalFileName(rapi.getInputName())
   f = open(dirPath + filename, 'rb')
   figure = Figure.fromfile(f, False)
   g = geometry(figure)
   b = Bones(figure.bones,len(g.positions))
   msh = NoeMesh([],[],"mesh0", "mat0")
   msh.setIndices(g.indices)
   msh.setPositions(g.positions)
   msh.setUVs(g.texcoord)
   msh.setNormals(g.normals)
   msh.setWeights(b.bWeList)
   mdl = NoeModel([msh],[],[])
   mdl.setBones(b.bones)
   mdlList.append(mdl)
   return 1
   
def mdl_create(g,figure):
    print('figure.vertices: %d' % len(figure.vertices))
    for x, y, z in figure.vertices:
        g.positions.append(NoeVec3((x,y,z)))
        g.texcoord.append(NoeVec3((0,0,0)))
    for face in figure.faces:
        if len(face) == 3:
            a, b, c = face
            for i in (c, b, a):
                g.indices.append(i)
                
        elif len(face) == 4:
            a, b, c, d = face
            for i in (c, b, a):
                g.indices.append(i)
            for i in (d, b, c):
                g.indices.append(i)               
                
        elif len(face) == 9:
            a, b, c, u1, v1, u2, v2, u3, v3 = face

            g.texcoord[a]=(NoeVec3([u1, v1, 0]))
            g.texcoord[b]=(NoeVec3([u2, v2, 0]))
            g.texcoord[c]=(NoeVec3([u3, v3, 0]))
                
            for i in (c, b, a):
                g.indices.append(i)
        else:
            a, b, c, d, u1, v1, u2, v2, u3, v3, u4, v4 = face
            g.texcoord[a]=(NoeVec3([u1, v1, 0]))
            g.texcoord[b]=(NoeVec3([u2, v2, 0]))
            g.texcoord[c]=(NoeVec3([u3, v3, 0]))
            g.texcoord[d]=(NoeVec3([u4, v4, 0]))
            
            for i in (c, b, a):
                g.indices.append(i)
            for i in (d, b, c):
                g.indices.append(i)
    
class geometry:
    def __init__(self,f):
        self.positions = []
        self.indices = []
        self.texcoord = []
        self.normals = []
        mdl_create(self,f)

class Bones:
    def __init__(self,b,v):
        self.bones = []
        self.boneMap = []
        #weight
        self.boWe = [1.0, 0.0, 0.0, 0.0]
        self.boId = [0, 0, 0, 0]
        self.bWeList = [NoeVertWeight(self.boId, self.boWe)]*v
        for i in range (0,len(b)):
            boneName = "bone"+str(i)
            bonePIndex = b[i][0]
            boneMat = NoeMat43(( 
            NoeVec3((b[i][1][0], b[i][1][4], b[i][1][8])), 
            NoeVec3((b[i][1][1], b[i][1][5], b[i][1][9])), 
            NoeVec3((b[i][1][2], b[i][1][6], b[i][1][10])), 
            NoeVec3((b[i][1][3], b[i][1][7], b[i][1][11])) ))
            #translate = NoeVec3((b[i][1][3],b[i][1][7],b[i][1][11]))
            #rotate = NoeQuat((0.0, 0.0, 0.0, 1.0))
            #boneMat = rotate.toMat43(transposed = 1)
            #boneMat[3] = translate
            self.bones.append(NoeBone(i,boneName,boneMat,None,bonePIndex))
            if b[i][3] - b[i][2] > 0:
                for x in range(b[i][2], b[i][3]):
                    self.bWeList[x] = NoeVertWeight([i, 0, 0, 0], self.boWe)
```

[3.png](https://xentaxbackup.github.io/file/21419_3.png)
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-09T17:09:18+00:00
- Post Title: Noesis Plugin MascotCapsule (MBAC)?

new plugin without "mascotcapsule .py"
(meshes, normals, uvs ,bones)
'uv need manual sczle in 3d editor'
[fmt_mbac.zip](https://xentaxbackup.github.io/file/21565_fmt_mbac.zip)
