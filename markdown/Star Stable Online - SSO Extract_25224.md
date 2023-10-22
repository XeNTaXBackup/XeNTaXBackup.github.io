## Post #1
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-04-06T13:53:52+00:00
- Post Title: Star Stable Online - SSO Extract

This tool can extract and convert game resources from Star Stable Online (SSO) and several other games developed in the Pixeltale Game Studio Engine.




1.png (19.79 KiB) Viewed 197 times



DOWNLOAD LINK: https://drive.google.com/drive/folders/ ... sp=sharing


To run it, you first need to install the .NET 6 Desktop Runtime. from [https://dotnet.microsoft.com/en-us/down ... .0/runtime](https://dotnet.microsoft.com/en-us/download/dotnet/6.0/runtime)


You can report bugs in this topic, and we'll see if it's something that can be fixed or not. This tool does not come with any form of guarantee of support!

I recommend that you create copies of the game files, and of any converted models extracted by the tool. There is no guarantee that this tool will work with future updates of the game.

Common Questions

Q: Can I mod games with this tool?
A: No, it only unpacks and converts resources. There are no plans to add any modding functionality.

Change log
1.0 - First version
1.1
+ New option to extract all resources from the CSA-files (without conversion). This is useful if you want to research the formats yourself.
+ Cancel button added.
* Fixed a bug where extraction would fail if the destination folder name contained non-english characters.

1.3
+ Added support for older games: Star Stable 1, Star Stable 2, Star Stable 3, Star Stable 4 and Barbie Horse Adventures - Riding Camp.
+ Added support for all known vertex formats (three were missing in the last version).
+ New option to select different folder layouts during extraction. SSO has over 50K resources so this helps to organize them better.
+ Added a button to open the log file directly after extraction to easier support and debugging.
* Switch the model file format to FBX instead of DAE. There were several bugs that could not be solved in the DAE format.

1.3.1
+ Minor bug fix, some models where not converted successfully.
## Post #2
- Username: RoJaXeN
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 06, 2022 8:21 am
- Post datetime: 2022-04-08T00:18:59+00:00
- Post Title: Star Stable Online - SSO Extract

Is there a chance in the future to fix the extractor against the new image format, if the developers would decide to change formats?
## Post #3
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-04-08T06:31:49+00:00
- Post Title: Star Stable Online - SSO Extract

> Reply from RoJaXeN ↑Fri Apr 08, 2022 8:18 am at Fri Apr 08, 2022 8:18 am
>
> 
Is there a chance in the future to fix the extractor against the new image format, if the developers would decide to change formats?
That all depends on how much it requires. The new files are only these small icons now, so not that interesting. If you use v1.0 then they will be unpacked without an extension to the AdditionalTextures folder. Feel free to have a look at them and figure out what they are. Looks like bitmap data without a header to me:

```
Icon_HorseHair40_Extra_01
Icon_HorseHair40_Extra_02
Icon_HorseHair40_Extra_03
```
## Post #4
- Username: Horselover97
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 11:40 am
- Post datetime: 2022-04-10T03:42:43+00:00
- Post Title: Star Stable Online - SSO Extract

What are the file names for the horses I can’t find them
## Post #5
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-04-10T08:45:58+00:00
- Post Title: Star Stable Online - SSO Extract

> Reply from Horselover97 ↑Sun Apr 10, 2022 11:42 am at Sun Apr 10, 2022 11:42 am
>
> 
What are the file names for the horses I can’t find them

They are named GHnn_Keypose. The next version will try to rename them into something more natural.
## Post #6
- Username: Horselover97
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 11:40 am
- Post datetime: 2022-04-11T21:34:16+00:00
- Post Title: Star Stable Online - SSO Extract

What is the file name of the horse textures?
## Post #7
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-04-12T06:30:10+00:00
- Post Title: Star Stable Online - SSO Extract

> Reply from Horselover97 ↑Tue Apr 12, 2022 5:34 am at Tue Apr 12, 2022 5:34 am
>
> 
What is the file name of the horse textures?

There are several thousands of textures. I suggest that you browse through the texture folders to find what you are looking for.
## Post #8
- Username: Pollaris
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2020 9:34 am
- Post datetime: 2022-04-17T07:45:35+00:00
- Post Title: Star Stable Online - SSO Extract

The only problem what i have with software is not having models in it. Like I changed every folder, made new ones and still nothing
## Post #9
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-04-17T09:00:52+00:00
- Post Title: Star Stable Online - SSO Extract

> Reply from Pollaris ↑Sun Apr 17, 2022 3:45 pm at Sun Apr 17, 2022 3:45 pm
>
> 
The only problem what i have with software is not having models in it. Like I changed every folder, made new ones and still nothing

There should be a file named "ssoextract_log.txt" in the destination folder. I should be able to see what is wrong if you send that to me in a DM.
## Post #10
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-04-17T15:17:11+00:00
- Post Title: Star Stable Online - SSO Extract

First preview of v1.1 is now available.
## Post #11
- Username: hzzslg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 31, 2021 9:07 am
- Post datetime: 2022-05-22T21:13:50+00:00
- Post Title: Star Stable Online - SSO Extract

Hi ! Have you worked on other features? I would be interested in the rigs of the 3D models but I don't know how to get them
## Post #12
- Username: Taltos2003
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 31, 2022 2:57 pm
- Post datetime: 2022-09-04T08:09:56+00:00
- Post Title: Star Stable Online - SSO Extract

Hey! When I wanted to use the software it says that "you must install missing frameworks for .NET" . I installed the program called .NET how could I solve this problem?
## Post #13
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-09-04T08:51:36+00:00
- Post Title: Star Stable Online - SSO Extract

> Reply from Taltos2003 ↑Sun Sep 04, 2022 4:09 pm at Sun Sep 04, 2022 4:09 pm
>
> 
Hey! When I wanted to use the software it says that "you must install missing frameworks for .NET" . I installed the program called .NET how could I solve this problem?

You have not installed .NET if you get that message. You need to install the ".NET Desktop Runtime", the download link is in the first post of the thread.
## Post #14
- Username: Kitty Cute
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 04, 2022 5:13 am
- Post datetime: 2022-09-12T02:09:24+00:00
- Post Title: Star Stable Online - SSO Extract

I love your program thank you so much for making it!! Is there any way you could make it also have a repackage option so we can edit the extracted files and then actually put them in the game?
## Post #15
- Username: Kitty Cute
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 04, 2022 5:13 am
- Post datetime: 2022-10-14T20:56:28+00:00
- Post Title: Star Stable Online - SSO Extract

Is this still active? I would like to report a bug... No matter what I do, it always says "3 textures failed"... And I think one is the texture I need, the Zony...
## Post #16
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-10-15T20:36:25+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from Kitty Cute ↑Sat Oct 15, 2022 4:56 am at Sat Oct 15, 2022 4:56 am
>
> 
Is this still active? I would like to report a bug... No matter what I do, it always says "3 textures failed"... And I think one is the texture I need, the Zony...

I tested it today with the latest game version and I didn't get any errors. Can you share the extraction log file?
## Post #17
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-11-19T15:03:50+00:00
- Post Title: Re: Star Stable Online - SSO Extract

v1.3 released, link is in the first post of this thread. It contains some minor tweaks and support for the earlier (non multiplayer) versions of Star Stable.

Features that might be in future versions:
Exporting rigs/skeletons, this is partly implemented already but there are several bugs left to fix. (80% done)
Exporting materials with multiple textures. (0% done)
Exporting shaders. (50% done)
Exporting animations, this is probably the most time consuming and maybe impossible if it there are too much game engine specific stuff.  (20% done)
Support for more older PX games. (0% done)
## Post #18
- Username: blueveilbride
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 26, 2022 9:50 pm
- Post datetime: 2022-11-26T13:53:57+00:00
- Post Title: Re: Star Stable Online - SSO Extract

Hello! The textures extracted correctly in the folder. However, the 3D-models have not been extracted at all. Any help?
## Post #19
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-11-26T18:54:19+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from blueveilbride ↑Sat Nov 26, 2022 9:53 pm at Sat Nov 26, 2022 9:53 pm
>
> 
Hello! The textures extracted correctly in the folder. However, the 3D-models have not been extracted at all. Any help?

That is weird, I will need to see your log file to understand what went wrong. It is in the destination folder and is named "ssoextract_log*.txt"...

While double checking the tool with the last game update I noticed another problem, a few materials were not exported correcly. I will fix this but this is probably not the same problem as you have.
## Post #20
- Username: no0t2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 08, 2022 3:14 am
- Post datetime: 2022-12-07T19:17:15+00:00
- Post Title: Re: Star Stable Online - SSO Extract

Hello! I've be using this extractor and no matter how many times I try to restart the conversion tool it still fails to extract 1498 models. Now I'm unsure if it's due to the game being updated after a while, but I'd just like to know, thank you! : )
## Post #21
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-12-07T19:33:04+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from no0t2 ↑Thu Dec 08, 2022 3:17 am at Thu Dec 08, 2022 3:17 am
>
> 
Hello! I've be using this extractor and no matter how many times I try to restart the conversion tool it still fails to extract 1498 models. Now I'm unsure if it's due to the game being updated after a while, but I'd just like to know, thank you! : )

