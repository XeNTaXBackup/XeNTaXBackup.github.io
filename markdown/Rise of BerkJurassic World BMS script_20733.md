## Post #1
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-06-25T22:48:57+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

I extracted files from the Rise of Berk apk with the intention of getting some of the models and textures which I believe are stored in the .dab files. Aluigi made a BMS script that works with both jurassic world and and TMMT Legends .dab files.
Rise of Berk is made by Ludia (same company that did jurassic world and TMMT Legends) and the dab files have the same LPKG header, but quickbms throws up errors and quits when I try to use the script to extract Rise of Berk's dab files. I'm too much of a layman to alter the script myself and was wondering if anyone could help. 
Linked is the script along with a .dab from Rise of Berk.
[http://www.mediafire.com/file/xdphvpdlj ... e.zip/file](http://www.mediafire.com/file/xdphvpdljazr1yg/dab_sample.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-26T06:18:19+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from Snapdragons ↑Wed Jun 26, 2019 6:48 am at Wed Jun 26, 2019 6:48 am
>
> Rise of Berk is made by Ludia (same company that did jurassic world and TMMT Legends) and the dab files have the same LPKG header, but quickbms throws up errors and quits when I try to use the script to extract Rise of Berk's dab files.what's the error?

```
Error: No such file or directory

Last script line before the error or that produced the error:
  7   open FDDE "dhr"

Press ENTER or close the window to quit
```
*.dhr is missing! Surprise.  

(You also need to provide a .dsb file, I guess.)
## Post #3
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-06-26T09:47:00+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from shakotay2 ↑Wed Jun 26, 2019 2:18 pm at Wed Jun 26, 2019 2:18 pm
>
> 

(You also need to provide a .dsb file, I guess.)

I tried loading the dsb along with the dab when attempting to use the script again and the same type of error pointed me toward the dhr file, so I tried loading that in too, but I ended up getting this error:

Error: incomplete input file 2: C:\Users\username\Desktop\local_global_low.dsb
       Can't read 40 bytes from offset 0019a780.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 2     0%   0          792752     . offset 0019a780

Last script line before the error or that produced the error:
  62  log "" OFFSET SIZE 2    # dsb

Press ENTER or close the window to quit

Here are the dsb and dhr files
[https://www.mediafire.com/file/5e65ghb9 ... r.zip/file](https://www.mediafire.com/file/5e65ghb9a71bl7v/dsb_and_dhr.zip/file)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-26T11:43:38+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

Thx. Simplest way to adapt the script would be to have dab, dsb and dhr files from Jurassic World.
With some debug (print) lines in the script u could see how it works and then try to understand why it doesn't for Rise of Berk.

(btw: the smaller the files in question the easier it could be)
## Post #5
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-06-26T21:16:19+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from shakotay2 ↑Wed Jun 26, 2019 7:43 pm at Wed Jun 26, 2019 7:43 pm
>
> 
With some debug (print) lines in the script u could see how it works and then try to understand why it doesn't for Rise of Berk.






I tried comparing a couple dhr and dsb files from both games respectively, but I'll admit I'm not quite sure what I'm looking at beyond the headers. 

Here are some Jurassic world samples I used
[http://www.mediafire.com/file/ji94tirhw ... s.zip/file](http://www.mediafire.com/file/ji94tirhwo8ift5/Jurassic_World_Samples.zip/file)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-27T20:24:38+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

problem: Rise of Berk dhr doesn't follow the "size dummy zero rule":
.



dhr-not-zero.png (8.13 KiB) Viewed 190 times



(Maybe insert 4 more "get dummy long" lines?)

Hey guys and dolls, seems sometimes I have some fit of being a trial 'n error genius (sadly for milli seconds only)  
Try this:

```
    getdstring DUMMY 0x10
    getdstring DUMMY 0x10
    get DUMMY1 long
    get SIZE long
    get DUMMY2 long
    get DUMMY2 long
    get DUMMY2 long
    get DUMMY2 long
    get DUMMY2 long
    get ZERO1 long
```


BUT: not sure if any of those dat files contain any meaningful data:  

```
FLAGS TYPE OFFSET SIZE 0 0 780100 40
  000be774 40         0000206c.dat
FLAGS TYPE OFFSET SIZE 0 0 780140 116
  000be79c 116        0000206d.dat
FLAGS TYPE OFFSET SIZE 0 1 1654312 124
  00193e58 124        0000206e.dat
FLAGS TYPE OFFSET SIZE 0 0 780256 164
  000be810 164        0000206f.dat
FLAGS TYPE OFFSET SIZE 0 0 780420 48
  000be8b4 48         00002070.dat
FLAGS TYPE OFFSET SIZE 0 0 780468 28
  000be8e4 28         00002071.dat
FLAGS TYPE OFFSET SIZE 0 0 780496 368
  000be900 368        00002072.dat
FLAGS TYPE OFFSET SIZE 0 1 1654436 32
  00193ed4 32         00002073.dat
FLAGS TYPE OFFSET SIZE 0 1 1654468 40
  00193ef4 40         00002074.dat
FLAGS TYPE OFFSET SIZE 0 1 1654508 48
  00193f1c 48         00002075.dat
FLAGS TYPE OFFSET SIZE 0 0 780864 148
  000bea70 148        00002076.dat
FLAGS TYPE OFFSET SIZE 0 1 1654556 32
  00193f4c 32         00002077.dat
FLAGS TYPE OFFSET SIZE 0 1 1654588 100
  00193f6c 100        00002078.dat
FLAGS TYPE OFFSET SIZE 0 1 1654688 32
  00193fd0 32         00002079.dat
FLAGS TYPE OFFSET SIZE 0 1 1654720 24
  00193ff0 24         0000207a.dat
FLAGS TYPE OFFSET SIZE 0 0 781012 180
  000beb04 180        0000207b.dat
FLAGS TYPE OFFSET SIZE 0 0 781192 24
  000bebb8 24         0000207c.dat
FLAGS TYPE OFFSET SIZE 0 0 781216 28
  000bebd0 28         0000207d.dat
FLAGS TYPE OFFSET SIZE 0 0 781244 244
  000bebec 244        0000207e.dat
FLAGS TYPE OFFSET SIZE 0 1 1654744 416
  00194008 416        0000207f.dat
FLAGS TYPE OFFSET SIZE 0 1 1655160 40
  001941a8 40         00002080.dat
FLAGS TYPE OFFSET SIZE 0 1 1655200 32
  001941d0 32         00002081.dat
FLAGS TYPE OFFSET SIZE 0 0 781488 148
  000bece0 148        00002082.dat
FLAGS TYPE OFFSET SIZE 0 0 781636 16
  000bed74 16         00002083.dat
FLAGS TYPE OFFSET SIZE 0 1 1655232 16
  001941f0 16         00002084.dat
FLAGS TYPE OFFSET SIZE 0 0 781652 56
  000bed84 56         00002085.dat
FLAGS TYPE OFFSET SIZE 0 0 781708 68
  000bedbc 68         00002086.dat
FLAGS TYPE OFFSET SIZE 0 0 781776 128
  000bee00 128        00002087.dat
FLAGS TYPE OFFSET SIZE 0 0 781904 364
  000bee80 364        00002088.dat
FLAGS TYPE OFFSET SIZE 0 1 1655248 16
  00194200 16         00002089.dat
FLAGS TYPE OFFSET SIZE 0 0 782268 56
  000befec 56         0000208a.dat
FLAGS TYPE OFFSET SIZE 0 0 782324 68
  000bf024 68         0000208b.dat
FLAGS TYPE OFFSET SIZE 0 0 782392 128
  000bf068 128        0000208c.dat
FLAGS TYPE OFFSET SIZE 0 0 782520 484
  000bf0e8 484        0000208d.dat
FLAGS TYPE OFFSET SIZE 0 1 1655264 16
  00194210 16         0000208e.dat
FLAGS TYPE OFFSET SIZE 0 0 783004 56
  000bf2cc 56         0000208f.dat
FLAGS TYPE OFFSET SIZE 0 0 783060 68
  000bf304 68         00002090.dat
FLAGS TYPE OFFSET SIZE 0 0 783128 128
  000bf348 128        00002091.dat
FLAGS TYPE OFFSET SIZE 0 0 783256 364
  000bf3c8 364        00002092.dat
FLAGS TYPE OFFSET SIZE 0 1 1655280 192
  00194220 192        00002093.dat
FLAGS TYPE OFFSET SIZE 0 1 1655472 56
  001942e0 56         00002094.dat
FLAGS TYPE OFFSET SIZE 0 0 783620 128
  000bf534 128        00002095.dat
FLAGS TYPE OFFSET SIZE 0 0 783748 100
  000bf5b4 100        00002096.dat
FLAGS TYPE OFFSET SIZE 0 0 783848 120
  000bf618 120        00002097.dat
FLAGS TYPE OFFSET SIZE 0 1 1655528 5448
  00194318 5448       00002098.dat
FLAGS TYPE OFFSET SIZE 0 0 783968 164
  000bf690 164        00002099.dat
FLAGS TYPE OFFSET SIZE 0 0 784132 48
  000bf734 48         0000209a.dat
FLAGS TYPE OFFSET SIZE 0 1 1660976 96
  00195860 96         0000209b.dat
FLAGS TYPE OFFSET SIZE 0 0 784180 96
  000bf764 96         0000209c.dat
FLAGS TYPE OFFSET SIZE 1 1 17236524 8259
  0107025c 8259       0000209d.dat
FLAGS TYPE OFFSET SIZE 0 0 784276 36
  000bf7c4 36         0000209e.dat
FLAGS TYPE OFFSET SIZE 0 0 784312 100
  000bf7e8 100        0000209f.dat
FLAGS TYPE OFFSET SIZE 0 1 1661072 96
  001958c0 96         000020a0.dat
FLAGS TYPE OFFSET SIZE 0 0 784412 96
  000bf84c 96         000020a1.dat
FLAGS TYPE OFFSET SIZE 0 0 784508 100
  000bf8ac 100        000020a2.dat
FLAGS TYPE OFFSET SIZE 0 0 784608 124
  000bf910 124        000020a3.dat
FLAGS TYPE OFFSET SIZE 0 1 1661168 6804
  00195920 6804       000020a4.dat
FLAGS TYPE OFFSET SIZE 0 0 784732 164
  000bf98c 164        000020a5.dat
FLAGS TYPE OFFSET SIZE 0 0 784896 48
  000bfa30 48         000020a6.dat
FLAGS TYPE OFFSET SIZE 0 0 784944 28
  000bfa60 28         000020a7.dat
FLAGS TYPE OFFSET SIZE 0 0 784972 492
  000bfa7c 492        000020a8.dat
FLAGS TYPE OFFSET SIZE 0 1 1667972 32
  001973b4 32         000020a9.dat
FLAGS TYPE OFFSET SIZE 0 1 1668004 40
  001973d4 40         000020aa.dat
FLAGS TYPE OFFSET SIZE 0 1 1668044 64
  001973fc 64         000020ab.dat
FLAGS TYPE OFFSET SIZE 0 0 785464 148
  000bfc68 148        000020ac.dat
FLAGS TYPE OFFSET SIZE 0 1 1668108 1376
  0019743c 1376       000020ad.dat
FLAGS TYPE OFFSET SIZE 0 1 1669484 40
  0019799c 40         000020ae.dat
FLAGS TYPE OFFSET SIZE 0 1 1669524 32
  001979c4 32         000020af.dat
FLAGS TYPE OFFSET SIZE 0 0 785612 148
  000bfcfc 148        000020b0.dat
FLAGS TYPE OFFSET SIZE 0 1 1669556 1856
  001979e4 1856       000020b1.dat
FLAGS TYPE OFFSET SIZE 0 1 1671412 2320
  00198124 2320       000020b2.dat
FLAGS TYPE OFFSET SIZE 0 1 1673732 32
  00198a34 32         000020b3.dat
FLAGS TYPE OFFSET SIZE 0 1 1673764 32
  00198a54 32         000020b4.dat
FLAGS TYPE OFFSET SIZE 0 0 785760 180
  000bfd90 180        000020b5.dat
FLAGS TYPE OFFSET SIZE 0 0 785940 56
  000bfe44 56         000020b6.dat
FLAGS TYPE OFFSET SIZE 0 1 1673796 24
  00198a74 24         000020b7.dat
FLAGS TYPE OFFSET SIZE 0 0 785996 56
  000bfe7c 56         000020b8.dat
FLAGS TYPE OFFSET SIZE 0 0 786052 100
  000bfeb4 100        000020b9.dat
FLAGS TYPE OFFSET SIZE 0 0 786152 120
  000bff18 120        000020ba.dat
FLAGS TYPE OFFSET SIZE 0 1 1673820 240
  00198a8c 240        000020bb.dat
FLAGS TYPE OFFSET SIZE 0 0 786272 164
  000bff90 164        000020bc.dat
FLAGS TYPE OFFSET SIZE 0 0 786436 48
  000c0034 48         000020bd.dat
FLAGS TYPE OFFSET SIZE 0 0 786484 96
  000c0064 96         000020be.dat
FLAGS TYPE OFFSET SIZE 0 0 786580 96
  000c00c4 96         000020bf.dat
FLAGS TYPE OFFSET SIZE 0 0 786676 124
  000c0124 124        000020c0.dat
FLAGS TYPE OFFSET SIZE 0 1 1674060 5448
  00198b7c 5448       000020c1.dat
FLAGS TYPE OFFSET SIZE 0 0 786800 164
  000c01a0 164        000020c2.dat
FLAGS TYPE OFFSET SIZE 0 0 786964 48
  000c0244 48         000020c3.dat
FLAGS TYPE OFFSET SIZE 0 0 787012 368
  000c0274 368        000020c4.dat
FLAGS TYPE OFFSET SIZE 0 1 1679508 32
  0019a0c4 32         000020c5.dat
FLAGS TYPE OFFSET SIZE 0 1 1679540 40
  0019a0e4 40         000020c6.dat
FLAGS TYPE OFFSET SIZE 0 1 1679580 32
  0019a10c 32         000020c7.dat
FLAGS TYPE OFFSET SIZE 0 0 787380 148
  000c03e4 148        000020c8.dat
FLAGS TYPE OFFSET SIZE 0 1 1679612 32
  0019a12c 32         000020c9.dat
FLAGS TYPE OFFSET SIZE 0 1 1679644 40
  0019a14c 40         000020ca.dat
FLAGS TYPE OFFSET SIZE 0 1 1679684 32
  0019a174 32         000020cb.dat
FLAGS TYPE OFFSET SIZE 0 0 787528 148
  000c0478 148        000020cc.dat
FLAGS TYPE OFFSET SIZE 0 0 787676 32
  000c050c 32         000020cd.dat
FLAGS TYPE OFFSET SIZE 0 1 1679716 144
  0019a194 144        000020ce.dat
FLAGS TYPE OFFSET SIZE 0 0 787708 96
  000c052c 96         000020cf.dat
FLAGS TYPE OFFSET SIZE 0 0 787804 100
  000c058c 100        000020d0.dat
FLAGS TYPE OFFSET SIZE 0 0 787904 120
  000c05f0 120        000020d1.dat
FLAGS TYPE OFFSET SIZE 0 1 1679860 660
  0019a224 660        000020d2.dat
FLAGS TYPE OFFSET SIZE 0 0 788024 164
  000c0668 164        000020d3.dat
FLAGS TYPE OFFSET SIZE 0 0 788188 48
  000c070c 48         000020d4.dat
FLAGS TYPE OFFSET SIZE 0 0 788236 28
  000c073c 28         000020d5.dat
FLAGS TYPE OFFSET SIZE 0 0 788264 364
  000c0758 364        000020d6.dat
FLAGS TYPE OFFSET SIZE 0 1 1680520 208
  0019a4b8 208        000020d7.dat
FLAGS TYPE OFFSET SIZE 0 1 1680728 40
  0019a588 40         000020d8.dat
FLAGS TYPE OFFSET SIZE 0 1 1680768 32
  0019a5b0 32         000020d9.dat
FLAGS TYPE OFFSET SIZE 0 0 788628 148
  000c08c4 148        000020da.dat
FLAGS TYPE OFFSET SIZE 0 0 788776 24
  000c0958 24         000020db.dat
FLAGS TYPE OFFSET SIZE 0 0 788800 96
  000c0970 96         000020dc.dat
FLAGS TYPE OFFSET SIZE 0 0 788896 120
  000c09d0 120        000020dd.dat
FLAGS TYPE OFFSET SIZE 0 1 1680800 32
  0019a5d0 32         000020de.dat
FLAGS TYPE OFFSET SIZE 0 0 789016 56
  000c0a48 56         000020df.dat
FLAGS TYPE OFFSET SIZE 0 0 789072 144
  000c0a80 144        000020e0.dat
FLAGS TYPE OFFSET SIZE 0 0 789216 12
  000c0b10 12         000020e1.dat
FLAGS TYPE OFFSET SIZE 0 0 789228 24
  000c0b1c 24         000020e2.dat
FLAGS TYPE OFFSET SIZE 0 0 789252 480
  000c0b34 480        000020e3.dat
FLAGS TYPE OFFSET SIZE 0 0 789732 24
  000c0d14 24         000020e4.dat
FLAGS TYPE OFFSET SIZE 0 0 789756 8
  000c0d2c 8          000020e5.dat
FLAGS TYPE OFFSET SIZE 0 0 789764 24
  000c0d34 24         000020e6.dat
FLAGS TYPE OFFSET SIZE 0 0 789788 16
  000c0d4c 16         000020e7.dat
FLAGS TYPE OFFSET SIZE 0 1 1680832 96
  0019a5f0 96         000020e8.dat
FLAGS TYPE OFFSET SIZE 0 0 789804 96
  000c0d5c 96         000020e9.dat
FLAGS TYPE OFFSET SIZE 0 0 789900 100
  000c0dbc 100        000020ea.dat
FLAGS TYPE OFFSET SIZE 0 0 790000 120
  000c0e20 120        000020eb.dat
FLAGS TYPE OFFSET SIZE 0 1 1680928 156
  0019a650 156        000020ec.dat
FLAGS TYPE OFFSET SIZE 0 0 790120 164
  000c0e98 164        000020ed.dat
FLAGS TYPE OFFSET SIZE 0 0 790284 48
  000c0f3c 48         000020ee.dat
FLAGS TYPE OFFSET SIZE 0 0 790332 28
  000c0f6c 28         000020ef.dat
FLAGS TYPE OFFSET SIZE 0 0 790360 364
  000c0f88 364        000020f0.dat
FLAGS TYPE OFFSET SIZE 0 1 1681084 32
  0019a6ec 32         000020f1.dat
FLAGS TYPE OFFSET SIZE 0 1 1681116 40
  0019a70c 40         000020f2.dat
FLAGS TYPE OFFSET SIZE 0 1 1681156 64
  0019a734 64         000020f3.dat
FLAGS TYPE OFFSET SIZE 0 0 790724 148
  000c10f4 148        000020f4.dat
FLAGS TYPE OFFSET SIZE 0 0 790872 24
  000c1188 24         000020f5.dat
FLAGS TYPE OFFSET SIZE 0 0 790896 48
  000c11a0 48         000020f6.dat
FLAGS TYPE OFFSET SIZE 0 0 790944 344
  000c11d0 344        000020f7.dat
FLAGS TYPE OFFSET SIZE 0 0 791288 304
  000c1328 304        000020f8.dat
FLAGS TYPE OFFSET SIZE 0 0 791592 132
  000c1458 132        000020f9.dat
FLAGS TYPE OFFSET SIZE 0 0 791724 604
  000c14dc 604        000020fa.dat
FLAGS TYPE OFFSET SIZE 0 0 792328 116
  000c1738 116        000020fb.dat
FLAGS TYPE OFFSET SIZE 0 0 792444 116
  000c17ac 116        000020fc.dat
FLAGS TYPE OFFSET SIZE 0 0 792560 136
  000c1820 136        000020fd.dat

- 8446 files found in 14 seconds
  coverage file 0   100%   202904     202880     . offset 00031878
  coverage file 1    99%   18925960   18926064   . offset 00000000
  coverage file 2    99%   792288     792752     . offset 00000000

Press ENTER or close the window to quit
```
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-28T13:25:49+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

seems they do have a meaning:
.



00000028e-dat.png (73.12 KiB) Viewed 179 times
## Post #8
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-07-02T08:34:56+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from shakotay2 ↑Fri Jun 28, 2019 9:25 pm at Fri Jun 28, 2019 9:25 pm
>
> 
seems they do have a meaning:
.
00000028e-dat.png

Thank you so much for your work!!   
Seems it’s time for me to learn h2o huh? Also, the app downloads data over wi-fi so I have a feeling more assets will appear if I can get the app running in an emulator or VM so it will generate more files. (currently trying that at the moment)

But I also find it strange. Someone at models-resource managed to extract two models and I’m wondering if they had knowledge of h2o or if they had some other method up their sleeve. Although (as far as I can see) I believe they are uncontactable.
[https://www.models-resource.com/mobile/ ... iseofberk/](https://www.models-resource.com/mobile/dreamworksdragonsriseofberk/)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-03T07:09:33+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from Snapdragons ↑Tue Jul 02, 2019 4:34 pm at Tue Jul 02, 2019 4:34 pm
>
> Someone at models-resource managed to extract two models and I’m wondering if they had knowledge of h2o or if they had some other method up their sleeve.The format is simple. So it's not a matter of hex2obj - basic scripting or coding skills (Max script, blender/Noesis python script or C- coding) should do the trick.

(Question for me is how they knew to adapt the bms script? If their upload is from before 6-27-2019 they probably found it on their own.  )
## Post #10
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-08-14T00:08:59+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from shakotay2 ↑Wed Jul 03, 2019 3:09 pm at Wed Jul 03, 2019 3:09 pm
>
> 
The format is simple.

Sorry to be a bother! But I finally got a rooted emulator to generate the files I wanted to get to. I have since been trying to learn how these models work, but my understanding is a bit eh...shaky at best. A bit of help would be wonderful if you have the time. 

I'm still trying to learn how to find start addresses (which I know takes practice and trial & error) but what I did find out about these models is that the vertices form a cloud when the padding is set to intervals of 12. The type is float. For faces, the type is byte. I know the start address for the faces should be somewhere around the "scrambled alphabet" but the addresses I've tried lead to really warped faces that only show up on one side of the model. I have zero clue about the UVs or textures though. (or what "pad int" is supposed to do for that matter).
So I've come this far, but now I'm just kinda bumbling around. For all I know my guesses are just way off. 

Sample file from the image: [https://www.mediafire.com/file/06j78env ... 3.dat/file](https://www.mediafire.com/file/06j78envyaj7ooe/00000183.dat/file)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-14T10:53:31+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from Snapdragons ↑Wed Aug 14, 2019 8:08 am at Wed Aug 14, 2019 8:08 am
>
> 
but the addresses I've tried lead to really warped faces that only show up on one side of the model.As I wrote: the format is pretty simply - you won't find easier ones:
.



00000183-dat.png (119.78 KiB) Viewed 123 times

(For the one "sided thingie": import the obj to blender and invert normals or try out backface culling.
You need to provide the texture to tell more.)
## Post #12
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-08-15T09:16:04+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from shakotay2 ↑Wed Aug 14, 2019 6:53 pm at Wed Aug 14, 2019 6:53 pm
>
> 
You need to provide the texture to tell more.)

I believe these are them!
[http://www.mediafire.com/file/o2skzk2o6 ... r.zip/file](http://www.mediafire.com/file/o2skzk2o62nt9ap/textures_pvr.zip/file)

Edit: Tried to use PVRTexTool but it puts out a white image. (Though that might just be something on my end)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-15T11:01:03+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

fmt_pvrtc_pvr.py (Noesis) fails in def parseV3(self):
because self.fmt == 6 is unhandled so far.
## Post #14
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-08-15T21:17:26+00:00
- Post Title: Rise of Berk/Jurassic World BMS script

> Reply from shakotay2 ↑Thu Aug 15, 2019 7:01 pm at Thu Aug 15, 2019 7:01 pm
>
> 
fmt_pvrtc_pvr.py (Noesis) fails in def parseV3(self):
because self.fmt == 6 is unhandled so far.

Yeah I'm running Noesis4296 and it throws up errors. 
Is it some weird pvr specific to Ludia?
