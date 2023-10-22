## Post #1
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-02T17:08:44+00:00
- Post Title: IDOLM@STER One For All .pmd

Hello, I'm trying to make a .pmd idolmaster ofa extension plugin, and so far have managed to get bone count and names, texture count and names and mesh count, however i can't seem to be able to make sense of vertex format. I think that vertex data for the first submesh, ACC_HEADShape starts at 0xF5D4 but I'm not sure how to parse it and where the vertex/face count for each submesh is stored, and there's one strange issue with the printf function for texture names not diplaying the first 4 characters in texture name. Could anyone help me out with this? I'm pretty new to Python and reverse engineering game data in general so I'm a bit lost here. Here's the sample model: [https://www.dropbox.com/s/pqpm8bki9vzwy ... r.pmd?dl=0](https://www.dropbox.com/s/pqpm8bki9vzwyhe/chr_body_rank_104_a_slender.pmd?dl=0)
And this is my code:

```

import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("The IDOLM@STER One For All Model", ".pmd")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel)
   noesis.logPopup()
       #print
   return 1

NOEPY_HEADER = "PMD"

def noepyCheckType(data):

   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)

   bs.seek(0x10, NOESEEK_ABS) #PTR - Bone block

   bs.seek(0x13, NOESEEK_REL)
   BoneCount = bs.read("i") #Bone count
   print(BoneCount)
   bs.seek(0x70C, NOESEEK_ABS) #Bones
   bs.seek(0xFC, NOESEEK_REL) #First bone data
   BoneNames = []
   for i in range(0, BoneCount[0]-1):
      BoneNames.append (bs.readBytes(32).decode("UTF-8").rstrip("\0"))
      bs.seek(0xFC, NOESEEK_REL) #Skip bone data
   print(BoneNames)
   
   bs.seek(0xF448, NOESEEK_ABS) #PME - Mesh block
   
   bs.seek(0x13, NOESEEK_REL)
   MeshCount = bs.read("i") #Mesh count
   print(MeshCount)
   MeshNames = []
   #for i in range(0, MeshCount[0]):
   bs.seek(0x49, NOESEEK_REL) #Seek to mesh name
   MeshNames.append (bs.readBytes(32).decode("UTF-8").rstrip("\0"))
   bs.seek(0x17, NOESEEK_REL)
   VCount=bs.read("i")
   print(VCount)
   bs.seek(0x125, NOESEEK_REL) #Seek to vertex data
   VertBuff = bs.readBytes(VCount[0] * 0x2C)
   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 44, 0)
   rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VCount[0], noesis.RPGEO_POINTS, 1)
      
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)
   
   bs.seek(0x10C240, NOESEEK_ABS) #PTE - Texture block

   bs.seek(0x13, NOESEEK_REL) #Texture count
   TexCount = bs.read("i")
   print(TexCount)
   bs.seek(0xA9, NOESEEK_REL)
   TexNames = []
   for i in range(0, TexCount[0]):
      TexNames.append (bs.readBytes(40).decode("UTF-8").rstrip("\0")+".gtf")
      bs.seek(0x148, NOESEEK_REL)
   print(TexNames)
   
   rapi.rpgClearBufferBinds()   
   return 1
```
## Post #2
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-07T16:56:57+00:00
- Post Title: IDOLM@STER One For All .pmd

Anyone? I have been able to identify the faces but still nothing on vertices
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-07T20:14:56+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Sun Sep 08, 2019 12:56 am at Sun Sep 08, 2019 12:56 am
>
> 
Anyone? I have been able to identify the faces but still nothing on verticesthe faces (face indices) generally don't really help. 
Usually you start finding point clouds. That's the way how I do it.
Then you search for suiting face indices.

In this case I'm not sure about the format, HF or shorts:
.



-pmd.png (55.41 KiB) Viewed 303 times
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-08T03:17:33+00:00
- Post Title: IDOLM@STER One For All .pmd

chr_body_all.png (68.66 KiB) Viewed 294 times



Might need to take care of some extra faces.
## Post #5
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-08T06:58:48+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from Bigchillghost ↑Sun Sep 08, 2019 11:17 am at Sun Sep 08, 2019 11:17 am
>
> 

