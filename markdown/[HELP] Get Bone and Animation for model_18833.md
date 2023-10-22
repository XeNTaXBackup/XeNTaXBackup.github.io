## Post #1
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-18T17:15:12+00:00
- Post Title: [HELP] Get Bone and Animation for model

..............
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-18T18:33:11+00:00
- Post Title: [HELP] Get Bone and Animation for model

> Reply from tainhx
>
> I have some obj with extension is *.skin , some files Bone with extension is *.bon and Animation is *.ani.... How can convert it to use in Blender or Unreal Engine?What game it is? There might already exist tools.

Using hex2obj:



CMS00441-skin.jpg (251.46 KiB) Viewed 608 times


bte: I've a deja vue as if a similar model was already treated in this forum
## Post #3
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-18T18:42:28+00:00
- Post Title: [HELP] Get Bone and Animation for model

Game is Scion of Fate. And How about bone and animation?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-18T19:23:42+00:00
- Post Title: [HELP] Get Bone and Animation for model

> Reply from tainhx
>
> Game is Scion of Fate.Surprise! 

> And How about bone and animation?Looks doable. But who would?
(From the low quality of the models I'd be surprised if someone would do it.)
## Post #5
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-19T07:03:19+00:00
- Post Title: [HELP] Get Bone and Animation for model

So you can't extract bone and animation, Master?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-19T08:01:13+00:00
- Post Title: [HELP] Get Bone and Animation for model

I'm too busy with other concerns, sorry. What I'm doing here are 15 minutes "jobs" just for fun (with very few exceptions  ).

(I'm planning to release some hex2skel tool since years but I'll need a month of spare time at least to finish it which I hadn't so far.)

In fact that .bon format is a little bit annoying, no time to fiddle out all the matrices
(some look ok, though, see Bip01 L Thigh for example):

```
1B 00 00 00 
Bip01 00 00 30 02 00 
    00 40 03 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 Scene Root  00 dae
    00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 B8 35 00 00 00 
    00 
    FF FF 7F BF 00 00 00 00 00 00 00 00 00 00 80 3F
    00 00 00 00 00 00 00 00 FF FF 7F 3F 00 00 00 00
    00 00 B8 35 00 00 00 00 00 00 00 00 79 84 7B 40
    50 C3 F7 B2 00 00 80 3F 
Bip01 Footsteps 28 00 00 00 00 00 00 
    00 00 EC FD 7F 28 00 2A 00 77 C2 F8 77 70 F1 FC 
    77 38 1C F9 77 1E 1C F9 77 18 D3 
Bip01 18 D3 00 0F 78 01 3B 01 10 D3 00 0F 
    70 05 3B 01 E8 16 44 0E 01 E1 12 00 14 00 00 00 
    70 05 3B 01 00 00 13 00 78 13 13 00 00 00 00 00 
    00 00 80 3F 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 80 3F 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00 
    00 00 00 00 80 BB F3 3C 50 C3 F7 B2 00 00 80 3F 
Bip01 Head 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
Bip01 Neck 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 DD 93 59 34 28 30 7D 3F 01 5B 17 BE 00 00 00 
    00 FF FF 7F 3F 12 19 DC B4 63 2D B8 B5 00 00 00 
    00 8F 49 BE B5 02 5B 17 BE 27 30 7D BF 00 00 00 
    00 00 00 00 00 2A 41 09 41 44 CC D8 B4 00 00 80 
    3F 
Bip01 L Calf 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 
Bip01 L Thigh 00 00 00 00 
    48 02 3B 01 30 01 40 0E 00 00 00 00 00 00 00 00 
    48 02 3B 01 00 00 00 00 00 00 00 00 00 00 00 00 
    90 FE 02 3E D8 95 7C BF 68 2C CE 3D 00 00 00 00 
    53 CF 7D BF B8 FD 04 BE 90 85 55 BC 00 00 00 00 
    75 71 D4 3C CD FE C8 BD 77 AD 7E BF 00 00 00 00 
    B5 6E 89 3F E2 72 2D 40 4F A7 FA BD 00 00 80 3F 
Bip01 L Clavicle 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 
Bip01 Neck 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 F9 58 64 3F A4 FD D3 
    BE 29 D5 39 3E 00 00 00 00 24 BC CF 3E 94 06 69 
    3F CC 0E A9 3D 00 00 00 00 75 27 4C BE FA 44 51 
    31 52 DC 7A 3F 00 00 00 00 4D 03 FE 3E 17 04 01 
    41 7F 01 15 31 00 00 80 3F 
Bip01 L Finger0 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 
```
## Post #7
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-19T16:29:53+00:00
- Post Title: [HELP] Get Bone and Animation for model

> Reply from Szkaradek123
>
> Hello

Here is blender importer for models from this game.
It works only with Blender version 249 and Python version 2.6


It import skinned and textured meshes with animations.

-select *.skn files for importing meshes
-select *.ani files for unpacking animations
-after unpacking *.ani files select *.anim files for  animation

For Noesis use fbx blender exporter. 

Importer:
http://www.mediafire.com/download/9fo7x ... -20%5D.zip


Example:
http://www.mediafire.com/download/9a45j ... onnest.zip

This plugin can use to extract *.ani files?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-19T17:54:12+00:00
- Post Title: [HELP] Get Bone and Animation for model

DragonNest uses "Eternity Engine Ani File 0.1" files which are totally different from the ones of Scions of Fate, afaics.
(The DragonNest meshes have *.skn extension while SoF meshes are *.skin.
So how could you think this could work anyhow?  )
## Post #9
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-20T07:49:58+00:00
- Post Title: [HELP] Get Bone and Animation for model

Sorry I dont have knowledge about 3d ....Currently I can get mesh from *.skin...And need some help for *.ani and *.bon
## Post #10
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-09-26T04:51:55+00:00
- Post Title: [HELP] Get Bone and Animation for model

> Reply from shakotay2
>
> I'm too busy with other concerns, sorry. What I'm doing here are 15 minutes "jobs" just for fun (with very few exceptions  ).

(I'm planning to release some hex2skel tool since years but I'll need a month of spare time at least to finish it which I hadn't so far.)

In fact that .bon format is a little bit annoying, no time to fiddle out all the matrices
(some look ok, though, see Bip01 L Thigh for example):
Code: Select allBoneN00002.bon
1B 00 00 00 
Bip01 00 00 30 02 00 
    00 40 03 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 Scene Root  00 dae
    00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 B8 35 00 00 00 
    00 
    FF FF 7F BF 00 00 00 00 00 00 00 00 00 00 80 3F
    00 00 00 00 00 00 00 00 FF FF 7F 3F 00 00 00 00
    00 00 B8 35 00 00 00 00 00 00 00 00 79 84 7B 40
    50 C3 F7 B2 00 00 80 3F 
Bip01 Footsteps 28 00 00 00 00 00 00 
    00 00 EC FD 7F 28 00 2A 00 77 C2 F8 77 70 F1 FC 
    77 38 1C F9 77 1E 1C F9 77 18 D3 
Bip01 18 D3 00 0F 78 01 3B 01 10 D3 00 0F 
    70 05 3B 01 E8 16 44 0E 01 E1 12 00 14 00 00 00 
    70 05 3B 01 00 00 13 00 78 13 13 00 00 00 00 00 
    00 00 80 3F 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 80 3F 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00 
    00 00 00 00 80 BB F3 3C 50 C3 F7 B2 00 00 80 3F 
Bip01 Head 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
Bip01 Neck 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 DD 93 59 34 28 30 7D 3F 01 5B 17 BE 00 00 00 
    00 FF FF 7F 3F 12 19 DC B4 63 2D B8 B5 00 00 00 
    00 8F 49 BE B5 02 5B 17 BE 27 30 7D BF 00 00 00 
    00 00 00 00 00 2A 41 09 41 44 CC D8 B4 00 00 80 
    3F 
Bip01 L Calf 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 
Bip01 L Thigh 00 00 00 00 
    48 02 3B 01 30 01 40 0E 00 00 00 00 00 00 00 00 
    48 02 3B 01 00 00 00 00 00 00 00 00 00 00 00 00 
    90 FE 02 3E D8 95 7C BF 68 2C CE 3D 00 00 00 00 
    53 CF 7D BF B8 FD 04 BE 90 85 55 BC 00 00 00 00 
    75 71 D4 3C CD FE C8 BD 77 AD 7E BF 00 00 00 00 
    B5 6E 89 3F E2 72 2D 40 4F A7 FA BD 00 00 80 3F 
Bip01 L Clavicle 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 
Bip01 Neck 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 F9 58 64 3F A4 FD D3 
    BE 29 D5 39 3E 00 00 00 00 24 BC CF 3E 94 06 69 
    3F CC 0E A9 3D 00 00 00 00 75 27 4C BE FA 44 51 
    31 52 DC 7A 3F 00 00 00 00 4D 03 FE 3E 17 04 01 
    41 7F 01 15 31 00 00 80 3F 
Bip01 L Finger0 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 00 00

So is there anyway to read this data and generate to Amature in Blender?
## Post #11
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-12-12T18:03:24+00:00
- Post Title: [HELP] Get Bone and Animation for model

hello, I have some info about this *.bon format

First 4 byte is NUmber of bones

Every bone has 164 byte for data in 3 part
part 1 50 bytes
part 2 50 bytes
=> relationship, local coordinate , global coordinate,...
part 3 64 bytes (matrix transform)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-14T16:55:39+00:00
- Post Title: [HELP] Get Bone and Animation for model

dunno why you opened another thread for it.
As I wrote the .bon format is weird
only thing that makes sense for me is the negation of assumed x position of L/R Forearm:

16 Bip01 L Forearm 8C 09 0B 00 00 00 00 00 43 00 00 
    00 E0 02 3B 01 E0 63 51 0E 00 00 00 00 AE 0A 07 
    00 E0 02 3B 01 00 00 

19 Bip01 L Forearm 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 1C D1 12 00 00 00 00 
    00 64 99 F8 77 00 00 13 00 40 CF 1C 00 

 0.876523 -0.481272 0.009180  0.000000   rotation matrix (?)
 -0.006603 0.007047 0.999953 0.000000 
 -0.481314  -0.876543 0.002999 0.000000 

 3.815593 5.535347 0.589638 1.000000  position


40 Bip01 R Forearm 8C 09 0B 00 00 00 00 00 43 00 00 
    00 E0 02 3B 01 E0 63 51 0E 00 00 00 00 AE 0A 07 
    00 E0 02 3B 01 00 00 

43 Bip01 R Forearm 00 00 00 00 00 
    00 00 00 00 00 00 00 00 00 1C D1 12 00 00 00 00 
    00 64 99 F8 77 00 00 13 00 40 CF 1C 00 

 -0.876523 -0.481272 0.009177 0.000000 
 -0.006600 -0.007047 -0.999953 0.000000 
 0.481314 -0.876543 0.003001 0.000000 

 -3.815595 5.535347 0.589627 1.000000 position




17 Bip01 L UpperArm 77 8C 09 0B 00 82 00 00 
    00 00 00 00 00 00 00 00 00 01 00 00 00 A8 2C DE 
    77 8C 09 0B 00 30 3F 15 0F 

24 Bip01 L UpperArm 00 13 00 0C 00 00 00 00 74 13 
    00 01 00 00 00 22 00 FB 7F 01 00 00 00 A8 D5 12 
    00 08 D5 12 00 94 E6 


41 Bip01 R UpperArm 77 8C 09 0B 00 82 00 00 
    00 00 00 00 00 00 00 00 00 01 00 00 00 A8 2C DE 
    77 8C 09 0B 00 30 3F 15 0F

48 Bip01 R UpperArm 00 13 00 0C 00 00 00 00 74 13 
    00 01 00 00 00 22 00 FB 7F 01 00 00 00 A8 D5 12 
    00 08 D5 12 00 94 E6
## Post #13
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-12-21T08:05:13+00:00
- Post Title: [HELP] Get Bone and Animation for model

16 Bip01 L Forearm 8C 09 0B 00 00 00 00 00 43 00 00
00 E0 02 3B 01 E0 63 51 0E 00 00 00 00 AE 0A 07
00 E0 02 3B 01 00 00

19 Bip01 L Forearm 00 00 00 00 00
00 00 00 00 00 00 00 00 00 1C D1 12 00 00 00 00
00 64 99 F8 77 00 00 13 00 40 CF 1C 00 

In your opinion, that bytes stand for what information?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-21T19:11:23+00:00
- Post Title: [HELP] Get Bone and Animation for model

I don't have an opinion about them and it's not needed; we've the bone names and matrices; all we need is a suitable smd file for it with hierarchy such as:
Spine3 - Neck - Clavicle - Upperarm - Forearm - Hand - Finger
Pelvis - Spine - Thigh - Calf - Foot - Toe
Spine - Spine1 - Spine2 -

compare to bone names:
1 Bip01 root
3 Bip01 Head (no matrix!)
5 Bip01 Neck 
7 Bip01 L Thigh 
9 Bip01 Neck ?
11 Bip01 L Hand 
13 Bip01 L Finger0 
15 Bip01 L Calf 
17 Bip01 L UpperArm 
19 Bip01 L Forearm 
21 Bip01 Spine 
23 Bip01 L Foot 
25 Bip01 L Clavicle 
27 Bip01 Spine1 
29 Bip01 
31 Bip01 R Thigh 
33 Bip01 Neck ?
35 Bip01 R Hand 
37 Bip01 R Finger0 
39 Bip01 R Calf 
41 Bip01 R UpperArm 
43 Bip01 R Forearm 
45 Bip01 Spine ?
47 Bip01 R Foot 
49 Bip01 R Clavicle 
51 Bip01 Pelvis 
53 Bip01 Spine ?

Ignore the odd numbering; also very strange that we have "neck" and "spine" thrice, neck with different matrices; as I wrote: weird format.
## Post #15
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2018-12-28T08:43:22+00:00
- Post Title: [HELP] Get Bone and Animation for model

Here is bone data : [https://pastebin.com/E0bBwUZD](https://pastebin.com/E0bBwUZD). I saved data follow format : (‘child bone name’,‘parent bone name’, child’s matrix)

I'm trying to figure our the way to re-create armature from that data by python in blender
## Post #16
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-01-18T07:56:21+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

.........
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-18T15:05:50+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Maybe it's a problem with the null (or root) bone's translation? I had a similar problem here when the indian's legs were moved by rotation only:
[viewtopic.php?f=16&t=12979&p=107315&hil ... im#p107315](http://forum.xentax.com/viewtopic.php?f=16&t=12979&p=107315&hilit=drag+md5anim#p107315)

After fixing he proceeded correctly but I don't have the time to check the details again.

quote "So we would need the translation values/bones' positions for the initial pose, apply them once at animation startup then play rotations only."

(Well, this was easy because it were ASCII files, iirc. Would be hard to do it with binary ani files.)
## Post #18
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-01-27T14:18:03+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2
>
> Maybe it's a problem with the null (or root) bone's translation? I had a similar problem here when the indian's legs were moved by rotation only:
viewtopic.php?f=16&t=12979&p=107315&hil ... im#p107315

After fixing he proceeded correctly but I don't have the time to check the details again.

quote "So we would need the translation values/bones' positions for the initial pose, apply them once at animation startup then play rotations only."

(Well, this was easy because it were ASCII files, iirc. Would be hard to do it with binary ani files.)

Root bone is Bip01 or Scene Root?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-27T14:54:29+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

"Scene Root" obviously. This seems a little bit strange to me: we don't have any bone with Scene Root as a parent in the smd (from Noesis smd export).
It should read 14 "Bip01 Pelvis"  0, shouldn't it?

```
  0 "Scene Root"  -1
  1 "Bip01 Footsteps"  -1
  2 "Bip01 Head"  13
  3 "Bip01 L Calf"  10
  4 "Bip01 L Clavicle"  13
  5 "Bip01 L Finger0"  8
  6 "Bip01 L Foot"  9
  7 "Bip01 L Forearm"  12
  8 "Bip01 L Hand"  7
  9 "Bip01 L HorseLink"  3
  10 "Bip01 L Thigh"  26
  11 "Bip01 L Toe0"  6
  12 "Bip01 L UpperArm"  4
  13 "Bip01 Neck"  27
  14 "Bip01 Pelvis"  -1
  15 "Bip01 Ponytail1"  2
  16 "Bip01 R Calf"  23
  17 "Bip01 R Clavicle"  13
  18 "Bip01 R Finger0"  21
  19 "Bip01 R Foot"  22
  20 "Bip01 R Forearm"  25
  21 "Bip01 R Hand"  20
  22 "Bip01 R HorseLink"  16
  23 "Bip01 R Thigh"  26
  24 "Bip01 R Toe0"  19
  25 "Bip01 R UpperArm"  17
  26 "Bip01 Spine"  14
  27 "Bip01 Spine1"  26
  28 "Bip01 Tail"  26
  29 "Bip01 Tail1"  28
  30 "Bip01 Tail2"  29
end
```


In the bone.txt file created by the script it reads:
0: Bip01, p Scene Root

14: Bip01 Pelvis, p Bip01

So looks ok to me.
## Post #20
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-01-27T15:27:58+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2
>
> "Scene Root" obviously. This seems a little bit strange to me: we don't have any bone with Scene Root as a parent in the smd (from Noesis smd export).
It should read 14 "Bip01 Pelvis"  0, shouldn't it?
Code: Select allnodes
  0 "Scene Root"  -1
  1 "Bip01 Footsteps"  -1
  2 "Bip01 Head"  13
  3 "Bip01 L Calf"  10
  4 "Bip01 L Clavicle"  13
  5 "Bip01 L Finger0"  8
  6 "Bip01 L Foot"  9
  7 "Bip01 L Forearm"  12
  8 "Bip01 L Hand"  7
  9 "Bip01 L HorseLink"  3
  10 "Bip01 L Thigh"  26
  11 "Bip01 L Toe0"  6
  12 "Bip01 L UpperArm"  4
  13 "Bip01 Neck"  27
  14 "Bip01 Pelvis"  -1
  15 "Bip01 Ponytail1"  2
  16 "Bip01 R Calf"  23
  17 "Bip01 R Clavicle"  13
  18 "Bip01 R Finger0"  21
  19 "Bip01 R Foot"  22
  20 "Bip01 R Forearm"  25
  21 "Bip01 R Hand"  20
  22 "Bip01 R HorseLink"  16
  23 "Bip01 R Thigh"  26
  24 "Bip01 R Toe0"  19
  25 "Bip01 R UpperArm"  17
  26 "Bip01 Spine"  14
  27 "Bip01 Spine1"  26
  28 "Bip01 Tail"  26
  29 "Bip01 Tail1"  28
  30 "Bip01 Tail2"  29
end

In the bone.txt file created by the script it reads:
0: Bip01, p Scene Root

14: Bip01 Pelvis, p Bip01

So looks ok to me.

> 14 "Bip01 Pelvis"  -1 --> Something is wrong in code.. let me check again.It should like you wrote

 So we should remove "Scene Root"?
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-27T16:34:06+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

I wouldn't say so; in the bone.txt file Scene Root is the parent of Bip01 and Bip01 is the parent of Pelvis.
Question is why the node "Bip01" doesn't appear in the smd file.
## Post #22
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-01-28T03:50:33+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

................
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-28T06:26:28+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

The node Scene Root is missing in your bone.txt file.
Usually first node should read like so: 0 "Bip01"  -1

In the smd created by Noesis the -1 is in the last node; could work but not sure:

```
nodes
  0 "Bip01"  31
  1 "Bip01 Footsteps"  0
  2 "Bip01 Head"  13
  3 "Bip01 L Calf"  10
  4 "Bip01 L Clavicle"  13
  5 "Bip01 L Finger0"  8
  6 "Bip01 L Foot"  9
  7 "Bip01 L Forearm"  12
  8 "Bip01 L Hand"  7
  9 "Bip01 L HorseLink"  3
  10 "Bip01 L Thigh"  26
  11 "Bip01 L Toe0"  6
  12 "Bip01 L UpperArm"  4
  13 "Bip01 Neck"  27
  14 "Bip01 Pelvis"  0
  15 "Bip01 Ponytail1"  2
  16 "Bip01 R Calf"  23
  17 "Bip01 R Clavicle"  13
  18 "Bip01 R Finger0"  21
  19 "Bip01 R Foot"  22
  20 "Bip01 R Forearm"  25
  21 "Bip01 R Hand"  20
  22 "Bip01 R HorseLink"  16
  23 "Bip01 R Thigh"  26
  24 "Bip01 R Toe0"  19
  25 "Bip01 R UpperArm"  17
  26 "Bip01 Spine"  14
  27 "Bip01 Spine1"  26
  28 "Bip01 Tail"  26
  29 "Bip01 Tail1"  28
  30 "Bip01 Tail2"  29
  31 "Scene Root"  -1
end
```
## Post #24
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-01-28T07:35:29+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2
>
> The node Scene Root is missing in your bone.txt file.
Usually first node should read like so: 0 "Bip01"  -1

In the smd created by Noesis the -1 is in the last node; could work but not sure:
Code: Select allversion 1
nodes
  0 "Bip01"  31
  1 "Bip01 Footsteps"  0
  2 "Bip01 Head"  13
  3 "Bip01 L Calf"  10
  4 "Bip01 L Clavicle"  13
  5 "Bip01 L Finger0"  8
  6 "Bip01 L Foot"  9
  7 "Bip01 L Forearm"  12
  8 "Bip01 L Hand"  7
  9 "Bip01 L HorseLink"  3
  10 "Bip01 L Thigh"  26
  11 "Bip01 L Toe0"  6
  12 "Bip01 L UpperArm"  4
  13 "Bip01 Neck"  27
  14 "Bip01 Pelvis"  0
  15 "Bip01 Ponytail1"  2
  16 "Bip01 R Calf"  23
  17 "Bip01 R Clavicle"  13
  18 "Bip01 R Finger0"  21
  19 "Bip01 R Foot"  22
  20 "Bip01 R Forearm"  25
  21 "Bip01 R Hand"  20
  22 "Bip01 R HorseLink"  16
  23 "Bip01 R Thigh"  26
  24 "Bip01 R Toe0"  19
  25 "Bip01 R UpperArm"  17
  26 "Bip01 Spine"  14
  27 "Bip01 Spine1"  26
  28 "Bip01 Tail"  26
  29 "Bip01 Tail1"  28
  30 "Bip01 Tail2"  29
  31 "Scene Root"  -1
end

So I should remove Scene Root out bone list and make Bip01 has parent index is -1?
## Post #25
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-03-16T07:05:19+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

I re-post full script here.Currently  the script can parse SKIN, BON and Animation but the animation still not right (rotation is good but the translation is fail..the mesh can move forward but floating little up and down)

```
from os.path import *
from math import *
from inc_noesis import *

MAIN_BON_FILE_NAME = ""
ROOT_DIR = ""
FILE_BON_PATH = ""

ROOT_DIR = dirname(dirname(dirname(abspath(__file__))))
FILE_BON_PATH = ROOT_DIR + "\\YulgangVN\\Bones\\"

MESH_LIST = []
BONE_LIST = []
ANI_LIST = []
# registerNoesisTypes is called by Noesis to allow the script to register formats.
# Do not implement this function in script files unless you want them to be dedicated format modules!


def registerNoesisTypes():
    handle = noesis.register("YulgangVN - SKIN", ".skin;.bon;.ani")
    noesis.setHandlerTypeCheck(handle, checkSkinType)
    noesis.setHandlerLoadModel(handle, checkSkinLoad)
    # noesis.setHandlerWriteModel(handle, noepyWriteModel)
    # noesis.setHandlerWriteAnim(handle, noepyWriteAnim)

    noesis.logPopup()
    # print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
    return 1


# check if it's this type based on the data
def checkSkinType(data):
    if len(data) < 16:
        return 0

    return 1


# load the model
def checkSkinLoad(data, mdlList):
    global MESH_LIST
    global BONE_LIST
    global ANI_LIST
    ctx = rapi.rpgCreateContext()
    filePath = rapi.getInputName()   # get file path
    fileExt = filePath.split('.')[-1]  # get file extesion

    boneData = rapi.loadPairedFile("YulgangVN - BON", ".bon")
    aniData = rapi.loadPairedFile("YulgangVN - Ani", ".ani")

    # create parser
    yulgangParser = YulgangParser(data, boneData, aniData, fileExt)

    MESH_LIST = yulgangParser.parseSkin()
    BONE_LIST = yulgangParser.parseBon()
    ANI_LIST = yulgangParser.parseAni()

    mdl = NoeModel(MESH_LIST, BONE_LIST, ANI_LIST)
    # important, don't forget to put your loaded model in the mdlList
    mdlList.append(mdl)

    return 1


def normalize(v, tolerance=0.0001):
    mag2 = sum(n * n for n in v)
    # print(mag2)
    if mag2 != 0.0:
        if abs(mag2 - 1.0) > tolerance:
            mag = sqrt(mag2)
            v = tuple(n / mag for n in v)
    return v


def axisangle_to_q(v, theta):
    v = normalize(v)
    x, y, z = v
    theta /= 2
    w = cos(theta)
    x = x * sin(theta)
    y = y * sin(theta)
    z = z * sin(theta)
    return x, y, z, w


class YulgangParser(object):
    def __init__(self, skinData, boneData, aniData, fileExt=""):
        self.skinStream = NoeBitStream(skinData)
        self.bonStream = NoeBitStream(boneData)
        self.aniStream = NoeBitStream(aniData)
        self.fileExt = fileExt
        self.bones = {}  # new
        return

    def parseBon(self):
        global BONE_LIST
        if self.bonStream is None:
            print('Data stream is null')

        # MAIN_BON_FILE_NAME = filePath.split('\\')[4]

        # boneFile = open(FILE_BON_PATH + 'bone' + ".txt", "w")
        boneNameList = []  # create arrray to contain all bone name

        boneCount = self.bonStream.readInt()  # read bone count
        print('Bone Count: ' + str(boneCount))

        noeBones = []
        for i in range(boneCount):
            currentOffset = self.bonStream.tell()  # get current offset

            boneName = self.bonStream.readString()  # read current bone name
            boneNameList.append(boneName)

            self.bonStream.seek(currentOffset + 50,
                                NOESEEK_ABS)  # seek 50 bytes

            bonePName = self.bonStream.readString()  # read parent bone name
            self.bonStream.seek(currentOffset + 100,
                                NOESEEK_ABS)  # seek 50 bytes

            boneMatrix = NoeMat44.fromBytes(
                self.bonStream.readBytes(64)).toMat43()

            # create NoeBone
            noeBone = NoeBone(len(noeBones), boneName,
                              boneMatrix, bonePName, -1)

            # new - it creat dict bonename==> index
            self.bones[boneName] = noeBone
            noeBones.append(noeBone)

        # check if bone doesnt have info from birnary file, create empty infor for it
        # e.x: Scene Root
        for noeBone in noeBones:
            if noeBone.parentName not in boneNameList:
                parentBone = NoeBone(
                    len(noeBones), noeBone.parentName, NoeMat43(), "", -1)
                self.bones[parentBone.name] = parentBone
                noeBones.append(parentBone)  # add to main list
                break

        # calculate bone parent index
        for bone in noeBones:
            if bone.parentName in self.bones:
                bone.parentIndex = self.bones[bone.parentName].index
                # boneFile.write(str(bone.index) + "::" + bone.name + "::" +
                #                bone.parentName + "::" + str(bone.parentIndex) + "\n")  # write to file

        # print("Write file " + 'bone' + ".txt success!")
        # boneFile.close()  # close file

        return noeBones

    def parseSkin(self):
        if self.skinStream is None:
            print('Data stream is null')
        elif self.fileExt != 'skin':
            print('Selected file is not Skin format')

        self.skinStream.readUByte()    # number of mesh in file

        vertexCount = self.skinStream.readInt()
        indicesCount = self.skinStream.readInt() * 3
        weightCount = self.skinStream.readInt()
        materialCount = self.skinStream.readInt()

        vertPostList = []
        indiceList = []
        weights = []
        vertUVList = []
        skinIdList = []
        matList = []
        skinWeightList = []
        skinIndiceList = []

        self.skinStream.readBytes(6 * 4)  # unknow
        self.skinStream.readBytes(16 * 4)  # unknow
        self.skinStream.readBytes(16 * 4)  # unknow

        for i in range(vertexCount):
            curOffset = self.skinStream.tell()
            vertPostList.append(NoeVec3.fromBytes(
                self.skinStream.readBytes(12)))

            if weightCount == 1:
                seekOffset = curOffset + 36
                bwgt = [1.0]
                bidx = [self.skinStream.read("B")]
                self.skinStream.readUByte()
                self.skinStream.readUByte()
                self.skinStream.readUByte()
                self.skinStream.readBytes(4 * 3)
                uv = NoeVec3()
                uv.vec3 = self.skinStream.read("ff")+(0,)
                vertUVList.append(uv)
            elif weightCount == 2:
                seekOffset = curOffset + 40
                w1 = self.skinStream.readFloat()
                w2 = 1.0 - w1
                bwgt = [w1, w2]
                bidx = self.skinStream.read("BB")
                self.skinStream.readUByte()
                self.skinStream.readUByte()
                self.skinStream.readBytes(4 * 3)
                uv = NoeVec3()
                uv.vec3 = self.skinStream.read("ff")+(0,)
                vertUVList.append(uv)
            elif weightCount == 3:
                seekOffset = curOffset + 44
                w1 = self.skinStream.readFloat()
                w2 = self.skinStream.readFloat()
                w3 = 1.0 - w1 - w2
                bwgt = [w1, w2, w3]
                bidx = self.skinStream.read("BBB")
                # print(bidx)
                self.skinStream.readUByte()
                self.skinStream.read("fff")
                uv = NoeVec3()
                uv.vec3 = self.skinStream.read("ff")+(0,)
                vertUVList.append(uv)
            elif weightCount == 4:
                seekOffset = curOffset + 48
                w1 = self.skinStream.readFloat()
                w2 = self.skinStream.readFloat()
                w3 = self.skinStream.readFloat()
                w4 = 1.0 - w1 - w2 - w3
                bwgt = [w1, w2, w3, w4]
                bidx = self.skinStream.read("BBBB")
                self.skinStream.read("fff")
                uv = NoeVec3()
                uv.vec3 = self.skinStream.read("ff")+(0,)
                vertUVList.append(uv)
            # weights.append(NoeVertWeight(bidx, bwgt))
            self.skinStream.seek(seekOffset, NOESEEK_ABS)
            skinWeightList.append(bwgt)
            skinIndiceList.append(bidx)

        # read indiceList
        for i in range(indicesCount):
            indiceList.append(self.skinStream.readShort())

        # read matertial list
        meshList = []
        new = open("log.txt", 'w')  # outside Noesis log file
        for i in range(materialCount):
            weights = []
            new.write(str(i)+"\n")
            mat = NoeMaterial("", "")
            matList.append(mat)

            self.skinStream.readInt()
            matIDStart = self.skinStream.readInt() * 3
            matIDCount = self.skinStream.readInt() * 3
            self.skinStream.readInt()
            self.skinStream.readInt()
            boneMap = self.skinStream.read("28i")
            # print(boneMap)

            mesh = NoeMesh(indiceList[matIDStart:matIDStart+matIDCount], vertPostList, str(i).zfill(2))
            mesh.uvs = vertUVList

            # procedure to get correct vertex bone index
            newSkinIndiceList = []
            for i in range(vertexCount):
                newSkinIndiceList.append(skinIndiceList[i])
            for idx in indiceList[matIDStart:matIDStart+matIDCount]:
                bidx = skinIndiceList[idx]
                bwgt = skinWeightList[idx]
                newbidx = []
                new.write(str(idx)+str(bidx)+str(bwgt)+'\n')
                for m in range(len(bidx)):
                    newbidx.append(boneMap[bidx[m]])
                newSkinIndiceList[idx] = newbidx

            for i in range(vertexCount):
                weights.append(NoeVertWeight(
                    newSkinIndiceList[i], skinWeightList[i]))
            mesh.weights = weights
            meshList.append(mesh)
        new.close()

        return meshList

    def parseAni(self):
        global BONE_LIST
        if self.aniStream is None:
            print('Ani stream is null')
            return 0
        if len(BONE_LIST) == 0:
            print('Bone List is empty.Please parse BON first')
            return 0
        print("bones:", len(self.bones))

        animList = []
        noeKeyFramedBones = []
        self.aniStream.seek(512, NOESEEK_ABS)  # ignore 512 bytes

        boneCount = self.aniStream.readUByte()   # get bone count
        curBone = NoeBone(0, "", NoeMat43())

        for i in range(boneCount):
            currentOffset = self.aniStream.tell()

            name = self.aniStream.readString()  # read bone name
            curBone = self.bones[name]  # get bone by name

            self.aniStream.seek(currentOffset + 50, NOESEEK_ABS)  # seek 50 bytes
            # get bone pose matrix
            matrix44 = NoeMat44.fromBytes(self.aniStream.readBytes(64))  # .inverse()
            # print(matrix44)
            matrix43 = matrix44.toMat43()
            # print(matrix43)

            quatFromMatrix = matrix43.toQuat()
            transFromMatrix = matrix43[2]

            posNoeKeyFramedValues = []   # array contain list translation
            translateFrameCount = self.aniStream.readInt()
            for j in range(translateFrameCount):
                time = self.aniStream.readInt() / 320.0
                xp = self.aniStream.readFloat()
                yp = self.aniStream.readFloat()
                zp = self.aniStream.readFloat()
                if time > 0:  # ignroe frame 0
                    vector = NoeVec3((xp, yp, zp))
                    transMatrix = transFromMatrix.__mul__(vector)
                    # print(transMatrix)
                    posKeyFrameValue = NoeKeyFramedValue(time, vector)  # create instance
                    posNoeKeyFramedValues.append(posKeyFrameValue)   # add to list

            rotNoeKeyFramedValues = []   # array contain list rotation
            rotateFrameCount = self.aniStream.readInt()
            for j in range(rotateFrameCount):
                rotTime = self.aniStream.readInt() / 320.0
                v = self.aniStream.read("3f")  # read vector
                angle = self.aniStream.read("f")[0]  # read angle
                # convert vector + angle to QUAT
                if rotTime > 0:  # ignore frame 0
                    quat = axisangle_to_q(v, angle)
                    rotMatrix = NoeQuat()
                    rotMatrix.quat = quat
                    rotMatrix = quatFromMatrix.__mul__(rotMatrix)
                    rotKeyFrameValue = NoeKeyFramedValue(
                        rotTime, rotMatrix)  # create instance
                    rotNoeKeyFramedValues.append(
                        rotKeyFrameValue)   # add to list

            # create NoeKeyFramedBone
            if len(self.bones) > 0:
                actionBone = NoeKeyFramedBone(self.bones[name].index)
            else:
                actionBone = NoeKeyFramedBone(curBone.index)

            actionBone.setRotation(rotNoeKeyFramedValues,
                                   noesis.NOEKF_ROTATION_QUATERNION_4)
            actionBone.setTranslation(
                posNoeKeyFramedValues, noesis.NOEKF_TRANSLATION_VECTOR_3)

            # add to keyframedBones list
            noeKeyFramedBones.append(actionBone)

        # create NoeKeyFramedAnim
        anim = NoeKeyFramedAnim(
            "Animation 1", BONE_LIST, noeKeyFramedBones, 10)

        # add to animList
        animList.append(anim)
        return animList

```

Sample data: 

 Data.7z
(65.67 KiB) Downloaded 29 times

 ( A Monster Cat in game)
Sample data 2: [https://1drv.ms/u/s!AtK3xgihMkhwhI5X4qoASMisva14PQ](https://1drv.ms/u/s!AtK3xgihMkhwhI5X4qoASMisva14PQ) (Blacksmith)
Blacksmith's IDLE animation demo: [https://www.youtube.com/watch?v=AEAQaz0KKWo](https://www.youtube.com/watch?v=AEAQaz0KKWo)

Current problem is the translation animation (Mesh floating up and down a little)
## Post #26
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-03-26T08:29:43+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Up for help !!!!!
## Post #27
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-05-13T10:03:15+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Up for help ....
## Post #28
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-05-25T20:02:54+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Up for help
## Post #29
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-08-14T10:07:13+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Up for helppppppp........
## Post #30
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-10-24T10:07:58+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Up for help
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-25T09:27:12+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

All Scene root frames are zero:
31 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000

That's why the cat doesn't move forwards, I guess.
## Post #32
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-10-28T15:19:21+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Fri Oct 25, 2019 5:27 pm at Fri Oct 25, 2019 5:27 pm
>
> 
All Scene root frames are zero:
31 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000

That's why the cat doesn't move forwards, I guess.

Where you get this?
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-28T16:55:15+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

From Animation 1_mainsequence.smd, exported by Noesis, I guess, but not sure.
## Post #34
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-12-18T17:01:28+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

I stuck on this problem many months.. so sad
## Post #35
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2019-12-19T09:56:29+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Fri Oct 25, 2019 5:27 pm at Fri Oct 25, 2019 5:27 pm
>
> 
All Scene root frames are zero:
31 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000

That's why the cat doesn't move forwards, I guess.

@Shakotay2: so what is casual value for scene root frame?
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-19T15:52:10+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from tainhx ↑Thu Dec 19, 2019 5:56 pm at Thu Dec 19, 2019 5:56 pm
>
> 
@Shakotay2: so what is casual value for scene root frame?I dunno. The referred quote "All Scene root frames are zero:" only explains why there's no translational moving.

There should be an increment of the x values for example per frame to see the cat moving.
You simply could create such data and look whether it does the trick.
## Post #37
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-01T16:18:48+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Thu Dec 19, 2019 11:52 pm at Thu Dec 19, 2019 11:52 pm
>
> 
tainhx wrote: ↑Thu Dec 19, 2019 5:56 pm
@Shakotay2: so what is casual value for scene root frame?
I dunno. The referred quote "All Scene root frames are zero:" only explains why there's no translational moving.

There should be an increment of the x values for example per frame to see the cat moving.
You simply could create such data and look whether it does the trick.

i dont know..that is all data for animation which I can get from binary file game

I posted all my code .. And did you read it ?

I can post all data about animation and skeleton hierarchy... and could we make a review ?
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-01T17:31:05+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from tainhx ↑Thu Jan 02, 2020 12:18 am at Thu Jan 02, 2020 12:18 am
>
> I posted all my code .. And did you read it ?I didn't read any line in this thread.
## Post #39
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-03T16:15:17+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Bone Info

> -------------------------------- Bone 1 -------------------------------
>
> Bip01 00 00 4D 01 00 00 03 02 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Scene Root 61 74 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 1.370907E-06	-1	0	0
>
> 0	0	1	0
>
> 1	1.370907E-06	0	0
>
> 3.624069E-07	0	2.850418	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 2 -------------------------------
>
> Bip01 Footsteps 28 00 00 00 00 00 00 00 00 EC FD 7F 28 00 2A 00 77 C2 F8 77 70 F1 FC 77 38 1C F9 77 1E 1C F9 77 08 02
>
> Bip01 D0 21 13 00 00 00 00 00 00 00 00 00 00 02 C9 00 38 5A F4 0E 01 E1 12 00 14 00 00 00 00 02 C9 00 18 6F E4 0E 68 6E C3 0C 18 6F E4 0E
>
> 1	0	0	0
>
> 0	0	1	0
>
> 0	1	0	0
>
> 3.624069E-07	0	-0.00222373	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 3 -------------------------------
>
> Bip01 Head 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Neck 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 8.440163E-07	-0.61566	0.7880119	0
>
> 1	-8.147209E-07	-1.707598E-06	0
>
> -1.693309E-06	-0.7880119	-0.61566	0
>
> 6.545762E-06	-3.051524	3.343692	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 4 -------------------------------
>
> Bip01 L Calf 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 88 01 C9 00 00 2B E7 0E 00 00 00 00 00 00 00 00 88 01 C9 00 00 00
>
> Bip01 L Thigh 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -7.811306E-08	0.5946214	-0.8040059	0
>
> -0.9999999	5.564973E-07	5.087255E-07	0
>
> -7.49926E-07	-0.8040059	-0.5946214	0
>
> 0.4917081	1.653781	1.569878	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 5 -------------------------------
>
> Bip01 L Clavicle 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Neck 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 0.9800663	0.1959461	-0.03278989	0
>
> 0.1986707	-0.9666253	0.1617576	0
>
> -2.34949E-07	0.1650476	0.9862856	0
>
> 0.1417526	-1.673021	2.894331	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 6 -------------------------------
>
> Bip01 L Finger0 01 96 F8 77 FF FF FF FF E0 CD 12 00 74 D3 12 00 A8 CE 12 00 91 81 F9 77 01 00 00 00 82 00 00 00 00 00
>
> Bip01 L Hand 77 E0 06 9C 00 00 00 00 00 00 00 00 00 02 00 00 00 90 DF 1F 00 CC CF 12 00 22 42 DE 77 48 09 56 00 82 00 00 00
>
> 6.543621E-06	-1	5.671332E-06	0
>
> 0.9999996	6.496234E-06	-0.0007996252	0
>
> -0.0007995992	-5.612343E-06	-0.9999997	0
>
> 0.6778374	-2.295426	0.2234462	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 7 -------------------------------
>
> Bip01 L Foot 41 72 6D 00 00 13 00 0C 00 00 00 01 72 13 00 F0 04 C9 00 90 1C 01 0F 01 00 00 00 A8 D5 12 00 F0 04 C9 00 94 E6
>
> Bip01 L HorseLink E0 D5 12 00 0D C2 E6 77 00 00 13 00 00 00 00 00 F0 0A 33 0F 00 00 FF FF F0 0A 33 0F 18 D6 C3 0C
>
> 8.171241E-14	-1.589326E-08	-0.9999999	0
>
> -1	-1.370907E-06	-5.992424E-14	0
>
> 1.370907E-06	-0.9999999	1.589326E-08	0
>
> 0.4917076	1.75989	0.3414732	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 8 -------------------------------
>
> Bip01 L Forearm 68 07 15 00 00 00 00 00 43 00 00 00 82 00 00 00 7B 62 DF 77 00 00 00 00 0E 08 48 00 82 00 00 00 00 00
>
> Bip01 L UpperArm 77 68 07 15 00 82 00 00 00 00 00 00 00 00 00 00 00 01 00 00 00 A8 2C DE 77 68 07 15 00 82 00 00 00
>
> 0.004034618	-0.1710232	-0.9852587	0
>
> 0.9999248	-0.01071311	0.005954279	0
>
> 0.0115735	0.9852087	-0.1709672	0
>
> 0.6733064	-1.623927	1.329131	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 9 -------------------------------
>
> Bip01 L Hand D0 12 00 01 01 01 01 F8 D0 12 00 91 81 F9 77 50 96 F8 77 FF FF FF FF 08 D1 12 00 0D C2 E6 77 00 00 13 00 00 00
>
> Bip01 L Forearm 90 00 28 F1 9E 00 02 00 00 00 82 00 00 00 1C D1 12 00 00 00 00 00 64 99 F8 77 00 00 13 00 20 14 21 00
>
> 6.543621E-06	-1	5.671332E-06	0
>
> 1	6.500701E-06	-3.307184E-06	0
>
> -3.28127E-06	-5.607168E-06	-1	0
>
> 0.6778342	-1.815854	0.2234434	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 10 -------------------------------
>
> Bip01 L HorseLink 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 L Calf 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -7.187159E-07	-0.499614	-0.8662482	0
>
> -0.9999999	5.564973E-07	5.087255E-07	0
>
> -2.278982E-07	-0.8662482	0.499614	0
>
> 0.4917081	2.111459	0.9510366	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 11 -------------------------------
>
> Bip01 L Thigh 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Spine 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -5.38122E-07	-0.05416617	-0.9985319	0
>
> -0.9999999	5.564973E-07	5.087255E-07	0
>
> -5.281244E-07	-0.9985319	0.05416617	0
>
> 0.4917088	1.723245	2.850418	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 12 -------------------------------
>
> Bip01 L Toe0 72 6D 00 68 07 15 00 00 00 00 00 43 00 00 00 82 00 00 00 7B 62 DF 77 00 00 00 00 0E 08 48 00 82 00 00 00 00 00
>
> Bip01 L Foot 41 72 6D 00 77 68 07 15 00 82 00 00 00 00 00 00 00 00 00 00 00 01 00 00 00 A8 2C DE 77 68 07 15 00 82 00 00 00
>
> 1.370907E-06	-0.9999999	-4.371138E-08	0
>
> -1	-1.370907E-06	-5.992424E-14	0
>
> -1.905824E-21	-4.371138E-08	0.9999999	0
>
> 0.4917082	1.3246	-0.002223626	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 13 -------------------------------
>
> Bip01 L UpperArm 00 13 00 0C 00 00 00 01 72 13 00 F0 04 C9 00 90 1C 01 0F 01 00 00 00 A8 D5 12 00 F0 04 C9 00 94 E6
>
> Bip01 L Clavicle FF E0 D5 12 00 0D C2 E6 77 00 00 13 00 00 00 00 00 F0 0A 33 0F 00 00 FF FF F0 0A 33 0F 18 D6 C3 0C
>
> 0.005567177	-0.03580741	-0.9993432	0
>
> 0.9999248	-0.01071311	0.005954279	0
>
> 0.01091928	0.9993013	-0.03574508	0
>
> 0.6646844	-1.568471	2.876835	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 14 -------------------------------
>
> Bip01 Neck 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 88 01 C9 00 00 2B E7 0E 00 00 00 00 00 00 00 00 88 01 C9 00 00 00
>
> Bip01 Spine1 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 1.254946E-06	-0.9154132	0.4025154	0
>
> 1	2.544899E-07	-2.53899E-06	0
>
> -2.221789E-06	-0.4025154	-0.9154132	0
>
> 5.448519E-06	-2.251147	2.99176	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 15 -------------------------------
>
> Bip01 Pelvis 70 73 00 28 00 00 00 00 00 00 00 00 EC FD 7F 28 00 2A 00 77 C2 F8 77 70 F1 FC 77 38 1C F9 77 1E 1C F9 77 08 02
>
> Bip01 D0 21 13 00 00 00 00 00 00 00 00 00 00 02 C9 00 38 5A F4 0E 01 E1 12 00 14 00 00 00 00 02 C9 00 18 6F E4 0E 68 6E C3 0C 18 6F E4 0E
>
> -1.3868E-06	-3.824388E-12	1	0
>
> 1	2.757707E-06	1.3868E-06	0
>
> 2.757707E-06	-1	0	0
>
> 0	1.723244	2.850418	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 16 -------------------------------
>
> Bip01 Ponytail1 00 00 13 00 0C 00 00 00 01 72 13 00 01 00 00 00 E8 0A 33 0F 01 00 00 00 A8 D5 12 00 08 D5 12 00 94 E6
>
> Bip01 Head 96 F8 77 FF FF FF FF E0 D5 12 00 0D C2 E6 77 00 00 13 00 00 00 00 00 F0 0A 33 0F 00 00 FF FF F0 0A 33 0F C6 C1 E6 77
>
> 1.303953E-06	-0.951161	-0.3086953	0
>
> 1	2.227104E-06	-2.63814E-06	0
>
> -3.196793E-06	0.3086953	-0.951161	0
>
> 3.359732E-06	-3.64527	2.981094	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 17 -------------------------------
>
> Bip01 R Calf 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 88 01 C9 00 00 2B E7 0E 00 00 00 00 00 00 00 00 88 01 C9 00 00 00
>
> Bip01 R Thigh 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -1.656195E-06	0.5946214	-0.8040059	0
>
> -0.9999999	-3.473156E-06	-5.087256E-07	0
>
> 3.094937E-06	-0.8040059	-0.5946214	0
>
> -0.4917079	1.653779	1.569878	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 18 -------------------------------
>
> Bip01 R Clavicle 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Neck 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -0.9800669	0.1959434	-0.03278989	0
>
> 0.198668	0.9666259	-0.1617576	0
>
> -2.175808E-07	0.1650476	0.9862856	0
>
> -0.1417433	-1.673022	2.894331	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 19 -------------------------------
>
> Bip01 R Finger0 01 96 F8 77 FF FF FF FF E0 CD 12 00 74 D3 12 00 A8 CE 12 00 91 81 F9 77 01 00 00 00 82 00 00 00 00 00
>
> Bip01 R Hand 77 E0 06 9C 00 18 02 C9 00 88 C5 4A 1A 02 00 00 00 90 DF 1F 00 18 02 C9 00 22 42 DE 77 48 09 56 00 60 CE C4 0C
>
> -3.627694E-06	-1	5.671332E-06	0
>
> 0.9999997	-3.580425E-06	0.0007996252	0
>
> 0.0007995994	-5.60733E-06	-0.9999997	0
>
> -0.6778262	-2.295428	0.2234462	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 20 -------------------------------
>
> Bip01 R Foot 41 72 6D 00 00 13 00 0C 00 00 00 01 72 13 00 F0 04 C9 00 90 1C 01 0F 01 00 00 00 A8 D5 12 00 F0 04 C9 00 94 E6
>
> Bip01 R HorseLink E0 D5 12 00 0D C2 E6 77 00 00 13 00 00 00 00 00 F0 0A 33 0F 00 00 FF FF F0 0A 33 0F 18 D6 C3 0C
>
> 8.171241E-14	-1.589326E-08	-0.9999999	0
>
> -1	-1.370907E-06	-5.992424E-14	0
>
> 1.370907E-06	-0.9999999	1.589326E-08	0
>
> -0.4917077	1.759888	0.3414732	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 21 -------------------------------
>
> Bip01 R Forearm 68 07 15 00 00 00 00 00 43 00 00 00 82 00 00 00 7B 62 DF 77 00 00 00 00 0E 08 48 00 82 00 00 00 00 00
>
> Bip01 R UpperArm 77 68 07 15 00 82 00 00 00 00 00 00 00 00 00 00 00 01 00 00 00 A8 2C DE 77 68 07 15 00 82 00 00 00
>
> -0.004034119	-0.1710232	-0.9852587	0
>
> 0.9999248	0.01071603	-0.005954279	0
>
> -0.01157638	0.9852087	-0.1709672	0
>
> -0.6732972	-1.623928	1.329131	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 22 -------------------------------
>
> Bip01 R Hand D0 12 00 01 01 01 01 F8 D0 12 00 91 81 F9 77 50 96 F8 77 FF FF FF FF 08 D1 12 00 0D C2 E6 77 00 00 13 00 00 00
>
> Bip01 R Forearm 90 00 28 F1 9E 00 02 00 00 00 82 00 00 00 1C D1 12 00 00 00 00 00 64 99 F8 77 00 00 13 00 20 14 21 00
>
> -3.627694E-06	-1	5.671332E-06	0
>
> 1	-3.584889E-06	3.307184E-06	0
>
> 3.281398E-06	-5.604478E-06	-1	0
>
> -0.6778244	-1.815856	0.2234434	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 23 -------------------------------
>
> Bip01 R HorseLink 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 R Calf 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 2.17592E-06	-0.499614	-0.8662482	0
>
> -0.9999999	-3.473156E-06	-5.087256E-07	0
>
> 2.754449E-06	-0.8662482	0.499614	0
>
> -0.4917092	2.111458	0.9510366	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 24 -------------------------------
>
> Bip01 R Thigh 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Spine 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 6.961064E-07	-0.05416617	-0.9985319	0
>
> -0.9999999	-3.473156E-06	-5.087256E-07	0
>
> 3.440502E-06	-0.9985319	0.05416617	0
>
> -0.4917088	1.723243	2.850418	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 25 -------------------------------
>
> Bip01 R Toe0 72 6D 00 68 07 15 00 00 00 00 00 43 00 00 00 82 00 00 00 7B 62 DF 77 00 00 00 00 0E 08 48 00 82 00 00 00 00 00
>
> Bip01 R Foot 41 72 6D 00 77 68 07 15 00 82 00 00 00 00 00 00 00 00 00 00 00 01 00 00 00 A8 2C DE 77 68 07 15 00 82 00 00 00
>
> 1.370907E-06	-0.9999999	1.589326E-08	0
>
> -1	-1.370907E-06	-5.992424E-14	0
>
> -8.171241E-14	1.589326E-08	0.9999999	0
>
> -0.4917071	1.324598	-0.002223626	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 26 -------------------------------
>
> Bip01 R UpperArm 00 13 00 0C 00 00 00 01 72 13 00 F0 04 C9 00 90 1C 01 0F 01 00 00 00 A8 D5 12 00 F0 04 C9 00 94 E6
>
> Bip01 R Clavicle FF E0 D5 12 00 0D C2 E6 77 00 00 13 00 00 00 00 00 F0 0A 33 0F 00 00 FF FF F0 0A 33 0F 18 D6 C3 0C
>
> -0.005567072	-0.03580742	-0.9993432	0
>
> 0.9999248	0.01071603	-0.005954279	0
>
> -0.0109222	0.9993013	-0.03574508	0
>
> -0.6646754	-1.568473	2.876835	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 27 -------------------------------
>
> Bip01 Spine 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Pelvis 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 1.370864E-06	-0.9999686	0.007929914	0
>
> 1	1.348912E-06	-2.773513E-06	0
>
> -2.762729E-06	-0.007929914	-0.9999686	0
>
> 4.849001E-07	1.369536	2.614913	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 28 -------------------------------
>
> Bip01 Spine1 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Spine 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> 1.352285E-06	-0.9864168	0.1642621	0
>
> 1	9.153093E-07	-2.735926E-06	0
>
> -2.548412E-06	-0.1642621	-0.9864168	0
>
> 2.460135E-06	-0.07128753	2.628077	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 29 -------------------------------
>
> Bip01 Tail 67 68 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Spine 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -1.370907E-06	0.9999999	-0.0003370483	0
>
> 1	1.371842E-06	2.7736E-06	0
>
> -2.774062E-06	0.0003370483	0.9999999	0
>
> 4.260239E-07	2.035062	3.242873	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 30 -------------------------------
>
> Bip01 Tail1 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 88 01 C9 00 00 2B E7 0E 00 00 00 00 00 00 00 00 88 01 C9 00 00 00
>
> Bip01 Tail 67 68 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -1.370871E-06	0.9999737	0.007256305	0
>
> 1	1.350781E-06	2.773527E-06	0
>
> -2.763653E-06	-0.007256305	0.9999737	0
>
> -1.672849E-06	3.566073	3.241094	1
>
> --------------------------------------------------------------------------------------------------------------------------------
>
> -------------------------------- Bone 31 -------------------------------
>
> Bip01 Tail2 65 4C 69 6E 6B 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> Bip01 Tail1 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
>
> -1.370902E-06	0.9999965	-0.002603509	0
>
> 1	1.378128E-06	2.773591E-06	0
>
> -2.77717E-06	0.002603509	0.9999965	0
>
> -3.846943E-06	5.151954	3.251362	1
>
> --------------------------------------------------------------------------------------------------------------------------------

Skeleton Heirarchy



Capture.PNG (92.02 KiB) Viewed 106 times



Animation data

> Animation Count: 31
>
>  ********************************** BONE 1 ******************************************
>
> Bip01
>
> 1.45183E-06	-0.9998477	-0.01745247	0
>
> 6.053597E-08	-0.01745247	0.9998477	0
>
> 1	1.452667E-06	-3.539026E-08	0
>
> 3.624069E-07	-0.05070901	2.66307	1
>
> Frame Translate: 10
>
> Translate List:
>
> 1. 0  3.624069E-07   2.66307   -0.05070901
>
> 2. 640  3.624069E-07   2.648846   -0.05070901
>
> 3. 1280  3.624069E-07   2.632629   -0.05070901
>
> 4. 1920  3.624069E-07   2.619311   -0.05070901
>
> 5. 2560  3.624069E-07   2.613785   -0.05070901
>
> 6. 3200  3.624069E-07   2.617333   -0.05070901
>
> 7. 3840  3.624069E-07   2.626402   -0.05070901
>
> 8. 4480  3.624069E-07   2.638625   -0.05070901
>
> 9. 5120  3.624069E-07   2.651636   -0.05070901
>
> 10. 5760  3.624069E-07   2.66307   -0.05070901
>
> Frame Rotation: 1
>
> Rotation List:
>
> 1. 0  -0.008726218  0.9999238   -0.008726266   1.570871
>
> 
>
>  ********************************** BONE 2 ******************************************
>
> Bip01 Footsteps
>
> 1.451828E-06	1	6.073749E-08	0
>
> -0.01745247	-3.518872E-08	0.9998477	0
>
> -0.9998477	1.452665E-06	-0.01745247	0
>
> 0.04623166	9.321506E-08	-2.6486	1
>
> Frame Translate: 10
>
> Translate List:
>
> 1. 0  0.04623166   -2.6486   9.321506E-08
>
> 2. 640  0.04598343   -2.634379   9.271454E-08
>
> 3. 1280  0.0457004   -2.618164   9.214387E-08
>
> 4. 1920  0.04546796   -2.604848   9.167521E-08
>
> 5. 2560  0.04537151   -2.599322   9.148075E-08
>
> 6. 3200  0.04543345   -2.60287   8.889759E-08
>
> 7. 3840  0.04559171   -2.611937   8.920725E-08
>
> 8. 4480  0.04580504   -2.624159   8.962466E-08
>
> 9. 5120  0.04603212   -2.637168   9.006898E-08
>
> 10. 5760  0.04623167   -2.648601   9.045944E-08
>
> Frame Rotation: 1
>
> Rotation List:
>
> 1. 0  0.008726218  -0.9999238   0.008726266   1.570871
>
> 
>
>  ********************************** BONE 3 ******************************************
>
> Bip01 Pelvis
>
> -1.925507E-12	-1.3868E-06	1	0
>
> -1.3868E-06	1	1.3868E-06	0
>
> 1	1.3868E-06	1.724113E-13	0
>
> -1.723244	2E-06	2.799595E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 0
>
> Rotation List:
>
> 
>
>  ********************************** BONE 4 ******************************************
>
> Bip01 Spine
>
> -0.04441527	0.9990131	-1.447027E-06	0
>
> -4.157663E-06	1.26361E-06	1	0
>
> -0.9990131	-0.04441527	-4.097436E-06	0
>
> -0.2355066	0.3537677	-8.172055E-07	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 1
>
> Rotation List:
>
> 1. 0  2.683171E-06  -1   1.356657E-06   1.615226
>
> 
>
>  ********************************** BONE 5 ******************************************
>
> Bip01 Spine1
>
> 0.9271838	-0.3746069	-1.03901E-06	0
>
> 1.03901E-06	-2.019631E-07	1	0
>
> 0.3746069	0.9271838	-2.019632E-07	0
>
> 1.440499	-0.001631484	-4.525521E-09	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  5.690307E-14  1   -2.7736E-06   0.3839728
>
> 2. 640  -0.3456554  0.5546737   -0.7568747   0.009080651
>
> 3. 1280  -0.3456565  0.5546701   -0.7568769   0.01035307
>
> 4. 1920  -0.345656  0.5546713   -0.7568763   0.008502242
>
> 5. 2560  -0.3456569  0.5546699   -0.7568769   0.003528142
>
> 6. 3200  0.3456554  -0.5546749   0.7568739   0.002265423
>
> 7. 3840  0.3456564  -0.5546702   0.7568769   0.005789387
>
> 8. 4480  0.3456549  -0.5546752   0.7568739   0.007803127
>
> 9. 5120  0.3456568  -0.554669   0.7568776   0.008306507
>
> 10. 5760  0.3456575  -0.5546663   0.7568793   0.007299643
>
> 
>
>  ********************************** BONE 6 ******************************************
>
> Bip01 Neck
>
> 0.9869089	-0.1612792	-4.47324E-07	0
>
> 4.47324E-07	-3.630987E-08	1	0
>
> 0.1612792	0.9869089	-3.630962E-08	0
>
> 2.210049	-0.0006870193	-1.90648E-09	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -7.599779E-13  1   -2.7736E-06   0.1619867
>
> 2. 640  0.162065  2.109053E-06   0.9867801   0.006265775
>
> 3. 1280  0.162065  5.4725E-06   0.9867801   0.006581069
>
> 4. 1920  0.162065  1.756438E-06   0.9867801   0.005593653
>
> 5. 2560  0.1620651  1.623913E-06   0.98678   0.005121449
>
> 6. 3200  0.162065  1.224284E-06   0.9867801   0.003648406
>
> 7. 3840  -0.1620649  -1.941606E-05   -0.9867801   0.001341847
>
> 8. 4480  -0.162065  -3.831219E-06   -0.9867801   0.006905876
>
> 9. 5120  -0.162065  -5.378721E-06   -0.9867801   0.00960401
>
> 10. 5760  -0.162065  1.86846E-06   -0.9867801   0.009358624
>
> 
>
>  ********************************** BONE 7 ******************************************
>
> Bip01 Head
>
> 0.8592761	-0.5115121	-1.418726E-06	0
>
> 1.418727E-06	-3.903095E-07	1	0
>
> 0.511512	0.8592762	-3.903116E-07	0
>
> 0.874334	2.527846E-07	7.382141E-13	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  2.02809E-12  1   -2.773593E-06   0.5369436
>
> 2. 640  -0.06431516  0.8096707   -0.5833496   0.02857856
>
> 3. 1280  -0.06830952  0.8145825   -0.5760115   0.02902718
>
> 4. 1920  -0.08869461  0.8396956   -0.5357653   0.01112027
>
> 5. 2560  0.05578259  -0.7956843   0.6031374   0.02366891
>
> 6. 3200  0.06684335  -0.8130272   0.5783759   0.03862155
>
> 7. 3840  0.07866909  -0.8282249   0.5548465   0.0198306
>
> 8. 4480  0.3649832  0.08849335   -0.9267989   0.0007318474
>
> 9. 5120  -0.04965315  0.7976821   -0.6010306   0.007232628
>
> 10. 5760  -0.08308719  0.824241   -0.56011   0.005737165
>
> 
>
>  ********************************** BONE 8 ******************************************
>
> Bip01 Ponytail1
>
> 0.3423362	0.9395775	2.606011E-06	0
>
> -2.606009E-06	-1.824096E-06	1	0
>
> -0.9395776	0.3423362	-1.824093E-06	0
>
> 0.07981364	0.6911161	-2.08312E-06	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -1.875466E-12  -1   2.773598E-06   1.221394
>
> 2. 640  -2.653782E-08  1   -2.761065E-06   0.03022237
>
> 3. 1280  9.71844E-09  1   -2.816696E-06   0.03445731
>
> 4. 1920  7.11042E-08  1   -2.714643E-06   0.02829744
>
> 5. 2560  -1.495493E-07  1   -2.83047E-06   0.01174246
>
> 6. 3200  2.916836E-08  -1   2.786282E-06   0.007539657
>
> 7. 3840  3.01599E-09  -1   2.760739E-06   0.01926847
>
> 8. 4480  -1.854555E-11  -1   2.780847E-06   0.02597043
>
> 9. 5120  9.423722E-09  -1   2.767924E-06   0.02764602
>
> 10. 5760  -1.359097E-08  -1   2.782019E-06   0.02429497
>
> 
>
>  ********************************** BONE 9 ******************************************
>
> Bip01 L Clavicle
>
> -0.2747411	0.4517935	0.8487638	0
>
> 0.9514194	0.2553406	0.1720534	0
>
> 0.1389913	-0.8548004	0.4999976	0
>
> -0.5788462	-0.09342528	0.1417477	1
>
> Frame Translate: 9
>
> Translate List:
>
> 1. 0  -0.5788462   0.1417477   -0.09342528
>
> 2. 640  -0.5779466   0.1453714   -0.09342608
>
> 3. 1280  -0.5769771   0.1491712   -0.09342668
>
> 4. 1920  -0.576134   0.1523958   -0.09342731
>
> 5. 2560  -0.5753461   0.1553441   -0.09342818
>
> 6. 3200  -0.5747754   0.1574419   -0.09342852
>
> 7. 4480  -0.5760544   0.1526966   -0.0934275
>
> 8. 5120  -0.5774943   0.1471579   -0.09342637
>
> 9. 5760  -0.5788462   0.1417477   -0.09342528
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.5964752  -0.7626138   -0.2502749   2.935041
>
> 2. 640  -0.0007998433  3.290661E-06   -0.9999997   0.006265779
>
> 3. 1280  -0.0007987684  -1.016166E-05   -0.9999997   0.006581058
>
> 4. 1920  -0.0007955282  4.570086E-07   -0.9999997   0.00559367
>
> 5. 2560  -0.0007899824  -5.221582E-06   -0.9999997   0.005121445
>
> 6. 3200  -0.0007868338  -1.122689E-05   -0.9999997   0.003648352
>
> 7. 3840  0.0007463604  6.404069E-05   0.9999997   0.001341789
>
> 8. 4480  0.0007997563  3.440178E-06   0.9999997   0.00690586
>
> 9. 5120  0.0008008118  5.578278E-06   0.9999997   0.009603964
>
> 10. 5760  0.0007904914  -8.360107E-07   0.9999997   0.009358642
>
> 
>
>  ********************************** BONE 10 ******************************************
>
> Bip01 L UpperArm
>
> 0.6131918	-0.7430818	-0.2680024	0
>
> 0.7899128	0.5743208	0.2149259	0
>
> 0.005788148	0.3434894	-0.9391387	0
>
> 0.5335677	1.427327E-08	2.083012E-07	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  0.7595309  0.375821   -0.5309156   1.484887
>
> 2. 640  -0.2433313  -0.4210749   -0.8737768   0.01281292
>
> 3. 1280  -0.238594  -0.4232301   -0.8740419   0.01448992
>
> 4. 1920  -0.2340637  -0.4254387   -0.8741946   0.01180767
>
> 5. 2560  -0.231196  -0.4268815   -0.8742543   0.004875731
>
> 6. 3200  0.2308793  0.427077   0.8742425   0.003129233
>
> 7. 3840  0.2327982  0.4260604   0.8742297   0.008022764
>
> 8. 4480  0.2360742  0.4244492   0.874135   0.01087395
>
> 9. 5120  0.2399259  0.4225948   0.8739847   0.01165262
>
> 10. 5760  0.2437824  0.4208827   0.8737436   0.01030786
>
> 
>
>  ********************************** BONE 11 ******************************************
>
> Bip01 L Forearm
>
> 0.687974	-0.7257352	1.559638E-09	0
>
> -2.024574E-09	-5.996064E-10	1	0
>
> 0.7257352	0.687974	-1.302647E-11	0
>
> 1.548721	1.19766E-07	-1.009195E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -4.573127E-10  1   1.930955E-09   0.8121026
>
> 2. 640  5.882974E-08  1   2.875517E-07   0.008642265
>
> 3. 1280  -2.474027E-07  1   -9.621894E-08   0.009564091
>
> 4. 1920  -1.248055E-06  1   -1.605607E-06   0.007629496
>
> 5. 2560  2.708627E-06  1   4.967202E-06   0.003107781
>
> 6. 3200  3.210306E-06  -1   -1.443885E-06   0.001992088
>
> 7. 3840  4.759734E-07  -1   7.933272E-07   0.005152637
>
> 8. 4480  -2.966786E-07  -1   3.299052E-07   0.007092589
>
> 9. 5120  -6.724381E-07  -1   -2.165011E-06   0.007739286
>
> 10. 5760  3.874513E-07  -1   1.218081E-06   0.006966964
>
> 
>
>  ********************************** BONE 12 ******************************************
>
> Bip01 L Hand
>
> 0.7068989	-0.7073098	-0.002615004	0
>
> 0.09105354	0.08733314	0.9920092	0
>
> 0.7014294	0.7014883	-0.1261388	0
>
> 1.122231	-2.003141E-07	-3.877077E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  0.1495009  0.9865831   -0.06559895   0.7951213
>
> 2. 640  0.3431955  -0.6652383   -0.6630799   0.006419006
>
> 3. 1280  0.3520766  -0.6535838   -0.6699778   0.007280521
>
> 4. 1920  0.3604773  -0.6424348   -0.6762645   0.005952051
>
> 5. 2560  0.3655353  -0.6355208   -0.6800715   0.002463328
>
> 6. 3200  -0.3660118  0.6348333   0.6804572   0.001581596
>
> 7. 3840  -0.3627471  0.6393135   0.6780065   0.004047814
>
> 8. 4480  -0.3567753  0.6472889   0.6735937   0.005472889
>
> 9. 5120  -0.3495412  0.6569242   0.6680355   0.005849582
>
> 10. 5760  -0.3423708  0.6663134   0.6624265   0.005163033
>
> 
>
>  ********************************** BONE 13 ******************************************
>
> Bip01 L Finger0
>
> 0.9999999	6.077447E-10	8.066993E-10	0
>
> 3.730353E-10	0.0007963177	0.9999996	0
>
> 1.998609E-09	0.9999996	-0.0007963179	0
>
> 0.4795723	-5.964147E-09	-1.155862E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 0
>
> Rotation List:
>
> 
>
>  ********************************** BONE 14 ******************************************
>
> Bip01 R Clavicle
>
> -0.2747411	0.4517982	-0.8487613	0
>
> -0.9514194	-0.2553416	0.172052	0
>
> 0.1389913	-0.8547976	-0.5000024	0
>
> -0.5788461	-0.09342445	-0.1417482	1
>
> Frame Translate: 9
>
> Translate List:
>
> 1. 0  -0.5788461   -0.1417482   -0.09342445
>
> 2. 640  -0.5797229   -0.138119   -0.09342381
>
> 3. 1280  -0.5806191   -0.1343014   -0.09342296
>
> 4. 1920  -0.5813614   -0.1310519   -0.09342247
>
> 5. 2560  -0.5820251   -0.1280732   -0.09342201
>
> 6. 3200  -0.5824885   -0.1259491   -0.09342152
>
> 7. 4480  -0.5814299   -0.1307484   -0.09342258
>
> 8. 5120  -0.5801474   -0.1363256   -0.09342343
>
> 9. 5760  -0.5788462   -0.1417482   -0.09342452
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  0.5964751  -0.7626132   0.250277   2.935038
>
> 2. 640  -0.0007983608  1.181752E-05   -0.9999997   0.006265733
>
> 3. 1280  -0.000790579  -1.182813E-05   -0.9999997   0.006581034
>
> 4. 1920  -0.0008033478  -1.544131E-06   -0.9999997   0.005593689
>
> 5. 2560  -0.000791734  -3.76213E-06   -0.9999997   0.005121439
>
> 6. 3200  -0.0008010631  -1.791004E-05   -0.9999997   0.003648458
>
> 7. 3840  0.0008041436  3.425193E-05   0.9999997   0.001341879
>
> 8. 4480  0.0007957829  8.544976E-06   0.9999997   0.006905894
>
> 9. 5120  0.0007975028  5.949047E-06   0.9999997   0.009603981
>
> 10. 5760  0.0007943593  -8.230833E-06   0.9999997   0.00935848
>
> 
>
>  ********************************** BONE 15 ******************************************
>
> Bip01 R UpperArm
>
> 0.4999248	-0.5485936	0.6701643	0
>
> -0.8278854	-0.5299349	0.1837781	0
>
> -0.254324	0.6466947	0.7191004	0
>
> 0.5335677	5.970529E-08	6.820166E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.6332179  0.1491845   0.7594597   1.404837
>
> 2. 640  0.9935731  0.09572489   0.06040846   0.01218692
>
> 3. 1280  0.9936831  0.09834518   0.05405639   0.01374157
>
> 4. 1920  0.9937251  0.101014   0.0480269   0.0111681
>
> 5. 2560  0.9937212  0.1027663   0.04423977   0.004604526
>
> 6. 3200  -0.9937142  -0.1029635   -0.04393783   0.002955035
>
> 7. 3840  -0.9937248  -0.1017925   -0.04636148   0.00758278
>
> 8. 4480  -0.9937153  -0.0998008   -0.05069288   0.01029689
>
> 9. 5120  -0.993658  -0.09759637   -0.05584526   0.01105959
>
> 10. 5760  -0.9935609  -0.09546103   -0.06102436   0.00980717
>
> 
>
>  ********************************** BONE 16 ******************************************
>
> Bip01 R Forearm
>
> 0.6548741	-0.755738	1.27227E-10	0
>
> 1.240266E-09	8.655961E-10	1	0
>
> 0.755738	0.6548741	4.540326E-10	0
>
> 1.548721	6.470347E-08	-2.288577E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  5.671782E-10  1   -2.794112E-10   0.8567803
>
> 2. 640  1.175516E-08  1   1.245755E-07   0.01732829
>
> 3. 1280  -5.053637E-08  1   -1.776785E-07   0.01941984
>
> 4. 1920  -1.673241E-07  1   -1.89445E-08   0.01569151
>
> 5. 2560  3.58467E-07  1   1.588369E-07   0.006447416
>
> 6. 3200  1.316066E-07  -1   4.729277E-07   0.004136311
>
> 7. 3840  -1.363796E-07  -1   -1.952639E-07   0.01063758
>
> 8. 4480  1.418646E-07  -1   2.885182E-07   0.0145045
>
> 9. 5120  6.925009E-08  -1   -2.86273E-07   0.01565598
>
> 10. 5760  -1.946858E-07  -1   6.33604E-08   0.01395312
>
> 
>
>  ********************************** BONE 17 ******************************************
>
> Bip01 R Hand
>
> 0.2504919	-0.9676894	0.02882865	0
>
> -0.05018355	0.0167592	0.9985994	0
>
> 0.9668173	0.2515877	0.04436405	0
>
> 1.122231	4.07914E-08	8.372139E-09	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.01425637  0.9990654   0.04080542   1.317765
>
> 2. 640  0.1724403  -0.9344629   -0.311518   0.01275285
>
> 3. 1280  0.1775665  -0.9326909   -0.3139393   0.01443885
>
> 4. 1920  0.1824369  -0.9310067   -0.316138   0.01178355
>
> 5. 2560  0.1855123  -0.9299558   -0.3174389   0.004872783
>
> 6. 3200  -0.1857703  0.9298774   0.3175175   0.003128011
>
> 7. 3840  -0.1838151  0.9305326   0.3167351   0.008010807
>
> 8. 4480  -0.1802873  0.9317464   0.3151906   0.0108442
>
> 9. 5120  -0.1761202  0.9331868   0.3132797   0.01160617
>
> 10. 5760  -0.1719503  0.9346396   0.3112586   0.01025902
>
> 
>
>  ********************************** BONE 18 ******************************************
>
> Bip01 R Finger0
>
> 1	8.951365E-10	-2.188301E-09	0
>
> 1.856555E-11	-0.0007963179	0.9999997	0
>
> 5.243725E-09	0.9999996	0.0007963181	0
>
> 0.4795724	7.50864E-10	-1.090206E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 0
>
> Rotation List:
>
> 
>
>  ********************************** BONE 19 ******************************************
>
> Bip01 L Thigh
>
> 0.1430508	0.9653637	0.2181964	0
>
> 0.1506191	0.1966615	-0.9688334	0
>
> 0.9781873	-0.171457	0.1172696	0
>
> -0.3638786	-0.2195628	0.4917082	1
>
> Frame Translate: 1
>
> Translate List:
>
> 1. 0  -0.3638786   0.4917082   -0.2195628
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.7557973  -0.1220798   -0.643325   3.194139
>
> 2. 640  -0.219655  0.9584754   -0.18187   0.01708614
>
> 3. 1280  -0.2270002  0.9568666   -0.1813206   0.01785949
>
> 4. 1920  -0.2340055  0.9552793   -0.1807842   0.01361876
>
> 5. 2560  -0.238442  0.9542474   -0.1804369   0.005411031
>
> 6. 3200  0.2388788  -0.9541448   0.1804012   0.003459585
>
> 7. 3840  0.2359527  -0.9548287   0.1806338   0.009095638
>
> 8. 4480  0.2309376  -0.9559813   0.1810183   0.01289902
>
> 9. 5120  0.2249214  -0.9573295   0.1814682   0.01467044
>
> 10. 5760  0.2190014  -0.9586171   0.1819113   0.01384966
>
> 
>
>  ********************************** BONE 20 ******************************************
>
> Bip01 L Calf
>
> 0.8384945	-0.54491	-1.306229E-08	0
>
> 6.775474E-09	-8.511768E-10	1	0
>
> 0.54491	0.8384947	-1.236447E-08	0
>
> 1.282423	7.734184E-08	-2.50123E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  8.139591E-09  1   -2.003678E-08   0.5762817
>
> 2. 640  1.064398E-07  1   3.737192E-07   0.04880033
>
> 3. 1280  -1.437645E-07  1   -2.564566E-07   0.05149461
>
> 4. 1920  -4.249406E-08  1   2.117961E-07   0.03963289
>
> 5. 2560  -1.154636E-06  1   -1.187356E-06   0.01584165
>
> 6. 3200  -1.271177E-06  -1   1.566388E-06   0.01013461
>
> 7. 3840  8.79382E-07  -1   -5.630685E-07   0.02653844
>
> 8. 4480  1.210309E-07  -1   3.791953E-07   0.0373855
>
> 9. 5120  2.450592E-07  -1   2.800871E-07   0.04218484
>
> 10. 5760  -2.56334E-07  -1   -3.685051E-07   0.03952339
>
> 
>
>  ********************************** BONE 21 ******************************************
>
> Bip01 L HorseLink
>
> 0.181782	0.9833389	-5.000456E-08	0
>
> 7.874319E-09	7.408261E-09	1	0
>
> -0.983339	0.1817819	4.394995E-09	0
>
> 0.7696977	-2.578061E-08	-3.70856E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  1.14379E-08  -1   -2.03406E-08   1.387998
>
> 2. 640  -9.447918E-07  -1   2.235986E-07   0.03175716
>
> 3. 1280  8.534516E-07  -1   -3.901138E-08   0.03369329
>
> 4. 1920  -2.741051E-07  -1   3.699058E-07   0.02606485
>
> 5. 2560  -1.895829E-07  -1   2.459154E-06   0.0104541
>
> 6. 3200  3.981388E-06  1   -1.785256E-06   0.006689739
>
> 7. 3840  -2.823547E-06  1   -2.43359E-07   0.0174803
>
> 8. 4480  4.005588E-07  1   -5.767693E-07   0.02453233
>
> 9. 5120  -1.598826E-06  1   -2.121612E-07   0.02755801
>
> 10. 5760  9.668382E-07  1   5.156308E-07   0.02570818
>
> 
>
>  ********************************** BONE 22 ******************************************
>
> Bip01 L Foot
>
> 0.5889726	-0.7815632	0.2055966	0
>
> -0.2352475	0.0775812	0.9688342	0
>
> 0.7731557	0.618983	0.1381677	0
>
> 0.7036819	2.271313E-08	-3.684285E-09	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.03746501  0.961396   0.272606   0.941724
>
> 2. 640  0.6983897  -0.0004052874   0.7157176   0.001218435
>
> 3. 1280  0.6970609  0.001869043   0.7170094   0.001406323
>
> 4. 1920  0.6957139  0.0003294488   0.7183189   0.001168835
>
> 5. 2560  0.694912  0.002694115   0.7190897   0.000488725
>
> 6. 3200  -0.6946695  -0.001481567   -0.7193274   0.0003140219
>
> 7. 3840  -0.6953083  -0.002767335   -0.7187063   0.0007985223
>
> 8. 4480  -0.6962517  -0.001562622   -0.717796   0.00106714
>
> 9. 5120  -0.6973335  -0.0004872872   -0.7167466   0.001124374
>
> 10. 5760  -0.6985145  0.0002871121   -0.7155959   0.0009784789
>
> 
>
>  ********************************** BONE 23 ******************************************
>
> Bip01 L Toe0
>
> 5.960479E-08	0.9999999	-1.085499E-13	0
>
> -4.733058E-15	-1.390874E-14	1	0
>
> -0.9999999	5.960473E-08	1.836224E-14	0
>
> 0.3436968	0.4352901	-8.153917E-09	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 0
>
> Rotation List:
>
> 
>
>  ********************************** BONE 24 ******************************************
>
> Bip01 R Thigh
>
> -0.04199011	0.9819898	-0.1842094	0
>
> -0.1424794	-0.1883731	-0.9717073	0
>
> 0.9889067	0.01455605	-0.1478231	0
>
> -0.3638786	-0.2195601	-0.4917094	1
>
> Frame Translate: 1
>
> Translate List:
>
> 1. 0  -0.3638786   -0.4917094   -0.2195601
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.692021  0.1180452   -0.7121603   3.11229
>
> 2. 640  0.2116626  0.9586785   0.1900905   0.01717769
>
> 3. 1280  0.2203144  0.9571785   0.1878055   0.01757687
>
> 4. 1920  0.2286733  0.9555842   0.1859228   0.01317262
>
> 5. 2560  0.2338458  0.9552442   0.1811754   0.005184278
>
> 6. 3200  -0.2352868  -0.9516887   -0.1973036   0.003308422
>
> 7. 3840  -0.2313516  -0.9540794   -0.1902863   0.008757004
>
> 8. 4480  -0.2251625  -0.9560321   -0.1878947   0.01256701
>
> 9. 5120  -0.2178312  -0.958087   -0.1860615   0.01452048
>
> 10. 5760  -0.210623  -0.9600453   -0.1842579   0.01395843
>
> 
>
>  ********************************** BONE 25 ******************************************
>
> Bip01 R Calf
>
> 0.8682674	-0.4960964	6.304719E-09	0
>
> -7.570897E-09	-4.565812E-09	1	0
>
> 0.4960963	0.8682675	7.025935E-10	0
>
> 1.282423	-3.621814E-09	9.317525E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -5.276664E-09  1   1.209787E-08   0.5190971
>
> 2. 640  4.906583E-07  1   -3.465329E-07   0.05198397
>
> 3. 1280  -4.382247E-07  1   -2.328364E-07   0.05413757
>
> 4. 1920  4.204748E-07  1   6.454445E-07   0.04126811
>
> 5. 2560  7.027636E-08  1   -1.683582E-07   0.01641732
>
> 6. 3200  -3.426457E-07  -1   1.614862E-06   0.01049042
>
> 7. 3840  3.197301E-08  -1   -9.217557E-07   0.02756615
>
> 8. 4480  -2.581969E-07  -1   -1.998851E-07   0.0390781
>
> 9. 5120  -2.385953E-08  -1   -3.332794E-07   0.04449896
>
> 10. 5760  -6.008842E-08  -1   8.165575E-07   0.04217182
>
> 
>
>  ********************************** BONE 26 ******************************************
>
> Bip01 R HorseLink
>
> 0.05283966	0.998603	2.312996E-09	0
>
> -7.854309E-09	1.078791E-08	1	0
>
> -0.998603	0.05283967	-2.153073E-08	0
>
> 0.7696978	-2.788576E-08	-6.820436E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  9.903816E-09  -1   5.365584E-09   1.517932
>
> 2. 640  -4.544536E-07  -1   -4.763003E-07   0.03485529
>
> 3. 1280  -3.901599E-07  -1   1.869895E-08   0.03662284
>
> 4. 1920  -3.271947E-07  -1   -7.612464E-07   0.02814915
>
> 5. 2560  3.230873E-06  -1   1.933809E-06   0.01125624
>
> 6. 3200  -1.271613E-06  1   -2.428094E-06   0.007201014
>
> 7. 3840  9.442173E-07  1   1.16734E-06   0.01884981
>
> 8. 4480  -7.54342E-07  1   -5.420844E-07   0.02655969
>
> 9. 5120  -1.670734E-08  1   3.254315E-07   0.03002444
>
> 10. 5760  2.121121E-07  1   -2.961787E-07   0.0282483
>
> 
>
>  ********************************** BONE 27 ******************************************
>
> Bip01 R Foot
>
> 0.4494099	-0.8767739	-0.1711673	0
>
> 0.2240085	-0.07487982	0.9717064	0
>
> 0.8647837	0.4750373	-0.1627531	0
>
> 0.7036821	4.610988E-08	2.368978E-08	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  0.04914641  0.9740309   -0.2210168   1.106183
>
> 2. 640  -0.8452355  0.005481902   -0.534366   0.001208887
>
> 3. 1280  -0.8193501  0.005013166   -0.5732716   0.001391405
>
> 4. 1920  -0.8003164  0.002426793   -0.599573   0.001155469
>
> 5. 2560  -0.765369  0.001295536   -0.6435904   0.0004835825
>
> 6. 3200  0.8655315  -0.0136814   0.5006676   0.0003135804
>
> 7. 3840  0.8279313  -0.006247103   0.5607948   0.0007912657
>
> 8. 4480  0.8165905  -0.003718041   0.5772054   0.001055611
>
> 9. 5120  0.8080392  -0.002952306   0.5891213   0.001111124
>
> 10. 5760  0.797478  -0.001548999   0.603346   0.0009661423
>
> 
>
>  ********************************** BONE 28 ******************************************
>
> Bip01 R Toe0
>
> -0.1736481	0.9848078	-2.763339E-07	0
>
> -1.258233E-07	2.584108E-07	1	0
>
> -0.9848078	-0.1736481	-7.903918E-08	0
>
> 0.3436968	0.4352901	9.260922E-10	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 1
>
> Rotation List:
>
> 1. 0  1.713278E-07  -1   -7.641624E-08   1.745329
>
> 
>
>  ********************************** BONE 29 ******************************************
>
> Bip01 Tail
>
> -0.9225666	0.3833648	-0.04361829	0
>
> -0.04026782	0.01676482	0.9990483	0
>
> -0.3837312	-0.9234449	2.940122E-05	0
>
> -0.6924073	-0.5978718	-8.276898E-07	1
>
> Frame Translate: 1
>
> Translate List:
>
> 1. 0  -0.6924073   -8.276898E-07   -0.5978718
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  0.02181119  -0.9997526   -0.00436666   2.747855
>
> 2. 640  0.5293524  0.10237   0.8422033   0.1418574
>
> 3. 1280  0.3796259  -0.06301847   0.9229912   0.1105638
>
> 4. 1920  -0.7568464  -0.6519799   -0.04588776   0.1995273
>
> 5. 2560  -0.7335796  -0.6102812   -0.2990282   0.3188646
>
> 6. 3200  0.556802  -0.2852211   -0.7801413   0.1587288
>
> 7. 3840  0.7955385  0.1679956   -0.5821477   0.2121692
>
> 8. 4480  -0.3198673  0.6218182   -0.7148615   0.1116873
>
> 9. 5120  0.4068806  0.6805212   0.6093759   0.1238502
>
> 10. 5760  0.4699453  0.4635224   0.7511979   0.1973363
>
> 
>
>  ********************************** BONE 30 ******************************************
>
> Bip01 Tail1
>
> 0.9348993	0.2936245	0.1993687	0
>
> -0.1902568	-0.05958419	0.9799246	0
>
> -0.299609	0.9540621	-0.0001588251	0
>
> 1.53138	-0.001204666	1.020616E-07	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.08343614  -0.8329291   0.5470534   0.3641047
>
> 2. 640  -0.298865  3.49047E-06   0.9542954   0.1542682
>
> 3. 1280  -0.2988655  1.51981E-06   0.9542952   0.03089448
>
> 4. 1920  0.298865  -2.902202E-06   -0.9542954   0.1994559
>
> 5. 2560  0.2988648  -2.245528E-06   -0.9542955   0.2316584
>
> 6. 3200  0.2988651  -2.683966E-06   -0.9542954   0.2089157
>
> 7. 3840  0.2988649  -2.696397E-06   -0.9542954   0.06914907
>
> 8. 4480  -0.2988647  2.986135E-06   0.9542955   0.1331287
>
> 9. 5120  -0.298865  2.288576E-06   0.9542954   0.1828748
>
> 10. 5760  -0.298865  2.30708E-06   0.9542954   0.2080128
>
> 
>
>  ********************************** BONE 31 ******************************************
>
> Bip01 Tail2
>
> 0.8109493	0.5560135	0.182237	0
>
> -0.1503856	-0.1029298	0.9832546	0
>
> -0.5654606	0.8247755	-0.0001455502	0
>
> 1.586627	-0.001023646	1.590222E-07	1
>
> Frame Translate: 0
>
> Translate List:
>
> Frame Rotation: 10
>
> Rotation List:
>
> 1. 0  -0.08753043  -0.9550406   0.2832594   0.627514
>
> 2. 640  -0.564815  1.859881E-06   0.8252175   0.1912026
>
> 3. 1280  0.5648178  -2.219141E-05   -0.8252156   0.008587314
>
> 4. 1920  0.5648152  -2.183546E-06   -0.8252174   0.2193935
>
> 5. 2560  0.5648149  -1.232943E-06   -0.8252176   0.1257552
>
> 6. 3200  0.5648154  -2.048349E-06   -0.8252173   0.1793897
>
> 7. 3840  0.5648151  -2.361465E-06   -0.8252175   0.2305405
>
> 8. 4480  -0.5648152  6.561819E-06   0.8252174   0.08160017
>
> 9. 5120  -0.5648149  2.166461E-06   0.8252176   0.2131138
>
> 10. 5760  -0.564815  1.728419E-06   0.8252176   0.2777495
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-03T17:23:51+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

I don't see any new info. Why not try out what I proposed?

> Reply from shakotay2 ↑Thu Dec 19, 2019 11:52 pm at Thu Dec 19, 2019 11:52 pm
>
> 
.


 Horse-Animation 1_mainsequence - fake.zip
(121.32 KiB) Downloaded 19 times


Drag 'n drop it onto the Noesis 3D viewer window.
Translation (bone "Scene Root", movement in z direction, -0.05 per frame) needs to be adjusted to the bone rotation, of course.
(Dunno, why the horse is lame - the cat's bones (the four legs) moved more fluently, iirc. But I can't find the smd.)
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-04T10:49:51+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

well, here's that cat again. Translation is not perfect but - surprise - "Scene Root" pos/rot is zero in each frame.


 cat-Animation 1_mainsequence.zip
(58.54 KiB) Downloaded 21 times


(I know this is the result from ages ago so the solution might be too simple as that we could see it.)

Still don't know whom the basic Noesis Yulgang script is from. Demonsangel? finale00?
## Post #42
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-04T15:46:46+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Mr Szkaradek123 helped write almost script...He created function convert angle rotation
## Post #43
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-04T15:51:43+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Sat Jan 04, 2020 1:23 am at Sat Jan 04, 2020 1:23 am
>
> 
I don't see any new info. Why not try out what I proposed?
shakotay2 wrote: ↑Thu Dec 19, 2019 11:52 pm
.
Horse-Animation 1_mainsequence - fake.zip
Drag 'n drop it onto the Noesis 3D viewer window.
Translation (bone "Scene Root", movement in z direction, -0.05 per frame) needs to be adjusted to the bone rotation, of course.
(Dunno, why the horse is lame - the cat's bones (the four legs) moved more fluently, iirc. But I can't find the smd.)

Could you export animation data for this horse? So I can compare it with my cat
## Post #44
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-04T15:54:26+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Sat Jan 04, 2020 6:49 pm at Sat Jan 04, 2020 6:49 pm
>
> 
well, here's that cat again. Translation is not perfect but - surprise - "Scene Root" pos/rot is zero in each frame.
cat-Animation 1_mainsequence.zip
(I know this is the result from ages ago so the solution might be too simple as that we could see it.)

Still don't know whom the basic Noesis Yulgang script is from. Demonsangel? finale00?

So my problem here is lack of Scene Root animation data for each frame?...But that is all data I can get from  game file by reading by Hex Workshop..No info about Scene Root .. it just appear once time in  *.BON file..
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-04T21:43:39+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from tainhx ↑Sat Jan 04, 2020 11:51 pm at Sat Jan 04, 2020 11:51 pm
>
> Could you export animation data for this horse? So I can compare it with my catWhy not do it yourself?


 ScionOfFate-Data.7z
(65.67 KiB) Downloaded 26 times



> Reply from tainhx ↑Sat Jan 04, 2020 11:54 pm at Sat Jan 04, 2020 11:54 pm
>
> So my problem here is lack of Scene Root animation data for each frame?
No. The cat moves although Scene Root data is zero. The problem lies elsewhere.

Comparing cat and horse animations is a good idea.
## Post #46
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-07T15:29:00+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Sun Jan 05, 2020 5:43 am at Sun Jan 05, 2020 5:43 am
>
> 
tainhx wrote: ↑Sat Jan 04, 2020 11:51 pmCould you export animation data for this horse? So I can compare it with my cat
Why not do it yourself?
ScionOfFate-Data.7z
tainhx wrote: ↑Sat Jan 04, 2020 11:54 pmSo my problem here is lack of Scene Root animation data for each frame?
No. The cat moves although Scene Root data is zero. The problem lies elsewhere.

Comparing cat and horse animations is a good idea.

I don't understand data structure of *.smd file so I can't extract it like what I did which *.bon
## Post #47
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-07T16:17:31+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from tainhx ↑Tue Jan 07, 2020 11:29 pm at Tue Jan 07, 2020 11:29 pm
>
> I don't understand data structure of *.smd fileIt doesn't really matter - smd was just for visualization and more clear for me (all data from bon and ani in ONE file, except the mesh).
I know I'm not always as clear as I should be so here's my question concerning cat-Animation 1_mainsequence.smd:

the cat in there is moving correctly (more or less), like you wish?
"Yes" or "no"? If "no" I fear I can't help any further.

If "yes" then have a look at the two named bones: "Scene Root" is not moving (other than for the horse, iirc).
Bone "Bip01 Footsteps" seems to be the base for the translational moving of the cat, I'd say.
.



cat_moving.png (21.91 KiB) Viewed 138 times


The first three values (after the bone number, 0..31) in the smd time block are the position, 3 euler angles (rotation, in radians) to follow.

```
  0 0.000000 2.711911 -0.653285 -0.000000 1.570796 -0.000000
  1 0.000000 -2.656473 0.000000 -0.000000 -1.570796 -0.000000
```


"Bip01 Footsteps", frame 0
  1 0.000000 -2.656473 0.000000 -0.000000 -1.570796 -0.000000
frame 1
  1 0.000000 -2.653497 0.000000 -0.000000 -1.570796 -0.000000
...
frame 80
  1 0.000000 -2.530534 -0.000000 -0.000000 -1.570796 -0.000000
...
frame 139
  1 0.000000 -2.602156 0.000000 -0.000000 -1.570796 -0.000000

So this (-2.656473...-2.602156) makes the cat moving in y direction (plus trans/rot of other bones).

So now simply look what's different with the not correctly moving animals.
## Post #48
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-09T15:48:04+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> the cat in there is moving correctly (more or less)?
Yes..The cat is moving correctly but less..It not like in game
Here is video for cat moving in game : [https://1drv.ms/v/s!AtK3xgihMkhwhIlYcViI-obfPDo8hg](https://1drv.ms/v/s!AtK3xgihMkhwhIlYcViI-obfPDo8hg)

Could you try with anothe sample is Blacksmith
Sample data 2: [https://1drv.ms/u/s!AtK3xgihMkhwhI5X4qoASMisva14PQ](https://1drv.ms/u/s!AtK3xgihMkhwhI5X4qoASMisva14PQ) (Blacksmith)
Blacksmith's IDLE animation demo: [https://www.youtube.com/watch?v=AEAQaz0KKWo](https://www.youtube.com/watch?v=AEAQaz0KKWo)

You can see the lower body of Blacksmith in demo absoluty is static..but in nosesis it is waving a little
## Post #49
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-09T18:17:05+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from tainhx ↑Thu Jan 09, 2020 11:48 pm at Thu Jan 09, 2020 11:48 pm
>
> You can see the lower body of Blacksmith in demo absoluty is static..but in nosesis it is waving a littleI'd really recommend to "hold the line"; what about comparing cat and horse animation data?  

(For the Blacksmith I dunno; doesn't look like rounding errors   - you could set [Right/Left thigh, calf , foot, Toe0] framelines to fixed values to cure it.)
## Post #50
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-01-10T15:49:37+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from shakotay2 ↑Fri Jan 10, 2020 2:17 am at Fri Jan 10, 2020 2:17 am
>
> 
tainhx wrote: ↑Thu Jan 09, 2020 11:48 pmYou can see the lower body of Blacksmith in demo absoluty is static..but in nosesis it is waving a littleI'd really recommend to "hold the line"; what about comparing cat and horse animation data?  

(For the Blacksmith I dunno; doesn't look like rounding errors   - you could set [Right/Left thigh, calf , foot, Toe0] framelines to fixed values to cure it.)

"hold the line" ?
## Post #51
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-10T16:21:50+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

What I demanded was to focus on the files we were talking about, not switch to other problems/files.
(Seems I can't help you any further, sorry.)
## Post #52
- Username: tainhx
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Jun 26, 2018 5:03 pm
- Post datetime: 2020-11-23T10:36:48+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

Up for helping ...
## Post #53
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-12-29T02:10:49+00:00
- Post Title: Re: [HELP] Get Bone and Animation for model

> Reply from tainhx ↑Sat Mar 16, 2019 3:05 pm at Sat Mar 16, 2019 3:05 pm
>
> 
Noesis Python model import+export test module, imports/exports some data from/to a made-up format
Hello tainhx! would you mind in edit the script a bit, to we can switch off, load the bones and animations? because the files have no names, and takes time to find which bone/anim correspond to the mesh and the script throw error and error many times. Thank you!
