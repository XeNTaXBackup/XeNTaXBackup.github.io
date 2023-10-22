## Post #1
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-18T04:19:17+00:00
- Post Title: Havok binary files

Hello! I would like to ask, can anyone help me with converting 2013 Havok binary skeleton/animation files to a usable format, or at least to [Havok ASCII](http://puu.sh/hRoCq/9c11b40524.hkx)?

I have the format pretty much figured out, I just haven't the foggiest idea on how to convert it to something usable. 


[Here's some sample animations and a skeleton.](http://puu.sh/hRnHb/a2d2e2b8ea.zip)


There is already a Blender importer, but it only works for the 2012 version. However, the 2011 and 2013 formats are very similar, so I can't imagine there's a large difference between 2012 and 2013.

The animations use hkaSplineCompressedAnimation. Here's some info we got so far:

```
{
  int m_numFrames;
  int m_numBlocks;
  int m_maxFramesPerBlock;
  int m_maskAndQuantizationSize;
  float m_blockDuration;
  float m_blockInverseDuration;
  float m_frameDuration;
  hkArray<unsigned int,hkContainerHeapAllocator> m_blockOffsets;
  hkArray<unsigned int,hkContainerHeapAllocator> m_floatBlockOffsets;
  hkArray<unsigned int,hkContainerHeapAllocator> m_transformOffsets;
  hkArray<unsigned int,hkContainerHeapAllocator> m_floatOffsets;
  hkArray<unsigned char,hkContainerHeapAllocator> m_data;
  int m_endian;
};
```

[More definitions here.](http://puu.sh/hRo8t/9ce9b8efe4.zip)


And if you look at the ASCII example in the link at the top, it corresponds to this part here:

```
         <!-- memSizeAndFlags SERIALIZE_IGNORED -->
         <!-- referenceCount SERIALIZE_IGNORED -->
         <hkparam name="type">HK_SPLINE_COMPRESSED_ANIMATION</hkparam>
         <hkparam name="duration">1.066667</hkparam>
         <hkparam name="numberOfTransformTracks">30</hkparam>
         <hkparam name="numberOfFloatTracks">0</hkparam>
         <hkparam name="extractedMotion">#0043</hkparam>
         <hkparam name="annotationTracks" numelements="0"></hkparam>
         <hkparam name="numFrames">33</hkparam>
         <hkparam name="numBlocks">1</hkparam>
         <hkparam name="maxFramesPerBlock">256</hkparam>
         <hkparam name="maskAndQuantizationSize">120</hkparam>
         <hkparam name="blockDuration">8.500002</hkparam>
         <hkparam name="blockInverseDuration">0.117647</hkparam>
         <hkparam name="frameDuration">0.033333</hkparam>
         <hkparam name="blockOffsets" numelements="1">
            0
         </hkparam>
         <hkparam name="floatBlockOffsets" numelements="1">
            4744
         </hkparam>
         <hkparam name="transformOffsets" numelements="0"></hkparam>
         <hkparam name="floatOffsets" numelements="0"></hkparam>
         <hkparam name="data" numelements="4752">
            69 0 0 0 69 112 240 0 69 5 240 0 69 1 240 0
            69 1 240 0 69 1 240 0 69 1 10 0 69 5 240 0
            ...
```

It's from 2010 though, which as you can see is very different from the 2013 layout.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-18T09:16:10+00:00
- Post Title: Havok binary files

> Reply from SergeantJoe
>
> There is already a Blender importer, but it only works for the 2012 version.speaking of which?
Does it support hkaSplineCompressedAnimation?
## Post #3
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-18T09:21:28+00:00
- Post Title: Havok binary files

I believe so, [it's the one that cra0 and others did for Alien Isolation](http://forum.xentax.com/viewtopic.php?p=103131#p103131). 

I haven't been able to test it though, I don't have that game and cra0 couldn't give me any samples since he got bored and quit a long time ago.


EDIT: Awww, fuck. I didn't look closely enough, the Blender importer is only for models. The bone tool is actually a separate exe, and it just converts hkx files to SMD. 

Whether those files are ascii or binary I dont know. I should probably buy the game and make sure.


But still, that's good. Now we know it's at least possible to convert hkx files to a useable format. If we ask Wolfin I'm sure he'll explain how it works.

Or if all else fails we can jerry-rig the 2013 files to work with that program. I tried this with the Skyrim hkx converter, but the format is too different from 2010-2013.
## Post #4
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2015-05-19T01:52:50+00:00
- Post Title: Havok binary files

> the Blender importer is only for models. The bone tool is actually a separate exe
Where's that uploaded?
## Post #5
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-19T02:52:04+00:00
- Post Title: Havok binary files

[It's an attachement a few posts below the one I linked.](http://forum.xentax.com/viewtopic.php?p=103133#p103133)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-19T05:03:30+00:00
- Post Title: Havok binary files

> Reply from SergeantJoe
>
> , and it just converts hkx files to SMD. 
[..]
But still, that's good. Now we know it's at least possible to convert hkx files to a useable format.
That's known since ages.
What we don't know is how to uncompress hkaSplineCompressedAnimations.
## Post #7
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-19T05:38:27+00:00
- Post Title: Havok binary files

Could you please quickly explain what you mean by uncompress? What exactly is that process?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-19T05:59:09+00:00
- Post Title: Havok binary files

> Reply from SergeantJoe
>
> What exactly is that process?If I knew exactly about uncompressing hkaSplineCompressedAnimations we wouldn't talk here, would we?  

Think of a zipped file. You'll need to know the decompression algo to decompress it.
Or look here (NOT hkx related): [viewtopic.php?f=16&t=8630&p=96977#p96977](http://forum.xentax.com/viewtopic.php?f=16&t=8630&p=96977#p96977)

btw, here's the BrawlerA.hkx (hk_2013.2.0-r1) skeleton as smd:

```
version 1
nodes
0 "Bip01" -1
1 "Bip01 Pelvis" 0
2 "Direction" 1
3 "Sync01" 2
4 "Balance" 1
5 "Bip01 Spine" 4
6 "Bip01 Spine1" 5
7 "Bip01 Spine2" 6
8 "Bip01 Spine3" 7
9 "Bip01 Neck" 8
10 "Bip01 Head" 9
11 "Bip01 L Thigh" 1
12 "Bip01 R Thigh" 1
13 "Bip01 L Calf" 11
14 "Bip01 R Calf" 12
15 "Bip01 L Foot" 13
16 "Bip01 R Foot" 14
17 "Bip01 L Toe0" 15
18 "Bip01 R Toe0" 16
19 "Bip01 L Clavicle" 9
20 "Bip01 R Clavicle" 9
21 "Bip01 L UpperArm" 19
22 "Bip01 R UpperArm" 20
23 "Bip01 L Forearm" 21
24 "Bip01 R Forearm" 22
25 "Bip01 L Hand" 23
26 "Bip01 R Hand" 24
27 "Bip01 L Finger0" 25
28 "Bip01 R Finger0" 26
29 "Bip01 L Finger01" 27
30 "Bip01 R Finger01" 28
31 "Bip01 L Finger02" 29
32 "Bip01 R Finger02" 30
33 "Bip01 L Finger1" 25
34 "Bip01 R Finger1" 26
35 "Bip01 L Finger11" 33
36 "Bip01 R Finger11" 34
37 "Bip01 L Finger12" 35
38 "Bip01 R Finger12" 36
39 "Bip01 L Finger2" 25
40 "Bip01 R Finger2" 26
41 "Bip01 L Finger21" 39
42 "Bip01 R Finger21" 40
43 "Bip01 L Finger22" 41
44 "Bip01 R Finger22" 42
45 "Bip01 L Finger3" 25
46 "Bip01 R Finger3" 26
47 "Bip01 L Finger31" 45
48 "Bip01 R Finger31" 46
49 "Bip01 L Finger32" 47
50 "Bip01 R Finger32" 48
51 "Bip01 L Finger4" 25
52 "Bip01 R Finger4" 26
53 "Bip01 L Finger41" 51
54 "Bip01 R Finger41" 52
55 "Bip01 L Finger42" 53
56 "Bip01 R Finger42" 54
57 "Bip01 L ForeTwist" 21
58 "Bip01 R ForeTwist" 22
59 "Bip01 LUpArmTwist" 19
60 "Bip01 RUpArmTwist" 20
61 "Bip01 L Prop" 25
62 "Bip01 R Prop" 26
63 "face_ingame_jaw" 10
64 "face_ingame_r_upper_lip" 10
65 "face_ingame_r_lip" 10
66 "face_ingame_l_lip" 10
67 "face_ingame_l_upper_lip" 10
68 "face_ingame_l_upper_eyelid" 10
69 "face_ingame_l_outer_eyebrow" 10
70 "face_ingame_l_inner_eyebrow" 10
71 "face_ingame_r_outer_eyebrow" 10
72 "face_ingame_r_inner_eyebrow" 10
73 "face_ingame_r_upper_eyelid" 10
74 "face_ingame_r_eye" 10
75 "face_ingame_l_eye" 10
76 "face_ingame_r_lower_lip" 63
77 "face_ingame_l_lower_lip" 63
78 "CameraSync01" 0
79 "Bip01 L Hand Effector" 0
80 "Bip01 R Hand Effector" 0
81 "l_upperarm_twist" 0
82 "r_upperarm_twist" 0
83 "l_shoulder_joint" 0
84 "r_shoulder_joint" 0
85 "Jiggle_R_Colar" 20
86 "Jiggle_L_Colar" 19
87 "Jiggle_R_Cuff" 24
88 "Jiggle_L_Cuff" 23
89 "Jiggle_B_Waist" 5
90 "Jiggle_R_Waist" 5
91 "Jiggle_R_Waist_002" 0
92 "Jiggle_L_Waist" 5
93 "Jiggle_L_Waist_002" 0
94 "Jiggle_R_Leg" 12
95 "Jiggle_L_Leg" 11
96 "Jiggle_R_Shin" 14
97 "Jiggle_L_Shin" 13
98 "Jiggle_R_Hem" 16
99 "Jiggle_L_Hem" 15
100 "Bip01 Bag001" 0
101 "Jiggle_Wei_Hair01" 10
102 "Jiggle_Long_Necklace" 0
103 "Jiggle_Long_Necklace_02" 0
104 "Jiggle_Short_Necklace" 0
105 "Jiggle_Short_Necklace_02" 0
106 "Jiggle_Stomache" 0
107 "Jiggle_Jackie_Bag" 0
108 "Jiggle_Jackie_Phone" 0
109 "Jiggle_Jackie_Necklace" 0
110 "Jiggle_Jackie_Hair" 0
111 "Bip01_Jackie_Chain_001" 0
112 "Bip01_Jackie_Chain_002" 0
113 "Bip01_Jackie_Chain_003" 0
114 "Bip01_Calvin_Necklace_001" 0
115 "Bip01_Calvin_Necklace_002" 0
116 "Jiggle_R_Boob" 0
117 "Jiggle_L_Boob" 0
118 "Jiggle_Hair_Frnt" 0
119 "Jiggle_Hair_Bck" 0
120 "Jiggle_Hair_Lft" 0
121 "Jiggle_Hair_Rgt" 0
122 "Jiggle_B_Skirt_Rgt" 0
123 "Jiggle_B_Skirt_Lft" 0
124 "Jiggle_Hair_Ponytail" 0
end
skeleton
time 0
0 0.000000 -0.000000 0.998452 0.000000 -0.000000 -1.570795
1 0.000000 0.000000 0.000000 0.090661 -1.570796 -1.661456
2 -0.998452 0.000000 -0.000001 1.067801 -1.570451 2.073792
3 0.000000 0.000000 -0.000000 0.000000 -0.000000 0.000000
4 0.061026 -0.020621 0.000000 1.140897 -1.569705 2.000695
5 0.000000 -0.000000 -0.000000 -1.570797 -1.570796 -1.570797
6 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
7 0.120951 -0.000096 -0.000000 -0.000000 -0.000000 0.000000
8 0.120951 -0.000096 -0.000000 -0.000000 -0.000000 0.000000
9 0.128489 -0.019381 -0.000000 -0.000000 -0.000001 0.182813
10 0.077382 0.006895 0.000000 -0.000000 0.000000 -0.130540
11 -0.000000 0.000000 0.089957 -3.141027 -0.054466 -3.061052
12 0.000000 -0.000000 -0.089957 3.141030 0.054469 -3.061052
13 0.449787 -0.000000 0.000000 0.000000 0.000000 -0.000977
14 0.449787 0.000000 0.000000 -0.000000 -0.000000 -0.000977
15 0.447161 0.000000 -0.000000 -0.228498 -0.054245 0.081667
16 0.447161 0.000000 0.000000 0.228498 0.054246 0.081667
17 0.098783 0.133179 -0.001318 -0.000000 -0.000000 1.570796
18 0.098783 0.133179 0.001318 0.000000 -0.000000 1.570796
19 -0.039012 0.017390 0.037606 -0.944282 -1.403160 -2.387639
20 -0.039012 0.017390 -0.037606 0.944258 1.403165 -2.387663
21 0.164030 0.000000 0.000000 -0.036490 0.659105 -0.304214
22 0.164030 0.000000 -0.000000 0.036490 -0.659105 -0.304214
23 0.269872 0.000000 -0.000000 -0.000000 0.000000 -0.148916
24 0.269873 0.000000 0.000000 0.000000 -0.000000 -0.148916
25 0.257988 0.000000 0.000000 -1.880375 -0.019397 0.169870
26 0.257988 0.000000 -0.000000 1.880375 0.019397 0.169870
27 0.024097 0.004039 -0.034148 1.160342 0.687200 0.420147
28 0.024097 0.004039 0.034148 -1.160342 -0.687200 0.420147
29 0.040794 0.000000 0.000000 -0.000000 -0.000000 0.211794
30 0.040794 -0.000000 0.000000 0.000000 -0.000000 0.211794
31 0.034064 -0.000000 0.000000 0.000000 -0.000000 0.016612
32 0.034064 0.000000 0.000000 -0.000000 0.000000 0.016612
33 0.103943 -0.000469 -0.035487 -0.000819 0.235556 -0.000191
34 0.103943 -0.000468 0.035487 0.000819 -0.235556 -0.000191
35 0.034173 0.000000 -0.000000 -0.000000 -0.000000 0.085069
36 0.034173 0.000000 0.000000 0.000000 0.000000 0.085069
37 0.024721 0.000000 0.000000 0.000000 0.000000 0.092737
38 0.024721 -0.000000 -0.000000 -0.000000 -0.000000 0.092737
39 0.108053 0.000488 -0.009367 -0.153563 0.054423 0.031571
40 0.108054 0.000488 0.009367 0.153563 -0.054423 0.031572
41 0.039110 -0.000000 -0.000000 -0.000000 -0.000000 0.026296
42 0.039110 0.000000 0.000000 0.000000 0.000000 0.026296
43 0.028279 0.000000 0.000000 0.000000 0.000000 0.043986
44 0.028279 -0.000000 0.000000 0.000000 -0.000000 0.043986
45 0.101948 0.005554 0.016613 -0.231834 -0.118925 0.053755
46 0.101949 0.005554 -0.016613 0.231834 0.118925 0.053755
47 0.038861 0.000000 0.000000 -0.000000 0.000000 0.048242
48 0.038861 0.000000 -0.000000 -0.000000 0.000000 0.048242
49 0.027379 0.000000 -0.000000 -0.000000 -0.000000 -0.007270
50 0.027379 0.000000 0.000000 0.000000 -0.000000 -0.007270
51 0.093347 0.012723 0.037965 -0.216471 -0.261607 0.166656
52 0.093347 0.012724 -0.037965 0.216471 0.261607 0.166656
53 0.029315 0.000000 0.000000 -0.000000 -0.000000 0.001411
54 0.029315 0.000000 -0.000000 -0.000000 0.000000 0.001411
55 0.020510 -0.000000 -0.000000 0.000000 0.000000 0.077614
56 0.020510 0.000000 0.000000 -0.000000 -0.000000 0.077614
57 0.269872 0.000000 -0.000000 -0.156721 0.000000 -0.148916
58 0.269872 0.000000 0.000000 0.156722 -0.000000 -0.148916
59 0.164030 0.000000 0.000000 0.055100 0.659106 -0.304214
60 0.164030 0.000000 0.000000 -0.055100 -0.659105 -0.304214
61 -0.000000 -0.000000 -0.000000 -0.000000 -0.000000 -0.000000
62 0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
63 0.047304 0.043625 0.000000 3.141592 -0.000001 2.315846
64 0.036751 0.111929 -0.009477 2.953683 -1.569883 1.705637
65 0.032480 0.102163 -0.023402 2.953683 -1.569883 1.705637
66 0.032482 0.102158 0.023256 2.953683 -1.569883 1.705637
67 0.036752 0.111929 0.008951 2.953683 -1.569883 1.705637
68 0.105850 0.102149 0.031216 -0.523877 -1.570796 -1.099988
69 0.127614 0.087155 0.044827 -0.523877 -1.570796 -1.099988
70 0.126146 0.105804 0.013712 -0.523877 -1.570796 -1.099988
71 0.127614 0.087155 -0.045484 -0.811932 -1.570796 -0.811932
72 0.126240 0.106008 -0.014382 -0.523877 -1.570796 -1.099988
73 0.105850 0.102149 -0.027988 -0.523877 -1.570796 -1.099988
74 0.099929 0.081067 -0.028751 -3.141590 -1.483529 1.517725
75 0.099929 0.081067 0.028556 -0.000001 -1.483529 -1.623864
76 0.062223 0.033175 0.010326 0.849986 1.570796 -3.064284
77 0.062217 0.033175 -0.010183 1.738467 1.570451 -2.175804
78 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
79 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
80 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
81 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
82 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
83 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
84 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
85 0.031651 -0.058240 -0.061391 0.000000 0.000000 -0.000000
86 0.019416 -0.064813 0.035275 0.000000 -0.000000 -0.000000
87 0.184674 -0.000000 0.000000 -0.000000 0.000001 0.000000
88 0.185000 -0.000000 0.000000 -0.000000 0.000000 -0.000000
89 0.034000 -0.129245 -0.000000 -3.094408 -1.570796 1.522815
90 -0.022000 0.148000 -0.124000 -3.094408 -1.570796 1.522815
91 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
92 -0.022000 0.148000 0.115000 -3.094408 -1.570796 1.522815
93 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
94 0.000000 0.000000 0.000000 -0.000000 0.000000 0.000000
95 0.000000 -0.000000 -0.000000 -0.000000 0.000000 -0.000000
96 0.253332 -0.009209 -0.005665 -3.136642 0.054246 0.081667
97 0.253414 -0.009210 0.004172 3.050716 1.516326 -0.009345
98 -0.000000 0.000000 0.000000 -0.000003 0.000000 -0.000000
99 -0.000000 0.000000 0.000000 -0.000000 -0.000000 0.000000
100 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
101 0.215375 0.091877 0.000000 3.097516 -1.570796 1.561804
102 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
103 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
104 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
105 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
106 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
107 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
108 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
109 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
110 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
111 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
112 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
113 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
114 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
115 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
116 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
117 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
118 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
119 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
120 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
121 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
122 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
123 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
124 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
end
```
## Post #9
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-19T06:20:08+00:00
- Post Title: Havok binary files

> Reply from shakotay2
>
> Think of a zipped file. You'll need to know the decompression algo to decompress it.
Ah, okay. I was thinking of something along those lines but wasn't exactly sure.

So it's basically a formula used to convert binary values to numbers? Because I think I saw something related to that.
We have an insane amount of information that we were incredibly lucky to get, I'm certain it's in there somewhere.


Thanks for the smd by the way. Did you find a method to automate the process or is it still done manually?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-19T21:07:41+00:00
- Post Title: Havok binary files

> Reply from SergeantJoe
>
> So it's basically a formula used to convert binary values to numbers? Because I think I saw something related to that.
We have an insane amount of information that we were incredibly lucky to get, I'm certain it's in there somewhere.yeah, we would need the formulae or we could use the Havok Content Tools with 3dsmax 



Havok_spline_compression.JPG (61.53 KiB) Viewed 628 times


and save two version of an animation: spline compressed and uncompressed. Then compare the outputs to each other. That's the idea.
But it's just a hobby of mine and I'm too busy with real life than to expect having this solved too soon.
Maybe there's a solution somewhere in the inet?

> Did you find a method to automate the process or is it still done manually?It's half automated, three offsets to be searched manually. But that's of very low priority since some basic skeletons are sufficient, aren't they?
(If you need another one to be transformed feel free to PM it. That's normally a 5 minutes job to transform it.)
## Post #11
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-19T21:16:52+00:00
- Post Title: Havok binary files

> Reply from shakotay2
>
> or we could use the Havok Content Tools with 3dsmax and save two version of an animation: spline compressed and uncompressed. Then compare the outputs to each other.
You know, this just might be the idea that solves the whole problem.

Even with university I got a ton of time on my hands, I'll definitely try this out. 
Is there a specific place or link where I can get those tools? I tried searching but only found technical problem forum threads about them.

> Reply from shakotay2
>
> But that's of very low priority since some basic skeletons are sufficient, aren't they?
Of course. We have all the skeletons we need, but I thought it was necessary to have one in hkx ascii to load in the Havok Standalone tool. 

Luckily it seems we don't need that program anymore though since it's possible to convert hkx straight to smd.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-19T21:30:54+00:00
- Post Title: Havok binary files

> Reply from SergeantJoe
>
> Even with university I got a ton of time on my hands, I'll definitely try this out.yeah, that was the time when life was sooo easy. 

> Is there a specific place or link where I can get those tools? I tried searching but only found technical problem forum threads about them.
I'm not too sure but guess I got them from here:
[https://software.intel.com/sites/havok/en/](https://software.intel.com/sites/havok/en/)
## Post #13
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-19T21:50:53+00:00
- Post Title: Havok binary files

Alright, perfect. Let's see how this goes.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2015-05-20T05:34:07+00:00
- Post Title: Havok binary files

Oh, out from the shadows I emerge.

Havok, huh? Personally I'm interested in the old format used by Bioshock 1 and 2. 4.1.0-r1 if I recall correctly. I know UE Viewer supports the mesh plus the model but never heard of the HKX animations being cracked. Tried available tools and got a half-way XML conversion but all animations get nulled of course due to it being archaic compared to the HKX version used in Sonic Generations and Skyrim.

And... of course the tools aren't quite designed to read skeletons from an Unreal skeletalmesh. Oh Bioshock, such a crazy hybrid you are.

Anywho, interested to see what comes of this.
## Post #15
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-20T07:51:36+00:00
- Post Title: Havok binary files

Man, you have no idea how happy I am to have you here. For over two years now it's been just the me, Bastien, and now once again Shako. To have someone else even as a spectator is an unprecedented event.



Also, I had a thought. [There is already a program that can convert SplineCompressedAnimations from binary to ascii format.](http://www.nexusmods.com/skyrim/mods/1797/)

It's intended for 2010 files though. We can't just give it 2013 files unless we remove some data at the beginning, so I don't know how reliable that is.


[But we can take a look at the source code](https://github.com/figment/hkxcmd) and see what decompression algorithm it uses, that'll give us a place to start at least.


EDIT: Yup, if I give the 2010 converter a 2011 file it converts but gives odd results, and 2013 doesn't work at all.

Also if you use it's report feature, you get some pretty interesting stuff.

```
VTable:	FALSE
Name:	hkaSplineCompressedAnimationTrackCompressionParams
Parent:	HK_NULL
Size:	28
#IFace:	0
#Enums:	2
 000	RotationQuantization (POLAR32=0;THREECOMP40=1;THREECOMP48=2;THREECOMP24=3;STRAIGHT16=4;UNCOMPRESSED=5) {00000000}
 001	ScalarQuantization (BITS8=0;BITS16=1) {00000000}
#Members:	12
 000	rotationTolerance,HK_NULL,HK_NULL,hkReal,0000000b,00000000,0,00000000,0,HK_NULL,HK_NULL
 001	translationTolerance,HK_NULL,HK_NULL,hkReal,0000000b,00000000,0,00000000,4,HK_NULL,HK_NULL
 002	scaleTolerance,HK_NULL,HK_NULL,hkReal,0000000b,00000000,0,00000000,8,HK_NULL,HK_NULL
 003	floatingTolerance,HK_NULL,HK_NULL,hkReal,0000000b,00000000,0,00000000,12,HK_NULL,HK_NULL
 004	rotationDegree,HK_NULL,HK_NULL,hkUint16,00000006,00000000,0,00000000,16,HK_NULL,HK_NULL
 005	translationDegree,HK_NULL,HK_NULL,hkUint16,00000006,00000000,0,00000000,18,HK_NULL,HK_NULL
 006	scaleDegree,HK_NULL,HK_NULL,hkUint16,00000006,00000000,0,00000000,20,HK_NULL,HK_NULL
 007	floatingDegree,HK_NULL,HK_NULL,hkUint16,00000006,00000000,0,00000000,22,HK_NULL,HK_NULL
 008	rotationQuantizationType,HK_NULL,RotationQuantization,enum RotationQuantization,00000018,00000004,0,00000000,24,HK_NULL,HK_NULL
 009	translationQuantizationType,HK_NULL,ScalarQuantization,enum ScalarQuantization,00000018,00000004,0,00000000,25,HK_NULL,HK_NULL
 010	scaleQuantizationType,HK_NULL,ScalarQuantization,enum ScalarQuantization,00000018,00000004,0,00000000,26,HK_NULL,HK_NULL
 011	floatQuantizationType,HK_NULL,ScalarQuantization,enum ScalarQuantization,00000018,00000004,0,00000000,27,HK_NULL,HK_NULL
Version:	0
```


Which matches the info from the 2013 PBD perfectly!

```
{
  BITS8 = 0x0,
  BITS16 = 0x1,
};

/* 2852 */
enum hkaSplineCompressedAnimation::TrackCompressionParams::RotationQuantization
{
  POLAR32 = 0x0,
  THREECOMP40 = 0x1,
  THREECOMP48 = 0x2,
  THREECOMP24 = 0x3,
  STRAIGHT16 = 0x4,
  UNCOMPRESSED = 0x5,
};

/* 26472 */
struct hkaSplineCompressedAnimation::TrackCompressionParams
{
  float m_rotationTolerance;
  float m_translationTolerance;
  float m_scaleTolerance;
  float m_floatingTolerance;
  unsigned __int16 m_rotationDegree;
  unsigned __int16 m_translationDegree;
  unsigned __int16 m_scaleDegree;
  unsigned __int16 m_floatingDegree;
  hkEnum<enum hkaSplineCompressedAnimation::TrackCompressionParams::RotationQuantization,unsigned char> m_rotationQuantizationType;
  hkEnum<enum hkaSplineCompressedAnimation::TrackCompressionParams::ScalarQuantization,unsigned char> m_translationQuantizationType;
  hkEnum<enum hkaSplineCompressedAnimation::TrackCompressionParams::ScalarQuantization,unsigned char> m_scaleQuantizationType;
  hkEnum<enum hkaSplineCompressedAnimation::TrackCompressionParams::ScalarQuantization,unsigned char> m_floatQuantizationType;
};

```


If that's not the key then I'll eat my hat.
## Post #16
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-30T01:51:18+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Even with university I got a ton of time on my hands
Welp, I completely ate my words, as soon as I said that finals week started. 


Although here's a cool little sidenote: every day on the bus I would have a laptop with no access to heavy hardware like Max. 
But over time I managed to create a small program that automatically splits .bin files into hkx files, so I can get samples much easier or so people can get their own.



- > 




[EXECUTABLE](http://www.mediafire.com/download/yka0kn7jskkv4f5/SDDE_hkxSeparator.jar)
[SOURCE CODE](http://www.mediafire.com/view/acn95tbo4s9c426/SleepingDogsAnimationSeparator.java)


It does NOT do any conversion though, just separates the files. That's up next, as soon as I get these Max scripts working!

If we figure out the process, I could even add a function that not only extracts them but converts them directly to SMD! Although that may be a bit too optimistic.


Also, is nobody going to look at the [smoking gun I posted](http://forum.xentax.com/viewtopic.php?p=106266#p106266)?

Theoretically we don't need to search for the decompression algorithm because we already have it.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-30T06:29:44+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Also, is nobody going to look at the smoking gun I posted?I did, especially at

> If that's not the key then I'll eat my hat.
and I didn't want to tell you: "sorry for your hat, mate"  
because what you have is a log, nothing more and nothing less.

The key would be, imho, to have hkxcmd recompiled using the suiting Havok SDK.

What I managed so far is to compile it with the 2010 SDK.
To come next will be a recompile with the 2013 SDK but I wouldn't wonder if I failed.

Also I find it totally annoying to have thousands of code lines compiled just to handle
a stupid compressed animation (hkaSplineCompressedAnimation).

It should be as simple as the hkx2smd conversion I did without any f...... library but the compression algo seems to be burried in hkaAnimation.lib.

That's the only reason why I care for this Havok shit.
## Post #18
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-30T08:02:55+00:00
- Post Title: Re: Havok binary files

> Reply from shakotay2
>
> and I didn't want to tell you: "sorry for your hat, mate"  
because what you have is a log, nothing more and nothing less.
Oh, well then. Now I know. 

Even a disappointing answer is better than no answer at all.

> Reply from shakotay2
>
> The key would be, imho, to have hkxcmd recompiled using the suiting Havok SDK.
That's exactly what I was trying to get at. If all the logs are the same for 2010/2013, then I'd wager the compression algorithm is the same as well.

I've already compared the differences between the 2010 and 2013 files, they are almost exactly the same except for some extra data at the top of the 2013 ones.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-30T08:46:02+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> shakotay2 wrote:I've already compared the differences between the 2010 and 2013 files, they are almost exactly the same except for some extra data at the top of the 2013 ones.I tried to load your uploaded BrawlerA.hkx (with the first 0xDE bytes cut) into Havok ToolStandAlone (2013) and this is the error message it purges: 

Havok Preview Asset
---------------------------
Wrong platform for packfile

Then I compared two hk_2010 files, GirlSkeleton and muscle03 where the first is loaded and the latter fails with the same error as above.
These are the bytes in the header that are different:



hk_2010.1.0-r1.JPG (167.89 KiB) Viewed 259 times



Once I'll get the muscle loaded I'll try it with a compressed animation.

Patching the BrawlerA just causes CTDs.
Maybe you could code a tool that logs the hkx headers? Should not be too hard.

Once we have that we could write a tool to create hkx headers.


edit: recompiling with Havok SDK 2013 (as if I knew it  )

got hundreds of errors because of missing defines such as
HK_REFLECTION_DEFINE_SIMPLE, HK_REFLECTION_DEFINE_VIRTUAL which where used in 2010's SDK
and seem to have gone away with SDK 2013

After I fixed that the next error popped up:
fatal error C1083: Cannot open include file: 'Physics/Dynamics/Entity/hkpRigidBody.h': No such file or directory

so it's gonna going to be an endless story (as always with Havok, niflib and so on)

After having copied dozens of folders from 2010's SDK to 2013 (it's not the very best idea to force backwards compatibility, I know  )
I got syntax errors and that's the point where I state: too annoying to continue.

Maybe I should start with a simple "compressed animation sample" from SDK 2013, if so.

To be clear: figment is a great coder, so is his hkxcmd tool for 2010 hkx.

Havok is a great SDK, too. But seems you'll have to start from scratch for 2013 hkx (although having a working project for 2010 ones).
That's ridiculous. (or I'm simply too dumb, maybe  )
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-30T13:30:47+00:00
- Post Title: Re: Havok binary files

yeah, animated skeletons:



AnimatedSkel.JPG (43.13 KiB) Viewed 250 times


(looking later whether they're compressed)
## Post #21
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-05-30T19:56:52+00:00
- Post Title: Re: Havok binary files

Hmm, so hkxcmd is a bust no matter what?


And I already search for the animation headers, so yeah it's pretty easy to write them all to a separate log file. 

But wait, by header do you mean all the data up to "WààW", or the entire block up to offset 0x0230?
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-30T20:20:57+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Hmm, so hkxcmd is a bust no matter what?
it's ok for 2010-hkx but not worth for me to adapt it for 2013-hkx files. There are too many changes in the code from 2010's to 2013's SDK.

> And I already search for the animation headers, so yeah it's pretty easy to write them all to a separate log file. 
>
> 
>
> But wait, by header do you mean all the data up to "WààW", or the entire block up to offset 0x0230?
I meant all the bytes from "WààW" up to "hkClass".
But "logging" was the wrong term, what I meant was "analyzing" so that we could create a working fake header for muscle03.hkx for example.

So we need to know what the data at offsets 0x0C and 0x10 for example means.
## Post #23
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-06-03T08:10:24+00:00
- Post Title: Re: Havok binary files

it is possible to have animations of Dark Souls?
## Post #24
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-03T09:30:33+00:00
- Post Title: Re: Havok binary files

Maybe! What version do they use? 

PM me a few samples and I can take a look.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-04T06:46:38+00:00
- Post Title: Re: Havok binary files

> Reply from dibe91
>
> it is possible to have animations of Dark Souls?Do you have a skeleton?
Makes no sense to ask for animations if you don't have a skeleton, imho:



c2310_hkx.JPG (95.35 KiB) Viewed 191 times

(version: hk_2010.2.0-r1)
## Post #26
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-06-04T17:56:00+00:00
- Post Title: Re: Havok binary files

> Reply from shakotay2
>
> dibe91 wrote:it is possible to have animations of Dark Souls?Do you have a skeleton?
Makes no sense to ask for animations if you don't have a skeleton, imho:
c2310_hkx.JPG(version: hk_2010.2.0-r1)

sure.I have everything I need.you may only be passed havok tools? I can not find them!
## Post #27
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-09T23:11:28+00:00
- Post Title: Re: Havok binary files

The havok tools are [here](https://software.intel.com/sites/havok/en/).
## Post #28
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-06-10T03:48:31+00:00
- Post Title: Re: Havok binary files

I used the sdk demoes to get the animations out
just load the respective files in the skeletal animation demo. They need to be PC I couldnt get the ps3 versions  to work
then read the data
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-10T07:13:30+00:00
- Post Title: Re: Havok binary files

So then try to read the attached file (from the opening post with data before 57 E0 E0 57 cut) and you'll be an alltime hero.  
Its endian signature at 0x11: 01 says: I'm a little endian file.
Nethertheless I could not load it using the havok sdk.

(Debugging is very time consuming - you need to go through assembler code because of missing sources such as hkload.cpp and so on.)


 BrawlerA-cut.zip
(7.97 KiB) Downloaded 32 times



@SergeantJoe: just to be sure: your uploaded hkx are PC files, aren't they?
## Post #30
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-10T09:53:39+00:00
- Post Title: Re: Havok binary files

Yes, all my files are PC.
## Post #31
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-06-11T15:00:49+00:00
- Post Title: Re: Havok binary files

a question ... you can bring your animations on 3d studio max 2011? and if possible, you can even to match the skin of the model with the skeleton?
## Post #32
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-06-13T01:26:44+00:00
- Post Title: Re: Havok binary files

Sorry I forgot to check back. I converted the files to a custom animation type then bvh then imported to Motion Builder 2012 then fbx.
Long winded. 
Can I post my code instead of looking at the files? I will also try looking at the files
## Post #33
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-13T03:25:57+00:00
- Post Title: Re: Havok binary files

By all means, please do. We need anything we can get.
## Post #34
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-06-13T04:40:43+00:00
- Post Title: Re: Havok binary files

I am assuming you can compile and run the havok sdk demo
Also assuming BrawlerA.hkx is the name of your skeleton file?

It is a long piece of code but you only need minimal adjustment
You can also change the conversion type

The compile time might be a bit long as we are re-purposing their demo project
replace 
> D:\hk2014_1_0_r1\Demo\Demos\Animation\Api\Playback\AnimatedSkeleton\AnimatedSkeletonDemo.cpp with this

[code here](http://pastebin.com/f6ZztsKf)

```
hkStringBuf assetFile("BrawlerA.hkx"); //loads skeleton

//line 1276
ofstream ofile("BrawlerA.skel", ios::binary); //saves skeleton in new format


//Line 1313 - 1316 (Read anim directory and create export folder)
char outfile[MAX_PATH] =  "F:/inAnimations/"; //Our animation folder
strcat(outfile,animfile.c_str());

char workdir[MAX_PATH] = "F:/OutAnimations/"; //output folder
strcat(workdir,animfile.c_str());

```


```
class AnimatedSkeletonDemo : public hkDefaultAnimationDemo
{
	public:

		HK_DECLARE_CLASS_ALLOCATOR( HK_MEMORY_CLASS_DEMO );

		AnimatedSkeletonDemo( hkDemoEnvironment* env );

		~AnimatedSkeletonDemo();

		Result stepDemo(); 

	private:

		class hkLoader* m_loader;

		class hkaSkeleton* m_skeleton;

		class hkaAnimation* m_animation;

		class hkaAnimationBinding* m_binding;

		hkArray<class hkaAnimatedSkeleton*> m_activeSkeletons;

};

```


I will get vS2012 in the mean time and test it myself
## Post #35
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-13T06:00:13+00:00
- Post Title: Re: Havok binary files

> Reply from JohnHudeski
>
> I am assuming you can compile and run the havok sdk demo
I cannot unfortunately. All my stuff is set up for Java, not C++.

Also, where exactly is the sdk demo located? Now that university is finally over I have a lot more time, I can probably get Visual Studio up and running soon.
## Post #36
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-06-13T06:51:43+00:00
- Post Title: Re: Havok binary files

google havok sdk.
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-14T11:40:48+00:00
- Post Title: Re: Havok binary files

> Reply from JohnHudeski
>
> I am assuming you can compile and run the havok sdk demo
Also assuming BrawlerA.hkx is the name of your skeleton file?yep. But it's very likely that it's not a matter of using the SDK but a matter of how hkx format was modified by SleepingDogs devs.

BrawlerA.hkx can not be loaded, as simple as that. (And I've no interest to debug the problem due to some missing sources as said above.)

@SergeantJoe: remember what I said (post as of May 19th) about recreating hkx using Havok Content Tools with 3dsmax?
Why not use the BrawlerA smd for it? Then compare the headers of the created hkx with the one of the unloadable SD BrawlerA hkx?
## Post #38
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-14T21:24:45+00:00
- Post Title: Re: Havok binary files

Yup, I haven't forgotten about that! Like I said I have a lot more time now so I should have those ready today or tomorrow.
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-14T21:30:38+00:00
- Post Title: Re: Havok binary files

accidentally I managed to do it, but the created file is an hkt, not hkx:



hk_2013.1.0-r1-hkt.JPG (61.15 KiB) Viewed 222 times


Also for some reason the skeleton is not visible in the standalone tool (ToolStandAlone.exe).

This might be caused by the fact that I imported the BrawlerA smd from this thread into blender,
exported as FBX and reimported to max before using the HavokContentTools plugin.

(the hkt version is said to be hk_2013.1.0-r1 - dunno how to make a .2.0-r1 of it.)

(maybe 1.0= hkt, 2.0= hkx?)
## Post #40
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-18T00:25:37+00:00
- Post Title: Re: Havok binary files

I'm pretty sure 2013.1.0 is the version number of the tools. If you look on the download page they have 2012.1.0 and 2012.2.0,but interestingly enough no 2013.2.0.
## Post #41
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-18T04:26:23+00:00
- Post Title: Re: Havok binary files

Okay, so. I got the content tools, but I can't seem to export anything properly. There's all sorts of garbage in the file, but no actual animation info even though it's in the view XML modifier.

Also, to get an hkx you need to select Packfile in Write to Platform.
## Post #42
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-24T04:09:32+00:00
- Post Title: Re: Havok binary files

I got the SDK and VS set up, but I'll need john to give some more details. 

I sent him a PM, but until he comes back we gotta figure this out. I got myself an hkx file, but it seems to be creating model and skeleton files, not animations.
## Post #43
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-06-26T15:51:58+00:00
- Post Title: Re: Havok binary files

Sorry I've been away (battling being broke and the blues lol)
If you have a detailed animation format of choice that is easy to replicate (basically good documentation)
I will attempt a conversion tomorrow (Saturday)
## Post #44
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-26T21:35:41+00:00
- Post Title: Re: Havok binary files

I already said this in my PM but I'll say it again here so people can see: [Source Engine SMD](https://developer.valvesoftware.com/wiki/SMD) is easily the best format out there for this situation. 

It's very simple, and is stored in plain ASCII to boot. It can contain mesh, UVs, bones, weights, and animations, all in the same file. 

Plus every major 3D software already has plugins for it. That includes the big 3 - Blender/Max/Maya.
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-05T22:11:31+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Okay, so. I got the content tools, but I can't seem to export anything properly. There's all sorts of garbage in the file, but no actual animation info even though it's in the view XML modifier.don't know what you did exactly but if you load a skeleton and its animation into 3dsmax an hkx export should be possible.

I tried Adria and her walking animation and exported it spline compressed correctly.

Only problem I have is that I didn't manage to export the skeleton and the animation seperately -
they are in one hkx file:



AdriaWalk.JPG (140.49 KiB) Viewed 128 times


(minor problem: how to get rid of the collision sphere?)
## Post #46
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-07-05T22:35:19+00:00
- Post Title: Re: Havok binary files

> Reply from shakotay2
>
> I tried Adria and her walking animation and exported it spline compressed correctly.

Only problem I have is that I didn't manage to export the skeleton and the animation seperately -
they are in one hkx file
But it should be enough right? Wasn't the whole point was to compare compressed vs noncompressed?
## Post #47
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-05T23:02:33+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> But it should be enough right? Wasn't the whole point was to compare compressed vs noncompressed?yep, to compare the headers, so that one could fake the header of a SD anim to get it loaded by the Havok Standalone tool.

Up to offset 0x269 there are few different bytes only in the headers of Adria's compr/uncompr anim files (between the strings __types__  and hkClass) but for THG_BRW_STR_Haymaker.hkx for example it's totally different.

So I guess there's little chance to have this hkx anim ever loaded into the standalone tool.
## Post #48
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-07-08T16:21:10+00:00
- Post Title: Re: Havok binary files

So I got my lazy ass to work on it this morning
couldnt even open the files
Kept getting a "access Violation reading location 0x00000004"
Not sure if the file is at fault or I am

```
    m_skeleton = ac->m_skeletons[0];  //This line fails

```


WTF

How did you guys get the first SMD file?
## Post #49
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-07-08T18:45:26+00:00
- Post Title: Re: Havok binary files

What do you mean? Could you give some more details?

What is this exactly, what file are you opening?
## Post #50
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-07-09T17:12:35+00:00
- Post Title: Re: Havok binary files

I mean how was anyone able to convert the skeleton into a SMD file?
## Post #51
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-07-09T19:39:40+00:00
- Post Title: Re: Havok binary files

Only shakotay can do that, although he did it mostly by hand and never explained how.


If you're stuck, just skip the skeleton extraction for now and use [the existing one.](http://forum.xentax.com/viewtopic.php?p=106227#p106227) All these specific anims use the same skeleton anyway.
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-10T13:14:29+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Only shakotay can do that, although he did it mostly by hand and never explained how.there are at least 10 people in this forum who can/could do this but noone explained how to do it.
Anyway, it will be part of my skel2smd exporter which will be released sooner or later.
## Post #53
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-07-12T13:14:16+00:00
- Post Title: Re: Havok binary files

I wish the error was more explicit
## Post #54
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-07-12T21:32:04+00:00
- Post Title: Re: Havok binary files

Just in case, could you quickly detail your previous long-winded method? 

I wasn't able to nab the code you posted before it got taken down.
## Post #55
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-01-02T16:10:33+00:00
- Post Title: Re: Havok binary files

Welp, Hudeski and Bastien are officially gone for good. I've lately been trying this myself again, and looking at this: 

> Reply from Skykila
>
> there is a utility AssetCc2 (hkSDK_Root\Tools\BatchProcess\AssetCc). It can convert any erialized .HKX file to xml .hkx
It seems to be legit, but I can't quite get it working. I tried cutting out the starting data, changing the version number, etc. Nothing worked. 
I was using the 2014 build of the tool with 2013 files, so as I went to try the 2013 tool I discovered [it is now impossible to get the Havok SDK at all!](http://www.havok.com/pcxs_redirect/)

What now? 

I really don't want to stoop to paying someone money to help but at this rate it seems inevitable. If it will even work.
## Post #56
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-11T11:50:44+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Welp, Hudeski and Bastien are officially gone for good."officially gone"? What does that mean?

> It seems to be legit, but I can't quite get it working.Same here. I used AssetCc1.exe (Asset Converter Collection) from hk2013_1_0_r1 - SDK on an hkx with the header hk_2013.2.0-r1 and it says:
"Unsupported file format.
Perhaps this file is not a binary or xml packfile or a tagfile."
Same with hk2014_1_0_r1 SDK, and I've never seen an hk_2013.2.0-r1 SDK, iirc (but there was an hk2012_2_0_r1 SDK).

> as I went to try the 2013 tool I discovered it is now impossible to get the Havok SDK at all!My hopes were Havok were gone forever, really!  but

look here: [http://forum.keenswh.com/threads/havok- ... o.7374695/](http://forum.keenswh.com/threads/havok-content-tools-no-longer-available-what-to-do.7374695/)
It says: "it seems Microsoft acquired Havok from Intel" ( ---> it also seems my sig comes true )

> What now?Wait for an official offer from MS.

btw: anyone experienced with SDKs and animation may ask himself: what do these guys fool around and don't seem to get a proper solution with a working SDK?
The problem is this: look at the header of hkRig_L4101.hkx (in hk2013_1_0_r1\Demo\Demos\Resources\Animation\HavokGirl) for example with the version tag (before __classnames__) overwritten by FFFF...

It's totally different compared to the BrawlerA hkx we're fooling around with. Its header signature is hk_2013.2.0-r1 and when trying to load it there's this error message:
Util\hkLoader.cpp(87): [0x3BF82A57] Warning: Wrong platform for packfile

(Trying to track down the error in the assembly (yes, no source available for that in the SDK) is not worth wasting my lifetime.  )

(The idea was to replace the header of BrawlerA with a suiting one but I guess that doesn't make much sense since the whole file's structure appears to be different.)

Atm I'm quarreling creating a BrawlerA.hkx from the brawler SMD in this thread:



Brawler_hkx.JPG (75.51 KiB) Viewed 135 times


It is not loaded by the SDK though having this damned hk_2013.1.0-r1 header.
Now it complains that no skeleton is loaded. (really f... hate it.  )

(ahh, see, I'm reproducing information, that I gave 6 months ago. Sry for that.  )

Reviewing my successful test with Adria (where creation of a compressed havok animation was possible) I've come
to the conclusion that the actual problem must be related to the brawler's bones.

Maybe there's too many of them connected to the root?
## Post #57
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-01-11T19:38:38+00:00
- Post Title: Re: Havok binary files

> Reply from shakotay2
>
> Maybe there's too many of them connected to the root?
Possibly. You could try just deleting those jiggle ones and reimporting the SMD.
## Post #58
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-02-29T04:49:02+00:00
- Post Title: Re: Havok binary files

I made this for dark souls hkx files, maybe its applicable:

[https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases)

Place hkx converter "SSFADF.exe" in root of hkx animation directory, double-click, it will recursively search for all animations (*.hkx except Skeleton.hkx and Skeleton-out.hkx)
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-29T09:30:52+00:00
- Post Title: Re: Havok binary files

For hkx files  with this header (which I was referring to in my last post):

```
00000 57 E0 E0 57 10 C0 C0 10  00 00 00 00 0B 00 00 00 WààW.ÀÀ.........
00010 08 01 00 01 03 00 00 00  02 00 00 00 00 00 00 00 ................
00020 00 00 00 00 4B 00 00 00  68 6B 5F 32 30 31 33 2E ....K...hk_2013.
00030 32 2E 30 2D 72 31 00 FF  00 00 00 00 FF FF FF FF 2.0-r1.ÿ....ÿÿÿÿ
```

SSFADF.exe says "bad file"
## Post #60
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-03T21:01:30+00:00
- Post Title: Re: Havok binary files

Oh right, that .exe reads files up to 2012.2, sorry!
## Post #61
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-03-04T06:31:17+00:00
- Post Title: Re: Havok binary files

> Reply from Snaz
>
> I made this for dark souls hkx files, maybe its applicable:

https://github.com/Danilodum/dark_souls_hkx/releases

Place hkx converter "SSFADF.exe" in root of hkx animation directory, double-click, it will recursively search for all animations (*.hkx except Skeleton.hkx and Skeleton-out.hkx)

> Reply from shakotay2
>
> For hkx files  with this header (which I was referring to in my last post):
Code: Select allOffset 0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
00000 57 E0 E0 57 10 C0 C0 10  00 00 00 00 0B 00 00 00 WààW.ÀÀ.........
00010 08 01 00 01 03 00 00 00  02 00 00 00 00 00 00 00 ................
00020 00 00 00 00 4B 00 00 00  68 6B 5F 32 30 31 33 2E ....K...hk_2013.
00030 32 2E 30 2D 72 31 00 FF  00 00 00 00 FF FF FF FF 2.0-r1.ÿ....ÿÿÿÿ
SSFADF.exe says "bad file"

Hot damn, this could finally be it!

Files from the original game are dated 2011. If you cut out all the data before WaaW, and change 2011 to 2010, [hkxcmd](http://www.nexusmods.com/skyrim/download/37272) can now process them! [Example](http://puu.sh/nud6I/5df0a855f0.zip) (.bin is the original file, .hkx is the 2011->2010, -out.hkx is the processed file)

SSFADF recognizes them, but does not think they are animations for some reason. I also can't seem to load it in the standalone tool.
## Post #62
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-05T23:20:13+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> Snaz wrote:I made this for dark souls hkx files, maybe its applicable:

https://github.com/Danilodum/dark_souls_hkx/releases

Place hkx converter "SSFADF.exe" in root of hkx animation directory, double-click, it will recursively search for all animations (*.hkx except Skeleton.hkx and Skeleton-out.hkx)
shakotay2 wrote:For hkx files  with this header (which I was referring to in my last post):
Code: Select allOffset 0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
00000 57 E0 E0 57 10 C0 C0 10  00 00 00 00 0B 00 00 00 WààW.ÀÀ.........
00010 08 01 00 01 03 00 00 00  02 00 00 00 00 00 00 00 ................
00020 00 00 00 00 4B 00 00 00  68 6B 5F 32 30 31 33 2E ....K...hk_2013.
00030 32 2E 30 2D 72 31 00 FF  00 00 00 00 FF FF FF FF 2.0-r1.ÿ....ÿÿÿÿ
SSFADF.exe says "bad file"

Hot damn, this could finally be it!

Files from the original game are dated 2011. If you cut out all the data before WaaW, and change 2011 to 2010, hkxcmd can now process them! Example (.bin is the original file, .hkx is the 2011->2010, -out.hkx is the processed file)

SSFADF recognizes them, but does not think they are animations for some reason. I also can't seem to load it in the standalone tool.

Both hkxcmd and ssfadf can process up to 2012.2 hkx files,  also, I don't believe ssfadf works well on xml
## Post #63
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-03-06T00:21:50+00:00
- Post Title: Re: Havok binary files

Nope, hkxcmd only supports 2010. It will take a 2011 file without a word, but then doesn't write anything.

I changed the version to 2010, converted the files with hkxcmd, then shoved the converted data into the structure used by Dark Souls files, and it WORKS!





Somewhat. The skeleton is 100% perfect, but the anim is all funky. It's like none of the bones move except the core one.

EDIT: I even managed to get the root motion! You can clearly see the base animation, but it's just not moving all the bones for some reason.
## Post #64
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-06T20:56:23+00:00
- Post Title: Re: Havok binary files

You're right havok goes up to 2010. Maybe this could help [https://github.com/Highflex/havok2fbx/releases](https://github.com/Highflex/havok2fbx/releases)

havok2fbx reads up to 2012
## Post #65
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-03-06T21:51:30+00:00
- Post Title: Re: Havok binary files

havok2fbx only works with 2014.1.0, it even specifically says so. But, all it takes is a quick rename from 2010 to 2014, and it works! 

However, once again the skeleton is perfect but the anim is borked, in the exact same manner. What the heck is going on here?


An interesting point, is that if I removes bones from the transformTrackToBoneIndices array in hkaAnimationBinding those bones will not be affected by the animation, leaving them in their normal pose.
So, I'm fairly sure the format conversion is all correct, it must be the animation data itself that is doing that. Could it have gotten messed up during the binary->xml conversion? 

I tried changing the header data and got SDAFS.exe to accept the binary file, but it crashes. Probably because the file has an hkaDefaultAnimatedReferenceFrame and lacks an hkaAnimationContainer and hkRootLevelContainer.
Do you think it would be possible to upload the source to the exe as well instead of just the dll? Maybe I can modify the program to only look for the anim data and nothing else.


Or could it be something else that's locking them at zero? I did notice the DS skeleton had the lockTranslation values all set to false, but changing that doesn't do anything.
## Post #66
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-07T20:13:21+00:00
- Post Title: Re: Havok binary files

All I did was mix hkxcmd and havok2fbx a bit so I could get to the animation key data. Here you go: 

[https://github.com/Danilodum/dark_souls_ssfdaf](https://github.com/Danilodum/dark_souls_ssfdaf)

You'll need this too [https://www.dropbox.com/s/uxfu2bkm907gx ... r1.7z?dl=0](https://www.dropbox.com/s/uxfu2bkm907gx32/hk2012_2_0_r1.7z?dl=0) , but this still won't do you much good, best would be to get the sdk havok2fbx uses and use that one to write something like ssfdaf, try asking highflex for the sdk
## Post #67
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-03-08T06:28:16+00:00
- Post Title: Re: Havok binary files

I switched hkaAnimationBinding blendHint from NORMAL to ADDITIVE just for giggles, and the animation is all there!




The hkx file structure is correct, but it's like all the bones are being rotated 90 degrees in the wrong direction. Fuck! I tried messing with the skeleton direction and animation binding, but no dice. I don't know what else to try at this point. 


However it's worth noting, in the Havok SDK and Content Tools there are programs called AssetCc. Those can convert from binary to XML, and XML back to binary. 
Unfortunately it gives the same exact result as a file converted with hkxcmd. 

I do suspect the problem here is version mismatching. 
All the files are 2011.2 while hkxcmd is 2010.2, the AssetCc I have from Snaz's SDK is 2012.2, and my content tools are 2014.1. Really wish there was a full download page somewhere.
## Post #68
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-04-04T11:15:27+00:00
- Post Title: Re: Havok binary files

You think I'm just going to give up when we're the closest we've been in four years? HA!

A complete breakdown of AssetCc:

```
AssetCc1.exe --strip --rules8011 xml.hkx bin.hkx
```

Conversion back and forth between binary/xml!

-The difference between Cc1 and Cc2 is that 1 keeps the original version number, 2 converts it to the number the exe it was built with.
-Doing --rules4101 instead of --rules8011 gives a slightly different binary file, although I'm not quite sure what the significance of the differences are.
-The --strip removes all the extra junk at the start of the file.

Now we can convert a file to xml, change a value, and convert it back to binary and see what's the difference.


It's just the thing is, everything seems to be working just fine already. The 2010 Skyrim anims work 100% perfectly with this tool, why are these all messed up? 

I don't think it's the version number, I've tried converting the files to 2012 and 2013 binary with AssetCc2, then converting it to xml, but same thing.

And I still need samples of 2012 files from A:I. Maybe those will have the same issue.
## Post #69
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-04-05T00:41:12+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> -Doing --rules4101 instead of --rules8011 gives a slightly different binary file, although I'm not quite sure what the significance of the differences are.
According to the Havok Standalone Tool the Rules are platform versions:




So I suppose it's best to stick with 4101.
## Post #70
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-04-10T05:45:08+00:00
- Post Title: Re: Havok binary files

Still no luck with game->Max, so I tried the other way around. 

To replace animations, you simply swap data starting with the "WaaW" and ending with "+    yyyyyy". 





I have no idea what the heck those two header numbers do but they're clearly a memory size pointer or something. 
If they're too large it crashes so I set them both the the minimum possible. 

Works perfectly, at least for swapping animations that are already ingame.




Although I wonder if it would be possible to create 100% custom anims?
In the Havok Content Tools for Max the Prune modifier removes all the extra junk, leaving a file that is almost identical to the original.

Theoretically it would be possible to use AssetCC to convert the xml files to binary, then stick them ingame with the above method.
## Post #71
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2016-04-20T00:43:40+00:00
- Post Title: Re: Havok binary files

Hey Lads, my sincere gratitude for all your continued efforts & brilliant progress so far !  And a special thx to the original/current author of hkxPack java client (sgtJoe ?).

I hope it's not too Off-Topic, but humbly requesting some brief advice or nudge in right direction WRT manual parsing of hkBinaryPacked Files, specifically BigEndian (PS3)

Also, like to share (a work in progress) 010 Template for Parsing hk-2011-01-r1 (classname/type/data - 48/48/48) - (was bundled with first or2nd VISION / anarchy release - still cant find it anywhere, so have had to make due with newer/older Libs without much success).



Currently stuck on the Vlookup, cant quite wrap my head around it, ive also included a sample file, if anyone can find the time to check it out. Would love a brief explanation, just fetching first one or 2 types/names, already have the 6 offsets from Names, and another offset in types/data, how to tie it all up. 

- ( On a sidenote Are ClassID's different from Hk version to version, or is it just the Sig ?
 - While PS3 flag in Hdr makes little difference, BigEndian flag will always cause problems with Deserialization (even if manually editing to 0 - and even removing Platform/Endianness checks in Source) -  obv. needing BitSwap 
 -> so can one maybe parse this on a PPC /BE System (Linux Box/or Debug PS3 cache dump) .or would i need to manually parse,swapping uints/floats, so on  
- or even as last resort, parse the entire thing manually (c# /c) and then reconstruct/instantiate the hkObjects one by one.

Would love any advice or your own experiences, would it be better for me to build a manual parser - as ive had nothing but grief with deserialization/unpack, though i havnt yet tried the SDAC/headerswap.

Keep up the great work, hope to make some contributions in near future, once i figure out my a$$ from my elbow with it all 

Here is the 010 (Unfinished) Template / Structure Definition:-  To use with ur own hkFiles, Change Fseek on Line12 to 0 or to the start address of hk WaaW header.  Will update as & when i make progress

Download/View @ Pastebin
[http://pastebin.com/HerN0A2U](http://pastebin.com/HerN0A2U)


Here is my working sample hkxPacked File (containerfile - hkHeader starts @ offset 54324 / 0xD434)

[https://mega.nz/#!rsxWkZoI!nHT0ogG_oYY2 ... rhOtqLl6Jw](https://mega.nz/#!rsxWkZoI!nHT0ogG_oYY2ZidID2rz44J1QBteMUticrhOtqLl6Jw)
[QD_hkBinaryPacked_Parser.zip](https://xentaxbackup.github.io/file/10804_QD_hkBinaryPacked_Parser.zip)
## Post #72
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-15T22:29:31+00:00
- Post Title: Re: Havok binary files

Hate to bump on this topic myself, but I was looking into Dark Soul III HKX files, which have the following header:


The weird thing about these files is that at lines 00000080 and some others are just the single character repeating, which I have not seen in any other HKX files.

Also, havok2fbx does not work due to the HKX files being 64bit rather than 32bit.
I tried editing the revision numbers and most of the binary information to match the 2012 r1 and 2010 r2 binaries, but to no avail.

Interestingly, I did find this program called [hkxpack](https://github.com/Dexesttp/hkxpack) which does unpack the HKX files, but unfortunately it unpacks them into an XML which neither Noesis with the damnhavok plugin nor hkxcmd can read, and opening it up it can be clearly seen that typical HKX->XML conversions do not look the same.

Looking further into the hkxpack tool, I see that it outputs the HKX files as Tag-XML, where the importers I use expect regular XML, and hkxcmd is not converting them to regular xml or any other format.

EDIT: I tried editing the 64bit skeleton from DSIII and matched the format/structure as best as I can, but no matter what I do, even with getting the format 100% the same, it can't be converted to any other format through hkxcmd nor the Havok tools.

Does anyone know what can be done about these?
## Post #73
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-17T08:09:24+00:00
- Post Title: Re: Havok binary files

> Reply from HunterAP
>
> Does anyone know what can be done about these?if it's about the skeleton only it can be extracted manually from the hkx file from my experience:



DarkSoulsIII_skel.jpg (70.92 KiB) Viewed 580 times


save code as smd file:

```
nodes
0 "Master" -1
1 "Lower_Root" 0
2 "Pelvis" 1
3 "bag_B_L" 2
4 "bag_b_R" 2
5 "bag_L" 2
6 "bag_R" 2
7 "L_Thigh" 2
8 "L_Calf" 7
9 "L_Foot" 8
10 "L_Toe0" 9
11 "L_Toe0Nub" 10
12 "LCalfTwist" 7
13 "L_Wepon_Case" 2
14 "R_Thigh" 2
15 "R_Calf" 14
16 "R_Foot" 15
17 "R_Toe0" 16
18 "R_Toe0Nub" 17
19 "RCalfTwist" 14
20 "R_Wepon_Case" 2
21 "Upper_Root" 0
22 "Spine" 21
23 "Spine1" 22
24 "B_Wepon_Case" 23
25 "B_Wepon_Case0_L" 23
26 "B_Wepon_Case0_R" 23
27 "L_Arm_Root" 23
28 "L_Clavicle" 27
29 "L_UpperArm" 28
30 "L_Forearm" 29
31 "L_Hand" 30
32 "L_Finger0" 31
33 "L_Finger01" 32
34 "L_Finger02" 33
35 "L_Finger0Nub" 34
36 "L_Finger1" 31
37 "L_Finger11" 36
38 "L_Finger12" 37
39 "L_Finger1Nub" 38
40 "L_Finger2" 31
41 "L_Finger21" 40
42 "L_Finger22" 41
43 "L_Finger2Nub" 42
44 "L_Finger3" 31
45 "L_Finger31" 44
46 "L_Finger32" 45
47 "L_Finger3Nub" 46
48 "L_Finger4" 31
49 "L_Finger41" 48
50 "L_Finger42" 49
51 "L_Finger4Nub" 50
52 "L_Shield" 31
53 "L_Weapon" 31
54 "L_ForeTwist" 29
55 "L_Shoulderpad" 29
56 "LUpArmTwist" 28
57 "Neck" 23
58 "Head" 57
59 "HeadNub" 58
60 "R_Arm_Root" 23
61 "R_Clavicle" 60
62 "R_UpperArm" 61
63 "R_Forearm" 62
64 "R_Hand" 63
65 "R_Finger0" 64
66 "R_Finger01" 65
67 "R_Finger02" 66
68 "R_Finger0Nub" 67
69 "R_Finger1" 64
70 "R_Finger11" 69
71 "R_Finger12" 70
72 "R_Finger1Nub" 71
73 "R_Finger2" 64
74 "R_Finger21" 73
75 "R_Finger22" 74
76 "R_Finger2Nub" 75
77 "R_Finger3" 64
78 "R_Finger31" 77
79 "R_Finger32" 78
80 "R_Finger3Nub" 79
81 "R_Finger4" 64
82 "R_Finger41" 81
83 "R_Finger42" 82
84 "R_Finger4Nub" 83
85 "R_Shield" 64
86 "R_Weapon" 64
87 "R_Weapon_to_left" 64
88 "R_ForeTwist" 62
89 "R_Shoulderpad" 62
90 "RUpArmTwist" 61
end
skeleton
time 0
0 0.000000 0.970140 -0.054000 0.000000 1.570796 0.000000
1 0.000000 0.000000 -0.000000 0.000000 -1.570796 0.000000
2 0.000000 0.000000 0.000000 3.141590 0.000000 1.570798
3 0.102369 0.067501 -0.118728 3.141593 -0.349069 1.570798
4 0.102369 -0.067498 -0.118728 -3.141590 0.349063 1.570798
5 0.102559 0.172900 0.055072 -3.141591 -0.174536 1.570798
6 0.102560 -0.172895 0.055071 -3.141590 0.174530 1.570798
7 -0.000000 0.103349 0.000000 -0.000001 -0.019934 -3.141591
8 0.443364 -0.000000 0.000000 -0.000000 0.189795 0.000000
9 0.423298 0.000000 -0.000000 0.000000 -0.169516 -0.000000
10 0.110321 0.000000 0.134743 3.141416 -1.570451 -3.141416
11 0.078623 0.000000 0.000000 0.000000 -0.000000 -3.141593
12 0.443364 -0.000000 0.000000 0.000000 0.189795 0.000000
13 0.035116 0.185465 0.005854 -1.623160 -0.697336 -3.141589
14 0.000000 -0.103349 -0.000000 -0.000001 -0.019934 -3.141591
15 0.443364 -0.000000 -0.000000 -0.000000 0.189797 0.000000
16 0.423298 0.000000 -0.000000 0.000000 -0.169518 -0.000000
17 0.110321 0.000000 0.134743 3.141416 -1.570451 -3.141416
18 0.078623 0.000000 0.000000 -0.000000 -0.000000 0.000000
19 0.443364 -0.000000 -0.000000 0.000000 0.189797 0.000000
20 0.035116 -0.185000 0.005853 -1.518440 -0.697336 -3.141589
21 -0.000199 0.089070 -0.000000 0.000000 -1.570796 0.000000
22 0.000000 0.027248 -0.000053 -3.141591 0.000000 1.570796
23 0.137738 0.000000 -0.000150 -0.000000 -0.000000 -0.000000
24 -0.002311 -0.000289 -0.158794 -0.000668 -0.000433 0.994837
25 -0.002311 0.097063 -0.158794 -3.141439 -0.000000 1.570796
26 -0.002311 -0.097060 -0.158794 -3.141439 -0.000000 1.570796
27 0.192637 0.054731 -0.035426 3.141591 0.000000 1.570796
28 -0.000000 -0.026113 -0.000000 0.000798 -0.000003 -0.000000
29 0.116357 0.000000 0.000000 -0.000796 -0.023052 0.000019
30 0.282076 0.000000 0.000000 0.000000 0.113538 0.000000
31 0.231722 0.000000 -0.000000 1.570797 -0.090485 -0.000000
32 0.022472 -0.020140 0.007940 -1.365101 -0.381454 -0.561813
33 0.042931 -0.000000 -0.000000 -0.000000 -0.026295 0.000000
34 0.024978 0.000000 0.000000 0.000000 0.000000 -0.000000
35 0.028448 -0.000000 -0.000000 -0.000000 0.000000 -0.000000
36 0.076584 -0.022206 -0.015239 0.000796 -0.000000 -0.000000
37 0.038286 0.000000 0.000000 0.000000 -0.000000 -0.000000
38 0.020783 0.000000 0.000000 0.000000 -0.000000 0.000000
39 0.026549 0.000000 0.000000 0.000000 -0.000000 0.000000
40 0.078816 -0.001225 -0.015238 0.000796 -0.000000 -0.000000
41 0.041986 0.000000 0.000000 0.000000 -0.000000 -0.000000
42 0.024718 -0.000000 -0.000000 0.000000 -0.000000 0.000000
43 0.031424 0.000000 0.000000 0.000000 -0.000000 0.000000
44 0.076947 0.019304 -0.015238 0.000796 -0.000000 -0.000000
45 0.039014 -0.000000 0.000000 0.000000 -0.000000 -0.000000
46 0.021675 0.000000 0.000000 0.000000 -0.000000 0.000000
47 0.027197 0.000000 0.000000 0.000000 -0.000000 0.000000
48 0.074308 0.038334 -0.015237 0.000796 -0.000000 -0.000000
49 0.032427 -0.000000 0.000000 0.000000 -0.000000 -0.000000
50 0.017567 0.000000 0.000000 0.000000 -0.000000 0.000000
51 0.023240 0.000000 0.000000 0.000000 -0.000000 0.000000
52 0.059999 0.000000 0.012112 -0.000001 -0.261800 0.000000
53 0.059999 0.000000 0.012112 3.141592 -0.000000 0.000000
54 0.282076 0.000000 0.000000 0.000000 0.113538 -0.000000
55 0.000002 0.000002 0.000000 -0.000000 0.023053 -0.000000
56 0.116357 0.000000 0.000000 -0.196404 -0.023052 0.000019
57 0.239683 -0.000000 -0.033470 0.000000 0.000000 0.000000
58 0.067741 -0.000000 -0.000000 -0.000000 0.000002 -0.000000
59 0.181918 -0.000000 0.000000 0.000000 -0.000000 0.000000
60 0.192637 -0.054729 -0.035426 3.141591 0.000000 1.570796
61 -0.000001 -0.026113 -0.000000 -0.000798 0.000003 -3.141593
62 0.116357 0.000000 -0.000000 0.000796 -0.023052 -0.000019
63 0.282076 0.000000 0.000000 0.000000 0.113538 0.000000
64 0.231723 0.000000 -0.000000 -1.570797 -0.090485 0.000000
65 0.022473 0.020140 0.007940 1.365101 -0.381454 0.561813
66 0.042931 -0.000000 -0.000000 0.000000 -0.026295 0.000000
67 0.024978 0.000000 0.000000 0.000000 0.000000 0.000000
68 0.028448 -0.000000 0.000000 -0.000000 -0.000000 -3.141593
69 0.076585 0.022206 -0.015239 -0.000796 -0.000000 -0.000000
70 0.038286 -0.000000 0.000000 0.000000 -0.000000 0.000000
71 0.020783 -0.000000 0.000000 -0.000000 -0.000000 -0.000000
72 0.026549 -0.000000 0.000000 -0.000000 0.000000 3.141593
73 0.078817 0.001225 -0.015238 -0.000796 -0.000000 -0.000000
74 0.041986 0.000000 -0.000000 0.000000 -0.000000 0.000000
75 0.024718 0.000000 -0.000000 -0.000000 -0.000000 -0.000000
76 0.031424 -0.000000 0.000000 -0.000000 0.000000 3.141593
77 0.076948 -0.019303 -0.015237 -0.000796 -0.000000 -0.000000
78 0.039014 -0.000000 0.000000 0.000000 -0.000000 0.000000
79 0.021675 -0.000000 0.000000 -0.000000 -0.000000 -0.000000
80 0.027197 0.000000 -0.000000 -0.000000 0.000000 3.141593
81 0.074309 -0.038334 -0.015237 -0.000796 -0.000000 -0.000000
82 0.032427 0.000000 -0.000000 0.000000 -0.000000 0.000000
83 0.017567 -0.000000 0.000000 -0.000000 -0.000000 -0.000000
84 0.023240 0.000000 0.000000 -0.000000 0.000000 3.141593
85 0.060000 -0.000001 0.012110 0.000001 -0.261800 -0.000000
86 0.060000 -0.000001 0.012110 0.000001 -0.000000 -0.000000
87 0.060000 -0.000001 0.012110 0.000001 -0.000000 -0.000000
88 0.282076 0.000000 0.000000 -0.000000 0.113538 0.000000
89 -0.000000 0.000000 -0.000000 0.000000 -0.023050 -3.141592
90 0.116357 0.000000 0.000000 0.196404 -0.023052 -0.000019
end
```


Some dumbo dev added additional 16 zeroes after R_Weapon_to_left so you've to care not to overview R_ForeTwist, R_Shoulderpad and RUpArmTwist when scanning for bonenames programmatically. 

btw: I've always been asking myself how anyone could ever have the idea to hide such simple things in such a shitty format like hkx? (Hope it will be burried by MS in the deepest sea to be found, hahaha...)
## Post #74
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-17T17:35:59+00:00
- Post Title: Re: Havok binary files

Strange, whatever skeleton file you were looking at has only 91 bones, whereas the one I'm looking at (c0000/hkx/skeleton.hkx) has 110 bones. You can look at the file [from this link](http://www.mediafire.com/download/x6z5mqyz1ycwqh0/ds3.7z).

How did you manage to convert from the HKX bone coordinates and rotations to SMD format?
If I could find a way to batch the process, I could get full DSIII animations out.
## Post #75
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-17T23:33:04+00:00
- Post Title: Re: Havok binary files

> Reply from HunterAP
>
> How did you manage to convert from the HKX bone coordinates and rotations to SMD format?
If I could find a way to batch the process, I could get full DSIII animations out.

This is a project I started last year for Alien:Isolation, it's a HKX converter that outputs SMD skeleton.  It works with 2012.2.0 and 2010.2.0, I had intended to take it all the way with support for many versions, and animation output, but I simply moved on to other projects.  It's written in C#, a lot of the file structure is defined at the top of Program.cs, and maybe will help people, so I'm making the code public.

[https://bitbucket.org/Volfin/hkx2smd/overview](https://bitbucket.org/Volfin/hkx2smd/overview)
## Post #76
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-18T02:09:55+00:00
- Post Title: Re: Havok binary files

> Reply from volfin
>
> HunterAP wrote:How did you manage to convert from the HKX bone coordinates and rotations to SMD format?
If I could find a way to batch the process, I could get full DSIII animations out.

This is a project I started last year for Alien:Isolation, it's a HKX converter that outputs SMD skeleton.  It works with 2012.2.0 and 2010.2.0, I had intended to take it all the way with support for many versions, and animation output, but I simply moved on to other projects.  It's written in C#, a lot of the file structure is defined at the top of Program.cs, and maybe will help people, so I'm making the code public.

https://bitbucket.org/Volfin/hkx2smd/overview

I tried building your program as both x86 and x64, normally running the 2014.1.0-r1 HKX files give some errors in the header, but if I copy-paste the 2012.2.0-r1 header over the original, the program reads everything and gets up to "class hkaskeleton signature: 0xFEC1CEDB", then after a few seconds the program crashes with the "System.OutOfMemoryException" error. Looking it up says that I don;t have enough memory, even though I have 16GB of RAM, but I'm assuming that your program is looking for a big chunk of sequential memory that I may not have if my memory usage is fragmented.

What's interesting is that I've tried this with multiple skeletons, and it doesn't matter what size the HKX file is, I still get the error.

I would fix the issue myself, but I'm not versed in C#, so I don't know how to fix it in the code myself.

If you'd like, I could just send you a HKX sample of the skeleton and animations.
## Post #77
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-18T04:46:51+00:00
- Post Title: Re: Havok binary files

Well the point of me releasing it is that I have no time to mess with it anymore (haven't touched it since Alien:Isolation).  I know it worked for Alien: Isolation and Skyrim, but don't guarantee anything else. The problem is HKX is very customizable so the format varies widely from game to game, and then on top of that many developers modify it in-house to do even more strange things, and some even obfuscate it purposely to prevent people reverse engineering their animations. 

So likely the code will have to be tweaked for every particular game, no small job.  That's why I gave the code out.
## Post #78
- Username: philgrf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 07, 2017 1:11 am
- Post datetime: 2017-03-06T17:52:50+00:00
- Post Title: Re: Havok binary files

As I understand, the spline compression is a technic that is animation specific.

See this article at riot game engineering
[https://engineering.riotgames.com/news/ ... ation-data](https://engineering.riotgames.com/news/compressing-skeletal-animation-data)
So, it is likely there is no simple link between the hkx file and the animation keys.

Maybe the way hkx animation is encoded is similar to the one described in the article that is to say :
- rotation is encoded as quaternion (x,y,z,w),
- the highest value among (x,y,z,w) is discarded as x^2+y^2+z^2+w^2=1 and can thus be reconstructed from the 3 others,
- bytes need to be read according to a key (m bytes for discarded value, n bytes for remaining value1, n bytes for remaining value2, n bytes for remaining value3)

edit : this article at bitsquid describes also the technic
[http://bitsquid.blogspot.fr/2009_11_01_archive.html](http://bitsquid.blogspot.fr/2009_11_01_archive.html)

Best regards

Phil
## Post #79
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-03-10T17:52:44+00:00
- Post Title: Re: Havok binary files

The SDK also has a LOT of documentation files in it, including files for all the compression types instead of just Spline. It's not available through Intel anymore but I managed to save copies. Feel free to PM me for the link.
## Post #80
- Username: philgrf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 07, 2017 1:11 am
- Post datetime: 2017-03-12T10:26:41+00:00
- Post Title: Re: Havok binary files

Sergeant Joe,

I thank you for your reminding of the Intel documentation.
I have downloaded havok 2013 before Intel closed the public access.
At the time I downloaded, I couldn't make any sense of spline compression.

Now, I understand better :
After spending some time on xentax forum, I started to get acquainted with binary files ans lately with file compression.
Following your advice, I looked again at havok 2013 help files.

The game I'm interested in is using spline compression. 
So, I restricted my field of research the spline compression.

There are havok default settings for spline compression :
Position : 16 bits
Rotation : 40 bits
Scale : 16 bits 
Float (what for ? timeline ?) : 16 bits
Frames per block : 256

As the spline compression is highly customizable(*) in havok, this should only be considered as a reference.
At least, it gives the structure of the data.

I am a beginner at reading binary files but it looks like an interesting challenge :

- identify blocks,
- identify number of frame per blocks,
- guess bone ordering,
- guess quantization for each bone,
- translate into skeleton pose,
- translate into animation.

I need to evaluate the required time.

Best regards

Phil

 *() : Even, a per bone customization is possible. The doc says :
"Judiciously setting compression parameters per bone can result in a significant reduction in output data size. One such use case is to create level of detail compression by grouping bones roughly by depth in the hierarchy; tight tolerances could be user for "major bones" such as spine and arm bones while more relaxed tolerances for "minor bones" such as hands and fingers could be used to gain additional savings. A similar use case might involve grouping bones as "upper body" and "lower body". Extremities such as hands often contain a significant number of bones though their visual impact may be limited."
## Post #81
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2017-04-03T18:40:28+00:00
- Post Title: Re: Havok binary files

Does anyone have a working link for the script that flips the skeleton or model because when I open animation in 3dsmax the skeleton has the right animation but the model is all over the place.
## Post #82
- Username: zweihard
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 24, 2017 7:18 am
- Post datetime: 2017-07-31T22:52:19+00:00
- Post Title: Re: Havok binary files

Would anyone mind helping me out with obtaining the animation data for Dark Souls III?

Regards
## Post #83
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-08-01T11:49:12+00:00
- Post Title: Re: Havok binary files

> Reply from zweihard
>
> Would anyone mind helping me out with obtaining the animation data for Dark Souls III?
Sorry, you're out of luck. Havok formats are incredibly difficult, even with all the documentation nobody has been able to figure it out.
## Post #84
- Username: zweihard
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 24, 2017 7:18 am
- Post datetime: 2017-08-01T20:23:18+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> zweihard wrote:Would anyone mind helping me out with obtaining the animation data for Dark Souls III?
Sorry, you're out of luck. Havok formats are incredibly difficult, even with all the documentation nobody has been able to figure it out.

Reverse engineering job huh?
## Post #85
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2017-11-24T21:25:26+00:00
- Post Title: Re: Havok binary files

Sorry for bringing up this topic again, but Im kinda stuck with a havok file here.

I got a havok binary with the hk_2012.2.0-r1 header. However, none of the converters seem to work with it (even when renaming the header) and the original havok preview tool says something like "wrong platform".

Anyone has an idea of what is so special/wrong about that file?

[hk_2012.2.0-r1 binary](https://mega.nz/#!QSwBgZCA!xmSosYMXvY8a5begv6FceXLIpYLMi9n-kPBvNlRykIU)
## Post #86
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-11-28T11:01:54+00:00
- Post Title: Re: Havok binary files

I honestly have no idea, and there's nobody else that can help. Sorry, you just have to give up.
## Post #87
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2017-11-28T11:15:56+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe
>
> I honestly have no idea, and there's nobody else that can help. Sorry, you just have to give up.

well, there are some people that made the converters, so there should be some other help out there...in theory haha
however, thanks for looking into it!
## Post #88
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-09T15:51:15+00:00
- Post Title: Re: Havok binary files

> Reply from Ginsor
>
> Sorry for bringing up this topic again, but Im kinda stuck with a havok file here.

I got a havok binary with the hk_2012.2.0-r1 header. However, none of the converters seem to work with it (even when renaming the header) and the original havok preview tool says something like "wrong platform".

Anyone has an idea of what is so special/wrong about that file?

hk_2012.2.0-r1 binary

Been a while since i tried my luck figuring this out, but just if it helps: look out for the c# project shared by the awesome (if not mistaken) SeargentJoe, (hkx2smd, and there is another one, or similar project on github, with some fiddling managed to parse some basic 2013 structs, im looking to research splinecompressed anims & bone/weight/blendweight conversion. though quite difficult to find older/recent havok src. (looking for 2011r3 & 2013+)

Just off top of my head, and old snippet idk if works:-  look for this flag in ur data which specifies platform type and modify to ur build platform.  also thinking might be some endianness conversion needed ( ? )

    public enum hkPlatform
    {
        HCL_PLATFORM_WIN32 = 0x0,
        HCL_PLATFORM_X64 = 0x1,
        HCL_PLATFORM_MACPPC = 0x2,
        HCL_PLATFORM_IOS = 0x4,
        HCL_PLATFORM_MAC386 = 0x8,
        HCL_PLATFORM_PS3 = 0x10,
        HCL_PLATFORM_XBOX360 = 0x20,
        HCL_PLATFORM_WII = 0x40,
        HCL_PLATFORM_LRB = 0x80,
        HCL_PLATFORM_LINUX = 0x100,
        HCL_PLATFORM_NGP = 0x400,
        HCL_PLATFORM_ANDROID = 0x800,
        HCL_PLATFORM_CTR = 0x1000//4096
    }
if u look up my old posts, io posted 010 template for havok while back, somewhere on forum, including offset of Platform flag  (i didnt have much joy parsing PS3 files on win32 build)
## Post #89
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2017-12-10T02:19:15+00:00
- Post Title: Re: Havok binary files

After  all this time I'm also trying to get some newer formats of HKX working. Right now, Volfin's hkt2smd is crashing because newer formats report that for a variable used in the code, there is over 1.5 billion elements in an array (AKA way too much to work with), and I'm not sure how to go about patching it.

Also, interestingly, trying to use hkt2smd on Dark Souls 1 has a similar error but in a different section.
## Post #90
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-16T07:37:49+00:00
- Post Title: Re: Havok binary files

> Reply from HunterAP
>
> After  all this time I'm also trying to get some newer formats of HKX working. Right now, Volfin's hkt2smd is crashing because newer formats report that for a variable used in the code, there is over 1.5 billion elements in an array (AKA way too much to work with), and I'm not sure how to go about patching it.

Also, interestingly, trying to use hkt2smd on Dark Souls 1 has a similar error but in a different section.

can u post here sample of both assets ur trying to parse ?  i can take a look.
## Post #91
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2017-12-16T07:46:28+00:00
- Post Title: Re: Havok binary files

> Reply from Loomy
>
> HunterAP wrote:After  all this time I'm also trying to get some newer formats of HKX working. Right now, Volfin's hkt2smd is crashing because newer formats report that for a variable used in the code, there is over 1.5 billion elements in an array (AKA way too much to work with), and I'm not sure how to go about patching it.

Also, interestingly, trying to use hkt2smd on Dark Souls 1 has a similar error but in a different section.

can u post here sample of both assets ur trying to parse ?  i can take a look.

Of course. I'm including two files: one is the player skeleton from Dark Souls 2, and the other is the player skeleton from Dark Souls 3.
[hkx.zip](https://xentaxbackup.github.io/file/13691_hkx.zip)
## Post #92
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2017-12-21T18:55:15+00:00
- Post Title: Re: Havok binary files

In meanwhile, i came across this hkx2xml converter.[https://github.com/Dexesttp/hkxpack](https://github.com/Dexesttp/hkxpack). it looks promising.  Iiirc its easier and there are couple of tools to convert raw HKxmlTagFile to a couple of formats. 



Still trying to fix up volfins awesome project. (its just a matter of few extra trash/padding bytes + some random extra info, 

still not sure about the HeaderFlags PointerSize if it has any bearing.. older files usually have value of 4 here, these 2014 / dk files have pointer 8.  Think it has something to do with calculating the section / data block total sizes.. this java project above seems to give some clues. 

Anyway here is output of DK3 file. (dk2 file only spat out seemingly broken file with only 5 attachments/bones) and no refpose/indices info

Does this look right ? or do u maybe have an smd or other version of DK2 / 3 skeleton to use as ref ?

```
<hkpackfile classversion="11" contentsversion="hk_2014.1.0-r1">
    <hksection name="__data__">
        <hkobject class="hkRootLevelContainer" name="#90" signature="0x2772c11e">
            <hkparam name="namedVariants" numelements="1">
                <hkobject>
                    <hkparam name="name">Merged Animation Container</hkparam>
                    <hkparam name="className">hkaAnimationContainer</hkparam>
                    <hkparam name="variant">#91</hkparam>
                </hkobject>
            </hkparam>
        </hkobject>
        <hkobject class="hkaAnimationContainer" name="#91" signature="0x26859f4c">
            <!-- memSizeAndRefCount SERIALIZE_IGNORED -->
            <hkparam name="skeletons" numelements="1">#92</hkparam>
            <hkparam name="animations" numelements="0"></hkparam>
            <hkparam name="bindings" numelements="0"></hkparam>
            <hkparam name="attachments" numelements="0"></hkparam>
            <hkparam name="skins" numelements="0"></hkparam>
        </hkobject>
        <hkobject class="hkaSkeleton" name="#92" signature="0xfec1cedb">
            <!-- memSizeAndRefCount SERIALIZE_IGNORED -->
            <hkparam name="name">Master</hkparam>
            <hkparam name="parentIndices" numelements="110">
65535 0 1 2 0 4 5 0 7 8 8 10 11 11 11 11 15 15 10 10 10 10 10 8
8 8 25 26 26 26 26 30 30 25 25 25 25 25 8 7 39 40 41 42 43 43 43
43 43 48 48 50 50 52 52 52 55 56 57 55 59 60 55 62 63 55 65 66
55 68 69 55 55 50 50 43 43 43 77 43 79 79 81 81 83 83 83 86 87
88 86 90 91 86 93 94 86 96 97 86 99 100 86 86 81 81 43 43 42 42</hkparam>
            <hkparam name="bones" numelements="110">
                <hkobject>
                    <hkparam name="name">Master</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Foot_Target2</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Foot_Target1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Foot_Target</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Foot_Target2</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Foot_Target1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Foot_Target</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">RootPos</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Pelvis</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Hip</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Thigh</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Calf</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Calf_Skirt</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_CalfTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_CalfTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Foot</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_FootTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Toe0</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Knee</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Knee_Skirt</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Thigh_Skirt</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_ThighTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_ThighTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Wepon_Case</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Hip</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Thigh</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Calf</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Calf_Skirt</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_CalfTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_CalfTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Foot</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_FootTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Toe0</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Knee</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Knee_Skirt</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Thigh_Skirt</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_ThighTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_ThighTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Wepon_Case</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">RootRotY</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">RootRotXZ</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Spine</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Spine1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Spine2</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">B_Wepon_Case</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">B_Wepon_Case0_L</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">B_Wepon_Case0_R</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Collar</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Clavicle</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Shoulder</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_UpperArm</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Elbow</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Forearm</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_ForeArmTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_ForeArmTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Hand</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger0</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger01</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger02</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger11</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger12</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger2</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger21</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger22</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger3</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger31</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger32</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger4</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger41</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Finger42</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Shield</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Weapon</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_UpArmTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_UpArmTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Pectoral</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">L_Po</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Neck</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">Head</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Clavicle</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Shoulder</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_UpperArm</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Elbow</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Forearm</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_ForeArmTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_ForeArmTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Hand</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger0</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger01</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger02</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger11</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger12</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger2</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger21</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger22</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger3</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger31</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger32</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger4</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger41</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Finger42</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Shield</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Weapon</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_UpArmTwist</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_UpArmTwist1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Pectoral</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">R_Po</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">SpineArmor1</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
                <hkobject>
                    <hkparam name="name">SpineArmor2</hkparam>
                    <hkparam name="lockTranslation">false</hkparam>
                </hkobject>
            </hkparam>
            <hkparam name="referencePose" numelements="110">

(0.0 0.0 0.0 1.0)(0.0 0.7071061730384827 0.0 0.7071073055267334)(0.9999998211860657 0.9999999403953552 0.9999998211860657 1.0)
(-0.06271867454051971 0.9761797189712524 0.10334890335798264 -0.9761798977851868)(-0.49987614154815674 0.4998769462108612 -0.5001237988471985 0.5001230835914612)(0.9999997019767761 0.9999997615814209 1.0000001192092896 0.0)
(0.4433634281158447 0.0 1.2665987014770508E-6 0.9758566617965698)(-7.783820166196165E-8 -1.1212688377781888E-6 1.19486983862771E-7 1.0)(0.9999997019767761 1.0 0.9999997019767761 0.0)
(0.42329806089401245 -1.4901161193847656E-7 -9.164214134216309E-7 1.0418891906738281E-4)(2.4693511659279466E-4 -1.729398500174284E-4 1.6194296392768592E-7 -0.9999998807907104)(1.000000238418579 1.0 1.0000004768371582 0.0)
(-0.06271988898515701 0.9761797785758972 -0.10334904491901398 -0.9761799573898315)(-0.5010172128677368 0.5010135769844055 -0.49898040294647217 0.49898460507392883)(0.9999995827674866 0.999998927116394 0.9999993443489075 0.0)
(0.4433632493019104 6.332993507385254E-7 6.9141387939453125E-6 0.9796545505523682)(-2.2538009147865523E-7 -4.222733423375757E-6 -9.79873817641419E-8 0.9999999403953552)(0.9999998807907104 0.9999998807907104 0.9999999403953552 0.0)
(0.4232977628707886 -9.015202522277832E-7 -1.7292797565460205E-5 -8.538961410522461E-4)(-0.0020329768303781748 -1.8076931883115321E-4 -1.1241216668622656E-7 -0.9999979138374329)(1.0 1.000000238418579 1.0000004768371582 0.0)
(0.0 0.9699996113777161 0.0 -0.9699997901916504)(0.0 -0.7071061730384827 0.0 0.7071073055267334)(1.0000001192092896 1.0 1.0000001192092896 0.0)
(0.0 6.556510925292969E-7 0.0 -0.9699976444244385)(0.7071061730384827 0.7071073055267334 1.6493457906108233E-6 1.6493461316713365E-6)(0.9999998211860657 0.9999998211860657 0.9999996423721313 0.0)
(-2.384185791015625E-7 0.10334886610507965 -0.004999629687517881 -3.814697265625E-6)(-0.004983692429959774 -2.0406770636327565E-4 -0.9999874830245972 2.81304301097407E-6)(1.0000001192092896 1.0 1.0000001192092896 0.0)
(-2.384185791015625E-7 0.10334903001785278 3.828472472378053E-7 -3.814697265625E-6)(-0.00996700394898653 2.0000154563604156E-6 -0.9999502897262573 1.1557366406123037E-6)(1.0000005960464478 1.0000004768371582 1.000000238418579 0.0)
(0.44336360692977905 -1.043081283569336E-7 3.725290298461914E-9 -0.01285165548324585)(3.9115556660362927E-7 0.09475500136613846 -3.323658290810272E-7 0.9955005645751953)(0.999998927116394 0.9999991059303284 0.9999993443489075 0.0)
(0.005000710487365723 -5.289912223815918E-7 9.685754776000977E-8 0.07964915037155151)(1.0430816388407038E-7 1.1175874448099421E-8 9.080398655214594E-9 1.0)(0.9999999403953552 1.0 0.9999997019767761 0.0)
(0.19473174214363098 -3.0547380447387695E-7 8.195638656616211E-8 0.06361275911331177)(-6.518663722090423E-4 -7.450582373280668E-9 6.984921085972928E-9 -0.9999997615814209)(0.9999998807907104 1.000000238418579 1.0000003576278687 0.0)
(0.005000710487365723 -3.7997961044311523E-7 9.685754776000977E-8 0.07964915037155151)(-3.260561206843704E-4 3.725291186640334E-9 -5.1688413549300094E-8 -0.9999998807907104)(0.9999998807907104 1.0000001192092896 0.9999995827674866 0.0)
(0.423298180103302 -1.564621925354004E-7 3.725290298461914E-8 0.04429394006729126)(6.184566192501961E-10 -0.08465617150068283 2.8226178727663864E-8 0.9964102506637573)(1.000000238418579 1.0000001192092896 1.000000238418579 0.0)
(0.11036860942840576 -7.82310962677002E-7 3.714114427566528E-5 2.2232532501220703E-4)(-1.2516978813437163E-6 -0.7054907083511353 6.599295261366933E-7 0.7087191343307495)(1.0000003576278687 1.000000238418579 1.0000004768371582 0.0)
(0.11032231897115707 -4.470348358154297E-7 0.1347428858280182 2.2232532501220703E-4)(-5.960465898624534E-8 -0.7072290778160095 -5.392941204718227E-8 0.7069844007492065)(1.0 1.0 1.0000001192092896 0.0)
(0.4438374638557434 -5.9604644775390625E-8 0.004977501928806305 -0.012847363948822021)(-8.940698990045348E-7 -0.04743093624711037 4.4140335830888944E-7 -0.9988745450973511)(0.9999988079071045 0.9999984502792358 0.9999992251396179 0.0)
(0.4433634281158447 -4.470348358154297E-8 6.332993507385254E-8 -0.01285165548324585)(3.7066646996208874E-7 0.04743088036775589 -3.46757673241882E-7 0.9988745450973511)(0.999999463558197 0.9999997019767761 0.9999997615814209 0.0)
(-1.7881393432617188E-7 -5.9604644775390625E-8 1.862645149230957E-9 -0.01727050542831421)(-1.183711447083624E-6 1.0244551873483942E-8 -1.3722824121487065E-7 1.0)(0.9999993443489075 0.9999991059303284 0.9999996423721313 0.0)
(0.004999816417694092 -8.195638656616211E-8 -1.862645149230957E-9 -0.017220675945281982)(6.877884152345359E-4 -8.381904947896146E-9 -3.1286626067661416E-10 0.9999997615814209)(1.0 0.9999998211860657 1.000000238418579 0.0)
(0.2290000319480896 -4.470348358154297E-8 1.6763806343078613E-8 -0.014988124370574951)(3.4371772198937833E-4 -9.313227966600834E-10 -3.262540246851131E-7 0.9999999403953552)(1.000000238418579 1.0000009536743164 1.0000003576278687 0.0)
(0.035256266593933105 0.18546460568904877 0.005854020826518536 -4.0531158447265625E-6)(-0.23517447710037231 0.6817288994789124 -0.646933913230896 -0.24782048165798187)(0.9999999403953552 0.9999998807907104 1.0000005960464478 0.0)
(-1.0192394256591797E-4 -0.10334472358226776 -0.0050003682263195515 -3.337860107421875E-6)(0.004983412567526102 -2.0755900186486542E-4 0.9999874830245972 1.2996783880225848E-6)(0.9999997615814209 0.9999996423721313 0.9999997615814209 0.0)
(0.0 -0.10334891080856323 -3.0311957743833773E-7 -3.337860107421875E-6)(0.009967002086341381 3.2130635929661366E-8 0.9999502897262573 -8.27911208034493E-7)(1.0000001192092896 1.0000001192092896 1.0000008344650269 0.0)
(0.4433634281158447 3.650784492492676E-7 1.4901161193847656E-8 -0.016976237297058105)(1.6614800415482023E-6 -0.09475644677877426 1.1728847937320097E-7 -0.9955005049705505)(0.999999463558197 0.9999995231628418 0.9999988079071045 0.0)
(0.005000650882720947 -5.587935447692871E-7 8.195638656616211E-8 0.11868458986282349)(5.5879368687783426E-8 -8.195640788244418E-8 4.656613761255812E-9 1.0)(0.9999998211860657 0.9999999403953552 0.9999998211860657 0.0)
(0.19473588466644287 -4.246830940246582E-7 7.450580596923828E-8 0.10264760255813599)(-6.515683489851654E-4 -1.4901164746561335E-8 9.196812555956058E-8 0.9999998211860657)(1.0 1.000000238418579 0.9999998211860657 0.0)
(0.005000412464141846 -5.066394805908203E-7 7.450580596923828E-8 0.11868464946746826)(-3.2591455965302885E-4 -1.4901164746561335E-8 4.982576840006914E-8 0.9999999403953552)(0.9999996423721313 0.9999994039535522 0.9999992847442627 0.0)
(0.42329829931259155 -3.203749656677246E-7 5.9604644775390625E-8 0.08332878351211548)(3.787137003996577E-8 0.08465758711099625 1.2449393693714228E-7 -0.996410071849823)(1.000000238418579 1.0 1.000000238418579 0.0)
(0.11036861687898636 -3.0547380447387695E-7 3.807246685028076E-5 -0.03433758020401001)(-2.98023280720372E-7 -0.7054906487464905 -2.1587771570352743E-8 0.7087191939353943)(1.0000005960464478 1.000000238418579 1.0000004768371582 0.0)
(0.11032214760780334 -2.5331974029541016E-7 0.13474291563034058 -0.03433758020401001)(-2.980233304583635E-8 0.7072291374206543 -3.918832192084665E-8 -0.7069844007492065)(0.9999998807907104 0.9999998807907104 1.0 0.0)
(0.44383734464645386 3.5762786865234375E-7 0.0049771517515182495 -0.016971945762634277)(5.625189487545867E-7 -0.04743184521794319 1.6763809895792292E-8 -0.9988744854927063)(1.000000238418579 0.9999989867210388 0.9999999403953552 0.0)
(0.44336366653442383 3.5762786865234375E-7 -3.557652235031128E-7 -0.016976237297058105)(-1.583248945280502E-7 0.047431580722332 -1.9962324415701005E-7 0.9988744854927063)(0.9999995231628418 0.9999995231628418 0.9999997019767761 0.0)
(-1.7881393432617188E-7 0.0 1.862645149230957E-8 -0.02139604091644287)(3.9329761420958675E-6 -9.313227966600834E-10 -2.478373630765418E-7 -0.9999999403953552)(0.9999997615814209 0.9999993443489075 0.9999988675117493 0.0)
(0.004999876022338867 -1.4901161193847656E-8 5.587935447692871E-9 -0.021346211433410645)(-6.89333479385823E-4 6.612391700855369E-8 -1.0350779433565549E-7 0.9999997615814209)(1.000000238418579 0.9999999403953552 0.9999994039535522 0.0)
(0.2289811372756958 2.0116567611694336E-7 -4.0978193283081055E-8 -0.01911342144012451)(-3.4494567080400884E-4 5.401672353855247E-8 -1.0858641985578288E-7 0.9999999403953552)(1.0000005960464478 0.9999997019767761 0.9999999403953552 0.0)
(0.03525662422180176 -0.18499965965747833 0.005852219648659229 -3.2186508178710938E-6)(0.24782225489616394 -0.6469369530677795 0.6817261576652527 0.23517277836799622)(0.9999996423721313 0.9999999403953552 1.0 0.0)
(0.0 5.960464477539062E-7 0.0 -0.9699976444244385)(0.0 0.7071061730384827 0.0 0.7071073055267334)(0.9999998211860657 0.9999999403953552 0.9999998211860657 0.0)
(0.0 0.0 0.0 -1.9399993419647217)(0.0 8.940698847936801E-8 0.0 1.0)(0.9999998807907104 0.9999998807907104 0.9999998807907104 0.0)
(1.4781122445128858E-5 0.09297889471054077 1.1921142117898853E-7 -2.032978057861328)(0.5008527040481567 0.5004714131355286 0.49914610385894775 0.4995279908180237)(0.9999998807907104 0.9999997019767761 0.9999997615814209 0.0)
(0.08824312686920166 -2.384153958701063E-7 -6.734335329383612E-5 0.09506207704544067)(0.0012430419446900487 -1.6616193533991463E-5 -3.969018052885076E-6 0.9999991655349731)(1.0000003576278687 1.0000001192092896 1.0000003576278687 0.0)
(0.08824539184570312 1.2678037819569E-7 -1.7670518718659878E-4 0.0030153989791870117)(-0.0025665792636573315 -0.007100915536284447 2.2918244212633E-5 0.9999714493751526)(0.999999463558197 1.0 0.9999995231628418 0.0)
(-0.0198361873626709 -2.8836686396971345E-4 -0.15860965847969055 -0.0238226056098938)(0.003198340767994523 0.0058908844366669655 0.47714802622795105 0.8787973523139954)(1.0000001192092896 0.9999996423721313 0.9999998211860657 0.0)
(-0.019836068153381348 0.09706246107816696 -0.1586097925901413 -0.024552524089813232)(-0.7070885300636292 -0.7070885896682739 0.005075222812592983 0.0050757816061377525)(1.0 1.0 1.000000238418579 0.0)
(-0.0198361873626709 -0.09706015884876251 -0.1586095243692398 -0.023096978664398193)(-0.7070885300636292 -0.7070885896682739 0.005075222812592983 0.0050757816061377525)(1.0 1.0 1.000000238418579 0.0)
(0.22450745105743408 -1.5800912933627842E-7 -0.03411300852894783 -0.025649964809417725)(7.398753950838E-5 3.986101073678583E-4 1.5451513172592968E-4 0.9999998807907104)(1.0000001192092896 1.0 0.9999999403953552 0.0)
(0.15122711658477783 0.021774835884571075 -0.03602876514196396 -0.025263845920562744)(-0.7071065902709961 -0.7071067690849304 2.821679809130728E-4 2.809754223562777E-4)(1.000000238418579 0.9999998211860657 1.0 0.0)
(0.1517028659582138 0.004615187644958496 -2.354457974433899E-4 -0.01840841770172119)(-0.022500373423099518 0.007598421070724726 -0.19506095349788666 0.980503499507904)(0.9999997615814209 0.9999998807907104 1.0000001192092896 0.0)
(0.1497916728258133 1.1920928955078125E-7 -3.725290298461914E-9 -0.01843559741973877)(0.010970291681587696 -0.007931319065392017 -0.382723867893219 0.923763632774353)(1.000000238418579 1.0000001192092896 0.9999998807907104 0.0)
(0.2823597192764282 3.5762786865234375E-7 0.0049918703734874725 0.10059946775436401)(-6.007032027355308E-8 0.028380651026964188 -1.1920931797249068E-7 0.9995971918106079)(0.9999993443489075 0.9999988675117493 0.9999999403953552 0.0)
(0.28207600116729736 5.960464477539062E-7 -1.1175870895385742E-8 0.09707248210906982)(-5.308540096393699E-8 0.05673839896917343 -5.960465898624534E-8 0.9983890056610107)(0.9999995827674866 0.9999996423721313 1.0 0.0)
(0.10107529163360596 -4.76837158203125E-7 -1.4901161193847656E-8 -0.2206215262413025)(0.040611632168293 -2.2351748896198842E-8 -1.192093321833454E-7 0.9991750121116638)(0.9999995827674866 0.9999998807907104 1.000000238418579 0.0)
(0.005000472068786621 -1.1920928955078125E-7 9.685754776000977E-8 -0.21599024534225464)(0.020393889397382736 -1.1175874448099421E-8 -1.192093321833454E-7 0.9997919797897339)(0.9999997019767761 0.9999998807907104 1.0 0.0)
(0.23172274231910706 -1.1920928955078125E-7 4.470348358154297E-8 -0.2269192934036255)(0.706383466720581 -0.03198031708598137 0.031980182975530624 0.7063829302787781)(0.9999997615814209 0.9999996423721313 0.9999998211860657 0.0)
(0.018261641263961792 -0.019700229167938232 0.002788543701171875 -0.21448227763175964)(-0.6146956086158752 0.07776301354169846 -0.2999844253063202 0.7253355383872986)(1.0000001192092896 1.0000001192092896 1.0 0.0)
(0.05320483446121216 1.7881393432617188E-7 -5.9604644775390625E-8 -1.0618152618408203)(4.470350489782504E-8 1.4901168299275014E-8 -5.960467319710006E-8 1.0)(1.0 0.9999998807907104 0.9999998807907104 0.0)
(0.03606909513473511 5.9604644775390625E-8 2.9802322387695312E-8 -0.979928195476532)(-2.980233304583635E-8 0.013146941550076008 5.96046660916727E-8 0.9999135136604309)(0.9999999403953552 0.9999997615814209 1.0 0.0)
(0.10058736801147461 -0.0345129519701004 -0.00377655029296875 -0.2922293543815613)(0.02760077826678753 1.2290483573451638E-4 9.633605077397078E-5 0.9996190667152405)(0.9999998211860657 1.000000238418579 1.0000001192092896 0.0)
(0.044240087270736694 -8.940696716308594E-8 0.0 -0.4000392556190491)(5.96046660916727E-8 0.0 -1.4901166522918174E-8 1.0)(0.9999997615814209 0.9999998211860657 0.9999998211860657 0.0)
(0.03024597465991974 2.9802322387695312E-8 2.384185791015625E-7 -0.43798696994781494)(0.0 0.0 1.4901166522918174E-8 1.0)(0.9999999403953552 1.0 0.9999998807907104 0.0)
(0.10080927610397339 -0.010271385312080383 -0.004487276077270508 -0.2841809391975403)(0.027600867673754692 1.2390321353450418E-4 9.681288793217391E-5 0.9996190667152405)(0.9999995827674866 1.0000001192092896 0.9999997019767761 0.0)
(0.04669712483882904 -8.940696716308594E-8 1.1920928955078125E-7 -0.3889474868774414)(0.0 -1.4901166522918174E-8 -2.980233304583635E-8 0.9999999403953552)(1.0 1.0 0.9999998211860657 0.0)
(0.031089022755622864 0.0 -1.1920928955078125E-7 -0.42975372076034546)(-2.980233659855003E-8 0.0 1.4901168299275014E-8 1.0)(1.0 0.9999999403953552 1.0 0.0)
(0.097603440284729 0.013259053230285645 -0.0025795698165893555 -0.27253928780555725)(0.027601340785622597 1.2364987924229354E-4 9.663406672189012E-5 0.9996190071105957)(1.0000003576278687 1.0 1.0000005960464478 0.0)
(0.04489700496196747 -2.9802322387695312E-8 0.0 -0.36790913343429565)(-2.980233304583635E-8 0.0 -1.4901166522918174E-8 1.0)(0.9999999403953552 0.9999999403953552 1.0 0.0)
(0.03146611154079437 0.0 0.0 -0.40874916315078735)(-2.980233304583635E-8 0.0 2.980233304583635E-8 1.0)(0.9999995827674866 0.9999997019767761 0.9999995231628418 0.0)
(0.09500029683113098 0.03574499487876892 -5.257129669189453E-5 -0.26156097650527954)(0.027510059997439384 1.266003237105906E-4 2.1457681214087643E-6 0.999621570110321)(1.0000001192092896 1.0 1.0 0.0)
(0.039303138852119446 2.9802322387695312E-8 0.0 -0.34494131803512573)(5.96046660916727E-8 -1.6391282997574308E-7 -1.4901166522918174E-8 0.9999999403953552)(0.9999998211860657 0.9999998211860657 0.9999997615814209 0.0)
(0.019024088978767395 0.0 1.1920928955078125E-7 -0.3724498748779297)(-2.980233659855003E-8 0.0 -1.4901168299275014E-8 0.9999999403953552)(1.0000003576278687 1.0 0.9999999403953552 0.0)
(0.0899820625782013 0.001641497015953064 0.012756586074829102 -0.26473286747932434)(-6.556513199029723E-7 -0.13052663207054138 2.0861632776814076E-7 0.9914448261260986)(1.0000003576278687 0.9999990463256836 0.9999997615814209 0.0)
(0.0899820625782013 0.001641497015953064 0.012756586074829102 -0.26473286747932434)(-1.0 -2.384186927884002E-7 -2.384186927884002E-7 -9.536747711536009E-7)(0.9999998807907104 0.9999998807907104 0.9999999403953552 0.0)
(0.005000114440917969 5.960464477539062E-7 -3.3527612686157227E-8 0.09933030605316162)(-0.059619080275297165 -1.0244550985305523E-8 2.0861631355728605E-7 0.9982211589813232)(0.9999992847442627 0.9999994039535522 1.0000001192092896 0.0)
(0.13166868686676025 5.960464477539062E-7 -5.21540641784668E-8 0.0982980728149414)(-0.029822934418916702 0.0 -2.980232949312267E-8 0.9995551705360413)(0.9999992847442627 0.9999998807907104 0.9999997615814209 0.0)
(0.13633787631988525 0.020000051707029343 0.07568766176700592 -0.025132596492767334)(-0.6774513721466064 -0.7202507853507996 0.10649914294481277 -0.10467228293418884)(1.0015506744384766 0.9999998807907104 1.0000001192092896 0.0)
(0.06180167198181152 0.0798998698592186 0.06078160181641579 -0.02502363920211792)(-0.7070889472961426 -0.7070890069007874 0.0050207702443003654 0.005022003315389156)(1.000000238418579 0.9999999403953552 1.0000001192092896 0.0)
(0.22450745105743408 -1.5800912933627842E-7 -0.03411300852894783 -0.025649964809417725)(-3.469410330581013E-6 2.773013534351776E-7 6.994621071498841E-5 1.0)(1.0000003576278687 0.9999997615814209 1.0 0.0)
(0.06800031661987305 1.15914735943079E-5 -5.4176896810531616E-5 -5.224943161010742E-4)(3.9931042010721285E-6 0.007499575614929199 -6.986159132793546E-5 0.999971866607666)(0.9999995231628418 1.0 0.9999998211860657 0.0)
(0.15122711658477783 -0.021775124594569206 -0.036028649657964706 -0.024937331676483154)(-0.7071067690849304 0.7071066498756409 2.8026843210682273E-4 -2.828749711625278E-4)(1.0 0.9999995827674866 1.0 0.0)
(0.1517029106616974 -0.004614114761352539 -2.3495405912399292E-4 0.020531415939331055)(0.02250034548342228 0.007598401978611946 0.19506101310253143 0.9805035591125488)(0.9999995827674866 0.9999995827674866 1.0000004768371582 0.0)
(0.14979174733161926 -1.1920928955078125E-7 -1.862645149230957E-8 0.020531415939331055)(-0.010970259085297585 -0.007931292988359928 0.382724404335022 0.9237634539604187)(0.9999997615814209 0.9999997615814209 1.0000001192092896 0.0)
(0.2823590040206909 -2.384185791015625E-7 0.004992775619029999 0.04150569438934326)(-8.10250853078287E-8 0.028380470350384712 -1.7881397695873602E-7 0.9995971918106079)(1.0000007152557373 1.0000005960464478 1.0000005960464478 0.0)
(0.2820759415626526 -2.384185791015625E-7 1.6763806343078613E-8 0.03797346353530884)(3.864989039925604E-8 0.05673839524388313 -4.1723257027115324E-7 0.9983890056610107)(1.0000001192092896 1.0 0.9999997019767761 0.0)
(0.10114264488220215 -1.1920928955078125E-7 1.3187527656555176E-6 0.00645291805267334)(-0.04044368490576744 3.166497464235363E-8 0.0 0.9991818070411682)(1.0000007152557373 1.0000007152557373 1.000000238418579 0.0)
(0.005000054836273193 -2.384185791015625E-7 1.1064112186431885E-6 0.009520351886749268)(-0.02022607810795307 -1.9557779395995567E-8 2.980232949312267E-8 0.9997953772544861)(1.0000009536743164 1.000000238418579 1.0000005960464478 0.0)
(0.231722891330719 -1.1920928955078125E-7 2.9802322387695312E-8 0.002285599708557129)(0.7063834071159363 0.03198035806417465 0.03198026865720749 -0.7063829898834229)(1.0000001192092896 0.9999999403953552 0.9999999403953552 0.0)
(0.018261224031448364 0.01970021426677704 0.0027886629104614258 -0.9029252529144287)(0.6146954894065857 0.07776302099227905 0.29998457431793213 0.7253355383872986)(0.9999997615814209 0.9999999403953552 0.9999997615814209 0.0)
(0.053204894065856934 -1.7881393432617188E-7 2.9802322387695312E-8 0.21487027406692505)(-5.215407838932151E-8 2.2351747119842003E-8 -8.940698847936801E-8 0.9999999403953552)(1.0000001192092896 0.9999998211860657 1.0000001192092896 0.0)
(0.03606909513473511 1.1920928955078125E-7 -5.9604644775390625E-8 0.14948266744613647)(1.4901164746561335E-8 0.013146894983947277 1.1920931797249068E-7 0.9999135136604309)(1.0000001192092896 1.0000001192092896 0.9999998807907104 0.0)
(0.1005869209766388 0.03451305627822876 -0.0037763118743896484 -0.8984594345092773)(-0.027600953355431557 1.2290482118260115E-4 -9.629134001443163E-5 0.9996190667152405)(0.9999993443489075 1.000000238418579 0.9999995827674866 0.0)
(0.04424005746841431 5.9604644775390625E-8 -2.384185791015625E-7 -0.22814559936523438)(-2.980232594040899E-8 0.0 1.4901162970204496E-8 0.9999999403953552)(0.9999999403953552 0.9999999403953552 1.0 0.0)
(0.03024590015411377 -7.450580596923828E-8 0.0 -0.05336880683898926)(-5.96046660916727E-8 0.0 2.980233304583635E-8 1.0)(0.9999997019767761 0.9999997615814209 0.9999997615814209 0.0)
(0.1008090078830719 0.010271534323692322 -0.004487156867980957 -0.8900254964828491)(-0.027600975707173347 1.238584954990074E-4 -9.682778181741014E-5 0.9996190071105957)(0.9999993443489075 1.0000003576278687 0.9999995231628418 0.0)
(0.04669696092605591 -8.940696716308594E-8 -2.384185791015625E-7 -0.2253413200378418)(-2.2351747119842003E-8 1.1920931797249068E-7 4.4703494239684005E-8 0.9999999403953552)(0.9999998807907104 0.9999999403953552 0.9999999403953552 0.0)
(0.031088978052139282 2.086162567138672E-7 3.5762786865234375E-7 -0.052474141120910645)(5.960467319710006E-8 -1.043081780949251E-7 -2.980233659855003E-8 1.0)(0.9999998807907104 0.9999998211860657 0.9999998807907104 0.0)
(0.09760302305221558 -0.01325899362564087 -0.002579212188720703 -0.8814303874969482)(-0.02760154753923416 1.236498646903783E-4 -9.652974404161796E-5 0.9996189475059509)(1.0000001192092896 1.0 1.000000238418579 0.0)
(0.04489696025848389 1.4901161193847656E-8 -1.1920928955078125E-7 -0.22307193279266357)(9.685756907629184E-8 1.4901164746561335E-8 -2.980232949312267E-8 0.9999999403953552)(0.9999999403953552 0.9999999403953552 0.9999999403953552 0.0)
(0.031465888023376465 7.450580596923828E-8 0.0 -0.0518721342086792)(7.450584149637507E-9 0.0 0.0 1.0)(0.9999998211860657 0.9999998807907104 0.9999999403953552 0.0)
(0.09500008821487427 -0.03574506938457489 -5.221366882324219E-5 -0.8729028701782227)(-0.027510175481438637 1.2660030915867537E-4 -2.130866732841241E-6 0.999621570110321)(0.9999999403953552 1.000000238418579 0.9999998211860657 0.0)
(0.039302945137023926 -5.9604644775390625E-8 0.0 -0.22158098220825195)(0.0 2.980232949312267E-8 0.0 0.9999999403953552)(0.9999998807907104 0.9999998807907104 1.0000001192092896 0.0)
(0.01902410387992859 4.470348358154297E-8 0.0 -0.0534520149230957)(5.297364623402245E-6 -2.4288901840918697E-6 2.950431053250213E-6 0.9999999403953552)(1.0000001192092896 0.9999999403953552 0.9999997019767761 0.0)
(0.08998164534568787 -0.0016420930624008179 0.012753963470458984 -0.8813233375549316)(1.4901166878189542E-7 -0.1305263340473175 -1.0430816388407038E-7 0.9914448857307434)(1.0 0.9999999403953552 0.9999998807907104 0.0)
(0.08998188376426697 -0.0016420632600784302 0.012754082679748535 -0.8813232183456421)(1.713633963618122E-7 -1.7881397695873602E-7 -1.6391281576488836E-7 0.9999999403953552)(0.9999999403953552 0.9999999403953552 0.9999997615814209 0.0)
(0.004999935626983643 -3.5762786865234375E-7 7.599592208862305E-7 0.035716116428375244)(0.059619270265102386 -7.078052277620372E-8 0.0 0.9982211589813232)(0.9999997615814209 0.9999998807907104 1.0 0.0)
(0.13199996948242188 -3.5762786865234375E-7 1.1175870895385742E-8 0.03675049543380737)(0.029822908341884613 -3.2596297216969106E-8 2.980232949312267E-8 0.999555230140686)(1.0000001192092896 1.0000003576278687 1.0 0.0)
(0.1363372802734375 -0.02000001259148121 0.0756877064704895 -0.02483266592025757)(0.10320363938808441 0.10845133662223816 -0.7122749090194702 0.6857490539550781)(1.0015547275543213 1.0000003576278687 0.9999998807907104 0.0)
(0.061802029609680176 -0.0798998773097992 0.060781802982091904 -0.023825466632843018)(-0.7070889472961426 -0.7070890069007874 0.0050207702443003654 0.005022003315389156)(1.000000238418579 0.9999999403953552 1.0000001192092896 0.0)
(0.23924338817596436 1.0543494681769516E-6 -3.090009558945894E-4 0.003342926502227783)(-0.0024852673523128033 4.043487206217833E-5 4.730349701276282E-6 0.9999968409538269)(0.9999996423721313 1.0 0.9999998807907104 0.0)
(0.23924338817596436 1.054348103934899E-6 -3.0900142155587673E-4 0.003342926502227783)(-0.0024956935085356236 7.048349652905017E-5 4.5977512854733504E-6 0.9999968409538269)(0.9999991655349731 0.9999996423721313 0.9999997019767761 0.0)</hkparam>
            <hkparam name="referenceFloats" numelements="0"/>
            <hkparam name="floatSlots" numelements="0"/>
            <hkparam name="localFrames" numelements="0"/>
            <hkparam name="partitions" numelements="0"/>
        </hkobject>
    </hksection>
</hkpackfile>

```
## Post #93
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-06-04T01:44:15+00:00
- Post Title: Re: Havok binary files

IS anyone still working on this?
And would anyone know where i can still download the Havok animation to or creation tools?
## Post #94
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-04T08:33:33+00:00
- Post Title: Re: Havok binary files

not really, but here's the skeleton (as .smd) from the DarkSouls3 hkx the HunterAP uploaded:

```
version 1
nodes
0 "Master" -1
1 "L_Foot_Target2" 0
2 "L_Foot_Target1" 1
3 "L_Foot_Target" 2
4 "R_Foot_Target2" 0
5 "R_Foot_Target1" 4
6 "R_Foot_Target" 5
7 "RootPos" 0
8 "Pelvis" 7
9 "L_Hip" 8
10 "L_Thigh" 8
11 "L_Calf" 10
12 "L_Calf_Skirt" 11
13 "L_CalfTwist" 11
14 "L_CalfTwist1" 11
15 "L_Foot" 11
16 "L_FootTwist" 15
17 "L_Toe0" 15
18 "L_Knee" 10
19 "L_Knee_Skirt" 10
20 "L_Thigh_Skirt" 10
21 "L_ThighTwist" 10
22 "L_ThighTwist1" 10
23 "L_Wepon_Case" 8
24 "R_Hip" 8
25 "R_Thigh" 8
26 "R_Calf" 25
27 "R_Calf_Skirt" 26
28 "R_CalfTwist" 26
29 "R_CalfTwist1" 26
30 "R_Foot" 26
31 "R_FootTwist" 30
32 "R_Toe0" 30
33 "R_Knee" 25
34 "R_Knee_Skirt" 25
35 "R_Thigh_Skirt" 25
36 "R_ThighTwist" 25
37 "R_ThighTwist1" 25
38 "R_Wepon_Case" 8
39 "RootRotY" 7
40 "RootRotXZ" 39
41 "Spine" 40
42 "Spine1" 41
43 "Spine2" 42
44 "B_Wepon_Case" 43
45 "B_Wepon_Case0_L" 43
46 "B_Wepon_Case0_R" 43
47 "Collar" 43
48 "L_Clavicle" 43
49 "L_Shoulder" 48
50 "L_UpperArm" 48
51 "L_Elbow" 50
52 "L_Forearm" 50
53 "L_ForeArmTwist" 52
54 "L_ForeArmTwist1" 52
55 "L_Hand" 52
56 "L_Finger0" 55
57 "L_Finger01" 56
58 "L_Finger02" 57
59 "L_Finger1" 55
60 "L_Finger11" 59
61 "L_Finger12" 60
62 "L_Finger2" 55
63 "L_Finger21" 62
64 "L_Finger22" 63
65 "L_Finger3" 55
66 "L_Finger31" 65
67 "L_Finger32" 66
68 "L_Finger4" 55
69 "L_Finger41" 68
70 "L_Finger42" 69
71 "L_Shield" 55
72 "L_Weapon" 55
73 "L_UpArmTwist" 50
74 "L_UpArmTwist1" 50
75 "L_Pectoral" 43
76 "L_Po" 43
77 "Neck" 43
78 "Head" 77
79 "R_Clavicle" 43
80 "R_Shoulder" 79
81 "R_UpperArm" 79
82 "R_Elbow" 81
83 "R_Forearm" 81
84 "R_ForeArmTwist" 83
85 "R_ForeArmTwist1" 83
86 "R_Hand" 83
87 "R_Finger0" 86
88 "R_Finger01" 87
89 "R_Finger02" 88
90 "R_Finger1" 86
91 "R_Finger11" 90
92 "R_Finger12" 91
93 "R_Finger2" 86
94 "R_Finger21" 93
95 "R_Finger22" 94
96 "R_Finger3" 86
97 "R_Finger31" 96
98 "R_Finger32" 97
99 "R_Finger4" 86
100 "R_Finger41" 99
101 "R_Finger42" 100
102 "R_Shield" 86
103 "R_Weapon" 86
104 "R_UpArmTwist" 81
105 "R_UpArmTwist1" 81
106 "R_Pectoral" 43
107 "R_Po" 43
108 "SpineArmor1" 42
109 "SpineArmor2" 42
end
skeleton
time 0
0 0.000000 0.000000 0.000000 0.000000 1.570308 0.000000
1 -0.062719 0.976180 0.103349 -1.570302 0.000000 -1.570798
2 0.443363 0.000000 0.000001 -0.000000 -0.000002 0.000000
3 0.423298 -0.000000 -0.000001 -0.000494 0.000346 -0.000000
4 -0.062720 0.976180 -0.103349 -1.574862 0.000001 -1.570789
5 0.443363 0.000001 0.000007 -0.000000 -0.000008 -0.000000
6 0.423298 -0.000001 -0.000017 0.004066 0.000362 0.000001
7 0.000000 0.970000 0.000000 0.000000 -1.570308 0.000000
8 0.000000 0.000001 0.000000 3.141588 0.000000 1.570798
9 -0.000000 0.103349 -0.005000 0.000408 -0.009967 -3.141589
10 -0.000000 0.103349 0.000000 -0.000004 -0.019934 -3.141590
11 0.443364 -0.000000 0.000000 0.000001 0.189795 -0.000001
12 0.005001 -0.000001 0.000000 0.000000 0.000000 0.000000
13 0.194732 -0.000000 0.000000 0.001304 0.000000 -0.000000
14 0.005001 -0.000000 0.000000 0.000652 -0.000000 0.000000
15 0.423298 -0.000000 0.000000 -0.000000 -0.169515 0.000000
16 0.110369 -0.000001 0.000037 -0.000593 -1.566216 0.000592
17 0.110322 -0.000000 0.134743 -3.141570 -1.570308 3.141569
18 0.443837 -0.000000 0.004978 0.000002 0.094897 -0.000001
19 0.443363 -0.000000 0.000000 0.000001 0.094897 -0.000001
20 -0.000000 -0.000000 0.000000 -0.000002 0.000000 -0.000000
21 0.005000 -0.000000 -0.000000 0.001376 -0.000000 -0.000000
22 0.229000 -0.000000 0.000000 0.000687 -0.000000 -0.000001
23 0.035256 0.185465 0.005854 -1.623162 -0.697335 -3.141588
24 -0.000102 -0.103345 -0.005000 -0.000415 -0.009967 3.141592
25 0.000000 -0.103349 -0.000000 0.000000 -0.019934 -3.141591
26 0.443363 0.000000 0.000000 -0.000003 0.189798 -0.000001
27 0.005001 -0.000001 0.000000 0.000000 -0.000000 0.000000
28 0.194736 -0.000000 0.000000 -0.001303 -0.000000 0.000000
29 0.005000 -0.000001 0.000000 -0.000652 -0.000000 0.000000
30 0.423298 -0.000000 0.000000 -0.000000 -0.169518 -0.000000
31 0.110369 -0.000000 0.000038 -0.000086 -1.566216 0.000085
32 0.110322 -0.000000 0.134743 -3.141554 -1.570451 3.141554
33 0.443837 0.000000 0.004977 -0.000001 0.094899 -0.000000
34 0.443364 0.000000 -0.000000 -0.000000 0.094899 -0.000000
35 -0.000000 0.000000 0.000000 -0.000008 0.000000 0.000000
36 0.005000 -0.000000 0.000000 -0.001379 0.000000 -0.000000
37 0.228981 0.000000 -0.000000 -0.000690 0.000000 -0.000000
38 0.035257 -0.185000 0.005852 -1.518443 -0.697336 -3.141587
39 0.000000 0.000001 0.000000 0.000000 1.570308 0.000000
40 0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
41 0.000015 0.092979 0.000000 1.573446 0.000002 1.570033
42 0.088243 -0.000000 -0.000067 0.002486 -0.000033 -0.000008
43 0.088245 0.000000 -0.000177 -0.005134 -0.014202 0.000082
44 -0.019836 -0.000288 -0.158610 0.011244 0.007302 0.994879
45 -0.019836 0.097062 -0.158610 -3.127237 -0.000001 1.570796
46 -0.019836 -0.097060 -0.158610 -3.127237 -0.000001 1.570796
47 0.224507 -0.000000 -0.034113 0.000148 0.000797 0.000309
48 0.151227 0.021775 -0.036029 -3.140796 0.000002 1.570797
49 0.151703 0.004615 -0.000235 -0.047106 0.006123 -0.392896
50 0.149792 0.000000 -0.000000 0.026342 -0.006256 -0.785644
51 0.282360 0.000000 0.004992 -0.000000 0.056769 -0.000000
52 0.282076 0.000001 -0.000000 -0.000000 0.113538 -0.000000
53 0.101075 -0.000000 -0.000000 0.081246 -0.000000 -0.000000
54 0.005000 -0.000000 0.000000 0.040791 -0.000000 -0.000000
55 0.231723 -0.000000 0.000000 1.570797 -0.090485 -0.000000
56 0.018262 -0.019700 0.002789 -1.328216 -0.258871 -0.581257
57 0.053205 0.000000 -0.000000 0.000000 0.000000 -0.000000
58 0.036069 0.000000 0.000000 -0.000000 0.026295 0.000000
59 0.100587 -0.034513 -0.003777 0.055209 0.000240 0.000199
60 0.044240 -0.000000 0.000000 0.000000 0.000000 -0.000000
61 0.030246 0.000000 0.000000 0.000000 -0.000000 0.000000
62 0.100809 -0.010271 -0.004487 0.055209 0.000242 0.000200
63 0.046697 -0.000000 0.000000 0.000000 -0.000000 -0.000000
64 0.031089 0.000000 -0.000000 -0.000000 0.000000 0.000000
65 0.097603 0.013259 -0.002580 0.055210 0.000242 0.000200
66 0.044897 -0.000000 0.000000 -0.000000 -0.000000 -0.000000
67 0.031466 0.000000 0.000000 -0.000000 0.000000 0.000000
68 0.095000 0.035745 -0.000053 0.055027 0.000253 0.000011
69 0.039303 0.000000 0.000000 0.000000 -0.000000 -0.000000
70 0.019024 0.000000 0.000000 -0.000000 -0.000000 -0.000000
71 0.089982 0.001641 0.012757 -0.000001 -0.261800 0.000001
72 0.089982 0.001641 0.012757 3.141591 -0.000000 0.000000
73 0.005000 0.000001 -0.000000 -0.119309 0.000000 0.000000
74 0.131669 0.000001 -0.000000 -0.059655 -0.000000 -0.000000
75 0.136338 0.020000 0.075688 -3.129461 0.299536 1.633850
76 0.061802 0.079900 0.060782 -3.127390 -0.000002 1.570796
77 0.224507 -0.000000 -0.034113 -0.000007 0.000001 0.000140
78 0.068000 0.000012 -0.000054 0.000007 0.014999 -0.000140
79 0.151227 -0.021775 -0.036029 3.140796 -0.000004 -1.570796
80 0.151703 -0.004614 -0.000235 0.047106 0.006123 0.392896
81 0.149792 -0.000000 -0.000000 -0.026342 -0.006256 0.785645
82 0.282359 -0.000000 0.004993 -0.000000 0.056769 -0.000000
83 0.282076 -0.000000 0.000000 0.000000 0.113538 -0.000001
84 0.101143 -0.000000 0.000001 -0.080909 0.000000 -0.000000
85 0.005000 -0.000000 0.000001 -0.040455 -0.000000 0.000000
86 0.231723 -0.000000 0.000000 -1.570797 -0.090485 0.000000
87 0.018261 0.019700 0.002789 1.328216 -0.258871 0.581258
88 0.053205 -0.000000 0.000000 -0.000000 0.000000 -0.000000
89 0.036069 0.000000 -0.000000 0.000000 0.026295 0.000000
90 0.100587 0.034513 -0.003776 -0.055209 0.000240 -0.000199
91 0.044240 0.000000 -0.000000 -0.000000 0.000000 0.000000
92 0.030246 -0.000000 0.000000 -0.000000 0.000000 0.000000
93 0.100809 0.010272 -0.004487 -0.055209 0.000242 -0.000200
94 0.046697 -0.000000 -0.000000 -0.000000 0.000000 0.000000
95 0.031089 0.000000 0.000000 0.000000 -0.000000 -0.000000
96 0.097603 -0.013259 -0.002579 -0.055210 0.000242 -0.000200
97 0.044897 0.000000 -0.000000 0.000000 0.000000 -0.000000
98 0.031466 0.000000 0.000000 0.000000 -0.000000 0.000000
99 0.095000 -0.035745 -0.000052 -0.055027 0.000253 -0.000011
100 0.039303 -0.000000 0.000000 0.000000 0.000000 0.000000
101 0.019024 0.000000 0.000000 0.000011 -0.000005 0.000006
102 0.089982 -0.001642 0.012754 0.000000 -0.261800 -0.000000
103 0.089982 -0.001642 0.012754 0.000000 -0.000000 -0.000000
104 0.005000 -0.000000 0.000001 0.119309 -0.000000 -0.000000
105 0.132000 -0.000000 0.000000 0.059655 -0.000000 0.000000
106 0.136337 -0.020000 0.075688 -0.013558 0.300251 -1.610790
107 0.061802 -0.079900 0.060782 -3.127390 -0.000002 1.570796
108 0.239243 0.000001 -0.000309 -0.004971 0.000081 0.000009
109 0.239243 0.000001 -0.000309 -0.004991 0.000141 0.000009
end
```



DarkSouls3_skel.jpg (134.4 KiB) Viewed 311 times
## Post #95
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-06-04T10:19:28+00:00
- Post Title: Re: Havok binary files

you can help me? with bloodborne the skeleton of monsters has problems when I try to convert it on sfm alchune bones are strangely related. and then there is the problem of the physics of cloaks, hairs etc..i as an editor use 3d studio max would it be possible to create a script?
## Post #96
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-04T10:54:52+00:00
- Post Title: Re: Havok binary files

> Reply from dibe91
>
> as an editor use 3d studio max would it be possible to create a script?I don't have access to 3dsmax since about a year now; so sorry, no.

Also this thread is about hkx files, Havok tools and a C# source from volfin.

Noone did care for a maxscript so far, iirc.
(All I know is that you could use Havok Content Tools with 3dsmax.)

You might upload your bloodborne monster skeleton hkx, though, if any.
## Post #97
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-06-04T16:43:46+00:00
- Post Title: Re: Havok binary files

so if I understand correctly you want the original skeleton. perfect I can do it but I give you all the skeletons of the monsters because it happens to everyone.
## Post #98
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-06-04T17:45:33+00:00
- Post Title: Re: Havok binary files

I need to ask what is the difference between file version 11 and 9  (2013.3.0-r1 and 2011.1.0-r1). It seems like extra padding in places you least expect

AssetCc can convert file type 9 but not type 11
I am trying to write a converter (required a lot of address recalculations and pad removals). I haven't completed this yet but it became obvious that some classes were larger in later representations
has anyone successfully converted a file later than 2012 to an older format?

This is what i ended up with

```
typedef struct
{
    string s<hidden=true>;
}TempStr<read=ReadTemStr, optimize=false>;
string ReadTemStr(TempStr& t)
{
    return t.s;
}

typedef struct 
{
    //ubyte[4]  LayoutRules
    ubyte uk;// no.# Flags ?  = 4
    ubyte uk1;
    ubyte Endianness; // 01 = BE 00 = LE  (Bool)
    ubyte Platform; // ?? 01 = PS3 (Couldbe wrong, or swap with one of above flag)
    
}hkHdrFlags; //Header flags

typedef struct
{
    char Magic[8]; 
	/// This is a user settable tag.
	int32 m_userTag;
		
	/// Binary file version. Currently 9 or 11
	int32 m_fileVersion;
		
	/// The structure layout rules used by this file.
	hkHdrFlags m_layoutRules;
				
	/// Number of packfilesections following this header.
	int32 m_numSections;
		
	/// Where the content's data structure is (section and offset within that section).
	int32 m_contentsSectionIndex;
	int32 m_contentsSectionOffset;

	/// Where the content's class name is (section and offset within that section).
	int32 m_contentsClassNameSectionIndex;
    /// nameSection.AbsAddr + this offset = hkRootLevelContainer
    int32 m_contentsClassNameSectionOffset; 
        
    /// Future expansion
	char m_contentsVersion[16];

    if(m_fileVersion == 9)
    {
        int32 misc;
        int pad[1];
    }
    else
    {
        int32 misc;
        short m_maxPredicates;
        short unkn;
    
        int pad[4];
    }
    
}HavokHdr<bgcolor=cLtGray>;


typedef struct(int padSz) //64
{
    ///
	char sectionHdr[19]; //m_sectionTag[19];
    ///
	char m_nullByte;
    /// Absolute file offset of where this sections data begins.
	unsigned int m_absoluteDataStart;
    /// Offset of local fixups from absoluteDataStart.
	unsigned int m_localFixupsOffset;
    /// Offset of global fixups from absoluteDataStart.
	unsigned int m_globalFixupsOffset;
    /// Offset of virtual fixups from absoluteDataStart.
	unsigned int m_virtualFixupsOffset;
    /// Offset of exports from absoluteDataStart.
	unsigned int m_exportsOffset;
    /// Offset of imports from absoluteDataStart.
	unsigned int m_importsOffset;
    /// Offset of the end of section. Also the section size.
	unsigned int m_endOffset;
    char padding[padSz];
}hkxSection <bgcolor=cLtGreen, read=readSecName>;
string readSecName(hkxSection& s)
{
    string ss = StringToWString(s.sectionHdr,CHARSET_ANSI );
    SPrintf(ss, "%s - Abs: %d, (Off: %d)", ss, s.m_absoluteDataStart, s.m_localFixupsOffset);
    return ss;
}


typedef struct 
{
    uint signature;
    char nine;
    string name;
}CLASSNAME <read=ReadClassName>;
string ReadClassName( CLASSNAME& cn)
{
    return cn.name;
}

HavokHdr header;
local int padSz = 0;
if (header.m_fileVersion == 11)
    padSz = 16;
hkxSection section(padSz)[header.m_numSections]<optimize=false>;

//Use to identify typese
local int currAdd= 0;
while(FTell() < section[1].m_absoluteDataStart-1 )
{
    CLASSNAME classNames;
}

local int objID = 0;
local string tmpName = "";

//A data position descriptor aimed at the current section
//Direct Address
//Non-empty members linker from DATA (used when the next memebr to read is a direct member)
typedef struct
{
	//The data parent, in the current section.	
	int from;	
	//The data position, in the current section.	
	int to;
} DataInternal; //DirectAddress; __Data__1

//A data position descriptor aimed at a given section.
//External Address (pointers)
//Pointer linker from DATA (used when the next memebr to read is a pointer)
typedef struct
{
	//The data parent, in the current section.
	int from;	
	//The section the data is in.
	int section;	
	//The data position, in the given section.
	int to;
} DataExternal<read=PointerAddr>; //ExternalAddress __Data__2&3
string PointerAddr(DataExternal& d2)
{
	string addr ="";  
	//if(d2.from != -1) 
    //    SPrintf( addr, "%d", section[d2.section].m_absoluteDataStart + d2.from );
    return addr;
}

typedef struct
{
    int size;
    byte content[size];
} DataDirectMember<optimize=false>;

typedef struct(int size)
{
    local int sz= size;
    byte a[size];
}DataChunk<optimize=false, read=ReadDataChunk>;
string ReadDataChunk(DataChunk& dc)
{
    string s;
    SPrintf(s, "Addr: %d, Size: %d", FTell(), dc.sz);
    return s;
}


FSeek(section[2].m_absoluteDataStart + section[2].m_localFixupsOffset);
local int data1Size = (section[2].m_globalFixupsOffset - section[2].m_localFixupsOffset);
DataInternal _data_1[data1Size/8]<bgcolor=cLtRed>; //Not objects in the type section? but what?

local int j =0;
local int add2= section[2].m_absoluteDataStart;
for( j =0; j < data1Size/8; j++)
{
    Printf("\nAddr: %d", add2 +  _data_1[j].from);
    FSeek(add2 +  _data_1[j].from);
    Printf("\t[%d]:(%d, %d)", j, _data_1[j].from, _data_1[j].to);
    DataChunk dataChunk(_data_1[j].to - _data_1[j].from)<bgcolor=0x01FF10>;
    if(ReadByte() != '\0' )
        TempStr extraName<bgcolor=0x000000, fgcolor=0xffffff>; //hack    
}


FSeek(section[2].m_absoluteDataStart + section[2].m_globalFixupsOffset);
data1Size = (section[2].m_virtualFixupsOffset - section[2].m_globalFixupsOffset);
//params array pointers
DataExternal params[ (data1Size/12)] <bgcolor=cLtPurple>;


//The actual hkobjects
FSeek(section[2].m_absoluteDataStart + section[2].m_virtualFixupsOffset);
data1Size = (section[2].m_exportsOffset - section[2].m_virtualFixupsOffset);

//How Do we map var to the nodes?
local int nodeCount = (data1Size/12);
DataExternal dataNodes[ nodeCount]<bgcolor=cLtBlue, hidden=false>;
for( j =0; j < nodeCount; j++)
{
    FSeek(section[dataNodes[j].section].m_absoluteDataStart +  dataNodes[j].to);
    TempStr nodeName;

    //IGNORE THIS COMMENT
    //Not all have param Arrays (First one Deosnt? Cos it is a container?)
    if(j > 0)
    {
        FSeek(section[params[j-1].section].m_absoluteDataStart +  params[j-1].to);
        DataChunk ParamArray(4)<bgcolor=0xFFFF00>;
    }

    //FSeek(section[dataNodes[j].section].m_absoluteDataStart +  dataNodes[j].from);
    //Some Data - Class Specific
}

```


Cannot do any more from within the template as the serialization is far more involved
I looked through 56 .h files and converted xmls to figure out what gets serialized and how. There are some annoying defaults involved 
but the whole process seems straight forward from here but very tedious to recreate the classes and write the xml converter. except for the arrays

I did not touch the animation and skinning classes yet only the base hkObjects and HavokBehaviour objects
My plan is to write a converter so the project can be reloaded into havok animation and we can see/modify the blend trees
the behaviour template files are also in xml but seem a bit tedious.
## Post #99
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-06-05T07:39:35+00:00
- Post Title: Re: Havok binary files

This does not make sense
The data does not align



Untitlffed.png (23.69 KiB) Viewed 278 times



//According to the xml conversion

```
public class hkRootLevelContainer  //"parent" null
{
	//objectSize 12
	
	//numImplementedInterfaces=0
	//declaredEnums numelements="0"
	//declaredMembers numelements="1"
	hkArray<hkRootLevelContainerNamedVariant> namedVariants; //TYPE_ARRAY:TYPE_STRUCT "offset"=0 class=#0002	

}

//name="#0002" class="hkClass" signature="0x33d42383"
public class hkRootLevelContainerNamedVariant  //"parent" null
{
	//objectSize 12
		
	//numImplementedInterfaces=0
	//declaredEnums numelements="0"
	//declaredMembers numelements="3"
	TYPE_STRINGPTR name; //"offset" 0	
	TYPE_STRINGPTR className; // "offset" 4	
	hkRefPtr<hkReferencedObject> variant; // TYPE_POINTER:TYPE_STRUCT "offset" 8 class=#0003
			
	//"describedVersion" 1
}

```


Where is there a gap of 12 bytes between the hkArray and the first hkString
The String a vtable and a char*
## Post #100
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-06-05T09:09:39+00:00
- Post Title: Re: Havok binary files

Hi,could somebody help me to get collision meshes from hkx files? I want to extract collision meshes from bloodborne here is example files:
[https://mega.nz/#F!V9ciUIoB!zD-1YAEA7iLeKhdtHt-tIQ](https://mega.nz/#F!V9ciUIoB!zD-1YAEA7iLeKhdtHt-tIQ)

I included also nav meshes just in case. Also these files should be in big endian.
## Post #101
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-06-05T20:40:31+00:00
- Post Title: Re: Havok binary files

Turns out I do not have a clue how the direct and external data work.
The mapping of data is a bit confusing (indirections)
## Post #102
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-06-10T21:36:10+00:00
- Post Title: Re: Havok binary files

I think I'm just trying to ask how you do you bind the data to class. The offsetting seem a bit odd. There are gaps I did not expect.
## Post #103
- Username: ronwall
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 17, 2020 11:54 am
- Post datetime: 2020-10-29T03:16:06+00:00
- Post Title: Re: Havok binary files

> Reply from JohnHudeski ↑Mon Jun 04, 2018 9:44 am at Mon Jun 04, 2018 9:44 am
>
> 
IS anyone still working on this?

This thread  is the top google search on Havok Spline Animation format
and the aswer is in the source code  of HavokLib by Lukas Cone

[memberlist.php?mode=viewprofile&u=45121](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=45121)

[https://github.com/PredatorCZ/HavokLib/ ... ressor.hpp](https://github.com/PredatorCZ/HavokLib/blob/master/source/hka_spline_decompressor.hpp)

Also i read this one that is in python to undertand better the havok formats(no spline animation), well if you go to the xml you can skip this
[https://github.com/krenyy/botw_havok](https://github.com/krenyy/botw_havok)


I'm also writing something near to a spec  of this (cuz im using kaitai)
## Post #104
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2020-10-29T05:12:11+00:00
- Post Title: Re: Havok binary files

Gee, if only we had this information back in 2015 when it actually mattered. Thanks anyway I suppose.
## Post #105
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2020-11-21T05:04:19+00:00
- Post Title: Re: Havok binary files

> Reply from SergeantJoe ↑Thu Oct 29, 2020 1:12 pm at Thu Oct 29, 2020 1:12 pm
>
> 
Gee, if only we had this information back in 2015 when it actually mattered. Thanks anyway I suppose.
## Post #106
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-10T01:34:29+00:00
- Post Title: Re: Havok binary files

I've tried the mentioned tools posted by you guys on the thread, unfortunately neither seem to work for a havok 2010 asset, is anyone still around that could take a look and maybe something can be done to de-serialize this sample to XML? Game name is NFSTheRun.


 staticmodelgroup001of001_physics_win32.zip
(1.47 KiB) Downloaded 24 times


It looks like there are two assets in one based on the havok header, like a bundle perhaps?
Also it has nothing to do with animations.
