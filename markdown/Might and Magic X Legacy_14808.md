## Post #1
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-06T12:46:36+00:00
- Post Title: Might and Magic X Legacy

Hello, I'm trying to extract data from MMX. It's written in Unity so I can access it's asset [with Unity Assets Bundle Extractor](https://github.com/DerPopo/UABE):



Also every .pak file (archive with game files) has it's .info.xml file with informations about it's content:

```
Meshes        0.0 kb	 0.0% 
Animations    0.0 kb	 0.0% 
Sounds        4.2 mb	 99.8% 
Shaders       0.0 kb	 0.0% 
Other Assets  5.0 kb	 0.1% 
Levels        0.0 kb	 0.0% 
Scripts       0.1 kb	 0.0% 
Included DLLs 0.0 kb	 0.0% 
File headers  4.1 kb	 0.1% 
Complete size 4.2 mb	 100.0% 

Used Assets, sorted by uncompressed size:
 477.5 kb	 11.1% Assets/Sounds/Monster/Mermaid/Mermaid_Move2Loop.wav
 413.9 kb	 9.6% Assets/Sounds/Monster/Mermaid/Mermaid_Victory.wav
 376.4 kb	 8.8% Assets/Sounds/Monster/Mermaid/Mermaid_Move1.wav
 375.2 kb	 8.7% Assets/Sounds/Monster/Mermaid/Mermaid_AttackLaunchMeleeCrit.wav
 372.2 kb	 8.7% Assets/Sounds/Monster/Mermaid/Mermaid_Hit.wav
 334.2 kb	 7.8% Assets/Sounds/Monster/Mermaid/Mermaid_IdleBridge.wav
 330.1 kb	 7.7% Assets/Sounds/Monster/Mermaid/Mermaid_AttackLaunchRanged.wav
 265.5 kb	 6.2% Assets/Sounds/Monster/Mermaid/Mermaid_Die.wav
 254.8 kb	 5.9% Assets/Sounds/Monster/Mermaid/Mermaid_AttackLaunchMelee.wav
 226.6 kb	 5.3% Assets/Sounds/Monster/Mermaid/Mermaid_LaunchAttack3.wav
 209.7 kb	 4.9% Assets/Sounds/Monster/Mermaid/Mermaid_Defend.wav
 199.5 kb	 4.6% Assets/Sounds/Monster/Mermaid/Mermaid_LaunchAttack2.wav
 128.4 kb	 3.0% Assets/Sounds/Monster/Mermaid/Mermaid_Turn90Right.wav
 128.4 kb	 3.0% Assets/Sounds/Monster/Mermaid/Mermaid_Turn90Left.wav
 58.5 kb	 1.4% Assets/Sounds/Monster/Mermaid/Mermaid_VictoryBark.mp3
 35.7 kb	 0.8% Assets/Sounds/Monster/Mermaid/Mermaid_IdleBridgeBark.mp3
 29.3 kb	 0.7% Assets/Sounds/Monster/Mermaid/Mermaid_DieBark.mp3
 17.9 kb	 0.4% Assets/Sounds/Monster/Mermaid/Mermaid_AttackCritBark.mp3
 15.7 kb	 0.4% Assets/Sounds/Monster/Mermaid/Mermaid_AttackMagicBark.mp3
 15.7 kb	 0.4% Assets/Sounds/Monster/Mermaid/Mermaid_AttackBark.mp3
 15.7 kb	 0.4% Assets/Sounds/Monster/Mermaid/Mermaid_AbilityBark.mp3
 9.9 kb	 0.2% Assets/Sounds/Monster/Mermaid/Mermaid_HitBark.mp3
 3.8 kb	 0.1% Assets/AudioToolkit/AudioCategories/AudioController_MermaidSounds.prefab
 0.5 kb	 0.0% Built-in AssetBundle: 
 0.3 kb	 0.0% Assets/AudioToolkit/AudioObjects/SFXCombat1AudioObject.prefab
 0.3 kb	 0.0% Assets/AudioToolkit/AudioObjects/DefaultAudioObject.prefab
 0.1 kb	 0.0% Assets/dll/Legacy.Framework.dll

***Player size statistics***
Level 0 '../client/assets/StreamingAssets/res/0a1a214816ad4565869606451173f554.pak' uses 4.2 MB uncompressed / 4.2 MB uncompressed.
Total uncompressed size 4.2 MB. Total uncompressed size 4.2 MB.
System memory in use before: 112.7 MB.
Unloading 26 Unused Serialized files (Serialized files now loaded: 0 / Dirty serialized files: 0)
System memory in use after: 102.3 MB.

Unloading 33 unused Assets to reduce memory usage. Loaded Objects now: 2077.
Total: 17.342653 ms (FindLiveObjects: 0.186541 ms CreateObjectMapping: 0.170071 ms MarkObjects: 7.973805 ms  DeleteObjects: 5.496283 ms)


*** Completed 'Build.WebAssetBundle.WindowsStandalonePlayer' in 1 seconds
</Raw>
```


