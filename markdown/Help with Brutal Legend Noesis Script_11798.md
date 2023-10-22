## Post #1
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-08-17T04:52:08+00:00
- Post Title: Help with Brutal Legend Noesis Script?

I'm trying to write a Noesis plugin to load Brutal Legend meshes. I think I figured most of the header out, and I figured out that
meshes are in the order of the materials listed. I think I found the vert and face count and found the face buffer which is a the bottom of the file.
So everything else between should be Vert, Normal and UV. Since I've never done any of this before I'm kinda flying in the dark.

This is what  I got 

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Brutal Legend", ".meshFix")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "hsem"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) > 16:
      return 1
   #if bs.readBytes(32).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
   #   return 0
   #return 1

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   bs.seek(0x54, NOESEEK_ABS) #Seek to header info
   MatCount = bs.read("i")
   print(MatCount)
   bs.seek(0x3, NOESEEK_REL) #Seek to header info
   bs.seek(0x1, NOESEEK_REL) #Seek to header info
   #MatCharCount = bs.readUInt()Materials are in Model Order
   #bs.seek(0x3, NOESEEK_REL) #Seek past junk
   MatNames = []
   for i in range(0, MatCount[0]):
      MatNames.append (bs.readString())
   print(MatNames)
   bs.seek(0x14, NOESEEK_REL) #Seek past junk
   VertCount = bs.read("i")
   print(VertCount)
   pos = bs.tell()
   print(pos)
   bs.seek(0x0E, NOESEEK_REL) #Seek past junk
   FaceCount = bs.read("i")
   print(FaceCount)
   pos = bs.tell()
   print(pos)
   bs.seek(0xE0, 0) #Seek past junk
   pos = bs.tell()
   print(pos)
   VertBuff = bs.readBytes(VertCount[0] * 0x28)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 36, 0)
   #rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 36, 16)
   #rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 36, 28)
   rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertCount[0], noesis.RPGEO_POINTS, 1)
   pos = bs.tell()
   print(pos)
   FaceBuff = bs.readBytes(FaceCount[0] * 3)
   #rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FaceCount[0], noesis.RPGEO_TRIANGLE, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
   #print(MatCharCount)
   rapi.rpgClearBufferBinds()   
   return 1

