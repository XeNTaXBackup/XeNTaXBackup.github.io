## Post #1
- Username: nemix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 08, 2016 2:23 am
- Post datetime: 2017-08-18T12:21:41+00:00
- Post Title: Dragon Ball Online [Renderware Engine] Models & Rigs

Hi guys, I'm close to becoming part of the dragonball online global development team
the rest of the team is working on the game, fixing it and bringing it back for many years
im supposed to bring new 3d content to the game but thats for later
my job is to find a way to add new meshes ingame

extracting is no problem i even made a video
[https://youtu.be/wLZ-bY5Yi-w](https://youtu.be/wLZ-bY5Yi-w)

with shakotays tool from 2013 [https://forum.xentax.com/memberlist.php ... le&u=41194](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=41194)

but sadly his tool converts the .dff hex data to obj

best would be a fbx format for me with a skeleton and the model should be already rigged

so i can use that rig and add new meshes and assign them to that skeleton

since its renderware, same engine for gta sa and gta sa has been modded a lot with new meshes and animations
maybe some modding genius can help me find a way to do the same for dragonball online dff mesh files
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-18T16:53:30+00:00
- Post Title: Dragon Ball Online [Renderware Engine] Models & Rigs

> Reply from nemix
>
> but sadly his tool converts the .dff hex data to objyes, too sad.

Couldn't he have created an fbx format with a skeleton and the model already rigged? This lazy-bones!

Anyways, here's a slightly extended version that's logging the offset addresses of verts, uvs and face indicies blocks.


 DBallExtract_log.zip
(85.14 KiB) Downloaded 31 times


(That should help you to code your own tool which is capable of whatever you wish.)

edit: for the bones, it's no fun, annoying, to be honest, not continous, how serious developers would do, but with breaks (thus restart the counting with 0), really hate such:

0 "Bip01 Pelvis"
1 "Bip01 Spine"
2 "B_tail1"

0 "Bip01 Spine1"
1 "Bip01 R Thigh"
2 "Bip01 L Thigh"
3 "Bip01 L Calf"
4 "Bip01 L Foot"
5 "Bip01 L Toe0"
6 "Bip01 R Calf"
7 "Bip01 R Foot"
8 "Bip01 R Toe0"
9 "Bip01 Neck"
10 "B_bust"

0 "Bip01 R Clavicle"
1 "Bip01 L Clavicle"
2 "Bip01 Head"
3 "B_H5"

0 "Bip01 L UpperArm"
1 "Bip01 L Forearm"
2 "Bip01 L Hand"
3 "Bip01 L Finger2"
4 "Bip01 L Finger1"
5 "Bip01 L Finger0"
6 "Bip01 R UpperArm"
7 "Bip01 R Forearm"
8 "Bip01 R Hand"
9 "Bip01 R Finger2"
10 "Bip01 R Finger1"
11 "Bip01 R Finger0"
## Post #3
- Username: nemix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 08, 2016 2:23 am
- Post datetime: 2017-08-18T17:51:38+00:00
- Post Title: Dragon Ball Online [Renderware Engine] Models & Rigs

Thanks a lot i hope we can work on a functioning tool 

thanks for all the support
