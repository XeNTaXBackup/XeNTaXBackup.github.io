## Post #1
- Username: harky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 05, 2018 5:58 am
- Post datetime: 2019-11-15T18:49:48+00:00
- Post Title: Elsword motion files

just some motion files, load editing programs and etc... I would like to know if anyone has any idea why this happens, I will leave a link with two motion files, one that load and one that doesn't,if it is possible someone give me a help or explanation of why this happens, thank you in advance

[https://www.mediafire.com/file/bm2r59z0 ... u.rar/file](https://www.mediafire.com/file/bm2r59z0q8ene7n/Motion_Lu.rar/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-15T20:12:07+00:00
- Post Title: Elsword motion files

The "not loading" one with signature "KSM" is uncompressed, contains mesh, bones and (assumed) animation frames.
.



Motion_Lu-mesh.png (84.49 KiB) Viewed 457 times
## Post #3
- Username: harky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 05, 2018 5:58 am
- Post datetime: 2019-11-15T22:53:42+00:00
- Post Title: Elsword motion files

> Reply from shakotay2 ↑Sat Nov 16, 2019 4:12 am at Sat Nov 16, 2019 4:12 am
>
> 
The "not loading" one with signature "KSM" is uncompressed, contains mesh, bones and (assumed) animation frames.
.
Motion_Lu-mesh.png

Is there any way to "extract" what's inside?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-16T07:59:50+00:00
- Post Title: Elsword motion files

why not? You could start to build a skeleton with hierarchy, bones are easy to find:

RWeapon_Position
   Bip01_Footsteps
   Bip01_Pelvis   Bip01_Spine
   Bone01   Bone03   Bone05   Bone07
COLLISION_SPHERE3_Lowbody

Bip01_Head
Bip01_L_Clavicle   
Bip01_R_Clavicle
Bip01_R_UpperArm   
Bip01_R_Forearm   
Bip01_R_Hand   
Dummy01_RWeapon

Bone_RForearm

Bone_RHand   
ATTACK_SPHERE1_Rfoot

...

Bip01_Ponytail11   
Bip01_Ponytail12   
Bip01_Ponytail1Nub
Bip01_R_Calf   
Bip01_R_Foot   
Bip01_R_Toe0   
Bip01_R_Toe0Nub   
Bip01_L_Calf   
Bip01_L_Foot   
Bip01_L_Toe0   
Bip01_L_Toe0NubKAC

In case you can't do it you need to wait for someone who can.
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-19T13:23:45+00:00
- Post Title: Elsword motion files

Regarding Elsword, I believe that this directx animation file itself was probably converted (or produced) by a third party.
I checked older clients (2011,2014) and since that time KSM has been used for character animation and the format has not been changed until now.
the KSM format has been uploaded to github (2014).
There is also a firm file separation within the KSM, and the animation seems to start with the KAC as a header.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-19T13:49:51+00:00
- Post Title: Elsword motion files

yeah, well, since we have two skeleton builder apps now, I might give the skeleton a go. But I'm too busy with other things. (Like always...   )
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-19T16:17:46+00:00
- Post Title: Elsword motion files

I took a quick look and made a test plugin. (Maybe I'll add weight later)


> Reply from shakotay2 ↑Mon Dec 19, 2022 9:49 pm at Mon Dec 19, 2022 9:49 pm
>
> 
I might give the skeleton a go
( ̶n̶e̶e̶d̶ ̶p̶a̶r̶e̶n̶t̶s̶)Edit: I sloved it:

[fmt_ksm.zip](https://xentaxbackup.github.io/file/23157_fmt_ksm.zip)
## Post #8
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-19T22:15:10+00:00
- Post Title: Elsword motion files

> Reply from Durik256 ↑Tue Dec 20, 2022 12:17 am at Tue Dec 20, 2022 12:17 am
>
> 
I took a quick look and made a test plugin. (Maybe I'll add weight later)

Thank you!
I know there is a mesh file in directx format for just the mesh for this game, but it is very fragmented, so being able to preview it as a cohesive model in ksm would be very useful! Perhaps it is a reference for animation in game.

I have recently learned to use skeletal animation conversion from vertex animation using NinjaRipper2,
so having the base bone information would be very useful for capturing. Of course, whether or not I actually do that is another story...

It would be very nice to have animations available as well, as this game seems to employ very good animations.
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-19T22:33:04+00:00
- Post Title: Elsword motion files

> Reply from einherjar007 ↑Tue Dec 20, 2022 6:15 am at Tue Dec 20, 2022 6:15 am
>
> 
very good animations.
I still don’t understand why ksm is needed if there is such a *.x (DirectX) file which can be opened
## Post #10
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-19T22:42:03+00:00
- Post Title: Elsword motion files

> Reply from Durik256 ↑Tue Dec 20, 2022 6:33 am at Tue Dec 20, 2022 6:33 am
>
> 
einherjar007 wrote: ↑Tue Dec 20, 2022 6:15 am
very good animations.

I still don’t understand why ksm is needed if there is such a *.x (DirectX) file which can be opened
As for animation, only data beginning with KAC in KSM. The game does not use dirextx animations for the human characters. We believe that these animations were created or converted by a third party.

*Edit
Here are some samples. Files are very scattered and will be added when main characters and other files are found.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1KO91_8NS5Wb6C1wGDctjtJEfSgNMq7xM?usp=sharing)

Here is the source for the animation controller KAC within KSM.
[https://github.com/haywoodspartan/Elswo ... roller.cpp](https://github.com/haywoodspartan/Elsword-Source-2014/blob/5b4c1c040314e90ec3e541f2d75bf31b5062da91/KTDXLIB/KTDXAnimationController.cpp)

The KAC is followed by the version, number of animation sets, etc. Animation near separators can be found at 00 00 00 00 00 02 00 00 00 00 00, with exceptions depending on the file.
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-20T02:59:27+00:00
- Post Title: Elsword motion files

I started making and it turns out you have the source code.  haha, I feel like I wasted my time.  I won't continue anymore... I'll leave what I did here.
## Post #12
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-20T03:06:50+00:00
- Post Title: Elsword motion files

> Reply from Durik256 ↑Tue Dec 20, 2022 10:59 am at Tue Dec 20, 2022 10:59 am
>
> 
I started making and it turns out you have the source code.  haha, I feel like I wasted my time.  I won't continue anymore... I'll leave what I did here.
Sorry if I have offended you. I was just trying to introduce the information I found to help.
By the way, I have been gradually researching the format lately and will try my best to build on the data you left.

"Good men mean well. We just don't always end up doing well."
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-20T15:04:03+00:00
- Post Title: Elsword motion files

i made plugin for Noesis
for *.x files [KSM(mesh) and KAC(animations)]



couple animations ("Walk_D", "Walk"):



Motion_Lu.x.gif (255.17 KiB) Viewed 225 times
## Post #14
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-20T21:50:56+00:00
- Post Title: Elsword motion files

> Reply from Durik256 ↑Tue Dec 20, 2022 11:04 pm at Tue Dec 20, 2022 11:04 pm
>
> 
I'm not offended in any way, just why reinvent the wheel when the source code is available. this is not the first time. I after all spent the time that from scratch to sort a format.  

**(remove image from quote  )

Thank you! I didn't mean to offend. I was just following someone's previous request to create a Cocos2D plugin, for which they were grateful to find the source code. I think people take it differently.

By the way, I think I can handle this format. The part you prepared has already been very helpful. I am not familiar with Noesis functions so I will have to do it differently, but I think I can get the results.

And I have learned to remove images from quotes. Will be careful next time!
## Post #15
- Username: ProbiusPrime
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 06, 2023 5:17 pm
- Post datetime: 2023-01-07T04:34:37+00:00
- Post Title: Elsword motion files

image >> [https://ibb.co/VBqJtqT](https://ibb.co/VBqJtqT)
(img tag doesnt work. sorry)

How did you guys see that animations?

I need this game's motion, and used fmt.py on the top thread.
But I can't see animation. I can see only like this.
What should I do to extract these animations for other tools like blender?
