## Post #1
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-21T11:45:42+00:00
- Post Title: trackmania noesis problem

while i decompressed the gbx, i cannot convert most of the assets with noesis, because of the error, [https://www.mediafire.com/file/00s01vin ... d.Gbx/file](https://www.mediafire.com/file/00s01vinoyewq92/MainBodyHigh.Solid.Decompressed.Gbx/file) and [https://www.mediafire.com/file/ss88lsre ... 9.Gbx/file](https://www.mediafire.com/file/ss88lsreng3hqp5/MainbodyHigh.Solid.Decompressed%25282%2529.Gbx/file) are the files i tried
[unknown.png](https://xentaxbackup.github.io/file/20653_unknown.png)
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-29T16:41:44+00:00
- Post Title: trackmania noesis problem

actually, i fixed the mesh amount problem but i still need a fix for this one
## Post #3
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-22T19:27:26+00:00
- Post Title: trackmania noesis problem

also, the plugin doesn't support ascii gbx
## Post #4
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-01-17T15:08:46+00:00
- Post Title: trackmania noesis problem

bumpy lumpy jumpy
## Post #5
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-01-17T15:09:22+00:00
- Post Title: trackmania noesis problem

and also everything is positioned at the same location
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-17T16:32:57+00:00
- Post Title: trackmania noesis problem

> Reply from fajNYgosciu1234 ↑Mon Jan 17, 2022 11:09 pm at Mon Jan 17, 2022 11:09 pm
>
> 
and also everything is positioned at the same locationThe "clumped mesh" problem, maybe?

> Reply from Bigchillghost ↑Thu Jan 13, 2022 7:46 pm at Thu Jan 13, 2022 7:46 pm
>
> let along the vertices need to be transformed to the correct positions with the corresponding bone transformation info
--------------------
Concerning Gbx and the Noesis script: don't know the script (and if so wouldn't have the time to patch it), but mesh format looks simple:
.



dsStadiumCar-Gbx.png (97.78 KiB) Viewed 191 times
## Post #7
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-11-23T07:03:54+00:00
- Post Title: trackmania noesis problem

[https://cdn.discordapp.com/attachments/ ... _gbx_PC.py](https://cdn.discordapp.com/attachments/776437698629599253/1044662365230215198/fmt_Trackmania_gbx_PC.py)
here's the plug-in, it can't read some or most cars with gbx decompressed
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-23T12:10:32+00:00
- Post Title: trackmania noesis problem

> Reply from fajNYgosciu1234 ↑Wed Nov 23, 2022 3:03 pm at Wed Nov 23, 2022 3:03 pm
>
> 
https://cdn.discordapp.com/attachments/ ... _gbx_PC.py
here's the plug-in, it can't read some or most cars with gbx decompressedThanks; whom is the py script from? (There are not many scripts that use bs.data[addr:bs.dataSize])

btw: any script is rather worthless as long as it isn't accompanied by a working sample, here .gbx.
(Not working samples aren't very helpful for trying to patch scripts.)

This is the patched script (sorry to unknown original author for spoiling it  ) to give you the idea.
Loads one sub mesh only. Fails with MainbodyHigh.Solid.Decompressed.Gbx

```
import noesis
#import rapi

def registerNoesisTypes():
	handle = noesis.register("Trackmania",".gbx")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "GBX"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      print("'gbx' not found!")
      return 0
   return 1  	

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)

	texList = []
	matList = []
	TexNames = []

	bs.seek(0x89, NOESEEK_REL)
	NumMeshes = bs.readUInt()

	for i in range(1):
		addr=bs.tell()
		fileBuff = bs.data[addr:bs.dataSize]
		addr1= fileBuff.find(b'\x0E\x60\x00\x09\x38\x00\x00')
		addr += addr1
		bs.seek(addr);print(hex(addr))
		bs.seek(-0x48, NOESEEK_REL)
		MaterialName = (bs.readBytes(8).decode("ASCII").lstrip("\0FF"))
		#bs.seek(0x4C, NOESEEK_REL)

		addr=bs.tell()
		fileBuff = bs.data[addr:bs.dataSize]
		addr1= fileBuff.find(b'\x38\x00\x00\x00\x01\x00\x00\x00')
		print(hex(addr),hex(addr1))
		addr += addr1 + 8
		bs.seek(addr);print(hex(addr))

		VCount = bs.readUInt();print("vCnt: ", VCount, MaterialName)
		if VCount == 0:
			print("not supported"); return 1
		bs.seek(0x8, NOESEEK_REL)
		UVAddress = bs.tell()
		UVsize = VCount*8
		UVBuff = bs.readBytes(UVsize)
		rapi.rpgBindUV1BufferOfs(UVBuff, noesis.RPGEODATA_FLOAT, 8, 0)
		bs.seek(0x28, NOESEEK_REL)			
		VAddress= bs.tell()
		FVFsize = int(40)
		VBuff = bs.readBytes(VCount*FVFsize)
		rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
		bs.seek(0x18, NOESEEK_REL)
		FCount = bs.readUInt()
		FAddress= bs.tell();print(hex(FAddress))
		FBuff = bs.readBytes(FCount*2)
		rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, FCount, noesis.RPGEO_TRIANGLE, 1)
		material = NoeMaterial(MaterialName,"")
		matList.append(material)
		rapi.rpgSetMaterial(MaterialName)
		bs.seek(addr+1, NOESEEK_ABS)

	mdl = rapi.rpgConstructModel()
	mdl.setModelMaterials(NoeModelMaterials(texList, matList))
	mdlList.append(mdl)
	rapi.rpgClearBufferBinds()
	return 1
```

You may change line 33 to

```
	for i in range(5):
```
This will show the 4 wheels' material names, but doesn't load their meshes.
.



ds stadium car-Gbx.jpg (30.08 KiB) Viewed 120 times
## Post #9
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-11-23T14:45:31+00:00
- Post Title: trackmania noesis problem

> Reply from shakotay2 ↑Wed Nov 23, 2022 8:10 pm at Wed Nov 23, 2022 8:10 pm
>
> 
fajNYgosciu1234 wrote: ↑Wed Nov 23, 2022 3:03 pm
https://cdn.discordapp.com/attachments/ ... _gbx_PC.py
here's the plug-in, it can't read some or most cars with gbx decompressed
Thanks; whom is the py script from? (There are not many scripts that use bs.data[addr:bs.dataSize])

btw: any script is rather worthless as long as it isn't accompanied by a working sample, here .gbx.
(Not working samples aren't very helpful for trying to patch scripts.)

This is the patched script (sorry to unknown original author for spoiling it  ) to give you the idea.
Loads one sub mesh only. Fails with MainbodyHigh.Solid.Decompressed.Gbx
Code: Select allfrom inc_noesis import *
import noesis
#import rapi

def registerNoesisTypes():
	handle = noesis.register("Trackmania",".gbx")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "GBX"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      print("'gbx' not found!")
      return 0
   return 1  	

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)

	texList = []
	matList = []
	TexNames = []

	bs.seek(0x89, NOESEEK_REL)
	NumMeshes = bs.readUInt()

	for i in range(1):
		addr=bs.tell()
		fileBuff = bs.data[addr:bs.dataSize]
		addr1= fileBuff.find(b'\x0E\x60\x00\x09\x38\x00\x00')
		addr += addr1
		bs.seek(addr);print(hex(addr))
		bs.seek(-0x48, NOESEEK_REL)
		MaterialName = (bs.readBytes(8).decode("ASCII").lstrip("\0FF"))
		#bs.seek(0x4C, NOESEEK_REL)

		addr=bs.tell()
		fileBuff = bs.data[addr:bs.dataSize]
		addr1= fileBuff.find(b'\x38\x00\x00\x00\x01\x00\x00\x00')
		print(hex(addr),hex(addr1))
		addr += addr1 + 8
		bs.seek(addr);print(hex(addr))

		VCount = bs.readUInt();print("vCnt: ", VCount, MaterialName)
		if VCount == 0:
			print("not supported"); return 1
		bs.seek(0x8, NOESEEK_REL)
		UVAddress = bs.tell()
		UVsize = VCount*8
		UVBuff = bs.readBytes(UVsize)
		rapi.rpgBindUV1BufferOfs(UVBuff, noesis.RPGEODATA_FLOAT, 8, 0)
		bs.seek(0x28, NOESEEK_REL)			
		VAddress= bs.tell()
		FVFsize = int(40)
		VBuff = bs.readBytes(VCount*FVFsize)
		rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
		bs.seek(0x18, NOESEEK_REL)
		FCount = bs.readUInt()
		FAddress= bs.tell();print(hex(FAddress))
		FBuff = bs.readBytes(FCount*2)
		rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, FCount, noesis.RPGEO_TRIANGLE, 1)
		material = NoeMaterial(MaterialName,"")
		matList.append(material)
		rapi.rpgSetMaterial(MaterialName)
		bs.seek(addr+1, NOESEEK_ABS)

	mdl = rapi.rpgConstructModel()
	mdl.setModelMaterials(NoeModelMaterials(texList, matList))
	mdlList.append(mdl)
	rapi.rpgClearBufferBinds()
	return 1
You may change line 33 to
Code: Select all	for i in range(5):This will show the 4 wheels' material names, but doesn't load their meshes.
.
ds stadium car-Gbx.jpg
the plug-in i found was from the vg resource forums [https://www.vg-resource.com/thread-37380.html](https://www.vg-resource.com/thread-37380.html)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-23T15:07:26+00:00
- Post Title: trackmania noesis problem

Ok, the script author is Tuliopilloto.
who wrote to squidiskool 
> This script was tested only with the file you posted, so there is no guarantee that it will work with all files.
## Post #11
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2023-04-09T19:45:55+00:00
- Post Title: trackmania noesis problem

Hi I would like to know how to convert a mod because gbx to obj 
I am looking for a script for blender or noesis tools thank you.

[https://www.vg-resource.com/thread-37380-page-2.html](https://www.vg-resource.com/thread-37380-page-2.html)

i want to get these 2 mods for private use thanks for any help or info

[https://drive.google.com/u/0/uc?id=1ZBc ... t=download](https://drive.google.com/u/0/uc?id=1ZBccfDh6w56va0HwqQ99MouzJc2nSdhU&export=download)
## Post #12
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-05-20T15:02:19+00:00
- Post Title: trackmania noesis problem

[https://cdn.discordapp.com/attachments/ ... ressed.Gbx](https://cdn.discordapp.com/attachments/493152982293282816/1109495890219106435/Detroit.Item.Decompressed.Gbx)
[https://cdn.discordapp.com/attachments/ ... ressed.Gbx](https://cdn.discordapp.com/attachments/493152982293282816/1109494155631149076/CustomModTrans_2.Item.Decompressed.Gbx)
[https://cdn.discordapp.com/attachments/ ... ressed.Gbx](https://cdn.discordapp.com/attachments/493152982293282816/1109494154624508076/RoadBump_10.Item.Decompressed.Gbx)
[https://cdn.discordapp.com/attachments/ ... ressed.Gbx](https://cdn.discordapp.com/attachments/493152982293282816/1109494153592705024/RoadBump_8.Item.Decompressed.Gbx)
[https://cdn.discordapp.com/attachments/ ... ressed.Gbx](https://cdn.discordapp.com/attachments/493152982293282816/1109490561662075021/WildWest1.Item.Decompressed.Gbx)
several samples from mappacks which were extracted from a zip file
one of these contain textures, so it's like table top racing stores it in .amodel
opening these in noesis gives an error about uv size
