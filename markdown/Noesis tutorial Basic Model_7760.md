## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-28T02:07:20+00:00
- Post Title: Noesis tutorial Basic Model

First thing is a quote from Señor Casaroja.

```
Yo bebo cuando tengo ocasión, ya veces cuando no tengo ocasión.
```


Ok so noesis now supports python scripting to import and export 3d models.
There are several great reasons to use noesis over other methods.
1.Tons of supported functions are already ready for us and do not need to be added like xbox and ps2 images.
2.No need to compile scripts can be tested in real time.
3.Very fast scripting language.
[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)


So the first thing you will want is a file format to add to noesis.
In our example we will use [X360]Strike Witches Shirogane no Tsubasa

First thing is use quickbms to extract our files the script is here for this game
[viewtopic.php?f=16&t=7751](http://forum.xentax.com/viewtopic.php?f=16&t=7751)

We end up with a bunch of files the files we care about are
player01.bin the file to extract
the texture files .dds
and the model files .gmo
So we will look at CH01_TOP.GMO

So first thing we need is a bare minimum noesis script

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1
```


So lets look at what we have here
handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
This line tells noesis what file type to use this script with
The first part is a text line that tells the user the name of the game "Strike Witches Shirogane no Tsubasa"
the second part is the actual file type of the format. ".gmo"

The next part
NOEPY_HEADER = "GXXM0124"
This is what this file format always starts out with and is very important to make sure noesis loads the correct script with our format.
We use this here

```
def noepyCheckType(data):
bs = NoeBitStream(data)
if len(data) < 16:
return 0
if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
return 0
return 1 
```


so in our example file the header is always
GXXM0124 with padding 00's to make it 16 bytes
so in noesis we did 2 checks
the first if len(data) < 16:
return 0
this says if our file is < 16 bytes it cant be a valid file
The next thing we do is declare a file stream
bs = NoeBitStream(data)
now with our file stream open we read 16 bytes as a string and see if it matches our header
if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
return 0
so then if both of these are true we return a 1 at the end and noesis will continue on to the next part of our script.
def noepyLoadModel(data, mdlList):
this says start the model loading process
then we need to create a context for our model
ctx = rapi.rpgCreateContext()
the next command clears out all buffers this is good to add at the end of your script to free up memory it also prevents noesis from throwing an error when no model is loaded
rapi.rpgClearBufferBinds()
then finally we end our code with a success command
return 1

now if you run this code you should get this when you open the model


Now we want to start reading our format so
the first interesting part of our data is at 0x1C
So we see to that offset
bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
Here i see 3 values i want to read as little endian values. "normally 360 games are big endian games this game was just written so bad they dint bother to change it from pc format"
hdrInfo = bs.read("iii")
if this was big endian all you have to do in python is change it to this
hdrInfo = bs.read(">iii")
the i stands for integer in python this is a great reference table for the possible values
[http://docs.python.org/library/struct.html](http://docs.python.org/library/struct.html)
[http://www.tutorialspoint.com/python/py ... rators.htm](http://www.tutorialspoint.com/python/python_basic_operators.htm)
this command stored 3 little endian ints into the array hdrInfo
so if we do
print(hdrInfo)
we get this in our output window
(1, 23, 1)
which is perfect as the data we read looked like this

```
01 00 00 00 17 00 00 00 01 00 00 00
```

the next piece of information we want is at offset 0x34
so ill seek to that offset but this time i will seek relative to my current position 0x28
bs.seek(0xC, NOESEEK_REL) #Seek past junk
This next value is the vertex count so
VCount = bs.read("i")
then we skip 4 bytes
bs.seek(0x4, NOESEEK_REL) #Seek past junk
and read the face count
FCount = bs.read("i")
OK that's all we really need from the header so now we seek to the start of the data.
bs.seek(0x70, NOESEEK_ABS) #Seek to File Start
ok so here remember we read those 3 values into our array we will use them now those values represented
Texture Count 1
Bone Count 23
Material Count 1
so we make a loop to read our texture name(s)
TexNames = []
for i in range(0, hdrInfo[0]):
TexNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
and we will print it to verify it looks right
print(TexNames)
So now our output looks like this
(1, 23, 1)
['ch01_mm.tga']
Perfect.
So your script should be like this now.

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
   hdrInfo = bs.read("iii")
   print(hdrInfo)
   bs.seek(0xC, NOESEEK_REL) #Seek past junk
   VCount = bs.read("i")
   bs.seek(0x4, NOESEEK_REL) #Seek past junk
   FCount = bs.read("i")
   bs.seek(0x70, NOESEEK_ABS) #Seek to File Start
   TexNames = []
   for i in range(0, hdrInfo[0]):
      TexNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
   print(TexNames)
   rapi.rpgClearBufferBinds()   
   return 1

```

Ok next come the bones
The bone format is 32 bytes bone name and 0x40 bytes bone data
so for now we will just import the name and worry about the data later
BoneNames = []
for i in range(0, hdrInfo[1]):
BoneNames.append (bs.readBytes(32).decode("ASCII").rstrip("\0"))
bs.seek(0x40, NOESEEK_REL) #Seek past bone stuff
print(BoneNames)
and the output from the print command is

```
['ch01_top_BackCloth', 'ch01_top_BackHair', 'ch01_top_BackHair2', 'ch01_top_FrontCloth', 'ch01_top_FrontHair', 'ch01_top_Gun', 'ch01_top_Head', 'ch01_top_LeftArm', 'ch01_top_LeftEar', 'ch01_top_LeftFinger', 'ch01_top_LeftForeArm', 'ch01_top_LeftHand', 'ch01_top_LeftShoulder', 'ch01_top_RightArm', 'ch01_top_RightEar', 'ch01_top_RightFinger', 'ch01_top_RightForeArm', 'ch01_top_RightHand', 'ch01_top_RightShoulder', 'ch01_top_Spine', 'ch01_top_Spine1', 'ch01_top_Top', 'ch01_top_neck']
```

So next is the material section
this section's size in total is 0x130
and is broken down by
0xC0 -stuff
0x28 -Material Name
0x48 -stuff
so for now we will once again read in the name
MaterialNames = []
for i in range(0, hdrInfo[2]):
bs.seek(0xC0, NOESEEK_REL) #Seek past Material stuff
MaterialNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
bs.seek(0x48, NOESEEK_REL) #Seek past Material stuff
print(MaterialNames)
Ok so now we are at the vertex data
0xA68
each vertex is 0x58 in size
so noesis has a very nice way to get this data for us.
VertBuff = bs.readBytes(VCount[0] * 0x58)
so now that we read all that data into a buffer we can parse that buffer
rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 0)
this says read 3 flaots at position 0 in the VertBuff and that each vertex is 88 bytes
Now we can test this quickly with these lines here
rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
mdl = rapi.rpgConstructModel()
mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList

So now we have this

and here is our code so far

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
   hdrInfo = bs.read("iii")
   print(hdrInfo)
   bs.seek(0xC, NOESEEK_REL) #Seek past junk
   VCount = bs.read("i")
   bs.seek(0x4, NOESEEK_REL) #Seek past junk
   FCount = bs.read("i")
   bs.seek(0x70, NOESEEK_ABS) #Seek to File Start

   TexNames = []
   for i in range(0, hdrInfo[0]):
      TexNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
   print(TexNames)


   BoneNames = []
   for i in range(0, hdrInfo[1]):
      BoneNames.append (bs.readBytes(32).decode("ASCII").rstrip("\0"))
      bs.seek(0x40, NOESEEK_REL) #Seek past bone stuff
   print(BoneNames)

   MaterialNames = []
   for i in range(0, hdrInfo[2]):
      bs.seek(0xC0, NOESEEK_REL) #Seek past Material stuff
      MaterialNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
      bs.seek(0x48, NOESEEK_REL) #Seek past Material stuff
   print(MaterialNames)

   VertBuff = bs.readBytes(VCount[0] * 0x58)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 0)
   rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)         #important, don't forget to put your loaded model in the mdlList

   rapi.rpgClearBufferBinds()   
   return 1