Hi, this is probably due to a bug that I have already found and fixed. I have now uploaded a new version (v1.3.1) with a fix. Please try that one and see if it helps. If you still have problems, please share the extraction log file.
## Post #22
- Username: no0t2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 08, 2022 3:14 am
- Post datetime: 2022-12-07T20:14:36+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from locknut ↑Thu Dec 08, 2022 3:33 am at Thu Dec 08, 2022 3:33 am
>
> 
no0t2 wrote: ↑Thu Dec 08, 2022 3:17 am
Hello! I've be using this extractor and no matter how many times I try to restart the conversion tool it still fails to extract 1498 models. Now I'm unsure if it's due to the game being updated after a while, but I'd just like to know, thank you! : )


Hi, this is probably due to a bug that I have already found and fixed. I have now uploaded a new version (v1.3.1) with a fix. Please try that one and see if it helps. If you still have problems, please share the extraction log file.

It works properly now, thank you very much!
## Post #23
- Username: Emma Pinkwatcher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 15, 2022 12:45 am
- Post datetime: 2022-12-14T17:08:32+00:00
- Post Title: Re: Star Stable Online - SSO Extract

I downloaded the textures and models but where do I find the Tennessee walking horses model so I can ride them in game? I don't have star coins to buy them so I decided to do this... please help if possible? If that spoiler sso youtuber (forgot their name lol) can do it maybe you can?
## Post #24
- Username: Horselover97
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 11:40 am
- Post datetime: 2022-12-14T22:43:40+00:00
- Post Title: Re: Star Stable Online - SSO Extract

