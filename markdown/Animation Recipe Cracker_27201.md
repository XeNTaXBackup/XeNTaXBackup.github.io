## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-14T15:05:06+00:00
- Post Title: Animation Recipe Cracker

1) Introduction
Animation Recipe Cracker, abbreviated as ARC, is a helper tool aimed for quick research and examination on animation data. It provides a text-based C-like layout definition interface with dozens of pre-defined variables, along with other commands for custom variable definition, allowing to de-serialize different animation formats in a concise yet flexible way. There're also plenty of useful GUI options for interpreting the read data.

2) Change Log

```
				Bug fix for matrix convertion.
2023.09.14 - v1.0.1		Initial release.

```

3) User Interface


4) Main Features
1. Support for parsing animation related data of all sorts of data types;
2. Ability to handle variant-length data structures;
3. Support for common arithmetic, logical and bit operations;
4. Support for conditional evaluations and loop statements;
5. Support for dictionary/vector assignment and reference;
6. Formatting operations for debugging raw/converted transformation info and entire data pool;
7. Visualization of animation;
8. Export of the animation as the FBX format.

5) Notes

There are some components used or required by ARC which are not likely to be changed frequently so they're detached from the release of the ARC executable.

The first component is an external mesh viewer called "ViewScene" which ARC uses to preview the animation.

The second component is required by ARC for its GUI is based on Qt technology thus it requires the Qt dependencies for execution.

These components can be downloaded through the links provided in the attachment.

You must place both the ViewScene folder and the Qt dependencies into the same path of the ARC executable.
The overall folder layout of ARC should be:

```
ARC/ViewScene/*
ARC/platforms/*
ARC/Qt5**.dll

```


Microsoft Visual C++ 2015 Redistributable (x86) or above is required for runtime.

