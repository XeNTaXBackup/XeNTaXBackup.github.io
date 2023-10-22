## Post #1
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2023-07-24T11:06:51+00:00
- Post Title: Legend of Kay Anniversary .dat files

Hello. It's been a while.
A long time ago, I got a script for extracting the massive 4 GB pak and came across many weird files in different extension (.dat, .for, .txt, etc...). I've put these files aside for a while until now, as I found a tool called Rawtex that allowed me to extract textures from (what I assume to be) model files. The data appears to be little endian, but aside from that there are no clear indices. The models are mostly 1 or 2 MB.
Here's some samples: [https://www.mediafire.com/file/fmctt33o ... s.zip/file](https://www.mediafire.com/file/fmctt33o0nesw5e/LoKA+Samples.zip/file)
Any help would be appreciated.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-24T11:47:20+00:00
- Post Title: Legend of Kay Anniversary .dat files

> Reply from GianaSistersFan64 ↑Mon Jul 24, 2023 7:06 pm at Mon Jul 24, 2023 7:06 pm
>
> The data appears to be little endian, but aside from that ...Well, the mesh format appears to be simple. On a quick glance I found a point cloud. The sphere at the bottom indicates normals. This means the vertex count needs to be reduced 'till the sphere disappears.

At offset 0xC9F50 there's face indices. So I don't see a reason for you why not to give it a go.  
.



Kay-00000000-dat.png (127.26 KiB) Viewed 114 times
## Post #3
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2023-07-24T13:19:15+00:00
- Post Title: Legend of Kay Anniversary .dat files

> Reply from shakotay2 ↑Mon Jul 24, 2023 7:47 pm at Mon Jul 24, 2023 7:47 pm
>
> 
GianaSistersFan64 wrote: ↑Mon Jul 24, 2023 7:06 pmThe data appears to be little endian, but aside from that ...
Well, the mesh format appears to be simple. On a quick glance I found a point cloud. The sphere at the bottom indicates normals. This means the vertex count needs to be reduced 'till the sphere disappears.

At offset 0xC9F50 there's face indices. So I don't see a reason for you why not to give it a go.  
.
Kay-00000000-dat.png

Ah, cool.
This is all I could get with Hex2Obj. I couldn't find the face and didn't cared about UV (it's a bit hard to find the correct value).
[2023-07-24_151352.png](https://xentaxbackup.github.io/file/24104_2023-07-24_151352.png)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-24T13:57:55+00:00
- Post Title: Legend of Kay Anniversary .dat files

Vertices of the face seem to start at 0x8D54.
And why not try to get the other simple parts at least? Then look which blocks are left over.
.



Kay-2.png (159.62 KiB) Viewed 98 times


.
Might be eyeballs (.H2O parameters file):

0x637B4 960
Vb1
12 99
0x623CC 182
020000
0x0 255
## Post #5
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2023-07-24T17:14:28+00:00
- Post Title: Legend of Kay Anniversary .dat files

> Reply from shakotay2 ↑Mon Jul 24, 2023 9:57 pm at Mon Jul 24, 2023 9:57 pm
>
> 
Vertices of the face seem to start at 0x8D54.
And why not try to get the other simple parts at least? Then look which blocks are left over.
.
Kay-2.png
.
Might be eyeballs (.H2O parameters file):

0x637B4 960
Vb1
12 99
0x623CC 182
020000
0x0 255
Still couldn't find the face indice for the face, it must be stored elsewhere. I tried looking for the UV, but no sign.
Though the model looks a bit more complete.
[2023-07-24_190737.png](https://xentaxbackup.github.io/file/24107_2023-07-24_190737.png)
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-07-24T22:32:37+00:00
- Post Title: Legend of Kay Anniversary .dat files

> Reply from GianaSistersFan64 ↑Tue Jul 25, 2023 1:14 am at Tue Jul 25, 2023 1:14 am
>
> 
I tried looking for the UV, but no sign.
i made plugin for Noesis. [fmt_KAY.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_KAY.py) 
*(only for "..\Kay\00000000.dat)
## Post #7
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2023-07-24T23:43:43+00:00
- Post Title: Legend of Kay Anniversary .dat files

> Reply from Durik256 ↑Tue Jul 25, 2023 6:32 am at Tue Jul 25, 2023 6:32 am
>
> 
GianaSistersFan64 wrote: ↑Tue Jul 25, 2023 1:14 am
I tried looking for the UV, but no sign.

i made plugin for Noesis. fmt_KAY.py 
*(only for "..\Kay\00000000.dat)
I don't know how much to thank you.  I could try to make a support for other specific models with the script if it's not too hard. But nonetheless, I'm looking forward to more!

Aside, how do you move the bones in Noesis? I'm required to open Blender to test the armature.