So I can export RAW file and I know it's type, it should be no problem, but it is. I cannot open extracted file in any program. [Here](https://drive.google.com/open?id=0B90vRKE4dnmJXzN4SVNRSlk5MVU) is example data from game and [here](https://drive.google.com/open?id=0B90vRKE4dnmJdEU3clZuME4wV1E) is extracted RAW sound file that should be WAV. [This](https://drive.google.com/open?id=0B90vRKE4dnmJelBrUWwwQVlsNEU) should be model in PREFAB format.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-07T08:03:19+00:00
- Post Title: Might and Magic X Legacy

jaguar-warrior.dat  



jaguar-warrior_dat.png (79.58 KiB) Viewed 149 times



0x70 - length of face indices (divide by 2 for face count)
0x82f60 - vertex count
0x82f8c - vertex stride(?)

the UV block starts right after the vertex block ends
the length of the vertex block is stride * count
## Post #3
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-07T16:40:11+00:00
- Post Title: Might and Magic X Legacy

Wow, you're awesome. How about other data? I especially need skeletons and animations. Is it possible to extract them? If you need some game files, [here you are](https://drive.google.com/file/d/0B90vRKE4dnmJNWxaSFhFbmw2aW8/view?pref=2&pli=1)
## Post #4
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-09T13:00:56+00:00
- Post Title: Might and Magic X Legacy

Somebody something?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-09T13:31:20+00:00
- Post Title: Might and Magic X Legacy

you won't expect someone to download 124 MB of samples, do you?
Also for animations follow (my) "unwritten rules", please.
upload an animation sample file (<100 kB if possible)
upload suiting skeleton
tell number of bones, if possible
(The more infos you provide the more likely someone will care for your request.)
## Post #6
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-09T16:11:07+00:00
- Post Title: Might and Magic X Legacy

You're right. Sorry for that. I believe that skeleton is with mesh because I cannot find separate file for it. This archive is quite mess, but I believe I extracted all we need for test. [Here you are](https://drive.google.com/open?id=0B90vRKE4dnmJRGtwZjc4Q2VQVjA)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-09T20:49:43+00:00
- Post Title: Might and Magic X Legacy

static mesh format is the same as for characters; we'd need a character model file for skeleton (might be >100 kB)



orc_mesh-dat.jpg (158.51 KiB) Viewed 115 times
## Post #8
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-11T16:51:54+00:00
- Post Title: Might and Magic X Legacy

