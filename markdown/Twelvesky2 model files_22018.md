## Post #1
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-16T09:47:42+00:00
- Post Title: Twelvesky2 model files

I need model files of TwelveSky 2. I will use this model file in a different game. I need to transfer the model file to 3ds max.
I just extracted texture using "offzip". I couldn't extract the meshes. I would really appreciate if you can help.

include *.SOBJECT files :  3d meshes and textures

[http://www.mediafire.com/file/ufdtyuvx0 ... _files.zip](http://www.mediafire.com/file/ufdtyuvx0cpa8sg/sobject_model_files.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-16T15:11:26+00:00
- Post Title: Twelvesky2 model files

Y0170001-Sobject-decompressed.png (111.19 KiB) Viewed 214 times
## Post #3
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-16T16:07:07+00:00
- Post Title: Twelvesky2 model files

> Reply from shakotay2 ↑Thu Apr 16, 2020 11:11 pm at Thu Apr 16, 2020 11:11 pm
>
> 
Y0170001-Sobject-decompressed.png

wow, super. Very thanks Did you just use meshextractor? I also have no knowledge of these issues. Is it possible to automatically extract all meshes with script?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-16T16:13:56+00:00
- Post Title: Twelvesky2 model files

> Reply from Sancje ↑Fri Apr 17, 2020 12:07 am at Fri Apr 17, 2020 12:07 am
>
> Is it possible to automatically extract all meshes with script?Guess so - but you need to find someone who's motivated to write a script.
## Post #5
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-16T17:05:44+00:00
- Post Title: Twelvesky2 model files

> Reply from shakotay2 ↑Fri Apr 17, 2020 12:13 am at Fri Apr 17, 2020 12:13 am
>
> 
Sancje wrote: ↑Fri Apr 17, 2020 12:07 amIs it possible to automatically extract all meshes with script?
Guess so - but you need to find someone who's motivated to write a script.

I will have a few questions and a request.I would be glad if you help.

1-) did you just use mesh extractor to extract the meshes ? did you use any other tools? (offzip, quickbms...)
2-) In your extracted model, the edges are a bit sharp. Is it possible to soften edges using Meshextractor?
3-) Could you do a few more examples?
4-)Which version of meshextractor are you using?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-16T18:54:53+00:00
- Post Title: Twelvesky2 model files

> Reply from Sancje ↑Fri Apr 17, 2020 1:05 am at Fri Apr 17, 2020 1:05 am
>
> 
1-) did you just use mesh extractor to extract the meshes ? did you use any other tools? (offzip, quickbms...)decompressed sobject with offzip

> 2-) In your extracted model, the edges are a bit sharp. Is it possible to soften edges using Meshextractor?Nope, it's a (data format) converter only (with attached 3D viewer) not a 3D tool.
Use File\SaveAs mesh to export as wavefront obj file. Load that into the 3D tool of your choice for beautifying, whatever.

> 3-) Could you do a few more examples?Not atm.

> 4-)Which version of meshextractor are you using?Current version (view link in my sig).
## Post #7
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-16T19:57:45+00:00
- Post Title: Twelvesky2 model files

> Reply from shakotay2 ↑Fri Apr 17, 2020 2:54 am at Fri Apr 17, 2020 2:54 am
>
> 
Sancje wrote: ↑Fri Apr 17, 2020 1:05 am
1-) did you just use mesh extractor to extract the meshes ? did you use any other tools? (offzip, quickbms...)decompressed sobject with offzip
2-) In your extracted model, the edges are a bit sharp. Is it possible to soften edges using Meshextractor?Nope, it's a (data format) converter only (with attached 3D viewer) not a 3D tool.
Use File\SaveAs mesh to export as wavefront obj file. Load that into the 3D tool of your choice for beautifying, whatever.
3-) Could you do a few more examples?Not atm.
4-)Which version of meshextractor are you using?Current version (view link in my sig).

thank you for your answers. Finally, some places on the model are black. how can i fix ? Thanks again.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-16T21:40:48+00:00
- Post Title: Twelvesky2 model files

I usually provide the first submesh only. So it's not a matter of "fixing" you just need to search for further submeshes:

0x43024 1590
Vb1
76 68
0x3A874 457
020000
0x0 255

Create an empty .txt file, copy above 6 lines into it, save as "whatever.H2O" and load it into hex2obj.