```


And this is what I'm working on "[https://www.dropbox.com/s/udlmxpk9i892t ... endbox.zip](https://www.dropbox.com/s/udlmxpk9i892tiu/BrutalLegendbox.zip)". I figure if I can figure out a box I should be able to work with other meshes with 1 material.

Any advice would be great.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-17T10:44:11+00:00
- Post Title: Help with Brutal Legend Noesis Script?

how should anyone help you if you don't tell the whole truth?  

You commented out rapi.rpgCommitTriangles(). So why?
Guess because of this error: "RuntimeError: Position buffer would have been read out of bounds by provided indices."

Don't know why it complains about the position buffer since it's a problem of the FaceBuffer. Maybe it's reading random faceindices past the file's end then tries to address non existing vertexes.

Whatever. Your fault is to confuse faceindices and faces, your FaceCount (=36) is the FaceIndexCount.
this is the correct line:
FaceBuff = bs.readBytes(FaceCount[0] *2) # rename FaceCount to FaceIndexCount!
It's *2 because each face index is a Word.

But the result is more a plane than a box. Didn't bother checking this in depth.



plane_box.JPG (36.46 KiB) Viewed 428 times



btw. don't worry about your simple problem. Saw you used print commands to control your work. Very good!
Only suggestion would be to use it such as
print("counts verts, faceindices: %d, %d" %(VertCount[0], FaceIndexCount[0])) 
and
print("addr 0x%x" %(pos))    # hex address

UVpos most likely to be 24, Word (uint16) (/ 16384.0 or similar), USHORT in Noesis
upps, well, USHORT seems to apply to the vertices, too.

edit:
(there's another error in your script, tested the model in hex2obj only atm.)
You'll need to learn the basics. The vertex stride is 40 (0x28), so you must use it here:
rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 40, 0)

Maybe check the models using hex2obj (view link in my sig) before writing a suitable script for Noesis, 3dsmax, blender, whatever.
btw. in hex2obj switch format from float to WordAll
## Post #3
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-08-17T19:55:06+00:00
- Post Title: Help with Brutal Legend Noesis Script?

Appreciate the input! I'll certainly look into this (as far as the script is concerned) when I'm back at my regular computer. In the mean time I tried that program on a more complected model than the Box and I changed from WordAll to HF_all and pushed the strip button and it came out perfect-ish, normals are inverted but thats an easy fix.



I can't tell from my current position if the UVs are right though.

Is there something special about that strip button that I need to look out for when I fix my script?
[OphHeart.PNG](https://xentaxbackup.github.io/file/7677_OphHeart.PNG)
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-08-23T00:31:08+00:00
- Post Title: Help with Brutal Legend Noesis Script?

> Reply from shakotay2
>
> You commented out rapi.rpgCommitTriangles(). So why?
Guess because of this error: "RuntimeError: Position buffer would have been read out of bounds by provided indices."

Don't know why it complains about the position buffer since it's a problem of the FaceBuffer. Maybe it's reading random faceindices past the file's end then tries to address non existing vertexes.
The index buffer contains values out of range for the position array given the position array's size and stride, hence the position buffer would have been read out of bounds by the provided indices.

You could replace hex2obj with a 50-line Noesis script, exposing all of the fields settable in that GUI as variables defined at the top of the script, if you wanted. This way it would also be trivial to expand far beyond the scope of hex2obj and allow additional fields for other vertex components and such.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-23T07:00:52+00:00
- Post Title: Help with Brutal Legend Noesis Script?

well, seems you took it as offence as it was not meant to be.
What about catching this 'Runtime error'? or omitting a message like `check the face indices`?

> Reply from MrAdults
>
> You could replace hex2obj with a 50-line Noesis script, [...]Interesting thought.
And 'yes', I know, hex2obj is a poor tool.
But for me it's rather helpful and I guess for 3 or 4 guys, too.
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-08-23T15:52:05+00:00
- Post Title: Help with Brutal Legend Noesis Script?

I'm not sure how those words convey offense. I'm just taking care of business. Maybe it's the "well, time to address more crap that I don't even care to but still feel mildly obliged to address" feeling conveying my dissatisfaction which is perceived as offense.

That *is* catching the error. I've written explicit checks for analyzing the index/vertex buffers and passing back appropriate errors (like the one above telling you that your index buffer contains values out of range for reading your position buffer) if you're doing something terrible. I guess you didn't get that "provided indices" refers to the index buffer. But it does. If anything, it's a problem with the lack of documentation as opposed to the error text.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-23T19:05:56+00:00
- Post Title: Help with Brutal Legend Noesis Script?

> Reply from MrAdults
>
> I guess you didn't get that "provided indices" refers to the index buffer.Be sure I got it. But are you sure all users of Noesis will do?
As I can see this discussion is leading to nothing. So let's stop it.
## Post #8
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-08-24T00:17:29+00:00
- Post Title: Help with Brutal Legend Noesis Script?

Got it, I think.



```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Brutal Legend", ".meshFix")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "hsem"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) > 16:
      return 1
   #if bs.readBytes(32).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
   #   return 0
   #return 1

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   bs.seek(0x54, NOESEEK_ABS) #Seek to header info
   BeginVertexWork = "BeginVertexWork"
   BeginFaceWork = "BeginFaceWork"
   MatCount = bs.read("i")
   print(MatCount)
   bs.seek(0x3, NOESEEK_REL) #Seek to header info
   bs.seek(0x1, NOESEEK_REL) #Seek to header info
   #MatCharCount = bs.readUInt()Materials are in Model Order
   #bs.seek(0x3, NOESEEK_REL) #Seek past junk
   MatNames = []
   for i in range(0, MatCount[0]):
      MatNames.append (bs.readString())
   print(MatNames)
   bs.seek(0x14, NOESEEK_REL) #Seek past junk
   VertCount = bs.read("i")
   print(VertCount)
   pos = bs.tell()
   print(pos)
   bs.seek(0x0E, NOESEEK_REL) #Seek past junk
   FaceCount = bs.read("i")
   print(FaceCount)
   pos = bs.tell()
   print(pos)
   #bs.seek(0xE0, NOESEEK_REL) #Seek past junk
   bs.seek(0x41, NOESEEK_REL) #Seek past junk
   pos = bs.tell()
   print(pos)
   print(BeginVertexWork)
   VertBuff = bs.readBytes(VertCount[0] * 0x28)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 40, 0)
   rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 40, 16)
   rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_HALFFLOAT, 40, 24)
   #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertCount[0], noesis.RPGEO_POINTS, 1)
   pos = bs.tell()
   print(pos)
   print(BeginFaceWork)
   FaceBuff = bs.readBytes(FaceCount[0] * 0x02)
   rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FaceCount[0], noesis.RPGEO_TRIANGLE_STRIP, 1)
   pos = bs.tell()
   print(pos)
   rapi.rpgSetMaterial(MatNames[0])
   material = NoeMaterial(MatNames, "")
   MatNames.append(material)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
   #print(MatCharCount)
   rapi.rpgClearBufferBinds()   
   return 1