```

so now that we know our verts are good we can try to load the faces so
comment out
#rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
and put
FaceBuff = bs.readBytes(FCount[0] * 2)
rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FCount[0], noesis.RPGEO_TRIANGLE, 1)
you might notice the model looks transparent without turning off face culling if thats the case just add this line
rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)

So now you have

and the code

```
from inc_noesis import *
import noesis
#rapi methods should only be used during handler callbacks
import rapi
#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
   bs = NoeBitStream(data)
   bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
   hdrInfo = bs.read("iii")
   print(hdrInfo)
   bs.seek(0xC, NOESEEK_REL) #Seek past junk
   VCount = bs.read("i")
   bs.seek(0x4, NOESEEK_REL) #Seek past junk
   FCount = bs.read("i")
   bs.seek(0x70, NOESEEK_ABS) #Seek to File Start

   TexNames = []
   for i in range(0, hdrInfo[0]):
      TexNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
   print(TexNames)


   BoneNames = []
   for i in range(0, hdrInfo[1]):
      BoneNames.append (bs.readBytes(32).decode("ASCII").rstrip("\0"))
      bs.seek(0x40, NOESEEK_REL) #Seek past bone stuff
   print(BoneNames)

   MaterialNames = []
   for i in range(0, hdrInfo[2]):
      bs.seek(0xC0, NOESEEK_REL) #Seek past Material stuff
      MaterialNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
      bs.seek(0x48, NOESEEK_REL) #Seek past Material stuff
   print(MaterialNames)

   VertBuff = bs.readBytes(VCount[0] * 0x58)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 0)
   #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
   FaceBuff = bs.readBytes(FCount[0] * 2)
   rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FCount[0], noesis.RPGEO_TRIANGLE, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)         #important, don't forget to put your loaded model in the mdlList

   rapi.rpgClearBufferBinds()   
   return 1
```

Ok so now we will add in our normals and uv coordinates.
rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 12)
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 48)

so now that we have our uv's all set we want to test them so lets make a material and assign the texture we think is needed to it.
so we need 2 arrays
texList = []
matList = []
Then we create our material with a diffuse texture
rapi.rpgSetMaterial("CH01_MM")
material = NoeMaterial("CH01_MM", "")
material.setTexture("CH01_MM.DDS")
matList.append(material)
and after we construct the model we pass
mdl.setModelMaterials(NoeModelMaterials(texList, matList))

So now we should get this result

and this should be your code so far

```
from inc_noesis import *
import noesis
#rapi methods should only be used during handler callbacks
import rapi
#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
   bs = NoeBitStream(data)
   bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
   hdrInfo = bs.read("iii")
   print(hdrInfo)
   bs.seek(0xC, NOESEEK_REL) #Seek past junk
   VCount = bs.read("i")
   bs.seek(0x4, NOESEEK_REL) #Seek past junk
   FCount = bs.read("i")
   bs.seek(0x70, NOESEEK_ABS) #Seek to File Start

   texList = []
   matList = []
   TexNames = []
   BoneNames = []
   MaterialNames = []

   for i in range(0, hdrInfo[0]):
      TexNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
   print(TexNames)

   for i in range(0, hdrInfo[1]):
      BoneNames.append (bs.readBytes(32).decode("ASCII").rstrip("\0"))
      bs.seek(0x40, NOESEEK_REL) #Seek past bone stuff
   print(BoneNames)

   for i in range(0, hdrInfo[2]):
      bs.seek(0xC0, NOESEEK_REL) #Seek past Material stuff
      MaterialNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
      bs.seek(0x48, NOESEEK_REL) #Seek past Material stuff
   print(MaterialNames)

   mname = "CH01_MM"
   material = NoeMaterial("CH01_MM", "")
   material.setTexture("CH01_MM.DDS")
   matList.append(material)

   VertBuff = bs.readBytes(VCount[0] * 0x58)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 0)
   rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 12)
   rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 48)
   FaceBuff = bs.readBytes(FCount[0] * 2)
   rapi.rpgSetMaterial("CH01_MM")
   rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FCount[0], noesis.RPGEO_TRIANGLE, 1)

   mdl = rapi.rpgConstructModel()
   mdl.setModelMaterials(NoeModelMaterials(texList, matList))

   mdlList.append(mdl)         #important, don't forget to put your loaded model in the mdlList
   rapi.rpgClearBufferBinds()   
   return 1
```

Now in the model CH01_TOP.GMO there is only one material and one texture but in CH01_UNDER.GMO There are 3 textures and 3 materials.
So in order to fix this we need to find out more about our materials.
I have found the relevant information in the material and here is the structure

Structure Material {
Long -Texture ID
0xBC -unkown / not needed "its probably some color information about the material"
Material Name 0x20
0x10 -unkown / not needed
Long - Material Start Indecie
Long - Number of indecies in the material
0x38 -unkown / not needed
}

So now that we know How our material is made up lets get that information stored for use.
we will change
MaterialNames = []
for i in range(0, hdrInfo[2]):
bs.seek(0xC0, NOESEEK_REL) #Seek past Material stuff
MaterialNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
bs.seek(0x48, NOESEEK_REL) #Seek past Material stuff
print(MaterialNames)

into
MaterialInfo = []
for i in range(0, hdrInfo[2]):
TexID = bs.read("i")
bs.seek(0xBC, NOESEEK_REL) #Seek past Material stuff
MaterialName = (bs.readBytes(32).decode("ASCII").rstrip("\0"))
bs.seek(0x10, NOESEEK_REL) #Seek past Material stuff
IndStart = bs.read("i")
IndCount = bs.read("i")
bs.seek(0x38, NOESEEK_REL) #Seek past Material stuff
MaterialInfo.append([MaterialName, TexID[0], IndStart[0], IndCount[0]])
print(MaterialInfo)

Now we will add a loop to create our materials with the texture assigned

for i in range(0, hdrInfo[2]):
material = NoeMaterial(MaterialInfo[0],"")
material.setTexture(TexNames[MaterialInfo[1]] + ".dds")
matList.append(material)
print(matList)

Now we need to have our faces load with the correct material so we use this
for i in range(0, hdrInfo[2]):
FaceBuff = bs.readBytes(MaterialInfo[3] * 2)
rapi.rpgSetMaterial(MaterialInfo[0]) #call this before before commit triangles it assignes this set of triangles to the material name given
rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, MaterialInfo[3], noesis.RPGEO_TRIANGLE, 1)

So now both models load with the correct textures and our code should look like this.

```
from inc_noesis import *
import noesis
#rapi methods should only be used during handler callbacks
import rapi
#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Strike Witches Shirogane no Tsubasa", ".gmo")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
   bs = NoeBitStream(data)
   bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
   hdrInfo = bs.read("iii")
   print(hdrInfo)
   bs.seek(0xC, NOESEEK_REL) #Seek past junk
   VCount = bs.read("i")
   bs.seek(0x4, NOESEEK_REL) #Seek past junk
   FCount = bs.read("i")
   bs.seek(0x70, NOESEEK_ABS) #Seek to File Start

   texList = []
   matList = []
   TexNames = []
   BoneNames = []
   MaterialInfo = []

   for i in range(0, hdrInfo[0]):
      TexNames.append (rapi.getExtensionlessName(bs.readBytes(40).decode("ASCII").rstrip("\0")))
   print(TexNames)

   for i in range(0, hdrInfo[1]):
      BoneNames.append (bs.readBytes(32).decode("ASCII").rstrip("\0"))
      bs.seek(0x40, NOESEEK_REL) #Seek past bone stuff
   print(BoneNames)

   for i in range(0, hdrInfo[2]):
      TexID = bs.read("i")
      bs.seek(0xBC, NOESEEK_REL) #Seek past Material stuff
      MaterialName = (bs.readBytes(32).decode("ASCII").rstrip("\0"))
      bs.seek(0x10, NOESEEK_REL) #Seek past Material stuff
      IndStart = bs.read("i")
      IndCount = bs.read("i")
      bs.seek(0x38, NOESEEK_REL) #Seek past Material stuff
      MaterialInfo.append([MaterialName, TexID[0], IndStart[0], IndCount[0]])
   print(MaterialInfo)

   for i in range(0, hdrInfo[2]):
      material = NoeMaterial(MaterialInfo[i][0],"")
      material.setTexture(TexNames[MaterialInfo[i][1]] + ".dds")
      matList.append(material)
      print(matList)

   VertBuff = bs.readBytes(VCount[0] * 0x58)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 0)
   rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 12)
   rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 48)
   for i in range(0, hdrInfo[2]):
      FaceBuff = bs.readBytes(MaterialInfo[i][3] * 2)
      rapi.rpgSetMaterial(MaterialInfo[i][0])
      rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, MaterialInfo[i][3], noesis.RPGEO_TRIANGLE, 1)
   mdl = rapi.rpgConstructModel()
   mdl.setModelMaterials(NoeModelMaterials(texList, matList))
   mdlList.append(mdl)         #important, don't forget to put your loaded model in the mdlList   
   rapi.rpgClearBufferBinds()   
   return 1
