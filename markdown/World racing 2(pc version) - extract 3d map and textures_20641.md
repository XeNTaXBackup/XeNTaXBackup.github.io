## Post #1
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-06-11T00:09:44+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

Hey guys. Anyone have script to extract the map files from this game?

What i want to do is to be able to open this map in 3dsmax 2012.

.vtx is the file ending of the biggest file but there are other files there. The biggest ones are the 3d files which i want to open but also the texture files.

I will post a link to mediafire with a folder from the map
 Its called ct autobahn. Its not big in size maybe 30 mb.

Link to sample from mediafire : [https://www.mediafire.com/file/ae56ba5x ... 1.zip/file](https://www.mediafire.com/file/ae56ba5xvhz9m4a/V1.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-18T09:57:19+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from toab776 ↑Tue Jun 11, 2019 8:09 am at Tue Jun 11, 2019 8:09 am
>
> What i want to do is to be able to open this map in 3dsmax 2012.I don't have access to 3dsmax atm (and most people/extractors don't care for maps, afai experienced.  )

> .vtx is the file ending of the biggest file but there are other files there.rough view of the map:



Autobahn-vtx.jpg (227.39 KiB) Viewed 255 times


(mesh format uses floats, FVF size is 32 here)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-18T14:17:02+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

part of map level:



Autobahn-part-of-level.png (115.55 KiB) Viewed 248 times
## Post #4
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-06-21T20:58:11+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from shakotay2 ↑Tue Jun 18, 2019 5:57 pm at Tue Jun 18, 2019 5:57 pm
>
> 
toab776 wrote: ↑Tue Jun 11, 2019 8:09 amWhat i want to do is to be able to open this map in 3dsmax 2012.I don't have access to 3dsmax atm (and most people/extractors don't care for maps, afai experienced.  )
.vtx is the file ending of the biggest file but there are other files there. rough view of the map:
Autobahn-vtx.jpg
(mesh format uses floats, FVF size is 32 here)

Looking very good. Did you manage to extract the model and its textures? Could it be seen in 3dsmax now?

Thanks in advance. toab776.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-21T22:12:12+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from toab776 ↑Sat Jun 22, 2019 4:58 am at Sat Jun 22, 2019 4:58 am
>
> Looking very good. Did you manage to extract the model and its textures?what I got is what you see (in my posts).
## Post #6
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-06-22T10:51:49+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from shakotay2 ↑Sat Jun 22, 2019 6:12 am at Sat Jun 22, 2019 6:12 am
>
> 
toab776 wrote: ↑Sat Jun 22, 2019 4:58 amLooking very good. Did you manage to extract the model and its textures?what I got is what you see (in my posts).

To continue with what i managed to do here is a picture of my work right now through the mesh extractor program i am using.

