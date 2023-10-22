## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-01-14T15:29:21+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

Hi guys! I talked to the guy who made the Dragon nest model viewer and got the file format for this game. It includes model, texture, bones and animation, in otherwise full file format. I started creating a noesis python script but got stuck and Chrrox has helped me....ALOT to intepret and understand. But I am totally stuck so I present what I have now and hopefully the community can help to build it on 

In the provided zip file there is:

dragon nest.py
+model
+texture
+anim file

I was able to make noesis count bones, show the model without texture and....yes, that is about it 

[http://www.2shared.com/file/GrmHBqGg/dragon_nest.html](http://www.2shared.com/file/GrmHBqGg/dragon_nest.html)


Oops, forgot the file format source so here it is on pastebin, and comments in code is chinese but maybe understand with google translate:

[http://pastebin.com/z9GFxfxp](http://pastebin.com/z9GFxfxp)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-14T16:50:03+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

Call rapi.rpgSetMaterial before you commit the triangles.
Then the texture should be applied to those faces.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-01-14T16:58:54+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

sweet, going to a party now but will hop on this info asap
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-14T17:32:40+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

Your normals and UV's might be a little weird because of how you are calling the functions.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-16T06:10:23+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

The chinese characters are all messed up in pastebin.
Maybe you can post it somewhere else or just upload it?

```

```


There are two "render modes" as the spec says. One of them (when it's 1 or 257) requires you to commit triangles using TRIANGLE_STRIP, the other (when it's 0) with TRIANGLE. 

There are two msh types; one with bones/weights and the other doesn't. I don't know when this would be checked.

I also don't know how to find the correct texture. Maybe I'm actually just missing textures.
But other than that it gets the geometry.

There are also some weird structs after the vertex section sometimes. I'm not sure what they are, or when they occur.

There are some files where you have

```
count {
   char[256] name
}

```


I'm not too sure when it occurs

But, you can use it for reference if you want. I probably just have to see what patterns those unknowns are.
[fmt_DragonNest_msh.7z](https://xentaxbackup.github.io/file/4994_fmt_DragonNest_msh.7z)
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-02-20T19:15:27+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

Updated pastebin with english translation

[http://pastebin.com/AiQmvg83](http://pastebin.com/AiQmvg83)
## Post #7
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-05-08T14:21:07+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

sorry for call back this old thread.

i just finishied a viewer(mesh and anime), but in opengl + qt. the document is nearly right but has lots of error.
btw, if any problems with mesh or anime, maybe I can help.
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-05-09T07:05:10+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

I would like to be able to export model + animation in some way
## Post #9
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-06-06T05:18:05+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

how can import those anim files into 3dsmax, please help
## Post #10
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-06-07T00:25:46+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

> Reply from amzerof6
>
> how can import those anim files into 3dsmax, please help

You need to export those anims to something readable in 3DS Max, normally to the format of the model (normally fbx).
## Post #11
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-06-08T03:48:32+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

> Reply from Darko
>
> amzerof6 wrote:how can import those anim files into 3dsmax, please help

You need to export those anims to something readable in 3DS Max, normally to the format of the model (normally fbx).

I tried every Dragon Nest‘s tools, but there's no one can convert anim files successful.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-10T08:18:29+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

> Reply from amzerof6
>
> I tried every Dragon Nest‘s tools, but there's no one can convert anim files successful.Does that apply to this one, too?
[http://www.dnmodz.com/guides/msh-converter/](http://www.dnmodz.com/guides/msh-converter/)

Brief: "You can choose a msh file,as well as its animation file(*.ani) that you can finish a
msh-to-fbx conversion."

(If it doesn't work you should upload an ani sample because noone can help without it.)
## Post #13
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-06-12T11:54:16+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

> Reply from shakotay2
>
> amzerof6 wrote:I tried every Dragon Nest‘s tools, but there's no one can convert anim files successful.Does that apply to this one, too?
http://www.dnmodz.com/guides/msh-converter/

Brief: "You can choose a msh file,as well as its animation file(*.ani) that you can finish a
msh-to-fbx conversion."

(If it doesn't work you should upload an ani sample because noone can help without it.)

yes,I tried this tool , but when I import those fbx files to 3dsmax had some errors . model and skin were fine , but there's no animations . 
[airhound.rar](https://xentaxbackup.github.io/file/7468_airhound.rar)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-20T18:54:25+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

thx.
This is the skeleton. I'm unsure whether Bip01 is a dummy. 
If so there should be a direct connection between Pelvis and Spine.



airhound_skel.JPG (76.65 KiB) Viewed 536 times
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-11-22T16:45:14+00:00
- Post Title: [NOESIS] Dragon Nest, help needed

Hello

Here is blender importer for models from this game.
It works only with Blender version 249 and Python version 2.6


It import skinned and textured meshes with animations.

-select *.skn files for importing meshes
-select *.ani files for unpacking animations
-after unpacking *.ani files select *.anim files for  animation

For Noesis use fbx blender exporter. 

Importer:
[http://www.mediafire.com/download/9fo7x ... -20%5D.zip](http://www.mediafire.com/download/9fo7x0f34c5jikc/Blender249%5BDragonNest%5D%5Bskn%5D%5Bani%5D%5B2014-11-20%5D.zip)


Example:
[http://www.mediafire.com/download/9a45j ... onnest.zip](http://www.mediafire.com/download/9a45jctb30gxfgc/dragonnest.zip)
## Post #16
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-11-23T09:38:14+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

> Reply from Szkaradek123
>
> Hello

Here is blender importer for models from this game.
It works only with Blender version 249 and Python version 2.6


It import skinned and textured meshes with animations.

-select *.skn files for importing meshes
-select *.ani files for unpacking animations
-after unpacking *.ani files select *.anim files for  animation

For Noesis use fbx blender exporter. 

Importer:
http://www.mediafire.com/download/9fo7x ... -20%5D.zip


Example:
http://www.mediafire.com/download/9a45j ... onnest.zip

Awesome!

Before I download everything to have a look, does it work with any version of Dragon Nest?

It seems there are 3 loool 

[http://dragonnest.nexon.net/](http://dragonnest.nexon.net/)
[http://dn.cherrycredits.com/](http://dn.cherrycredits.com/)
[http://www.dragonnest.eu/](http://www.dragonnest.eu/)
## Post #17
- Username: orokborokhulu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 12, 2014 8:03 pm
- Post datetime: 2014-12-12T10:27:13+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

blender importer is works!   thanks
## Post #18
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-26T16:17:27+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

> Reply from Szkaradek123
>
> Hello

Here is blender importer for models from this game.
It works only with Blender version 249 and Python version 2.6


It import skinned and textured meshes with animations.

-select *.skn files for importing meshes
-select *.ani files for unpacking animations
-after unpacking *.ani files select *.anim files for  animation

For Noesis use fbx blender exporter. 

Importer:
http://www.mediafire.com/download/9fo7x ... -20%5D.zip


Example:
http://www.mediafire.com/download/9a45j ... onnest.zip
many thanks for the wonderful share, any chance to make support in Noesis? really would be grateful if you can make adaptation to Noesis, many thanks for your time mate.
## Post #19
- Username: TheAnkou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 31, 2015 9:38 pm
- Post datetime: 2018-04-29T18:35:40+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

> Reply from Szkaradek123
>
> Hello

Here is blender importer for models from this game.
It works only with Blender version 249 and Python version 2.6


It import skinned and textured meshes with animations.

-select *.skn files for importing meshes
-select *.ani files for unpacking animations
-after unpacking *.ani files select *.anim files for  animation

For Noesis use fbx blender exporter. 

Importer:
http://www.mediafire.com/download/9fo7x ... -20%5D.zip


Example:
http://www.mediafire.com/download/9a45j ... onnest.zip

Hello, your script works perfectly, but there is a problem with Skin modifier, it doesn't apply on .msh when import .skn (also there is wrong bone hierarchy) file into blender, but  succesfully applies and set bone hierarchy when import .anim file
As you can see on screenshots, 

.skn import (rotating bones doesn't change model position, that means Skin modifier isn't applied) 


.anim import (model is animated -> skin modifier applied) 



Might be usefull: [http://www.gpbeta.com/post/develop/drag ... converter/](http://www.gpbeta.com/post/develop/dragon-nest-msh-converter/)

I'm really need mesh with skin modifier in bind pose, thanks

Best wishes,
Ankou
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-30T20:52:43+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

> Reply from TheAnkou
>
> but there is a problem with Skin modifier, it doesn't apply on .msh when import .sknI don't think so, look at  mesh.skinList.append(skin) in def mshParser(filename,g).

> (also there is wrong bone hierarchy)In fact the above mentioned parser creates a skeleton ('bind') without bones hierarchy. The parenting information is read from the anim files later.

So def aniParser(filename,g) creates the anims from lotus_golem.ani for example and
def animParser(filename,g) creates the 'pose' skeleton using the parent/child info from an anim file.

That's the way it goes, the anims are shown correctly.

I modified the py script to get the mesh with hierarchical skeleton (without creating anim frames). Then deleted the 'bind' skeleton.

```
	skeleton=Skeleton()
	skeleton.name='pose'
	skeleton.BONESPACE=True
	skeleton.NICE=True
	action=Action()
	action.BONESPACE=True
	action.BONESORT=True
	
	bone=Bone()
	bone.name='Scene Root'
	bone.matrix=Matrix().invert()
	skeleton.boneList.append(bone)
	while(True):
		if g.tell()==g.fileSize():break
		bone=Bone()
		child = g.find('\x00')
		parent = g.find('\x00')
		abone=ActionBone()
		abone.name=child
		bone.name=child
		bone.parentName=parent
		
		pos = VectorMatrix(g.f(3))#;print m,pos
		rot = QuatMatrix(g.f(4)).resize4x4()#c;print m,rot
		scale = g.f(3)
		count = g.i(1)[0]
		bone.matrix=rot*pos
		for m in range(count):#position keys
			g.H(1)[0]
			g.f(3)
		count = g.i(1)[0]
		for m in range(count):#rotation keys
			g.H(1)[0]
			g.short(4,'h',15)
		count = g.i(1)[0]
		for m in range(count):#scale keys
			g.H(1)[0]
			g.f(3)
		#action.boneList.append(abone)
		skeleton.boneList.append(bone)	
	skeleton.BINDMESH=True
	skeleton.draw()
	scene = bpy.data.scenes.active
	for object in scene.objects:
		if object.type=='Mesh':
			bindPose('bind','pose',object)
			#skeleton.BINDMESH=True
	#action.skeleton='pose'		
	#action.draw()	
	action.setContext()
```




Lotus_Golem_test.jpg (133.95 KiB) Viewed 250 times
## Post #21
- Username: TheAnkou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 31, 2015 9:38 pm
- Post datetime: 2018-05-02T02:23:10+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

> Reply from shakotay2
>
> I modified the py script to get the mesh with hierarchical skeleton (without creating anim frames). Then deleted the 'bind' skeleton.

Hi, script works perfectly!

> Reply from shakotay2
>
> In fact the above mentioned parser creates a skeleton ('bind') without bones hierarchy. The parenting information is read from the anim files later.
But i wanted that when you import .skn, script imports mesh already with bones hierarchy. Because when i convert model to .nif and animations to .kf file and load them in nifskope, due to mesh without bone hierarchy, animations are not loading.

Anyways, with your script to load .anim without keys, i have found another way to do that properly.
Thanks for reply and script, have a nice day!

Best wishes,
Ankou
## Post #22
- Username: roronoaSanji
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 30, 2018 2:16 am
- Post datetime: 2018-05-29T20:20:03+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

Random noob here

I runned the script and imported the .skn but it doesn't have texture?
## Post #23
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-19T10:58:57+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

How to use that plugin in Blender v2.49? And it will work with v2.79?
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-19T11:41:03+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

> Reply from tainhx
>
> How to use that plugin in Blender v2.49?review some of the dozens of posts of Szkaradek how to use his scripts, especially with Win7 and later.

> And it will work with v2.79?nope
## Post #25
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-19T16:38:53+00:00
- Post Title: Re: [NOESIS] Dragon Nest, help needed

I run script and choose an ani file but nothing happen
