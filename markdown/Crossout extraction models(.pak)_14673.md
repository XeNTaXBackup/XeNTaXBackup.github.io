## Post #1
- Username: Panasonic
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 21, 2016 12:56 am
- Post datetime: 2016-07-22T20:51:51+00:00
- Post Title: Crossout extraction models(.pak)

Hi.
This site (zenhax.com) helped extract from .pak, files such as: mdl-msh000, tfd and others. Need help to convert them in a convenient format(.obj)


A folder with the files after extraction:
[https://yadi.sk/d/ILSWawMxtYdqT](https://yadi.sk/d/ILSWawMxtYdqT)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-22T21:18:56+00:00
- Post Title: Crossout extraction models(.pak)

uvs are a little bit funny - have to be zoomed. (Dunno why where so much empty space between the parts.)



mustang-mdl-msh000.jpg (199.6 KiB) Viewed 796 times
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-22T21:40:08+00:00
- Post Title: Crossout extraction models(.pak)

shakotay beat me to it   

0x08 - vertex stride
0x0c - number of vertices
0x10 - number of face indices

textures are dds and are in some kind of headerless uncompressed tfd archive
i guess the archive index is in the tfh file
## Post #4
- Username: Panasonic
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 21, 2016 12:56 am
- Post datetime: 2016-07-23T18:21:41+00:00
- Post Title: Crossout extraction models(.pak)

I'm stupid to figure it out  thanks for the help
## Post #5
- Username: Panasonic
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 21, 2016 12:56 am
- Post datetime: 2016-07-24T10:01:40+00:00
- Post Title: Crossout extraction models(.pak)

I can not find value: startaddr 0x(step 1)
[engine_v8_epic.rar](https://xentaxbackup.github.io/file/11352_engine_v8_epic.rar)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-24T11:12:14+00:00
- Post Title: Crossout extraction models(.pak)

here you go  



engine_v8_epic.mdl-msh000.png (61.47 KiB) Viewed 817 times
## Post #7
- Username: Panasonic
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 21, 2016 12:56 am
- Post datetime: 2016-07-24T11:15:25+00:00
- Post Title: Crossout extraction models(.pak)

how do you get this value? I do not understand
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-24T12:15:12+00:00
- Post Title: Crossout extraction models(.pak)

experience with pattern recognition, but sometimes the offset are given to you and sometimes are not.
when they are not you just have to trace where the patterns start and end.
To find the vertex block start address i usually set the column width in the hex editor the same as the vertex stride
and the face indices are easier to find because just like the tutorial says, 
they look like a scrambled alphabet then you just trace it back to where it doesn't look like that and test it
## Post #9
- Username: Panasonic
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 21, 2016 12:56 am
- Post datetime: 2016-07-24T13:06:20+00:00
- Post Title: Crossout extraction models(.pak)

AceWell, Thank you very much! Thank you guys  How to get UVs? Textures wrong lie.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-25T14:25:13+00:00
- Post Title: Crossout extraction models(.pak)

All you have to do is enter the numbers you see in the image then go to "File > SaveAs mesh" 
to save the mesh with UVs. Then you import the mesh into your favorite 3d software,
you may need to flip the mesh normals so they point out and you might need to flip the UVs vertical or may
even need to scale them up or down so they line up with the image. 
i don't know for sure because there were no texture samples to check
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-03T03:27:15+00:00
- Post Title: Crossout extraction models(.pak)

i made a Noesis python script to open your mdl-msh000 model samples  
*script updated April 3, 2018*


 fmt_Crossout_mdl-msh000.zip
(873 Bytes) Downloaded 109 times
## Post #12
- Username: Turbozis
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 21, 2017 4:20 am
- Post datetime: 2017-09-20T21:29:29+00:00
- Post Title: Crossout extraction models(.pak)

> Reply from AceWell
>
> i made a Noesis python script to open your mdl-msh000 model samples  
fmt_Crossout_mdl-msh000.zip
Recieving an error while trying to use it

```
  File "C:\Users\user\Desktop\noesisv4293\plugins\python\fmt_Crossout_mdl-msh000.py", line 22, in noepyLoadModel
    VBuf = bs.readBytes(VCount * VBytes)
  File "C:\Users\user\Desktop\noesisv4293\plugins\python\inc_noesis.py", line 125, in readBytes
    return noesis.bsReadBytes(self.h, numBytes)
OverflowError: Python int too large to convert to C long

```
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-09-21T17:56:33+00:00
- Post Title: Crossout extraction models(.pak)

You can use the 3D Object Converter (Windows) or i3DConverter (macOS) to open these files also.
## Post #14
- Username: Turbozis
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 21, 2017 4:20 am
- Post datetime: 2017-09-22T06:27:42+00:00
- Post Title: Crossout extraction models(.pak)

> Reply from Karpati
>
> You can use the 3D Object Converter (Windows) or i3DConverter (macOS) to open these files also.
Either I'm stupid or this doesn't seem to work
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-09-22T13:52:17+00:00
- Post Title: Crossout extraction models(.pak)

> Reply from Turbozis
>
> Either I'm stupid or this doesn't seem to work

It works fine. Just open the *.mdl-msh000 file.
[mustang.jpg](https://xentaxbackup.github.io/file/13335_mustang.jpg)
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-09-22T13:53:11+00:00
- Post Title: Re: Crossout extraction models(.pak)

I attached the original and the converted file.
[mustang.zip](https://xentaxbackup.github.io/file/13336_mustang.zip)
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-22T20:59:01+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from Turbozis
>
> Recieving an error while trying to use it
you must upload not working sample, no samples no party, and as always no promises
## Post #18
- Username: HugeButt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 14, 2017 1:01 am
- Post datetime: 2017-10-03T18:27:23+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from AceWell
>
> Turbozis wrote:Recieving an error while trying to use it
you must upload not working sample, no samples no party, and as always no promises

They, actually, changed something in models somewhere near open beta ~june this year. Here's same mustang model, but from recent build, since Turbozis got lost.
Had no luck with geting anything worth out of it with hex2obj (because i'm the arse-handed one, I guess).
[mustang.zip](https://xentaxbackup.github.io/file/13382_mustang.zip)
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-04T01:23:00+00:00
- Post Title: Re: Crossout extraction models(.pak)

normals looked flipped, but need more samples to write a new script  



mustang.mdl-msh000.png (46.14 KiB) Viewed 394 times



edit
i'd like to see more *.tfh and *.tfd texture sample pairs too so i can make a texture script for Noesis.
## Post #20
- Username: HugeButt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 14, 2017 1:01 am
- Post datetime: 2017-10-04T05:51:49+00:00
- Post Title: Re: Crossout extraction models(.pak)

[More models with textures.](https://mega.nz/#!t2I2SK7Y!mDfIgLw6A64Bb0l3H_mYMnYORwNW1yIQ35a3SLRJBZA). It got quiet bigger than maximum filesize.
## Post #21
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-04T16:38:35+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from HugeButt
>
> More models with textures.. It got quiet bigger than maximum filesize.

The new format has a different header.
[chevy_pickup.zip](https://xentaxbackup.github.io/file/13388_chevy_pickup.zip)
## Post #22
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-06T18:15:46+00:00
- Post Title: Re: Crossout extraction models(.pak)

I added a new Hammer Engine (Crossout, Star Conflict) .MDL-MSH*/MDF loader module to my program to support the new .MDL-MSH* format.
I released the 3D Object Converter v6.518 as a web update now, so just use the Help/Check for updates... function to get it.
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-08T22:28:43+00:00
- Post Title: Re: Crossout extraction models(.pak)

here is Noesis python texture script to open your *.tfh/*.tfd sample pairs   
*script updated Jan 11, 2018*


 tex_Crossout_tfh_tfd.zip
(855 Bytes) Downloaded 119 times


supports dxt1, dxt5 and rgba32
you must have the tfh and tfd file in same location so the script can find everything.
## Post #24
- Username: armobil
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 20, 2017 12:08 am
- Post datetime: 2017-10-17T18:32:28+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from Karpati
>
> I released the 3D Object Converter v6.518 as a web update now, so just use the Help/Check for updates... function to get it.

This does not work for all models, in some errors a "bad polygons"
[scntst_drone.rar](https://xentaxbackup.github.io/file/13452_scntst_drone.rar)
## Post #25
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-17T18:51:50+00:00
- Post Title: Re: Crossout extraction models(.pak)

This model has another vertex format.
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-18T07:29:47+00:00
- Post Title: Re: Crossout extraction models(.pak)

i updated the Noesis python script so it opens both the old and new samples in this thread here   
[viewtopic.php?p=121063#p121063](http://forum.xentax.com/viewtopic.php?p=121063#p121063)

edit
the next update might be to combine it with the texture script so it loads the diffuse texture and displays it in viewport
## Post #27
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-18T18:07:13+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from armobil
>
> Karpati wrote:This does not work for all models, in some errors a "bad polygons"

I modified the loader module to handle the vertex format value in the new format.
I released the 3D Object Converter v6.519 as a web update now, so just use the Help/Check for updates... function to get it.

I will release the modified macOS and Linux versions later.
## Post #28
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2017-11-13T05:43:14+00:00
- Post Title: Re: Crossout extraction models(.pak)

Hi, I unpacked and converted models, but I am stupid and could not normally convert textures. 
How can I do that?
## Post #29
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2017-12-14T20:55:20+00:00
- Post Title: Re: Crossout extraction models(.pak)

Noesis scripts don't work for me:
mdl-msh script gives "TypeError: an integer is required" error.

Texture script gives this: 

```
0xa :imgFmt
E:\gamedata_XO\gamedata_060_1606\ui\textures\logo.tfd tfd file
0x0 :mainMipOffset
0x32000 :datasize
Traceback (most recent call last):
  File "F:\noesisv4279\plugins\python\tex_Crossout_tfh_tfd.py", line 42, in noepyLoadRGBA
    print(imgWidth, "x", imgHeight)
UnboundLocalError: local variable 'imgWidth' referenced before assignment
```


And does anyone have ideas how to open Crossout compiled lua scripts?
## Post #30
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-14T22:10:16+00:00
- Post Title: Re: Crossout extraction models(.pak)

you have to upload the not working samples so i can modify scripts.
## Post #31
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2017-12-15T16:33:38+00:00
- Post Title: Re: Crossout extraction models(.pak)

[http://www.mediafire.com/file/md8gvapa4 ... ut_smpl.7z](http://www.mediafire.com/file/md8gvapa405i9gp/crossout_smpl.7z)

I know that texture is DTX5 (I opened it with Texture Finder and partially exported), but probably it's bigger than 2k and not square.
About model script - I tried models from latest client and it worked. Looks like it doesn't work with models from 0.6. However, 3D Object Converter opens them correctly.
## Post #32
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-15T20:08:50+00:00
- Post Title: Re: Crossout extraction models(.pak)

thanks! i have updated the Noesis python texture script here   
[viewtopic.php?p=134377#p134377](http://forum.xentax.com/viewtopic.php?p=134377#p134377)

edit

> Reply from Gazyi
>
>  Looks like it doesn't work with models from 0.6.
then you will need to provide me some of these "0.6" models. 
all samples i have are working with the Noesis python script.
## Post #33
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2017-12-16T11:23:13+00:00
- Post Title: Re: Crossout extraction models(.pak)

Thanks, now it works with most textures, but some still has problems - some with pixel messed, some give "WARNING: Not enough texture data for specified image type!" -can't be previewed or exported, and some use BGRA888.
Sorry, looks like I put mesh from latest version. 
New archive - sample textures with problems (smpl.txt contains resolutions and image formats at which TextureFinder gives best results for each texture sample) and 0.6.0 mesh.
[http://www.mediafire.com/file/c4jqv73ia ... x_smpl.rar](http://www.mediafire.com/file/c4jqv73iatdeyjk/060+tex_smpl.rar)
## Post #34
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-17T03:57:36+00:00
- Post Title: Re: Crossout extraction models(.pak)

okay i updated the Noesis python texture script here   
[viewtopic.php?f=16&t=14673&p=134377#p134377](http://forum.xentax.com/viewtopic.php?f=16&t=14673&p=134377#p134377)

and i updated the Noesis python model script here   
[viewtopic.php?f=16&t=14673&p=121063#p121063](http://forum.xentax.com/viewtopic.php?f=16&t=14673&p=121063#p121063)

both should be good now, or at least until another file version emerges.
## Post #35
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2017-12-17T09:55:10+00:00
- Post Title: Re: Crossout extraction models(.pak)

Thank you.
## Post #36
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-17T22:49:52+00:00
- Post Title: Re: Crossout extraction models(.pak)

i just fixed a couple of mistakes i made in the texture script that affected the rgba sample colors, 
this is now fixed so please redownload from here  
[viewtopic.php?p=134377#p134377](http://forum.xentax.com/viewtopic.php?p=134377#p134377)
and now it finally should be good
## Post #37
- Username: knifers
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 09, 2018 1:05 am
- Post datetime: 2018-01-08T23:06:14+00:00
- Post Title: Re: Crossout extraction models(.pak)

Thanks for work  

Sory for beg but on tfh files

```
UnboundLocalError: local variable 'imgHeight' referenced before assignment
```


Samples for 0.8.45
[http://www20.zippyshare.com/v/Pm3PoOKe/file.html](http://www20.zippyshare.com/v/Pm3PoOKe/file.html)

for samples from 0.6 all working fine
## Post #38
- Username: ThunderFlame
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 09, 2018 4:02 am
- Post datetime: 2018-01-09T09:30:55+00:00
- Post Title: Re: Crossout extraction models(.pak)

It seems as if the script shows the tfh files but not the tfds, I suppose you need both of them in order to view the texture, and then wrap said texture around the models.
## Post #39
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-10T07:28:46+00:00
- Post Title: Re: Crossout extraction models(.pak)

looks like they changed some bytes/bits in the tfh header, will look at it later, in the meantime 
you can use TextureFinder to convert the texure data from the tfd files if you are in a hurry.
## Post #40
- Username: knifers
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 09, 2018 1:05 am
- Post datetime: 2018-01-10T19:48:12+00:00
- Post Title: Re: Crossout extraction models(.pak)

TF work well but I can't export big textures in one bitmap at once if they don't fit all in preview window (or I'm doing something wrong), also some textures are cut.
## Post #41
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-11T07:24:21+00:00
- Post Title: Re: Crossout extraction models(.pak)

okay they changed quite a bit in the header and the offset table is now filled with bogus info 
so i made this temporary script to open all your newest samples until i get a better look 

*temporary script removed, see this post [viewtopic.php?p=134377#p134377](http://forum.xentax.com/viewtopic.php?p=134377#p134377) *

i don't see a way to track versions yet so for now the scripts will stay separate.  
you will have to disable the other when you want to use this and vice versa.
## Post #42
- Username: knifers
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 09, 2018 1:05 am
- Post datetime: 2018-01-11T14:15:20+00:00
- Post Title: Re: Crossout extraction models(.pak)

Thanks, but my bad   Looks like not all textiures are same.

In "samples2" pack "avatars" working well but on others

```
UnboundLocalError: local variable 'datasize' referenced before assignment
```


Also, same on "cityruin2" pack, additionally in TF it looks cut off

Samples2
[http://www106.zippyshare.com/v/Hl0FVXcq/file.html](http://www106.zippyshare.com/v/Hl0FVXcq/file.html)

Cityruin2
[http://www37.zippyshare.com/v/DRJEJQ3t/file.html](http://www37.zippyshare.com/v/DRJEJQ3t/file.html)
## Post #43
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-11T21:29:57+00:00
- Post Title: Re: Crossout extraction models(.pak)

okay i updated the script here   
[viewtopic.php?p=134377#p134377](http://forum.xentax.com/viewtopic.php?p=134377#p134377)
it opens all tfh/tfd samples in this thread except 4 (mask images) which you likely have no use for anyway,
but i will look at those some other day.
## Post #44
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2018-01-12T04:06:30+00:00
- Post Title: Re: Crossout extraction models(.pak)

It WORKS!
## Post #45
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2018-01-12T04:32:42+00:00
- Post Title: Re: Crossout extraction models(.pak)

[https://skfb.ly/6vJQW](https://skfb.ly/6vJQW)
## Post #46
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2018-04-03T22:21:45+00:00
- Post Title: Re: Crossout extraction models(.pak)

Sorry to bother again, but looks like header files of textures were updated. Noesis don't cut mipmaps and most textures are shifted.
Brief hex diff showed that only textures file headers were updated.
Samples of both 0.6.0 and 0.9.40 textures: [http://www.mediafire.com/file/2hana136d ... amples.rar](http://www.mediafire.com/file/2hana136d93lmge/xo_texturesamples.rar)

And it would be useful to load other mdl-msh than 000, because some of them contains different meshes.
Samples: [http://www.mediafire.com/file/ptn6g17gf ... amples.rar](http://www.mediafire.com/file/ptn6g17gf0gzyzd/fullsamples.rar)

I tried Star Conflict scripts - they didn't work with them.
## Post #47
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-04T03:08:45+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from Gazyi
>
> And it would be useful to load other mdl-msh than 000, because some of them contains different meshes.
model script updated here to open more (000-009)
[viewtopic.php?p=121063#p121063](http://forum.xentax.com/viewtopic.php?p=121063#p121063)

and here is a new Noesis python texture script for this new version (0.9.40)
*script updated April 5, 2018*


 tex_Crossout_v940_tfh_tfd.zip
(890 Bytes) Downloaded 89 times


i didn't want to break the previous script, so i will do this for new versions from here on.
this script will conflict other *.tfh scripts so move them out of python folder while using this one.
## Post #48
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2018-04-05T17:52:40+00:00
- Post Title: Re: Crossout extraction models(.pak)

Thank you for fast response, but now most textures gives error:

```
  File "F:\noesisv4296\plugins\python\tex_Crossout_v940_tfh_tfd.py", line 57, in noepyLoadRGBA
    bs2.seek(mainMipOffset, NOESEEK_ABS)        
  File "F:\noesisv4296\plugins\python\inc_noesis.py", line 165, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "F:\noesisv4296\plugins\python\inc_noesis.py", line 161, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "F:\noesisv4296\plugins\python\inc_noesis.py", line 78, in setOffset
    noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size. (690258959 > 2795520)
```


```
  File "F:\noesisv4296\plugins\python\tex_Crossout_v940_tfh_tfd.py", line 57, in noepyLoadRGBA
    bs2.seek(mainMipOffset, NOESEEK_ABS)        
  File "F:\noesisv4296\plugins\python\inc_noesis.py", line 165, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "F:\noesisv4296\plugins\python\inc_noesis.py", line 161, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "F:\noesisv4296\plugins\python\inc_noesis.py", line 78, in setOffset
    noesis.bsSetOfs(self.h, ofs)
OverflowError: Python int too large to convert to C long
```


Problematic samples: [http://www.mediafire.com/file/ljib4bakg ... cabins.rar](http://www.mediafire.com/file/ljib4bakgiwaq51/0940cabins.rar)
## Post #49
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-05T22:39:00+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from Gazyi
>
> Thank you for fast response, but now most textures gives error:
Problematic samples: http://www.mediafire.com/file/ljib4bakg ... cabins.rar
v094 texture script fixed   
[viewtopic.php?p=139337#p139337](http://forum.xentax.com/viewtopic.php?p=139337#p139337)
## Post #50
- Username: Anonsarah2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 18, 2018 8:15 am
- Post datetime: 2018-06-18T02:08:01+00:00
- Post Title: Re: Crossout extraction models(.pak)

I'm getting another error with the latest script, might be something on my end with the avatars.tfh & tfc's, perhaps was updated? 

Can send samples if youd like
## Post #51
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-06-19T03:41:49+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from Anonsarah2
>
> I'm getting another error with the latest script ... perhaps was updated?
likely, what is the game version?
you can upload some samples but i don't know if i will keep updating this script every time there is update .
## Post #52
- Username: Anonsarah2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 18, 2018 8:15 am
- Post datetime: 2018-06-19T23:29:51+00:00
- Post Title: Re: Crossout extraction models(.pak)

Ver is currently 0.9.80, uploaded both files

Can understand is bit of a bother to update the script with the game, so big thanks if you're still up to it these days 

[https://nofile.io/f/PvdbnPbH6sg/avatars.zip](https://nofile.io/f/PvdbnPbH6sg/avatars.zip)
## Post #53
- Username: knifers
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 09, 2018 1:05 am
- Post datetime: 2018-11-01T22:08:54+00:00
- Post Title: Re: Crossout extraction models(.pak)

They already change archives from pak to grp and pk2
## Post #54
- Username: Persival
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 06, 2018 10:14 am
- Post datetime: 2018-12-02T12:46:32+00:00
- Post Title: Re: Crossout extraction models(.pak)

> Reply from knifers
>
> They already change archives from pak to grp and pk2

- Yeap, PAK file replaced by GRP files, someone say that open it nearly impossible. So any new textures, models and assets become non-extractable from game files. It's really sad if there no chance to have in-game models for some close view.
## Post #55
- Username: TheInfinityUser
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 2:45 pm
- Post datetime: 2021-05-01T08:54:36+00:00
- Post Title: Re: Crossout extraction models(.pak)

A while later, I'd also like to decompile the models and textures, but there is only one mdl file now instead of three among others. The mdl file appears to be a tcf model. I'd also like to know how to open the other files.
## Post #56
- Username: someoneohyea
- Rank: n00b
- Number of posts: 13
- Joined date: Tue May 04, 2021 6:58 pm
- Post datetime: 2021-05-04T14:06:06+00:00
- Post Title: Re: Crossout extraction models(.pak)

C:\Users\User\Desktop\texturesUNP\ns\plugins\python\tex_Crossout_v940_tfh_tfd.py
Traceback (most recent call last):
  File "C:\Users\User\Desktop\texturesUNP\ns\plugins\python\tex_Crossout_v940_tfh_tfd.py", line 1, in <module>
    from inc_noesis import *
  File "C:\Users\User\Desktop\texturesUNP\ns\plugins\python\inc_noesis.py", line 7, in <module>
    import noesis
ModuleNotFoundError: No module named 'noesis'

how could that happen?
