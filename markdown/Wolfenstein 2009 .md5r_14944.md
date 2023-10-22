## Post #1
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-26T18:58:49+00:00
- Post Title: Wolfenstein 2009 .md5r

So the models in this game use .md5r, which seems to be a modification of quake 4 .md5.

I tried .md5 importers, but none worked.

I have a small sample here. If someone can figure out what makes these different from normal .md5s, it could help a lot.
[mg42.rar](https://xentaxbackup.github.io/file/11619_mg42.rar)
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-08-27T00:08:18+00:00
- Post Title: Wolfenstein 2009 .md5r

I never tried this tool but maybe can work

source:  [https://github.com/bquintero/MD5R2OBJ](https://github.com/bquintero/MD5R2OBJ)
[Release.rar](https://xentaxbackup.github.io/file/11620_Release.rar)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-27T03:27:47+00:00
- Post Title: Wolfenstein 2009 .md5r

mg42_md5r.png (24.1 KiB) Viewed 251 times
## Post #4
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-27T09:49:46+00:00
- Post Title: Wolfenstein 2009 .md5r

Wolf2obj extracted the models, but they came out broken.

That mesh extractor is a good start, but I kinda need them to be extracted with bones as well. The .md5r format is a modified .md5. Since we have mesh and animation converters for the normal .md5, I thought we could perhaps find a way to open this particular format.
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-08-27T20:49:50+00:00
- Post Title: Wolfenstein 2009 .md5r

[out]
## Post #6
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-27T22:45:20+00:00
- Post Title: Wolfenstein 2009 .md5r

It is based on md5mesh and anim since it's an upgraded version of the engine.
Atleast I think it is.
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-08-28T02:45:06+00:00
- Post Title: Wolfenstein 2009 .md5r

[out]
## Post #8
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-28T15:19:25+00:00
- Post Title: Wolfenstein 2009 .md5r

Well I cannot code for shit. I have literally 0 knowledge in this area, which is why I ask here. I work on modelling and mapping mostly.
Which one on github are you talking about?
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-08-28T15:37:44+00:00
- Post Title: Wolfenstein 2009 .md5r

[out]
## Post #10
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-28T16:26:01+00:00
- Post Title: Wolfenstein 2009 .md5r

I tried it before, meshes came out deformed and without bones.
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-08-28T17:46:27+00:00
- Post Title: Wolfenstein 2009 .md5r

[out]
## Post #12
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-29T22:07:19+00:00
- Post Title: Wolfenstein 2009 .md5r

Ah if you mean like that sure, now we have to hope someone picks it up.
## Post #13
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-11-19T16:28:57+00:00
- Post Title: Wolfenstein 2009 .md5r

Sorry to revive this thread, but, if it's not asking too much, could someone arrange a quickbms script for these models, or something along those lines.

I understand if I am asking too much.

Thanks in advance.
## Post #14
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-12-11T18:59:11+00:00
- Post Title: Wolfenstein 2009 .md5r

I ask once more, if someone wants to.
## Post #15
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2021-06-04T04:48:27+00:00
- Post Title: Wolfenstein 2009 .md5r

> Reply from luxox18 ↑Sat Aug 27, 2016 8:08 am at Sat Aug 27, 2016 8:08 am
>
> 
I never tried this tool but maybe can work

source:  https://github.com/bquintero/MD5R2OBJ


I can't get this tool to process the map files that are packed in .pk4 archive.

```
cwd: D:\DOWNLOADS\Release
parsing mp_rooftops.procb...
```

I tried all other maps, no luck. Models seems to work.
## Post #16
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-02-17T15:31:27+00:00
- Post Title: Re: Wolfenstein 2009 .md5r

I tried hex2obj and MD5R2OBJ but all meshes look garbage. Are there Blender or Noesis plugins that can fix character meshes?



bandicam 2023-02-17 07-22-56-075.jpg (72.74 KiB) Viewed 85 times



Samples:
[https://drive.google.com/file/d/1E2r34a ... share_link](https://drive.google.com/file/d/1E2r34aUppCNKFgR1QHwVPwBU2SbO1Iwk/view?usp=share_link)
[https://drive.google.com/file/d/1KJHmr2 ... share_link](https://drive.google.com/file/d/1KJHmr26JH_tzoNU7yapwNutn33O5eIrK/view?usp=share_link)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-17T20:25:49+00:00
- Post Title: Re: Wolfenstein 2009 .md5r

Yes, not too easy.  
I combined vertices from hex2obj with face indices from wolf2obj (MD5R2OBJ) and this is the result:
.



box_car-mdr5.png (24.52 KiB) Viewed 72 times
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-17T21:07:33+00:00
- Post Title: Re: Wolfenstein 2009 .md5r

Kuebelwagen.png (242.62 KiB) Viewed 69 times


(Sadly the patched wolf2obj gives too many qnans, partially.)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-18T02:21:41+00:00
- Post Title: Re: Wolfenstein 2009 .md5r

Anim files contain an ASCII skeleton plus binary data.
I cut the skel off and did some adjustions to meet the requirements of smd format:
.



body_nurse_skel.md5r.png (9.78 KiB) Viewed 63 times


But WHAT is this? I didn't touch the data itself, just separated the data and added a smd "frame".
I assume the rotation data is different from what smd "expects".

```
nodes
0 "origin" -1
1 "hips" 0
2 "l_upleg" 1
3 "l_knee" 2
4 "l_ankle" 3
5 "l_ball" 4
6 "r_upleg" 1
7 "r_knee" 6
8 "r_ankle" 7
9 "r_ball" 8
10 "waist" 0
11 "stomach" 10
12 "chest" 11
13 "shoulders" 12
14 "l_clavicle" 13
15 "l_uparm" 14
16 "l_bicep" 15
17 "l_elbow" 15
18 "l_forarm" 17
19 "l_wrist_ik" 17
20 "l_index_1" 19
21 "l_index_2" 20
22 "l_middle_1" 19
23 "l_middle_2" 22
24 "l_pinky_1" 19
25 "l_pinky_2" 24
26 "l_ring_1" 19
27 "l_ring_2" 26
28 "l_thumb_1" 19
29 "l_thumb_2" 28
30 "l_wpn_ctrl" 19
31 "neck" 13
32 "head" 31
33 "head_channel" 32
34 "inview_camera_ctrl" 33
35 "r_clavicle" 13
36 "r_uparm" 35
37 "r_bicep" 36
38 "r_elbow" 36
39 "r_forarm" 38
40 "r_wrist_ik" 38
41 "r_index_1" 40
42 "r_index_2" 41
43 "r_middle_1" 40
44 "r_middle_2" 43
45 "r_pinky_1" 40
46 "r_pinky_2" 45
47 "r_ring_1" 40
48 "r_ring_2" 47
49 "r_thumb_1" 40
50 "r_thumb_2" 49
51 "r_wpn_ctrl" 40
end
skeleton
time 0
0 0 0 0  -0.5 -0.5 -0.5
1 -0 -0 38.1829986572  0.5 -0.5 0.5
2 -0.0000004176 3.8708627224 36.1989784241  0.5085807443 -0.5085807443 0.4912694097
3 -0.5476119518 3.870860815 20.3894844055  0.5313433409 -0.5313433409 0.4665556848
4 -2.6156847477 3.870860815 4.5297665596  0.2339509577 -0.2339509428 0.6672832966
5 3.0505254269 3.8708598614 -0.0002414041  -0.0007219986 0.0007219985 0.7071064115
6 -0.0000005152 -3.8708589077 36.1989784241  0.5085807443 -0.5085807443 0.4912694097
7 -0.5476118922 -3.870860815 20.3894844055  0.5313433409 -0.5313433409 0.4665556848
8 -2.6156845093 -3.870860815 4.5297660828  0.2339509577 -0.2339509428 0.6672832966
9 3.0505254269 -3.8708598614 -0.0002414043  -0.0007219786 0.0007220186 0.7071064115
10 -0.0000007985 -0.0000019924 38.1830062866  -0.5217341185 -0.5217341185 -0.4772772193
11 0.5221601725 0.0000001222 44.0382423401  -0.4949281812 -0.4949281812 -0.5050209165
12 0.4133720994 -0.000000381 49.4268302917  -0.4501407743 -0.4501407743 -0.545319438
13 -0.561065197 -0.0000003863 54.4760055542  -0.3833087683 -0.3833087683 -0.5942006111
14 -1.0562121868 3.7179067135 55.3415794373  0.197090432 -0.7971971631 0.0136900302
15 -1.9707065821 6.5412368774 54.5860900879  0.3011398613 -0.5362804532 0.1057149768
16 -1.9707065821 6.5412368774 54.5860900879  0.3011398613 -0.5362804532 0.1057149768
17 -3.3560752869 13.5326356888 49.4585914612  -0.0208139997 -0.5481040478 0.4203710556
18 1.6904726028 18.7008991241 46.0110664368  -0.0208139997 -0.5481040478 0.4203710556
19 2.6369898319 19.6702461243 45.3644599915  -0.0208139997 -0.5481040478 0.4203710556
20 5.9653358459 21.5848999023 44.1632537842  0.7233980298 0.4997120202 -0.0056689247
21 6.8311433792 22.0106544495 43.3035545349  0.8324522972 0.2829134464 -0.1356895268
22 5.3629908562 22.1834697723 43.8457145691  0.6804249287 0.5661585331 -0.1608132124
23 6.1093053818 22.722826004 42.9122619629  0.8296058774 0.3086545467 -0.2964248955
24 3.8400723934 22.2080688477 43.2316856384  0.7202874422 0.5286515951 -0.2869329154
25 4.3885889053 22.4222507477 42.3805236816  0.8182404637 0.3588441014 -0.3553783596
26 4.6982297897 22.5889949799 43.5338478088  0.685521841 0.5363999605 -0.3327924907
27 5.2396783829 22.8939476013 42.511806488  0.8269938231 0.2715627551 -0.4362458289
28 4.5223226547 19.4882907867 44.2524261475  0.5149120688 0.2895844877 0.591768682
29 5.760207653 19.8225727081 43.7515602112  0.575715363 0.1341901422 0.4145435393
30 4.5997691154 21.5005512238 42.6420402527  0.8393440843 0.2467217147 -0.3372848928
31 -1.9004691839 -0.0000001034 57.4356765747  -0.5066490173 -0.5066490173 -0.4932613969
32 -1.8333097696 -0.0000009242 59.9433059692  -0.5549765229 -0.5549765229 -0.4381792545
33 -1.0713953972 0.0000009762 63.137878418  -0.6802355647 -0.6802355647 -0.1930791885
34 5.5839219093 0.0000040848 62.9480705261  -0.5 -0.5 -0.4999999702
35 -1.0562090874 -3.7179074287 55.3415870667  0.7971971631 -0.197090432 0.5704774857
36 -1.97070539 -6.5412373543 54.5860900879  0.5362804532 -0.3011398613 0.7813721299
37 -1.97070539 -6.5412373543 54.5860900879  0.5362804532 -0.3011398613 0.7813721299
38 -3.3560750484 -13.5326395035 49.4585952759  0.5481040478 0.0208140109 0.7227979302
39 1.6904728413 -18.7009010315 46.0110664368  0.5481040478 0.0208140109 0.7227979302
40 2.6369900703 -19.6702480316 45.3644561768  0.5481040478 0.0208140109 0.7227979302
41 5.9653315544 -21.584897995 44.1632614136  0.4763935506 -0.0056690997 0.4997122884
42 6.831143856 -22.0106506348 43.3035469055  0.4566960037 -0.1356896162 0.282913655
43 5.3629879951 -22.1834640503 43.8457069397  0.4366072118 -0.1608130336 0.5661583543
44 6.1093015671 -22.7228279114 42.9122619629  0.3586348891 -0.2964248657 0.3086543381
45 3.8400769234 -22.2080631256 43.2316818237  0.34551844 -0.2869328558 0.5286514759
46 4.3885812759 -22.4222507477 42.3805198669  0.2746265531 -0.3553783298 0.3588441014
47 4.6982359886 -22.5889911652 43.5338478088  0.3627452552 -0.3327924311 0.5363998413
48 5.2396807671 -22.8939476013 42.5117988586  0.2280888259 -0.4362458587 0.2715626955
49 4.5223221779 -19.4882965088 44.2524375916  0.5484669805 0.5917687416 0.2895846069
50 5.7602086067 -19.8225765228 43.7515602112  0.6918803453 0.4145435691 0.1341902465
51 4.5997667313 -21.5005512238 42.6420402527  -0.8450377584 0.2235819399 0.3510971069
end
```
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-02-18T02:44:15+00:00
- Post Title: Re: Wolfenstein 2009 .md5r

I have no idea what happened here:
.



head_fem_01_mesh-md5r.png (97 KiB) Viewed 57 times
