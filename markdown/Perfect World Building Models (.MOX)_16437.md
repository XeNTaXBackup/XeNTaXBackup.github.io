## Post #1
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2017-06-22T16:25:57+00:00
- Post Title: Perfect World Building Models (.MOX)

Hi everyone,
i know there is a way to extract .pck files from perfect world with spck tools. There is one file like "building.pck". After extract i have .mox (models) and .dds (textures), but anyone knows how i can convert the .mox to .obj or like similar model format?

I added a .mox file, if someone needs to test it...

I really hope u can help 
[d6b.zip](https://xentaxbackup.github.io/file/13024_d6b.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-22T18:43:47+00:00
- Post Title: Perfect World Building Models (.MOX)

found a small mesh but faces are unsure, tried toggling backface culling in Noesis, but the result is not really good:



d6b-mox.jpg (140.11 KiB) Viewed 209 times

but this may serve as a starting point.

There's some convex hull data sections (maybe collision mesh?)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-22T19:48:03+00:00
- Post Title: Perfect World Building Models (.MOX)

i think your address was off by a couple of bytes, this is what i got for first submesh  



d6b_mox.png (22 KiB) Viewed 204 times
## Post #4
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2017-06-22T20:21:44+00:00
- Post Title: Perfect World Building Models (.MOX)

Oh okay? Nice... mhh ok, with this its very hard to find out, wich model is wich building xD There are many .mox files with no correct filenames.. a model viewer would helpfull i think..
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-06-29T17:30:56+00:00
- Post Title: Perfect World Building Models (.MOX)

I converted your sample file (all of subobjects) to Wavefront .obj/mtl format.
[d6b_mox_to_obj.zip](https://xentaxbackup.github.io/file/13053_d6b_mox_to_obj.zip)
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-06-29T17:38:27+00:00
- Post Title: Perfect World Building Models (.MOX)

> Reply from olli9000
>
> A model viewer would helpfull i think..

I think this is what you are waiting for:
[e5d.jpg](https://xentaxbackup.github.io/file/13055_e5d.jpg)
## Post #7
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2017-06-30T06:30:24+00:00
- Post Title: Perfect World Building Models (.MOX)

wow nice, thanks    I dont know about this software, nice work  But the last official version is 6.509 right? Mh if this file format is ready to use in a newer version, i think about to buy this programm 

Best regards
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-06-30T18:04:43+00:00
- Post Title: Perfect World Building Models (.MOX)

I released the v6.510 as a web update now.

How to get the 3D Object Converter v6.510:
Please download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v6.510.

I recommend to copy all of .mox and .dds files to the same folder. If you open a .mox file (and you turned on the textured view) you will see the full textured model.
## Post #9
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2017-06-30T20:07:50+00:00
- Post Title: Perfect World Building Models (.MOX)

Thank you
