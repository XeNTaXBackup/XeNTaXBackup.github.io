## Post #1
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-06T03:06:43+00:00
- Post Title: Giana Sisters - Twisted Dreams

[http://www.mediafire.com/file/4y9agc8ck ... verted.zip](http://www.mediafire.com/file/4y9agc8ckueewk8/gianamodelsunconverted.zip)

So I dumped the raw files from the Game.Pak file and they all have the strange extension name ".86". I mainly want to get the models converted as while I have the animation files for Giana which contain some form of skeleton data, I can't seem to attach them to a ninjaripped model at all. I know for a fact these models were made in [3dsMax seeing as the video showing behind the scenes explicitly shows so.](https://www.youtube.com/watch?v=FHovZ4fBCJc)
Anybody know if they can get this loadable into 3dsMax?
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-06T12:42:24+00:00
- Post Title: Giana Sisters - Twisted Dreams

These the only type of files you got? Seems there's no geometry data but some skeletons probably.
## Post #3
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-07T03:05:59+00:00
- Post Title: Giana Sisters - Twisted Dreams

Yeah, sadly. However is it at least possible to get these to an importable format? Hopefully so I mesh the model into it?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-07T03:16:14+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> is it at least possible to get these to an importable format?
Maybe. But that's usually not what I care for. 
What did you use to dump these files? I sense it didn't extract all of them. 
You may need to upload the orginal archive.
## Post #5
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-07T04:11:50+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Bigchillghost
>
> Mario123311 wrote:is it at least possible to get these to an importable format?
Maybe. But that's usually not what I care for. 
What did you use to dump these files? I sense it didn't extract all of them. 
You may need to upload the orginal archive.
I used QuickBMS. I also tried a Python script just now as I scanned the Game.PAK archive only to find out in a hex editior that there are multiple instances of "OBJ" being mentioned. I think you are right...

I am uploading the archive right now considering I am stumped and it's not really giving me everything it seems. Granted this is the archive of the DEMO version but still, I want to at least get Giana's (the player's) model and possibly the common owl enemies. Nothing more than that, really.

EDIT: [http://www.mediafire.com/file/gjku1vncs8iniq1/Game.pak](http://www.mediafire.com/file/gjku1vncs8iniq1/Game.pak)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-07T07:59:08+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> 
I used QuickBMS.
If it's this script that you're using:
[http://aluigi.altervista.org/bms/helldorado.bms](http://aluigi.altervista.org/bms/helldorado.bms)

The .x86 files seem to be the only possible model files if there's only one pak archive for this game, while they seem to be encrypted or compressed. 
Have no idea why it would be like that especially when you've already extracted most of the assets(.fbx, .dds, .wav, etc.) correctly.
## Post #7
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-07T16:39:56+00:00
- Post Title: Giana Sisters - Twisted Dreams

Think you could at least get into a way to convert the skeleton data? I do have Giana's model hard-ripped, but the animation files like I said - I can't seem to find a way to actually use their skeleton data as bones for the model.

EDIT: I think I found the raw mesh data, However they don't mention the texture files at all.

[http://www.mediafire.com/file/64zo9sodh ... shdata.zip](http://www.mediafire.com/file/64zo9sodh2d6rrj/meshdata.zip)
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-07T17:31:47+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> Think you could at least get into a way to convert the skeleton data?
Not really.  Handling skeleton data is my next goal though. Still get a lot to learn.

> Reply from Mario123311
>
> I do have Giana's model hard-ripped, but the animation files like I said - I can't seem to find a way to actually use their skeleton data as bones for the model.
The ripped model apparently is different from the original one. It might have changed the vertices orders and torn the face buffer apart into several submesh groups. So the weights and bone indices simply won't match with them. And honestly I have no idea how you're supposed to fit the skeleton to a separate model without recombining them through some custom tools.

So unless you get the model from the binary data, I don't think it'll work.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-08T04:47:24+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> 
EDIT: I think I found the raw mesh data, However they don't mention the texture files at all.

http://www.mediafire.com/file/64zo9sodh ... shdata.zip
So I was right. There are other .pak archives. You should have mentioned it earlier.

Is this what you're looking for? 



giana.jpg (45.16 KiB) Viewed 750 times
## Post #10
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-09T01:30:04+00:00
- Post Title: Giana Sisters - Twisted Dreams

Yes, YES~

Those are exactly what I am looking for indeed. Really, I don't know how else to thank you, then again I typically am not very good when it comes to hex-editing. Which archive did you happen to find it in? Maybe there is a way to extract it?
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-09T01:49:38+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> Which archive did you happen to find it in?
You can find it in both rendermesh_ 0 and 1. But there are about 240 models inside 0. And the rest archives contain only vertices which I believe should be used by some vertex shaders.

> Reply from Mario123311
>
> Maybe there is a way to extract it?
Yeah. I've written a simple obj convertor for this format but I can't reach my laptop right now.
## Post #12
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-09T03:13:16+00:00
- Post Title: Giana Sisters - Twisted Dreams

I'm willing to wait, so don't worry about it. :3 If too much time passes, just be sure to PM me if possible. This script will really come in handy, and hopefully it works on Bubsy as well for that matter for those curious enough.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-09T05:04:36+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> This script will really come in handy
It's a command line tool written in C. Grab it here.


 GSTDConv.rar
(59.02 KiB) Downloaded 61 times


How to use: drag and drop one .bin.win32 file onto the tool, or run the following batch command:

```
for %%f in (*.win32) do GSTDConv.exe "%%f"
pause
```

It supports only rendermeshes, so there're only rendermesh_0.bin.win32 and rendermesh_1.bin.win32 that you can extract from.

> Reply from Mario123311
>
> and hopefully it works on Bubsy as well for that matter for those curious enough.
It might or might not. Currently I've only encountered 3 types of vertex formats in the samples you provided. So any other formats might possibly result in wrong outputs.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-09T10:30:39+00:00
- Post Title: Giana Sisters - Twisted Dreams

> Reply from Mario123311
>
> Think you could at least get into a way to convert the skeleton data?If you told us which x86 file Giana's skeleton is contained in I could have a look at.

(here's 0_00000004.x86 skeleton, DRAGON_INTRO_skeleton, with wings):



0_00000004-x86-skel.jpg (38.85 KiB) Viewed 704 times



.smd file:

```
version 1
nodes
0 "MOTION" -1
1 "REF_0" -1
2 "SPINE" 0
3 "LeftLegNew_1" 2
4 "RightLegNew_1" 2
5 "Spine_0" 2
6 "Tail_0" 2
7 "LeftLegNewUpTwist_0" 3
8 "RightLegNewUpTwist_0" 4
9 "Spine_1" 5
10 "Tail_1" 6
11 "LeftLegNew_2" 7
12 "RightLegNew_2" 8
13 "Spine_2" 9
14 "Tail_2" 10
15 "LeftLegNew_3" 11
16 "RightLegNew_3" 12
17 "SchwabbelBelly" 13
18 "Spine_3" 13
19 "Tail_3" 14
20 "LeftLegNewToeBase" 15
21 "RightLegNewToeBase" 16
22 "Spine_4" 18
23 "Tail_4" 19
24 "LeftleftToe" 20
25 "LeftmidToe" 20
26 "LeftrightToe" 20
27 "RightleftToe" 21
28 "RightmidToe" 21
29 "RightrightToe" 21
30 "LeftArm2_1" 22
31 "LeftSchwabbelBreast" 22
32 "Neck_0" 22
33 "RightArm2_1" 22
34 "RightSchwabbelBreast" 22
35 "LeftArm2UpTwist_0" 30
36 "LeftWing1" 32
37 "Neck_1" 32
38 "RightWing1" 32
39 "RightArm2UpTwist_0" 33
40 "LeftArm2_2" 35
41 "LeftWing2" 36
42 "Neck_Head" 37
43 "RightWing2" 38
44 "RightArm2_2" 39
45 "LeftArm2LowTwist_0" 40
46 "LeftWing3" 41
47 "Jaw" 42
48 "LeftBrow1" 42
49 "LeftBrow2" 42
50 "LeftEyeball" 42
51 "LeftLipUpperMid" 42
52 "LeftLipUpperOuter" 42
53 "LeftLowerEyelid" 42
54 "LeftLowerEyelid2" 42
55 "LeftNostril1" 42
56 "LeftNostril2" 42
57 "LeftUpperEyelid" 42
58 "LeftUpperEyelid2" 42
59 "LipUpperInner" 42
60 "RightBrow1" 42
61 "RightBrow2" 42
62 "RightEyeball" 42
63 "RightLipUpperMid" 42
64 "RightLipUpperOuter" 42
65 "RightLowerEyelid" 42
66 "RightLowerEyelid2" 42
67 "RightNostril1" 42
68 "RightNostril2" 42
69 "RightUpperEyelid" 42
70 "RightUpperEyelid2" 42
71 "RightWing3" 43
72 "RightArm2LowTwist_0" 44
73 "LeftArm2_3" 45
74 "LeftWing3_11" 46
75 "LeftWing3_21" 46
76 "LeftLipLowerMid" 47
77 "LeftLipLowerOuter" 47
78 "LipLowerInner" 47
79 "RightLipLowerMid" 47
80 "RightLipLowerOuter" 47
81 "Tounge1" 47
82 "RightWing3_11" 71
83 "RightWing3_21" 71
84 "RightArm2_3" 72
85 "LeftHandIndex_0" 73
86 "LeftHandMiddle_0" 73
87 "LeftWing3_12" 74
88 "LeftWing3_22" 75
89 "Tounge2" 81
90 "RightWing3_12" 82
91 "RightWing3_22" 83
92 "RightHandIndex_0" 84
93 "RightHandMiddle_0" 84
94 "LeftHandIndex_1" 85
95 "LeftHandMiddle_1" 86
96 "LeftWing3_13" 87
97 "Tounge3" 89
98 "RightWing3_13" 90
99 "RightHandIndex_1" 92
100 "RightHandMiddle_1" 93
101 "LeftHandIndex_2" 94
102 "LeftHandMiddle_2" 95
103 "RightHandIndex_2" 99
104 "RightHandMiddle_2" 100
end
skeleton
time 0
0  0.000000 0.000000 0.000000  0.000000 1.570796 0.000000
1  0.000000 0.000000 0.000000  -1.570796 -0.000000 0.000000
2  0.000000 197.315872 360.962708  0.768062 -0.000000 0.000000
3  183.477081 -58.828117 57.657276  1.095968 -0.514215 -1.232365
4  -183.477005 -58.827747 57.657661  -2.112998 0.361111 1.121518
5  0.000000 36.618622 67.178520  -1.570796 -0.993661 1.570796
6  1.656136 7.861646 -43.977188  2.241531 1.053901 2.420019
7  62.003166 -0.000000 0.000000  -0.163389 0.000000 0.000000
8  -62.003506 0.000669 0.000607  -0.058479 0.000000 -0.000000
9  21.243019 27.889320 0.000000  0.029962 -0.127416 -0.062600
10  199.138519 82.649940 18.000420  -0.342274 0.852711 0.107343
11  186.865234 0.000000 -0.000000  -0.328765 0.619770 -2.101843
12  -186.864624 -0.000414 -0.000529  -0.072074 0.365242 -1.770248
13  85.177055 -0.000000 0.000000  -0.034585 0.109577 -0.285447
14  231.887070 -27.282337 -0.000000  -1.038179 0.550738 -1.190199
15  210.393921 -0.000000 0.000000  -0.282738 -0.317046 0.206048
16  -210.394043 -0.000400 0.000562  -0.096074 -0.110605 -0.046681
17  26.316948 -356.441986 0.000000  0.000000 1.570451 0.000000
18  78.876122 -37.603687 0.000000  0.049862 0.030127 -0.087274
19  220.833252 0.000000 -0.000000  -0.175036 0.867514 0.077946
20  62.046978 151.104141 22.390455  0.032568 -0.124927 0.795904
21  -62.046993 -151.103973 -22.390923  0.013077 -0.128421 0.949889
22  86.237221 -6.182445 0.000000  -0.035141 -0.101757 0.017651
23  220.833252 0.000000 0.000000  -0.151212 0.857507 0.111035
24  -10.061495 1.722162 71.482498  0.152656 1.137368 0.303844
25  10.555599 8.097599 0.204237  2.507188 1.462835 2.675087
26  -13.324170 15.942491 -65.490402  2.958544 1.212318 3.135060
27  10.061648 -1.722181 -71.482704  0.152656 1.137368 0.303844
28  -10.555517 -8.097600 -0.204424  2.507188 1.462835 2.675087
29  13.324328 -15.942437 65.490257  2.958544 1.212318 3.135060
30  61.779079 -3.081566 -133.109436  -0.891117 0.731468 -2.145374
31  66.871231 -183.383377 -86.771736  2.934389 0.975780 2.000780
32  78.428207 -9.982084 14.018810  -0.133761 0.144847 -0.452558
33  61.779030 -3.081309 133.108994  -1.909438 0.893657 -0.168627
34  66.871231 -183.383377 86.771736  -2.934389 -0.975780 2.000780
35  61.341255 0.000000 -0.000000  -0.451258 -0.000000 0.000000
36  -75.546349 108.651344 -66.341805  2.114413 0.661749 1.799386
37  69.016762 0.000000 -0.000000  0.000000 0.000000 -0.000000
38  -75.546410 108.651009 66.744003  2.114413 0.661749 -1.342206
39  -61.341717 -0.000313 -0.000027  0.061772 0.000000 0.000000
40  40.193710 -0.000000 0.000000  -0.620526 -0.816780 0.480290
41  63.506222 -16.810806 -6.225982  0.211748 -0.044535 0.058658
42  -0.000000 0.000000 -0.000000  0.492215 0.258422 0.123264
43  -63.506310 16.810337 6.226064  0.211748 -0.044535 0.058658
44  -40.193943 0.000002 0.000292  0.267731 -1.173426 -0.247746
45  30.248343 -0.000000 0.000000  0.469056 0.000000 0.000000
46  83.205086 42.049797 9.869717  0.273400 -0.123739 0.589744
47  89.862541 -9.323002 0.315674  2.649387 1.559052 2.259005
48  234.874649 -21.493223 -75.199654  0.735251 0.833722 -0.165182
49  204.390579 15.872798 -100.235390  0.420879 1.030333 0.183113
50  193.408218 -26.488466 -67.440834  -1.637870 -0.053473 -0.729932
51  231.745667 -162.842606 -64.478851  0.119128 1.122653 -0.632675
52  168.826340 -69.256996 -99.852020  0.432600 1.279963 -0.582495
53  201.202942 -54.776707 -79.837440  -0.414829 0.529059 -1.081382
54  181.300079 -34.807110 -92.819344  -1.670827 1.059987 -2.679844
55  281.443695 -110.140648 -52.570045  -1.307162 0.697655 -2.642497
56  287.355591 -165.361374 -40.063473  -1.528291 0.671097 -2.920946
57  221.204865 -37.527470 -82.518105  0.096809 0.954381 -0.801635
58  198.008682 -23.520573 -98.981468  -0.280924 1.226508 -0.808993
59  294.967285 -199.322403 0.201103  -0.000000 -0.000000 -0.632963
60  234.874908 -21.493246 75.601906  0.735251 0.833722 2.976411
61  204.390854 15.872795 100.637100  0.420879 1.030333 -2.958479
62  193.408218 -26.488466 67.843048  1.503723 -0.053473 -0.729932
63  231.794312 -143.679306 70.016930  -0.000000 -1.345989 -0.632963
64  160.351257 -74.949219 100.136185  0.000000 -1.329627 -0.632963
65  210.576065 -58.759972 75.050003  -0.168603 0.775716 2.718020
66  180.092438 -36.768578 98.062004  1.622924 1.317652 -2.313493
67  281.444244 -110.140633 52.972202  -1.307162 0.697655 0.499096
68  287.355072 -165.361603 40.465702  -1.528291 0.671097 0.220647
69  222.757507 -32.944771 75.141403  0.474666 0.923381 2.492942
70  204.644562 -11.921675 98.957207  -0.423862 1.221208 2.301353
71  -83.204994 -42.049828 -9.869679  0.273400 -0.123739 0.589744
72  -30.248123 0.000019 -0.000502  -0.035231 -0.000000 0.000000
73  28.733236 0.000000 -0.000000  0.000000 0.000000 -0.810941
74  37.108231 -32.317722 -1.595227  -0.083180 0.138073 -1.288089
75  -28.627552 -29.643560 -7.027029  -0.041847 0.052645 -1.481251
76  60.778301 -107.867310 181.653687  0.000000 -0.543056 -0.000000
77  98.456528 -57.683548 121.580978  0.143826 -0.199506 0.013958
78  -0.000000 -110.221428 244.903397  -1.570796 -1.466250 1.570796
79  -61.107689 -94.537857 189.991653  -3.119785 -0.272817 3.084643
80  -98.647789 -59.699951 119.473381  3.141593 -0.169736 -3.141593
81  -0.000000 -82.091072 34.889473  -0.324990 -0.000000 0.000000
82  -37.108715 32.318062 1.594886  -0.083180 0.138073 -1.288089
83  28.627712 29.643982 7.026526  -0.041847 0.052645 -1.481251
84  -28.733538 -0.000079 -0.000143  -0.008151 -0.091178 0.178201
85  39.172543 -5.014783 13.235258  0.785937 -0.238801 -0.113896
86  39.355934 0.989481 -12.940097  -0.944589 0.409622 -0.297971
87  66.300766 9.481778 -2.339839  0.007561 0.018119 -0.087282
88  43.399082 -4.656626 0.207219  -0.152436 -0.050447 -0.349064
89  -0.000000 -12.461084 75.019089  0.258654 -0.000000 0.000000
90  -66.300446 -9.481553 2.340160  0.007561 0.018119 -0.087282
91  -43.399071 4.656708 -0.207131  -0.152436 -0.050447 -0.349064
92  -39.172718 5.015209 -13.235213  0.323326 -0.130723 -0.201262
93  -39.355988 -0.989424 12.940157  0.130203 0.196924 -0.233645
94  48.688549 0.000000 -0.000000  0.000000 -0.000000 -1.141901
95  47.901009 -0.000000 -0.000000  0.028678 -0.005714 -1.000894
96  83.267868 -1.001770 0.402264  -0.059989 -0.012339 -0.119787
97  0.000000 -8.763008 58.737389  0.246638 -0.000000 0.000000
98  -83.268127 1.001476 -0.402405  -0.059989 -0.012339 -0.119787
99  -48.688393 -0.000760 0.000566  0.000000 -0.000000 -0.927226
100  -47.901577 -0.000252 0.000036  0.027042 -0.011127 -0.807231
101  62.872612 -0.000000 -0.000000  3.141593 -0.000000 -0.090867
102  61.034996 0.000000 0.000000  -0.077481 0.009802 -0.048692
103  -62.872753 0.000243 0.000144  3.141593 -0.000000 -0.090867
104  -61.035275 0.000405 -0.000420  -0.077481 0.009802 -0.048692
end
```
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-09T20:29:30+00:00
- Post Title: Giana Sisters - Twisted Dreams

Maria, 252 bones, mostly hair_xx_y:



0_00000014-x86-Maria_smd.jpg (69.39 KiB) Viewed 684 times
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-09T21:42:07+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

> Reply from shakotay2
>
> Maria, 252 bones, mostly hair_xx_y:
I actually watched a gameplay video after seeing that. No wonder the hair physics look good  Still bit of an overkill for a game like that imo.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-10T17:50:18+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

I was surprised, too, but
maybe this is one of the things the developers thought would make their game "special"?
## Post #18
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-11T04:44:26+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

I found two files with the "CUTE SKELETON" name, but the files themselves seem to be slightly different. I assume Punk Giana's skeleton is basically just a duplicate of her basic cute skeletal file with added bones for a ponytail. 

Hopefully these are the right ones. I know the anim graph that comes in the Game.Pak shows this definently had to do with Giana's model herself.

[http://www.mediafire.com/file/2qwqat696e2t1zl/skel.zip](http://www.mediafire.com/file/2qwqat696e2t1zl/skel.zip)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-11T20:44:12+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

Cute from 0_00000038.x86 has the same bone names as Maria.



Cute-0038-x86.jpg (65.13 KiB) Viewed 306 times
## Post #20
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2018-04-13T03:00:00+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

Mind if I have the converted skeleton files at all in that case? Depending on if it's a converted file or if you used a script to load it into blender there... I'm honestly rather excited to see if I can get the mesh to work with it.
## Post #21
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-07-21T19:58:48+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

I'm sorry for the bump.
Concerning the useful GSTDConv tool, is it possible to make it an FBX convertor instead of an OBJ? Because OBJ files can't support skeleton and bones so this is why we can't rig some part of the character models. I could post the models to Model Resources so everyone can have the posable models, instead of doing everything by themself.
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-22T10:20:57+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

> Reply from GianaSistersFan64 ↑Wed Jul 22, 2020 3:58 am at Wed Jul 22, 2020 3:58 am
>
> 
Concerning the useful GSTDConv tool, is it possible to make it an FBX convertor instead of an OBJ? Because OBJ files can't support skeleton and bones so this is why we can't rig some part of the character models.
You know, making it an FBX convertor won't make any difference. The feature you're asking for requires further work on the skin info.
## Post #23
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-07-22T10:51:08+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

> Reply from Bigchillghost ↑Wed Jul 22, 2020 6:20 pm at Wed Jul 22, 2020 6:20 pm
>
> 
GianaSistersFan64 wrote: ↑Wed Jul 22, 2020 3:58 am
Concerning the useful GSTDConv tool, is it possible to make it an FBX convertor instead of an OBJ? Because OBJ files can't support skeleton and bones so this is why we can't rig some part of the character models.

You know, making it an FBX convertor won't make any difference. The feature you're asking for requires further work on the skin info.

But isn't there a way to extract the skeletons and (if possible) attach them to the models?
## Post #24
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-08-14T01:14:01+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

I'm finding that only the 'Rise of the Owlverlord' archives result in any 'rendermesh' archives when the level pak's are extracted. I can't find any in the actual 'Twisted Dreams' files...
## Post #25
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-14T07:24:44+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

Update to the GSTD rips :
Maybe going to the other port could be easier to get the models from the game, like the Switch port. I managed to find the rom of the game online and extracted it with the required tools. The files are organised like in the original version, except Game.pak is splited in many pak files. However, there is an issue...



Some of them are compressed differently so we can't use the helldorado QuickBMS script to decompress them.
Here's a sample file using the different compression, which you can analyse it : [http://www.mediafire.com/file/ljvydxwch ... s.zip/file](http://www.mediafire.com/file/ljvydxwch1it7mf/animations.zip/file)
Helps would be very appreciated! 

EDIT : This was sloved.
## Post #26
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-22T10:12:24+00:00
- Post Title: Re: Giana Sisters - Twisted Dreams

I extracted a level pak on the Switch version and i didn't find any rendermesh files, so Rise of the Owlverlord is not the only one.
BUT!!!
I found 4 rendermesh files in another pak file, and they are very big so i'm guessing these must contains all the models of the game. Using the convertor don't give much anything, all i got was a weird looking model and a giant vine. The extentions are different, instead of being win32 files, they are nx files so that's probably why we get nothing interesting by using the convertor.
Here are the files : [http://www.mediafire.com/file/tk1ec4sw6 ... s.zip/file](http://www.mediafire.com/file/tk1ec4sw6m8gbxn/GSTDOE_rendermesh_files.zip/file)
