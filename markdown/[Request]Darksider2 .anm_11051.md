## Post #1
- Username: RatedR203
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 17, 2013 5:16 am
- Post datetime: 2013-12-17T20:22:30+00:00
- Post Title: [Request]Darksider2 .anm

Hello,i'm a little bit begginer in 3ds max,i unpacked darksiders and i used noesis for .dcm files.
But animations are .anm and i dont know how to use it in 3ds max or noesis.
Anyone can help me?
Sorry if i wrong section,but i don't know where is section to put a question here.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-18T14:14:23+00:00
- Post Title: [Request]Darksider2 .anm

> Reply from RatedR203
>
> Hello,i'm a little bit begginer in 3ds max,i unpacked darksiders and i used noesis for .dcm files.Hi RatedR203, welcome to the forum!  
It's finale00's Noesis python plugin fmt_DarkSiders2_dcm.py, isn't it?

> But animations are .anm and i dont know how to use it in 3ds max or noesis.
Afaik anims are not handled by the script. 
You'll need to upload a .anm sample so that someone could have a look at.

A .dcm sample would also be nice.
## Post #3
- Username: RatedR203
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 17, 2013 5:16 am
- Post datetime: 2013-12-18T23:39:19+00:00
- Post Title: [Request]Darksider2 .anm

