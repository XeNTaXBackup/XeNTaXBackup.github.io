## Post #1
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-08-27T02:01:03+00:00
- Post Title: Question Export . bin 3ds max

Hello everyone
I have problem
how to export .bin 3ds max as file this

[http://www.mediafire.com/file/81nm21gg3 ... _Color.rar](http://www.mediafire.com/file/81nm21gg39jrx39/Angel_Wing_7_Color.rar)

thank so so much for help
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-27T11:17:45+00:00
- Post Title: Question Export . bin 3ds max

what is this? ran online animation?

I'm pretty sure you won't get any reply if you don't explain your problem.
Noone would start with animations if he did not have a mesh and a skeleton.

Do you have a skeleton?
(There's a good chance to get it from the .bin which you uploaded.)
## Post #3
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-08-29T13:25:54+00:00
- Post Title: Question Export . bin 3ds max

> Reply from shakotay2
>
> what is this? ran online animation?

I'm pretty sure you won't get any reply if you don't explain your problem.
Noone would start with animations if he did not have a mesh and a skeleton.

Do you have a skeleton?
(There's a good chance to get it from the .bin which you uploaded.)
Yeah bro do you know make file .bin for animation
do you have fb? bro

file sample
[http://www.mediafire.com/file/81nm21gg3 ... _Color.rar](http://www.mediafire.com/file/81nm21gg39jrx39/Angel_Wing_7_Color.rar)
## Post #4
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-09-01T10:55:27+00:00
- Post Title: Question Export . bin 3ds max

Anyone know it
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-04T20:05:27+00:00
- Post Title: Question Export . bin 3ds max

skin and bones files are binary .x files; the mesh (skin) can be loaded using DXViewer:



binary-x-file.JPG (31.25 KiB) Viewed 240 times


(I'll check the bones files sooner or later. It can't be converted to an ASCII file using MeshConvert /xt from the DirectX-SDK.)
## Post #6
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-09-06T02:38:35+00:00
- Post Title: Question Export . bin 3ds max

> Reply from shakotay2
>
> skin and bones files are binary .x files; the mesh (skin) can be loaded using DXViewer:
binary-x-file.JPG
(I'll check the bones files sooner or later. It can't be converted to an ASCII file using MeshConvert /xt from the DirectX-SDK.)
bro do you have fb?
i want talk with you about it. i already convert .x to .max but i need know how to export .bin animation ^^
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-08T17:11:49+00:00
- Post Title: Question Export . bin 3ds max

> Reply from blackcatyb
>
> i want talk with you about it.I'm a coder, not a talker, sry. 

> i already convert .x to .max but i need know how to export .bin animation ^^yep, and I already wrote that you'll need the skeleton first:



AWing_skel.jpg (29.15 KiB) Viewed 220 times


(Hierarchy is missing, but required since names of bones are meaningless - Bonexx_mirrored.)
Parenting ids might be in the bin file.
## Post #8
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-09-10T09:52:12+00:00
- Post Title: Question Export . bin 3ds max

> Reply from shakotay2
>
> blackcatyb wrote:i want talk with you about it.I'm a coder, not a talker, sry. 
i already convert .x to .max but i need know how to export .bin animation ^^yep, and I already wrote that you'll need the skeleton first:
AWing_skel.jpg
(Hierarchy is missing, but required since names of bones are meaningless - Bonexx_mirrored.)
Parenting ids might be in the bin file.

you try file .max this problem no one know export animation .bin file @@!
[http://www.mediafire.com/?brb95945ujip6es/](http://www.mediafire.com/?brb95945ujip6es/)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-10T11:54:06+00:00
- Post Title: Question Export . bin 3ds max

> Reply from blackcatyb
>
> you try file .max this problemI don't have max installed atm. I'd need an fbx file (and a dae file, maybe)

> no one know export animation .bin file @@!did you ever look at the bin file? It's frames contain 6 floats and two DWords, iirc, so it's hard to get a rotation matrix and the position from it as you'd need it for an (ASCII) animation .x file:

```
   4;
   62;
   0;16;0.452612,0.717604,0.529327,0.000000,-0.426220,0.695510,-0.578448,0.000000,-0.783248,0.036203,0.620654,0.000000,31.000202,0.000005,0.000011,1.000000;;,
...
   4960;16;0.452612,0.717604,0.529327,0.000000,-0.426220,0.695510,-0.578448,0.000000,-0.783248,0.036203,0.620654,0.000000,31.000202,0.000005,0.000011,
1.000000;;;
  }
  { Bip01_R_UpperArm }
```
## Post #10
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-09-11T13:24:35+00:00
- Post Title: Question Export . bin 3ds max

> Reply from shakotay2
>
> blackcatyb wrote:you try file .max this problem I don't have max installed atm. I'd need an fbx file (and a dae file, maybe)
no one know export animation .bin file @@!did you ever look at the bin file? It's frames contain 6 floats and two DWords, iirc, so it's hard to get a rotation matrix and the position from it as you'd need it for an (ASCII) animation .x file:
Code: Select all  AnimationKey {
   4;
   62;
   0;16;0.452612,0.717604,0.529327,0.000000,-0.426220,0.695510,-0.578448,0.000000,-0.783248,0.036203,0.620654,0.000000,31.000202,0.000005,0.000011,1.000000;;,
...
   4960;16;0.452612,0.717604,0.529327,0.000000,-0.426220,0.695510,-0.578448,0.000000,-0.783248,0.036203,0.620654,0.000000,31.000202,0.000005,0.000011,
1.000000;;;
  }
  { Bip01_R_UpperArm }
fbx file you need
[http://www.mediafire.com/?5kuszjywbuazu35/](http://www.mediafire.com/?5kuszjywbuazu35/)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-14T16:35:26+00:00
- Post Title: Question Export . bin 3ds max

hah, cool, wings skeleton. How did you get it?



wings_skeleton.JPG (29.9 KiB) Viewed 192 times


You can export it from Noesis as smd file to see the hierarchy:

```
nodes
  0 "w_cos_angel01_wings"  -1
  1 "Bone12_mirrored_"  -1
  2 "Bone01_mirrored_"  1
  3 "Bone05_mirrored_"  2
  4 "Bone15_mirrored_"  3
  5 "Bone02_mirrored_"  2
  6 "Bone03_mirrored_"  5
  7 "Bone04_mirrored_"  6
  8 "Bone16_mirrored_"  7
  9 "Bone09_mirrored_"  6
  10 "Bone07_mirrored_"  5
  11 "Bone14_mirrored_"  10
  12 "Bone17_mirrored_"  2
  13 "Bone18_mirrored_"  12
  14 "Bone01_mirrored__mirrored_"  1
  15 "Bone02_mirrored__mirrored_"  14
  16 "Bone07_mirrored__mirrored_"  15
  17 "Bone14_mirrored__mirrored_"  16
  18 "Bone03_mirrored__mirrored_"  15
  19 "Bone04_mirrored__mirrored_"  18
  20 "Bone16_mirrored__mirrored_"  19
  21 "Bone09_mirrored__mirrored_"  18
  22 "Bone17_mirrored__mirrored_"  14
  23 "Bone18_mirrored__mirrored_"  22
  24 "Bone05_mirrored__mirrored_"  14
  25 "Bone15_mirrored__mirrored_"  24
end
skeleton
```
## Post #12
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2017-09-16T13:46:47+00:00
- Post Title: Question Export . bin 3ds max

> Reply from shakotay2
>
> hah, cool, wings skeleton. How did you get it?
wings_skeleton.JPG
You can export it from Noesis as smd file to see the hierarchy:
Code: Select allversion 1
nodes
  0 "w_cos_angel01_wings"  -1
  1 "Bone12_mirrored_"  -1
  2 "Bone01_mirrored_"  1
  3 "Bone05_mirrored_"  2
  4 "Bone15_mirrored_"  3
  5 "Bone02_mirrored_"  2
  6 "Bone03_mirrored_"  5
  7 "Bone04_mirrored_"  6
  8 "Bone16_mirrored_"  7
  9 "Bone09_mirrored_"  6
  10 "Bone07_mirrored_"  5
  11 "Bone14_mirrored_"  10
  12 "Bone17_mirrored_"  2
  13 "Bone18_mirrored_"  12
  14 "Bone01_mirrored__mirrored_"  1
  15 "Bone02_mirrored__mirrored_"  14
  16 "Bone07_mirrored__mirrored_"  15
  17 "Bone14_mirrored__mirrored_"  16
  18 "Bone03_mirrored__mirrored_"  15
  19 "Bone04_mirrored__mirrored_"  18
  20 "Bone16_mirrored__mirrored_"  19
  21 "Bone09_mirrored__mirrored_"  18
  22 "Bone17_mirrored__mirrored_"  14
  23 "Bone18_mirrored__mirrored_"  22
  24 "Bone05_mirrored__mirrored_"  14
  25 "Bone15_mirrored__mirrored_"  24
end
skeleton
export .smd after rename it .bin?
## Post #13
- Username: blackcatyb
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Dec 22, 2015 12:54 pm
- Post datetime: 2018-02-19T14:43:51+00:00
- Post Title: Question Export . bin 3ds max

up for help
