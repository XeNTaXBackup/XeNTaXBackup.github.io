## Post #1
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-05-12T03:24:24+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

Hey,

Couple of months ago me and the animation genius mr. shakotay2 tried to extract animation's from a chinese Saint Seiya game and we did not succeed  
But now there's a new opportunity to achieve victory and I would love your help!

I want to import Saint Seiya[PS2] into 3DSMAX (or any other similar software)
I'm still a noob and first I need to understand what I'm dealing with  

It seems like the animation files are in .gai format, but there are 2 other type of files that seem to contain information about bones.
Can you guys help me to understand what are these other formats?

Sample (800kb): [http://www.mediafire.com/download/s5h8s ... Dragon.rar](http://www.mediafire.com/download/s5h8sk9d6hqev59/Dragon.rar)

Here they are:
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-12T23:07:49+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from asdasd123
>
> and the animation genius mr. shakotay2 tried to extract animation's from a chinese Saint Seiya game and we did not succeedI feel the slight banter,
but it doesn't hurt me,
doesn't hurt me - today  

Anyway, 0252_01h.gmi bone names contain too much "hair", too less "finger",
(is it "tip?", then why there's 7 of them? ok: 2,3, 4,5 some kind of "economy" fingers  ), 
parenting ids: first byte in this sequence: 03 00 88 00 88 00):

nodes
1 *h_all_root*
2 *h_jnt_waist*
3 *h_jnt_lbody*
4 *h_jnt_luleg*
5 *h_jnt_ruleg*
6 *h_jnt_llleg*
7 *h_jnt_rlleg*
8 *h_jnt_ubody*
9 *h_jnt_lfoot*
10 *h_jnt_rfoot*
11 *h_jnt_head*
12 *h_jnt_luarm*
13 *h_jnt_opt1*
14 *h_jnt_opt2*
15 *h_jnt_ruarm*
16 *h_jnt_llarm*
17 *h_jnt_ltoe*
18 *h_jnt_rlarm*
19 *h_jnt_rtoe*
20 *h_jnt_hair1*
21 *h_jnt_hair2*
22 *h_jnt_hair27*
23 *h_jnt_hair3*
24 *h_jnt_hair4*
25 *h_jnt_hair5*
26 *h_jnt_mouth_l*
27 *h_jnt_mouth_low*
28 *h_jnt_mouth_r*
29 *h_jnt_mouth_up*
30 *h_jnt_tooth_low*
31 *h_jnt_tooth_up*
32 *h_jnt_lhand*
33 *h_jnt_rhand*
34 *h_jnt_hair12*
35 *h_jnt_hair15*
36 *h_jnt_hair18*
37 *h_jnt_hair21*
38 *h_jnt_hair23*
39 *h_jnt_hair25*
40 *h_jnt_hair6*
41 *h_jnt_hair9*
42 *h_jnt_ltip1*
43 *h_jnt_ltip2*
44 *h_jnt_ltip4*
45 *h_jnt_ltip6*
46 *h_jnt_ltip7*
47 *h_jnt_rtip1*
48 *h_jnt_rtip2*
49 *h_jnt_rtip4*
50 *h_jnt_rtip6*
51 *h_jnt_rtip7*
52 *h_jnt_hair10*
53 *h_jnt_hair13*
54 *h_jnt_hair16*
55 *h_jnt_hair19*
56 *h_jnt_hair22*
57 *h_jnt_hair24*
58 *h_jnt_hair26*
59 *h_jnt_hair7*
60 *h_jnt_ltip3*
61 *h_jnt_ltip5*
62 *h_jnt_rtip3*
63 *h_jnt_rtip5*
64 *h_jnt_hair11*
65 *h_jnt_hair14*
66 *h_jnt_hair17*
67 *h_jnt_hair20*
68 *h_jnt_hair8*
69 *h_ik_l1*
70 *h_ik_r1*
71 *h_ik_l2*


ltips' par id: 26, rtips' par id: 27, doesn't make sense to me
but parenting seems to be ok so far:



0252_parenting.jpg (45.15 KiB) Viewed 154 times
## Post #3
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-05-13T02:45:52+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from shakotay2
>
> I feel the slight banter
Kkkk a slight banter, but I really meant it, you're one of the best I've ever seen extracting animations (no jokes this time  ). 

> Reply from shakotay2
>
> Anyway, 0252_01h.gmi bone names contain too much "hair", too less "finger",
(is it "tip?", then why there's 7 of them? ok: 2,3, 4,5 some kind of "economy" fingers  ), 
parenting ids: first byte in this sequence: 03 00 88 00 88 00):
It seems like "tip" is an extra bone for index and middle fingers. I guess they didn't have resources for the other fingers   



.gmi files can be opened with Noesis:
- 0250_01.gmi is the model
- 0250_01h.gmi is the hair
- I guess 0250_01s.gmi should be some sort of default skeleton, but I really don't know.



Weird thing is that Noesis loads the bones, but doesn't export them...

Well, since the model can be exported to 3DSMAX and you've seem to have loaded the bones, is there a script that could load the .gai animation?

I'm re-uploading Dragon model (with textures this time): [http://www.mediafire.com/download/jiem4 ... xtures.rar](http://www.mediafire.com/download/jiem4vr2f2bk3ee/Dragon+with+textures.rar)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-13T08:31:00+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from asdasd123
>
> Kkkk a slight banter, but I really meant it, you're one of the best I've ever seen extracting animations (no jokes this time  ).It's the title "animation genius" which you used so unwise, hahaha.
There's only one animation genius in this forum, MrAdults, just to keep you informed .
The other, fatduck, has left since some time. (There's also chrrox, who might come close.)

There's some other guys "who know what they're doing" when it comes to animations.
(Me, I'm only an apprentice with animations, though I still hope to have my hex2skeleton extractor released some day.)

> It seems like "tip" is an extra bone for index and middle fingers. I guess they didn't have resources for the other fingersyep, that's what I meant with economic.

> .gmi files can be opened with Noesis:Really would have spared me some time if you guys told the whole truth with your requests  

> Weird thing is that Noesis loads the bones, but doesn't export them...use smd format for example for export: 


gmi-skel-Noesis_smd_export.jpg (67.28 KiB) Viewed 142 times



> Well, since the model can be exported to 3DSMAX and you've seem to have loaded the bones,dunno what you mean - I've used blender to import an smd created by my extractor (unfinished).

> is there a script that could load the .gai animation?Has to be written, I guess.

In 5875_00_01_00.gai there's 60 bones and (maybe) 60x25 animation frames.
## Post #5
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-05-14T16:09:41+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from shakotay2
>
> It's the title "animation genius" which you used so unwise, hahaha.
There's only one animation genius in this forum, MrAdults, just to keep you informed .
The other, fatduck, has left since some time. (There's also chrrox, who might come close.)

There's some other guys "who know what they're doing" when it comes to animations.

Ow, didn't know that   . Still think your scripts are good though  

> Reply from shakotay2
>
> Has to be written, I guess. In 5875_00_01_00.gai there's 60 bones and (maybe) 60x25 animation frames.

Would it be too much to ask you if you could write one? Or least point me on the right direction   
And if you'd need any help at all, I'm here to google/search/do any repeated work required!

As you can see I'm kinda passionate about the animations
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-14T18:58:39+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from asdasd123
>
> Would it be too much to ask you if you could write one?On a quick glance there's too many unknowns.
In 5875_00_01_00.gai for example at 0xE76 there's an index table interrupted
22 times by 0102010601
offset 0F3E 0001 010102010601 72 61 0000
offset 1BA6 0001 010102010601 60 BF 0000

offset 0x2220 00 0102010601  7E 3E 0000

I'm too busy atm to dig deeper.

> Or least point me on the right directionYou could try to modify the PerfectWorld stck script.
At 0x2930 in the above mentioned .gai there might start translations.

Load the skeleton into 3dsmax then start the modified script to apply animations.
## Post #7
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-05-15T00:53:50+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from shakotay2
>
> asdasd123 wrote:Would it be too much to ask you if you could write one?On a quick glance there's too many unknowns.
In 5875_00_01_00.gai for example at 0xE76 there's an index table interrupted
22 times by 0102010601
offset 0F3E 0001 010102010601 72 61 0000
offset 1BA6 0001 010102010601 60 BF 0000

offset 0x2220 00 0102010601  7E 3E 0000

Ok, I've just spent the last 3 hours looking at this hex... 
...and considering I've just found out that hex values are written from right to left, that's proof that I don't really know what I was looking for   

However I do remember you've once told me to look for patterns, so I'm hoping I've found something useful:

I used IDA software to disassemble the .gai and found something that reminds me of an index

The offsets in red seem to be the index for different offsets on the table you've found.
And some (but not all) of the addresses on the second column (blue) point towards different "chunks of data" with 3 values separated by commas (x,y,z maybe?)



Does this mean something?

You've once said that you need to find rotations, translations, (and something else I've forgotten). Does every animation have them? If I find those would it be possible to import the animation? What should I be looking for?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-15T20:07:39+00:00
- Post Title: Importing  .gai  animation [PS2] - here comes a new challeng

> Reply from asdasd123
>
> I used IDA software to disassemble the .gai and found something that reminds me of an indexwell, creative (or funny?) idea to use IDA for such  

> The offsets in red seem to be the index for different offsets on the table you've found.
>
> And some (but not all) of the addresses on the second column (blue) point towards different "chunks of data" with 3 values separated by commas (x,y,z maybe?)
>
> 
>
> Does this mean something?I'm sorry to say that it doesn't (as far as I can see).
There's positions (or maybe quaternions) from 0x2930 upto file's end.

And the most obvious thing which I can't understand how you could overlook this during all your research:
at 0xB60 there's that offset: 0x2930
There's 49 offsets following which are the key to divide up the animation data block, I guess.
Into chunks of 105 frames or something like that.

There's counts at the beginning of the file: 0x0008: 60 bonecount, 0x000C: 20 unkn count
And there's those useless(?) indices tables with a range from 0x9C to 0xFF.

> You've once said that you need to find rotations, translations, (and something else I've forgotten).scaling

> Does every animation have them?in most cases, yes

> If I find those would it be possible to import the animation?Look at the data at 0x2930. Learn more about transitions, rotations, quaternions. Try to understand how the PerfectWorld maxscript works.
(I'd try to convert quaternions to euler if there are some.)

You could delete the translation part and try rotations only:

```
	    (
		    rot = RotationAnimation()
		    rot.BoneId = i
		    rot.KeyFrame = i*200-10
		    x = ReadFloat stream
		    y = ReadFloat stream
		    z = ReadFloat stream
		    w = ReadFloat stream
			
		    rot.Quaternion = quat x y z w
	
		    append allRotations rot
	    )

```


I just discovered that the order of bonenames in 5875_00_01_00.gai is totally different from 0252_01h.gmi.
Which gmi does the gai belong to?
