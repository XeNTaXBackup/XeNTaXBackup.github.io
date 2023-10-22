## Post #1
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-09-19T11:04:18+00:00
- Post Title: [REQ] J-Stars Victory Vs+ model extraction script/tool

A couple of weeks ago I made a post about Burning Blood and shakotay2 made a Make_h2o tool. Since Spike also made J-Stars I wanted to try and extract its models too, sadly the encryption/compression hasn't been defeated, so I went ahead and extracted the unencrypted/uncompressed files from the memory of the RPCS3 emulator, and got them without a problem, they're fairly similar to the Burning Blood format with minor differences.

[J-Stars Samples](https://www.mediafire.com/file/3g0ouh4zkyuwzen/samples_jstars.7z/file)

.srd (pointer/reference file for the model and texture data)
.srdi (raw model data)
.srdv (raw texture data)

They also have the $VTX entries and $RSI subentries that ends with $CT0, but the values are in big endian.



This is the first $VTX entry in koro-sensei.srd, it points to the neck tie submesh in koro-sensei.srdi
20 bytes after $VTX we have the submesh vertices count 00 00 01 44,  0x144 = 324 decimal.
29 bytes after $RSI we have the vertices start address 00 00 00, and right below it, after 13 bytes, the face indices start address 00 83 A0, 0x83a0, right next to it we have the face indices block length 00 00 06 12, 0x612 when divided by 2 we get the FI count 0x309 = 777 decimal.

To get the UV start address we must add the bytes in blue to the vertices start address, they’re not always in the same position in the $VTX section, but they are behind 08 FF FF FF: 0x0 + 0x7980 UV start address.

For the FVFsize we divide the vertices block length by the vertices count:
0x5100 / 0x144 = 0x40 = 64 decimal (haven’t found models with other value).
To get size UVB we need to subtract the values in blue from the values in purple 1 byte after the vertices address and divide the difference by the vertices count: (0x83a0 – 0x7980) / 0x144 = 0x8 = 8 decimal (some are 8 and some 16).

And if I understood the hex2obj tutorial correctly the values between the vertices block and the UVs block should be the submesh’s normals, we can get their start address if we add the vertices block length to the vertices start address: 0x0 + 0x5100 = 0x5100.
Before the $CT0 we have the name of the submesh, in this case tieShape:C_CLOTH.
Open koro-sensei.srdi in hex2obj and input the calculated values from koro-sensei.srd.



Also if you're reading this post shakotay2, thanks for your help, if you're also interested in this, the pattern after $RSI is "01 05 01 02 00 00 00 00"

I've been extracting them manually, but it's getting tiresome and I've only managed to get 14 characters.

[https://www.deviantart.com/josoukitsune/gallery](https://www.deviantart.com/josoukitsune/gallery)

Extracting this guy was a nightmare, I don't want to go through that again
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-19T16:10:11+00:00
- Post Title: [REQ] J-Stars Victory Vs+ model extraction script/tool

> Reply from JosouKitsune ↑Thu Sep 19, 2019 7:04 pm at Thu Sep 19, 2019 7:04 pm
>
> Extracting this guy was a nightmare, I don't want to go through that againyeah, you're truly one of the brave hearted guys here, kudos!  


> Reply from JosouKitsune ↑Thu Sep 19, 2019 7:04 pm at Thu Sep 19, 2019 7:04 pm
>
> they're fairly similar to the Burning Blood format with minor differences.well, srdi uses triangle strips with a terminal of 0xFFFF (termination marker for strip)  

Here's the updated tool:
.


 Make_obj-jstars.zip
(49.39 KiB) Downloaded 25 times


(tested with koro-sensei and Allen only - koro-sensei_25.objx is spoiled, no time to care for it)


btw: the blender wavefront importer complains

```
        parsing obj file...
0.0100 sec
        loading materials and images...
0.0000 sec
        building geometry...
        verts:74 faces:111 materials: 0 smoothgroups:0 ...
Warning Cannot scanfill, fallback on a triangle fan.

```
Not sure what "he's" talking about, these are the triangles in question

```
# faceIndexCnt: 333, triangles: 111
g submesh_0
f 54/54 55/55 19/19 
f 7/7 8/8 5/5 
f 8/8 6/6 5/5 
f 5/5 6/6 1/1 
f 6/6 3/3 1/1 
f 1/1 3/3 2/2 
f 3/3 3/3 2/2 
f 2/2 3/3 4/4 
f 3/3 3/3 4/4 
f 4/4 3/3 19/19 
f 3/3 20/20 19/19 
f 19/19 20/20 54/54 
f 20/20 20/20 54/54 
f 54/54 20/20 56/56 
f 11/11 9/9 8/8 
f 9/9 18/18 8/8 
f 8/8 18/18 6/6 
f 18/18 21/21 6/6 
f 6/6 21/21 3/3 
f 21/21 20/20 3/3 
f 20/20 20/20 56/56 
f 20/20 21/21 56/56 
f 56/56 21/21 57/57 
f 21/21 18/18 57/57 
f 57/57 18/18 58/58 
f 18/18 9/9 58/58 
f 58/58 9/9 10/10 
f 9/9 11/11 10/10 
f 10/10 11/11 10/10 
f 11/11 12/12 10/10 
f 10/10 12/12 24/24 
f 12/12 15/15 24/24 
f 26/26 61/61 24/24 
f 61/61 60/60 24/24 
f 24/24 60/60 10/10 
f 60/60 59/59 10/10 
f 10/10 59/59 58/58 
f 24/24 15/15 26/26 
f 15/15 25/25 26/26 
f 26/26 25/25 26/26 
f 25/25 62/62 26/26 
f 26/26 62/62 63/63 
f 17/17 25/25 15/15 
f 16/16 17/17 13/13 
f 17/17 15/15 13/13 
f 13/13 15/15 14/14 
f 15/15 12/12 14/14 
f 14/14 12/12 22/22 
f 12/12 11/11 22/22 
f 22/22 11/11 23/23 
f 11/11 11/11 23/23 
f 23/23 11/11 27/27 
f 11/11 8/8 27/27 
f 27/27 8/8 7/7 
f 37/37 37/37 36/36 
f 37/37 35/35 36/36 
f 36/36 35/35 45/45 
f 35/35 33/33 45/45 
f 45/45 33/33 48/48 
f 33/33 29/29 48/48 
f 48/48 29/29 46/46 
f 34/34 34/34 35/35 
f 34/34 32/32 35/35 
f 35/35 32/32 33/33 
f 32/32 28/28 33/33 
f 33/33 28/28 29/29 
f 28/28 30/30 29/29 
f 29/29 30/30 29/29 
f 30/30 31/31 29/29 
f 29/29 31/31 29/29 
f 31/31 47/47 29/29 
f 29/29 47/47 46/46 
f 47/47 64/64 46/46 
f 46/46 64/64 46/46 
f 64/64 66/66 46/46 
f 47/47 65/65 64/64 
f 46/46 66/66 48/48 
f 66/66 67/67 48/48 
f 48/48 67/67 45/45 
f 67/67 68/68 45/45 
f 45/45 68/68 36/36 
f 68/68 38/38 36/36 
f 36/36 38/38 37/37 
f 38/38 38/38 37/37 
f 37/37 38/38 39/39 
f 38/38 51/51 39/39 
f 39/39 51/51 41/41 
f 68/68 69/69 38/38 
f 69/69 70/70 38/38 
f 38/38 70/70 51/51 
f 70/70 72/72 51/51 
f 51/51 72/72 71/71 
f 51/51 51/51 41/41 
f 51/51 71/71 41/41 
f 41/41 71/71 52/52 
f 71/71 71/71 52/52 
f 52/52 71/71 73/73 
f 71/71 74/74 73/73 
f 44/44 41/41 52/52 
f 43/43 43/43 44/44 
f 43/43 40/40 44/44 
f 44/44 40/40 41/41 
f 40/40 42/42 41/41 
f 41/41 42/42 39/39 
f 42/42 49/49 39/39 
f 39/39 49/49 37/37 
f 49/49 50/50 37/37 
f 37/37 50/50 37/37 
f 50/50 53/53 37/37 
f 37/37 53/53 35/35 
f 53/53 34/34 35/35 

```
There's bad tris like f 3/3 3/3 4/4 or f 37/37 50/50 37/37 which I was sure the hex2obj code should exclude but since the mesh is loaded successfully my motivation to care for this is limited...
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-19T17:46:26+00:00
- Post Title: [REQ] J-Stars Victory Vs+ model extraction script/tool

koro-sensei-srdi.png (186.43 KiB) Viewed 195 times
## Post #4
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-09-19T19:16:01+00:00
- Post Title: [REQ] J-Stars Victory Vs+ model extraction script/tool

> Reply from shakotay2 ↑Fri Sep 20, 2019 12:10 am at Fri Sep 20, 2019 12:10 am
>
> 
JosouKitsune wrote: ↑Thu Sep 19, 2019 7:04 pmExtracting this guy was a nightmare, I don't want to go through that again  
yeah, you're truly one of the brave hearted guys here, kudos!

Thanks, I know I sound pedantic and lazy, but it's just the guy had multiple parts and accidentally skipped some, so going back to try all meshes to get the missing one was a chore  
Anyways thanks for the tool again.
## Post #5
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-09-20T07:44:18+00:00
- Post Title: [REQ] J-Stars Victory Vs+ model extraction script/tool

any chance of a noesis script or anything with rigging applied? I'd rather not deal with OBJ.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-22T11:00:37+00:00
- Post Title: [REQ] J-Stars Victory Vs+ model extraction script/tool

Allen's bones - feel free to build a hierarchical skeleton with them:

```
1 CHEEK_01_R
2 CHEEK_02_L
3 CHEEK_02_R
4 CHEEK_03_L
5 CHEEK_03_R
6 CHEEK_EYE_L
7 CHEEK_EYE_R
8 CHIN
9 CHIN_middle
10 CLANK_L
11 CLANK_LC
12 CLANK_R
13 CLANK_RC
14 CLAVICLE_L
15 CLAVICLE_R
16 EFFECT_L
17 EFFECT_R
18 ELBOWROLL_L
19 ELBOWROLL_R
20 ELBOW_L
21 ELBOW_LC
22 ELBOW_R
23 ELBOW_RC
24 EQUIPMENT_01
25 EQUIPMENT_02
26 EYE
27 EYEBALL_01_L
28 EYEBALL_01_R
29 EYEBALL_02_L
30 EYEBALL_02_R
31 EYEBROWS_01_L
32 EYEBROWS_01_R
33 EYEBROWS_02_L
34 EYEBROWS_02_R
35 EYEBROWS_03_L
36 EYEBROWS_03_R
37 EYEBROWS_04_L
38 EYEBROWS_04_R
39 EYE_down_01_L
40 EYE_down_01_R
41 EYE_down_02_L
42 EYE_down_02_R
43 EYE_down_03_L
44 EYE_down_03_R
45 EYE_up_01_L
46 EYE_up_01_R
47 EYE_up_02_L
48 EYE_up_02_R
49 EYE_up_03_L
50 EYE_up_03_R
51 FACE
52 F_FORE0_L
53 F_FORE0_R
54 F_FORE1_L
55 F_FORE1_R
56 F_FORE2_L
57 F_FORE2_R
58 F_FORE3_L
59 F_FORE3_R
60 F_LITTLE0_L
61 F_LITTLE0_R
62 F_LITTLE1_L
63 F_LITTLE1_R
64 F_LITTLE2_L
65 F_LITTLE2_R
66 F_LITTLE3_L
67 F_LITTLE3_R
68 F_MEDICINAL0_L
69 F_MEDICINAL0_R
70 F_MEDICINAL1_L
71 F_MEDICINAL1_R
72 F_MEDICINAL2_L
73 F_MEDICINAL2_R
74 F_MEDICINAL3_L
75 F_MEDICINAL3_R
76 F_MIDDLE0_L
77 F_MIDDLE0_R
78 F_MIDDLE1_L
79 F_MIDDLE1_R
80 F_MIDDLE2_L
81 F_MIDDLE2_R
82 F_MIDDLE3_L
83 F_MIDDLE3_R
84 F_THUMB0_L
85 F_THUMB0_R
86 F_THUMB1_L
87 F_THUMB1_R
88 F_THUMB2_L
89 F_THUMB2_R
90 F_THUMB3_L
91 F_THUMB3_R
92 HEAD
93 HIP_L
94 HIP_R
95 MOUTH
96 MOUTH_down_01_L
97 MOUTH_down_01_R
98 MOUTH_down_02_L
99 MOUTH_down_02_R
100 MOUTH_down_03_L
101 MOUTH_down_03_R
102 MOUTH_down_middle
103 MOUTH_up_01_L
104 MOUTH_up_01_R
105 MOUTH_up_02_L
106 MOUTH_up_02_R
107 MOUTH_up_03_L
108 MOUTH_up_03_R
109 MOUTH_up_04_L
110 MOUTH_up_04_R
111 MOUTH_up_middle
112 NECK
113 NOSE_middle
114 NULL
115 OPTION_01
116 OPTION_02
117 OPTION_03
118 OPTION_04
119 OPTION_05
120 OPTION_06
121 OPTION_07
122 OPTION_08
123 OPTION_09
124 OPTION_10
125 OPTION_11
126 OPTION_12
127 OPTION_13
128 RESERVE
129 SHOULDER_L
130 SHOULDER_LC
131 SHOULDER_R
132 SHOULDER_RC
133 SPINE1
134 SPINE2
135 SPINE3
136 THIGH_L
137 THIGH_R
138 THROW
139 TOE1_L
140 TOE1_R
141 TOE2_L
142 TOE2_R
143 TONGUE
144 TOOTH_down1_middle
145 TOOTH_down2_middle
146 TOOTH_down_01_L
147 TOOTH_down_01_R
148 TOOTH_up1_middle
149 TOOTH_up2_middle
150 TOOTH_up_01_L
151 TOOTH_up_01_R
152 TOOTH_up_02_L
153 TOOTH_up_02_R
154 UTILITY_01
155 UTILITY_05
156 WAIST
157 WRIST_L
158 WRIST_R

```