[](https://ibb.co/2vtxgNR)
[](https://ibb.co/qxTkZg7)

The problem i am having is finding the face indices in the numbers. I have not yet made the UV's.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-22T19:15:52+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

face indices are in CT_Autobahn.idx
they are like such (you need some trick to get the output from hex2obj):

f 1 2 3 
f 1 3 4 
f 5 6 7 
f 5 7 8 
...

(Maximum face index was 62415 for the first submesh, iirc. FIs' count was 162415.)
-------------------------
2nd submesh:
.



CT_Autobahn_part2.png (57.93 KiB) Viewed 194 times



You need to copy .vtx and .idx into one file for such:
copy /b ct_autobahn.vtx + ct_autobahn.idx ct_all.vt_idx

Load ct_all.vt_idx into hex2obj.

Then save 20 different obj files with 20 different vertex start addresses and FI start addresses.

btw: UV pos is 16
## Post #8
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-06-29T15:31:15+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from shakotay2 ↑Sun Jun 23, 2019 3:15 am at Sun Jun 23, 2019 3:15 am
>
> 
face indices are in CT_Autobahn.idx
they are like such (you need some trick to get the output from hex2obj):

f 1 2 3 
f 1 3 4 
f 5 6 7 
f 5 7 8 
...

(Maximum face index was 62415 for the first submesh, iirc. FIs' count was 162415.)
-------------------------
2nd submesh:
.
CT_Autobahn_part2.png

You need to copy .vtx and .idx into one file for such:
copy /b ct_autobahn.vtx + ct_autobahn.idx ct_all.vt_idx

Load ct_all.vt_idx into hex2obj.

Then save 20 different obj files with 20 different vertex start addresses and FI start addresses.

btw: UV pos is 16

When you say UV pos is 16. What does it mean?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-29T15:59:12+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

It means that you have to replace the 99 in the screenshot in my previous post by 16.
## Post #10
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-06-29T21:58:44+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from shakotay2 ↑Sat Jun 29, 2019 11:59 pm at Sat Jun 29, 2019 11:59 pm
>
> 
It means that you have to replace the 99 in the screenshot in my previous post by 16.

After i do this can i extract the mesh with materials assigned now?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-30T09:26:02+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from toab776 ↑Sun Jun 30, 2019 5:58 am at Sun Jun 30, 2019 5:58 am
>
> 
shakotay2 wrote: ↑Sat Jun 29, 2019 11:59 pm
It means that you have to replace the 99 in the screenshot in my previous post by 16.


After i do this can i extract the mesh with materials assigned now?You can extract the mesh with uvs using File/SaveAs mesh in hex2obj.

Google how to create materials/.mtl files for blender then you can simply insert a line
mtllib my_materials.mtl into the obj file.

Each submesh needs a usemtl line in the face indices block, for example:
g SM_1
usemtl material1
## Post #12
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-06-30T12:50:13+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from shakotay2 ↑Sun Jun 30, 2019 5:26 pm at Sun Jun 30, 2019 5:26 pm
>
> 
toab776 wrote: ↑Sun Jun 30, 2019 5:58 am
shakotay2 wrote: ↑Sat Jun 29, 2019 11:59 pm
It means that you have to replace the 99 in the screenshot in my previous post by 16.


After i do this can i extract the mesh with materials assigned now?
You can extract the mesh with uvs using File/SaveAs mesh in hex2obj.

Google how to create materials/.mtl files for blender then you can simply insert a line
mtllib my_materials.mtl into the obj file.

Each submesh needs a usemtl line in the face indices block, for example:
g SM_1
usemtl material1

If i wanted to extract the materials that the games makers made in the qad file. How would this be done? I am aware that i will have to manually apply textures later one by one but i mean like all roads have same material assigned so i only have to apply textures once and the grass has same materials etc etc.

... in short to extract the material names and position and size from the qad or vtx file.

And also. What exactly is this testUV.obj? What is it used for?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-30T16:47:35+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from toab776 ↑Sun Jun 30, 2019 8:50 pm at Sun Jun 30, 2019 8:50 pm
>
> ... in short to extract the material names and position and size from the qad or vtx file.I have no idea and time to check for it.

> And also. What exactly is this testUV.obj? What is it used for?It's just a helper file for displaying uvs - you can ignore it.
## Post #14
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-07-01T08:13:56+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

> Reply from shakotay2 ↑Mon Jul 01, 2019 12:47 am at Mon Jul 01, 2019 12:47 am
>
> 
toab776 wrote: ↑Sun Jun 30, 2019 8:50 pm... in short to extract the material names and position and size from the qad or vtx file.I have no idea and time to check for it.
And also. What exactly is this testUV.obj? What is it used for?
It's just a helper file for displaying uvs - you can ignore it.

Alright man. Thank you. Appreciate it anyways. I will keep on messing around with the code. I will finish it eventually.

You can reply when you have time?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-28T12:43:52+00:00
- Post Title: World racing 2(pc version) - extract 3d map and textures

textures are ptx - you need to play around with TextureFinder for example.
.



car-ptx.png (96.85 KiB) Viewed 77 times

IrfanView, Raw file, 16 bit, 6 5 5
(dunno why it reads 24 BPP, a bug in IV? cause I selected 16 BPP)
## Post #16
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-09-28T16:05:25+00:00
- Post Title: Re: World racing 2(pc version) - extract 3d map, textures and materials

> Reply from shakotay2 ↑Sat Sep 28, 2019 8:43 pm at Sat Sep 28, 2019 8:43 pm
>
> 
textures are ptx - you need to play around with TextureFinder for example.
.
car-ptx.pngIrfanView, Raw file, 16 bit, 6 5 5
(dunno why it reads 24 BPP, a bug in IV? cause I selected 16 BPP)

Looking very good.

Are these the textures inside the objects folder? Maybe they are only for the objects. Do you think there might be textures for: grass, tarmac, railing, trees and such landscape and maybe even road signs as well as sand and dirt in there?
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-29T06:49:54+00:00
- Post Title: Re: World racing 2(pc version) - extract 3d map, textures and materials

everything you want  
V1.zip\V1\Objects\Textures
## Post #18
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2019-09-29T12:27:30+00:00
- Post Title: Re: World racing 2(pc version) - extract 3d map, textures and materials

> Reply from shakotay2 ↑Sun Sep 29, 2019 2:49 pm at Sun Sep 29, 2019 2:49 pm
>
> 
everything you want  
V1.zip\V1\Objects\Textures

Hmm so maybe there is grass and tarmac and sand and dirt also in there?