chr_body_all.png

Might need to take care of some extra faces.

Thank you so much, this is very helpful 
However, I don't quite understand how to calculate vertex count. Do you mind explaining that part?
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-08T07:26:15+00:00
- Post Title: IDOLM@STER One For All .pmd

pmd.png (90.2 KiB) Viewed 283 times
## Post #7
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-08T09:59:36+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from Bigchillghost ↑Sun Sep 08, 2019 3:26 pm at Sun Sep 08, 2019 3:26 pm
>
> 
pmd.png

Thank you, almost got every mesh down, except of slender_dShape and ACCHEAD_Shape
Do I understand correctly that for example the slender_dShape mesh has 72 vertices and 143 poly indices, and that indices start at 0x105FB4 and vertex data at 0xF1110 ? Because for some reason I am unable to preview mesh, but vertex cloud works just fine
Here's one of working meshes on the other hand 



slender_cShape1-min.png (122.25 KiB) Viewed 271 times
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-08T10:41:00+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Sun Sep 08, 2019 5:59 pm at Sun Sep 08, 2019 5:59 pm
>
> 
almost got every mesh down, except of slender_dShape and ACCHEAD_Shape
ACCHEAD_Shape:



ACC_HEADShape.png (133.04 KiB) Viewed 265 times



> Reply from MarieRose1301 ↑Sun Sep 08, 2019 5:59 pm at Sun Sep 08, 2019 5:59 pm
>
> 
Do I understand correctly that for example the slender_dShape mesh has 72 vertices and 143 poly indices, and that indices start at 0x105FB4 and vertex data at 0xF1110 ?
Yep. 

> Reply from MarieRose1301 ↑Sun Sep 08, 2019 5:59 pm at Sun Sep 08, 2019 5:59 pm
>
> Because for some reason I am unable to preview mesh, but vertex cloud works just fine
Coz the amount of vertex is below 256 and the format is using 8-bit integer to store the indices, which's out of AMR's expectation.

> Reply from MarieRose1301 ↑Sun Sep 08, 2019 5:59 pm at Sun Sep 08, 2019 5:59 pm
>
> 
Here's one of working meshes on the other hand 
slender_cShape1-min.png
Congratulations, you've already get the hang of that app.
## Post #9
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-08T12:59:50+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from Bigchillghost ↑Sun Sep 08, 2019 6:41 pm at Sun Sep 08, 2019 6:41 pm
>
> 
MarieRose1301 wrote: ↑Sun Sep 08, 2019 5:59 pm
almost got every mesh down, except of slender_dShape and ACCHEAD_Shape

ACCHEAD_Shape:
ACC_HEADShape.png
MarieRose1301 wrote: ↑Sun Sep 08, 2019 5:59 pm
Do I understand correctly that for example the slender_dShape mesh has 72 vertices and 143 poly indices, and that indices start at 0x105FB4 and vertex data at 0xF1110 ? 
Yep. 
MarieRose1301 wrote: ↑Sun Sep 08, 2019 5:59 pmBecause for some reason I am unable to preview mesh, but vertex cloud works just fine
Coz the amount of vertex is below 256 and the format is using 8-bit integer to store the indices, which's out of AMR's expectation.
MarieRose1301 wrote: ↑Sun Sep 08, 2019 5:59 pm
Here's one of working meshes on the other hand 
slender_cShape1-min.png

Congratulations, you've already get the hang of that app.

Here's what I got working  Thank you very much for your help, I hope I have enough info to start reading meshes in Noesis now 



ranko.PNG (127.67 KiB) Viewed 256 times
## Post #10
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-08T15:31:19+00:00
- Post Title: IDOLM@STER One For All .pmd

Almost complete geometry, only misses slender_dShape from main body files and kurome_O_OBJ_O_SORTBIASm4__O_AU from head file 



ranko_almost.PNG (119.84 KiB) Viewed 241 times
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-09T18:49:54+00:00
- Post Title: IDOLM@STER One For All .pmd

I've updated the Make_obj tool for creating all submeshes (tested with chr_body_rank_104_a_slender.pmd only!):

