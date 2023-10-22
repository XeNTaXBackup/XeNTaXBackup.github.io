## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-14T05:04:07+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

[This files](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/dx_ripper_black_ninja/meshes.7z) are result of "dx ripper's" work (usually bunch of a .rip files) + textures. So
here is [source code](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/dx_ripper_black_ninja/rip_src.7z) for "dx ripper", description of a .rip format is in outtypes.h i suppose
here is [milkshape plugin](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/dx_ripper_black_ninja/dxrip_v130_ms_plugin.zip) for .rip files (can't load many files at a time, though)

can somebody make maxscript or/and noesis plugin? 'cause milkshape can't load many files at a time

i can provide with all necessary information, also i'll try to get .rip format description if outtypes.h is not enough

[ripper's page](http://www.blackninja2000.narod.ru/rus/directx_ripper.html)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-14T08:41:52+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

New ripping tools always bring a smile to my face!   I think it would be cool to expand the functionality of Noesis with DirectX ripping tools too.
What version of Milkshape is that plugin designed for? The plugin functions but i couldn't get it to import any of your samples. I'm using version 1.8.5.

EDIT: I finally got the plugin to import the files. You only have to enter the number behind the mesh prefix and not the entire file name.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-14T08:47:20+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

> Reply from AceWell
>
> New ripping tools always bring a smile to my face!   I think it would be cool to expand the functionality of Noesis with DirectX ripping tools too.
What version of Milkshape is that plugin designed for? The plugin functions but i couldn't get it to import any of your samples. I'm using version 1.8.5.my version of MS is 1.8.4, and it's not a new tool, it's way too old, but it's from russian
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-14T16:27:31+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

Looks simple enough. Have rip files to work with?
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-14T16:42:35+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

> Reply from finale00
>
> Looks simple enough. Have rip files to work with?sure, in the first post or [here](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/dx_ripper_black_ninja/meshes.7z)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-14T17:59:11+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

Don't know how to figure out how to texture it it's just one big mesh (which is reasonable I guess)

[https://www.dropbox.com/sh/7stlpd4qvkq3 ... per_rip.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/vlT0RyD6Bp/fmt_dxripper_rip.py)

Script supports two loading modes configurable at the top

0: load selected model (default)
1: load all models in folder



Really slow since it's python.
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-14T23:46:51+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

That's great and so fast, thanks from whole russian dx ripper community.
When i'm trying to load several objects (mode 1) it works fine, but too long for 300 objects, though
That's why i'm trying to load something in "mode 0" to convert folder in batch mode, but all models give me this:

```
Traceback (most recent call last):
  File "M:\dist\distg\Noesis\noesis\plugins\python\fmt_dxripper_rip.py", line 70, in noepyLoadModel
    load_single_model(data, mdlList)
  File "M:\dist\distg\Noesis\noesis\plugins\python\fmt_dxripper_rip.py", line 57, in load_single_model
    parser = SanaeParser(data)
TypeError: __init__() takes exactly 3 arguments (2 given)
Cleaned 8.00MB (in 2 pools).
```

can u help me with this? also can u add support for UV coordinates?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-15T00:32:11+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

Updated. Should be fine now.
The mesh name is the same as the filename.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-15T04:36:48+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

> Reply from finale00
>
> Updated. Should be fine now.
The mesh name is the same as the filename.thank, it works great, but still what about UV coords?

> Reply from finale00
>
> Don't know how to figure out how to texture it it's just one big mesh (which is reasonable I guess)it's one texture per mesh, so texture has same number in the name as mesh file

p.s.: if u have a time i uppload [full rip scene](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/dx_ripper_black_ninja/frame00.7z) and also [log file](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/dx_ripper_black_ninja/Driver.exe.log.7z) in wich u can find what texture on what mesh u should put on, but this log file is not in ripped scene folder and i don't know will be that right way to use that "texture-to-mesh" info from that file
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-15T05:19:19+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

uv's are there you should be able to just create and assign materials if it's really just one texture per mesh.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-15T05:45:08+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

> Reply from finale00
>
> uv's are theremy bad, you right! didn't get them before for some reason.
Can u add aplying texture files on models in noesis preview? like i said: texture has same number in the name as mesh file, but texture file names start with "t" and then number goes. Aplying textures on models with same number in the name fair for 80% of the ripped resources, though, but still...
Thanks!
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-15T05:52:24+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

8 texture names are defined for each file. Usually there are only 5 or 6.
The first one is usually the same number as the mesh, but not always.

I've updated the script that assumes the first texture name is the material, but noesis keeps crashing on me when I try to view some files for some reason.

Don't know may be an issue on my end.
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-15T06:38:26+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

> Reply from finale00
>
> I've updated the script that assumes the first texture name is the material, but noesis keeps crashing on me when I try to view some files for some reason.
Don't know may be an issue on my end.that's odd  
'll be cool to see texture support also
## Post #14
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-07-17T05:13:03+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

I created a topic about DX Ripper [here](http://forum.xentax.com/viewtopic.php?f=33&t=9282).
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-09-10T13:09:51+00:00
- Post Title: [request] need maxscript or/and noesis plug for .rip format

format is changed a bit
finale, can u help with new format?
[samples here](https://dl.dropbox.com/u/9919707/blogs/xentax.com/dx-ripper/Frame0001.7z)
