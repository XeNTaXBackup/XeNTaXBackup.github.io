## Post #1
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-01-04T14:54:15+00:00
- Post Title: Noesis / Maxscript scripting questions

Hi all, i recently started getting my hands on Noesis and i wanted to give it a try to open some meshes and writing my own scripts to perform the task...
But i'm really new to it and i'm stuck at reading the binary file's vertices and faces i have an error message saying that the "vertex position list is empty" i tried looking at already existing scripts for other games assets but it's a bit confusing.
I mainly use Hex2obj and ModelResearcher to extract some meshes but having a script for doing it is faster and could help me for learning purposes...
Here is my script for now (i've made it with the exemple sample provided in Neosis) :
- [http://www.mediafire.com/file/zh3diy5aj ... -Script.py](http://www.mediafire.com/file/zh3diy5aji6rb56/Import-RGM-Script.py)

And this is the error message : 


Theses are the samples i'm using for making the script :
- [http://www.mediafire.com/file/bddsn7szq ... %u53F0.rgm](http://www.mediafire.com/file/bddsn7szqrt8whs/%25u7CD6%25u679C%25u821E%25u53F0.rgm) (STAGE file)
- [http://www.mediafire.com/file/hiuk6edvh ... ancer1.rgm](http://www.mediafire.com/file/hiuk6edvh566ilz/discoclub_dancer1.rgm) (AVATAR file)
- [http://www.mediafire.com/file/nym1t18lt ... ove_01.rgm](http://www.mediafire.com/file/nym1t18lttzyycz/dancermove_01.rgm) (ANIMATION file)

Note that my goal is mainly being able to read / import Avatars and Stages RGMs on Noesis (Animations aren't for me at all it's too difficult)
I've studied the format for a while now and i have collected many infos about it, i still have trouble saying what data types i'm seeing but i guess it will comes with time...

But after looking at many RGM samples i can give these informations (with help of other skilled peoples) :

```
- little endian
- byte = 8 bit int
- short = 16 bit int
- long = 32 bit int
- float = 32 bit float
```


It's common to every RGMs i've "worked" with !
also it's a "dynamic file format" i don't know yet what it exactly means but i don't think it's really important for now...
Anyway thanks for reading, if someone can guide me with Noesis scripting i will really appreciate it.
I know that their is a tutorial made by "Chroxx" somewhere on xentax but it's missing the pictures (because links are dead) and it's still a bit confusing.
As usual sorry for my english.

Oh and Happy new year
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-04T22:56:53+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from Loginoux
>
> i tried looking at already existing scripts for other games assets but it's a bit confusing.
indeed many are confusing, and some for no reason, i newbified your script to open the discoclub_dancer1.rgm  

```

def registerNoesisTypes():
    handle = noesis.register("Audition online dance battle [PC]", ".RGM")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    bs = NoeBitStream(data)
    if noeStrFromBytes(bs.readBytes(9)) != "Delight3D": return 0
    return 1

#load the model
def noepyLoadModel(data, mdlList):              #standard line
    ctx = rapi.rpgCreateContext()               #standard line
    bs = NoeBitStream(data)                     #standard line
    bs.seek(0x25a, NOESEEK_ABS)      #jump to position 0x25a from 0x0
    vCount = bs.readUInt()            #read vertex count
    bs.readByte()                      #skip this unknown byte
    vBuff = bs.readBytes(vCount * 32)   #read vertex buffer which is vertex count * vertex stride
    fCount = bs.readUInt() * 3           #read face count and multiply by 3
    fBuff = bs.readBytes(fCount * 2)      #read face buffer which is face count * 2
    rapi.rpgBindPositionBufferOfs(vBuff, noesis.RPGEODATA_FLOAT, 32, 0)   #pos of vertices (byte array, data type, stride, pos within stride)
    rapi.rpgBindUV1BufferOfs(vBuff, noesis.RPGEODATA_FLOAT, 32, 24)       #UV1  (byte array, data type, stride, pos within stride)
    rapi.rpgCommitTriangles(fBuff, noesis.RPGEODATA_SHORT, fCount, noesis.RPGEO_TRIANGLE, 1)
    mdlList.append(rapi.rpgConstructModel())    #standard line
    rapi.rpgClearBufferBinds()                  #standard line
    return 1                                    #standard line

```

see how simple it can be? this script reads only the mesh and UVs but still, its simple.   
i put comments in there so you can see what is happening.

edit
adding link to original research thread because it has much info about basic rgm reversal already   
[viewtopic.php?f=16&t=14885](http://forum.xentax.com/viewtopic.php?f=16&t=14885)
## Post #3
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-01-05T00:37:53+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from AceWell
>
> Loginoux wrote:i tried looking at already existing scripts for other games assets but it's a bit confusing.
indeed many are confusing, and some for no reason, i newbified your script to open the discoclub_dancer1.rgm  
Code: Select allfrom inc_noesis import *

def registerNoesisTypes():
    handle = noesis.register("Audition online dance battle [PC]", ".RGM")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    bs = NoeBitStream(data)
    magic = noeStrFromBytes(bs.readBytes(9))
    if magic != "Delight3D":
       return 0
    return 1

#load the model
def noepyLoadModel(data, mdlList):              #standard line
    ctx = rapi.rpgCreateContext()               #standard line
    bs = NoeBitStream(data)                     #standard line
    bs.seek(0x25a, NOESEEK_ABS)      #jump to position 0x25a from 0x0
    vCount = bs.readUInt()            #read vertex count
    bs.readByte()                      #skip this unknown byte
    vBuff = bs.readBytes(vCount * 32)   #read vertex buffer which is vertex count * vertex stride
    fCount = bs.readUInt() * 3           #read face count and multiply by 3
    fBuff = bs.readBytes(fCount * 2)      #read face buffer which is face count * 2
    rapi.rpgBindPositionBufferOfs(vBuff, noesis.RPGEODATA_FLOAT, 32, 0)   #pos of vertices (byte array, data type, stride, pos within stride)
    rapi.rpgBindUV1BufferOfs(vBuff, noesis.RPGEODATA_FLOAT, 32, 24)       #UV1  (byte array, data type, stride, pos within stride)
    if fCount % 3 == 0:                       #check if evenly divisible by 3 and do this
        rapi.rpgCommitTriangles(fBuff, noesis.RPGEODATA_SHORT, fCount, noesis.RPGEO_TRIANGLE, 1)
    else:                                        #if not evenly divisible by 3 do this instead
        rapi.rpgCommitTriangles(fBuff, noesis.RPGEODATA_SHORT, fCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
    mdlList.append(rapi.rpgConstructModel())    #standard line
    rapi.rpgClearBufferBinds()                  #standard line
    return 1                                    #standard line

see how simple it can be? this script reads only the mesh and UVs but still, its simple.   
i put comments in there so you can see what is happening.

Hi thank you for replying ! 
It's super clear now it makes more sense to me, i will try to read other RGM files and use this script as a base, i might need to change just some lines i guess !
I will update my progress here so far.
Thank you very much !
## Post #4
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-01-09T15:51:13+00:00
- Post Title: Noesis / Maxscript scripting questions

Hello guys, i tried to continue with Noesis scripting and i'm fine with it i can read some models now ! 
recently i tried to import the stage's RGM to 3ds max, so i started writing a script for it : 

```
clearListener()
-- Open a "*.RGM" file
fRGM = getOpenFileName \
caption:"Open an RGM file:" \
filename:"C:\Users\RGM\Acv tool -CN\*.rgm" \
types:"RGM(*.rgm)|*.rgm"
-- Read binaries from "*.RGM"
if fRGM != undefined then
(
   f = fopen fRGM "rb"
   clearlistener()
	
   Vert_array=#()
   Face_array=#()
   UV_array=#()

   fseek f 762 #seek_set
	
	-- Vertex data
	
	   vertexCount = readbyte f #unsigned
	 print ("VertexCount: " + vertexCount as string)
   for x = 1 to vertexCount do
   (
      vx = readfloat f
	   print ("VectorX: " + vx as string)
      vy = readfloat f
      vz = readfloat f
      append Vert_array[vx,vy,vz]
   )
 
	   Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
		   
-- Close the RGM file
fclose f
	   )
```
 

But i have a problem with vertex count... i think i have found the spot where it is stored in the file (i mean the address) but i have trouble actually reading the data...
i tried doing readlong, readfloats, readshort to get the right value (because i was confused and still having trouble telling if the data is a long short etc) but it's still not correct ! my script is stopping waaaay before the end of the vertex buffer...
Anyone have an idea ?

thanks.

PS : the vertex count address is right before the vertex buffer one in every file i saw (including avatars)
And also the file is a chinese one it's the same structure between all of the them just different another language...
## Post #5
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-02-11T22:16:13+00:00
- Post Title: Noesis / Maxscript scripting questions

Hi guys !
After a few weeks i updated my script but i didn't managed to extract the stage mesh yet...
I have mainly collected infos about the format and updated my kind of "data structure" a little bit...
I discovered that 1 single vertex is stored as 32 bytes and that the 12 first bytes are basically x,y and z value the 20 others are still unknown to this date :/
So i tried skipping these "20" bytes left in my maxscript but it doesn't work i don't know how i could do it "manually"

```
clearListener()
-- Open a "*.RGM" file
fRGM = getOpenFileName \
caption:"Open an RGM file:" \
filename:"C:\Users\Videos\Acv tool -CN\*.rgm" \
types:"RGM(*.rgm)|*.rgm"

-- Read binaries from "*.RGM"
if fRGM != undefined then
(
   f = fopen fRGM "rb"
   clearlistener()
	
   Vert_array=#()
   Face_array=#()
   UV_array=#()

	--Header
	/*fseek f 0 #seek_set
	ID = readstring f
	print("ID: " + ID)
	fseek f 30 #seek_set
	unk01 = readbyte f
	print("unk01 = " + unk01 as string)
	fseek f 31 #seek_set
	unk02 = readbyte f
	print("unk02 = " + unk02 as string)
	fseek f 38 #seek_set
	unk03 = readbyte f
	print("unk03 = " + unk03 as string)
	fseek f 41 #seek_set
	unk04 = readstring f
	print("unk04 = " + unk04)
	fseek f 47 #seek_set
	unk05 = readshort f
	print("unk05 = " + unk05 as string)*/
	
	/*for x = 1 to 20 do(
		strings =readstring f
		whitespace = readshort f
		print("String:" + strings)
		print("Whitespace:" + whitespace as string)
	)*/
	
	-- Vertex data
	fseek f 0x2FA #seek_set
	vertexCount = readshort f #seet_set
	print ("VertexCount: " + vertexCount as string)
   for x = 1 to vertexCount do
   (
      vx = readfloat f
      vy = readfloat f
      vz = readfloat f
      -- Unknowns values
      --unk000 = readfloat f
      --unk001 = readfloat f
      --unk002 = readfloat f
	  --unk003 = readfloat f
	  --unk004 = readfloat f
	  
      append Vert_array[vx,vy,vz]
   )
   
	-- face data
   /*fseek f 0x1EB83  #seek_set
   FacesCount = readshort f #unsigned
   print ("FacesCount: " + FacesCount as string)

   for i = 1 to FacesCount do
   (
      fa = readshort f #unsigned
      fb = readshort f #unsigned
      fc = readshort f #unsigned
      append Face_array[fa+1,fb+1,fc+1]
   )*/
   
	-- UV data (not any info in the file....)
   /*count = readlong f #unsigned
   for i = 1 to count do
   {
      tu = readfloat f
      tv = readfloat f
      append UV_array[tu,1-tv,0]
   )*/
   
	-- Build the mesh
   msh = mesh vertices:Vert_array faces:Face_array name:(getFilenameFile fRGM)
   --msh.numTVerts = UV_array.count
   --buildTVFaces msh
   --for j = 1 to UV_array.count do setTVert msh j UV_array[j]
   --for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
   
   --Printing
	Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
		
	free Face_array
	free Vert_array
	--free UV_array		
		
-- Close the RGM file
fclose f
	   )

```
 

It's possible that i'm doing huge mistakes because i'm still beginner in this...
Thanks for reading if someone have any suggestion or tips feel free to let me know i will appreciate the help.
## Post #6
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-03-12T10:23:52+00:00
- Post Title: Noesis / Maxscript scripting questions

Hi, since i wasn't able to fix my last maxscript i tried alternative ways to export some meshes and i have managed to have some quite "good" results for exemple : 





I can export 100% of the vertices from any RGM now without any issues the only thing that bothers me are the faces... sometimes they are screwed and in some cases everything is fine i don't understand why, i'm using both ModelResearcher and Hex2obj for that...
If someone is interested i can provide some "problematic" samples cause it's really weird.

Also I don't have any new things on the structure of the format i just know the organization some bytes are still unknown to me more specifically for avatars... i have to remove these bytes and check how the game react to it maybe it will give me some ideas.

Anyway if someone have an idea for my maxscript feel free to let me know ! 
Have a nice day.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-12T14:03:23+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from Loginoux
>
> 
I can export 100% of the vertices from any RGM now without any issues the only thing that bothers me are the faces... sometimes they are screwed and in some cases everything is fine i don't understand why, i'm using both ModelResearcher and Hex2obj for that...
Normally it's because the face indices chunk is a group of submeshes referencing vertices starting from somewhere else at the vertices chunk. 
There should be some fields in the file telling you all the submeshes' indicies counts or something like that. Same thing can be applied to the vertices.
## Post #8
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-03-12T15:22:46+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from Bigchillghost
>
> Loginoux wrote:
I can export 100% of the vertices from any RGM now without any issues the only thing that bothers me are the faces... sometimes they are screwed and in some cases everything is fine i don't understand why, i'm using both ModelResearcher and Hex2obj for that...
Normally it's because the face indices chunk is a group of submeshes referencing vertices starting from somewhere else at the vertices chunk. 
There should be some fields in the file telling you all the submeshes' indicies counts or something like that. Same thing can be applied to the vertices.

Hum interesting, after my investigations (it could be 200% wrong) of the format i've noticed it's mainly something like : vertex count -> vertex buffer / Face count -> face buffer and when their is multiples meshes into 1 file it's just : [Object 1] vertex buffer / face buffer / texture string [Object 2] vertex buffer / face buffer... etc.

So i don't know if it could be the issue here, but it might be.
I just have to know how to read the faces correctly with hex2obj now that you informed me about that.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-13T00:01:24+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from Loginoux
>
> I just have to know how to read the faces correctly with hex2obj now that you informed me about that.
You have to find all the needed elements(counts & offsets) for each submesh, that's how hex2obj works.
## Post #10
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-03-16T15:17:59+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from Bigchillghost
>
> Loginoux wrote:I just have to know how to read the faces correctly with hex2obj now that you informed me about that.
You have to find all the needed elements(counts & offsets) for each submesh, that's how hex2obj works.

Let's take an exemple...
Here is the problematic file : [http://www.mediafire.com/file/h33mj31tf ... Fa3703.rgm](http://www.mediafire.com/file/h33mj31tfkg1rpc/%C2%BF%C2%A9%C3%80%C3%9A%C2%BC%C2%BC%C3%86%C2%AE%C3%81%C3%9Fa3703.rgm)

At first i'm trying to have a "point cloud" from the file i'm working with, in the case of this rgm everything is alright as you can see on the picture the values i entered seems correct.



But when it comes to faces (note that this is a single "mesh" RGM, every vertices are stored into 1 single vertex buffer) they are screwed !



Maybe i didn't understood what you were trying to explain to me ? i don't know...
Also i have trouble finding the UVs, some parts of the file are still weird for me especially what's after the face's short values array (at the end of the textures path strings).
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T18:54:09+00:00
- Post Title: Noesis / Maxscript scripting questions

sometimes you've to use less face indices, then look where to proceed with the next "submesh" even if you think there aren't any:



rgm.jpg (165.99 KiB) Viewed 448 times
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-17T00:57:00+00:00
- Post Title: Noesis / Maxscript scripting questions

> Reply from Loginoux
>
> Maybe i didn't understood what you were trying to explain to me ? i don't know...
This is what I mean:
To make it brief, I'll just skip those normals and UV stuffs. Say there's a file containing two submeshes where geo data are arranged like:

```
					then comes submesh 2		
v x11 y11 z11											v x21 y21 z21
v x12 y12 z12											v x22 y22 z22
v x13 y13 z13											v x23 y23 z23
...														...

f v11 v12 v13											f v21 v22 v23
...														...

```

For such case you can load these two submeshes one by one easily. But what if I put them together like this without updating the values of the indices of submesh 2?

```
v x12 y12 z12
v x13 y13 z13
...
v x21 y21 z21
v x22 y22 z22
v x23 y23 z23
...

f v11 v12 v13
...
f v21 v22 v23
...
```

In this case you can't load it as one single mesh. 
But obviously it has nothing to do with your condition. Here you're just making a mistake.
The triangle count before the indices buffer is a LONG32 interger.



whatever.jpg (106.12 KiB) Viewed 437 times
## Post #13
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2018-12-10T17:40:52+00:00
- Post Title: Noesis / Maxscript scripting questions

Hello guys, long time i haven't checked the forum lol
But after all : THANKS for the help !! i managed to learn a lot from it !!
I have a problem with the textures now...
I wrote a script that works fine, for now it parses the vertices, faces, and UVs correctly but once under max i can't put the textures on the mesh...
I don't know if maxscript can load textures for me but it don't really want the script to do it since it only works for 1 model not all the other ones yet (so instead doing it manually is still ok).

My problem is about the UVs, normally since the mesh is imported and the UVs parsed i should be able to place the texture directly on the mesh...
BUT it's not the case here, it's like i literally lost the UV, i don't understand why...



If someone have an idea, feel free to lemme know !
Thanks
