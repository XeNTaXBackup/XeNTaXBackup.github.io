## Post #1
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-06-09T19:26:19+00:00
- Post Title: How can I open this .skeleton and .anim file?

Hello, 

I have two file in attachments. One is act_10.skeleton, contain skeleton data. Another is idle_a_01.anim, example of animation. But don't know how to open it. We can read all data in hex as it not encrypt. Hope anyone will interest in this and help me know how to open skeleton and apply animation to it.

Thank you and have a nice day. 
[act_10.zip](https://xentaxbackup.github.io/file/20266_act_10.zip)
## Post #2
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-07-09T09:15:49+00:00
- Post Title: How can I open this .skeleton and .anim file?

Up topic to keep this issue alive... Please can someone let we know how to open it? Thank you
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-09T12:25:30+00:00
- Post Title: How can I open this .skeleton and .anim file?

Which game is it from?

Strange mix of binary and ASCII data, here's ASCII , assumed keyframes for Bip001, act_10.skeleton:

```
0,0,0,0,1900,0,0,0,5200,0.08,0.01,0.01,12266,0.35,0.01,0.1,14666,0.4,0.01,0.12,16100,0.41,0.01,0.13,17700,0.39,0.01,0.13,19300,0.34,0.01,0.11,20900,0.25,0.01,0.09,22700,0.11,0,0.04,23300,0.04,0.05,0.01,23433,0.03,0.04,0.01,23566,0.01,0,0,23666,0,-0.05,0,23700,-2.56,-0.06,-0.87,26633,-2.56,-0.07,-0.87,26666,-2.53,-0.07,-0.92,26700,-2.56,-0.07,-0.87,26733,-2.75,-0.07,-0.6,27400,-2.76,-0.06,-0.61,28400,-2.81,-0.05,-0.64,29766,-2.86,-0.08,-0.6,31066,-2.89,-0.1,-0.58,31900,-2.89,-0.1,-0.57,33100,-2.88,-0.09,-0.59,34433,-2.85,-0.05,-0.62
```


Attempt to give it some structure:
0,0,0,0,
1900,0,0,0,
5200,0.08,0.01,0.01,
12266,0.35,0.01,0.1,
14666,0.4,0.01,0.12,
16100,0.41,0.01,0.13,
17700,0.39,0.01,0.13,
19300,0.34,0.01,0.11,
20900,0.25,0.01,0.09,
22700,0.11,0,0.04,
23300,0.04,0.05,0.01,
23433,0.03,0.04,0.01,
23566,0.01,0,0,
23666,0,-0.05,0,
23700,-2.56,-0.06,-0.87,
26633,-2.56,-0.07,-0.87,
26666,-2.53,-0.07,-0.92,
26700,2.56,-0.07,-0.87,
26733,-2.75,-0.07,-0.6,
27400,-2.76,-0.06,-0.61,
28400,-2.81,-0.05,-0.64,
29766,-2.86,-0.08,-0.6,
31066,-2.89,-0.1,-0.58,
31900,-2.89,-0.1,-0.57,
33100,-2.88,-0.09,-0.59,
34433,-2.85,-0.05,-0.62
...
## Post #4
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-07-09T13:28:17+00:00
- Post Title: How can I open this .skeleton and .anim file?

> Reply from shakotay2 ↑Fri Jul 09, 2021 8:25 pm at Fri Jul 09, 2021 8:25 pm
>
> 
Which game is it from?

> Game Name: "Dawn of Isles"
>
> Producer: NetEase Games
>
> Official Site: https://www.dawn-of-isles.com
>
> XAPK: https://apkpure.com/dawn-of-isles/com.netease.hdjygb

> Sorry for lack infomation. I attach second file of that skeleton in same folder. It may contain more information.

Thank you shakotay.
[act_10_01.zip](https://xentaxbackup.github.io/file/20434_act_10_01.zip)
## Post #5
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-07-09T13:36:07+00:00
- Post Title: How can I open this .skeleton and .anim file?

Here is another example of animations of that skeleton in anim folder...
[anim.zip](https://xentaxbackup.github.io/file/20438_anim.zip)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-09T16:51:47+00:00
- Post Title: How can I open this .skeleton and .anim file?

you could try to transform the following into an smd file, not too hard but tedious.
Looks like: bone_name, 3x3 rot matrix and position (x,y,z):

Bip001 Pelvis_20
-0.000001 1 0 
-1 -0.000001 0 
0 0 1 
0.011691 -0.078477 -0.679508 

-0.000001 1 0 
1 0.000001 0.000001 
0.000001 0 -1 
0.011692 -0.078474 0.679506 

0 0 -1 
0 1 0 
1 0 0 
0 0 0 

Bip001 Spine
-0.985412 -0.129717 0.11017 
0.141334 -0.984363 0.105142 
0.094808 0.119179 0.988336 
0 0.162846 0 

Bip001 L Calf
-0.985411 0.129719 0.11017 
-0.141337 -0.984362 -0.105145 
0.094808 -0.119182 0.988335 
0 -0.162846 0 

Bip001 R Calf
-0.96209 0 0.272733 
-0.000001 -1 -0.000003 
0.272733 -0.000004 0.96209 
-0.137526 0.000001 -0.218398 

Bip001 Pelvis_08
-0.946917 0.310298 0.084041 
-0.080026 0.025671 -0.996462 
-0.311357 -0.950293 0.000523 
-0.127151 -0.248158 0.002103 

Bip001 Pelvis_05
-0.999921 0.000001 0.012605 
-0.000001 -1 -0.000003 
0.012605 -0.000003 0.999921 
-0.071148 -0.000001 0.23435 

Bip001 Pelvis_02
-0.946918 -0.310296 0.084039 
-0.080026 -0.025665 -0.996462 
-0.311355 0.950294 0.000529 
-0.12715 0.248 0.002104 

Bip001 Pelvis_11
-0.999291 0.000001 -0.037645 
0.000001 1 0 
0.037645 0 -0.999291 
-0.119312 -0.000001 0.254926 

B_Acc02_bone
-0.953791 0.281306 -0.105594 
0.243678 0.518566 -0.819579 
-0.175795 -0.807438 -0.563152 
-0.122032 -0.167729 0.202 

Bone028
-0.948847 0.304348 0.084042 
-0.080026 0.025671 -0.996462 
-0.305428 -0.952215 -0.000003 
-0.125879 -0.248566 0.017935 

Bone022
...

But you'll need the complete list of bone names before, dunno why there are so many "pelvis" lines. 
edit: ok, Pelvis_08/Pelvis_02 seems to be mirrored, maybe it's upper_legs, left/right?