My fault. This archive is total mess and I pick wrong file. [This set](https://drive.google.com/open?id=0B90vRKE4dnmJeG1yQUwySlowUTg) should be OK
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-11T21:42:29+00:00
- Post Title: Might and Magic X Legacy

thx - did you check those dat files or use hex2obj on them?

On a quick glance I don't see any skeleton data in them.
## Post #10
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-11T22:07:12+00:00
- Post Title: Might and Magic X Legacy

Unity Assets Bundle Extractor defines those files as meshes. I didn't find any separates skeletons file in this archive, so I believe they must be with models, but no I didn't look at those files with hex2obj because I dont' know how to. If somebody give me quick tuturial, that would be great
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-11T22:30:47+00:00
- Post Title: Might and Magic X Legacy

This is a rather simple format which uses floats so the tut button in hex2obj should do.

Anyways getting the mesh wouldn't help you too much. It would only be useful to assure that all data (or > 90% of it) is related to the mesh
and I didn't overlook something.
## Post #12
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-11T22:52:09+00:00
- Post Title: Might and Magic X Legacy

Button 'tut' is disabled in my hex2obj app. What I'm doing wrong? Besides, if there is no skeleton in this file, [this model](https://drive.google.com/open?id=0B90vRKE4dnmJQVFHSl9HUDFBMFE) could help, because MMX uses the same models as Heroes 6, but I don't know if bones are named in the same way. Maybe this helps.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-12T07:10:55+00:00
- Post Title: Might and Magic X Legacy

> Reply from Kwarc
>
> Button 'tut' is disabled in my hex2obj app. What I'm doing wrong?very strange - never heard of such.
As a workaround you could simply open the file hex2obj_tut.rtf in your hex2obj folder.

> Besides, if there is no skeleton in this file, this model could help, because MMX uses the same models as Heroes 6, but I don't know if bones are named in the same way. Maybe this helps.I don't have a clue how you could think this could help?
It's a wavefront obj file which per definition doesn't hold skeleton data, afaik.
## Post #14
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-12T13:43:37+00:00
- Post Title: Might and Magic X Legacy

Right, [that](https://drive.google.com/open?id=0B90vRKE4dnmJWktLZlIwY1Y2Qjg) should be better. It's model with skeleton from H6. I've downloaded newer version of hex2obj and everything works fine. But decoding hexes in that file is really hard for me, because I'm really a noob
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-12T15:39:02+00:00
- Post Title: Might and Magic X Legacy

> Reply from Kwarc
>
> this model could help, because MMX uses the same models as Heroes 6, but I don't know if bones are named in the same way. Maybe this helps.how should we know if the bones are named in the same way if the don't have an MMV skeleton?
H6 skeleton bonenames:
nodes
  0 "NotABone0"  -1
  1 "c:OrcWarrior_geo"  -1
  2 "c:OrcWarrior_base"  1
  3 "c:OrkWarrior_setup"  1
  4 "c:Weapon_setup"  3
  5 "c:OrcWarrior_base_Weapon_export"  4
  6 "c:Shield_setup"  3
  7 "c:Shield_scale_grp"  6
  8 "c:Shield_01_jnt"  7
  9 "c:OrcWarrior_base_Shield"  6
  10 "c:OrcWarrior_Skeleton_grp"  3
  11 "c:weightSpine_grp"  10
  12 "c:OrcWarrior_weightSpine_e_jnt"  11
  13 "c:OrcWarrior_weightSpine_d_jnt"  11
  14 "c:OrcWarrior_weightSpine_c_jnt"  11
  15 "c:OrcWarrior_weightSpine_b_jnt"  11
  16 "c:OrcWarrior_spine_low_jnt"  10
  17 "c:OrcWarrior_hip_jnt"  16
  18 "c:R_Cloth01_jnt"  17
  19 "c:R_Cloth02_jnt"  18
  20 "c:R_Cloth03_jnt"  19
  21 "c:R_Cloth04_jnt"  20
  22 "c:R_Cloth05_jnt"  21
  23 "c:R_Cloth06_jnt"  22
  24 "c:FM_Cloth01_jnt"  17
  25 "c:FM_Cloth02_jnt"  24
  26 "c:FM_Cloth03_jnt"  25
  27 "c:FM_Cloth04_jnt"  26
  28 "c:FM_Cloth05_jnt"  27
  29 "c:FM_Cloth06_jnt"  28
  30 "c:BM_Cloth01_jnt"  17
  31 "c:BM_Cloth02_jnt"  30
  32 "c:BM_Cloth03_jnt"  31
  33 "c:BM_Cloth04_jnt"  32
  34 "c:BM_Cloth05_jnt"  33
  35 "c:BM_Cloth06_jnt"  34
  36 "c:OrcWarrior_rt_upLeg_jnt"  17
  37 "c:OrcWarrior_rt_knee_jnt"  36
  38 "c:OrcWarrior_rt_ankle_jnt"  37
  39 "c:OrcWarrior_rt_ball_jnt"  38
  40 "c:L_Cloth01_jnt"  17
  41 "c:L_Cloth02_jnt"  40
  42 "c:L_Cloth03_jnt"  41
  43 "c:L_Cloth04_jnt"  42
  44 "c:OrcWarrior_lf_upLeg_jnt"  17
  45 "c:OrcWarrior_lf_knee_jnt"  44
  46 "c:OrcWarrior_lf_ankle_jnt"  45
  47 "c:OrcWarrior_lf_ball_jnt"  46
  48 "c:OrcWarrior_spine_mid_jnt"  16
  49 "c:OrcWarrior_spine_hi_jnt"  48
  50 "c:OrcWarrior_spine_end_jnt"  49
  51 "c:OrcWarrior_lf_clavicle_jnt"  50
  52 "c:OrcWarrior_lf_upArm_jnt"  51
  53 "c:OrcWarrior_lf_elbow_jnt"  52
  54 "c:OrcWarrior_lf_wrist_jnt"  53
  55 "c:OrcWarrior_lf_hand_jnt"  54
  56 "c:OrcWarrior_lf_thumb_a_jnt"  55
  57 "c:OrcWarrior_lf_thumb_b_jnt"  56
  58 "c:OrcWarrior_lf_thumb_c_jnt"  57
  59 "c:OrcWarrior_lf_pinkyCup_jnt"  55
  60 "c:OrcWarrior_lf_pinky_a_jnt"  59
  61 "c:OrcWarrior_lf_pinky_b_jnt"  60
  62 "c:OrcWarrior_lf_pinky_c_jnt"  61
  63 "c:OrcWarrior_lf_ringCup_jnt"  55
  64 "c:OrcWarrior_lf_ring_a_jnt"  63
  65 "c:OrcWarrior_lf_ring_b_jnt"  64
  66 "c:OrcWarrior_lf_ring_c_jnt"  65
  67 "c:OrcWarrior_lf_middle_a_jnt"  55
  68 "c:OrcWarrior_lf_middle_b_jnt"  67
  69 "c:OrcWarrior_lf_middle_c_jnt"  68
  70 "c:OrcWarrior_lf_index_a_jnt"  55
  71 "c:OrcWarrior_lf_index_b_jnt"  70
  72 "c:OrcWarrior_lf_index_c_jnt"  71
  73 "c:OrcWarrior_neck_jnt"  50
  74 "c:OrcWarrior_head_a_jnt"  73
  75 "c:LongHair01_jnt"  74
  76 "c:LongHair02_jnt"  75
  77 "c:LongHair03_jnt"  76
  78 "c:LongHair04_jnt"  77
  79 "c:LongHair05_jnt"  78
  80 "c:BHair01_jnt"  74
  81 "c:BHair02_jnt"  80
  82 "c:MHair01_jnt"  74
  83 "c:MHair02_jnt"  82
  84 "c:FHair01_jnt"  74
  85 "c:FHair02_jnt"  84
  86 "c:OrcWarrior_Jaw01_jnt"  74
  87 "c:OrcWarrior_Jaw02_jnt"  86
  88 "c:R_Beard01_jnt"  87
  89 "c:R_Beard02_jnt"  88
  90 "c:L_Beard01_jnt"  87
  91 "c:L_Beard02_jnt"  90
  92 "c:L_Beard03_jnt"  91
  93 "c:M_Beard01_jnt"  87
  94 "c:M_Beard02_jnt"  93
  95 "c:M_Beard03_jnt"  94
  96 "c:M_Beard03_jnt|orc:M_Beard04_j"  95
  97 "c:M_Beard05_jnt"  96
  98 "c:M_Beard06_jnt"  97
  99 "c:M_Skull01_jnt"  50
  100 "c:M_Skull02_jnt"  99
  101 "c:OrcWarrior_rt_clavicle_jnt"  50
  102 "c:OrcWarrior_rt_upArm_jnt"  101
  103 "c:OrcWarrior_rt_elbow_jnt"  102
  104 "c:OrcWarrior_rt_wrist_jnt"  103
  105 "c:OrcWarrior_rt_hand_jnt"  104
  106 "c:OrcWarrior_rt_ringCup_jnt"  105
  107 "c:OrcWarrior_rt_ring_a_jnt"  106
  108 "c:OrcWarrior_rt_ring_b_jnt"  107
  109 "c:OrcWarrior_rt_ring_c_jnt"  108
  110 "c:OrcWarrior_rt_middle_a_jnt"  105
  111 "c:OrcWarrior_rt_middle_b_jnt"  110
  112 "c:OrcWarrior_rt_middle_c_jnt"  111
  113 "c:OrcWarrior_rt_index_a_jnt"  105
  114 "c:OrcWarrior_rt_index_b_jnt"  113
  115 "c:OrcWarrior_rt_index_c_jnt"  114
  116 "c:OrcWarrior_rt_thumb_a_jnt"  105
  117 "c:OrcWarrior_rt_thumb_b_jnt"  116
  118 "c:OrcWarrior_rt_thumb_c_jnt"  117
  119 "c:OrcWarrior_rt_pinkyCup_jnt"  105
  120 "c:OrcWarrior_rt_pinky_a_jnt"  119
  121 "c:OrcWarrior_rt_pinky_b_jnt"  120
  122 "c:OrcWarrior_rt_pinky_c_jnt"  121
  123 "c:grpJoint1ZERO"  1
  124 "c:wpn_export_jnt"  123
end

You could try to use this H6 skeleton for MMX but in my experience it's very unlikely that it will fit:


 H6-OrcWarrioroutout_skel.zip
(3.71 KiB) Downloaded 16 times
## Post #16
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-12T16:00:51+00:00
- Post Title: Re: Might and Magic X Legacy

Ok, but the question is how to extract animation from RAW data? File named 'shield-bash' should be AnimationClip.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-12T16:27:11+00:00
- Post Title: Re: Might and Magic X Legacy

It does not make sense to care for animations as long as you don't have a model with suiting skeleton and working skinning.
## Post #18
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-08-12T18:07:25+00:00
- Post Title: Re: Might and Magic X Legacy

I understand, are you sure that model doesn't have skeleton?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-12T19:14:02+00:00
- Post Title: Re: Might and Magic X Legacy

talking about orc_warrior_base.dat? then, nope, I'm not sure.

But I didn't find any bone names in it. It's a waste of life and time to analyse 3D data without bone names.
So we don't even know the number of bones.

(Seems there's 105 matrices blocks.)
## Post #20
- Username: Kwarc
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 06, 2016 9:39 pm
- Post datetime: 2016-09-08T07:34:39+00:00
- Post Title: Re: Might and Magic X Legacy

I would try, but I don't know how to extract animation. Sample animation should be [here](https://drive.google.com/file/d/0B90vRKE4dnmJRGtwZjc4Q2VQVjA/view) (shield bash file). I would extract it from [Heroes VI](https://drive.google.com/open?id=0B90vRKE4dnmJbm1sancyQVpSVUU), but [this script isn't finnished](http://forum.xentax.com/viewtopic.php?f=16&t=8582) and I have no idea how to fix it :/
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-09T08:08:26+00:00
- Post Title: Re: Might and Magic X Legacy

> Reply from Kwarc
>
> Sample animation should be here  (shield bash file)no, is not, there's the py script for Homm6 gobj files and a gobj sample.
(shield_bash.dat is from MMX, isn't it?)

Also we'd need the MMX skeleton before we can deal with animations.

And as I wrote 4 weeks ago:
"how should we know whether the [MMX] bones are named in the same way [as for the HoMM6 skeleton] if the don't have an MMX skeleton?"

We don't even know whether the skeletons have the same bone count.

Don't expect me to do a profound investigation - I don't have the time for such.
So if I don't understand some data after 15 minutes I'll stop.

(I'm more a patcher of scripts and sources if they don't behave like they should.  )

Also I'm going to have hard times 'till Xmas so all what I'm doing here is just for relaxing.
