## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-05T05:49:58+00:00
- Post Title: Custom .elu models in search of their UV's!

Hello!well as the title says I'm trying to figure how to get the UV's from the meshes inside the custom .elu models. 
I have been asking people with more knowledge about this, and since I was able to extract all the meshes that the .elu model contains, now what would be missing is to be able to extract them with their corresponding uv's, but according to I have asked the uv's are tied to the triangles .Therefore, it is not possible to extract them with hex2obj, AMR or MR, it only remains to extract it with a script.

There is already a script to open these models, but it does not work for the .elu that I want to extract, but by checking the script for blender 2.49b, I have been able to realize some things, such as:

```
        px, py, pz = struct.unpack('<3f', file_object.read(12))

        position = Blender.Mathutils.Vector(px, pz, py)

        mesh.verts.extend(position)

```


After 3F the block begins, and the DWORD is just before the 3F, I have followed this method and I have been able to calculate the vertices count and faces counts. In the case of full armor, it is divided into head, chest, hands, legs and feet, although the order may vary.
Another thing I have been able to notice is that before the block begins there is a part in text that says the name of the mesh that will come next, example "eq_chest ..", so if you search for "eq_" in the editor, you will find in almost most of cases 5 sections, which are the 5 meshes that make up the complete model.

Well, until this part I have been able to achieve it, I am just learning a little more how to quickly identify the blocks and be able to extract the models, but to be honest with respect to the values ​​of the uv's I know very little, someone who knows more can take a look at the blender script, and thus be able to modify it, since I have realized that it does not vary much with the normal model that the script can open, only that the position of the blocks and the value of the header have changed a bit, well no I'm sure it's just that, but it's something I've identified after looking at the model and script.

Well, the other alternative that I have tried is to change the format of the custom .elu so that it has the same order as the normal .elu, which can be opened with the script, since I have previously modified that way for other games and has had result, but in this one still not, but at least I was able to load the vertices, I already know that it is not the best way, but I still do not understand the script much and I feel that it is easier to modify some values ​​in the hex editor (at least for my).

I'll add the script that works in blender 2.49b, and a model that can be opened with the script, and then the other custom model. By the way the script opens mesh (with their uv's), loads the textures, and the bones with their respective weights. I only want the mesh section and its respective UV's, as I mentioned I have already been able to extract the meshes (with AMR and MR), I still lack the UV's. Hope someone can give me a hand with this, and thanks for your time reading this.  