> Reply from shakotay2 ↑Tue Sep 10, 2019 2:47 am at Tue Sep 10, 2019 2:47 am
>
> 

(some superfluous vertices)
.



chr_body_rank_104_a_slender-pmd.png (82.35 KiB) Viewed 214 times
## Post #12
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-10T13:52:26+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from shakotay2 ↑Tue Sep 10, 2019 2:49 am at Tue Sep 10, 2019 2:49 am
>
> 
I've updated the Make_obj tool for creating all submeshes (tested with chr_body_rank_104_a_slender.pmd only!):
shakotay2 wrote: ↑Tue Sep 10, 2019 2:47 am

(some superfluous vertices)
.
chr_body_rank_104_a_slender-pmd.png

I have just gotten to try the program, it actually does work on other models as well, but with the same issue as the AMR, it won't convert meshes with few faces like eyes for example. Do you think you could link me the source so I can study it? C is the only programming language I actually understand on more than surface/basic level
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-10T14:14:16+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Tue Sep 10, 2019 9:52 pm at Tue Sep 10, 2019 9:52 pm
>
> but with the same issue as the AMR, it won't convert meshes with few faces like eyes for example.
I don't understand. If you can load the rest of the meshes into noesis, why can't that one? It's just the same format but using unsigned char instead of short for the face indices storage.
## Post #14
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-10T14:47:01+00:00
- Post Title: IDOLM@STER One For All .pmd

> Reply from Bigchillghost ↑Tue Sep 10, 2019 10:14 pm at Tue Sep 10, 2019 10:14 pm
>
> 
MarieRose1301 wrote: ↑Tue Sep 10, 2019 9:52 pmbut with the same issue as the AMR, it won't convert meshes with few faces like eyes for example. 

I don't understand. If you can load the rest of the meshes into noesis, why can't that one? It's just the same format but using unsigned char instead of short for the face indices storage.

I cannot load anything in noesis yet in fact as I haven't been able to code anything yet ^^"
## Post #15
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-10T16:42:54+00:00
- Post Title: IDOLM@STER One For All .pmd

I feel completely stupid right now but I have no idea how to read a number stored in 4 bytes...



dunno.PNG (28.08 KiB) Viewed 184 times
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-10T16:45:48+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Tue Sep 10, 2019 9:52 pm at Tue Sep 10, 2019 9:52 pm
>
> 
I have just gotten to try the program, it actually does work on other models as well, but with the same issue as the AMR, it won't convert meshes with few faces like eyes for example.yeah, the byte indices don't really fit, even when I switched to backface culling in a test.

> Do you think you could link me the source so I can study it? C is the only programming language I actually understand on more than surface/basic levelPmed you.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-10T16:52:38+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Wed Sep 11, 2019 12:42 am at Wed Sep 11, 2019 12:42 am
>
> 
I feel completely stupid right now but I have no idea how to read a number stored in 4 bytes...
dunno.PNGbs = NoeBitStream(data, NOE_BIGENDIAN)
bs.readUInt()
## Post #18
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-10T16:56:42+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from shakotay2 ↑Wed Sep 11, 2019 12:52 am at Wed Sep 11, 2019 12:52 am
>
> sdfsdfsdf

000001B7 should be 439 right? It outputs 2 for me ;_;
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-10T17:21:16+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

see my update above - works as expected
## Post #20
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-10T18:35:45+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from shakotay2 ↑Wed Sep 11, 2019 1:21 am at Wed Sep 11, 2019 1:21 am
>
> 
see my update above - works as expected

Now it gives me 3070230528 im so stupid haha xd
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-11T08:32:53+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Tue Sep 10, 2019 10:47 pm at Tue Sep 10, 2019 10:47 pm
>
> I cannot load anything in noesis yet in fact as I haven't been able to code anything yet ^^"
Here's a Noesis Python script for the format.


 fmt_IDOLMASTER_pmd.zip
(1.07 KiB) Downloaded 34 times



Loading all meshes into Noesis:
## Post #22
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-04T17:39:42+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

