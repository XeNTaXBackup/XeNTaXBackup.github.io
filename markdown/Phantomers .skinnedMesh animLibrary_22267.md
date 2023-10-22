## Post #1
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2020-06-11T23:38:31+00:00
- Post Title: Phantomers *.skinnedMesh *animLibrary

This is a dead game and cannot be intercepted，Cannot use ninja,  I want to export the model for use, but I will not write Noesis script, Can you help me? I will upload a copy.

I will try to upload the complete file.

This is a sample File！！！！
[https://drive.google.com/file/d/1ickT0q ... sp=sharing](https://drive.google.com/file/d/1ickT0qO90xP43gkuT2MdPlRUuHFizcyw/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-12T05:25:13+00:00
- Post Title: Phantomers *.skinnedMesh *animLibrary

Using hex2obj (view link in my sig):
.



blackcat_mill_1st-skinnedMesh.png (67.05 KiB) Viewed 144 times
## Post #3
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2020-06-13T22:33:35+00:00
- Post Title: Phantomers *.skinnedMesh *animLibrary

> Reply from shakotay2 ↑Fri Jun 12, 2020 1:25 pm at Fri Jun 12, 2020 1:25 pm
>
> 
Using hex2obj (view link in my sig):
.
blackcat_mill_1st-skinnedMesh.png
Sorry, I’m so stupid  , I don’t understand the usage of Hex2obj, can write a general script?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-14T05:50:25+00:00
- Post Title: Phantomers *.skinnedMesh *animLibrary

I don't have the time to write general scripts, sorry.
Here's a specific one that loads one submesh from blackcat_mill_1st.skinnedMesh only.

DOESN'T load other skinnedMesh files. (You'll need to change these 3 lines for such: bs.seek(0xAA6, NOESEEK_ABS), bs.seek(0xB957, NOESEEK_ABS) and bs.seek(0xD677, NOESEEK_ABS) )

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("Phantomers",".skinnedMesh")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
def noepyCheckType(data):
    bs = NoeBitStream(data)
    Magic = bs.readBytes(4)
    if Magic != b'\x53\x6B\x69\x6E':# "Skin"
        print("'Skin' not found!")
        return 0
    return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)

	bs.seek(0xAA6, NOESEEK_ABS)
	VCnt = bs.readUInt()
	print("VCnt, ", VCnt)
	print("hex VCnt: ",hex(VCnt))
	bs.seek(1, NOESEEK_REL)# skip 01
	FVFsize = int(12)
	VBSize = VCnt * FVFsize
	VBuff = bs.readBytes(VBSize)

	bs.seek(0xB957, NOESEEK_ABS)
	UVBSize = VCnt * 8
	UVBuff = bs.readBytes(VBSize)

	bs.seek(0xD677, NOESEEK_ABS)	
	FCnt = bs.readUInt()
	print("FCnt, ", FCnt)
	print("hex FCnt: ",hex(FCnt))
	bs.seek(1, NOESEEK_REL)# skip 01
	print("FIs at:", hex(bs.tell()))
	FBuff = bs.readBytes(FCnt*2)

	rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
	rapi.rpgBindUV1BufferOfs(UVBuff, noesis.RPGEODATA_FLOAT, 8, 0)
	rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, FCnt, noesis.RPGEO_TRIANGLE, 1)
	
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	rapi.rpgClearBufferBinds()
	return 1

```




blackcat_mill_1st-skinnedMesh_.png (30.01 KiB) Viewed 107 times
## Post #5
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2020-06-14T18:47:19+00:00
- Post Title: Phantomers *.skinnedMesh *animLibrary

Anyway thank you
## Post #6
- Username: XiNTaX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 20, 2021 12:55 am
- Post datetime: 2022-12-03T22:15:52+00:00
- Post Title: Phantomers *.skinnedMesh *animLibrary

Hi, do you still have the game installer or can you help get it?
