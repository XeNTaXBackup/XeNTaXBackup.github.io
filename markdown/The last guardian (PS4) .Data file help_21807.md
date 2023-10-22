## Post #1
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-25T10:11:43+00:00
- Post Title: The last guardian (PS4) .Data file help?

Hello! So i need help with reverse engineering models for the last Guardian (PS4) as I am frankly, a bit stuck,

 the .bod file is in fact, used as an interpreter for the .data files, which are the ones that contain model data, the .elems contains face (and possibly skeleton, i'm not really sure) data, verts file contains vertex data, uv file contains uv data. Any help would greatly be appreated, thank you!
[bird.zip](https://xentaxbackup.github.io/file/17552_bird.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-25T16:47:41+00:00
- Post Title: The last guardian (PS4) .Data file help?

> Reply from Reindeercoat ↑Tue Feb 25, 2020 6:11 pm at Tue Feb 25, 2020 6:11 pm
>
> the .bod file is in fact, used as an interpreter for the .data files, which are the ones that contain model dataDidn't have the time to look into the .bod file, just merged the .data files and used hex2obj on it:
.



birda.jpg (207.31 KiB) Viewed 387 times



> the .elems contains face (and possibly skeleton, i'm not really sure) dataI don't see other than face indices there. There's a skeleton.bod file which should contain bones (joints, jt_) and possibly the matrices.
## Post #3
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-26T10:09:04+00:00
- Post Title: The last guardian (PS4) .Data file help?

Thanks m8! You're a life saver! While i have managed to successfully recreate your results by merging the .dat files and using hex2obj for the bird, i seem to be having a bit of trouble with the more advanced models, such as trico (forgive me, i am still a really big noob to this as tbh this is my first time doing something like this) i'll keep you updated if i have any sucess with other models, thank you!
## Post #4
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-26T15:04:25+00:00
- Post Title: The last guardian (PS4) .Data file help?

Update: managed to get most of the mesh from trico!



1582728950800_image.png (64.3 KiB) Viewed 349 times



I say most since for some reason while the point cloud did show data for the tail and eyes, i had to lower the face count, otherwise a lot of excess mesh happens (which is possibly submesh data used for the tail, eyes and horns, although i am not entirely sure how to fix that, forgive me for my ignorance as i am still new to this)

I'll submit the combined mesh data if you'd like!
## Post #5
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-26T15:08:05+00:00
- Post Title: The last guardian (PS4) .Data file help?

Here's the point cloud, for some reason xentax won't let me post more than 1 image per reply



6uiop.PNG (19.42 KiB) Viewed 347 times
## Post #6
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-26T15:49:05+00:00
- Post Title: The last guardian (PS4) .Data file help?

Wait, one more question, how exactly would one go about to extract skeleton data? Thank you!
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-26T16:20:06+00:00
- Post Title: The last guardian (PS4) .Data file help?

> Reply from Reindeercoat ↑Wed Feb 26, 2020 11:04 pm at Wed Feb 26, 2020 11:04 pm
>
> I'll submit the combined mesh data if you'd like!Feel free to do so.

> Reply from Reindeercoat ↑Wed Feb 26, 2020 11:49 pm at Wed Feb 26, 2020 11:49 pm
>
> Wait, one more question, how exactly would one go about to extract skeleton data? Thank you!That's not a 15 minutes job, usually: find the bone names, find/create the hierarchy (usually bone ids in a table), find the matrices.

You might read here ("Approaches of Parsing Bone Representations"): [viewtopic.php?f=29&t=19429](https://forum.xentax.com/viewtopic.php?f=29&t=19429)

and find out which "bone format" to be found in birda_skeleton.bod for example.

And remember: (quote) "Recognizing these forms is not a big deal, but parsing them correctly is."
## Post #8
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-26T16:41:30+00:00
- Post Title: The last guardian (PS4) .Data file help?

Thank you so much m8!

Here's the merged trico data if you wanna take a look!

[https://filebin.net/864hxwnde8i7qfr5](https://filebin.net/864hxwnde8i7qfr5)

(Apologies for the filebin link, apperantly it's too large to be added as an attachment)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-26T17:10:01+00:00
- Post Title: The last guardian (PS4) .Data file help?

Thanks! How to find the start of submeshes:

I used this H2O file:

0x1B7326 84916
Vb1
32 24
0x10 14094
020000
0x0 255

(which will result in showing the head and many worn faces)

Looking into the test.obj file reveals these lines as a possible border between submeshes:

```
f 14002 14000 13999 
f 172 173 174 
f 1 2 3 
f 85 2 1 
f 85 169 2 
f 32 85 1 
```

You reduce the face indices count to 62637 and the first submesh seems to look nice.
That's how you've done it, didn't you?

(There might be some magic table which holds the counts, dunno so far.)
I'd need the .bod file to check this.

You can add 14094x32 (dec.) to 0x10 to get the vertex start address of the next submesh (start of FIs also to be modified, count is just for test):
.



wings.png (41.24 KiB) Viewed 319 times
## Post #10
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-26T17:27:29+00:00
- Post Title: The last guardian (PS4) .Data file help?

Thank you so much, man, i seriously cannot thank you enough!

> "You reduce the face indices count to 62637 and the first submesh seems to look nice.
>
> That's how you've done it, didn't you?"

Yup! Tbh it seems like reducing the indice number did help on that part thankfully

Here's the bod files! (i also theough in the skeleton.bod just in case!)
[bod.zip](https://xentaxbackup.github.io/file/17560_bod.zip)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-26T17:41:34+00:00
- Post Title: The last guardian (PS4) .Data file help?

This is where you find the vertex counts (and maybe more) in the .bod file:
.



condora-bod-counts.png (37.98 KiB) Viewed 309 times



FD 23 00 00 is a vertex count (2nd submesh) in little endian notation, so decimal: 9213

have fun

btw: the 2nd E0 37 might just be a reminder (to be ignored when scanning for vertex counts?)
red rectangles: counts of face indices

2nd submesh:

0x1D5C86 45786
Vb1
32 24
0x6E1D0 9213
020000
0x0 255
## Post #12
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-27T14:16:13+00:00
- Post Title: The last guardian (PS4) .Data file help?

Ooh!! Honetsly thank you so so much! I have managed to get almost all the mesh i need execpt for the eyes, whiskers and tail, (it turns out the horns are in seperate files but right now they arent my main priotity, so i'll extract them later) i'll keep you updated if i suceed, thank you!
## Post #13
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-27T14:21:56+00:00
- Post Title: The last guardian (PS4) .Data file help?

Also very small update; the textures the game uses are in the gnf format, so they were very easy to extract with noesis; so i decided to enbed most of trico's textures on the model i got so far!

 (note, the game uses a particle system to generate the feathers, so that's why the poor thing's bald until i manage to find a way to recreate said system)
[trico.PNG](https://xentaxbackup.github.io/file/17574_trico.PNG)
## Post #14
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-27T17:23:56+00:00
- Post Title: The last guardian (PS4) .Data file help?

Update: I have managed to find what seems to be the vertice start address for the whiskers, eyes, and tail! (along with a a few exess leg verticies), the address apperantly being 9f1d0 and having at least 10000 vertices or so, not really sure tbh

But i am having a bit of trouble finding the faces for them tbh.
[gbvf.PNG](https://xentaxbackup.github.io/file/17577_gbvf.PNG)
## Post #15
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-29T15:54:43+00:00
- Post Title: The last guardian (PS4) .Data file help?

Update: so far no good, while i have been able to find the vertices for the eyes, whiskers and tail, everytime i try to calculate the faces for them, the model ends up almost looking like it exploded, with the faces going everywhere, (most likeley because i probably calculated the faces wrong one way or another, please forgive me as i am still very inexperinced in this) so i need some help figuring them out, thank you!
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-29T16:21:59+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

> Reply from Reindeercoat ↑Sat Feb 29, 2020 11:54 pm at Sat Feb 29, 2020 11:54 pm
>
> so i need some help figuring them out, thank you!You need to show what you did (H2O files, calculations, whatever) - I don't have the time to do it from scratch
## Post #17
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-29T16:23:38+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

Ok! Thank you so much btw! Ngl you have actually helped me a lot with all these and i cannot thank you enough!
## Post #18
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-02-29T17:20:18+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

> You need to show what you did (H2O files, calculations, whatever) - I don't have the time to do it from scratch

I'm absolutley sorry for the late response but Here's the h2o file! I deeply apologise if i have made been any stupid mistakes with the calculations as well
[h.zip](https://xentaxbackup.github.io/file/17601_h.zip)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-29T21:20:49+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

well, while I really prefer to do things intuitively I'd strongly recommend to look for the counts in the *.bod file here
(in case you didn't so far   ).
There's many possible FI starting blocks (0000 0100 0200) but I didn't get the idea which to choose for the eyes/tail neither know whether the tail is in the eyes submesh or is to be handled "separate".
.



condora.png (89.14 KiB) Viewed 249 times


I don't have the time for a closer look because I'm working on my address shifter which could come in handy here (or maybe not, dunno atm).

(What is funny that you'll see the full beast again (with eyes and all) in case you use a vertex count of 32906 for the last point cloud.)

well, this H2O file is for the tail only:

0x1EC23A 339
Vb1
32 24
0xB6170 76
020000
0x0 255

tail 2:

0x1EC4E0 1101
Vb1
32 24
0xB6AF0 228
020000
0x0 255
## Post #20
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-03-01T12:18:00+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

Thank you so much man, i really cannot thank you enough!

> I don't have the time for a closer look because I'm working on my address shifter which could come in handy here (or maybe not, dunno atm).

Ooh! Sounds interesting, i can't wait to see it done, it could probably help a lot of people, me included!    

> (What is funny that you'll see the full beast again (with eyes and all) in case you use a vertex count of 32906 for the last point cloud.)

Interesting! perhaps theoritically if i were to find it's face start address + list, i would be able to extract the whole model rather than simply piece by piece then? Or would that be impossible?
## Post #21
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-03-02T12:45:58+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

update: managed to find the third bit of the tail! (albeit with a few missing faces but that's better than nothing!)
[tailbitcal.PNG](https://xentaxbackup.github.io/file/17613_tailbitcal.PNG)
## Post #22
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-03-02T12:46:35+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

here it is in the viewer
[tailbit.PNG](https://xentaxbackup.github.io/file/17614_tailbit.PNG)
## Post #23
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-03-02T12:47:17+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

and here it is on the model in blender
[tailblen.PNG](https://xentaxbackup.github.io/file/17615_tailblen.PNG)
## Post #24
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-03-02T15:26:33+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

> usually: find the bone names, find/create the hierarchy (usually bone ids in a table), find the matrices

Sorry if this is dumb queation but what exactly would one do to find the matrices? While i have been able to find the bone names easily, i'm not really sure what to look for when searching for the matrice data, is there some form of pattern it has, or are they in a specific area in the skeleton .bod file? Thank you!

(Sorry again if this is a dumb question, i am still very much a beginner and tbh this is the first time i do anything like this, especially considering the game's files haven't been researched before afaik)
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-02T17:10:55+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

> Reply from Reindeercoat ↑Mon Mar 02, 2020 11:26 pm at Mon Mar 02, 2020 11:26 pm
>
> 
usually: find the bone names, find/create the hierarchy (usually bone ids in a table), find the matrices

Sorry if this is dumb queation but what exactly would one do to find the matrices? You could read here ("Approaches of Parsing Bone Representations"):
[viewtopic.php?f=29&t=19429](https://forum.xentax.com/viewtopic.php?f=29&t=19429)

Here's the counts from the condora_model.blob (didn't check them all, so maybe some counts/addresses are missing or wrong):
For example, last mesh: FIcnt= 10527 (3 less)

0 0x10 vCnt: 14094, FIcnt: 62640 0x1b7326

1 0x6e1d0 vCnt: 9213, FIcnt: 45786 0x1d5c86

2 0xb6170 vCnt: 76, FIcnt: 342 0x1ec23a
3 0xb6af0 vCnt: 228, FIcnt: 1080 0x1ec4e6

4 0xb8770 vCnt: 132, FIcnt: 600 0x1ecd56
5 0xb97f0 vCnt: 2837, FIcnt: 5352 0x1ed206
6 0xcfa90 vCnt: 1118, FIcnt: 3456 0x1efbd6
7 0xd8650 vCnt: 1112, FIcnt: 1872 0x1f16d6
8 0xe1150 vCnt: 11174, FIcnt: 14184 0x1f2576
9 0x138610 vCnt: 8450, FIcnt: 13860 0x1f9446
10 0x17a650 vCnt: 39, FIcnt: 177 0x20008e
11 0x17ab30 vCnt: 3327, FIcnt: 8988 0x2001f0
12 0x194b10 vCnt: 50, FIcnt: 108 0x204828
13 0x195150 vCnt: 200, FIcnt: 648 0x204900
14 0x196a50 vCnt: 120, FIcnt: 360 0x204e10
15 0x197950 vCnt: 396, FIcnt: 948 0x2050e0
16 0x19aad0 vCnt: 92, FIcnt: 366 0x205848
17 0x19b650 vCnt: 193, FIcnt: 840 0x205b24
18 0x19ce70 vCnt: 228, FIcnt: 1080 0x2061b4
19 0x19eaf0 vCnt: 132, FIcnt: 600 0x206a24
20 0x19fb70 vCnt: 84, FIcnt: 360 0x206ed4
21 0x1a05f0 vCnt: 389, FIcnt: 1284 0x2071a4
22 0x1a3690 vCnt: 286, FIcnt: 810 0x207bac
23 0x1a5a50 vCnt: 228, FIcnt: 930 0x208200

24 0x1a76d0 vCnt: 2018, FIcnt: 10530 0x208944
(vSum: 56216)
.



condora_head.png (93.77 KiB) Viewed 147 times



(I really should have taken care for the counts in the bod file earlier - sometimes I'm such a dumbo...  )
## Post #26
- Username: Reindeercoat
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 01, 2020 2:28 pm
- Post datetime: 2020-03-02T20:19:37+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

First off; thank you so much! Thanks to your help, i have managed to extract the rest of the model, including the whiskers and eyes!!! I cannot thank you enough!!!


As for the skeleton, Skelbuilder doesn't seem to work for the skeleton.bod files though (doesn't generate an fbx file) perhaps something in the skeleton is encrypted or needs to be modified?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-02T20:33:48+00:00
- Post Title: Re: The last guardian (PS4) .Data file help?

> Reply from Reindeercoat ↑Tue Mar 03, 2020 4:19 am at Tue Mar 03, 2020 4:19 am
>
> As for the skeleton, Skelbuilder doesn't seem to work for the skeleton.bod files though (doesn't generate an fbx file) perhaps something in the skeleton is encrypted or needs to be modified?don't have the time to check it. 

There's dozens (if not hundreds) of different skeleton/animation formats. Guess you need to read through the posts of Bigchillghost's thread to understand how to get the matrices here.

While building the meshes appears to be super simple in most cases, imho, building the matrices often is not. (It's not a beginner's task, btw.  )

anyways, you may try to find something useful in here:


 birda_skel.zip
(3.34 KiB) Downloaded 16 times



Here's some names (first two handled seperately for some reason):
Bone7
game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Beak
(numbers are not the bone ids, just for listing purposes)

```
1 "jt_Beak"
2 "remoteAttach"
3 "entityFlags"
4 "parent"
5 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Head"
6 "children"
7 "extensions"
8 "position"
9 "scale"
10 "rotation"
11 "rootRotation"
12 "rootPosition"
13 "rootScale"
14 "jt_Head"
15 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Neck"
16 "jt_Neck"
17 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Spine"
18 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Fing_Lf"
19 "jt_Fing_Lf"
20 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Hand_Lf"
21 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingC_Lf"
22 "jt_WingC_Lf"
23 "jt_Hand_Lf"
24 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ArmLow_Lf"
25 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingB_Lf"
26 "jt_WingB_Lf"
27 "jt_ArmLow_Lf"
28 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ArmUp_Lf"
29 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingA_Lf"
30 "jt_WingA_Lf"
31 "jt_ArmUp_Lf"
32 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Shoulder_Lf"
33 "jt_Shoulder_Lf"
34 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Fing_Rt"
35 "jt_Fing_Rt"
36 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Hand_Rt"
37 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingC_Rt"
38 "jt_WingC_Rt"
39 "jt_Hand_Rt"
40 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ArmLow_Rt"
41 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingB_Rt"
42 "jt_WingB_Rt"
43 "jt_ArmLow_Rt"
44 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ArmUp_Rt"
45 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingA_Rt"
46 "jt_WingA_Rt"
47 "jt_ArmUp_Rt"
48 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Shoulder_Rt"
49 "jt_Shoulder_Rt"
50 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingSub_Lf"
51 "jt_WingSub_Lf"
52 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_WingSub_Rt"
53 "jt_WingSub_Rt"
54 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeMiddle1_Lf"
55 "jt_ToeMiddle1_Lf"
56 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeMiddle_Lf"
57 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeThumb1_Lf"
58 "jt_ToeThumb1_Lf"
59 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeThumb_Lf"
60 "jt_ToeThumb_Lf"
61 "jt_ToeMiddle_Lf"
62 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Foot_Lf"
63 "jt_Foot_Lf"
64 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_LegLow_Lf"
65 "jt_LegLow_Lf"
66 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_LegUp_Lf"
67 "jt_LegUp_Lf"
68 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeMiddle1_Rt"
69 "jt_ToeMiddle1_Rt"
70 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeMiddle_Rt"
71 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeThumb1_Rt"
72 "jt_ToeThumb1_Rt"
73 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_ToeThumb_Rt"
74 "jt_ToeThumb_Rt"
75 "jt_ToeMiddle_Rt"
76 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Foot_Rt"
77 "jt_Foot_Rt"
78 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_LegLow_Rt"
79 "jt_LegLow_Rt"
80 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_LegUp_Rt"
81 "jt_LegUp_Rt"
82 "jt_Spine"
83 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Root"
84 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Pelvis"
85 "jt_Pelvis"
86 "jt_Root"
87 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_PaAxis"
88 "jt_PaAxis"
89 "game/assets/sub_chara/birdA/skin/birdA_skeleton_jt_Origin"
90 "jt_Origin"
91 "Skeleton"
92 "game/assets/sub_chara/birdA/skin/birdA_skeleton_entity"
93 "SceneRoot"
94 "game/assets/sub_chara/birdA/skin/birdA_skeleton"
95 "bones"
96 "sklData"
97 "charaScale"
98 "childSelection"
99 "animDataBinds"
100 "geometryBuffer"
101 "baseName"
102 "instanceCtx"
103 "createCascadeBatchFlags"
```


reduced to the min (unsorted and ignore the numbers  ):

```

0 "assetName"
1 "jt_Beak"
2 "remoteAttach"
3 "entityFlags"
4 "parent"

6 "children"
7 "extensions"
8 "position"
9 "scale"
10 "rotation"
11 "rootRotation"
12 "rootPosition"
13 "rootScale"
14 "jt_Head"

16 "jt_Neck"

19 "jt_Fing_Lf"

22 "jt_WingC_Lf"
23 "jt_Hand_Lf"

26 "jt_WingB_Lf"
27 "jt_ArmLow_Lf"

30 "jt_WingA_Lf"
31 "jt_ArmUp_Lf"

33 "jt_Shoulder_Lf"

35 "jt_Fing_Rt"

38 "jt_WingC_Rt"
39 "jt_Hand_Rt"

42 "jt_WingB_Rt"
43 "jt_ArmLow_Rt"

46 "jt_WingA_Rt"
47 "jt_ArmUp_Rt"

49 "jt_Shoulder_Rt"

51 "jt_WingSub_Lf"

53 "jt_WingSub_Rt"

55 "jt_ToeMiddle1_Lf"

58 "jt_ToeThumb1_Lf"

60 "jt_ToeThumb_Lf"
61 "jt_ToeMiddle_Lf"

63 "jt_Foot_Lf"

65 "jt_LegLow_Lf"

67 "jt_LegUp_Lf"

69 "jt_ToeMiddle1_Rt"

72 "jt_ToeThumb1_Rt"

74 "jt_ToeThumb_Rt"
75 "jt_ToeMiddle_Rt"

77 "jt_Foot_Rt"

79 "jt_LegLow_Rt"

81 "jt_LegUp_Rt"
82 "jt_Spine"

85 "jt_Pelvis"
86 "jt_Root"

88 "jt_PaAxis"

90 "jt_Origin"
91 "Skeleton"
92 "birdA_skeleton_entity"
93 "SceneRoot"
94 "birdA_skeleton"
95 "bones"
96 "sklData"
97 "charaScale"
98 "childSelection"
99 "animDataBinds"
100 "geometryBuffer"
101 "baseName"
102 "instanceCtx"
103 "createCascadeBatchFlags"

```


So you have the bone names (joints, "jt_...") and some matrices. Questions is: which belongs to which? Have fun...
