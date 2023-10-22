## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-20T14:44:38+00:00
- Post Title: S4League SCN Files

Hey Guys,

I haven't played S4League for years and tried it again because of a friend.

Now I want to export some Ingame Models from the game but unfortunately, they're all in SCN Format.
I don't know how to read or convert them.
I've found an very old Thread here (from 2014) but the Scripts back then were either unfinished or incompatible today.

I don't know much about REing file formats that's why I'm asking here for help.

Maybe some old information from this Thread might help you understanding the fileformat better.


I've uploaded some of the files here:
[http://res.cellenseres.de/scnfiles.7z](http://res.cellenseres.de/scnfiles.7z)

If you could provide me a working converter (scn -> obj/fbx/dae), I'd love to give a donation of $20 to you (if you're the first one who can provide it to me).
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-20T19:45:50+00:00
- Post Title: S4League SCN Files

Can't provide a converter, had just a quick glance:
.



asteroid-scn.png (105.46 KiB) Viewed 199 times
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-20T20:30:01+00:00
- Post Title: S4League SCN Files

This looks interesting, but It's what I've already found in the old post.
Thank you, tho. Will try it using MeshExtractor.
Unfortunately I don't know how to use it correctly/getting the correct addresses... Dx

A Converter which converts the models with working UVs would be top notch
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-20T20:35:22+00:00
- Post Title: S4League SCN Files

> Reply from ChrisX930 ↑Tue Apr 21, 2020 4:30 am at Tue Apr 21, 2020 4:30 am
>
> 
This looks interesting, but It's what I've already found in the old post.Where exactly? Format is not the same, is it?
If it were you could use Seyren's script.
## Post #5
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-20T20:37:09+00:00
- Post Title: S4League SCN Files

> Reply from shakotay2 ↑Tue Apr 21, 2020 4:35 am at Tue Apr 21, 2020 4:35 am
>
> 
ChrisX930 wrote: ↑Tue Apr 21, 2020 4:30 am
This looks interesting, but It's what I've already found in the old post.Where exactly? Format is not the same, is it?
If it were you could use Seyren's script.
[viewtopic.php?f=16&t=11201&start=45](https://forum.xentax.com/viewtopic.php?f=16&t=11201&start=45)

But nothing there helped me getting the models exported.

A simple to use Converter would be awesome. But not sure if anyone would do that.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-20T22:05:12+00:00
- Post Title: S4League SCN Files

> Reply from ChrisX930 ↑Tue Apr 21, 2020 4:37 am at Tue Apr 21, 2020 4:37 am
>
> A simple to use Converter would be awesome. But not sure if anyone would do that.The simpler to use the harder the work.  

btw: getting the uvs was simpler than I thought:
.



asteroid_part2.png (107.14 KiB) Viewed 177 times


Seems this asteroid's format is similar to this one, indeed  
> Reply from shakotay2 ↑Wed Feb 12, 2014 7:55 pm at Wed Feb 12, 2014 7:55 pm
>
> 
(but I can't check seyren's script because I don't have 3dsmax installed)

Why not use Noesis py? (Works for asteroid.scn (48810 bytes) from this thread only!)

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

   bs.seek(0x432E, NOESEEK_ABS)  #Seek to counts in asteroid.scn
   facesCount = bs.read("i")	# facce indices count
   vertsCount = bs.read("i")
   VertBuff = bs.readBytes(vertsCount[0] * 12)
   facesCount2 = bs.read("i")	# face indices count again
   print(facesCount2)
   if facesCount2!=facesCount:
      print("error: 2nd facesCount doesn't match!")
      return 1
   idxBuff = bs.readBytes(facesCount[0] *2 *3)
   vertsCount2 = bs.read("i")	# verts count again
   if vertsCount2!=vertsCount:
      print("error: 2nd vertsCount doesn't match!")
      return 1

   bs.seek(vertsCount[0] * 12, NOESEEK_REL)
   vertsCount2 = bs.read("i")	# verts count again or uv count, whatever
   if vertsCount2!=vertsCount:
      print("error: uv Count doesn't match!")
      return 1
   uv1Buf = bs.readBytes(vertsCount[0] * 8)

   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 12, 0)
   rapi.rpgBindUV1Buffer(uv1Buf, noesis.RPGEODATA_FLOAT, 8)
   rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, facesCount[0]*3, noesis.RPGEO_TRIANGLE, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)          #important, don't forget to put your loaded model in the mdlList

   return 1