```

[fmt_SW_GMO.rar](https://xentaxbackup.github.io/file/4886_fmt_SW_GMO.rar)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-11-28T07:31:43+00:00
- Post Title: Noesis tutorial Basic Model

Yo bebo cuando tengo ocasión, ya veces cuando no tengo ocasión. 

Great work, Chrrox!
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-11-30T08:16:30+00:00
- Post Title: Noesis tutorial Basic Model

> Reply from Mr.Mouse
>
> Great work, Chrrox!
Indeed.
## Post #4
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-11-30T08:29:26+00:00
- Post Title: Noesis tutorial Basic Model

> Reply from chrrox
>
> 
There are several great reasons to use noesis over other methods.

Thanks chrrox, this is just...so so awesome!
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-11-30T13:03:22+00:00
- Post Title: Noesis tutorial Basic Model

Thanks chrrox
I'm not completely sure, but sucess.
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-12-01T16:53:13+00:00
- Post Title: Noesis tutorial Basic Model

Nice one man! Hopefully will unlock alot of more importers etc
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-01T23:17:31+00:00
- Post Title: Noesis tutorial Basic Model

I'd like a template that I could just fill in without having to deal with the details.
Perhaps someone can make one such that I only have to write the parser function (otherwise I'll probably end up making one eventually after figuring out efficient ways to do it).

You know, something like

```
#register plugin and stuff
def ...

#load model
def ...

#build model
def ...

def...

#parser functions
def...

def...

def...

```


So for example you're reading vertex information, and then you want to pass it to the "builder" function that takes your list of vertices.
Of course, it could get complicated, but maybe for very common things like loading vertices or faces I just have to pass in a list and don't care what happens after.
## Post #8
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-06T17:38:47+00:00
- Post Title: Noesis tutorial Basic Model

Very good tutorial Mate, Thank You.
 
I've used this as the base to do the SWTOR exporter instead of codeing a stand alone program.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-11T07:52:15+00:00
- Post Title: Noesis tutorial Basic Model

Nice tutorial, followed it and the samples that came with noesis while writing a template 
The template is pretty much just me copying code from Sanae3D though, only because I'm used to it, and I like to use a lot of functions or methods. At least that way, I can re-use functions quickly without having to worry about whether it will conflict with any existing code.

```
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   parser = CrucisFatalFake_LMD(data)
   parser.parse_file()
   mdl = NoeModel(parser.meshList, None, None)
   mdlList.append(mdl)
   mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
   return 1

class CrucisFatalFake_LMD(object):
    
   def __init__(self, data):
       
      self.inFile = StructReader(data)
      self.meshList = []
      self.uvList = []
      self.vertList = ""
...

```


Now I just need to figure out how to assign materials flexibly...



Maybe parse entire file first, and then go through the data and start building meshes and stuff...

EDIT: There we go...now I want to load the textures directly from the file.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-15T07:00:34+00:00
- Post Title: Noesis tutorial Basic Model

lol chrrox your tutorials getting nuked.
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-15T13:02:37+00:00
- Post Title: Noesis tutorial Basic Model

meh not to big a deal.
I am going to wait for the restructure to be over before i post much to avoid it being lost.
also i don't think anyone ever used it since i didn't see any new people contribute to the site.
I don't think all these sites cared about file samples being posted i think the issue Google had was people directly linking to warez releases.
## Post #12
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-04-15T13:59:12+00:00
- Post Title: Noesis tutorial Basic Model

> Reply from chrrox
>
> also i don't think anyone ever used it since i didn't see any new people contribute to the site.

Hey! I know I don't brainfart a new script every hour like finale does, but I started with this tutorial for Noesis.
## Post #13
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2012-09-01T19:39:28+00:00
- Post Title: Noesis tutorial Basic Model

Hi Chrrox,

can i ask how do you use "MaterialInfo.append([MaterialName, TexID[0], IndStart[0], IndCount[0]])" the IndStart list? Because I cant see, as if it was used. If it's not than what tells to Noesis which set of face use which mat? Only the position in the list?
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-01T19:50:07+00:00
- Post Title: Noesis tutorial Basic Model

MaterialInfo.append([MaterialName, TexID[0], IndStart[0], IndCount[0]]) is just an array i made
it tells me how to load the mesh data correctly.
they just give a triangle list then they tell you how its broken down by materials.
so like say i had 90 faces
they would say break it down
start 0 count 25
then the next would be
start 25 count 15
then it would go
start 40 count x until no faces were left
and i am just assigning the materials to the faces as i load them.
## Post #15
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2012-09-01T23:54:02+00:00
- Post Title: Noesis tutorial Basic Model

thanks for the info, in the meantime i finished my plugin  just one thing left. How can i say "look for the textures in this folder". Because every folder have a texture folder and now i have to copy all texture file into the same folder as the file, and that is, hmm annoying. 
My code is based on your tutorial, i use rpg, nothing immediate draw and other fancy things.
## Post #16
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-09-02T12:40:27+00:00
- Post Title: Re: Noesis tutorial Basic Model

Try using something along the lines of:

```
dirPath        = rapi.getDirForFilePath(rapi.getInputName())
```

with

```
texture     = rapi.loadTexByHandler(tex,'.dds')
texture.name    = texName.split('.dds')[0] #//you can leave the .split() away if you want
texList.append(texture)



mdl.setModelMaterials(NoeModelMaterials(texList, matList))

```
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-02T13:00:45+00:00
- Post Title: Re: Noesis tutorial Basic Model

It should be enough to just specify the absolute path of the texture in the material and just set that as the texture.

I usually just tell people to create a "textures" folder and dump all the textures in there.
## Post #18
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-02T19:46:57+00:00
- Post Title: Re: Noesis tutorial Basic Model

```
from inc_noesis import *
import noesis
#rapi methods should only be used during handler callbacks
import rapi
#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
	handle = noesis.register("Rinne no Lagrange Kamogawa Dream Match", ".gcm")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
	noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
	return 1

NOEPY_HEADER = "PHYR"

#check if it's this type based on the data
def noepyCheckType(data):
	bs = NoeBitStream(data)
	if len(data) < 7:
		return 0
	if bs.readBytes(7).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
		return 0
  return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1

```

I'll wrote Noesis plugins.
I'm not sure whether I'm doing this right, so far.
Will you explain this part "if len(data) < 7:"?
Is this number right?


 GCM.7z
(84.24 KiB) Downloaded 63 times
## Post #19
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-02T20:33:07+00:00
- Post Title: Re: Noesis tutorial Basic Model

NOEPY_HEADER = "PHYR"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 7:
      return 0
   if bs.readBytes(7).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
  return 1 

should be

NOEPY_HEADER = "PHYR"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
  return 1 

this just checks to make sure the first 4 characters of the file are PHYR

also your file is big endian keep that in mind
## Post #20
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2012-09-03T09:40:13+00:00
- Post Title: Re: Noesis tutorial Basic Model

Hi, 

this time i don't ask for help   but it's somehow connected to file check. My plugin is ready, but every time i select the file format i only get an empty list in the viewer, but it occurs only under win7x64. The problem doesn't appear under xp.
Is there a workaround to solve this? I tried to run as admin but that didn't helped. 
Should I run Noe in compatibility mode? (I'm currently at work so i can't try it out, and it's so long until i get home )
## Post #21
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-09-03T10:06:41+00:00
- Post Title: Re: Noesis tutorial Basic Model

I run 7x64 and don't seem to have that problem, pm me the script and a model to test.

Does it occur if you just select "all known formats" ? Also, in the Noesis explorer try going to a parent fodler and back, see if that helps.
## Post #22
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-03T10:16:10+00:00
- Post Title: Re: Noesis tutorial Basic Model

Thank you very much for your quick reply.
May I ask a few questions?
I've got a lot to learn.
Actually, I don’t know what to question, at first.
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T12:49:43+00:00
- Post Title: Re: Noesis tutorial Basic Model

You should start by reading the tutorial.
## Post #24
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-03T13:44:47+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from finale00
>
> You should start by reading the tutorial.
Sorry, 
I'm a complete noob, please help.

I can't understand "bs.seek(0x1C, NOESEEK_ABS)" part.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T14:05:05+00:00
- Post Title: Re: Noesis tutorial Basic Model

There are several ways to go to different positions of a file (eg: seeking)

They are typically seeking from
-beginning of the file (absolute offset) eg: seek_abs
-current position (relative offset) eg: seek_curr
-end of file (seeking backwards)
## Post #26
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-03T14:43:27+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from finale00
>
> There are several ways to go to different positions of a file (eg: seeking)

They are typically seeking from
-beginning of the file (absolute offset) eg: seek_abs
-current position (relative offset) eg: seek_curr
-end of file (seeking backwards)
Thank you for your explanation.
But, i don't understand these code "0x1C".
## Post #27
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-09-03T15:12:56+00:00
- Post Title: Re: Noesis tutorial Basic Model

[http://en.wikipedia.org/wiki/Hexadecimal](http://en.wikipedia.org/wiki/Hexadecimal)

0x is the way to write hexadecimal
## Post #28
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-03T17:45:27+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from Demonsangel
>
> http://en.wikipedia.org/wiki/Hexadecimal

0x is the way to write hexadecimal
That's not what I want to know.
Why it was "1C" what I'd like to know.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T17:49:14+00:00
- Post Title: Re: Noesis tutorial Basic Model

This tutorial assumes you already know how to reverse models

You should read
[viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739)
## Post #30
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-03T17:53:40+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from finale00
>
> This tutorial assumes you already know how to reverse models

You should read
viewtopic.php?f=29&t=3739
Thanks, finale00
## Post #31
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-12T23:06:31+00:00
- Post Title: Re: Noesis tutorial Basic Model

I know this may sound dumb but i got lost in the very first steps.

I just did this:

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
	handle = noesis.register("S4 League", ".scn")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
	#noesis.setHandlerWriteModel(handle, noepyWriteModel)
	#noesis.setHandlerWriteAnim(handle, noepyWriteAnim)

	noesis.logPopup()
	print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
	return 1


#check if it's this type based on the data
def noepyCheckType(data):
	bs = NoeBitStream(data)
	if bs.readInt() != 0x01000000 :
		return 0
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	rapi.rpgClearBufferBinds()
	hdrInfo = bs.read("i")
	print(hdrInfo)	
	return 1

```


