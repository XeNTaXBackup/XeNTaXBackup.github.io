## Post #1
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-12-30T14:17:53+00:00
- Post Title: fmo animations

Now that model edits on fml models are possible,i think its time to move onto animations and they are fmo animations.
The bones have been already figured out by gh0stblade and he has made a script to load the bones in noesis although the script doesnt work with mesh. But it loads all the bone correctly

Here is the python script for noesis by gh0stblade- [https://www.sendspace.com/file/xfvkw4](https://www.sendspace.com/file/xfvkw4)



Following is the bone hierarchy inside the model
MDL - 6 Child
n_CTR - 1 Child
o_body - 2 Child
j_chest - 3 Child
o_sako_l - 1 Child
j_u_arm_l - 1 Child
j_f_arm_l - 1 Child
HAND_L - 0 Child
o_sako_r - 1 Child
j_u_arm_r - 1 Child
j_f_arm_r - 1 Child
HAND_R - 0 Child
j_neck_a - 1 Child
j_neck - 0 Child
n_waist_b - 2 Child
j_thigh_l - 1 Child
j_leg_l - 1 Child
L_FOOT - 0 Child
j_thigh_r - 1 Child
j_leg_r - 1 Child
R_FOOT - 0 Child
L_SKIN - 0 Child

Here is a model file -[https://www.sendspace.com/file/hkuhpy](https://www.sendspace.com/file/hkuhpy)

Here is the animation structure

i think its a simple animation format. What makes it simple is that the content of the fmo file contains name of the bone,after bone comes their corresponding animation.



I'm attaching some animation files here -[https://www.sendspace.com/file/qdn7ro](https://www.sendspace.com/file/qdn7ro)

It would be great if someone helps out on this. If this is possible i can make custom animations for the game.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-30T22:00:04+00:00
- Post Title: fmo animations

looks like most of your post was plucked right from this thread   
[viewtopic.php?f=16&t=13978](http://forum.xentax.com/viewtopic.php?f=16&t=13978)

why so many threads on same format, research will get buried or overlooked  

Noesis fml script by Gh0stBlade is here btw, no need for external filehost   
[viewtopic.php?p=117176#p117176](http://forum.xentax.com/viewtopic.php?p=117176#p117176)
## Post #3
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-12-30T23:20:40+00:00
- Post Title: fmo animations

> Reply from AceWell
>
> looks like most of your post was plucked right from this thread   
viewtopic.php?f=16&t=13978

why so many threads on same format, research will get buried or overlooked  

Noesis fml script by Gh0stBlade is here btw, no need for external filehost   
viewtopic.php?p=117176#p117176

That was the model file,this is about the animations bro.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-01T11:48:02+00:00
- Post Title: fmo animations

you'll have to find out what the data means - it's not too obvious:



fmo_anims.JPG (52.63 KiB) Viewed 95 times


For translation/rotation we'd expect 3 or four floats; here it's only two (green).
Are the dwords (blue) the frame time? strange: 60, 76, 98, 124, 154, 176, 200, 216
Normally time offset is equal-distant.
