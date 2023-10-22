## Post #1
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-02T04:48:33+00:00
- Post Title: chuanshuo OL 3D models samples

Hello! This is a very old Chinese 3D online game, but there is no browser or export and import plug-in. It feels like it uses orge engine.

These model mount files.
[https://anonfiles.com/H3qcvfLbx4/0151_7z](https://anonfiles.com/H3qcvfLbx4/0151_7z)

[https://anonfiles.com/P9q8v3Lfx4/0159_7z](https://anonfiles.com/P9q8v3Lfx4/0159_7z)

[https://anonfiles.com/Tcqcv3L5x1/0402_7z](https://anonfiles.com/Tcqcv3L5x1/0402_7z)

[https://anonfiles.com/V6qav8L7x2/1010_7z](https://anonfiles.com/V6qav8L7x2/1010_7z)
=================================
*.anim   Animation file

*.bp   bones file

*.mesh   skin file(Include vertices & faces)



model   It is a configuration file
=================================
Which friend can help me write a noesis script！
## Post #2
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-02T04:52:24+00:00
- Post Title: chuanshuo OL 3D models samples

*.mash

4D 45 53 48 32 2E 30 30 00 00 00 00 0E 01 00 00
AE 82 A3 BD D7 01 09 40 99 AD 6E 3F 25 96 D5 39
A2 67 07 40 38 92 67 3F 3D 34 A0 3A 1D 76 0A 40
49 A4 4E 3F ED C8 E9 BD F7 66 10 40 7F B9 2F 3F


4D 45 53 48 32 2E 30 30   hear

00 00 00 00 **
0E 01 00 00  vertices count

There seems to be something else on purpose at the top of the lower part。

vertices count/2    actually is


=========================================================================
This online game is a bit like 

Webzen Mu OL
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-02T13:20:47+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from ptg1121 ↑Wed Mar 02, 2022 12:48 pm at Wed Mar 02, 2022 12:48 pm
>
> 
Which friend can help me write a noesis script！
edit: (.mesh) only vertex cloud and (.bp) bones (without parent)


anim:

```
int numFrame
int unk
int numBones

for numBones:
	int lenNameString
	string name
	for numFrame:
		data 40 bytes on frame

```

[chuanshuo OL.zip](https://xentaxbackup.github.io/file/21872_chuanshuo OL.zip)
## Post #4
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-02T23:21:47+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Wed Mar 02, 2022 9:20 pm at Wed Mar 02, 2022 9:20 pm
>
> 
ptg1121 wrote: ↑Wed Mar 02, 2022 12:48 pm

HI Durik256：
Thanks. I have restored the vertices, but I can't restore the skin. There is a list of bones. I will share more cases！
## Post #5
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-03T00:41:10+00:00
- Post Title: chuanshuo OL 3D models samples

I also shared the protagonist resource file。


[https://anonfiles.com/9dP66fL5x8/001_7z](https://anonfiles.com/9dP66fL5x8/001_7z)
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-03T07:22:43+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from ptg1121 ↑Thu Mar 03, 2022 8:41 am at Thu Mar 03, 2022 8:41 am
>
> 

Hello ptg1121, which script do you used to unpack the Game.pak  ? or do you get an unpacked client? if you don't mind can share from where I can download it? Thanks!:mrgreen:
## Post #7
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-03T09:49:00+00:00
- Post Title: chuanshuo OL 3D models samples

hi moonpaladin:
I don't have this unpacking tool. It's from someone else's private server client.


Here are the client and server of the second generation of the engine. You can have a look

[https://www.cr173.com/soft/699010.html](https://www.cr173.com/soft/699010.html)
## Post #8
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-03T10:44:35+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from moonpaladin ↑Thu Mar 03, 2022 3:22 pm at Thu Mar 03, 2022 3:22 pm
>
> 
ptg1121 wrote: ↑Thu Mar 03, 2022 8:41 am


Hello ptg1121, which script do you used to unpack the Game.pak  ? or do you get an unpacked client? if you don't mind can share from where I can download it? Thanks!:mrgreen:

There is an unpacking tool here
[viewtopic.php?f=10&t=8352&hilit=fengyun](https://forum.xentax.com/viewtopic.php?f=10&t=8352&hilit=fengyun)
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-03T14:50:32+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from ptg1121 ↑Thu Mar 03, 2022 6:44 pm at Thu Mar 03, 2022 6:44 pm
>
> 
There is an unpacking tool here
viewtopic.php?f=10&t=8352&hilit=fengyun
Ty, gonna try it!
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-03T16:11:53+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from ptg1121 ↑Thu Mar 03, 2022 8:41 am at Thu Mar 03, 2022 8:41 am
>
> 
I also shared the protagonist resource file。

[fmt_mesh2.zip](https://xentaxbackup.github.io/file/21903_fmt_mesh2.zip)
## Post #11
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-03T23:27:28+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from moonpaladin ↑Thu Mar 03, 2022 10:50 pm at Thu Mar 03, 2022 10:50 pm
>
> 

HI 
This is the mount you want
https://anonfiles.com/5bj3K4L6xd/ride_7z
## Post #12
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-03T23:56:31+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from ptg1121 ↑Fri Mar 04, 2022 7:27 am at Fri Mar 04, 2022 7:27 am
>
> 
Thanks!
## Post #13
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-04T00:54:57+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Fri Mar 04, 2022 12:11 am at Fri Mar 04, 2022 12:11 am
>
> 
good！！！
## Post #14
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-09T09:51:50+00:00
- Post Title: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Fri Mar 04, 2022 12:11 am at Fri Mar 04, 2022 12:11 am
>
> 
HI Durik256:
Thank you for your help. It seems that they have no UV information and no material
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2022-03-10T18:13:29+00:00
- Post Title: chuanshuo OL 3D models samples

I have finished my Chuanshuo *.MESH loader module and I have released the following programs as web updates:

- 3D Object Converter v8.023 (Windows)
- i3DConverter v4.202	  (macOS)
- i3DConverter v2.202	  (Linux)

How to get the 3D Object Converter v8.023:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).
After it just use the Help/Check for updates... function to get the v8.023.

How to get the i3DConverter macOS v4.202:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
After it just use the Help/Check for updates... function to get the v4.202.

How to get the i3DConverter Linux v2.202:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
After it just use the Help/Check for updates... function to get the v2.202.



The .mesh file has not reference to the external texture file, that is why I can’t assign it to the material table.

You can add the texture file to the material table by hand using the following procedure:

- open your 3d model (file)
- click on the Object, Bone, Material selector on the toolbar (from right the 1st icon on the toolbar)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK

- (Click on the textured view icon.)





Chuanshuo.jpg (80.35 KiB) Viewed 76 times
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2022-03-10T18:14:59+00:00
- Post Title: Re: chuanshuo OL 3D models samples

Here I attached the converted file in Wavefront .obj/mtl format.
[Chuanshuo_mesh_to_obj.zip](https://xentaxbackup.github.io/file/21922_Chuanshuo_mesh_to_obj.zip)
## Post #17
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-11T05:53:20+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from Karpati ↑Fri Mar 11, 2022 2:13 am at Fri Mar 11, 2022 2:13 am
>
> 
I have finished my Chuanshuo *.MESH loader module and I have released the following programs as web updates:
Really cool! one day I'm gonna be able to buy your converter, Karpati
## Post #18
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-11T05:56:00+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Fri Mar 04, 2022 12:11 am at Fri Mar 04, 2022 12:11 am
>
> 
I also shared the protagonist resource file。
Thanks Durik! your noesis script works in many of the samples, but throw an error in some others, if you don't mind I'm attaching the samples, if you can give support for the UV's gonna be awesome   , Thanks for your time and effort.   
[https://www.mediafire.com/file/y1dp7pev ... s.zip/file](https://www.mediafire.com/file/y1dp7pev722zlhp/chuanshuo_OL_samples.zip/file)
## Post #19
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-12T05:11:00+00:00
- Post Title: Re: chuanshuo OL 3D models samples

I have been trying to get any kind of mesh with hex2obj but seems that can't handle this task with it, or I could be wrong? If someone can get the mesh + uvs with hex2obj please share your values, it gonna help alot, to have a clue about how to get the right values. Thanks!
## Post #20
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2022-03-12T08:42:04+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from moonpaladin ↑Fri Mar 11, 2022 1:53 pm at Fri Mar 11, 2022 1:53 pm
>
> 
Really cool! one day I'm gonna be able to buy your converter, Karpati

The choice is yours.
## Post #21
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-12T18:38:32+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from moonpaladin ↑Fri Mar 11, 2022 1:56 pm at Fri Mar 11, 2022 1:56 pm
>
> 
but throw an error in some others
remove line 36 >>  'bs.seek(36, NOESEEK_REL)'. and you can open all models.   


> Reply from moonpaladin ↑Sat Mar 12, 2022 1:11 pm at Sat Mar 12, 2022 1:11 pm
>
> 
+ uvs with hex2obj please share your values
do you have a script (source code) what could be the problem to study it?
(hex2obj does not seem to support padding index)
model researcher:



uv_mesh.png (170.32 KiB) Viewed 156 times
## Post #22
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-13T03:29:26+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Sun Mar 13, 2022 2:38 am at Sun Mar 13, 2022 2:38 am
>
> 
remove line 36 >>  'bs.seek(36, NOESEEK_REL)'. and you can open all models.
NOESEEK_REL hates me    

> Reply from Durik256 ↑Sun Mar 13, 2022 2:38 am at Sun Mar 13, 2022 2:38 am
>
> 
do you have a script (source code) what could be the problem to study it?
(hex2obj does not seem to support padding index)
I was doing it! didn't know about that padding   ! thanks Durik! always saving me xd
## Post #23
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-13T06:59:44+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Sun Mar 13, 2022 2:38 am at Sun Mar 13, 2022 2:38 am
>
> 
Thanks Durik!
## Post #24
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-13T17:44:59+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from moonpaladin ↑Sun Mar 13, 2022 2:59 pm at Sun Mar 13, 2022 2:59 pm
>
> 
Thanks Durik!
cool.   
i dont know how add uvs triangles in noesis.(can someone tell me)
i create a plugin that exports a temporary *.obj and loads it.
The only disadvantage of this method is that export model via >>(File>Export from Preview)

[fmt_mesh2.zip](https://xentaxbackup.github.io/file/21942_fmt_mesh2.zip)
## Post #25
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-13T18:52:26+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Mon Mar 14, 2022 1:44 am at Mon Mar 14, 2022 1:44 am
>
> 
Thanks Durik! well I just tested and at open any model throw this error xD  :could be my pc:
## Post #26
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-15T23:18:59+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from Durik256 ↑Sun Mar 13, 2022 2:38 am at Sun Mar 13, 2022 2:38 am
>
> 
HI Durik256:
Thank you for sharing, thank you！

ModelResearcher I'm useful, too


4D 45 53 48 32 2E 30 30 50 00 00 00

50 00 00 00  This is the map index

shader  In this document
## Post #27
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-03-16T01:19:59+00:00
- Post Title: Re: chuanshuo OL 3D models samples

I can't locate the bone parenting data, I would guess that the game doesn't store it?

here is my attempt in maxscript:


I had assumed the mesh format was simple and that I could try to practice importing the animation data.
However my issue was with the frost script because I have never written a script parser before.

Parsing the frost script caused me alot of trouble, so ended up having to read the script more bluntly.
I've spent more time then I wanted to on this game, so I won't be looking at the animation data.

```
	maxscript for chuanshuo
	by mariokart64n
	date march 15 2022
*/

clearListener()

try(destroyDialog ro_chuanshuo)catch(ro_chuanshuo)
rollout ro_chuanshuo "Chuanshuo" (
	button btn1 "import"
	checkbox chk1 "clearscene" checked:true
	checkbox chk2 "colours" checked:false
	checkbox chk3 "normals (slow)" checked:false
	checkbox chk4 "weights (slower)" checked:false
	struct fmtMODEL_Particle_Emitter_Item (
		name = "",
		shape = "mesh\plane01.mesh",
		type = "LINE",
		number = 1,
		particle = "blink.particle"
		)
	struct fmtMODEL_Particle_Emitter (
		item = #()
		)
	struct fmtMODEL_Trial_Emitter_Item (
		name = "",
		shape = "mesh\edge01.mesh",
		trail = "blade0000.trail"
		)
	struct fmtMODEL_Trial_Emitter (
		item = #()
		)
	struct fmtMODEL_Locator_Item (
		name = "",
		file = ""
		)
	struct fmtMODEL_Locator (
		item = #(),
		fn addItem &tag &param = (
			local i = 1
			local item_index = 0
			for i = 1 to item.count do (
				if item[i].name == tag[2] do (
					item_index = i
					exit
					)
				)
			if item_index == 0 then (
				append item (fmtMODEL_Locator_Item name:tag[2])
				item_index = item.count
				)
			case param[1] of (
				"file": item[item_index].file = param[2]
				)
			)
		)
	struct fmtMODEL_XYZ (
		x =  0.0,
		y =  0.0,
		z =  0.0
		)
	struct fmtMODEL_Sizebox (
		minimum = fmtMODEL_XYZ(),
		maximum = fmtMODEL_XYZ()
		)
	struct fmtMODEL_Pickbox (
		minimum = fmtMODEL_XYZ(),
		maximum = fmtMODEL_XYZ()
		)
	struct fmtMODEL_Binepose (
		file = ""
		)
	struct fmtMODEL_Particle_Parameter (
		name = "",
		visible = false,
		start = 300,
		end  = 1500
		)
	struct fmtMODEL_Action_Item (
		name = "",
		file = ""
		)
	struct fmtMODEL_Action (
		item = #()
		)
	struct fmtMODEL_Group_Mesh (
		name = "",
		billboard = false,
		y_billboard = false,
		animuv = false,		
		alphamode = "",
		animcolor = true,
		environmentmaps = true,
		effect_by_light = true,
		specular = true,
		mesh = ""
		)
	struct fmtMODEL_Group_Level (
		name = "",
		mesh_index = #(),
		animcolor = "",
		animuv = "",
		animvisibility = ""
		)
	struct fmtMODEL_Group_Object (
		name = "",
		mesharray = #(),
		levelarray = #(),
		fn addItem &tag &param = (
			local i = 1
			case tag[4] of (
				"mesharray": (
					local mesharray_index = 0
					for i = 1 to mesharray.count do (
						if mesharray[i].name == tag[5] do (
							mesharray_index = i
							exit
							)
						)
					if mesharray_index == 0 then (
						append mesharray (fmtMODEL_Group_Mesh name:tag[5])
						mesharray_index = mesharray.count
						)
					case param[1] of (
						"billboard": mesharray[mesharray_index].billboard = execute param[2]
						"y_billboard": mesharray[mesharray_index].y_billboard = execute param[2]
						"animuv": mesharray[mesharray_index].animuv = try(execute param[2])catch(param[2])
						"alphamode": mesharray[mesharray_index].alphamode = param[2]
						"animcolor": mesharray[mesharray_index].animcolor = try(execute param[2])catch(param[2])
						"environmentmaps": mesharray[mesharray_index].environmentmaps = execute param[2]
						"effect_by_light": mesharray[mesharray_index].effect_by_light = execute param[2]
						"specular": mesharray[mesharray_index].specular = execute param[2]
						"mesh": mesharray[mesharray_index].mesh = param[2]
						)
					)
				"levelarray": (
					local levelarray_index = 0
					for i = 1 to levelarray.count do (
						if levelarray[i].name == tag[5] do (
							levelarray_index = i
							exit
							)
						)
					if levelarray_index == 0 then (
						append levelarray (fmtMODEL_Group_Level name:tag[5])
						levelarray_index = levelarray.count
						)
					
					case param[1] of (
						"animcolor": levelarray[levelarray_index].animcolor = param[2]
						"animuv": levelarray[levelarray_index].animuv = param[2]
						"animvisibility": levelarray[levelarray_index].animvisibility = param[2]
						default: (
							case tag[6] of (
								"mesh_index": (
									append levelarray[levelarray_index].mesh_index #(param[1] as integer, param[2] as integer)
									)
								)
							)
						)
					)
				)
			)
		)
	struct fmtMODEL_Group_Item (
		name = "",
		object = #(),
		fn addItem &tag &param = (
			local i = 1
			local object_index = 0
			for i = 1 to object.count do (
				if object[i].name == tag[3] do (
					object_index = i
					exit
					)
				)
			if object_index > 0 then (
				object[object_index].addItem &tag &param
				)
			else (
				append object (fmtMODEL_Group_Object name:tag[3])
				object_index = object.count
				object[object_index].addItem &tag &param
				)
			)
		)
	struct fmtMODEL_Group (
		item = #(),
		fn addItem &tag &param = (
			local i = 1
			local item_index = 0
			for i = 1 to item.count do (
				if item[i].name == tag[2] do (
					item_index = i
					exit
					)
				)
			if item_index > 0 then (
				item[item_index].addItem &tag &param
				)
			else (
				append item (fmtMODEL_Group_Item name:tag[2])
				item_index = item.count
				item[item_index].addItem &tag &param
				)
			)
		)
	struct fmtMODEL_Texture_Item (
		index = 0,
		file = ""
		)
	struct fmtMODEL_Texture_Layer (
		name = "",
		item = #()
		)
	struct fmtMODEL_Texture (
		layer = #(),
		fn addItem &tag &param = (
			local i = 1
			local layer_index = 0
			for i = 1 to layer.count do (
				if layer[i].name == tag[2] do (
					layer_index = i
					exit
					)
				)
			if layer_index == 0 do (
				append layer (fmtMODEL_Texture_Layer name:tag[2])
				layer_index = layer.count
				)
			
			append layer[layer_index].item (fmtMODEL_Texture_Item index:(param[1] as integer) file:param[2])
			)
		)
	struct fmtMODEL_Timer (
		animuvcircle = 10000,
		animcolorcircle = 6000,
		animvisibilitycircle = 6000
		)
	struct fmtMODEL_Shader (
		file = ""
		)
	struct fmtMODEL (
		shader = fmtMODEL_Shader(),
		timer = fmtMODEL_Timer(),
		group = fmtMODEL_Group(),
		action = fmtMODEL_Action(),
		bindpose = fmtMODEL_Binepose(),
		pickbox = fmtMODEL_Pickbox(),
		sizebox = fmtMODEL_Sizebox(),
		locator = fmtMODEL_Locator(),
		trial_emitter = fmtMODEL_Trial_Emitter(),
		particle_emitter = fmtMODEL_Particle_Emitter(),
		texture = fmtMODEL_Texture(),
		fn read_model file = (
			local f = try(openFile file mode:"rt")catch(undefined)
			if f != undefined then (
				local tag = #()
				local s = ""
				local ss = #()
				local b = 0
				local grp = ""
				local tmp = ""
				local x = 0
				while not eof f do (
					s = readLine f
					
					if not matchPattern s pattern:"*=*" and not matchPattern s pattern:"*{*" and not matchPattern s pattern:"*}*" then (
						if (x = findString s "//") != undefined and x > 1 do (
							s = subString s 1 (x - 1)
							)
						if matchpattern s pattern:"//*" do continue
						s = trimRight (trimLeft s)
						if s.count == 0 do continue
						if s != undefined and s.count > 0 do (
							append tag s
							)
						)
					else if matchPattern s pattern:"*{*" then (
						b += 1
						)
					else if matchPattern s pattern:"*}*" then (
						b -= 1
						if tag.count > 0 do (
							deleteItem tag tag.count
							)
						)
					else if matchPattern s pattern:"*=*" then (
						ss = filterString s "= ;\n\r\t"
						if ss.count >= 2 and tag.count > 0 do (
							case tag[1] of (
								"shader": (
									case ss[1] of (
										"file": (shader.file = ss[2])
										)
									)
								"timer": (
									case ss[1] of (
										"animuvcircle": timer.animuvcircle = execute ss[2]
										"animcolorcircle": timer.animcolorcircle = execute ss[2]
										"animvisibilitycircle": timer.animvisibilitycircle = execute ss[2]
										)
									)
								"group": (
									group.addItem &tag &ss
									)
								"bindpose": (
									case ss[1] of (
										"file": bindpose.file = ss[2]
										)
									)
								"locator": (
									locator.addItem &tag &ss
									)
								"texture": (
									texture.addItem &tag &ss
									)
								)
							)
						)
					)
				close f
				) else (format "failed to open file\n")
			if f == undefined then false else true
			)
		)
	struct fmtBIND_Bone (
		matrix = #(
			#(1.0, 0.0, 0.0, 0.0),
			#(0.0, 1.0, 0.0, 0.0),
			#(0.0, 0.0, 1.0, 0.0),
			#(0.0, 0.0, 0.0, 1.0)
			),
		name_len = 0,
		name = "",
		fn read_bone &f = (
			matrix = #(
				#(readFloat f, readFloat f, readFloat f, readFloat f),
				#(readFloat f, readFloat f, readFloat f, readFloat f),
				#(readFloat f, readFloat f, readFloat f, readFloat f),
				#(readFloat f, readFloat f, readFloat f, readFloat f)
				)
			name_len = readLong f #unsigned
			local i = 1
			name = ""
			for i = 1 to name_len do (
				name += bit.IntAsChar(readByte f #unsigned)
				)
			)
		)
	struct fmtBIND (
		fileid = "BIND1.00",
		count = 0,
		bind = #(),
		fn read_bind file = (
			local f = try(fopen file "rb")catch(undefined)
			local i = 1
			if f != undefined then (
				local fsize = 0
				fseek f 0 #seek_end
				fsize = ftell f
				fseek f 0 #seek_set
				fileid = ""
				if fsize > 12 do (
					for i = 1 to 8 do (
						fileid += bit.IntAsChar(readByte f #unsigned)
						)
					)
				bind = #()
				if fileid == "BIND1.00" then (
					if (count = readLong f #unsigned) > 0 do (
						bind[count] = fmtBIND_Bone()
						for i = 1 to count do (
							bind[i] = fmtBIND_Bone()
							bind[i].read_bone(&f)
							)
						)
					) else (format "invaild file\n")
				fclose f
				) else (format "failed to open file: \t%\n" file)
			if f == undefined then false else true
			),
		fn build_bind = (
			--for o in selection do format "\t\t\t\t#(\"%\", \"%\"),\n" o.name (try(o.parent.name)catch(""))
			local parents = #(
				#("Hips", ""),
				#("Spine", "Hips"),
				#("Spine1", "Spine"),
				#("Neck", "Spine1"),
				#("Head", "Neck"),
				#("RightHjoint16", "Head"),
				#("RightHjoint17", "RightHjoint16"),
				#("RightHjoint18", "RightHjoint16"),
				#("RightHjoint19", "RightHjoint18"),
				#("RightHjoint20", "RightHjoint16"),
				#("RightHjoint21", "RightHjoint20"),
				#("RightHjoint25", "RightHjoint16"),
				#("RightHjoint24", "RightHjoint16"),
				#("RightHjoint27", "RightHjoint16"),
				#("RightHjoint26", "RightHjoint16"),
				#("RightHjoint22", "RightHjoint16"),
				#("RightHjoint23", "RightHjoint22"),
				#("LeftHjoint16", "Head"),
				#("LeftHjoint18", "LeftHjoint16"),
				#("LeftHjoint19", "LeftHjoint18"),
				#("LeftHjoint20", "LeftHjoint16"),
				#("LeftHjoint21", "LeftHjoint20"),
				#("LeftHjoint25", "LeftHjoint16"),
				#("LeftHjoint26", "LeftHjoint16"),
				#("LeftHjoint27", "LeftHjoint16"),
				#("LeftHjoint24", "LeftHjoint16"),
				#("LeftHjoint22", "LeftHjoint16"),
				#("LeftHjoint23", "LeftHjoint22"),
				#("LeftHjoint17", "LeftHjoint16"),
				#("LeftArm", "Spine1"),
				#("LeftForeArm", "LeftArm"),
				#("LeftHand", "LeftForeArm"),
				#("Leftjoint19", "LeftHand"),
				#("Leftjoint20", "Leftjoint19"),
				#("RightArm", "Spine1"),
				#("RightForeArm", "RightArm"),
				#("RightHand", "RightForeArm"),
				#("Rightjoint19", "RightHand"),
				#("Rightjoint20", "Rightjoint19"),
				#("LeftUpLeg", "Hips"),
				#("LeftLeg", "LeftUpLeg"),
				#("LeftFoot", "LeftLeg"),
				#("LeftToeBase", "LeftFoot"),
				#("Leftjoint14", "LeftToeBase"),
				#("Leftjoint15", "Leftjoint14"),
				#("RightUpLeg", "Hips"),
				#("RightLeg", "RightUpLeg"),
				#("RightFoot", "RightLeg"),
				#("RightToeBase", "RightFoot"),
				#("Rightjoint14", "RightToeBase"),
				#("Rightjoint15", "Rightjoint14"),
				#("joint10", "Hips"),
				#("joint11", "joint10"),
				#("joint12", "joint11"),
				#("joint13", "joint12"),
				#("joint14", "joint13"),
				#("joint15", "joint14"),
				#("Bip01_Pelvis", ""),
				#("Bip01_Spine", "Bip01_Pelvis"),
				#("Bip01_R_Thigh", "Bip01_Spine"),
				#("Bip01_R_Calf", "Bip01_R_Thigh"),
				#("Bip01_R_HorseLink", "Bip01_R_Calf"),
				#("Bip01_R_Foot", "Bip01_R_HorseLink"),
				#("Bip01_R_Toe0", "Bip01_R_Foot"),
				#("Bip01_R_Toe0Nub", "Bip01_R_Toe0"),
				#("Bip01_L_Thigh", "Bip01_Spine"),
				#("Bip01_L_Calf", "Bip01_L_Thigh"),
				#("Bip01_L_HorseLink", "Bip01_L_Calf"),
				#("Bip01_L_Foot", "Bip01_L_HorseLink"),
				#("Bip01_L_Toe0", "Bip01_L_Foot"),
				#("Bip01_L_Toe0Nub", "Bip01_L_Toe0"),
				#("Bip01_R_Clavicle", "Bip01_Spine"),
				#("Bip01_R_UpperArm", "Bip01_R_Clavicle"),
				#("Bip01_R_Forearm", "Bip01_R_UpperArm"),
				#("Bip01_R_Hand", "Bip01_R_Forearm"),
				#("Bip01_R_Finger0", "Bip01_R_Hand"),
				#("Bip01_R_Finger0Nub", "Bip01_R_Finger0"),
				#("Bip01_L_Clavicle", "Bip01_Spine"),
				#("Bip01_L_UpperArm", "Bip01_L_Clavicle"),
				#("Bip01_L_Forearm", "Bip01_L_UpperArm"),
				#("Bip01_L_Hand", "Bip01_L_Forearm"),
				#("Bip01_L_Finger0", "Bip01_L_Hand"),
				#("Bip01_L_Finger0Nub", "Bip01_L_Finger0"),
				#("Bip01_Neck", "Bip01_Spine"),
				#("Bip01_Head", "Bip01_Neck"),
				#("Bip01_HeadNub", "Bip01_Head"),
				#("Bip01", "Bip01_Pelvis"),
				#("joint0", ""),
				#("joint1", "joint0"),
				#("joint2", "joint1"),
				#("joint5", "joint0"),
				#("joint6", "joint5"),
				#("joint3", "joint0"),
				#("joint4", "joint3"),
				#("joint13", "joint0"),
				#("joint14", "joint13"),
				#("joint15", "joint14"),
				#("joint16", "joint15"),
				#("joint17", "joint16"),
				#("joint18", "joint17"),
				#("joint7", "joint0"),
				#("joint8", "joint7"),
				#("joint9", "joint8"),
				#("joint10", "joint9"),
				#("joint11", "joint10"),
				#("joint12", "joint11"),
				#("joint19", "joint0"),
				#("joint20", "joint19"),
				#("joint21", "joint20"),
				#("joint22", "joint21"),
				#("joint23", "joint22"),
				#("joint24", "joint23"),
				#("joint25", "joint0"),
				#("joint26", "joint25"),
				#("joint27", "joint26"),
				#("joint28", "joint27"),
				#("joint29", "joint28"),
				#("joint30", "joint29"),
				#("joint31", "joint0"),
				#("joint32", "joint31"),
				#("joint33", "joint32"),
				#("joint34", "joint33"),
				#("joint37", "joint33"),
				#("joint38", "joint37"),
				#("joint35", "joint33"),
				#("joint36", "joint35"),
				#("joint39", "joint31"),
				#("joint40", "joint39"),
				#("joint41", "joint40"),
				#("joint42", "joint41"),
				#("joint43", "joint42"),
				#("joint44", "joint43"),
				#("joint45", "joint31"),
				#("joint46", "joint45"),
				#("joint47", "joint46"),
				#("joint48", "joint47"),
				#("joint49", "joint48"),
				#("joint50", "joint49")
				)
			local i = 1, ii = 1
			local b
			local t = matrix3 1
			local boneArray = #()
			for i = 1 to bind.count do (
				t = matrix3 \
					([bind[i].matrix[1][1], bind[i].matrix[1][2], bind[i].matrix[1][3]] + bind[i].matrix[1][4]) \
					([bind[i].matrix[2][1], bind[i].matrix[2][2], bind[i].matrix[2][3]] + bind[i].matrix[2][4]) \
					([bind[i].matrix[3][1], bind[i].matrix[3][2], bind[i].matrix[3][3]] + bind[i].matrix[3][4]) \
					([bind[i].matrix[4][1], bind[i].matrix[4][3], bind[i].matrix[4][2]] * bind[i].matrix[4][4] * 39.370078740157480314960629921259842519685039370079)
				b = BoneSys.createBone t.position (t.position + [0.0, 1.0, 0.0]) [0, 1, 0]
				b.transform = t-- * (matrix3 [1,0,0] [0,0,1] [0,-1,0] [0,0,0])
				b.width = b.height = 1
				b.showLinksOnly = b.showLinks = true
				b.name = bind[i].name
				append boneArray b
				)
			for i = 1 to bind.count do (
				for ii = 1 to parents.count do (
					if matchPattern bind[i].name pattern:parents[ii][1] do (
						b = getNodeByName parents[ii][2]
						if b != undefined do (
							boneArray[i].parent = b
							)
						exit
						)
					)
				)
			boneArray
			)
		)
	struct fmtMESH_Material (
		index = 0,
		position = 0,
		count = 0,
		fn read_MESH_material &f = (
			index = readLong f #unsigned
			position = readLong f #unsigned
			count = readLong f #unsigned
			)
		)
	struct fmtMESH_Index (
		face1 = #(0, 0, 0), -- positions
		face2 = #(0, 0, 0), -- texcoord0
		face3 = #(0, 0, 0), -- texcoord1
		fn read_MESH_index &f = (
			face1 = #(readLong f #unsigned, readLong f #unsigned, readLong f #unsigned)
			face2 = #(readLong f #unsigned, readLong f #unsigned, readLong f #unsigned)
			face3 = #(readLong f #unsigned, readLong f #unsigned, readLong f #unsigned)
			)
		)
	struct fmtMESH (
		fileid = "MESH2.00",
		tex_index = 0,
		vertex_count = 0,
		position = #(),
		normal = #(),
		colour = #(),
		uv0_count = 0,
		texcorrd0 = #(),
		uv1_count = 0,
		texcorrd1 = #(),
		face_count = 0,
		face = #(),
		info_count = 0,
		info = #(),
		fn read_mesh file = (
			local f = try(fopen file "rb")catch(undefined)
			if f != undefined then (
				local fsize = 0
				fseek f 0 #seek_end
				fsize = ftell f
				fseek f 0 #seek_set
				if fsize > 12 then (
					local i = 1
					fileid = ""
					
					for i = 1 to 8 do (
						fileid += bit.IntAsChar (readByte f #unsigned)
						)
					if fileid == "MESH2.00" then (
						tex_index = readLong f #unsigned
						
						position = #()
						normal = #()
						colour = #()
						if (vertex_count = readLong f #unsigned) > 0 do (
							position[vertex_count] = [0.0, 0.0, 0.0]
							normal[vertex_count] = [0.0, 0.0, 0.0]
							colour[vertex_count] = (color 0 0 0 255)
							
							for i = 1 to vertex_count do (
								position[i] = [readFloat f, readFloat f, readFloat f]
								position[i] = [position[i][1], position[i][3], position[i][2]]
								position[i] *= 39.370078740157480314960629921259842519685039370079
								)
							for i = 1 to vertex_count do (
								normal[i] = [readFloat f, readFloat f, readFloat f]
								normal[i] = [normal[i][1], normal[i][3], normal[i][2]]
								)
							for i = 1 to vertex_count do (
								colour[i] = color (readByte f #unsigned) (readByte f #unsigned) (readByte f #unsigned) (readByte f #unsigned)
								)
							
							)
						texcorrd0 = #()
						if (uv0_count = readLong f #unsigned) > 0 do (
							texcorrd0[uv0_count] = [0.0, 0.0, 0.0]
							for i = 1 to uv0_count do (
								texcorrd0[i] = [readFloat f, 1.0 - (readFloat f), 0.0]
								)
							)
						
						texcorrd1 = #()
						if (uv1_count = readLong f #unsigned) > 0 do (
							texcorrd1[uv1_count] = [0.0, 0.0, 0.0]
							for i = 1 to uv1_count do (
								texcorrd1[i] = [readFloat f, readFloat f, 0.0]
								)
							)
						
						face = #()
						if (face_count = readLong f #unsigned) > 0 do (
							face[face_count] = fmtMESH_Index()
							for i = 1 to face_count do (
								face[i] = fmtMESH_Index()
								face[i].read_MESH_index(&f)
								)
							)
						info = #()
						if (info_count = readLong f #unsigned) > 0 do (
							info[info_count] = fmtMESH_Material()
							for i = 1 to info_count do (
								info[i] = fmtMESH_Material()
								info[i].read_MESH_material(&f)
								)
							)
						) else (format "invalid file type\n")
					) else (format "file is invalid\n")
					
				
				
				
				fclose f
				) else (format "failed to read file\n")
			if f == undefined then false else true
			),
		fn build_mesh &boneArray &texArray &fpath impNorm:false impColor:false impSkin:false = (
		
-- 			format "vertex_count: \t%\n" vertex_count
-- 			format "uv0_count: \t%\n" uv0_count
-- 			format "uv1_count: \t%\n" uv1_count
-- 			format "face_count: \t%\n" face_count
-- 			format "info_count: \t%\n" info_count
			local msh = undefined
			
			if position.count > 0 and face.count > 0 do (
				local i = 1, ii = 1
				local faceArray = #()
				local uv0Array = #()
				local uv1Array = #()
				faceArray[face_count] = [1, 1, 1]
				uv0Array[face_count] = [1, 1, 1]
				uv1Array[face_count] = [1, 1, 1]
				for i = 1 to face_count do (
					faceArray[i] = ([face[i].face1[1], face[i].face1[3], face[i].face1[2]] + 1)
					uv0Array[i] = ([face[i].face2[1], face[i].face2[3], face[i].face2[2]] + 1)
					uv1Array[i] = ([face[i].face3[1], face[i].face3[3], face[i].face3[2]] + 1)
					)
				
				local mat = undefined
				local l = fmtMODEL_Texture_Layer()
				local t = fmtMODEL_Texture_Item()
				local tex = "noTexture"
				for l in texArray.layer do (
					
					if l.name == "layer0" do (
						for t in l.item do (
							if t.index == tex_index do (
								tex = t.file
								)
							)
						exit
						)
					)
				if tex != undefined and tex != "" and tex != "noTexture" do (
					mat = Standard()
					mat.diffuseMap = Bitmaptexture fileName:(fpath + tex)
					)
				
				msh = mesh vertices:position faces:faceArray tverts:texcorrd0
				msh.backfacecull = on
				msh.displayByLayer = false
				msh.wirecolor = random (color 0 0 0) (color 255 255 255)
				if mat != undefined do (
					msh.material = mat
					showTextureMap mat on
					)
				
				--if layer != undefined do (layer.addNode msh)
				if texcorrd0.count > 0 do (
					
					meshop.setNumMaps msh 3 keep:true
					
					meshop.setNumMapVerts msh 1 texcorrd0.count keep:true
					meshop.setNumMapVerts msh 2 texcorrd1.count keep:true
					
					
					for i = 1 to texcorrd0.count do meshOp.setMapVert msh 1 i texcorrd0[i]
					for i = 1 to texcorrd1.count do meshOp.setMapVert msh 2 i texcorrd1[i]
					
					meshop.setNumMapFaces msh 1 uv0Array.count
					meshop.setNumMapFaces msh 2 uv1Array.count
					
					for i = 1 to uv0Array.count do meshop.setMapFace msh 1 i uv0Array[i]
					for i = 1 to uv1Array.count do meshop.setMapFace msh 2 i uv1Array[i]
					)
				setCommandPanelTaskMode #modify
				if impColor do (
					setNumCPVVerts msh position.count
					buildVCFaces msh
					for i = 1 to faceArray.count do setVCFace msh i faceArray[i]
					for i = 1 to colour.count do setVertColor msh i colour[i]
					for i = 1 to colour.count do meshop.setVertAlpha msh -2 #(i) (colour[i].alpha * 0.392157)
					--msh.showVertexColors = true
					--msh.vertexColorType = #color
					)
				if impNorm do (
					for i = 1 to faceArray.count do setFaceSmoothGroup msh i 1
					select msh
					local normMod = Edit_Normals()
					local normID = #{}, x
					
					modPanel.addModToSelection normMod ui:off
					msh.Edit_Normals.MakeExplicit selection:#{1..(normal.count)}
					for i = 1 to normal.count do (
						normID = #{}
						normMod.ConvertVertexSelection #{i} &normID
						for x in normID do normMod.SetNormal x (normalize normal[i])
						)
					select msh
					modPanel.addModToSelection (VertexPaint ()) ui:off
					)
				if impSkin and boneArray.count > 0 do (
					local x = 1, j = 0
					local groups = #()
					local weight = #()
					groups[vertex_count] = #()
					weight[vertex_count] = #()
					for i = 1 to vertex_count do (
						groups[i] = #()
						weight[i] = #()
						)
					for i = 1 to info.count do (
						for ii = (info[i].position + 1) to (info[i].position + info[i].count) do (
							append groups[ii] info[i].index
							)
						)
					for i = 1 to groups.count do (
						append weight[i] (1.0 / groups[i].count)
						)
					
					local skinMod = skin()
					select msh
					modPanel.addModToSelection skinMod ui:off
					
					local boneNames = #()
					boneNames[boneArray.count] = ""
					for x = 1 to boneArray.count do (
						if x!=boneArray.count then (
							skinOps.addbone skinMod boneArray[x] 0
							)
						else (
							skinOps.addbone skinMod boneArray[x] 1
							)
						boneNames[x] = boneArray[x].name
						)
					
					local boneIDMap = #()
					boneIDMap[boneArray.count] = 0
					local boneNameIdx = 0
					for x = 1 to boneArray.count do (
						boneNameIdx = findItem boneNames (skinOps.GetBoneName skinMod x 0)
						if boneNameIdx==0 do (boneNameIdx=1)
						boneIDMap[x]=boneNameIdx
						)
					
					modPanel.setCurrentObject skinMod
					local bi = #(), wv = #()
					local boneid = 0
					for x = 1 to groups.count do ( -- verts
						bi = #()
						wv = #()
						for j = 1 to groups[x].count do (
							boneid = groups[x][j]
							boneid = findItem boneIDMap (boneid + 1)
							if weight[x][j] > 0.0 and boneid > 0 do (
								append bi boneid
								append wv weight[x][j]
								)
							)
						skinOps.ReplaceVertexWeights skinMod x bi wv
						)
					)
				)
			msh
			)
		)
	fn open_mesh file = (
		-- create a object to store file data to
		local m = fmtMESH()
		
		-- open the file
		local f = try(fopen file "rb")catch(undefined)
		
		-- test if the file is open
		if f != undefined then (
			
			-- read data to struct from file
			m.read_mesh(&f)
			
			m.build()
			
			-- close file
			fclose f
			) else (messagebox "failed to open file")
		
		m
		)
	fn open_file file = (
		if chk1.checked do (
			delete $*
			)
		local f = undefined
		local model = fmtMODEL()
		if model.read_model(file) then (
			local fpath = getFilenamePath file
			local bindpose = fpath + model.bindpose.file
			local shaderfile = fpath + model.shader.file
			if doesFileExist shaderfile then (
				model.read_model(shaderfile)
				) else (format "failed to load shader\n")
			local boneArray = #()
			if doesFileExist bindpose then (
				local bnd = fmtBIND()
				f = try(openFile file mode:"rt")catch(undefined)
				if f != undefined then (
					if bnd.read_bind(bindpose) then (
						with redraw off with undo off (
							boneArray = bnd.build_bind()
							)
						) else (format "failed to load bind\n")
					fclose f
					) else (format "failed to open file: \t%\n" file)
				) else (format "failed to locate bindpose\n")
			local i = 1, ii = 1, iii = 1
			local mesh_file = ""
			local msh = undefined
			local mesh = fmtMESH()
			local layer = undefined
			for i = 1 to model.group.item.count do (
				for ii = 1 to model.group.item[i].object.count do (
					layer = LayerManager.getLayerFromName model.group.item[i].name
					if layer == undefined do (
						layer = layermanager.newLayerFromName model.group.item[i].name
						)
					for iii = 1 to model.group.item[i].object[ii].mesharray.count do (
						mesh_file = fpath + model.group.item[i].object[ii].mesharray[iii].mesh
						if doesFileExist mesh_file then (
							mesh = fmtMESH()
							mesh.read_mesh(mesh_file)
							msh = mesh.build_mesh boneArray model.texture fpath impNorm:chk3.checked impColor:chk2.checked impSkin:chk4.checked
							if msh != undefined do (
								layer.addNode(msh)
								)
							) else (format "failed to load mesh file: \t%\n" mesh_file)
						)
					)
				)
			) else (format "failed to read model\n")
		)
	on btn1 pressed do (open_file (GetOpenFileName caption:"Select File" types: ("model|MODEL|All files (*.*)|*.*|")))
	)
createDialog ro_chuanshuo

```
## Post #28
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-03-16T09:38:03+00:00
- Post Title: Re: chuanshuo OL 3D models samples

> Reply from mariokart64n ↑Wed Mar 16, 2022 9:19 am at Wed Mar 16, 2022 9:19 am
>
> 

Thank you for your attention. He's a skeleton file。