Not a big deal, just trying to read an int and in the guide it said it was going to be written in the output log, but only this shows up:



I think it has something to do with the header reading, but i don't know what to do.

I'm not sure if this is supposed to happen, since the images from the tutorial are missing and i'm not sure if i should continue  or not.

I know this is one of those mistakes that will make you be ashamed for life, but i don't know what is wrong, i'm sorry 

File i'm trying to read is attached in the post
[body.rar](https://xentaxbackup.github.io/file/7327_body.rar)
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-13T06:10:59+00:00
- Post Title: Re: Noesis tutorial Basic Model

use this line:
   if bs.readInt() != 0x00000001 :

because the signature 01 00 00 00 in the header is little endian.
## Post #33
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-14T01:46:38+00:00
- Post Title: Re: Noesis tutorial Basic Model

Thank you for your help shakotay2, once again you got me out of this nooby issues  

I got another question, how does the Vertex Buff actually works? Since in the guide they use the following:

```
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 0)
   rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)         #important, don't forget to put your loaded model in the mdlList

```


I don't really know what a vertex with a size of 88 bytes meant, so i started trying random numbers until one worked, which was 24.


[Using sword.scn](http://puu.sh/8Lrti.scn)
(Vertex count: 0x0986, after that there are 345 floats and the int that tells you the faces, which is positioned at 0x19B6, in this case are 282 faces)


the bad thing for this is that the number of the vertices, faces, uvs, etc are between the buffers, so the only way to be able to continue to get the number of faces is by using 0x04 instead of 0x18

So my question is, since the coordinates are made by floats,and since floats are 4 bytes, should i use 4 or should i use 24 and go back to the position of the faces count?, because if i do the last thing i said using FaceBuff = bs.readBytes(FCount[0] * 2) the following result appears:



Thanks in advance again ^^
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-15T12:48:13+00:00
- Post Title: Re: Noesis tutorial Basic Model

didn't get exactly what you mean.
use this for sword.scn (and only sword.scn):

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("S4 League", ".scn")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
   #noesis.setHandlerWriteModel(handle, noepyWriteModel)
   #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)

   noesis.logPopup()
   print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1


#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if bs.readInt() != 0x00000001 :
      return 0
   return 1


#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()
   hdrInfo = bs.read("i")
   print(hdrInfo)   
   # works for sword.scn only!
   bs.seek(0x982, NOESEEK_ABS)  #Seek to counts
   facesCount = bs.read("i")	# faces count
   vertsCount = bs.read("i")
   VertBuff = bs.readBytes(vertsCount[0] * 12)
   facesCount2 = bs.read("i")	# faces count again
   print(facesCount2)
   if facesCount2!=facesCount:
      print("error: 2nd facesCount doesn't match!")
      return 1
   idxBuff = bs.readBytes(facesCount[0] *2 *3)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 12, 0)
   #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, facesCount[0], noesis.RPGEO_POINTS, 1)
   rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, facesCount[0]*3, noesis.RPGEO_TRIANGLE, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)          #important, don't forget to put your loaded model in the mdlList

   return 1
```
it's just a quick hack - I'm not familiar with Noesis.

(Maybe it's a good idea to edit further questions into your previous post?
 So not to spam chrrox' tutorial.)
## Post #35
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-06-19T16:24:16+00:00
- Post Title: Re: Noesis tutorial Basic Model

You should bump chrrox's tutorial as much as you can.
## Post #36
- Username: clang7775
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 29, 2014 2:31 am
- Post datetime: 2014-09-28T18:43:06+00:00
- Post Title: Re: Noesis tutorial Basic Model

Thanks for the tutorial! Time to dust off my python skills (and indenting!)
## Post #37
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-10-30T09:28:16+00:00
- Post Title: Re: Noesis tutorial Basic Model

anyone have images for this this tutorial ?

thx ...
## Post #38
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-06-25T09:17:50+00:00
- Post Title: Re: Noesis tutorial Basic Model

Hello. i just began writing a script for a game and i think i got the wrong header because i get this error:


[http://sta.sh/21xrx3h6mxxn?edit=1](http://sta.sh/21xrx3h6mxxn?edit=1) - these are the model and the script,anyone able to tell me what's wrong and how to fix it?
## Post #39
- Username: MarieRose1301
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-06-25T09:33:10+00:00
- Post Title: Re: Noesis tutorial Basic Model

the string you are showing is not ascii and its not 16 bytes long.
try something like

NOEPY_HEADER = 0x334D430A

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readUInt() != NOEPY_HEADER:
      return 0
## Post #40
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-06-25T09:42:47+00:00
- Post Title: Re: Noesis tutorial Basic Model

It gives me an other error this time 
It's my first time writing a noesis plugin, so I'm a little bit lost here, sorry
## Post #41
- Username: MarieRose1301
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-06-25T10:00:04+00:00
- Post Title: Re: Noesis tutorial Basic Model

Here is a start for you.
[fmt_cm3d2.7z](https://xentaxbackup.github.io/file/9341_fmt_cm3d2.7z)
## Post #42
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-06-25T10:23:13+00:00
- Post Title: Re: Noesis tutorial Basic Model

Thank you so much, i hope there won't be any more problems ^^'
## Post #43
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-04-28T23:58:08+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from finale00
>
> There are several ways to go to different positions of a file (eg: seeking)

They are typically seeking from
-beginning of the file (absolute offset) eg: seek_abs
-current position (relative offset) eg: seek_curr
-end of file (seeking backwards)

So what is the correct syntax in Noesis for seeking to an offset from the end of a file?
i have been trying something like bs.seek(-44, 2) without success.
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-29T03:32:19+00:00
- Post Title: Re: Noesis tutorial Basic Model

"2" is ony valid when using import os, I guess - since there's
NOESEEK_ABS = 0 and NOESEEK_REL = 1 only.

I tried such (import os required)

```

   statinfo = os.stat(fileName)
   print("statinfo, file size: ", statinfo.st_size)
   fsize= statinfo.st_size
   with open(fileName, "rb") as f:
       #f.seek(fsize-11, os.SEEK_SET)
       f.seek(-11, 2)
       a= f.read()
       print("a: ", a)
```

where test.txt is an ASCII file, opened in binary mode (to avoid weird outputs from print())
Both f.seek lines worked - if you use f.seek(-11, 2) you don't need to get the file size!

But I dunno how to get the filename via rapi, when the file is opened in the Noesis file explorer -

bs = NoeBitStream(data)
bs.seek(-11, 2) didn't work.
## Post #45
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-04-30T00:18:43+00:00
- Post Title: Re: Noesis tutorial Basic Model

Okay thanks, i hoped there was something simple i was overlooking like NOESEEK_END i could use. i don't know enough about programming to make work what you have there. i will have to find another way 

editx2
okay this works 

```
    bs.seek(len(data) - 0x2C, NOESEEK_ABS) #goto 44 bytes from end of file
