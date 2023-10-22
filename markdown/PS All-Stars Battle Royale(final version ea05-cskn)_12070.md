## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-10-09T05:44:40+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

I obtained some models from Playstation all stars battle royale dumping the vram from the console.

The IDmagic has changed from the beta version (MODL to EA05) the vertex size is 16 and the uv pos is 12 (I used hex2obj for obtain some meshes but with this method some faces are lost), also I used the decompresed faces from vram dump over the meshes in t-pose but not all faces are in the dump file (the dump file only have the faces that are shown front to the camera, all faces behind are not rendered)

I extracted this mesh with hex2obj (some faces are lost)



here are some models

[http://www.mediafire.com/download/wnu9c ... a_ea05.rar](http://www.mediafire.com/download/wnu9cxac7oa7dx7/psa_ea05.rar)

here is a model + the old noesis script by chrrox for import cskn meshes.

[http://www.mediafire.com/download/6vkbz ... suit02.rar](http://www.mediafire.com/download/6vkbzf5x41oj05c/radec_alternativesuit02.rar)

the original files use edge indices compression, maybe someone can modify the script for import this files to noesis with all faces 

thanks
## Post #2
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2014-10-09T10:31:56+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

You can loaded manually each mesh.


```
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("Playstation All Stars", ".cskn")
	noesis.setHandlerTypeCheck(handle, binModCheckType)
	noesis.setHandlerLoadModel(handle, binModLoadModel)
	#noesis.logPopup()

	return 1


def binModCheckType(data):
	td = NoeBitStream(data)
	return 1

class binFile: 
         
	def __init__(self, bs):
		self.bs = bs
		rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
		self.texList  = []
		self.matList  = [] 
		self.boneList = []
		self.boneMap  = []
		self.offsetList = []
		self.meshOffsets = []

	def loadAll(self, bs):
		indexCount = 0x8A0
		indexSize = 0x370
		indexOffset = 0x1C00
		bs.seek(indexOffset, NOESEEK_ABS)
		edgeData = bs.readBytes(indexSize)
		edgeDecomp = rapi.decompressEdgeIndices(edgeData, indexCount)
		for i in range(0, indexCount):
			t = edgeDecomp[i*2]
			edgeDecomp[i*2] = edgeDecomp[i*2 + 1]
			edgeDecomp[i*2 + 1] = t

		vertexOffset = 0x1F70
		bs.seek(vertexOffset, NOESEEK_ABS)
		vertCount = 0x1A2
		vSize = 0x10
		vertBuff = bs.readBytes(vSize * vertCount)
		#UVBuff = bs.readBytes(vertCount * 6)
		#rapi.rpgBindUV1BufferOfs(UVBuff, noesis.RPGEODATA_SHORT, 6, 0)
		rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, vSize, 0)
		#rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vertCount, noesis.RPGEO_POINTS, 1)
		rapi.rpgCommitTriangles(edgeDecomp, noesis.RPGEODATA_USHORT, indexCount, noesis.RPGEO_TRIANGLE, 1)

def binModLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bin = binFile(NoeBitStream(data, NOE_BIGENDIAN))
	bin.loadAll(bin.bs)
	try:
		mdl = rapi.rpgConstructModel()
	except:
		mdl = NoeModel()
	mdl.setModelMaterials(NoeModelMaterials(bin.texList, bin.matList))
	mdlList.append(mdl); mdl.setBones(bin.boneList)	
	return 1
```
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-09T14:06:10+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

thx, kovalevich007. I added some lines to your script if you don't mind:

```
from inc_noesis import *

indOffArr = [0x1C00, 0x5100, 0x10100, 0x1B280, 0x26800, 0x31B00, 0x3CE80, 0x42280, 0x4DC00]# 4 addresses to be added
matName = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12"]

def registerNoesisTypes():
   handle = noesis.register("Playstation All Stars", ".cskn")
   noesis.setHandlerTypeCheck(handle, binModCheckType)
   noesis.setHandlerLoadModel(handle, binModLoadModel)
   #noesis.logPopup()

   return 1


def binModCheckType(data):
   td = NoeBitStream(data)
   return 1

class binFile:
         
   def __init__(self, bs):
      self.bs = bs
      rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
      self.texList  = []
      self.matList  = []
      self.boneList = []
      self.boneMap  = []
      self.offsetList = []
      self.meshOffsets = []
      self.materials = []

   def loadAll(self, bs):
      dataTableOffs = 0x1546
      for j in range(0, 9):
        self.materials.append(j)
        indexOffset = indOffArr[j]
        bs.seek(dataTableOffs, NOESEEK_ABS)
        bs.seek(2, NOESEEK_REL)
        vertCount = bs.readUShort()
        indexCount =  bs.readUShort()
        #print("indCnt: %d vertCnt: %d" %(indexCount, vertCount))
        bs.seek(8, NOESEEK_REL)
        #indexCount = 0x8A0
        #indexSize = 0x370
        indexSize =  bs.readUShort()
        bs.seek(indexOffset, NOESEEK_ABS)
        edgeData = bs.readBytes(indexSize)
        edgeDecomp = rapi.decompressEdgeIndices(edgeData, indexCount)
        for i in range(0, indexCount):
           t = edgeDecomp[i*2]
           edgeDecomp[i*2] = edgeDecomp[i*2 + 1]
           edgeDecomp[i*2 + 1] = t

        #vertexOffset = 0x1F70
        vertexOffset = indexOffset + indexSize
        print("indexOff: 0x%x, cnt: %d, size: 0x%x,  vertOff: 0x%x, cnt: %d" %(indexOffset, indexCount, indexSize, vertexOffset, vertCount))
        bs.seek(vertexOffset, NOESEEK_ABS)
        #vertCount = 0x1A2
        vSize = 0x10
        vertBuff = bs.readBytes(vSize * vertCount)
        #UVBuff = bs.readBytes(vertCount * 6)
        #rapi.rpgBindUV1BufferOfs(UVBuff, noesis.RPGEODATA_SHORT, 6, 0)
        rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, vSize, 0)
        #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, vertCount, noesis.RPGEO_POINTS, 1)
        rapi.rpgSetMaterial(matName[j])
        rapi.rpgCommitTriangles(edgeDecomp, noesis.RPGEODATA_USHORT, indexCount, noesis.RPGEO_TRIANGLE, 1)
        dataTableOffs += 128

def binModLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bin = binFile(NoeBitStream(data, NOE_BIGENDIAN))
   bin.loadAll(bin.bs)
   try:
      mdl = rapi.rpgConstructModel()
   except:
      mdl = NoeModel()
   mdl.setModelMaterials(NoeModelMaterials(bin.texList, bin.matList))
   mdlList.append(mdl); mdl.setBones(bin.boneList)   
   return 1
```


now you'll get 9 submeshes from the radec_suit02.
I'm pretty sure there are 4 more submeshes but I got lost when trying to find the last 4 offsets for the IndOffsArr I introduced.

The max range of for i in range(0, 9) must be set to 13  (or size of IndOffsArr)
or other value for other models.
dataTableOffs = 0x1546 also to be changed for different models.



radec_suit02.jpg (97.09 KiB) Viewed 883 times



(Maybe someone else will find a method to get the submesh count and the indexOffsets automatically?)
For this suit search for FFFFFFFF22. You'll find it 13 times (== 13 submeshes?).
## Post #4
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2014-10-09T15:26:07+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

indOffArr = [0x1C00, 0x5100, 0x10100, 0x1B280, 0x26800, 0x31B00, 0x3CE80, 0x42280, 0x4DC00, 0x59800, 0x5D400, 0x69280, 0x74280]
for i in range(0, 13)

[](http://img-fotki.yandex.ru/get/6817/53372620.0/0_ec634_1c4cd924_orig)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-09T18:08:14+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

how to build groups (i.e. submeshes) using Noesis script?
(so that exported wavefront models contain lines such as
g mesh0)

I tried it manually for the first 4 submeshes and first I thought I failed
since the left foot wasn't part of the lower body (left part of pic).

Then I realized that it's a matter of material to be introduced (simply used the loop index for generating name and index).
btw: I changed the loop var i to j in the script of my previous post



radec_suit02_SM0to3.png (234.93 KiB) Viewed 866 times


really don't know why they separated the foot and the arm.  (prefer playing RPGs where NPCs may lose their life but never separate body parts...)
## Post #6
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2014-10-09T18:36:22+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

```
rapi.rpgSetMaterial(str(indexOffset))
```


Another would be to understand how to get the UV...
## Post #7
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-10-09T21:37:15+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

thanks kovalevich007 and shakotay2 for the help!! 
The only thing I know about uvs, they are in half float. I don't know much about noesis script and his structure but the script posted here is easy to understand for import other meshes from other characters
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-10T06:11:47+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

thx.
UVBuff = rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vSize, 12)



radec_suit02_uvs.jpg (176.99 KiB) Viewed 835 times
## Post #9
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-10-10T08:30:15+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

> Reply from shakotay2
>
> UVBuff = rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_HALFFLOAT, vSize, 12)

Thanks! works fine in all meshes
## Post #10
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2014-10-10T10:09:02+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

thx shakotay2.
[](http://img-fotki.yandex.ru/get/5113/53372620.0/0_ec699_2e99275_orig)
## Post #11
- Username: WareWolff
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 26, 2014 6:53 pm
- Post datetime: 2014-10-13T14:40:22+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

awesome! i thought most people had just quit on ps all-stars models a while back, nice to see more recent progress, hopefully we will eventually see Drake, Cole, Emmett (if possible, because he's dlc), or Polygon Man's models
## Post #12
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-10-29T22:30:28+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

Can this script be used to get the UVs from the cskn models from the PSA-S beta?
## Post #13
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2016-03-19T18:40:10+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

Sorry for the gigantic bump, but I have a memory dump which I've been extracting things from, but the script hasn't been working on anything. It's either been crashing or getting this error:


Here's what I'm trying to load:
[http://puu.sh/nMmVX.cskn](http://puu.sh/nMmVX.cskn)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-19T19:54:39+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

> Reply from lemurboy12
>
> , but the script hasn't been working on anything. It's either been crashing or getting this error:guess, you didn't read this thread, did you?  
(looks like you were using chrrox' original script)

Using the script from this thread we were talking about 17 months ago gives this:


 Lemurboy-test1out.zip
(26.23 KiB) Downloaded 69 times


indOffsArr  = [0xCF80, ...]
dataTableOffs = 0xCEC6

hehehe, 3 downloads within 5 minutes?
sry, it's just a sphere, nothing more
## Post #15
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2016-03-20T03:18:04+00:00
- Post Title: PS All-Stars Battle Royale(final version ea05-cskn)

I was using the script from this thread.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-20T09:21:32+00:00
- Post Title: Re: PS All-Stars Battle Royale(final version ea05-cskn)

then read my post as of Thu Oct 09, 2014 3:06 pm:

> dataTableOffs = 0x1546 also to be changed for different models.
indOffsArr  = [...] and for j in range(0, numberOfSubmeshes): also have to be adapted.
(numberOfSubMeshes has to be set manually)

You best start of setting it to 1 for a first test with one submesh.

Doing some research I got this:



cskn_secTest.jpg (75.69 KiB) Viewed 199 times


(search pattern for dataTableOffs: FFFFFFFF2000, -> 2 submeshes)

btw: getting the startaddressses of the (edged) indices blocks automatically should be possible soon.
Only need to find/calculate one required offset value.
## Post #17
- Username: You'reAnAllStar
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 04, 2016 5:55 am
- Post datetime: 2017-12-18T03:23:16+00:00
- Post Title: Re: PS All-Stars Battle Royale(final version ea05-cskn)

The MediaFire links are dead. Were these scripts backed up anywhere?
## Post #18
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-01-22T13:30:23+00:00
- Post Title: Re: PS All-Stars Battle Royale(final version ea05-cskn)

can anyone post current script for this? I'm totaly lost in updates and string replaces for it
## Post #19
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2019-06-11T15:51:43+00:00
- Post Title: Re: PS All-Stars Battle Royale(final version ea05-cskn)

Yeah, I can't find the current scripts anywhere for this game. The only version I found was the older version and the link was dead anyway. I'd really like a method of getting the proper meshes and such from this without the ever-present error I remember encountering last time. 

[https://www.dropbox.com/s/6ygqbgc72oayr ... s.zip?dl=0](https://www.dropbox.com/s/6ygqbgc72oayre1/fatprincess.zip?dl=0)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-11T19:43:18+00:00
- Post Title: Re: PS All-Stars Battle Royale(final version ea05-cskn)

Afair the scripts in this thread were used for cskn files with the signature 45413035 (EA05 - as the thread title says, surprise  )

But fat_princess.c0.p0.cskn from your zip for example starts with 4D4F444C "MODL".
## Post #21
- Username: You'reAnAllStar
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 04, 2016 5:55 am
- Post datetime: 2019-08-18T07:16:14+00:00
- Post Title: Re: PS All-Stars Battle Royale(final version ea05-cskn)

Really? I could have sworn there was a version of the script that didn't have that error, but I might be misremembering.
