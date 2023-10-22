## Post #1
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-02T03:55:21+00:00
- Post Title: Importing .STCK animation - We need your help!

Hi there!

We are trying to import .STCK animation from the game Saint Seiya online (developed by the same company that made Perfect World, also know as PW)

The story so far:

- Both PW's .STCK and SSeiya's .STCK have the same header "MOXBKCTS"
- I tried to import the animation using shakotay2's .STCK script for PW, but it didn't work
- Dispite having the same header, the structure of the files are different

- Now we are trying to figure out SSeiya's .STCK structure. 
- Can you help ? 

Thanks in advance  
[Sample.rar](https://xentaxbackup.github.io/file/10257_Sample.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-07T17:14:37+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> 
shakotay2's script + few modificationsNot sure which problems you solved but I would kindly beg you to mark the changes you applied to my script.

From what I see you've added
numBones = #()               
nBones = #()               

tmp = #()               
unk = #()      

fd = #() 

but these variables are no arrays. (Not sure if you know what you are doing.)

If you meet a problem like this:
--  Frame:
--   i: 67
--   id: undefined

you may be required to set nBones manually in the script.

My script was designed to work with Max2009 and PerfectWorld files.
Tested with boss (upper body) and bloatfly only.

Also keep in mind that there's no UNICODE support by my script.

(I remember renaming the "unreadable" stck filenames to something like 00001.stck to make them work with the script.)
## Post #3
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-13T02:46:32+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> (Not sure if you know what you are doing.)
I apologize for wrongly correcting your script. 
From what I've read, my Max2011 was not handling well the undeclared numBones and returned 'undefined', I think my newbie change indirectly took care of that.

Above all, you're right. I didn't know what I was doing and I'm still a newbie
The only thing that I know is that I really, really want to see your script working and import those animations  

> Reply from shakotay2
>
> My script was designed to work with Max2009 and PerfectWorld files.
I've just installed 3DSMax 2009 and it seems to work a lot better, although I'm still having troubles
My model is from Saint Seiya Online, created by the same company that made PW. 
Since the .stck starts with the same MOXB I'm hoping your script will work (might be newbie's hope, but all I've got  )

> Reply from shakotay2
>
> Tested with boss (upper body) and bloatfly only.
I have high hopes for your script, but since last time you couldn't test it with simple walk/run animations, this is what I'm aiming for.
That's why I've extracted a humanoid model with running animation.

> Reply from shakotay2
>
> 
If you meet a problem like this:
--  Frame:
--   i: 67
--   id: undefined

you may be required to set nBones manually in the script.

Yup, met that and few other problems. Setting it manually to 56 didn't help, I'm still puzzled as to why is that happening 

It would mean a lot if you could take a look at my sample.  

Thanks in advance!
[Sample.rar](https://xentaxbackup.github.io/file/10300_Sample.rar)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-13T10:34:21+00:00
- Post Title: Importing .STCK animation - We need your help!

The animation file is useless for me without suiting .ski and .bon file.
## Post #5
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-13T11:05:48+00:00
- Post Title: Importing .STCK animation - We need your help!

Here you go!

Unfortunately Zaramot's importer doesn't work with Saint Seiya models, so I'm using killercracker's altered version of Zaramot's (also included on the sample)

Thanks in advance!
[Ski + Bon + Stck + Importer.rar](https://xentaxbackup.github.io/file/10303_Ski + Bon + Stck + Importer.rar)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-13T15:15:03+00:00
- Post Title: Importing .STCK animation - We need your help!

I imported ski and bon file using killercracker's script
then I started my script for Perfect World .stck import.

It throws "load ski and bon file before! "! (Although they are visibly loaded.)

This means killercracker's Saint Seiya script is not compatible with mine.

As simple as that.

No surprise, since it's different games. The scripts for (ski+bone) import are different.
Then how should the animation import work with the Perfect World script?
(Although the signature MOXBKCTS is identical, admitted.)

(Also my script was tested with one geometry only. But there's 5 geometries for Ikki.)
## Post #7
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-13T21:48:14+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> It throws "load ski and bon file before! "! (Although they are visibly loaded.)

Want to see something completely weird? Just add my array declaration and it'll work and load!

I have no idea why   

> Reply from Code
>
> ...
struct ScaleAnimation (BoneId, KeyFrame, Scaling )

allBones = #()
bone_names = #()
numbones = #() <------ add this line

fn GetBoneNames = (   -- from steev, 10-28-2008
...

If it also works for you, you should get to the point where I was originally asking for help: a unable to convert error

Thank you for all your efforts so far! Hope you can solve this puzzle
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-14T01:35:10+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> shakotay2 wrote:It throws "load ski and bon file before! "! (Although they are visibly loaded.)

Want to see something completely weird? Just add my array declaration and it'll work and load!nope, I fear you didn't get it. There's no difference except that the error message is not thrown. (The mesh and skeleton are loaded without adding your numBones array. numBones is no array, as I said.)

ClearListener()
nBones = GetBoneNames()
nBones = 56 -- add this line and the error message will not be thrown, too

edit: well, thx, anyway. The real problem was that I forgot to give the function ReadAniFile the parameter nBones!

Look at the Saint Seiya .stck files  to see the difference to PerfectWorld .stck files.
Look for the frame count, for example. For the Running.stck it is (wrongly read as) 1, iirc. Doesn't make much sense. <- nope, it's 1 and it's correct. (3dsMax does magic things...)

Maybe it's a small difference only. We'll see...
## Post #9
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-14T10:32:05+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> Maybe it's a small difference only. We'll see...

Okay, couldn't find a 1 mesh model, but I've extracted a simpler model with 2 meshes. Hope it helps.

If you need any other samples, just let me know  
[Jaco - 2 meshes.rar](https://xentaxbackup.github.io/file/10304_Jaco - 2 meshes.rar)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-14T19:22:23+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> shakotay2 wrote:Maybe it's a small difference only. We'll see...

Okay, couldn't find a 1 mesh model, but I've extracted a simpler model with 2 meshes. Hope it helps.

If you need any other samples, just let me knowI'll give you some overview, maybe you can search for a simple animation for yourself then.
The following picture show a Perfect world anim; the arrow marks the position, the "underscore" marks the rotation.
The pattern 01 000000 01 000000 helps to understand the structure. (Surprisingly we seem to have a Frame_cnt of 1 here.  )

For the Saint Seiya .stck the 13 00000 might be the frame count (transition/rotation). The patterns 01 000000 1E 000000
and 01 000000 1E 000000 01 000000 mark transition/rotation (wild guess).



stck_anim_.jpg (249.12 KiB) Viewed 422 times


(As you can see from the Running.stck file there's a section from 0x1DC6 to 0x222B which appears to be similar to the Perfect World 000.stck from the picture.)

Sadly there is varying frame counts in Running.stck which would require frame interpolation -> no time for such, sry.

If you can find a simple Saint Seiya .stck with constant fram counts, I'd take a look at.

btw: didn't forget the picture - while I was desperately trying to reduce it's size to 250 kB you posted.
## Post #11
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-14T19:32:52+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> Sadly there is varying frame counts in Running.stck which would require frame interpolation -> no time for such, sry.

If you can find a simple Saint Seiya .stck with constant fram counts, I'd take a look at.

Okay, i've been looking at hex for the past 3 hours, trying to undestand it's concepts by your explanation.  

So far, all the .stck tested have similar structures

Got a few questions, if you don't mind:

- Why do you say that frame counts are varying? By the exemple, shouldn't it be a fix number (0x13) ?
- Is there a "test" to find out if 01 000000 1E 000000 01 000000 mark transition/rotation ?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-15T08:22:08+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> - Why do you say that frame counts are varying? By the exemple, shouldn't it be a fix number (0x13) ?There's different sizes of data blocks in Running.stck:



varying_counts.jpg (197.7 KiB) Viewed 402 times



> - Is there a "test" to find out if 01 000000 1E 000000 01 000000 mark transition/rotation ?Don't know what you mean exactly. (What I meant was that the patterns can be used as markers, obviously.)
You could plot the vectors in 3D space. Transitions should be recognizable this way, if you mean this.

You could build the sum of squares of vector components. Someone said sum (or square root of sum) should be 1.0 for rotation quaternions but I'm not sure if this is always true.
## Post #13
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-15T16:37:39+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> There's different sizes of data blocks in Running.stck

Okay, I stumbled across something interesting. 
I've found a post on a chinese website by Fatduck 

> Reply from Fatduck on a chinese website
>
> 先前給這格式難倒了(其實是自己不小心把兩組變數記錄錯了)
動作檔是沒有 keyTime 的, 也就是把一定時間內的動作以平均方式分佈記錄!

Google translation:
Previously stumped for this format (in fact, they do not accidentally record the wrong two variables)
Movement file is not keyTime, that is the movement within a certain time record average in a distributed manner!

And than he puts this structure:

```
=========[/b]
[b]char[8]       "MOXBKCTS"
dword         nAnim              //Animation Count ??
dword         nBones
dword         ??
dword         ??
dword         FramePerSecond
struct BoneAnim {
   dword            nID
   struct TransAnim {
      dword         nPosKey
      dword         ??               //always 1
      dword         ??               //always 255
      struct TransData {
         float X3    posXYZ
      }
      dword         nTimeStart
      dword         nTimeEnd
      dword         nFrameStart
      dword         nFrameEnd
   }
   struct RotAnim {
      dword         nRotKey
      dword         ??               //always 1
      dword         ??               //always 255
      struct RotData {
         float X4    quatXYZW
      }
      dword         nTimeStart
      dword         nTimeEnd
      dword         nFrameStart
      dword         nFrameEnd
   }
}[/b]
```


Could this mean that 0x130000 is not a frame count, but actually a time? Does this help? Hope it does    

Fingers crossed! Thanks!
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-16T12:39:06+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> Okay, I stumbled across something interesting. 
I've found a post on a chinese website by Fatduckthat is for Perfect World, isn't it?

> Could this mean that 0x130000 is not a frame count, but actually a time?doesn't really matter for me - I'm thinking more in "patterns" than in variable names. What I need is constant times or constant frame counts that would keep things simple.

I'm pretty sure that the 13 00 00 00 (=19 dec.) is a frame count. It counts position/rotation vectors.
The 1E 00 00 00 (30 dec.) in the pic of my previous post might be a frame time.

We've a bonecount of 56 in Running.stck, 56 datablocks for transistions, 56 for rotations.
But we've varying frame counts, as I wrote.

Is there any stck file with constant frame counts?

(Well, think it's a good idea to create a program that can check whether they are constant.)
-> PMed you.
## Post #15
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-16T13:57:49+00:00
- Post Title: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> asdasd123 wrote:that is for Perfect World, isn't it?

Probably, although there was no reference as to which game it was from

------------------------------------------------------

Found something really interesting while testing files with your program:

Every model has it's own main folder containing: 
- folder with .stck animations
- folder with textures
- .bon file
- .ecm file
- .ski file
- .smd file
- and a single .STCK file

All those single .STCK have a constant frame of 1, maybe it's some kind of reference all the other animations

This time I'm uploading an entire model's folder (765 kb).
The file Natasha.stck is the single .STCK for this model.

Thanks for all you've done so far  
[Natasha.rar](https://xentaxbackup.github.io/file/10319_Natasha.rar)
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-16T15:18:36+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

well, thank you, too. Seems it's similar with Perfect World's .stck files.
I did care for the "simple" ones only.

Maybe you can find a Saint Seiya .stck where at least the frame counts for all odd blocknumbers
(or all even numbers) are constant (and != 1)?
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2016-01-16T15:22:39+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

here a small tip of stck structure.

文件头:MOXBKCTS
版本:2
骨骼数41
未知：【0】【150】【30】
===========<1oh,c>=============
骨骼索引: 0
关键帧数: 1
未知:	1 30
A-0  <0.000000 0.000000 0.000000>
未知:5000 1 65536
-------<4oh,4>-------
未知索引: 65536
未知索引数: 1966080
未知:	65536 65536
U-0: <0.000000 -1.#QNAN0 0.000000 0.000000>
U-1: <0.000000 0.000000 0.000000 0.000000>
U-2: <0.000000 1.124843 0.957760 -0.000000>
U-3: <1.124745 0.957871 -0.000000 1.124457>
U-4: <0.958196 -0.000000 1.123989 0.958723>
U-5: <-0.000000 1.123354 0.959440 -0.000000>
U-6: <1.122561 0.960335 -0.000000 1.121622>
U-7: <0.961394 -0.000000 1.120547 0.962607>
U-8: <-0.000000 1.119347 0.963960 -0.000000>
U-9: <1.118034 0.965442 -0.000000 1.116617>
U-10: <0.967040 -0.000000 1.115108 0.968742>
U-11: <-0.000000 1.113518 0.970536 -0.000000>
U-12: <1.111857 0.972409 -0.000000 1.110137>
U-13: <0.974350 -0.000000 1.108368 0.976346>
U-14: <-0.000000 1.106560 0.978385 -0.000000>
U-15: <1.104737 0.980442 -0.000000 1.102875>
U-16: <0.982543 -0.000000 1.101030 0.984624>
U-17: <-0.000000 1.099168 0.986725 -0.000000>
U-18: <1.097344 0.988782 -0.000000 1.095525>
U-19: <0.990834 -0.000000 1.093766 0.992819>
U-20: <-0.000000 1.092034 0.994772 -0.000000>
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-16T16:17:52+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

where is the news compared to this thread? [viewtopic.php?f=16&t=11776&hilit=perfect+world+.stck](http://forum.xentax.com/viewtopic.php?f=16&t=11776&hilit=perfect+world+.stck)

btw: one difference between the "none constant" .stck of Perfect World and Saint Seiya are these indices:



Running_stck_indices.jpg (228.23 KiB) Viewed 245 times


In run.stck from Natasha I've found a sequence which fulfills the needs I asked for above:
95. 1
96. 23
97. 1
98. 23
99. 1
100. 23
101. 1
102. 23
103. 1
104. 23
105. 1
106. 23
107. 1
108. 23
109. 1
110. 23
111. 1
112. 23
113. 1
114. 23
115. 1
116. 23
117. 1
118. 23
119. 1
120. 23
121. 1
122. 23
123. 1
124. 23
125. 1
126. 23

But it's a little bit too short.
## Post #19
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-17T00:56:21+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> But it's a little bit too short.

I haven't found anything too big yet, but take a look at those animations from Mouses, specially his Repulse.stck.

17 seems to repeat twice, don't know how much that meatters:

18. 17
19. 1
20. 17
21. 1
22. 17
23. 1
24. 17
25. 1
26. 17
27. 1
28. 17
29. 1
30. 17
31. 1
32. 17
33. 1
34. 17
35. 1
36. 17
37. 1
38. 17
39. 1
40. 17
41. 1
42. 17
43. 1
44. 1
45. 17
46. 17
47. 1
48. 17
49. 1
50. 17
51. 1
52. 17
53. 1
54. 17
55. 1
56. 17
57. 1
58. 17
59. 1
60. 17
61. 1
62. 17
63. 1
64. 17
65. 1
66. 17
67. 1
68. 17
69. 1
70. 17
71. 1
72. 1
73. 17
74. 17
75. 1
76. 17
77. 1
78. 17
79. 1

[http://www.mediafire.com/download/6ydqt ... Mouses.rar](http://www.mediafire.com/download/6ydqtf07yg1a7am/Mouses.rar)   --- 337 kb
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-17T08:36:47+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> 17 seems to repeat twice, don't know how much that meatters:great! Doesn't matter, I guess. That's a very good starting point, imho. Will try to adjust the script - but don't expect too much. And don't expect it too soon. 

edit: well, forget everything what I said about frame interpolating and none constant frame counts.
True is: - the script simply reads the frames depending on the frame count, no matter whether counts vary
- 3dsmax seems to create (interpolate/copy?) missing frames automatically

Only problem is that we seem to have constant transitions because frames are just copied:



mouseMove.JPG (62.95 KiB) Viewed 228 times



here's the script which was tested with Repulse.stck for mouse only!

```
	Import Saint Seiya .stck Animation
	basic structure borrowed from Taylor Mouse
	1-17-2016; only tested with Repulse.stck from mouse

	(Exit_cnt: quickhack because the former script could handle one geometry only)
   
	(renaming of folders might be required if there are problems with asian characters)
*/

/************************************************************************************************
 STRUCTS 
************************************************************************************************/
struct D3Bone ( ID, Name, TheBone )
struct TranslationAnimation ( BoneId, KeyFrame, Position )
struct RotationAnimation (BoneId, KeyFrame, Quaternion  )
struct ScaleAnimation (BoneId, KeyFrame, Scaling )

allBones = #()
bone_names = #()
Exit_cnt = 0

fn GetBoneNames = (	-- from steev, 10-28-2008
    max modify mode --important! the below won't work unless you're in the modify tab
	print geometry
    for n in geometry do
    (
        select n -- this selects the current object in the array
        if n.modifiers != undefined do
        (
            if n.modifiers[#Skin] != undefined do
            (
                sk = n.modifiers[#Skin]
                modPanel.setCurrentObject sk -- this selects the skin modifier
                numBones = skinops.getnumberbones sk
                if (numBones>0) then ( print ("bones found:")
                    Exit_cnt += 1
                    if Exit_cnt==2 then return numBones
                )

                for i = 1 to numBones do
                (
                    bnName = skinops.getbonename sk i 1
                    append bone_names bnName
                    format "% %'\n" i bnName					
                )
                for i = 1 to numBones do
                (
			b = D3Bone()
			b.ID = i				--> for reference only
			b.Name = bone_names[i]			-- name of the bone
			--format "%: %\n" i b.Name
			b.TheBone = GetNodeByName b.Name	-- find the bone in the scene
			append allBones b					
		)
		-- print allBones
            )
        )
    )
	return numBones  -- returns 'undefined' if no skeleton loaded!
)


/************************************************************************************************
	MAIN function
************************************************************************************************/
function ReadAniFile fName nBones startFrame =
(
    startingFrame = 0
    startingFrame = startFrame 
		
    format "-- Start reading PerfectWorld ANIMATION file --"

    stream = fOpen fname "rb"	-- Open the file for reading

    MOXB = readlong stream
    if (MOXB != 0x42584F4D) then
	    throw "This doesn't seem to be a PerfectWorld file!"
    KCTS = readlong stream
    if (KCTS != 0x5354434B) then
	    throw "This doesn't seem to be a PerfectWorld anim file!"
    anim_cnt =  readlong stream
    nAllBones =  readlong stream		-- notinuse: number of all bones
	--nBones = 60	-- Natasha
    
    /* Frame data*/
    Frame_cnt = #()
    Frame_offs = #()
    allTranslations = #()
    allRotations = #()

    for i=1 to nBones do	/* handle BONES */
    (
	    tmp =  readlong stream -- 00000000
	    unk =  readlong stream ; --print unk 10 000000
	    unk =  readlong stream ; tmp =  readlong stream -- 1E 000000 00000000
	    if (i != 1) then (
		    ID =  readlong stream ; -- format "ID %\n" ID
	    )
		else 	ID = 9999
	    Frame_cnt = readlong stream
	    tmp =  readlong stream ; unk =  readlong stream ;

 	    -- Read the translation data structure
        print ("@ trans: 0x"+ bit.intAsHex(ftell stream) as string)		
	    for fd=1 to Frame_cnt do
	    (
		    tran = TranslationAnimation()
		    tran.BoneId = i
		    tran.KeyFrame = i*200-10		-- 200 seems to work good for the boss
		    tran.Position = [ReadFloat stream, ReadFloat stream, ReadFloat stream]

		    append allTranslations tran
	    )

	    tmp =  readlong stream  -- 00000000
	    unk =  readlong stream ; --print unk   0x0215= 533
	    tmp =  readlong stream ; tmp =  readlong stream
	    Frame_cnt = readlong stream	
	    tmp =  readlong stream ; unk =  readlong stream ; 
    
	    /* ROTATION */
	    -- Read the rotation data structure
        print ("@ rot: 0x"+ bit.intAsHex(ftell stream) as string)
	    for fd=1 to Frame_cnt do
	    (
		    rot = RotationAnimation()
		    rot.BoneId = i
		    rot.KeyFrame = i*200-10
		    x = ReadFloat stream
		    y = ReadFloat stream
		    z = ReadFloat stream
		    w = ReadFloat stream
			
		    rot.Quaternion = quat x y z w
	
		    append allRotations rot
	    )

    )
    --print allTranslations
    --print allRotations

	--echo "-- DONE READING ANI FILE --\n"
	--echo "-- APPLYING ANIMATION TO THE BONES --\n"
	
	--Apply the Rotation
	prevQ = quat 1 -- set a starting rotation
	prevB = 1
	for i=1 to allRotations.count do
	(
		b = allBones[allRotations[i].BoneId].TheBone
		if(b == undefined) then continue
		
		t = allRotations[i].KeyFrame + startingFrame 
		q = allRotations[i].Quaternion

		with animate on
		(
			at time t (
				b.assumeskinpose()
				local mtrx = matrix3 1
				rotate mtrx (inverse q)
				mtrx.row4 = b.pos
				if b.parent != undefined then(
					mtrx = mtrx * b.parent.transform 
				)
				b.transform = mtrx
				deleteKey b.position.controller (numKeys b.position.controller)
				deleteKey b.scale.controller (numKeys b.scale.controller)
			)
		)
		
	)

	-- Apply the Translation
	for i=1 to allTranslations.count do
	(
		b = allBones[allTranslations[i].BoneId].TheBone
		t = allTranslations[i].KeyFrame + startingFrame
		pos = allTranslations[i].Position

		with animate on
			at time t 
				in coordsys parent b.position = pos
	)
	
	fClose stream
)

-- entry point --

ClearListener()
nBones = GetBoneNames()

if (nBones == undefined) then (
	messagebox "load ski and bon file before! (mesh and skeleton)"
	throw "load ski and bon file before! (mesh and skeleton)"
	exit -- the script should terminate here
)
else format "nBones: %\n" nBones

fname = getOpenFileName \
caption:"3D Model" \
types:"3D Model (*.*)|*.stck" \
historyCategory:"3D Model"

ReadAniFile fName nBones 10  -- uups, forgot nBones as a parameter
max create mode

```


The anims appear and Floating hit 1 perform similar to Repulse. Not sure if that's what it should be.
## Post #21
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-17T12:30:23+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> here's the script which was tested with Repulse.stck for mouse only!

Thank you, thank you, thank you! This is such a great advance!        
Yesterday was my birthday and I'm really, really happy just by seeing some movement     

> Reply from shakotay2
>
> The anims appear and Floating hit 1 perform similar to Repulse. Not sure if that's what it should be.

Yup, I've tested with other animations (like walk and run) and either the model only moves with his head/arms, or I get "unable to convert. undefinded to type: float"
I'm uploading a new model with known animations and the model with the error

Also I've noticed something that maybe will help (or maybe you've already noticed).
Most (but not all) models seem to have a number of frames equal to twice the number of bones. Eg: 44 bones = 88 frames
Maybe every two frames should be rotation and transition of a certain bone, the trick would be knowing what bone is it (maybe the .STCK on the main folder is for that)

[http://www.mediafire.com/download/46gun ... /Misty.rar](http://www.mediafire.com/download/46gunj126gdhelv/Misty.rar) --- 331 kb --- "unable to convert. undefinded to type: float"
[http://www.mediafire.com/download/its2x ... /Shina.rar](http://www.mediafire.com/download/its2x53xm9kj3n6/Shina.rar) --- 363 kb --- model with know animations
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-17T12:53:58+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

> Reply from asdasd123
>
> Maybe every two frames should be rotation and transition of a certain bone,that's true for most animation formats (you did not look into the script, did you?  )
btw: wouldn't call it "frames", it's animation data blocks. One frame in the transition data block, 17 frames in the rotation data block

> the trick would be knowing what bone is it (maybe the .STCK on the main folder is for that)the bone's list is logged in the Listener

> or I get "unable to convert. undefinded to type: float"that's animations with the index list I mentioned before (see picture in one of the previous posts)
Maybe it's sufficient to just skip them by inserting some dummy reads.
(nope, for _Walk.stck it's a little bit harder)

The indices are very likely to be the keyposes - so not a good idea to ignore them.
## Post #23
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-17T21:04:37+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

> Reply from shakotay2
>
> that's true for most animation formats (you did not look into the script, did you?  )

kkkkk did not. In fact ... i struggle reading code   

> Reply from shakotay2
>
> that's animations with the index list I mentioned before (see picture in one of the previous posts)
Maybe it's sufficient to just skip them by inserting some dummy reads.
(nope, for _Walk.stck it's a little bit harder)

The indices are very likely to be the keyposes - so not a good idea to ignore them.

Alright, what can I do to help ?
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-17T22:44:37+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

cross fingers?  

Well, I'm stuck atm and this ate way too much of my lifetime today.

The rotations are no quaternions in Misty's _Walk.stck. So I ignored them as well as those indices.
As a consequence for so much ignorance Misty's just shrinking vertically instead of walking:



Misty_Walk.JPG (57.19 KiB) Viewed 210 times



btw: wish you a Happy Birthday, subsequently! But no presents any more, I fear.
(Rotations will be the last thing I'll try ...)
## Post #25
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-01-19T14:49:51+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

(sorry for not answering sooner, i was in the hospital, broke my ankle)

> Reply from shakotay2
>
> cross fingers?

Alright, they are crossed

> Reply from shakotay2
>
> btw: wish you a Happy Birthday, subsequently! But no presents any more, I fear.
(Rotations will be the last thing I'll try ...)

Believe me, your efforts so far have been one of the best gifts I've recieved this year    

Even if you can't figure it out, I'm really thankfull for your desire to help.   

Really, thank you!
## Post #26
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2016-01-20T14:25:56+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

> --echo "-- DONE READING ANI FILE --\n"
>
>    --echo "-- APPLYING ANIMATION TO THE BONES --\n"
>
> 
>
>    --Apply the Rotation
>
>    prevQ = quat 1 -- set a starting rotation
>
>    prevB = 1
>
>    for i=1 to allRotations.count do
>
>    (
>
>       b = allBones[allRotations.BoneId].TheBone
>
>       if(b == undefined) then continue
>
> 
>
>       t = allRotations.KeyFrame + startingFrame 
>
>       q = allRotations.Quaternion
>
> 
>
>       with animate on
>
>       (
>
>          at time t (
>
>             b.assumeskinpose()
>
>             local mtrx = matrix3 1
>
>             rotate mtrx (inverse q)
>
>             mtrx.row4 = b.pos
>
>             if b.parent != undefined then(
>
>                mtrx = mtrx * b.parent.transform 
>
>             )
>
>             b.transform = mtrx
>
>             deleteKey b.position.controller (numKeys b.position.controller)
>
>             deleteKey b.scale.controller (numKeys b.scale.controller)
>
>          )
>
>     )
>
> 
>
>     )
>
> 
>
>    -- Apply the Translation
>
>    for i=1 to allTranslations.count do
>
>    (
>
>       b = allBones[allTranslations.BoneId].TheBone
>
>       t = allTranslations.KeyFrame + startingFrame
>
>       pos = allTranslations.Position
>
> 
>
>       with animate on
>
>          at time t 
>
>             in coordsys parent b.position = pos
>
>    )
>
> 
>
>    fClose stream
>
> )

for i=1 to keyframes do

(
Frame+=10
           at time Frame 
                (
                   animate on
                     (
                       --> BASE TRANSLATION  (Bip01)
                       --> BASE ROTATION        (Bip01)

                             for j=2 to bonecount do
                                 (
                                      --> PARENT (J) TRANSLATION
                                      --> PARENT (J) ROTATION
                                 )

                      )
                )
)

this template also works in max to make a bonesystem animated with keyframes and with different Speed between each keyframe played
## Post #27
- Username: KamixSama
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 28, 2017 2:11 pm
- Post datetime: 2017-06-12T23:43:08+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

Hi  XeNTaxX Member

and @shakotay2

i was asking for a animatin import script (3dsmax) (.stck) files...
i saw some threads on this forum about importing .stck files.

and i wil be very happy if someone have a working import script
## Post #28
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-03-12T21:21:30+00:00
- Post Title: Re: Importing .STCK animation - We need your help!

it s possible to import animation stck in 3dsmax?
