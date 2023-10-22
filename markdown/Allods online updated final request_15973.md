## Post #1
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2017-03-09T00:24:54+00:00
- Post Title: Allods online updated final request

Hello everyone i wanted to draw attention to this game again altho i know years ago another thread was made.
I am a designer and consider this game a character design marvel however my brain is not made for reverse engineering even tho i tried to follow tutorials on these forums to decode it myself.
Im asking anyone that has looked at this in the past to please give it another look and try to decode the .bins from models and animation for a noesis/blender/whatever else script

What i know so far:
the paks are simple zlib and cant be decompressed with 7-zip or other program.
The model lods are stuck on each other but thats not really a problem for as i am willing to fix them myself in a 3d program
The skyforge .bins which might be similar since its from same company have already been decoded by user Acewell on this thread: /viewtopic.php?f=16&t=13497

Im adding some model and animation .bins below.
Thanks in advance
[AedMale_lowpoly.(Geometry).rar](https://xentaxbackup.github.io/file/12578_AedMale_lowpoly.(Geometry).rar)
## Post #2
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2017-03-09T00:25:39+00:00
- Post Title: Allods online updated final request

Here is the animation file
[Aed_male.Special03.(SkeletalAnimation).rar](https://xentaxbackup.github.io/file/12579_Aed_male.Special03.(SkeletalAnimation).rar)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-09T02:19:23+00:00
- Post Title: Allods online updated final request

for AedMale_lowpoly.(Geometry).bin use offzip

```
offzip -a AedMale_lowpoly.(Geometry).bin c:\offzip\extracted
```


then you can use Hex2obj to get the model



AedMale_lowpoly.(Geometry).bin.png (33 KiB) Viewed 402 times


looks like the LOD mesh is on top of the main mesh again
## Post #4
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2017-03-09T10:02:13+00:00
- Post Title: Allods online updated final request

thanks for the reply! looks like the lod thing is just a bad storing decision by the devs.
i've tried using hex2obj before its a very cool program but still can u create a noesis script?
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-09T05:57:27+00:00
- Post Title: Allods online updated final request

> Reply from AceWell
>
> for AedMale_lowpoly.(Geometry).bin use offzip
instead of using offzip to decompress use this bms script so you can run on entire folders and keep the file names  

```

comtype zlib_noerror
get ZSIZE asize
get NAME basename
get EXT extension
string NAME + "_decomp."
string NAME + EXT
clog NAME 0 ZSIZE ZSIZE

```


> Reply from freakshow
>
> can u create a noesis script?
to make a Noesis python script i would need more than one sample to compare data
## Post #6
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2017-09-07T23:06:14+00:00
- Post Title: Allods online updated final request

For the sake of getting a neosis script for this, here are some creature samples. 
[https://drive.google.com/open?id=0B1wKL ... 3gwLUJsYzA](https://drive.google.com/open?id=0B1wKLwDcg7TcLXFud3gwLUJsYzA)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-13T02:20:39+00:00
- Post Title: Allods online updated final request

okay here try this Noesis python script 
*script updated Jan 10, 2018*


 fmt_AllodsOnline_bin.zip
(949 Bytes) Downloaded 69 times


first you have to decompress the bin files with the bms script i posted earlier  

i will try to work on the texture script next
## Post #8
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2017-09-14T11:37:30+00:00
- Post Title: Allods online updated final request

Edit: Keep in mind I might just be doing something really really stupid. 

After running the files through quickBMS I have encountered one of two errors, the first being contained within the image attached and the second resulting in a Noesis crash with the resulting error code

EXCEPTION_CODE		"c0000005"
EXCEPTION_ADDR		"02a228fe"
EXCEPTION_EIP		        "02a228fe"
[Error 1.PNG](https://xentaxbackup.github.io/file/13310_Error 1.PNG)
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-14T15:45:26+00:00
- Post Title: Allods online updated final request

don't know, you have to upload the decompressed samples that gave the errors for investigation.
## Post #10
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2017-09-14T16:21:21+00:00
- Post Title: Allods online updated final request

Here are all the files I attempted to run through Noesis.

[https://drive.google.com/open?id=0B1wKL ... FpqUHJQYzA](https://drive.google.com/open?id=0B1wKLwDcg7TcWWZyNFpqUHJQYzA)
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-14T20:41:32+00:00
- Post Title: Allods online updated final request

they have different strides than 32 set in the script and i have no way to determine this, could be 24, 28, 32 or 36.
guess you just have to change it on line 29 in the script by hand until a better solution comes around.
## Post #12
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2017-09-16T16:03:47+00:00
- Post Title: Allods online updated final request

New error I've encountered, some files bring up the error. 'OverflowError: Python int too large to convert to C long'

edit - Apart from that this plugin is amazing!
edit edit - line 36, in noepyLoadModel
IBuf = bs.readBytes(FCount*2)
## Post #13
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2017-09-18T10:35:55+00:00
- Post Title: Allods online updated final request

Sorry for double posting, forgot to include a sample that triggered the error.
[Hadagan_Appartament_House.(Geometry)_decomp.bin.zip](https://xentaxbackup.github.io/file/13324_Hadagan_Appartament_House.(Geometry)_decomp.bin.zip)
## Post #14
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2018-01-09T11:52:09+00:00
- Post Title: Allods online updated final request

I hope this won't get me banned but is there any chance someone could look at this again?
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-10T01:00:57+00:00
- Post Title: Allods online updated final request

edit
okay i made a final attempt to autodetect the stride and to only read the first LOD so no need to separate mesh any more.   
i updated the script in this post
[viewtopic.php?p=133751#p133751](http://forum.xentax.com/viewtopic.php?p=133751#p133751)
## Post #16
- Username: TheLifeweaver
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 13, 2016 5:54 am
- Post datetime: 2018-01-10T11:51:13+00:00
- Post Title: Re: Allods online updated final request

I'd like to thank you for giving it another go and from what I can tell its unlocked a number of new models, however a significant number generate a line 48 failed to acquire buffer bytes errors. I'll post a sample but I have the feeling I've pushed my luck with this.

Damn Allods Team.
[OgreCannon.(Geometry)_decomp.bin.zip](https://xentaxbackup.github.io/file/13775_OgreCannon.(Geometry)_decomp.bin.zip)
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-10T20:35:03+00:00
- Post Title: Re: Allods online updated final request

> Reply from TheLifeweaver
>
> I'll post a sample but I have the feeling I've pushed my luck with this.
yep, at this point you'll have to edit the script by hand, any change i make to it will break it for the majority of samples.
for your sample change line 39 from this

```
    myIndex = myString.find(b'\x00\x00\x01\x00\x02\x00') 
```

to this

```
    myIndex = myString.find(b'\x00\x00\x01\x00') 
```

because the first pattern does not exist in that file   
i could remove that part of the script that tries to draw only the main LOD instead of all, 
but you will have to go back to removing overlapping geometry again.
## Post #18
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-28T03:43:24+00:00
- Post Title: Re: Allods online updated final request

Helloo, anyone still here trying to get the models from this game? here are some examples..


[https://www.mediafire.com/file/hutt46jt ... 9.bin/file](https://www.mediafire.com/file/hutt46jtag91973/Axe_2H_D_16_PowerOrc.%2528Geometry%2529.bin/file)

[https://www.mediafire.com/file/87gkjrdt ... 9.bin/file](https://www.mediafire.com/file/87gkjrdtrm871bk/EngineerGun_PowerPraiden.%2528Geometry%2529.bin/file)
## Post #19
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-28T16:46:34+00:00
- Post Title: Re: Allods online updated final request

Hello again! seems like are some .bin files that had two or more meshes in the same geometry.bin file, that's why it shows error, is any way to separate the meshes and uv maps in these case? because uv + meshes looks so messy. Thanks

[https://www.mediafire.com/file/mkp8f943 ... in.7z/file](https://www.mediafire.com/file/mkp8f9432j0cp5v/MountCar.%2528Geometry%2529.bin.7z/file)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T19:20:18+00:00
- Post Title: Re: Allods online updated final request

> Reply from moonpaladin ↑Thu Jan 28, 2021 11:43 am at Thu Jan 28, 2021 11:43 am
>
> 
Helloo, anyone still here trying to get the models from this game? here are some examples..
https://www.mediafire.com/file/hutt46jt ... 9.bin/fileThe Axe's first mesh is simple to get using hex2obj (view link in my sig) while the script seems to look for a lower LOD.
.



Axe_2H_D_16_PowerOrc.png (104.6 KiB) Viewed 90 times
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T19:34:22+00:00
- Post Title: Re: Allods online updated final request

MountCar.png (147.35 KiB) Viewed 88 times
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T19:53:14+00:00
- Post Title: Re: Allods online updated final request

I didn't check how to properly divide up into sub meshes:
.



submeshes-how.png (106.93 KiB) Viewed 87 times


(There's also lots of doubles which may need to be handled before.)
## Post #23
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-28T20:03:17+00:00
- Post Title: Re: Allods online updated final request

It's certainly an odd format.  While it's easy to get the data for the vertices, UVs and faces, there doesn't seem to be anything obvious referring to the actual mesh parts.  In the case of the MountCar file, there are several tables after the face data, each with 0x44 entries - I can see tables for what looks like bone names, bone name offsets, bone data, possible bone map, and another table mostly consisting of floats.

Is it possible there's some sort of companion file with extra information in?
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T21:04:47+00:00
- Post Title: Re: Allods online updated final request

Maybe you can make some grouping using a byte in the FVFblock:

   43e8:  1.404180 1.819670 0.236610  0.346654 0.476176 85 F2 48 FF  FF 00 00 00  39 255 255 255 
   4408:  1.245370 2.008840 0.859255  0.855578 0.430977 53 23 34 FF  FF 00 00 00  3 255 255 255 544

   50e8:  1.389930 -1.013220 0.811186  0.800173 0.428872 14 3E 6B FF  FF 00 00 00  3 255 255 255 
   5108:  1.587730 -1.342230 0.132218  0.322254 0.475328 68 AF 0C FF  FF 00 00 00  0 255 255 255 648

   54e8:  1.541570 -1.193150 0.202857  0.346654 0.476176 85 F2 48 FF  FF 00 00 00  0 255 255 255 
   5508:  1.426860 -0.851314 0.435501  0.282457 0.403209 0C 7F B6 FF  FF 00 00 00  3 255 255 255 680

   9b28:  0.224665 2.833090 1.714700  0.045335 0.982854 80 AC F7 FF  FF 00 00 00  3 255 255 255 
   9b48:  0.146531 0.772728 2.593010  0.309990 0.976342 F0 62 4C FF  FF 00 00 00  6 255 255 255 1242

   a548:  -0.085373 0.458653 2.491380  0.790059 0.232928 80 00 78 FF  FF 00 00 00  6 255 255 255 
   a568:  -0.266773 0.961993 3.015780  0.690360 0.330258 7F FF 80 FF  FF 00 00 00  30 255 255 255 1323
   f8e8:  -0.208150 1.265330 2.953150  0.660827 0.211892 5B 80 05 FF  FF 00 00 00  30 255 255 255 
   f908:  -0.633336 0.650284 2.545980  0.735946 0.445295 FF 80 7F FF  FF 00 00 00  3 255 255 255 1992

Group "30" looks promising (face indices 1323 up to 1991, maybe more):
.



Group30.png (19.97 KiB) Viewed 83 times



Needs further checks.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T21:11:57+00:00
- Post Title: Re: Allods online updated final request

well, not so bad (but group3 has several parts, biggest here):
.



group3.png (48.04 KiB) Viewed 82 times


   f908:  -0.633336 0.650284 2.545980  0.735946 0.445295 FF 80 7F FF  FF 00 00 00  3 255 255 255 1992

  1c108:  -1.215630 0.928266 0.254375  0.047319 0.278180 6A 93 03 FF  FF 00 00 00  3 255 255 255 
  1c128:  -1.305700 1.408490 1.460090  0.591820 0.983158 80 7F 00 FF  FF 00 00 00  24 255 255 255 3593

(face indices 1992 up to 3592)
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T21:31:17+00:00
- Post Title: Re: Allods online updated final request

Here's the index/group list (so for creating an obj file you'll have to backup this into an array instead of continuous writing of faces in case you want to join "sub groups" otherwise there would be 347 sub meshes):


 MountCar_groups.zip
(1.31 KiB) Downloaded 13 times
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-28T23:23:46+00:00
- Post Title: Re: Allods online updated final request

Left part of pic shows group3, consists of 107 submeshes:
.



Group3_all.jpg (129.84 KiB) Viewed 78 times
## Post #28
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-29T04:29:00+00:00
- Post Title: Re: Allods online updated final request

wow!Thanks Shakotay. Yes, I assume that they use a list to activate certain geosets of the model and thus form a mount, and then other geosets for another, the problem is to export the mesh with its indices and thus group them and form the exact models of the mounts, although I see that you have been able to achieve it in a certain way, I'll be reviewing it! If you ever get a way to divide them by their indices, that would be great! that game has many good models! I'm gonna try to get more of these kind of models.

[https://www.mediafire.com/file/r1h650l1 ... 9.bin/file](https://www.mediafire.com/file/r1h650l13mkcibe/MountChopperCar.%2528Geometry%2529.bin/file)
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-29T08:29:54+00:00
- Post Title: Re: Allods online updated final request

Here's the wavefront obj file (no normals):
[MountChopperCar.(Geometry)_decomp_0.zip](http://www.uploadmb.com/dw.php?id=1611908738)
-----
Here is the H2O file for hex2obj (copy 6 lines into a txt file and name it MountChopperCar.H2O, load decompressed bin, then the H2O file, press 'mesh' button to display; use File\SaveAs mesh to create obj file).

0x75370 101559
Vb1
32 12
0x8 14907
020000
0x0 255

(There will be autocreated submeshes (every 500 faces), though. So better use the obj from the zip.)
Maximum vertex count is 15003, so there's 96 verts left.
.



MotorChopper.png (188.57 KiB) Viewed 67 times
## Post #30
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-29T16:42:37+00:00
- Post Title: Re: Allods online updated final request

Thanks alot Shakotay!
## Post #31
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-31T18:10:24+00:00
- Post Title: Re: Allods online updated final request

Shakotayyyyyyy! I was trying to find a way to separate the meshes and I found a file that will help alot with that step its called .xdb file it content more data about the geometry and textures!I'm attaching a file, please if you got it working, tell me some steps to make it working too! I'm trying to get some mounts that I really love u.u

[https://www.mediafire.com/file/2ykan3wd ... no.7z/file](https://www.mediafire.com/file/2ykan3wd57okh5k/MountDino.7z/file)
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-31T19:38:37+00:00
- Post Title: Re: Allods online updated final request

> Reply from moonpaladin ↑Mon Feb 01, 2021 2:10 am at Mon Feb 01, 2021 2:10 am
>
> 
Shakotayyyyyyy! I was trying to find a way to separate the meshes and I found a file that will help alot with that step its called .xdb file
Well, more confusion than help for me:

```
        <Item>
            <lods>
                <Item>
                    <indexBufferBegin>0</indexBufferBegin>
                    <indexBufferEnd>8040</indexBufferEnd>
                    <vertexBufferBegin>0</vertexBufferBegin>
                    <vertexBufferEnd>2072</vertexBufferEnd>
                </Item>
                <Item>
                    <indexBufferBegin>68757</indexBufferBegin>
                    <indexBufferEnd>74145</indexBufferEnd>
                    <vertexBufferBegin>0</vertexBufferBegin>
                    <vertexBufferEnd>2072</vertexBufferEnd>
                </Item>
                <Item>
                    <indexBufferBegin>74145</indexBufferBegin>
                    <indexBufferEnd>77499</indexBufferEnd>
                    <vertexBufferBegin>0</vertexBufferBegin>
                    <vertexBufferEnd>2074</vertexBufferEnd>
                </Item>
            </lods>

```


> , tell me some steps to make it working too!
file offset 0x0004 (4 bytes before start of vertices at 0x0008)
A8 23 0A 00 -> 0x0A23A8: 664488, size of vertex block

FVFsize 36 (for other models: if it doesn't fit try 28 or 32)

vertex count: 18458 (664488/36)

Enter the params (see pic below), toggle button 'noPtC' to 'PtCld',
press 'mesh' button

At the bottom of the left hand list box find next address: 0xa23b0

edit: now update the params as follows, then toggle button 'PtCld' back to 'noPtC'

Find  "size of face indices block" (DWORD) at 0xa23b4: 36 1D 04 00
0x41D36, decimal: 269622

face index count: 269622/2= 134811
start of face indices: 0xa23b8 (enter address without the '0x')
.



MountDino.png (193.03 KiB) Viewed 148 times



There's 4 submeshes, afaics.

(You need to be a coder to separate them into smaller pieces.)
## Post #33
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-31T20:58:07+00:00
- Post Title: Re: Allods online updated final request

Thanks for the fast response Shakotay! I just try with the the parameter that you used loading the decompress bin model, and got this :C



dino_error.png (51.24 KiB) Viewed 137 times
## Post #34
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-31T22:18:27+00:00
- Post Title: Re: Allods online updated final request

I'm trying with other mount and got the same model, only vertices xD. 



mount_ho.png (69.09 KiB) Viewed 131 times
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-31T22:27:34+00:00
- Post Title: Re: Allods online updated final request

ehm, yeah, read my post completely!  

> face index count: 269622/2= 134811
>
> start of face indices: 0xa23b8

Has to be applied, of course (thought this being obvious  )
Then switch to 'noPtC'.

edit: well, this was the misleading part in my previous post, sorry
"Enter the params (see pic below), toggle button 'noPtC' to 'PtCld',"
## Post #36
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-01-31T22:50:16+00:00
- Post Title: Re: Allods online updated final request

hahaha yeah! was my mistake ! thanks Shakotay!!
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-01T07:21:28+00:00
- Post Title: Re: Allods online updated final request

You can use a whatever face index count but it must be < calculated face index count (see my post somewhere above).

But you can't set the vertex count independently! Because there's a relationship: the maximum face index (FI) equals the vertex count.
Max FI is calculated and displayed in the lower left listbox when pressing the go1 button.
(See the tutorial (tut button))

(The maximum face index is not the same as the face index count, btw.)
## Post #38
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-02-01T14:40:33+00:00
- Post Title: Re: Allods online updated final request

Yeah, I'm still practicing but got the mount!!!!!love you hahaha
## Post #39
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-02-02T07:51:13+00:00
- Post Title: Re: Allods online updated final request

Sorry for so many posts :c
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-02T08:51:56+00:00
- Post Title: Re: Allods online updated final request

well, sometimes a further step is required: press the go1 button when you have entered your params.
at the bottom of the left lower listbox you'll find the max face index: 37773 (MountBeetle). Use it as the vertex count for step 3

Is different from the calculated (overall) vertex count here.
--------------------

For the 2nd mesh of the Hoverboard we didn't get the face indices so far:
(maybe this time the .xdb file could come in handy?)
.



Hoverboard_sails.png (34.6 KiB) Viewed 78 times
## Post #41
- Username: Cyn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 03, 2022 11:12 am
- Post datetime: 2022-11-04T13:36:36+00:00
- Post Title: Re: Allods online updated final request

Raising this thread from the dead, sorry

Working on exports using the BMS script and Noesis plug-in provided in earlier posts. Personally, i work a lot with wow .m2 format, so these files arent too out of my realm of understanding. I can see how the LOD detection works in each file and ive noticed that changing small bytes and chunks of data to match the expected search of "00 00 01 00 02 00" resulting in the destruction of error #48 and a nice render produced. Im getting to a spot where i can reliably extract whatever model it is that im looking for.

Apparently we used to have a texture viewer for Allods but i dont see it working anymore. Anyone have any info on how we can get these textures decompressed? Ive been able to "fix" or extract the following models:
MountCar
MountCarCabrio
MountChopper
MountChopperAtoll
MountChopperGreen
MountChopperDead
MountCopter
MountChariot
Each separate piece of the v14 exoskeleton

If more work will be done on the file format, id be happy to explore building a 010 template for the .bin (geometry) files


This is my first post here, thank you for being a community before i arrived here


EDIT: Using texture finder i can see some of the texture in DXTC3 format, got it extracted using 256 width and 8 byte offset produced the most detailed image in TF 2.0

Notes:
-The first 8 bytes of the file are a pointer to the offset of the first LOD, At that offset (by 8 bytes) is the pointer for whatever section is next (presumably the second LOD)
-At the location of this pointer seems to be an 4 byte identifier for the mesh (usually just 1) followed by a 4 byte bit-by-bit length of the indices section (usually in raw byte form) these two pieces of information should give us reliable meshes produce via the noesis script