Hey, I’m having trouble with the 1.3 version. It keeps telling that many files wouldn’t converted and the new Christmas horses doesn’t show up when it converted the first time 

Here’s my logs
[https://drive.google.com/drive/folders/ ... Bgsz-3QrDQ](https://drive.google.com/drive/folders/1AhWpPitOgtsJUQ7qzUjGUFBgsz-3QrDQ)
## Post #25
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-12-14T23:27:16+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from Horselover97 ↑Thu Dec 15, 2022 6:43 am at Thu Dec 15, 2022 6:43 am
>
> 
Hey, I’m having trouble with the 1.3 version. It keeps telling that many files wouldn’t converted and the new Christmas horses doesn’t show up when it converted the first time 

Here’s my logs
https://drive.google.com/drive/folders/ ... Bgsz-3QrDQ
Thanks for sharing the logs. Can you first try with the 1.3.1 version and see if that fixes the problem?
## Post #26
- Username: lucygoosey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 02, 2022 5:55 am
- Post datetime: 2022-12-22T20:48:30+00:00
- Post Title: Re: Star Stable Online - SSO Extract

Hi! I was just wondering if it is possible to get the rigs of the horse models to make poses in Blender and such. Thanks!
## Post #27
- Username: Kitty Cute
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 04, 2022 5:13 am
- Post datetime: 2022-12-23T11:31:29+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from lucygoosey ↑Fri Dec 23, 2022 4:48 am at Fri Dec 23, 2022 4:48 am
>
> 
Hi! I was just wondering if it is possible to get the rigs of the horse models to make poses in Blender and such. Thanks!

Wouldn't the Rigs come with the .dae Models?
## Post #28
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2022-12-23T12:33:59+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from lucygoosey ↑Fri Dec 23, 2022 4:48 am at Fri Dec 23, 2022 4:48 am
>
> 
Hi! I was just wondering if it is possible to get the rigs of the horse models to make poses in Blender and such. Thanks!

I'm still working on that, it's almost done but they still don't look quite right.

> Reply from Kitty Cute ↑Fri Dec 23, 2022 7:31 pm at Fri Dec 23, 2022 7:31 pm
>
> 
Wouldn't the Rigs come with the .dae Models?

Nothing comes for free I'm afraid  To export something I first need to analyse and reverse engineer the file format and then write code to convert that into a standard format. And sometimes this is not possible at all, if a game uses functionality that is uniquely tied to it's game engine.
## Post #29
- Username: Kitty Cute
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 04, 2022 5:13 am
- Post datetime: 2022-12-25T11:21:18+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from locknut ↑Fri Dec 23, 2022 8:33 pm at Fri Dec 23, 2022 8:33 pm
>
> 
lucygoosey wrote: ↑Fri Dec 23, 2022 4:48 am
Hi! I was just wondering if it is possible to get the rigs of the horse models to make poses in Blender and such. Thanks!


I'm still working on that, it's almost done but they still don't look quite right.
Kitty Cute wrote: ↑Fri Dec 23, 2022 7:31 pm
Wouldn't the Rigs come with the .dae Models?


Nothing comes for free I'm afraid  To export something I first need to analyse and reverse engineer the file format and then write code to convert that into a standard format. And sometimes this is not possible at all, if a game uses functionality that is uniquely tied to it's game engine.

Oh ok... I was just wondering, when you have the time and think you're up to it, is there any way you could make the program have an import into the game option? I know that would be very hard to make, but you seem like you have an idea of how to do it, right? Sorry if I'm asking for too much :3
## Post #30
- Username: Horselover97
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 11:40 am
- Post datetime: 2023-01-26T00:36:20+00:00
- Post Title: Re: Star Stable Online - SSO Extract

It won’t upload the DAE files. It keeps telling me that 0 models were converted 
Here my log [https://drive.google.com/file/d/1ScW3jZ ... p=drivesdk](https://drive.google.com/file/d/1ScW3jZHjwG6sBo71Brw2DETPEjxyHXFK/view?usp=drivesdk)
## Post #31
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2023-01-26T07:31:24+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from Horselover97 ↑Thu Jan 26, 2023 8:36 am at Thu Jan 26, 2023 8:36 am
>
> 
It won’t upload the DAE files. It keeps telling me that 0 models were converted 
Here my log https://drive.google.com/file/d/1ScW3jZ ... p=drivesdk

Hi!
I just tested it with the latest game version and it converted all models without errors. The log file did not contain any clues for why it didnt work for you, so I will have to investigate this more and come back...
## Post #32
- Username: Horselover97
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 11:40 am
- Post datetime: 2023-01-31T02:09:04+00:00
- Post Title: Re: Star Stable Online - SSO Extract

it worked but the files are now fbx
## Post #33
- Username: Emma Pinkwatcher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 15, 2022 12:45 am
- Post datetime: 2023-06-26T17:48:13+00:00
- Post Title: Re: Star Stable Online - SSO Extract

I think there is a bug / error to the extract. The horse models, (GH81 and others), won't show up in the files.
## Post #34
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2023-06-26T18:52:05+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from Emma Pinkwatcher ↑Tue Jun 27, 2023 1:48 am at Tue Jun 27, 2023 1:48 am
>
> 
I think there is a bug / error to the extract. The horse models, (GH81 and others), won't show up in the files.

Hi
I just double checked this and GH81 are processed correctly for me. The filename is "GH81_Magical_Haflinger_SkinMesh.pme" if you extract, and "GH81_Magical_Haflinger_SkinMesh.fbx" if you convert.

If you dont see this, then please try again into a new empty folder and send me the log file if it still does not work as expected.
## Post #35
- Username: Emma Pinkwatcher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 15, 2022 12:45 am
- Post datetime: 2023-06-26T19:35:04+00:00
- Post Title: Re: Star Stable Online - SSO Extract

oh, ok I see now. I had to remove the files then extract them again. Thank you for your help! Also, thank you for creating the extract program. It helps me with photography ^^
## Post #36
- Username: FnSilvicot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 19, 2023 1:37 pm
- Post datetime: 2023-10-19T06:14:11+00:00
- Post Title: Re: Star Stable Online - SSO Extract

I have been checking this post for a year and have been waiting for possible animation updates, but just now I realized that this forum is about to be closed, so I just registered here just to reply. 
I am an artist who knows nothing about programming and is not good at English. So I'm sorry I never expressed my support for you here.

I must thank you for being able to access the model, which has been a great help.
I mainly have two questions:
1. Is animations and skeletons still possible? At least the skeletons? I'm not sure if it's too difficult, maybe I can commission you to create this feature? I really need it.
2. How can I use it on Star Stable 1-4? I downloaded them, but they don't have a CSA file.

I know it's already late, and I'm not sure if you can see this reply before the website closes. But if possible, my email is [fnsilvicot@gmail.com](mailto:fnsilvicot@gmail.com)
Anyway, thank you for everything you've done so far :>
## Post #37
- Username: locknut
- Rank: advanced
- Number of posts: 58
- Joined date: Tue Jan 04, 2022 9:50 pm
- Post datetime: 2023-10-19T06:56:51+00:00
- Post Title: Re: Star Stable Online - SSO Extract

Hi!
Thanks for the support 

I have not done anything with animations, and there are no plans to do that now. The skeletons are "kinda done", the only problem is that they are sometimes rotated 90 or 180 degrees. But I suspect that most artists will know how to adjust them so maybe I should just release it anyway with this bug.

I will rehost the tool somewhere else when this forum goes down, I didnt know that the date had been set to Dec 1st, so I should probably get started on that soon.

When you install SS 1-4, you will see a "data.csa" in the game folder. That is the file you need to select in SSO Extract.
## Post #38
- Username: FnSilvicot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 19, 2023 1:37 pm
- Post datetime: 2023-10-19T13:21:38+00:00
- Post Title: Re: Star Stable Online - SSO Extract

> Reply from locknut ↑Thu Oct 19, 2023 2:56 pm at Thu Oct 19, 2023 2:56 pm
>
> 

Yes, this is definitely a huge help! The rotation of the skeleton is not a big problem <33 
And about SS 1-4, it's working, thank you!!!! After install, the csa file is indeed there
