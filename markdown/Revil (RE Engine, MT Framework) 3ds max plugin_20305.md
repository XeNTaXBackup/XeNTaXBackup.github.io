## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-03T15:11:06+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

Following plugin will let you import animations from RE Engine and MT Framework.

Supported RE Engine titles.

 Resident Evil 7
 Resident Evil 2
 Resident Evil 3
 Resident Evil Resistance
 Devil May Cry 5
 Resident Evil 8
 Resident Evil Verse


Supported MTF titles.
There is some many of them, so here is complete list: [https://en.wikipedia.org/wiki/MT_Framew ... _Framework](https://en.wikipedia.org/wiki/MT_Framework#Games_using_MT_Framework)

Enjoy.



Master page.

Fixes, changes for MT Framework LMT against MTF Tools (old maxcript)

 Much faster loading
 Proper animation indexing
 Animations are fully sampled
 Ability to disable IK when importing motion
 Ability to resample animations
 Properly loading non-uniform scale animations
 

MTF LMT Limitations

 IK links must be still created with MTF Tools
 You can no longer regenerate skeleton in MTF Tools, but a default pose will be set at frame -1
 Sometimes, IK chain can be severed. In this case, you must relink start and end bone in IK controller. DO NOT create new IK with MTF Tools.
 Some scale animations might still look broken (some MTF V1.5+ titles only)


I will also require from you any and every feedback you can think of.
For plugin, you can create issues in repo.
For everything else here, or on blog. 
Thank you.
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-15T13:55:41+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax V1.1 has been released.

Fixed wrong frame distribution where resulting animations were slightly faster.
Maxscript listener will now show whenever plugin tries to print any information and from now on, user will be always informed properly. User no longer needs to open listener manually.
## Post #3
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2019-05-17T00:32:26+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

Thanks for tool,
I know there are a couple scripts out there to import models,
but will you be adding that feature to this plugin?

Here are some ideas (that I'm sure you've already thought of).
Make the window a bit wider or resizable so animation names don't cut off.
Keep the window open after importing an animation.
Add or Edit/Remove/Reset/Save buttons.
I'm not talking about a "repack" to use in game (Although that would be cool), but to save "Favorite" Animations for later use.

The animations work with the original models.
I tried with custom models and the weights seem to break, but that's probably not your plugin's fault.
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-17T07:42:20+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from protosk8 ↑Fri May 17, 2019 8:32 am at Fri May 17, 2019 8:32 am
>
> 
Thanks for tool,
I know there are a couple scripts out there to import models,
but will you be adding that feature to this plugin?

Here are some ideas (that I'm sure you've already thought of).
Make the window a bit wider or resizable so animation names don't cut off.
Keep the window open after importing an animation.
Add or Edit/Remove/Reset/Save buttons.
I'm not talking about a "repack" to use in game (Although that would be cool), but to save "Favorite" Animations for later use.

The animations work with the original models.
I tried with custom models and the weights seem to break, but that's probably not your plugin's fault.

Thanks for ideas, I haven't thought about them.
Here's my take on them.
It would require additional research, It's written under WinAPI and I'm not much friend of it.
As the matter of importing, it's not possible, since 3DS will create/destroy plugin instance, each time file is imported. I had tested this in past, and in conclusion, the only way would be, to create additional utility, this would require for user to find this utility in Max'es pile of UI. Where for some users is hard to find import button, imagine how and if they would find this, even with guide.
This doesn't seem like useful thing to me, the time spent on implementing such thing would be wasted, since nobody would actually use it. Each animation has unique name, and I cannot possibly think, how this feature would even work.
As the matter of export, there are more things than animation. Like events, scripts or other things that are stored inside motion files.
As the matter of pure repacking, it's possible. I have thought about making mot <-> motlist repacker.
## Post #5
- Username: RafaX564
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 28, 2012 8:53 am
- Post datetime: 2019-12-03T02:47:27+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

Could you please update this plugin for MAX 2020?

Amazing job btw!
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-04-04T19:59:37+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax v1.2 has been released

Added support for LMT loading.
Added support for motlist99, mot78 formats.
RE motion formats are now properly sampled.
Added resample option (animation will be resampled to current scene FPS)
Added option to load all animations at once (ranges will be printed into listener, units are ticks).

Basically adding ability to load LMT files from MT Framework and a new format from RE3 Remake (demo).
Experimental phase, tool might be unstable.
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-04-05T00:55:18+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

You may not be planning to update MT Framework Mobile, but is it possible to support Monster Hunter Explore mod and lmt?
Samples can be provided as needed. Please consider that.
## Post #8
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-04-05T16:20:40+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

Would you mind taking a look at Re 7 motlist.60? Or was the engine different at the time?
In case i can provide the files.
## Post #9
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-04-06T21:04:38+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

please resident Evil 7 motlist
## Post #10
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2020-04-13T16:22:25+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from PredatorCZ ↑Fri May 03, 2019 11:11 pm at Fri May 03, 2019 11:11 pm
>
> 
Following plugin will let you import animations from Resident Evil 2 Remake, Resident Evil 3 Remake and all titles under MT Framework engine.

Have you personally tested Resident Evil 3? I have tried numerous times and it keeps crashing on me.
## Post #11
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-04-21T07:39:35+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from askB ↑Tue Apr 14, 2020 12:22 am at Tue Apr 14, 2020 12:22 am
>
> 
Have you personally tested Resident Evil 3? I have tried numerous times and it keeps crashing on me.

Tested only demo. There wasn't a release version, when it was in the development .
## Post #12
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-04-26T19:28:53+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax v1.3 has been released.

Fixed positions for mot78 formats. #6
Fixed frame distribution for Big Endian LMT formats.
Fixed crash when loading pose animations. #3 
Minor crash fixes.
Added some missing codecs.
## Post #13
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-05-01T13:25:15+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax v1.4 has been released.

Added support for RE7.
More fixes.
## Post #14
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-05-01T16:03:52+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

Thanks so much for re7
## Post #15
- Username: neociano
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 12, 2017 8:08 pm
- Post datetime: 2020-09-02T05:44:10+00:00
- Post Title: Revil (RE Engine, MT Framework) 3ds max plugin

would this work for Ultimate Marvel vs Capcom 3 for pc?
## Post #16
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2020-09-09T15:54:28+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

Which script should I use to import model files from resident evil 5,6,rev,rev2
I tried your MT FRAMEWORK TOOLS to import pl1010.mod model from rev,but 3dmax crashed when I used REVIL 3DS MAX PLUGIN to import .lmt animation in 3dmax 2017.
## Post #17
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-09-20T21:15:46+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax V1.5 has been released

 Removed 32bit support.
 Added support for 2021.
 Added ability to load Additive animations.
 Added ability to suppress logging of missing bones.
 Added asset caching for faster loading.
 Fixed few crash problems.
 Added catch handling for non-critical errors.
 Fixed reference pose from -1 frame to -1 tick.
## Post #18
- Username: wuxian
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 28, 2020 11:15 pm
- Post datetime: 2020-09-28T15:33:01+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

How about animations of Resident evil 4 ？
## Post #19
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-11-15T13:29:56+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from wuxian ↑Mon Sep 28, 2020 11:33 pm at Mon Sep 28, 2020 11:33 pm
>
> 
How about animations of Resident evil 4 ？

TBA
## Post #20
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-11-15T13:30:45+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax V1.6 has been released.

Stability fixes.
New config format (moved to XML).
Message boxes no longer shows, when suppressing prompts.


EDIT:
Hotfix V1.6.2 has been released.

Fixed crash, when loading some LMT files.
## Post #21
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2021-03-08T21:55:56+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax v1.7 has been released.

 Fixed RE glitchy rotations #14
 Fixed RE wandering bones #11
 Fixed RE indetity rotations for pose bones
 Fixed RE3 subscript exceptions when loading all
## Post #22
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-05-10T21:21:51+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from PredatorCZ ↑Tue Mar 09, 2021 5:55 am at Tue Mar 09, 2021 5:55 am
>
> 
RevilMax v1.7 has been released.

 Fixed RE glitchy rotations #14
 Fixed RE wandering bones #11
 Fixed RE indetity rotations for pose bones
 Fixed RE3 subscript exceptions when loading all

Resident Evil Village support?
## Post #23
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2021-05-23T09:33:16+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

RevilMax v1.7 has been released.

 Added support for motlist486, mot458 formats.
 Added support for 2022.
 Added Iceborne LMT support.
## Post #24
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-05-23T12:46:03+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from PredatorCZ ↑Sun May 23, 2021 5:33 pm at Sun May 23, 2021 5:33 pm
>
> 
RevilMax v1.7 has been released.

 Added support for motlist486, mot458 formats.
 Added support for 2022.
 Added Iceborne LMT support.

Does it mean now it support MHW Iceborn models? No longer need Blender?
And even for mod?
## Post #25
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2021-05-28T14:16:57+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from Darkhowlings ↑Sun May 23, 2021 8:46 pm at Sun May 23, 2021 8:46 pm
>
> 
Does it mean now it support MHW Iceborn models? No longer need Blender?
And even for mod?

Motions only, but I didn't had time to test them.
## Post #26
- Username: Martins
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 12, 2010 9:46 pm
- Post datetime: 2021-06-18T12:54:57+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

First  just want to say thanks, fora all your efforts! This really is a sexy plugin  .
Can you give us an option to choose which and how many animations to load at once? instead of load just one or all of them ?

Also,with latest 1.8 and 1.8.1 releases,  loading LMT animations ´ll crash MAX 2017.      1.7 still works fine though.
## Post #27
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-06-28T05:12:25+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

I see to the Monster Hunter Rise file, but doesn't seem to support it in motlist.484.
If you need a sample file, I can prepare it.

*EDIT
The upcoming Monster Hunter Stories 2 is developed using the MT Framework.
The *.arc file is zlib and can be decompressed with offzip. Neither *.mod files nor *.lmt can be used with plugins.
## Post #28
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-07-09T20:15:35+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from einherjar007 ↑Mon Jun 28, 2021 1:12 pm at Mon Jun 28, 2021 1:12 pm
>
> 
I see to the Monster Hunter Rise file, but doesn't seem to support it in motlist.484.
If you need a sample file, I can prepare it.

*EDIT
The upcoming Monster Hunter Stories 2 is developed using the MT Framework.
The *.arc file is zlib and can be decompressed with offzip. Neither *.mod files nor *.lmt can be used with plugins.

What offzip command did you use?
I am not getting anything beyond dat files in my attempts.
## Post #29
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-10T02:39:33+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from 09williamsad ↑Sat Jul 10, 2021 4:15 am at Sat Jul 10, 2021 4:15 am
>
> 
What offzip command did you use?
I am not getting anything beyond dat files in my attempts.

use -a -1.
I tried it with the demo version. It may be different in the product version. 
If the file is not encrypted, we can infer the format of the file in the header.
## Post #30
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-07-10T07:10:48+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from einherjar007 ↑Sat Jul 10, 2021 10:39 am at Sat Jul 10, 2021 10:39 am
>
> 

use -a -1.
I tried it with the demo version. It may be different in the product version. 
If the file is not encrypted, we can infer the format of the file in the header.

Looks like it has changed.
"  0x0819581e .
- zlib Z_DATA_ERROR, the data in the file is not in zip format
  or uses a different windowBits value (-z). Try to use -z -15

  0x08299e6d .
- zlib Z_DATA_ERROR, the data in the file is not in zip format
  or uses a different windowBits value (-z). Try to use -z -15

  0x0832b000

- no valid full zip data found"

Samples [https://mega.nz/folder/PT4wnIja#w1qy0KrBcqI2w9u0ubiueg](https://mega.nz/folder/PT4wnIja#w1qy0KrBcqI2w9u0ubiueg)
## Post #31
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-10T08:56:02+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

I think they use of blowfish encryption. 
Are they the PC version? I used the Demo version of the Switch version.
## Post #32
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-07-10T08:56:35+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from einherjar007 ↑Sat Jul 10, 2021 4:56 pm at Sat Jul 10, 2021 4:56 pm
>
> 
I think they use of blowfish encryption. 
Are they the PC version? I used the Demo version of the Switch version.

PC version.
Sample files <Link removed due to site policy>
## Post #33
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2021-07-12T13:53:07+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

Switch demo and full are using standard arc files.
Samples you posted are encrypted like the ones from Dragon Dogma Online, don't know why, don't care.
Capcom really pisses me off with their encryptions and DRMs lately.
## Post #34
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-07-14T18:44:28+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from einherjar007 ↑Sat Jul 10, 2021 4:56 pm at Sat Jul 10, 2021 4:56 pm
>
> 
I think they use of blowfish encryption. 
Are they the PC version? I used the Demo version of the Switch version.

Tried the switch version.
Files are exported but it looks like files are missing, I tried a few of the monster arc files and only got tex files.
## Post #35
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2021-07-14T21:54:55+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

[https://github.com/Silvris/MH-Tools-and ... Extract.py](https://github.com/Silvris/MH-Tools-and-Scripts/blob/master/MHStories2ARCExtract.py)

Works on both Switch and PC arcs. PC arcs are blowfish encrypted, while both arcs are zlib-compressed. IIRC they changed something in arc structure, so likely no actual tool for .arcs works on these. I've not looked into the resulting LMT files yet, but I imagine it'll be somewhat similar to MHGU's, given the model version is only 2 after MHGU.
## Post #36
- Username: Kenvida
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 25, 2021 6:39 pm
- Post datetime: 2021-09-30T23:40:36+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

Halow any guide everytime i export model in 3dmax one anmation only load.
## Post #37
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-04T12:49:24+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from PredatorCZ ↑Fri May 03, 2019 11:11 pm at Fri May 03, 2019 11:11 pm
>
> 
Following plugin will let you import animations from RE Engine and MT Framework.

Supported RE Engine titles.

 Resident Evil 7
 Resident Evil 2
 Resident Evil 3
 Resident Evil Resistance
 Devil May Cry 5
 Resident Evil 8
 Resident Evil Verse


Supported MTF titles.
There is some many of them, so here is complete list: https://en.wikipedia.org/wiki/MT_Framew ... _Framework

Enjoy.



Master page.

Fixes, changes for MT Framework LMT against MTF Tools (old maxcript)

 Much faster loading
 Proper animation indexing
 Animations are fully sampled
 Ability to disable IK when importing motion
 Ability to resample animations
 Properly loading non-uniform scale animations
 

MTF LMT Limitations

 IK links must be still created with MTF Tools
 You can no longer regenerate skeleton in MTF Tools, but a default pose will be set at frame -1
 Sometimes, IK chain can be severed. In this case, you must relink start and end bone in IK controller. DO NOT create new IK with MTF Tools.
 Some scale animations might still look broken (some MTF V1.5+ titles only)


I will also require from you any and every feedback you can think of.
For plugin, you can create issues in repo.
For everything else here, or on blog. 
Thank you.

Thank you for this amazing tool. I just have two more questions. I just recently unpack the devil may cry 5 because I would like to have Nero Demon model and animation. I see that they use MOT type of file for animation and some kind of unknown number of mesh. 

May I ask if there is a plugin to import these models into 3dsmax? So I can export to fbx for other purposes. Thank you
## Post #38
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2022-05-10T09:07:43+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from SCArkadia ↑Sun Aug 22, 1971 8:22 am at Sun Aug 22, 1971 8:22 am
>
> 
May I ask if there is a plugin to import these models into 3dsmax? So I can export to fbx for other purposes. Thank you

I never used mesh importer tbh, there should be Noesis script for RE Engine somewhere.
## Post #39
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-10T13:32:05+00:00
- Post Title: Re: Revil (RE Engine, MT Framework) 3ds max plugin

> Reply from PredatorCZ ↑Tue May 10, 2022 5:07 pm at Tue May 10, 2022 5:07 pm
>
> 
SCArkadia wrote: ↑Sun Aug 22, 1971 8:22 am
May I ask if there is a plugin to import these models into 3dsmax? So I can export to fbx for other purposes. Thank you


I never used mesh importer tbh, there should be Noesis script for RE Engine somewhere.

I see I see. I will try to find it  Thanks a lot my man