```
## Post #46
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-18T16:55:54+00:00
- Post Title: Re: Noesis tutorial Basic Model

The download link doesn't work. I really need this tool ASAP :)
## Post #47
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-11-06T05:20:54+00:00
- Post Title: Re: Noesis tutorial Basic Model

please re upload the images,tutorial without images are pretty useless.No offence.
## Post #48
- Username: dragoncrest
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 21, 2014 11:47 pm
- Post datetime: 2018-05-13T15:07:37+00:00
- Post Title: Re: Noesis tutorial Basic Model

can you make a tutorial about animation?
thanks.
## Post #49
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-20T21:02:54+00:00
- Post Title: Re: Noesis tutorial Basic Model

in noesis, how to skip junk data like texture path at the beginning of If the length of this path is before it?
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-20T22:05:52+00:00
- Post Title: Re: Noesis tutorial Basic Model

bs = NoeBitStream(data)
lenStr = bs.readUShort()# 2 bytes for length of pathstring
bs.seek(lenStr, NOESEEK_REL)# skip path

for one byte string length use lenStr = bs.readByte()
for DWORD (4 bytes) string length use lenStr = bs.readInt()

(not tested but should work)
## Post #51
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-08-01T09:41:41+00:00
- Post Title: Re: Noesis tutorial Basic Model

I have a problem. I'm trying to create a script that can import dark souls 2 models by modifying an old dark souls script 1. if I try to import a dark souls 2 model of the basic version of the game, it works correctly:



while if I try to import a model of dark souls 2 scholar of the first sin this happens to me:



I leave you the complete script. I have only changed the type of model to be imported.

```

