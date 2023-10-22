## Post #1
- Username: DanTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 10, 2016 2:11 am
- Post datetime: 2016-10-11T00:15:44+00:00
- Post Title: Broken UV map on Saints Row the Third model I extracted

Hello. I'm pretty new to exporting/importing models, and 3D modeling in general. I've been using Blender 2.77 on Windows for over a month now and I've managed to import a model into Garry's Mod and created a ragdoll out of a model of Axl I downloaded. Now I'm taking a bigger step forward by extracting models from Saints Row the Third. 

I've managed to extract Pierce from the game using Gibbed tools, SR4 Mesh Viewer and Texture utilities all from saintsrowmods. I converted him into an obj. using the mesh viewer and imported him into Blender. The model looks fine, but when I attempted to apply one of his textures to him, this happened:

[http://i.imgur.com/9OqENEw.png](http://i.imgur.com/9OqENEw.png)

The texture is not being applied correctly and it seems like the UV map is broken. I have no idea how to fix this and I really need help.
Here are all the files I got when I extracted Pierce and his textures.

[http://i.imgur.com/bLWz8Zh.png](http://i.imgur.com/bLWz8Zh.png)

Is there anyway to fix the UV map or extract the model with the UV map the way it's suppose to be? Do I need to use an alternative method to extract? I feel so lost right now.
I am determined to make a Gmod playermodel of Pierce and possibly some other characters, however I'm afraid this problem is going to prevent me from doing so.

I can provide sample files if necessary for analyses. Any help is greatly appreciated! I really need it...
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-11T19:53:13+00:00
- Post Title: Broken UV map on Saints Row the Third model I extracted

> Reply from DanTheFox
>
> SR4 Mesh Viewerwhich version? This one (?):
[https://www.saintsrowmods.com/forum/thr ... ewer.4604/](https://www.saintsrowmods.com/forum/threads/sr4-character-mesh-viewer.4604/)

> and it seems like the UV map is broken.for me the mesh appears to be strange, too.

> The model looks fine,? really, there's dozens of extra edges and the mesh looks odd,
having no smooth surface

Did you try to export kinzie or oleg for example as wavefront .obj using the above linked viewer?

Similar problems as with Pierce?
## Post #3
- Username: DanTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 10, 2016 2:11 am
- Post datetime: 2016-10-11T23:58:48+00:00
- Post Title: Broken UV map on Saints Row the Third model I extracted

> which version? This one (?):
>
> https://www.saintsrowmods.com/forum/thr ... ewer.4604/ Yes I used v1.6 and downloaded MV_src_1.6.7z

> ? really, there's dozens of extra edges and the mesh looks odd,
>
> having no smooth surface Yeah...like I said I am new to this and I was unsure so I assumed that the model was like that...My stupid mistake.

> Did you try to export kinzie or oleg for example as wavefront .obj using the above linked viewer?
>
> 
>
> Similar problems as with Pierce? Not yet, but I did export Phillipe Loren as practice before Pierce and the same thing happened to him. Though I will go ahead and extract them and I'll inform you on what I get.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-12T05:24:55+00:00
- Post Title: Broken UV map on Saints Row the Third model I extracted

I'd suggest to try out Mariusz' blender importer from here:
[viewtopic.php?f=16&t=10987&p=98364&hili ... _pc#p98364](http://forum.xentax.com/viewtopic.php?f=16&t=10987&p=98364&hilit=npc_basehead.ccmesh_pc#p98364)

(be sure to have old blender 2.49b installed; doesn't work with newer versions!)

His script has several advantages compared to meshviewer obj export (right side of pic) as can be seen in the below pic:

no extra edges, proper smoothing, correct uv map

Since I could check the accompanying basehead ccmesh model only I can't asssure that the script will work for other models like Pierce etc.



npc_basehead.jpg (171.59 KiB) Viewed 146 times
## Post #5
- Username: DanTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 10, 2016 2:11 am
- Post datetime: 2016-10-12T19:58:40+00:00
- Post Title: Broken UV map on Saints Row the Third model I extracted

> Reply from shakotay2
>
> I'd suggest to try out Mariusz' blender importer from here:
viewtopic.php?f=16&t=10987&p=98364&hili ... _pc#p98364

(be sure to have old blender 2.49b installed; doesn't work with newer versions!)

His script has several advantages compared to meshviewer obj export (right side of pic) as can be seen in the below pic:

no extra edges, proper smoothing, correct uv map

Since I could check the accompanying basehead ccmesh model only I can't asssure that the script will work for other models like Pierce etc. Alright, I'll give it a go. Also Kinzie and Oleg came out the same way.

Thank you for the suggestion though. I will inform you on what happens.