Here is a sample .anm from darksiders2 
[http://www22.zippyshare.com/v/4428242/file.html](http://www22.zippyshare.com/v/4428242/file.html)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-19T00:02:52+00:00
- Post Title: [Request]Darksider2 .anm

Thx - but an anim without the model is useless.
Would need the DeadLord model, too.

Also some "skeletal reference" would be required. Is there a DeadLord file where "Biped",
"Pelvis", "Root", "Head", or "bone" is contained?
## Post #5
- Username: RatedR203
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 17, 2013 5:16 am
- Post datetime: 2013-12-19T08:47:05+00:00
- Post Title: [Request]Darksider2 .anm

Model of deadlord: [http://www30.zippyshare.com/v/52433639/file.html](http://www30.zippyshare.com/v/52433639/file.html)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-19T14:09:15+00:00
- Post Title: [Request]Darksider2 .anm

Thank you.
Sry to bother you: for me with this model the script crashes Noesis:

Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "..\noesisv4092\plugins\python\fmt_DarkSiders2_dcm.py", line 31, in noepyLoadModel
    parser.parse_file()
  File "..\noesisv4092\plugins\python\fmt_DarkSiders2_dcm.py", line 191, in parse_file
    self.parse_skinned_meshes(numMesh)
  File "..\noesisv4092\plugins\python\fmt_DarkSiders2_dcm.py", line 109, in parse_skinned_meshes
    rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, mesh.numIdx, noesis.RPGEO_TRIANGLE, 1)        
RuntimeError: Index buffer was not valid for drawing.

Looks like a problem with structSize but I won't waste more time on debugging so my question would be:
does this model load for you?
If 'yes', could you please paste the py script you're using (in code tags)?
## Post #7
- Username: RatedR203
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 17, 2013 5:16 am
- Post datetime: 2013-12-19T19:13:34+00:00
- Post Title: [Request]Darksider2 .anm

From here: 
```
https://www.dropbox.com/s/7stlpd4qvkq3096
```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-19T19:41:08+00:00
- Post Title: [Request]Darksider2 .anm

that's the script I'm using, too.

It is loading the deadlord_a.dcm without any problems?

If 'yes' I've to search for my error.

edit: I solved the .dcm prob in another way:
[](http://www.pic-upload.de/view-21684082/DS2.jpg.html)
## Post #9
- Username: RatedR203
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 17, 2013 5:16 am
- Post datetime: 2013-12-30T01:39:05+00:00
- Post Title: [Request]Darksider2 .anm

.dcm i know how to import,but i want to know how to import .anm from darksiders in 3ds max
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-30T08:55:54+00:00
- Post Title: [Request]Darksider2 .anm

yes.
But before you can import animations you'll need to understand the model format.
That's the sense of my approach.

Firstly I couldn't reveal the bones parenting (from the .dcm model):

28. Bone_BM_Thigh_R
239

29. Bone_BM_Calf_L
76? (331)

30. Bone_BM_Thigh_L
75? (330)

31. Bone_BM_Spine1
86

32. Bone_BM_Finger_Pinky1_L
161

33. Bone_BM_Finger_Ring1_L
156

34. Bone_BM_Finger_Middle1_L
152

And since the DeadLord_Attack1.anm file you provided doesn't contain any hint (at least I didn't find one)
which skeletal bone is refering to which data section I don't think that someone will dig deeper into this too soon.
## Post #11
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2014-01-02T18:22:57+00:00
- Post Title: [Request]Darksider2 .anm

Any success?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T19:58:00+00:00
- Post Title: [Request]Darksider2 .anm

I tried to "translate" the skeleton to a PrimaryBasicMale-smd (see SleepingDogs thread,
[viewtopic.php?f=16&t=10730&start=90](http://forum.xentax.com/viewtopic.php?f=16&t=10730&start=90) Dec., 2nd)
but some bones are missing/don't fit:

...
51 "Bone_BM_Finger_Pinky1_L" 25
52 "Bone_BM_Finger_Pinky1_R" 26
53 "Bone_BM_Finger_Pinky2_L" 51
54 "Bone_BM_Finger_Pinky2_R" 52
55 "Bone_BM_Finger_Pinky3_L" 53
56 "Bone_BM_Finger_Pinky3_R" 54
57 "Bone_BM_ForeArmRoll_L" 21
58 "Bone_BM_ForeArmRoll_R" 22
59 "Bone_BM_UpperArmRoll_L" 19
60 "Bone_BM_UpperArmRoll_R" 20
--61 "Bip01 L Prop" 25
--62 "Bip01 R Prop" 26
63 "Bone_BM_Jaw" 10
64 "Bone_BM_Face_UpperLip1_R" 10 -- there are too many lip parts in DS2
65 "Bone_BM_Face_UpperLip2_R" 10
66 "Bone_BM_Face_UpperLip2_L" 10
67 "Bone_BM_Face_UpperLip1_L" 10
68 "Bone_BM_Face_EyeLid_L" 10
69 "Bone_BM_Face_EyeBrow_L" 10
70 "face_ingame_l_inner_eyebrow" 10 -- and too less eyebrow parts
71 "Bone_BM_Face_EyeBrow_R" 10
72 "face_ingame_r_inner_eyebrow" 10
73 "Bone_BM_Face_EyeLid_R" 10
--74 "face_ingame_r_eye" 10
--75 "face_ingame_l_eye" 10
76 "Bone_BM_Face_LowerLip2_R" 63
77 "Bone_BM_Face_LowerLip2_L" 63
--78 "CameraSync01" 2
--79 "Bip01 L Hand Effector" 25
--80 "Bip01 R Hand Effector" 26
81 "l_upperarm_twist" 0
82 "r_upperarm_twist" 0
83 "l_shoulder_joint" 0
84 "r_shoulder_joint" 0

Since I don't owe the game so far I don't think that I will bother myself analyzing the anim file.

(Maybe I'll finish the skeleton some day, but not too soon.)
## Post #13
- Username: Shadowmist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 06, 2014 3:51 am
- Post datetime: 2014-11-09T02:38:22+00:00
- Post Title: [Request]Darksider2 .anm

Hey guys, I have both the models as well as skeletons extracted. Could I help in any way with providing of the assets so that we can get the animations extracted? This game has awesome animations especially Death's unique stances. Any help would be greatly appreciated!
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-09T14:00:35+00:00
- Post Title: [Request]Darksider2 .anm

> Reply from Shadowmist
>
> Could I help in any way with providing of the assets so that we can get the animations extracted?maybe (see below).

atm the parenting bone IDs are unknown. Also the order of bones is strange:

17. Bone_BM_Finger_Pinky1_L
161
18. Bone_BM_Finger_Ring1_L
156
19. Bone_BM_Finger_Middle1_L
152
20. Bone_BM_Finger_Ring2_L
157
21. Bone_BM_Finger_Ring3_L
158
22. Bone_BM_Finger_Index1_L
147
23. Bone_BM_Finger_Middle2_L
153
24. Bone_BM_Finger_Middle3_L
154
25. Bone_BM_Finger_Thumb1_L
139
26. Bone_BM_Finger_Index2_L
148
...

The parent bone IDs might be calculated from the bold numbers or not.
But I'm really bored by such nonsense.

So I just put in the DS2 bonenames into a decent skeleton, PrimaryBasicMale from SleepingDogs (where the developers don't seem to have consumed drugs as the ones from DS2 might have, hahaha  )



PrimaryBasicMale_with_DS2_bonenames.jpg (123.24 KiB) Viewed 267 times


(well, to be honest, my knowledge on 3D modelling and drugs is rather poor, so I probably don't know what I'm talking about...  )

The pos/rotations are still the ones from Sleeping Dogs so uploading the skeleton file wouldn't help here.

Now to your request - you could try finding a DS2 model with less lip parts and more eyebrow parts (see my post above)
using zaramot's import script from this thread:
[viewtopic.php?f=16&t=9483&start=75](http://forum.xentax.com/viewtopic.php?f=16&t=9483&start=75)

If you find one I could try to build a complete SMD skeleton file.

(yes, you're keen on the animations. But for me it doesn't make sense to care for animations as long as the skeleton is not finished.)
## Post #15
- Username: countzero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 03, 2014 10:04 pm
- Post datetime: 2014-12-06T03:55:30+00:00
- Post Title: [Request]Darksider2 .anm

{removed}
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-06T08:45:17+00:00
- Post Title: Re: [Request]Darksider2 .anm

looks like zaramot's solution, with the bones hierarchy unsolved?



Uriel_bones.JPG (54.01 KiB) Viewed 112 times



Can't check it 'cause I don't have max2015.
## Post #17
- Username: countzero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 03, 2014 10:04 pm
- Post datetime: 2014-12-06T22:13:29+00:00
- Post Title: Re: [Request]Darksider2 .anm

It is.  Had to assign matIDs manually to match UV coordinate seams.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-07T01:23:54+00:00
- Post Title: Re: [Request]Darksider2 .anm

Ty for trying but couldn't load your max2013 version of the file neither with 3dsmax2013, 32 bit nor 64 bit
It says: "was saved by a newer version of 3ds Max and cannot be loaded."
(maybe a PC problem, it's very old, hope Santa is merciful sending me a new one... Santa, ... ,hello??).

But don't bother.

I gave the bones hierarchy problem another try. 

Looked like left hand fingerbones have to be ordered like this (with their order in the file "BoneIDs" 18,19,20,...,31.32 ignored):

(problem to be solved: Thumb1_L, Index1_L should have Bone_BM_Hand_L as a parent)

deadlord_a.dcm

 26 - Bone_BM_Finger_Thumb1_L #(139)
 28 - Bone_BM_Finger_Thumb2_L #(140)
 29 - Bone_BM_Finger_Thumb3_L #(141)

 23 - Bone_BM_Finger_Index1_L #(147)
 27 - Bone_BM_Finger_Index2_L #(148)
 32 - Bone_BM_Finger_Index3_L #(149)

 20 - Bone_BM_Finger_Middle1_L #(152)
 24 - Bone_BM_Finger_Middle2_L #(153)
 25 - Bone_BM_Finger_Middle3_L #(154)

 19 - Bone_BM_Finger_Ring1_L #(156)
 21 - Bone_BM_Finger_Ring2_L #(157)
 22 - Bone_BM_Finger_Ring3_L #(158)

 18 - Bone_BM_Finger_Pinky1_L #(161)
 30 - Bone_BM_Finger_Pinky2_L #(162)
 31 - Bone_BM_Finger_Pinky3_L #(163)

Fell free to finish the bones hierarchy since I'm too busy.
I would take the #(xxx) parenting numbers as a guideline only and with
 5  Bone_BM_Hand_L
chose the ids like this for example
 18 - Bone_BM_Finger_Thumb1_L 5
 19 - Bone_BM_Finger_Thumb2_L 18
 20 - Bone_BM_Finger_Thumb3_L 19

(You also could try to order them alphabetically which might work faster.)

edit: hehehe, seems as if I randomly grabbed the easiest part. With the right hand it looks as crazy as before:
 42 Bone_BM_Finger_Thumb1_R #(205)
 44 Bone_BM_Finger_Thumb2_R #(211)
 45 Bone_BM_Finger_Thumb3_R #(216)

 39 Bone_BM_Finger_Index1_R #(202)
 43 Bone_BM_Finger_Index2_R #(210)
 48 Bone_BM_Finger_Index3_R #(215)

 36 Bone_BM_Finger_Middle1_R #(201)
 40 Bone_BM_Finger_Middle2_R #(208)
 41 Bone_BM_Finger_Middle3_R #(214)

 34 Bone_BM_Finger_Ring1_R #(200)
 37 Bone_BM_Finger_Ring2_R #(209)
 38 Bone_BM_Finger_Ring3_R #(213)

 35 Bone_BM_Finger_Pinky1_R #(204)
 46 Bone_BM_Finger_Pinky2_R #(207)
 47 Bone_BM_Finger_Pinky3_R #(212)
## Post #19
- Username: countzero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 03, 2014 10:04 pm
- Post datetime: 2014-12-08T06:34:09+00:00
- Post Title: Re: [Request]Darksider2 .anm

Thanks for your work on the bones hierarchy.  I guess the *.anm files are pretty useless.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-08T10:12:15+00:00
- Post Title: Re: [Request]Darksider2 .anm

thx again. Got it loaded (so can spare the money for a new PC another month  )