```
## Post #7
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-20T22:36:44+00:00
- Post Title: S4League SCN Files

> Reply from shakotay2 ↑Tue Apr 21, 2020 6:05 am at Tue Apr 21, 2020 6:05 am
>
> 
-snip-

Which script do you mean exactly?
I mean, I have 3DS Max 2018 installed and [ tried the Script from berti ](https://forum.xentax.com/viewtopic.php?p=92230#p92230) (second post, has been probably updated during the postings in the thread).



Tried the Script:

> Code: Select allfSCN = getOpenFileName caption:"Choose Model File:" \
>
> types:"S4League Models (*.scn)|*.scn|"
>
> 
>
> if fSCN != undefined then
>
> (
>
> 	f = fopen fSCN "rb"
>
> 	clearlistener()
>
> 
>
> 	Face_array=#()
>
> 	Vert_array=#()
>
> 	UV_array=#()
>
> 	
>
> 	fseek f 8 #seek_set
>
> 	modelName = readstring f
>
> 	fseek f 81 #seek_cur
>
> 	
>
> 	for i = 1 to 4 do
>
> 	(
>
> 		submeshName = readstring f
>
> 		modelName = readstring f
>
> 		fseek f 88 #seek_cur
>
> 		fseek f 2052 #seek_cur
>
> 		print ("Mesh: " + submeshName)
>
> 		someint = readlong f #unsigned
>
> 		print ("\tSomeint: " + someint as string)
>
> 		count = readlong f #unsigned
>
> 		print("\tVertices: " + count as string)
>
> 		for x = 1 to count do
>
> 		(
>
> 			vx = readfloat f
>
> 			vy = readfloat f
>
> 			vz = readfloat f
>
> 			append Vert_array[vx,vy,vz]
>
> 		)
>
> 		
>
> 		count = readlong f #unsigned
>
> 		print("\tFaces: " + count as string)
>
> 		for i = 1 to count do
>
> 		(
>
> 			fa = readshort f #unsigned
>
> 			fb = readshort f #unsigned
>
> 			fc = readshort f #unsigned
>
> 			append Face_array[fa+1,fb+1,fc+1]
>
> 		)
>
> 			
>
> 		count = readlong f #unsigned
>
> 		print("\tNormals: " + count as string)
>
> 		for i = 1 to count do
>
> 		(
>
> 			nx = readfloat f
>
> 			ny = readfloat f
>
> 			nz = readfloat f
>
> 		)
>
> 
>
> 		count = readlong f #unsigned
>
> 		print("\tUVs: " + count as string)
>
> 		for i = 1 to count do
>
> 		(
>
> 		  tu = readfloat f
>
> 		  tv = readfloat f
>
> 		  append UV_array[tu,1-tv,0]
>
> 	   )
>
> 
>
> 		fseek f 12 #seek_cur
>
> 		str = readstring f
>
> 		fseek f 73 #seek_cur
>
> 		str = readstring f
>
> 		b = readbyte f
>
> 		fseek f 1420 #seek_cur -- I need to find the size of this block, it seems to change between submeshes
>
> 		fseek f 48 #seek_cur
>
> 
>
> 
>
> 		msh = mesh vertices:Vert_array faces:Face_array name:submeshName
>
> 		msh.numTVerts = UV_array.count
>
> 		buildTVFaces msh
>
> 		for j = 1 to UV_array.count do setTVert msh j UV_array[j]
>
> 		for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
>
> 		free Face_array
>
> 		free Vert_array
>
> 		free UV_array
>
> 	)
>
> 	gc()
>
> 	fclose f 
>
> )


EDIT:

> Reply from shakotay2 ↑Tue Apr 21, 2020 6:05 am at Tue Apr 21, 2020 6:05 am
>
> 
Why not use Noesis py? (Works for asteroid.scn (48810 bytes) from this thread only!)
Code: Select all#Noesis Python model import+export test module, imports/exports some data from/to a made-up format

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

   bs.seek(0x432E, NOESEEK_ABS)  #Seek to counts in asteroid.scn
   facesCount = bs.read("i")	# facce indices count
   vertsCount = bs.read("i")
   VertBuff = bs.readBytes(vertsCount[0] * 12)
   facesCount2 = bs.read("i")	# face indices count again
   print(facesCount2)
   if facesCount2!=facesCount:
      print("error: 2nd facesCount doesn't match!")
      return 1
   idxBuff = bs.readBytes(facesCount[0] *2 *3)
   vertsCount2 = bs.read("i")	# verts count again
   if vertsCount2!=vertsCount:
      print("error: 2nd vertsCount doesn't match!")
      return 1

   bs.seek(vertsCount[0] * 12, NOESEEK_REL)
   vertsCount2 = bs.read("i")	# verts count again or uv count, whatever
   if vertsCount2!=vertsCount:
      print("error: uv Count doesn't match!")
      return 1
   uv1Buf = bs.readBytes(vertsCount[0] * 8)

   rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 12, 0)
   rapi.rpgBindUV1Buffer(uv1Buf, noesis.RPGEODATA_FLOAT, 8)
   rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, facesCount[0]*3, noesis.RPGEO_TRIANGLE, 1)
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)          #important, don't forget to put your loaded model in the mdlList

   return 1

Tried the NOESIS Script
Result:
[https://imgur.com/0damDtz](https://imgur.com/0damDtz)

EDIT 2:

I believe it fails on all other files because of this part in the Script:

```
 bs.seek(0x432E, NOESEEK_ABS)  #Seek to counts in asteroid.scn
