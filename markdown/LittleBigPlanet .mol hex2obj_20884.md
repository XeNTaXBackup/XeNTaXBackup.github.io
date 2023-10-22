## Post #1
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-07-31T09:13:50+00:00
- Post Title: LittleBigPlanet .mol hex2obj

I need help with LittleBigPlanet models.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-31T11:20:37+00:00
- Post Title: LittleBigPlanet .mol hex2obj

sonic_hr.mol is compressed - use offzip for example
## Post #3
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-07-31T11:43:54+00:00
- Post Title: LittleBigPlanet .mol hex2obj

> Reply from shakotay2 ↑Wed Jul 31, 2019 7:20 pm at Wed Jul 31, 2019 7:20 pm
>
> 
sonic_hr.mol is compressed - use offzip for example I think i got it to work [https://imgur.com/UWuWph4](https://imgur.com/UWuWph4) So after that i just open the 4 files and figure the addresses out?



[https://imgur.com/PHEEqVK](https://imgur.com/PHEEqVK) i got sonic's right ear
## Post #4
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-01T07:12:58+00:00
- Post Title: LittleBigPlanet .mol hex2obj

This might be hard than the other one i did i think the ending might be 4E50?
## Post #5
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-01T08:38:31+00:00
- Post Title: LittleBigPlanet .mol hex2obj

> Reply from shakotay2 ↑Wed Jul 31, 2019 7:20 pm at Wed Jul 31, 2019 7:20 pm
>
> 
I think the ending for the Faces is 0004E50. That's my guess
## Post #6
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-01T09:11:38+00:00
- Post Title: LittleBigPlanet .mol hex2obj

shakotay2 i think i got the Face's start address correct but i need to find the ending.

0x0000026E is where the start i think should be.
[SonicModel1.PNG](https://xentaxbackup.github.io/file/16556_SonicModel1.PNG)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-01T13:33:21+00:00
- Post Title: LittleBigPlanet .mol hex2obj

noone will understand what you're talking about if you don't upload the .dat file in question
## Post #8
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-01T16:31:36+00:00
- Post Title: LittleBigPlanet .mol hex2obj

[https://drive.google.com/open?id=1-o6T9 ... eIY4iZxTwu](https://drive.google.com/open?id=1-o6T9qPh7pt4jp02GVgiZ-eIY4iZxTwu) There it's the same file that i had problems with
## Post #9
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-02T03:57:07+00:00
- Post Title: LittleBigPlanet .mol hex2obj

Does this mean anything?
[soniclbp.PNG](https://xentaxbackup.github.io/file/16557_soniclbp.PNG)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-02T05:45:19+00:00
- Post Title: LittleBigPlanet .mol hex2obj

(I can't access the inked drive in your post as of Thursday.)

> Reply from sonicdude143 ↑Fri Aug 02, 2019 11:57 am at Fri Aug 02, 2019 11:57 am
>
> 
Does this mean anything?compressed size of data block -> uncompressed sodb / start of data block I guess
## Post #11
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-02T05:49:11+00:00
- Post Title: LittleBigPlanet .mol hex2obj

So, we found the start then the ending might be close
[https://mega.nz/#!Zj5y1ACL!Z13w6fH5z5Pb ... K1XPZRw5dc](https://mega.nz/#!Zj5y1ACL!Z13w6fH5z5PbBwEVvwIROwVSkgfqartWiK1XPZRw5dc)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-02T08:18:00+00:00
- Post Title: LittleBigPlanet .mol hex2obj

00000025.dat:
0x026E is not start of FIs because 0x0260 is start of vertices.

My guess that FIs might be here <>:
00002860   00 00 FF 0C 5D B2 <42 00>  53 F2 64 00 DC 19 <6E 00>

is wrong, too, because the highest FI (0x25A) can't be found in the block up to 0x4E60.
## Post #13
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-02T08:44:24+00:00
- Post Title: LittleBigPlanet .mol hex2obj

> Reply from shakotay2 ↑Fri Aug 02, 2019 4:18 pm at Fri Aug 02, 2019 4:18 pm
>
> 
00000025.dat:
0x026E is not start of FIs because 0x0260 is start of vertices.

My guess that FIs might be here <>:
00002860   00 00 FF 0C 5D B2 <42 00>  53 F2 64 00 DC 19 <6E 00>

is wrong, too, because the highest FI (0x25A) can't be found in the block up to 0x4E60.

So, you're right about the Start of FI 0x3154? Wait maybe i was wrong about it
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-02T18:15:23+00:00
- Post Title: LittleBigPlanet .mol hex2obj

You need to understand the format of the block at 0x2860, probably uv data:

```

( one line represents 16 bytes in the model file )
Values are shown in decimal notation.
startaddress taken from go1 editbox
address 0x2860:
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292   342  3072 32549 23040  2906 55296 
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292 23200 35328 23568 33792 30952  4096 
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292 23024 31744 23472 23552   520  3584 
    0 65292 20784 20480 20752 20992 64392  2048 
    0 65292 23986 16896 21490 25600 56345 28160 
    0 65292   570 35840 32619 49152 60858 23552 
    0 65292 28989  7168 29085  5120 63656 47104 
    0 65292 26976  8704 26896  8704 64728  1536 
    0 65292 28416     0 28336     0 65416  1024 
    0 65292 28882 23040 28786 23552   904 28160 
address 0x2960:
    0 65292 36505 26112 36873 10752 

...

address 0x4c10:
    0 65292 40195 27648 39554 58880 52228 29696 
    0 65292 36966  7680 37926 38912 22724 52224 
    0 65292 63687 46592 64263 48640 24065  8704 
    0 65292  2407 57344  2471 56832 26431 54784 
    0 65292 27201 42496 27121 42496  1000 17408 
    0 65292 23858 17408 24065 59904 28056 28672 
    0 65292 23024 31744 23472 23552   520  3584 
    0 65292 20784 20480 20752 20992 64392  2048 
    0 65292 23200 35328 23568 33792 30952  4096 
    0 65292 24910 64512 24863 48128 59529  4096 
    0 65292 26923 19968 27915 24064 64665 59904 
    0 65292 27152 14848 28845 37376 63080  7168 
    0 65292  2927 59904   750 22528 31544  2048 
    0 65292  5668 11264  5686 13312 30825 40448 
    0 65292 31461  1024 29765 57856  1145 55296 
    0 65292 31507 63488 31652  6144 29097 12288 
address 0x4d10:
    0 65292  3154 51712  2563 23552 29864 49664 
    0 65292  5332 43520  4836 39936 32441 49664 
    0 65292  9620 10240  9044  7680  1721 35840 
    0 65292 11204  9216 11188  2560  1769 56832 
    0 65292 11204  9216 11188  2560  1769 56832 
    0 65292   439 41984  3431 44032  1677 44032 
    0 65292 33431 57344 36599 50176  1761 15872 
    0 65292  6613 38912  6678 53248   298 53760 
    0 65292 32663 58368    39 48640    94 49152 
    0 65292  2951 45568  3271 32768  1822 16896 
    0 65292  5751 17408  5943 11776  2125 49664 
    0 65292 64919 26112 65095 29184 31842 64512 
    0 65292 63559  1536 63895 23552 32307 44032 
    0 65292 62262 52224 62375  5632 31107 51712 
    0 65292 62006 51712 61463  9216  1428  2560 
    0 65292  4280 22528  4232 28672 32783  4096 
address 0x4e10:
    0 65292 60866 24576 62243 18432 47730 62464 
    0 65292 12336     0 12288     0 32584  1024 
    0 65292 39872     0 39920     0  9494  7168 
    0 65292 39232     0 39216     0  4487 40960 
    0 65292 38368     0 38496     0  2023 60416 

```


We've an interesting point cloud with this H2O file:

0x0 500
Vb1
16 99
0x260 603
121000
0x0 255

----------------------------

The FIs are - as assumed by me in a PM - in a different file (found them in 0000c890.dat).
You can get the FIs and only the FIs using this H2O file (ignore the mesh!):

0x1 340
Vb1
6 99
0x260 608
121410
0x0 255

-----------------
(Someone should write a bms script to unzip the mol files properly.)
------------------

combining above mentioned point cloud and FIs gives this:
.



00000025.dat.test.png (52.06 KiB) Viewed 220 times

(about 5 zero vectors added: v 0.0 0.0 0.0)
(I'm off now, too much time spent with this.)
## Post #15
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-02T21:58:13+00:00
- Post Title: LittleBigPlanet .mol hex2obj

Has anyone tried to make a bms for extracting MSHb format?
## Post #16
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-11T23:35:59+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

I was searching through BetaVest's models 00000019.dat and i found this
And i remember in the tutorial find scrambled alphabet
EDIT( i found more scrambled alphabet before that
[https://mega.nz/#!5ihhnQKZ!pXKlD8EqleSf ... itfhWdrF6M](https://mega.nz/#!5ihhnQKZ!pXKlD8EqleSfQgxqqMbGIL9AV9XLDv5OFitfhWdrF6M)
EDIT#2 Found what i think is the FIs 
[https://imgur.com/a/lcRDQmw](https://imgur.com/a/lcRDQmw)
[bEta.PNG](https://xentaxbackup.github.io/file/16595_bEta.PNG)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-12T20:44:12+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Try out this H2O file:

0x4690 541
Vb1
16 99
0x248 312
121010
0x0 255
## Post #18
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-17T01:26:11+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

> Reply from shakotay2 ↑Tue Aug 13, 2019 4:44 am at Tue Aug 13, 2019 4:44 am
>
> 
Try out this H2O file:

0x4690 541
Vb1
16 99
0x248 312
121010
0x0 255
You are a very helpful, person and i can't believe, i found the start of the FIs Thank you.
## Post #19
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-17T07:44:16+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

So far, i got the model uvs alright it looks decent.
[Betates.PNG](https://xentaxbackup.github.io/file/16602_Betates.PNG)
## Post #20
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-17T17:51:32+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Alright since you have been helping me i did the Walker model and i got everything right
[mesh_viewer 2019-08-17 12-50-00-51.png](https://xentaxbackup.github.io/file/16607_mesh_viewer 2019-08-17 12-50-00-51.png)
## Post #21
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-18T00:47:33+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

One more thing before we celebrate, basically from looking at the Beta Vest 00000019.dat the Vertices start at 0x248 and the start of FI 0x4690 00 02 03 00 which from little bit of hex knowledge in my brain for single meshes this right here ‰.Š. if you see this it's the ending which that's what i got for my Walker Body model i think it's for some models. I just need one help with these kind of models. With the 2 ________.dat files when i export them forgot  to add a link  [https://mega.nz/#!Y2phEaZS!tQgFJ666DdRp ... FOACkgBYco](https://mega.nz/#!Y2phEaZS!tQgFJ666DdRpkI5D4qTC4XKyI_nofwd9vFOACkgBYco)
[https://mega.nz/#!0nwz1Qwa!IQ_p6LI7l8-h ... SscpKOBJ8Q](https://mega.nz/#!0nwz1Qwa!IQ_p6LI7l8-hUInd1TbRP4GQg144DrTN3SscpKOBJ8Q)
[WalkerHead.PNG](https://xentaxbackup.github.io/file/16608_WalkerHead.PNG)
## Post #22
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-18T04:20:45+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

I got another model finished
sonic_hd.mol(00000019.dat)

0x7250 998
VB1
16 99
0x248 512
1210
[SonicHands.png](https://xentaxbackup.github.io/file/16610_SonicHands.png)
## Post #23
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-20T21:56:40+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hmm, i had a idea what if i make a .mol extractor which you need the data.farc and the blurayguids.map and you can view the textures and export models and textures
## Post #24
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-24T01:23:24+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, uh i have one more problem can't really seem to find UVs [https://mega.nz/#!AzAA3QQY!v39HIrG2r_mT ... MBA53cqdDE](https://mega.nz/#!AzAA3QQY!v39HIrG2r_mT9ewK20h9dHjP1u0k_CYsOMBA53cqdDE) i just have the model but i just need some help with UVs that come with the model
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-24T08:22:08+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

0x4150 650
Vb1
16 99
0x248 287
121010
0x2654 24
## Post #26
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-08-25T06:00:05+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Alright, i finally finished my goals 1 know about the models format and it's data 2 finally learned, how to do it myself 3 finally finishing the model.
Thank you for the help and support you gave me, i am happy and now thanks to you i learned alot about Hex2Obj and the funny, thing is i'm 13 and thank you.  
[ALBP.png](https://xentaxbackup.github.io/file/16652_ALBP.png)
## Post #27
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2019-09-21T01:00:12+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Been a long time i actually got some more models finished plus i got a tool that can extract it easy but i still use hex2obj for some models
## Post #28
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-01-11T20:44:30+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, it's been while hasn't it? I am having trouble finding UVs, I tried my count 1360 x 24 = 7F80 and took that minus, the FI 10131


(Note this .mol file is actually decompiled, like how offzip is.)
'
[https://drive.google.com/file/d/11y1RBF ... sp=sharing](https://drive.google.com/file/d/11y1RBFRfCl6rKCnvIjayYat_V8hwRLCu/view?usp=sharing)

My h2o 

0x10131 1734
Vb1
16 99
0x22B 1360
121010
0x81B1 24

I got other UVs right for sonic_hr.mol and stuff with success LBP2 models are hard.
[mesh_viewer 2020-01-11 14-43-14-89.png](https://xentaxbackup.github.io/file/17328_mesh_viewer 2020-01-11 14-43-14-89.png)
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-11T21:48:52+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

try this:
.



grapple_hook-mol.png (42.12 KiB) Viewed 64 times


well, for the values: 0xAC2E= 0x22B + (2 x 1360 x 16 +3) dec.   (don't asks me for details...)
## Post #30
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-01-11T22:08:43+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Thank you :3
## Post #31
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-01-14T03:41:59+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Alright, sorry to bother you and not asking for details. But is there a way to get UVs? I tried different methods, 

1 1336 x 24 = 0x12e87 - 0x7D40 = 0x12E87‬ which doesn't work I tried your method 

2. 2 x 1336 x 16 +3 = 0xA703 + 0x22b. Yes, I did try dec, and so on I tried many methods which looks almost it but jumbled mess.

[https://drive.google.com/file/d/17Ij731 ... sp=sharing](https://drive.google.com/file/d/17Ij7312Y2FDdkXm3Crw-Xvi2yUHxbnb-/view?usp=sharing)

Here's the model. Can you explain for the UVs, sorry for bothering you.
0x12E87 822
Vb1
16 99
0x22B 1336
121010
0x8782 20
[mesh_viewer 2020-01-13 21-40-56-25.png](https://xentaxbackup.github.io/file/17348_mesh_viewer 2020-01-13 21-40-56-25.png)
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-14T09:07:29+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

> Reply from sonicdude143 ↑Tue Jan 14, 2020 11:41 am at Tue Jan 14, 2020 11:41 am
>
> I tried your method 

2. 2 x 1336 x 16 +3 = 0xA703 + 0x22b. Yes, I did try dec,0xA703 + 0x22B = 0xA92E  
(UVBsize is 24 here, though. It's rather obvious looking into the hexdata, with some experience.)
.



direct_control_seat.mol.png (55.19 KiB) Viewed 125 times
## Post #33
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-01-14T12:37:41+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Alright, I am good to go for now.
## Post #34
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-01-14T22:15:42+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Alright, tried your method two times for different models lbp_badge.mol UVs worked!

and googly_star.mol too! Here it is I think I might make a doc of how to extract, these models.
[https://imgur.com/a/jkpLUvD](https://imgur.com/a/jkpLUvD)
## Post #35
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-02-22T06:10:08+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, I got a question does sackboy have extra UVs for to map out decals like the zipper, or stitching? Me and my friend, are fixing the sackboy model. Which he extracted. I taught him alot of things that you taught me.
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-22T09:45:16+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

> Reply from sonicdude143 ↑Sat Feb 22, 2020 2:10 pm at Sat Feb 22, 2020 2:10 pm
>
> 
Hey, I got a question does sackboy have extra UVs for to map out decals like the zipper, or stitching?Hey, I don't have that sackboy file (*.mol, *.dat?)

> Me and my friend, are fixing the sackboy model. Which he extracted. I taught him alot of things that you taught me.Cool!
## Post #37
- Username: Marshivolt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 22, 2020 6:47 pm
- Post datetime: 2020-02-22T10:55:57+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hi! I'm the friend sonicdude143 mentioned, Here's the model file:
[https://www.dropbox.com/s/jsq5hv98qwg1j ... y.mol?dl=0](https://www.dropbox.com/s/jsq5hv98qwg1jcy/sack_boy.mol?dl=0)
I already decompressed it with Offzip, This is the file we were trying to grab the stitches and zipper UVs out of.
If it helps any, Here's what we've figured out so far for Sackboy's normal UVs:
Face Indices:
Start Address: 172E04 Count: 4697
UVs:
FVF Size: 16 UV Position: 99
Start UVB: 161C40 Size UVB: 24
Vertices:
Start Address: 2BC Count: 2920
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-22T11:34:28+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Ahh, yeah, see, I have a deja vue. Had to search for "sack_boy" on my drive:
.

> Reply from shakotay2 ↑Sun Mar 15, 2015 4:44 pm at Sun Mar 15, 2015 4:44 pm
>
> 

Try 0x161c48 and 0x161c50 as a second/third uv start address:
.



sack_boy_uvs_2_3.png (25.7 KiB) Viewed 99 times
## Post #39
- Username: Marshivolt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 22, 2020 6:47 pm
- Post datetime: 2020-02-22T11:57:19+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

That did it! Thank you!
## Post #40
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-02-22T16:34:43+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Thank you very much here's a comparison from Models-Resource and my friend's model
[Untitled.png](https://xentaxbackup.github.io/file/17541_Untitled.png)
## Post #41
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-02-23T04:21:35+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, we're having trouble with the Teeth_01_fm.mol model for the Face start.
[teeth_01_fm.zip](https://xentaxbackup.github.io/file/17547_teeth_01_fm.zip)
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-23T11:35:27+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

teeth? Looks like a skeleton file to me -> 33 "Bip01" strings contained.

ahh, see, use faked tristripped FIs:
.



teeth.png (40.86 KiB) Viewed 76 times



uvs? Dunno, block at 0x3c0 has constant and/or too big values, more or less.
## Post #43
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-03-08T18:27:10+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, um me and another friend Kraken is having troubles with the Qore cap UVs which I also taught him  

We can't seem to figure out UVs I tried all the methods.Can you help us? Thanks also if you have a discord friend me here thanks. Mr.Hatsman#9705
[qore_cap_he_decompressed.zip](https://xentaxbackup.github.io/file/17655_qore_cap_he_decompressed.zip)
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-08T22:22:39+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

qore_cap_he_decompressed-mol-uvs.png (38.62 KiB) Viewed 53 times
## Post #45
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-04-04T22:42:22+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, it's me again dang these models are getting more hard to find. I am having trouble on this model which I think I found the start 


Face Start : 17179 though, Hex2Obj won't render it correctly? If you can help me that would be great thanks!
[bioshocki_booker_hr.zip](https://xentaxbackup.github.io/file/17882_bioshocki_booker_hr.zip)
## Post #46
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-05T07:22:19+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

There's some fiddling required, yeah. Here's the first submesh:
.



bioshocki_booker_hr-mol.png (84.45 KiB) Viewed 78 times
## Post #47
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-06-01T17:10:30+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Well, I am having trouble again since I remember ripping this model but now Hex2Obj isn't doing it I guess? But I remember it using BigE and it doesn't seem to work and using LitE also gives me another problem.
[tag_he.zip](https://xentaxbackup.github.io/file/18261_tag_he.zip)
## Post #48
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-01T17:54:08+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

I can't seem to find a specific problem here other than getting the correct end of first submesh in face indices list (at 0xF764):
.



tag_he.png (114.14 KiB) Viewed 56 times
## Post #49
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-08-29T07:05:20+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

Hey, it's me it has been a while keep on coming back lol I'm just having a problem with the grass_strip.mol like it's sorta weird when you go far it has multiple vertices and the UVs are wrong any ideas?
[grass_strip.zip](https://xentaxbackup.github.io/file/18663_grass_strip.zip)
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-29T08:41:05+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

> Reply from sonicdude143 ↑Sat Aug 29, 2020 3:05 pm at Sat Aug 29, 2020 3:05 pm
>
> when you go far it has multiple vertices and the UVs are wrong any ideas?Could you be more specific, please?
As always I cared for the first submesh only and apart from some fiddling to get the uvs' start address it was not too hard:
.



grass_strip.png (56.28 KiB) Viewed 34 times
## Post #51
- Username: sonicdude143
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Jul 30, 2019 6:15 pm
- Post datetime: 2020-09-02T23:47:28+00:00
- Post Title: Re: LittleBigPlanet .mol hex2obj

I don't know it's Hex2obj or me but I have everything right and Hex2Obj doesn't seem to be loading the UV for this model you can check my .h2o

Someone needs to make a mol extractor with bones or something,
[stoney_soil.zip](https://xentaxbackup.github.io/file/18684_stoney_soil.zip)
