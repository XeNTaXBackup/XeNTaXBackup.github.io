## Post #1
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-11T03:43:34+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

I found 4 rendermesh files in one of the pak files of the game, and they are very big so i'm guessing these must contains all the models of the game. Using the convertor tool (which meant to be used for the PC version) don't give much anything, all i got was a weird looking model and a giant vine. The extentions are different, instead of being win32 files, they are nx files so that's probably why we get nothing interesting by using the convertor. Unfortunately, i didn't find any other informations about these files. 
Here are the files : [http://www.mediafire.com/file/tk1ec4sw6 ... s.zip/file](http://www.mediafire.com/file/tk1ec4sw6m8gbxn/GSTDOE_rendermesh_files.zip/file)
It's would be nice if we can get skeleton datas as well as the dark counterpart of the level objects. I have been struggling to have the game's models perfectly ripped.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-13T12:11:28+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Using hex2obj (view link in my sig)
.



rendermesh_0.png (83.95 KiB) Viewed 218 times


(One submesh only.)
## Post #3
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-13T13:04:41+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from shakotay2 ↑Sun Dec 13, 2020 8:11 pm at Sun Dec 13, 2020 8:11 pm
>
> 
Using hex2obj (view link in my sig)
.
rendermesh_0.png
(One submesh only.)

I tried a bit of experience with Hex2obj before, but it's pretty confusing for me. Also for unknown reason, i can't open rendermesh_0.bin.nx with it.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-13T19:02:18+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Yeah, there's a lot of meshes in those files - at least in 0.bin and 1.bin.  Files 2 and 3 seems to have lots of "mesh" data but no face information that I can see.  File 0 alone has 4998 separate meshes.  Here's an example of one (obviously I don't have textures to test it with):
## Post #5
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-13T19:31:33+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from DKDave ↑Mon Dec 14, 2020 3:02 am at Mon Dec 14, 2020 3:02 am
>
> 
Yeah, there's a lot of meshes in those files - at least in 0.bin and 1.bin.  Files 2 and 3 seems to have lots of "mesh" data but no face information that I can see.  File 0 alone has 4998 separate meshes.  Here's an example of one (obviously I don't have textures to test it with):

Rendermesh 2 and 3 are probably used to make models morph into their dark counterpart which mean they are vertex shaders. Though having the models ripped from them would still be nice, even if there's only vertices.

There was a convertor for the models files of the game, but work only on win32 files since they had that extension. Also rendermesh files where in every level files, which had the models that the level were using so getting all models at once was difficult.

Maybe the creator of the convertor (or someone else) can create an alt version that work perfectly for the nx files.

By the way, despite i have all textures of the game, i don't know which of them fit in your ripped model.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-13T19:53:27+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

rendermesh_0-0x5F415b8.png (86.84 KiB) Viewed 188 times
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-13T20:11:08+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

The format of the whole archive isn't too bad - there's a table at the start which has info like the stride value for each mesh.  This is referenced from the 2nd table, which has the vertex/face counts, etc.  Then the vertex/face data tables after that.

There's probably an index somewhere for the textures that are referred to from the mesh data in these files.

Here's one of the meshes without face data from 2.bin.  Logically there should probably be face data somewhere, but doesn't seem to be in files 2 & 3.

29,000 vertices in this mesh.
## Post #8
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-13T21:31:07+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from shakotay2 ↑Mon Dec 14, 2020 3:53 am at Mon Dec 14, 2020 3:53 am
>
> 
rendermesh_0-0x5F415b8.png
Ok for some unknown reasons i can open rendermesh_0 on Hex2obj. I took the coordinate of the model shown here and put it texture on it.



Carriagesmall.png (204.76 KiB) Viewed 181 times



> Reply from DKDave ↑Mon Dec 14, 2020 4:11 am at Mon Dec 14, 2020 4:11 am
>
> 
The format of the whole archive isn't too bad - there's a table at the start which has info like the stride value for each mesh.  This is referenced from the 2nd table, which has the vertex/face counts, etc.  Then the vertex/face data tables after that.

There's probably an index somewhere for the textures that are referred to from the mesh data in these files.

Here's one of the meshes without face data from 2.bin.  Logically there should probably be face data somewhere, but doesn't seem to be in files 2 & 3.

29,000 vertices in this mesh.
Can you tell me how you get the models step by step? I'd love to get the Owlverlords and other enemies i didn't got.

Since texture files aren't mentioned, you have to find the texture yourself on the textures folder by basing it from the shape and UV of the model. For exemple, the carriage shown here is a popular level object so it's was easy to find. But there is others that are hard to recognise and look for their textures.
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-14T00:05:36+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

If you want to try out my hacked together work in progress Noesis script, I've attached it.

You only need to enter the required mesh number in the file and it should display it.  UVs and normals are included where known, as not every mesh has the same vertex layout!
[fmt_ds_giana_nx.zip](https://xentaxbackup.github.io/file/19182_fmt_ds_giana_nx.zip)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-14T03:01:56+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Nice script! Position offsets would be nice, too, to not have the meshes clumped:
.



a1000submeshes.png (152.23 KiB) Viewed 157 times
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-14T03:11:26+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

1000-2000.jpg (140.34 KiB) Viewed 157 times
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-14T03:22:21+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

4000-4500.jpg (175.56 KiB) Viewed 155 times

4000-4500
## Post #13
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-14T07:13:35+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from DKDave ↑Mon Dec 14, 2020 8:05 am at Mon Dec 14, 2020 8:05 am
>
> 
If you want to try out my hacked together work in progress Noesis script, I've attached it.

You only need to enter the required mesh number in the file and it should display it.  UVs and normals are included where known, as not every mesh has the same vertex layout!

Thanks for the script but unfortunately i couldn't reach my laptop until next Saturday. I see in those pictures this is a mess but despite that, i can recognize some model like the floating boats, owl machine and other platforms. 

I was always curious if the unused enemies had their models. I found their textures files, but i can't find them in-game nor their animation files. [https://mobile.twitter.com/YukkuriFan64 ... 9645177864](https://mobile.twitter.com/YukkuriFan64/status/1335171179645177864)
## Post #14
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-14T13:05:34+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

I've looked for the positional info in the file but couldn't see anything that worked - unless someone else knows where it is, and I can easily add it.
## Post #15
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-14T14:47:05+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from DKDave ↑Mon Dec 14, 2020 9:05 pm at Mon Dec 14, 2020 9:05 pm
>
> 
I've looked for the positional info in the file but couldn't see anything that worked - unless someone else knows where it is, and I can easily add it.
Have you checked both rendermesh 0 and 1? Character models are always located at the end of rendermesh files so they are probably located in rendermesh 1.
I'd love to help you, but i don't know much about hex analysis, so good luck
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-14T15:27:57+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Yeah, I found some characters models in file 0:



I've also amended my code to include an export to .obj option for the models (attached).  It successfully exports all models in file 0 - haven't tried the others yet.
[fmt_ds_giana_nx.zip](https://xentaxbackup.github.io/file/19187_fmt_ds_giana_nx.zip)
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-12-14T15:51:04+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from GianaSistersFan64 ↑Mon Dec 14, 2020 3:31 am at Mon Dec 14, 2020 3:31 am
>
> 
There was a convertor for the models files of the game, but work only on win32 files since they had that extension. Also rendermesh files where in every level files, which had the models that the level were using so getting all models at once was difficult.

Maybe the creator of the convertor (or someone else) can create an alt version that work perfectly for the nx files.
Its only difference from the PC version is that it uses 64-bit integers for certain offset fields. So you might actually consider it as a 'win64' file.  
Here's the updated GSTDConv tool compatible for both PC & Switch versions, tested with the samples provided in both threads so far.


 GSTDConv.zip
Updated 2020.12.14 (6.89 KiB) Downloaded 17 times



A random big model for an intimidating guy:
[](https://ibb.co/Wp5x2hZ)

All meshes in these rendermesh files have unique global IDs, which must be how the assets are referenced. There's no further info than that. So you need to look into other asset files for material info and such.
## Post #18
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-14T17:14:14+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from DKDave ↑Mon Dec 14, 2020 11:27 pm at Mon Dec 14, 2020 11:27 pm
>
> 
Yeah, I found some characters models in file 0:



I've also amended my code to include an export to .obj option for the models (attached).  It successfully exports all models in file 0 - haven't tried the others yet.
Wait... Did you really found this in the rendermesh file? This character you found doesn't fit to the Giana Sisters style and it's funny it's left here. He (probably) came from Fade To Silence, which make sense since both games were developed in the same time. 
> Reply from Bigchillghost ↑Mon Dec 14, 2020 11:51 pm at Mon Dec 14, 2020 11:51 pm
>
> 
Its only difference from the PC version is that it uses 64-bit integers for certain offset fields. So you might actually consider it as a 'win64' file.  
Here's the updated GSTDConv tool compatible for both PC & Switch versions, tested with the samples provided in both threads so far.
GSTDConv.zip

A random big model for an intimidating guy:


All meshes in these rendermesh files have unique global IDs, which must be how the assets are referenced. There's no further info than that. So you need to look into other asset files for material info and such.
Welcome back and thank you  But like i said, i couldn't reach my laptop until Saturday. But i'm still looking forward for the progress and hope we can get the dark counterpart of the level objects and characters rigged.
## Post #19
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-14T17:27:28+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Yeah, there's a few characters like that in there.  Could be leftovers, or just Easter eggs for us to find.

As far as I can see, there's no skeleton info in those files, so those must be stored elsewhere.

It would be good to get some of the textures to experiment with too.
## Post #20
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-14T17:42:20+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from DKDave ↑Tue Dec 15, 2020 1:27 am at Tue Dec 15, 2020 1:27 am
>
> 
Yeah, there's a few characters like that in there.  Could be leftovers, or just Easter eggs for us to find.

As far as I can see, there's no skeleton info in those files, so those must be stored elsewhere.

It would be good to get some of the textures to experiment with too.

The skeleton datas are probably stored in the animations file. Check this thread to get the file and extract it : [viewtopic.php?f=21&t=23005&p=168758#p168758](https://forum.xentax.com/viewtopic.php?f=21&t=23005&p=168758#p168758)

For the textures, check this page : [https://www.textures-resource.com/pc_co ... teddreams/](https://www.textures-resource.com/pc_computer/gianasisterstwisteddreams/)
There isn't everything, but it's should be enough.
## Post #21
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-12-14T19:10:49+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

I did manage to get the textures working at least - but still not sure how they're referenced properly.  But it's a start!  Still definitely a lot more in those files to work out.  This is with the diffuse and normal texture maps, although I'm not sure if the normal map is displaying properly or not.
## Post #22
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-14T19:36:49+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from DKDave ↑Tue Dec 15, 2020 3:10 am at Tue Dec 15, 2020 3:10 am
>
> 
I did manage to get the textures working at least - but still not sure how they're referenced properly.  But it's a start!  Still definitely a lot more in those files to work out.  This is with the diffuse and normal texture maps, although I'm not sure if the normal map is displaying properly or not.

Gurglewocky's (the red dragon) textures name is dragon_c.dds and dragon_n.dds. All image files are dds files so it's easy to open them. 
I already ripped Gurglewocky, but your rip is different from mine. Mine had his tail straight and his eyes was more open. 

By the way, here's the character models i got from the PC version : [http://www.mediafire.com/file/h6id5dvc3 ... J.zip/file](http://www.mediafire.com/file/h6id5dvc3rbsnvt/Models+OBJ.zip/file)
There is the girls ( Cute and Punk Giana and Maria), enemies and bosses. Maybe this could help to compare their models from the PC and Switch version. There is also their textures with their original names.
## Post #23
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-19T14:47:40+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

I tried the convertor and came across with several interesting stuff.
The "Non-Giana Sisters" models are  leftovers from Rogue Stormers, not Fade To Silence, my bad.
Rendermesh 0 contain a lot of placeholders, uncluding for Rogue Stormers.
I remembered Black Forest Games did a Rogue Stormers level for Twisted Dreams, which explain everything. But there is no textures for the models used that could be found in the game's files. [https://www.youtube.com/watch?v=rFhW_Ah85ss](https://www.youtube.com/watch?v=rFhW_Ah85ss)
Characters's real models are only in Rendermesh 1. There is also in Rendermesh 0, but it's not their real models, only level sceneries.
Also, i know i already sended this, here's the already extracted animation pak file : [https://www.mediafire.com/file/t7qsh4d2 ... k.zip/file](https://www.mediafire.com/file/t7qsh4d2lka4yzs/animations.pak.zip/file)
Maybe merging the x86 files with the rendermesh files could result the character models being rigged, but i'm not sure if it's can work. There is also ppc files, which i don't know much about these.

By the way, i made a picture showing off some character models.

There is indeed models of the unused enemies, i was right.
## Post #24
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-23T09:59:43+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Another bump, but also something interesting i discovered.
When looking at level datas, i found several files that may be related to skeleton datas and morphing level objects.
There is block3000000000001.block.nx, probably used to morph models, and it mention other things.
vt_index.bin.nx mentions a lot of textures name.
And rendershape.bin.nx mentions also textures name as well as models name. I also noticed it's contained bone names, which suggest it may contain skeleton datas.
There is also other files which i don't know what much they do, but judging by their file size, it's probably contain other interesting things.
Here are the files : [https://www.mediafire.com/file/fvacpfq0 ... s.zip/file](https://www.mediafire.com/file/fvacpfq04vfxjkh/GSTDLeveldatas.zip/file)
I got these files from level 1-4. And there isn't all models so we need to get the same files from every levels.
Also, is there any tool that can view skeleton data with hex editing similar to Hex2obj?
## Post #25
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-12-27T23:13:10+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from GianaSistersFan64 ↑Wed Dec 23, 2020 5:59 pm at Wed Dec 23, 2020 5:59 pm
>
> 
Another bump, but also something interesting i discovered.
When looking at level datas, i found several files that may be related to skeleton datas and morphing level objects.
There is block3000000000001.block.nx, probably used to morph models, and it mention other things.
vt_index.bin.nx mentions a lot of textures name.
And rendershape.bin.nx mentions also textures name as well as models name. I also noticed it's contained bone names, which suggest it may contain skeleton datas.
There is also other files which i don't know what much they do, but judging by their file size, it's probably contain other interesting things.
Here are the files : https://www.mediafire.com/file/fvacpfq0 ... s.zip/file
I got these files from level 1-4. And there isn't all models so we need to get the same files from every levels.
Also, is there any tool that can view skeleton data with hex editing similar to Hex2obj?
So... Anyone is interested?
Also rendershape.bin.nx shows the models real extension, which seems to be vmesh or model files. Like i mentioned in my previous post, we have to unpake every level files and get the same files from every of these to get everything, kinda like the rendermesh files from the PC version.
Sorry for bumping, but i'm out of ideas right now, i guess i got everything we needed to get the models rigged and their morphing animations. I hope we could get a great result if it's work.
## Post #26
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2021-01-01T23:30:57+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Ok, i promise this is my last bump, but i'd still love to know if it would work and we are pretty close to the goal. Anyway, here's the files from the rest of the levels : [https://www.mediafire.com/file/dyhi6y0u ... s.zip/file](https://www.mediafire.com/file/dyhi6y0ug8ua99v/allleveldatas.zip/file)
However, levela-3 contains a lot of xml files, which mention a lot of things, but i don't know what they are meant to be used for. Also, just to let you know, the zip file when decompressed does 333 Mb. If you want to know more, please read my previous posts.
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-02T17:30:54+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

level1-1.png (105.58 KiB) Viewed 76 times



For the xmls I assume once you know which object (from actorentry.xml) has
object UID="32651"
you can use this as position offsets: (just a wild guess)
<element index="12" data="18000.000000" />
<element index="13" data="0.000000" />
<element index="14" data="6300.000000" />
## Post #28
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2021-01-02T18:44:39+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

> Reply from shakotay2 ↑Sun Jan 03, 2021 1:30 am at Sun Jan 03, 2021 1:30 am
>
> 
level1-1.png

For the xmls I assume once you know which object (from actorentry.xml) has
object UID="32651"
you can use this as position offsets: (just a wild guess)
<element index="12" data="18000.000000" />
<element index="13" data="0.000000" />
<element index="14" data="6300.000000" />
Since actorentry.xml mention many times "transform" and "shape", it's probably related to their morphing. Also, did you find any vertex shader data inside block.nx or other files? But anyway, thanks for the reply.

It's pretty odd levela-3 is the only level pak to have many xml files. I'm not even sure if it's connected to the other levels as well or just only the level where they are.
## Post #29
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2021-01-06T22:04:05+00:00
- Post Title: Re: Giana Sisters : Twisted Dreams - Owltimate Edition NX files

Ok, i know you all have enough of my bumps but i don't want the thread to be left in a corner with dust on it.  
Anyway i'd love to know if there is any tools that can view skeleton data, kinda similar to Hex2obj. I tried to find one, but i couln't. I want to check inside the rendershape.bin.nx files myself and maybe i can find something interesting.
