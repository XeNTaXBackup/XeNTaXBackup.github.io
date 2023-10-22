## Post #1
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-12-14T09:29:03+00:00
- Post Title: Macross PS2 mdl

Hi guys, I was trying to extract models from this game but there is no way to do that because we can't decompress the game files  
So using PCSX2 emulator I found the decompressed file of vf1s, it has different models inside: fighter, battroid and gerwalk and textures. I cut the file to split these models and textures. Now we can examine the model format, this is what I know:





The model is made by tiny submeshes so maybe it is more easy if we check the submesh header, as you can see all submeshes have the same ID. Maybe by reading that we can extract all submeshes at once. I used model researcher and vertices are Float, padding 20, UVs are Float padding 24 but there are no faces, we need to autogenerate them.. 
I don't know if my info is correct, I am not sure about UVs...

Here are 4 vf1s model files from the decompressed file:
[https://www.mediafire.com/file/wss183r8 ... l.rar/file](https://www.mediafire.com/file/wss183r81ytsmaj/macross_PS2_vf1s_mdl.rar/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-14T10:55:59+00:00
- Post Title: Macross PS2 mdl

vif tags, yeah.., (16 bytes after "sub mesh ID")
I have no idea why it looks so strange:
.



vf1s_01.jpg (63.76 KiB) Viewed 315 times
## Post #3
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-12-14T11:28:31+00:00
- Post Title: Macross PS2 mdl

It looks like something, Can you try with vf1s_00.mdl? it is fighter mode(airplane). I think vf1s_01.mdl is battroid mode(robot).
but I don't know why it looks weird, lol. Maybe I am wrong with vertices offset or padding
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-14T12:31:23+00:00
- Post Title: Macross PS2 mdl

Here you go (from the shape it doesn't look that different to me):
.



vf1s_00.jpg (111.62 KiB) Viewed 300 times



> Reply from roocker666 ↑Wed Dec 14, 2022 7:28 pm at Wed Dec 14, 2022 7:28 pm
>
> Maybe I am wrong with vertices offset or paddingGuess, it's correct - cool, that you found that. I didn't use your data, though. It's just searching vif tags (which include the vertex count) and log the vertices after them.

edit: that's all bogus because the FVFsize is different!
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-14T12:49:57+00:00
- Post Title: Macross PS2 mdl

How to get the thing (required H2O files see appended zip file, didn't care for uvs, sry):

```
to create obj files from all contained submeshes.

After hex2obj processed the H2O files there should exist the same amount of obj files 
in the model's folder named from *_0.obj to *_xx.obj.

When executing the py script below in a blender Text Editor window with alt-p
make sure to have set "path_to_obj_dir" in the *.py to YOUR model/H2O directory.

Also be sure that there are no obj files in a maybe contained subdirectory.
(they would be loaded, too)

Best choice would be to have a separate folder for each *.mdl and its obj files.

Keep in mind that ?3.obj is NOT created from ?3.H2O! 
First line in an obj reveals its H2O-source.
```


blender import (if you don't want to import the sub meshes  one by one).
Save code as imp_multiple_obj.py file for example.
Be sure to adjust the path 'D:\\', 'test\\mdl' to the one on your pc before executing the script.

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
#path_to_obj_dir = os.path.join('C:\\', 'objects')
path_to_obj_dir = os.path.join('D:\\', 'test\\mdl')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```


edit: H2O files deleted because of wrong FVFsize
(uv address are wrong; just taken from old code without correction!)
## Post #6
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-12-14T20:31:28+00:00
- Post Title: Macross PS2 mdl

Thanks for the .H2O files and the script. I imported the files to Blender and yes, it looks like that. I don't know WTF...

BTW, I found new info, all data before 1st submesh is a MESH GROUP HEADER!, we know that 1st submesh is at 0x4B48(Image 2), so 0x4B40 tells you the number of submeshes in that group: "4F" that means 79 submeshes. Now here is the weird thing: at 0x4B10 first two bytes are maybe the size of this mesh group(this includes mesh group header and all submeshes) but 3FE is not the correct size, we need one more 0, like this: 3FE0. Now count from 0x4B10 until you get 3FE0 bytes, you can see the next Mesh group header one line down with the same format.

So, to find the correct size of each Mesh group put one more 0 in the first two bytes and add 10(Hex). something like this:
"3FE", put one more 0 ---> "3FE0" and add 10(Hex), ---> 3FE0 + 10 = 3FF0

You can know the size of each Mesh group with this method. It works but I don't know why, this is so f*****g weird... lol!
## Post #7
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T03:47:03+00:00
- Post Title: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Dec 14, 2022 6:55 pm at Wed Dec 14, 2022 6:55 pm
>
> 
vif tags, yeah.., (16 bytes after "sub mesh ID")
I have no idea why it looks so strange:

OK, here is an update. I Found about 63 Groups of submeshes, to find the next group search for: 00 00 03 68, this is some kind of ID for Groups.

For UVs I think is vertAddr + 20, it looks like something. The mesh looks better if is FVF32, I am not sure about UVs yet..

Here are a few pictures:



MACROSS_TEST2.jpg (83.05 KiB) Viewed 221 times
## Post #8
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T03:48:07+00:00
- Post Title: Macross PS2 mdl

This is the format, I am not sure if everything is correct:



MACROSS_TEST2_1.jpg (183.6 KiB) Viewed 220 times
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-18T09:31:13+00:00
- Post Title: Macross PS2 mdl

edit: ignore FVFsize! 16 is wrong - must be 32

(Ok, forget about the lower part this post since you were talking of vf1s_00.mdl (but uv problem remains.
First H2O for that model is

0x0 39
Vb1
16 99
0x4b6c 24
021000
0x4d14 255

Calculation of uv addr same as below.

)
---------------------------------

> Reply from roocker666 ↑Tue Apr 18, 2023 11:47 am at Tue Apr 18, 2023 11:47 am
>
> For UVs I think is vertAddr + 20, it looks like something. The mesh looks better if is FVF32, I am not sure about UVs yet..Well, dunno, as for vf1s_01.mdl
with current 0002.H2O (wrong uv addr 0x6338)

0x0 39
Vb1
16 99
0x611c 24
021000
0x6338 255

edit: correction
(vAddr=0x611c, vCnt=12) -> uv addr is= vAddr + 12 (according to rooker)

Next vertex block at 0x6414 then.
## Post #10
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T20:09:48+00:00
- Post Title: Macross PS2 mdl

> Reply from shakotay2 ↑Tue Apr 18, 2023 5:31 pm at Tue Apr 18, 2023 5:31 pm
>
> 
(Ok, forget about the lower part this post since you were talking of vf1s_00.mdl (but uv problem remains.
First H2O for that model is

0x0 39
Vb1
16 99
0x4b6c 24
021000
0x4d14 8

Calculation of uv addr same as below.

)
---------------------------------

Sorry but why 0x4b6c 24?  Because vertices count at 0x4b64 says 12(0C), yes this is 1st submesh in "vf1s_00.mdl", sorry for not explaining that, lol.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-18T20:43:32+00:00
- Post Title: Macross PS2 mdl

> Reply from roocker666 ↑Wed Apr 19, 2023 4:09 am at Wed Apr 19, 2023 4:09 am
>
> Sorry but why 0x4b6c 24?  Because vertices count at 0x4b64 says 12(0C), yes this is 1st submesh in "vf1s_00.mdl", sorry for not explaining that, lol.Are you sure? 24 because of signature search (well, it should be 25, but I subtracted 1 to make it fit). The mesh seemed o fit to me then:
.



s2_signature.png (32.08 KiB) Viewed 171 times



But I see: every 2nd value might be a normal. Need to check this...
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-04-18T20:45:11+00:00
- Post Title: Macross PS2 mdl

> Reply from roocker666 ↑Tue Apr 18, 2023 11:48 am at Tue Apr 18, 2023 11:48 am
>
> 
MACROSS_TEST2_1
just a byte search

i made plugin for Noesis:


 fmt_mdl.zip
(711 Bytes) Downloaded 26 times



*file structure something like this (just a quick look):

```
4 int (nameOfs,unkofs,unk2ofs,dataOfs)
seek(nameOfs)
int numName
for numName:
	32 bytes

seek(unkofs)
	read unk inf
	
seek(unk2ofs)
for unkNum:
	176 bytes block 

seek(dataOfs)
	read data

```
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-18T20:47:21+00:00
- Post Title: Macross PS2 mdl

Haha, should have noticed that earlier... 

I'm asking myself when was the first hint for a FVFsize of 32?? 
ha, I see:

> Reply from roocker666 ↑Tue Apr 18, 2023 11:47 am at Tue Apr 18, 2023 11:47 am
>
> 
For UVs I think is vertAddr + 20, it looks like something. The mesh looks better if is FVF32, I am not sure about UVs yet..

Seems I was in a confusion of vf1s_00 and vf1s_01- Someting like this. Need to patch the code...

Looks better now, but some parts still missing, well... (the signature 0380xx6C appears 788 times. But there must be a strange bug, shxt... Array[11997] was big enough...  ) Hmm, I filtered all meshes with a count <20. Not a good idea, seems...
.



vf1s_00.png (73.46 KiB) Viewed 158 times



Aaaaargh, 788 H2O files!!
## Post #14
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T21:25:46+00:00
- Post Title: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 4:47 am at Wed Apr 19, 2023 4:47 am
>
> 
Haha, should have noticed that earlier... 

I'm asking myself when was the first hint for a FVFsize of 32?? 
ha, I see:
roocker666 wrote: ↑Tue Apr 18, 2023 11:47 am
For UVs I think is vertAddr + 20, it looks like something. The mesh looks better if is FVF32, I am not sure about UVs yet..

Seems I was in a confusion of vf1s_00 and vf1s_01- Someting like this. Need to patch the code...

Looks better now, but some parts still missing, well... (the signature 0380xx6C appears 788 times. But there must be a strange bug, shxt... Array[11997] was big enough...  ) Hmm, I filtered all meshes with a count <20. Not a good idea, seems...


Aaaaargh, 788 H2O files!!

Yep, there are about 788 submeshes.
## Post #15
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T21:27:19+00:00
- Post Title: Macross PS2 mdl

> Reply from Durik256 ↑Wed Apr 19, 2023 4:45 am at Wed Apr 19, 2023 4:45 am
>
> 
roocker666 wrote: ↑Tue Apr 18, 2023 11:48 am
MACROSS_TEST2_1

just a byte search

i made plugin for Noesis:
fmt_mdl.zip

*file structure something like this (just a quick look):
Code: Select all'GFX2OBJ/PS2;0200'
4 int (nameOfs,unkofs,unk2ofs,dataOfs)
seek(nameOfs)
int numName
for numName:
	32 bytes

seek(unkofs)
	read unk inf
	
seek(unk2ofs)
for unkNum:
	176 bytes block 

seek(dataOfs)
	read data
  That is awesome man!, I will test your script
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-18T21:29:19+00:00
- Post Title: Re: Macross PS2 mdl

more meshes:
.



vf1s_00-full.png (31.63 KiB) Viewed 233 times
## Post #17
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T22:38:09+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 5:29 am at Wed Apr 19, 2023 5:29 am
>
> 
more meshes:

That looks a lot better. What about UVs? I used vertAddr + 12, these are first 8 submeshes. It looks like something but Y axis too big.



vf1s00_mdl_UVs 12.jpg (120.29 KiB) Viewed 217 times
## Post #18
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-18T22:46:57+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from Durik256 ↑Wed Apr 19, 2023 4:45 am at Wed Apr 19, 2023 4:45 am
>
> 
roocker666 wrote: ↑Tue Apr 18, 2023 11:48 am
MACROSS_TEST2_1

just a byte search

i made plugin for Noesis:
fmt_mdl.zip

I tested your plugin, works fine thanks. Did you find UVs? I tried with vertAddr +12, 16, 20 and 24 but nothing yet... +12 and +24 look like something.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-19T05:40:16+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from roocker666 ↑Wed Apr 19, 2023 6:38 am at Wed Apr 19, 2023 6:38 am
>
> 
That looks a lot better. What about UVs? I used vertAddr + 12,In the picture of your post as of Wed Dec 14, 2022 10:29 am you wrote 0x4B6C +8.
Post as of Tue Apr 18, 2023 4:48 am: 0x4B80 (-> +20)

To me (vertAddr+12) is a possible uv address that makes sense because at vertAddr +16 there should be normals.
tx: vertAddr+12, ty: vertAddr+28 ?
v1 tx1
n1 ty1
v2 tx2
n2 ty2
.. ...

Your latest uv picture looks good, bw. Just scale down y of uvs.

btw: I logged them like so (not bad but too less points, imho):
.



vf1s_00_uvs.png (22.61 KiB) Viewed 168 times
## Post #20
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-19T07:22:07+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 1:40 pm at Wed Apr 19, 2023 1:40 pm
>
> 
roocker666 wrote: ↑Wed Apr 19, 2023 6:38 am
That looks a lot better. What about UVs? I used vertAddr + 12, In the picture of your post as of Wed Dec 14, 2022 10:29 am you wrote 0x4B6C +8.
Post as of Tue Apr 18, 2023 4:48 am: 0x4B80 (-> +20)

To me (vertAddr+12) is a possible uv address that makes sense because at vertAddr +16 there should be normals.
tx: vertAddr+12, ty: vertAddr+28 ?
v1 tx1
n1 ty1
v2 tx2
n2 ty2
.. ...

Your latest uv picture looks good, bw. Just scale down y of uvs.

Sorry, I was testing different values for UVs: +12, +16, +20, +24, lol. BUt yes I think +12 is correct. But in your picture, Uvs looks fine!, I mean don't look scaled in Y axis, don't know Why I get scaled Uvs in Y axis. Here is the texture(maybe you need to filp yours in Y and X  but that is all):



vf1s00 texture.jpg (48.52 KiB) Viewed 168 times
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-19T08:06:13+00:00
- Post Title: Re: Macross PS2 mdl

Thanks! Perfecly (almost  ):
.



vf1s_00_Tex.jpg (148.85 KiB) Viewed 159 times



Need to restructure the whole thing from Make_obj/H2O to pure Make_obj.
(Want the exe or the C source?)
## Post #22
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-19T08:30:45+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 4:06 pm at Wed Apr 19, 2023 4:06 pm
>
> 
Thanks! Perfecly (almost  ):


Need to restructure the whole thing from Make_obj/H2O to pure Make_obj.
(Want the exe or the C source?)

Nice!, it looks great. I think we need to apply the skeleton to fix the pose but I am ok with that  Thanks man. 

I think the exe is fine
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-19T08:55:56+00:00
- Post Title: Re: Macross PS2 mdl

Here you go:
.


 DLL_Make_obj_Macross.zip
(62.85 KiB) Downloaded 15 times



(Tested with vf1s_00.mdl only!)
## Post #24
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-19T09:13:14+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 4:55 pm at Wed Apr 19, 2023 4:55 pm
>
> 
Here you go:


(Tested with vf1s_00.mdl only!)

THANK YOU!
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-19T09:47:08+00:00
- Post Title: Re: Macross PS2 mdl

There's some strange flickering when moving the plane. Any idea what causes this?
.



flickering.jpg (155.88 KiB) Viewed 140 times

In wireframe mode it looks ok. Maybe a matter of the dozens of sub meshes around where the uv coordinates don't fit exactly?
## Post #26
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-19T09:50:42+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 5:47 pm at Wed Apr 19, 2023 5:47 pm
>
> 
There some strange flickering when moving the plane. Any idea what's causes this?

That is because the two legs are in the same place, we need to split the legs. And it will be the same with other parts, probaly arms, hands, etc.
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-19T09:52:21+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from roocker666 ↑Wed Apr 19, 2023 5:50 pm at Wed Apr 19, 2023 5:50 pm
>
> That is because the two legs are in the same place, we need to split the legs.Time for Durik.
## Post #28
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-19T10:03:10+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from shakotay2 ↑Wed Apr 19, 2023 5:52 pm at Wed Apr 19, 2023 5:52 pm
>
> 
Time for Durik.

Well, if he can attach the skeleton that will be the solution, that is too hard for me.. lol

BTW there is a dude inside   


Thats funny
[vf1s00_pilot.jpg](https://xentaxbackup.github.io/file/23694_vf1s00_pilot.jpg)
## Post #29
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-21T10:05:03+00:00
- Post Title: Re: Macross PS2 mdl

I tried to build battroid mode(robot) piece by piece, It is a nightmare! I used other model that I extracted with ninja ripper as guidance. Now looks good but it still needs more work... Here is my result so far:



VF1S00_FIX.jpg (106.75 KiB) Viewed 107 times
## Post #30
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-05-08T11:22:25+00:00
- Post Title: Re: Macross PS2 mdl

This is a Game Made by tise right?
Maybe this .MdL is very similar to the King of Route 66 one.
That would be awesome!!!!
[viewtopic.php?t=21245](https://forum.xentax.com/viewtopic.php?t=21245)
I checked for Scripts on tose Games before
## Post #31
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-09T02:22:37+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from Henchman800 ↑Mon May 08, 2023 7:22 pm at Mon May 08, 2023 7:22 pm
>
> 
This is a Game Made by tise right?
Maybe this .MdL is very similar to the King of Route 66 one.

Both games were developed by Sega AM2 but .MDL files are different. Besides, Macross files use an unknow compression method, we don't know how to decompress those files yet  I dumped these .MDL files from PCSX2 memory.
## Post #32
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-05-09T10:58:31+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from roocker666 ↑Tue May 09, 2023 10:22 am at Tue May 09, 2023 10:22 am
>
> 
Both games were developed by Sega AM2 but .MDL files are different.

Yes! And both Games got supported by Ninja Developer tose:
Look for yourself 
Kor66 was an arcade Game ported to ps2 though.
So maybe it helps with your compression problem and we have both .mdls figured out
## Post #33
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-09T18:46:02+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from Henchman800 ↑Tue May 09, 2023 6:58 pm at Tue May 09, 2023 6:58 pm
>
> 

Yes! And both Games got supported by Ninja Developer tose:
Look for yourself 
Kor66 was an arcade Game ported to ps2 though.
So maybe it helps with your compression problem and we have both .mdls figured out

OK, I analyzed kor66 files, .MDL is actually a container, it has textures(.P2IG) and meshes(.TMB)
In macross .CMP is the compressed container(unknow compession method by CRITOOL/ROFS), inside has textures .tm2 and meshes .MDL

So meshes from kor66 .TMB is a different format than macross meshes .MDL (yes, analyzed both already).

BTW, You can get kor66 textures with Console Texture Explorer, are similar to tm2 but palette is not at end, it is at the start(after header):



ARI_KAO6.P2IG.jpg (60.69 KiB) Viewed 48 times
## Post #34
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2023-05-10T12:25:09+00:00
- Post Title: Re: Macross PS2 mdl

> Reply from roocker666 ↑Wed May 10, 2023 2:46 am at Wed May 10, 2023 2:46 am
>
> 
BTW, You can get kor66 textures with Console Texture Explorer, are similar to tm2 but palette is not at end, it is at the start(after header):
ARI_KAO6.P2IG.jpg

Wow thanks for sharing!
I will give it a try when im Home next week.