```

But how to get the correct address for each scn?
I'd like to extract the models of multiple SCNs (Maps, Characterfiles)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-20T22:45:41+00:00
- Post Title: S4League SCN Files

You need to be a coder to patch that max script.
Why not use the python script? Easy to use.  

For other .scn than the asteroid the start address of counts in this line 
bs.seek(0x432E, NOESEEK_ABS)  #Seek to counts 
has to be adjusted.

Good night (before our parallel editing gives a full fuss...)
## Post #9
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-20T22:47:49+00:00
- Post Title: S4League SCN Files

> Reply from shakotay2 ↑Tue Apr 21, 2020 6:45 am at Tue Apr 21, 2020 6:45 am
>
> 
You need to be a coder to patch that max script.
Why not use the python script? Easy to use.  

For other .scn than the asteroid this line (uses start address of counts)
bs.seek(0x432E, NOESEEK_ABS)  #Seek to counts 
has to be adjusted.

That's what I also notices rn xD
I'd like to extract multiple SCN files (Maps, Characterstuff etc).
Is there a to get the address (0x432E) automatically for each file?
How to even get the correct address?

Good night



EDIT:
I checked out a Map SCN and it seems that it has multiple models in it (of course it'd have that).
I'd try to find the correct addresses by looking for a huge amount of zeros in hex and the next following not-zero address.
I've checked BladeCity.scn and the addresses for "each(?)" models are:
0x8E5, 0xD76A, 0xF1F5, 0x10E12, 0x1299A, 0x13C67, 0x15312, 0x15DED, 0x17624, 0x1913B, 0x1AB06, 0x1C61D ...
and over hundred more (maybe?)

Doing that manually with each Model in the SCN would be a total pain in the ass, obviously.

So if someone could help me out exporting the models from a SCN File to obj files (or better, as dae/fbx with all models of the scene in it and their correct location in 3d space), I'd love to even give some compensation for expenses-

Here's the link to the bladecity.scn:
[https://res.cellenseres.de/bladecity.scn](https://res.cellenseres.de/bladecity.scn)
## Post #10
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-20T23:22:46+00:00
- Post Title: S4League SCN Files

Did that stuff quickly so might break on some models but worked on the few I tried. Get rid of the previous one or it'll be messy.
Also keep your money.
[noesis_scn_model_plugin.zip](https://xentaxbackup.github.io/file/17984_noesis_scn_model_plugin.zip)
## Post #11
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-20T23:43:20+00:00
- Post Title: S4League SCN Files

> Reply from Joschka ↑Tue Apr 21, 2020 7:22 am at Tue Apr 21, 2020 7:22 am
>
> 
Did that stuff quickly so might break on some models but worked on the few I tried. Get rid of the previous one or it'll be messy.
At least this is a great start!




It works for small SCeNes, but for Maps like the one I've sent in the last Post, the script's gonna crash on me


Maps:
[https://res.cellenseres.de/bladecity.scn](https://res.cellenseres.de/bladecity.scn)
[https://res.cellenseres.de/alicehouse.scn](https://res.cellenseres.de/alicehouse.scn)
[https://res.cellenseres.de/azit.scn](https://res.cellenseres.de/azit.scn)

Would also love to see "submesh_x" replaced with the material-name. Would be way easier to setup the materials that way.

Thank you! (and good night, 1:43am here rn xD )
## Post #12
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-21T00:09:28+00:00
- Post Title: S4League SCN Files

> Reply from ChrisX930 ↑Tue Apr 21, 2020 7:43 am at Tue Apr 21, 2020 7:43 am
>
> 
Would also love to see "submesh_x" replaced with the material-name. Would be way easier to setup the materials that way.

Not 100% sure what you're referring too, you mean this ? 

If so take the attached script. 

> Reply from ChrisX930 ↑Tue Apr 21, 2020 7:43 am at Tue Apr 21, 2020 7:43 am
>
> 
It works for small SCeNes, but for Maps like the one I've sent in the last Post, the script's gonna crash on me

Took a quick look and the buffers seem really similar, you'll probably be able to extract them easily. It'll be a nice opportunity for you to learn too.
[noesis_fmt_scn_v2.zip](https://xentaxbackup.github.io/file/17986_noesis_fmt_scn_v2.zip)
## Post #13
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2020-04-21T09:51:54+00:00
- Post Title: S4League SCN Files

> Reply from Joschka ↑Tue Apr 21, 2020 8:09 am at Tue Apr 21, 2020 8:09 am
>
> -snip-

not exactly what I meant.
The materials should have the same name as the textures used for them.
this are card_woman_body(.tga) and card_woman_head(.tga) for the card_slaughter.scn



Well, learning this by myself... I mean, I can try it but I don't have ANY clue about python   

I don't even understand how to read the filestructure and get the info I need from it
