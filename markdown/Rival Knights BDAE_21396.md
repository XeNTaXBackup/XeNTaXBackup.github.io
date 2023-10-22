## Post #1
- Username: outlawer1545
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 17, 2019 1:12 pm
- Post datetime: 2019-11-17T05:30:35+00:00
- Post Title: Rival Knights BDAE

Hi im the newbile of XenTaX User
first sorry for my bad english   

i extracted from gameloft Mobile app game 'rival knights' data file with android emulator
and i finally got a some of resource file

but seems thoes resource is encrypted with bdae

so i tryin to find all of forum post about the 'gameloft bdae' 
i tried all as i can get noesis plugin, 3ds max script but it is not workin

as i know bdae can get 3d model with hex2obj but i wish got a with rigged model

somehow i can found some of otherway 
using UU3D Pro plugin but this one should be spend some money.. 

so i uploaded this post for find otherways 
plz.. help me plz..

here is bdae models sample

[https://drive.google.com/file/d/1t_1_TG ... sp=sharing](https://drive.google.com/file/d/1t_1_TG0VYS8Tx8AyShEUcz85WM1BiS18/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-17T07:32:19+00:00
- Post Title: Rival Knights BDAE

> Reply from outlawer1545 ↑Sun Nov 17, 2019 1:30 pm at Sun Nov 17, 2019 1:30 pm
>
> as i know bdae can get 3d model with hex2obj"To know" is not "to have"   
.



T01Armor001-bdae.png (99.96 KiB) Viewed 79 times



> but i wish got a with rigged modelYou know you'll need an hierarchical skeleton for such?
bone names with maybe partial hierarchy, no parenting indices:

```
  1  T01Armor001_d.tga 
  2  T01Armor001_d_tga 
  3  ./T01Armor001_d.tga 
  4  T01Armor001_n.tga 
  5  T01Armor001_n_tga 
  6  ./T01Armor001_n.tga 
  7  T01_cubemap.dds 
  8  T01_cubemap_dds 
  9  ../../battlefields/T01Battlefield/T01_cubemap.dds 
 10  Material__14 
 11  Metal.bdae 
 12  #Metal-fx 
 13  DiffuseSampler 
 14  NormalMapSampler 
 15  ReflectionCubeSampler 
 16  ReflectionCube2Sampler 
 17  Reflection2Factor 
 18  SphericalEnvSampler 
 19  GoldReflectionColor 
 20  Metal-fx-profile_GLES2/CurrentTechnique 
 21  NotHardwareSkinned 
 22  T01Armor001-mesh 
 23  T01Armor001 
 24  T01Armor001-mesh-skin 
 25  T01Armor001.max 
 26  T01Armor001_max 
 27  Bip001-node 
 28  Bip001 
 29  Bip001_Pelvis-node 
 30  Bip001_Pelvis 
 31  Bone17 
 32  Bip001_L_Thigh-node 
 33  Bip001_L_Thigh 
 34  Bone13 
 35  Bip001_L_Calf-node 
 36  Bip001_L_Calf 
 37  Bone4 
 38  Bip001_L_Foot-node 
 39  Bip001_L_Foot 
 40  Bone10 
 41  Bip001_L_Toe0-node 
 42  Bip001_L_Toe0 
 43  Bone14 
 44  Bip001_R_Thigh-node 
 45  Bip001_R_Thigh 
 46  Bone27 
 47  Bip001_R_Calf-node 
 48  Bip001_R_Calf 
 49  Bone18 
 50  Bip001_R_Foot-node 
 51  Bip001_R_Foot 
 52  Bone24 
 53  Bip001_R_Toe0-node 
 54  Bip001_R_Toe0 
 55  Bone28 
 56  Bip001_Spine-node 
 57  Bip001_Spine 
 58  Bone30 
 59  Bip001_Spine1-node 
 60  Bip001_Spine1 
 61  Bone31 
 62  Bip001_Spine2-node 
 63  Bip001_Spine2 
 64  Bone32 
 65  Bip001_L_Clavicle-node 
 66  Bip001_L_Clavicle 
 67  Bone5 
 68  Bip001_L_UpperArm-node 
 69  Bip001_L_UpperArm 
 70  Bone15 
 71  Bip001_L_Forearm-node 
 72  Bip001_L_Forearm 
 73  Bone11 
 74  Bip001_L_Hand-node 
 75  Bip001_L_Hand 
 76  Bone12 
 77  Bip001_L_Finger0-node 
 78  Bip001_L_Finger0 
 79  Bone6 
 80  Bip001_L_Finger01-node 
 81  Bip001_L_Finger01 
 82  Bone7 
 83  Bip001_L_Finger1-node 
 84  Bip001_L_Finger1 
 85  Bone8 
 86  Bip001_L_Finger11-node 
 87  Bip001_L_Finger11 
 88  Bone9 
 89  shield_dummy-node 
 90  shield_dummy 
 91  LastPose = undefined
 
 92  Point_L_ShoulderPad-node 
 93  Point_L_ShoulderPad 
 94  B_L_Clavicle_pad001-node 
 95  B_L_Clavicle_pad001 
 96  Bip001_Neck-node 
 97  Bip001_Neck 
 98  Bone16 
 99  Bip001_Head-node 
100  Bip001_Head 
101  Bone3 
102  helm_dummy-node 
103  helm_dummy 
104  aim_target_head-node 
105  aim_target_head 
106  aim_target_head-node_PIVOT 
107  aim_target_head_PIVOT 
108  helm_dummy-node_PIVOT 
109  helm_dummy_PIVOT 
110  Bip001_R_Clavicle-node 
111  Bip001_R_Clavicle 
112  Bone19 
113  Bip001_R_UpperArm-node 
114  Bip001_R_UpperArm 
115  Bone29 
116  Bip001_R_Forearm-node 
117  Bip001_R_Forearm 
118  Bone25 
119  Bip001_R_Hand-node 
120  Bip001_R_Hand 
121  Bone26 
122  Bip001_R_Finger0-node 
123  Bip001_R_Finger0 
124  Bone20 
125  Bip001_R_Finger01-node 
126  Bip001_R_Finger01 
127  Bone21 
128  Bip001_R_Finger1-node 
129  Bip001_R_Finger1 
130  Bone22 
131  Bip001_R_Finger11-node 
132  Bip001_R_Finger11 
133  Bone23 
134  lance_dummy-node 
135  lance_dummy 
136  Point_R_ShoulderPad-node 
137  Point_R_ShoulderPad 
138  B_R_Clavicle_pad001-node 
139  B_R_Clavicle_pad001 
140  aim_target_left-node 
141  aim_target_left 
142  aim_target_left-node_PIVOT 
143  aim_target_left_PIVOT 
144  aim_target_right-node 
145  aim_target_right 
146  aim_target_right-node_PIVOT 
147  aim_target_right_PIVOT 
148  Point_L_Pad-node 
149  Point_L_Pad 
150  B_L_Thigh_Pad001-node 
151  B_L_Thigh_Pad001 
152  Bone1 
153  Point_R_Pad-node 
154  Point_R_Pad 
155  B_R_Thigh_Pad001-node 
156  B_R_Thigh_Pad001 
157  Bone2 
158  camera_target_dummy-node 
159  camera_target_dummy 
160  T01Armor001-node 
161  #T01Armor001-mesh-skin 
162  #Material__14 
163  Default 
164  DefaultGold 
165  NotHardwareSkinnedGold 
166  #B_L_Thigh_Pad001-node 
167  #B_R_Thigh_Pad001-node 
168  #Bip001_Pelvis-node 
169  lance_tip_1-node 
170  lance_tip_1 
171  #T01Armor001.max 

```
If you can't do it for yourself you have to wait for someone who can.
## Post #3
- Username: outlawer1545
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 17, 2019 1:12 pm
- Post datetime: 2019-11-17T08:15:58+00:00
- Post Title: Rival Knights BDAE

thx for your effort..
is there any chance for get quickbms script about encryted file?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-17T09:05:32+00:00
- Post Title: Rival Knights BDAE

file signature is "BRES", T01Armor001.bdae is not encrypted, not even compressed
## Post #5
- Username: outlawer1545
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 17, 2019 1:12 pm
- Post datetime: 2019-11-17T09:13:14+00:00
- Post Title: Rival Knights BDAE

thx for answer
now i will search what as i can do
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-17T09:33:12+00:00
- Post Title: Rival Knights BDAE

There's the BRRES Viewer (version 1.0-1.2) by Kentilan.
File signature is "bres" here and it expects "MOD0" and "TEX0". Your bdae doesn't contain the latter and thus sadly is not loaded.
## Post #7
- Username: outlawer1545
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 17, 2019 1:12 pm
- Post datetime: 2019-11-17T09:45:16+00:00
- Post Title: Rival Knights BDAE

mean that's not workin tho.. what should i do?
