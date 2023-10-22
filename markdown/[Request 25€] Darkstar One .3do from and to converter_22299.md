## Post #1
- Username: bc304
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 20, 2020 6:42 am
- Post datetime: 2020-06-19T23:08:08+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

Hi,

I would like to request a converter from and to the .3do 3D File format from Darkstar one by Ascaron Entertainment.
They are bundled with a .shd file (I assume this stands for shaders?).
I would offer a monetary reward of 25€.
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-06-22T15:54:48+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

Without having .3do sample files we can't help you.
## Post #3
- Username: bc304
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 20, 2020 6:42 am
- Post datetime: 2020-06-22T16:34:30+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

You are right. I am sorry. 
I didnt find a direct way to attach them. Hope Zip/rar is ok.

Here are some samples:
[http://www.mediafire.com/file/6z4mto95g ... s.rar/file](http://www.mediafire.com/file/6z4mto95g3and2h/Darkstar_One_3do_shd_samples.rar/file)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-22T17:13:42+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

Mesh format appears to be simple, using hex2obj (view link in my sig):
.



terminal_3do.png (108.79 KiB) Viewed 132 times


(FVFsize assumed to be found at offset 0x78.)

> Reply from bc304 ↑Sat Jun 20, 2020 7:08 am at Sat Jun 20, 2020 7:08 am
>
> 
Hi,

I would like to request a converter from and to the .3do 3D File formatHi, I have my doubts that someone will code a "to .3do" converter. Maybe for static meshes with vertex counts maintained.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-22T17:28:53+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

.shd contains only geo positions and normals:
(hideoutlod.shd)


Highest LOD of hideoutlod.3do:



hideoutlod.3do.jpg (142.68 KiB) Viewed 129 times
## Post #6
- Username: bc304
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 20, 2020 6:42 am
- Post datetime: 2020-06-22T18:07:54+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

That did go very fast. Didnt know it would be that easy.

First, I wanna say that I do not have much (or any) knowledge about modding/reverse engineering or hex, so sorry if I dont get something.

I forgot to mention that there is a "modding guide" with an official 3do converter for the game from the developers. The catch (at least I think it is) is that it only supports an really old ".x" format. An old directx 3d file format of some sorts. I had no luck converting an .obj into that and then the .x into a .3do whatsover, maybe I was just doing it wrong.

I attach the guide and the command line converter.

[http://www.mediafire.com/file/6fza5nmh8 ... t.rar/file](http://www.mediafire.com/file/6fza5nmh8h5oe05/Modding_kit.rar/file)

I am looking for a "semi" easy way to work with the models. I dont want any fancy programs or anything.
I want to extract the existing models, change them, convert them back and put them into the game.
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-06-22T20:29:28+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

I have watched the Apple WWDC 2020, but after it I wrote a new .3do loader module.



DarkStar_One.png (109.13 KiB) Viewed 120 times
## Post #8
- Username: bc304
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 20, 2020 6:42 am
- Post datetime: 2020-06-27T00:27:20+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

Great news! Did you only wrote a loader or also a export?
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-06-28T14:10:43+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

> Reply from bc304 ↑Sat Jun 27, 2020 8:27 am at Sat Jun 27, 2020 8:27 am
>
> 
Great news! Did you only wrote a loader or also a export?

I have finished my DarkStar One .3do and .shd loader modules and I have released the following program as web updates:

- 3D Object Converter v7.033 (Windows)

How to get the 3D Object Converter:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.033.
## Post #10
- Username: bc304
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 20, 2020 6:42 am
- Post datetime: 2020-07-04T16:12:36+00:00
- Post Title: [Request 25€] Darkstar One .3do from and to converter

Thanks Karpati for the work! The loader works like a charm.

While loading them is great, I still search for a way to export them. I attached the .x to .3do converter in an above post.

Does anyone have any information regarding this .x format? How to convert something into it?