```


That should handle most of the heavy lifting. It was freaking out when it reached the very end of the Face/Face Index/Whatever Buffer. I just added an extra byte and it worked. Now its on to multi-material models and then models with bones.
## Post #9
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-09-01T04:34:11+00:00
- Post Title: Help with Brutal Legend Noesis Script?

Going well so far. Could I get some help with the Rigs? [https://www.dropbox.com/s/0afwqfvywtpma ... 2.zip?dl=0](https://www.dropbox.com/s/0afwqfvywtpma3g/spine2.zip?dl=0)
As far as I can see there are 7 offsets listed at the bottom of the header. The second and third one seem to be some kind of parenting information. But I can't tell which one contains position information. Any help would be great.

I also updated the script. The locations where the vertex and index counts are defined are different for every model, so I just added a place to put the TSBS locations to grab the counts and "s" defines which submesh to load. Also some rig experiments. Clearly, its very messy. It is also currently set up for the mesh in this post.

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Brutal Legend", ".MeshFix")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "hsem"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) > 16:
      return 1
   #if bs.readBytes(32).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
   #   return 0
   #return 1

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   #bs.seek(0x54, NOESEEK_ABS) #Seek to header info

   #Manual Entery Required!
   MatCountLOC = (84)
   tsbsLOC = [592, 696, 814, 915, 1046, 1177, 1277, 1391, 1491, 1617, 1729, 1829, 1930, 2031, ]
   MeshStart = [2135]
   bs.seek(MatCountLOC, NOESEEK_ABS)
   MatCount = bs.read("L")   
   MatNames = []
   #Do GETMATNAMES - Static

   
   for i in range(0, MatCount[0]):
      pos = bs.tell()
      print(pos)
      MatCharCount = bs.readUInt()#Materials are in Model Order
      MatNames.append (bs.readBytes(MatCharCount).decode("ASCII").rstrip("\0"))

   print(MatNames)
   

   VertCount = []
   FaceCount = []
   FaceType = []
   VertType = []
   MatID = []
   MeshCount = bs.read("I")
   print(MeshCount)


   for i in range(0, MeshCount[0]):
      bs.seek(tsbsLOC[i], NOESEEK_ABS)
      ReadSBST = bs.readUInt()
      MatID.append (bs.readUInt())
      MeshID = bs.readUInt()
      BVXD = bs.readUInt()
      #if VertBuffSig != CorrectVertBuffSig
         #noesis.doException("VertSig Incorrect" + repr(VertBuffSig))
      #pos = bs.tell()
      #print("Got Vert From", pos)
      VertCount.append (bs.readUInt())
      VertType.append (bs.readUInt())
      bs.seek(2, NOESEEK_REL)
      BIXD = bs.readUInt()
      Nothing = bs.readUInt()
      pos = bs.tell()
      print("Got Face From", pos)
      FaceCount.append (bs.readUInt())
      FaceType.append (bs.readUInt())

   print("Vert Count:", VertCount)
   print("Vert Type:", VertType)
   print("Face Count:", FaceCount)
   print("Face Type:", FaceType)
   pos = bs.tell()
   print(pos)


   #Do Bones We rig. Now
   if VertType[0] == 1024:
      rigFile = rapi.loadPairedFile("Brutal Legend", ".RigHeader")
      rig = NoeBitStream(rigFile)
      boneList = []
      Blank2 = rig.readUInt()
      Float1 = rig.readHalfFloat()
      Float2 = rig.readHalfFloat()
      Float3 = rig.readHalfFloat()
      Float4 = rig.readHalfFloat()
      BoneNameSize = rig.readUInt()
      BoneCount = rig.read("L") 
      UNK3 = rig.readUInt()
      UNK4 = rig.readUInt()
      UNK5 = rig.readUInt()
      UNK6 = rig.readUInt()
      UNK7 = rig.readUInt()
      UNK8 = rig.readUInt()
      UNK9 = rig.readUInt()
      UNK10 = rig.readUInt()
      UNK11 = rig.readUInt()
      Float6 = rig.readFloat()
      UNK12 = rig.readUInt()
      UNK13 = rig.readUInt()
      UNK14 = rig.readUInt()
      rig.seek(76, NOESEEK_ABS)
      Offset1 = rig.readUInt()
      Offset2 = rig.readUInt()
      Offset3 = rig.readUInt()
      Offset4 = rig.readUInt()
      Offset5 = rig.readUInt()
      Offset6 = rig.readUInt()
      Offset7 = rig.readUInt()
      Blank2 = rig.readUInt()
      pos = rig.tell()
      print("I am At", pos, "For RigSig")
      print(BoneCount)
      RigSig = rig.readUInt()
      print("The Rig Sig is", RigSig)
      print("RigNameSizeIs", BoneNameSize)
      rigSource = rapi.loadPairedFile("Brutal Legend", ".RigFix")
      rigsource = NoeBitStream(rigSource)
      
      BoneNames = []
      BoneNames.append (rigsource.readBytes(BoneNameSize).decode("ASCII").rstrip("\0"))
      print("Bone Names", BoneNames)
      print(Offset1)
      rigsource.seek(Offset5, NOESEEK_ABS)
      BoneID = []
      boneList2 = list(boneList)
      pos = rigsource.tell()
      print("First", pos)
      for i in range(0, BoneCount[0]):
         #rigsource.seek(2, NOESEEK_REL)
         #pos = rigsource.tell()
         #print("First1", pos)
         #Gibber = rigsource.readUInt() 
         BONE_XPOS = rigsource.readHalfFloat()
         BONE_YPOS = rigsource.readHalfFloat()
         BONE_ZPOS = rigsource.readHalfFloat()
         #pos = rigsource.tell()
         #print("First2", pos)
         BoneID.append (i)
         quat = NoeQuat([0, 0, 0, 1])
         mat = quat.toMat43()
         mat[3] = [BONE_XPOS, BONE_YPOS, BONE_ZPOS]
         boneList2.append(NoeBone(i, "bone%03i"%i, mat, None, BoneID[i]))
         boneList = rapi.multiplyBones(boneList2)
         #pos = rigsource.tell()
         #print("First3", pos)
         


   bs.seek(MeshStart[0], NOESEEK_ABS)
   VertBuff = []
   FaceBuff = []
   BoneBuff = []
   s = int(3) 


      
   if VertType[s] == 512:
      for i in range(0, MeshCount[0]):
            pos = bs.tell()
            print("Where Am I?", pos)
            VertBuff.append (bs.readBytes(VertCount[i] * 40))
            pos = bs.tell()
            print("VertDone, Where Am I?", pos)
            FaceBuff.append (bs.readBytes(FaceCount[i] * 0x02))
            pos = bs.tell()
            print("FaceDone, Where Am I?", pos)


   if VertType[s] == 1024:
      for i in range(0, MeshCount[0]):
            pos = bs.tell()
            print("Where Am I?", pos)
            #BlockUNK1 = bs.readUInt()
            #BlockUNK2 = bs.readUInt()
            pos = bs.tell()
            print("VertBegin, Where Am I?", pos)
            VertBuff.append (bs.readBytes(VertCount[i] * 48))
            pos = bs.tell()
            print("VertDone, FaceBegin, Where Am I?", pos)
            FaceBuff.append (bs.readBytes(FaceCount[i] * 0x02))
            pos = bs.tell()
            print("FaceDone, Where Am I?", pos)


   if VertType[s] == 512:
      rapi.rpgBindPositionBufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 40, 0)
      rapi.rpgBindNormalBufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 40, 16)
      #rapi.rpgBindColorBuffer(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 40, 20, 3)
      rapi.rpgBindUV1BufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 40, 24)
      rapi.rpgBindUV2BufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 40, 32)
      print("Buffered")
      #VertBuff = None
      #bs.seek(-216, NOESEEK_REL)
      #VertBlockFix = bs.read(FirstVertBlock * 40)
      #bs.seek(FirstVertBlock)
      #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertCount[i], noesis.RPGEO_POINTS, 1)
   if VertType[s] == 1024:
      print("Buffering")
      rapi.rpgBindPositionBufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 48, 8)
      rapi.rpgBindNormalBufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 48, 32)
      rapi.rpgBindUV1BufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 48, 16)
      rapi.rpgBindUV2BufferOfs(VertBuff[s], noesis.RPGEODATA_HALFFLOAT, 48, 24)
      #VertBuff = None
      #bs.seek(-216, NOESEEK_REL)
      #VertBlockFix = bs.read(FirstVertBlock * 40)
      #bs.seek(FirstVertBlock)
      #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VertCount[i], noesis.RPGEO_POINTS, 1)

   if FaceType[s] == 2:
      rapi.rpgCommitTriangles(FaceBuff[s], noesis.RPGEODATA_USHORT, FaceCount[s], noesis.RPGEO_TRIANGLE, 1)
   else:
      rapi.rpgCommitTriangles(FaceBuff[s], noesis.RPGEODATA_USHORT, FaceCount[s], noesis.RPGEO_TRIANGLE_STRIP, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
   mdl.setBones(boneList)
   rapi.rpgClearBufferBinds()
   
   rapi.rpgSetMaterial(MatNames[0])
   material = NoeMaterial(MatNames, "")
   material.setTexture(MatNames[0])
   MatNames.append(material)
   

   #print(MatCharCount)
   rapi.rpgClearBufferBinds()   
   return 1

```
## Post #10
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-09-04T22:26:42+00:00
- Post Title: Help with Brutal Legend Noesis Script?

In case anyone is interested, the Rig file seems to be a mutated version of a Havok skeleton. Brutal Legend uses Havok as its physics engine anyway. The first offset in the header points to some nonsense I don't understand but the second offset points to something that resembles the "parentIndices" section of a Havok skeleton. I barely understand that stuff and whats confusing is the area that should be the "referencePose" (offset 5 in the header, I think) doesn't produce anything resembling what should be the bone positions. Could anyone who understands Havok stuff offer an opinion on these assumptions?
## Post #11
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-09-14T21:03:09+00:00
- Post Title: Help with Brutal Legend Noesis Script?

When unpack I obtain *.mesh but not *.meshfix
can you help with this?

thanks in advance
