## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2018-03-15T02:30:14+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

Hey Guys,

I really need help with hkx animations which I've extracted from Final Fantasy XIV.
They work on Havk Content Tools without problems, but converting this animations seems to be very tricky... and I was unable to get it to work yet.

My Setup:
- HavokContentTools_2014-1-1_20150216_32Bit_Anarchy
- Blender 2.79
- Maya 2015 & Maya 2017

Here's a video where I tested a animation in Havok Content Tools:
[https://www.youtube.com/watch?v=LkrCzYyG5Ck](https://www.youtube.com/watch?v=LkrCzYyG5Ck)

I've loaded both, the skeleton and the animation, and saved them both in a separate file again.
Reason: I've "converted" the Files I had from FFXIV to Havok hkx 2014.1.1
Both files were still working in Havok Content Tools when I loaded them both (like you can see it in the video above).

I've tried to convert both files to an fbx file by using havok2fbx with the command:
havok2fbx.exe -hk_skeleton skel.hkx -hk_anim anim.hkx -fbx test_animation.fbx

After converting the fbx with Noesis and/or Autodesk FBX Converter, I tried to load it in Autodesk Maya and Blender.
Both gave me the same result: a buggy animation.
Here's another video that shows the buggy animation:
[https://www.youtube.com/watch?v=KsIebJgCyPQ](https://www.youtube.com/watch?v=KsIebJgCyPQ)

I've linked the Model as FBX and the skeleton + animation as hkx.
I hope you'll be able to help me out with that.
[http://cellenseres.de/FFXIV/Mods/Cruise_Chaser.zip](http://cellenseres.de/FFXIV/Mods/Cruise_Chaser.zip) (660kb)

Thank you in advance!


.----.---.-.--.--.-..-....--..-.-.-.--.-.-..---.-.-.-.-.-.-.-.-.--.-.-...-..-.--.--.-.-.-.--.-.-.-.-..-.-...-.---.--
I've also tried this tutorial to convert the animation to FBX, without success (using HavokContentTools x32 since x64 won't work on my PC for whatever reason (I've win10 x64 installed)):

> Reply from dropoff
>
> 
Download havok 2014 firstly. Here is link:
https://drive.google.com/drive/folders/ ... WRDaEVacVE 
You need that file: HavokContentTools_2014-1-0_20140830_64Bit_PcXs.exe

Then you need to unpack data3.bnd with binder tool from game and find animations for character but here is already extracted files by me:
https://mega.nz/#!wp1x3aLZ!nr9cPhBaB3es ... 7-T9lb7L1g

I dont remember if this all main character animations but im shure most of them.

Now install and open up havok and click file/open and select skeleton from my "skeleton" folder then click file/add and choose any animation from hi/md/lo folder.
If you want to load another animation you need to remove old one but dont remove skeleton,remove only animation and then click add again and select new file.


You need to check a lot of files here. If you want gestures they are started at "a000_080000.hkx" file in hi folder.

When you found animation that you want to export select file/save.
Choose "XML (Cross Platform Text)" and save file with hkx extension.



Then you need to download fallout 4 animation tools here:
https://www.nexusmods.com/fallout4/mods/16694/?#content

Unpack tools and go to folder "F4AK_HKXPackUI" then run "f4ak_hkxpack_UI.exe".

Here in "skeleton.hkx" choose my converted skeleton from folder "Use_That_Skeleton_In_f4_animation_tools" and drop your exported from havok animation to "drag and drop" table.
Then press "Сonvert HKX to FBX" button.


You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-15T10:16:42+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

I also tried havok2fbx, but no luck.

You can check out some of the Fallout 4 modding tools. I think it uses the same Havok version as FFXIV.
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2018-03-15T11:29:09+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

> Reply from akderebur
>
> I also tried havok2fbx, but no luck.

You can check out some of the Fallout 4 modding tools. I think it uses the same Havok version as FFXIV.

I tried the Fallout 4 Modding tools already, check the lower part of my Post 
It's a Tutorial which uses the Fallout 4 Modding tools^^

Still: I had no luck with it yet.
I can convert them to FBX but the animation is kinda fucked up.

This is how it should look:
[https://www.youtube.com/watch?v=LkrCzYyG5Ck](https://www.youtube.com/watch?v=LkrCzYyG5Ck)

This is how it looks after converting:
[https://www.youtube.com/watch?v=KsIebJgCyPQ](https://www.youtube.com/watch?v=KsIebJgCyPQ)
## Post #4
- Username: solenrael
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 29, 2017 9:23 am
- Post datetime: 2018-03-18T03:59:25+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

I've been having this exact issue, regardless of what I tried. At one point 64bit was working (it's not now, for some reason) and that didn't work either - neither did importing it into blender with .ascii or the aforementioned hkx2fbx method.

I also tried converting it to Gamebryo KF format with Skyrim's hkxcmd, but this one may be user error, so you could try that and see if it works.
## Post #5
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2018-03-18T10:18:20+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

> Reply from solenrael
>
> I've been having this exact issue, regardless of what I tried. At one point 64bit was working (it's not now, for some reason) and that didn't work either - neither did importing it into blender with .ascii or the aforementioned hkx2fbx method.

I also tried converting it to Gamebryo KF format with Skyrim's hkxcmd, but this one may be user error, so you could try that and see if it works.

I've tried to convert the hkx to Gamebyro KF, too.
But the problem is, that this converter only supports hkx 2010 files. FFXIV uses hkx 2014 files.
I wasn't able to convert the animation and skeleton to 2010 version either.
## Post #6
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2018-03-25T07:03:58+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

Havok content is notorious for being impossible to extract because it is highly customizable, every single game has slightly different hkx files. So you need someone to write a new tool for every single game, but Xentax isn't interested. (trust me, I've tried)

Sorry, you're just out of luck.
## Post #7
- Username: razar51
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 07, 2018 2:08 am
- Post datetime: 2018-11-29T02:55:27+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

I looked into it since I also wanted to utilize ffxiv animations.

The reason you are getting the 'buggy' animation seems to be that the animation tracks are getting applied to the wrong bones in the skeleton.

The havok2fbx tool was not taking into account that ffxiv animations utilize hkaAnimationBinding to specify which bones the animation tracks apply to. It was assuming a 1-to-1 mapping of Track-Bone when ffxiv havok files seem to have more bones in the skeleton than tracks in the animation, so no 1-to-1 mapping.

I released a modified version of the tool here that should address that problem:
[https://github.com/razar51/havok2fbx/releases](https://github.com/razar51/havok2fbx/releases)

First time using GitHub to make a release so let me know if I screwed it up somehow.
## Post #8
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-12-11T21:09:19+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

> Reply from razar51
>
> I looked into it since I also wanted to utilize ffxiv animations.

The reason you are getting the 'buggy' animation seems to be that the animation tracks are getting applied to the wrong bones in the skeleton.

The havok2fbx tool was not taking into account that ffxiv animations utilize hkaAnimationBinding to specify which bones the animation tracks apply to. It was assuming a 1-to-1 mapping of Track-Bone when ffxiv havok files seem to have more bones in the skeleton than tracks in the animation, so no 1-to-1 mapping.

I released a modified version of the tool here that should address that problem:
https://github.com/razar51/havok2fbx/releases

First time using GitHub to make a release so let me know if I screwed it up somehow.

did anyone tried this method?

could someone provide me any models and animation from FFXIV ?
## Post #9
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2018-12-27T19:26:49+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

> Reply from razar51
>
> I looked into it since I also wanted to utilize ffxiv animations.

The reason you are getting the 'buggy' animation seems to be that the animation tracks are getting applied to the wrong bones in the skeleton.

The havok2fbx tool was not taking into account that ffxiv animations utilize hkaAnimationBinding to specify which bones the animation tracks apply to. It was assuming a 1-to-1 mapping of Track-Bone when ffxiv havok files seem to have more bones in the skeleton than tracks in the animation, so no 1-to-1 mapping.

I released a modified version of the tool here that should address that problem:
https://github.com/razar51/havok2fbx/releases

First time using GitHub to make a release so let me know if I screwed it up somehow.

Awesome job mate!
Works great with the most models I tried! 

But I'm a bit confused.
I've extracted a model sheet (.pap file) which should contain more than one Animation



when I open the skeleton and the extracted pap (hkx), it seems that the hkx has only one animation (or plays all of them at the same time?)
when converting this to an fbx, it only has one Animation in it :/

Probably you know how to fix that?

I've uploaded two files for you (anim.hkx and bones.hkx (skeleton))
[hkx.zip](https://xentaxbackup.github.io/file/15389_hkx.zip)
## Post #10
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-12-27T23:46:28+00:00
- Post Title: Convert "FFXIV hkx animation" to Blender/Unity/Maya?

@ChrisX930

Hey, you said you got it to work? Could you please make a video tutorial about the whole process? From exporting models/animations out of FFXIV/converting/Importing into Modeling program?
This would be very usefull and I would be greatfull and verry appreciated if you could help me out.

Thank you,
