## Post #1
- Username: AllHailTreesus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 16, 2016 10:18 am
- Post datetime: 2017-06-25T18:15:06+00:00
- Post Title: Dark Souls III HKX Animations

Does anybody know what converters, and specific version of Havok Tools I need to open Dark Souls III's .hkx animations? 
I've been desperately trying to find any forums or downloads that mention the right version, but I've found nothing.
## Post #2
- Username: zweihard
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 24, 2017 7:18 am
- Post datetime: 2017-07-31T21:40:36+00:00
- Post Title: Dark Souls III HKX Animations

Did you get any success?
## Post #3
- Username: imarceldoe
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 28, 2016 9:55 pm
- Post datetime: 2017-08-04T18:46:45+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from AllHailTreesus
>
> Does anybody know what converters, and specific version of Havok Tools I need to open Dark Souls III's .hkx animations? 
I've been desperately trying to find any forums or downloads that mention the right version, but I've found nothing.

It's the same ones Fallout 4 use.

Havok 2014 64 Bit.
## Post #4
- Username: zweihard
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 24, 2017 7:18 am
- Post datetime: 2017-08-18T14:47:31+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from imarceldoe
>
> AllHailTreesus wrote:Does anybody know what converters, and specific version of Havok Tools I need to open Dark Souls III's .hkx animations? 
I've been desperately trying to find any forums or downloads that mention the right version, but I've found nothing.

It's the same ones Fallout 4 use.

Havok 2014 64 Bit.

Really? How do you open them for previewing?
## Post #5
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-19T17:05:30+00:00
- Post Title: Dark Souls III HKX Animations

I was able to import animations to 3ds max,but here is some issues.

You need Havok 2014 64 Bit to open hkx from ds3.


I dont know how i can properly export from havok tool to 3ds max but with fallout 4 animation tools i was able to do it.

And when i apply animation to rigged model. Skeleton applies well and animations seems to work fine but meshes doesnt scale or something.

