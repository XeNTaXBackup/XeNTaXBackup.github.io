## Post #1
- Username: Cornalito
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 19, 2018 5:52 am
- Post datetime: 2022-04-10T00:57:53+00:00
- Post Title: WRC 10 .P3D MODELS

Hi, i tried convert this models with a blender script for WRC 7, but only shows the skeleton data, theres a way to convert this models in a usable format like obj or fbx?

Theres some files:
[https://drive.google.com/file/d/107HqU7 ... sp=sharing](https://drive.google.com/file/d/107HqU77NJAUrT5KOSyzCl6cZNrY5VeZT/view?usp=sharing)
## Post #2
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2022-12-28T20:31:11+00:00
- Post Title: WRC 10 .P3D MODELS

hey there,

i'm currently looking at the WRC Series and failing at the recent two Games (WRC10 and WRC Generations)

here is what i've gathered so far:

Extracting:

Ekey has updated the *.PKG Quickbms Script to extract the new Games
[https://zenhax.com/viewtopic.php?t=17621&#p74340](https://zenhax.com/viewtopic.php?t=17621&#p74340)

all these Files are using RIFF as a Container which can be viewed more or less with riffpad.exe or any hex editor

.PSI = Scene File -> stores linked *.P3D Mesh and *.PMA Materials
.PAN = Animation File -> well, animation data
.PMA = Material File -> stores linked *.PTX Textures
.PTX = Texture File -> basically a headerless DDS File (DXT1, DXT5, BC4, BC5S, BC7)
.P3D = Mesh File -> Blockwise stored Submeshes

Textures:

Acewell has created a Texture Plugin for Noesis
[viewtopic.php?p=139861#p139861](https://forum.xentax.com/viewtopic.php?p=139861#p139861)

newer WRC games do use BC4 and BC7 Textures aswell - i've added them similar to his BC5S Method
Noesis prints out errors on large scaled Textures but converts them well

Meshes:

h3x3r and Szkaradek123 over at ZenHax already made some research about that P3D Format and already made an Import Script 
which works fine with WRC 6,7,8,9, also with ETRC European Truck Racing Championship Vehicles
if vertices exceed the 65k limit (mostly on interior meshes) it will look scrambled

[https://zenhax.com/viewtopic.php?t=8872](https://zenhax.com/viewtopic.php?t=8872)

Vehicles need to have that Bone Structure, otherwise all Meshes will be centered to 0,0,0, ending up with a Puzzle
Hierachy starts with "Root" Node followed by "D_Main" and all Dummies / Nodes, each Node has a Matrix 4x4 Transform data set

WRC 7 has 43 "MeLiMesh" entries and 71 "GeLiGeom" / "SGLiSuGe" probably SubGeometry. 16 bytes after "SGLiSuGe" the 3d data starts:

vpos = Position
vnor = Normals
vtan = Tangents
vuvs = UV Data
indx = Indices

WRC 10 added a livery editor - which added these to the Structure

vski = Skin Data
vcol = Color / Collission?

WRC 10 has 71 "MeLiMesh" entries and 143 "GeLiGeom" / "SGLiSuGe" but it now starts after 24 Bytes instead of 16 Bytes

the Blender import is able to load the Bone Structure of WRC 10 Files - but fails at parsing the Mesh (Index out of Range) 
and i cant figure if that 24 Byte Offset causes that Issue

[https://imgur.com/Y1wVMWj](https://imgur.com/Y1wVMWj)

Model Researcher shows, WRC10 is fine (except for scaled UV)

[https://imgur.com/4nlTBLf](https://imgur.com/4nlTBLf)



WRC Generations totally flipped over the RIFF structure
the Bones remain the same but now each "NodsNoHe" contains "MeRe" - Mesh Resource? WRC Generations Yaris has again 71 of them
"MeRe_" seems to be the ID [Hex: 4D65526506 00 00 00 _XX_ 00 00 00 FF FF] 

```
D_Main
Exhaust					MeRe	37	55
Exhaust_LOD1				MeRe	1C	28
Wiper_L					MeRe	01	01
Wiper_L_LOD1				MeRe	2D	45
Wiper_R					MeRe	12	18
Wiper_R_LOD1				MeRe	3E	62
Cockpit					MeRe	23	35
Cockpit_LOD1				MeRe	08	08
Cockpit_LOD2				MeRe	33	51
Optics_FL				MeRe	18	24
Optics_FL_LOD1				MeRe	44	68
Optics_FR				MeRe	29	41
Optics_FR_LOD1				MeRe	0E	14
Optics_RL				MeRe	3A	58
Optics_RL_LOD1				MeRe	1F	31
Optics_RR				MeRe	04	04
Optics_RR_LOD1				MeRe	30	48
SeatPilot				MeRe	15	21
SeatPilot_LOD1				MeRe	41	65
SeatCoPilot				MeRe	26	38
SeatCoPilot_LOD1			MeRe	0B	11
Engine					MeRe	35	53
Engine_LOD1				MeRe	1A	26
Suspension				MeRe	46	70
Suspension_LOD1				MeRe	2B	43
Body					MeRe	10	16
Body_LOD1				MeRe	3C	60
Body_LOD2				MeRe	21	33
Body_LOD3				MeRe	06	06
Boot					MeRe	38	56
Optics_RM				MeRe	1D	29
Optics_RM_LOD1				MeRe	02	02
Boot_LOD1				MeRe	2E	46
Spoiler					MeRe	13	19
Spoiler_LOD1				MeRe	3F	63
Glass_R					MeRe	24	36
Glass_R_LOD1				MeRe	09	09
Bumper_F				MeRe	34	52
Bumper_F_LOD1				MeRe	19	25
Cache_LightPods_B			MeRe	45	69
Cache_LightPods_B_LOD1			MeRe	2A	42
LightPods_B				MeRe	0F	15
LightPods_B_LOD1			MeRe	3B	59
Door_R					MeRe	20	32
Door_R_LOD1				MeRe	05	05
Mirror_R				MeRe	31	49
Mirror_R_LOD1				MeRe	16	22
Glass_FR				MeRe	42	66
Glass_FR_LOD1				MeRe	27	39
Door_L					MeRe	0C	12
Door_L_LOD1				MeRe	36	54
Mirror_L				MeRe	1B	27
Mirror_L_LOD1				MeRe	00	00
Glass_FL				MeRe	2C	44
Glass_FL_LOD1				MeRe	11	17
Hood					MeRe	3D	61
LightPods_T				MeRe	22	34
LightPods_T_LOD1			MeRe	07	07
Hood_LOD1				MeRe	32	50
Bumper_R				MeRe	17	23
Bumper_R_LOD1				MeRe	43	67
Wing_L					MeRe	28	40
Wing_L_LOD1				MeRe	0D	13
Wing_R					MeRe	39	57
Wing_R_LOD1				MeRe	1E	30
Glass_F					MeRe	03	03
Glass_F_LOD1				MeRe	2F	47
Glass_RL				MeRe	14	20
Glass_RL_LOD1				MeRe	40	64
Glass_RR				MeRe	25	37
Glass_RR_LOD1				MeRe	0A	10

```


again 71 "MRsc" -> 150 "GeLiGeom" / "SGLiSuGe" which gives the offsets on the meshdata (vcol,vtan,vnor,vpos,vuvs,vski)

these values will be needed to go through the "GeHeGSiz" starting 4 bytes after "GHda"
First entry seems to be Mirror_L_LOD1

```
vcol	00000000	(0000)	File Offset	0x6E
vtan	F0040000	(1264)	File Offset	0x55E
vnor	E0090000	(2528)	File Offset	0xA4E
vpos	C0130000	(5056)	File Offset	0x142E
vuvs	90220000	(8848)	File Offset	0x22FE
indx	????????	(????) 	File Offset	0x27EA
Mirror_LOD1 Submesh Mirror: 
vcol	10310000	(12560)	File Offset	0x317E
and so on

```


Looks correct - yet i havent seen the link to the index, but it seems to be at the end of each submesh block

[https://imgur.com/vqYi7io](https://imgur.com/vqYi7io)

would be awesome if someone could take a look at the Blender Script and help me parsing the WRC Generation Meshes


Here are some example files to take a look at

WRC Generations Yaris with material and some texture files etc.
WRC 7 and 10 Yaris - more or less identical
Riffpad.exe - to view the files with structure
"updated" noesis PTX script - as mentioned i added BC7 BC4

[https://www.mediafire.com/file/8u9nqstp ... G.rar/file](https://www.mediafire.com/file/8u9nqstpm3j6lvb/WRC10G.rar/file)
## Post #3
- Username: Keane1432
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 28, 2016 1:56 am
- Post datetime: 2023-01-02T13:55:17+00:00
- Post Title: WRC 10 .P3D MODELS

Hello! 

Have you somehow managed to import the Generations 3D models to either Blender or some other software? 

Thanks!
## Post #4
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2023-01-02T15:25:41+00:00
- Post Title: WRC 10 .P3D MODELS

i'm currently trying to write my first Noesis Script - but i'm not that good at coding, so it takes time

i now know that the Bytes after the "SGLiSuGe" are the Vertices Count Value and the Faces Count Value - the first 4 Bytes after "vpos" / "vtan" etc. are the Chunk Size

WRC 7 looks like this
SGLiSuGe _ _ _ _ _ _ vertices count - faces count - CD AB vpos chunksize ... 

WRC10 has moved the Chunk Size in between that "Strm" and "vpos"
SGLiSuGe _ _ _ _ _ _ vertices count - faces count - CD AB Strm chunksize vpos ...

that should be the issue why the Blender Script cant find the correct Values - which is no wonder, since the Script has been written in 2018

as mentioned, WRC Generations flipped that File Structure but the Data seems to be the same
SGLiSuGe _ _ _ _ _ _ vertices count - vpos chunkstart vuvs chunkstart etc. the last entry is the face index count and its chunkstart


my noesis script opens the first submesh at the moment 
still have to do:
hierachy / bones structure
moving the mesh to its parent bone / transform
fixing the normals
fixing the uv
repeat the process to load all submeshes inside one file

[https://imgur.com/a/MGGfxmE](https://imgur.com/a/MGGfxmE)

the meshes on that screenshots are from V-Rally 4 which is using the same structure as WRC 7

funfact: wrc generations had a v-rally 4 logo inside one of their ui textures

games using that p3d file
WRC 5 FIA World Rally Championship
WRC 6 FIA World Rally Championship
WRC 7 FIA World Rally Championship
WRC 8 FIA World Rally Championship
WRC 9 FIA World Rally Championship
WRC 10 FIA World Rally Championship
WRC Generations
ETRC FIA European Truck Championship
V-Rally 4

i'm sure some of the motogp / motocross games are using the same system, anything related to Kylotonn KT Racing / Nacon / BigBen / Milestone

edit:

WRC Generations - again only the first submesh

[https://imgur.com/a/KboO1nX](https://imgur.com/a/KboO1nX)

here are Three Noesis Scripts - still in Progress - maybe someone can help me here
WRC Generations splits the Meshdata in Chunks - skipping / ignoring the Block Header (GHda____) is needed to append the next Chunk


 P3D.rar
(3.48 KiB) Downloaded 34 times
## Post #5
- Username: Keane1432
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 28, 2016 1:56 am
- Post datetime: 2023-01-03T15:20:50+00:00
- Post Title: WRC 10 .P3D MODELS

Great progress, so my understanding is, those scripts now are not yet working in Blender?

Thanks!
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-03T20:35:55+00:00
- Post Title: WRC 10 .P3D MODELS

You need some deeper understanding to patch the 2.49b py scripts. I tweaked it a bit, got a lot of NANs (why?), this is a result:
.



WCR10.jpg (107.95 KiB) Viewed 714 times



If someone told me what the numbers after Strm mean I could give it another try:

```
                        NoHe 92 570 
                        1 Exhaust 1 (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, -0.037325441837310791, -0.34830546379089355, 0.027960419654846191, 1.0) (205, 171, 0, 0, 0, 0, 1, 0, 0, 0, 205, 171) 
                        LIST : 12470 MeLi 670 
                            Mesh 66 682 
                            LIST : 12384 GeLi 756 
                                Geom 32 768 
                                LIST : 12332 SGLi 808 
                                    SuGe 12 820 
                                        6 296 460 43981 
                                    Strm 1188 840 
                                    Strm 1188 2036 
                                    Strm 2372 3232 
                                    Strm 3556 5612 
                                    Strm 1188 9176 
                                    indx 2760 10372 
f 0 1 2 
f 2 3 0 
f 4 0 3 
f 5 2 1 
f 1 6 5 
f 3 7 4 
f 8 4 7 
f 3 2 9 
f 10 5 6 
f 6 11 10 
f 10 11 12 
f 5 10 13 
f 2 5 14 
f 14 9 2 
f 13 14 5 
f 12 15 10 
f 13 10 15 
f 15 12 16 
```
(face indices need a +1 when used for wavefront obj, btw)

> Reply from guki ↑Mon Jan 02, 2023 11:25 pm at Mon Jan 02, 2023 11:25 pm
>
> the first 4 Bytes after "vpos" / "vtan" etc. are the Chunk SizeFor me it looks as if the 4 bytes after "vpos" are a float in WCR10 P3D files.
## Post #7
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2023-01-03T21:06:25+00:00
- Post Title: WRC 10 .P3D MODELS

i didnt write the blender 2.49b script - i decided to do one from scratch inside noesis

the 4 bytes after Strm are the chunksize of the following sector

Strm(1188)vcol

start at vcol + 1188 will lead to next Strm block


on wrc 7 there was no Strm - and the chunksize was after vcol(xxxx) etc.



1.png (39.77 KiB) Viewed 712 times
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-04T00:19:28+00:00
- Post Title: WRC 10 .P3D MODELS

> Reply from guki ↑Wed Jan 04, 2023 5:06 am at Wed Jan 04, 2023 5:06 am
>
> 
inside noesis
Sorry, I didn't read that thread at all. just downloaded the files from the first post.
i would use recursion.
I quickly made a plugin, (loads all meshes, only vertices and uvs).
*easy to add the rest


just noticed. uvs needs to be scaled. add after line 62 "rapi.rpgSetUVScaleBias(NoeVec3([16]*3),None)"
[fmt_p3d.zip](https://xentaxbackup.github.io/file/23251_fmt_p3d.zip)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-04T06:55:21+00:00
- Post Title: WRC 10 .P3D MODELS

Hi Durik, really cool!  

I always asked myself WHY these old blender scripts are so complicated.  

It's lines like this one (see if tag== 'NoHe') which I find totally annoying:
b=g.word(g.i(1)[0])[-25:])

(Finally I end up with spamming them with dozens of print commands to understand what the current address is.  )
## Post #10
- Username: Keane1432
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 28, 2016 1:56 am
- Post datetime: 2023-01-04T09:17:00+00:00
- Post Title: WRC 10 .P3D MODELS

So I finally understood where to put the scripts   

Looking forward to the progress of the WRC Generations script, so it can load the full car, not only one mesh.. Keep it up!
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-04T21:58:28+00:00
- Post Title: WRC 10 .P3D MODELS

> Reply from shakotay2 ↑Wed Jan 04, 2023 2:55 pm at Wed Jan 04, 2023 2:55 pm
>
> 
Hi Durik, b=g.word(g.i(1)[0])[-25:])
Hi, Shakotay)
yes, I noticed that too. perhaps this is done intentionally to confuse the "readers" of the code.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-04T22:36:13+00:00
- Post Title: WRC 10 .P3D MODELS

> Reply from Durik256 ↑Thu Jan 05, 2023 5:58 am at Thu Jan 05, 2023 5:58 am
>
> 
Hi, Shakotay)
yes, I noticed that too. perhaps this is done intentionally to confuse the "readers" of the code.Haha, really? (Why should he have done so?  )

An obvious reason is how python is "constructed". Many people praise it for its flexibility in handling lists, tuples and indexing.
See this example (taken from Sergii Boiko's blog):

```
1. >>> nums = [10, 20, 30, 40, 50, 60, 70, 80, 90]
2. >>> nums[:-2]
3. [10, 20, 30, 40, 50, 60, 70]
```

Well, I see the point, but still don't like it.  (You may have noticed that the ':' is before the -2 here, so "coming from the end".)
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-04T22:58:05+00:00
- Post Title: WRC 10 .P3D MODELS

> Reply from shakotay2 ↑Thu Jan 05, 2023 6:36 am at Thu Jan 05, 2023 6:36 am
>
> 
 so "coming from the end".)
yep it's "slicing" an array. arr[start:end].

```
nums[:-2] = [0:arr.Lenght - 2].
same with index access:
nums[-2] = nums[arr.Lenght - 2] = 80
```


I like Python because of the fact that you do not need to explicitly specify the types of variables. simpler entries. no need for parentheses, semicolons, etc. for a while later a bit awkward to write in c#  
*(but it passes quickly)
## Post #14
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2023-01-05T15:49:57+00:00
- Post Title: WRC 10 .P3D MODELS

thank you very much Durik! that was fast

i still have to learn a lot and that blender script totally confused me

```
            bs.seek(6,1)
            meshname = bs.readString()
            rapi.rpgSetName(meshname)

```


NodsNoHe tells the Bone / Mesh Name and the Transform Matrix which are parent/child in the hierachy

Normals of these Meshes seems to be Halffloat

```
            buf = bs.readBytes(vnum*12)
            rapi.rpgBindNormalBuffer(buf, noesis.RPGEODATA_HALFFLOAT, 8)

```


mapping turns out well, some meshes seem to use a different pattern - the mirrors and windows look totally scrambled, maybe a second uv channel?

[https://imgur.com/a/hy298gQ](https://imgur.com/a/hy298gQ)

i will take a closer look on that

thanks again 


edit:

took another look on these "broken" meshes and yes, they do use multiple uv channels
meshes with COLOTANBNORMPOS_UV0_ should be fine by now
meshes with COLOTANBNORMPOS_UV0_UV1_ have two uv channels
meshes with COLOTANBNORMPOS_UV0_UV1_UV2_ have three uv channels

[https://imgur.com/a/LJvJ8ZB](https://imgur.com/a/LJvJ8ZB)

wrc 10 yaris frontwindow piece and mirror

if it uses two uv channels - the padding is 4
mirror_r
807
1340
vpos 0x7e6af4
vuvs 0x7e90d4 - leaving the padding on 0 will look broken
fpos 0x7eaa14

vuvs 0x7e90d4	uv0 - padding 4 first start - fits the body texture mapping
vuvs 0x7e90d8	uv1 - second start - looks like a carbon mapping - for the livery editor i guess

if it uses three uv channels the padding is 8
glass_f
vcount 188
fcount 170
vpos 0x9bdba0
vuvs 0x9be47c - leaving the padding on 0 will look broken
fpos 0x9bed52

uv padding 8
vuvs 0x9be47c uv0 - they now use a windscreen.ptx texture with the banner and name decals
vuvs 0x9be480 uv1 - could be the dirt / damage layer
vuvs 0x9be484 uv2 - another dirt / damage layer?



this format drives me crazy

edit 2:

> Reply from Keane1432 ↑Wed Jan 04, 2023 5:17 pm at Wed Jan 04, 2023 5:17 pm
>
> 
Looking forward to the progress of the WRC Generations script, so it can load the full car, not only one mesh.. Keep it up!

i was able to rebuild Durik246's script to load up WRC Generations files, currently this also requires some hex editing on the larger p3d files aswell

also i need to add these additional uv channels



puma.jpg (207.88 KiB) Viewed 441 times
## Post #15
- Username: markBotella
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 03, 2023 7:21 pm
- Post datetime: 2023-03-03T11:23:43+00:00
- Post Title: WRC 10 .P3D MODELS

Hello, I would like to make a 3d model of wrc generations, it would be the bell helmet of a rally 2 co-driver. How could I do it, thanks and if someone could do it, I would really appreciate it, thanks
## Post #16
- Username: laurorosas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 27, 2020 9:50 am
- Post datetime: 2023-05-03T02:46:22+00:00
- Post Title: Re: WRC 10 .P3D MODELS

Hello!  Can you attach the script to extract the cars from the WRC Generations?
