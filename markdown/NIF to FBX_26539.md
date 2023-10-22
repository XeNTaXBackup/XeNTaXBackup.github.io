## Post #1
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-06T15:42:32+00:00
- Post Title: NIF to FBX?

Is there any way to convert nif to fbx with animations,mesh and skeleton?
I tried NifSkope but it only can be exported as .obj.
also I tried using blender plugin and it doesn't work, even noesis didn't work.
The game is Divinity 2 DKS.
Here is the file if someone want to look in it.
[https://www.sendspace.com/file/4ic8su](https://www.sendspace.com/file/4ic8su)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-06T17:08:39+00:00
- Post Title: NIF to FBX?

Nif 20.3.0.9, nearest hit is:

> Reply from shakotay2 ↑Sun Feb 21, 2021 3:15 am at Sun Feb 21, 2021 3:15 am
>
> 
Or try this:
.



nifObject.png (75.93 KiB) Viewed 236 times
## Post #3
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-06T17:23:48+00:00
- Post Title: NIF to FBX?

You are the one who managed to mod Divinity 2 DKS believe it or not we are still trying we even created a new tools for unpacking/repacking game files.
But that only exports .obj? I need .fbx

I even opened this file in NifSkope and it's working my question is how to get .fbx from that file?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-06T17:56:01+00:00
- Post Title: NIF to FBX?

> Reply from xandro ↑Tue Mar 07, 2023 1:23 am at Tue Mar 07, 2023 1:23 am
>
> 
You are the one who managed to mod Divinity 2 DKS believe it or not we are still trying we even created a new tools for unpacking/repacking game files.Haha, good things never die, do they? 

> But that only exports .obj? I need .fbxYeah; you could import .obj to Noesis then export to .fbx.
But it's probably the weights and skeleton you need, do you?

> I even opened this file in NifSkope and it's working my question is how to get .fbx from that file?Afair NifSkope exports to .obj only, does it?

Well, best choice would be Noesis then. But it's Nif importer doesn't deal with 20.3.0.9, just 20.3.0.4.
## Post #5
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-06T18:00:30+00:00
- Post Title: NIF to FBX?

Great game... Thank you for those guides 10+ years ago.
That's right I have single nif with animations,mesh and skeleton.
I want to get single .FBX and open it in blender I tried many many things nothing seemed to work.
I tried next : 
Noesis
NifSkope only able to export as .obj
Blender Plugin
3ds max plugin
If you have any advice or idea please feel free to share it.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-06T19:15:09+00:00
- Post Title: NIF to FBX?

You could try to get the skeleton from the nif file using Durik's SkelFinder:

> Reply from Durik256 ↑Sat Nov 19, 2022 10:46 am at Sat Nov 19, 2022 10:46 am
>
> 
Some basic knowledge required about bones and matrixes, though. Usually you'll need three addresses: start of bone names table, start of hierarchy table and start of matrices.
So many bones in the boar nif at 0x1311...(maybe for different LODs?) But with some luck the bone names' table starts at 0x1B09 (05 000000= 5, length DWord of "Bip01")
## Post #7
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-06T22:48:17+00:00
- Post Title: NIF to FBX?

I found a way with blender plugin I got some version which works kinda.
So the problem is next
I can import whole nif with mesh,animation and skeleton animation works but not all of them sometimes models are buggy do you maybe know the reason?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-06T23:52:29+00:00
- Post Title: NIF to FBX?

> Reply from xandro ↑Tue Mar 07, 2023 6:48 am at Tue Mar 07, 2023 6:48 am
>
> 
I found a way with blender plugin I got some version which works kinda.
So the problem is next
I can import whole nif with mesh,animation and skeleton animation works but not all of them sometimes models are buggy do you maybe know the reason?No, I didn't use Blender Nif importers for years. But if you have a working model you simply could add debug print lines into said py script, then compare the logged lines from both, a working model and a buggy one.

Thus you'll see at least where the problems is (you need to have some python skills and format understanding to solve it then, though).

Did you check the console output? Usually gives a first hint.
## Post #9
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T10:52:03+00:00
- Post Title: NIF to FBX?

Let me explain it like this, I need to export that NIF file to FBX with animation,mesh and armature.
I did some research and someone did it in 2010/2011 even imported it in Unity I found out that guy used some blender plugin and pyffi I guess.Unfortunatly he don't know which version he used and he told me he had a lot of problem but made it work.
And I'm not very familiar with python to do that by myself.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T11:08:59+00:00
- Post Title: NIF to FBX?

> Reply from xandro ↑Thu Mar 30, 2023 6:52 pm at Thu Mar 30, 2023 6:52 pm
>
> And I'm not very familiar with python to do that by myself.I'm sorry to say but I don't think that anyone else will do it for you (10 years later).

It's not a matter of scripting or coding - it's just a matter of creating a workflow.
(If you can't do that you might rethink your ambitions.)

My best suggestion would be to start with the meshes:

> Reply from shakotay2 ↑Mon Mar 28, 2016 4:48 pm at Mon Mar 28, 2016 4:48 pm
>
> 

> Reply from shakotay2 ↑Tue Apr 24, 2012 7:29 am at Tue Apr 24, 2012 7:29 am
>
> 
read the NifTools section in the above linked post.
If you can re-create any workflow we might talk about the skeleton.

(I have no idea whether that unity guy you mentioned got working animations. This would be a long way to go.)
## Post #11
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T11:50:42+00:00
- Post Title: NIF to FBX?

He did there is even a youtube video, we talked and he told me that he had a lot of problems.
So I'm c# developer I created a couple of tools in the past but for this one I have no idea from where to start.
I tried many blender plugin and only one seemed to work but not propertly, animations are messy.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T12:17:31+00:00
- Post Title: NIF to FBX?

> Reply from xandro ↑Thu Mar 30, 2023 7:50 pm at Thu Mar 30, 2023 7:50 pm
>
> I tried many blender plugin and only one seemed to work but not propertly, animations are messy.Why not upload a sample in question and tell us your workflow?  

(Plus, if you have at least one working animation you should show it, too, of course.)
## Post #13
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T12:31:31+00:00
- Post Title: NIF to FBX?

Here is a nif object : [https://www.sendspace.com/file/4wy8av](https://www.sendspace.com/file/4wy8av)
Blender plugin I use : [https://www.sendspace.com/file/gl3xmh](https://www.sendspace.com/file/gl3xmh)

How it looks once I import it in blender : [https://prnt.sc/Osu8jXM7VG_-](https://prnt.sc/Osu8jXM7VG_-)
When I play the animation I clearly can see mesh moves but not propertly.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T13:09:11+00:00
- Post Title: NIF to FBX?

> Reply from xandro ↑Thu Mar 30, 2023 8:31 pm at Thu Mar 30, 2023 8:31 pm
>
> 
Here is a nif object : https://www.sendspace.com/file/4wy8av
Blender plugin I use : https://www.sendspace.com/file/gl3xmh

How it looks once I import it in blender : https://prnt.sc/Osu8jXM7VG_-
When I play the animation I clearly can see mesh moves but not propertly.Thank you!

Well, from here [https://github.com/niftools/blender_nif ... don/issues](https://github.com/niftools/blender_niftools_addon/issues) I can see you gave a feedback. Brave!  

The project's last update is from a year ago - so it's assumed to be "fresh".  It provides general nif support, afaics.
(Maybe they're not focused on Divinity II nifs, surprise.)

I'll try this out. But don't expect too much.
## Post #15
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T13:19:27+00:00
- Post Title: NIF to FBX?

Like I said I asked anyone and everywhere I did everything I could.
I just don't understand how someone in 2010/2011 manage to export it in .FBX I think they used PyFFI in that time.
I even tried to install windows 7 on virtualbox and tried to install old blender 2.49b and old pyffi but no luck.
And yes they are not focusing on Divinity 2 no one does.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T14:47:43+00:00
- Post Title: Re: NIF to FBX?

Which blender version did you use for the plugin?
When I try 2.82 which the Niftools were allegedly written for I get:
"ImportError: cannot import name 'prod' from 'math' (unknown location)"

(I used blender 2.82, 64 bit, btw.)
## Post #17
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T14:49:39+00:00
- Post Title: Re: NIF to FBX?

I used blender 3.4 and it worked except for animations.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T14:54:07+00:00
- Post Title: Re: NIF to FBX?

blender 32 bit or 64 bit version?
## Post #19
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T14:55:34+00:00
- Post Title: Re: NIF to FBX?

It's 64bit version.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T15:24:55+00:00
- Post Title: Re: NIF to FBX?

well, see, there's a problem with the back legs:
.



pig_strange_legs.png (209.8 KiB) Viewed 127 times



Quadruped models are said to be more difficult. Did you try a character model?
Or an animated chest, if any?

This will take some time to check the scripts. As always I'm very busy. So can take some weeks.
But don't expect more than some print lines for debugging.

When you delete the pig's mesh and look at its skeleton you can guess that it's faulty.
You might try a skeleton builder to get the correct skeleton. There's two tools, one from Durik, the other one from Bigchillghost.

btw, when unfolding the bones hierarchy of Scene root in the outliner it looks ok.
So it's assumed that the rotations were calculated wrongly (just a wild guess).
## Post #21
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T15:45:49+00:00
- Post Title: Re: NIF to FBX?

Here try this model : [https://www.sendspace.com/file/fzm8eh](https://www.sendspace.com/file/fzm8eh)
80% of animations works propertly, still there is a problem with others.
About those coordinates, someone told me there is a problem with calculating rotation's while developers told me "You don't know what you talk about" so I came here in hope someone could show me a right direction, that guy even send me all the math required to calculate it right, I'm just not great with python.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T16:09:21+00:00
- Post Title: Re: NIF to FBX?

yeah, cool. You can export it to fbx and load it into Noesis.

The pig's head's moving nicely from 240 ms to 500 ms, for example.
edit: well, seems it's milliseconds, not frames in Noesis (up to 1200). In blender it's assumed to be frames (up to 250?)

Here's the pig's skeleton in smd format (maybe some rotation values are wrong?)

```
nodes
  0 "Reference"  73
  1 "Reference NonAccum"  0
  2 "Bip01"  1
  3 "Bip01 Footsteps"  2
  4 "Bip01 Pelvis"  2
  5 "Bip01 Spine"  4
  6 "Bip01 Spine1"  5
  7 "Bip01 Spine2"  6
  8 "Bip01 Neck"  7
  9 "Bip01 Head"  8
  10 "Bip01 HeadNub"  9
  11 "Bip01 Ponytail1"  9
  12 "Bip01 Ponytail1Nub"  11
  13 "Bip01 Ponytail2"  9
  14 "Bip01 Ponytail2Nub"  13
  15 "Bip01 JawBone"  9
  16 "Dummy_Impact_05"  9
  17 "Dummy_Cast_Secondary"  9
  18 "Dummy_Cast_Primary"  9
  19 "Dummy_Impact_02"  9
  20 "Dummy_Head_Above"  9
  21 "Dummy_Head_Around"  9
  22 "Bip01 Clavicle.L"  8
  23 "Bip01 UpperArm.L"  22
  24 "Bip01 Forearm.L"  23
  25 "Bip01 Hand.L"  24
  26 "Bip01 Finger0.L"  25
  27 "Bip01 Finger0Nub.L"  26
  28 "Dummy_Impact_04"  22
  29 "Bip01 Clavicle.R"  8
  30 "Bip01 UpperArm.R"  29
  31 "Bip01 Forearm.R"  30
  32 "Bip01 Hand.R"  31
  33 "Bip01 Finger0.R"  32
  34 "Bip01 Finger0Nub.R"  33
  35 "Dummy_Impact_01"  30
  36 "Dummy_Impact_03"  6
  37 "Bip01 Thigh.L"  5
  38 "Bip01 Calf.L"  37
  39 "Bip01 HorseLink.L"  38
  40 "Bip01 Foot.L"  39
  41 "Bip01 Toe0.L"  40
  42 "Bip01 Toe0Nub.L"  41
  43 "Bip01 Thigh.R"  5
  44 "Bip01 Calf.R"  43
  45 "Bip01 HorseLink.R"  44
  46 "Bip01 Foot.R"  45
  47 "Bip01 Toe0.R"  46
  48 "Bip01 Toe0Nub.R"  47
  49 "Bip01 Tail"  5
  50 "Bip01 Tail1"  49
  51 "Bip01 TailNub"  50
  52 "Boar"  73
  53 "Bip01 Footsteps_end"  3
  54 "Bip01 HeadNub_end"  10
  55 "Bip01 Ponytail1Nub_end"  12
  56 "Bip01 Ponytail2Nub_end"  14
  57 "Bip01 JawBone_end"  15
  58 "Dummy_Impact_05_end"  16
  59 "Dummy_Cast_Secondary_end"  17
  60 "Dummy_Cast_Primary_end"  18
  61 "Dummy_Impact_02_end"  19
  62 "Dummy_Head_Above_end"  20
  63 "Dummy_Head_Around_end"  21
  64 "Bip01 Finger0Nub.L_end"  27
  65 "Dummy_Impact_04_end"  28
  66 "Bip01 Finger0Nub.R_end"  34
  67 "Dummy_Impact_01_end"  35
  68 "Dummy_Impact_03_end"  36
  69 "Bip01 Toe0Nub.L_end"  42
  70 "Bip01 Toe0Nub.R_end"  48
  71 "Bip01 TailNub_end"  51
  72 "Boar_end"  52
  73 "Scene Root"  -1
end
skeleton
time 0
  0 0.000000 0.000000 0.000000 -0.000000 -1.570796 -1.570796
  1 0.000000 0.000000 0.000000 -0.000000 0.000000 -0.000000
  2 517.459900 463.074432 515.832092 -1.570055 -0.000024 -0.000000
  3 -591.973633 -0.000066 -0.000018 1.570795 0.000000 -0.000000
  4 0.000115 -0.000074 -0.000017 -0.000000 -1.570796 -1.570797
  5 45.538841 55.676006 45.528015 1.191767 0.000006 0.000033
  6 164.696304 201.302734 164.673782 0.314925 0.000012 0.000016
  7 145.875610 178.290054 145.870728 0.183933 0.000003 0.000003
  8 -0.000014 93.754105 -0.200937 -0.000000 -0.000000 0.000000
  9 -0.000058 252.194473 0.000029 -1.397790 0.000050 0.000004
  10 -0.000074 298.048584 -0.000026 0.000000 0.000000 -0.000000
  11 -63.308262 -37.067284 -46.798855 -0.510581 -1.225192 1.792191
  12 -0.000059 195.990448 0.000116 1.571593 -0.000003 -3.141592
  13 102.855873 90.544868 80.694115 -2.989203 0.299004 1.845733
  14 0.000056 195.990479 -0.000072 1.571593 -0.000003 3.141593
  15 -1.767554 -218.092484 34.795414 3.141591 -0.095118 1.570796
  16 76.953209 -10.236980 531.403015 -3.141591 0.304331 1.570796
  17 10.028607 -196.528748 497.110565 -3.141591 0.312574 1.570797
  18 10.020944 -193.782288 496.316040 -3.141591 0.277684 1.570796
  19 102.759064 302.322357 -44.360611 -3.141591 0.304331 1.570796
  20 15.591098 406.861572 -94.534187 -3.141591 0.304331 1.570796
  21 15.417193 68.282410 14.109765 -3.141591 0.308373 1.570796
  22 145.585236 0.000090 0.200517 2.510821 0.001049 1.570722
  23 -0.000006 230.582291 0.000026 -1.315316 -0.339778 1.534946
  24 0.000144 507.108093 0.000047 -0.604740 0.000006 0.000003
  25 0.000005 204.178528 0.000016 -1.210856 0.090976 -0.250377
  26 0.000054 67.611160 -0.000018 0.000033 -0.000773 0.000033
  27 -0.000180 16.902819 -0.000042 -0.000000 0.000000 -0.000000
  28 53.875999 140.821945 113.337616 1.733357 -0.930459 -1.772541
  29 -145.585251 0.000119 0.201262 2.510822 -0.001072 -1.570706
  30 -0.000025 230.582535 -0.000225 -1.545917 0.339816 -1.535007
  31 -0.000065 507.108215 0.000050 -0.604730 0.000021 0.000011
  32 0.000021 204.178436 0.000107 -1.211005 -0.074903 0.252041
  33 -0.000027 67.611191 -0.000026 0.000033 0.000840 0.000033
  34 0.000116 16.902765 0.000038 3.141592 0.000000 0.000000
  35 -43.247368 43.655651 -58.757385 -0.035712 -0.122443 -1.275804
  36 -236.528778 121.321335 -154.707977 3.141559 1.507641 1.570766
  37 67.815338 43.736511 56.894299 1.401501 0.102906 2.909705
  38 0.000061 293.582458 -0.000058 -1.637556 -0.000040 0.000001
  39 0.000013 183.356033 -0.000011 1.561059 0.000000 0.000042
  40 -0.000038 177.932999 -0.000004 -0.128693 0.199656 0.156429
  41 -0.000081 62.202305 80.051582 1.570796 -0.000000 -0.000000
  42 0.000091 8.113413 -0.000001 -3.141593 -0.000000 0.000000
  43 -74.628746 -58.022881 -44.860973 1.761433 -0.102937 -2.909771
  44 -0.000044 293.582336 -0.000080 -1.673452 -0.000022 0.000001
  45 -0.000038 183.355911 0.000071 1.561032 0.000000 0.000037
  46 -0.000016 177.933105 0.000216 -0.458122 -0.238829 -0.084071
  47 -0.000013 62.202354 80.051628 1.570796 0.000000 0.000000
  48 -0.000004 8.113349 0.000003 -0.000000 0.000000 -0.000000
  49 -50.685326 -64.217865 -57.601292 2.108591 -0.000008 0.000028
  50 96.758041 118.265938 96.741570 -0.280043 -0.000061 0.000261
  51 0.000017 195.990570 -0.000004 1.571593 -0.000003 3.141593
  52 0.000000 0.000000 0.000000 -0.000000 -1.570796 -1.570796
  53 0.000005 295.986786 -0.000012 -0.000000 -0.000000 -0.000000
  54 -0.000025 155.017593 -0.000013 -0.000000 0.000000 -0.000000
  55 0.000018 195.990601 -0.000027 0.000000 0.000000 0.000000
  56 -0.000016 195.990555 0.000059 0.000000 0.000000 0.000000
  57 -0.000024 155.017609 0.000017 0.000000 0.000000 -0.000000
  58 0.000011 155.017548 -0.000053 -0.000000 0.000000 -0.000000
  59 0.000002 155.017502 0.000005 0.000000 0.000000 -0.000000
  60 -0.000001 155.017532 0.000018 0.000000 0.000000 -0.000000
  61 -0.000036 155.017563 0.000003 0.000000 0.000000 -0.000000
  62 0.000001 155.017456 0.000023 0.000000 0.000000 -0.000000
  63 -0.000000 155.017502 -0.000008 -0.000000 0.000000 -0.000000
  64 0.000023 16.902819 0.000014 -0.000000 0.000000 -0.000000
  65 -0.000005 196.016251 -0.000002 -0.000000 0.000000 0.000000
  66 0.000039 16.902754 0.000013 -0.000000 -0.000000 -0.000000
  67 0.000047 277.787476 0.000009 -0.000000 0.000000 0.000000
  68 -0.000005 263.815338 0.000003 -0.000000 0.000000 -0.000000
  69 -0.000016 8.113394 0.000001 0.000000 0.000000 -0.000000
  70 0.000032 8.113385 0.000001 -0.000000 0.000000 -0.000000
  71 0.000021 195.990570 0.000048 0.000000 -0.000000 0.000000
  72 0.000000 100.000000 -0.000000 -0.000000 0.000000 -0.000000
  73 0.000000 0.000000 0.000000 -1.570796 -0.000000 0.000000
end
```
## Post #23
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T16:13:45+00:00
- Post Title: Re: NIF to FBX?

Hmm okay this is step  I tried exporting it with noesis before and it never worked except for raw mesh.
How could I check if rotations are good? maybe compare them with one from nifSkope? I'm not sure, nifskopes uses different coordinate system as far as I know.
Also how did you get those numbers?
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T16:30:05+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Fri Mar 31, 2023 12:13 am at Fri Mar 31, 2023 12:13 am
>
> How could I check if rotations are good?For the pig the mouth is moving nicely from 950 ms to the end. This means rotations for related bones are correct. This is strange, usually when using wrong formulas every bone is affected. In some cases (other format, though) I set all rotations to zero and checked the translation. but this doesn't work always.

Thus I could see whether the skeleton was intact.

Instead of wild guessing I'd recommend to build the skeleton using a skeleton finder. There's some dozens of example here in the forum by Bigchillghost and Durik. With some luck there's a nif example among them, dunno.

> maybe compare them with one from nifSkope? I'm not sure, nifskopes uses different coordinate system as far as I know.The main problem with Nifskope is that it exports to obj only. At least the last version I used one or two years ago.

Ha, well, I remember having had NifSkope compiled on my old PC. I have no idea whether I can get it running again (because of HD change).

"The numbers?" Simply export as SMD from Noesis after having dragged an fbx onto it. Yeah, one of the coolest features of Noesis. Wouldn't want to miss it...
## Post #25
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T16:32:55+00:00
- Post Title: Re: NIF to FBX?

So you are telling me the skeleton could be the problem and I should try to export it on some other way?
Because those nif files are from parts(mesh,skeleton,animations) and I merge them in one NIF so blender could open them otherwise there is couple of problems.

Sorry, When I said "numbers" I meant rotations, thanks I will check that in noesis.
Also I remember noesis could export nif skeleton to fbx.
Here is the skeleton of the pig : [https://www.sendspace.com/file/8652du](https://www.sendspace.com/file/8652du)
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T16:51:31+00:00
- Post Title: Re: NIF to FBX?

That skeleton looks decent. Now it's just a matter of time to combine this skeleton with the animation frames.  But who will do it?  

But it has less bones and the hierarchy might be different. Maybe not so easy to perform?

```
nodes
  0 "Scene Root"  -1
  1 "Reference"  0
  2 "Reference NonAccum"  1
  3 "Bip01"  2
  4 "Bip01 Footsteps"  3
  5 "Bip01 Pelvis"  3
  6 "Bip01 Spine"  5
  7 "Bip01 Spine1"  6
  8 "Bip01 Spine2"  7
  9 "Bip01 Neck"  8
  10 "Bip01 Head"  9
  11 "Bip01 HeadNub"  10
  12 "Bip01 Ponytail1"  10
  13 "Bip01 Ponytail1Nub"  12
  14 "Bip01 Ponytail2"  10
  15 "Bip01 Ponytail2Nub"  14
  16 "Bip01 JawBone"  10
  17 "Dummy_Impact_05"  10
  18 "Dummy_Cast_Secondary"  10
  19 "Dummy_Cast_Primary"  10
  20 "Dummy_Impact_02"  10
  21 "Dummy_Head_Above"  10
  22 "Dummy_Head_Around"  10
  23 "Bip01 L Clavicle"  9
  24 "Bip01 L UpperArm"  23
  25 "Bip01 L Forearm"  24
  26 "Bip01 L Hand"  25
  27 "Bip01 L Finger0"  26
  28 "Bip01 L Finger0Nub"  27
  29 "Dummy_Impact_04"  23
  30 "Bip01 R Clavicle"  9
  31 "Bip01 R UpperArm"  30
  32 "Bip01 R Forearm"  31
  33 "Bip01 R Hand"  32
  34 "Bip01 R Finger0"  33
  35 "Bip01 R Finger0Nub"  34
  36 "Dummy_Impact_01"  31
  37 "Dummy_Impact_03"  7
  38 "Bip01 L Thigh"  6
  39 "Bip01 L Calf"  38
  40 "Bip01 L HorseLink"  39
  41 "Bip01 L Foot"  40
  42 "Bip01 L Toe0"  41
  43 "Bip01 L Toe0Nub"  42
  44 "Bip01 R Thigh"  6
  45 "Bip01 R Calf"  44
  46 "Bip01 R HorseLink"  45
  47 "Bip01 R Foot"  46
  48 "Bip01 R Toe0"  47
  49 "Bip01 R Toe0Nub"  48
  50 "Bip01 Tail"  6
  51 "Bip01 Tail1"  50
  52 "Bip01 TailNub"  51
end
skeleton
time 0
  0 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
  1 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
  2 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
  3 -0.000000 52.770729 59.964443 0.000000 -0.000000 -1.570795
  4 -0.000000 0.000000 -59.197372 0.000000 -0.000000 1.570795
  5 -0.000000 0.000000 0.000000 -0.000000 -1.570796 -1.570795
  6 10.139530 -0.010773 0.000014 -0.000005 0.000001 1.192445
  7 36.609955 -0.024542 -0.000001 -0.000000 -0.000001 0.315119
  8 32.420204 -0.007331 -0.000001 -0.000000 -0.000000 0.184036
  9 9.375415 -0.020087 -0.000000 0.000000 0.000000 -0.000000
  10 25.219458 0.000003 -0.000001 -0.000002 0.000003 -1.398568
  11 29.804855 0.000003 -0.000001 -0.000000 0.000000 0.000000
  12 8.112296 -1.618045 -18.132809 -1.818831 1.260274 -0.574104
  13 19.599062 0.000007 0.000002 3.141592 -0.000003 1.570000
  14 7.950425 -1.899242 20.265848 -2.888400 -1.299467 -0.572248
  15 19.599056 -0.000002 -0.000014 -3.141592 -0.000003 1.570000
  16 -21.809240 3.479539 -0.176734 -0.000000 -1.570796 -3.046475
  17 -1.023701 53.140301 7.695333 -0.000000 -1.570796 2.837261
  18 -19.652868 49.711071 1.002868 -0.000000 -1.570796 2.829019
  19 -19.378227 49.631603 1.002105 -0.000000 -1.570796 2.863909
  20 30.232227 -4.436053 10.275923 -0.000000 -1.570796 2.837261
  21 40.686115 -9.453411 1.559119 -0.000000 -1.570796 2.837261
  22 6.828235 1.410981 1.541732 -0.000000 -1.570796 2.833220
  23 0.000010 0.020042 14.558525 1.570796 -0.852983 1.570000
  24 23.058250 -0.000005 -0.000004 -1.538602 -0.031556 -1.124208
  25 50.710808 0.000006 0.000002 0.000000 -0.000000 -0.200000
  26 20.417854 0.000000 -0.000001 0.258563 -0.005290 -1.385574
  27 6.761121 -0.000001 -0.000000 -0.000796 0.000000 -0.000000
  28 1.690283 0.000000 -0.000001 -0.000000 0.000000 -0.000000
  29 14.082219 11.333744 5.387600 -1.690804 -0.000001 0.630550
  30 0.000011 0.020130 -14.558525 -1.570796 0.852977 1.570000
  31 23.058250 -0.000008 0.000001 1.538602 0.031556 -1.124208
  32 50.710819 0.000004 -0.000004 -0.000000 -0.000000 -0.200000
  33 20.417858 0.000001 0.000004 -0.254472 0.020400 -1.389525
  34 6.761122 -0.000001 0.000002 0.000796 -0.000000 -0.000000
  35 1.690279 -0.000000 -0.000000 -0.000000 0.000000 3.141592
  36 4.365568 -5.875739 -4.324728 -0.004591 -1.278076 -0.123117
  37 12.132133 -15.470763 -23.652884 -0.000000 -1.570796 1.633949
  38 -3.735413 9.426335 20.347826 2.917799 0.089684 1.572859
  39 29.358227 -0.000002 -0.000003 -0.000000 0.000000 -1.419884
  40 18.335594 0.000003 -0.000002 0.000000 0.000000 1.304289
  41 17.793306 -0.000001 0.000001 0.177600 0.163503 -0.236019
  42 6.220233 8.005159 0.000000 -0.000000 -0.000000 1.570796
  43 0.811335 -0.000000 0.000001 -0.000000 0.000000 -3.141593
  44 -3.735416 9.426451 -20.347771 -2.917799 -0.089689 1.572860
  45 29.358234 -0.000007 -0.000003 0.000000 0.000000 -1.419884
  46 18.335588 0.000004 -0.000002 0.000000 0.000000 1.304289
  47 17.793318 0.000006 -0.000001 -0.177599 -0.163502 -0.236019
  48 6.220235 8.005167 0.000000 -0.000000 -0.000000 1.570796
  49 0.811338 -0.000000 0.000001 0.000000 -0.000000 -0.000000
  50 -13.550591 -6.909731 -0.000009 -0.000009 -0.000003 -3.126749
  51 21.522713 -0.014268 0.000000 0.000019 0.000264 0.417888
  52 19.599062 0.000002 0.000001 3.141593 -0.000003 1.570000
end
```
## Post #27
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T17:19:05+00:00
- Post Title: Re: NIF to FBX?

How I can combine skeleton with animation frames? I'm willing to do it, I'm just not sure if I can.
So I still don't get it is the skeleton or animation problem? I always thought it's some animation problem.
It have less bones? what does that mean, you compared the Boar.nif and the one I sent you? with the skeleton?
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-30T18:00:03+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Fri Mar 31, 2023 1:19 am at Fri Mar 31, 2023 1:19 am
>
> 
How I can combine skeleton with animation frames? I'm willing to do it, I'm just not sure if I can.That's not a 15 minutes job. You'll need some experience for such. If you can't do it for yourself you need to wait 'til someone spends the time.

> So I still don't get it is the skeleton or animation problem?If I knew the solution I'd tell. Surely. I didn't check the animation frames.
What I can see is that the last skeleton.nif you uploaded looks decent. So that could be a good start.

> It have less bones? what does that mean, you compared the Boar.nif and the one I sent you? with the skeleton?Yes, I just compared both SMDs which I uploaded. There's no magic behind this.

I've already spent more time than intended. If you want it quick I can't serve, sorry. As I said, maybe in some weeks.
## Post #29
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-30T18:56:23+00:00
- Post Title: Re: NIF to FBX?

Okay, thank you so much
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-31T10:52:37+00:00
- Post Title: Re: NIF to FBX?

The funny thing is that NifSkope plays the boar's animation perfectly. But as I said this version exports to .obj only.
If I don't miss something I'll need to patch the source code (which I neither have the time nor am, well, capable  ) to get the anims out.
(afair there was a .dae export in one of those dozens of versions...)

edit: well, I'm such a dumbo. You can "Save As" Keyframe (*.kf). That it is...
.



Boar-Anim.jpg (156.74 KiB) Viewed 38 times



(hmm, dragging the .kf onto Noesis and loading the skeleton.nif doesn't show an animation. I could have sworn it worked with some other format, some day...) .kfa has the same contents as .kf, btw

I finally tried to combine nif/kf using said blender plugin. This is what it tells then:

niftools:INFO:Animation estimated at 24 frames per second.
niftools:WARNING:Unknown KF root block found : Scene Root
niftools:WARNING:This type isn't currently supported: <class 'generated.formats.nif.nimain.niobjects.NiNode.NiNode'>
niftools:INFO:Finished successfully
## Post #31
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-31T12:50:54+00:00
- Post Title: Re: NIF to FBX?

Yes, I forgot to mention NifSkope is playing every single animation perfectly I also tried the same thing you did with noesis It never showed any animation, this is all confusing.

I played around with .SMD but to be honest I have no idea what am I trying to do.

edit: I just tried improting humanSkeleton into blender and still no luck animations are not even working on 2 legs model
I tried import just skeleton as nif in Noesis everything looks perfect, even when I open it in blender (only skeleton without animations) looks great.
Once I add animations it's a mess.So I guess it has to do with some animations they are probably not calculated right.
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-31T13:40:05+00:00
- Post Title: Re: NIF to FBX?

The key is the keyframe (.kf) file.   Since you're a coder you should be able to extract the frame data. Next step would be to combine skeleton and that data. (I used md5anim format some years ago for testing; not for nif, though.)

(If interpolated keyframes are used things become a little bit more complicated.)

edit: well, I see, the .kf file is the same as the Boar-nif. This is so ridiculous. What do these guys think?
Seems we need to rip the frames manually...
## Post #33
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-31T14:08:57+00:00
- Post Title: Re: NIF to FBX?

Hmm.. It's a real mess even I could get those framerates I'm not capable of combining them with skeleton.
I think Larian made a terrible job with all of this.
I simply want to export those models, maybe add them in unity, this game is so forgotten, underrated and no one wants to work on it.
And here I am talking with the possibly first modder who managed to mod this game.

How i can rip the frames manually?
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-31T14:41:36+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Fri Mar 31, 2023 10:08 pm at Fri Mar 31, 2023 10:08 pm
>
> And here I am talking with the possibly first modder who managed to mod this game.I'm not sure whether I was the first one, more than ten years ago. What I know is: no one followed me, no one seemed to use my infos. Except you, maybe.  

> How i can rip the frames manually?You wrote, you're a C# coder, didn't you? Thus you should know about data structures. Keyframes are rather simple (sometimes; harder, if interpolated, compressed, whatever f...)

In the Boar nif search for blocks of 26 zeroes. First occurence of keyframes should be at 0x55654. count there is (0x29) = 41, size of block= 312,
well could be bone number and a float (2+4 bytes), so weights table? No, numbers get much too high. So it's frametime and float?

I have no idea.

The next block at 0x557c4 has a count of 667, 667*6= 4002 -> 0xFA2, so calculated block end at 0x56766.
In fact it's 0x567AC, but that shouldn't matter. Seems it's 27 blocks, what does that mean?

Blocksizes vary, too much guesswork. 

I'll leave you alone now. Maybe I could give you an impression, how to analyse that nif?
Maybe simply log some blocks and try to give their contents some meaning.
## Post #35
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-31T14:52:41+00:00
- Post Title: Re: NIF to FBX?

You made that guide and it helped me so much. I even managed to enable night in some areas in that game, people loved it.
Yes I'm C# dev I even created a tool to extract all .NIF textures from divinity 2 to .DDS.
I have problem understanding the data structure I never reversed engineered anything before this game and before your guide, only that made me learn it how to do it, and i'm still just a begginer.Once I find everything I need in HEX it's actually pretty simple to get all of that with some code.The hardest part is to analyze the whole .KF file.

It would be nice if you have any advice what should I look in those KF/NIF files, I know even nifSkope have option to show every offSet of specific block.
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-31T14:59:56+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Fri Mar 31, 2023 10:52 pm at Fri Mar 31, 2023 10:52 pm
>
> It would be nice if you have any advice what should I look in those KF/NIF files, I know even nifSkope have option to show every offSet of specific block.Yep, NifSkope is a pretty good "data viewer". In fact I have little to no knowledge about kf files. Plus, what we have isn't a real kf, afaics, but a nif file containing the animation frames.

So I'd suggest to log some of the blocks and show your results.
## Post #37
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-31T15:04:15+00:00
- Post Title: Re: NIF to FBX?

Okay one last question because I start working on that, what the result should look like once I get it.Am I looking for keyframes? how they look like?, I'm really not sure what I should find in that NIF file
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-31T15:30:01+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Fri Mar 31, 2023 11:04 pm at Fri Mar 31, 2023 11:04 pm
>
> 
Okay one last question because I start working on that, what the result should look like once I get it.Am I looking for keyframes? how they look like?, I'm really not sure what I should find in that NIF fileYou shouldn't find keyframes, simply log some blocks; number (2 bytes), float (4 bytes).

For understanding keyframes you need to google, I guess. Learn about transition/translation and rotation, and quaternions, maybe.

Here's frame matrices: 
> Reply from shakotay2 ↑Sat Jun 29, 2013 3:34 pm at Sat Jun 29, 2013 3:34 pm
>
> 

This is code to read keyframes (example only,does not fit for every animation format):

```
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
```
## Post #39
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-03-31T15:49:09+00:00
- Post Title: Re: NIF to FBX?

Thanks I'm checking everything in nifskope for now I even remove bunch of branchs that was useless I removed all other animation and just left one to see what is going to happen, everything works fine but nifSkope if giving me wrong offSet for some things.

Here is the screenshot of something they called "Compact Control Points" : [https://prnt.sc/deBC4VNkqA-b](https://prnt.sc/deBC4VNkqA-b)
I tried removing those and animations is breaking(like one leg is not moving anymore...)

I found where they are (thanks to nifSkope) : [https://prnt.sc/7N1D78mG97C7](https://prnt.sc/7N1D78mG97C7)
For some reason those numbers are not in the order in hex like in the nifSkope.'
Now even I manage to create a tool to get those numbers what should my next step be I have no clue. I just know I will have to combine them somehow with skeleton and display them somewhere.

edit : So what I found I discovered is that I will surely need those "Compact Control Points", still I have to check what else.
After all I do from NifSkope I can't import it in blender again.
I tried comparing values from Compact Control Points with the one from SMD file and they are not there hmm?
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-01T16:10:07+00:00
- Post Title: Re: NIF to FBX?

Ok, forget the blocks I assumed to be logged: they seem to contain just "per vertex weights".

This is funny. Where, the hell, are the frames in this d... nif?

edit: meanwhile I'd guess they're preceded by 000000 FFFFFFFF. There's 1108 of them in the boar nif.
## Post #41
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-04-01T16:37:56+00:00
- Post Title: Re: NIF to FBX?

It's really weird.
I'm right now trying to create own tool to export those skeletons (for now) but I'm with something.

This is SMD exported by nif and I discovered the numbers on the right side are some references to bones I guess.
Here is a picture : [https://prnt.sc/AA1Cz7V_tHhK](https://prnt.sc/AA1Cz7V_tHhK)

I can't find those number anywhere in the file I even tried using NifSkope but it's a different.
Here is the skeleton I'm trying to analyze : [https://www.sendspace.com/file/ni5vc9](https://www.sendspace.com/file/ni5vc9)

Anyway I tried to find something in those anim nif files but no luck with that, they used NIF files for almost everything textures,objects,items,animations I even found the one that are used for some settings in game It's ridiculous.

I asked to many folks and no one managed to do it.They are probably not interested or not capable of.

edit : 
Here is the animation of model where I removed all other animation and left only one to make it easier to analyze : [https://www.sendspace.com/file/2dej89](https://www.sendspace.com/file/2dej89)

I only found those `Compact Control Points` which has some numbers Im not sure what they mean, on the other hand I don't see any floats values.
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-01T18:05:41+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Sun Apr 02, 2023 12:37 am at Sun Apr 02, 2023 12:37 am
>
> This is SMD exported by nif and I discovered the numbers on the right side are some references to bones I guess.That's the parent ids. Time to learn the basics...
## Post #43
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-04-01T18:08:27+00:00
- Post Title: Re: NIF to FBX?

Okay but where are those Id's in nif file?
## Post #44
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-04-01T23:19:00+00:00
- Post Title: Re: NIF to FBX?

> Reply from shakotay2 ↑Sun Apr 02, 2023 2:05 am at Sun Apr 02, 2023 2:05 am
>
> 
Time to learn the basics...
Now that right there is PRICELESS!
## Post #45
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-04-01T23:24:14+00:00
- Post Title: Re: NIF to FBX?

I'm sorry about it but I never before heard of .SMD files, it's my first time working with it.
## Post #46
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-04-02T00:21:52+00:00
- Post Title: Re: NIF to FBX?

Does not matter the file format. One needs to understand the basics of Parent-Child relationship in skeletal structures.
There is also the GrandParent-Partent-Child and such! And in some systems? Each bone desendent of a Parent Bone needs to be accounted for.
So if an Arm bone goes up? Any Bone attached needs to account for that.
In some cases? The animation information found in a file does not account for the computational differences.
So a strict export of an animation file may show as a screwed up animation with a subpar exporter.

So say I have an animation that the arm is raised. Now in the Game Engine the rest of the arm follows.
Upon export of the animation information? The animation can be screwed up since computational movement is in the Engine itself.

It is rare but I have seen it and have Game source code that proves it.

It is easy to see the effect if you use 3dMax and know how to create a Biped with given bone information.
## Post #47
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-02T05:27:08+00:00
- Post Title: Re: NIF to FBX?

> Reply from xandro ↑Sun Apr 02, 2023 12:37 am at Sun Apr 02, 2023 12:37 am
>
> I only found those `Compact Control Points` which has some numbers Im not sure what they mean, on the other hand I don't see any floats values.Once you've found out what they mean you'll be king.  
But before reinventing the wheel I'd suggest to check Nif.xml for example (just a wild guess, type is float here, while your CCPs are integers):

```
        For interpolators storing data via a B-spline.
        <add name="Start Time" type="float">Animation start time.</add>
        <add name="Stop Time" type="float">Animation stop time.</add>
        <add name="Spline Data" type="Ref" template="NiBSplineData">Refers to NiBSplineData.</add>
        <add name="Basis Data" type="Ref" template="NiBSplineBasisData">Refers to NiBSPlineBasisData.</add>
    </niobject>
```


I don't have any idea:

```
32769 32048 29616 32769 31584 29616 32769 31421 29616 32769 31482 29616 32769 31809 29616 32769 
32339 29616 32769 32731 29616 32769 32655 29616 32769 32192 29616 32769 31683 29616 32769 31466 
29616 32769 31523 29616 32769 31544 32770 32766 32814 32770 32766 32814 32770 32766 32814 32769 
32766 32814 32770 32766 32814 32770 32766 32814 32770 32766 32814 32770 32766 32814 32770 32766 
32814 32770 32766 32814 32770 32766 32814 32770 32765 32814 32770 32766 32814 32770 32766 32814 
32770 32766 32814 32770 32766 32814 32770 32766 32814 32770 32766 32814 32770 43162 32770 43118 
32770 43019 32770 42848 32770 42677 32770 42523 32770 42410 32770 42353 32770 42382 32770 42492 
32770 42649 32770 42828 32770 43000 32770 43135 32770 43208 32770 43242 32770 43241 32770 43204 
32770 43127 32770 42987 32770 42814 32770 42636 32770 42481 32770 42376 32770 42354 32770 42426 
32770 42562 32770 42733 32770 42913 32770 43068 32770 43182 32770 43208 32770 43202 32770 43178 
32770 43162 32770 43162 62554 32784 62474 32807 62305 32861 62030 32956 61746 33054 61467 33144 
61202 33213 60969 33252 60774 33244 60644 33189 60541 33109 60449 33016 60384 32927 60347 32856 
60348 32817 60393 32795 60493 32791 60647 32804 60887 32835 61232 32898 61645 32981 62107 33070 
62588 33152 63063 33212 63506 33232 63884 33203 64178 33140 64334 33053 64370 32958 64300 32869 
64169 32805 63950 32778 63475 32769 62965 32777 62675 32783 62573 32783 33752 43532 33713 43505 
33624 43441 33452 43305 33257 43135 33053 42942 32875 42760 32769 42647 32824 42707 33008 42898 
33223 43104 33431 43287 33605 43426 33729 43517 33792 43560 33821 43579 33820 43579 33789 43558 
33722 43512 33593 43417 33416 43275 33206 43089 32991 42881 32814 42696 32771 42649 32903 42791 
33108 42996 33325 43196 33519 43359 33670 43474 33770 43545 33792 43560 33787 43557 33766 43542 
33752 43532 33753 43532 48368 33314 48368 33613 48368 34301 48368 35611 48368 37088 48368 38621 
48368 39947 48368 40725 48368 40321 48368 38957 48368 37345 48368 35771 48368 34449 48368 33488 
48368 33010 48368 32769 48368 32781 48368 33036 48368 33544 48368 34542 48368 35886 48368 37471 
48368 39079 48368 40393 48368 40715 48368 39733 48368 38209 48368 36577 48368 35110 48368 33940 
48368 33196 48368 32963 48368 33028 48368 33218 48368 33306 48368 33311 870 36588 846 36424 
791 36046 689 35345 579 34576 468 33799 376 33145 323 32769 351 32964 445 33632 
560 34443 677 35260 779 35966 856 36492 895 36756 915 36891 914 36884 893 36742 
851 36461 772 35916 668 35200 550 34379 436 33571 346 32929 324 32775 391 33249 
497 34005 616 34839 727 35611 820 36243 880 36653 899 36783 894 36747 878 36641 
871 36593 870 36590 31148 33512 31185 33493 31269 33448 31431 33343 31616 33204 31809 33036 
31977 32873 32076 32769 32025 32824 31852 32997 31648 33177 31451 33329 31287 33437 31170 33502 
```


Some values (say 32769 or 32770) appear and repeat in a strange manner. I thought 29616  to be "reliable" but it has 18 occurences only.

edit: after having had a closer look into the NifSkope source code I'd suggest to download and compile it (Qt required with the version I have).

There's void doKeyframes() in Skeleton.cpp.  It should be possible to patch that code for logging the frames.

Also I overread this:

> Reply from xandro ↑Fri Mar 31, 2023 12:32 am at Fri Mar 31, 2023 12:32 am
>
> Also I remember nifskope could export nif skeleton to fbx.Could you tell which NifSkope version you used for this?
## Post #48
- Username: xandro
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Aug 02, 2021 11:55 pm
- Post datetime: 2023-04-02T09:45:29+00:00
- Post Title: Re: NIF to FBX?

Sorry  I wanted to say Noesis not nifSkope.
I will download a source code and try to modify some things.
I also asked a couple of people on discord server called "Nif Mania" I hope someone will respond.

edit : someone told me the frames in kf file depends on the type of interpolator, some int/short values represent floats in smaller range like 0 to 1 or -1 to 1

They also told me about rotations : "If you want to get the rotations, you use the rotation handle as the offset in the Compact Control Points array of the NiBSplineData. You take element size as 4. You then get from that array the Num Control Points elements that you have in NiBSplineBasisData"

When I asked about keyframes they told me this : 
"I assume you mean the times associated with that, they are uniform between the start and stop time"
Here is how pyffi calculates them : [https://prnt.sc/4vHpP9RF7dKT](https://prnt.sc/4vHpP9RF7dKT)
