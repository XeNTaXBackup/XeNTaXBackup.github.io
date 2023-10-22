## Post #1
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-11-30T22:58:57+00:00
- Post Title: FGDK3 animations and bones (PS2)

Hello everyone, I was wondering if anyone would want to take a quick look at this. For a while I've been working on reverse engineering the formats used by Frontier Developments' FGDK3 engine used in some of their older games. Models and textures have been easy to document but animations and bones are still a WIP. Here's what I have to share right now:

* Uses 3x3 Animation Matrice possibly? (mentioned within game's executable)
* Bone names are stored around 0003D3D0 (hex) within sample overlay
* Total size of animations is 155440?
* Animations at 25fps
Also, tool currently used for extraction operations [https://github.com/20kdc/Gibbed.FGDK3/tree/armatures](https://github.com/20kdc/Gibbed.FGDK3/tree/armatures) (armature branch of fork)
I'm not sure exactly where animation or bones are but I'm assuming they are stored as either a float32 or float64, not sure about the endianness


Thanks in advance!
[sample.7z](https://xentaxbackup.github.io/file/21328_sample.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-02T13:12:14+00:00
- Post Title: FGDK3 animations and bones (PS2)

How did you get the dog? A .dat file is required, the sample you uploaded is named 5.ovl (output from ExportPreload.exe, obviously).

```
Usage: Gibbed.FGDK3.ExportPreload [OPTIONS]+ <PRELOAD.DAT> [output_path]

Options:
  -t, --target=VALUE         set target (dogs/zoo)
  -v, --verbose              be verbose
  -h, --help                 show this message and exit
```


btw: from my experience throwing in an animation data file usually leads to nothing

(Most if not any "working" animation threads start with the mesh, then the skeleton, then weights, then anims. Just my 2 cents.)
The weights part may be skipped in case you're satisfied with a moving skeleton as a first step.
## Post #3
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-02T20:26:00+00:00
- Post Title: FGDK3 animations and bones (PS2)

The Preload.dat you mentioned comes from the root of the disc, and basically defines where the data in all of the overlays are stored, among other things. I got the dog by providing the program with preload.dat, dogs.dgf, and OVERLAY.zip, all from the root of the game disc. I can provide this files if needed, although I’ll need to upload them externally due to them being too big. The program currently outputs textures, gui text, and models from the overlays into png, txt, and dae/obj respectively. The current version of the program outputs dae while older versions did obj.
## Post #4
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-02T20:28:16+00:00
- Post Title: FGDK3 animations and bones (PS2)

With the fork I sent in the OP, this one can partially parse bones, with their names and vert groups, although it isn’t complete and has some issues. The major thing is that in its current state it does not do bone positions and all bones are at the root, however vert groups somewhat work and moving the bones will effect some parts of the mesh, although some names are wrong and there is no parent/child layout yet.
## Post #5
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-02T20:31:05+00:00
- Post Title: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Thu Dec 02, 2021 9:12 pm at Thu Dec 02, 2021 9:12 pm
>
> 
L, then anims. Just my 2 cents.)
The weights part may be skipped in case you're satisfied with a moving skeleton as a first step. This is probably one of the main goals is to get proper bones position so they can be moved like normal.
## Post #6
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-02T20:46:41+00:00
- Post Title: FGDK3 animations and bones (PS2)

Update! I've uploaded the files you'll need [here](https://file.io/cytKZXxxoES0). Note that the archive I sent only includes the 5.ovl, and not any of the other overlays in the overlay.zip. If needed, I can provide the full overlay.zip if required.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-03T08:21:11+00:00
- Post Title: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Fri Dec 03, 2021 4:26 am at Fri Dec 03, 2021 4:26 am
>
> I got the dog by providing the program with preload.dat, dogs.dgf, and OVERLAY.zipUnderstand. (So there's no separate "dogs.dat"?)

The "program" is ExportPreload.exe? (Just to be sure.  ) 

> Reply from Dogmander ↑Fri Dec 03, 2021 4:26 am at Fri Dec 03, 2021 4:26 am
>
> The program currently outputs textures, gui text, and models from the overlays
questions: 1) I still don't understand the workflow of ExportPreload.exe: when this exe creates an .ovl file why is it required to provide it with OVERLAY.zip?  
2) "models from the overlays"? So there's the dog's model (data) in 5.ovl? (looks to me as if it contained animation data and bone names)

> Note that the archive I sent only includes the 5.ovl,The one from your opening post?
(btw, "[https://file.io/cytKZXxxoES0](https://file.io/cytKZXxxoES0)", it says "The file you requested has been deleted".)

preload.dat, dogs.dgf are huge, aren't they?
What I'd need for a start is just the mesh data (and skeleton data) from the dog.
## Post #8
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-03T20:06:49+00:00
- Post Title: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Fri Dec 03, 2021 4:21 pm at Fri Dec 03, 2021 4:21 pm
>
> 
Dogmander wrote: ↑Fri Dec 03, 2021 4:26 amI got the dog by providing the program with preload.dat, dogs.dgf, and OVERLAY.zipUnderstand. (So there's no separate "dogs.dat"?)

The "program" is ExportPreload.exe? (Just to be sure.  ) 
Dogmander wrote: ↑Fri Dec 03, 2021 4:26 amThe program currently outputs textures, gui text, and models from the overlays
questions: 1) I still don't understand the workflow of ExportPreload.exe: when this exe creates an .ovl file why is it required to provide it with OVERLAY.zip?  
2) "models from the overlays"? So there's the dog's model (data) in 5.ovl? (looks to me as if it contained animation data and bone names)
Note that the archive I sent only includes the 5.ovl,The one from your opening post?
(btw, "https://file.io/cytKZXxxoES0", it says "The file you requested has been deleted".)

preload.dat, dogs.dgf are huge, aren't they?
What I'd need for a start is just the mesh data (and skeleton data) from the dog.
Answers to your questions, no, there is no dogs.dat, all games using this engine have the file named that. Yes, the program is named ExportPreload.exe. You are required to provide it in the overlay.zip as normally that is how all the ovl files are stored together on the game disc. Yes, the overlays have model data, even if it isn’t clear apparent when looking at it, as well as other types of game resources. The files aren’t that big, all together they are around 1mb (not including all of the other ovls, only 5.ovl). I’ll send you links to what you’ll need when I’m at my computer, as I’m sending this from my phone.
## Post #9
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-03T20:39:19+00:00
- Post Title: FGDK3 animations and bones (PS2)

This repo I created a while back has a few useful things that you might want to take a look at. [https://github.com/Dogmander/dogs-life-docs](https://github.com/Dogmander/dogs-life-docs)
Here are the downloads, I created multiple download sources just incase one of them doesn't work.
[https://filebin.net/o4ck4rlezg8ddih2](https://filebin.net/o4ck4rlezg8ddih2)
[https://gofile.io/d/KI9wxC](https://gofile.io/d/KI9wxC)
## Post #10
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-03T22:55:14+00:00
- Post Title: FGDK3 animations and bones (PS2)

Did you send a reply but deleted it? I received a notification saying you posted a reply but I don't see it and when clicking on it, it states it doesn't exist. If you simply weren't ready or something of the likes that's fine.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-03T23:55:48+00:00
- Post Title: FGDK3 animations and bones (PS2)

yeah, had a problem using parameters for debugging but after dozens of attempts I found this to work:
-tdogs Preload.dat D:\\tmp\\unp

(Will take some time, C# is not my preferred coding language, hopefully I'll get the skeleton at least.)
## Post #12
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-04T00:15:46+00:00
- Post Title: FGDK3 animations and bones (PS2)

Alright, sounds good. Hope that all is well.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-05T23:54:57+00:00
- Post Title: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Sat Dec 04, 2021 8:15 am at Sat Dec 04, 2021 8:15 am
>
> 
Alright, sounds good. Hope that all is well.Yeah, thanks. Hope all's fine for you, too.

Rick's source code, btw, is written excellently ([https://github.com/gibbed/Gibbed.FGDK3](https://github.com/gibbed/Gibbed.FGDK3)). 
The parenting of bones seems to be missing, though. So no bones' hierarchy shown in blender.
But since I'm not familiar with the .dae format it's a long way to go.
So far I checked the collection of vertex, weights and face data. Seems to be ok (surprise  ).

But the .dae files I get from the compiled project are faulty - I have no idea, where my fault could be (only change were some additional Console.WriteLine()):

```
Root
AutoExporterJoint27
AutoExporterJoint10
AutoExporterJoint11
AutoExporterJoint28
AutoExporterJoint43
AutoExporterJoint5
AutoExporterJoint12
AutoExporterJoint20
AutoExporterJoint8
AutoExporterJoint30
AutoExporterJoint31
AutoExporterJoint42
AutoExporterJoint41
AutoExporterJoint40

```
It's not a matter of the paramters since I get the same error when I drag n' drop PRELOAD.DAT onto the compiled exe file.
.

shape_0_lod0.dae created using the exe from your zip, with correct bone names:

```
_world_
_root_
Between_the_eyes_dummy
Bip01
Bip01_Head
Bip01_L_Calf
Bip01_L_Clavicle
Bip01_L_Finger0
Bip01_L_Foot
Bip01_L_Forearm
Bip01_L_Hand
Bip01_L_Thigh
Bip01_L_Toe0
Bip01_L_UpperArm
Bip01_Neck
...
```
## Post #14
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-06T20:22:59+00:00
- Post Title: FGDK3 animations and bones (PS2)

Good to hear back. If need be, you could switch to have it use a different output format, COLLADA was chose as it supported bones (unlike OBJ) and it doesn’t have the format differences that FBX has.
## Post #15
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-16T21:18:37+00:00
- Post Title: FGDK3 animations and bones (PS2)

Just checking in, what's the haps? I'm still here, thankfully.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-17T00:08:24+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

well, still that bug with the .dae output (missing Bip01 lines), I compiled ICSharpCode.SharpZipLib.dll to be sure to have the correct version, at no avail. (Maybe it's because I downgraded from Net 4.8 which I don't want to install.  )

(Or maybe there's a newer version of ShapeExporter.cs?)

(And, 'yes', we'll need that .dae export because wavefront .obj doesn't support bones, afaik.)
## Post #17
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-12-29T20:04:43+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

How difficult would it be to fix that bug? Also I know that Wavefront OBJ doesn't support bones. I believe the ShapeExporter.cs is the newest, although you can check the other branches and main repo to see if they are different or lack the bug.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-30T12:37:32+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Thu Dec 30, 2021 4:04 am at Thu Dec 30, 2021 4:04 am
>
> although you can check the other branches and main repo to see if they are different or lack the bug.Well, I don't have the time for fiddling, sorry.
I guess, the exe file you compiled/uploaded depends on different source files. Here is a picture showing parts of the dae files (left side from the FGDK3 project I compiled, right side: output from the exe you've provided):
.



differences.png (105.97 KiB) Viewed 94 times


<Name_array id="Armature_m0-skin-joints-array" count="64"> is the correct count, obviously (missed it on the picture).
## Post #19
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-02T17:28:24+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Which repo did you compile? I think you might have used one of the other ones and not the armature one I sent. [https://github.com/20kdc/Gibbed.FGDK3/tree/armatures](https://github.com/20kdc/Gibbed.FGDK3/tree/armatures) This one is the only one I know that sets the proper names
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-02T18:18:44+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Mon Jan 03, 2022 1:28 am at Mon Jan 03, 2022 1:28 am
>
> 
Which repo did you compile? I think you might have used one of the other ones and not the armature one I sent. https://github.com/20kdc/Gibbed.FGDK3/tree/armatures This one is the only one I know that sets the proper namesIt reads "20kdc Armature stuff (incomplete)" and it doesn't contain the AssetExporters folder (with ShapeExporter.cs).
Thus I used the main branch with "Git clone" to get AssetExporters. (I could try this with the armatures branch, too, but to be honest, I don't believe that this will change anything.  )
## Post #21
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-02T23:08:49+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

If you are unsure of the problem, you could probably write your own script based on the current one.
## Post #22
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-03T21:36:16+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

It would probably be a whole lot easier for you, as you could write a tool in a programming language you are better/more comfortable with than C#.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T07:20:39+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Tue Jan 04, 2022 5:36 am at Tue Jan 04, 2022 5:36 am
>
> 
It would probably be a whole lot easier for you, as you could write a tool in a programming language you are better/more comfortable with than C#.It would be a lot easier for me if you gave me your damned project you created the exe from instead of insulting me, man.
## Post #24
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T09:07:33+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

I’m sorry that I may have insulted you, I’ll provide the project when I’m at my PC.
## Post #25
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T10:25:36+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Tue Jan 04, 2022 3:20 pm at Tue Jan 04, 2022 3:20 pm
>
> 
Dogmander wrote: ↑Tue Jan 04, 2022 5:36 am
It would probably be a whole lot easier for you, as you could write a tool in a programming language you are better/more comfortable with than C#.
It would be a lot easier for me if you gave me your damned project you created the exe from instead of insulting me, man.

Here's the project you asked for. Sorry if I was rude.
[Gibbed.FGDK3-armatures-source.7z](https://xentaxbackup.github.io/file/21512_Gibbed.FGDK3-armatures-source.7z)
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T12:32:22+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Thanks for the (working) source.
Well, like I thought: it was a source problem. Me dumbo thought the more modular repo to be the newest one. Big fault!
 void ExportShapes() for example is located in program.cs now, AssetExporters\ShapeExporter.cs doesn't exist any more. How misleading...

Now I'm starting where I was 2 weeks ago, motivation: low...

edit: let's start with the simple (?) things: why are the bone "all in a clump" when loading the dae into blender?

Need to check the assumed parent ID, other = boneNameLookupStream.ReadValueU32(endian);

SMD file, just an ugly try, most is a mess, from L_forearm down bones are "in a line" but fingers should be spread

```
nodes
0 "<root>" -1
1 "<world>" 0
2 "Between_the_eyes_dummy" 4
3 "Bip01" 1
4 "Bip01 Head" 23
5 "Bip01 L Calf" 11
6 "Bip01 L Clavicle" 14
7 "Bip01 L Finger0" 10
8 "Bip01 L Foot" 5
9 "Bip01 L Forearm" 13
10 "Bip01 L Hand" 9
11 "Bip01 L Thigh" 33
12 "Bip01 L Toe0" 8
13 "Bip01 L UpperArm" 6
14 "Bip01 Neck" 33
15 "Bip01 Neck1" 14
16 "Bip01 Neck2" 15
17 "Bip01 Pelvis" 3
18 "Bip01 Ponytail1" 33
19 "Bip01 Ponytail11" 18
20 "Bip01 Ponytail12" 19
21 "Bip01 Ponytail2" 20
22 "Bip01 Ponytail21" 21
23 "Bip01 Ponytail22" 22
24 "Bip01 R Calf" 30
25 "Bip01 R Clavicle" 14
26 "Bip01 R Finger0" 29
27 "Bip01 R Foot" 24
28 "Bip01 R Forearm" 32
29 "Bip01 R Hand" 28
30 "Bip01 R Thigh" 33
31 "Bip01 R Toe0" 27
32 "Bip01 R UpperArm" 25
33 "Bip01 Spine" 17
34 "Bip01 Spine1" 33
35 "Bip01 Spine2" 34
36 "Bip01 Spine3" 35
37 "Bip01 Tail" 36
38 "Bip01 Tail1" 37
39 "Bip01 Tail2" 38
40 "Bip01 Tail3" 39
41 "Bip01 Tail4" 40
42 "Bip02 L Finger1" 10
43 "Bip02 L Finger3" 10
44 "Bip02 Ponytail2" 33
45 "Bip02 Ponytail21" 44
46 "Bip02 R Finger1" 29
47 "Bip02 R Finger3" 29
48 "bone" 55
49 "Collar" 55
50 "Eyes" 55
51 "HotdogDummy" 55
52 "Jake" 55
53 "Mouth_holding_dummy" 55
54 "RectumDummy" 55
55 "Tag" -1
end
skeleton
time 0
0 0.000012 -135.985001 -264.412018 -2.751688 1.570796 -1.570796
1 -41.802799 -0.822902 545.385010 3.141585 1.300268 1.570804
2 -0.000015 -0.000015 -0.000000 -1.570796 -0.000001 -1.570795
3 48.677998 0.000357 -102.729996 -0.391902 -0.000000 -0.000004
4 87.908302 0.000004 -0.064592 0.104719 -0.000000 0.000000
5 81.635696 0.000004 -0.068024 0.157079 -0.000000 0.000000
6 86.508301 0.000003 -0.067405 0.340340 -0.000001 0.000000
7 89.756897 0.000002 0.000128 -1.627959 0.000003 -0.000108
8 2.369920 -0.000000 -0.097856 0.169626 -0.000000 0.000000
9 124.685997 0.000006 -0.073088 0.204533 -0.000001 0.000000
10 93.737503 0.000005 0.000013 0.773037 0.000104 0.000036
11 6.195540 58.429401 -49.931099 1.530382 -0.086315 0.748660
12 30.737902 -0.004928 -0.034709 0.056873 0.617945 0.107381
13 44.046600 -0.007682 -0.048295 -0.086146 0.109650 0.167418
14 16.094799 -56.768703 -51.734303 1.690288 0.139266 -0.662433
15 32.876400 0.008654 -0.033763 -0.017693 -0.580771 -0.260300
16 43.763401 0.007689 -0.050204 -0.206987 0.004320 -0.151071
17 62.528301 1.293060 6.918280 1.518101 -0.000002 0.000002
18 25.130800 -0.000000 -0.006980 -1.484663 0.000003 0.000003
19 76.269897 31.907900 -40.635597 0.753683 -0.190700 0.150815
20 76.623192 32.228802 -40.610699 -0.638316 -0.198548 -0.128362
21 76.269798 -26.926901 -40.635399 0.753684 0.190701 -0.150810
22 76.623192 -27.247801 -40.610596 -0.638316 0.198549 0.128367
23 96.096695 1.334790 -39.836800 -1.474804 -0.000002 -3.141590
24 140.921005 0.930111 30.271900 1.570772 1.483534 1.570823
25 140.355011 -2.973210 43.989902 0.069811 -0.942476 1.570799
26 -13.470599 -16.011499 106.790993 1.570639 0.781765 1.570917
27 16.633001 31.064499 -76.223595 -1.895220 0.550515 -2.647642
28 170.609009 0.000009 -0.000019 1.502209 0.294888 -2.512872
29 161.408997 -0.000006 -0.000012 -0.878544 -0.000000 0.000000
30 176.556000 -0.000001 -0.000008 0.055860 -0.066815 -0.031688
31 59.564102 -5.496171 -20.726301 0.218066 -0.006518 0.015249
32 16.626001 -31.818699 -76.223793 -1.895343 -0.550711 2.647570
33 170.609009 -0.000029 0.000010 1.501098 -0.326937 2.551046
34 161.408997 -0.000011 -0.000014 -0.823140 -0.000000 0.000000
35 176.556000 -0.000003 -0.000013 -0.067115 0.070926 0.029823
36 59.685402 6.753920 -20.622902 0.296605 0.006518 -0.015249
37 -84.224892 64.010101 76.349007 -1.290346 0.104542 -3.057053
38 152.850006 -0.000008 -0.000013 -1.348498 0.000000 0.000000
39 182.147003 0.000001 -0.000022 -0.692784 0.050450 0.124569
40 10.075800 -3.371450 116.825996 1.633709 -0.099592 0.001741
41 -84.224892 -64.010002 76.349403 -1.281844 -0.079440 3.105671
42 152.850006 0.000001 -0.000009 -1.349208 0.000000 0.000000
43 182.147003 0.000012 0.000010 -0.696247 -0.051665 -0.070240
44 10.075800 -7.706210 116.825996 1.633709 0.099592 -0.001741
45 -141.056000 0.000518 25.919901 2.320231 -0.011592 0.013055
46 40.686802 -0.000003 -0.045662 -0.508899 0.076222 0.042537
47 65.668098 -0.000000 -0.084073 0.033926 -0.095940 0.003175
48 105.633995 -0.000003 -0.085351 0.348372 -0.049235 0.017828
49 114.047005 -0.000008 -0.063579 0.470105 -0.000001 0.000000
50 58.539398 -98.571198 1.162000 0.000001 -1.169371 0.000003
51 -3.091610 146.989990 269.766998 -1.616318 1.570796 3.119404
52 -3.092000 -3.732590 -49.846001 -0.196123 1.570796 1.860432
53 -3.146700 318.379974 271.213013 -3.141593 -0.000000 -1.570796
54 8193.000000 0.000003 410.422974 -0.036134 -1.000019 -0.000000
55 1.000000 2.000000 3.000000 0.000002 -1.000019 -1.555078
end

```
-------------------------

R_Clavicle is one bone of the skeleton - in "Collada 1.4.1" dae files the string is contained 8 times (or 18 sometimes). (That's why I prefer smd.)

And yeah, seems I'm quicker getting the skeleton directly from the .ovl file:

bone-no translation "euler angles (radians)"
---------------------------------------------
0 0.000012 -135.985001 -264.412018 -2.751688 1.570796 -1.570796
1 -41.802799 -0.822902 545.385010 3.141585 1.300268 1.570804
2 -0.000015 -0.000015 -0.000000 -1.570796 -0.000001 -1.570795
3 48.677998 0.000357 -102.729996 -0.391902 -0.000000 -0.000004
...
see above SMD lines
## Post #27
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T21:56:51+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Yeah, currently all that the script does is create a bunch of bones with their names and weights but it doesn't assign any of the bone locations to the bones, which is what we want. But it's good that it seems like you've figured out some stuff.
## Post #28
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:03:27+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Tue Jan 04, 2022 8:32 pm at Tue Jan 04, 2022 8:32 pm
>
> 


no translation "euler angles (radians)"
---------------------------------------------
0 0.000012 -135.985001 -264.412018 -2.751688 1.570796 -1.570796
1 -41.802799 -0.822902 545.385010 3.141585 1.300268 1.570804
2 -0.000015 -0.000015 -0.000000 -1.570796 -0.000001 -1.570795
3 48.677998 0.000357 -102.729996 -0.391902 -0.000000 -0.000004
4 87.908302 0.000004 -0.064592 0.104719 -0.000000 0.000000
5 81.635696 0.000004 -0.068024 0.157079 -0.000000 0.000000
6 86.508301 0.000003 -0.067405 0.340340 -0.000001 0.000000
7 89.756897 0.000002 0.000128 -1.627959 0.000003 -0.000108
8 2.369920 -0.000000 -0.097856 0.169626 -0.000000 0.000000
9 124.685997 0.000006 -0.073088 0.204533 -0.000001 0.000000
10 93.737503 0.000005 0.000013 0.773037 0.000104 0.000036
...

Are those values directly from the ovl?
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T22:04:38+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

That's what I wrote. 

(Sadly getting bone and parenting IDs is horrible. Now I understand why the project fails in getting them.)
## Post #30
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:06:38+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Got it, so do you think we'll be able to take the positional and rotational values and turn them into a more proper skeleton?
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T22:10:46+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Depends on the hierarchy - no hierarchy, no proper skeleton. (Simply look at the "order" of the bone names in the .ovl. Without any rule, afaics.)
## Post #32
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:19:48+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Looking at it, there seem to be common names for things, mainly Bip#, and we might be able to guess the hirarchy based on these and other things. Are we able to get the positions of all the bones in the ovl and create a bone for each of thoses at those positions?
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T22:23:13+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

yeah, but it's a matter of waste of time and life..

I did some fiddling (+/-  are the applied ID corrections, stopped it after a while...) So  32 +17 means 32 was 15 before.
Bones
 0 - <root> = 1
 1 - <world> = 0
 2 - Between_the_eyes_dummy = 29
 3 - Bip01 = 1
 4 - Bip01 Head = 23
 5 - Bip01 L Calf = 11
 6 - Bip01 L Clavicle = 14?
 7 - Bip01 L Finger0 = 10  -3
 8 - Bip01 L Foot = 5
 9 - Bip01 L Forearm = 11
 10 - Bip01 L Hand = 9  -3
 11 - Bip01 L Thigh = 17
 12 - Bip01 L Toe0 = 8
 13 - Bip01 L UpperArm = 6
 14 - Bip01 Neck = 33
 15 - Bip01 Neck1 = 14  -10
 16 - Bip01 Neck2 = 15

 17 - Bip01 Pelvis = 3?
 18 - Bip01 Ponytail1 = 33
 19 - Bip01 Ponytail11 = 18?
 20 - Bip01 Ponytail12 = 19
 21 - Bip01 Ponytail2 = 33?
 22 - Bip01 Ponytail21 = 21?
 23 - Bip01 Ponytail22 = 22?
 24 - Bip01 R Calf = 30  +23
 25 - Bip01 R Clavicle = 14?
 26 - Bip01 R Finger0 = 29 +12
 27 - Bip01 R Foot = 24  +16

 28 - Bip01 R Forearm = 32  +17
 29 - Bip01 R Hand = 28  +12
 30 - Bip01 R Thigh = 17
 31 - Bip01 R Toe0 = 27
 32 - Bip01 R UpperArm = 25  +11
 33 - Bip01 Spine = 3
 34 - Bip01 Spine1 = 33  +14
 35 - Bip01 Spine2 = 34  +14
 36 - Bip01 Spine3 = 35  +14
 37 - Bip01 Tail = 36 -3
 38 - Bip01 Tail1 = 37 -3
 39 - Bip01 Tail2 = 38 -3
 40 - Bip01 Tail3 = 39 -3
 41 - Bip01 Tail4 = 40 -3

 42 - Bip02 L Finger1 = 10
 43 - Bip02 L Finger3 = 10
 44 - Bip02 Ponytail2 = 74
 45 - Bip02 Ponytail21 = 75
 46 - Bip02 R Finger1 = 29
 47 - Bip02 R Finger3 = 29
 48 - bone = 82
 49 - Collar = 84
 50 - Eyes = 86
 51 - HotdogDummy = 22
 52 - Jake = 85
 53 - Mouth_holding_dummy = 30
 54 - RectumDummy = 104
 55 - Tag = 83

The problem is what is the order of matrices? Does it follow the odd order of bone name strings?
## Post #34
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:27:01+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

I'm not sure, all I know is that it is using a 3x3 matrice from what I found in the game executable, which makes sense. Also, in 5.ovl, there appear to be two sets of bone strings, one that we already found and one at the end of the file, I'm not sure what the other ones are for. Although, when fiddling around in an emulator and changing the names of the first set of bones to be different in memory, it did affect the transformations of the bones and stopped them from transforming most of the time, although some animations still worked.
## Post #35
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:29:32+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

I'll have to try with both sets of bone names to see what happens, this is with the first. This screenshot is from a while ago when I messed with it. Notice the glitch with one of the front paws. 


image_2022-01-04_172811.png (242.78 KiB) Viewed 113 times
## Post #36
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:30:36+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

image_2022-01-04_173032.png (185.03 KiB) Viewed 112 times
## Post #37
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:33:59+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Also, where in the OVL did you find most of the bones values (floating)? Are you able to provide some addresses or ranges of addresses?
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T22:38:21+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

The data I used starts around 0x3C106, with DWords included (those IDs?). 3x3 matrices (rotation), yes and 3 floats for translational values.
## Post #39
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:41:04+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Correct me if I'm wrong, but what are the IDs mainly for? My memory is a bit ruff on their purpose.
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T22:51:58+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

The bones are numbered, starting from 0xFFFF (-1) ("root" usually).
After the name there's the parenting ID (for smd files at least).
So
34 "Bip01 R Thigh" 4 
35 "Bip01 R Calf" 34 
36 "Bip01 R Foot" 35 
37 "Bip01 R Toe0" 36 

means R_Toe0 is tied to R_Foot. if the Foot moves the child (Toe) will be moving, too. (Or inverse kinematic, but that's another story...)
## Post #41
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T22:52:57+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Ah, I get it, so the IDs are needed for proper parenting and hierarchy.
## Post #42
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T23:20:21+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Wed Jan 05, 2022 6:51 am at Wed Jan 05, 2022 6:51 am
>
> 
The bones are numbered, starting from 0xFFFF (-1) ("root" usually).
After the name there's the parenting ID (for smd files at least).
So
34 "Bip01 R Thigh" 4 
35 "Bip01 R Calf" 34 
36 "Bip01 R Foot" 35 
37 "Bip01 R Toe0" 36 

means R_Toe0 is tied to R_Foot. if the Foot moves the child (Toe) will be moving, too. (Or inverse kinematic, but that's another story...)

Where and how are you sourcing these ids? where in each bone section are they located?
## Post #43
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-04T23:45:33+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Speaking of SMD files, are you currently doing anything with these bone values and inserting them into an SMD?
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-05T06:34:05+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

I've updated the SMD file here:

> Reply from shakotay2 ↑Tue Jan 04, 2022 8:32 pm at Tue Jan 04, 2022 8:32 pm
>
> 
As you can see it's a mess (even in the "good" section fingers, well, claws, are not spread):
.



FGDK3_skel_err.png (183.22 KiB) Viewed 27 times


(Changing 14 "Bip01 Neck" 36 won't change too much, will it?)

(Maybe the bone names need to be sorted, I have no idea.  )
Such like:
0 "__Root" -1 
1 "Bip01" 0 
2 "Bip01 Pelvis" 1 
3 "xxx" 2 
4 "Bip01 Spine" 2 
5 "Bip01 Spine1" 4 
6 "Bip01 Spine2" 5 
7 "Bip01 Spine3" 6 
8 "Bip01 Neck" 7 
...
## Post #45
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T11:16:29+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Yeah, that doesn’t look normal
## Post #46
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T12:36:10+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Wed Jan 05, 2022 2:34 pm at Wed Jan 05, 2022 2:34 pm
>
> 
I've updated the SMD file here:
shakotay2 wrote: ↑Tue Jan 04, 2022 8:32 pm
As you can see it's a mess (even in the "good" section fingers, well, claws, are not spread):
.
FGDK3_skel_err.png
(Changing 14 "Bip01 Neck" 36 won't change too much, will it?)

(Maybe the bone names need to be sorted, I have no idea.  )
Such like:
0 "__Root" -1 
1 "Bip01" 0 
2 "Bip01 Pelvis" 1 
3 "xxx" 2 
4 "Bip01 Spine" 2 
5 "Bip01 Spine1" 4 
6 "Bip01 Spine2" 5 
7 "Bip01 Spine3" 6 
8 "Bip01 Neck" 7 
...
Yeah, maybe it does need to be sorted, and just the game engine does that. I’m not sure. But does the sorting affect the positions and rotations of the bones?
## Post #47
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-05T15:58:42+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Using ASH on the dumped data:



5_dmp.png (86.5 KiB) Viewed 98 times
## Post #48
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-05T17:15:21+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

haha, savoir of the bones! I thought you could try out your ASH sooner or later.  
Happy New Year, Bigchillghost!
## Post #49
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T20:07:31+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Bigchillghost ↑Wed Jan 05, 2022 11:58 pm at Wed Jan 05, 2022 11:58 pm
>
> 
Using ASH on the dumped data:
5_dmp.png

Woah, cool! That looks pretty normal, except for that one bone in the ground. Could you send me this program and I can test it out? Hopefully this will help with figuring out the bones a lot! Bonetastic!
## Post #50
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T20:47:25+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Bigchillghost ↑Wed Jan 05, 2022 11:58 pm at Wed Jan 05, 2022 11:58 pm
>
> 
Using ASH on the dumped data:
5_dmp.png
I tried using ASH on my computer with the same settings shown in the screenshot with 5.ovl but it errors out. Help?  
[image_2022-01-05_154720.png](https://xentaxbackup.github.io/file/21532_image_2022-01-05_154720.png)
## Post #51
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T21:11:01+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from shakotay2 ↑Thu Jan 06, 2022 1:15 am at Thu Jan 06, 2022 1:15 am
>
> 
haha, savoir of the bones! I thought you could try out your ASH sooner or later.  
Happy New Year, Bigchillghost!
Have you had any luck with ASH, shakotay?
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-05T21:39:05+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

well, I feel ashamed, but it's too complicated for me. I usually do my SMD approach but I don't have that overview like Bigchillghost has.

I assume he dumped from # 0x3C106:
16 00 00 00  01 00 00 00 bone ID (22) parent ID (1)
 -0.000000 -0.000000 1.000000 
 1.000000 0.000000 0.000000 
 0.000000 1.000000 0.000000 
 0.000012 -135.985001 -264.412018 
20 00 02 00 
1A 00 00 00  16 00 00 00 
 -0.267238 0.000000 -0.963630 
 0.963630 -0.000002 -0.267238 
 -0.000002 -1.000000 0.000000 
 -41.802799 -0.822902 545.385010 
30 00 02 00 
1B 00 00 00  1A 00 00 00 
...
the IDs result in the following list where I didn't know which bones/names belonged to which ID. Now with Bigchillghost order it's more clear:
0 22  1
1 26  22
2 27  26
3 18  27
4 19  18
5 20  19
6 21  20
7 23  21
8 24  23
9 25  24
10 28  25
11 33  28
12 34  33
13 35  34

14 36  28
15 37  36
16 38  37

17 74  28
18 75  74

19 58  28
20 60  28
21 78  28
22 80  28
23 29  28
24 30  28
25 82  28

26 83  25

27 31  23 Clavicle to neck
28 10  31 upperarm to clavicle
29 11  10 forearm to upper
30 12  11 hand to forearm
31 13  12 finger hand

32 32  23
33 14  32
34 15  14
35 16  15
36 17  16

37 2 L_Thigh 18 (once you know this name things become clearer)
38 3  2
39 4  3
40 5  4

41 6 R_Thigh 18
42 7  6
43 8  7
44 9  8

45 39  18
46 40  39
47 41  40
48 42  41
49 43  42

50 104  26

51 84  1
52 85  1
53 86  1
...
56 00 00 00  01 00 00 00 
 -1.000000 0.000000 -0.000000 
 -0.000000 0.000000 1.000000 
 0.000000 1.000000 -0.000000 
 -3.146700 318.379974 271.213013 
70 03 02 00 

Don't remember if I changed some IDs (without a plan) so some may be wrong
## Post #53
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T21:44:21+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Do you think with chill's help from ASH we'll be able to automatically parse bones from OVLs and/or add proper functionality to Gibbed's tool?
## Post #54
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-05T21:52:14+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

well, ASH is a great tool, obviously. And it should be possible. Dunno about his plans but for me, I'm too busy with my own projects.
So I'm here from time to time (usually for 15-minutes-jobs  ) - maybe I get a proper SMD exported from 5.ovl in future.
## Post #55
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-05T22:00:06+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Okay, cool. But nonetheless the info from ASH should help somewhat with us and anyone else who decides to pick this up in the future.
## Post #56
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-06T00:25:18+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Well, happy New Year to you too, shakotay.  

The problem of this format lies in discrete bone index list. I tried to remap the bone IDs and the parent IDs in Noesis but the coord system of this format is in local space, and a former bone could be the child of a later bone so the "usual" workflow of converting a local space bone tree to world space no longer worked. So instead I just dumped the data from the file and filled the empty bone slots with Identity Matrices. Here's the Noesis script that'll perform the task to dump the data used in my previous post.
[0000_FGDK3(PS2)_ovl.zip](https://xentaxbackup.github.io/file/21533_0000_FGDK3(PS2)_ovl.zip)
## Post #57
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-06T00:58:48+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Bigchillghost ↑Thu Jan 06, 2022 8:25 am at Thu Jan 06, 2022 8:25 am
>
> 
Well, happy New Year to you too, shakotay.  

The problem of this format lies in discrete bone index list. I tried to remap the bone IDs and the parent IDs in Noesis but the coord system of this format is in local space, and a former bone could be the child of a later bone so the "usual" workflow of converting a local space bone tree to world space no longer worked. So instead I just dumped the data from the file and filled the empty bone slots with Identity Matrices. Here's the Noesis script that'll perform the task to dump the data used in my previous post.

It worked, thank you!
[image_2022-01-05_195846.png](https://xentaxbackup.github.io/file/21534_image_2022-01-05_195846.png)
## Post #58
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-06T01:23:46+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Okay, when I import it into Blender there are a few problems when looking at it with the dog model. First, it is tilted to the side a bit for some reason. Second, some of the bones don't line up correctly. Third, some bones are way off from where they would probably be. Nonetheless, for the most part it still worked although there are some quirks that need to be looked into.
[image_2022-01-05_202308.png](https://xentaxbackup.github.io/file/21535_image_2022-01-05_202308.png)
## Post #59
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-06T05:23:45+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Thu Jan 06, 2022 9:23 am at Thu Jan 06, 2022 9:23 am
>
> 
... some of the bones don't line up correctly ... some bones are way off from where they would probably be.
Last time I checked, Blender doesn't like FBX so much.
Don't know whether it's a matter of gimbal lock or something. You can try with different rotation order in ASH and see if things could change.

Edit: Never mind. It doesn't seem to work when using other rotation orders.

> Reply from Dogmander ↑Thu Jan 06, 2022 9:23 am at Thu Jan 06, 2022 9:23 am
>
> 
it is tilted to the side a bit for some reason
But this definitely is resulted from gimbal lock:



gimbal_lock.png (25.8 KiB) Viewed 32 times
## Post #60
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-06T20:12:22+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Bigchillghost ↑Thu Jan 06, 2022 1:23 pm at Thu Jan 06, 2022 1:23 pm
>
> 
Dogmander wrote: ↑Thu Jan 06, 2022 9:23 am
... some of the bones don't line up correctly ... some bones are way off from where they would probably be.

Last time I checked, Blender doesn't like FBX so much.
Don't know whether it's a matter of gimbal lock or something. You can try with different rotation order in ASH and see if things could change.

Edit: Never mind. It doesn't seem to work when using other rotation orders.
Dogmander wrote: ↑Thu Jan 06, 2022 9:23 am
it is tilted to the side a bit for some reason

But this definitely is resulted from gimbal lock:
gimbal_lock.png
How hard do you think it will be to solve this issue?
## Post #61
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-07T15:57:57+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

> Reply from Dogmander ↑Fri Jan 07, 2022 4:12 am at Fri Jan 07, 2022 4:12 am
>
> 
How hard do you think it will be to solve this issue?
According to the raw rotation matrix of "HotdogDummy" (as row-major):

```
-2.98e-08          0          1
1           5.76e-08   1.49e-08
```

The decoded Euler angles should be [-90 0 -90] for local space XYZ rotation order (or ZYX rotation order in world space, which corresponds to the spec in ASH). But you should use the ZYX rotation order on only those problematic matrices like the "HotdogDummy" one otherwise it'll trigger a butterfly effect (causing more gimbal lock issues) and make things much worse. Maybe in the future I'll find a more elegant solution but for now a manual correction will do the trick.



manually_corrected.png (21.64 KiB) Viewed 77 times
## Post #62
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-07T16:02:11+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Here's the ASCII version of the corrected FBX file (with rotations of "HotdogDummy" and "Jake" both set to [-90 0 -90]).


 5.7z
(3.84 KiB) Downloaded 13 times
## Post #63
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-08T04:17:30+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Okay, thank you. I’ll try this out tomorrow and tell you how it goes.
## Post #64
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-08T14:46:13+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Blender doesn't support ASCII FBX files, and when I convert them to binary with FBX Converter 2013.3, it has some issues in blender. Converting to DAE also has major issues. What should I try doing?
## Post #65
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-12T13:25:21+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Just noticed that there's a "multiplyBones" method in the Noesis API. Now it can be loaded correctly:


You can try export it to FBX/DAE/glTF etc. and see if Blender can import it without issues.
[0000_FGDK3(PS2)_ovl.zip](https://xentaxbackup.github.io/file/21589_0000_FGDK3(PS2)_ovl.zip)
## Post #66
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-12T21:46:16+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Thanks, I’ll try it out
## Post #67
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-12T23:12:48+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Was able to successfully output as DAE and import it into blender. The only small problem is that there is a very small bit of horizontal misalignment with the model, nothing too major and can probably be easily fixed (manually or automatically). All that needs to be done now for the most part is figuring out the weights for the model. 


image_2022-01-12_180635.png (50.52 KiB) Viewed 38 times

 

Edit: Another problem is that the bones "Collar" and "Eyes" don't appear to line up with where they are on the mesh, although this could be intentional for some reason.
## Post #68
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2022-01-12T23:16:58+00:00
- Post Title: Re: FGDK3 animations and bones (PS2)

Although, we could source the weights for the mesh from the vertex groups generated by gibbed.fgdk3 or whatever, as they do have proper weight locations. The names for the vertex weights that correspond to bone names are mostly wrong, though. [https://github.com/20kdc/Gibbed.FGDK3/tree/armatures](https://github.com/20kdc/Gibbed.FGDK3/tree/armatures)