So I have rewritten my plugin based on the one provided by Bigchillghost, however I am having issues reading certain textures. Some work fine, but some, like normal maps and several ao and sphere maps do not, due to different pixel data sizes and compressions, for example this one(chr_comn_ran_face2.gtf from chr_head_rank_104_krn_a.pta). Could anyone take a look?
[](https://ibb.co/QfGgqrF)
[fmt_IDOLMASTER_OFA_pmd.rar](https://xentaxbackup.github.io/file/16860_fmt_IDOLMASTER_OFA_pmd.rar)
## Post #23
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-05T14:41:32+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

Trying to read bones, but Noesis just freezes when opening files, lol   
[](https://ibb.co/M8MGBDx)
## Post #24
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-06T07:24:04+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

Could anyone help?
I suspect my bone rotation and scale data isn't right, but i dont really know how to fix that
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-06T10:24:15+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

very few people only can judge from a picture  

Still freezing? See a suspisious NoeBone () line, where you shortened the params list.
(I know that's possible in C, in python, too? Just in case...)

params
noeBone = NoeBone(len(noeBones), boneName, boneMatrix, boneParentName, -1)
## Post #26
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-06T12:57:18+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from shakotay2 ↑Sun Oct 06, 2019 6:24 pm at Sun Oct 06, 2019 6:24 pm
>
> 
very few people only can judge from a picture  

Still freezing? See a suspisious NoeBone () line, where you shortened the params list.
(I know that's possible in C, in python, too? Just in case...)

params
noeBone = NoeBone(len(noeBones), boneName, boneMatrix, boneParentName, -1)

Tried, still the same. I shortened the param list because that's the root bone, with no parent(it doesn't even have a name), I saw some plugins with shortened param lists so i thought it might work this way xd

```

import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("The iDOLM@STER One For All Model", ".pmd")
	noesis.setHandlerTypeCheck(handle, pmdCheckType)
	noesis.setHandlerLoadModel(handle, pmdLoadModel)
    
	handle = noesis.register("The iDOLM@STER One For All Texture", ".pta")
	noesis.setHandlerTypeCheck(handle, ptaCheckType)
	noesis.setHandlerLoadRGBA(handle, ptaLoadRGBA)

	noesis.logPopup()
	return 1

NOEPY_HEADER = "PMD"

def ptaCheckType(data):
	bs = NoeBitStream(data)
	return 1

def pmdCheckType(data):

	bs = NoeBitStream(data)
	if len(data) < 3:
		return 0
	if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
		return 0
	return 1

def ptaLoadRGBA(data, texList):
	bs = NoeBitStream(data, NOE_BIGENDIAN)
	Header = bs.readBytes(3).decode("ASCII")
	print(Header)
	bs.seek(0x5, NOESEEK_REL)
	FileCount=bs.readInt()
	print(FileCount)
	bs.seek(0x4, NOESEEK_REL)
	TextureOffsets = []
	for i in range(0, FileCount):
		TextureOffsets.append (bs.readInt())
	print(TextureOffsets)
	print(FileCount % 4)
	if(FileCount % 4 != 0):
		bs.seek((4 - FileCount % 4)*4, NOESEEK_REL)
	TextureNames = []
	Files = []
	for i in range(0, FileCount):
		TextureNames.append(bs.readBytes(128).decode("UTF-8").rstrip("\0"))
	bs = NoeBitStream(data)
	bs.setEndian(NOE_BIGENDIAN)
	bs.seek(TextureOffsets[0], NOESEEK_ABS)

	for i in range(0, FileCount):
		bs.seek(TextureOffsets[i], NOESEEK_ABS)
		bs.seek(0x6, NOESEEK_REL)
		FMT = bs.readBytes(1)
		bs.seek(0x11, NOESEEK_REL)
		NRML = bs.readBytes(1)
		print(FMT)
		print(NRML)
		bs.seek(0x7, NOESEEK_REL)
		imgWidth = bs.readShort()
		imgHeight = bs.readShort()
		print(imgWidth, "x", imgHeight)
		bs.seek(0x5C, NOESEEK_REL)
		if FMT == b'\x80':
			data = bs.readBytes(imgWidth*imgHeight)
			texFmt = noesis.NOESISTEX_DXT1
			texList.append(NoeTexture(TextureNames[i], imgWidth, imgHeight, data, texFmt))
		if FMT == b'\x40':
			data = bs.readBytes(imgWidth*imgHeight)
			texFmt = noesis.NOESISTEX_DXT3
			texList.append(NoeTexture(TextureNames[i], imgWidth, imgHeight, data, texFmt))
		if FMT == b'\00':
			data = bs.readBytes(imgWidth*imgHeight)
			texFmt = noesis.NOESISTEX_DXT5
			texList.append(NoeTexture(TextureNames[i], imgWidth, imgHeight, data, texFmt))
		if FMT == b'\00' and NRML == b'\85':
			data = bs.readBytes(imgWidth*imgHeight*4)
			data = rapi.imageDecodeRaw(data, imgWidth[0], imgHeight[0], "a8r8g8b8")
			texFmt = noesis.NOESISTEX_RGB16
			texList.append(NoeTexture(TextureNames[i], imgWidth, imgHeight, data, texFmt))
		if FMT == b'\04':
			data = bs.readBytes(imgWidth*imgHeight*4)
			texFmt = noesis.NOESISTEX_DXT5
			texList.append(NoeTexture(TextureNames[i], imgWidth, imgHeight, data, texFmt))
		if FMT == b'\x10':
			data = bs.readBytes(imgWidth*imgHeight)
			texFmt = noesis.NOESISTEX_DXT5
			texList.append(NoeTexture(TextureNames[i], imgWidth, imgHeight, data, texFmt))

	print(TextureNames)
	return 1

def pmdLoadModel(data, mdlList):

	global boneList, texList, texNameList
	boneList = []
	texList = []
	texNameList = []

	baseName = rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getLastCheckedName()))
	texName = baseName
	if baseName.endswith("glamour"):
		texName = baseName[:-8]
	elif baseName.endswith("slender"):
		texName = baseName[:-8]

	bs = NoeBitStream(data, NOE_BIGENDIAN)
	bs.seek(0x10, NOESEEK_ABS) #PTR - Bone block
	BoneBlock=bs.readBytes(3).decode("UTF-8")
	print(BoneBlock)
	bs.seek(0x05, NOESEEK_REL)
	BoneCountOffset=bs.readInt()
	print(BoneCountOffset)
	BoneBlockSize = bs.readInt()
	print(BoneBlockSize)
	bs.seek(BoneCountOffset, NOESEEK_ABS)
	BoneCount=bs.readInt()
	print(BoneCount)
	bs.seek(0xE, NOESEEK_REL)
	bs.seek(8*BoneCount+42, NOESEEK_REL)
	BoneNames = []
	for i in range(0, BoneCount):
		if(i == 0):
			BoneNames.append ("ROOT")
			bs.seek(0x20, NOESEEK_REL)
			BoneParent=bs.readInt()
			BoneChild=bs.readInt()
			BoneUNK=bs.readInt()
			BoneNULL=bs.readInt()
			POS = NoeVec3.fromBytes(bs.readBytes(0xC))
			bs.seek(0x4, NOESEEK_REL)
			ROT = NoeAngles.fromBytes(bs.readBytes(0xC))
			bs.seek(0x4, NOESEEK_REL)
			SCL = NoeVec3.fromBytes(bs.readBytes(0xC))
			bs.seek(0x4, NOESEEK_REL)
			MTRX = ROT.toMat43()
			MTRX[3] = POS;
			MTRX[0][0] = SCL[0]
			MTRX[1][1] = SCL[1]
			MTRX[2][2] = SCL[2]
			Bone = NoeBone(i, BoneNames[i], MTRX, BoneParent, -1)
			boneList.append(Bone)
			bs.seek(0x9C, NOESEEK_REL)
		else:
			BoneNames.append (bs.readBytes(32).decode("UTF-8").rstrip("\0"))
			BoneParent=bs.readInt()
			BoneChild=bs.readInt()
			BoneUNK=bs.readInt()
			BoneNULL=bs.readInt()
			POS = NoeVec3.fromBytes(bs.readBytes(0xC))
			bs.seek(0x4, NOESEEK_REL)
			ROT = NoeAngles.fromBytes(bs.readBytes(0xC))
			bs.seek(0x4, NOESEEK_REL)
			SCL = NoeVec3.fromBytes(bs.readBytes(0xC))
			bs.seek(0x4, NOESEEK_REL)
			MTRX = ROT.toMat43()
			MTRX[3] = POS;
			MTRX[0][0] = SCL[0]
			MTRX[1][1] = SCL[1]
			MTRX[2][2] = SCL[2]
			Bone = NoeBone(i, BoneNames[i], MTRX, BoneParent, -1)
			boneList.append(Bone)
			if(i == BoneCount-1): #last bone is C bytes shorter
				bs.seek(0xB0, NOESEEK_REL)
			else:
				bs.seek(0xBC, NOESEEK_REL)
		
	print(BoneNames)
	MeshBlock=bs.readBytes(3).decode("UTF-8")
	print(MeshBlock)
	bs.seek(0xD, NOESEEK_REL)
	MeshCount=bs.readInt()
	print(MeshCount)
	bs.seek(MeshCount*8+8, NOESEEK_REL)
	ctx = rapi.rpgCreateContext()
	rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
	MeshNames = []
	MaterialInfo = []
	for i in range(0, MeshCount):
		bs.seek(0x10, NOESEEK_REL)
		MeshNames.append (noeStrFromBytes(bs.readBytes(0x20), "UTF8"))

		bs.seek(0x18, NOESEEK_REL)
		VertCount = bs.readInt()

		bs.seek(4, NOESEEK_REL)
		VertSize = bs.readInt()
		FaceSize = VertSize // VertCount

		FaceIndexCount = bs.readInt()

		bs.seek(4, NOESEEK_REL)
		FaceIndexSize = bs.readInt()
		IndexSize = FaceIndexSize // FaceIndexCount

		bs.seek(0x58, NOESEEK_REL)
		MeshOffset = bs.readInt()

		bs.seek(0x84, NOESEEK_REL)
		MeshOffset += bs.tell()

		VData = bs.readBytes(VertSize)
		IndexData = bs.readBytes(FaceIndexSize)

		rapi.rpgSetName(MeshNames[i])
		rapi.rpgBindPositionBuffer(VData, noesis.RPGEODATA_FLOAT, FaceSize)
		rapi.rpgBindNormalBufferOfs(VData, noesis.RPGEODATA_SHORT, FaceSize, 0x10)
		rapi.rpgBindUV1BufferOfs(VData, noesis.RPGEODATA_HALFFLOAT, FaceSize, 0x18)
		if IndexSize == 1:
			idxType = noesis.RPGEODATA_UBYTE
		elif IndexSize == 2:
			idxType = noesis.RPGEODATA_USHORT
		else:
			idxType = noesis.RPGEODATA_INT

		rapi.rpgCommitTriangles(IndexData, idxType, FaceIndexCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
		rapi.rpgClearBufferBinds()
		
		bs.seek(MeshOffset, NOESEEK_ABS)

	print(MeshNames)

	bs.seek(0x04, NOESEEK_REL)
	MaterialBlock=noeStrFromBytes(bs.readBytes(3), "UTF8")
	print(MaterialBlock)
	bs.seek(0x09, NOESEEK_REL)
	MaterialOffset=bs.readInt()
	print(MaterialOffset)
	MaterialCount=bs.readInt()
	print(MaterialCount)
	bs.seek(0xF, NOESEEK_REL)
	bs.seek(MaterialCount*8+10, NOESEEK_REL)

	bs.seek(MaterialOffset-13, NOESEEK_REL)
	TextureBlock=noeStrFromBytes(bs.readBytes(3), "UTF8")
	print(TextureBlock)
	bs.seek(0xD, NOESEEK_REL)
	TextureCount=bs.readInt()
	print(TextureCount)
	bs.seek(0xF, NOESEEK_REL)
	bs.seek(TextureCount*8+41, NOESEEK_REL)
	#textures are .gtf in a .pta file container with the same name as the model minus _glamour or _slender, no idea how to have Noesis open that file together with the model
	TextureNames = []
	for i in range(0, TextureCount):
		TextureNames.append (noeStrFromBytes(bs.readBytes(40), "UTF8") + ".gtf")
		bs.seek(0x148, NOESEEK_REL)
	print(TextureNames)

	if( rapi.checkFileExists( rapi.getDirForFilePath( rapi.getLastCheckedName() ) + texName + ".pta" ) ):
		data = rapi.loadIntoByteArray( rapi.getDirForFilePath( rapi.getLastCheckedName() ) + texName + ".pta" )
		ptaLoadRGBA(data, texList)

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	return 1
```
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-06T14:50:05+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

yeah, this line in the else: path of your bone loop makes it crash:
MTRX = ROT.toMat43()

Some ROT values are too big, I think:

```
PTR
32
60776
214
1 (0.0, 0.0, 0.0)
2 (0.0, 0.0, 0.0)
3 (0.0, 0.0, 0.0)
4 (0.0, 0.0, 0.0)
5 (0.0, -632378032652288.0, 0.0)
...

```

(Might be a matter of endianness?)

These are the bytes at 0xCB8 in the pmd, 3f c9 0f d8, that's big endian notation of a 32 bit float value.
Your script seems to switch Noesis to BigENDIAN but the output is -632378032652288.0?
(You usually get that value in case you read it as a little endian one.

(little endian (d8 0f c9 3f) would result in 1.570796, which seems to be a correct ROT value i.e. an angle in radians (180°).
But in the pmd it's big endian.  )

Maybe better you read your matrices using POS = NoeVec3( (bs.readFloat(), bs.readFloat(), bs.readFloat()) )
for example.
Bones look funny, so you might need to recheck that:
.



bones_or_not_bones.png (101.39 KiB) Viewed 83 times
## Post #28
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-06T16:25:41+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from shakotay2 ↑Sun Oct 06, 2019 10:50 pm at Sun Oct 06, 2019 10:50 pm
>
> 
yeah, this line in the else: path of your bone loop makes it crash:
MTRX = ROT.toMat43()

Some ROT values are too big, I think:
Code: Select allDetected file type: The iDOLM@STER One For All Model
PTR
32
60776
214
1 (0.0, 0.0, 0.0)
2 (0.0, 0.0, 0.0)
3 (0.0, 0.0, 0.0)
4 (0.0, 0.0, 0.0)
5 (0.0, -632378032652288.0, 0.0)
...

(Might be a matter of endianness?)

These are the bytes at 0xCB8 in the pmd, 3f c9 0f d8, that's big endian notation of a 32 bit float value.
Your script seems to switch Noesis to BigENDIAN but the output is -632378032652288.0?
(You usually get that value in case you read it as a little endian one.

(little endian (d8 0f c9 3f) would result in 1.570796, which seems to be a correct ROT value i.e. an angle in radians (180°).
But in the pmd it's big endian.  )

Maybe better you read your matrices using POS = NoeVec3( (bs.readFloat(), bs.readFloat(), bs.readFloat()) )
for example.

PS3 games don't usually use LittleEndian, do they?
I've tried using floats, and it does not freeze anymore, no bones pop out either though 

Seems like at very least scales are displayed correctly now, not so sure about positions and rotations(might as well be wrong order)
Here's an extract from my log:

```
PTR
32
60776
214
Postition:
(1.0, 1.0, 1.0)
Rotation:
(0.0, 0.0, 0.0)
Scale:
(0.0, 0.0, 0.0)
Postition:
(0.0, 0.0, 0.0)
Rotation:
(0.0, 0.0, 0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(0.0, 0.0, 0.0)
Rotation:
(0.0, 0.0, 0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(-0.0, 0.0, -0.0)
Rotation:
(0.0, 0.0, 0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(0.0, 0.0, 0.0)
Rotation:
(0.0, 0.0, 0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(-0.0, 111.0, 0.0)
Rotation:
(0.0, 1.570796012878418, 0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(0.0, 0.0, 0.0)
Rotation:
(0.0, 0.0, 0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(-0.0, 0.0, -0.0)
Rotation:
(-0.0, -0.0, -0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(9.0, 0.0, 0.0)
Rotation:
(0.0, 0.0, -0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(15.0, 0.0, 7.0)
Rotation:
(-0.0, -0.0, -0.0)
Scale:
(1.0, 1.0, 1.0)
Postition:
(5.0, -0.0, -0.0)
Rotation:
(-7.000000096013537e-06, 0.0, 0.0)
Scale:
(1.0, 1.0, 1.0)
```
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-06T16:39:48+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Mon Oct 07, 2019 12:25 am at Mon Oct 07, 2019 12:25 am
>
> 
I've tried using floats, and it does not freeze anymore, no bones pop out either thoughYou need to add
mdl.setBones(boneList) before mdlList.append(mdl)

For the endianness thingie: I think readBytes(count) simply reads "byte by byte" no matter which endianness was chosen.
## Post #30
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-06T16:48:32+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from shakotay2 ↑Mon Oct 07, 2019 12:39 am at Mon Oct 07, 2019 12:39 am
>
> 
MarieRose1301 wrote: ↑Mon Oct 07, 2019 12:25 am
I've tried using floats, and it does not freeze anymore, no bones pop out either though You need to add
mdl.setBones(boneList) before mdlList.append(mdl)

For the endianness thingie: I think readBytes(count) simply reads "byte by byte" no matter which endianness was chosen.

That's kind of weird, some bones are pretty much located where they are actually supposed to be, most of those are physical bones like neck/back/knee ribbons and skirt

Just checked again and some bones have their locations all mixed up
for example BASE bone is fine but MUNE1 is mixed up and so on

This is head, for some reason the face bones are on ground and oriented wrong, perhaps the locations arent just locations but offsets relative the parent bone: [](https://imgbb.com/)
## Post #31
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-10-08T18:10:36+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

No idea how to determine which bones use relative or absolute positions. Might be missing some info?
[](https://ibb.co/CBTSFhF)
[ptr.png](https://xentaxbackup.github.io/file/16875_ptr.png)
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-09T04:54:08+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

> Reply from MarieRose1301 ↑Sun Oct 06, 2019 8:57 pm at Sun Oct 06, 2019 8:57 pm
>
> 
Code: Select allfor i in range(0, BoneCount):
	if(i == 0):
		...
	else:
		...
This is totally unnecessary.  

Should simply use the 4x4 matrix instead:


Didn't care for the skin info though.
[fmt_IDOLMASTER_pmd_skel.zip](https://xentaxbackup.github.io/file/16877_fmt_IDOLMASTER_pmd_skel.zip)
## Post #33
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2020-01-03T13:51:45+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

I've been able to make the plugin read all the textures correctly, however still cannot figure out neither triangle strip degenerate triangle elimination, nor the bone weights. The plugin attached reads the same .pmd stuff as before + .pta archives and separate .gtf files.
[](https://imgur.com/jDOItef)
[fmt_IDOLMASTER_OFA_pmd.zip](https://xentaxbackup.github.io/file/17282_fmt_IDOLMASTER_OFA_pmd.zip)
## Post #34
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2020-01-04T19:28:11+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

Does anyone happen to have more model samples? Leon's head would have been very nice in particular.
## Post #35
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2020-04-23T11:07:37+00:00
- Post Title: Re: IDOLM@STER One For All .pmd

Tried to parse the material section of the files but I'm not sure where exactly are materials linked with corresponding textures, does anyone have any ideas? I was thinking that the triangle strip artifact could possibly be related to the way the mesh is broken on materials, meaning that if i manage to get which vertice belongs to which material could possibly help avoiding the degenerate triangles by breaking the for cycle when the data belonging to this particular material ends?
[EDIT] Disregard the part about 304 bytes-long materials not being important, the color ones contain diffuse IDs 
[EDIT 2] Got the diffuse, sphere and normal texture IDs from the COLOR, OUTLINE and SHADOW submaterials and it seems to be correct now. However, no clues on how does one assign the materials to correct faces.
The picture goes like: Material name, Material ID, Diffuse ID, Sphere ID and Normal ID
[materials.PNG](https://xentaxbackup.github.io/file/18001_materials.PNG)
