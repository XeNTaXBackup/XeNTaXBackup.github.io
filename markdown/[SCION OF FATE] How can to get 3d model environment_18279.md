## Post #1
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-06-26T09:06:50+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

Currently, after install game, there is a folder named MESH. It contains all 3d model (NPC,Items,...) but doesn't have environment mesh(house,...).Anyone can help me ?

Link download game : [http://fate.netgame.com/](http://fate.netgame.com/)
## Post #2
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-06-27T15:45:28+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

Anyone can help me ?
## Post #3
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-04T16:02:22+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

Hello, anyone here?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-05T02:39:56+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

You still don't realize where your problem is. If you're asking for help, try not to make yourself too great a nuisance.
So upload the files instead of waiting for others to install the game even if they're willing to help.
## Post #5
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-05T07:58:53+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from Bigchillghost
>
> You still don't realize where your problem is. If you're asking for help, try not to make yourself too great a nuisance.
So upload the files instead of waiting for others to install the game even if they're willing to help.

Sorry, I so stupid.

I find out somefile,but cannot read.

Here is the file which I collected : [https://1drv.ms/u/s!AtK3xgihMkhwg7pf9Arx0qz9VLkqTw](https://1drv.ms/u/s!AtK3xgihMkhwg7pf9Arx0qz9VLkqTw). I found an file txt which contain some infomation of model : vertex, faces...
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-05T10:13:35+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from tainhx
>
> I found an file txt which contain some infomation of model : vertex, faces...
Is that file from the game or generated from somewhere else? 

For those YOM files, the format is simple, but it's tedious to do it manually. 
A few examples from 101.YOM, which seem to be the submeshes with the most polygons:
## Post #7
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-05T11:00:51+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from Bigchillghost
>
> tainhx wrote:I found an file txt which contain some infomation of model : vertex, faces...
Is that file from the game or generated from somewhere else? 

For those YOM files, the format is simple, but it's tedious to do it manually. 
A few examples from 101.YOM, which seem to be the submeshes with the most polygons:

That files are available in folder game after install (I mean YOM file, texture,...)

Do you want full file for that map? that mesh missing Texture...and How can open YOM file and extract model ? pleas give me a guide
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-05T11:41:53+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from tainhx
>
> That files are available in folder game after install (I mean YOM file, texture,...)
I was referring to the text file 101.txt.

> Reply from tainhx
>
> Do you want full file for that map?
Nope.

> Reply from tainhx
>
> How can open YOM file and extract model ? pleas give me a guide
All you need is an Hex editor and [Hex2Obj](http://forum.xentax.com/viewtopic.php?f=29&t=10894). But if you want to extract all the meshes in these files, you'll have to program to do it. You can check the tutorial through the link in my signature for further infomation.
## Post #9
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-05T15:44:18+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from Bigchillghost
>
> tainhx wrote:That files are available in folder game after install (I mean YOM file, texture,...)
I was referring to the text file 101.txt.
tainhx wrote:Do you want full file for that map? 
Nope.
tainhx wrote:How can open YOM file and extract model ? pleas give me a guide
All you need is an Hex editor and Hex2Obj. But if you want to extract all the meshes in these files, you'll have to program to do it. You can check the tutorial through the link in my signature for further infomation.

So can I do it manually follow your tool?

Does 101.txt file contain all thing we need to use Hex2Obj?

And Could you show me tutorial to get one mesh from that 101.txt file?
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-05T16:03:36+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from tainhx
>
> So can I do it manually follow your tool?
It's not MY tool. But sure you can do it yourself.

> Reply from tainhx
>
> Does txt file contain all thing we need to use Hex2Obj?
Hex2Obj doesn't deal with text files, but only binary data. So you can extract some models from the YOM files. If you wan't to make use of that text file, you'll need some programing knowledge to read the geometry info and write them into a new obj file or other common formats.
## Post #11
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-05T16:05:11+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from Bigchillghost
>
> tainhx wrote:So can I do it manually follow your tool?
It's not MY tool. But sure you can do it yourself.
tainhx wrote:Does txt file contain all thing we need to use Hex2Obj?
Hex2Obj doesn't deal with text files, but only binary data. So you can extract some models from the YOM files. If you wan't to make use of that text file, you'll need some programing knowledge to read the geometry info and write them into a new obj file or other common formats.

Yeah..I mean extract mesh from YOM file
## Post #12
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-06T15:44:46+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

I opend YOM file in TinyHexer and compare it with file 101.txt as image which I attached.

Is that block data for first mesh in 101.txt? if it is right ,I don't know how to find parameter to use it in Hex2Obj tool 
[Capture.PNG](https://xentaxbackup.github.io/file/14557_Capture.PNG)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T15:47:00+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

I've added some YOM support (101.YOM) to the Make_obj project (C-source included).

[viewtopic.php?f=29&t=15955&p=141900#p141900](http://forum.xentax.com/viewtopic.php?f=29&t=15955&p=141900#p141900)



101-YOM.jpg (151.02 KiB) Viewed 128 times



> Reply from tainhx
>
> I don't know how to find parameter to use it in Hex2Obj toolLook into the Make_log.obj file created when using the exe file in the zip file of post in the link above.

first submesh,  face indices
0. 16ee 39

vertices
vAddr: 156a, 12

btw: you wouldn't use hex2obj to create 500 submeshes, would you?  

(It's just a tool to ease the first approach, getting the first submesh.)
## Post #14
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-06T16:15:47+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from shakotay2
>
> I've added some YOM support (101.YOM) to the Make_obj project (C-source included).

viewtopic.php?f=29&t=15955&p=141900#p141900
101-YOM.jpg
tainhx wrote:I don't know how to find parameter to use it in Hex2Obj tool Look into the Make_log.obj file created when using the exe file in the zip file of post in the link above.

first submesh,  face indices
0. 16ee 39

vertices
vAddr: 156a, 12

btw: you wouldn't use hex2obj to create 500 submeshes, would you?  

(It's just a tool to ease the first approach, getting the first submesh.)

Yes I would to it manually     . I don't good at C/C++ program

> first submesh,  face indices
>
> 0. 16ee 39
>
> 
>
> vertices
>
> vAddr: 156a, 12

It mean the block data in Tiny Hexer is right data for first mesh in 101.txt? And why is 0x16ee while that address in hex is 0x16e0
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T16:38:21+00:00
- Post Title: [SCION OF FATE] How can to get 3d model environment

> Reply from tainhx
>
> And why is 0x16ee while that address in hex is 0x16e0what does that mean "that address in hex"?

You need to understand (read tutorials) where a face indices block starts, here is a DWord facexIndexCount (0x27) before the first face index:



101-YOM-fst_submesh.jpg (131.06 KiB) Viewed 122 times
## Post #16
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-06T19:27:10+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

Currently I can open Obj file in Blender And see 500 submesh ...But seem some submesh will linked with other submesh in order to make bigger mesh (ships mesh will include flag,body..And each that part is submesh). Can we know which submesh linked together?
[Capture_2.PNG](https://xentaxbackup.github.io/file/14561_Capture_2.PNG)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T21:37:35+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

> Reply from tainhx
>
> (ships mesh will include flag,body..Where do you have that information from?

> Can we know which submesh linked together?I have no idea. There's MESH INDEX groups in 101.txt, maybe that helps?

MESH INDEX: 152
MESH INDEX: 153
MESH INDEX: 3205
MESH INDEX: 3210
---------------------

But you can simply select submeshes 10 to 15 in blender for example to get the ship parts moved together:



101-ship.jpg (48.96 KiB) Viewed 96 times



btw: there's is a good chance to use the World Matrix positions as offsets for the submeshes to un-clump the whole thing

(Overall I'd say those meshes are not impressive enough to spend more time with this, imho, so it's up to you to try out things.)
## Post #18
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-07T08:02:39+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

> Reply from shakotay2
>
> tainhx wrote:(ships mesh will include flag,body..Where do you have that information from?
Can we know which submesh linked together?I have no idea. There's MESH INDEX groups in 101.txt, maybe that helps?

MESH INDEX: 152
MESH INDEX: 153
MESH INDEX: 3205
MESH INDEX: 3210
---------------------

But you can simply select submeshes 10 to 15 in blender for example to get the ship parts moved together:
101-ship.jpg

btw: there's is a good chance to use the World Matrix positions as offsets for the submeshes to un-clump the whole thing

(Overall I'd say those meshes are not impressive enough to spend more time with this, imho, so it's up to you to try out things.)

> There's MESH INDEX groups in 101.txt, maybe that helps?
>
> 
>
> MESH INDEX: 152
>
> MESH INDEX: 153
>
> MESH INDEX: 3205
>
> MESH INDEX: 3210
>
> ---------------------

Is that right? I don't see it in 101.txt?

Anyway,Thank you very much for help me
## Post #19
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-07T10:23:19+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

Another question

We have mesh, we have UV and texture right now, So could we improve Make Obj tool to get full mesh with texture?

And There are some submesh has wrong information.Example SM_18, when I search index 18 in 101.txt, it give me another mesh



SubMessh18txt.PNG (160.41 KiB) Viewed 86 times
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-07T13:33:03+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

> Reply from tainhx
>
> We have mesh, we have UV and texture right now, So could we improve Make Obj tool to get full mesh with texture?The tool doesn't support texture/material but for any coder it should be possible to create a suiting material file (.mtl) for blender, I guess. You can insert a line 
mtllib my_materials.mtl to the obj file.
Each submesh needs a usemtl line, for example:
g SM_1
usemtl material1

> And There are some submesh has wrong information.Example SM_18, when I search index 18 in 101.txt, it give me another mesh I didn't care for indices (dunno how they count in 101.txt), I just numbered the submeshes in 101.YOM from the beginning on.

For 101.YOM you've to look here in 101.txt:
RENDERUNIT INDEX: 11
TEXTURE INDEX: 21
VERTEX °³¼ö: 64

Face °³¼ö: 126

Another example:
RENDERUNIT INDEX: 414 (in 101.txt) is submesh 420 in the Make_log.obj file (# 420. 1c852e 636).



submesh_420.jpg (32.63 KiB) Viewed 80 times
## Post #21
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-07T15:56:21+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

> Reply from shakotay2
>
> tainhx wrote:We have mesh, we have UV and texture right now, So could we improve Make Obj tool to get full mesh with texture?The tool doesn't support texture/material but for any coder it should be possible to create a suiting material file (.mtl) for blender, I guess. You can insert a line 
mtllib my_materials.mtl to the obj file.
Each submesh needs a usemtl line, for example:
g SM_1
usemtl material1
And There are some submesh has wrong information.Example SM_18, when I search index 18 in 101.txt, it give me another mesh I didn't care for indices (dunno how they count in 101.txt), I just numbered the submeshes in 101.YOM from the beginning on.

For 101.YOM you've to look here in 101.txt:
RENDERUNIT INDEX: 11
TEXTURE INDEX: 21
VERTEX °³¼ö: 64

Face °³¼ö: 126

Another example:
RENDERUNIT INDEX: 414 (in 101.txt) is submesh 420 in the Make_log.obj file (# 420. 1c852e 636).
submesh_420.jpg

I thought RENDERUNIT INDEX: 414 is SM_414 in Make_log.obj
## Post #22
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-07-08T15:46:02+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

Some Submesh have right index in 101.txt..some wrong :(:(:(
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-10T20:40:32+00:00
- Post Title: Re: [SCION OF FATE] How can to get 3d model environment

use this list to find the suiting submesh in Make_log.obj:


 101-txt-vert-face-counts.zip
(3.31 KiB) Downloaded 20 times

Looks like so:
 	RENDERUNIT INDEX: 0
	VERTEX: 12
	Face: 39
 	RENDERUNIT INDEX: 1
	VERTEX: 90
	Face: 240
 	RENDERUNIT INDEX: 2
	VERTEX: 307
	Face: 798
 	RENDERUNIT INDEX: 3
	VERTEX: 360
	Face: 960
[...]
 	RENDERUNIT INDEX: 489
	VERTEX: 43
	Face: 180
 	RENDERUNIT INDEX: 490
	VERTEX: 83
	Face: 162
 	RENDERUNIT INDEX: 491
	VERTEX: 40
	Face: 84

(Keep in mind that there's 500 submeshes in the Make_log.obj, this explains the oddities.)
# vAddr: 156a, 12
# 0. 16ee 39
# vAddr: 1760, 90
# 1. 392c 240
# vAddr: 3b24, 307
# 2. 6188 798
[...]
# vAddr: 25a268, 43
# 498. 25a7cc 180
# vAddr: 25a958, 83
# 499. 25e7b0 162
# vAddr: 25e918, 40
# 500. 260730 84


Sadly I couldn't determine the "world offsets" for the submeshes since I don't see much sense in here for example:

[...]
 RENDERUNIT INDEX: 486
 		World Matrix: -1682.802979	-337.331055	2206.236328
 RENDERUNIT INDEX: 487
 		World Matrix: -1682.802979	-337.331055	2206.236328
 RENDERUNIT INDEX: 486
 		World Matrix: -1947.464111	-338.274963	1808.319580
 RENDERUNIT INDEX: 487
 		World Matrix: -1947.464111	-338.274963	1808.319580
 RENDERUNIT INDEX: 486
 		World Matrix: -1962.520630	-320.321350	2174.964355
 RENDERUNIT INDEX: 487
 		World Matrix: -1962.520630	-320.321350	2174.964355 
 RENDERUNIT INDEX: 20
 		World Matrix: 731.095825	-328.255524	541.421875
 RENDERUNIT INDEX: 486
 		World Matrix: -1890.636475	-322.087830	2176.203125 
 RENDERUNIT INDEX: 487
 		World Matrix: -1890.636475	-322.087830	2176.203125
[...]

but some are to be found in the 101.YOM, so maybe used in the Make_obj project.
