## Post #1
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-07T05:00:17+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

I am adventuring to understand a little about creating a script for Noesis and seeing some topics as a basis, this is where i got, the script reads the file, but the face count is not correct for the body.



0000_brg.MUA.png (93.18 KiB) Viewed 229 times
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-07T05:03:22+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

This is the code:
fmt_BlazBlueCrossTagBattle_PC.py

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("BlazBlue Cross Tag Battle PC",".MUA")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "MUA"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.seek(0x94, NOESEEK_ABS)
	FCount = bs.readUInt()
	bs.seek(0x8c, NOESEEK_ABS)
	VCount = bs.readUInt()
	bs.seek(0x90, NOESEEK_ABS)
	FAddress = bs.readUInt()
	bs.seek(0x88, NOESEEK_ABS)
	VAddress = bs.readUInt()
	VBSize = int(80)
	bs.seek(VAddress, NOESEEK_ABS)
	VBuff = bs.readBytes(VCount * VBSize)
	rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize, 0)
	rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize,36)
	bs.seek(FAddress, NOESEEK_ABS)
	FBuff = bs.readBytes(FCount * 2)
	rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1
```


Sample file:

 0000_brg.zip
(76 KiB) Downloaded 17 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-07T07:29:01+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

> Reply from reh ↑Sat Mar 07, 2020 1:00 pm at Sat Mar 07, 2020 1:00 pm
>
> this is where i got, the script reads the file, but the face count is not correct for the body.I wouldn't say so, 4096 looks like the overall faceindex count.
Guess you need to find/use all the counts (colored: 2nd submesh):
.



MUA-counts.png (36.26 KiB) Viewed 196 times


Maybe check in other MUAs whether the pattern 01000000 01000000 is some kind of marker to find the vertex counts.

And, well, just in case, here's the heavy stuff (needs to be modified/expanded to find the 2nd occurence):

```
	fileBuff = bs.data[addr:bs.dataSize]
	bs.seek(addr+fileBuff.find(b'\x01\x00\x00\x00\x01\x00\x00\x00'))
	offset= bs.tell()
	print("01000000 01000000:", hex(offset))
