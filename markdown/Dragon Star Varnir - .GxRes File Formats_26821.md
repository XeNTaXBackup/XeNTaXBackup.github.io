## Post #1
- Username: NikoPlymouth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 16, 2019 3:10 pm
- Post datetime: 2023-06-04T02:43:56+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

Heya! So I've unpacked the models from Dragon Star Varnir using this tool here: [viewtopic.php?p=165305#p165305](https://forum.xentax.com/viewtopic.php?p=165305#p165305)

But I'm unsure what to do with the.GxRes files that result (.GxResModel, .GxResTexture, etc.)

Example files are here: [https://mega.nz/folder/wp1DjJKK#RSIzqo6K1RWxNJnmytRLJw](https://mega.nz/folder/wp1DjJKK#RSIzqo6K1RWxNJnmytRLJw)

I'll look into it more for myself, but any help would be appreciated!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-04T18:33:16+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

I wasn't in the mood to resolve the sub meshes so I started a point cloud skinner:
.



Dragonstar_Varnir-PtCld-skinner_.jpg (238.09 KiB) Viewed 203 times
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-05T14:34:50+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

> Reply from NikoPlymouth ↑Sun Jun 04, 2023 10:43 am at Sun Jun 04, 2023 10:43 am
>
> 
(.GxResModel, .GxResTexture, etc.)
I made a plugin for *.GxResTexture, I haven't looked at the model yet
[tex_GxResTexture.py](https://github.com/Durik256/Noesis-Plugins/blob/master/tex_GxResTexture.py)



body_cout.GxResTexture.png (36.12 KiB) Viewed 184 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-05T16:33:26+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

Cool.  
I checked for uvs but somehow lost interest (only suiting value in maybe counts table was vertex count.)

0x1A34D4 87495
Vb1
68 52
0xC54C 12774
021000
0x0 255
.



Dragonstar_Varnir fst SM Ptcld.jpg (153.96 KiB) Viewed 178 times
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-05T18:54:50+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

> Reply from shakotay2 ↑Tue Jun 06, 2023 12:33 am at Tue Jun 06, 2023 12:33 am
>
> 
lost interest
i too)
*EDIT final   only for "C011.GxResModel: [fmt_GxResModel.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_GxResModel.py)



C011.GxResModel.png (240.44 KiB) Viewed 144 times


*strange, why does it constantly write to me that the file is too large, although it is much less than 1MB?
## Post #6
- Username: NikoPlymouth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 16, 2019 3:10 pm
- Post datetime: 2023-06-06T14:48:33+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

I appreciate the help from both of you still! I'll look further into this on my own time and try and get it sorted out
## Post #7
- Username: nudgenudgenudge
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 06, 2016 11:31 am
- Post datetime: 2023-06-09T16:00:03+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

Another tool is in undertow.
[https://www.undertow.club/threads/megad ... mod.13835/](https://www.undertow.club/threads/megadimension-neptunia-viir-mod.13835/)
[https://www.undertow.club/threads/neptu ... ost-228276](https://www.undertow.club/threads/neptunia-virtual-stars-mod-request.16486/post-228276)

These are made for the following games.
- Megadimention Neptunia VIIR
- Dragon Star Varnir
- Death end re;Quest
- Death end re;Quest2
- Neptunia Vitual Stars

In this tool, the name of the file expanded from the dat file will be a sequential number.
It also uses extensions stored within the dat file, such as mdlx and tex.
The import script for blender doesn't load textures automatically.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-09-13T16:50:30+00:00
- Post Title: Dragon Star Varnir - .GxRes File Formats

> Reply from NikoPlymouth ↑Sun Jun 04, 2023 10:43 am at Sun Jun 04, 2023 10:43 am
>
> 
Heya! So I've unpacked the models from Dragon Star Varnir using this tool here: viewtopic.php?p=165305#p165305

But I'm unsure what to do with the.GxRes files that result (.GxResModel, .GxResTexture, etc.)

Example files are here: https://mega.nz/folder/wp1DjJKK#RSIzqo6K1RWxNJnmytRLJw

I'll look into it more for myself, but any help would be appreciated!

I have finished my Dragon Star Varnir *.GXRESCOLLISIONMESH, *.GXRESMODEL, *.GXRESMODELEXT, *.GXRESTEXTURE load modules and I released the following programs:

- 3D Object Converter v10.404   (Windows)
- i3DConverter v5.403	         (macOS)
- i3DConverter v3.403	         (Linux)

How to get the 3D Object Converter v10.404:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v10.404.)

How to get the i3DConverter macOS v5.403:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v5.403.)

How to get the i3DConverter Linux v3.403:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v3.403.)
