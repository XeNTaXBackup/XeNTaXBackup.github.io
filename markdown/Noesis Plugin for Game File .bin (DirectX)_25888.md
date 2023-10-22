## Post #1
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-09T15:26:23+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

Good Day,
i hope i am not in wrong section for postng this
,
theres an old game from my disk which i want to load in noesis
,
but , the file is somewhat not readable by noesis.
, it is originally an .X file (DirectX file) .
is there a way or is there someone who can help me, 
make this .bin file to load in noesis,
i provided the  the raw file (.x file) and the game converted file (.bin)  in attachment.
.
how to make it load in noesis ?
## Post #2
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-10-09T17:29:48+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Sun Oct 09, 2022 11:26 pm at Sun Oct 09, 2022 11:26 pm
>
> 
Good Day,
i hope i am not in wrong section for postng this
,
theres an old game from my disk which i want to load in noesis
,
but , the file is somewhat not readable by noesis.
, it is originally an .X file (DirectX file) .
is there a way or is there someone who can help me, 
make this .bin file to load in noesis,
i provided the  the raw file (.x file) and the game converted file (.bin)  in attachment.
.
how to make it load in noesis ?
I used a program called "FragMOTION" to load your .x file [http://www.fragmosoft.com/](http://www.fragmosoft.com/)
[image_2022-10-09_132854121.png](https://xentaxbackup.github.io/file/22891_image_2022-10-09_132854121.png)
## Post #3
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-09T17:32:54+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

thanks for the reply
but
fragmotion only import .X file
the one we need to import
Is the game file which is .bin this is the game file 
,
.bin file came from .x ,
but sadly no tool i saw from internet that can open .BIN (game file)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-09T22:24:08+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Mon Oct 10, 2022 1:32 am at Mon Oct 10, 2022 1:32 am
>
> 
.bin file came from .x ,What does that mean exactly?

> but sadly no tool i saw from internet that can open .BIN (game file)That's probably because that .bin file doesn't meet the specs of a binary DirectX .x file (compare headers in hex editor).
## Post #5
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-10T00:00:08+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

Sorry to make it confusing

but this is what i mean

the .x file is the raw file of the game assets
the .bin is the game readable file
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-10T09:53:29+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

yeah, still confusing for me - what does AnimationCreator do exactly?
Is gameFile_bone.x the same file as gameFile_Animation.x? (They share the same size, 905 bytes.)

> Reply from kigwaness ↑Mon Oct 10, 2022 8:00 am at Mon Oct 10, 2022 8:00 am
>
> 
How to make a plugin, for the noesis to load the .bin?,I'd be surprised if someone would care for it without having a bigger context.
(Means, is this something that could help for other games using .x format?)

> Reply from kigwaness ↑Mon Oct 10, 2022 8:00 am at Mon Oct 10, 2022 8:00 am
>
> i got a tool that convert .x file to .bin (game readable file)Which tool is it? AnimationCreator?

Anyways with some basic coding skills you could do the .bin to .x transformation for yourself. Could take some time but looks doable.
Problem is to transform the (assumed) 8 floats frame in the .bin (0x55F: 1.000000 1.000000 1.000000 -0.139883 0.000000 0.000000 -0.772450 -5.703300) quaternions? into a 16 floats frame at time line 160 (0.000001,1.000000,-0.000000,0.000000,-0.022552,0.000000,0.999746,0.000000,0.999746,-0.000001,0.022552,0.000000,-0.139883,0.000000,0.000000,1.000000).

Example  Bip01_Pelvis from gameFile_animation.x:

```
  
  { Bip01_Pelvis }

  AnimationKey  {
   4;
   31;
   0;16;0.000001,1.000000,-0.000000,0.000000,-0.000002,0.000000,1.000000,0.000000,1.000000,-0.000001,0.000002,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   160;16;0.000001,1.000000,-0.000000,0.000000,-0.022552,0.000000,0.999746,0.000000,0.999746,-0.000001,0.022552,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   320;16;0.000001,1.000000,-0.000000,0.000000,-0.086078,0.000000,0.996288,0.000000,0.996288,-0.000001,0.086078,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   480;16;0.000001,1.000000,-0.000000,0.000000,-0.183801,0.000000,0.982963,0.000000,0.982963,-0.000001,0.183801,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   640;16;0.000001,1.000000,-0.000000,0.000000,-0.307453,0.000000,0.951563,0.000000,0.951563,-0.000001,0.307453,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   800;16;0.000001,1.000000,-0.000000,0.000000,-0.446754,0.000001,0.894657,0.000000,0.894657,-0.000001,0.446755,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   960;16;0.000001,1.000000,-0.000000,0.000000,-0.589684,0.000001,0.807634,0.000000,0.807634,-0.000001,0.589684,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   1120;16;0.000001,1.000000,-0.000000,0.000000,-0.723649,0.000001,0.690169,0.000000,0.690168,-0.000001,0.723649,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   1280;16;0.000001,1.000000,-0.000000,0.000000,-0.837293,0.000001,0.546754,0.000000,0.546754,-0.000001,0.837293,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   1440;16;0.000001,1.000000,-0.000000,0.000000,-0.922437,0.000001,0.386147,0.000000,0.386147,-0.000000,0.922437,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   1600;16;0.000001,1.000000,-0.000000,0.000000,-0.975532,0.000001,0.219858,0.000000,0.219858,-0.000000,0.975532,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   1760;16;0.000001,1.000000,-0.000000,0.000000,-0.998190,0.000001,0.060140,0.000000,0.060140,-0.000000,0.998190,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   1920;16;0.000001,1.000000,-0.000000,0.000000,-0.996641,0.000001,-0.081893,0.000000,-0.081893,0.000000,0.996641,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   2080;16;0.000001,1.000000,-0.000000,0.000000,-0.980309,0.000001,-0.197469,0.000000,-0.197469,0.000000,0.980309,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   2240;16;0.000001,1.000000,-0.000000,0.000000,-0.959899,0.000001,-0.280344,0.000000,-0.280344,0.000000,0.959899,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   2400;16;0.000001,1.000000,-0.000000,0.000000,-0.945367,0.000001,-0.326007,0.000000,-0.326007,0.000000,0.945367,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   2560;16;0.000001,1.000000,-0.000000,0.000000,-0.944081,0.000001,-0.329712,0.000000,-0.329712,0.000000,0.944081,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   2720;16;0.000001,1.000000,-0.000000,0.000000,-0.958341,0.000001,-0.285627,0.000000,-0.285626,0.000000,0.958341,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   2880;16;0.000001,1.000000,-0.000000,0.000000,-0.980309,0.000001,-0.197469,0.000000,-0.197469,0.000000,0.980309,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   3040;16;0.000001,1.000000,-0.000000,0.000000,-0.997479,0.000001,-0.070964,0.000000,-0.070964,0.000000,0.997479,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   3200;16;0.000001,1.000000,-0.000000,0.000000,-0.996312,0.000001,0.085807,0.000000,0.085807,-0.000000,0.996312,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   3360;16;0.000001,1.000000,-0.000000,0.000000,-0.965261,0.000001,0.261286,0.000000,0.261286,-0.000000,0.965261,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   3520;16;0.000001,1.000000,-0.000000,0.000000,-0.897547,0.000001,0.440918,0.000000,0.440918,-0.000001,0.897547,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   3680;16;0.000001,1.000000,-0.000000,0.000000,-0.793028,0.000001,0.609185,0.000000,0.609185,-0.000001,0.793028,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   3840;16;0.000001,1.000000,-0.000000,0.000000,-0.658549,0.000001,0.752538,0.000000,0.752537,-0.000001,0.658549,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   4000;16;0.000001,1.000000,-0.000000,0.000000,-0.506595,0.000001,0.862184,0.000000,0.862184,-0.000001,0.506595,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   4160;16;0.000001,1.000000,-0.000000,0.000000,-0.352714,0.000000,0.935731,0.000000,0.935731,-0.000001,0.352714,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   4320;16;0.000001,1.000000,-0.000000,0.000000,-0.212649,0.000000,0.977129,0.000000,0.977129,-0.000001,0.212649,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   4480;16;0.000001,1.000000,-0.000000,0.000000,-0.100191,0.000000,0.994968,0.000000,0.994968,-0.000001,0.100191,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   4640;16;0.000001,1.000000,-0.000000,0.000000,-0.026368,0.000000,0.999652,0.000000,0.999652,-0.000001,0.026368,0.000000,-0.139883,0.000000,0.000000,1.000000;;,
   4800;16;0.000001,1.000000,-0.000000,0.000000,-0.000002,0.000000,1.000000,0.000000,1.000000,-0.000001,0.000002,0.000000,-0.139883,0.000000,0.000000,1.000000;;;
  }
 }
```


In the .bin file (from about 0x516 to 0x9A3) it looks like this (hex2obj's table feature uses DWORDs instead of floats, sorry for that),
just to understand the binary structure and compare it to above ASCII code:

```
    0 3f800000 3f800000 3f800000 be0f3d7d     0     0 bfffbfff bfff7fff 
  160 3f800000 3f800003 3f800003 be0f3d7d     0     0 bf45bf45 c0b6816e 
  320 3f800000 3f7ffffa 3f7ffffa be0f3d7d     0     0 bd2ebd2e c2b18564 
  480 3f800000 3f7ffffa 3f7ffffa be0f3d7d     0     0 b9d1b9d1 c5a18b43 
  640 3f800001 3f7ffffb 3f7ffffc be0f3d7d     0     0 b541b541 c92d925b 
  800 3f800002 3f7ffffa 3f800007 be0f3d7d     0     0 af99af99 ccfa99f5 
  960 3f800001 3f7ffffc 3f7fffff be0f3d7d     0     0 a8fea8fe d0b0a162 
 1120 3f800001 3f800006 3f7ffffb be0f3d7d     0     0 a1a4a1a4 d405a80b 
 1280 3f800001 3f7ffffc 3f7ffffa be0f3d7d     0     0 99d099d0 d6bfad7f 
 1440 3f800001 3f7ffffd 3f7ffffb be0f3d7d     0     0 91d291d2 d8bbb178 
 1600 3f7fffff 3f800001 3f800002 be0f3d7d     0     0 8a028a02 d9f3b3e7 
 1760 3f800000 3f800000 3f800000 be0f3d7d     0     0 82b882b8 da77b4ef 
 1920 3f800000 3f7ffffe 3f7ffffe be0f3d7d     0     0 7c497c49 da6eb4dd 
 2080 3f800000 3f7ffffe 3f7ffffd be0f3d7d     0     0 77047704 da0fb41f 
 2240 3f800000 3f7ffff8 3f7ffff7 be0f3d7d     0     0 732e732e d998b331 
 2400 3f800001 3f7ffffb 3f7ffffa be0f3d7d     0     0 710a710a d942b286 
address 0x777:
 2560 3f800000 3f7ffff8 3f7ffff7 be0f3d7d     0     0 70dd70dd d93bb277 
 2720 3f7fffff 3f800004 3f7ffff8 be0f3d7d     0     0 72ef72ef d98fb31f 
 2880 3f800000 3f7ffffe 3f7ffffd be0f3d7d     0     0 77047704 da0fb41f 
 3040 3f800000 3f800001 3f800001 be0f3d7d     0     0 7cc87cc8 da73b4e7 
 3200 3f800000 3f800002 3f800002 be0f3d7d     0     0 83e283e2 da6cb4d9 
 3360 3f800000 3f7ffff8 3f7ffff7 be0f3d7d     0     0 8bed8bed d9b7b370 
 3520 3f800001 3f7ffffa 3f7ffff7 be0f3d7d     0     0 947b947b d828b051 
 3680 3f800002 3f7ffffe 3f7ffffc be0f3d7d     0     0 9d1d9d1d d5b1ab65 
 3840 3f800000 3f800003 3f7ffff3 be0f3d7d     0     0 a565a565 d26ba4d7 
 4000 3f800002 3f7ffffb 3f7ffffe be0f3d7d     0     0 acf3acf3 ce8d9d1b 
 4160 3f800001 3f7ffffb 3f7ffffd be0f3d7d     0     0 b37cb37c ca6e94de 
 4320 3f800000 3f800003 3f800003 be0f3d7d     0     0 b8c9b8c9 c6798cf3 
 4480 3f800000 3f7ffffd 3f7ffffd be0f3d7d     0     0 bcb4bcb4 c3208641 
 4640 3f800000 3f7ffffc 3f7ffffc be0f3d7d     0     0 bf25bf25 c0d581ac 
 4800 3f800000 3f800000 3f800000 be0f3d7d     0     0 bfffbfff bfff7fff 
    0   271     0   259    12 30706942 70535f31 00656e69     0 
address 0x9b7:
```

(The DWORD conversion shows 3f800000 for example. In fact it's 0000803F, so little endian float. Sorry for this confusion; as I said, it's a quick'n dirty means to show the binary structure.)
## Post #7
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-10T11:11:58+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

thread seems to get messy if question is ask repeadtly
thanks again
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-10T12:12:17+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Mon Oct 10, 2022 7:11 pm at Mon Oct 10, 2022 7:11 pm
>
> 
for more clearer what that tool can make

https://www.mediafire.com/file/j87rclop ... ax.7z/fileThat's the same video as before, isn't it?
Can't you simply tell, what AnimationCreator does? Which is the input file, what is the output?

btw: you still didn't answer which tool you mean by: "tool that convert .x file to .bin"
----------------------------------------------------------------

> and if it wont bother you sir, can i PM you regarding this topicWell, no, sorry. I usually spent 15 minutes only on different topics.

As I wrote you won't get a get-it-ready tool, imho.

You'll need to focus on the problem, that is, if I'm correct, to convert the .bin frames to .x ones.
The 16 floats should be of format XMFLOAT4X4. But sadly there's no decent hint to be found what is what (scale, translation, rotation).
Nearest hit:
[https://cpp.hotexamples.com/de/examples ... mples.html](https://cpp.hotexamples.com/de/examples/-/-/XMFLOAT4X4/cpp-xmfloat4x4-function-examples.html)

XMMatrixDecompose( &scale, &rotQuat, &translate, xmInMat );
where xmInMat is of format XMFLOAT4X4 (16 floats)

But scale (3 floats), rotQuat (4 floats), translation (3 floats) give 10 floats in sum, not 8 (.bin) or 16 (.x), so I'm stuck here.
-----------
Thing is that you need the .bin to .x part, I'm aware of this.
For the reverse way I found a decent description (how to get trans, scale, rot from a 4x4 matrix):
[https://math.stackexchange.com/question ... ion-rotati](https://math.stackexchange.com/questions/237369/given-this-transformation-matrix-how-do-i-decompose-it-into-translation-rotati)
## Post #9
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-10T12:57:42+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

thank you very much
i will read all the links you provided
god bless
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-10T14:26:58+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Mon Oct 10, 2022 8:57 pm at Mon Oct 10, 2022 8:57 pm
>
> 
thank you very much
i will read all the links you providedwell, my bad - you won't get far, I guess.
Because I broke the golden rule: "always start with the skeleton".

I strongly suggest to read through Approaches of Parsing Bone Representations from Bigchillghost.

> Reply from Bigchillghost ↑Fri Feb 01, 2019 2:46 pm at Fri Feb 01, 2019 2:46 pm
>
> 

Some simple py code (amongst other code lines, of course) containing

```
        for j in range(0, 16):
            Matrix.append(bs.readFloat())
        boneMat = NoeMat43( [(Matrix[0],Matrix[1],Matrix[2]),
                             (Matrix[3],Matrix[4],Matrix[5]),
                             (Matrix[6],Matrix[7],Matrix[8]),
                             (Matrix[9],Matrix[10],Matrix[11])
                             ] )
```
should do to read the skeleton bones.

Afaik there's no py scripts handling ASCII data, so a toBin transformation of

```
    FrameTransformMatrix {
   0.000001,1.000000,-0.000000,0.000000,-0.000002,0.000000,1.000000,0.000000,1.000000,-0.000001,0.000002,0.000000,-0.139883,0.000000,0.000000,1.000000;;
  }
```
is required.

After the skeleton is read successfully you could care for the "reverse way", getting the skeleton from .bin. That's how I'd do it.
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-11T03:58:04+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Sun Oct 09, 2022 11:26 pm at Sun Oct 09, 2022 11:26 pm
>
> 
how to make it load in noesis ?
I parsed *.x file

and took parents from there. and took data from the first frame from *.bin
as
scale 12 bytes (3 float)
position 12 bytes (3 float)
quat 8 bytes (4 short?) *not used
without rotations the skeleton is correct.:

need to solve problem with quaternion (rotation)
I also parsed the animation from *.x as NoeAnim and then as NoeKeyFramedAnim and got a bad result. (this is most likely due to multiplyBones, I don’t want to delve into it) to add animation, uncomment lines 27,28,36

anyway, I'm not interested. I should have been asleep a couple of hours ago. plugins are attached. good luck with this
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-11T08:26:11+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from Durik256 ↑Tue Oct 11, 2022 11:58 am at Tue Oct 11, 2022 11:58 am
>
> 
anyway, I'm not interested. I should have been asleep a couple of hours ago. plugins are attached. good luck with thishaha, Durik, who would care for it if not you?   You're the savior of the Noesis followers.
## Post #13
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-11T13:00:23+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

thanks very much
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-12T00:45:05+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

> Reply from shakotay2 ↑Tue Oct 11, 2022 4:26 pm at Tue Oct 11, 2022 4:26 pm
>
> 
You're the savior of the Noesis followers.
  

damn, I made a mistake in animation parsing. assigned x=0. before the loop even though it didn't need to be done. because of this, the animation was broken.
Fix(for *.x):

but if load *.bin as an animation (by reading the rotation as denormalized quaternions with short values).
the animation is still broken.
## Post #15
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-12T04:43:59+00:00
- Post Title: Noesis Plugin for Game File .bin (DirectX)

I hope masters here can have more interest 
i can uplaod the entire source ( if there soneone is interested -I HOPE)
together with all its dependencies and other third partry stuff , to make it work
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-12T11:42:13+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Wed Oct 12, 2022 12:43 pm at Wed Oct 12, 2022 12:43 pm
>
> 
this is the source

aaaaa, are you serious?
why not do it right away, why are we reinventing the wheel here.
that's it, the problem with quanterions is solved:
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-12T12:14:15+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

> Reply from Durik256 ↑Wed Oct 12, 2022 7:42 pm at Wed Oct 12, 2022 7:42 pm
>
> 
, why are we reinventing the wheel here.Guess, the source code is copyrighted and kigwaness was afraid to break the rules...
## Post #18
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-12T12:20:00+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

> Reply from shakotay2 ↑Wed Oct 12, 2022 8:14 pm at Wed Oct 12, 2022 8:14 pm
>
> 
the source code is copyrighted
maybe, but at least he could mention that he has it. rather than just upload an unknown file and say make me a plugin.
## Post #19
- Username: kigwaness
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 02, 2021 3:53 pm
- Post datetime: 2022-10-12T12:38:29+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

> Reply from Durik256 ↑Wed Oct 12, 2022 8:20 pm at Wed Oct 12, 2022 8:20 pm
>
> 
shakotay2 wrote: ↑Wed Oct 12, 2022 8:14 pm
the source code is copyrighted

maybe, but at least he could mention that he has it. rather than just upload an unknown file and say make me a plugin.

my 1 post was not posted
maybe because my internet was not good the time i posted.
,
yes sir, i got it, But i was hesistant to directly post it, since i still dont know if it allowed or not (sorry for that)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-12T22:58:49+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

haha, well, all the time I didn't get, WHY gameFile_animation.x was not loaded by assimp_viewer (3.3.1 crashed with an assertion error).
Now with the newest version it told me that at least one mesh is required to load the .x asset.

So I added a homer mesh, which I had lying around  and, bingo (see red skeleton, ignore Homer):
.



gameFile_animx-modified.jpg (161.7 KiB) Viewed 422 times
## Post #21
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-17T18:43:34+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

parser from here: [github.com/xfile_parser.py](https://github.com/oguna/Blender-XFileImporter/blob/master/xfile_parser.py)
*compressed models (bzip) sometimes give a zlib error.

result: use fragMotion for *.x files. 
[fmt_X.zip](https://xentaxbackup.github.io/file/22924_fmt_X.zip)
## Post #22
- Username: james54
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 30, 2022 2:35 pm
- Post datetime: 2022-11-30T09:22:33+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

looking for .bin animation container plug in pls dm me if have tnx
## Post #23
- Username: Xjohn4
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 10, 2023 7:02 pm
- Post datetime: 2023-05-11T01:49:24+00:00
- Post Title: Re: Noesis Plugin for Game File .bin (DirectX)

> Reply from kigwaness ↑Mon Oct 10, 2022 8:00 am at Mon Oct 10, 2022 8:00 am
>
> 
Sorry to make it confusing

but this is what i mean

the .x file is the raw file of the game assets
the .bin is the game readable file

Hi! What converter you used to return the .bin file type to .x? Thank you.