Script: [https://www.mediafire.com/file/1snjgoz7 ... rt.py/file](https://www.mediafire.com/file/1snjgoz7lodivp2/gunz_import.py/file)
Custom .elu model: [https://www.mediafire.com/file/wteabqzp ... el.7z/file](https://www.mediafire.com/file/wteabqzplg8107t/Custom_.elu_model.7z/file)
Normal .elu model: [https://www.mediafire.com/file/6ye4o2vm ... el.7z/file](https://www.mediafire.com/file/6ye4o2vmc1vyj4v/Normal_.elu_model.7z/file)

To the left, meshes extracted (with AMR and MR), at the right when I edited a bit the custom .elu model to suit the normal .elu and it can be opened by the script, well it fails.



test16.png (37.03 KiB) Viewed 127 times



A special thanks to shakotay2, DKDave and Bigchillghost, what little I know I have learned with their help.
## Post #2
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-06T15:43:46+00:00
- Post Title: Custom .elu models in search of their UV's!

bump!
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-07T11:20:42+00:00
- Post Title: Custom .elu models in search of their UV's!

Well, not a fan of Blender so I did it with Noesis:

```

import rapi
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("custom elu", ".elu;")
	noesis.setHandlerTypeCheck(handle, checkType)
	noesis.setHandlerLoadModel(handle, convModel)
	return 1

#check if it's this type based on the data
def checkType(data):
	if len(data) < 0x80:
		return 0
	bs = NoeBitStream(data)
	Magic = bs.readUInt()
	if Magic != 0x107F060:
		return 0
	Version = bs.readUInt()
	if Version != 0:
		return 0
	return 1

#convert the model to obj
def convModel(data, mdlList):
	boneCnt = 0x1F # this field must be assigned manually
	meshCnt = 5 # this field must be assigned manually
	bs = NoeBitStream(data)
	bs.seek(0x12, NOESEEK_ABS)
	outName = rapi.getInputName().replace("elu","obj")
	ObjFile = open(outName, "wb")
	ObjFile.write(b'# Wavefront OBJ\n\n')
	accIndexBase = 1
	accByPolyVertIdx = 1
	for i in range(0, meshCnt):
		Len = bs.readUShort()
		meshName = noeStrFromBytes(bs.readBytes(Len))
		Len = bs.readUShort()
		bs.seek(Len, NOESEEK_REL)
		bs.seek(boneCnt*0x14, NOESEEK_REL)
		vertCnt = bs.readUInt()
		posStream = NoeBitStream()
		for j in range(0, vertCnt):
			x,y,z = bs.readFloat(),bs.readFloat(),bs.readFloat()
			posStream.writeString('v %f %f %f\n'%(x,y,z), 0)
		posStream.writeString('# %d vertices\n\n'%vertCnt, 0)
			
		polyCnt = bs.readUInt()
		polyStream = NoeBitStream()
		uvStream = NoeBitStream()
		polyStream.writeString('g %s\n'%meshName, 0)
		for j in range(0, polyCnt):
			polyStream.writeString('f', 0)
			for k in range(0, 3):
				vertIdx = bs.readInt() + accIndexBase
				polyStream.writeString(' %d/%d/%d'%(vertIdx, accByPolyVertIdx, accByPolyVertIdx), 0)
				accByPolyVertIdx += 1
			polyStream.writeString('\n', 0)
			for k in range(0, 3):
				u,v,w = bs.readFloat(),bs.readFloat(),bs.readFloat()
				uvStream.writeString('vt %f %f\n'%(u,1.0-v), 0)
			bs.seek(8, NOESEEK_REL)
		accIndexBase += vertCnt
		uvStream.writeString('# %d texture coordinates\n\n'%(polyCnt*3), 0)
		polyStream.writeString('# %d triangles\n\n'%polyCnt, 0)
		
		nmStream = NoeBitStream()
		for j in range(0, polyCnt):
			bs.seek(12, NOESEEK_REL)
			for k in range(0, 3):
				x,y,z  = bs.readFloat(),bs.readFloat(),bs.readFloat()
				nmStream.writeString('vn %f %f %f\n'%(x,y,z), 0)
		nmStream.writeString('# %d normals\n\n'%(polyCnt*3), 0)
		
		ObjFile.write(posStream.getBuffer())
		ObjFile.write(nmStream.getBuffer())
		ObjFile.write(uvStream.getBuffer())
		ObjFile.write(polyStream.getBuffer())
		
		bs.seek(8, NOESEEK_REL)
		blendInfoCnt = bs.readUInt()
		for j in range(0, blendInfoCnt):
			weightNum = bs.readUByte()
			for k in range(0, weightNum):
				boneID = bs.readInt()
				weight = bs.readFloat()
				bs.seek(12, NOESEEK_REL)
				boneNameLen = bs.readUShort()
				bs.seek(boneNameLen, NOESEEK_REL)
		if i == 0:
			for j in range(0, boneCnt):
				boneNameLen = bs.readUShort()
				bs.seek(boneNameLen, NOESEEK_REL)
				parentBoneNameLen = bs.readUShort()
				bs.seek(parentBoneNameLen, NOESEEK_REL)
				bs.seek(0x26C, NOESEEK_REL)
				cnt = bs.readInt()
				bs.seek(cnt*12, NOESEEK_REL)
				cnt2 = bs.readInt()
				bs.seek(cnt2*0x38, NOESEEK_REL)
				bs.seek(cnt2*0x30+0xC, NOESEEK_REL)
		
	ObjFile.close()
	return 0

```

There'll be an obj file created at the same path as the input elu model and the script will not load it otherwise Noesis will crash.
Note that there's no count records for bones and meshes in the file so you must assign them manually at line 30 & 31 in the script for other custom elu files.
[bloodsuit.jpg](https://xentaxbackup.github.io/file/19866_bloodsuit.jpg)
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-08T15:50:42+00:00
- Post Title: Custom .elu models in search of their UV's!

> Reply from Bigchillghost ↑Wed Apr 07, 2021 7:20 pm at Wed Apr 07, 2021 7:20 pm
>
> 
Well, not a fan of Blender so I did it with Noesis:
Code: Select all# custom elu importer by Bigchillghost

import rapi
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("custom elu", ".elu;")
	noesis.setHandlerTypeCheck(handle, checkType)
	noesis.setHandlerLoadModel(handle, convModel)
	return 1

#check if it's this type based on the data
def checkType(data):
	if len(data) < 0x80:
		return 0
	bs = NoeBitStream(data)
	Magic = bs.readUInt()
	if Magic != 0x107F060:
		return 0
	Version = bs.readUInt()
	if Version != 0:
		return 0
	return 1

#convert the model to obj
def convModel(data, mdlList):
	boneCnt = 0x1F # this field must be assigned manually
	meshCnt = 5 # this field must be assigned manually
	bs = NoeBitStream(data)
	bs.seek(0x12, NOESEEK_ABS)
	outName = rapi.getInputName().replace("elu","obj")
	ObjFile = open(outName, "wb")
	ObjFile.write(b'# Wavefront OBJ\n\n')
	accIndexBase = 1
	accByPolyVertIdx = 1
	for i in range(0, meshCnt):
		Len = bs.readUShort()
		meshName = noeStrFromBytes(bs.readBytes(Len))
		Len = bs.readUShort()
		bs.seek(Len, NOESEEK_REL)
		bs.seek(boneCnt*0x14, NOESEEK_REL)
		vertCnt = bs.readUInt()
		posStream = NoeBitStream()
		for j in range(0, vertCnt):
			x,y,z = bs.readFloat(),bs.readFloat(),bs.readFloat()
			posStream.writeString('v %f %f %f\n'%(x,y,z), 0)
		posStream.writeString('# %d vertices\n\n'%vertCnt, 0)
			
		polyCnt = bs.readUInt()
		polyStream = NoeBitStream()
		uvStream = NoeBitStream()
		polyStream.writeString('g %s\n'%meshName, 0)
		for j in range(0, polyCnt):
			polyStream.writeString('f', 0)
			for k in range(0, 3):
				vertIdx = bs.readInt() + accIndexBase
				polyStream.writeString(' %d/%d/%d'%(vertIdx, accByPolyVertIdx, accByPolyVertIdx), 0)
				accByPolyVertIdx += 1
			polyStream.writeString('\n', 0)
			for k in range(0, 3):
				u,v,w = bs.readFloat(),bs.readFloat(),bs.readFloat()
				uvStream.writeString('vt %f %f\n'%(u,1.0-v), 0)
			bs.seek(8, NOESEEK_REL)
		accIndexBase += vertCnt
		uvStream.writeString('# %d texture coordinates\n\n'%(polyCnt*3), 0)
		polyStream.writeString('# %d triangles\n\n'%polyCnt, 0)
		
		nmStream = NoeBitStream()
		for j in range(0, polyCnt):
			bs.seek(12, NOESEEK_REL)
			for k in range(0, 3):
				x,y,z  = bs.readFloat(),bs.readFloat(),bs.readFloat()
				nmStream.writeString('vn %f %f %f\n'%(x,y,z), 0)
		nmStream.writeString('# %d normals\n\n'%(polyCnt*3), 0)
		
		ObjFile.write(posStream.getBuffer())
		ObjFile.write(nmStream.getBuffer())
		ObjFile.write(uvStream.getBuffer())
		ObjFile.write(polyStream.getBuffer())
		
		bs.seek(8, NOESEEK_REL)
		blendInfoCnt = bs.readUInt()
		for j in range(0, blendInfoCnt):
			weightNum = bs.readUByte()
			for k in range(0, weightNum):
				boneID = bs.readInt()
				weight = bs.readFloat()
				bs.seek(12, NOESEEK_REL)
				boneNameLen = bs.readUShort()
				bs.seek(boneNameLen, NOESEEK_REL)
		if i == 0:
			for j in range(0, boneCnt):
				boneNameLen = bs.readUShort()
				bs.seek(boneNameLen, NOESEEK_REL)
				parentBoneNameLen = bs.readUShort()
				bs.seek(parentBoneNameLen, NOESEEK_REL)
				bs.seek(0x26C, NOESEEK_REL)
				cnt = bs.readInt()
				bs.seek(cnt*12, NOESEEK_REL)
				cnt2 = bs.readInt()
				bs.seek(cnt2*0x38, NOESEEK_REL)
				bs.seek(cnt2*0x30+0xC, NOESEEK_REL)
		
	ObjFile.close()
	return 0

There'll be an obj file created at the same path as the input elu model and the script will not load it otherwise Noesis will crash.
Note that there's no count records for bones and meshes in the file so you must assign them manually at line 30 & 31 in the script for other custom elu files.

wowoowoowowwowo!THANKS Bigchillghost
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-08T16:36:29+00:00
- Post Title: Custom .elu models in search of their UV's!

```
	boneCnt = 0x1F # this field must be assigned manually
	meshCnt = 5 # this field must be assigned manually


```


> There'll be an obj file created at the same path as the input elu model and the script will not load it otherwise Noesis will crash.
>
> Note that there's no count records for bones and meshes in the file so you must assign them manually at line 30 & 31 in the script for other custom elu files.
Bigchillghost!, in case of the katana.elu, meshCnt should be = 1, but how about the boneCnt? how to calculate it depending on the model?
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-08T17:17:43+00:00
- Post Title: Custom .elu models in search of their UV's!

One last question if I can,  is about this model, the header is a bit different, the "gz_hum_DesertWarrior.tgaV³d" should be "eq_legs_DesertWarrior" and the "gz_hum_DesertWarrior.tga" should be at the end of the file, also I change a bit on the header in these part, but the noesis just crash xD. So, I'm doing something wrong.  Thanks!  

[https://www.mediafire.com/file/ruj8kios ... r.elu/file](https://www.mediafire.com/file/ruj8kios4q1y5we/man-parts_DesertWarrior.elu/file)



example.png (11.4 KiB) Viewed 64 times
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-09T14:49:38+00:00
- Post Title: Custom .elu models in search of their UV's!

> Reply from moonpaladin ↑Fri Apr 09, 2021 12:36 am at Fri Apr 09, 2021 12:36 am
>
> 
Bigchillghost!, in case of the katana.elu, meshCnt should be = 1, but how about the boneCnt? how to calculate it depending on the model?
You know you don't have to mention my ID at the begining of almost every reply of yours, right?    

For katana_eSkatana.elu, there's no bones in the file so boneCnt = 0. But anyway I've managed to determine them automatically so no need for any manual assignment. Here's the latest version of the script:


 fmt_custom_elu.zip
(1.32 KiB) Downloaded 13 times


Compatible with also the DesertWarrior sample from your last post.

An interesting fact though, there're also 5 meshes and 0x1F bones in the DesertWarrior model. Not sure if all skeletal models of this "custom" elu format comply to that.
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-09T15:46:22+00:00
- Post Title: Custom .elu models in search of their UV's!

> You know you don't have to mention my ID at the begining of almost every reply of yours, right?

XD! You right!. Thanks Bigchillghost, really appreciate that you taked your time on this!
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-09T16:19:12+00:00
- Post Title: Custom .elu models in search of their UV's!

> You know you don't have to mention my ID at the begining of almost every reply of yours, right?    
>
> 
>
> For katana_eSkatana.elu, there's no bones in the file so boneCnt = 0. But anyway I've managed to determine them automatically so no need for any manual assignment. Here's the latest version of the script:
>
> fmt_custom_elu.zip
>
> Compatible with also the DesertWarrior sample from your last post.
>
> 
>
> An interesting fact though, there're also 5 meshes and 0x1F bones in the DesertWarrior model. Not sure if all skeletal models of this "custom" elu format comply to that.

@Bigchillghost, I had this same error with the first attempt of the script, but anyways it exported the model, but with this model is just exporting the first two meshes (chest and legs), what is that error refering? because this model doesn't have much difference (Only at the end as I can see), This one uses 1 textures per each mesh, not one for entire model like the others examples models.   Thanks!

[https://www.mediafire.com/file/vhg33kg4 ... k.elu/file](https://www.mediafire.com/file/vhg33kg4814jnjf/woman-parts_gpunk.elu/file)
[https://www.mediafire.com/file/vxiqcrnu ... k.elu/file](https://www.mediafire.com/file/vxiqcrnuhm1nd8y/man-parts_gpunk.elu/file)



error25.png (47.3 KiB) Viewed 47 times
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-10T06:27:18+00:00
- Post Title: Custom .elu models in search of their UV's!

> Reply from moonpaladin ↑Sat Apr 10, 2021 12:19 am at Sat Apr 10, 2021 12:19 am
>
> I had this same error with the first attempt of the script, but anyways it exported the model, but with this model is just exporting the first two meshes (chest and legs)
I see. This format treated everything as mesh objects including these "Bip" objects. Just realized that.
Here's the updated script where "Bip" meshes are discarded in the output:


 fmt_custom_elu.zip
(1.19 KiB) Downloaded 13 times
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-10T13:48:21+00:00
- Post Title: Custom .elu models in search of their UV's!

> Reply from Bigchillghost ↑Sat Apr 10, 2021 2:27 pm at Sat Apr 10, 2021 2:27 pm
>
> 
moonpaladin wrote: ↑Sat Apr 10, 2021 12:19 amI had this same error with the first attempt of the script, but anyways it exported the model, but with this model is just exporting the first two meshes (chest and legs)

I see. This format treated everything as mesh objects including these "Bip" objects. Just realized that.
Here's the updated script where "Bip" meshes are discarded in the output:
fmt_custom_elu.zip

Thanks! Bigchillghost