6) Download
[ARC.7z](https://xentaxbackup.github.io/file/24374_ARC.7z)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-14T15:09:20+00:00
- Post Title: Animation Recipe Cracker

Refer to the user manual for detail usage.
[ARC Manual.7z](https://xentaxbackup.github.io/file/24341_ARC Manual.7z)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-14T15:12:36+00:00
- Post Title: Animation Recipe Cracker

Example:





stand.gif (59.84 KiB) Viewed 436 times
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-14T15:14:27+00:00
- Post Title: Animation Recipe Cracker

Skeleton dump and animation file of the above example:


 stand.7z
(32.37 KiB) Downloaded 20 times



Layout context:

```
long	posCnt
long	skip[posCnt][3]
long	skip
long	boneCnt
begin	loop[boneCnt]
	long	skip[2]
	long	animKeyOffset
	calc	animKeyOffset[/][6]
	dict	OffsetToBoneMap[animKeyOffset][boneIdx]
	long	skip[6]
end	loop[boneCnt]
begin	loop[boneCnt]
	value	boneIndex[OffsetToBoneMap][boneIdx]
end	loop[boneCnt]
long	keyCnt
begin	loop[keyCnt]
	long	elementCnt
	begin	loop[boneCnt]
		float	Translation[3]
		float	Rotation[3]
	end	loop[boneCnt]
end	loop[keyCnt]

```


```
BigEndian, Quaternion, ColMajor, Up/Front/Right: +Z/-Y/X
```

Related thread:
[viewtopic.php?p=192417#p192417](https://forum.xentax.com/viewtopic.php?p=192417#p192417)
## Post #5
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-09-20T17:34:31+00:00
- Post Title: Animation Recipe Cracker

This looks amazing! I have a baked animation format that encodes eulers as short3, and loc as bounded short3, but I haven't been able to work out how loc transform is to be interpreted. I'll definitely try this tool on that format at some point!
## Post #6
- Username: reggin2023
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 07, 2023 1:49 pm
- Post datetime: 2023-09-20T20:47:15+00:00
- Post Title: Animation Recipe Cracker

I also have a problematic (for me) animation, I tried to get it with your tool, but nothing worked

```
long skip[3]//magic
long skip[1]//anim count
short boneCnt
short KeyCnt
begin loop[keyCnt]
	begin loop[boneCnt]
		//float TransformMatrix[12] EDIT >> note from Bigchillghost in the next msg 
		float Rotation[9]
		float Translation[3]
	end loop[boneCnt]
end loop[keyCnt]

```

[001c7b6a.zip](https://xentaxbackup.github.io/file/24362_001c7b6a.zip)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-21T17:43:14+00:00
- Post Title: Animation Recipe Cracker

> Reply from reggin2023 ↑Thu Sep 21, 2023 4:47 am at Thu Sep 21, 2023 4:47 am
>
> 
I also have a problematic (for me) animation, I tried to get it with your tool, but nothing worked
The key data should be represented as a "Rotation[9]" followed by a "Translation[3]" instead of a "TransformMatrix[12]", which is for row-major storage only. Anyway, the anim keys of the 1st frame have a huge deviation than the initial frame at the bone area, while the following frames have less deviation from each other. So it's likely that the initial frame need to be multiplied by the following keys. Not sure whether each following frame stores relatively to its previous one, just wild guesses. Whatsoever, world space animations and/or other types of delta storage have exceeded the ability of this tool. So your best chance might be looking for clues from the game executables/libraries.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-23T03:37:49+00:00
- Post Title: Animation Recipe Cracker

> Reply from Bigchillghost ↑Fri Sep 22, 2023 1:43 am at Fri Sep 22, 2023 1:43 am
>
> 
So it's likely that the initial frame need to be multiplied by the following keys. Not sure whether each following frame stores relatively to its previous one, just wild guesses.
Got it. It's the world space bind pose that was multiplied by each anim keys:
skeleton layout:

```
long	boneIndex
long	skip[2]
float	TransformMatrix[16] // world inversed bind pose
float	TransformMatrix[16] // world bind pose
float	TransformMatrix[16] // identity
float	TransformMatrix[16] // local bind pose
float	TransformMatrix[16] // world static pose

```




anims.gif (80.46 KiB) Viewed 305 times



Might add support for such format in future version.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-23T14:28:21+00:00
- Post Title: Animation Recipe Cracker

Updated v1.0.2:
- Added individual Radian switch checkbox for Euler and Axis Angle;
- Bug fix for matrix convertion.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T01:26:36+00:00
- Post Title: Animation Recipe Cracker

Hello BigchillGhost,
another amazing tool made by you, congratz.
It's a little bit over my head but I'd like to support the idea (if you'd believe that?  ).

So, this is NOT a request and NOT a test of your profound skills but if you find the time you might have a look at

> Reply from shakotay2 ↑Wed Feb 08, 2023 1:26 am at Wed Feb 08, 2023 1:26 am
>
> 
("unfinished animation processing")
and

> Reply from shakotay2 ↑Wed Feb 08, 2023 2:26 am at Wed Feb 08, 2023 2:26 am
>
> 

Samples:

> Reply from Genshinrange ↑Tue Feb 07, 2023 10:09 pm at Tue Feb 07, 2023 10:09 pm
>
> 
.
The more complex OrcWarrior has the advantage of bone names (instead of numbers only):

> Reply from shakotay2 ↑Sun Aug 14, 2022 6:46 pm at Sun Aug 14, 2022 6:46 pm
>
> 
.
Juggernaut, skeleton (child of '2' is '11', btw)



Juggernaut_skel_hierarchy.jpg (117.63 KiB) Viewed 209 times
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-06T14:07:58+00:00
- Post Title: Animation Recipe Cracker

> Reply from shakotay2 ↑Fri Oct 06, 2023 9:26 am at Fri Oct 06, 2023 9:26 am
>
> 
this is NOT a request ... but if you find the time you might have a look at...
("unfinished animation processing")
Sounds no difference to me. Still I'm the one that needs to do the labors...  

I see that you're doing a byte searching to get the addresses of the anim groups and key counts etc., but in fact the data was stored in a deeply nested layout and it shouldn't be a problem to tell which curve belongs to which bone if you group them one level at a time. The problem is, how do you distinguish between a translation and a rotation curve:

```
        bone 0
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 0
                slot 4, slot id 9, keyCnt 0
                slot 5, slot id 10, keyCnt 0
                slot 6, slot id 11, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 1
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 0
                slot 4, slot id 9, keyCnt 0
                slot 5, slot id 10, keyCnt 0
                slot 6, slot id 11, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 2
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 58, max key time 69
                slot 4, slot id 9, keyCnt 61, max key time 69
                slot 5, slot id 10, keyCnt 41, max key time 69
                slot 6, slot id 11, keyCnt 30, max key time 69
                        key 8, good sqrsum -> 0.985794
                        key 9, good sqrsum -> 0.995618
                        key 10, good sqrsum -> 0.999051
                        key 17, good sqrsum -> 0.993575
                        key 18, good sqrsum -> 0.998947
                        key 20, good sqrsum -> 0.985768
                        key 28, good sqrsum -> 0.991062
                        key 29, good sqrsum -> 0.997652
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 3
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 44, max key time 69
                slot 4, slot id 9, keyCnt 30, max key time 69
                slot 5, slot id 10, keyCnt 37, max key time 69
                slot 6, slot id 11, keyCnt 33, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 4
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 1, max key time 0
                slot 4, slot id 9, keyCnt 1, max key time 0
                slot 5, slot id 10, keyCnt 0
                slot 6, slot id 11, keyCnt 0
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 5
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 51, max key time 69
                slot 4, slot id 9, keyCnt 40, max key time 69
                slot 5, slot id 10, keyCnt 53, max key time 69
                slot 6, slot id 11, keyCnt 26, max key time 69
                        key 0, good sqrsum -> 0.984535
                        key 1, good sqrsum -> 0.99339
                        key 2, good sqrsum -> 0.996724
                        key 3, good sqrsum -> 0.994339
                        key 4, good sqrsum -> 0.98499
                        key 18, good sqrsum -> 0.986872
                        key 24, good sqrsum -> 0.996097
                        key 25, good sqrsum -> 0.999036
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 6
                slot 0, slot id 5, keyCnt 10, max key time 69
                slot 1, slot id 6, keyCnt 13, max key time 69
                slot 2, slot id 7, keyCnt 6, max key time 69
                slot 3, slot id 8, keyCnt 39, max key time 69
                slot 4, slot id 9, keyCnt 22, max key time 69
                slot 5, slot id 10, keyCnt 47, max key time 69
                slot 6, slot id 11, keyCnt 10, max key time 69
                        key 3, good sqrsum -> 0.99285
                        key 4, good sqrsum -> 0.996336
                        key 5, good sqrsum -> 0.995396
                        key 6, good sqrsum -> 0.993794
                        key 7, good sqrsum -> 0.990877
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 7
                slot 0, slot id 5, keyCnt 41, max key time 69
                slot 1, slot id 6, keyCnt 53, max key time 69
                        key 11, good sqrsum -> 1.00114
                        key 14, bad sqrsum 1.1054
                        key 15, bad sqrsum 1.11995
                        key 16, bad sqrsum 1.12742
                        key 17, bad sqrsum 1.12794
                        key 18, bad sqrsum 1.12154
                        key 19, bad sqrsum 1.10812
                        key 22, good sqrsum -> 1.02191
                slot 2, slot id 7, keyCnt 48, max key time 69
                        key 8, bad sqrsum 1.12299
                        key 9, comp 1 value outside range of [-1, +1]
                        key 9, bad sqrsum 1.25463
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.37554
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.47874
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.5586
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.60984
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.62778
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.61773
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.58906
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.54389
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.48451
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.41325
                        key 20, comp 1 value outside range of [-1, +1]
                        key 20, bad sqrsum 1.33248
                        key 21, comp 1 value outside range of [-1, +1]
                        key 21, bad sqrsum 1.24451
                        key 22, bad sqrsum 1.15166
                slot 3, slot id 8, keyCnt 43, max key time 69
                slot 4, slot id 9, keyCnt 34, max key time 69
                slot 5, slot id 10, keyCnt 35, max key time 69
                slot 6, slot id 11, keyCnt 41, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 8
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 0
                slot 4, slot id 9, keyCnt 0
                slot 5, slot id 10, keyCnt 0
                slot 6, slot id 11, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 9
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 0
                slot 4, slot id 9, keyCnt 0
                slot 5, slot id 10, keyCnt 0
                slot 6, slot id 11, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 10
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 46, max key time 69
                slot 4, slot id 9, keyCnt 39, max key time 69
                slot 5, slot id 10, keyCnt 35, max key time 69
                slot 6, slot id 11, keyCnt 34, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 11
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 28, max key time 69
                slot 4, slot id 9, keyCnt 51, max key time 69
                slot 5, slot id 10, keyCnt 44, max key time 69
                slot 6, slot id 11, keyCnt 57, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 12
                slot 0, slot id 5, keyCnt 9, max key time 69
                slot 1, slot id 6, keyCnt 15, max key time 69
                slot 2, slot id 7, keyCnt 16, max key time 69
                slot 3, slot id 8, keyCnt 34, max key time 69
                        key 10, good sqrsum -> 0.982286
                        key 11, good sqrsum -> 0.996804
                        key 12, good sqrsum -> 0.996403
                        key 14, good sqrsum -> 0.98147
                slot 4, slot id 9, keyCnt 53, max key time 69
                slot 5, slot id 10, keyCnt 45, max key time 69
                slot 6, slot id 11, keyCnt 49, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 13
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 64, max key time 69
                slot 4, slot id 9, keyCnt 53, max key time 69
                slot 5, slot id 10, keyCnt 55, max key time 69
                slot 6, slot id 11, keyCnt 45, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 14
                slot 0, slot id 5, keyCnt 40, max key time 69
                slot 1, slot id 6, keyCnt 54, max key time 69
                        key 11, good sqrsum -> 1.00131
                        key 14, bad sqrsum 1.13444
                        key 15, bad sqrsum 1.15901
                        key 16, bad sqrsum 1.1734
                        key 17, bad sqrsum 1.18079
                        key 18, bad sqrsum 1.1813
                        key 19, bad sqrsum 1.17498
                        key 20, bad sqrsum 1.16169
                        key 21, bad sqrsum 1.14111
                        key 22, bad sqrsum 1.1127
                        key 31, good sqrsum -> 0.990181
                        key 32, good sqrsum -> 0.999705
                        key 33, good sqrsum -> 0.986369
                slot 2, slot id 7, keyCnt 50, max key time 69
                        key 8, good sqrsum -> 1.00853
                        key 9, bad sqrsum 1.14176
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.25958
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.369
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.4615
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.53341
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.5802
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.59692
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.58761
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.56042
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.51733
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.4607
                        key 20, comp 1 value outside range of [-1, +1]
                        key 20, bad sqrsum 1.39281
                        key 21, comp 1 value outside range of [-1, +1]
                        key 21, bad sqrsum 1.31573
                        key 22, comp 1 value outside range of [-1, +1]
                        key 22, bad sqrsum 1.23139
                        key 23, bad sqrsum 1.14172
                slot 3, slot id 8, keyCnt 48, max key time 69
                slot 4, slot id 9, keyCnt 38, max key time 69
                slot 5, slot id 10, keyCnt 33, max key time 69
                slot 6, slot id 11, keyCnt 43, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 15
                slot 0, slot id 5, keyCnt 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 0
                slot 4, slot id 9, keyCnt 0
                slot 5, slot id 10, keyCnt 0
                slot 6, slot id 11, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 16
                slot 0, slot id 5, keyCnt 39, max key time 69
                slot 1, slot id 6, keyCnt 54, max key time 69
                        key 10, bad sqrsum 1.11447
                        key 11, bad sqrsum 1.18418
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.24345
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.29193
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.32976
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.3556
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.37094
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.37907
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.38009
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.37408
                        key 20, comp 1 value outside range of [-1, +1]
                        key 20, bad sqrsum 1.36078
                        key 21, comp 1 value outside range of [-1, +1]
                        key 21, bad sqrsum 1.33962
                        key 22, comp 1 value outside range of [-1, +1]
                        key 22, bad sqrsum 1.30978
                        key 23, comp 1 value outside range of [-1, +1]
                        key 23, bad sqrsum 1.26957
                        key 24, bad sqrsum 1.12728
                        key 30, bad sqrsum 1.1521
                        key 31, bad sqrsum 1.17746
                        key 32, bad sqrsum 1.18744
                        key 33, bad sqrsum 1.17189
                        key 34, bad sqrsum 1.13428
                        key 36, good sqrsum -> 1.01934
                        key 37, good sqrsum -> 1.01515
                        key 38, good sqrsum -> 1.02354
                        key 42, good sqrsum -> 1.02933
                        key 43, good sqrsum -> 0.993634
                slot 2, slot id 7, keyCnt 50, max key time 69
                        key 8, good sqrsum -> 1.01179
                        key 9, bad sqrsum 1.15057
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.23341
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.31464
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.39295
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.45619
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.50506
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.53675
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.54598
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.53383
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.50554
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.46293
                        key 20, comp 1 value outside range of [-1, +1]
                        key 20, bad sqrsum 1.40867
                        key 21, comp 1 value outside range of [-1, +1]
                        key 21, bad sqrsum 1.34494
                        key 22, comp 1 value outside range of [-1, +1]
                        key 22, bad sqrsum 1.27332
                        key 23, bad sqrsum 1.19501
                        key 24, bad sqrsum 1.11124
                        key 25, good sqrsum -> 1.02127
                slot 3, slot id 8, keyCnt 51, max key time 69
                slot 4, slot id 9, keyCnt 37, max key time 69
                slot 5, slot id 10, keyCnt 39, max key time 69
                slot 6, slot id 11, keyCnt 43, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 17
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 40, max key time 69
                slot 4, slot id 9, keyCnt 38, max key time 69
                slot 5, slot id 10, keyCnt 43, max key time 69
                slot 6, slot id 11, keyCnt 43, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 18
                slot 0, slot id 5, keyCnt 44, max key time 69
                slot 1, slot id 6, keyCnt 54, max key time 69
                        key 9, comp 1 value outside range of [-1, +1]
                        key 9, bad sqrsum 1.32078
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.45842
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.56915
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.65589
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.7178
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.76076
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.78864
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.80567
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.8156
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.81843
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.81425
                        key 20, comp 1 value outside range of [-1, +1]
                        key 20, bad sqrsum 1.80236
                        key 21, comp 1 value outside range of [-1, +1]
                        key 21, bad sqrsum 1.78137
                        key 22, comp 1 value outside range of [-1, +1]
                        key 22, bad sqrsum 1.7497
                        key 23, comp 1 value outside range of [-1, +1]
                        key 23, bad sqrsum 1.70502
                        key 24, comp 1 value outside range of [-1, +1]
                        key 24, bad sqrsum 1.54034
                        key 25, comp 1 value outside range of [-1, +1]
                        key 25, bad sqrsum 1.49509
                        key 26, comp 1 value outside range of [-1, +1]
                        key 26, bad sqrsum 1.46326
                        key 27, comp 1 value outside range of [-1, +1]
                        key 27, bad sqrsum 1.45051
                        key 28, comp 1 value outside range of [-1, +1]
                        key 28, bad sqrsum 1.46102
                        key 29, comp 1 value outside range of [-1, +1]
                        key 29, bad sqrsum 1.48893
                        key 30, comp 1 value outside range of [-1, +1]
                        key 30, bad sqrsum 1.56144
                        key 31, comp 1 value outside range of [-1, +1]
                        key 31, bad sqrsum 1.58719
                        key 32, comp 1 value outside range of [-1, +1]
                        key 32, bad sqrsum 1.59326
                        key 33, comp 1 value outside range of [-1, +1]
                        key 33, bad sqrsum 1.56798
                        key 34, comp 1 value outside range of [-1, +1]
                        key 34, bad sqrsum 1.51471
                        key 35, comp 1 value outside range of [-1, +1]
                        key 35, bad sqrsum 1.39038
                        key 36, comp 1 value outside range of [-1, +1]
                        key 36, bad sqrsum 1.35393
                        key 37, comp 1 value outside range of [-1, +1]
                        key 37, bad sqrsum 1.34594
                        key 38, comp 1 value outside range of [-1, +1]
                        key 38, bad sqrsum 1.35406
                        key 39, comp 1 value outside range of [-1, +1]
                        key 39, bad sqrsum 1.38586
                        key 40, comp 1 value outside range of [-1, +1]
                        key 40, bad sqrsum 1.3947
                        key 41, comp 1 value outside range of [-1, +1]
                        key 41, bad sqrsum 1.38904
                        key 42, comp 1 value outside range of [-1, +1]
                        key 42, bad sqrsum 1.36307
                        key 43, comp 1 value outside range of [-1, +1]
                        key 43, bad sqrsum 1.32101
                        key 44, bad sqrsum 1.16955
                        key 45, bad sqrsum 1.13143
                        key 46, bad sqrsum 1.10869
                        key 47, bad sqrsum 1.10446
                        key 48, bad sqrsum 1.11523
                        key 49, bad sqrsum 1.13656
                        key 50, bad sqrsum 1.18891
                        key 51, bad sqrsum 1.20898
                        key 52, comp 1 value outside range of [-1, +1]
                        key 52, bad sqrsum 1.21803
                        key 53, bad sqrsum 1.20232
                slot 2, slot id 7, keyCnt 48, max key time 69
                        key 6, bad sqrsum 1.1663
                        key 7, comp 1 value outside range of [-1, +1]
                        key 7, bad sqrsum 1.3877
                        key 8, comp 1 value outside range of [-1, +1]
                        key 8, bad sqrsum 1.4921
                        key 9, comp 1 value outside range of [-1, +1]
                        key 9, bad sqrsum 1.48505
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.49235
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.50495
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.49093
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.4701
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.44969
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.41744
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.37478
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.32502
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.27018
                        key 19, bad sqrsum 1.21087
                        key 20, bad sqrsum 1.14667
                        key 22, good sqrsum -> 1.00033
                slot 3, slot id 8, keyCnt 57, max key time 69
                slot 4, slot id 9, keyCnt 51, max key time 69
                slot 5, slot id 10, keyCnt 51, max key time 69
                slot 6, slot id 11, keyCnt 53, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 19
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 64, max key time 69
                slot 4, slot id 9, keyCnt 56, max key time 69
                slot 5, slot id 10, keyCnt 58, max key time 69
                slot 6, slot id 11, keyCnt 54, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 20
                slot 0, slot id 5, keyCnt 40, max key time 69
                slot 1, slot id 6, keyCnt 54, max key time 69
                        key 0, bad sqrsum 1.11016
                        key 8, good sqrsum -> 0.981692
                        key 9, bad sqrsum 1.17118
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.28057
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.37009
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.44258
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.49803
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.53925
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.56688
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.58347
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.59268
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.59452
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.58906
                        key 20, comp 1 value outside range of [-1, +1]
                        key 20, bad sqrsum 1.57584
                        key 21, comp 1 value outside range of [-1, +1]
                        key 21, bad sqrsum 1.55397
                        key 22, comp 1 value outside range of [-1, +1]
                        key 22, bad sqrsum 1.52239
                        key 23, comp 1 value outside range of [-1, +1]
                        key 23, bad sqrsum 1.47918
                        key 24, comp 1 value outside range of [-1, +1]
                        key 24, bad sqrsum 1.32451
                        key 25, comp 1 value outside range of [-1, +1]
                        key 25, bad sqrsum 1.28302
                        key 26, comp 1 value outside range of [-1, +1]
                        key 26, bad sqrsum 1.25431
                        key 27, comp 1 value outside range of [-1, +1]
                        key 27, bad sqrsum 1.24315
                        key 28, comp 1 value outside range of [-1, +1]
                        key 28, bad sqrsum 1.25345
                        key 29, comp 1 value outside range of [-1, +1]
                        key 29, bad sqrsum 1.28009
                        key 30, comp 1 value outside range of [-1, +1]
                        key 30, bad sqrsum 1.34968
                        key 31, comp 1 value outside range of [-1, +1]
                        key 31, bad sqrsum 1.37569
                        key 32, comp 1 value outside range of [-1, +1]
                        key 32, bad sqrsum 1.38413
                        key 33, comp 1 value outside range of [-1, +1]
                        key 33, bad sqrsum 1.36399
                        key 34, comp 1 value outside range of [-1, +1]
                        key 34, bad sqrsum 1.3187
                        key 35, comp 1 value outside range of [-1, +1]
                        key 35, bad sqrsum 1.21181
                        key 36, bad sqrsum 1.18081
                        key 37, bad sqrsum 1.17495
                        key 38, bad sqrsum 1.18369
                        key 39, comp 1 value outside range of [-1, +1]
                        key 39, bad sqrsum 1.21426
                        key 40, comp 1 value outside range of [-1, +1]
                        key 40, bad sqrsum 1.22276
                        key 41, comp 1 value outside range of [-1, +1]
                        key 41, bad sqrsum 1.21773
                        key 42, bad sqrsum 1.19418
                        key 43, bad sqrsum 1.15631
                        key 44, good sqrsum -> 1.02134
                        key 45, good sqrsum -> 0.988573
                        key 49, good sqrsum -> 1.02412
                slot 2, slot id 7, keyCnt 48, max key time 69
                        key 6, good sqrsum -> 0.98317
                        key 7, bad sqrsum 1.1942
                        key 8, comp 1 value outside range of [-1, +1]
                        key 8, bad sqrsum 1.31999
                        key 9, comp 1 value outside range of [-1, +1]
                        key 9, bad sqrsum 1.45111
                        key 10, comp 1 value outside range of [-1, +1]
                        key 10, bad sqrsum 1.48202
                        key 11, comp 1 value outside range of [-1, +1]
                        key 11, bad sqrsum 1.50404
                        key 12, comp 1 value outside range of [-1, +1]
                        key 12, bad sqrsum 1.51751
                        key 13, comp 1 value outside range of [-1, +1]
                        key 13, bad sqrsum 1.51771
                        key 14, comp 1 value outside range of [-1, +1]
                        key 14, bad sqrsum 1.50238
                        key 15, comp 1 value outside range of [-1, +1]
                        key 15, bad sqrsum 1.47279
                        key 16, comp 1 value outside range of [-1, +1]
                        key 16, bad sqrsum 1.43058
                        key 17, comp 1 value outside range of [-1, +1]
                        key 17, bad sqrsum 1.37878
                        key 18, comp 1 value outside range of [-1, +1]
                        key 18, bad sqrsum 1.31947
                        key 19, comp 1 value outside range of [-1, +1]
                        key 19, bad sqrsum 1.25371
                        key 20, bad sqrsum 1.18183
                        key 21, bad sqrsum 1.10423
                        key 22, good sqrsum -> 1.01905
                slot 3, slot id 8, keyCnt 45, max key time 69
                slot 4, slot id 9, keyCnt 40, max key time 69
                slot 5, slot id 10, keyCnt 37, max key time 69
                slot 6, slot id 11, keyCnt 44, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 21
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 31, max key time 69
                slot 4, slot id 9, keyCnt 60, max key time 69
                slot 5, slot id 10, keyCnt 49, max key time 69
                slot 6, slot id 11, keyCnt 56, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 22
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 52, max key time 69
                slot 4, slot id 9, keyCnt 56, max key time 69
                slot 5, slot id 10, keyCnt 55, max key time 69
                slot 6, slot id 11, keyCnt 52, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 23
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 7, max key time 69
                slot 4, slot id 9, keyCnt 7, max key time 69
                slot 5, slot id 10, keyCnt 62, max key time 69
                slot 6, slot id 11, keyCnt 58, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 24
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 7, max key time 69
                slot 4, slot id 9, keyCnt 6, max key time 69
                slot 5, slot id 10, keyCnt 64, max key time 69
                slot 6, slot id 11, keyCnt 57, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 25
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 37, max key time 69
                slot 4, slot id 9, keyCnt 39, max key time 69
                slot 5, slot id 10, keyCnt 58, max key time 69
                slot 6, slot id 11, keyCnt 45, max key time 69
                        key 26, good sqrsum -> 0.982767
                        key 27, good sqrsum -> 0.990111
                        key 28, good sqrsum -> 0.990528
                        key 29, good sqrsum -> 0.982939
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 26
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 57, max key time 69
                slot 4, slot id 9, keyCnt 58, max key time 69
                slot 5, slot id 10, keyCnt 60, max key time 69
                slot 6, slot id 11, keyCnt 44, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 27
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 19, max key time 69
                slot 4, slot id 9, keyCnt 60, max key time 69
                slot 5, slot id 10, keyCnt 48, max key time 69
                slot 6, slot id 11, keyCnt 49, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 28
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 6, max key time 69
                slot 4, slot id 9, keyCnt 6, max key time 69
                slot 5, slot id 10, keyCnt 56, max key time 69
                slot 6, slot id 11, keyCnt 56, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 29
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 1, max key time 0
                slot 3, slot id 8, keyCnt 6, max key time 69
                slot 4, slot id 9, keyCnt 5, max key time 69
                slot 5, slot id 10, keyCnt 58, max key time 69
                slot 6, slot id 11, keyCnt 57, max key time 69
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
        bone 30
                slot 0, slot id 5, keyCnt 1, max key time 0
                slot 1, slot id 6, keyCnt 1, max key time 0
                slot 2, slot id 7, keyCnt 0
                slot 3, slot id 8, keyCnt 51, max key time 69
                slot 4, slot id 9, keyCnt 56, max key time 69
                slot 5, slot id 10, keyCnt 56, max key time 69
                slot 6, slot id 11, keyCnt 54, max key time 69
                        key 8, good sqrsum -> 0.980039
                        key 9, good sqrsum -> 0.986642
                        key 39, good sqrsum -> 0.98842
                        key 40, good sqrsum -> 0.990534
                        key 41, good sqrsum -> 0.982666
                slot 7, slot id 12, keyCnt 1, max key time 0
                        key 0, good sqrsum -> 1
```

HexEdit template for Juggernaut.gobj:


 gObj.zip
(999 Bytes) Downloaded 17 times



Up to this point I have no further interest in continuing the research, but let me know if you manage to convert them while it turns out to be an uncommon format.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T16:19:58+00:00
- Post Title: Animation Recipe Cracker

> Reply from Bigchillghost ↑Fri Oct 06, 2023 10:07 pm at Fri Oct 06, 2023 10:07 pm
>
> Sounds no difference to me. Still I'm the one that needs to do the labors...I like your sense of humor.  

> but in fact the data was stored in a deeply nested layoutI see. That's probably the reason why nobody solved it so far. I was in the hope that I might have overlooked something...

btw, "slots" are the same as like Unreal Engine's "Animation slots"?

> HexEdit template for Juggernaut.gobj:Thanks for the effort!
Is animation data stored in the gobj file?
Because from Demonsangel's  script it seems the animations are in separate files:

```
        if DEBUGANIM and not os.path.isdir(dirPath + '/anm/'):
            os.mkdir(dirPath + '/anm/')
```


But at 0x6BF80 (Juggernaut.gobj) it looks like an animation curve:
.



Juggernaut_0x6BF80.png (2.74 KiB) Viewed 185 times



> Up to this point I have no further interest in continuing the research,It's ok. This is a big step forward after 10 years of stagnation with HOMM6 anims.

> but let me know if you manage to convert them while it turns out to be an uncommon format.I fear I'm not qualified enough.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T16:22:14+00:00
- Post Title: Animation Recipe Cracker

If anyone is interested in HOMM6 animations I strongly suggest to have a look at Bigchillghost's template in HexEdit (copy the xml into the exe's folder before starting):
.



HexEdit-template-gobj.png (59.38 KiB) Viewed 176 times
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-06T16:43:50+00:00
- Post Title: Animation Recipe Cracker

> Reply from shakotay2 ↑Sat Oct 07, 2023 12:19 am at Sat Oct 07, 2023 12:19 am
>
> 
btw, "slots" are the same as like Unreal Engine's "Animation slots"?
Nope, I just use that word habitually. My guess is that for each bone in each anim group, they store 8 animation curves of difference actions. Coz the end time of each action match with the track length. Hence the problem: either they're all rotations, or they're all translations. Otherwise I can't think of a way if they need to coexist.

> Reply from shakotay2 ↑Sat Oct 07, 2023 12:19 am at Sat Oct 07, 2023 12:19 am
>
> 
Is animation data stored in the gobj file?
Well, definitely.

> Reply from shakotay2 ↑Sat Oct 07, 2023 12:19 am at Sat Oct 07, 2023 12:19 am
>
> I fear I'm not qualified enough.
Or maybe it just doesn't worth the efforts.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T16:48:19+00:00
- Post Title: Animation Recipe Cracker

> Reply from Bigchillghost ↑Sat Oct 07, 2023 12:43 am at Sat Oct 07, 2023 12:43 am
>
> 
Or maybe it just doesn't worth the efforts.That's possible. I just stumbled accross it when reviewing the forum before it will shut down.

(Ok, I will continue in the HOMM6 thread to not spam here.)

Thanks again for your help Really appreciated!
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-06T17:01:46+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from shakotay2 ↑Sat Oct 07, 2023 12:48 am at Sat Oct 07, 2023 12:48 am
>
> 
I just stumbled accross it when reviewing the forum before it will shut down.
Ha, out of sight and out of mind.  

> Reply from shakotay2 ↑Sat Oct 07, 2023 12:48 am at Sat Oct 07, 2023 12:48 am
>
> 
(Ok, I will continue in the HOMM6 thread to not spam here.)
I appreciate your good intention but what difference will it make? Feel free to do whatever you like here.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T17:30:07+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from Bigchillghost ↑Sat Oct 07, 2023 1:01 am at Sat Oct 07, 2023 1:01 am
>
> 
I appreciate your good intention but what difference will it make?This forum shouldn't shut down as a mess what I'm very likely to create.  

btw, which "level" do you mean?

> Reply from Bigchillghost ↑Fri Oct 06, 2023 10:07 pm at Fri Oct 06, 2023 10:07 pm
>
> and it shouldn't be a problem to tell which curve belongs to which bone if you group them one level at a time.
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-06T17:38:06+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from shakotay2 ↑Sat Oct 07, 2023 1:30 am at Sat Oct 07, 2023 1:30 am
>
> 
btw, which "level" do you mean?
I was talking about reversing the nested structure. One level at a time using the chunk size to break the entire binary blob into senseful structures. The number of items in each anim group matches with the bone count so I assume they match to each bone accordingly. Or were you saying they're otherwise?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T17:46:59+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from Bigchillghost ↑Sat Oct 07, 2023 1:38 am at Sat Oct 07, 2023 1:38 am
>
> 
I was talking about reversing the nested structure. One level at a time using the chunk size to break the entire binary blob into senseful structures. The number of items in each anim group matches with the bone count so I assume they match to each bone accordingly. Or were you saying they're otherwise?Well, I'm not in the position to say otherwise. Still fighting with the names.
We've a set of animations, "Move", Run and so on. Are these "animgroups"?
What is "items"? There's 31 curves. So items==curves?

> Reply from Bigchillghost ↑Sat Oct 07, 2023 1:38 am at Sat Oct 07, 2023 1:38 am
>
> 
using the chunk size to break the entire binary blob into senseful structures.Isn't this what you've done already? Is there a deeper nesting?
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-06T18:15:42+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from shakotay2 ↑Sat Oct 07, 2023 1:46 am at Sat Oct 07, 2023 1:46 am
>
> 
We've a set of animations, "Move", Run and so on. Are these "animgroups"?
Yes, that's correct. Maybe I forgot to change some naming of the elements in that template. But if you've observed the file using the template, you'd see there're 31 elements contained in each so-called animations, and under each of these elements there're 8 actual anim curves. Think of the concept that a "move" anim group consists of 4 specific anims: "move left/front/right/back". You can ignore other terms like 
"items" etc., I was just describing things from a programming aspect.

> Isn't this what you've done already? Is there a deeper nesting?
Yesh I was just saying it'd be clear once you got the nested structure figured out. There's no noticeable deeper nesting except for some bytes before each key count and these fields don't seem to show any hints.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-07T10:05:23+00:00
- Post Title: Re: Animation Recipe Cracker

Me again. Great tool but I can't seem to use it. Had a rough look into the detailed manual but couldn't find a hint.

What I did: File Open stand.ab 
File Import Skeleton stand.end
(copying layout into Animation Layout window)
Compile
Execute
(RT error)  matter of checkBoxes or parameter(s) I have to regard?
Changed "Euler" to "Quaternion" - still RT
.
Ok, had to switch to Big Endian.
On execute nothing happens.

From the manual I see there's an "Animation .. conversion completed."

Ok, "solved"  
Convert
Preview

Done.

Hmm, maybe I'm a little bit dump, but I'd suggest to give the users this "Compile-Execute-Convert-Previev" hint at least?
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-07T10:38:22+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from shakotay2 ↑Sat Oct 07, 2023 6:05 pm at Sat Oct 07, 2023 6:05 pm
>
> 
Hmm, maybe I'm a little bit dump, but I'd suggest to give the users this "Compile-Execute-Convert-Previev" hint at least?
You can just hit preview without performing individual steps as compile, execute, and convert. In fact there's no need to care about which step you should take first if you're confident about that your params are absolutely correct. The tool automatically performs the necessary steps in between. But to avoid unexpected crash it's recommended to perform these steps manually.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-08T12:25:33+00:00
- Post Title: Re: Animation Recipe Cracker

Btw, your layout parser. Did you write it from scratch or did you have some reference? (Such as a library or similar.)

From Lazov's MR I saw he included python to do some scripting:

> Reply from Lazov ↑Wed Apr 19, 2017 2:02 am at Wed Apr 19, 2017 2:02 am
>
> 
(I'm pretty sure that I don't really want to do that but the idea is cool.)
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-08T13:17:09+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from shakotay2 ↑Sun Oct 08, 2023 8:25 pm at Sun Oct 08, 2023 8:25 pm
>
> 
Btw, your layout parser. Did you write it from scratch or did you have some reference? (Such as a library or similar.)
Well, everything is written from scratch. The parser is rather simple given the limited form of the semantic grammar. I just registered some constraint rules for the pre-defined variables. But to support nested layout execution and generic custom variables I had to rewrite the context executor in a datatype-driven manner. It's different than that in ASH BTW.

> Reply from shakotay2 ↑Sun Oct 08, 2023 8:25 pm at Sun Oct 08, 2023 8:25 pm
>
> 
From Lazov's MR I saw he included python to do some scripting
Not that I hadn't thought about it. But the idea was to ease the coding process and let the GUI do the dirty work. It won't make things easier to introduce a seperate scripting engine given the app logics being heavily attached to the structures of the read data. But then again, why not just stick to formal programming or better, use Noesis, if you're going to use Python for the task?
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-08T13:46:50+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from Bigchillghost ↑Sun Oct 08, 2023 9:17 pm at Sun Oct 08, 2023 9:17 pm
>
> ...Thanks!

> It won't make things easier to introduce a seperate scripting engine given the app logics being heavily attached to the structures of the read data.Very good point!

> or better, use Noesis, if you're going to use Python for the task?Well, a great tool, admitted, but.. Python is not my first choice, to be honest.
I tried using the C-interface of Noesis but felt narrowed down somehow.

Need to think about it and what I actually try to achieve...

Big thanks for your valuable contributions over all the years!
Too sad that this forum has/will come to an end.

But it was foreseeable since one (ore two) years..
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-08T16:07:34+00:00
- Post Title: Re: Animation Recipe Cracker

> Reply from shakotay2 ↑Sun Oct 08, 2023 9:46 pm at Sun Oct 08, 2023 9:46 pm
>
> 
Well, a great tool, admitted, but.. Python is not my first choice, to be honest.
I tried using the C-interface of Noesis but felt narrowed down somehow.
Yeah I know you're a fan of C. I used to be one too. But nowadays most of my work are done in C++. Sometimes I switch to Noesis if I need to implement something quick or just for examination. 

> Reply from shakotay2 ↑Sun Oct 08, 2023 9:46 pm at Sun Oct 08, 2023 9:46 pm
>
> 
Big thanks for your valuable contributions over all the years!
The same to you. You're one of those who guided me into this path. Really appreciated all the joys and pleasures we shared along these years!  

> Reply from shakotay2 ↑Sun Oct 08, 2023 9:46 pm at Sun Oct 08, 2023 9:46 pm
>
> 
Too sad that this forum has/will come to an end.
Indeed it's a shame. But the way I see it, it's never the forum that truely mattered, but the people who dedicated to the community, the mutual identification and empathy among the members. Nevertheless, we'll be here, till the last moment of its life circle.
## Post #27
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-10-08T17:12:06+00:00
- Post Title: Re: Animation Recipe Cracker

My Thanks and Respect to both of you.
I have followed your many posts and learned what I needed for my narrow needs.

Not a Game series many follow but I fully understand the Animations.

Thanks again.
## Post #28
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-10-10T16:10:23+00:00
- Post Title: Re: Animation Recipe Cracker

Can you take a look at IFF from Project IGI from 2000?

[https://mega.nz/file/tbQVkKQT#u9QDwt4bf ... b85F5pFtT0](https://mega.nz/file/tbQVkKQT#u9QDwt4bfV-XpkNJMrKCEnzbS_z5jEHncb85F5pFtT0)
