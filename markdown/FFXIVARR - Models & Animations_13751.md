## Post #1
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-01T05:54:33+00:00
- Post Title: FFXIV:ARR - Models & Animations

Hello there! There's now a model viewer for static models for ARR. I'm wondering if anyone is able to make a 3DS Max script to import the models and animations?

Seems like the models are in the .mdl format with skeleton as .sklb and animations as .pap?

Sample files: [https://www.mediafire.com/?ep213w977yce1ky](https://www.mediafire.com/?ep213w977yce1ky)
## Post #2
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-03T00:06:20+00:00
- Post Title: FFXIV:ARR - Models & Animations

Welp, I guess no one wants to try this? I can offer up to $150 USD if anyone can complete a working script.
## Post #3
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2016-01-07T22:56:55+00:00
- Post Title: FFXIV:ARR - Models & Animations

I've tried to use FFXIV data explorer on .dat archives of the FFXIV:ARR to export some models in .obj format, the .obj files were created but they didn't open in any 3d programm that i have. In the Explorer models loaded without any trouble. Maybe new version of 3dsMax can open those obj, or it is just everyone issue?
## Post #4
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-08T00:17:08+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from Splasher9
>
> I've tried to use FFXIV data explorer on .dat archives of the FFXIV:ARR to export some models in .obj format, the .obj files were created but they didn't open in any 3d programm that i have. In the Explorer models loaded without any trouble. Maybe new version of 3dsMax can open those obj, or it is just everyone issue?

I have no problems with exporting .obj's with the explorer and opening them in 3ds max 2012/2015 nor blender. Thing is, I'm looking to use the animations as well as models.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-08T09:19:20+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from Keezie
>
> Thing is, I'm looking to use the animations as well as models.Thing is that's it's a little bit harder to get animations. At first you need the skeleton bones, their parenting, the weights for the skinning.
Then you have to care for the animation frames. (Even worse animation data may be compressed.)

That's the reason why most animation requests aren't satisfied too soon.  



m8004b0001.jpg (171.37 KiB) Viewed 625 times



For the bones: can you translate their names to english?

n_hara
n_asi_a_l
n_asi_a_r
n_kami_l
n_kami_r
n_kao
n_kosi
n_ude_l
n_ude_r
n_asi_b_l
n_asi_b_r
n_hana
n_sippo_a
n_umab_l
n_umab_r
n_sippo_b
## Post #6
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-09T01:19:36+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> 

For the bones: can you translate their names to english?

n_hara
n_asi_a_l
n_asi_a_r
n_kami_l
n_kami_r
n_kao
n_kosi
n_ude_l
n_ude_r
n_asi_b_l
n_asi_b_r
n_hana
n_sippo_a
n_umab_l
n_umab_r
n_sippo_b

This is the best I can come up with:

n_hara - stomach
n_asi_a_l - leg / foot (a) (left)
n_asi_a_r - leg / foot (a) (right)
n_kami_l - hair/head(left)
n_kami_r - hair/head (right)
n_kao - face
n_kosi - waist/hip
n_ude_l - arm (left)
n_ude_r - arm (right)
n_asi_b_l - leg / foot (b) (left)
n_asi_b_r - leg / foot (b) (right)
n_hana - nose
n_sippo_a - tail part a
n_umab_l - [mabu? - eyelid] (left)
n_umab_r - [mabu? - eyelid] (right)
n_sippo_b - tail part b
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-09T03:51:16+00:00
- Post Title: FFXIV:ARR - Models & Animations

FFXIV - Square Enix - Japan

Google translator says this
hara - belly
asi - leg
kami - hair
kao - face
kosi - hip
ude - arm
hana - flower
sippo - tail
umab - horse b (?)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-09T11:37:52+00:00
- Post Title: FFXIV:ARR - Models & Animations

thx for the translations, folks.
Will use it next time when trying to build the skeleton.
## Post #9
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-10T04:52:49+00:00
- Post Title: FFXIV:ARR - Models & Animations

I've just noticed that the files original formats can be converted into .hkx and played with havok content tools. Here is a sample of the .hkx working with the 64bit stand alone: [http://www.mediafire.com/download/mqep4 ... /m0071.rar](http://www.mediafire.com/download/mqep4q65jzhodjp/m0071.rar)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-10T07:48:04+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from Keezie
>
> I've just noticed that the files original formats can be converted into .hkxhow?
## Post #11
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-10T08:07:22+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> Keezie wrote:I've just noticed that the files original formats can be converted into .hkxhow?

With IonCannon's FFXIV: Model Viewer, you can export as raw or his format which strips the FFXIV header [supposedly] and leaves the base .hkx which havok can open.
You can get the viewer here: [http://ffxivexplorer.fragmenterworks.co ... _64bit.zip](http://ffxivexplorer.fragmenterworks.com/downloads/v1_6/ffxiv_explorer_1_6_64bit.zip)

Do you think you could work this into a script? :O
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-10T10:14:52+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from Keezie
>
> With IonCannon's FFXIV: Model Viewer, you can export as raw[...]
Do you think you could work this into a script? :Othx - I see, a .index file from the game is needed to use this Viewer/Exporter.
As I PMed, I'm not working on a script but I will try to create a skeleton asap (smd format).

For the animations it could be helpfull if you uploaded a raw export of monster.pap if possible.
## Post #13
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-10T10:32:35+00:00
- Post Title: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> Keezie wrote:With IonCannon's FFXIV: Model Viewer, you can export as raw[...]
Do you think you could work this into a script? :Othx - I see, a .index file from the game is needed to use this Viewer/Exporter.
As I PMed, I'm not working on a script but I will try to create a skeleton asap (smd format).

For the animations it could be helpfull if you uploaded a raw export of monster.pap if possible.

Here's the monster.pap that goes along with that monster: [https://www.mediafire.com/?50qdz7k2nb39qwa](https://www.mediafire.com/?50qdz7k2nb39qwa)
## Post #14
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-12T23:04:05+00:00
- Post Title: FFXIV:ARR - Models & Animations

Any progress shakotay2?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-12T23:12:43+00:00
- Post Title: FFXIV:ARR - Models & Animations

expect me at the first light on the fifth day...(skeleton only)
## Post #16
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-18T16:31:18+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> expect me at the first light on the fifth day...(skeleton only)

Will he light the fires of gondor?
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-18T17:14:43+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

He should burn in the fires of Gondor, since he broke his promisses.  

Well, still quarreling with how to build the matrices i.e. how to format the data?
Like this:
0.000000 0.000000 0.000000 0.000000 
1.000000 1.000000 1.000000 1.000000 
0.000000 0.076563 -0.067450 -0.137815 

0.000000 -0.272357 0.652550 -0.272357 
0.652550 1.000000 1.000000 1.000000 
0.000000 -0.076563 -0.067450 -0.137815 

or like this?
0.000000 0.000000 0.000000 1.000000 
1.000000 1.000000 1.000000 0.000000 
0.076563 -0.067450 -0.137815 0.000000 

-0.272357 0.652550 -0.272357 0.652550 
1.000000 1.000000 1.000000 0.000000 
-0.076563 -0.067450 -0.137815 0.000000 

There's some reason to take the latter, because
square sum of these components is near to 1.0:
-0.272357 0.652550 -0.272357 0.652550 (rotation quaternion?)

so -0.076563 -0.067450 -0.137815 0.000000 
might be the position.

(In fact I'm unsure and a little bit exhausted from Saint Seiya anims.)

I didn't even get the bones hierarchy - so continuing is rather useless atm.

Does anyone know any skeleton from any format that uses similar bone names as asi, kosi?

- well, should have looked at the other example earlier: there's english bone names

but doesn't help either - can't seem to find where the j_legs can be found here: 



m8005b0001_mdl.jpg (44.17 KiB) Viewed 304 times



Would just need a model sample with head, pelvis, arm and leg (strings in sklb and mdl file).
## Post #18
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-24T18:52:37+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

@shakotay2, I didn't realize you had updated your post. Here is another model with legs, arms, a head, and some other bits and pieces: [https://www.mediafire.com/?lbdxpa4hj9d9mk3](https://www.mediafire.com/?lbdxpa4hj9d9mk3)

There are hundreds of models that I can extract if you'd like, would just take a bit of time.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-24T19:31:01+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

> Reply from Keezie
>
> Here is another model with legs, arms, a head, and some other bits and pieces:
well, this one has kosi, kubi, sako.  

> There are hundreds of models that I can extract if you'd like, would just take a bit of time.I'd need one only, but with "arm" and "leg" as bone names, please.

(btw: don't hurry, as always, I'm very busy)
## Post #20
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-24T21:08:29+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> Keezie wrote:Here is another model with legs, arms, a head, and some other bits and pieces:
well, this one has kosi, kubi, sako.  
There are hundreds of models that I can extract if you'd like, would just take a bit of time.I'd need one only, but with "arm" and "leg" as bone names, please.

(btw: don't hurry, as always, I'm very busy)

Oh, the english "arm" and "leg" as bone names. This will take awhile!

Edit: Found one so far: [http://www.mediafire.com/?3ggb5t98s3fh521](http://www.mediafire.com/?3ggb5t98s3fh521)
Edit2: Here's a second one with "arm" and "leg" as bone names. Animations are available for it as well: [https://www.mediafire.com/?tstdtszn8su2s4i](https://www.mediafire.com/?tstdtszn8su2s4i)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-24T22:09:02+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

thx! This will take a while - but i hope to get a decent skeleton at least...
## Post #22
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-24T22:22:43+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> thx! This will take a while - but i hope to get a decent skeleton at least...

You're welcome. Let me know if you need anymore files.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-27T21:05:40+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

well, in some rare cases things turn out to be much easier than expected:



m8008.JPG (100.37 KiB) Viewed 261 times
## Post #24
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-01-27T22:02:32+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

> Reply from shakotay2
>
> well, in some rare cases things turn out to be much easier than expected:

Yes, I noted the simple structure on that one so I figured it'd be the best to send.
## Post #25
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2019-08-20T09:54:07+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

Hey,

any updates?

Thank u
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-20T10:37:20+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

updates for what? Havok?
This thread is dead (since 3.5 years!) for good reasons.

You might inspect the Havok project by PredatorCZ:
[viewtopic.php?f=16&t=19691](https://forum.xentax.com/viewtopic.php?f=16&t=19691)
## Post #27
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2019-08-20T13:43:02+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

Thanks for your answer!

Ist Havok work with FFXIV?
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-20T14:49:21+00:00
- Post Title: Re: FFXIV:ARR - Models & Animations

dunno. All I know is the sample Keezie provided was loadable with Havok tools.
