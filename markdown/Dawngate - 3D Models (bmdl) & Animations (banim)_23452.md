## Post #1
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-02-16T12:27:43+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

Hey everyone,
since the big "Dawngate: Rebirth"-Project got changed into the commercial project "Dreambound", which has nothing to do with restoring the original game, I'm now trying to restore the game as best as possible by myself.

For this purpose, I've already exported all the models using this Noesis Extension:
[viewtopic.php?t=11348](https://forum.xentax.com/viewtopic.php?t=11348)

However, this Extension does not take the animations into consideration, which are stored as "*.banim"-Files outside of the bmdl-file itself.
Using HexEdit, I noticed that the bone-instructions are partially readable, yet the I'm tapping in the dark when it comes to the actual parameters/frames of the animation etc.

So I was wondering if there's already a known method of reading/translating those files into a useable format. (Or somebody maybe knowing a tool, which can read this format, since I haven't found anything in this regard).

Any kind of help would be hugely appriecated. Alternatively, I'd also be very thankful if anybody can give me any advise on how to do this myself.
## Post #2
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-02-27T16:17:46+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

I still couldn't figure out how to read the animations.
I'm interested in restoring the original game in a new engine (without any commerical interest) as you can check out[ here](https://twitter.com/of_shapers).

For those of you interested to have a look at those files, you can find one example [here (Google Drive)](https://drive.google.com/drive/folders/1BAqJVfCDLxeLL4s8Z6c7FQQbstz0Y9CF?usp=sharing). It contains the 3D model of a minion (the bmdl) and it's animations (the banim files)

There is also a "generic" minion_ranged.banim, which doesn't seem to have any real animation data. But it seems to showcase the "minimal" requirement of animation data.
So a "translate"-command seems to consist of at least 16 bytes, while a Quaternion-Rotation takes 20 bytes in this file.

Every bone seems to be only reference once for every "action" in the file.
Before the animation-data start, there is an overall overview of all the bones of the 3D model.
Then, once bone is effected by an animation, you might see something like: "arm_2_L_1.rotate + data" and "arm_2_L_1.translate + data". But you never see any data like that twice. So there's no 2 "arm_2_L_1.rotate" for example. Instead, the data will be bigger accordingly.

Longer animations (like the death animation) have different byte-sizes for the animation data. So a translate could be 488 bytes (30,5 times of the reference data), while a rotation in the same animation could "only" be 310 bytes (15,5 times of the reference data).

So I assume that the animation data only consist of the different keyframe data. So something like (at frame x, have your rotation at y) etc. which explains the varying byte length. 

If there's anybody who can help me here, I'd be very thankful. Even if it's "only" to help me to be able to help myself xD
I don't mind spending multiple hours into restoring that information if I know what I have to look for. But looking at the data without any knowledge/experience makes it quite hard for me.
[minion_ranged_1.png](https://xentaxbackup.github.io/file/19610_minion_ranged_1.png)
## Post #3
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-02-27T19:14:50+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

So, I've noticed something interesting for the bone-translate function.

It seems like the first values are kind of a timeline.
For example:

00 00 = First Frame
FF FF = Last Frame

Followed by 6 bytes for each of those frames.

So you can read it like this:

00 00 = First Frame
FF FF = Last Frame
EA E1 FF FF 00 00 = Vector at First Frame
EA E1 FF FF 00 00 = Vector at Last Frame

I had a look at other animations and it always seems to follow this logic. Here is another example:

Frame Data:
00 00 
97 10
F6 12
B4 17
71 1C
D0 1E
2F 21 
EC 25
4B 28
09 2D
68 2F
25 34
E3 38 
55 55
E3 78
1B 87
54 95
2E A1
67 AF
41 BB
5E C2
96 D0
 E3
C6 F1 
FF FF 

Vector Data:
B5 F4 9D 9F 03 00 
B6 F4 9C 9F 00 00 
0F F5 99 A0 41 00 
DD F7 85 A8 63 02 
FA F9 DE AE D2 04 
C2 FA 6F B1 35 06 
72 FB D2 B3 B6 07 
D1 FC BE B8 18 0B 
71 FD 16 BB D8 0C 
8A FE 54 BF 39 10 
FE FE 25 C1 C0 11 
AC FF F2 C3 3C 14 
FF FF 5F C5 A2 15 
ED FF B5 C5 C5 16 
CF FF 6E C5 CB 16 
41 FF F8 C2 65 14 
64 FE 29 BF AD 10 
A1 FD CB BB 63 0D 
E3 FC 83 B8 2F 0A 
97 FC 33 B7 E7 08 
A4 FC 6C B7 21 09 
3A FD 15 BA CE 0B 
7A FE BF BF 81 11 
6A FF FE C3 C7 15 
D5 FF E1 C5 AD 17

The first data block always goes from 00 00 to FF FF and defines each timestamp in between. The amount of frame data seems to always match the amount of vector data. So if there is 86 bytes of timeline data, then the corresponding is 86 x 3 bytes accordingly. In the example above, you'll also notice that both data blocks are 24 lines each. It might not be a lot yeah, but It's a first step I guess.
## Post #4
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-02-27T20:20:01+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

The same logic seems to apply for "scale" (6 bytes for vector data) and "rotate" (8 bytes for quaternion data) aswell.
Every movement seems to follow those rules. Now I "only" have to figure out which data type those bytes are and how to "import" them into the 3d model.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-28T12:59:45+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

well you're speaking of "6 bytes for vector data" but you don't show their values. So dunno if you know what you're doing.  
Had a quick glance at the anim data and I may be totally wrong so don't rely on my thoughts too much.  
(There's a good chance that the data I focused on is a quaternion, because there's 4 words of which I chose only 3.)

Values in green rectangle assumed to be x,y,z of a translation (value, vector data, whatever).
Looks for me to be half float values but results in too big results, partially.

So I chose shorts, resulting "curve" looks, ..., interesting.

We've these bones here:
spine_1_C_1
fk_1_L_1, fk_1_R_2
spine_2_C_1, spine_3_C_1
arm_1_L_1, arm_1_R_1
fk_1_C_1
head_1_C_1
arm_2_L_1, arm_2_R_1
fk_1_R_1, fk_2_L_1
arm_3_L_1, arm_3_R_1

and I dunno which value belongs to which, maybe one x,y,z-translation for each bone?
.



minion ranged anim.png (50.09 KiB) Viewed 125 times


(The skeleton looks different, though.)
## Post #6
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-02-28T14:20:34+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

First of all, let me say that I'm very thankful for somebody to have a look at it 

I don't know what I'm doing and try to make sense out of what I see.
You seem to be looking at completely different information though.

So I'll try to explain, what I'm looking at (since that is the only data, which makes logic to me).

In ASCI, I can read the different bones at Offset 000009D0, which are the ones you're mentioning.

The animation instructions are starting at 00001048, which has readable ASCI functions. After that animation instruction, there is a seems to be "Keyframe"-Data. So 00 00 for the first frame, followed by FF FF for the last frame.
If an animation has more keyframes, those will be between this 00 00 and FF FF accordingly.
So an animation with 5 keyframes has data like:
00 00  xx xx  xx xx  xx xx  FF FF

After that last FF FF, the actual information of the animation seems to start.
With minion_ranged.anim, the first frame data starts at 00001068. As a Quaternion, this data is 8 bytes. Every keyframe then has it's own chunk of 8 byte data.
But this example only views the rotation of the bone, while you can find the translating of the bone afterwards at 00001078. Here, the structure is identical. But after the "timeline" from 00 00 to FF FF, the vector data is only 6 bytes in size.

So based on what I see, it's "only" about adding the animation data to the existing bmdl python script.
## Post #7
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-02-28T15:39:38+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

Ah and just for clarification. The script to read the bmdl (with the actual 3D data) exists [here](https://forum.xentax.com/viewtopic.php?t=11348).

Looking at the bmdl file as reference, all the "animation" code seems to be identical with the minion_ranged.banim.
In fact, almost that entire animation file is included into the initial bmdl. The only difference being the header and some "2 byte" differences here and there spread between the bone-list and what I believe to be the "animation"-instructions.
## Post #8
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-03-01T15:22:34+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

There are more signs, which make me confident in my thesis.
I added some debugging to the initial bmdl-reader script at Line 113 (before the bone is added to its list):

```
print(boneMtx.toAngles())
```


Doing this will give me output like this:

```
(270.0, 90.0, 273.67510986328125)
(NoeBone:1,fk_1_L_1,None,0)
(0.0, 0.0, 90.0)
(NoeBone:2,fk_1_R_2,None,0)
(0.0, 0.0, 90.0)
```


When I now have a look at the bmdl file at 0000BB92, 0000B9CA and 0000BA7E for my assumed quaternions of spine_1_C_1, fk_1_L_1 & fk_1_R_2 then I see:

spine_1_C_1

```
FF FF 00 00 FF FF 00 00
```


fk_1_L_1

```
F5 07 F5 07 FF FF 00 00
```


fk_1_R_2

```
F5 07 F5 07 FF FF 00 00
```


With the bones fk_1_L_1 and fk_1_R_2 having not only an identical rotation in Noesis, but also an identical hex string for my assumed quaternion, I feel confident that there's more to it.

But I couldn't really find a reasonable conversion to get those Rotations out of these hex strings.

Another aspect is wether those values from the Noesis Script contain rounding errors or not.
When I go to [quaternions.online](https://quaternions.online/) and type in the angles (270/90/270), then I get the Quaternion (0/-0.707/0/-0.707) which would make sense with the hex string for the spine_1_C_1 above (Both when only looking at 4 and 8 bytes depending on the parameters order).

But when it comes to those other two, I don't know how to really make sense out of those numbers.Wether their rotation is based in relation to it's parenting bone or "in general".
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T15:36:31+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

Maybe use the skeleton (from Noesis smd export) as a reference:

```
nodes
  0 "spine_1_C_1"  -1
  1 "fk_1_L_1"  0
  2 "fk_1_R_2"  0
  3 "spine_2_C_1"  0
  4 "spine_3_C_1"  3
  5 "arm_1_L_1"  4
  6 "arm_1_R_1"  4
  7 "fk_1_C_1"  4
  8 "head_1_C_1"  4
  9 "arm_2_L_1"  5
  10 "arm_2_R_1"  6
  11 "fk_1_R_1"  7
  12 "fk_2_L_1"  7
  13 "arm_3_L_1"  9
  14 "arm_3_R_1"  10
end
skeleton
time 0
  0 0.000000 0.066201 0.823695 1.570796 -1.506650 1.570796
  1 -0.288017 -0.013102 -0.349659 0.000000 -0.000000 -3.077446
  2 -0.288018 -0.013101 0.349658 0.000000 -0.000000 -3.077446
  3 0.493824 -0.000000 0.000000 0.000000 -0.000000 -0.056378
  4 0.458150 0.000000 0.000000 0.000000 -0.000000 -0.284782
  5 0.061883 0.154936 -0.637021 -1.101570 1.463735 -2.269376
  6 0.061884 0.154937 0.637022 1.101450 -1.463738 -2.269353
  7 0.005265 0.407226 -0.000000 -3.102707 -0.133786 1.692305
  8 0.638488 0.010319 0.000000 0.000000 -0.000000 0.040890
  9 0.388428 0.000002 -0.000001 0.007115 -0.074572 0.000345
  10 0.388427 -0.000000 0.000001 -0.007115 0.074572 0.000345
  11 0.149970 0.129564 -0.378035 2.754210 0.079887 1.482760
  12 0.046090 0.159568 0.393194 3.027556 0.024110 -1.644531
  13 0.516391 0.000000 -0.000000 -0.000001 0.000000 0.000000
  14 0.516393 0.000002 -0.000000 0.000104 0.000000 0.000001
end
```

values:
0.000000 0.066201 0.823695 transition of spine_1_C_1
1.570796 -1.506650 1.570796 rotation (radians)
## Post #10
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-03-01T16:33:42+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

Thanks a lot! I'll take a look into those numbers. They seem to make a little bit more sense.
## Post #11
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-03-23T06:05:06+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

@Aisora
Any progress on the animations?
## Post #12
- Username: Aisora
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Feb 16, 2021 8:10 pm
- Post datetime: 2021-03-23T20:36:37+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

Hi,
Yes and No.
I have a solution, but wasn't really able to put a lot of time into it yet.
Since I am extracting those animations from banim files, which the client contains, I can simply have a look in the client itself on how those files are being read in the first place.
I also think that I've found the code responsible for "translating" those instructions accordingly. You can just search for "banim" and "bmdl" using Ghidra on the Dawngate.exe and you'll find the function, which turns the byte-array into an actual object. But I didn't really advance from here yet, since work keeps me very busy at the moment.
## Post #13
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-07T13:20:58+00:00
- Post Title: Dawngate - 3D Models (bmdl) & Animations (banim)

> Reply from shakotay2 ↑Mon Mar 01, 2021 11:36 pm at Mon Mar 01, 2021 11:36 pm
>
> 

It's also a good idea, but I found that the rotation of my guide rotation is wrong, and the quaternion becomes that radian..