Or simply in the meshextractor gui replace the following parameters addr (without the "0x") and count (for face indices and vertices) of the first submesh to get the missing one:
0x43024 1590
0x3A874 457
## Post #9
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-17T12:26:58+00:00
- Post Title: Twelvesky2 model files

> Reply from shakotay2 ↑Fri Apr 17, 2020 5:40 am at Fri Apr 17, 2020 5:40 am
>
> 
I usually provide the first submesh only. So it's not a matter of "fixing" you just need to search for further submeshes:

0x43024 1590
Vb1
76 68
0x3A874 457
020000
0x0 255

Create an empty .txt file, copy above 6 lines into it, save as "whatever.H2O" and load it into hex2obj.

Or simply in the meshextractor gui replace the following parameters addr (without the "0x") and count (for face indices and vertices) of the first submesh to get the missing one:
0x43024 1590
0x3A874 457

very thanks again.
## Post #10
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-17T18:28:41+00:00
- Post Title: Twelvesky2 model files

I decompressed the model files of the game with quickbms. I need a automatic script to open this models (for obj,fbx,.). I would be happy if you help
Can you help me please ?

include original game *.SOBJECT files : 3d meshes and textures
[http://www.mediafire.com/file/ufdtyuvx0 ... _files.zip](http://www.mediafire.com/file/ufdtyuvx0cpa8sg/sobject_model_files.zip)

Decompressed *.SOBJECT files: 3d meshes and textures.(*.mdl extension) Opened with quickbms.
[https://www.mediafire.com/file/sj33z4xb ... _FILES.zip](https://www.mediafire.com/file/sj33z4xb1vcqlt8/Decompressed_SOBJECT_FILES.zip)

Quickbms download link : [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)

Quickbms Twelvesky2 unpack script:

```
struct RES
{
<compressed model data>
<compressed Texture data>
}


Code:

# Game: 
# by
# script

get PRENAME basename
get NUMRES long
savepos OFS_RES
for i = 1 to NUMRES
goto OFS_RES
get FLAG1 long
get USIZE long
if FLAG1 != 1
math FLAG1 -= USIZE
math FLAG1 *= -1
else
math FLAG1 -= 1
endif
get CSIZE long
savepos OFS_RES
set RESNAME PRENAME
string RESNAME += _
if i < 10
string RESNAME += "0"
endif
string RESNAME += i
string RESNAME += .mdl
if USIZE > 0
clog RESNAME OFS_RES CSIZE USIZE
endif
math OFS_RES += CSIZE
math OFS_RES += FLAG1

goto OFS_RES
get FLAG1 long
get USIZE long
if FLAG1 != 1
math FLAG1 -= USIZE
math FLAG1 *= -1
else
math FLAG1 -= 1
endif
get CSIZE long
savepos OFS_RES
set RESNAME PRENAME
string RESNAME += _
if i < 10
string RESNAME += "0"
endif
string RESNAME += i
string RESNAME += .dds
if USIZE > 0
clog RESNAME OFS_RES CSIZE USIZE
endif
math OFS_RES += CSIZE
math OFS_RES += FLAG1
next i
```
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-18T08:04:43+00:00
- Post Title: Twelvesky2 model files

Don't trust this script! It's intended to be used as a startup only. So don't blame me.  

Finding the start address of the second submesh will require some fiddling (using a while loop for example).
(The addr output refers to Y017001_01 only!)

Since you're free with the model extension "mdl2" (for example) is better than "mdl" which is widely spread.

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("TwelveSkies2_test",".mdl2")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = 0x0003

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
       return 0
   sig = bs.readUInt()
   if sig not in [NOEPY_HEADER]:
       print("wrong Header <> 03 00!")
       return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	addr= 0x180; vAddr= addr + 4 ; VBSize = int(76)
	bs.seek(addr)
	vCnt1 = bs.readUInt()
	VBuff = bs.readBytes(vCnt1 * VBSize)
	fiCntAddr= vAddr + VBSize * vCnt1
	bs.seek(fiCntAddr, NOESEEK_ABS)#
	fCnt1 = bs.readUInt()
	print("vCnt1  fCnt1", vCnt1,fCnt1)

	rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize, 0)
	rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, VBSize,VBSize-8)

	offset= bs.tell()
	print("FIs at:", hex(offset)); FBSize= fCnt1 * 3 * 2
	FBuff = bs.readBytes(FBSize)
	rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt1*3, noesis.RPGEO_TRIANGLE, 1)
	# handling submesh 2, got LOD instead
	addr= fiCntAddr + 4 + FBSize
	fileBuff = bs.data[addr:bs.dataSize]# reminder: Size must be reduced here
	addr1= fileBuff.find(b'\x01\x00\x00\x00')
	addr += addr1
	bs.seek(addr-4)
	b = bs.readUInt()
	offset= bs.tell()
	print("LOD at:", hex(offset), b); 
	# submesh 2?
	addr += 4
	fileBuff = bs.data[addr:bs.dataSize]# reminder: Size must be reduced here
	addr1= fileBuff.find(b'\x01\x00\x00\x00')
	addr += addr1
	bs.seek(addr)
	offset= bs.tell()
	print("SM2? at:", hex(offset)); 

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1
```

.



Y03_2001.png (63.38 KiB) Viewed 135 times
## Post #12
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-18T09:38:46+00:00
- Post Title: Twelvesky2 model files

thank you so much   .  these things are very hard for me. I'm very amateur. I was trying to learn your hex2obj. I haven't even figured it out yet.
## Post #13
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-18T17:26:33+00:00
- Post Title: Twelvesky2 model files

> Reply from shakotay2 ↑Fri Apr 17, 2020 5:40 am at Fri Apr 17, 2020 5:40 am
>
> 
I usually provide the first submesh only. So it's not a matter of "fixing" you just need to search for further submeshes:

0x43024 1590
Vb1
76 68
0x3A874 457
020000
0x0 255

Create an empty .txt file, copy above 6 lines into it, save as "whatever.H2O" and load it into hex2obj.

Or simply in the meshextractor gui replace the following parameters addr (without the "0x") and count (for face indices and vertices) of the first submesh to get the missing one:
0x43024 1590
0x3A874 457

hi, How did you calculate the FVFsize and UVpos value(76,68) ? Are these values constant?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-18T18:48:05+00:00
- Post Title: Twelvesky2 model files

> Reply from Sancje ↑Sun Apr 19, 2020 1:26 am at Sun Apr 19, 2020 1:26 am
>
> hi, How did you calculate the FVFsizeThere's no general recipe.
Here it's (startAddrFIs -  startOfVertices) / vertexCount
(FI= faceIndex)
Getting the startOfVertices is a matter of experience usually.

> and UVpos value(76,68) ?No recipe. Position of float uvs (tx, ty) usually is a multiple of 4, here it's 76 - 8. (8= sizeOfTx + sizeOfTy)

> Are these values constant?Usually. (But there's 3D formats which use 3 or more different values in one model file.)
## Post #15
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-18T19:15:09+00:00
- Post Title: Twelvesky2 model files

> Reply from shakotay2 ↑Sun Apr 19, 2020 2:48 am at Sun Apr 19, 2020 2:48 am
>
> 
Sancje wrote: ↑Sun Apr 19, 2020 1:26 amhi, How did you calculate the FVFsize There's no general recipe.
Here it's (startAddrFIs -  startOfVertices) / vertexCount
(FI= faceIndex)
Getting the startOfVertices is a matter of experience usually.
and UVpos value(76,68) ?No recipe. Position of float uvs (tx, ty) usually is a multiple of 4, here it's 76 - 8. (8= sizeOfTx + sizeOfTy)
Are these values constant?Usually. (But there's 3D formats which use 3 or more different values in one model file.)

> Getting the startOfVertices is a matter of experience usually.

Thanks for sharing this valuable information with me, it is really helpful. so how can we gain experience?  How can I guess? what should be the approach for "Getting the startOfVertices"? is there an easy method ?
## Post #16
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-19T10:01:56+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from shakotay2 ↑Sun Apr 19, 2020 2:48 am at Sun Apr 19, 2020 2:48 am
>
> 
Sancje wrote: ↑Sun Apr 19, 2020 1:26 amhi, How did you calculate the FVFsize There's no general recipe.
Here it's (startAddrFIs -  startOfVertices) / vertexCount
(FI= faceIndex)
Getting the startOfVertices is a matter of experience usually.
and UVpos value(76,68) ?No recipe. Position of float uvs (tx, ty) usually is a multiple of 4, here it's 76 - 8. (8= sizeOfTx + sizeOfTy)
Are these values constant?Usually. (But there's 3D formats which use 3 or more different values in one model file.)

I am trying to find submesh. I couldn't find my mistake.I tried all the face start addresses. I'm waiting for your help.

Model link: [http://www.mediafire.com/file/dkm9639jm ... 001_01.zip](http://www.mediafire.com/file/dkm9639jmrbn47z/Y034001_01.zip)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-19T10:50:47+00:00
- Post Title: Re: Twelvesky2 model files

start with the first submesh (the rest is harder to find I guess):

0x9C80 1362
Vb1
76 68
0x184 522
020000
0x0 255

(For that file you can change the header in the script to NOEPY_HEADER = 0x0002)
## Post #18
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-19T11:54:29+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from shakotay2 ↑Sun Apr 19, 2020 6:50 pm at Sun Apr 19, 2020 6:50 pm
>
> 
start with the first submesh (the rest is harder to find I guess):

0x9C80 1362
Vb1
76 68
0x184 522
020000
0x0 255

(For that file you can change the header in the script to NOEPY_HEADER = 0x0002)

Thanks. how can i find other submeshes with hex2obj? I've been trying since yesterday.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-19T11:55:58+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from Sancje ↑Sun Apr 19, 2020 7:54 pm at Sun Apr 19, 2020 7:54 pm
>
> Thanks. how can i find other submeshes with hex2obj? I've been trying since yesterday.I don't know a simple solution.
You need to gain experience, as simple as that. Takes weeks, if not month. 

Learn to think in "blocks": where does FIs block start? (simple in most cases), where does it end? (Might be the start of the next vertex block (sometimes/for other 3D formats). Additional bytes to be met in between, such as counts, sometimes bounding box values (in other 3D format files), whatever).

0x7CBCF 3327
Vb1
76 99
0x6D1D3 842
020000
0x0 255
## Post #20
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-04-19T14:14:32+00:00
- Post Title: Re: Twelvesky2 model files

Here I attached the full models I converted from Y017001_01.mdl and Y032001_01.mdl.
[Twelve_Sky_2_mdl_to_obj.zip](https://xentaxbackup.github.io/file/17970_Twelve_Sky_2_mdl_to_obj.zip)
## Post #21
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-19T14:19:32+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from Karpati ↑Sun Apr 19, 2020 10:14 pm at Sun Apr 19, 2020 10:14 pm
>
> 
Here I attached the full models I converted from Y017001_01.mdl and Y032001_01.mdl.

thanks. what method do you follow? Do you have a general tool or script?
## Post #22
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-04-19T19:39:09+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from Sancje ↑Sun Apr 19, 2020 10:19 pm at Sun Apr 19, 2020 10:19 pm
>
> 
What method do you follow? Do you have a general tool or script?

I will release the updated 3D Object Converter.
## Post #23
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-19T19:57:48+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from Karpati ↑Mon Apr 20, 2020 3:39 am at Mon Apr 20, 2020 3:39 am
>
> 
Sancje wrote: ↑Sun Apr 19, 2020 10:19 pm
What method do you follow? Do you have a general tool or script?


I will release the updated 3D Object Converter.

when do you release?
## Post #24
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-04-20T18:11:42+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from Sancje ↑Mon Apr 20, 2020 3:57 am at Mon Apr 20, 2020 3:57 am
>
> 
when do you release?

I have finished my Twelve Sky 2 (extracted *.SOBJECT file) *.MDL loader module and I have released the following program as web update:

- 3D Object Converter v7.028 (Windows)

How to get the 3D Object Converter v7.028:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.028.
## Post #25
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-04-21T19:22:11+00:00
- Post Title: Re: Twelvesky2 model files

I have updated the 3D Object Converter app to handle the situation I did find in the Y030001_1.mdl and Y029001_1.mdl files.
I have tested on the biggest models I did find in the games also.

Just use the Help/Check for updates... function to get the v7.029.
## Post #26
- Username: Sancje
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Sep 08, 2014 10:04 pm
- Post datetime: 2020-04-21T20:56:01+00:00
- Post Title: Re: Twelvesky2 model files

> Reply from Karpati ↑Wed Apr 22, 2020 3:22 am at Wed Apr 22, 2020 3:22 am
>
> 
I have updated the 3D Object Converter app to handle the situation I did find in the Y030001_1.mdl and Y029001_1.mdl files.
I have tested on the biggest models I did find in the games also.

Just use the Help/Check for updates... function to get the v7.029.

thank you very much for your help