Note that there are little and big endian versions of the game, and they
are basically the same format. Therefore, all'''

from inc_noesis import *
import noesis
import rapi
import os

logd = open("darksouls2.log","w")

def registerNoesisTypes():
    '''Register the plugin. Just change the Game name and extension.'''
    
    handle = noesis.register("Dark Souls2", ".flv")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    
    if len(data) < 16:
        return 0
    try:
        bs = NoeBitStream(data)
        idstring = noeStrFromBytes(bs.readBytes(6))
        if idstring == "FLV":
            return 1
        return 0
    except:
        return 0
    
def get_endian(data):
    
    bs = NoeBitStream(data)
    bs.seek(6)
    endian = bs.readByte()
    if endian == 0x4C: # "L"
        return 0
    elif endian == 0x42: # "B"
        return 1 

def noepyLoadModel(data, mdlList):
    '''Build the model, set materials, bones, and animations. You do not
    need all of them as long as they are empty lists (they are by default)'''
    
    endian = get_endian(data)
    ctx = rapi.rpgCreateContext()
    parser = SanaeParser(data, endian)
    parser.parse_file()
    mdl = rapi.rpgConstructModel()
    mdl.setModelMaterials(NoeModelMaterials(parser.texList, parser.matList))
    mdl.setBones(parser.boneList)
    mdl.setAnims(parser.animList)
    mdlList.append(mdl)
    return 1

def logD(what):
    logFile = open("fmt_DarkSouls2_flv.log")

class FLV_mesh(object):
    
    def __init__(self):
        
        self.numFaceGroups = 0
        self.numIndices = []
        self.idxOffsets = []
        self.idxBuffs = [] #one mesh may have multiple parts
        self.numVerts = 0
        self.vertSize = 0
        self.vertOfs = 0
        self.vertSectionSize = 0
        self.vertBuff = bytes()
        self.uvBuff = bytes()
        self.matIds = 0

class FLV_mat(object):
    def __init__(self):
        self.Name1 = ""
        self.MTDName = ""
        self.texName = ""
        self.nParams = 0
        self.paramStartIndex = 0
        self.unknown0 = 0

class SanaeParser(object):
    
    def __init__(self, data, endian=0):
        
        self.inFile = NoeBitStream(data, endian)
        self.animList = []
        self.texList = []
        self.matList = []
        self.boneList = []
        self.meshList = []
        self.materialList = []
        self.dataOfs = 0 #offset to mesh data        
        if endian:
            rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
        
    def build_meshes(self):
        
        rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)
        for mesh in self.meshList:
            
            print(mesh.vertSize)
            #rapi
            if mesh.vertSize == 28:
                rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 28, 0)
                #noesis.doException("vertSize = 28, UVs not implemented...yet")
                rapi.rpgBindUV1BufferOfs(mesh.uvBuff,noesis.RPGEODATA_FLOAT,8,0)
            elif mesh.vertSize == 32:
                rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 32, 0)
                #rapi.rpgBindNormalBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 32, 20)
                rapi.rpgBindUV1BufferOfs(mesh.uvBuff,noesis.RPGEODATA_FLOAT,8,0)
                #rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_HALFFLOAT, 32, 16)
                #noesis.doException("vertSize = 32, UVs not implemented...yet")
            elif mesh.vertSize == 36:
                rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 36, 0)
                rapi.rpgBindUV1BufferOfs(mesh.uvBuff,noesis.RPGEODATA_FLOAT,8,0)
                #noesis.doException("vertSize = 36, UVs not implemented...yet")
            elif mesh.vertSize == 40:
                rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 40, 0)
                rapi.rpgBindUV1BufferOfs(mesh.uvBuff,noesis.RPGEODATA_FLOAT,8,0)
                
                #rapi.rpgBindUV1BufferOfs(mesh.vertBuff, noesis.RPGEODATA_HALFFLOAT,40,36)
            elif mesh.vertSize == 44:
                rapi.rpgBindPositionBufferOfs(mesh.vertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
                rapi.rpgBindUV1BufferOfs(mesh.uvBuff,noesis.RPGEODATA_FLOAT,8,0)
                #noesis.doException("vertSize = 44, UVs not implemented...yet")
            
            #for j in range(mesh.numFaceGroups): # Not sure
            for j in range(1):
                numIdx = mesh.numIndices[j]
                idxBuff = mesh.idxBuffs[j]
                rapi.rpgSetMaterial(self.materialList[mesh.matIds].Name1)
                rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE_STRIP, 1)
            #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, mesh.numVerts, noesis.RPGEO_POINTS, 1)
                
            
    def get_indices(self, numIdx):
        
        return self.inFile.readBytes(numIdx*2)

    def jnr(self,offs):
        oldOffs = self.inFile.tell()
        self.inFile.seek(offs)
        eos = False
        #strEnd = '00'.decode('hex')
        tmpBuffer = ""
        while not eos:
            tmpByte = self.inFile.readBytes(1)
            self.inFile.readBytes(1)
            tmpChar = ord(tmpByte)
            if(ord(tmpByte) == 0):
                eos = True
                break
            else:
                tmpBuffer += str(chr(ord(tmpByte)))
        self.inFile.seek(oldOffs)
        return tmpBuffer

    def jnr2(self,offs):
        oldOffs = self.inFile.tell()
        self.inFile.seek(offs)
        eos = False
        #strEnd = '00'.decode('hex')
        tmpBuffer = ""
        while not eos:
            tmpByte = self.inFile.readBytes(1)
            self.inFile.readBytes(1)
            tmpChar = ord(tmpByte)
            if(ord(tmpByte) == 0):
                eos = True
                break
            else:
                tmpBuffer += str(chr(ord(tmpByte)))
        newOffs = self.inFile.tell()
        self.inFile.seek(oldOffs)
        return [tmpBuffer,newOffs]

    def parse_faces(self):
        
        for mesh in self.meshList:
            for i in range(mesh.numFaceGroups):
                numIdx = mesh.numIndices[i]
                idxOfs = mesh.idxOffsets[i]
                self.inFile.seek(idxOfs)
                idxBuff = self.get_indices(numIdx)
                mesh.idxBuffs.append(idxBuff)
                
                
    def parse_vertices(self):
        
        for mesh in self.meshList:
            self.inFile.seek(mesh.vertOfs)
            #logd.write(str(mesh.vertSize) + " : " + str(mesh.vertOfs) + "," + str(mesh.vertSectionSize) + "\n")
            mesh.vertBuff = self.inFile.readBytes(mesh.vertSectionSize)
            #if(mesh.vertSize == 40):
            for i in range(mesh.numVerts):
                vS = mesh.vertSize
                vPos = i * vS
                tmpVert = mesh.vertBuff[vPos:vPos+mesh.vertSize]
                vU = struct.pack("f",float(struct.unpack("h",tmpVert[(vS-4):(vS-2)])[0] / 1024.0))
                vV = struct.pack("f",float(struct.unpack("h",tmpVert[(vS-2):(vS)])[0] / 1024.0))
                mesh.uvBuff += vU
                mesh.uvBuff += vV


    def resolveTextureName(self,inName):
        tmpName1 = inName.split('\\')
        logd.write(str(tmpName1[len(tmpName1)-1].split('.')))
        tmpName2 = tmpName1[len(tmpName1) - 1].split('.')
        type1 =  self.myWD + "\\" + self.myOutDIR + "\\" + tmpName2[0] + ".dds"
        type2 =  self.myWD + "\\" + self.myOutDIR + "\\" + tmpName2[0] + "_n [Unknown24].dds"
        logd.write("TYPE1: " + type1)
        #type1 = self.findInSubDir(tmpName2[0] + ".dds")
        #if(type1 == -1):
        #    return (tmpName2[0] + ".dds")
        #else:
        #    return type1
        return [type1,type2]
                        
                    

    def findInSubDir(self,filename,subdirectory = ''):
        logd.write("myWD = " + self.myWD + "\n")
        if subdirectory:
            path = subdirectory
        else:
            path = self.myWD
            for root, dirs, names in os.walk(path):
                if filename in names:
                    return os.path.join(root,filename)
                else:
                    return -1





    def parse_materials(self, numMat):
        for m in range(numMat):# in self.materialList:
            logd.write("PARSE MATERIAL INFO: " + str(self.inFile.tell()) + "\n")
            Name1 = self.jnr(self.inFile.readUInt())
            tmpMatThing = self.jnr2(self.inFile.readUInt())
            MTDName = tmpMatThing[0]
            tmpTexz = self.resolveTextureName(self.jnr(tmpMatThing[1]))
            texName = tmpTexz[0]
            normalName = tmpTexz[1]
            nParams = self.inFile.readUInt()
            paramStartIndex = self.inFile.readUInt()
            unknown0 = self.inFile.readUInt()
            self.inFile.read('3L')
            #logd.write("MATERIAL {}: {}\n".format(mat.Name1,mat.texName))
            mat = FLV_mat()
            mat.Name1 = Name1
            self.materialList.append(mat)
            
            material = NoeMaterial(Name1,texName)
            material.setNormalTexture(normalName)
            self.matList.append(material)

            
    def parse_bones(self, numBones):
        
        for i in range(numBones):
            self.inFile.seek(64, 1)
            
    def parse_unk1(self, count):
        
        for i in range(count):
            #logd.write("unk1: " + str(self.inFile.tell()))
            self.inFile.seek(128, 1)
            
    def parse_part_info(self, numParts):
        
        for mesh in self.meshList:
            #logd.write("part_info: " + str(self.inFile.tell()) + "\n")
            logd.write("PARSE PART INFO: " + str(self.inFile.tell()) + "\n")
            self.inFile.read('1L')
            matIds = self.inFile.readUInt()
            self.inFile.read('6L')
            numFaceGroups = self.inFile.readUInt()
            self.inFile.read('3L')
            #logd.write("NUM FACESGROUPS:" + str(numFaceGroups) + "\n")
            mesh.numFaceGroups = numFaceGroups
            mesh.matIds = matIds
            
    def parse_face_info(self):
        
        for mesh in self.meshList:
            for i in range(mesh.numFaceGroups):
                groupNum = self.inFile.readUInt()
                self.inFile.readUInt()
                numIdx = self.inFile.readUInt()
                #logd.write("NUM FACES:" + str(numIdx) + "\n")
                idxOfs = self.inFile.readUInt() + self.dataOfs
                idxSize = self.inFile.readUInt()
                self.inFile.read('3L')
                
                mesh.numIndices.append(numIdx)
                mesh.idxOffsets.append(idxOfs)
                            
    def parse_vertex_info(self):
        
        for mesh in self.meshList:
            self.inFile.read('1L')
            vertDescriptor = self.inFile.read('1L')
            vertSize = self.inFile.readUInt()
            numVerts = self.inFile.readUInt()
            self.inFile.readUInt()
            unk = self.inFile.readUInt()
            sectionSize = self.inFile.readUInt()
            vertOfs = self.inFile.readUInt() + self.dataOfs
            
            mesh.numVerts = numVerts
            mesh.vertSize = vertSize
            mesh.vertOfs = vertOfs
            mesh.vertSectionSize = sectionSize
            
    def getfdir(self):
        tmpDir = rapi.getInputName().split('\\')
        myCWD = ''
        for i in range(len(tmpDir) - 1):

            if(i == (len(tmpDir) - 2)):
                myCWD += tmpDir[i]
            else:
               myCWD += tmpDir[i] + '\\'
        
        return [myCWD,tmpDir[len(tmpDir) - 1].split('.')[0]]



    def parse_file(self):
        '''Main parser method'''
        tmpTing = self.getfdir()
        self.myWD = tmpTing[0]
        self.myOutDIR = tmpTing[1] +"_unpack"
        logd.write("myOutDIR = " + self.myOutDIR + "\n")
        
        

        #logd.write(rapi.getInputName())
        #header
        idstring = self.inFile.readBytes(6)
        
        #version?
        unk, type1, type2 = self.inFile.read('3H')
        
        self.dataOfs = self.inFile.readUInt()
        dataSize = self.inFile.readUInt()
        numBones = self.inFile.readUInt()
        numMat = self.inFile.readUInt()
        count = self.inFile.readUInt()
        numParts = self.inFile.readUInt()
        numMesh = self.inFile.readUInt()
        
        #create some mesh objects
        for i in range(numMesh):
            mesh = FLV_mesh()
            self.meshList.append(mesh)

        #for i in range(numMat):
        #    mat = FLV_mat()
        #    self.materialList.append(mat)
        
        self.inFile.read('6f')
        self.inFile.seek(64, 1)
        self.parse_bones(numBones)
        self.parse_materials(numMat)
        self.parse_unk1(count)
        self.parse_part_info(numParts)
        self.parse_face_info()        
        logd.write("PARSE VERTEX INFO: " + str(self.inFile.tell()) + "\n")
        self.parse_vertex_info()
        logd.write("PARSE FACES: " + str(self.inFile.tell()) + "\n")
        #parse data
        self.parse_faces()
        logd.write("PARSE VERTS: " + str(self.inFile.tell()) + "\n")
        self.parse_vertices()
        logd.write("END FILE ACCESS? " + str(self.inFile.tell()) + "\n")
        self.build_meshes()

```
## Post #52
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-01-05T07:20:46+00:00
- Post Title: Re: Noesis tutorial Basic Model

Need tutorial for import Bone and Animation
## Post #53
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-18T21:26:35+00:00
- Post Title: Re: Noesis tutorial Basic Model

For skeleton bones look here:
[https://forum.xentax.com/viewtopic.php?f=29&t=19429](https://forum.xentax.com/viewtopic.php?f=29&t=19429)

You may read here, too:
[viewtopic.php?f=13&t=14446&hilit=NoeKeyFramedValue](http://forum.xentax.com/viewtopic.php?f=13&t=14446&hilit=NoeKeyFramedValue)

Be sure to read this documentation located in Noesis/Plugins/Python/__NPReadMe.txt 
as advised by Gh0stBlade.
## Post #54
- Username: rusian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 01, 2011 7:08 pm
- Post datetime: 2019-06-16T05:43:47+00:00
- Post Title: Re: Noesis tutorial Basic Model

hi
how do i print opened filename and path
## Post #55
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-02-28T00:57:36+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from chrrox ↑Mon Nov 28, 2011 10:07 am at Mon Nov 28, 2011 10:07 am
>
> 
Ok so now we will add in our normals and uv coordinates.
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 88, 48)

Hi chrrox, I'm trying to create a python script to extract the Gintama Rumble models from the PS4 version.
I'm using hex2obj as guide, trying to pars the values I found to a Noesis py script using your rapi tutorial, the problem is that in hex2obj the UVs are in WORDUV and the UV POS is 40 with a vertex size of 44.



My question is how to re-write the quoted line using this information?
Cause I tried using
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 44, 40)
But the UVs came out so tiny.



This is my script.

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Gintama Rumble PS4",".tmd")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "tmd0"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readBytes(4).decode("ASCII") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.seek(0xcc, NOESEEK_ABS)
	FCount = bs.read("i")
	bs.seek(0xc, NOESEEK_REL)
	VCount = bs.read("i")
	bs.seek(0x70, NOESEEK_ABS)
	FAddress = bs.readUInt()
	bs.seek(0x1c, NOESEEK_REL)
	VAddress = bs.readUInt()
	#print("{} {} {} {}".format(FCount[0]*3, VCount[0], hex(FAddress), hex(VAddress)))
	bs.seek(VAddress, NOESEEK_ABS)
	VertBuff = bs.readBytes(VCount[0] * 0x2c)
	#print("\n{}".format(VertBuff))
	rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
	rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_USHORT, 44, 40)
	bs.seek(FAddress, NOESEEK_ABS)
	FaceBuff = bs.readBytes(FCount[0] * 6)
	rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, FCount[0]*3, noesis.RPGEO_TRIANGLE, 1)
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1
```


Here is the [sample file](https://www.mediafire.com/file/2x2yth899sby19q/pl00Hair00_00.tmd/file).
## Post #56
- Username: JosouKitsune
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-02-28T10:46:19+00:00
- Post Title: Re: Noesis tutorial Basic Model

your options for uv's if they are 4 bytes would be
	PYNOECONSTN(RPGEODATA_SHORT),
	PYNOECONSTN(RPGEODATA_USHORT),
	PYNOECONSTN(RPGEODATA_HALFFLOAT),
I would try short instead of ushort.
## Post #57
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-02-28T15:51:33+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from chrrox ↑Fri Feb 28, 2020 6:46 pm at Fri Feb 28, 2020 6:46 pm
>
> 
your options for uv's if they are 4 bytes would be
	PYNOECONSTN(RPGEODATA_SHORT),
	PYNOECONSTN(RPGEODATA_USHORT),
	PYNOECONSTN(RPGEODATA_HALFFLOAT),
I would try short instead of ushort.
Thanks, I tried the SHORT option and it did upscale, but not by much and the HALFFLOAT option shrank the UVs.
Is there a way to upscale the UVs automatically? 
The scale parameter in the export options doesn't seem to affect the UVs.
## Post #58
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-02-28T18:48:57+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from JosouKitsune ↑Fri Feb 28, 2020 11:51 pm at Fri Feb 28, 2020 11:51 pm
>
> 
chrrox wrote: ↑Fri Feb 28, 2020 6:46 pm
your options for uv's if they are 4 bytes would be
	PYNOECONSTN(RPGEODATA_SHORT),
	PYNOECONSTN(RPGEODATA_USHORT),
	PYNOECONSTN(RPGEODATA_HALFFLOAT),
I would try short instead of ushort.

Thanks, I tried the SHORT option and it did upscale, but not by much and the HALFFLOAT option shrank the UVs.
Is there a way to upscale the UVs automatically? 
The scale parameter in the export options doesn't seem to affect the UVs.

I looked at other people's py scripts and they used this action to zoom in on uv: {"rpgSetUVScaleBias", RPGSetUVScaleBias, METH_VARARGS, "sets uv coordinate scale and bias - pass None, None to disable. (OO|i)"}, //args=NoeVec3 (scale), NoeVec3 (bias), optional uv index - or None, None
## Post #59
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-02-29T00:15:18+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from bymutou ↑Sat Feb 29, 2020 2:48 am at Sat Feb 29, 2020 2:48 am
>
> 
JosouKitsune wrote: ↑Fri Feb 28, 2020 11:51 pm
chrrox wrote: ↑Fri Feb 28, 2020 6:46 pm
your options for uv's if they are 4 bytes would be
	PYNOECONSTN(RPGEODATA_SHORT),
	PYNOECONSTN(RPGEODATA_USHORT),
	PYNOECONSTN(RPGEODATA_HALFFLOAT),
I would try short instead of ushort.

Thanks, I tried the SHORT option and it did upscale, but not by much and the HALFFLOAT option shrank the UVs.
Is there a way to upscale the UVs automatically? 
The scale parameter in the export options doesn't seem to affect the UVs.


I looked at other people's py scripts and they used this action to zoom in on uv: {"rpgSetUVScaleBias", RPGSetUVScaleBias, METH_VARARGS, "sets uv coordinate scale and bias - pass None, None to disable. (OO|i)"}, //args=NoeVec3 (scale), NoeVec3 (bias), optional uv index - or None, None

Thanks for this, the UVs are looking fine now.





Though the factor I ended up with was 32.0285, such a weird scale, there may be a better one.

```
rapi.rpgSetUVScaleBias((32.0285,32.0285,32.0285),None)
```
## Post #60
- Username: 11H5
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 01, 2020 8:12 am
- Post datetime: 2020-04-01T20:20:58+00:00
- Post Title: Re: Noesis tutorial Basic Model

if anyone can help will be great !

after inspect element from sketchfab i saved this files . 
zip files .

file.osgjs
model_file.bin
model_file_wireframe.bin

now i'm trying to open this files in Noesis to see the 3d model , but i can't .

maybe there's a plugin i can add to Noesis so it would work ?
## Post #61
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-02T11:22:44+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from 11H5 ↑Thu Apr 02, 2020 4:20 am at Thu Apr 02, 2020 4:20 am
>
> maybe there's a plugin i can add to Noesis so it would work ?Not to my knowledge. Last solution for sketchfab models I remember was from Szkaradek123, a blender 2.49b project (doesn't work with newest blender!): Blender249[sketchfab][htm][2019-10-16] (Maybe to be found on Zenhax, don't remember.)

Older/other version was Blender249[osgjs][2017-02-23].

fyi: discussion on xentax concerning leeching of commercial models has been stopped.
## Post #62
- Username: RyanTroy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 11, 2020 7:00 pm
- Post datetime: 2020-05-02T11:49:17+00:00
- Post Title: Re: Noesis tutorial Basic Model

Thanks for the good tutorial, unfortunately I'm stuck when trying to get faces I get this error.



I've attached the file and my script for reference.


 mga_test.zip
(34.75 KiB) Downloaded 23 times
## Post #63
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-02T12:49:21+00:00
- Post Title: Re: Noesis tutorial Basic Model

Which script example did you take as a base? Looks more complicated than needed -
maybe have a look at this one for example:

> Reply from shakotay2 ↑Thu May 15, 2014 8:48 pm at Thu May 15, 2014 8:48 pm
>
> 

Your example would work like so:

```
      #faces.append (bs.readBytes(6).decode('ascii').rstrip('\0'))
      f1 = bs.readUShort();f2 = bs.readUShort();f3 = bs.readUShort()
      faces.append(f1);faces.append(f2);faces.append(f3)
```


But it would require "old Noesis style"?, without "rapi", afair.

```
		msh.setIndices(faces)
		msh.setPositions(verts)
		msh.setUVs(uvs)
		meshes.append(msh)
```
## Post #64
- Username: RyanTroy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 11, 2020 7:00 pm
- Post datetime: 2020-05-02T13:42:36+00:00
- Post Title: Re: Noesis tutorial Basic Model

Thanks it worked, I followed this tutorial [viewtopic.php?f=29&t=7760](https://forum.xentax.com/viewtopic.php?f=29&t=7760)

Also how can I proceed if I have several files of the same type and the starting address of vertices keeps changing ? for example sometimes it's 0x3f sometimes 0x79 or 0x5d
## Post #65
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-02T14:49:32+00:00
- Post Title: Re: Noesis tutorial Basic Model

There's no general recipe, you can do a full format analysis, you can search for patterns, or for magic tables (containing counts and/or offsets).

An example for pattern search is to be found here (in case you find a pattern in .mga files)

> Reply from shakotay2 ↑Sat Mar 07, 2020 3:29 pm at Sat Mar 07, 2020 3:29 pm
>
>
## Post #66
- Username: TheFalcon19
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 25, 2019 9:42 pm
- Post datetime: 2020-07-18T03:12:07+00:00
- Post Title: Re: Noesis tutorial Basic Model

I can't figure out what I'm doing wrong, but I'm getting some misplaced vertices in Noesis.
The mesh is correct in Model Researcher and Mesh Reaper with the same data.

I'm using just the basic commands for vertex position:
VertexBuffer = bs.readBytes(VertexCount * 12)
and
rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 12, 0)

Here I highlighted an example where in noesis those four bytes end up +16 compared to hxd.
## Post #67
- Username: Dippergames420
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 23, 2019 8:42 am
- Post datetime: 2020-10-09T01:48:16+00:00
- Post Title: Re: Noesis tutorial Basic Model

I've been trying to extract these for a while now, and all else has seemingly failed, so I've decided to ask for help here.

There have been a few threads related to the models from Dragon Ball Z Ultimate Tenkaichi over the years, due to Noesis crashing when trying to export from the .AFS file. I did try the plugin from revelation ([viewtopic.php?p=61219#p61219](https://forum.xentax.com/viewtopic.php?p=61219#p61219)) along with the default Noesis .AFS plugin, and AFSExplorer, only to get a mixture of blank files and the aforementioned Noesis crash.

If it's at all possible, is there a way to write a script to dig into archives? I'd like to write one of them so I can extract the files from the .AFS, or better decompile one of the empty files into something legible for revelation's plugin. An old thread has a DL for the .AFS, so here you go:

[viewtopic.php?t=19077](https://forum.xentax.com/viewtopic.php?t=19077)


And here's the blank files for UT's Goku in a ZIP archive, for context:

[https://drive.google.com/file/d/198soxL ... sp=sharing](https://drive.google.com/file/d/198soxLWP6-LwUFMVWxo2k6cQidsYH89W/view?usp=sharing)

Any help is greatly appreciated!
## Post #68
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2021-10-16T21:05:09+00:00
- Post Title: Re: Noesis tutorial Basic Model

Hello!

Does anyone know if I can add more than 2 UVs with Noesis?
My models have up to 3 UVs for some Meshes.
rapi.rpgBindUV2BufferOfs() only goes up to 2. 

Thanks,

GHFear
## Post #69
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-17T09:52:27+00:00
- Post Title: Re: Noesis tutorial Basic Model

Apparently noesis supports up to 4 UV buffers through the following functions:

```
void (*rpgBindUVXBufferSafe)(void *data, rpgeoDataType_e dataType, int stride, int uvIndex, int elemCount, int bufferSize);
```

but I'm not sure they work in the same way as default implementation in form of BufferOfs do (arguments aside).
## Post #70
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-18T20:53:16+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from Spiritovod ↑Sun Oct 17, 2021 5:52 pm at Sun Oct 17, 2021 5:52 pm
>
> 
Apparently noesis supports up to 4 UV buffers through the following functions:
Code: Select allvoid (*rpgBindUVXBuffer)(void *data, rpgeoDataType_e dataType, int stride, int uvIndex, int elemCount);
void (*rpgBindUVXBufferSafe)(void *data, rpgeoDataType_e dataType, int stride, int uvIndex, int elemCount, int bufferSize);
but I'm not sure they work in the same way as default implementation in form of BufferOfs do (arguments aside).

Yes, if someone needs it (I don't know many people who make native plugin in Noesis since it's harder), the equivalent python function is  : 
```
{"rpgBindUVXBuffer", RPGBindUVXBuffer, METH_VARARGS, "binds uvx buffer. (Oiiii)"}, //args=bytes for uvX's, dataType, stride, uv index, uv elem count
```


So for example 
```
rapi.rpgBindUV2Buffer(bs.readBytes(4*submesh.vCount), noesis.RPGEODATA_HALFFLOAT, 0x4)
rapi.rpgBindUVXBuffer(bs.readBytes(4*submesh.vCount), noesis.RPGEODATA_HALFFLOAT, 0x4, 3, submesh.vCount)
```


Then you'll be able to view it just like the others in the data viewer and they'll export just fine 


You can add more if you want but you'll be limited by the export format at some point
## Post #71
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-01T21:11:46+00:00
- Post Title: Re: Noesis tutorial Basic Model

So pretty nooby question but how do you skip a byte or half a byte or whatever to get to your desired uint16 etc? Just with regular bs seek and then like bs.seek(0x2, NOESEEK_REL)

Also how do you deal with files that don't start with any specific header? For example my file starts with:

```
06 00 00 00 5B FD 00 00 03 7C 02 00 01 D4 00 00 00 00 00 00 6D B6 AA 06 00 00 00 00 24 9C 00 00 00 00 00 00 01 00 00 00 00 00 00 00 6D B6 AA 06 00 00 00 00 2C 8E 00 00 00 00 00 00 01 00 00 00 00 00 00 00 6D B6 AA 06 00 00 00 00 28 6E 00 00 00 00 00 00 01 00 00 00 00 00 00 00 6D B6 AA 06 00 00 00 00 30 A8 00 00 00 00 00 00 01 00 00 00 00 00 00 00 6D B6 AA 06 00 00 00 00 40 29 00 00 00 00 00 00 01 00 00 00 00 00 00 00 0F 2F 87 66 00 00 00 00 1B 12 00 00 00 00 00 00 01 00 00 00 00 00 00 00
```


First is the submesh count, second byte is vert count, third is poly count. However, I fail to find a header.
## Post #72
- Username: dkl77
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 26, 2020 4:06 am
- Post datetime: 2021-12-02T20:02:44+00:00
- Post Title: Re: Noesis tutorial Basic Model

Hello I am learning and practicing python and noesis and although I know that there is a tool called the cgf-converter I am working on a plugin to import cryengine files to noesis so far the mesh I have solved quite well but I am struggling with the bones I have not been able to resolve the indexes nor the parent index nor the matrix3x4 properly so noesis if anyone could point me in the right direction and can take a look I would really appreciate it

I leave the structure of the chunks bones and a file

pos 0x28 is the size of the bones chunks and 0x2C is the offset +32 start
each bone has 584 bytes chunk
numBones = (bs.readUInt()-32)//584
conbtrolerId = readUInt
physicGeometry = readBytes(256)
mass = float
MATRIX3x4 worldToBone = readBytes(48) 
boneName = readBytes(256)
limbID = readInt
offsetParent = readInt
numChildren = readUInt
offsetChild = readInt
[hmus_face_002.rar](https://xentaxbackup.github.io/file/21337_hmus_face_002.rar)
## Post #73
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-03T14:27:17+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from dkl77 ↑Fri Dec 03, 2021 4:02 am at Fri Dec 03, 2021 4:02 am
>
> 
Hello I am learning and practicing python and noesis and although I know that there is a tool called the cgf-converter I am working on a plugin to import cryengine files to noesis so far the mesh I have solved quite well but I am struggling with the bones I have not been able to resolve the indexes nor the parent index nor the matrix3x4 properly so noesis if anyone could point me in the right direction and can take a look I would really appreciate it

I leave the structure of the chunks bones and a file

pos 0x28 is the size of the bones chunks and 0x2C is the offset +32 start
each bone has 584 bytes chunk
numBones = (bs.readUInt()-32)//584
conbtrolerId = readUInt
physicGeometry = readBytes(256)
mass = float
MATRIX3x4 worldToBone = readBytes(48) 
boneName = readBytes(256)
limbID = readInt
offsetParent = readInt
numChildren = readUInt
offsetChild = readInt

It had a few traps for a beginner:
-the bone matrices used a column major layout (so you need to read the matrix column by column instead of line by line)
-the Y/Z axis are swapped in this game compared to Noesis, I swapped the coords, alternatively you can switch the preview angle instead using rapi.setPreviewOption("setAngOfs", "0 0 0") 
-I think you missed some bytes in your spec since there are 2 4x3 matrices, I use the second one (model space coord), the first one is probably the local space coords (so relative to the parent)

I recommend this great thread by Bigchillghost if you didn't check it already, it has several examples with some Noesis code for skeletons [viewtopic.php?f=29&t=19429](https://forum.xentax.com/viewtopic.php?f=29&t=19429)

Anyways, attached is a script to load your skeleton, I put some comments there too 

 fmt_skin.zip
(992 Bytes) Downloaded 23 times
## Post #74
- Username: dkl77
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 26, 2020 4:06 am
- Post datetime: 2021-12-03T17:52:27+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from Joschka ↑Fri Dec 03, 2021 10:27 pm at Fri Dec 03, 2021 10:27 pm
>
> 

It had a few traps for a beginner:
-the bone matrices used a column major layout (so you need to read the matrix column by column instead of line by line)
-the Y/Z axis are swapped in this game compared to Noesis, I swapped the coords, alternatively you can switch the preview angle instead using rapi.setPreviewOption("setAngOfs", "0 0 0") 
-I think you missed some bytes in your spec since there are 2 4x3 matrices, I use the second one (model space coord), the first one is probably the local space coords (so relative to the parent)

I recommend this great thread by Bigchillghost if you didn't check it already, it has several examples with some Noesis code for skeletons viewtopic.php?f=29&t=19429

awesome thanks for taking the time I really appreciate it I saw Bigchillghost's post but I couldn't understand very well how to apply it to my script now I'm going to compare what you did to understand or try to understand I'm still with my baby steps in python and data file analysis. right now I'm at my job as soon as I have a chance I'll check the script
## Post #75
- Username: nbakiki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 05, 2021 8:35 am
- Post datetime: 2021-12-05T00:45:01+00:00
- Post Title: Re: Noesis tutorial Basic Model

Hi! I'm trying to use the Noesis but I'm unable to download an .mview file from the developer's tools' network tab as mentioned in the notes. It's only downloading as a JPEG.
## Post #76
- Username: nbakiki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 05, 2021 8:35 am
- Post datetime: 2021-12-06T00:16:23+00:00
- Post Title: Re: Noesis tutorial Basic Model

> Reply from nbakiki ↑Sun Dec 05, 2021 8:45 am at Sun Dec 05, 2021 8:45 am
>
> 
Hi! I'm trying to use the Noesis but I'm unable to download an .mview file from the developer's tools' network tab as mentioned in the notes. It's only downloading as a JPEG.

Does anyone know how to download the .mview files from marmoset viewers?!