```
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-09T03:02:53+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

> Reply from shakotay2 ↑Sat Mar 07, 2020 3:29 pm at Sat Mar 07, 2020 3:29 pm
>
> 
Guess you need to find/use all the counts (colored: 2nd submesh):
How do I use more than one count?
Would I use more variables to store them? (Ex: Vcont1, Vcont2, ...).

> Reply from shakotay2 ↑Sat Mar 07, 2020 3:29 pm at Sat Mar 07, 2020 3:29 pm
>
> 
Maybe check in other MUAs whether the pattern 01000000 01000000 is some kind of marker to find the vertex counts.
Apparently, yes.

> Reply from shakotay2 ↑Sat Mar 07, 2020 3:29 pm at Sat Mar 07, 2020 3:29 pm
>
> 
And, well, just in case, here's the heavy stuff (needs to be modified/expanded to find the 2nd occurence):
Code: Select all	addr=bs.tell()
	fileBuff = bs.data[addr:bs.dataSize]
	bs.seek(addr+fileBuff.find(b'\x01\x00\x00\x00\x01\x00\x00\x00'))
	offset= bs.tell()
	print("01000000 01000000:", hex(offset))
As I understand it, this snippet points to the address before the vertex count (0x8B), but I don't understand exactly what I should do with it.

Excuse me if I seem too noob in my doubts.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-09T07:36:58+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

> Reply from reh ↑Mon Mar 09, 2020 11:02 am at Mon Mar 09, 2020 11:02 am
>
> As I understand it, this snippet points to the address before the vertex count (0x8B), but I don't understand exactly what I should do with it.What? It's for finding the counts which you need to use in the script then (more code to write, of course).

And as I wrote you need to find the second occurence of 01000000 01000000 in that file (dunno whether it's always the 2nd one).
Then seek 8 bytes (bs.seek(0x08, NOESEEK_REL)), read the count(s), use the count(s) (face index counts need additional code, btw).

In the end you can get the two submeshes (see 
> Reply from reh ↑Sat Mar 07, 2020 1:00 pm at Sat Mar 07, 2020 1:00 pm
>
> ) in a loop.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-13T21:04:07+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

How is it going?  

Updated your script a little bit. (Assuming the counts to follow after the 2nd 0100000001000000.)
As always python was giving me some headache so I made a poor patch (without a loop as it should have been)  :
.



0000_brg-MUA.png (76.25 KiB) Viewed 140 times



Also didn't care for the mesh count - just used 2. Script tested with 0000_brg.MUA only!

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("BlazBlue Cross Tag Battle PC",".MUA")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "MUA"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	addr=bs.tell()
	fileBuff = bs.data[addr:bs.dataSize]
	addr1= fileBuff.find(b'\x01\x00\x00\x00\x01\x00\x00\x00')
	addr += addr1
	bs.seek(addr)
	offset= bs.tell()
	#print("01000000:", hex(offset))
	addr += 8 #skip found bytes
	fileBuff = bs.data[addr:bs.dataSize]
	addr2= fileBuff.find(b'\x01\x00\x00\x00\x01\x00\x00\x00')
	addr += addr2 + 8
	bs.seek(addr)

	# submesh 2 value comes first
	vCnt2 = bs.readUInt()
	vCnt1 = bs.readUInt()
	bs.seek(12*16+12, NOESEEK_REL)# this offset maybe different for other modell files
	fCnt2 = bs.readUInt()
	fCnt1 = bs.readUInt()
	print("vCnt1,2  fCnt1,2", vCnt1,vCnt2,fCnt1,fCnt2)
	# using the addresses here only, ignore overall counts
	bs.seek(0x94, NOESEEK_ABS)
	FCount = bs.readUInt()
	bs.seek(0x8c, NOESEEK_ABS)
	VCount = bs.readUInt()
	bs.seek(0x90, NOESEEK_ABS)
	FAddress = bs.readUInt()
	bs.seek(0x88, NOESEEK_ABS)
	VAddress = bs.readUInt()
	VBSize = int(80)
	bs.seek(VAddress, NOESEEK_ABS)
	print("(FVFsize: {}) {} {} f {} v {}".format(VBSize, FCount, VCount, hex(FAddress), hex(VAddress)))
	VBuff = bs.readBytes(vCnt1 * VBSize)
	rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize, 0)
	rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize,36)
	bs.seek(FAddress, NOESEEK_ABS)
	FBuff = bs.readBytes(fCnt1 * 2)
	rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt1, noesis.RPGEO_TRIANGLE_STRIP, 1)
	# handling submesh 2
	VAddress += vCnt1*VBSize
	bs.seek(VAddress, NOESEEK_ABS)
	VBuff = bs.readBytes(vCnt2 * VBSize)
	rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize, 0)
	rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize,36)
	FAddress += fCnt1*2
	bs.seek(FAddress, NOESEEK_ABS)
	FBuff = bs.readBytes(fCnt2 * 2)
	rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt2, noesis.RPGEO_TRIANGLE_STRIP, 1)

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1
	
```
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-14T06:48:01+00:00
- Post Title: BlazBlue Cross Tag Battle PC Noesis Script Help

I've been reading some topics about python repetition structure to better understand what I should do with the loop, thank you very much for taking the time to tinker with the code and for having spent some headaches.  
The script works with the characters found in lobby3d, but it doesn't work with stages and most effects, I have to see why that is.
However, my initial intention was to acquire knowledge.  

PS: The script also works with the nintendo switch version and probably works with the PS4 version.
     To get the texture, use the [ Switch-Toolbox ](https://github.com/KillzXGaming/Switch-Toolbox/releases).
