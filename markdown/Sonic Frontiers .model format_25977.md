## Post #1
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-11-08T20:23:25+00:00
- Post Title: Sonic Frontiers .model format

Sonic Frontiers uses a simular format to Sonic Forces, but the existing tools are unable to import its models.

I have checked a few models and going by headers there are two types of model file:
One with "NEDARCV1 arc NEDLDIV1lodinfo NEDMDLV5model" in the header
Another with "Model NodesExt NodePrms SCAParam ShadowCa ShadowRe GIOcclus TerrainB ColorMas CyberMas"

I have not found any tools to import the former.
The latter can be imported using Turk645's blender importer, but the imported models look to be missing meshes.


Samples in 7z archives [https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1clIrssrZXijsAi4T9xw9OqMcAvC1NJXe?usp=share_link)

Importers tried:
Turk645 Hedgehog-Engine-2-Mesh-Blender-Importer - [https://github.com/Turk645/Hedgehog-Eng ... r-Importer](https://github.com/Turk645/Hedgehog-Engine-2-Mesh-Blender-Importer)
MSOModExp - [viewtopic.php?p=157955#p157955](https://forum.xentax.com/viewtopic.php?p=157955#p157955)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-09T16:03:27+00:00
- Post Title: Sonic Frontiers .model format

Looks as if it were a matter of FVFsizes, so fixing scripts should not be too hard - I thought:
.



eggman.jpg (62.99 KiB) Viewed 240 times



H2O file for the body:

0x1244D6 22947
Vb1
44 24
0x12F81C 5362
120100
0x0 255

(44 being the FVFsize here, just in case)
-------------------------

edit: the script finds below 6 parts, but the body (verts at 0x12F81C) is missing, will need some effort to get an idea, why:

1) params: 0x32cc
verts: 0x8dd8
2) params: 0x205c0
verts: 0x37d8c
3) params: 0xae174
verts: 0xae9f4
4) params: 0xb0f98
verts: 0xb1c2c

5) params: 0xb9790  hands ("chr_eggman_cloth")
verts: 0xc9f58

6) params: 0x106574
verts: 0x10770c
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-10T18:07:19+00:00
- Post Title: Sonic Frontiers .model format

Now I understand: magic tables are horrible. 30% of H2O files need fixing. Annoying.
.



Amy.jpg (92.31 KiB) Viewed 202 times
## Post #4
- Username: Langtanium
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 10, 2022 8:34 am
- Post datetime: 2022-11-11T00:24:19+00:00
- Post Title: Sonic Frontiers .model format

I don't know much about this topic, but its interesting that the amy .model file has extra code in the header, but looking a little lower it has a similar bit of code to sage's .model file.
I've been doing some texting importing them to blender and the .model files that have a header of "Model NodesExt NodePrms SCAParam ShadowCa ShadowRe GIOcclus TerrainB ColorMas CyberMas" can be imported just fine. The problem seems to be with any model with a header of "NEDARCV1 arc NEDLDIV1lodinfo NEDMDLV5model", these files seem to be offset in some way, and viewing a couple of them they all have the same amount of extra code in the header.



model file comp.png (51.88 KiB) Viewed 187 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-12T09:08:39+00:00
- Post Title: Sonic Frontiers .model format

> Reply from Langtanium ↑Fri Nov 11, 2022 8:24 am at Fri Nov 11, 2022 8:24 am
>
> The problem seems to be with any model with a header of "NEDARCV1 arc NEDLDIV1lodinfo NEDMDLV5model", these files seem to be offset in some way, and viewing a couple of them they all have the same amount of extra code in the header.Plus there may be several NEDMDLV5model blocks in a file. But that  doesn't matter in case you do a pattern search to get the meshes.
.



eggrobo_3_SM_reduc.jpg (223.3 KiB) Viewed 163 times

(There's 3 lods for the body, afaics, vertex counts: 7700, 4633 and 2507.)
## Post #6
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-11-13T19:20:21+00:00
- Post Title: Sonic Frontiers .model format

Importer tutorial has been made [https://www.youtube.com/watch?v=B_-YJ2I1_M4](https://www.youtube.com/watch?v=B_-YJ2I1_M4)
## Post #7
- Username: Langtanium
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 10, 2022 8:34 am
- Post datetime: 2022-11-16T20:16:41+00:00
- Post Title: Sonic Frontiers .model format

Now that the models can be obtained, I'm going to post on how to get the textures, so that the process of ripping Sonic Frontiers is faster.
The texture can be fixed using Skyth Tools (GitHub). After fixing the textures, I recommend using paint.net to view the dds files since a lot of them use a newer dds format (that gimp and photoshop can't open by default), and convert them to png.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-17T19:01:09+00:00
- Post Title: Sonic Frontiers .model format

yeah, someone needs to put the textures onto the models:
.



Sonic_cyloop_pattern_.jpg (80.35 KiB) Viewed 103 times


.
H2O files, head&legs, mouth&nose, hands&shoes, arms&ears:

0x4646 22887
Vb1
44 24
0xf914 4325
120100
0x0 255

0xf20a2 6363
Vb1
40 24
0xf5258 1186
120100
0x0 255

0x1331ee 28077
Vb1
40 24
0x140d48 5231
120100
0x0 255

0x3e1de 5433
Vb1
40 24
0x40c50 1010
120100
0x0 255

arms&ears, LOD2

0x109796 2829
Vb1
40 24
0x10adb0 552
120100
0x0 255