Im import model using zaramot script: [https://forum.xentax.com/viewtopic.php?f=16&t=14291](https://forum.xentax.com/viewtopic.php?f=16&t=14291)

BEFORE APPLY:

AFTER APPLY:
## Post #6
- Username: Madein
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 19, 2017 5:10 am
- Post datetime: 2017-10-19T22:40:08+00:00
- Post Title: Dark Souls III HKX Animations

Have you not been able to import the animation? What am I looking at with this screenshot? Can they be export into fbx files after 3ds max?
## Post #7
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-20T04:51:53+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from Madein
>
> Have you not been able to import the animation? What am I looking at with this screenshot? Can they be export into fbx files after 3ds max?

Edit: Im able to import animation but meshes do not scale on screenshot you can see what happens after animation import and you can export it to fbx.
## Post #8
- Username: Madein
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 19, 2017 5:10 am
- Post datetime: 2017-10-20T20:41:31+00:00
- Post Title: Dark Souls III HKX Animations

Awesome! The skeleton and the animation is all I really care for the moment. Renaming the bones using the ue4 mannequin's naming convention should allow the mannequin to use DS3 animation. Could you point me to a tutorial or something that would guide me through the process off ripping the files from DS3 and import the animations into a usable format in 3ds max or blender? 

Or did anyone made the files public somewhere?
## Post #9
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-20T22:21:13+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from Madein
>
> Awesome! The skeleton and the animation is all I really care for the moment. Renaming the bones using the ue4 mannequin's naming convention should allow the mannequin to use DS3 animation. Could you point me to a tutorial or something that would guide me through the process off ripping the files from DS3 and import the animations into a usable format in 3ds max or blender? 

Or did anyone made the files public somewhere?
Download havok 2014 firstly. Here is link:
[https://drive.google.com/drive/folders/ ... WRDaEVacVE](https://drive.google.com/drive/folders/0B8SgSQGjqypSS3JoZWRDaEVacVE) 
You need that file: HavokContentTools_2014-1-0_20140830_64Bit_PcXs.exe

Then you need to unpack data3.bnd with binder tool from game and find animations for character but here is already extracted files by me:
[https://mega.nz/#!wp1x3aLZ!nr9cPhBaB3es ... 7-T9lb7L1g](https://mega.nz/#!wp1x3aLZ!nr9cPhBaB3esNBeTfwojSpmwt_-TbEKsh7-T9lb7L1g)

I dont remember if this all main character animations but im shure most of them.

Now install and open up havok and click file/open and select skeleton from my "skeleton" folder then click file/add and choose any animation from hi/md/lo folder.
If you want to load another animation you need to remove old one but dont remove skeleton,remove only animation and then click add again and select new file.


You need to check a lot of files here. If you want gestures they are started at "a000_080000.hkx" file in hi folder.

When you found animation that you want to export select file/save.
Choose "XML (Cross Platform Text)" and save file with hkx extension.



Then you need to download fallout 4 animation tools here:
[https://www.nexusmods.com/fallout4/mods/16694/?#content](https://www.nexusmods.com/fallout4/mods/16694/?#content)

Unpack tools and go to folder "F4AK_HKXPackUI" then run "f4ak_hkxpack_UI.exe".

Here in "skeleton.hkx" choose my converted skeleton from folder "Use_That_Skeleton_In_f4_animation_tools" and drop your exported from havok animation to "drag and drop" table.
Then press "Сonvert HKX to FBX" button.


You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.
## Post #10
- Username: Madein
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 19, 2017 5:10 am
- Post datetime: 2017-10-23T18:56:17+00:00
- Post Title: Dark Souls III HKX Animations

Wow, that looks interesting and complicated. I will try that tonight and keep you updated. I am looking for the combat animation, like the light, heavy and special from various weapons. 

When you say that I need to unpack data3.bnd using the binder tool, is that tool and the data3.bnd in the links you provided?

Thank you so much for your help.
## Post #11
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-24T04:41:49+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from Madein
>
> 
When you say that I need to unpack data3.bnd using the binder tool, is that tool and the data3.bnd in the links you provided?
No i gave you link to already unpacked animations. Here if you want tool to unpack *.bnd:
[https://github.com/Atvaark/BinderTool/releases](https://github.com/Atvaark/BinderTool/releases)
Just drag *.bnd to *.exe.
## Post #12
- Username: Madein
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 19, 2017 5:10 am
- Post datetime: 2017-10-24T05:55:33+00:00
- Post Title: Dark Souls III HKX Animations

Okay, so a little update on your tutorial. 
It worked!
I was able to randomly find the roll animation. It's the a000_027110.hkx located in the c0000_a00_hi-(gesture_here) folder.
Once I converted the hkx into fbx I imported it into blender and 3ds max. 
Blender did not like it
[https://imgur.com/XRzNRmX](https://imgur.com/XRzNRmX)

But 3ds max was more tolerable. Orientation is messed up, but I think there is a way the put the animation in the right orientation, I just have yet to find how in 3ds max, I usually animate in blender. 
I then proceded to export the 3ds max animation into another fbx, then imported in into ue4. As predicted, it failed because there was no matching bones between the animation and the ue4 mannequin. I then found what I thought was the ''root'' in the animation skeleton (called ''master'') and renamed it to ''root'' I then tried to rename the whole skeleton from the animation using the naming convention of the ue4 mannequin. But throughout the process I noticed something odd. The animation skeleton seems to have inverted name.

In the image below you are seeing the skeleton as he is about the roll toward the camera, I have highlighted the lef elbow and you can see the corresponding bones zeroed in by 2 red lines in the viewport; the right elbows. I do not know if the culprit is the f4 skeleton or if From Software is making it harder for us by mirroring the bones.  
[https://imgur.com/3DbK3Sn](https://imgur.com/3DbK3Sn)

Finally, being confused by the way all the bones are inverted and with all the additionnal bones the animation skeleton has, I decided to rename only part of a leg and the Root. I exported it from 3ds max and imported it into ue4, choosing the mannequin as the skeletal mesh. It worked!

Well, the import worked and the animation exist and is compatible with the mannequin. The mannequin itself is not feeling too good from the botched renaming process, but playing the animation makes him move in a very distorted manner (only what I think is the root and part of a leg was renamed) 
[https://imgur.com/6q3vSf3](https://imgur.com/6q3vSf3)

but I feel like rename the skeleton correctly and then setting a root motion would make the mannequin reproduced DS3 roll animation, and all the other animations correctly renamed!

Now the long and painful process of renaming each bones, repositioning and testing to see if the renaming respect the mannequin hiearchy has begun.

Did Anything like that has been done before?
## Post #13
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-24T11:45:36+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from Madein
>
> Okay, so a little update on your tutorial. 
It worked!
I was able to randomly find the roll animation. It's the a000_027110.hkx located in the c0000_a00_hi-(gesture_here) folder.
Once I converted the hkx into fbx I imported it into blender and 3ds max. 
Blender did not like it
https://imgur.com/XRzNRmX

But 3ds max was more tolerable. Orientation is messed up, but I think there is a way the put the animation in the right orientation, I just have yet to find how in 3ds max, I usually animate in blender. 
I then proceded to export the 3ds max animation into another fbx, then imported in into ue4. As predicted, it failed because there was no matching bones between the animation and the ue4 mannequin. I then found what I thought was the ''root'' in the animation skeleton (called ''master'') and renamed it to ''root'' I then tried to rename the whole skeleton from the animation using the naming convention of the ue4 mannequin. But throughout the process I noticed something odd. The animation skeleton seems to have inverted name.

In the image below you are seeing the skeleton as he is about the roll toward the camera, I have highlighted the lef elbow and you can see the corresponding bones zeroed in by 2 red lines in the viewport; the right elbows. I do not know if the culprit is the f4 skeleton or if From Software is making it harder for us by mirroring the bones.  
https://imgur.com/3DbK3Sn

Finally, being confused by the way all the bones are inverted and with all the additionnal bones the animation skeleton has, I decided to rename only part of a leg and the Root. I exported it from 3ds max and imported it into ue4, choosing the mannequin as the skeletal mesh. It worked!

Well, the import worked and the animation exist and is compatible with the mannequin. The mannequin itself is not feeling too good from the botched renaming process, but playing the animation makes him move in a very distorted manner (only what I think is the root and part of a leg was renamed) 
https://imgur.com/6q3vSf3

but I feel like rename the skeleton correctly and then setting a root motion would make the mannequin reproduced DS3 roll animation, and all the other animations correctly renamed!

Now the long and painful process of renaming each bones, repositioning and testing to see if the renaming respect the mannequin hiearchy has begun.

Did Anything like that has been done before?

You can try to use bippy script for 3ds max ([http://www.scriptspot.com/3ds-max/scripts/bippy](http://www.scriptspot.com/3ds-max/scripts/bippy))
It can apply animation from 1 skeleton to biped skeleton,and as i know unreal engine use biped.
But that script doesnt work with new 3ds max versions but ive seen updated for 2016 version.

And i think you need to create dummy for each bone with orientation like on biped skeleton.

P.S.All bone names is original from software names. Not from f4.
## Post #14
- Username: ArtoriasZz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 26, 2018 6:41 am
- Post datetime: 2018-01-26T14:23:15+00:00
- Post Title: Dark Souls III HKX Animations

When i have installed Havok 2014 and try to start it up, i get the has stopped working error. Any help would be helpful and thank you if u can .
## Post #15
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-01-26T15:58:36+00:00
- Post Title: Dark Souls III HKX Animations

> Reply from ArtoriasZz
>
> When i have installed Havok 2014 and try to start it up, i get the has stopped working error. Any help would be helpful and thank you if u can .
Maybe you have 32 bit system. Download same file but 32 bit version.
## Post #16
- Username: ArtoriasZz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 26, 2018 6:41 am
- Post datetime: 2018-01-26T17:43:24+00:00
- Post Title: Re: Dark Souls III HKX Animations

Cheers, i have a 64bit system but 32bit version worked.
## Post #17
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-01-26T19:20:13+00:00
- Post Title: Re: Dark Souls III HKX Animations

You cannot open 64bit Havok file in 32bit tools, and otherwise, those tools are platform and architecture specific, but only for packfiles, whinch is old format but its still used more than tagfiles (I actually seen tagfiles used only in SW2), whinch are architecture independent, not sure about platform tho.
## Post #18
- Username: ArtoriasZz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 26, 2018 6:41 am
- Post datetime: 2018-01-26T22:11:30+00:00
- Post Title: Re: Dark Souls III HKX Animations

The error i get when i launch the 64bit version is called ToolStandAlone has stopped working. I have been looking around to find a fix for it and cant find one. The 32bit version works fine and its the version i dont need.
## Post #19
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-01-26T22:33:53+00:00
- Post Title: Re: Dark Souls III HKX Animations

I can confirm that.
I too cannot load skelton files. Thing is, that those files are using hknp structures, they are compatibility patched structures, that means they cannot be loaded into Tools, becouse Tools don't support them. Lucky thing is that I have researched Havok format, so now I can read any strucuture from Havok Packfiles, I will try to post them when the time comes.

You might try to use AssetCC on them and convert them into XML.
## Post #20
- Username: ArtoriasZz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 26, 2018 6:41 am
- Post datetime: 2018-01-26T22:37:09+00:00
- Post Title: Re: Dark Souls III HKX Animations

Do u have a link for AssetCC?
## Post #21
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-01-26T22:42:12+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from ArtoriasZz
>
> Do u have a link for AssetCC?
They are packed alongside tools, or in any SDK.

%Install Folder%\Havok\HavokContentTools\BatchProcess\AssetCc\
AssetCC1 will keep version
AssetCC2 will convert file to current version

In this case, you can use AssetCC1.
## Post #22
- Username: andrewcrinxi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 18, 2016 6:25 pm
- Post datetime: 2018-02-17T19:30:29+00:00
- Post Title: Re: Dark Souls III HKX Animations

any info about installing 64bit on windows 10? because on open it crash
## Post #23
- Username: jdrc8
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 23, 2017 5:42 am
- Post datetime: 2019-04-22T16:00:15+00:00
- Post Title: Re: Dark Souls III HKX Animations

I cant start 64 bit tools on my Windows 10 machine. Any info on how to fix this?
## Post #24
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2019-04-25T16:58:38+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from jdrc8 ↑Tue Apr 23, 2019 12:00 am at Tue Apr 23, 2019 12:00 am
>
> 
I cant start 64 bit tools on my Windows 10 machine. Any info on how to fix this?
IF you cant start it maybe you own a 32bit Windows 10?
## Post #25
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-04-28T02:34:56+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from Lynix ↑Fri Apr 26, 2019 12:58 am at Fri Apr 26, 2019 12:58 am
>
> 
jdrc8 wrote: ↑Tue Apr 23, 2019 12:00 am
I cant start 64 bit tools on my Windows 10 machine. Any info on how to fix this?

IF you cant start it maybe you own a 32bit Windows 10?

No, its a common thing that they dont work on latest win 10. Its fixable through registry. You need to find camerafollowsmoothness (not sure if it's how it called) parameter and change value to something without comma like replace it with dot.
## Post #26
- Username: 0ttonomous
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 20, 2019 4:14 pm
- Post datetime: 2019-06-20T08:19:46+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from dropoff ↑Sun Apr 28, 2019 10:34 am at Sun Apr 28, 2019 10:34 am
>
> 
Lynix wrote: ↑Fri Apr 26, 2019 12:58 am
jdrc8 wrote: ↑Tue Apr 23, 2019 12:00 am
I cant start 64 bit tools on my Windows 10 machine. Any info on how to fix this?

IF you cant start it maybe you own a 32bit Windows 10?


No, its a common thing that they dont work on latest win 10. Its fixable through registry. You need to find camerafollowsmoothness (not sure if it's how it called) parameter and change value to something without comma like replace it with dot.

Can you show this to me more in-depth? I can't convert any HKX files without being able to use the 64-bit version and I've spent hours looking for work-arounds. I'm at my wits end here.
## Post #27
- Username: 0ttonomous
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 20, 2019 4:14 pm
- Post datetime: 2019-06-20T08:22:27+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from PredatorCZ ↑Sat Jan 27, 2018 6:42 am at Sat Jan 27, 2018 6:42 am
>
> 
ArtoriasZz wrote:Do u have a link for AssetCC?
They are packed alongside tools, or in any SDK.

%Install Folder%\Havok\HavokContentTools\BatchProcess\AssetCc\
AssetCC1 will keep version
AssetCC2 will convert file to current version

In this case, you can use AssetCC1.

How do you use it? Nothing happens when I try it.
## Post #28
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-06-20T21:01:43+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from 0ttonomous ↑Thu Jun 20, 2019 4:19 pm at Thu Jun 20, 2019 4:19 pm
>
> 
dropoff wrote: ↑Sun Apr 28, 2019 10:34 am
Lynix wrote: ↑Fri Apr 26, 2019 12:58 am

IF you cant start it maybe you own a 32bit Windows 10?


No, its a common thing that they dont work on latest win 10. Its fixable through registry. You need to find camerafollowsmoothness (not sure if it's how it called) parameter and change value to something without comma like replace it with dot.


Can you show this to me more in-depth? I can't convert any HKX files without being able to use the 64-bit version and I've spent hours looking for work-arounds. I'm at my wits end here.
Just use new havok plugins from here https://forum.xentax.com/viewtopic.php?f=16&t=19691 They should work with ds3.
## Post #29
- Username: 0ttonomous
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 20, 2019 4:14 pm
- Post datetime: 2019-06-20T23:11:40+00:00
- Post Title: Re: Dark Souls III HKX Animations

Thank you.
## Post #30
- Username: qq531620267
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 04, 2019 1:27 pm
- Post datetime: 2019-07-05T08:14:47+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from dropoff ↑Fri Jun 21, 2019 5:01 am at Fri Jun 21, 2019 5:01 am
>
> 
0ttonomous wrote: ↑Thu Jun 20, 2019 4:19 pm
dropoff wrote: ↑Sun Apr 28, 2019 10:34 am


No, its a common thing that they dont work on latest win 10. Its fixable through registry. You need to find camerafollowsmoothness (not sure if it's how it called) parameter and change value to something without comma like replace it with dot.


Can you show this to me more in-depth? I can't convert any HKX files without being able to use the 64-bit version and I've spent hours looking for work-arounds. I'm at my wits end here.

Just use new havok plugins from here viewtopic.php?f=16&t=19691 They should work with ds3.

it's can't to work(win10 X64),Skeleton.HKX darg to Noesis,then it's disappear
## Post #31
- Username: EmiChu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 30, 2021 5:20 am
- Post datetime: 2021-04-04T02:54:49+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from dropoff ↑Sat Oct 21, 2017 6:21 am at Sat Oct 21, 2017 6:21 am
>
> 
..............

You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.

Hey, you said to "write if something doesn't work" and though I know it's been 4 years since you posted that, I do hope you're still active and are able to help. 

I am trying to convert Bloodborne animations into FBX so that Unity will be able to read them. So far I've been unsuccessful. I am able to get the animations exported to FBX (tried through various means) but in the end the animations will be all twisted.
Now I wanted to try the Fallout 4 tools you mentioned, but I get an error when starting the program and even though it does start after, any conversion to FBX doesn't actually get done when I click "Convert to FBX". (It literally just says it's done but then no file is created)

The error is R6034 Runtime Error, an application has made an attempt to load the C runtime library incorrectly.
Unfortunately I am unable to find any help regarding this error online (you'd think more people had this error but I guess not...)

Any tips maybe? Maybe I'm missing a program or something? Any help would be appreciated because I've been nonstop searching for the past week for any way to get the animations to work properly but in the end I always end up with twisted animations :/
## Post #32
- Username: Mahone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 17, 2021 6:20 pm
- Post datetime: 2021-04-20T13:14:56+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from EmiChu ↑Sun Apr 04, 2021 10:54 am at Sun Apr 04, 2021 10:54 am
>
> 
dropoff wrote: ↑Sat Oct 21, 2017 6:21 am
..............

You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.


Hey, you said to "write if something doesn't work" and though I know it's been 4 years since you posted that, I do hope you're still active and are able to help. 

I am trying to convert Bloodborne animations into FBX so that Unity will be able to read them. So far I've been unsuccessful. I am able to get the animations exported to FBX (tried through various means) but in the end the animations will be all twisted.
Now I wanted to try the Fallout 4 tools you mentioned, but I get an error when starting the program and even though it does start after, any conversion to FBX doesn't actually get done when I click "Convert to FBX". (It literally just says it's done but then no file is created)

The error is R6034 Runtime Error, an application has made an attempt to load the C runtime library incorrectly.
Unfortunately I am unable to find any help regarding this error online (you'd think more people had this error but I guess not...)

Any tips maybe? Maybe I'm missing a program or something? Any help would be appreciated because I've been nonstop searching for the past week for any way to get the animations to work properly but in the end I always end up with twisted animations :/

hmm. how did you get the animation?i got hkx files but nothing show up when i open with noesis plugin
## Post #33
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-10-20T18:08:51+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from EmiChu ↑Sun Apr 04, 2021 10:54 am at Sun Apr 04, 2021 10:54 am
>
> 
dropoff wrote: ↑Sat Oct 21, 2017 6:21 am
..............

You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.


Hey, you said to "write if something doesn't work" and though I know it's been 4 years since you posted that, I do hope you're still active and are able to help. 

I am trying to convert Bloodborne animations into FBX so that Unity will be able to read them. So far I've been unsuccessful. I am able to get the animations exported to FBX (tried through various means) but in the end the animations will be all twisted.
Now I wanted to try the Fallout 4 tools you mentioned, but I get an error when starting the program and even though it does start after, any conversion to FBX doesn't actually get done when I click "Convert to FBX". (It literally just says it's done but then no file is created)

The error is R6034 Runtime Error, an application has made an attempt to load the C runtime library incorrectly.
Unfortunately I am unable to find any help regarding this error online (you'd think more people had this error but I guess not...)

Any tips maybe? Maybe I'm missing a program or something? Any help would be appreciated because I've been nonstop searching for the past week for any way to get the animations to work properly but in the end I always end up with twisted animations :/

Hey! Have you figured it out? I too am trying to get Bloodborne animations, but i cant ( That Fallout4 GUI FBX converter doesnt do anything



I got this far -- i can open them in 3ds max, but after exporting them UE says "Warning: Could not create a valid skeleton from the import data that matches the given Skeletal Mesh.  Check the bone names of both the Skeletal Mesh for this AnimSet and the animation data you are trying to import."
## Post #34
- Username: Tekkamanchronos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 24, 2015 1:50 am
- Post datetime: 2022-04-23T21:05:21+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from EmiChu ↑Sun Apr 04, 2021 10:54 am at Sun Apr 04, 2021 10:54 am
>
> 
dropoff wrote: ↑Sat Oct 21, 2017 6:21 am
..............

You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.


Hey, you said to "write if something doesn't work" and though I know it's been 4 years since you posted that, I do hope you're still active and are able to help. 

I am trying to convert Bloodborne animations into FBX so that Unity will be able to read them. So far I've been unsuccessful. I am able to get the animations exported to FBX (tried through various means) but in the end the animations will be all twisted.
Now I wanted to try the Fallout 4 tools you mentioned, but I get an error when starting the program and even though it does start after, any conversion to FBX doesn't actually get done when I click "Convert to FBX". (It literally just says it's done but then no file is created)

The error is R6034 Runtime Error, an application has made an attempt to load the C runtime library incorrectly.
Unfortunately I am unable to find any help regarding this error online (you'd think more people had this error but I guess not...)

Any tips maybe? Maybe I'm missing a program or something? Any help would be appreciated because I've been nonstop searching for the past week for any way to get the animations to work properly but in the end I always end up with twisted animations :/

I'm having the same problem, were you able to find a solution?

Okay! i was able to figure out what i was doing wrong, so im gonna add in some more info for people who are trying to get this to work for stuff like blender. Atleast I am lol.

Okay here is the first problems, although someone posted the Havok files, These files like the person giving the instructions said Have to go through the conversion process, using the provided files as is will cause the converter to crash.
Follow the instructions and you will get a good havok file for using.
Once the file is saved from the Havok creator program and made into a good hkx file, you can use the hkx>FBX converter.
However once this file is converted it still needs help because blender does not support this type of FBX.
Open the newly created FBX in Noesis, then export it as a Dae animation. This will give you nice pretty bones for retargeting.
From there you can save it as an FBX if you want, or leave it as is. 
Siiiggghh, i can't believe you have to do this one at a time, someone make a bulk converter for the starting hkx files >_<
## Post #35
- Username: Tekkamanchronos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 24, 2015 1:50 am
- Post datetime: 2022-06-30T21:23:36+00:00
- Post Title: Re: Dark Souls III HKX Animations

> Reply from Mahone ↑Tue Apr 20, 2021 9:14 pm at Tue Apr 20, 2021 9:14 pm
>
> 
EmiChu wrote: ↑Sun Apr 04, 2021 10:54 am
dropoff wrote: ↑Sat Oct 21, 2017 6:21 am
..............

You will get fbx file with animation you choose you can check it in noesis or 3ds max and i dont recommend you to import it directly to unreal engine better to convert it firstly with noesis then import to 3ds max.

If something doesnt work then write to me.


Hey, you said to "write if something doesn't work" and though I know it's been 4 years since you posted that, I do hope you're still active and are able to help. 

I am trying to convert Bloodborne animations into FBX so that Unity will be able to read them. So far I've been unsuccessful. I am able to get the animations exported to FBX (tried through various means) but in the end the animations will be all twisted.
Now I wanted to try the Fallout 4 tools you mentioned, but I get an error when starting the program and even though it does start after, any conversion to FBX doesn't actually get done when I click "Convert to FBX". (It literally just says it's done but then no file is created)

The error is R6034 Runtime Error, an application has made an attempt to load the C runtime library incorrectly.
Unfortunately I am unable to find any help regarding this error online (you'd think more people had this error but I guess not...)

Any tips maybe? Maybe I'm missing a program or something? Any help would be appreciated because I've been nonstop searching for the past week for any way to get the animations to work properly but in the end I always end up with twisted animations :/


hmm. how did you get the animation?i got hkx files but nothing show up when i open with noesis plugin

I dont know if you figured it out after all this time, but i made a video addressing the issue you're having as well as everyone else having issues with BB
[https://youtu.be/VJiiZ3uXLz8](https://youtu.be/VJiiZ3uXLz8)
