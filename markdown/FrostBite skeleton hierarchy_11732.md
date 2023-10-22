## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-07-27T10:27:39+00:00
- Post Title: FrostBite skeleton hierarchy

Hi,
So I`m trying to figure out how skeleton hierarchy work in frostbite games. The hierarchy that is laid out in the file does not make much sense in 3ds max for me and I cannot find a proper way of how to parent the bones using skeleton file. So I turn to you guys for help with this, as I know you have tons of experience with this.
Here is the skeleton file [https://dl.dropboxusercontent.com/u/881 ... tSke01.txt](https://dl.dropboxusercontent.com/u/88155050/BF3/Mesh%20Research/VeniceAntSke01.txt)
and here is my maxsript that deals with it [https://dl.dropboxusercontent.com/u/881 ... 81.3%29.ms](https://dl.dropboxusercontent.com/u/88155050/BF3/Mesh%20Research/Bone_Maker%281.3%29.ms)

Guys please give me a hand with this   

thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-27T21:06:28+00:00
- Post Title: FrostBite skeleton hierarchy

not sure what you mean.
Check whether your parenting looks like this:
bonename boneparentname
 Spine Hips
 Spine1 Spine
 Spine2 Spine1
 LeftShoulder Spine2
 LeftArm LeftShoulder
 LeftArmRoll LeftArm
 LeftForeArm LeftArmRoll
 LeftForeArmRoll LeftForeArm
 LeftForeArmRoll1 LeftForeArmRoll
 LeftHand LeftForeArmRoll
 LeftHandMiddle0 LeftHand
 LeftHandMiddle1 LeftHandMiddle0
 LeftHandMiddle2 LeftHandMiddle1
 LeftHandMiddle3 LeftHandMiddle2
 LeftHandMiddle4 LeftHandMiddle3
## Post #3
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-07-27T22:10:47+00:00
- Post Title: FrostBite skeleton hierarchy

> Reply from shakotay2
>
> not sure what you mean.
Check whether your parenting looks like this:
bonename boneparentname
 Spine Hips
 Spine1 Spine
 Spine2 Spine1
 LeftShoulder Spine2
 LeftArm LeftShoulder
......

Well it seems it`s using integer based hierachy like this:
hips            =  1
spine          =  4
spine1        = 5
spine2        = 6
leftshoulder = 7   

[https://www.dropbox.com/s/9y8h8m9fvn7jag5/Capture.PNG](https://www.dropbox.com/s/9y8h8m9fvn7jag5/Capture.PNG)

      and so on. Tried many different ways using arrays, offsetting them, reversing them. Getting different results but not what I want. And doing it by hand gets very messy as I go near the facebones. Just can`t figure out the proper parenting routine.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-27T22:55:13+00:00
- Post Title: FrostBite skeleton hierarchy

in your script
after this line: BoneParent = hierarchy_array
insert	
 BP_ID = BoneParent as integer +1

instead of 
if (BoneParent != -1) then
 newBone.parent = BNarr
use
if (BP_ID!=0) then newBone.parent = BNarr[BP_ID]
## Post #5
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-07-28T16:31:28+00:00
- Post Title: FrostBite skeleton hierarchy

> Reply from shakotay2
>
> in your script
after this line: BoneParent = hierarchy_array
insert	
 BP_ID = BoneParent as integer +1

instead of 
if (BoneParent != -1) then
 newBone.parent = BNarr
use
if (BP_ID!=0) then newBone.parent = BNarr[BP_ID]

Thank you so much Shakotay2, it works like a dream. Big thanks again. ;]
## Post #6
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2014-08-01T03:08:03+00:00
- Post Title: FrostBite skeleton hierarchy

Just curious but does this mean you can extract Frostbite engine-run game assets with intact in-game skeletons and weights already (cough Battlefield 4 cough)?
## Post #7
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-08-20T20:01:41+00:00
- Post Title: FrostBite skeleton hierarchy

> Reply from artworkplay
>
> Just curious but does this mean you can extract Frostbite engine-run game assets with intact in-game skeletons and weights already (cough Battlefield 4 cough)?

Yes and no. For now I have only released a version that works with BF3 and MOHWF.
And version for BF4, BFHL ,Plants vs Zombies and Need for speed rivals is coming soon.
[https://www.youtube.com/watch?v=GyBvFlj ... LUHUfcuvSA](https://www.youtube.com/watch?v=GyBvFljTNwE&list=UU0N16omoshHu4LUHUfcuvSA)
