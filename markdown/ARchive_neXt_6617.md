## Post #1
- Username: dezmand07
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-15T00:49:58+00:00
- Post Title: ARchive_neXt

What is ARchive_neXt?

The next evolution of our forge file explorer.  Built to work on Win7 and Win8/8.1 both 32-bit and 64-bit.

Why the name change?

The only thing constant is change.

---

Well, it started out a long time as Assassin's Creed Explorer. It has since expanded into ForgeX, Archive X and now ARchive_neXt. A visual way of exploring Ubisoft .forge files from games such as Assassin's Creed, Assassin's Creed II, Assassin's Creed:Brotherhood, Assassin's Creed: Revelations, Assassin's Creed III, Assassin's Creed IV: Black Flag, Assassin's Creed: Unity, Assassin's Creed: Rogue, Assassin's Creed: Syndicate, Prince of Persia (2008), and Prince of Persia: The Forgotten Sands.

At this time you can view and export the DDS images/textures from all the games.  You can view the model files and export either as an .arx file (used for importing into 3DSMax with [arxImporter](http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=41)) or the common OBJ file format.

ARchive_neXt does not allow you to alter any of the .forge files.

Requirements:
.NET Framework 4.5
DirectX June 2010 Redistributable Runtime
One of the above mentioned games must be installed on your system.

You can get ARchive_neXt from the [Downloads](http://www.tbotr.net/modules.php?mod=Downloads&op=displayDownloads&sid=4&ssid=1) area.

-- MDA
## Post #2
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-17T22:39:49+00:00
- Post Title: ARchive_neXt

This issue was brought to my attention via private message.  I am re-posting it here for anyone else who may have the same issue.

> Hi.
>
> I downloaded your ForgeX from this page: http://www.tbotr.net/modules.php?mod=Do ... 4&sort=hot. During opening ForgeX I see: AC:Brotherhood so I open it. After that there is a tree with .forge files (DataPC files). But when I open any file I receive an error -> http://imageshack.us/f/101/error2k.jpg/. Did u have error with "Simplicit.neo"? Or maybe ForgeX folder should be placed in somewhere in AC:B folder? But I don't know where. Now I have this ForgeX folder in Desktop so maybe it's reason why I have error?

To solve this issue, please download lzonet_1.0.1.zip from the following location -->> [http://sourceforge.net/projects/lzo-net/](http://sourceforge.net/projects/lzo-net/)

Unzip the package, find the file "lzo.dll" and place that in your "Windows/system32" folder.  This should solve that issue.

Thank you for your support,
## Post #3
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-21T20:28:15+00:00
- Post Title: ARchive_neXt

Another dll issue brought to my attention, this one regarding viewing textures.  If you get a blank blue screen and/or an error message when attempting to view a dds texture...

Download the following -->> [dll](http://www.tbotr.net/Downloads/freeimage.zip)
Unzip it
Place the FreeImage.dll file in your "Windows/system32" folder

That should solve the problem.

Thanks for your support.
## Post #4
- Username: Nintynuts
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 26, 2011 1:46 am
- Post datetime: 2011-05-25T17:47:43+00:00
- Post Title: ARchive_neXt

I have AC:B installed in a custom steam directory. Could support for this be added?
## Post #5
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-05-25T18:27:23+00:00
- Post Title: ARchive_neXt

I tried to run (under Win7 x64), but it didn't wanted because of some System.Security.SecurityException. I can run with Admin rights, but I can see the windows and the image in the background, but nothing else. And I can't do anything.

Idea?
## Post #6
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-25T22:53:56+00:00
- Post Title: ARchive_neXt

> Reply from Nintynuts
>
> I have AC:B installed in a custom steam directory. Could support for this be added?

I'll work something out for the next update.

> Reply from evin
>
> I tried to run (under Win7 x64), but it didn't wanted because of some System.Security.SecurityException. I can run with Admin rights, but I can see the windows and the image in the background, but nothing else. And I can't do anything.

Idea?

The security exception sounds like it is not able to write to the registry.  Could be an issue with where I'm trying to write.  I'll switch that for the next update.  However that should not cause you not being able to see installed games.  That may be the same issue Nintynuts is having, and I'll work something out for that as well.  Hopefully, by the weekend.

Thank you for your support,
## Post #7
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2011-05-26T06:07:10+00:00
- Post Title: ARchive_neXt

Nice one, but no much more usefull than Elika Plugin, by my opinion, for my needs. One what i liked it's a String Table, but still useless if can't modify strings.

Also bad is when it can't find some game by registry, it should give browse for forge files,
also unstable, on some sections freezes and so on...

if someone can make simple toold to just decompress/compreesing forge files i can use decompressed data to modify, and there is nothing much needed than getting decompressed by lzo normally and way to compress in same way
## Post #8
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2011-05-28T19:57:59+00:00
- Post Title: ARchive_neXt

hello MichaelDarkAngel. Are you planning support for x64 operating systems? In windows 7 x64 ForgeX can not detect the list of games.
## Post #9
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-06-06T07:06:32+00:00
- Post Title: ARchive_neXt

How are the changes going?
## Post #10
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-06T22:37:45+00:00
- Post Title: ARchive_neXt

Well, I've cleaned up a lot of the code.  Removed all of the irrelevant information that was mainly more my own use.  And right this minute I'm working on an actual model viewer.  I've run into issues with that in the past, so I'm not sure exactly how far that is going to go.

Thanks for your support
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-08T05:18:45+00:00
- Post Title: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Well, I've cleaned up a lot of the code.  Removed all of the irrelevant information that was mainly more my own use.  And right this minute I'm working on an actual model viewer.  I've run into issues with that in the past, so I'm not sure exactly how far that is going to go.

Thanks for your support

Hi is it possible to make replace some files in the Data360.forge ?? I would like to play this game on X360 in my language and i would like to replace Localization Files with my language. I extracted my lang from PC version with Maki 1.2, but 360 version cannot be extracted, replace but they can be display in Maki 1.2, thats all. Please help with 360 files??

File from X360:

```
http://loadfiles.in/iur9i3glcwqn/Data360.forge
```

Thank you
## Post #12
- Username: quadcoremax
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 30, 2011 8:33 pm
- Post datetime: 2011-06-14T02:04:54+00:00
- Post Title: ARchive_neXt

Big THANX Michael !

With your 2 dlls, it works fine.

Ok, here's the issues, after checking UVs, none are actually existing. Same for textures materials. Maybe, I omitted something. Tested in Maya via obj importer.

The UVs could be easily remapped, but I like to ease my work, your tool is perfect for my custom games productions which I will showcase here once the work is done. I'll try to create something completely amazing with it soon.

Keep it up, I love it !
Thx for putting so much efforts,

Max

Artist/Animator/Texturer/Coder
=========================
Phenom X4 9950 BE OC 2900MHZ
OCZ Gold DDR2 4GB OC 1066MHZ
Gigabyte GA-MA78G-DS3H Rev2.0
ATI HD 4670 1024 MB
ATI HD 4670 512 MB
Corsair TX 750W
Triple Screen 19" LCD 3x DVI
XP SP 3
G25
G15
## Post #13
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-14T02:47:56+00:00
- Post Title: ARchive_neXt

> Reply from quadcoremax
>
> Big THANX Michael !

With your 2 dlls, it works fine.

Ok, here's the issues, after checking UVs, none are actually existing. Same for textures materials. Maybe, I omitted something. Tested in Maya via obj importer.

I haven't tested importing OBJ files with Maya, however if you open the OBJ file with notepad you'll see the section right after the vert list that defines the UVs.  For the materials there should be an MTL file named the same as your OBJ file that defines the textures to be used.  Also any DDS files found should also be exported.

The UVs being written, I know work well for 3DSMax.  Again, I haven't tested with Maya, so I can't say for sure.  I know that 3DSMax has an issue applying the MTL file even when being told where it is.  Maya may be having a similar issue.  I'll see if I can find some time to re-install Maya and check on these issues.

BTW, Blender does not seem to have either of these problems, just in case anyone was curious. 

> Reply from quadcoremax
>
> The UVs could be easily remapped, but I like to ease my work, your tool is perfect for my custom games productions which I will showcase here once the work is done. I'll try to create something completely amazing with it soon.

Keep it up, I love it !
Thx for putting so much efforts,

Max

Artist/Animator/Texturer/Coder
=========================
Phenom X4 9950 BE OC 2900MHZ
OCZ Gold DDR2 4GB OC 1066MHZ
Gigabyte GA-MA78G-DS3H Rev2.0
ATI HD 4670 1024 MB
ATI HD 4670 512 MB
Corsair TX 750W
Triple Screen 19" LCD 3x DVI
XP SP 3
G25
G15
## Post #14
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-14T04:10:15+00:00
- Post Title: ARchive_neXt

Update Progress Update

Well the model viewer is coming along...

Visit our Gallery for larger image

Some issues are occurring...

Visit our Gallery for larger image

What's interesting about the issue.  I need to create an .X file, so I can load that into the model viewer.  When loaded into the model viewer I get what you see above.  If I load that same .X file into Blender I have no issues.  The model viewer has similar issues with other models as well.  Some worse than others...

Visit our Gallery for larger image

Not really sure what is happening, but rest assured when exported the resulting model is in fact fine.

Other issues I'm having:

The rendering window will apparently only render on the form itself which causes the problem of the model being clipped by the tree view (this may be a DirectX/C# limitation).  I'm also still working on camera controls.

Thanks for your support.
## Post #15
- Username: quadcoremax
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 30, 2011 8:33 pm
- Post datetime: 2011-06-14T13:47:23+00:00
- Post Title: ARchive_neXt

Thx again, everything works as you explained.

Strange that Maya/3DS Max doesn't manage UV's as Blender does, once imported. I'll stick to Blender, been learning it in 2 days & it has some real powerful functions + py scripting is perfect for customizing/boosting production.

1 solution, if you're more comfortable with Maya/Max, just save it from Blender to dae file & import into Maya/Max, you should find all your UV shells. Cheers !



Maybe exporting as dae from ForgeX 'by default', would ease app compatibility, giving the same result across all 3D apps, but that's a tiny detail.

Looking forward to see your 3D viewer, 
Thx again for all efforts !

P.S.: Was thinking exporting some bunch of models in 1 row, if that's do-able, I'd appreciate that function a lot !
## Post #16
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2011-06-15T23:04:01+00:00
- Post Title: Re: ForgeX Beta Released

I get the issue with writing to the registry too. I can't run the program! It won't close either. It keeps saying an unhandled exception has occurred. So I have to close it through the Processes tab in Task Manager. Please can the creator upload the Beta version of the program!! I need this fixed ASAP! Great work though, not many people saying that, but this program is epic! AC:B models already! Very fast, kudos to you!  I just wish it worked on Windows 7 XD
## Post #17
- Username: hismastersvoice
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 01, 2011 7:55 pm
- Post datetime: 2011-06-16T15:51:55+00:00
- Post Title: Re: ForgeX Beta Released

Does this program work with Steam versions of the games? I've got AC2 and ACB installed in the default Steam directory and this is what I get when I launch ForgeX. As far as I can tell there should be some sort of directory tree in the left panel.
[Untitled-1.jpg](https://xentaxbackup.github.io/file/4342_Untitled-1.jpg)
## Post #18
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-16T21:29:26+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from hismastersvoice
>
> Does this program work with Steam versions of the games? I've got AC2 and ACB installed in the default Steam directory and this is what I get when I launch ForgeX. As far as I can tell there should be some sort of directory tree in the left panel.

Apparently Steam does not write the registry keys to the location I am trying to find them in.  Since I do not own the Steam version, I do not know what that location is.  If you could provide me with that information, I will be more than happy to include it in the next update which should be ready in about a week.

Thanks for your support,
## Post #19
- Username: hismastersvoice
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 01, 2011 7:55 pm
- Post datetime: 2011-06-17T09:43:42+00:00
- Post Title: Re: ForgeX Beta Released

Let's see.

Assassin's Creed Brotherhood

HKEY_CURRENT_USER\Software\Valve\Steam\Apps\48190

Assassin's Creed 2

HKEY_CURRENT_USER\Software\Valve\Steam\Apps\33230

Assassin's Creed

HKEY_CURRENT_USER\Software\Valve\Steam\Apps\15100

Hope that helps.
## Post #20
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2011-06-18T08:47:10+00:00
- Post Title: Re: ForgeX Beta Released

There is one more game with game resources such as *.forge - Shaun White Skateboarding
[HKEY_LOCAL_MACHINE\SOFTWARE\Ubisoft\Shaun White Skateboarding], and string value - "InstallDir"
## Post #21
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-18T16:57:11+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from dezmand07
>
> There is one more game with game resources such as *.forge - Shaun White Skateboarding
[HKEY_LOCAL_MACHINE\SOFTWARE\Ubisoft\Shaun White Skateboarding], and string value - "InstallDir"

Any chance you could give me all or part of one of the forge files from this game.  I will try to verify that the format is similar, at least enough to make adding it worthwile.

Thanks,
## Post #22
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2011-06-18T18:55:19+00:00
- Post Title: Re: ForgeX Beta Released

ok, several *.forge-files from the game
[http://narod.ru/disk/16406614001/DataPC.forge.html](http://narod.ru/disk/16406614001/DataPC.forge.html)
[http://narod.ru/disk/16410739001/DataPC_05.forge.html](http://narod.ru/disk/16410739001/DataPC_05.forge.html)
## Post #23
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2011-06-18T21:10:34+00:00
- Post Title: Re: ForgeX Beta Released

hi MichaelDarkAngel im new here and your tool seems very usefull. but, when I open your tool nothing happens? is that normal or is that something wrong with me?

windows 7 SP1 - 64bit home premium.

THANKS...
## Post #24
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2011-06-20T13:11:59+00:00
- Post Title: Re: ForgeX Beta Released

Hi there,

Am pretty new here too. I seem to have the same problem with the tool. On my laptop forge opens with no trees or files in view, just the bkg image. On my desktop forge crashes before it can run.

Both are on windows 7 64

Cheers
## Post #25
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-20T14:26:50+00:00
- Post Title: Re: ForgeX Beta Released

Please make it work with 360.forge file. I would kill someone  to play this game on x360 with my native lang.... . I have translated version from PC but i cannot repack the forge file 

```
http://loadfiles.in/iur9i3glcwqn/Data360.forge
```


Thx in advance
## Post #26
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2011-06-23T08:56:04+00:00
- Post Title: Re: ForgeX Beta Released

Hey, I got ForgeX to work on a Win XP machine but can you please tell me how I import .fex models into 3DS MAX? Where do I get the plugin, how do I install it? Can you please say everything from start to finish, don't leave any gaps? Assume I don't know what I'm doing  Cos I don't! So please help me in detail set up .fex import plugin!
## Post #27
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-24T01:22:59+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from carbint
>
> Hey, I got ForgeX to work on a Win XP machine but can you please tell me how I import .fex models into 3DS MAX? Where do I get the plugin, how do I install it? Can you please say everything from start to finish, don't leave any gaps? Assume I don't know what I'm doing  Cos I don't! So please help me in detail set up .fex import plugin!

Download NWMaxPlus v2.04.10 from -->> [here](http://www.tbotr.net/modules.php?mod=Downloads&req=viewsubcat&catid=1&subcatid=3&sort=new)

There are two folders inside the zip file (nwmax_plus and Startup).  Extract them into the Scripts directory of your 3DSMax installation.

Start 3DSMax.  NWMaxPlus will autostart.  Expand the "ForgeX FEX Loader", press the Browse button, and browse to where your FEX files are located, select one and press the Import button.

Done

This has been tested with 3DSMax6, 3DSMax7, 3DSMax8, 3DSMax9 and 3DSMax 2010.

Enjoy
## Post #28
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2011-06-24T07:45:04+00:00
- Post Title: Re: ForgeX Beta Released

Hey Michael.

Do you have any idea as to the problems of forge on windows 7 64? I am really keen to try it out. Will be more than happy to test different builds for ya!
## Post #29
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2011-06-24T17:10:24+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> carbint wrote:Hey, I got ForgeX to work on a Win XP machine but can you please tell me how I import .fex models into 3DS MAX? Where do I get the plugin, how do I install it? Can you please say everything from start to finish, don't leave any gaps? Assume I don't know what I'm doing  Cos I don't! So please help me in detail set up .fex import plugin! 

Download NWMaxPlus v2.04.10 from -->> here

There are two folders inside the zip file (nwmax_plus and Startup).  Extract them into the Scripts directory of your 3DSMax installation.

Start 3DSMax.  NWMaxPlus will autostart.  Expand the "ForgeX FEX Loader", press the Browse button, and browse to where your FEX files are located, select one and press the Import button.

Done

This has been tested with 3DSMax6, 3DSMax7, 3DSMax8, 3DSMax9 and 3DSMax 2010.

Enjoy

OMG thank you so much for your help!
## Post #30
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2011-06-24T19:23:02+00:00
- Post Title: Re: ForgeX Beta Released

Ummm... Nothing works with bones  The models are boneless in 3DS MAX! Sorry to bother you all again...
## Post #31
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-06-24T22:16:31+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from carbint
>
> Ummm... Nothing works with bones  The models are boneless in 3DS MAX! Sorry to bother you all again...

Yes they are boneless.  I have yet to determine the how the bones are stored, but I am working on it.
## Post #32
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2011-06-24T23:12:26+00:00
- Post Title: Re: ForgeX Beta Released

Ohh I thought the format already covered bones XD Well I'm rooting for you!
## Post #33
- Username: kampeador
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 17, 2011 4:32 am
- Post datetime: 2011-06-28T17:30:08+00:00
- Post Title: Re: ForgeX Beta Released

I have Assassin's creed 1 and Assassin's creed Brotherhood installed.
I have one big problem with ForgeX: [http://i56.tinypic.com/2n95zt.jpg](http://i56.tinypic.com/2n95zt.jpg)
## Post #34
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-06-28T19:52:35+00:00
- Post Title: Re: ForgeX Beta Released

For those having issues running the current version, if you haven't already and trust the program, try running the application as Administrator (right-click, then select Run as Administrator or change the properties of a shortcut so that it always runs that way).  This should help in a lot of cases to get past the issue of not having access privileges to some of the registry keys, which is what usually keeps it from being able to show anything for installed games.

Hope that helps.
## Post #35
- Username: LadyHorus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 03, 2011 8:03 am
- Post datetime: 2011-07-03T00:09:13+00:00
- Post Title: Re: ForgeX Beta Released

Hi there, I'm new.  I was looking for something that could help me get some of the ACB: Multiplayer models and I was recommended this program! Problem I'm having is the same as some others and I suspect it's because I'm running on a 64bit system as well. I have Windows 7 64bit with two different Program Files directories, one at C:\Program Files and the other at C:\Program Files (x86). Your ForgeX I assume looks under Program Files? It would be a life saver to have an option to browse for the correct directory as I'm sure not all systems are set up the same way as is obvious. Unfortunately for me I can't use your program as it is even after downloading the other dll files. All I get when I start up your program is the background image with the divider down one side. I can tell from screenshots it's supposed to display a tree on one side that shows available games?

I could try popping in the ACB disk to see if it will find it, but somehow I doubt it. I have it fully installed on my system so, it wouldn't make much sense.

Any help would be greatly appreciated! thank you
## Post #36
- Username: Shaddy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 08, 2008 7:11 pm
- Post datetime: 2011-07-04T20:39:54+00:00
- Post Title: Re: ForgeX Beta Released

Hey, i just wanted to say thank you for your work on the dreaded .forge format.

Btw, do you think there's hope of extracting audio? I've been itching to get the original sound files of AC for years
## Post #37
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-07-05T02:16:26+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from LadyHorus
>
> Hi there, I'm new.  I was looking for something that could help me get some of the ACB: Multiplayer models and I was recommended this program! Problem I'm having is the same as some others and I suspect it's because I'm running on a 64bit system as well. I have Windows 7 64bit with two different Program Files directories, one at C:\Program Files and the other at C:\Program Files (x86). Your ForgeX I assume looks under Program Files? It would be a life saver to have an option to browse for the correct directory as I'm sure not all systems are set up the same way as is obvious. Unfortunately for me I can't use your program as it is even after downloading the other dll files. All I get when I start up your program is the background image with the divider down one side. I can tell from screenshots it's supposed to display a tree on one side that shows available games?

I could try popping in the ACB disk to see if it will find it, but somehow I doubt it. I have it fully installed on my system so, it wouldn't make much sense.

Any help would be greatly appreciated! thank you

ForgeX looks in the registry for the location of any installed games.  Problem stems from the fact that I have only my own installation to draw that information from.  Versions of the game purchased from Steam have issues because Steam uses custom registry entries.  Windows Vista and Windows 7 have issues because they locate the registry entries dependent on how you install the game (administrator vs. regular user).  The next version of ForgeX will attempt to remedy these issues.  However work on the next version has slowed to a crawl.  I have a couple of websites that need attending to and at the moment they take precedence.

> Reply from Shaddy
>
> Hey, i just wanted to say thank you for your work on the dreaded .forge format.

Btw, do you think there's hope of extracting audio? I've been itching to get the original sound files of AC for years

I am not entirely familiar with audio formats, however I have read that AC1's audio files are headerless and it just requires applying the proper header.  I'll try looking into this more when I get back to working on this.

Thanks for your interest and support,
## Post #38
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2011-07-05T09:46:38+00:00
- Post Title: Re: ForgeX Beta Released

Hey Michael

Thanks for your reply and thanks for the work you are doing on forge x. Its greatly appreciated. Looking forward to the new build
## Post #39
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-07-07T10:20:09+00:00
- Post Title: Re: ForgeX Beta Released

Hey man,
just installed windows7 32 bit on one of my computers, and the first thing i tried to use was this, and it works great. Still no luck with x64 bit systems though.
Once installed and run as admin it worked great, great job.
One thing that is bugging me though is if i export a texture from one package, then go to another package, going back to that texture will not work.  This is the only problem i have with it. I'll provide a screen if i can, but its not really important, cause everything else works fine! 

Also, when i first installed it, i had to go slow with exporting the textures(waiting a few seconds before i could export another one), although that seems to have gone now(i dont know why lol).

Oh, and it doesn't search sub-directories(e.g. Assassin's Creed Brotherhood\multi) but copy-and-pasting all the .forge files into the main directory worked.

Anyways great job.

P.S. I love how it exports all materials applied to the model even when i only export the model, awesome.
## Post #40
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-07T13:08:19+00:00
- Post Title: Re: ForgeX Beta Released

cau u also do a repack of forge files ? What about suppot x360 - that would be reall deal
## Post #41
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2011-07-08T20:45:02+00:00
- Post Title: Re: ForgeX Beta Released

any updates ???
## Post #42
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2011-07-10T00:01:25+00:00
- Post Title: Re: ForgeX Beta Released

Please post some updates...
## Post #43
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-08-20T03:13:36+00:00
- Post Title: Re: ForgeX Beta Released

Zombie thread?
any updates yet?
## Post #44
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2011-08-25T21:10:19+00:00
- Post Title: Re: ForgeX Beta Released

I'm using Win7 x64 edition and it saves the game registry into [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Ubisoft\Assassin's Creed Brotherhood]. So I added a new path without the Wow6432Node. ForgeX found brotherhood, but when I click on something in the list I get this error

```
System.TypeInitializationException: The type initializer for 'Simplicit.Net.Lzo.LZOCompressor' threw an exception. ---> System.DllNotFoundException: Unable to load DLL 'lzo.dll': The specified module could not be found. (Exception from HRESULT: 0x8007007E)
   at Simplicit.Net.Lzo.LZOCompressor.__lzo_init3()
   at Simplicit.Net.Lzo.LZOCompressor..cctor()
   --- End of inner exception stack trace ---
   at Simplicit.Net.Lzo.LZOCompressor..ctor()
   at AC_Explorer.frmACX.acxDecompress(String forgeName, TreeNode treeNode, String tempExt)
   at AC_Explorer.frmACX.acxTreeView_AfterSelect(Object sender, TreeViewEventArgs e)
   at System.Windows.Forms.TreeView.TvnSelected(NMTREEVIEW* nmtv)
   at System.Windows.Forms.TreeView.WmNotify(Message& m)
   at System.Windows.Forms.TreeView.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
```


I have the steam edition btw, anyway around this error?
## Post #45
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-08-25T22:48:14+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from deadca7
>
> I'm using Win7 x64 edition and it saves the game registry into [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Ubisoft\Assassin's Creed Brotherhood]. So I added a new path without the Wow6432Node. ForgeX found brotherhood, but when I click on something in the list I get this error
Code: Select all************** Exception Text **************
System.TypeInitializationException: The type initializer for 'Simplicit.Net.Lzo.LZOCompressor' threw an exception. ---> System.DllNotFoundException: Unable to load DLL 'lzo.dll': The specified module could not be found. (Exception from HRESULT: 0x8007007E)


I have the steam edition btw, anyway around this error?

Check this [post](http://forum.xentax.com/viewtopic.php?p=54172#p54172) and the one right after it back on page one.  I believe the first post will solve your current problem.  Based on others' issues at that time you may not know you have the second problem until solving this one first.

Thanks,
## Post #46
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2011-08-26T00:13:36+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> Check this post and the one right after it back on page one.  I believe the first post will solve your current problem.  Based on others' issues at that time you may not know you have the second problem until solving this one first.

Thanks,

Thanks for the fast reply. I copied the lzo.dll into System32 and SysWOW64 which is the 32 folder on 64 bit. I got this error

```
System.TypeInitializationException: The type initializer for 'Simplicit.Net.Lzo.LZOCompressor' threw an exception. ---> System.BadImageFormatException: An attempt was made to load a program with an incorrect format. (Exception from HRESULT: 0x8007000B)
   at Simplicit.Net.Lzo.LZOCompressor.__lzo_init3()
   at Simplicit.Net.Lzo.LZOCompressor..cctor()
   --- End of inner exception stack trace ---
   at Simplicit.Net.Lzo.LZOCompressor..ctor()
   at AC_Explorer.frmACX.acxDecompress(String forgeName, TreeNode treeNode, String tempExt)
   at AC_Explorer.frmACX.acxTreeView_AfterSelect(Object sender, TreeViewEventArgs e)
   at System.Windows.Forms.TreeView.TvnSelected(NMTREEVIEW* nmtv)
   at System.Windows.Forms.TreeView.WmNotify(Message& m)
   at System.Windows.Forms.TreeView.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
```
## Post #47
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2011-09-05T17:11:46+00:00
- Post Title: Re: ForgeX Beta Released

I have problem
When I open ForgeX nothing shows, just picture of Ezio, Prince...
I tried running program as admin but same result.
Program is installed in Assassin's Creed Brotherhood directory and I'm using Win7 32bit
Any help?
## Post #48
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-10-24T10:35:01+00:00
- Post Title: Re: ForgeX Beta Released

I don't mean to drone on, but how about an update? 
I ask now because with revelations getting released soon, this is gonna become a popular thread
## Post #49
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-10-31T18:02:42+00:00
- Post Title: Re: ForgeX Beta Released

I'm curious, are there actually any plans for more functionality for Beyond good and evil? Sadly the old Jade plugin only allows you to unpack the main container, not actually get anything useful out of it
## Post #50
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2012-02-08T16:55:00+00:00
- Post Title: Re: ForgeX Beta Released

REVELATIONS HAS BEEN RELEASED. WOOO!
Sure, it was a (sortof) while ago, but nothing yet?

I'll have to hang out here for a while:
[viewtopic.php?f=10&t=3005](http://forum.xentax.com/viewtopic.php?f=10&t=3005)
## Post #51
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-02-20T17:02:02+00:00
- Post Title: Re: ForgeX Beta Released

Well no love for this tool anymore? I'm trying with AC2 but, Win7x64 Tried both directories (86) and normal, but the ForgeX window is empty -_-
## Post #52
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2012-03-29T07:43:31+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from CMihai
>
> Well no love for this tool anymore? I'm trying with AC2 but, Win7x64 Tried both directories (86) and normal, but the ForgeX window is empty -_-

I just use virtual box with windows7 32bit. I export the models to a shared folder(between the virtual pc and my computer).
This does require installing all the games onto the virtual machine.

Also, to export models from revelations, just copy paste all .forge files into the root folder of brotherhood.
I have exported many models, and i only get an issue on one of the models(i think its old altair's beard).

Also bump for update.
## Post #53
- Username: Tosyk
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-04T01:13:57+00:00
- Post Title: Re: ForgeX Beta Released

ForgeX Beta 2 has finally been released.

Complete and total rebuild, a very basic model viewer has been added, support for AC: Revelations and Shaun White Skateboarding has been added.

If ForgeX cannot find your installed games via the Registry, you will now be asked to point to your install directory.  This has the potential to incorrectly identify which game you are trying to open.  Multiple games can be added by right-clicking an empty area of the tree view window and selecting "Add Game".  This is a per session addition, meaning: Every time you start the program you will need to add your games.  I may fix this using ForgeX registry entries.

Yes there are bugs, some I am aware of, others I'm sure you will find.

Prince of Persia 2008: Model files do not appear in the model viewer properly, once extracted do not import into [insert 3D program] properly.
AC: Revelations: Unable to view/export beard model files.

Download and support from my website -- [TBotR](http://www.tbotr.net/) -- [Like](http://www.facebook.com/pages/The-Brotherhood-of-the-Realm/304591026230774) us on Facebook.
## Post #54
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-04T01:27:45+00:00
- Post Title: Re: ForgeX Beta Released

Cool thanks! any new about bones/weights?
## Post #55
- Username: com123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2011 12:39 am
- Post datetime: 2012-04-04T11:15:06+00:00
- Post Title: Re: ForgeX Beta Released

Only extract the dds files?
Other types of file how to extract?
## Post #56
- Username: Marky
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-05T00:23:24+00:00
- Post Title: Re: ForgeX Beta Released

At this time the only extractable file types are image files and model files.

For image files you can right-click the image in the right-side panel or right-click the file name in the tree view window after selecting it.

For model files you can select one of the "Export As" buttons in the right-side panel or right-click the file name in the tree view window after selecting it.

Unfortunately I have yet to figure out bone structures.

Thanks for your support,
## Post #57
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2012-04-08T15:18:30+00:00
- Post Title: Re: ForgeX Beta Released

any possibility to add AC1 xbox 360 version support? We really need this to translate the game into Russian.
## Post #58
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-04-08T16:58:54+00:00
- Post Title: Re: ForgeX Beta Released

Hey,

Thanks for forge x. Got it working eventually through a virtual pc on win 7 64 (so if anyone else is having problems on win 64 do it that way)

I was wondering if there is a possibility to just extract all files/textures in one go? (sorry if I have missed something really simple! )

Thanks

Mark
## Post #59
- Username: Marky
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-08T17:11:06+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from Marky
>
> Hey,

Thanks for forge x. Got it working eventually through a virtual pc on win 7 64 (so if anyone else is having problems on win 64 do it that way)

I was wondering if there is a possibility to just extract all files/textures in one go? (sorry if I have missed something really simple! )

Thanks

Mark
No you didn't miss anything.  I'm working on that for the next release.

> Reply from GamerSuper
>
> any possibility to add AC1 xbox 360 version support? We really need this to translate the game into Russian.
Sorry, no plans for xBox support.
## Post #60
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2012-04-10T16:05:11+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> Marky wrote:Hey,

Thanks for forge x. Got it working eventually through a virtual pc on win 7 64 (so if anyone else is having problems on win 64 do it that way)

I was wondering if there is a possibility to just extract all files/textures in one go? (sorry if I have missed something really simple! )

Thanks

Mark
No you didn't miss anything.  I'm working on that for the next release.
GamerSuper wrote:any possibility to add AC1 xbox 360 version support? We really need this to translate the game into Russian.
Sorry, no plans for xBox support.

Any chance to get some descriptions or sth about forge format from you? I know the guy who makes translations for x360 games into Russian... But forge is too hard for him. If he had descriptions or sth he would manage to make a translation.
Are you able to share the source code with him? Or you don't give it to anyone?
## Post #61
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-16T20:13:58+00:00
- Post Title: Re: ForgeX Beta Released

1. I got error message when I try view the model (ACR.)
2. I export the 3d objects as .OBJ but, when I try to open it there is no UV map on models. (ACR.)
## Post #62
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-16T22:09:15+00:00
- Post Title: Re: ForgeX Beta Released

1. Screenshot of the error window or at least a little more information on what the error is.
2. What 3D program are you using to import the OBJ file?

More information will get you more help.
## Post #63
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-17T08:14:23+00:00
- Post Title: Re: ForgeX Beta Released

1. screenshot [](http://www.imagebam.com/image/d6cec4185350894)
2. 3ds max
## Post #64
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-04-18T16:18:19+00:00
- Post Title: Re: ForgeX Beta Released

ForgeX really doesn't works on x64 systems.
You have to plan to fix it?
Me and three other guys tried out your tool, and it only works on x86 systems.
## Post #65
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-04-18T18:08:45+00:00
- Post Title: Re: ForgeX Beta Released

If you setup a virtual device and install your AC and forge x on that, it will work.... Not quite x64, but its a workaround!
## Post #66
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-22T16:21:49+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from ersel54
>
> 2. I export the 3d objects as .OBJ but, when I try to open it there is no UV map on models. (ACR.)

2. 3ds max

What version of 3DSMax?

Tested with 3DSMax6 and OBJ plugin -- imports mesh correctly, but does not import uv maps. [EDIT]It does import uv maps if you have that option checked[/EDIT]   
Tested with 3DSMax7 -- uv maps import properly, some faces import flipped.
Tested with 3DSMax8 -- uv maps import properly, some faces import flipped.
Tested with 3DSMax9 -- uv maps import properly, some faces import flipped.
Tested with 3DSMax2010 -- uv maps import properly (best importer in my opinion).
Tested with Blender -- uv maps import properly.

3DSMax 6 does not come with the OBJ plugin, you need to download an external plugin and that could be the issue.

As for the model viewing error, are you experiencing that error with all models?
## Post #67
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-22T17:52:14+00:00
- Post Title: Re: ForgeX Beta Released

New version 4.22.0 now online.

Fixed a bug in the OBJ exporter that was not exporting material names properly.

Thanks for your support.
## Post #68
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-22T20:41:53+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> ersel54 wrote:2. I export the 3d objects as .OBJ but, when I try to open it there is no UV map on models. (ACR.)

2. 3ds max

What version of 3DSMax?

Tested with 3DSMax6 and OBJ plugin -- imports mesh correctly, but does not import uv maps.
Tested with 3DSMax7 -- uv maps import properly, some faces import flipped.
Tested with 3DSMax8 -- uv maps import properly, some faces import flipped.
Tested with 3DSMax9 -- uv maps import properly, some faces import flipped.
Tested with 3DSMax2010 -- uv maps import properly (best importer in my opinion).
Tested with Blender -- uv maps import properly.

3DSMax does not come with the OBJ plugin, you need to download an external plugin and that could be the issue.

As for the model viewing error, are you experiencing that error with all models?
3ds max 2010 and yes I got this error on every model.
## Post #69
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-22T23:20:17+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from ersel54
>
> 3ds max 2010 and yes I got this error on every model.

The uv maps were there, but the issue I think you had was due to the material name bug I found and fixed with the latest release.

I'm not sure what could be causing the model viewer issue.  Are you able to view textures?
## Post #70
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-04-23T02:42:55+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> ersel54 wrote:3ds max 2010 and yes I got this error on every model.

The uv maps were there, but the issue I think you had was due to the material name bug I found and fixed with the latest release.

I'm not sure what could be causing the model viewer issue.  Are you able to view textures?

Any plan to fix also the issue on x64 systems?
## Post #71
- Username: Marky
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-23T03:05:29+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from Herdell
>
> Any plan to fix also the issue on x64 systems?

Until I upgrade to a 64-bit OS... No, sorry.    

I'm afraid at this time your only option is to try Marky's solution.
## Post #72
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-04-23T10:07:10+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> Herdell wrote:Any plan to fix also the issue on x64 systems?

Until I upgrade to a 64-bit OS... No, sorry.    

I'm afraid at this time your only option is to try Marky's solution.

IS ther eany chance of an update to export the whole library or multiple selections soon? Its the only thing I think would be helpful.... Even exporting all textures, or export all obj's.......... Its difficuilt to find what you are looking for at the moment

Keep up the good work!
## Post #73
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-23T11:53:44+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> ersel54 wrote:3ds max 2010 and yes I got this error on every model.

The uv maps were there, but the issue I think you had was due to the material name bug I found and fixed with the latest release.

I'm not sure what could be causing the model viewer issue.  Are you able to view textures?
I have downloaded latest version but still no uv maps and no issue with viewing textures are ok.
## Post #74
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-23T12:45:28+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from ersel54
>
> I have downloaded latest version but still no uv maps and no issue with viewing textures are ok.

Last thing I can think of


Model in the image viewer

Open 3DSMax2010 and select the OBJ Importer

Make sure the highlighted options are selected in the import window


And you should end up with this

If this still doesn't give you results, please let me know which model(s) you are trying to import.

We'll figure it out yet.
## Post #75
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-23T22:40:46+00:00
- Post Title: Re: ForgeX Beta Released

on forgeX beta/data location I think found something there is no ACR_MDL.stc file in that folder but there is ACB_MDL.stc and AC2_MDL.stc files.
can you take a look at setup?
## Post #76
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-23T23:51:12+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from ersel54
>
> on forgeX beta/data location I think found something there is no ACR_MDL.stc file in that folder but there is ACB_MDL.stc and AC2_MDL.stc files.
can you take a look at setup?

The .stc files are simply text files that provide information on the various file formats.  They have bearing what so ever on the function of the program.

If my previous suggestion does not solve your import issue, please provide with specific model names so that I may also test those models.

Thank you for your support,
## Post #77
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-24T09:36:07+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> ersel54 wrote:on forgeX beta/data location I think found something there is no ACR_MDL.stc file in that folder but there is ACB_MDL.stc and AC2_MDL.stc files.
can you take a look at setup?

The .stc files are simply text files that provide information on the various file formats.  They have bearing what so ever on the function of the program.

If my previous suggestion does not solve your import issue, please provide with specific model names so that I may also test those models.

Thank you for your support,
yes I tried what you said before but noway still error with viewing models and no uv maps when I export as .OBJ. 
the model name is:
dataPC/_CC_G_fedayin_trainee_female/models/CC_G_fedayin_female_rank01_LOD0
## Post #78
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-24T22:22:25+00:00
- Post Title: Re: ForgeX Beta Released

I have no idea what the problem with your setup is that would be causing the import issue, or even the model viewing issue for that fact.  You can open any of the exported OBJ files with notepad and clearly see the texture coordinates are there.

```
#Exported by ForgeX on 4/24/2012 6:03:23 PM
mtllib CC_G_Fedayin_Female_Rank01_LOD0.mtl

v 13 -203 4889
v 13 -206 4884
v 14 -206 4885
v -40 -183 4845

... snip ...

v -151 -370 4461
v -121 -381 4438
v -120 -360 4456
v -95 -374 4466
# 3564 vertices

vt 0.07617188 -0.2470703
vt 0.07714844 -0.2460938
vt 0.07714844 -0.2456055
vt 0.06933594 -0.2358398

... snip ...

vt 0.6992188 -0.9428711
vt 0.7275391 -0.887207
vt 0.7275391 -0.9428711
vt 0.7558594 -0.9428711
# 3564 texture coordinates

g CC_G_Fedayin_Female_Rank01_LOD0_0
usemtl CC_G_Fedayin_Uppercloth
s 0
f 1/1 2/2 3/3
f 4/4 5/5 6/6
f 7/7 8/8 9/9
f 10/10 11/11 12/12

... snip ...

f 1093/1093 1064/1064 1094/1094
f 1066/1066 1094/1094 1064/1064
f 1093/1093 1094/1094 1072/1072
f 1072/1072 1094/1094 1066/1066
# 4515 triangles

g CC_G_Fedayin_Female_Rank01_LOD0_1
usemtl CC_G_Fedayin_Lower
s 0
f 1095/1095 1096/1096 1097/1097
f 1097/1097 1098/1098 1095/1095
f 1099/1099 1100/1100 1101/1101
f 1101/1101 1102/1102 1099/1099

... snip ...

f 2294/2294 2296/2296 2261/2261
f 2296/2296 2295/2295 2292/2292
f 2292/2292 2258/2258 2296/2296
f 2261/2261 2296/2296 2258/2258
# 4515 triangles

g CC_G_Fedayin_Female_Rank01_LOD0_2
usemtl LIB_Universal_Female_Torso
s 0
f 2297/2297 2298/2298 2299/2299
f 2299/2299 2300/2300 2297/2297
f 2300/2300 2299/2299 2301/2301
f 2302/2302 2297/2297 2300/2300

... snip ...

f 2788/2788 2789/2789 2786/2786
f 2790/2790 2789/2789 2788/2788
f 2791/2791 2790/2790 2788/2788
f 2785/2785 2791/2791 2788/2788
# 4515 triangles

g CC_G_Fedayin_Female_Rank01_LOD0_3
usemtl CC_G_Fedayin_Armor
s 0
f 2792/2792 2793/2793 2794/2794
f 2794/2794 2795/2795 2792/2792
f 2796/2796 2797/2797 2798/2798
f 2798/2798 2799/2799 2796/2796

... snip ...

f 3563/3563 3564/3564 3562/3562
f 3563/3563 3560/3560 3564/3564
f 3559/3559 3562/3562 3564/3564
f 3559/3559 3564/3564 3560/3560
# 4515 triangles
```


The second section where the lines start with vt are the uv map (texture) coordinates.  Why they don't work for you and why the model viewer does not work...  Sorry, but I am out of suggestions.
## Post #79
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2012-04-26T18:19:19+00:00
- Post Title: Re: ForgeX Beta Released

@MichaelDarkAngel: thank you for the answers. but, I've checked all the codes yes the codes are there but... I don't know why the uv maps are not there on max 2010? .
I hope that you can found the solution.
## Post #80
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-26T21:59:29+00:00
- Post Title: Re: ForgeX Beta Released

There is one more suggestion I can make.  It may solve the model viewer issue, I doubt it would have any effect on the import issue.  It may not work for either one, but it's the last thing I can think of.

Try updating your DirectX.
## Post #81
- Username: thaitam7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 29, 2012 12:25 pm
- Post datetime: 2012-04-29T04:49:43+00:00
- Post Title: Re: ForgeX Beta Released

I can't open it, it stopped working, why???
## Post #82
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-04-29T05:30:58+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from thaitam7
>
> I can't open it, it stopped working, why???
You probably tried to run it in a x64 operating system.
Same problem here, and no solution soon, then, try a v-machine or
get some x86 OS.
## Post #83
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-29T14:39:48+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from thaitam7
>
> I can't open it, it stopped working, why???

It could be any number of reasons, without more specific information any answer would just be a guess.
## Post #84
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-05-19T17:04:50+00:00
- Post Title: Re: ForgeX Beta Released

Hi Michael!

With so much to read in this thread, it's unclear what state the beta is currently in. I'm hoping you can help me out since ForgeX stops working immediately when I try to run it. I'm running a 64-bit system and I have Revelations installed through Steam. From what I've read, it sounds like both of these things will prevent ForgeX from working. Do you have any suggestions? Or am I just out of luck for now? I'm trying to get the dlc Gladiator model for a mod project.

Best regards,
dragbody
## Post #85
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-05-19T17:32:49+00:00
- Post Title: Re: ForgeX Beta Released

I may have an idea about the uv maps / model display failure...

In some other cases i had problems with importing models cause the script / plugin used a different decimal seperator -> fucking up the coordinates 

So what you can try: What is the decimal seperator in your country? "." or "," ?

Try changing it in the windows language settings from "." to "," or vice versa...

See if that helps
## Post #86
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-05-19T18:13:30+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from dragbody
>
> Hi Michael!

With so much to read in this thread, it's unclear what state the beta is currently in. I'm hoping you can help me out since ForgeX stops working immediately when I try to run it. I'm running a 64-bit system and I have Revelations installed through Steam. From what I've read, it sounds like both of these things will prevent ForgeX from working. Do you have any suggestions? Or am I just out of luck for now? I'm trying to get the dlc Gladiator model for a mod project.

Best regards,
dragbody

Sorry, I still don't own a 64-bit OS, so there is still no support for a version working directly under that OS.  Best solution at this time is to try Marky's suggestion from this [post](http://forum.xentax.com/viewtopic.php?p=70951#p70951).

> Reply from Itze
>
> I may have an idea about the uv maps / model display failure...

In some other cases i had problems with importing models cause the script / plugin used a different decimal seperator -> fucking up the coordinates 

So what you can try: What is the decimal seperator in your country? "." or "," ?

Try changing it in the windows language settings from "." to "," or vice versa...

See if that helps

I always forget about the decimal separator difference.  Thanks for the tip
## Post #87
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-08-04T14:41:33+00:00
- Post Title: Re: ForgeX Beta Released

I found the solution for the uv maps / model display failure.
The problem is the one discovered by Itze, changing every "," in the .obj with a "." (using notepad), when you try to load the modified .obj, It'll have UV maps.
## Post #88
- Username: LaBamba
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 13, 2012 3:37 pm
- Post datetime: 2012-08-13T07:44:40+00:00
- Post Title: Re: ForgeX Beta Released

Could someone please get me 3D files of Iraqi city from Splinter Cell Conviction instead of me getting the game for that purpose? I mean that is Ubisoft game so it should work.
## Post #89
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-08-14T07:54:55+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from LaBamba
>
> Could someone please get me 3D files of Iraqi city from Splinter Cell Conviction instead of me getting the game for that purpose? I mean that is Ubisoft game so it should work.

No help here.  Splinter Cell Conviction does not use Forge files.  The files used by the game are completely different.
## Post #90
- Username: Walrus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2012 10:24 pm
- Post datetime: 2012-08-14T14:47:00+00:00
- Post Title: Re: ForgeX Beta Released

Hi all  

I've read the previous messages but I didn't find anything about this issue. Opening both models from Brotherhood and Revelations, almost every model it's showed in the model viewer without textures:

[](http://i49.tinypic.com/m7xbmq.jpg)

[](http://i49.tinypic.com/2qx55ph.jpg)

Does it depends because they're static models? Also exporting in .obj format importing in 3ds Max 2009 and 2012 they're without textures or materials. Usually they're under the same material even when it's clear that the model uses different texture files. I'm using the same import settings posted [here](http://forum.xentax.com/viewtopic.php?f=10&t=6617&start=73).

Those are the settings I'm using on Max 2012:



When it's easy discover some of the textures used by the model I can assign them in the mat editor, but usually the same texture it's assigned to every mesh, that creates wrong texturing:

[](http://i47.tinypic.com/2jdgbp1.jpg)

The UV coordinates are wrong in Max 2009 (they look too small to fit the correct texture map), but it seems that in Max 2012 they're right. Maybe it could be a good idea edit the obj exporter to make it export ALSO all the linked texture files, indipendently if they're already extracted.

Any suggestions?
## Post #91
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-08-15T00:55:57+00:00
- Post Title: Re: ForgeX Beta Released

Let's see if I can explain this...

> Reply from Walrus
>
> I've read the previous messages but I didn't find anything about this issue. Opening both models from Brotherhood and Revelations, almost every model it's showed in the model viewer without textures:

Does it depends because they're static models?

Type of model makes no difference.  It's all about where files are located and the relationships between files.

File Locations
The .forge files are containers of compressed datafiles.  When you select a .forge file, you a shown a listing of the datafiles contained within it.  When you select a datafile, ForgeX decompresses the datafile and organizes it into categories of files contained within the datafile.  Some datafiles do not show a listing of what is contained within, because I have yet to determine the nature of all file types.

File Relations
When you select a model file, inside that file is the vertex info, texture coordinate info, face info and IDs to other required files, such as animations and materials.  If the ID of the material can be found inside any of the decompressed datafiles contained in the parent .forge file, then inside that file ForgeX looks to determine the ID of any Material Sets used.  ForgeX will then go through the same process to determine the IDs of required texture files.

You will often find the same file in multiple locations, the game engine certainly has a better handle on where and how to find the required files than ForgeX does.  I created ForgeX to be as quick as possible and use as little resources as possible and still give you some way of knowing what it is you are looking at.  In turn, this does give it some limitations.

> Reply from Walrus
>
> Also exporting in .obj format importing in 3ds Max 2009 and 2012 they're without textures or materials. Usually they're under the same material even when it's clear that the model uses different texture files. I'm using the same import settings posted [snip]

I never did like the OBJ format, but it is there because it is universal.  Because of it's universality it relies on the import script used to handle the information contained within properly.  The script I have for 3DSMAX 6 - 9 will not apply the textures.  The one that I use for 3DSMAX 2012 does apply the textures.  Although it does look as if both handle meshes without a defined material incorrectly.  Whether that is an issue in the way I have written the OBJ file, or the way in which the script is handling the OBJ file, I have yet to determine.

Hopefully this provides some insight into some of your concerns.

Thanks for your support,
## Post #92
- Username: Walrus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2012 10:24 pm
- Post datetime: 2012-08-17T11:36:23+00:00
- Post Title: Re: ForgeX Beta Released

Thank you Michael  Now it's all clear.

I would report you also about a (probably?) issue about texture exporting in .dds format: usually the exported texture it's upside down. Exporting in any other format (.png, .bmp, .tga and so on) the texture it's exactly as showed in the preview of ForgeX. Not a big issue, but I tell you anyway
## Post #93
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-12-21T02:02:50+00:00
- Post Title: Re: ForgeX Beta Released

Posted this before the crash, apparently just before, because it didn't save 

So I finally got AC3, and while I can't play the game  because I don't have DirectX 10 due to the fact that I am still running Windows XP, I can however play around with the files  .

I can tell you right out of the gate they have changed the forge format, slightly perhaps, but still enough that I am going to need to do some significant file spelunking in order to make ForgeX work.

So give me a few more days, perhaps a week and I should have something workable or at the very least some more information.

Thanks,
## Post #94
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2012-12-21T12:40:25+00:00
- Post Title: Re: ForgeX Beta Released

Prince of Persia:Forgotten Sands not supported?
## Post #95
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-12-22T00:06:10+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from bruno021
>
> Prince of Persia:Forgotten Sands not supported?

Just bought it, downloading it right now 

Maybe we'll get lucky and it will get included in the next update.

Thanks,
## Post #96
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2012-12-22T00:16:48+00:00
- Post Title: Re: ForgeX Beta Released

MichaelDarkAngel,its just a great news!!!  Thanks!
## Post #97
- Username: wdw89
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Apr 07, 2012 4:10 pm
- Post datetime: 2013-02-02T12:23:05+00:00
- Post Title: Re: ForgeX Beta Released

Hello, I can't run ForgeX on Windows 8 x64. ForgeX crashes when I open it. Compatibility mode and run as administrator won't help. Can you fix it? Thank you.
This is the info:
 Application Name:	Forge_X Beta.exe
  Application Version:	2.4.22.0
  Application Timestamp:	4f943ca8
  Fault Module Name:	KERNELBASE.dll
  Fault Module Version:	6.2.9200.16451
  Fault Module Timestamp:	50988aa6
  Exception Code:	e0434f4d
  Exception Offset:	000000000003811c
## Post #98
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-02-02T18:32:55+00:00
- Post Title: Re: ForgeX Beta Released

As stated elsewhere in this topic.

ForgeX Beta will not work on a 64 bit OS.

I have recently upgraded to Win8 64 bit and I am currently working on a version of ForgeX that will work.

Current Status:

File viewing -- check
Image viewing -- check

Model viewing -- this is my current problem.  With the switch to Win8 also came a switch in DirectX.  What I was using in the previous version of ForgeX is not compatible with Win8 so its taking me longer than expected to re-write that portion.

I may shelve the model viewing for a later release and just move on to...

Model exporting -- the next section that I need to make sure works properly.

Once I get that much accomplished I'll have something to release.  But until, rest assured, I am working on it.

Thanks for your interest,

MDA
## Post #99
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-02-03T04:24:19+00:00
- Post Title: Re: ForgeX Beta Released

I'm looking forward to ForgeX on a 64 system. However, I'm looking forward even more to support for AC3. After all, I've got a buddy with an 86 system that gets the models I need
## Post #100
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2013-03-26T01:20:12+00:00
- Post Title: Re: ForgeX Beta Released

Any news? gonna be work on Win7 64bit?
## Post #101
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-03-26T22:49:08+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from ersel54
>
> Any news? gonna be work on Win7 64bit?

I can tell you it definitely works on Win8 64-bit.  I haven't tested on my Win7 laptop yet.  I'm still working on converting all the code for the differences in formats from one game to the next.

Really hoping that they don't change things again when AC:IV gets released.  Would make things a whole lot easier if they left the model formats alone.

Thanks for watching and waiting...

MDA
## Post #102
- Username: MRick33
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 18, 2011 3:19 pm
- Post datetime: 2013-04-01T21:06:55+00:00
- Post Title: Re: ForgeX Beta Released

YEssssssssss, if that work on win8-64, that will probably work on win7-64 no ??? 

really good news, thank for ur job MichaelDarkAngel
## Post #103
- Username: ersel54
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jun 19, 2011 5:01 am
- Post datetime: 2013-05-06T21:32:47+00:00
- Post Title: Re: ForgeX Beta Released

I'm tired of waiting release DAT TOOL  
seriously when do you gonna release this tool give us a date please.
## Post #104
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2013-11-10T17:24:39+00:00
- Post Title: Re: ForgeX Beta Released

A new version of ForgeX has already been released!
Go here: [http://www.tbotr.net/modules.php?mod=Do ... 4&sort=hot](http://www.tbotr.net/modules.php?mod=Downloads&req=viewsubcat&catid=4&subcatid=14&sort=hot)

It's called Archive_X32 or X64, depending on your operating system.

I HAVEN'T DONE NOTHING REGARDING THE TOOL, I'M WRITING HERE ONLY TO LET PEOPLE KNOW ABOUT THE NEW TOOL.
## Post #105
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2013-11-21T16:16:55+00:00
- Post Title: Re: ForgeX Beta Released

That's great! Patiently waiting for an ACIV Update 
Does archive_32/64 support repacking modified data by any chance?
## Post #106
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-11-22T01:48:52+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from eycaramba
>
> Does archive_32/64 support repacking modified data by any chance?

Simply put...

No.  And not likely that it ever will.

Sorry.

Thanks for your interest,

-- MDA
## Post #107
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-11-22T04:44:08+00:00
- Post Title: Re: ForgeX Beta Released

MDA - Thanks for your continued support of ForgeX and related programs. Your efforts are truly appreciated. I hear that you are looking into supporting multiplayer models from AC3. I am very much looking forward to when you are able to complete that. Best of luck to you!
## Post #108
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-11-25T19:36:16+00:00
- Post Title: Re: ForgeX Beta Released

Hey MDA 
Will Archive_32 support AC4? and when?
Thanks in advance
## Post #109
- Username: Helmmmy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-11-25T23:30:29+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from milance941
>
> Hey MDA 
Will Archive_32 support AC4? and when?
Thanks in advance

Yes it will, but in order for that to happen a few other things need to happen first.

I either need to get the game (probably a month or so) or I need to get a sample file from the game.

Regardless of that, the biggest hurdle right now, is getting my dev pc fixed.  I'm having issues getting anything done using my work laptop, it's Win7-64bit.  So doing anything on the 32-bit side is going to have to wait until my PC is fixed. 

Even minor fixes are an issue:

A localization issue has been discovered when using the OBJ exporter in Archive X (of course it has to be the most common exporter), such that when importing into 3DSMax the model looks extremely blocky.  I have been told the issue does not occur when importing into Blender.  I have someone testing a fix for the issue, but not sure how it will affect Blender users.  The person who told me it was happening in 3DSMax but not in Blender is using Archive X32 and I cannot give him a fix for it at the moment.

This appears to be a problem with all games prior to AC:3 as far as models go, but is probably causing problems with the texture maps in AC:3.

[EDIT] Well, I just found out the the replacement exe for some reason only wants to work on my laptop, so any updates will have to wait until my pc is fixed. 

Thanks for your interest,

-- MDA
## Post #110
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-11-26T22:28:36+00:00
- Post Title: Re: ForgeX Beta Released

I will provide you .forge file and you can check it 
I'm a Blender user but I also use Max and I didn't noticed any problem in Blender.
I got some exporting problems when I use Ninja Ripper for extracting models but your program works great so I eagerly wait for that update  If you need any other game file I'll upload it for you 
I will upload DataPC.forge and send you link via PM
## Post #111
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-11-26T23:12:00+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from milance941
>
> I will provide you .forge file and you can check it
That would be great.  I can get a jumpstart and start digging into the format.  I'll be that much further ahead for when I get things up and running again.

> Reply from milance941
>
> I'm a Blender user but I also use Max and I didn't noticed any problem in Blender.
I got some exporting problems when I use Ninja Ripper for extracting models but your program works great so I eagerly wait for that update
You'll only notice the issue if the language settings on your pc are set to use ',' for the decimal symbol.  Archive X will write the OBJ file using the ','.  When importing into 3DSMax, the importer is looking for '.' to be the decimal separator.  Once the import is finished it appears everything after the ',' gets ignored and the model ends up looking like something out of Minecraft, if not worse.

> Reply from milance941
>
> If you need any other game file I'll upload it for you 
I will upload DataPC.forge and send you link via PM
That one file should be enough, thanks.

-- MDA
## Post #112
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-11-26T23:19:04+00:00
- Post Title: Re: ForgeX Beta Released

I sent you link via PM 
Thanks for everything
## Post #113
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2013-11-28T09:03:31+00:00
- Post Title: Re: ForgeX Beta Released

Really, Thanks a lot!

If you need help with AC:IV I'm here too!
## Post #114
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-11-28T17:45:10+00:00
- Post Title: Re: ForgeX Beta Released

Well, they have changed the format slightly again, but the changes were easy enough to figure out.  I'm disappointed though because the DataPC forge doesn't have character models like the previous games have had.  So the best I can show you so far:

Aveline's Machete


Spanish Pistol


It's a start

--MDA
## Post #115
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2013-11-29T04:09:03+00:00
- Post Title: Re: ForgeX Beta Released

Been a while since I checked on this tool, mad thanks and massive props for the continued work and support MichaelDarkAngel
## Post #116
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2013-11-29T10:15:08+00:00
- Post Title: Re: ForgeX Beta Released

> Reply from MichaelDarkAngel
>
> Well, they have changed the format slightly again, but the changes were easy enough to figure out.  I'm disappointed though because the DataPC forge doesn't have character models like the previous games have had.  So the best I can show you so far:

...

It's a start

--MDA

You have been fast!
Do you have already figured what changes have they done to the new .forge format?
## Post #117
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-11-30T23:33:27+00:00
- Post Title: Re: ForgeX Beta Released

While waiting for my dev pc to get repaired I've been digging into the Ghost Recon Online big file.  Prepping for it to be the next game available.

I always attack the textures first, generally they are the easiest.

Thanks to aluigi I was able to figure out the big file format and the internal folder structure.



The above is a sample of the 11000+ folders and 190000+ files contained in the big file.  There are no file type designations to be found (much like AC games), but I think I have found a value that I can use to assume what the files are, plus now that I can see the file structure there are other assumptions that can be made.  The files inside the big container are stored as either uncompressed or zlib compressed.

The above sample listing are in fact image files (assumed they were because they were in a folder named 'Texture'), but they are not all individual files.  Looking at the first three files, this is what I have determined.

GRO-COM01_Body-Camo00_DM
Diffuse Material header file (contains height/width information and I hope DXT value, haven't determined that yet)
GRO-COM01_Body-Camo00_DM_M0
Diffuse Material image data
GRO-COM01_Body-Camo00_DM_MT
Diffuse Material thumbnail (assumed, not yet determined, height/width info possibly stored in the header file as well)

Those files suffixed with 'EM' quite possibly Emissive Material (specular map).
Those files suffixed with 'NM' quite possibly Normal Material.

So far one of the images



It appears that other files are also split this way between a header file and a data file.  That means a bit more work involved in making it easy for someone to pick what they want.

It's only the beginning,

--MDA
## Post #118
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-12-01T18:36:13+00:00
- Post Title: Re: ForgeX Beta Released

Great work so far MDA 
Here's another .forge file.
I think this one contains models.
Here's link [http://www.mediafire.com/download/71b2k ... eanSea.rar](http://www.mediafire.com/download/71b2kicj8vz41i4/DataPC_CaribbeanSea.rar)
## Post #119
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-02T19:26:01+00:00
- Post Title: Re: ForgeX Beta Released

Thanks again milance941.   

This one still doesn't contain any character models, but it does have animals, buildings and other mundane items.

Dolphin


Eagle


Keep plugging away,

-- MDA
## Post #120
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-12-02T20:31:05+00:00
- Post Title: Re: ForgeX Beta Released

MDA - Any updates on AC3 multiplayer support? It seems your tool is the best hope for grabbing any of those models. Thanks again for your time and effort
## Post #121
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-02T20:57:39+00:00
- Post Title: Re: Archive X

Future released updates are pending the repair of my PC.  As anything I do on my laptop for some reason only works on my laptop.

Hopefully sometime this month I'll finish the repairs on my PC and will then be able to release updates.

Thanks for your interest,

-- MDA
## Post #122
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-12-03T23:02:50+00:00
- Post Title: Re: Archive X

Hi MichaelDarkAngel.
First of all, I wanted to thank you for this great tool(s) and the hard work you did and are still doing.
However, I got some issues and I really hope you can help me.

I am using ArchiveX64 on win7 64 bit. The first issue (but not so important) is that I too have some problems previewing the models. I don't get any error message, I just have an empty wiewport.

The second problem, and this is what actually bothers me, is that somehow when I load the models in blender they have different sizes, eg the eyes and other body parts are way bigger than clothes and so on. Is that normal?

I am trying to rip models from Assassin's Creed III. I tried with Ninja Ripper, since I heard it was compatible, but for some reason that tool doesn't really work for me. It looks like your program is the only way to get the files from this game, but it's kinda impossible when the meshes don't actually fit together 

If you need a screen or whatever let me know.
## Post #123
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-04T01:08:47+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> I am using ArchiveX64 on win7 64 bit. The first issue (but not so important) is that I too have some problems previewing the models. I don't get any error message, I just have an empty wiewport.

The 'Model View' page at this time is merely a placeholder.  This was done so you would not have to wait for the 'OBJ View' page to load.  If you only want to export the model you have clicked on, this makes that process less time consuming.  I am working on how to use WPF for viewing of the models and once I have figured that out, the 'Model View' page will become more useful.

> Reply from RunaWhite
>
> The second problem, and this is what actually bothers me, is that somehow when I load the models in blender they have different sizes, eg the eyes and other body parts are way bigger than clothes and so on. Is that normal?

Unfortunately, yes, that is normal.  If there is a scale factor, I have yet to find it.  Also when loading in multiple models, as is necessary for most of the character models, you'll notice that the meshes don't always line up properly.  I have found some model set files.  However, not every model has a corresponding model set file.  Regardless of that, I still haven't figured out all the specifics of the model set file.

> Reply from RunaWhite
>
> It looks like your program is the only way to get the files from this game, but it's kinda impossible when the meshes don't actually fit together

I agree.  It's not the easiest thing to deal with, but it is a minor bit of tweaking.

Thanks for your interest,

-- MDA
## Post #124
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-12-04T01:45:48+00:00
- Post Title: Re: Archive X

I see. Well at least it is indeed common, I was afraid it was just my problem, glad to know it isn't.
Thanks for your answers  maybe somone will create a script which will allow us to automatically resize and fit all the parts, who knows. Yet it's still a nice tool!
## Post #125
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-12-04T16:03:26+00:00
- Post Title: Re: Archive X

Hey MDA 
I think this is the one 
Here's link [http://www.mediafire.com/download/i7dgj ... ra_chr.rar](http://www.mediafire.com/download/i7dgj54sc55a45y/DataPC_extra_chr.rar)
## Post #126
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-04T20:49:28+00:00
- Post Title: Re: Archive X

Yes, it does look like that contains most of the characters, however I think Intro contains some as well.
## Post #127
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-12-04T22:14:24+00:00
- Post Title: Re: Archive X

^ I'll upload that as well 
Thanks for heads up
## Post #128
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-04T22:50:17+00:00
- Post Title: Re: Archive X

Hmm, looking back at it, there's less than I remembered.  It looks like each of the main areas has additional character heads needed for that area.

If there's a list of what .forge files each world needs, I haven't found it yet. Hazarding a guess though, DataPC, DataPC_extra, DataPC_extra_chr, and DataPC_patch are global files, and the others correspond to a world of that name.  However I think in practice the engine loads header information for all forge files, so it can grab any resource at any time.
## Post #129
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-05T02:35:01+00:00
- Post Title: Re: Archive X

Lots of characters in that one milance941 

Edward Kenway (Legend)


Just a taste,

-- MDA
## Post #130
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-05T03:01:49+00:00
- Post Title: Re: Archive X

I've been working on parsing some of the non-graphic files in the archive.  If anyone is interested and can see about getting a tool to view them (or possibly work with MDA on it)  The current ones I'm looking at contain data on how missions behave and such.  Not as interesting as graphics perhaps, but it might tie some of the other resources together.
## Post #131
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-05T03:45:28+00:00
- Post Title: Re: Archive X

Back on Ghost Recon Online for a moment.

Having an issue with the model headers that is holding me back from being able to export the models properly.

Much like the textures, the models are also split into two files.  A header file and a data file.  The header file lets you know how many meshes, how many vertices and faces for each mesh and their starting points in the data indexes.

I have attached two sample files and the structure that I have determined so far looks like this

```
0000      Int32     ID Count
0004      Byte[4]   Unknown ID
0008      Byte      Mesh Count
0009      Int32     Block Count
0013      Byte[4]   Unknown
0017      Int16     Model Type (???)
0019      Int16[2]  Unknown

Start of Mesh Data repeat equal to mesh count

0023      UInt16    Vertex Index
0025      UInt16    Vertex Count
0027      UInt16    Face Index
0029      UInt16    Face Count
```


After that point it gets tricky.  In headers with multiple meshes, I can't determine the number of bytes in between each block of mesh data.

I also know how the header ends, so far that has been the same.  After the last mesh data block there is a single byte (0x20), followed by three UInt16 values (vertex count, face index count and 0), followed by six floats (probably representing the bounding box) and lastly a single byte (0xFF).

If anyone else could help me determine the fluctuating space between mesh data blocks, it would be greatly appreciated.

Thanks,

-- MDA
[GRO_Model_Headers.zip](https://xentaxbackup.github.io/file/6824_GRO_Model_Headers.zip)
## Post #132
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-05T04:53:28+00:00
- Post Title: Re: Archive X

Here you go:

```
UInt16    Vertex Count
UInt16    Face Index
UInt16    Face Count
UInt16    Unknown
UInt16    Unknown
UInt8     (Always 4?)
UInt8     Unknown
UInt8     Count
UInt8[Count] Unknown

```


Edit: The 3rd pair of UInt16's is also an Index/Count pair into something.
The array of bytes also looks like indexes into something. The values never repeat within a group, but frequently repeat from one mesh to another.
## Post #133
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-05T05:24:53+00:00
- Post Title: Re: Archive X

OMG!!!

Never thought to try that as byte values.

And I have also figured out that the two UInt16 values you have marked as unknown are another index, count pair.  Not quite sure what it's for yet.

Thanks again, that was a tremendous help.

-- MDA
## Post #134
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-05T05:33:42+00:00
- Post Title: Re: Archive X

Not a problem at all.  I've been doing this kind of thing for at least 10 years.  Often I have to break out the dissassembler, but this one wasn't that bad.  Going off what you already knew defiinitely made it easier to line up the data though.  My technique for this kind of data is to copy the hex bytes into a text editor, and then break it up into lines.  In this case I used the vertex + count to find the start of the next mesh.
## Post #135
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-12-05T12:15:30+00:00
- Post Title: Re: Archive X

Great 
Can I have Edward in his standard assassins uniform like this one [http://fc03.deviantart.net/fs71/f/2013/ ... 5wxnuf.png](http://fc03.deviantart.net/fs71/f/2013/156/e/8/assassin_s_creed_black_flag___edward_kenway_by_ivances-d5wxnuf.png)
I would also need Anne Bonny [http://s.cghub.com/files/Image/713001-7 ... 15_max.jpg](http://s.cghub.com/files/Image/713001-714000/713345/115_max.jpg)
I want to rig them 
Thanks for all you effort
## Post #136
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2013-12-06T08:33:54+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Lots of characters in that one milance941 

Edward Kenway (Legend)


Just a taste,

-- MDA

I can't wait for the update! Thanks for the work you are doing!
## Post #137
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-12-24T03:03:48+00:00
- Post Title: Re: Archive X

MDA - Any progress on the Ghost Recon Online work? I just remembered that the game had that awesome Ghost Recon/Assassin's Creed crossover armor. I'd be overjoyed to get my hands on it.
## Post #138
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-24T04:10:21+00:00
- Post Title: Re: Archive X

Finally got my PC back and I am finishing up re-installing key software.  So, an update may be coming soon, possibly before the end of the year.

As for GRO, having some issues locating the proper X,Y,Z info.  But I am getting closer and may be able to get that into the next update as well.

Thanks for your support,

-- MDA
## Post #139
- Username: Shockwave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2007 10:59 pm
- Post datetime: 2013-12-26T13:49:01+00:00
- Post Title: Re: Archive X

Hi MichaelDarkAngel! Thanks for all the work you've been doing on AC 4 .forge format extractor. I have a bunch of small questions:
1. Is it possible to extract shaders from a .forge archive and if yes, are they stored in compiled format or raw text?
2. Is it possible to extract scripts from a .forge archive?
3. What is a problem with modifying resources in a .forge format? Does the game perform some type of CRC check or smth?
4. Will you publish .forge format (and other AC 4 related formats which you've managed to process) specs somewhere or you prefer not  to share it?
## Post #140
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-26T19:00:16+00:00
- Post Title: Re: Archive X

> Reply from Shockwave
>
> Hi MichaelDarkAngel! Thanks for all the work you've been doing on AC 4 .forge format extractor. I have a bunch of small questions:
1. Is it possible to extract shaders from a .forge archive and if yes, are they stored in compiled format or raw text?

The shaders do appear to be compiled, but I haven't figured out what to do with them yet.  The next release will allow all files to be exported in one way or another.

> Reply from Shockwave
>
> 2. Is it possible to extract scripts from a .forge archive?

Haven't found scripts yet.  Of course, I also haven't put too much effort into looking for them.

> Reply from Shockwave
>
> 3. What is a problem with modifying resources in a .forge format? Does the game perform some type of CRC check or smth?

Don't know what the problems would be as I have never tried to modify the original resources.  But I will mention that a single resource can be stored in multiple locations.  Not just within a single forge file, but even within multiple forge files.

> Reply from Shockwave
>
> 4. Will you publish .forge format (and other AC 4 related formats which you've managed to process) specs somewhere or you prefer not  to share it?

I keep saying one of these days I'm going to write out the format, but always find something else to do.  I will at some point.

-- MDA
## Post #141
- Username: milance941
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2013-12-29T07:14:08+00:00
- Post Title: Re: Archive X

v1.12.28.0 Now Available

Added support for Assassin's Creed IV: Black Flag. There does appear to be an issue with some of the datafiles. We are looking into it and hope to have it fixed shortly.
Fixed an issue with the obj exporter.
Added an About form.
Due to some brilliant work by Tahg we now have actual descriptions for a good bit of the file type objects. Because of this, "Images" can now be found under "Texture Maps" and "Models" can now be found under "Mesh".

-- MDA
## Post #142
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2013-12-29T11:49:29+00:00
- Post Title: Re: Archive X

MDA thank you very much 
It was worth waiting
## Post #143
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2013-12-30T14:29:58+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> v1.12.28.0 Now Available

Added support for Assassin's Creed IV: Black Flag. There does appear to be an issue with some of the datafiles. We are looking into it and hope to have it fixed shortly.
Fixed an issue with the obj exporter.
Added an About form.
Due to some brilliant work by Tahg we now have actual descriptions for a good bit of the file type objects. Because of this, "Images" can now be found under "Texture Maps" and "Models" can now be found under "Mesh".

-- MDA

Thank you very much for your work!
## Post #144
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2014-01-12T21:42:01+00:00
- Post Title: Re: Archive X

@MDA
I have a problem with UV's when exported from Archive_x32.
That problem only appears on some models like Anne Bony (DataPC_extra_chr)
and it appears only on "head" mesh around eyes and mouth.
On these places UV are in straight line and two in single spot.
Please check that and see if you can fix it 
Thanks in advance
## Post #145
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-12T22:50:49+00:00
- Post Title: Re: Archive X

> Reply from milance941
>
> @MDA
I have a problem with UV's when exported from Archive_x32.
That problem only appears on some models like Anne Bony (DataPC_extra_chr)
and it appears only on "head" mesh around eyes and mouth.
On these places UV are in straight line and two in single spot.
Please check that and see if you can fix it 
Thanks in advance

Can you save the UV maps and send them to me, or at the very least screen shot the offending areas?

Which head model, LOD_1, LOD2, LOD_3 or LOD_4?

Blender, 3DSMax or something else?

Thanks,

-- MDA
## Post #146
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-12T23:09:47+00:00
- Post Title: Re: Archive X

Nevermind, found the issue.

The OBJ exporter is rounding after two digits, for both verts and tverts.  This is leading to less detail all around.

Will get this fixed shortly.

-- MDA
## Post #147
- Username: milance941
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-13T03:23:40+00:00
- Post Title: Re: Archive X

Fixed!

New version up on the website (v2.01.12.0) link is in my sig

This fixes the floating-point precision issue as reported by milance941.  Thanks for the tip.

-- MDA
## Post #148
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2014-01-18T21:04:46+00:00
- Post Title: Re: Archive X

MDA
Thank you very much 
I appreciate your effort
## Post #149
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-18T22:14:47+00:00
- Post Title: Re: Archive X

Assassin's Creed III Liberation HD support Coming Soon!!!

That is all.

-- MDA
## Post #150
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2014-01-20T14:11:32+00:00
- Post Title: Re: Archive X

MDA
I have another problem but now with textures.
A lot of diffuse textures are interpreted like specular (or mask).
Almost every diffuse texture is like that. Normal maps are fine.
Open extra chr.forge and check some textures like hair or some random models.
[](http://s1334.photobucket.com/user/milance941/media/Untitled_zpsc8a08bff.jpg.html)
## Post #151
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-20T16:05:16+00:00
- Post Title: Re: Archive X

It's almost as if they are watermarking the texture files.  They started doing it with AC3.  I haven't been able to figure out a way around it yet.

[EDIT]
And it does not happen with every texture, just a good chunk of them.  If you scroll a little further down to CHR_P_EdwardKenway** you can find those textures are okay.
[/EDIT]



-- MDA
## Post #152
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-20T20:51:51+00:00
- Post Title: Re: Archive X

Now Available v2.01.20.0

This version adds support for Assassin's Creed III: Liberation HD.
This version also fixes an issue with Archive_X32's image viewer not being able to scroll larger images.

-- MDA
## Post #153
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2014-01-21T18:18:05+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> It's almost as if they are watermarking the texture files.  They started doing it with AC3.  I haven't been able to figure out a way around it yet.

[EDIT]
And it does not happen with every texture, just a good chunk of them.  If you scroll a little further down to CHR_P_EdwardKenway** you can find those textures are okay.
[/EDIT]



-- MDA

Majority of models are fine but some have only one copy of their textures and it's oversaturated.
Anyway thank you for checking and for Liberation support
## Post #154
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-21T22:58:29+00:00
- Post Title: Re: Archive X

I tried a few things in Photoshop after extraction, and tried a few different DDS export formats but still no luck.  It may be a DX10 DDS, but I need to read up on that more to figure out exactly how to write the header.

And you'll notice this same issue in some of the Liberation textures as well.

-- MDA
## Post #155
- Username: hammerhorn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 23, 2011 10:31 pm
- Post datetime: 2014-01-25T05:55:22+00:00
- Post Title: Re: Archive X

Hi Michael

Red Normal Maps on Brotherhood...

Do you have any idea how these maps can be corrected? I was trying to extract the elements for one of the Cardinals but I noticed that all the normal maps for these characters have a strange red channel.  If you have any explanations or ideas on how to correct this I would appreciate it tremendously!
## Post #156
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-27T19:51:38+00:00
- Post Title: Re: Archive X

You are the first to mention this.   

This may be a similar situation as what has been occurring with the diffuse maps since AC3.  I can't explain it, nor do I have any course of action to attempt fixing it.  What is being exported are the in-game assets.

Sorry,

-- MDA
## Post #157
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2014-01-31T09:01:03+00:00
- Post Title: Re: Archive X

Would be possible a support for older PoP games? SoT/WW/T2T ?
## Post #158
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-31T13:49:23+00:00
- Post Title: Re: Archive X

> Reply from CMihai
>
> Would be possible a support for older PoP games? SoT/WW/T2T ?

Archive X will be supporting them in the future.

-- MDA
## Post #159
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2014-02-06T09:38:20+00:00
- Post Title: Re: Archive X

Good to hear that
## Post #160
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-03-21T11:28:06+00:00
- Post Title: Re: Archive X

Hi MDA, thank you again for the amazing work you did with this tool and AC models! I have extracted tons of them now 

I have a question though, is there a way to extract multiplayer characters as well? I ask this because I still couldn't figure it out... the format seems the same, but even if I try to copy them into the standard folder, the tool keeps giving me error messages...
## Post #161
- Username: riccochet
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-03-21T17:31:08+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> I have a question though, is there a way to extract multiplayer characters as well?

From which game, and is it a specific DLC?

I know that at least one of the games multi-player content follows the format from an older game.  That issue I had fixed earlier.  I don't have all the DLCs to verify the formats, so there could be an issue with some of them.

However, if you let me know what you're looking at specifically, I'll see what I can do.

Thanks for your support,

-- MDA
## Post #162
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-03-26T14:12:52+00:00
- Post Title: Re: Archive X

Oh yeah sorry. I am talking about MP characters from AC3 and AC4, DLCs are not needed for them I think
## Post #163
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-03-28T01:14:12+00:00
- Post Title: Re: Archive X

AC3 multi-player seems fine, although you will need to piece the model together from multiple files.

AC4 multi-player does have an issue with the forge files not opening correctly.  So that is something that I need to fix.  I will do that at some point next month.

-- MDA
## Post #164
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-03-28T09:59:22+00:00
- Post Title: Re: Archive X

Uhm, how does the extraction work exactly? If I add AC3 path into the Archive, the multiplayer files are not included. If I copy them into the same folder and try to open them, I get errors
## Post #165
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-03-28T22:45:17+00:00
- Post Title: Re: Archive X

AC: Brotherhood, AC: Revelations, ACIII and ACIV: Black Flag should all have a folder named "multi" inside the main install directory.  That is where you will find the multi-player forge files.

Until I can definitively determine another way to figure out what format a given forge file is using that is where the forge files need to be and that is the name of the directory they need to be in.

Hope that helps,

-- MDA
## Post #166
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-03-29T13:01:10+00:00
- Post Title: Re: Archive X

Oh, for some reason the multi folder wasn't opening correctly for me, that's why I thought that maybe there was another way to get them to work. But today, that strange issue seems to be gone   which is a good thing of course.

Thank you MDA!
## Post #167
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2014-07-13T17:00:34+00:00
- Post Title: Re: Archive X

MDA - Do you plan to finish your work on the Ghost Recon Online archives? There have been some updates that look really nice.
## Post #168
- Username: dragbody
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-07-13T20:02:52+00:00
- Post Title: Re: Archive X

> Reply from dragbody
>
> MDA - Do you plan to finish your work on the Ghost Recon Online archives? There have been some updates that look really nice.

I do, but I am stuck with PC issues again and I am in the middle of building another PC.  So it may be a couple of months before I have the new PC finished (buying pieces as I have the money to do so).

Sorry for the delays,

-- MDA
## Post #169
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2014-08-22T07:26:42+00:00
- Post Title: Re: Archive X

Hi MichaelDarkAngel,

thank you for your fantastic tool!

I only have one question, does the model viewer ment to be working? I can export obj, and view hex, but the "Model Viewer" just a blank white page...

Got everything updated (dx, opengl, vc driver)

Thank you
## Post #170
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-08-22T16:33:01+00:00
- Post Title: Re: Archive X

> Reply from Vindis
>
> Hi MichaelDarkAngel,

I only have one question, does the model viewer ment to be working? I can export obj, and view hex, but the "Model Viewer" just a blank white page...

Thank you

Model Viewer is not yet working.  Soon I will be getting back to working on this, as I just finished putting together a new PC and I am currently re-installing all my games.

Thanks for the interest,

-- MDA
## Post #171
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2014-10-07T07:43:46+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> hammerhorn wrote:Hi Michael

Red Normal Maps on Brotherhood...

Do you have any idea how these maps can be corrected? I was trying to extract the elements for one of the Cardinals but I noticed that all the normal maps for these characters have a strange red channel.  If you have any explanations or ideas on how to correct this I would appreciate it tremendously!

You are the first to mention this.   

This may be a similar situation as what has been occurring with the diffuse maps since AC3.  I can't explain it, nor do I have any course of action to attempt fixing it.  What is being exported are the in-game assets.

Sorry,

-- MDA
The problem is that the files are either being read incorrectly for some reason, or for some even crazier, unknown reason, this was done deliberately. There IS, however, a very easy fix for this problem.

1) Export the normal as a TGA. PNG won't work, as we need the Alpha channel to be it's own layer.
2) Open it in Photoshop.
3) Go to Image->Mode->Multichannel.
4) Delete the Magenta Layer, which is an exact copy of the Yellow layer. (BIG SOURCE OF THE PROBLEM RIGHT THERE!!)
5) Move the Cyan layer below the Alpha 1 layer.
6) Now convert it back into a RGB file, and it's all fixed.

MDA- Great program! Got a problem though. When I try to export Shaun Hasting's arms in Brotherhood, (DataPC_ACR_Villa_Present.forge->CR_U_Shaun_Hastings->Mesh->CR_U_Shaun_Hastings_Arms_LOD0) it gives me a "The filename is not valid." error. It does this no matter where I save the file or what I name it as. I can try to name it c:\a.obj, and I will still get that error. The error is identical with the Revelations version too. (Haven't tried it with AC3 yet, and I don't own AC4.)

Finally a request: Can you add FBX export support? It would allow you to add the mesh normals and exporting the skeleton rigs for the models.

Thanks in advance!
## Post #172
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-10-08T04:11:41+00:00
- Post Title: Re: Archive X

> Reply from Kjasi
>
> 

The problem is that the files are either being read incorrectly for some reason, or for some even crazier, unknown reason, this was done deliberately. There IS, however, a very easy fix for this problem.

1) Export the normal as a TGA. PNG won't work, as we need the Alpha channel to be it's own layer.
2) Open it in Photoshop.
3) Go to Image->Mode->Multichannel.
4) Delete the Magenta Layer, which is an exact copy of the Yellow layer. (BIG SOURCE OF THE PROBLEM RIGHT THERE!!)
5) Move the Cyan layer below the Alpha 1 layer.
6) Now convert it back into a RGB file, and it's all fixed.

MDA- Great program! Got a problem though. When I try to export Shaun Hasting's arms in Brotherhood, (DataPC_ACR_Villa_Present.forge->CR_U_Shaun_Hastings->Mesh->CR_U_Shaun_Hastings_Arms_LOD0) it gives me a "The filename is not valid." error. It does this no matter where I save the file or what I name it as. I can try to name it c:\a.obj, and I will still get that error. The error is identical with the Revelations version too. (Haven't tried it with AC3 yet, and I don't own AC4.)

Finally a request: Can you add FBX export support? It would allow you to add the mesh normals and exporting the skeleton rigs for the models.

Thanks in advance!

Thanks for the image fix.

There is an invalid character in the CR_U_Shaun_Hastings_Arms_LOD0 filename right between the "s_" at the "Arms_LOD0" area.  When I get the time to work on this again (probably after Unity comes out, and I get my hands on it), I'll look into fixing that and the possibility of adding FBX export.

I looked briefly but couldn't find the files for Shaun Hastings in AC:Revelations.  I did find them in AC:III (DataPC_DX11_extra_chr.forge->CHR_U_Shaun_Hastings_Body->Mesh->CHR_U_Shaun_Hastings_LOD0) and it appears the body is all contained in one file instead of being split into multiple files.

Thanks for your support,

--MDA
## Post #173
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-10-08T04:27:04+00:00
- Post Title: Re: Archive X

I did find him in Revelations (DataPC_ACFE_FinalTemple.forge->_CC_U_Shaun_Hastings->Mesh->CC_U_Shaun_Hastings_Arms_LOD0), but the file exhibits the same "invalid character in the filename" issue.

--MDA
## Post #174
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2014-10-10T18:20:23+00:00
- Post Title: Re: Archive X

Is there any news with GRO\GR Phantoms?))
## Post #175
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2014-10-13T20:25:48+00:00
- Post Title: Re: Archive X

Hello, can somebody please extract the AC4 dialogue file that contains all the subtitles from the game ? thanks.
## Post #176
- Username: DudE132
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 17, 2014 7:35 am
- Post datetime: 2014-10-16T23:45:07+00:00
- Post Title: Re: Archive X

To the creator, I am willing to donate money for your efforts if you can fulfill my request.

I wish to replace a pre existing outfit with this Unhooded Altair Outfit for permanent use so I can wear it throughout the entire game. 

The Unhooded version of Altairs Outift is only playable in certain sequences of the game. For example "Sequence 01" has you wear this outfit but is is not available for use throughout the rest of the game. Using this tool can you enable that outfit for my character to use permanently by replacing the files of another armor set with the Unhooded Altair Outfit files?

I've found something called "_Ezio_Ultimate_NoHood_NPC" which is in "DataPC_ACR_Villa_Past.forge" and it contains 7 categories

Material
Texture Map
Texture Set
Animation
Build Table
Anim Set
Mesh

This seems to be the correct outfit but I have absolutely zero knowledge and experience with this sort of thing, have no idea what to do, and I'll never figure it out on my own. It should be simple right? Just edit the forge file, and replace the files of one available outfit with the files of the outfit I want? I just have no clue how. 

My OCD is making really want to be able to use this armor so I'm willing donate some money in return for your efforts with the creation of this tool.
## Post #177
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-10-18T00:30:52+00:00
- Post Title: Re: Archive X

Sorry,

I have never attempted to replace anything in any of the forge files and I have no plans to do so.

Thanks for the offer.

--MDA
## Post #178
- Username: DudE132
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 17, 2014 7:35 am
- Post datetime: 2014-10-18T00:36:10+00:00
- Post Title: Re: Archive X

Well regardless do you think it is possible?
## Post #179
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-10-18T01:58:10+00:00
- Post Title: Re: Archive X

Unfortunately, I cannot give you a definitive answer.  Some games use file sizes to determine the validity of the container file, others don't.  Some games use a checksum system.  Any time you attempt to replace something in a game that doesn't give you an upfront option to mod the game, it's a crap-shoot.  At worst, you run the risk of corrupting your game, at best, it works.

What I can tell you, is that I have found multiple instances of files, sometimes within the same forge file, sometimes in multiple forge files.  This could make it that much more difficult to reliably replace something.

But I'll also say that it's not impossible, at least until it is attempted and proven otherwise.

--MDA
## Post #180
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2014-10-20T11:44:48+00:00
- Post Title: Re: Archive X

Hi MDA, 

I'm just asking if there will be an option in a future update to flip all exported textures vertically.
And any word on AC4 Black Flag multiplayer forge support? All seem to just open into nothing or 00000000>Unnamed_0000

Thanks for your work so far
## Post #181
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-10-20T22:02:51+00:00
- Post Title: Re: Archive X

The library I use for images does not support flipping on save for DDS files.  I do flip it inside the program, only because it is more aesthetically pleasing to look at.  However, if you "Export As" another file type, it will save the flipped version.  But, you will not be able to use that with the model file, because it exports the model file expecting to use the flipped DDS texture.

I'll put the Black Flag MP files on my "Look At" list for when I get back into this.  If I remember correctly, the AC3 MP files don't use the same format as the single-player files, so this may be the same case for AC4.

Thanks for your support,

--MDA
## Post #182
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-11-13T10:48:07+00:00
- Post Title: Re: Archive X

Hi!

Will AC Unity be supported as well?

I've seen that the actual version can open the forge files but every time you try to see something inside one of them you'll get an Exception
## Post #183
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-11-13T19:59:47+00:00
- Post Title: Re: Archive X

I thought the format in Unity would change considering the new graphics and all... but if ArchiveX will be able to open and extract the files, well, of course that would be amazing
## Post #184
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-11-14T01:44:03+00:00
- Post Title: Re: Archive X

> Reply from loriscangini
>
> Hi!

Will AC Unity be supported as well?

I've seen that the actual version can open the forge files but every time you try to see something inside one of them you'll get an Exception

> Reply from RunaWhite
>
> I thought the format in Unity would change considering the new graphics and all... but if ArchiveX will be able to open and extract the files, well, of course that would be amazing

Yes the format has changed, but I haven't had the time to look at or do anything about it yet. I've only got a couple hours in playing the game and I want to play a little longer before I start digging into forge file.

So give me about a week or so.

--MDA
## Post #185
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-11-14T13:01:49+00:00
- Post Title: Re: Archive X

Take your time MDA! We appreciate what you did so far and will do. Have fun playing the new AC games for now  

(about Rogue, I suppose you will need the PC files, right? Which will be available in 2015)
## Post #186
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-05T04:16:52+00:00
- Post Title: Re: Archive X

Because the only thing that remains the same is change.

ARchive_neXt Coming Soon!!!

● Support for Assassin's Creed Unity.
● Model Viewing... once again.

● Plus everything you remember from ArchiveX



--MDA
## Post #187
- Username: misterknister
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 20, 2014 7:22 pm
- Post datetime: 2014-12-05T12:27:04+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Because the only thing that remains the same is change.

ARchive_neXt Coming Soon!!!

● Support for Assassin's Creed Unity.
● Model Viewing... once again.

● Plus everything you remember from ArchiveX

--MDA
Thank you very much for the update! Will it be possible, sometime in the future, to edit the archives like Maki did? With this, one could possibly make an economy version of ACU for not-so-good-down-of-the-line-PC's.
## Post #188
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-05T13:37:15+00:00
- Post Title: Re: Archive X

OMG MDA, you're great! Honestly I was afraid that ACU models were not so easy to extract because of the next gen switch, but I can't wait!

One question though, just out of curiosity (and I am sorry if that has been asked already): are the skeleton and vertex groups so hard to get? Not that I mind because I can rig the characters myself, but let's say it would be less time consuming 

Again thank you for your work on ArchiveX!
## Post #189
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-05T22:05:47+00:00
- Post Title: Re: Archive X

> Reply from misterknister
>
> Thank you very much for the update! Will it be possible, sometime in the future, to edit the archives like Maki did? With this, one could possibly make an economy version of ACU for not-so-good-down-of-the-line-PC's.

Wasn't aware that Maki was able to do that, of course, I also never tried.  And even though, from what I've been able to find, it's stated that Maki should be able to replace models and textures, what you are talking about would be a replacement of the game's engine to enable it to run on a lower-end machine.  I don't see that as being possible.


> Reply from RunaWhite
>
> One question though, just out of curiosity (and I am sorry if that has been asked already): are the skeleton and vertex groups so hard to get? Not that I mind because I can rig the characters myself, but let's say it would be less time consuming

I've found bone and weight information for some models.  So in theory, I could skin a model.  The bigger issue is the skeleton, which I have yet to pin down.  I have a couple of prospects, as in file types I need to look into further.

Thanks for your support,

--MDA
## Post #190
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2014-12-06T16:01:54+00:00
- Post Title: Re: Archive X

Very cool! Thx!
And will it support another Ubisoft games? Watchdogs, GRFS:Phantoms?
## Post #191
- Username: misterknister
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 20, 2014 7:22 pm
- Post datetime: 2014-12-06T16:18:53+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> 
Wasn't aware that Maki was able to do that, of course, I also never tried.  And even though, from what I've been able to find, it's stated that Maki should be able to replace models and textures, what you are talking about would be a replacement of the game's engine to enable it to run on a lower-end machine.  I don't see that as being possible.
I thought of reducing the amount of polygons or, if sometime level editing is accessible, removing objects from the map.

> Reply from stVALVe
>
> Very cool! Thx!
And will it support another Ubisoft games? Watchdogs, GRFS:Phantoms?
Watch Dogs has already a working unpacker and uses a different engine, so I guess not, they're available in this forum: [viewtopic.php?f=16&t=11602&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=11602&start=15) [viewtopic.php?f=10&t=11534](http://forum.xentax.com/viewtopic.php?f=10&t=11534) etc.
## Post #192
- Username: stVALVe
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-06T20:11:40+00:00
- Post Title: Re: Archive X

> Reply from stVALVe
>
> Very cool! Thx!
And will it support another Ubisoft games? Watchdogs, GRFS:Phantoms?

I don't own Watchdogs, yet.  Even if I do get it, I probably will not do anything for it seeing as how someone else is already working on it.  Can't find much on GRFS:Phantoms, other than it's a Steam title.  However, if it's anything like Ghost Recon Phantoms (formerly Ghost Recon Online), it's unlikely I'll be doing anything with that.  I didn't like the way GRO split the assets, too complicated.  For the time being, ARchive_neXt will stick to the games using forge files.  In the future it may expand to other games.

--MDA
## Post #193
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-09T05:05:15+00:00
- Post Title: Re: Archive X

First Unity model

Nothing special.  Still working on the format.  This is the first one when I thought there were only slight changes from the Black Flag format.  Other models have shown there were more significant changes I needed to make.  Also I have found two other model formats, and a disturbing gap of repetitive face index information that screws up some of the models.
Pretty bad in some cases


Stay tuned...

--MDA
## Post #194
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-12T10:13:17+00:00
- Post Title: Re: Archive X

Keep up the awesome work, MDA
## Post #195
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-13T20:26:05+00:00
- Post Title: Re: Archive X

Figured out my display issue is caused by the DirectX model file that I create for viewing not a face index issue.  But once imported into 3DSMax the model looks fine, provided you "Export As" OBJ or ARX.  The X format has an issue with some of the multi-mesh AC:Unity models that does not appear in the previous games.



This is the screwed up model from above exported using my ARX format and imported into 3DSMax.  I will be releasing an ARX Importer for 3DSMax once I release ARchive_neXt.

--MDA
## Post #196
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-12-20T08:13:01+00:00
- Post Title: Re: Archive X

Very good work! Now what's left do do?

Also, if with your actual version is possible to extract some of the Unity models, can you release it, maybe something like a Beta version, anyway, thanks for what are you doing!
## Post #197
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-20T17:57:33+00:00
- Post Title: Re: Archive X

Putting the final touches on the first release now, need to test it on the couple machines I can.  Should have some thing ready by Sunday at the latest.

Figured out one of the problems with some of the Unity models was due to multiple meshes and the X file I was using.  However, the duplicate face indices problem still remains for some models.  So far the only place I have seen that problem has been a some NPC inventory items.

Got some other things that I would love to figure out to make this a little better (like better camera positioning and controls, proper progress reporting), but the program is useable at it stands right now.

So look for something soon.

--MDA
## Post #198
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-20T21:32:53+00:00
- Post Title: Re: Archive X

Sounds great! Thank you so much, MDA!
## Post #199
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-21T11:53:56+00:00
- Post Title: Re: Archive X

Hey MDA well is it possible to export the animations, well if you can add animation exporting system it would be really awesome and appriciated
## Post #200
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T06:51:42+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> What is Archive X?

The next evolution of ForgeX.  Built to work on Win7 and Win8 both 32-bit and 64-bit.

Why the name change?

When completed, Archive X will cover some 20 games with the possibility of adding more.

Will Assassin's Creed III and Assassin's Creed IV: Black Flag be supported?

Yes, currently AC3 is already supported and work has begun to add support for AC4.

---

Well, it started out a long time as Assassin's Creed Explorer. It has since expanded into ForgeX. A visual way of exploring Ubisoft .forge files from games such as Assassin's Creed, Assassin's Creed II, Assassin's Creed:Brotherhood, Assassin's Creed: Revelations, Assassin's Creed III, Assassin's Creed IV: Black Flag, Prince of Persia (2008) and Prince of Persia: The Forgotten Sands.

At this time you can view and export the DDS images/textures from all the games.  A later version will allow for the export in a variety of image file formats.  You can view the specifics of the model files and export either as an .arx file (used for importing into 3DSMax/gMax with an upcoming version NWMax Plus) or the common OBJ file format.  This will also allow you to view the specifics of a few other files contained in the forge files.  As I am able to decipher more, more will be added.

Archive X does not allow you to alter any of the .forge files.

Requirements:
.NET Framework 4.5
One of the above mentioned games must be installed on your system.

You can get Archive X from the Downloads area.

-- MDAHello, my friends, thank you for your great work. I use max2012, max2015 tests the nwmax_plus_v5_06_01 script, and try to import the Arx formats, but an error occurred. I don't know what I did wrong, please help, thank you. Here is a sample file chr_a_pig: [https://onedrive.live.com/redir?resid=6 ... file%2crar](https://onedrive.live.com/redir?resid=6A28B826BE5F1236!167&authkey=!AI1ACwX0kBFe1Qg&ithint=file%2Crar)
[BaiduShurufa_2014-12-22_14-45-28.png](https://xentaxbackup.github.io/file/8334_BaiduShurufa_2014-12-22_14-45-28.png)
## Post #201
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T07:57:03+00:00
- Post Title: Re: Archive X

> Reply from raykingnihong
>
> Hello, my friends, thank you for your great work. I use max2012, max2015 tests the nwmax_plus_v5_06_01 script, and try to import the Arx formats, but an error occurred. I don't know what I did wrong, please help, thank you.

That is an unfortunate error that I never did fix in nwMax_Plus.  It will happen the first time you try loading an arx file.

A Quick Fix:

Close the error window, close the code window, close the nwMax_Plus rollout.  DO NOT CLOSE 3DSMAX!!!

Click on MaxScript in the menubar at the top.  Select Run Script from the dropdown menu.  Browse to the Scripts/Startup directory.  Select autonwmax.ms, press the Open button.

This will restart nwMax_Plus and you should now be able to import your arx files.  I call this an unfortunate error because, unfortunately, you will have to do this every time you start 3DSMax.

A Better Fix:
Give me another hour or so, I'll be releasing a new version of the forge file explorer along with a stand-alone ARX importer for 3DSMax that does not have this problem.

Thanks for your patience,

--MDA
## Post #202
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T08:02:43+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> raykingnihong wrote:Hello, my friends, thank you for your great work. I use max2012, max2015 tests the nwmax_plus_v5_06_01 script, and try to import the Arx formats, but an error occurred. I don't know what I did wrong, please help, thank you.

That is an unfortunate error that I never did fix in nwMax_Plus.  It will happen the first time you try loading an arx file.

A Quick Fix:

Close the error window, close the code window, close the nwMax_Plus rollout.  DO NOT CLOSE 3DSMAX!!!

Click on MaxScript in the menubar at the top.  Select Run Script from the dropdown menu.  Browse to the Scripts/Startup directory.  Select autonwmax.ms, press the Open button.

This will restart nwMax_Plus and you should now be able to import your arx files.  I call this an unfortunate error because, unfortunately, you will have to do this every time you start 3DSMax.

A Better Fix:
Give me another hour or so, I'll be releasing a new version of the forge file explorer along with a stand-alone ARX importer for 3DSMax that does not have this problem.

Thanks for your patience,

--MDAThank you very much for your reply, your work is great
## Post #203
- Username: nav00811
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T09:07:00+00:00
- Post Title: Re: Archive X

Well, this will make some people happy, others unhappy.

ARchive_neXt v1.11.16.0 is now available [here](http://www.tbotr.net/Downloads/ARchive_neXt.exe), but it seems like it only wants to work on 64-bit versions.

You will need to download and install the [DirectX June 2010 Redistributable Runtime](http://www.microsoft.com/en-us/download/details.aspx?id=8109), make sure your system has all the current updates, mainly .NET Framework 4.5.

I have a demo video [here](http://www.tbotr.net/videos/ARchive_neXt_005.mp4) that details the camera controls for viewing models.

For those looking for a stand-alone ARX importer for 3DSMax, you can find that [here](http://www.tbotr.net/Downloads/arxImporter_v1_06_17.zip).  Extract and copy the files to your [3DSMax Install] directory.

Hopefully soon I will be able to figure out why it's not working on 32-bit versions.

Thanks,

--MDA
## Post #204
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T11:35:42+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Well, this will make some people happy, others unhappy.

ARchive_neXt v1.11.16.0 is now available here, but it seems like it only wants to work on 64-bit versions.

You will need to download and install the DirectX June 2010 Redistributable Runtime, make sure your system has all the current updates, mainly .NET Framework 4.5.

I have a demo video here that details the camera controls for viewing models.

For those looking for a stand-alone ARX importer for 3DSMax, you can find that here.  Extract and copy the files to your [3DSMax Install] directory.

Hopefully soon I will be able to figure out why it's not working on 32-bit versions.

Thanks,

--MDAHi Michael DarkAngel, thank you for your great work, I tested the AC IV black flag games, 3DSMax script works very well, I am running arximp.Ms directly. I also tested a archive_next tool, may not yet be fully support AC IV black flag error occurred some models do not display correctly, but can browse directly to the model, it was very good. Once again thank you very much Michael DarkAngel's great work
[BaiduShurufa_2014-12-22_19-37-39.png](https://xentaxbackup.github.io/file/8342_BaiduShurufa_2014-12-22_19-37-39.png)
## Post #205
- Username: StrunPS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 7:54 pm
- Post datetime: 2014-12-22T11:52:40+00:00
- Post Title: Re: Archive X

need help
## Post #206
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T12:18:09+00:00
- Post Title: Re: Archive X

> Reply from StrunPS
>
> need help

Let me know what model, and I'll see if I can help?

--MDA
## Post #207
- Username: StrunPS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 7:54 pm
- Post datetime: 2014-12-22T12:26:51+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> StrunPS wrote:need help

Let me know what model, and I'll see if I can help?

--MDA

any, even the one that is shown on the video
## Post #208
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-22T13:30:58+00:00
- Post Title: Re: Archive X

Thank you MDA!!!! I will test it later on my 64 bit laptop and let you know how it goes
## Post #209
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-12-22T13:57:30+00:00
- Post Title: Re: Archive X

The program works, but there are some problems, first of all I can't say any model, the only thing that pops up is the error message said by StrunPS.
The good thing is that if you ignore the exception and try to export the meshes to arx, it works.

I'll let you know if I find something else.

Let me know If I can do something more!
## Post #210
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-22T14:18:31+00:00
- Post Title: Re: Archive X

For me it's not working at all. The exception error appears right when I try to open the program, the 'Loading Preferences' bar in the lower part stays stuck there and the same message appears if I add the Unity path. Same if I have to close it, I can only force it via the Task Manager.

So, basically I can't view anything, not even the list of files. I have installed the directX update you linked and I have .NET Framework 4.5. Do I need to install/update something else in order to make it work?
[Senza titolo-1.jpg](https://xentaxbackup.github.io/file/8344_Senza titolo-1.jpg)
## Post #211
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T14:43:10+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> For me it's not working at all. The exception error appears right when I try to open the program, the 'Loading Preferences' bar in the lower part stays stuck there and the same message appears if I add the Unity path. Same if I have to close it, I can only force it via the Task Manager.

So, basically I can't view anything, not even the list of files. I have installed the directX update you linked and I have .NET Framework 4.5. Do I need to install/update something else in order to make it work?Hello, my friends, I also encountered the same problem at the start, but, as long as you opened the program in case of error, then back to the right path. Wait and can be used normally. But not all models are supported, some models could not be read error occurred.
## Post #212
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-22T14:55:09+00:00
- Post Title: Re: Archive X

> Reply from raykingnihong
>
> Hello, my friends, I also encountered the same problem at the start, but, as long as you opened the program in case of error, then back to the right path. Wait and can be used normally. But not all models are supported, some models could not be read error occurred.

Not sure what you mean, but it's really not working. Maybe it's because I have to update the .NET Framework from 4.5 to the newest 4.5.2? Gonna try and let you guys know.
## Post #213
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T15:07:42+00:00
- Post Title: Re: Archive X

When I experienced that DirectX error while testing, it had been caused by something wrong with the model file (see one of my previous posts for details). But I have only had that issue with some of the Unity models.  So that leaves me asking questions and guessing. 

You are using a 64-bit version of Windows? (I assume so, but still have to ask.)
You have installed all recent updates for your OS?
You have installed the DirectX runtime? (Again I assume so, that would not be the error if you had not.)
You are working with forge files from the PC version of the game? (Once again, I assume that to be the case. If not, I don't think they would import into 3DSMax properly.  Not to mention, I don't think you would get as far as you have.)

So that leaves me out of questions for now.  And there isn't much else I can do until I get home this evening.  

--MDA
## Post #214
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T15:20:45+00:00
- Post Title: Re: Archive X

Runa, I believe your issue is being caused by something I forgot to plan for. That is, the program not finding any games in the registry files. 
However, you should be able to close the program normally. Restart the program, then open Options/Preferences and browse to the directories where the forge files are located. 

--MDA
## Post #215
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-22T15:27:17+00:00
- Post Title: Re: Archive X

MDA, I'm having trouble with some of the models... the polygon of the meshes get disturbed
[http://www.mediafire.com/view/5f4qiuo4j ... apture.PNG](http://www.mediafire.com/view/5f4qiuo4ji44lo4/Capture.PNG)
## Post #216
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T15:53:20+00:00
- Post Title: Re: Archive X

> Reply from nav00811
>
> MDA, I'm having trouble with some of the models... the polygon of the meshes get disturbed
http://www.mediafire.com/view/5f4qiuo4j ... apture.PNG

Can you send me the exported file (tbotr at tbotr dot net). I will look at it when I get home this evening. 

--MDA
## Post #217
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T17:53:29+00:00
- Post Title: Re: Archive X

Nav-  I got your files. I will look at them later, I don't have access to 3DSMax at the moment. 

Runa- After looking at your issue again, you may need to set the ARchive_neXt.exe to run as administrator.  Now that I have looked at the picture a second time, the program appears to be crashing when it tries to create the temp directory.  I apologize for not looking at it closer earlier. 

--MDA
## Post #218
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-22T18:37:53+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Nav-  I got your files. I will look at them later, I don't have access to 3DSMax at the moment. 

Runa- After looking at your issue again, you may need to set the ARchive_neXt.exe to run as administrator.  Now that I have looked at the picture a second time, the program appears to be crashing when it tries to create the temp directory.  I apologize for not looking at it closer earlier. 

--MDA

That is weird then... I tried running it as Administrator, and I got the same issue  also, I can't close it manually. When I try I get the exception error and the program stays open. I need to force it... I am trying to update the .NET Framework, though I don't know if that will work...

EDIT: Nope. Not working. This is what happenes exactly:

1) When I open the tool I get that error message I posted in the previous page
2) The program loads anyway and this is what happens [http://i.imgur.com/hA9ImLz.jpg](http://i.imgur.com/hA9ImLz.jpg) loading preferences stuck and all empty
3) This is the error I get when I try to add Unity's path [http://i.imgur.com/wQkhXSr.jpg](http://i.imgur.com/wQkhXSr.jpg)
4) This is the error I get when I try to close it (without any luck) [http://i.imgur.com/n2Iob1M.jpg](http://i.imgur.com/n2Iob1M.jpg)

I am using Windows 7 with 64 bit system, DirectX is updated because I installed the one you linked, I have .NET Framework now updated to 4.5.2 version, everything else seems to be updated, running as Administrator doesn't change anything. Do I need to freak out?
## Post #219
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T19:50:15+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Nav-  I got your files. I will look at them later, I don't have access to 3DSMax at the moment. 

Runa- After looking at your issue again, you may need to set the ARchive_neXt.exe to run as administrator.  Now that I have looked at the picture a second time, the program appears to be crashing when it tries to create the temp directory.  I apologize for not looking at it closer earlier. 

--MDAHI MichaelDarkAngel ，My good friend, I use ARchive_neXt.exe to test Assassins.Creed.Liberation.HD errors, caching textures cannot be extracted to the specified folder.
[BaiduShurufa_2014-12-23_3-52-41.png](https://xentaxbackup.github.io/file/8349_BaiduShurufa_2014-12-23_3-52-41.png)
## Post #220
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T19:58:31+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> MichaelDarkAngel wrote:Nav-  I got your files. I will look at them later, I don't have access to 3DSMax at the moment. 

Runa- After looking at your issue again, you may need to set the ARchive_neXt.exe to run as administrator.  Now that I have looked at the picture a second time, the program appears to be crashing when it tries to create the temp directory.  I apologize for not looking at it closer earlier. 

--MDA

That is weird then... I tried running it as Administrator, and I got the same issue  also, I can't close it manually. When I try I get the exception error and the program stays open. I need to force it... I am trying to update the .NET Framework, though I don't know if that will work...

EDIT: Nope. Not working. This is what happenes exactly:

1) When I open the tool I get that error message I posted in the previous page
2) The program loads anyway and this is what happens http://i.imgur.com/hA9ImLz.jpg loading preferences stuck and all empty
3) This is the error I get when I try to add Unity's path http://i.imgur.com/wQkhXSr.jpg
4) This is the error I get when I try to close it (without any luck) http://i.imgur.com/n2Iob1M.jpg

I am using Windows 7 with 64 bit system, DirectX is updated because I installed the one you linked, I have .NET Framework now updated to 4.5.2 version, everything else seems to be updated, running as Administrator doesn't change anything. Do I need to freak out?Hello, my friend, as you are, my system configuration. Do you have to set the correct path
[BaiduShurufa_2014-12-23_3-58-6.png](https://xentaxbackup.github.io/file/8350_BaiduShurufa_2014-12-23_3-58-6.png)
## Post #221
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-22T19:59:57+00:00
- Post Title: Re: Archive X

> Reply from raykingnihong
>
> RunaWhite wrote:MichaelDarkAngel wrote:Nav-  I got your files. I will look at them later, I don't have access to 3DSMax at the moment. 

Runa- After looking at your issue again, you may need to set the ARchive_neXt.exe to run as administrator.  Now that I have looked at the picture a second time, the program appears to be crashing when it tries to create the temp directory.  I apologize for not looking at it closer earlier. 

--MDA

That is weird then... I tried running it as Administrator, and I got the same issue  also, I can't close it manually. When I try I get the exception error and the program stays open. I need to force it... I am trying to update the .NET Framework, though I don't know if that will work...

EDIT: Nope. Not working. This is what happenes exactly:

1) When I open the tool I get that error message I posted in the previous page
2) The program loads anyway and this is what happens http://i.imgur.com/hA9ImLz.jpg loading preferences stuck and all empty
3) This is the error I get when I try to add Unity's path http://i.imgur.com/wQkhXSr.jpg
4) This is the error I get when I try to close it (without any luck) http://i.imgur.com/n2Iob1M.jpg

I am using Windows 7 with 64 bit system, DirectX is updated because I installed the one you linked, I have .NET Framework now updated to 4.5.2 version, everything else seems to be updated, running as Administrator doesn't change anything. Do I need to freak out?  Hello, my friend, as you are, my system configuration. Do you have to set the correct path
[BaiduShurufa_2014-12-23_3-59-19.png](https://xentaxbackup.github.io/file/8351_BaiduShurufa_2014-12-23_3-59-19.png)
## Post #222
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-22T20:31:20+00:00
- Post Title: Re: Archive X

Thank you raykingnihong! That fixed the issue, my bad!!

Btw I am testing the program now and so far the issues I'm finding are:

1) I too get that same error message about previews and thus I can't see the meshes into the model viewer
2) I can't extract textures for some reason. Sometimes they extract automatically in DDS, but only the diffuses. If I try to manually export in other formats, I get another error message which says the maps cannot be found (but it seems to work if I click on 'Export All As')
3) Normal maps appear damaged
## Post #223
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-22T20:33:40+00:00
- Post Title: Re: Archive X

Ray - Thank you for that great tip. That might allow Runa to run the program. But more importantly, it means I have to account for an issue where the program may not be able to write the temp directory and preferences file where it wants to. 

Nav - I looked at your obj file, and I don't need 3DSMax to tell you that is one of models that has the duplicate face index issue. I'm still trying to figure out how I can get around that problem. 

--MDA
## Post #224
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-22T20:45:18+00:00
- Post Title: Re: Archive X

Well MDA how long can it take to fix that issue, please let me know if u have any idea about how long it can take cause i'll be waiting for that issue to be fixed...
## Post #225
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-22T21:30:46+00:00
- Post Title: Re: Archive X

MDA, this happens with all the normal maps I am exporting. I think this issue also appeared in ArchiveX, but I'm not sure. The green ones look fine though, this issue appears only with the standard blue normals.
[CN_S_Kid_arms_NormalMap.png](https://xentaxbackup.github.io/file/8352_CN_S_Kid_arms_NormalMap.png)
## Post #226
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-23T00:25:51+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> Thank you raykingnihong! That fixed the issue, my bad!!

Btw I am testing the program now and so far the issues I'm finding are:

1) I too get that same error message about previews and thus I can't see the meshes into the model viewer

And this is happening to you with all model files also?

> Reply from RunaWhite
>
> 2) I can't extract textures for some reason. Sometimes they extract automatically in DDS, but only the diffuses. If I try to manually export in other formats, I get another error message which says the maps cannot be found (but it seems to work if I click on 'Export All As')

By extract, do you mean along with a model file?  If so, I'll explain how that works.  There is a certain chain that I need to follow, in order to find the textures a model uses.
1. Find the Texture Set(s) referenced in the Mesh file.
2. Find the Material(s) referenced in the Texture Set(s).
3. Find the Texture Map(s) reference in the Material(s).

If any of those are missing from the Datafile the Mesh is located in you will not get exported textures, nor will you see textures in the model viewer.

I only decompress the Datafile when it is opened (if some people think it takes long for certain datafiles to open now, imagine waiting for close to a thousand of them to decompress before you could do anything   ).  But as a semi-workaround, if the program can not find a piece to the puzzle it needs in the datafile it starts in, it will look through all datafiles in the forge file.  If you happen to have already opened a datafile that has the piece, it will find it and use that.  If you watch the video I posted, you'll see I open the "CN_C_FR_Student_Scholar_M_DiffuseMap" datafile prior to opening the "CN_C_FR_Mid_M" datafile.  I did that so the model I was using would have textures.  Sorry if that hadn't been made clear before, but that is the way every version has worked, from ForgeX until now.

> Reply from RunaWhite
>
> 3) Normal maps appear damaged.
MDA, this happens with all the normal maps I am exporting. I think this issue also appeared in ArchiveX, but I'm not sure. The green ones look fine though, this issue appears only with the standard blue normals.

The issue with ArchiveX was a red/purple tint to a lot of the diffuse maps starting with ACIII if I remember correctly.  This is something new.  I have tried a few different DDS formats with no luck.  Much like trying to find that elusive trigger that will tell me how to read around the blocks of duplicate face indices, I need to find one for these normal maps as well.

Can you view any of the texture maps in the program?

--MDA
## Post #227
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-23T00:38:36+00:00
- Post Title: Re: Archive X

> Reply from raykingnihong
>
> HI MichaelDarkAngel ，My good friend, I use ARchive_neXt.exe to test Assassins.Creed.Liberation.HD errors, caching textures cannot be extracted to the specified folder.

I would be interested in seeing a screen shot of the full error window you are receiving with the textures you are having an issue with.  Based on what I can see it looks as though a slash (/) is missing from in between the name of the directory and the name of the texture.

[EDIT]
That is exactly what the problem is. Something else for me to fix.

Thanks for all the bug-squashing

--MDA
## Post #228
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-23T06:28:23+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> raykingnihong wrote:HI MichaelDarkAngel ，My good friend, I use ARchive_neXt.exe to test Assassins.Creed.Liberation.HD errors, caching textures cannot be extracted to the specified folder.

I would be interested in seeing a screen shot of the full error window you are receiving with the textures you are having an issue with.  Based on what I can see it looks as though a slash (/) is missing from in between the name of the directory and the name of the texture.

[EDIT]
That is exactly what the problem is. Something else for me to fix.

Thanks for all the bug-squashing

--MDAHI MichaelDarkAngel, you are right, it is incomplete led to a path, maps have been declassified in the cache directory. This is not an issue, is my path \, remind Everyone that we set the path must be a full path, Thank you very much for your help, my friend. we hope that through our strengths to help you test this great tool, it saves you on the timing. Today, I will continue to test this tool.
[BaiduShurufa_2014-12-23_14-50-32.png](https://xentaxbackup.github.io/file/8355_BaiduShurufa_2014-12-23_14-50-32.png)
## Post #229
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-23T07:07:10+00:00
- Post Title: Re: Archive X

Hi MichaelDarkAngel，I tested the Prince.of.Persia.The.Forgotten.Sands error.
[BaiduShurufa_2014-12-23_15-3-28.png](https://xentaxbackup.github.io/file/8356_BaiduShurufa_2014-12-23_15-3-28.png)
## Post #230
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-23T08:36:13+00:00
- Post Title: Re: Archive X

> Reply from raykingnihong
>
> Hi MichaelDarkAngel，I tested the Prince.of.Persia.The.Forgotten.Sands error.
[BaiduShurufa_2014-12-23_16-34-48.png](https://xentaxbackup.github.io/file/8357_BaiduShurufa_2014-12-23_16-34-48.png)
## Post #231
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-23T10:10:52+00:00
- Post Title: Re: Archive X

> And this is happening to you with all model files also?

Yes, all the models.

> By extract, do you mean along with a model file?  If so, I'll explain how that works.  There is a certain chain that I need to follow, in order to find the textures a model uses.
>
> 1. Find the Texture Set(s) referenced in the Mesh file.
>
> 2. Find the Material(s) referenced in the Texture Set(s).
>
> 3. Find the Texture Map(s) reference in the Material(s).
>
> 
>
> If any of those are missing from the Datafile the Mesh is located in you will not get exported textures, nor will you see textures in the model viewer.[
>
> 
>
> I only decompress the Datafile when it is opened (if some people think it takes long for certain datafiles to open now, imagine waiting for close to a thousand of them to decompress before you could do anything   ).  But as a semi-workaround, if the program can not find a piece to the puzzle it needs in the datafile it starts in, it will look through all datafiles in the forge file.  If you happen to have already opened a datafile that has the piece, it will find it and use that.  If you watch the video I posted, you'll see I open the "CN_C_FR_Student_Scholar_M_DiffuseMap" datafile prior to opening the "CN_C_FR_Mid_M" datafile.  I did that so the model I was using would have textures.  Sorry if that hadn't been made clear before, but that is the way every version has worked, from ForgeX until now.

Uhm, for some reason I could never preview the models in ForgeX nor ArchiveX. Certain diffuse textures were exported together with the models, but not always (sometimes the material file said the map could not be found) and not the secondary textures like normals and speculars. However, this is not a big deal... because I always pick the textures I need saving them in .png format (which is easier to use especially when they have an alpha channel).

The problem I was talking about is related to the single extraction; if I pick let's say only the diffise and try to export it manually in .png (or any other format) I get the error that says the texture can't be found. But, here again, not a big deal at all because it seems that with 'Export All As' it works 

> The issue with ArchiveX was a red/purple tint to a lot of the diffuse maps starting with ACIII if I remember correctly.  This is something new.  I have tried a few different DDS formats with no luck.  Much like trying to find that elusive trigger that will tell me how to read around the blocks of duplicate face indices, I need to find one for these normal maps as well.
>
> 
>
> Can you view any of the texture maps in the program?

The problem appears in every model, every standard blue normal map has that issue for me. Some models use a green one, which looks fine, without squares and all.
And yes, I can see all the textures.

Also, I have a question: I noticed there are some HD meshes included in the files... but are they extractable? If yes, how? Because the only export option available is 'Export Raw' and I can't save them in .obj like I do with the standard meshes.

Btw thank you very much for all the work you're doing on this tool!
## Post #232
- Username: nav00811
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-23T16:03:27+00:00
- Post Title: Re: Archive X

Ray - Your last two errors might be caused by adding that slash at the end of your Temp File Location. Yes, that will solve the image export issue, but it breaks everything else.

Runa - The image export issue, my fault, missed a slash (/) in the code.  Also found another issue with image export that I need to fix. 
The HD Mesh is going to be changed to Hair Mesh. Because that's what they are. 

Possibly tonight, I will have an update. 

--MDA
## Post #233
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-23T16:56:49+00:00
- Post Title: Re: Archive X

Awesome MDA im really waiting for that update
## Post #234
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-23T18:32:31+00:00
- Post Title: Re: Archive X

Awesome, thank you!
## Post #235
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-24T18:59:42+00:00
- Post Title: Re: Archive X

Updated - [ARchive_neXt](http://www.tbotr.net/Downloads/ARchive_neXt.exe) - for now version remains the same v1.11.16.0

Tested and working on Windows 7 Professional 32-bit, Windows 8.1 Professional 64-bit.
One thing I have noticed with Windows 7.  If you install the program into the root directory, you will be required to run the program as administrator (right-click on ARchive_neXt.exe, select Properties->Compatibility, check "Run this program as an administrator" under "Privilege Level").  While testing, if I did not do that it would not save my preferences file.  I did not see this same behavior in Windows 8.1.

Changes:
Temp directory and preferences file have been moved to a folder in your "My Documents" (Win7/8), "Documents" (Win8.1) folder.
Fixed the missing slash(/) that was causing image export issues.
Fixed another image export issue that would cause images to be exported without a file extension.
Fixed HD Mesh missing export options.  Forgot to change it to Hair Mesh.
Added "Export Raw Data" option to Models and Images.

To Do:
Still need to figure out duplicate face index issue.
Still need to figure out normal map issue.
Prince of Persia: The Forgotten Sands has some issues.

A host of other things I haven't even started on yet because getting the models and textures right has always been a top priority.

Happy Holidays to those who celebrate,

--MDA

I will not be able to continue working on this until Friday evening at the earliest.
## Post #236
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-25T18:15:52+00:00
- Post Title: Re: Archive X

MDA after Friday please first of all can you figure out duplicate face index issue and fix it...
## Post #237
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-26T07:28:07+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Updated - ARchive_neXt - for now version remains the same v1.11.16.0

Tested and working on Windows 7 Professional 32-bit, Windows 8.1 Professional 64-bit.
One thing I have noticed with Windows 7.  If you install the program into the root directory, you will be required to run the program as administrator (right-click on ARchive_neXt.exe, select Properties->Compatibility, check "Run this program as an administrator" under "Privilege Level").  While testing, if I did not do that it would not save my preferences file.  I did not see this same behavior in Windows 8.1.

Changes:
Temp directory and preferences file have been moved to a folder in your "My Documents" (Win7/8), "Documents" (Win8.1) folder.
Fixed the missing slash(/) that was causing image export issues.
Fixed another image export issue that would cause images to be exported without a file extension.
Fixed HD Mesh missing export options.  Forgot to change it to Hair Mesh.
Added "Export Raw Data" option to Models and Images.

To Do:
Still need to figure out duplicate face index issue.
Still need to figure out normal map issue.
Prince of Persia: The Forgotten Sands has some issues.

A host of other things I haven't even started on yet because getting the models and textures right has always been a top priority.

Happy Holidays to those who celebrate,

--MDA

I will not be able to continue working on this until Friday evening at the earliest.Hi MichaelDarkAngel, thank you for your great work, the tool works very well, if you can join the bones data read, once again thank you very much
## Post #238
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-26T10:27:47+00:00
- Post Title: Re: Archive X

Thank you again MDA! I tested the tool and works fine. I am not getting the exception error anymore when I load it, textures export fine, same as HD meshes. I still have the preview issue, I can't see any of the models and that would be useful also to see if all the needed textures are there. Btw take your time fixing the normals and all  

EDIT: I have a question not really related to the tool itself (unless it really depends on that), but more about the models:

I usually export in OBJ format and I noticed that the hair (both standard LOD0 and HQ) appears as outlined 'strands'. The mesh looks invisible once loaded and I was wondering if there is a way to 'fill' it correctly?

Probably it depends on the way they worked on their next gen models? Since we never had this issue with characters from the previous AC games...

EDIT2: Some models are not extractable, such as the legacy ones (Altair costume, Ezio costume, etc) and some parts for the Marquis de Sade. I get an exception error for those. Just to let you know MDA 

EDIT3: Added a picture to show the hair problem I'm getting. I get the same issue with blender and 3DS Max as well. As you can see the hair is completely empty.

EDIT4: I just encountered the same problem showed by nav00811. Arno's body (CN_U_Arnaud_Civilian2_Body_LOD0) is still screwed for me if I load it in 3DS Max (OBJ), same for Elise's body (CN_U_FR_Elise_LOD0). However, I suppose that is related to the duplicate face index issue you are already trying to fix? 
[Untitled 1.jpg](https://xentaxbackup.github.io/file/8385_Untitled 1.jpg)
## Post #239
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-27T05:23:48+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> Thank you again MDA! I tested the tool and works fine. I am not getting the exception error anymore when I load it, textures export fine, same as HD meshes. I still have the preview issue, I can't see any of the models and that would be useful also to see if all the needed textures are there. Btw take your time fixing the normals and all  

EDIT: I have a question not really related to the tool itself (unless it really depends on that), but more about the models:

I usually export in OBJ format and I noticed that the hair (both standard LOD0 and HQ) appears as outlined 'strands'. The mesh looks invisible once loaded and I was wondering if there is a way to 'fill' it correctly?

Probably it depends on the way they worked on their next gen models? Since we never had this issue with characters from the previous AC games...

The hair is what it is.  Two of three verts that make up every face are at the exact same position.  How it works in game, is beyond me.

> Reply from RunaWhite
>
> EDIT2: Some models are not extractable, such as the legacy ones (Altair costume, Ezio costume, etc) and some parts for the Marquis de Sade. I get an exception error for those. Just to let you know MDA

What forge file are they located in?

> Reply from RunaWhite
>
> EDIT4: I just encountered the same problem showed by nav00811. Arno's body (CN_U_Arnaud_Civilian2_Body_LOD0) is still screwed for me if I load it in 3DS Max (OBJ), same for Elise's body (CN_U_FR_Elise_LOD0). However, I suppose that is related to the duplicate face index issue you are already trying to fix?

Looks like something I need to fix in the OBJ export routine.  Exports fine for ARX, but not for model viewing or OBJ.

--MDA
## Post #240
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-27T11:46:10+00:00
- Post Title: Re: Archive X

Uhm... so there's no way to get the hair working?  I think it happens only with Arno, I tried loading Elise's hair and the mesh is fine, but Arno's is totally invisible for some reason.

About the forge files, let me locate them again.
## Post #241
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-12-27T13:53:36+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> Uhm... so there's no way to get the hair working?  I think it happens only with Arno, I tried loading Elise's hair and the mesh is fine, but Arno's is totally invisible for some reason.

About the forge files, let me locate them again.

Are you sure that Elise's hairs works?
For me it happens the thing you explained with her hair too
## Post #242
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-27T14:09:08+00:00
- Post Title: Re: Archive X

> Reply from loriscangini
>
> Are you sure that Elise's hairs works?
For me it happens the thing you explained with her hair too

Elise's hair LOD3 works fine it seems [http://i.imgur.com/FA4sopv.jpg](http://i.imgur.com/FA4sopv.jpg)

Arno's hair LOD3 works too, but eeewwww.... [http://i.imgur.com/3R5o5sz.jpg](http://i.imgur.com/3R5o5sz.jpg)

EDIT: Yeah, seems like all the LOD0/HD hair meshes are not working as standard meshes. They probably used an internal engine or something to render the strands. This means hoodless Arno, Elise and all the other characters can't be extracted properly... pity :\
## Post #243
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-12-27T15:08:54+00:00
- Post Title: Re: Archive X

> Reply from RunaWhite
>
> ...

Elise's hair LOD3 works fine it seems http://i.imgur.com/FA4sopv.jpg

Arno's hair LOD3 works too, but eeewwww.... http://i.imgur.com/3R5o5sz.jpg

EDIT: Yeah, seems like all the LOD0/HD hair meshes are not working as standard meshes. They probably used an internal engine or something to render the strands. This means hoodless Arno, Elise and all the other characters can't be extracted properly... pity :\

exactly, I think the hair are made with some tricks ingame!
## Post #244
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-27T17:30:27+00:00
- Post Title: Re: Archive X

As far as I'm concerned it is working.  That's how Ubisoft designed it.  It has to be lighting and shaders that makes it visible in game.  This isn't the normal alpha textured hair past games have had.

And this will happen with all the models tagged as "HD Mesh" (soon to be "Hair Mesh").

[EDIT]That's a pretty decent LOD3 for Elise's hair.  Generally they all end up looking like Arno's LOD3. 

--MDA
## Post #245
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-27T18:46:23+00:00
- Post Title: Re: Archive X

IKR? I was kinda surprised to see how different it was! That's why at first I thought it was the HD mesh   

Well it's sad for us, but makes sense. The hair in Unity looks more realistic than the previous ones in fact. Next gen power lol.

Weird thing, Assassin Arno has a standard hair mesh for the front part under the hood O_o
## Post #246
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-28T09:58:32+00:00
- Post Title: Re: Archive X

Updated [ARchive_neXt v1.11.16.1](http://www.tbotr.net/Downloads/ARchive_neXt.exe) -- Now Available

Changes:
Fixed issues with some of the character models not being viewable, exportable and/or not exporting properly.
"HD Mesh" has now been re-categorized as "Hair Mesh".
Other numerous minor fixes to things that were broken while trying to fix the character model issues above.

To Do:
Still need to figure out duplicate face index issue.  This issue appears to be localized to npc inventory items, and structures.  The character model issue from above was caused by absolute/relative face indexing.  With this version of the game, there is at least 4 different model formats.  While in previous AC games there was only one, even though it had changed sometimes from game to game, each game had only one format in any given forge file.
Still need to figure out the normal map issue.
AC:3 and AC:4 Multi-Player, and DLC forge files are currently not working.  In the past I had tagged these as older versions and that had worked to some extent.  Need to find a more reliable way of determining the proper format to use.
Prince of Persia has a second model format that needs to be incorporated.
POP: The Forgotten Sands has some issue with duplicating tree nodes.

Known Issues:
When the model viewer throws an error when attempting load a model, you will no longer be able to view any models until you restart the program.

That is all

--MDA
## Post #247
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-12-28T10:13:45+00:00
- Post Title: Re: Archive X

Has someone found the weapon models,I have found all the textures but I can't find the meshes!
## Post #248
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-28T14:57:22+00:00
- Post Title: Re: Archive X

> Reply from loriscangini
>
> Has someone found the weapon models,I have found all the textures but I can't find the meshes!

Ye man i found napoleon's gun
## Post #249
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-28T15:23:27+00:00
- Post Title: Re: Archive X

> Reply from loriscangini
>
> Has someone found the weapon models,I have found all the textures but I can't find the meshes!

Found some weapons at the end of "DataPC_extra.forge".  Look for the datafiles beginning with "UI_W_"

--MDA
## Post #250
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-28T17:42:15+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> loriscangini wrote:Has someone found the weapon models,I have found all the textures but I can't find the meshes!

Found some weapons at the end of "DataPC_extra.forge".  Look for the datafiles beginning with "UI_W_"

--MDAHi michaeldarkangel ,good job
## Post #251
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2014-12-30T03:32:06+00:00
- Post Title: Re: Archive X

MDA have you got any success in finding or solving the duplicate face issue
## Post #252
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-12-30T10:42:02+00:00
- Post Title: Re: Archive X

Thank you for the update, MDA!
## Post #253
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2015-01-01T15:56:59+00:00
- Post Title: Re: Archive X

please tell me which models are scene background?
## Post #254
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-01T19:00:06+00:00
- Post Title: Re: Archive X

> Reply from nav00811
>
> MDA have you got any success in finding or solving the duplicate face issue

Sorry, haven't figured that one out yet.

> Reply from kawayide
>
> please tell me which models are scene background?

Can't say that I have come across anything as background scenery, but I also haven't looked for it specifically.  If I do find something I'll let you know.

--MDA
## Post #255
- Username: hammerhorn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 23, 2011 10:31 pm
- Post datetime: 2015-01-03T11:01:10+00:00
- Post Title: Re: Archive X

I'm just visiting Archive neXt for the first time since you released it and an amazing tool.  I'm sorry if I couldn't find the information somewhere else in the thread but are the normal map exports supported.  I'd like to try and pull out some of the location models but when trying to parse the textures it doesn't seem to be error prone.  Is this not supported yet or is there something I might be doing wrong?  I'm trying to pull some of the paris location models out... specifically those for notre dame.  Any suggestions?
## Post #256
- Username: hammerhorn
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-03T16:33:52+00:00
- Post Title: Re: Archive X

> Reply from hammerhorn
>
> Any suggestions?

Unfortunately, you have hit upon the two issues I'm having the hardest time figuring out. Most, if not all, of the structural models have the "duplicate face index" issue. And a majority of the normal maps are strange looking. 

I'm still working on both of these issues. 

--MDA
## Post #257
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-01-06T06:05:19+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> hammerhorn wrote:Any suggestions?

Unfortunately, you have hit upon the two issues I'm having the hardest time figuring out. Most, if not all, of the structural models have the "duplicate face index" issue. And a majority of the normal maps are strange looking. 

I'm still working on both of these issues. 

--MDA

MDA do you have any idea how long it can take
## Post #258
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-01-06T14:48:06+00:00
- Post Title: Re: Archive X

I finally managed to get some decent looking hairs (not 100% perfect, but oh well)





They are so heavy, too many polygons ahah.

MDA, I'm really grateful for the work you've done on this tool!
## Post #259
- Username: Mathew1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 6:30 pm
- Post datetime: 2015-01-06T17:27:06+00:00
- Post Title: Re: Archive X

MDA, thank you very much for your tool, it's really well done!  

But i have some problem with import to 3DSMax arx format (AC Unity). I use your stand-alone ARX importer for 3DSMax.
Body, hair, characters, some objects importing without errors, but all architecture elements, windows, ceiling, some furniture importing with this error.


Obj-importer have problem with vertex  also.
[Error.png](https://xentaxbackup.github.io/file/8437_Error.png)
## Post #260
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-07T04:51:41+00:00
- Post Title: Re: Archive X

> Reply from nav00811
>
> MDA do you have any idea how long it can take

I'm getting closer.  I found some models where they use a set block size for the face indices and if there isn't enough faces they fill the rest of the block with the last face index.  I just need to test more models to see if that block size is static.

> Reply from Mathew1
>
> MDA, thank you very much for your tool, it's really well done!  

But i have some problem with import to 3DSMax arx format (AC Unity). I use your stand-alone ARX importer for 3DSMax.
Body, hair, characters, some objects importing without errors, but all architecture elements, windows, ceiling, some furniture importing with this error.

Obj-importer have problem with vertex  also.

That looks like it's an issue with relative/absolute face indexing.  Can you give me the location of a few of the models that you have found with this issue.  I thought I had figured out how to tag them properly, but I also haven't looked at every model yet.

--MDA
## Post #261
- Username: Mathew1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 6:30 pm
- Post datetime: 2015-01-07T23:24:28+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> 
That looks like it's an issue with relative/absolute face indexing.  Can you give me the location of a few of the models that you have found with this issue.  I thought I had figured out how to tag them properly, but I also haven't looked at every model yet.

MDA, location of a few of the models with this issue:

- DataPC_ACU_Versailles_assets.forge / VRS_LM_VersaillePalace_Clock_LOD0  / Mesh /  VRS_LM_VersaillePalace_Clock_LOD0
- DataPC_ACU_Versailles_assets.forge / VRS_LM_VersaillePalace_2F_WL_Statue_LOD0 / Mesh /  VRS_LM_VersaillePalace_2F_WL_Statue_LOD0
- DataPC_ACU_Versailles_assets.forge / VRS_LM_VersaillePalace_2F_InteriorPFirePlace02_LOD0 / Mesh / VRS_LM_VersaillePalace_2F_InteriorPFirePlace02_LOD0
- DataPC_ACU_Paris_assets.forge / VIL_Roof_Oculus_01_LOD0 / Mesh / VIL_Roof_Oculus_01_LOD
- DataPC_ACU_Paris_assets.forge / VIL_INT_Seat_01_LOD0 / Mesh / VIL_INT_Seat_01_LOD0
- DataPC_ACU_Paris_assets.forge / VIL_INT_CurtainDouble_01_LOD0 / Mesh / VIL_INT_CurtainDouble_01_LOD0
- DataPC_ACU_Paris_assets.forge / VIL_INT_Couch_01_LOD0 / Mesh / VIL_INT_Couch_01_LOD0
## Post #262
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-01-08T05:45:51+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> nav00811 wrote:MDA do you have any idea how long it can take

I'm getting closer.  I found some models where they use a set block size for the face indices and if there isn't enough faces they fill the rest of the block with the last face index.  I just need to test more models to see if that block size is static.
Mathew1 wrote:MDA, thank you very much for your tool, it's really well done!  

But i have some problem with import to 3DSMax arx format (AC Unity). I use your stand-alone ARX importer for 3DSMax.
Body, hair, characters, some objects importing without errors, but all architecture elements, windows, ceiling, some furniture importing with this error.

Obj-importer have problem with vertex  also.

That looks like it's an issue with relative/absolute face indexing.  Can you give me the location of a few of the models that you have found with this issue.  I thought I had figured out how to tag them properly, but I also haven't looked at every model yet.

--MDA
Okay great MDA Well im looking forward for the next update of archive next..
## Post #263
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-08T19:24:23+00:00
- Post Title: Re: Archive X

I think I have the duplicate face index issue straightened out.  But I don't have the full complement of forge files on my laptop, so I'll need to check out a few other models when I get home tonight.  The ones I have tested so far from the Data_PC forge file are looking good.  If everything goes well I should have another update tonight.

Keep your fingers crossed,

--MDA
## Post #264
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-01-09T11:56:27+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> I think I have the duplicate face index issue straightened out.  But I don't have the full complement of forge files on my laptop, so I'll need to check out a few other models when I get home tonight.  The ones I have tested so far from the Data_PC forge file are looking good.  If everything goes well I should have another update tonight.

Keep your fingers crossed,

--MDA

Awesome MDA... I'm waiting till that
## Post #265
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-09T22:17:41+00:00
- Post Title: Re: Archive X

Well, I think I jinxed myself.

I did fix the duplicate face index issue.  But in doing so, I found that most of the 'Fakes' models are upside-down and inside-out.  Well, I did find a way to fix that, but fixing that causes a mess of other issues.

So, it will be at least another day before I get everything sorted.

Sorry,

--MDA
## Post #266
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-01-10T03:15:35+00:00
- Post Title: Re: Archive X

> Reply from MichaelDarkAngel
>
> Well, I think I jinxed myself.

I did fix the duplicate face index issue.  But in doing so, I found that most of the 'Fakes' models are upside-down and inside-out.  Well, I did find a way to fix that, but fixing that causes a mess of other issues.

So, it will be at least another day before I get everything sorted.

Sorry,

--MDA

KK great MDA
## Post #267
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-11T23:51:25+00:00
- Post Title: Re: Archive X

ARchive_neXt v1.12.28.0 Now Available!

Big News:
This fixes the duplicate face index issue.
I have figured out the Skeleton file format (for the most part).  I haven't figured out how to turn that information into something useful.  But I do list out the matrices and hierarchy.  If anyone can figure out how to make it work, let me know.

Known Issues:
Screwy AC:Unity normal maps are still an issue.  I have also noticed this happening to a few diffuse maps.
Tinted ACIV, ACIII diffuse maps are still an issue.

There are still some issues with the model viewer.  I focused on making sure character models were visible, so some smaller item models and larger fakemesh models may not display properly.

Notes:
If you are using NWMax_Plus to import arx files into 3DSMax, please download the stand-alone arxImporter.  The arx file format has changed slightly and NWMax_Plus will no longer import them.
[EDIT] I should also mention that those of you who have been using the stand-alone arxImporter should also pick up the newer version.  The older version will not be able to import arx files exported from ARchive_neXt v1.12.28.0.  The newer version of arxImporter is backwards compatible and will import older arx files. [/EDIT]

Links:
[ARchive_neXt v1.12.28.0](http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=40)
[arxImporter v1.12.28.0](http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=41)

Thanks for your support,

--MDA
## Post #268
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-01-12T20:45:54+00:00
- Post Title: Re: Archive X

> Big News:
>
> This fixes the duplicate face index issue.
>
> I have figured out the Skeleton file format (for the most part).  I haven't figured out how to turn that information into something useful.  But I do list out the matrices and hierarchy.  If anyone can figure out how to make it work, let me know.

That sounds awesome, MDA! Unfortunately I can't provide any help with this, but there are some talented people like chrrox who might be able to figure out how to import the skeleton with the model (although the meshes should come with their vertex groups, or else the skeleton would just be a standalone armature). I usually rig the AC models myself, but in case there really is a way to get the models already rigged, I can wait.

> Known Issues:
>
> Screwy AC:Unity normal maps are still an issue.  I have also noticed this happening to a few diffuse maps.
>
> Tinted ACIV, ACIII diffuse maps are still an issue.

I am waiting to see if the normal maps can be eventually ripped from the game directly and if they appear as screwed as in ARchive_neXt. About the tinted maps, I think that depends on the way the colors are used into the game... which is weird though, considering it only happens with a few textures and not all of them.

> There are still some issues with the model viewer.  I focused on making sure character models were visible, so some smaller item models and larger fakemesh models may not display properly.
>
> 
>
> Notes:
>
> If you are using NWMax_Plus to import arx files into 3DSMax, please download the stand-alone arxImporter.  The arx file format has changed slightly and NWMax_Plus will no longer import them.
>
> [EDIT] I should also mention that those of you who have been using the stand-alone arxImporter should also pick up the newer version.  The older version will not be able to import arx files exported from ARchive_neXt v1.12.28.0.  The newer version of arxImporter is backwards compatible and will import older arx files. [/EDIT]
>
> 
>
> Links:
>
> ARchive_neXt v1.12.28.0
>
> arxImporter v1.12.28.0
>
> 
>
> Thanks for your support,
>
> 
>
> --MDA

Thanks to you for the hard and amazing work!
## Post #269
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-01-13T11:04:51+00:00
- Post Title: Re: Archive X

Hi

About Prince of Persia.

1.mdl format:
types:
a) 1,0,0,0,0,0 and 1,1,0,0,0,0 - maybe is the same
- list of bind matrices with used hash bone
- geometry data
- list of bone maps and materials (vertex ID start, vertex Count ...... )
b) 1,0,1,0,0,0 and 1,0,2,0,0,0 - maybe is the same
- many lists
- like in a)

So each mesh keeps bind matrices. When we want mesh correct position , we must tranform each bind matrice of mesh to bone position of skeleton with the same name.




2.skel format
- bone format: 
bone id - int32
hash -int32
bone hash - int32 - this is name of bone used for mesh skinweights and transform mesh to right position
flag - byte
bone parent id - int 32
.....
vector  position of bone 4*float
quat rotation of bone 4*float
.....
- bone hierarchy: absolute



here is sample how it works:
This blend have imported mdl files in original position :meshes + bind skeletons(matrices)
Now imports skeleton.
All meshes go to new position .


It requires Blender 249 and Python 26
1.run elika.blend
2.in Blender Text Window press alt+p and select "Lover_AddOn.SKEL"

[http://www.mediafire.com/download/gl9ss ... +Elika.zip](http://www.mediafire.com/download/gl9sscv2hbofpqq/Prince+Of+Persia+Elika.zip)

Edit:
Face don't look good.
## Post #270
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-14T01:29:51+00:00
- Post Title: Re: Archive X

> Reply from Szkaradek123
>
> About Prince of Persia.

...

So each mesh keeps bind matrices. When we want mesh correct position , we must tranform each bind matrice of mesh to bone position of skeleton with the same name.

I knew some of the meshes had bone information as well, but was never able to make it work properly.  Something I think I was doing wrong was not inverting the matrix and then I could never figure out the skin section.  I was just thinking about the possibility that the bone information in the model file might be transform matrices, but I could never find the correlation of the bone info between the model file and the skeleton file.

> Reply from Szkaradek123
>
> Edit:
Face don't look good.

If you are talking about ACT_Lover_Head_LOD0 crashing ARchive_neXt, or perhaps the raw data size is so much larger compared to the other models.  The crashing is an issue I need to fix (just found it earlier today).  The size, well, that is the proper size of the file.  There is a huge block of information ahead of the bone info, that I have never been able to figure out what to do with.  I have figured out the pattern, so I'm able to get past it in the models that have it.

The information in your blend file is going to help a lot.  I really appreciate it.

Thanks,

--MDA
## Post #271
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-18T19:46:51+00:00
- Post Title: Re: ARchive_neXt

Has anyone found a Bishop model?

MichaelDarkAngel, thank you for soft! Is there no way to add filters to search in SysTreeView or save tree-structure of archive as text file?
## Post #272
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-18T23:40:22+00:00
- Post Title: Re: ARchive_neXt

> Reply from erik945
>
> Has anyone found a Bishop model?

Not sure which model you are referring to.  Do you have a screenshot?  I have only finished up through Revelations, and have only played roughly 10% of each of the other games, so I don't know all the characters yet.

> Reply from erik945
>
> MichaelDarkAngel, thank you for soft! Is there no way to add filters to search in SysTreeView or save tree-structure of archive as text file?

Because of the way the program only populates the treeview as you expand it, search is pretty much rendered useless.  Doing it this way makes the program much quicker.  If you had to wait for every leaf, branch and tree to populate before you could do anything, on some machines you could be waiting an awful long time.

Thanks for your interest,

--MDA
## Post #273
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-19T01:25:06+00:00
- Post Title: Re: ARchive_neXt

Bones, Skins ans Skeletons were going so good, until I started working on AC2.

Well, Skins and Skeletons, not so bad, but bone information inside the model file... bad.

Prince of Persia and AC1 model formats are similar enough that I was able to figure that out with Szkaradek123's help.  AC2, the bone information has shrunk from 76 bytes to 40 bytes.  So you lose the information on how to link it to the skeleton and the matrix is no longer stored as floats.  I assumed the first eight bytes contain the name and ID and then the remaining 32 bytes would be the matrix possibly as half floats.  No matter how I try to read it I'm not getting the proper results.  And then it gets even worse once you move to AC:Brotherhood as you lose the name which has been contained in the first four bytes (it's now 0x00000000).

I have attached a raw data model from AC2, the bone information starts at 0x12 with the bone count read as a Long and then 40-byte blocks for each bone.  If anyone else wants to look at this and see if they can decipher it, it would be greatly appreciated.

Thanks for your help,

--MDA
[CU_Ezio_Chest_AA_LOD0.zip](https://xentaxbackup.github.io/file/8516_CU_Ezio_Chest_AA_LOD0.zip)
## Post #274
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-01-19T09:07:05+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Bones, Skins ans Skeletons were going so good, until I started working on AC2.

Well, Skins and Skeletons, not so bad, but bone information inside the model file... bad.

Prince of Persia and AC1 model formats are similar enough that I was able to figure that out with Szkaradek123's help.  AC2, the bone information has shrunk from 76 bytes to 40 bytes.  So you lose the information on how to link it to the skeleton and the matrix is no longer stored as floats.  I assumed the first eight bytes contain the name and ID and then the remaining 32 bytes would be the matrix possibly as half floats.  No matter how I try to read it I'm not getting the proper results.  And then it gets even worse once you move to AC:Brotherhood as you lose the name which has been contained in the first four bytes (it's now 0x00000000).

I have attached a raw data model from AC2, the bone information starts at 0x12 with the bone count read as a Long and then 40-byte blocks for each bone.  If anyone else wants to look at this and see if they can decipher it, it would be greatly appreciated.

Thanks for your help,

--MDA

Ну быть может у вас получится это сделать сделать?

Вся надежда на вас, дорогой и уважаемый MichaelDarkAngel! 

P.S Вы могли бы мне помочь вытащить модель вот этой женщины из ACU?
## Post #275
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-19T18:12:09+00:00
- Post Title: Re: ARchive_neXt

Haytham
DataPC_ACU_Paris_assets.forge - cn_u_enabler_head - model LOD0 don't correct extracting (MichaelDarkAngel, may be you can patch it?)
DataPC_ACU_Prologue.forge - cn_u_enabler_visual - body, clothes etc
DataPC_ACU_Prologue.forge - cn_u_enabler_diffusemap,normalmap,mask1mat - textures 
DataPC_SharedGroup00.forge - cn_u_enabler*** - head & hair textures
## Post #276
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-01-20T15:49:02+00:00
- Post Title: Re: ARchive_neXt

Any progress regarding the normal maps?
## Post #277
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-01-21T00:36:47+00:00
- Post Title: Re: ARchive_neXt

I thought I was on to something, because I found the bone name identifier in the 40-byte block of AC2 bone information.  It's the last four bytes of the block.  So it looks like this:

4 bytes - I'll call this Bone ID, becomes useless in later games as they zero it out.
4 bytes - I'll call this Type ID, always the same 0x9EF0E7A1.
4 bytes - Used to be the Bone Name, now all zeroes.
4 bytes - Unknown ID, always the same 0x05358B33, I'll go out on a limb and say this is an instruction ID that tells the game engine how to read the rest of the block.

This is where I can't figure it out.  20 bytes that somehow contains the transformation matrix.

4 bytes - Bone Name.  Yay! I figured that much out.

From AC2 to ACIV:Black Flag this format remains the same with the exception of some of the newer games expanding the Bone ID and unknown ID to 8 bytes.

As an example, bone 0xDED10611 (basically the pelvis bone) in AC1, before inverting the matrix looks like this:

```
 0.000 -1.000  0.000  0.000
 1.000  0.000  0.000  0.000
-0.035 -0.019  0.004  1.000
```


After inverting the matrix looks like this:

```
 0.000 -1.000  0.000  0.000
 1.000  0.000  0.000  0.000
-0.004 -0.019  0.035  1.000
```


Now, I've rounded a little bit so not all the 1s and 0s are exact, but you get the picture.

The following is the 40-byte block for that bone from the raw model data that I posted earlier.

```
60 AE E1 B5 A1 E7 F0 9E 00 00 00 00 33 8B 35 05 -->> 00 00 01 80 00 00 FF 7F 00 00 00 00 56 09 1F 00 00 D0 FF 7F <<-- 11 06 D1 DE
```


Somewhere in that section I have between the arrows is the matrix info I am looking for...  Any ideas...

One thing I have noticed that is nice.  Bone names remain the same from game to game.  That pelvis bone has the same ID in every game (0xDED10611).

Thanks for watching,

--MDA

@loriscangini -- No luck yet on the image issues, sorry.
## Post #278
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-01-21T10:15:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
>  ...

@loriscangini -- No luck yet on the image issues, sorry.

No problem! 

I was asking because I found the exact same problem with the textures from another game, and I don't manage to fix that!
## Post #279
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-01-21T10:17:57+00:00
- Post Title: Re: ARchive_neXt

> Reply from erik945
>
> Has anyone found a Bishop model?

I found the model: [http://3dmodelssanctuary.blogspot.it/20 ... ishop.html](http://3dmodelssanctuary.blogspot.it/2015/01/bishop.html)

She doesn't look perfect, but it's better than nothing!
## Post #280
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-01-21T10:50:50+00:00
- Post Title: Re: ARchive_neXt

Thank you again for your hard work, MDA!

I have tons of models to rig, but I'll wait for a bit in case you will be able to fully figure out the skeleton format
## Post #281
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-01-22T09:18:11+00:00
- Post Title: Re: ARchive_neXt

Thank you!
## Post #282
- Username: Mathew1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 6:30 pm
- Post datetime: 2015-01-22T12:29:22+00:00
- Post Title: Re: ARchive_neXt

I extracted many models and textures from the ACU and hadn't issue.
Thanks you again, MDA!
## Post #283
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-01-30T12:44:48+00:00
- Post Title: Re: ARchive_neXt

@loriscangini: You can bake decent normal maps in blender eventually. Of course they will need some modifications in Photoshop or Gimp and they won't certainly be as good as the ingame ones... but it's the only solution I have for the moment.
## Post #284
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-03T06:00:48+00:00
- Post Title: Re: ARchive_neXt

MichaelDarkAngel, как обстоят ваши дела?

До сих пор имеются проблемы с извлечением костей?

Если хотите, то я мог бы помочь вам !

У меня есть знакомые программисты, быть может они сумеют помочь вам.
## Post #285
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-02-03T06:57:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from Haytham
>
> MichaelDarkAngel, как обстоят ваши дела?

До сих пор имеются проблемы с извлечением костей?

Если хотите, то я мог бы помочь вам !

У меня есть знакомые программисты, быть может они сумеют помочь вам.

English Please...
## Post #286
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-02-04T02:35:49+00:00
- Post Title: Re: ARchive_neXt

Yes, English would be nice.  But Google translate works well enough (at least on this occasion) for me to get an idea.

> Reply from Haytham via Google translate
>
> what about your business?

There are still problems with the extraction of bones?

If you want, I could help you  !

I know some programmers , perhaps they will be able to help you.

That would be great.

Point them at these two posts
1) [viewtopic.php?p=103057#p103057](http://forum.xentax.com/viewtopic.php?p=103057#p103057)
2) [viewtopic.php?p=103106#p103106](http://forum.xentax.com/viewtopic.php?p=103106#p103106)

If they can figure out how the transform matrix is contained in those twenty bytes detailed in the second post from the model attached in the first post, I could finish that section.

Thanks,

--MDA
## Post #287
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-05T05:56:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Yes, English would be nice.  But Google translate works well enough (at least on this occasion) for me to get an idea.
Haytham via Google translate wrote:what about your business?

There are still problems with the extraction of bones?

If you want, I could help you  !

I know some programmers , perhaps they will be able to help you.

That would be great.

Point them at these two posts
1) viewtopic.php?p=103057#p103057
2) viewtopic.php?p=103106#p103106

If they can figure out how the transform matrix is contained in those twenty bytes detailed in the second post from the model attached in the first post, I could finish that section.

Thanks,

--MDA

я попытаюсь помочь вам

сейчас они заняты своим проектом - будут свободны через месяц.
## Post #288
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-02-13T20:50:25+00:00
- Post Title: Re: ARchive_neXt

Hey MDA have you been able to solve the normal map issue...
## Post #289
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-02-14T22:27:59+00:00
- Post Title: Re: ARchive_neXt

> Reply from nav00811
>
> Hey MDA have you been able to solve the normal map issue...

Not yet afaik.
## Post #290
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-24T04:24:22+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> nav00811 wrote:Hey MDA have you been able to solve the normal map issue...

Not yet afaik.

Знаю что не по теме, но вы так и не записали обучающее видео по скиннингу и риггингу моделей, не только AC но и других игр (пример, модели из GTA).

Я конечно не настаиваю, просто если будет время, поможете сделать риггинг вот этой модели:
[https://mega.co.nz/#!MxEUXDaS!EBImk5U1n ... VQJ04BtC28](https://mega.co.nz/#!MxEUXDaS!EBImk5U1nf4Fj3yqZCtyffZB-vkGwRM_0VQJ04BtC28)



P.S Создал вчера мод Bishop из ACU, если хотите, пришлю вам ссылку на скачивание.

Вот она
## Post #291
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-02-24T18:23:58+00:00
- Post Title: Re: ARchive_neXt

English guys... please...
## Post #292
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-24T21:37:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> English guys... please...

Я вам уже написал вам сообщение в ЛС, остальное за вами!
## Post #293
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2015-02-24T21:41:41+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Yes, English would be nice.  But Google translate works well enough (at least on this occasion) for me to get an idea.
Haytham via Google translate wrote:what about your business?

There are still problems with the extraction of bones?

If you want, I could help you  !

I know some programmers , perhaps they will be able to help you.

That would be great.

Point them at these two posts
1) viewtopic.php?p=103057#p103057
2) viewtopic.php?p=103106#p103106

If they can figure out how the transform matrix is contained in those twenty bytes detailed in the second post from the model attached in the first post, I could finish that section.

Thanks,

--MDA

Если какие нибудь продвижения?

Удаётся ли извлечь кости без помощи программы Zmodeler3 (программа платная и с геморойной активацией - я знаю что здесь запрещено общаться на русском языке, но всё же прошу вас ответить на мой вопрос)!

Я знаю что это будет сложно, но всё же нужно упростить задачу обычным пользователям - всё же было бы здорово если бы кто нибудь написал похожую на ARchive_neXt программу, но только для Far Cry 3-4 и Watch_Dogs.
## Post #294
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-24T22:57:31+00:00
- Post Title: Re: ARchive_neXt

OFF:
> Reply from Haytham
>
> я знаю что здесь запрещено общаться на русском языке, но всё же прошу вас ответить на мой вопрос)!how many warnings you need until admin came on you? only english is allowed here, all other languages are for personal conversations. one more time, please.
## Post #295
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-02-26T17:29:33+00:00
- Post Title: Re: ARchive_neXt

Hey MDA is there any idea you got about how long it can take to solve Normal Map Issue
## Post #296
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-02-27T10:44:42+00:00
- Post Title: Re: ARchive_neXt

I'd say just give him some time, Nav   he already said he couldn't figure out the issue yet. I understand that normal maps are important, if you are in a hurry and need them as soon as possible, you might consider the idea of baking them yourself with blender or another 3D program that allows you to do so.
## Post #297
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-02-27T16:57:51+00:00
- Post Title: Re: ARchive_neXt

> Reply from Haytham
>
> RunaWhite wrote:English guys... please...  

Я вам уже написал вам сообщение в ЛС, остальное за вами!

This is yr last warning mate!
## Post #298
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-08T10:24:21+00:00
- Post Title: Re: ARchive_neXt

Hi to all!

The PC version of Rogue is available, I am wondering if it'll be added to Archive_NeXt
## Post #299
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-03-08T10:28:41+00:00
- Post Title: Re: ARchive_neXt

Did you already try to extract from it, Loris? I thought the format was the same of AC4...
## Post #300
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-08T15:46:12+00:00
- Post Title: Re: ARchive_neXt

> Reply from loriscangini
>
> Hi to all!

The PC version of Rogue is available, I am wondering if it'll be added to Archive_NeXt

Haven't purchased it yet, but when I do it will be added.  Until then, copy/paste forge files into Unity's directory and see if it will open.

--MDA
## Post #301
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-08T16:04:36+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> loriscangini wrote:Hi to all!

The PC version of Rogue is available, I am wondering if it'll be added to Archive_NeXt

Haven't purchased it yet, but when I do it will be added.  Until then, copy/paste forge files into Unity's directory and see if it will open.

--MDA

The forge files can be opened if you set the path to Rogue in place of Black Flag and/or Unity, but it crashes when trying to open something inside of them
## Post #302
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-10T22:40:35+00:00
- Post Title: Re: ARchive_neXt

> Reply from loriscangini
>
> MichaelDarkAngel wrote:loriscangini wrote:Hi to all!

The PC version of Rogue is available, I am wondering if it'll be added to Archive_NeXt

Haven't purchased it yet, but when I do it will be added.  Until then, copy/paste forge files into Unity's directory and see if it will open.

--MDA

The forge files can be opened if you set the path to Rogue in place of Black Flag and/or Unity, but it crashes when trying to open something inside of them

Can't see any reason why the way you did it shouldn't work as well as the way I suggested, other than changes to the files.

Sorry everyone, but I guess you'll just have to wait until I get my copy.

--MDA
## Post #303
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-12T19:09:08+00:00
- Post Title: Re: ARchive_neXt

If useful I can try to upload a .forge file from my version.

EDIT:
Here's the DataPC, it should contain the weapons models
[https://mega.co.nz/#!xsVCXCAD!ugHIO9Hr2 ... lNrXZLwiCw](https://mega.co.nz/#!xsVCXCAD!ugHIO9Hr2T8qp8giu8r4eS6x2soalkP_jlNrXZLwiCw)
## Post #304
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-14T09:04:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from loriscangini
>
> If useful I can try to upload a .forge file from my version.

EDIT:
Here's the DataPC, it should contain the weapons models
https://mega.co.nz/#!xsVCXCAD!ugHIO9Hr2 ... lNrXZLwiCw

I think that the Black Flag format is more similar to the one used by Rogue, I can't preview the 3d models in the program, but ignoring the exceptions and exporting them, all works!
There are problems with the textures, none of them is correctly displayed!
## Post #305
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-03-14T12:27:52+00:00
- Post Title: Re: ARchive_neXt

> Reply from loriscangini
>
> loriscangini wrote:If useful I can try to upload a .forge file from my version.

EDIT:
Here's the DataPC, it should contain the weapons models
https://mega.co.nz/#!xsVCXCAD!ugHIO9Hr2 ... lNrXZLwiCw

I think that the Black Flag format is more similar to the one used by Rogue, I can't preview the 3d models in the program, but ignoring the exceptions and exporting them, all works!
There are problems with the textures, none of them is correctly displayed!

It works then? Cool, I need to try it myself!

Btw guys, I have a question; where can I find the textures for the weapons in ACU? They use shared maps, but I only found random single textures and I have no clue where to find the ones needed...
## Post #306
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-14T13:06:40+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> loriscangini wrote:loriscangini wrote:If useful I can try to upload a .forge file from my version.

EDIT:
Here's the DataPC, it should contain the weapons models
https://mega.co.nz/#!xsVCXCAD!ugHIO9Hr2 ... lNrXZLwiCw

I think that the Black Flag format is more similar to the one used by Rogue, I can't preview the 3d models in the program, but ignoring the exceptions and exporting them, all works!
There are problems with the textures, none of them is correctly displayed!

It works then? Cool, I need to try it myself!

Btw guys, I have a question; where can I find the textures for the weapons? They use shared maps, but I only found random single textures and I have no clue where to find the ones needed...

It works for the 3d models, but not the textures!
And I have the same question! Do someone knows where to find the Unity's weapons textures?
## Post #307
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-14T18:14:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Btw guys, I have a question; where can I find the textures for the weapons in ACU? They use shared maps, but I only found random single textures and I have no clue where to find the ones needed...

> Reply from loriscangini
>
> And I have the same question! Do someone knows where to find the Unity's weapons textures?

Not looking for anything specific, the only weapon textures I can pinpoint are in DataPC.forge and begin with "CN_W".  I'm sure this doesn't encompass all weapons, the others we would have to hunt for on a model-by-model basis.

--MDA

@loriscangini - I should have some time this weekend to check out the Rogue file you posted.
## Post #308
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-15T13:18:08+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> RunaWhite wrote:Btw guys, I have a question; where can I find the textures for the weapons in ACU? They use shared maps, but I only found random single textures and I have no clue where to find the ones needed...
loriscangini wrote:And I have the same question! Do someone knows where to find the Unity's weapons textures?

Not looking for anything specific, the only weapon textures I can pinpoint are in DataPC.forge and begin with "CN_W".  I'm sure this doesn't encompass all weapons, the others we would have to hunt for on a model-by-model basis.

--MDA

@loriscangini - I should have some time this weekend to check out the Rogue file you posted.

... Sorry, I made a mistake! I was searching for the 3d models of the weapons in Unity!
The strange thing is that in the DataPC file of unity there are the weapons textures but not the meshes, in the one from Rogue it happens the opposite, there are the 3d models but not the textures!

Anyway, let me know if I can do something else!
## Post #309
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-27T08:57:11+00:00
- Post Title: Re: ARchive_neXt

Any news about the Rogue format?
## Post #310
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-04-08T05:35:44+00:00
- Post Title: Re: ARchive_neXt

Hi!

Can someone tell me more or less what's the overall support on all Assassin's Creed games?
I've been reading the thread and all, but it's hard to tell the status on each game.
I can work on a detailed support list if MDA wants/is unsure on that, but I'm still getting all the games. 

From what I can see, AC:Unity does not support normal maps yet? I wasn't able to extract anything but meshes. Not even textures.

Thanks!
## Post #311
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-04-09T00:06:36+00:00
- Post Title: Re: ARchive_neXt

> Reply from lolwatt
>
> Hi!

Can someone tell me more or less what's the overall support on all Assassin's Creed games?
Meshes:
Assassin's Creed
Assassin's Creed II
Assassin's Creed: Brotherhood
Assassin's Creed: Revelations
Assassin's Creed III
Assassin's Creed IV: Black Flag
Assassin's Creed: Liberation
Assassin's Creed: Unity (multiple mesh formats, not all have been defined, yet)
Prince of Persia (2008)
Prince of Persia: The Forgotten Sands
Textures:
Assassin's Creed
Assassin's Creed II
Assassin's Creed: Brotherhood
Assassin's Creed: Revelations
Assassin's Creed III (some diffuse map issues)
Assassin's Creed IV: Black Flag (some diffuse map issues)
Assassin's Creed: Liberation
Assassin's Creed: Unity (some normal map issues)
Prince of Persia (2008)
Prince of Persia: The Forgotten Sands
Skeletons:
Still a work in progress for all games listed above.

> Reply from lolwatt
>
> From what I can see, AC:Unity does not support normal maps yet?
It would be more correct to say that AC:Unity normal maps do not extract properly.  There is something different about the majority of the normal maps that I have yet to determine.

> Reply from lolwatt
>
> I wasn't able to extract anything but meshes. Not even textures.
Can you expand on this?

--MDA

P.S.  Work has begun on AC:Rogue.  Ability to read the forge files, extract the datafiles, view/extract textures (so far no issues).
P.P.S  I'm sure if I have forgotten something, some one else will be kind enough to remind me
## Post #312
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-04-09T21:33:46+00:00
- Post Title: Re: ARchive_neXt

Thank you very much for your answer.

Regarding my problem with the textures, I will describe it down, I'm sorry if I'm missing something, I'm new to your tool and currently I only got AC Unity to play with.

I can see the meshes in the blue screen and extract them just fine to OBJ or ARX.

When it comes to textures, it seems I can't extract when they have a Material/Mesh with them. Or is it because it's a SET that includes a Normal Map?

[](http://postimg.org/image/kyx3x11nx/full/)

[](http://postimg.org/image/c567fxep9/full/)

Either way, thank you. I can't wait to try out on the other games too.
## Post #313
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-04-09T22:11:14+00:00
- Post Title: Re: ARchive_neXt

> Reply from lolwatt
>
> Regarding my problem with the textures, I will describe it down, I'm sorry if I'm missing something, I'm new to your tool and currently I only got AC Unity to play with.

I can see the meshes in the blue screen and extract them just fine to OBJ or ARX.

When it comes to textures, it seems I can't extract when they have a Material/Mesh with them. Or is it because it's a SET that includes a Normal Map?



Either way, thank you. I can't wait to try out on the other games too.

Watch the video I posted [here](http://www.tbotr.net/index.php).  That shows you how to have the textures visible on the model, and to extract with the model.  To explain it more.  Viewable textures are only stored in the "Texture Map" branch.  The other branches you see are necessary for linking textures to the models.  Earlier games, you will find out, store all the required files together in one "Datafile".  As they have progressed over the years, Ubisoft has seen fit to store less and less in the "Datafiles" to the point where we are now, so that most "Datafiles" only store a single file.  So in order for you to have everything extracted at the same time, you need to find the required "Datafiles" and open them prior to opening/viewing the model's "Datafile".

I hope that wasn't too confusing.

--MDA
## Post #314
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-04-10T03:41:21+00:00
- Post Title: Re: ARchive_neXt

Oh! Thank you for explaining.
I get how it works now. I can see the meshes with textures now.

I was extremely disappointed with the texture size of the weapons. hahaha.
A pretty game like that using 256x128 textures? That's an insult. 

My silly complaints about the game apart, I'm enjoying your tool and I appreciate the support!

Thanks.
## Post #315
- Username: StrunPS
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-04-18T17:46:16+00:00
- Post Title: Re: ARchive_neXt

Wondering what I've been up to lately?  Aside from adding AC file format specs to my [wiki](http://wiki.tbotr.net/index.php) page, and working on adding support for AC:Rogue to ARchive_neXt, I've also been working on an alternate way of loading the forge file into ARchive_neXt.



As you can see in the image above, you no longer have a listing of each individual "Datafile" in the forge file, but a listing of the resource types.  This way reads through the forge file, expanding every datafile, and sorting all files into their respective branches based on resource type.  In the image above I also have the "Show Only Known Files" preference selected which is why the list you see is rather small.  For this alternate method of loading I have also implemented a "Remove Duplicate Files" preference.  This will remove any duplicate files based on file id.

This method does take slightly longer to "open" a forge file, however I believe the benefits will overcome the time delay.

Testing this so far (only AC1 has been set up to test):

DataPC_Damascus.forge took the longest to load at 2 minutes 16 seconds.  You can shorten this time slightly (2 minutes 5 seconds) by having "Show Only Known Files" checked.  Having "Remove Duplicate Files" checked may cause slightly longer load times as that is an extra process performed after all files have been loaded, but so far tests have been minimal (as in less than a second).

Possible benefits from loading this way:

One less tree branch to deal with, all similar files stored together.
All file ids realized when the forge file is loaded; this means no more hunting for texture maps prior to viewing/extracting a model file (as long as the model file has textures associated and they are contained in the same forge file, ARchive_neXt will put it all together).

Load times, ultimately, will be dependent on the power of your PC.  My specs:
Windows 8.1 64-bit, 8GB Ram, AMD A10-6800K 4.1GHz

If all goes according to plan, I should have a release ready by the end of the month.

--MDA
## Post #316
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-04-19T08:55:58+00:00
- Post Title: Re: ARchive_neXt

Thank you so much MDA, this sounds really great!
## Post #317
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-04-21T15:35:19+00:00
- Post Title: Re: ARchive_neXt

Its really awesome MDA...
## Post #318
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-05-25T14:53:13+00:00
- Post Title: Re: ARchive_neXt

MDA how long until the next update is available... I am really looking forward for the normal maps fix.
## Post #319
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-05-27T09:43:33+00:00
- Post Title: Re: ARchive_neXt

Nav, MDA told you he couldn't find a solution yet and clearly he's very busy at the moment. Why don't you try to bake those normal maps yourself, like I suggested? 

You can follow a guide on Youtube called "Normal mapping in blender" (but I'm sure there are many other tutorials about that).

Or download the trial version of CrazyBump to easily and quickly generate the maps you need.

Asking the same thing over and over again won't bring you anywhere guys, just let him breathe and wait patiently for the next update
## Post #320
- Username: Ange
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 12, 2015 4:13 am
- Post datetime: 2015-07-12T05:42:37+00:00
- Post Title: Re: ARchive_neXt

Hi to all and thanks for all the work.
I export without problems meshes and textures (possible ones of course) but I am unable to see the models in archive_next. When I click on a mesh I get an error message "Error viewing the model! Error in the application at Microsoft.directX.Direct3D.Mesh.FromFile......
I was not able to find a thread in the forum on this subject, sorry if it exist already. if I fail the error, the model export very well.
And a second question : is it possible to edit and read the material and texture files, as it's sometimes a real pain to find the textures for a mesh.
Thanks again for this nice program.
## Post #321
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-07-13T02:04:01+00:00
- Post Title: Re: ARchive_neXt

Im having problems loading files with the Just Dance 3 series. I don't know which game engine it should run, but it's to be believed the Prince of Persia loader should do it. It won't load if anyone could help?

[http://www.mediafire.com/download/wsn64 ... urls.forge](http://www.mediafire.com/download/wsn64qr83r03ilb/Data360_CaliforniaGurls.forge) Heres one of the Just Dance 3 forge files.
## Post #322
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2015-07-13T04:45:09+00:00
- Post Title: Re: ARchive_neXt

I don't suppose there's any way to extract everything out of .forge file all at once yet, is there?
## Post #323
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-07-19T18:29:08+00:00
- Post Title: Re: ARchive_neXt

@Ange

Not being able to view models inside of ARchive_neXt may be a graphics card issue.  Unfortunately it is not something I can help you with.  My only suggestion is to make sure you have downloaded and installed the DirectX Redistributable I have linked on the ARchive_neXt download page.

As for the material and texture files; the reason ARchive_neXt cannot find them is due to the way it currently handles the Datafiles.  ARchive_neXt only expands the Datafiles as you open them, it then stores the IDs of the files contained within on the corresponding branches of the files.  When you select a model file, there are reference IDs for material files.  ARchive_neXt searches through all the open Datafiles in the parent forge file.  When it finds the material file, it reads that for references to either a template file or texture file (depending on the game).  The search starts all over again for that ID and so on until it reaches the end at the proper texture files.  So the answer is, no, there isn't a way to read the material files, at least not easily.

@planedec50

ARchive_neXt does not work with forge files from console games.

@snowboundmage

Still working on an alternate method of forge file extraction.  Early tests have proven to be promising, but lengthy.

@everyone

Sorry I have been MIA recently and with real life work heavy and steady as it is right now, it's likely I will continue to be MIA for the next month or so.  I have little time to work on my personal projects, but I am still working on them.  AC:Rogue support along with the alternate load method will be in the next update as soon as I have time to finish it.

Thanks for your patience,

--MDA
## Post #324
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-07-20T10:41:04+00:00
- Post Title: Re: ARchive_neXt

Again, thank you for your hard work MDA. Real life is way more important indeed, so please take your time!

I only have one question though: will the next update also include the skeleton support? In a screenshot you posted there is the Skeleton section, but I don't really know if it's still a very wip or not. Someone managed to rip models with bones using their own created script, but I can't tell how difficult that part is actually supposed to be.
## Post #325
- Username: gon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 25, 2015 9:14 am
- Post datetime: 2015-08-01T22:49:57+00:00
- Post Title: Re: ARchive_neXt

Hi, I´m wondering if anyone has found the weapons model files in AC Unity
## Post #326
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-08-19T03:43:08+00:00
- Post Title: Re: ARchive_neXt

A little bit of news:

According to Quterra my website has been blacklisted by Yandex for files or programs containing a virus.
Quterra also reports that it detected a reference to a blacklisted domain in my index.html file.  I don't have an index.html file on my site.  So I know that's not correct.  I suppose they could mean index.php, which does reference my domain, which has been blacklisted by Yandex.

This all stems from a PM I received today informing me that the download link for ARchive_neXt was broken.  Well, it's not.  However, if you use Chrome or Firefox you'll get the Red Screen informing you of a potential danger when trying to download anything from my site.  Both of those browsers use the SafeBrowsing API which has flagged something as being 'Undetermined Malware' back in May.  I have gone over my site with a fine-toothed comb and can find nothing out of the ordinary, or that I haven't put there myself.

So I then took the ARchive_neXt self-installer and ran it through Metascan.  I found out the last time it was scanned was 5 months ago, not sure by who.  But at that time 9 out of the 44 AV engines failed it as being some form of backdoor or trojan.  So I had it rescan, this time 13 of them failed it (how does that happen).  This was a freshly downloaded copy from my website.  I then decided to run my local copy that I used to upload to my website.  Metascan verified that it was the same file and that it failed the same 13 engines.  So just because I'm OCD, I scanned the local copy that I have before I change the filename (yes I generally keep three copies, one when I package it with the version number in the filename, one with the filename changed used to upload to my website, and a final one that I download from my website saved in a different location), it only failed 3 out of the 44 AV engines (again, how does that happen). ???

What does this all mean:
Everything is going to be on hold until I get some things straightened out.  I've requested a review from Google, because their Webmaster Tools couldn't give me any information as to where this Undetermined Malware is supposedly located.  I'll be sending Yandex an email to see if they will give me some information as to why they have blacklisted my site.  Personally, if being blacklisted by them means they won't crawl my site I think I'm better off.  Ultimately, I may need to look into code signing my projects.  Unfortunately, that means money, and that means you may not see any updates until I can afford the certificate.

Mondays suck! (oh, wait... it's Tuesday)

--MDA
## Post #327
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-08-19T08:04:52+00:00
- Post Title: Re: ARchive_neXt

That sounds seriously weird! I downloaded the tool again a few days ago because I didn't have it on this computer and I needed it to extract a few minor things... didn't have any issue and apparently my antivirus is not seeing it as a potential threat. Btw I really hope things will work out for you MDA, take your time and see what's going on, we'll be here patiently waiting for any future update about the matter.
## Post #328
- Username: mustafasahinfb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 23, 2015 9:22 pm
- Post datetime: 2015-08-23T13:29:29+00:00
- Post Title: Re: ARchive_neXt

Download link death  bkz: [http://www.tbotr.net/modules.php?mod=Do ... =1&dlid=40](http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=40)
Please share v1.12.28.0 download link.

v1.11.16.1 problems :  help pls
## Post #329
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-08-23T22:20:54+00:00
- Post Title: Re: ARchive_neXt

@mustafasahinfb: I suppose English is not your first language, right? MDA said the following in the previous post:

> According to Quterra my website has been blacklisted by Yandex for files or programs containing a virus.
>
> Quterra also reports that it detected a reference to a blacklisted domain in my index.html file. I don't have an index.html file on my site. So I know that's not correct. I suppose they could mean index.php, which does reference my domain, which has been blacklisted by Yandex.

Which means the link is probably down so that he can check and see what exactly is wrong with it. 

About the wrong normal maps, that is sadly a common issue and there's no solution at the moment. About your error, that seems to happen to a lot of people (me included) and might be related to a DirectX issue or incompatibility. Models are still extractable though, even if you cannot see them on the right.
## Post #330
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2015-08-25T00:38:17+00:00
- Post Title: Re: ARchive_neXt

I wonder when we can finally mod the game, not just extract something from it
## Post #331
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-08-29T23:46:38+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> So I then took the ARchive_neXt self-installer and ran it through Metascan.  I found out the last time it was scanned was 5 months ago, not sure by who.  But at that time 9 out of the 44 AV engines failed it as being some form of backdoor or trojan.  So I had it rescan, this time 13 of them failed it (how does that happen).  This was a freshly downloaded copy from my website.  I then decided to run my local copy that I used to upload to my website.  Metascan verified that it was the same file and that it failed the same 13 engines.  So just because I'm OCD, I scanned the local copy that I have before I change the filename (yes I generally keep three copies, one when I package it with the version number in the filename, one with the filename changed used to upload to my website, and a final one that I download from my website saved in a different location), it only failed 3 out of the 44 AV engines (again, how does that happen). ???

Hey! Just found out about this, so I decided to run the same scan on my copies of your files: ARchive_neXt v1.12.28.0.exe (downloaded Jan 12th, 2015) reports the same 13/44 viruses found. As a lark, I decided to try ARchive_neXt v1.11.16.0.exe, which was downloaded Jan 8th, 2015. It reports 6/43. Finally, I decided to give my Archive_X64_v2.01.20.0.exe, downloaded on Oct 6th 2014, a try. It reported 0/43.

I hope this info can help you solve this issue.
## Post #332
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-09-07T02:31:30+00:00
- Post Title: Re: ARchive_neXt

Since we need to decode the skeleton matrix, I've written a PHP script that will take a text file of the bone data (copied out of Archive Next and saved as a txt file) and attempt to covert the data into their proper  X/Y/Z H/P/B values. We still need to figure out the AC matrix, but with this, more of us can attempt to decode it.

The Skeleton Data file looks like this:

```

Bone ID: 4109D99F
 Parent: ROOT
 Matrix:
	0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 1.000000
	0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 1.000000

Bone ID: 4109D9A0
 Parent: 4109D99F
 Matrix:
	0.000000 0.000000 0.000000 0.000000
	-0.499999 -0.500000 -0.500000 0.500001
	0.000000 0.000000 0.000000 0.000000
	-0.499999 -0.500000 -0.500000 0.500001
```

Just copy this code into acreed.php, and run it on a php server. In the same folder, put your skeleton data txt file. I'm testing using the Generic_Unique_Male Skeleton.

```
This code was way out of date. Use .rar file in the following post.
```
## Post #333
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-10-14T06:49:17+00:00
- Post Title: Re: ARchive_neXt

I've severely updated my PHP converter. I've attached my files, and uploaded them to my website for online testing: [http://acreed.kjasi.com/](http://acreed.kjasi.com/). This site will always use my latest code. Should I start a bitbucket for this converter? Let me know.

I think I've gotten the converter as best I can get it. I'm seeing some shapes in the bones that resemble humans, meaning I've got some, if not all, of the position data correct. (Rotation issues aside) However, most of it is still a mess, as illustrated here:



Unless I'm mistaken, this means there are still some flaws in the original matrix data as retrieved by Archive Next. We'll have to wait for MDA to get a new update done before I can proceed too much more...

Edit: Updated, 2015-09-15:
- Can now adjust the matrix conversion dynamically on the page.

Edit2: Updated, 2015-10-01:
- Formulas can now be updated dynamically. NOTE: I've tried to make this as safe as possible, but a clever hacker might still be able to get in. Use caution if using on a live server.
[acreed_20151001.rar](https://xentaxbackup.github.io/file/9811_acreed_20151001.rar)
## Post #334
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-03T19:40:29+00:00
- Post Title: Re: ARchive_neXt

Has anyone attempted or had any luck with elise from unity? I'm struggling with her hair, cant find either a transparent texture or an alpha for it. Also getting an error when exporting.

Here's the full error [http://pastebin.com/0fMHURZX](http://pastebin.com/0fMHURZX)
## Post #335
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-11-05T15:16:33+00:00
- Post Title: Re: ARchive_neXt

Hair is not available, it seems. They used a different method and not their common meshes + textures, you can only get outlines with the tool and eventually create the hair yourself, like I did. It won't be perfect and certainly not as good as the original one, but there's no other option at the moment. 

I don't seem to recall that error so I'm not sure why you get it. I managed to export stuff from Unity with no troubles at all.
## Post #336
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-05T18:50:29+00:00
- Post Title: Re: ARchive_neXt

Dang, well thanks for the response. Is there any chance you can upload the 'outline for me? since i cant export it myslef. Thanks regardless
## Post #337
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-11-06T01:51:15+00:00
- Post Title: Re: ARchive_neXt

I don't know if I can... if I remember correctly sharing is not allowed on this forum, but I definitely need to read the rules all over again to be sure I'm not mistaken.

Btw I believe you missed something if the program doesn't properly work for you. 

You need:

Windows 7 32/64-bit or Windows 8/8.1 32/64-bit
.NET Framework 4.5
DirectX June 2010 Redistributable Runtime

Be sure everything is installed and set up correctly.
## Post #338
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-06T06:46:40+00:00
- Post Title: Re: ARchive_neXt

First of all, awesome tool (surprised I've never actually said that here before.  Second, I know you are busy MDA and there is probably higher priority things to support in this, but is support of AC4's multiplayer files planned or still planned if they were planned already? There is no rush, was just wondering  Keep up the great work with the tool.
## Post #339
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-06T19:13:04+00:00
- Post Title: Re: ARchive_neXt

This is the best i could come up with : /, Looks ugleh. sadlife
[http://i.imgur.com/dPib3Pf.png](http://i.imgur.com/dPib3Pf.png)
## Post #340
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-11-07T15:57:12+00:00
- Post Title: Re: ARchive_neXt

> Reply from pewposterous
>
> This is the best i could come up with : /, Looks ugleh. sadlife
http://i.imgur.com/dPib3Pf.png

It's not so bad actually... sadly even the one I managed to make doesn't look as good as the original one. I might play around with it using some hair shader in Cycles and whatnot, but yeah. Considering we can't get the real thing I guess we're already doing good
## Post #341
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-07T21:08:46+00:00
- Post Title: Re: ARchive_neXt

Yeah i guess tthats true. I would love to see any progress you make
## Post #342
- Username: Nate159WG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 18, 2014 7:36 pm
- Post datetime: 2015-11-14T06:58:27+00:00
- Post Title: Re: ARchive_neXt

Too bad that we can't get Normal maps from ACU yet. :<
Tried to use TexConv didn't work.
## Post #343
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-11-15T10:34:33+00:00
- Post Title: Re: ARchive_neXt

It seems to work with Intel Frame Analyzer, however the last time I tried there was an issue with the latest Nvidia drivers and the program crashed. I need to try again and see if they fixed it...
## Post #344
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-11-20T00:22:42+00:00
- Post Title: Re: ARchive_neXt

Hey guys 
Just wanted to let you know that I got Syndicate and immediatly tried to load the files using Unity's format to see if it was kinda compatible or not. I think it's not 'cause when I load the packages clicking on the + ARchive_neXt crashes (unless I'm doing something wrong to begin with). I'm not surprised of course, gave it a shot.
## Post #345
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-11-20T12:25:21+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Hey guys 
Just wanted to let you know that I got Syndicate and immediatly tried to load the files using Unity's format to see if it was kinda compatible or not. I think it's not 'cause when I load the packages clicking on the + ARchive_neXt crashes (unless I'm doing something wrong to begin with). I'm not surprised of course, gave it a shot.
I was considering doing that, but I figured I'd wait until we get an official update with "support".
## Post #346
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-11-20T13:03:42+00:00
- Post Title: Re: ARchive_neXt

Yep. MDA is currently busy and I think he's still working on a fix for the tool due to what happened recently, but I do hope this game will get its own support as well 

Also, I played a little bit and noticed the hair looks different from Unity... it seems like they switched back to standard meshes (I might be wrong), which is great
## Post #347
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-20T22:05:33+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Yep. MDA is currently busy and I think he's still working on a fix for the tool due to what happened recently, but I do hope this game will get its own support as well 

Also, I played a little bit and noticed the hair looks different from Unity... it seems like they switched back to standard meshes (I might be wrong), which is great

oh please let it be TRUE!
## Post #348
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-11-22T03:11:01+00:00
- Post Title: Re: ARchive_neXt

Hi, not sure if anyone can help me here, I've been lurking this topic / and the forum for about 3-5 months now. Basically, I'm trying to find the Paris buildings, so far, I've had no luck, I'd like to export the cafe theater, along with all its textures, if anyone could help, I'd really like that.

Recently, I tried to export Arno's desk, from his room. I couldn't find VIL_Int_WoodOak_01_Set, I checked everywhere within the game files, doesn't seem to exist.
## Post #349
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-11-22T23:30:06+00:00
- Post Title: Re: ARchive_neXt

> Reply from mikemanj2
>
> Hi, not sure if anyone can help me here, I've been lurking this topic / and the forum for about 3-5 months now. Basically, I'm trying to find the Paris buildings, so far, I've had no luck, I'd like to export the cafe theater, along with all its textures, if anyone could help, I'd really like that.
If it's anything like the previous AC files (I haven't checked Unity yet) then you'll basically be looking for the parts/elements that make up the cafe (Walls, floors, ceilings, tables, chairs, counter, etc...) and will have to assemble it back into the building you want. It doesn't exist as a single mesh. This gave them a lot more flexibility when designing/building the city.

If I'm right, you will also have to look inside the unnamed data blocks (usually named something like Cell00195_DataBlock) and look for the meshes inside those. Not all of the data blocks have names, and unnamed ones tend to have a lot of the game's data in it. If you STILL can't find it, then open Options->Preferences, and uncheck Show Only Known Files. This will unhide a lot of unknown file types. (although this shouldn't be needed for models & textures.)

Hope this helps.
## Post #350
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-24T04:17:35+00:00
- Post Title: Re: ARchive_neXt

Would archive_next bet getting updated eventually for syndicate? I would quite honestly pay someone if the could get me the twins or atleast evie
## Post #351
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-11-24T06:03:33+00:00
- Post Title: Re: ARchive_neXt

> Reply from pewposterous
>
> Would archive_next bet getting updated eventually for syndicate? I would quite honestly pay someone if the could get me the twins or atleast evie
Eventually, yes. MDA has stated that he wants to fix the false virus warnings for his downloads first, but then he'll continue his amazing work.

Honestly, if the code was on Github or Bitbucket, I would try to help him out, but he's been keeping his code close to chest, so to speak.
## Post #352
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-24T07:51:45+00:00
- Post Title: Re: ARchive_neXt

> Reply from Kjasi
>
> pewposterous wrote:Would archive_next bet getting updated eventually for syndicate? I would quite honestly pay someone if the could get me the twins or atleast evie
Eventually, yes. MDA has stated that he wants to fix the false virus warnings for his downloads first, but then he'll continue his amazing work.

Honestly, if the code was on Github or Bitbucket, I would try to help him out, but he's been keeping his code close to chest, so to speak.

Ahh Fair enough, unfortunate that he does but i understand. Well i wish him good luck!
## Post #353
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-11-26T03:38:36+00:00
- Post Title: Re: ARchive_neXt

To the gentleman who told me to look through unknown files, thanks for trying. I looked through just about every file I could and there's no mention of VIL_(examplehere)_(Examplehere)

The /only/ place I've seen any mention of VIL is Paris_assets, and I can't find everything there, say I was looking for one thing specifically; VIL_INT_WoodOak_01_Set, I can't FIND it anywhere, why is there not a search function, or some sort of filter I could apply?


EDIT: As far as I've gathered, the 'Set' part on the end isn't the actual name of the texture, and I /have/ found 'VIL_INT_WoodOak_01'

The issue is however that I've been using the Texture Set part of each asset to locate the textures, and the asset (VIL_Interior_LM_Desk_ArnoRoom_LOD_0) only lists one texture (VIL_INT_WoodOak_Set), how the hell do I figure out what other textures It's using? I've been at this all day, categorizing and sorting thousands upon thousands of objects with their assorted textures. So far I managed to get ONE chair textured, the assets just simply don't tell you all the textures that are required.

I have managed to get a screenshot of an asset using part of the desk's texture ingame. I've outlined what part.
## Post #354
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2015-11-26T10:24:03+00:00
- Post Title: Re: ARchive_neXt

> Reply from mikemanj2
>
> To the gentleman who told me to look through unknown files, thanks for trying. I looked through just about every file I could and there's no mention of VIL_(examplehere)_(Examplehere)

The /only/ place I've seen any mention of VIL is Paris_assets, and I can't find everything there, say I was looking for one thing specifically; VIL_INT_WoodOak_01_Set, I can't FIND it anywhere, why is there not a search function, or some sort of filter I could apply?


EDIT: As far as I've gathered, the 'Set' part on the end isn't the actual name of the texture, and I /have/ found 'VIL_INT_WoodOak_01'

The issue is however that I've been using the Texture Set part of each asset to locate the textures, and the asset (VIL_Interior_LM_Desk_ArnoRoom_LOD_0) only lists one texture (VIL_INT_WoodOak_Set), how the hell do I figure out what other textures It's using? I've been at this all day, categorizing and sorting thousands upon thousands of objects with their assorted textures. So far I managed to get ONE chair textured, the assets just simply don't tell you all the textures that are required.

I have managed to get a screenshot of an asset using part of the desk's texture ingame. I've outlined what part.

I don't know if i understood your problem, but if you can't find that texture in the forge files, ripp it directly from game. If you don't know how to do that send me the save game.
## Post #355
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-11-26T14:57:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from fil1969
>
> mikemanj2 wrote:To the gentleman who told me to look through unknown files, thanks for trying. I looked through just about every file I could and there's no mention of VIL_(examplehere)_(Examplehere)

The /only/ place I've seen any mention of VIL is Paris_assets, and I can't find everything there, say I was looking for one thing specifically; VIL_INT_WoodOak_01_Set, I can't FIND it anywhere, why is there not a search function, or some sort of filter I could apply?


EDIT: As far as I've gathered, the 'Set' part on the end isn't the actual name of the texture, and I /have/ found 'VIL_INT_WoodOak_01'

The issue is however that I've been using the Texture Set part of each asset to locate the textures, and the asset (VIL_Interior_LM_Desk_ArnoRoom_LOD_0) only lists one texture (VIL_INT_WoodOak_Set), how the hell do I figure out what other textures It's using? I've been at this all day, categorizing and sorting thousands upon thousands of objects with their assorted textures. So far I managed to get ONE chair textured, the assets just simply don't tell you all the textures that are required.

I have managed to get a screenshot of an asset using part of the desk's texture ingame. I've outlined what part.


I don't know if i understood your problem, but if you can't find that texture in the forge files, ripp it directly from game. If you don't know how to do that send me the save game.

TexMod was my method for the previous games, doesn't work with Unity, I don't see how sending the save game would help either, since this is just at the Cafe Theatre, which everyone gets.
My save game loads me infront of a mission 600 meters away.

But you could just tell me your method to rip the textures from the game?
## Post #356
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2015-11-26T17:08:06+00:00
- Post Title: Re: ARchive_neXt

> Reply from mikemanj2
>
> fil1969 wrote:mikemanj2 wrote:To the gentleman who told me to look through unknown files, thanks for trying. I looked through just about every file I could and there's no mention of VIL_(examplehere)_(Examplehere)

The /only/ place I've seen any mention of VIL is Paris_assets, and I can't find everything there, say I was looking for one thing specifically; VIL_INT_WoodOak_01_Set, I can't FIND it anywhere, why is there not a search function, or some sort of filter I could apply?


EDIT: As far as I've gathered, the 'Set' part on the end isn't the actual name of the texture, and I /have/ found 'VIL_INT_WoodOak_01'

The issue is however that I've been using the Texture Set part of each asset to locate the textures, and the asset (VIL_Interior_LM_Desk_ArnoRoom_LOD_0) only lists one texture (VIL_INT_WoodOak_Set), how the hell do I figure out what other textures It's using? I've been at this all day, categorizing and sorting thousands upon thousands of objects with their assorted textures. So far I managed to get ONE chair textured, the assets just simply don't tell you all the textures that are required.

I have managed to get a screenshot of an asset using part of the desk's texture ingame. I've outlined what part.


I don't know if i understood your problem, but if you can't find that texture in the forge files, ripp it directly from game. If you don't know how to do that send me the save game.

TexMod was my method for the previous games, doesn't work with Unity, I don't see how sending the save game would help either, since this is just at the Cafe Theatre, which everyone gets.
My save game loads me infront of a mission 600 meters away.

But you could just tell me your method to rip the textures from the game?

you can use Ninja Ripper 64bit or 32bit.. it depends what version Unity is.. till now i ripped all AC games with that tool, so i think you will be able get your textures.
## Post #357
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-11-26T23:58:56+00:00
- Post Title: Re: ARchive_neXt

> you can use Ninja Ripper 64bit or 32bit.. it depends what version Unity is.. till now i ripped all AC games with that tool, so i think you will be able get your textures.

I'm 99% sure even with my save game you'll struggle to find the texture, but if you find it on yours, send it to me, check any of the high cabnets in the cafe theatre, on the second floor, in the rooms that aren't walled with brick, the panels of these cabnets should be decorated with wooden carvings, and that will be the texture I need. I've tried using Ninja Ripper, either it does NOTHING ingame, or it wont even start.
## Post #358
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2015-11-27T06:00:41+00:00
- Post Title: Re: ARchive_neXt

[](http://wiki.xentax.com/index.php?title=)
> Reply from mikemanj2
>
> you can use Ninja Ripper 64bit or 32bit.. it depends what version Unity is.. till now i ripped all AC games with that tool, so i think you will be able get your textures.

I'm 99% sure even with my save game you'll struggle to find the texture, but if you find it on yours, send it to me, check any of the high cabnets in the cafe theatre, on the second floor, in the rooms that aren't walled with brick, the panels of these cabnets should be decorated with wooden carvings, and that will be the texture I need. I've tried using Ninja Ripper, either it does NOTHING ingame, or it wont even start.
Here:
## Post #359
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-12-05T19:23:50+00:00
- Post Title: Re: ARchive_neXt

Would you consider adding any support for console versions? or console games that use forge like Just Dance3?
## Post #360
- Username: Kjasi
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-08T00:13:00+00:00
- Post Title: Re: ARchive_neXt

Once again Google has falsely labeled ARchive_neXt as malware.  Downloads are currently suspended, and you may experience the "Red Screen of Internet Death"TM when visiting my site until Google processes my review request.

In other news:

AC:Rogue -- I believe I have support finished for this game, just need to test a few things.

AC:Syndicate -- This game has become my worst nightmare.  "Why?", you might ask.  Well, with this game, Ubisoft has elected to split the texture maps into two separate files (one is the top mipmap, the other is the remaining mipmaps).  Not only is the top mipmap now a separate file, but it is also contained within a separate datafile.  This would all be well and good if we were already using the alternate load method I have been working on, but we're not.  Of course, this means we may be forced into using that alternate load method which I haven't finished yet.

Rainbow Six: Siege -- Someone asked me if I could add support for this game.  Even though I don't plan on buying it, I was able to download the open beta version prior to the game's release.  I will be adding support based on those open beta files.  If anything has changed now that the game has been released I won't be able to make any changes.

> Reply from planedec50
>
> Would you consider adding any support for console versions? or console games that use forge like Just Dance3?

As much as I would love to try...  No.  Mainly, due to the fact that I don't have access to any of the console games.  Sorry.

I would like to thank everyone that helps out answering questions others have asked here.  You guys have been on the ball and getting to them before I see them.

--MDA
## Post #361
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-08T10:29:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Once again Google has falsely labeled ARchive_neXt as malware.  Downloads are currently suspended, and you may experience the "Red Screen of Internet Death"TM when visiting my site until Google processes my review request.

In other news:

AC:Rogue -- I believe I have support finished for this game, just need to test a few things.

AC:Syndicate -- This game has become my worst nightmare.  "Why?", you might ask.  Well, with this game, Ubisoft has elected to split the texture maps into two separate files (one is the top mipmap, the other is the remaining mipmaps).  Not only is the top mipmap now a separate file, but it is also contained within a separate datafile.  This would all be well and good if we were already using the alternate load method I have been working on, but we're not.  Of course, this means we may be forced into using that alternate load method which I haven't finished yet.

--MDA

Once again thank you for your hard work! Good to hear Rogue support is finished, also that you're working on Syndicate. Take your time for it though... as much as I'd love Syndicate support, there's no reason to rush it and I know how difficult it is to work on this stuff, especially when new games change things all the time. 

Btw guys, something that I wanted to let you know is that I could successfully rip normal maps from Unity. You need the Intel Frame Analyzer, but I think you should look for an old version because the new one crashes with the latest Nvidia drivers. Basically it allows you to load the game through it, then you press some keys to rip the scene and you can load everything in the Frame Analyzer window. Sadly it doesn't seem to work with meshes (I was hoping to get the original hair since it appears in the scenes), but if you want to get the standard normal maps from the game, this is the best way.
## Post #362
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-12-08T20:00:12+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Once again Google has falsely labeled ARchive_neXt as malware.  Downloads are currently suspended, and you may experience the "Red Screen of Internet Death"TM when visiting my site until Google processes my review request.

In other news:

AC:Rogue -- I believe I have support finished for this game, just need to test a few things.

AC:Syndicate -- This game has become my worst nightmare.  "Why?", you might ask.  Well, with this game, Ubisoft has elected to split the texture maps into two separate files (one is the top mipmap, the other is the remaining mipmaps).  Not only is the top mipmap now a separate file, but it is also contained within a separate datafile.  This would all be well and good if we were already using the alternate load method I have been working on, but we're not.  Of course, this means we may be forced into using that alternate load method which I haven't finished yet.

Rainbow Six: Siege -- Someone asked me if I could add support for this game.  Even though I don't plan on buying it, I was able to download the open beta version prior to the game's release.  I will be adding support based on those open beta files.  If anything has changed now that the game has been released I won't be able to make any changes.
planedec50 wrote:Would you consider adding any support for console versions? or console games that use forge like Just Dance3?

As much as I would love to try...  No.  Mainly, due to the fact that I don't have access to any of the console games.  Sorry.

I would like to thank everyone that helps out answering questions others have asked here.  You guys have been on the ball and getting to them before I see them.

--MDA

Thanks MDA, really appreciate what your doing.
## Post #363
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2015-12-09T13:15:22+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> MichaelDarkAngel wrote:Once again Google has falsely labeled ARchive_neXt as malware.  Downloads are currently suspended, and you may experience the "Red Screen of Internet Death"TM when visiting my site until Google processes my review request.

In other news:

AC:Rogue -- I believe I have support finished for this game, just need to test a few things.

AC:Syndicate -- This game has become my worst nightmare.  "Why?", you might ask.  Well, with this game, Ubisoft has elected to split the texture maps into two separate files (one is the top mipmap, the other is the remaining mipmaps).  Not only is the top mipmap now a separate file, but it is also contained within a separate datafile.  This would all be well and good if we were already using the alternate load method I have been working on, but we're not.  Of course, this means we may be forced into using that alternate load method which I haven't finished yet.

--MDA

wrong! The meshes are correctly ripped.. but are not uvmapped.

Once again thank you for your hard work! Good to hear Rogue support is finished, also that you're working on Syndicate. Take your time for it though... as much as I'd love Syndicate support, there's no reason to rush it and I know how difficult it is to work on this stuff, especially when new games change things all the time. 

Btw guys, something that I wanted to let you know is that I could successfully rip normal maps from Unity. You need the Intel Frame Analyzer, but I think you should look for an old version because the new one crashes with the latest Nvidia drivers. Basically it allows you to load the game through it, then you press some keys to rip the scene and you can load everything in the Frame Analyzer window. Sadly it doesn't seem to work with meshes (I was hoping to get the original hair since it appears in the scenes), but if you want to get the standard normal maps from the game, this is the best way.
[Senza titolo-2.jpg](https://xentaxbackup.github.io/file/10131_Senza titolo-2.jpg)
## Post #364
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-12-10T21:00:24+00:00
- Post Title: Re: ARchive_neXt

How do you guys even get the Analyzer to work? I get no HUD overlay and shortcut keys dont do anything  :<
## Post #365
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-10T23:59:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from pewposterous
>
> How do you guys even get the Analyzer to work? I get no HUD overlay and shortcut keys dont do anything  :<

You should be able to run the game through the GPA Monitor capture. Overlay usually appears on the top and pressing the shortcut keys the game freezes for a few seconds. After that you have to open the Frame Analyzer tool which automatically asks you to load your ripped scene.
## Post #366
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-12-11T00:50:29+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> pewposterous wrote:How do you guys even get the Analyzer to work? I get no HUD overlay and shortcut keys dont do anything  :<

You should be able to run the game through the GPA Monitor capture. Overlay usually appears on the top and pressing the shortcut keys the game freezes for a few seconds. After that you have to open the Frame Analyzer tool which automatically asks you to load your ripped scene.

Thanks for the help. I did do that, but no overlay appears. By default the programs buttons are ctrl-f1 to change the HUD display and ctr-shift-c to capture the scene, though both do nothing. Maybe im using a version that doesn't work. I even followed a tutorial :S. Maybe you could link me to the version your using if thats not to much trouble? Thanks eitherway
## Post #367
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-11T10:13:58+00:00
- Post Title: Re: ARchive_neXt

I am using gpa 15.2 release 247704 x64. See if you can find it, if not I'll drop you a pm.
## Post #368
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-12-11T10:54:06+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> I am using gpa 15.2 release 247704 x64. See if you can find it, if not I'll drop you a pm.

That would be great if you dont mind. Having trouble finding anything other than the latest.
## Post #369
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-12-12T15:32:08+00:00
- Post Title: Re: ARchive_neXt

I don't know if you can work on one archive alone but this is all i have for now. Maybe you can work on it?
[http://www.mediafire.com/download/wsn64 ... urls.forge](http://www.mediafire.com/download/wsn64qr83r03ilb/Data360_CaliforniaGurls.forge)
Thanks if you can!
## Post #370
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-12-12T17:53:04+00:00
- Post Title: Re: ARchive_neXt

Hey! I wanted to add some .forge file to planedec50's message, so you can learn more about xbox 360 forge.
[Here is the file](https://mega.nz/#!7RkFTIYT!1XwMCmXKnFgfX8Z1DhfHFH6VWG6dAaIjoVaEfU-s-0c)
## Post #371
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-12-16T07:07:32+00:00
- Post Title: Re: ARchive_neXt

If anyone knows the name of this thing atleast,  I'd really appreciate it.
Just the pillar in the circle, I desperately need this, been searching for it for a few weeks.



I'll pay legit money to anyone who can help me get every asset in the Cafe theatre.
## Post #372
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-12-18T14:20:15+00:00
- Post Title: Re: ARchive_neXt

I'm sorry but.. is there a place where I can download ARchive_neXt now?

I know it's suspended, but yeah.. =o
## Post #373
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-18T15:40:32+00:00
- Post Title: Re: ARchive_neXt

The tool is currently offline due to the issues MDA already explained. It will be back online once he manages to fix those.

And guys, I'm not sure offering money for extracting copyrighted stuff is right.
## Post #374
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-12-19T03:42:26+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> The tool is currently offline due to the issues MDA already explained. It will be back online once he manages to fix those.

Yesh, I understand. 
Perhaps an older version could be shared by anyone? Please?
## Post #375
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-12-19T07:29:21+00:00
- Post Title: Re: ARchive_neXt

I don't intend any copyright though, I am just doing it for a non-commercial project, the pay is just for whoever bothers to look through and find the assets, and a thank you for the help, because I have searched for days and I can't find this pillar still.
## Post #376
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-12-19T09:31:48+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> The tool is currently offline due to the issues MDA already explained. It will be back online once he manages to fix those.

And guys, I'm not sure offering money for extracting copyrighted stuff is right.

Took care of it...
## Post #377
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-12-21T07:49:31+00:00
- Post Title: Re: ARchive_neXt

So? Anyone know what the pillar is called?
## Post #378
- Username: Kjasi
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-22T08:08:31+00:00
- Post Title: Re: ARchive_neXt

ARchive_neXt is back!  This time, I hope for good.  I believe the issue was with the WinRar installer package.  I have switched to using a Windows installer package and it passes Metascan with flying colors.

New version is 2.12.21.0 which now supports AC:Rogue (still working on AC:Syndicate)

If you have been using my 3DSMax importer for arx files, you will also need to grab the newer version of it as well.

--MDA
## Post #379
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2015-12-22T08:45:35+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> ARchive_neXt is back!  This time, I hope for good.  I believe the issue was with the WinRar installer package.  I have switched to using a Windows installer package and it passes Metascan with flying colors.

New version is 2.12.21.0 which now supports AC:Rogue (still working on AC:Syndicate)

If you have been using my 3DSMax importer for arx files, you will also need to grab the newer version of it as well.

--MDA
Yay! Good to know that it wasn't caused by your code directly.
## Post #380
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-12-22T13:19:46+00:00
- Post Title: Re: ARchive_neXt

Good to have it back! 

I keep getting this with Assassin's Creed II.
It won't let me see anything at all.



Anyone else with the same issue?
## Post #381
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-12-22T14:35:38+00:00
- Post Title: Re: ARchive_neXt

it means exactly what error says, missing library lzo.dll... It need to sit next to exe file
## Post #382
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-12-22T15:22:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from michalss
>
> it means exactly what error says, missing library lzo.dll... It need to sit next to exe file

Haha. Uhh, that makes sense!
I did my homework now and searched, didn't know it was an issue on my side. 

Thank you!
## Post #383
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-22T16:40:15+00:00
- Post Title: Re: ARchive_neXt

Sorry about that.  lzo.dll is required by ArchiveX.dll, but it doesn't get picked up by the installer program because it's separate from the ARchive_neXt solution.  I didn't realize it wasn't there because I already have it installed.

It will be fixed tonight.

Thanks for pointing it out.

--MDA
## Post #384
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-12-22T21:28:05+00:00
- Post Title: Re: ARchive_neXt

Which lzo.dll file is that ?
## Post #385
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-12-22T21:32:41+00:00
- Post Title: Re: ARchive_neXt

Also,when I put a certain lzo.dll file in the main folder of the tool I get this in PoP Forgotten Sands:



errordat.png (78.04 KiB) Viewed 65 times
## Post #386
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-23T00:38:07+00:00
- Post Title: Re: ARchive_neXt

Missing lzo.dll issue fixed.  Now at version 1.12.22.0.

@Mr. Mouse --

I haven't figured out how to handle the StreamedSound*.forge files yet.  Of course, I really haven't put much effort into it either.

--MDA
## Post #387
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-23T00:58:07+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Missing lzo.dll issue fixed.  Now at version 1.12.22.0.

@Mr. Mouse --

I haven't figured out how to handle the StreamedSound*.forge files yet.  Of course, I really haven't put much effort into it either.

--MDA
======
next FreeImage.dll....)))
//for texture map
======
next erorr in application:
Microsoft.DirectX.Direct3D.Mesh.FromFile (bla-bla....)
======
File *.x ( in \TEMP) - not a complete model (1/2 or 1/4)
## Post #388
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-23T05:00:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paliha
>
> ======
next FreeImage.dll....)))
//for texture map
======
next erorr in application:
Microsoft.DirectX.Direct3D.Mesh.FromFile (bla-bla....)
======
File *.x ( in \TEMP) - not a complete model (1/2 or 1/4)

First error caused by another missing dll.  Second error caused by the first error.  This issue has been fixed.  New version 1.12.22.1 now available.

The last part could be caused by the error also, if by not complete you mean the textures are missing.

--MDA
## Post #389
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-23T12:04:48+00:00
- Post Title: Re: ARchive_neXt

Thank you for your hard work, again!
## Post #390
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-23T14:51:35+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 

First error caused by another missing dll.  Second error caused by the first error.  This issue has been fixed.  New version 1.12.22.1 now available.

The last part could be caused by the error also, if by not complete you mean the textures are missing.

--MDA

```
   в ARchive_neXt.arxForm.arxDrawMesh()
   в ARchive_neXt.arxForm.OnPaint(PaintEventArgs e)
   в System.Windows.Forms.Control.PaintWithErrorHandling(PaintEventArgs e, Int16 layer)
   в System.Windows.Forms.Control.WmPaint(Message& m)
   в System.Windows.Forms.Control.WndProc(Message& m)
   в System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   в System.Windows.Forms.ContainerControl.WndProc(Message& m)
   в System.Windows.Forms.Form.WndProc(Message& m)
   в System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   в System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   в System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)

```

Perhaps there is no initialization of context (buffer)
//win10 x64
## Post #391
- Username: m25s52
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 19, 2015 1:47 am
- Post datetime: 2015-12-23T16:52:24+00:00
- Post Title: Re: ARchive_neXt

Hi there! Thanks for all the hard work.

I have an issue with the latest version (I searched through the post but I'm not sure) -I'm talking specifically about AC Rogue because that's the only game I have installed : 

1. Every time I want to export an OBJ file it notifies me with the next error : "object reference not set to an instance of an object".
the OBJ file is being exported eventually but it doesn't create an MTL file (It also looks really weird when I open the OBJ file in Blender)

2. I'm unable to see the texture with the mesh in ARchive_neXt ( I can see the textures and the meshes separately but not together) - watched the video you uploaded...maybe I just don't get it

What am I dong wrong?
Thank you in advance and sorry for the noob questions 
[1.jpg](https://xentaxbackup.github.io/file/10198_1.jpg)
## Post #392
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-23T18:48:20+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paliha
>
> Code: Select allSystem.NullReferenceException: Object reference not set to an instance of an object.
   в ARchive_neXt.arxForm.arxDrawMesh()
   в ARchive_neXt.arxForm.OnPaint(PaintEventArgs e)
   в System.Windows.Forms.Control.PaintWithErrorHandling(PaintEventArgs e, Int16 layer)
   в System.Windows.Forms.Control.WmPaint(Message& m)
   в System.Windows.Forms.Control.WndProc(Message& m)
   в System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   в System.Windows.Forms.ContainerControl.WndProc(Message& m)
   в System.Windows.Forms.Form.WndProc(Message& m)
   в System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   в System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   в System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)

Perhaps there is no initialization of context (buffer)
//win10 x64

What model(s) are causing this error?

> Reply from m25s52
>
> Hi there! Thanks for all the hard work.

I have an issue with the latest version (I searched through the post but I'm not sure) -I'm talking specifically about AC Rogue because that's the only game I have installed : 

1. Every time I want to export an OBJ file it notifies me with the next error : "object reference not set to an instance of an object".
the OBJ file is being exported eventually but it doesn't create an MTL file (It also looks really weird when I open the OBJ file in Blender)

2. I'm unable to see the texture with the mesh in ARchive_neXt ( I can see the textures and the meshes separately but not together) - watched the video you uploaded...maybe I just don't get it

What am I dong wrong?
Thank you in advance and sorry for the noob questions

I'll look into your issue over the weekend.

--MDA
## Post #393
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-24T15:52:54+00:00
- Post Title: Re: ARchive_neXt

[quote="MichaelDarkAngel"]

What model(s) are causing this error?

[quote="m25s52"]
Assassin's Creed 4 Black Flag - error
Assassin's Creed III - error
Assassin’s Creed Unity - error
Assassin's Creed Rogue - error
---------
Assassin s Creed Syndicate - the text box is not active.
## Post #394
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-24T16:31:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paliha
>
> MichaelDarkAngel wrote:

What model(s) are causing this error?
m25s52 wrote:
Assassin's Creed 4 Black Flag - error
Assassin's Creed III - error
Assassin’s Creed Unity - error
Assassin's Creed Rogue - error
---------
Assassin s Creed Syndicate - the text box is not active.

Does that happen with every model you try to load? Because I never had that issue with AC4, AC3, nor Unity.

Syndicate text is not active because, as MDA said, he's still working on it and thus that game is not yet supported.

[OT]Happy holidays everyone [/OT]
## Post #395
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-24T17:18:47+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> 

Does that happen with every model you try to load?
======
Yes, in all games the review of the model fails. System.NullReferenceException - this is not a bug of the OS, this is a programming error. Either a pointer to the identifier of the UserControll where something is duplicated or missing initialization of this component.

> Reply from RunaWhite
>
> 
Because I never had that issue with AC4, AC3, nor Unity.
I'm happy for You...))) Then I have a lot of questions for my OS...))
## Post #396
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-24T21:37:40+00:00
- Post Title: Re: ARchive_neXt

@Paliha 
Do you have the [DirectX June 2010 Redistributable Runtime](http://www.microsoft.com/en-us/download/details.aspx?id=8109) installed?
I know my installer gives you the required DirectX .dlls, but you may need to install this as well.

--MDA
## Post #397
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-12-25T02:01:55+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> @Paliha 
Do you have the DirectX June 2010 Redistributable Runtime installed?
--MDA
If it's important, then twice. Although Win10 is all set by default.)))
I downloaded the app in dnSpy-1.5.0.0. Maybe the screenshots will help. This is the first error:
In Microsoft.DirectX.Direct3D.Mesh.FromFile(String filename, MeshFlags options, Device device, GraphicsStream& adjacency, ExtendedMaterial[]& materials, EffectInstance[]& effects)}	Microsoft.DirectX.Direct3D.Direct3DXException
Exception in application code:
[http://uploads.ru/jVOPF.png](http://uploads.ru/jVOPF.png)
The variable settings in the exception:
[http://uploads.ru/NdJ6e.png](http://uploads.ru/NdJ6e.png)
Checked on two laptops (Win7x64 and Win10x64).
## Post #398
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2015-12-25T11:18:56+00:00
- Post Title: Re: ARchive_neXt

Still looking for the pillar from a page or two back, any help is appreciated, a name, anything.
## Post #399
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2015-12-25T14:50:57+00:00
- Post Title: Re: ARchive_neXt

> Reply from mikemanj2
>
> Still looking for the pillar from a page or two back, any help is appreciated, a name, anything.

If nobody answered so far it probably means they have no clue (and I can't help you either). I suppose you can just wait and see if someone else managed to find it.
## Post #400
- Username: Verta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 29, 2015 1:53 pm
- Post datetime: 2015-12-29T05:56:37+00:00
- Post Title: Re: ARchive_neXt

Hello Michael DarkAngel

You could add support for your program files .forge game Tom Clancy's Rainbow Six Siege? 
Ready to help if needed.
## Post #401
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-29T21:39:20+00:00
- Post Title: Re: ARchive_neXt

> Reply from Verta
>
> You could add support for your program files .forge game Tom Clancy's Rainbow Six Siege? 
Ready to help if needed.

From a post of mine from a few pages back:

> Reply from MichaelDarkAngel
>
> Rainbow Six: Siege -- Someone asked me if I could add support for this game.  Even though I don't plan on buying it, I was able to download the open beta version prior to the game's release.  I will be adding support based on those open beta files.  If anything has changed now that the game has been released I won't be able to make any changes.

This will, however, not happen until I am finished adding support for AC:Syndicate.

--MDA
## Post #402
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-12-30T03:23:11+00:00
- Post Title: Re: ARchive_neXt

Thanks for the continued hard work MDA! Looking forward to perusing Syndicate!
## Post #403
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-12-30T14:50:35+00:00
- Post Title: Re: ARchive_neXt

I don't know if you saw my post from a few pages back, but i'm wondering if you could probably add support on these or work on them?
[http://www.mediafire.com/download/wsn64 ... urls.forge](http://www.mediafire.com/download/wsn64qr83r03ilb/Data360_CaliforniaGurls.forge)
[https://mega.nz/#!7RkFTIYT!1XwMCmXKnFgf ... VaEfU-s-0c](https://mega.nz/#!7RkFTIYT!1XwMCmXKnFgfX8Z1DhfHFH6VWG6dAaIjoVaEfU-s-0c)
Here are some samples if you want to work on them
## Post #404
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-30T18:03:46+00:00
- Post Title: Re: ARchive_neXt

> Reply from planedec50
>
> I don't know if you saw my post from a few pages back

My fault for not replying to you when I grabbed them earlier.  I do have them, I will look into adding support, most likely not until after Rainbow Six Siege.

--MDA
## Post #405
- Username: pewposterous
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-01T21:50:22+00:00
- Post Title: Re: ARchive_neXt

Somewhat good news:

[](http://www.tbotr.net/images/ARchive_neXt_005.png)
Click for larger image

[](http://www.tbotr.net/images/ARchive_neXt_006.png)
Click for larger image

Models are similar to AC:Unity.  Some textures are not split.  This means with the next update I can give you some support for AC:Syndicate.

Other fixes in the next update:
ACIV:Black Flag - Multi-Player support has been fixed
AC:Unity - Some model corrections
AC:Rogue - OBJ export has been fixed

Normal Map issues still remain for AC:Unity and beyond

Look for an update before the weekend is over.

--MDA
## Post #406
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-01-02T02:15:04+00:00
- Post Title: Re: ARchive_neXt

Thank you MDA, this looks great!

I've got a question though... is hair in Syndicate just the same as Unity (and thus not extractable due to shaders and all) or is the game using meshes with additional effects this time?
## Post #407
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-02T07:21:57+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Thank you MDA, this looks great!

I've got a question though... is hair in Syndicate just the same as Unity (and thus not extractable due to shaders and all) or is the game using meshes with additional effects this time?

So far, unfortunately, all I have found is similar to what we had in AC:Unity.

[EDIT]
After a little more hunting I can expand on this.  Major characters appear to use a mix of strand-style (much like AC:Unity hair) and overlapping faces (primarily for the roots).  Other character models use the basic overlapping faces style.  Facial hair I've only seen using the overlapping faces style.
[/EDIT]

--MDA
## Post #408
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-01-02T13:02:31+00:00
- Post Title: Re: ARchive_neXt

Uhm, so there is a good chance for us to get the real thing without having to recreate the hair all the time (and getting a crappy result anyway)? If by 'overlapping faces' you mean something like textured meshes...
## Post #409
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2016-01-02T14:00:54+00:00
- Post Title: Re: ARchive_neXt

Some Syndicate support and Black Flag MP support! What an awesome update, can't wait for it
## Post #410
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-02T20:07:28+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Uhm, so there is a good chance for us to get the real thing without having to recreate the hair all the time (and getting a crappy result anyway)? If by 'overlapping faces' you mean something like textured meshes...

This might give you a better idea of what I'm talking about.

Evie Hair Meshes
This is what I mean by strand-style
[](http://www.tbotr.net/images/EvieHair.png)
Click for larger image

This is what I mean by overlapping faces
Evie Roots
[](http://www.tbotr.net/images/EvieRoots.png)
Click for larger image

Jacob Hair Shell
[](http://www.tbotr.net/images/JacobShell.png)
Click for larger image

--MDA
## Post #411
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-01-02T23:50:29+00:00
- Post Title: Re: ARchive_neXt

Ahhhh okay makes sense now! Thank you for the screenshots  really helpful! Is there a working texture for those mesh pieces (with alpha and all) or is it just like Unity where you only got a plain color?
## Post #412
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-01-03T01:06:25+00:00
- Post Title: Re: ARchive_neXt

I wonder how they do it. Maybe using some kind of particle system, with the roots as the base, following the strands. Cant wait to play around! Thanks MDA!
## Post #413
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2016-01-03T01:27:07+00:00
- Post Title: Re: ARchive_neXt

Strand styles would be very helpful in recreating the hair used by the in-game hair systems (such as TressFX and NVIDIA HairWorks) in 3D systems. Finding and being able to extract the color/instructions for those hair systems would also greatly increase our ability to duplicate their look in 3D.

I do have a request for when you do some work on the 3D window... Can you add a system so we can change the controls used for the 3D window? I'd love to be able to set it up to work like Maya's windows.
## Post #414
- Username: pewposterous
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-03T02:28:08+00:00
- Post Title: Re: ARchive_neXt

Version 3.01.02.0 Now Available! (Link is in my sig)

Adds AC:Syndicate support (split texture map issue has been solved)
Adds ACIV:Black Flag multi-player support
Fixes some model issues in AC:Unity
Fixes model viewing issue in AC:Rogue

I'm sure there are a few other things that I fixed and forgotten about, but the above are the major adds/fixes.

If you want to play around with the Hair Meshes and you are using 3DSMax, you may want to grab my arxImporter.  The OBJ importer will not import those meshes.  Not sure how other modeling programs will handle it.  And because there are no visible faces, you will not see anything in ARchive_neXt's viewport or in the Perspective viewport in 3DSMax unless you enable "Edged Faces" (that's how I produced the screenshot for Evie's Hair in my previous post).

@RunaWhite
I didn't find any hair textures for those models that I posted, but I've only been playing around inside the DataPC.forge and the DataPC_ACVI_London.forge files so far.

@pewposterous
I like your idea

@Kjasi
I'll have to dig into the Hair Meshes again at some point.  Some of that information may be in the file somewhere and I just wasn't seeing it before.  As for the 3D window, that's probably as good as I'm going to be able to give you unless I can find something that someone else has done that I can figure out how to plugin to ARchive_neXt.  I've already tried a few when I first got the viewer working again that I wasn't able to make work.  I may be able to give you the ability to change the keymapping, but beyond that...

Enjoy!  I think I'm going to play a little bit AC - Something before tackling Rainbow Six Siege and waiting for bug reports.   

--MDA
## Post #415
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-01-03T10:39:25+00:00
- Post Title: Re: ARchive_neXt

Thanks MDA. Only thing ive noticed, Hair strands show up blank for me, maybe because there no volume? Nothing to actually display.

Also, would there ever be a chance for a search feature? There files can be a mess to search through.

Thirdly, has anyone located eyes? I'm looking for Evie and Jacob specifically. Edit: Found Textures - AVCI_LIB_EyeTech_Eyeball). Now for the meshes

Once again, thanks for the hard work Mda, go enjoy AC! You've more than earned it
## Post #416
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-01-03T13:20:39+00:00
- Post Title: Re: ARchive_neXt

I had the same issue with hair in Unity, I couldn't properly display them unless the strands were selected but I could extrude them anyway to create volume.

I also found a shared hair texture with alpha channel, not sure if that works with Evie's and Jacob's roots though I need to test it.

Anyway, THANK YOU so much MDA for the work you did and always do!

EDIT: I just tried the shared hair map on Evie's root and it seems to work  it will only require a simple recolor but it should definitely make things easier. Also it's good that the strands are separated in parts instead of being a huge block.
## Post #417
- Username: m25s52
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 19, 2015 1:47 am
- Post datetime: 2016-01-03T17:18:45+00:00
- Post Title: Re: ARchive_neXt

Thanks MDA! AC Rogue works!
## Post #418
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2016-01-03T18:16:55+00:00
- Post Title: Re: ARchive_neXt

Tried this tool this morning. But whenever I clicked (any) '+' (expand) (like #MichaelDarkAngel showed on the prev page), the tool returns an error. I could "continue" but that was pretty much it.
(tried several forge-files btw)

Just tried again, and now it returns with an 'faulting' [lzo.dll].
My question: what must be installed - as a prerequisite - to get the tool running fine?!
## Post #419
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-03T19:49:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paul44
>
> Tried this tool this morning. But whenever I clicked (any) '+' (expand) (like #MichaelDarkAngel showed on the prev page), the tool returns an error. I could "continue" but that was pretty much it.
(tried several forge-files btw)

Just tried again, and now it returns with an 'faulting' [lzo.dll].
My question: what must be installed - as a prerequisite - to get the tool running fine?!

Can you screenshot the error you are receiving?  What forge file(s) are you trying to open?  What operating system are you running?

--MDA
## Post #420
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-01-03T20:24:39+00:00
- Post Title: Re: ARchive_neXt

Anyone had any luck locating Eye textures, thought i found it. Unless they reuse the 1 texture, i have no idea :<.

Here's what ive been able to come up with so far. Hairs just temporary until i can figure out something better : /
[http://i.imgur.com/63HBqcU.png](http://i.imgur.com/63HBqcU.png)
Image is to large :O, is there any way to add spoiler

Well i needa sleep. 5 am O_O
## Post #421
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-01-03T23:34:02+00:00
- Post Title: Re: ARchive_neXt

I had the same issue, but tried Unity's texture and it works  you may need to adjust it a little bit, but there are other maps like the lashes and inner mouth that seem to perfectly match Syndicate UVs.

Great job on the hair btw!!! I think you could add a subdivision surface (not sure what you used to render her though) to smooth everything and it will be perfect
## Post #422
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2016-01-08T01:55:06+00:00
- Post Title: Re: ARchive_neXt

This might just be redundant info (Since its a little hard to keep up with everything in here) but, we know the ACS's normal maps are "BC7_TYPELESS" and not "DXT5" right?

```
444453207C0000000600000000080000000800000020000000000000010000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000200000000400000044583130000000000000000000000000000000000000000000100000000000000000000000000000000000006200000003000000000000000100000000000000
```
 Exporting the Normal texture as raw data and replacing the first 126 bytes with those bytes will make it work in programs that support the DX10 DDS header. If the texture you want isn't 2048x2048 this header won't work, obviously.
## Post #423
- Username: mambox
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-08T06:02:07+00:00
- Post Title: Re: ARchive_neXt

> Reply from Simguy
>
> This might just be redundant info (Since its a little hard to keep up with everything in here) but, we know the ACS's normal maps are "BC7_TYPELESS" and not "DXT5" right? Exporting the Normal texture as raw data and replacing the first 126 bytes with those bytes will make it work in programs that support the DX10 DDS header. If the texture you want isn't 2048x2048 this header won't work, obviously.

Any chance you would like to share which normal map you got the above header to work with?  I've tried a few that are 2048 x 2048 and could not make it work.  I even tried one that was 512 x 512, changing the height and width in the header and wasn't able to make that work either.

On another note, if it is in fact BC7_TYPELESS then the dxgiFormat in you header is incorrect.  BC7_TYPELESS = 97 0x61, BC7_UNORM = 98 0x62

I was really hoping this would work.  I have tried numerous DX10 formats since the days of the pink tinted textures with no luck yet.

--MDA
## Post #424
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2016-01-08T07:07:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Simguy wrote:This might just be redundant info (Since its a little hard to keep up with everything in here) but, we know the ACS's normal maps are "BC7_TYPELESS" and not "DXT5" right? Exporting the Normal texture as raw data and replacing the first 126 bytes with those bytes will make it work in programs that support the DX10 DDS header. If the texture you want isn't 2048x2048 this header won't work, obviously.

Any chance you would like to share which normal map you got the above header to work with?  I've tried a few that are 2048 x 2048 and could not make it work.  I even tried one that was 512 x 512, changing the height and width in the header and wasn't able to make that work either.

On another note, if it is in fact BC7_TYPELESS then the dxgiFormat in you header is incorrect.  BC7_TYPELESS = 97 0x61, BC7_UNORM = 98 0x62

I was really hoping this would work.  I have tried numerous DX10 formats since the days of the pink tinted textures with no luck yet.

--MDA

You're right, thats my bad. Its BC7_UNORM.
I used that header on "ACVI_CHR_P_Evie_Dracula_Body_NormalMap" in dlc_14 and "ACVI_CHR_P_EvieOutfit_01_Body_NormalMap" in DataPC_SharedGroup_00, not sure why its not working for you. I opened them in Photoshop using Intel's DDS Plugin if that helps.  I'll pm you the DDS's.
## Post #425
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2016-01-09T14:59:44+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Simguy wrote:This might just be redundant info (Since its a little hard to keep up with everything in here) but, we know the ACS's normal maps are "BC7_TYPELESS" and not "DXT5" right? Exporting the Normal texture as raw data and replacing the first 126 bytes with those bytes will make it work in programs that support the DX10 DDS header. If the texture you want isn't 2048x2048 this header won't work, obviously.

Any chance you would like to share which normal map you got the above header to work with?  I've tried a few that are 2048 x 2048 and could not make it work.  I even tried one that was 512 x 512, changing the height and width in the header and wasn't able to make that work either.

On another note, if it is in fact BC7_TYPELESS then the dxgiFormat in you header is incorrect.  BC7_TYPELESS = 97 0x61, BC7_UNORM = 98 0x62

I was really hoping this would work.  I have tried numerous DX10 formats since the days of the pink tinted textures with no luck yet.

--MDA

Assassin's Creed Syndicate - Evie The Aegis Update
by elonir: [http://elonir.deviantart.com/art/Assass ... -582115463](http://elonir.deviantart.com/art/Assassin-s-Creed-Syndicate-Evie-The-Aegis-Update-582115463)

Evie from Assassin's Creed: Syndicate wearing "The Aegis" outfit, model with in-game/original rig. Don't have eyes/hair mesh and texture for them, lashes and hand (was lazy to find them xD)
Link [https://www.sendspace.com/file/kgyi05](https://www.sendspace.com/file/kgyi05)

Update: Here's model with skeleton hierarchy for most bones, it will be easier to work with model. No need to attach bones to each other.
[https://www.sendspace.com/file/1ulgwp](https://www.sendspace.com/file/1ulgwp)
## Post #426
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-09T16:58:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from Simguy
>
> You're right, thats my bad. Its BC7_UNORM.
I used that header on "ACVI_CHR_P_Evie_Dracula_Body_NormalMap" in dlc_14 and "ACVI_CHR_P_EvieOutfit_01_Body_NormalMap" in DataPC_SharedGroup_00, not sure why its not working for you. I opened them in Photoshop using Intel's DDS Plugin if that helps.  I'll pm you the DDS's.

Okay, so here's my issues.  Irfanview does not handle DX10, throws a decode error upon loading.  Xnview converts DX10 to DXT5 upon loading.  Nvidia's DDS tools were not working either, any DX10 I would load into Photoshop would be solid black.  Swapped out Nvidia's Tools for Intel's Tools and now I can see.

Not sure how this is going to work for ARchive_neXt as I haven't put the code to test yet.  The version of the FreeImage dll is old and may not be able to handle DX10.  Maybe I'll get that finished before the end of the weekend.

--MDA

P.S. Thanks again Simguy
## Post #427
- Username: Simguy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-11T01:56:22+00:00
- Post Title: Re: ARchive_neXt

A little update.  As I thought, FreeImage can't handle DX10.  That means you will not be able to view the DX10 normal maps instead you'll see my generic "Bad Image" image.



You will be able to "Export" the proper DDS file from the right-click menu, and the proper DDS file will be exported when you export a model.

I haven't been able to find a new image library that is able to handle DX10 DDS images.

So not good news, but not totally bad news either.

--MDA
## Post #428
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-15T21:20:12+00:00
- Post Title: Re: ARchive_neXt

Hi!

I've been successfully been able to export whatever mesh I want to be exported and whatever mesh, but for some reason when I export the "CN_U_Elise_Party_Body_LOD0" as a .obj (because else I can't export it into Blender), it gives me an error:

See the end of this message for details on invoking 
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.NullReferenceException: Object reference not set to an instance of an object.
   at ARchive_neXt.arxForm.arxExportOBJ(TreeNode treeNode, String savePath)
   at ARchive_neXt.arxForm.arxExportModels(String fileExt)
   at ARchive_neXt.arxForm.tsmiExportModels_Click(Object sender, EventArgs e)
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ToolStrip.WndProc(Message& m)
   at System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)

It does make a .obj file of it, but when I import it into Blender, no mesh will appear.
The path to it is: DataPC_ACU_Versailles.forge > CN_U_FR_Elise_Party_Visuals > Mesh 
I'm using the latest version of the program, I have no idea if older versions (that are compatible with Unity of course) might fix the problem.
## Post #429
- Username: ShivShubh
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-16T02:55:03+00:00
- Post Title: Re: ARchive_neXt

Version 3.01.15.0 Now Available! (Link is in my sig)

This is just a quick update to fix the AC:Unity OBJ export error as reported by Greenplumpbob.

This also includes the DX10 texture fix.  If you are viewing a texture (mainly Normal Maps) and receive the "Bad Image" image, using "Export" will give you the proper image, "Export As" will result in the "Bad Image" image exported in the format you choose.

--MDA
## Post #430
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-01-16T12:04:33+00:00
- Post Title: Re: ARchive_neXt

Awesome. Thanks once again Mda!

Edit: Hmm this is what i get when i "Export" a normal map
## Post #431
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-01-16T13:05:04+00:00
- Post Title: Re: ARchive_neXt

What tool you used to open NM textures? For me everything is fine, I suggest you to use Noesis (update it to latest version) and NM will be fine
## Post #432
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-16T13:52:19+00:00
- Post Title: Re: ARchive_neXt

Awesome! The error got fixed, but for some reason the LOD0 version of the CN_U_Elise_Party_Body does only import one 'dot' and that's all. And when I export the LOD1 you can clearly see it is a lower detailed version of LOD0. So for some weird reason it had only one vertex (the LOD0). The rest is working clearly for me! Can't wait to use this program on Syndicate!

Edit: I also encounter this problem with Meshes not be able to load in the preview 3D view. It might be an DirectX, but the version that was needed and I found on this thread didn't fix it.
## Post #433
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-01-16T15:33:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> Awesome! The error got fixed, but for some reason the LOD0 version of the CN_U_Elise_Party_Body does only import one 'dot' and that's all. And when I export the LOD1 you can clearly see it is a lower detailed version of LOD0. So for some weird reason it had only one vertex (the LOD0). The rest is working clearly for me! Can't wait to use this program on Syndicate!

Edit: I also encounter this problem with Meshes not be able to load in the preview 3D view. It might be an DirectX, but the version that was needed and I found on this thread didn't fix it.

A similar situation, and what the problem is incompatibility Microsoft.DirectX.Direct3D.dll not known
For example:
1KMA_UI_AttackCrowdDisperion > 
                                            Material> 
                                                         Unnamed_0000
File ID: 
Resource Type: 
Material Template Reference:  - Not Found
Texture Set Reference:  - Not Found
Unknown Reference:  - Not Found
Unknown Reference:  - Not Found
Material Reference:  - Not Found
 Unknown Count: 0
Maybe that's the problem ?
## Post #434
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-16T16:59:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paliha
>
> Greenplumbbob wrote:Awesome! The error got fixed, but for some reason the LOD0 version of the CN_U_Elise_Party_Body does only import one 'dot' and that's all. And when I export the LOD1 you can clearly see it is a lower detailed version of LOD0. So for some weird reason it had only one vertex (the LOD0). The rest is working clearly for me! Can't wait to use this program on Syndicate!

Edit: I also encounter this problem with Meshes not be able to load in the preview 3D view. It might be an DirectX, but the version that was needed and I found on this thread didn't fix it. 

A similar situation, and what the problem is incompatibility Microsoft.DirectX.Direct3D.dll not known
For example:
1KMA_UI_AttackCrowdDisperion > 
                                            Material> 
                                                         Unnamed_0000
File ID: 
Resource Type: 
Material Template Reference:  - Not Found
Texture Set Reference:  - Not Found
Unknown Reference:  - Not Found
Unknown Reference:  - Not Found
Material Reference:  - Not Found
 Unknown Count: 0
Maybe that's the problem ?

It might be that, but it's weird that this error shows up with EVERY mesh I click. The textures do show up correctly. Maybe it is because I am overlooking a DirectX update, Like an Direct3D update?
## Post #435
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-16T17:27:58+00:00
- Post Title: Re: ARchive_neXt

@pewposterous

I get some odd looking normal maps also when using Photoshop CS2 with Intel's DDS plugin.  But it's the only thing I have found that comes close to working for me.  So maybe try zaramot's suggestion and use Noesis.

@zaramot

Where exactly is that normal map?  I would like to compare how it looks with what I'm using.

@Greenplumbbob

The CN_U_Elise_Party_Body_LOD0 mesh is an oddball.  It is extremely small, so small that most 3D programs may interpret all the verts being in the same place.  I can make an adjustment for that particular model type.

What model(s) are causing the other error you are receiving?  That's usually caused by missing textures, but I need to know why it considers it to be a missing texture and aborts as opposed to showing you a model with no textures.

--MDA
## Post #436
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-01-16T17:40:45+00:00
- Post Title: Re: ARchive_neXt

namespace Microsoft.DirectX.Direct3D..............

............public unsafe static Mesh FromFile(string filename, MeshFlags options, Device device, out GraphicsStream adjacency, out ExtendedMaterial[] materials, out EffectInstance[] effects)
//Variable num2==null
............
............int num2 = <Module>.D3DXLoadMeshFromXA((sbyte*)ptr8, options, unmanagedDevice, ptr4, ptr5, ptr7, (uint*)(&num), &ptr);
//Variable num2==80004005
if (num2 < 0) 
{ if (!DirectXException.IsExceptionIgnored)
  { Exception exceptionFromResultInternal = Direct3DXException.GetExceptionFromResultInternal(num2);
    DirectXException ex = exceptionFromResultInternal as DirectXException;
   if (ex != null)  { ex.ErrorCode = num2; 
                         throw ex; }
## Post #437
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-16T17:46:13+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 

@Greenplumbbob

The CN_U_Elise_Party_Body_LOD0 mesh is an oddball.  It is extremely small, so small that most 3D programs may interpret all the verts being in the same place.  I can make an adjustment for that particular model type.

What model(s) are causing the other error you are receiving?  That's usually caused by missing textures, but I need to know why it considers it to be a missing texture and aborts as opposed to showing you a model with no textures.

--MDA

Never heard of that, but I'm glad to know it is some different kind of mesh than the rest. i'll go with the LOD1 then and tweak it a bit. 
It's basically every mesh. I haven't came across any meshes that showed up at all without the error. I've been searching for LOD meshes for characters, Unity and Syndicate both. I haven't really looked for any 'scene' objects, but the ones I came across had the same error too. Right now I can only view Textures because of this issue in the '3d view'
I also need to go to a different 'forge' to get access to the textures. So say this one mesh is in: DataPC_ACVI_Prologue_1_BowRailWay_assets.forge I need to go to a whole different forge. to get the textures. Maybe that's causing the problem?
## Post #438
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-16T18:57:54+00:00
- Post Title: Re: ARchive_neXt

Version 3.01.16.0 Now Available! (Link is in my sig)

Adjustments to both the ARX and OBJ model exports for certain models that would otherwise be extremely small once imported into a 3D modeling program.

--MDA
## Post #439
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-01-16T19:45:29+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 

@zaramot

Where exactly is that normal map?  I would like to compare how it looks with what I'm using.

--MDA

It's from Syndicate, one of Evie's outfits (bottom of it), though I tried Unity too - NM looks fine after export too. Normal map was from DataPC_ACVI_London.forge - name ACVI_CHR_P_Evie_Outfit_03_Dress_NormalMap
## Post #440
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-01-16T20:08:39+00:00
- Post Title: Re: ARchive_neXt

> Reply from zaramot
>
> What tool you used to open NM textures? For me everything is fine, I suggest you to use Noesis (update it to latest version) and NM will be fine

I was using Photoshop C6. I downloaded Noesis and it works perfectly. Thanks!
## Post #441
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-16T20:12:55+00:00
- Post Title: Re: ARchive_neXt

This is how Photoshop CS2 with the Intel DDS plugin displays that normal map for me.



Clearly Noesis does a better job.

--MDA
## Post #442
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-17T11:56:11+00:00
- Post Title: Re: ARchive_neXt

Noesis seems to be the best exporter, especially when  you would export it in Noesis self and open it up in Photoshop. Weird thing is, is that when I open it up in Noesis, the background is all greyish and when I export it and import it into Photoshop it shows up like it should be. 

Maybe the reason for the Normal maps showing up like that (In aRchive_neXt) is because (from experience) most programs doesn't like greenish normal maps, but blue ones? Maybe that's why ARchive neXt was showing them all 'pixelated'?
## Post #443
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-17T15:29:46+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> Maybe the reason for the Normal maps showing up like that (In aRchive_neXt) is because (from experience) most programs doesn't like greenish normal maps, but blue ones? Maybe that's why ARchive neXt was showing them all 'pixelated'?

Nope, the pixelated version in ARchive_neXt was due to me assuming it was DXT5 compression when in fact it is BC7 compression as Simguy pointed out.  And the reason we can't see anything now in ARchive_neXt is due to the image library I use (Freeimage) for viewing DDS images doesn't handle the newer DX10 compression formats.

--MDA
## Post #444
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2016-01-17T21:42:04+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> Noesis seems to be the best exporter, especially when  you would export it in Noesis self and open it up in Photoshop. Weird thing is, is that when I open it up in Noesis, the background is all greyish and when I export it and import it into Photoshop it shows up like it should be. 

Maybe the reason for the Normal maps showing up like that (In aRchive_neXt) is because (from experience) most programs doesn't like greenish normal maps, but blue ones? Maybe that's why ARchive neXt was showing them all 'pixelated'?

The normal texture is actually green-ish. The textures blue channel is used for shader stuff, not for normal map stuff. The game generates the proper blue channel in shader code. Something like: 
```
blue_channel = sqrt(1.0 - (red_channel*red_channel - green_channel*green_channel))
```
## Post #445
- Username: WeylandYutani
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 22, 2015 5:02 am
- Post datetime: 2016-01-18T09:23:41+00:00
- Post Title: Re: ARchive_neXt

I have Issues importing the arx Files into 3DS Max, Max loads but freezes, i use 2015 so is there anything i miss to do ? Btw many of the Normals are bad Image and some are really important same as some shared diffuses are screwed.
## Post #446
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-18T17:40:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from WeylandYutani
>
> I have Issues importing the arx Files into 3DS Max, Max loads but freezes, i use 2015 so is there anything i miss to do ?

Are you getting any error messages?

> Reply from WeylandYutani
>
> Btw many of the Normals are bad Image and some are really important same as some shared diffuses are screwed.

Read this [post](http://forum.xentax.com/viewtopic.php?p=114390#p114390)
Also from this [post](http://forum.xentax.com/viewtopic.php?p=114580#p114580):

> Reply from MichaelDarkAngel
>
> This also includes the DX10 texture fix.  If you are viewing a texture (mainly Normal Maps) and receive the "Bad Image" image, using "Export" will give you the proper image, "Export As" will result in the "Bad Image" image exported in the format you choose.

--MDA
## Post #447
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-18T18:24:55+00:00
- Post Title: Re: ARchive_neXt

After a little testing/research, I think I found out the reason why Noesis has a much better looking normal map.

This is the Evie dress normal map converted to DXT5 using Microsoft's [texconv](http://directxtex.codeplex.com/releases/view/612866) tool:


So, if I can make texconv work with ARchive_neXt we should be able to view those pesky DX10 BC7 normal maps by converting them to DXT5.

> Reply from WeylandYutani
>
> I have Issues importing the arx Files into 3DS Max, Max loads but freezes, i use 2015 so is there anything i miss to do ?

I've come to the conclusion the issue you are having is also due to those pesky DX10 BC7 normal maps.  I use 3DSMax9, but it also crashes when attempting to import a model with one of those normal maps.  At least 3DSMax9 gives me an error message telling me it can't load the normal map.  Once I converted the normal map to DXT5 it loaded fine.

Progress? Maybe.

--MDA
## Post #448
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-18T20:34:16+00:00
- Post Title: Re: ARchive_neXt

Next update we will be able to view all normal maps (along with any other image that is DX10 BC7)



"Export" will still export the proper DX10 BC7 format, I will be adding an "Export As" option to allow these images to be exported as DXT5 format.

Before I release another update, I need to make this work with model exporting.

--MDA
## Post #449
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-19T21:27:01+00:00
- Post Title: Re: ARchive_neXt

Version 3.01.19.0 Now Available! (Link is in my sig)

DX10 Texture Maps are now viewable using texconv (included) to convert them to the DXT5 format.
ARX and OBJ model exports will now export the DXT5 format of any DX10 texture maps.
Fixed an issue where some OBJ material files were not writing the texture maps properly.

--MDA
## Post #450
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-21T00:38:52+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paliha
>
> For example:
1KMA_UI_AttackCrowdDisperion > Material > Unnamed_0000
File ID: 
Resource Type: 
Material Template Reference:  - Not Found
Texture Set Reference:  - Not Found
Unknown Reference:  - Not Found
Unknown Reference:  - Not Found
Material Reference:  - Not Found
 Unknown Count: 0
Maybe that's the problem ?

It took me a while to figure out what you were referencing with this post.  But I have.  I had not created the view material method for all games.  The games that currently works for are AC1, AC2, AC:Brotherhood, AC:Revelations, AC3, and AC3:Liberation.  But don't worry, the program does use the material files and it pulls the necessary information from them when it can find it.  The view material method is separate from the view model method and is not used by the view model method.

However, to keep things consistent, with the next update view material will work with all games.

--MDA
## Post #451
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-01-21T18:03:29+00:00
- Post Title: Re: ARchive_neXt

I wrote that exports to obj, converted fine, but without graphics.The mtl file is empty.And the problem with mesh_viewer not solved.
## Post #452
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-21T19:31:12+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paliha
>
> I wrote that exports to obj, converted fine, but without graphics.The mtl file is empty.

What model are you exporting?

> Reply from Paliha
>
> And the problem with mesh_viewer not solved.

Never said the mesh_viewer problem was solved.  Best reason I can come up with for those of you having that problem is, "It's a hardware issue."

--MDA
## Post #453
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-23T14:10:14+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 
Paliha wrote:And the problem with mesh_viewer not solved.

Never said the mesh_viewer problem was solved.  Best reason I can come up with for those of you having that problem is, "It's a hardware issue."

--MDA

Maybe it's what version of Windows they have? I've noticed that some programs were really buggy in Windows 7 and in Windows 8 (or the opposite) they were just fine. There is also this issue with windows 10 tons of people have since most Directx version just doesn't run on it, except for 12 of course, which leads a lot of programs to not even start up, or giving those 'Object not set to an instance' when it comes to, for example the mesh preview. (I guess there are tons of other errors, but I can't really think of more) 
So it might be a interesting way of figuring out if it's only people having trouble on what version of Windows, although it might be a death lead to the problem. I use Windows 7 64x. As far as I know, my computer doesn't have a hardware issue.

Edit: I'm going to test Assassin's creed 3 to test if the preview is just not working with the latest Assassin's creed games.
## Post #454
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-23T16:42:13+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> Maybe it's what version of Windows they have?
Before it's release I tested ARchive_neXt on the four versions I had available to me.
Windows XP 32-bit - Will not even start
Windows 7 Home 32-bit - Worked (dual-boot PC)
Windows 7 Pro 64-bit - Worked (laptop)
Windows 8 Pro 64-bit - Worked (dual-boot PC, the video on my website was made with this version)

Since then the dual-boot PC has been upgraded from Windows 8 to Windows 8.1 - Worked
That PC has been given to my daughter, built a new PC for myself.
Windows 8.1 Home 64-bit - Worked (New PC, fresh install)
Now both my laptop and my desktop PC have been upgraded to Windows 10 - Both are working with no issues.

I don't believe it is a Windows version problem.

> Reply from Greenplumbbob
>
> As far as I know, my computer doesn't have a hardware issue.
By "hardware issue", I mean more of a difference in our hardware.  Something in the way our PCs are configured could be different, it could even be a difference in software.  Since I can't reproduce the issue, it makes it tough for me to troubleshoot it.

> Reply from Greenplumbbob
>
> Edit: I'm going to test Assassin's creed 3 to test if the preview is just not working with the latest Assassin's creed games.
Unfortunately, I don't think this will be any different.

--MDA
## Post #455
- Username: defaltdobrasao
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 24, 2016 4:44 am
- Post datetime: 2016-01-23T20:55:02+00:00
- Post Title: Re: ARchive_neXt

hello man im costantly visiting this topic waitin for rainbow6 support as i read that u want to add support for it, can u estimate when and if u will do this? thank u so much
## Post #456
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2016-01-23T21:58:05+00:00
- Post Title: Re: ARchive_neXt

Why am i unable to download Archive Next V3.19
## Post #457
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-01-23T22:21:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Greenplumbbob wrote:Maybe it's what version of Windows they have?
Before it's release I tested ARchive_neXt on the four versions I had available to me.
Windows XP 32-bit - Will not even start
Windows 7 Home 32-bit - Worked (dual-boot PC)
Windows 7 Pro 64-bit - Worked (laptop)
Windows 8 Pro 64-bit - Worked (dual-boot PC, the video on my website was made with this version)

Since then the dual-boot PC has been upgraded from Windows 8 to Windows 8.1 - Worked
That PC has been given to my daughter, built a new PC for myself.
Windows 8.1 Home 64-bit - Worked (New PC, fresh install)
Now both my laptop and my desktop PC have been upgraded to Windows 10 - Both are working with no issues.

I don't believe it is a Windows version problem.
Greenplumbbob wrote:As far as I know, my computer doesn't have a hardware issue.
By "hardware issue", I mean more of a difference in our hardware.  Something in the way our PCs are configured could be different, it could even be a difference in software.  Since I can't reproduce the issue, it makes it tough for me to troubleshoot it.
Greenplumbbob wrote:Edit: I'm going to test Assassin's creed 3 to test if the preview is just not working with the latest Assassin's creed games.
Unfortunately, I don't think this will be any different.

--MDA
Like you thought, it didn't work. I did look around Directx's settings but sadly this didn't work either. But I guess with the fact that I bootcamped my computer, is that my specs aren't that great for either gaming or 3D work. And with that, I mean an Intel HD 4000 as graphics card and a Intel i5 as processor. I don't know if there is a compatibility with graphics and all that comes with the program?
## Post #458
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-01-24T01:45:17+00:00
- Post Title: Re: ARchive_neXt

I tried it on another laptop under Win7x64, the result is the same. No handler for Mesh Viewer. Strange, but under the debugger, Microsoft.DirectX.Direct3D.dll loads of the two distributions:
 1.c:\ARchive_neXt\Microsoft.DirectX.Direct3D.dll
 2.c:\WINDOWS\Microsoft.NET\DirectX for Managed Code\
Delete any positive result does not give.
May be better to switch to OpenGL ?
## Post #459
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-24T03:33:01+00:00
- Post Title: Re: ARchive_neXt

> Reply from nav00811
>
> Why am i unable to download Archive Next V3.19

Not sure.  I had a couple people on Facebook tell me they were receiving a 403 Forbidden error when trying to access my website.  If you are having the same issue, PM me and I will send the file to you that way.

--MDA
## Post #460
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-01-24T03:37:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from defaltdobrasao
>
> hello man im costantly visiting this topic waitin for rainbow6 support as i read that u want to add support for it, can u estimate when and if u will do this? thank u so much

Rainbow 6 has changed quite a bit in the forge file format along with file types.  They have very little in common with the AC games.  So it means I'm starting over trying to find files and determine the exact formats.  Be patient as this process takes a little longer.

--MDA
## Post #461
- Username: defaltdobrasao
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 24, 2016 4:44 am
- Post datetime: 2016-01-25T01:58:02+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> defaltdobrasao wrote:hello man im costantly visiting this topic waitin for rainbow6 support as i read that u want to add support for it, can u estimate when and if u will do this? thank u so much  

Rainbow 6 has changed quite a bit in the forge file format along with file types.  They have very little in common with the AC games.  So it means I'm starting over trying to find files and determine the exact formats.  Be patient as this process takes a little longer.

--MDA

aight man nice to see that u already know whats going on
thanks for reply
## Post #462
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2016-02-01T11:53:01+00:00
- Post Title: Re: ARchive_neXt

I had some crash issues in the past, but those seem to be resolved now. Either the newest release did the trick, or I've done something on my pc that got it working...

That said: when I checked out JacobFrye's outfit, I got this: [ [http://imgur.com/a/zckWF](http://imgur.com/a/zckWF) ] (1st picture).
So I asked #MichaelDarkAngel, and he told me I had to simply 'open' all Texture Maps related to this body (below, in the same 'branch'). (resulting in 2nd picture).

Request maybe: is it possible to add a context-sensitive option to 'Get Texture Maps'? Ie to collect that info automatically (where it applies)?
I can understand that you do not want to do this immediately, for load_time's sake.

EDIT:
not to mention the fact that they are not always consistent in their naming convention...! Ah, c'est la vie.

ps: FYI: for testing purposes, I had installed another/prev AC game; which I removed yesterday since the app works fine now. But when I launched it again thereafter, it gave me a crash error (but i could continue). Evt figured out that this was caused by the fact that the 'removed game' entry was still "active" in my preference settings. Disabling/restarting arch_next, and error gone...
For those of you who can't 'continue' in such cases, simply renaming/deleting [prefs.arx] should do it as well.
## Post #463
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-02T04:44:05+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paul44
>
> Request maybe: is it possible to add a context-sensitive option to 'Get Texture Maps'? Ie to collect that info automatically (where it applies)?
I can understand that you do not want to do this immediately, for load_time's sake.

I wish it were that easy.  The texture maps are referenced by file id in the model file.  However, the file id can only be discovered and indexed once the containing datafile is de-compressed.  Unfortunately, I have nothing pointing me to the containing datafile.

--MDA
## Post #464
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-02-05T20:50:52+00:00
- Post Title: Re: ARchive_neXt

So I got really curious if I was opening the models the wrong way after seeing Paul44's post, because that could have been a possibility, of me and other people selecting the mesh wrong. So after only been able to find the exact branch (as seen in Paul44's images) in the DataPC_12_dlc.forge. (The London.forge and any other .forge files only had the mesh but not the textures, unless I would move to another branch where there is only the texture located and not the mesh). 
I opened up what the Texture map said that the mesh needed (except for the average_male_skin) But sadly, after I finally selected the mesh, it still gave me the error:


From there, I just went somewhat deeper into the whole Ezio file itself and took a look at the material (I know this one is really different from the texture set or the maps) But I noticed that the program couldn't find them: 



It's not just with the one I selected, but with every file in the material (of the Ezios file at least). I hope this can help you out getting closer to fixing the problems of the 3D preview. I do enjoy the program though!
## Post #465
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-06T01:36:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> So I got really curious if I was opening the models the wrong way after seeing Paul44's post, because that could have been a possibility, of me and other people selecting the mesh wrong. So after only been able to find the exact branch (as seen in Paul44's images) in the DataPC_12_dlc.forge. (The London.forge and any other .forge files only had the mesh but not the textures, unless I would move to another branch where there is only the texture located and not the mesh). 
I opened up what the Texture map said that the mesh needed (except for the average_male_skin) But sadly, after I finally selected the mesh, it still gave me the error:

It makes no difference what approach you take to open the mesh.  If the model viewer is working you should not get an error.  If you go straight to the mesh and open it you should see a white, texture-less model.  You can then attempt to find and open the datafiles that contain the textures, go back to the mesh, and upon opening it you should now see a textured model.  Or, you could open the texture datafiles first, then open the mesh and it will be textured.  Either way, does not matter.

We (Paul44 and myself), have not come to a definitive conclusion as to what has 'fixed' the issue for him.

> Reply from Greenplumbbob
>
> From there, I just went somewhat deeper into the whole Ezio file itself and took a look at the material (I know this one is really different from the texture set or the maps) But I noticed that the program couldn't find them: 

It's not just with the one I selected, but with every file in the material (of the Ezios file at least). I hope this can help you out getting closer to fixing the problems of the 3D preview. I do enjoy the program though!

The material viewer routine was not completed for every game and has no bearing on whether or not the model viewer routine or export routine finds the textures that are required for a model.  Its only purpose was more for debugging another routine that I was working on.  It will work for all games in the next update.  But you will find that it works much like the model viewer and export routines, in that if you do not open the datafiles containing the textures you will see a lot of "Not Found".

Sorry for the confusion.

--MDA
## Post #466
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-02-06T15:03:31+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 

It makes no difference what approach you take to open the mesh.  If the model viewer is working you should not get an error.  If you go straight to the mesh and open it you should see a white, texture-less model.  You can then attempt to find and open the datafiles that contain the textures, go back to the mesh, and upon opening it you should now see a textured model.  Or, you could open the texture datafiles first, then open the mesh and it will be textured.  Either way, does not matter.

--MDA

I know from exporting and importing my own meshes, it creates a 'none' texture (if I have an option selected, but I guess with other 3D programs it would work the same). But I suppose that can't be the issue here, since Paul44's archive_next suddenly worked the way it should. It could hardly be the problem of me, replacing the program ever time there is a new update. But I've had programs who had stranger ways of fixing. Although I guess it's just the fact that I (and a lot of other people) seem to select it wrong. 

With 'datafile' I take it you mean this branch where you have everything together instead of seperated? Like this:
## Post #467
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-07T18:09:27+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> Although I guess it's just the fact that I (and a lot of other people) seem to select it wrong.
There is no "wrong" way to select.

Maybe this [video](http://www.tbotr.net/videos/ARchive_neXt_006.mp4) will help.

> Reply from Greenplumbbob
>
> With 'datafile' I take it you mean this branch where you have everything together instead of seperated?
[](http://www.tbotr.net/images/ARchive_neXt_010.png)
Click for larger image
A datafile is a compressed chunk of data within the forge file.  Datafiles may contain a single file or multiple files.  In order to determine what file(s) are contained within a given datafile, that datafile must be decompressed first.

> Reply from Greenplumbbob
>
> 
What you have in that image are all required files in the same datafile named AC3_Boston_Fakes.

--MDA
## Post #468
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-02-08T15:45:14+00:00
- Post Title: Re: ARchive_neXt

When following you video, and did exactly the same thing, I noticed when you select the mesh (with or without textures expanded), you'll have this black screen (Which I take it is the command prompt of the program that it's going to be using.) I've seen that 'window' a lot of times when opening whatever normal map with the program, but it doesn't with when I select a mesh the same way you did. I just simply get the error and no second window. I've no idea if it's correct that I have 2 .exe files. One to open the program and the second is Texconv.exe. Do I need to open Archive_next through Command prompt? I guess it doesn't matter if I open it up through Command Prompt or with the actual .exe file.
## Post #469
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-08T20:11:07+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> When following you video, and did exactly the same thing, I noticed when you select the mesh (with or without textures expanded), you'll have this black screen (Which I take it is the command prompt of the program that it's going to be using.) I've seen that 'window' a lot of times when opening whatever normal map with the program, but it doesn't with when I select a mesh the same way you did. I just simply get the error and no second window. I've no idea if it's correct that I have 2 .exe files. One to open the program and the second is Texconv.exe.
The black screen you see flashing is texconv.exe running to convert any DX10 dds textures into a useable DXT dds texture.  You don't see it happen when you attempt to view a model because the model viewer crashes before it gets to the point where it needs to convert those textures.

> Reply from Greenplumbbob
>
> Do I need to open Archive_next through Command prompt? I guess it doesn't matter if I open it up through Command Prompt or with the actual .exe file.
No.  You can start ARchive_neXt from the desktop shortcut, from the start menu, or from the ARchive_neXt.exe.  You do not need to do anything special.

--MDA
## Post #470
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-09T02:40:50+00:00
- Post Title: Re: ARchive_neXt

Version 3.02.07.0 Now Available! (Link is in my sig)

Fixes an issue where some exported MTL files were referencing textures improperly.

--MDA
## Post #471
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-09T03:36:07+00:00
- Post Title: Re: ARchive_neXt

I should also mention in regards to the latest release, there is a new mesh type (Softbody Mesh).  I haven't finished working out all the details of this type yet.  For the games I have gotten the farthest, you will see a screen much like the image below:

[](http://www.tbotr.net/images/ARchive_neXt_011.png)
Click for larger image

See that button that says "3D View".  Save your self some time and don't press it.  Nothing happens if you do press it, however, when trying to move on to something else after pressing it will throw an unhandled exception.  It's trying to dispose of a 3D view that was never created.  Not a big problem, just an annoying one.

When I was fixing the OBJ MTL export issue, I had forgotten that I wasn't finished with this mesh type yet.

Sorry for the annoyance.

--MDA
## Post #472
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2016-02-09T20:44:30+00:00
- Post Title: Re: ARchive_neXt

@Greenplumbbob: following is a 'sum up' of things I had done recently (in January). The problem is I can not determine what actually solved the crashing. If you plan to try this out, then do this step per step, reboot, rename/delete your [prefs.arx] and then run the program. and so on...
Before installing the latest vs, uninstall your current vs (just to be sure).

Summary (sofar):

Windows 7 x64 fully updated (something I do monthly normally)
-------------
I noticed I still had a prev vs of arch_next (v2.xx?); downloaded Dec last year. (forgot to note down exact vs).
Anyways: decided to reinstall/test that vs, and indeed I got errors again. Updated to current 3.1.x vs and everything is fine...
-------------
ASUS GPU TweakII (nvidia tweak tool):
installed pretty recently?! (jan). can't imagine, but maybe it added/updated some specific dll.
(did some minor testing with it, but had everything reset to default at the end)
-------------
- MS VC++ 2005-2008-2010-2012-2013 (x86 & x64)
- MS .NET fw 4.6
(all updated ~ but that was already the case as far as I can remember)
-------------
It does not seem to be the nvidia driver.
Uninstalled it completely (nvidia uninstaller guru3d), ran program with default vga giving crash, then installed nVidea v355.82_x64 (vs that definitely gave crash issues), and arch_next just works nicely..
-------------
[ [http://www.sereby.org/site/AiO](http://www.sereby.org/site/AiO) ]: ie update all vc/directx/.net (if needed)
(I believe that i tried this as well with arch_next already, but not sure - only those 3 options; ignored the rest. Fe: i do not have Java installed... at all)
-------------
I also recollect "forcing" to reinstall DirectX9: you need to edit the registry, but I do not remember the exact details...


Good luck.
## Post #473
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-02-10T18:31:43+00:00
- Post Title: Re: ARchive_neXt

> Reply from Paul44
>
> 

Summary (sofar):

Windows 7 x64 fully updated (something I do monthly normally)
-------------
I noticed I still had a prev vs of arch_next (v2.xx?); downloaded Dec last year. (forgot to note down exact vs).
Anyways: decided to reinstall/test that vs, and indeed I got errors again. Updated to current 3.1.x vs and everything is fine...
-------------
ASUS GPU TweakII (nvidia tweak tool):
installed pretty recently?! (jan). can't imagine, but maybe it added/updated some specific dll.
(did some minor testing with it, but had everything reset to default at the end)
-------------
- MS VC++ 2005-2008-2010-2012-2013 (x86 & x64)
- MS .NET fw 4.6
(all updated ~ but that was already the case as far as I can remember)
-------------
It does not seem to be the nvidia driver.
Uninstalled it completely (nvidia uninstaller guru3d), ran program with default vga giving crash, then installed nVidea v355.82_x64 (vs that definitely gave crash issues), and arch_next just works nicely..
-------------
[ http://www.sereby.org/site/AiO ]: ie update all vc/directx/.net (if needed)
(I believe that i tried this as well with arch_next already, but not sure - only those 3 options; ignored the rest. Fe: i do not have Java installed... at all)
-------------
I also recollect "forcing" to reinstall DirectX9: you need to edit the registry, but I do not remember the exact details...


Good luck.

Thanks for the post! I tried it out as fast as I saw the post. Here is what I did:

- I, also update Windows 7 every month so this wouldn't be the issue

- I keep re-installing every new version of the program, and I even reinstalled it again, I also uninstalled it with the program and then reinstalled it.

- I don't own a Nvidia card or anything Nvidia (I'll have one in my new computer, but that's going to take a while). So I wasn't being able to test out the tweak tool... it looked interesting though! Kind of reminded me of Cortex Razer, but they both are really different. 

-I noticed the link you gave me had already these updates in them, so what I did was installed the necessary things, as MS VC++ (All of them, although it seemed that I didn't had 2015 at first, but that one didn't seem to be the case). I installed MS .NET fw 4.6.1. I've no idea if the '1' is a problem, but I thought it's better to have it up-to-date. But everything except for the MS VC++ 2015 seemed to be up-to-date.

- I literally re-installed my Drivers again (worst decision ever, as my screen was all messed up and had to restart in order to fix that so I could install it again.) But this time I installed a somewhat older update. My computer is basically all Intel, due the fact that I bootcamped it. So it's orignally a mac. Anyway, I updated it to a earlier version, because when I used Archive_next with the latest driver update and I wanted to see if that could have been the case.

- Same here! Don't have Java installed as well. But I guess Java isn't really needed when it comes to programs like Archive_next. I was also lucky that I can read a little bit of German, else I wouldn't have figured out what to do. 

- I went searching for the Directx 9 reinstalling, and they mentioned I had to restore my system to when I didn't had Directx 9 on my computer. I wasn't going to take that risk because the Directx versions were the first thing I installed when I just bootcamped my computer to windows. But I found a site that told me to delete the folder in the registry (which wasn't the first time doing so, since I had to do the similar thing with other installed programs before.) So I did that correctly as well. 

And with all that done, I restarted my computer after every update or installed program that was needed. Also with programs that didn't ask to restart my computer, like Directx. Now the error that it always gives me (which was first a driver error because I didn't had my drivers installed to see if it mattered, but it did.):

************** Exception Text **************
System.NullReferenceException: Object reference not set to an instance of an object.
   at ARchive_neXt.arxForm.arxDrawMesh()
   at ARchive_neXt.arxForm.OnPaint(PaintEventArgs e)
   at System.Windows.Forms.Control.PaintWithErrorHandling(PaintEventArgs e, Int16 layer)
   at System.Windows.Forms.Control.WmPaint(Message& m)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ContainerControl.WndProc(Message& m)
   at System.Windows.Forms.Form.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
ARchive_neXt
    Assembly Version: 3.2.7.0
    Win32 Version: 3.02.07.0
    CodeBase: file:///C:/Program%20Files%20(x86)/TBotR/ARchive_neXt/ARchive_neXt.exe
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
Microsoft.DirectX
    Assembly Version: 1.0.2902.0
    Win32 Version: 5.04.00.2904
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.DirectX/1.0.2902.0__31bf3856ad364e35/Microsoft.DirectX.dll
----------------------------------------
Microsoft.DirectX.Direct3D
    Assembly Version: 1.0.2902.0
    Win32 Version: 9.05.132.0000
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.DirectX.Direct3D/1.0.2902.0__31bf3856ad364e35/Microsoft.DirectX.Direct3D.dll
----------------------------------------
Microsoft.DirectX.Direct3DX
    Assembly Version: 1.0.2911.0
    Win32 Version: 9.12.589.0000
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.DirectX.Direct3DX/1.0.2911.0__31bf3856ad364e35/Microsoft.DirectX.Direct3DX.dll
----------------------------------------
Accessibility
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/Accessibility/v4.0_4.0.0.0__b03f5f7f11d50a3a/Accessibility.dll
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1067.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
ArchiveX
    Assembly Version: 2.9.7.0
    Win32 Version: 2.09.07.0
    CodeBase: file:///C:/Program%20Files%20(x86)/TBotR/ARchive_neXt/ArchiveX.DLL
----------------------------------------
FreeImageNET
    Assembly Version: 3.11.0.0
    Win32 Version: 3.11.0.0
    CodeBase: file:///C:/Program%20Files%20(x86)/TBotR/ARchive_neXt/FreeImageNET.DLL
----------------------------------------
Microsoft.VisualC
    Assembly Version: 10.0.0.0
    Win32 Version: 12.00.52512.0 built by: VSWINSERVICING
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualC/v4.0_10.0.0.0__b03f5f7f11d50a3a/Microsoft.VisualC.dll
----------------------------------------

Now I know this error appears because it can't load the textures, as someone ever mentioned before. But maybe it's a bit helpful.
## Post #474
- Username: mustafasahinfb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 23, 2015 9:22 pm
- Post datetime: 2016-02-13T14:08:41+00:00
- Post Title: Re: ARchive_neXt

Last version fantastic    "search button" please
## Post #475
- Username: Kjasi
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 11, 2012 8:50 am
- Post datetime: 2016-02-14T05:53:33+00:00
- Post Title: Re: ARchive_neXt

Actually, I have a (I think) simple suggestion. On any parent item in the tree list, right-click->Load Children.

It opens up every tree item under the selected item. Load children on a .forge file? It loads all the files from that forge file. Load Children from a skeleton parent? It loads all the skeletons in that folder.

That will make a number of people happy, without forcing everyone to load an entire forge file if they don't want to.
## Post #476
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-14T15:29:26+00:00
- Post Title: Re: ARchive_neXt

> Reply from mustafasahinfb
>
> Last version fantastic    "search button" please
With the way ARchive_neXt works, a "Search Button" is extremely limited.

> Reply from Kjasi
>
> Actually, I have a (I think) simple suggestion. On any parent item in the tree list, right-click->Load Children.

It opens up every tree item under the selected item. Load children on a .forge file? It loads all the files from that forge file. Load Children from a skeleton parent? It loads all the skeletons in that folder.

That will make a number of people happy, without forcing everyone to load an entire forge file if they don't want to.
The only benefit to this would be on the forge file branch.  Once you open any branch within a forge file branch that expands the datafile and indexes all files within.  And that benefit can be extremely time consuming.

--MDA
## Post #477
- Username: ostrov88
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 16, 2016 10:25 pm
- Post datetime: 2016-02-20T07:40:32+00:00
- Post Title: Re: ARchive_neXt

Hello
Win 7 
3d view don't work
## Post #478
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-20T18:40:48+00:00
- Post Title: Re: ARchive_neXt

> Reply from ostrov88
>
> Hello
Win 7 
3d view don't work

It is a known issue that has yet to be solved.  You can still export the model without a problem.

--MDA
## Post #479
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-20T23:32:10+00:00
- Post Title: Re: ARchive_neXt

Do you plan to support Rainbow Six Siege?

Cheers.
## Post #480
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-21T04:49:37+00:00
- Post Title: Re: ARchive_neXt

> Reply from Gh0stBlade
>
> Do you plan to support Rainbow Six Siege?

Still working on it.

--MDA
## Post #481
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-02-22T15:35:57+00:00
- Post Title: Re: ARchive_neXt

So I took a break on trying to figure out to get the 3D viewer and went working with other programs who are a bit like this one, but just for other games, and I came to realise that the programs who were made with some "wrapper" Happen to give me errors or just doesn't open at all when it comes to 3D viewers, so I guess I'm either missing some sort of update and might be the problem instead of the program itself. So I'm going to look somewhat deeper into any 3D helping updates like DirectX and will give some feedback if I found an update that is required for any 3D viewing programs.
## Post #482
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-02-23T01:05:43+00:00
- Post Title: Re: ARchive_neXt

> Reply from Greenplumbbob
>
> So I took a break on trying to figure out to get the 3D viewer and went working with other programs who are a bit like this one, but just for other games, and I came to realise that the programs who were made with some "wrapper" Happen to give me errors or just doesn't open at all when it comes to 3D viewers, so I guess I'm either missing some sort of update and might be the problem instead of the program itself. So I'm going to look somewhat deeper into any 3D helping updates like DirectX and will give some feedback if I found an update that is required for any 3D viewing programs.
I do have the following listed as a requirement on the download page for ARchive_neXt
[DirectX June 2010 Redistributable Runtime](http://www.microsoft.com/en-us/download/details.aspx?id=8109)

--MDA
## Post #483
- Username: Greenplumbbob
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 16, 2016 5:07 am
- Post datetime: 2016-02-25T10:54:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 
I do have the following listed as a requirement on the download page for ARchive_neXt
DirectX June 2010 Redistributable Runtime

--MDA

After installing this version of DirectX, it did took some time to load instead of immediately ending up with the error, but sadly it still gives me the error. Is there any other software that needs to be used besides NET framework 4.5 and DirectX June 2010 Redistributable Runtime?
## Post #484
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-02-26T20:50:27+00:00
- Post Title: Re: ARchive_neXt

@Greenplumbbob

This is false, initialization of a class Viewer3D may occur more than once, and maybe somehow connected with the localization of the operating system. While the author does not switch to OpenGL there will be no progress.
## Post #485
- Username: Moonscapes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 21, 2016 3:04 pm
- Post datetime: 2016-03-21T22:00:08+00:00
- Post Title: Re: ARchive_neXt

o
## Post #486
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-04-12T10:15:49+00:00
- Post Title: Re: ARchive_neXt

I have an issue with the normal maps extraction. I've got the latest ARchive_neXt and my DirectX is updated, but whenever I try to save a normal map using the DX10 to DX5 option I get an error message, which says it can't export the texture 'cause the normal map cannot be found. I still see the Bad Image preview too.

Also, I think there is a problem with DLC Jack The Ripper. Jacob's textures seem to be bad? Not sure if it's just me.
## Post #487
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-04-17T19:15:43+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> I have an issue with the normal maps extraction. I've got the latest ARchive_neXt and my DirectX is updated, but whenever I try to save a normal map using the DX10 to DX5 option I get an error message, which says it can't export the texture 'cause the normal map cannot be found. I still see the Bad Image preview too.

1. Verify that you are using the latest version (3.2.7.0) -- Click About in the main menu.
2. Is this something that just started happening, or has it always happened.

Unfortunately, I cannot reproduce this issue.

> Reply from RunaWhite
>
> Also, I think there is a problem with DLC Jack The Ripper. Jacob's textures seem to be bad? Not sure if it's just me.

Can you give me a specific texture to look at?

Thanks for your help,

--MDA
## Post #488
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-04-18T10:33:00+00:00
- Post Title: Re: ARchive_neXt

> 1. Verify that you are using the latest version (3.2.7.0) -- Click About in the main menu.

I just checked to be sure and my version is indeed the 3.2.7.0... so I don't really know what's going on. 

> 2. Is this something that just started happening, or has it always happened.

I can't tell because this is my first try. I didn't need to extract normal maps until this moment.

> Can you give me a specific texture to look at?

Sure! One of the problematic diffuse textures is in dlc_21, ACVI_DLC_CHR_P_JacobFrye_Head_DiffuseMap. However every Jacob texture seems to have the same issue. This is how it looks:



> Thanks for your help

Thank YOU for the tool and everything
## Post #489
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-04-19T06:28:47+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> 1. Verify that you are using the latest version (3.2.7.0) -- Click About in the main menu.

I just checked to be sure and my version is indeed the 3.2.7.0... so I don't really know what's going on. 
2. Is this something that just started happening, or has it always happened.

I can't tell because this is my first try. I didn't need to extract normal maps until this moment.
I'm going to try a couple of things to see if I can make the error happen.


> Reply from RunaWhite
>
> Can you give me a specific texture to look at?

Sure! One of the problematic diffuse textures is in dlc_21, ACVI_DLC_CHR_P_JacobFrye_Head_DiffuseMap. However every Jacob texture seems to have the same issue.
Just wanted to be sure we were looking at the same textures.  That looks like a split texture issue.  If the DLC isn't doing things the same as the main game, I'll need to do some digging to see if I can find the other half of the texture file.

Thanks

--MDA
## Post #490
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2016-04-21T06:37:03+00:00
- Post Title: Re: ARchive_neXt

Hi
How To decompersing this file with lzo ? (file from Rainbow Six Siege)
I can then write to the header file manually dds
Thanks
[W_SA_CLASSIC586_NormalMap_PC_CHRTM.rar](https://xentaxbackup.github.io/file/10809_W_SA_CLASSIC586_NormalMap_PC_CHRTM.rar)
## Post #491
- Username: defaltdobrasao
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 24, 2016 4:44 am
- Post datetime: 2016-05-08T16:15:55+00:00
- Post Title: Re: ARchive_neXt

Hello there i wrote here some times ago asking for r6 siege support, are still some chanche that you make this for your application? I tried to put some forge from r6 to an ac game folder and of course i got crash but there are a lot of file that has been automatically discovered from the tool(i see a lot of maps mesh)
## Post #492
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-05-12T19:25:44+00:00
- Post Title: Re: ARchive_neXt

Hello MichaelDarkAngel,

I wonder is there bone or weight support in ARchive_neXt?

thanks
## Post #493
- Username: Moonscapes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 21, 2016 3:04 pm
- Post datetime: 2016-05-15T20:08:53+00:00
- Post Title: Re: ARchive_neXt

Do you know if the Bloofer Lady Outfit is able to be extracted yet?
## Post #494
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-05-30T19:05:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from defaltdobrasao
>
> Hello there i wrote here some times ago asking for r6 siege support, are still some chanche that you make this for your application? I tried to put some forge from r6 to an ac game folder and of course i got crash but there are a lot of file that has been automatically discovered from the tool(i see a lot of maps mesh)

I do plan to eventually add R6 support, but have recently taken a break from ARchive_neXt to pursue other things.  I can't give a specific date for coming back to this, but rest assured, I will come back to it.

--MDA
## Post #495
- Username: Tosyk
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-05-30T19:10:45+00:00
- Post Title: Re: ARchive_neXt

> Reply from Tosyk
>
> Hello MichaelDarkAngel,

I wonder is there bone or weight support in ARchive_neXt?

thanks

Short answer: Yes and No.

Longer answer: Bones and weights have been figured out for the earlier game(s).  The later games changed the format and have yet to be determined.  Because of that, I haven't yet written any kind of support into the export routine.

--MDA
## Post #496
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-05-30T19:11:52+00:00
- Post Title: Re: ARchive_neXt

> Reply from Moonscapes
>
> Do you know if the Bloofer Lady Outfit is able to be extracted yet?

Not familiar with this model.  Which game is it from?

--MDA
## Post #497
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-05-30T20:49:08+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Tosyk wrote:Hello MichaelDarkAngel,

I wonder is there bone or weight support in ARchive_neXt?

thanksShort answer: Yes and No.

Longer answer: Bones and weights have been figured out for the earlier game(s).  The later games changed the format and have yet to be determined.  Because of that, I haven't yet written any kind of support into the export routine.

--MDAthanks for reply!
is there a way to load bone and weights in 3ds max with ARchive_neXt atm? even for earlier game(s).
## Post #498
- Username: defaltdobrasao
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 24, 2016 4:44 am
- Post datetime: 2016-06-01T12:12:42+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> defaltdobrasao wrote:Hello there i wrote here some times ago asking for r6 siege support, are still some chanche that you make this for your application? I tried to put some forge from r6 to an ac game folder and of course i got crash but there are a lot of file that has been automatically discovered from the tool(i see a lot of maps mesh)

I do plan to eventually add R6 support, but have recently taken a break from ARchive_neXt to pursue other things.  I can't give a specific date for coming back to this, but rest assured, I will come back to it.

--MDA

glad to hear that as you are the only one that can mess with this anvil stuffs
thank u for reply
## Post #499
- Username: ClockworkAssassin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 22, 2016 5:56 am
- Post datetime: 2016-06-21T22:07:00+00:00
- Post Title: Re: ARchive_neXt

Hello
I'm trying to extract some models and textures from assassins creed and I got this issue too

> Reply from ostrov88
>
> 
3d view don't work

Any chance of a solution for the 3d model viewer issue?

EDIT
And I got some "corrupt" dds files I cannot export and I need them. Is it something related to game files or something with the exporter?
All i see is messed up textures with those, like multiple layers of it and a small useless low res sqyare at the bottom of it that looks like the shape of the intended texture
## Post #500
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2016-06-25T07:00:16+00:00
- Post Title: Re: ARchive_neXt

Hi Michael!
I asked like 10000 times, but this is 10001.
Will you add support for Data360.forge files? I need to get textures from Just Dance 3. I don't care about replacing them, I just need to extract.
## Post #501
- Username: muserigtc
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Jul 16, 2016 9:44 pm
- Post datetime: 2016-07-30T18:55:57+00:00
- Post Title: Re: ARchive_neXt

Can you update tools feature is Localization Package Unpacker and Repacker to Forge files......
I make Translation Subtitles....

Sorry For Bad English...
## Post #502
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-07-31T11:56:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from muslimcyberbjb
>
> Can you update tools feature is Localization Package Unpacker and Repacker to Forge files......
I make Translation Subtitles....

Sorry For Bad English...
Try to contact this guy: [saidsrc@gmail.com](mailto:saidsrc@gmail.com) He has tools for unpack/repack assassins creed text files.
## Post #503
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-08-05T16:41:49+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Moonscapes wrote:Do you know if the Bloofer Lady Outfit is able to be extracted yet?

Not familiar with this model.  Which game is it from?

--MDA
it's an outfit form AC Syndicate
## Post #504
- Username: NinjaNub
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 29, 2014 11:25 pm
- Post datetime: 2016-08-08T14:21:21+00:00
- Post Title: Re: ARchive_neXt

is it possible to use this tool with rainbow six siege? i've tried to set up the folders, but the field for siege is grayed out for whatever reason
## Post #505
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-08-08T18:36:26+00:00
- Post Title: Re: ARchive_neXt

> Reply from NinjaNub
>
> is it possible to use this tool with rainbow six siege? i've tried to set up the folders, but the field for siege is grayed out for whatever reason

It's been said he will add support, but it's been nearly a year now, so no idea if it's ever really coming.
## Post #506
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2016-08-30T04:13:17+00:00
- Post Title: Re: ARchive_neXt

Anyone extracted the tower of london pier mesh yet? I'd be interested in the names of all of those things if you wouldn't mind sharing.
## Post #507
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-09-11T12:44:44+00:00
- Post Title: Re: ARchive_neXt

Does this work with Rainbow Six: Siege?
## Post #508
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-09-11T12:45:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from volfin
>
> NinjaNub wrote:is it possible to use this tool with rainbow six siege? i've tried to set up the folders, but the field for siege is grayed out for whatever reason

It's been said he will add support, but it's been nearly a year now, so no idea if it's ever really coming.
Nvm I guess that answers it.
## Post #509
- Username: Moonscapes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 21, 2016 3:04 pm
- Post datetime: 2016-10-19T04:17:22+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Moonscapes wrote:Do you know if the Bloofer Lady Outfit is able to be extracted yet?

Not familiar with this model.  Which game is it from?

--MDA

Yes it's from AC Syndicate in the Victorian Legends Pack. Do you know if it will be possible to extract?

Thank you if you reply.
## Post #510
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2016-10-22T19:33:50+00:00
- Post Title: Re: ARchive_neXt

> Reply from Moonscapes
>
> Yes it's from AC Syndicate in the Victorian Legends Pack. Do you know if it will be possible to extract?

Thank you if you reply.

On my machine...

Assassin's Creed Syndicate->dlc_11->DataPC_11_dlc.forge->ACVI_CHR_P_EvieFrye_Outift12_Body_LOD0->Mesh->ACVI_CHR_P_EvieFrye_Outfit12_Body_LOD0

From there you can extract the main body mesh.  Use the Outfit12 LOD0 branches to extract some of the accessory meshes.  Textures, unfortunately are a little harder to find, and will most likely take you the longest to accomplish using a trial-and-error method.  Open a texture branch and then open the model to see if that particular texture was applied.

--MDA
## Post #511
- Username: Moonscapes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 21, 2016 3:04 pm
- Post datetime: 2016-10-25T00:19:45+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Moonscapes wrote:Yes it's from AC Syndicate in the Victorian Legends Pack. Do you know if it will be possible to extract?

Thank you if you reply.

On my machine...

Assassin's Creed Syndicate->dlc_11->DataPC_11_dlc.forge->ACVI_CHR_P_EvieFrye_Outift12_Body_LOD0->Mesh->ACVI_CHR_P_EvieFrye_Outfit12_Body_LOD0

From there you can extract the main body mesh.  Use the Outfit12 LOD0 branches to extract some of the accessory meshes.  Textures, unfortunately are a little harder to find, and will most likely take you the longest to accomplish using a trial-and-error method.  Open a texture branch and then open the model to see if that particular texture was applied.

--MDA

I hate to ask this since I know you'll probably say no, but could you possibly do it for me? I would do it, but I actually don't have any of the games installed, so I can't exactly get to the files.

Please respond, despite saying no though, just so I know!

Thank you.
## Post #512
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2016-11-10T02:52:50+00:00
- Post Title: Re: ARchive_neXt

I have this troubles too.
Can't preview any models from any game (tryed ACBF and AC Rogue)
I can give you any info if it could help you to resolve it.

> Reply from Paliha
>
> RunaWhite wrote:

Does that happen with every model you try to load? 

======
Yes, in all games the review of the model fails. System.NullReferenceException - this is not a bug of the OS, this is a programming error. Either a pointer to the identifier of the UserControll where something is duplicated or missing initialization of this component.
RunaWhite wrote:
Because I never had that issue with AC4, AC3, nor Unity.

I'm happy for You...))) Then I have a lot of questions for my OS...))
## Post #513
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2016-11-14T09:17:12+00:00
- Post Title: Re: ARchive_neXt

So I'm back again, last time I was looking for a certain asset in the game; a wooden pillar.

Someone was nice enough to find me the texture that it used, but I've been looking for around 3-4 months now for the actual pillar mesh, to no avail. I ended up making my own version of the mesh, in an attempt to reverse engineer a few things in the game.

Mine; 



What I'm trying to find in the files;

Bottom part



Upper part
## Post #514
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2016-11-15T10:22:49+00:00
- Post Title: Re: ARchive_neXt

I get the horrible sense that this topic is dead / dying, nowadays.. That would be a shame indeed, there's no other way or method of retrieveing game assets from ubisoft.
## Post #515
- Username: mikemanj2
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Nov 18, 2015 10:39 am
- Post datetime: 2016-11-15T12:54:53+00:00
- Post Title: Re: ARchive_neXt

I've come to the conclusion that most of the VIL_Int files are missing, I gather that Vil_int is the cafetheatre in game, where you save your games and train your assassin, every thing in that building is stored under one header, and that's Vil_int, I've checked all the celldatablocks, no mention of a vil_int in anything other than DataPC_ACU_Paris_assets.forge.

If anyone can help with this, I'd be very greatful and willing to help you in whatever way I can as well.
## Post #516
- Username: nixa3d
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 23, 2016 4:05 am
- Post datetime: 2016-12-15T10:02:59+00:00
- Post Title: Re: ARchive_neXt

Hello I have a problem, big problem for me... I tried extract objects about Notre Dame Paris with the files LOD0, but the floors uppers ( 2º & 3ª floor and the towerbell) is not LOD0, how i can extract this files? I searched for all forge files ( is a hard work) and don¨t find objects about this one.
Please i need your help for finissed this cathedral, Either i can´t to see the graphics 3D in the viewer, i think is for my obsolete card graphic Quadro 4000. sorry for my bad english.
Thanks for all
[captura Xentax.jpg](https://xentaxbackup.github.io/file/12058_captura Xentax.jpg)
## Post #517
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-12-20T14:35:17+00:00
- Post Title: Re: ARchive_neXt

> Reply from mikemanj2
>
> I get the horrible sense that this topic is dead / dying, nowadays.. That would be a shame indeed, there's no other way or method of retrieveing game assets from ubisoft.

Extracting assets from these games is really complicated for the way they are structured. If you didn't get the answers you were looking for, chances are nobody knows how to help you. I would love to get some AC sceneries, but I don't even bother considering how hard it is to find the right textures
## Post #518
- Username: nixa3d
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 23, 2016 4:05 am
- Post datetime: 2016-12-22T11:42:22+00:00
- Post Title: Re: ARchive_neXt

Many thanks Runawhite, at least someone has been able to answer me after a long time.
If the internal architecture is very complicated. pity. I wanted to finish this wonderful cathedral
See if a new version of ArchNext is possible?
Thanks again
## Post #519
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-01-01T20:08:28+00:00
- Post Title: Re: ARchive_neXt

I don't think a new version would fix that, not if this is how the AC games are made.

Btw just a little OT to wish you all a Happy New Year.
## Post #520
- Username: romanilyin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 29, 2015 11:54 pm
- Post datetime: 2017-01-10T08:05:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from ostrov88
>
> Hello
Win 7 
3d view don't work

Hello. I have same error.
AC:syndicate
wn10 x64
dx runtime installed
## Post #521
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-01-10T14:18:39+00:00
- Post Title: Re: ARchive_neXt

> Reply from romanilyin
>
> ostrov88 wrote:Hello
Win 7 
3d view don't work


Hello. I have same error.
AC:syndicate
wn10 x64
dx runtime installed

This happens to a lot of people, but the models can still be exported.
## Post #522
- Username: romanilyin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 29, 2015 11:54 pm
- Post datetime: 2017-01-10T14:28:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> This happens to a lot of people, but the models can still be exported.
Hello. Could you please explain how can I export models? I can export textures and materials. App crashes If I select any mesh.
How could I help to fix this errorr? Could I send logs with problem or smth else?
## Post #523
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-01-11T11:51:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from romanilyin
>
> RunaWhite wrote:This happens to a lot of people, but the models can still be exported.
Hello. Could you please explain how can I export models? I can export textures and materials. App crashes If I select any mesh.
How could I help to fix this errorr? Could I send logs with problem or smth else?

For me it works simply pressing OK on that error message and then right-clicking over the mesh > Export As (OBJ). Not sure why/when your program crashes...
## Post #524
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2017-01-28T13:59:22+00:00
- Post Title: Re: ARchive_neXt

it looks like For Honor is using the Anvil Next engine too. did anyone try using this tool on the game. there's a beta version online on right now.
## Post #525
- Username: OriginOfWaves
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-01-31T01:54:10+00:00
- Post Title: Re: ARchive_neXt

> Reply from OriginOfWaves
>
> it looks like For Honor is using the Anvil Next engine too. did anyone try using this tool on the game. there's a beta version online on right now.

Much like Rainbow Six Siege, For Honor's format is slightly different.  Different enough that you will not be able to find out any more than the datafile names.

I am currently working on it, along with RSS as well (the two are as similar to each other as they are different from AC games).  I have no idea how long this will take.  The time I can put in to this is limited right now.

--MDA
## Post #526
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2017-02-04T10:55:50+00:00
- Post Title: Re: ARchive_neXt

It looks like Ghost Recon: Wildlands is using the same engine too and there is a closed beta version online this weekend.
I was able to open it's files (tried Asssassin's Creed: Unity) but there is a problem with extracting textures.
## Post #527
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-02-04T18:20:52+00:00
- Post Title: Re: ARchive_neXt

I missed the beta registration, I'll have to keep watching this one to see if they offer it again.
## Post #528
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-02-04T21:33:15+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> I missed the beta registration, I'll have to keep watching this one to see if they offer it again.
Hey,
i can invite you to the beta on PC, would that help?
## Post #529
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-02-04T22:07:50+00:00
- Post Title: Re: ARchive_neXt

Thanks to Lord Vaako, I have been invited and now have the necessary files.  That now gives me three games to attempt adding to ARchive_neXt.

Hopefully I'll have some updates soon.
## Post #530
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-02-04T22:42:04+00:00
- Post Title: Re: ARchive_neXt

Thank You for your hard work ><
## Post #531
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-02-11T20:57:28+00:00
- Post Title: Re: ARchive_neXt

^^^ I agree with Crofty. Thank you indeed MDA!
## Post #532
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-02-11T23:55:58+00:00
- Post Title: Re: ARchive_neXt

For years people have asked for the ability to search in ARchive_neXt. For a search to work to the best of its ability, it needs a comprehensive and complete index. That isn't possible with ARchive_neXt due to the way it accesses the forge files.

Well, I've spent the past week or so, indexing every resource in every forge file from every game I have on my hard drive.

Here are the stats:
Assassin's Creed - 532,632 resources
Assassin's Creed II - 627,530 resources
Assassin's Creed:Brotherhood - 1,019,422 resources
Assassin's Creed:Revelations - 841,260 resources
Assassin's Creed III - 1,375,186 resources
Assassin's Creed IV:Black Flag - 1,564,511 resources
Assassin's Creed:Liberation - 352,484 resources
Assassin's Creed:Rogue - 1,110,497 resources
Assassin's Creed:Unity - 3,289,299 resources
Assassin's Creed:Syndicate - 5,992,260 resources
For Honor (Beta): 348,800 resources
Ghost Recon:Wildlands (Beta) - 1,056,301 resources
Prince of Persia - 235,517 resources
Prince of Persia:The Forgotten Sands - 366,441 resources
Rainbow Six Siege (Beta) - 203,609 resources

Now, I can get back to building in support for the three new games.
## Post #533
- Username: striking
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-02-12T13:41:13+00:00
- Post Title: Re: ARchive_neXt

I managed to extract the Rainbow Six Siege .forge archives yesterday.



Characters are not stored as one model, they're split.

Cheers.
## Post #534
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-02-14T14:50:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from Gh0stBlade
>
> I managed to extract the Rainbow Six Siege .forge archives yesterday.



Characters are not stored as one model, they're split.

Cheers.
:O Can you get any models?
## Post #535
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-02-17T14:01:02+00:00
- Post Title: Re: ARchive_neXt

> Reply from Kjasi
>
> I've severely updated my PHP converter. I've attached my files, and uploaded them to my website for online testing: http://acreed.kjasi.com/. This site will always use my latest code. Should I start a bitbucket for this converter? Let me know.

I think I've gotten the converter as best I can get it. I'm seeing some shapes in the bones that resemble humans, meaning I've got some, if not all, of the position data correct. (Rotation issues aside) However, most of it is still a mess, as illustrated here:

[im]http://i.imgur.com/F8fP9Yj.gif[/img]

Unless I'm mistaken, this means there are still some flaws in the original matrix data as retrieved by Archive Next. We'll have to wait for MDA to get a new update done before I can proceed too much more...

Edit: Updated, 2015-09-15:
- Can now adjust the matrix conversion dynamically on the page.

Edit2: Updated, 2015-10-01:
- Formulas can now be updated dynamically. NOTE: I've tried to make this as safe as possible, but a clever hacker might still be able to get in. Use caution if using on a live server.

Which program are you using
## Post #536
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-02-17T14:54:31+00:00
- Post Title: Re: ARchive_neXt

Hi, I would like to remind forum users that spamming/flooding this forum is against our rules. As a result, some posts were removed.

Cheers.
## Post #537
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-02-17T22:06:22+00:00
- Post Title: Re: ARchive_neXt

Can anyone confirm?  Does Steep use forge file archives?

Thanks
## Post #538
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-02-17T23:02:18+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Can anyone confirm?  Does Steep use forge file archives?

Thanks
[https://steamdb.info/depot/550041/](https://steamdb.info/depot/550041/)
## Post #539
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2017-02-19T23:48:48+00:00
- Post Title: Re: ARchive_neXt

ghost recon: wildlands open beta this week 

[http://ghostrecon.com/beta](http://ghostrecon.com/beta)
## Post #540
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-24T00:50:57+00:00
- Post Title: Re: ARchive_neXt

Any chance of ARchive_neXt being able to extract other filetypes (from Wildlands) as well? Just dumping them as binary file would probably suffice, ideally I wonder if they can be translated by a process similar to Far Cry's Dunia tools or Watchdogs' WDextractor.
## Post #541
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-02-24T01:23:37+00:00
- Post Title: Re: ARchive_neXt

> Reply from bouvrie
>
> Any chance of ARchive_neXt being able to extract other filetypes (from Wildlands) as well? Just dumping them as binary file would probably suffice, ideally I wonder if they can be translated by a process similar to Far Cry's Dunia tools or Watchdogs' WDextractor.

Much like the other games, everything inside the forge files will be exportable in some format.  Which basically means, for the majority of the files it will be a binary dump with whatever Ubisoft header that might be attached.
## Post #542
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-24T06:51:04+00:00
- Post Title: Re: ARchive_neXt

Great! Was not sure of that, based on the first post. I'm curious to see the Wildlands files!
## Post #543
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2017-02-25T10:33:11+00:00
- Post Title: Re: ARchive_neXt

Could you share some info about GRW dds ubi fileheader? its size, etc.
## Post #544
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-02-25T15:15:42+00:00
- Post Title: Re: ARchive_neXt

> Reply from Lord Vaako
>
> Could you share some info about GRW dds ubi fileheader? its size, etc.
I haven't made it that far yet, I'll let you know when I get there.
## Post #545
- Username: DorianKha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 05, 2017 8:25 am
- Post datetime: 2017-03-05T00:49:52+00:00
- Post Title: Re: ARchive_neXt

hello there !
i am very new to all of this but after reading a while i could not find the Archive neXt tool anywhere 
am i missing something ? i am getting an error when i try to reach the website.

Thanks 
(sorry for the poor english)
## Post #546
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-05T11:37:50+00:00
- Post Title: Re: ARchive_neXt

> Reply from DorianKha
>
> hello there !
i am very new to all of this but after reading a while i could not find the Archive neXt tool anywhere 
am i missing something ? i am getting an error when i try to reach the website.

Thanks 
(sorry for the poor english)
when you are in the website just Click on the title to download.([http://www.tbotr.net/modules.php?mod=Do ... =1&dlid=40](http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=40)
## Post #547
- Username: DorianKha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 05, 2017 8:25 am
- Post datetime: 2017-03-05T22:10:17+00:00
- Post Title: Re: ARchive_neXt

Got it sorted out 
thanks !
## Post #548
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2017-03-08T09:37:30+00:00
- Post Title: Re: ARchive_neXt

Someone was able to create a nice, huge map of Ghost Recon: Wildlands area - [http://swissgameguides.com/maps/ghost_r ... e_map.html](http://swissgameguides.com/maps/ghost_recon_wildlands/world/interactive_map.html)
Does anyone know how the ingame map is stored in GRW? as a sets of simple textures or 2d/3d model, e.t.c., or maybe someone was able to extract it already?
## Post #549
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-08T11:17:28+00:00
- Post Title: Re: ARchive_neXt

if you have a good machine or a high performance PC you can try NinjaRipper, bcs if it's not the case your game will crash with Ninja launcher
## Post #550
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-03-10T13:19:13+00:00
- Post Title: Re: ARchive_neXt

> Reply from ravenov
>
> if you have a good machine or a high performance PC you can try NinjaRipper, bcs if it's not the case your game will crash with Ninja launcher
I tried Ninjaripper back in closed beta and none of the settings worked on the game. It doesn't work with Wildlands at all
## Post #551
- Username: swinei
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-10T20:55:48+00:00
- Post Title: Re: ARchive_neXt

[Steep: Free Trial Begins this Weekend](http://blog.ubi.com/steep-free-weekend-begins-march-10/)

Yes, I have acquired my free trial, so I will be adding Steep support to ARchive_neXt.  Most likely a couple of updates away.  I'm still working on For Honor, Ghost Recon:Wildlands, and Rainbow Six Siege.  To that end, here's where I'm at right now.

For Honor
Still have some things to iron out with some of the images, and need to work on models yet.

[](http://www.tbotr.net/images/ARchive_neXt_014.png)
Click for larger image

Ghost Recon:Wildlands
Still have some things to iron out with some of the images, and need to work on models yet.

> Reply from Lord Vaako
>
> Someone was able to create a nice, huge map of Ghost Recon: Wildlands area - http://swissgameguides.com/maps/ghost_r ... e_map.html
Does anyone know how the ingame map is stored in GRW? as a sets of simple textures or 2d/3d model, e.t.c., or maybe someone was able to extract it already?

The background of that map was possibly stitched together from these background images you see below.

[](http://www.tbotr.net/images/ARchive_neXt_015.png)
Click for larger image

Rainbow Six Siege
The images are split into at most 4 files and because of that I'm having more problems than I had with the other games, however, things are still progressing. Much like the other games I still need to work on models.

[](http://www.tbotr.net/images/ARchive_neXt_016.png)
Click for larger image

Thanks for your patience,
## Post #552
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-13T05:13:33+00:00
- Post Title: Re: ARchive_neXt

Looking for a little help.  Having issues figuring out the For Honor model format.  Anyone that wants to help and take a look at the attached file.  Inside the zip is three binary model files and a text file detailing what I have figured out so far.

Any help would be greatly appreciated.

Thanks,
[FH_Model_Format.zip](https://xentaxbackup.github.io/file/12619_FH_Model_Format.zip)
## Post #553
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-03-13T08:03:53+00:00
- Post Title: Re: ARchive_neXt

I tried to figure out the geometry but the format is very different from Rainbow six siege. vertices looks weird... compressed?  I can see some figures but with no a correct structure :/

the new formats in Rainbow Six Siege works under float data with a vertex size of 12 bytes, uvs are in a different position. In the begin of these files that you posted, the files looks similar but the structure of the data is different
## Post #554
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-13T13:59:24+00:00
- Post Title: Re: ARchive_neXt

Don't think they are compressed, maybe this game using gpu skinning technique? Or maybe they are bit-packed. MichaelDarkAngel, if you will be able to find simpliest box shape it could help a lot, otherwise I will continue to strugle with this one - I'm very, very interested in this game, because of amazing armors this game have xD  Figuring out what's wrong with position will be the hardest task, other parts like uv's, bones and weights are pretty straightforward.
## Post #555
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-03-13T22:45:00+00:00
- Post Title: Re: ARchive_neXt

hey MichaelDarkAngel!

have you checked if the data obtained looks similar in ram ? if you want you can use intel gpa for obtain that specific data (models and textures) and not a entire process considering that is above 3 Gb, don't worry if the geometries are not showed in preview window, all data is captured in the file generated . so with this we can check if there are a compression or something ( I don't have the game so I can't check by myself  )
## Post #556
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2017-03-14T06:15:08+00:00
- Post Title: Re: ARchive_neXt

When the tool is updated to support for Honor, would it support extracting animations into usable formats (like FBX)? Would love to get the awesome character combat animations.
## Post #557
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-03-14T14:15:03+00:00
- Post Title: Re: ARchive_neXt

> Reply from HunterAP
>
> When the tool is updated to support for Honor, would it support extracting animations into usable formats (like FBX)? Would love to get the awesome character combat animations.
Animation support for FH, AC, etc would be an incredible addition, but it's understandable if it's too much.
## Post #558
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-03-15T17:07:33+00:00
- Post Title: Re: ARchive_neXt

What's your guessed ETA when you get Rainbow Six: Siege models and textures extractable with the tool the soonest time? No hurries, just curious as I've been waiting for this for a long time and now it seems to be getting closer.
## Post #559
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-16T16:19:57+00:00
- Post Title: Re: ARchive_neXt

> Reply from SergeantJoe
>
> HunterAP wrote:When the tool is updated to support for Honor, would it support extracting animations into usable formats (like FBX)? Would love to get the awesome character combat animations.
Animation support for FH, AC, etc would be an incredible addition, but it's understandable if it's too much.

I've never been able to crack the Havok animation format. So, at this time, they are still off the map.

> Reply from MaZTeR
>
> What's your guessed ETA when you get Rainbow Six: Siege models and textures extractable with the tool the soonest time? No hurries, just curious as I've been waiting for this for a long time and now it seems to be getting closer.

Currently working on Ghost Recon models. Probably tackle Rainbow Six models this weekend. Let's hope they're nothing like For Honor. Maybe sometime next week I'll be far enough along to release something for people to play around with.
## Post #560
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-16T17:46:25+00:00
- Post Title: Re: ARchive_neXt

Does it work with the Full Game "Ghost recon wildlands" ?, hope it's the same thing as the Beta files !
Thank you for your time & the others who are helping you...
## Post #561
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-03-17T01:56:44+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> I've never been able to crack the Havok animation format. So, at this time, they are still off the map.
This engine uses Havok? Interesting. Maybe the [Havok SDK](https://drive.google.com/drive/folders/0B3SZOCCKd7Ipb2w2SkN4bjJwSzg?pageId=109248185498456360507) can help? It's got the source code to all the havok animation types as well as a lot of documentation. (the official program has been canceled but their website says we can still use it)

Also, if it's possible to isolate a single structured .hkx file, we can try feeding it through Tools/BatchProcess/AssetCc, the official program for converting havok files from binary to xml. [That's what I did for Sleeping Dogs,](http://forum.xentax.com/viewtopic.php?p=117479#p117479) problem is that the filetypes usually have some tiny customization to them, which is enough to break support with the vanilla tools. 

In that same thread there's also a bunch of user-made converter programs with source code, [(1)](https://github.com/Highflex/havok2fbx/releases) [(2)](https://bitbucket.org/Volfin/hkx2smd/overview) but the same problem persist: slight game/version differences that I can't really do much about except try to muck around the hkx files with a hex editor.
## Post #562
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-17T05:00:30+00:00
- Post Title: Re: ARchive_neXt

A small sampling of Ghost Recon models...

[](http://www.tbotr.net/images/ARchive_neXt_017.png)
Click for larger image

[](http://www.tbotr.net/images/ARchive_neXt_018.png)
Click for larger image

Having trouble with models with multiple textures.  Can't understand why.

[EDIT]Spoke too soon.  Figured it out[/EDIT]
## Post #563
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-03-17T08:56:12+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> SergeantJoe wrote:HunterAP wrote:When the tool is updated to support for Honor, would it support extracting animations into usable formats (like FBX)? Would love to get the awesome character combat animations.
Animation support for FH, AC, etc would be an incredible addition, but it's understandable if it's too much.

I've never been able to crack the Havok animation format. So, at this time, they are still off the map.
MaZTeR wrote:What's your guessed ETA when you get Rainbow Six: Siege models and textures extractable with the tool the soonest time? No hurries, just curious as I've been waiting for this for a long time and now it seems to be getting closer.

Currently working on Ghost Recon models. Probably tackle Rainbow Six models this weekend. Let's hope they're nothing like For Honor. Maybe sometime next week I'll be far enough along to release something for people to play around with.
Very nice, looking forward to it.
## Post #564
- Username: GeekAndProud
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 13, 2017 11:03 pm
- Post datetime: 2017-03-21T04:25:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 

I've never been able to crack the Havok animation format. So, at this time, they are still off the map.

Last I checked Havok was just a physics engine and not an animation system.
## Post #565
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-21T06:38:09+00:00
- Post Title: Re: ARchive_neXt

> Reply from GeekAndProud
>
> MichaelDarkAngel wrote:

I've never been able to crack the Havok animation format. So, at this time, they are still off the map.


Last I checked Havok was just a physics engine and not an animation system.

It's both. [https://www.havok.com/animation-studio/](https://www.havok.com/animation-studio/)
## Post #566
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-03-22T15:28:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from SergeantJoe
>
> HunterAP wrote:When the tool is updated to support for Honor, would it support extracting animations into usable formats (like FBX)? Would love to get the awesome character combat animations.
Animation support for FH, AC, etc would be an incredible addition, but it's understandable if it's too much.

MDA implemented a skeleton option in the tool for AC, but the full animation in fbx with weights is not there yet. However, someone managed to figure it out through the Raw Data that you can export with right-click... not sure if that can be sorted and converted @MDA? I know you re busy with other games and rl though, so I totally understand if that would be too complicated or even impossible to do in ARchive_neXt. Not sure if you actually spoke to the guy already.
## Post #567
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-26T16:05:46+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> A small sampling of Ghost Recon models...


Click for larger image


Click for larger image

Having trouble with models with multiple textures.  Can't understand why.

[EDIT]Spoke too soon.  Figured it out[/EDIT]
No hurries, just curious, How long it remains for GRW tool(ARchive_neXt)...  
thanks for your time
## Post #568
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-26T16:28:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from ravenov
>
> No hurries, just curious, How long it remains for GRW tool(ARchive_neXt)...  
thanks for your time

Thought I was going to have a release a few minutes ago...  However, I ran into some issues that I need to fix to make the program a little more stable.  Hopefully I'll be able to do that relatively quickly.

With the upcoming release...
Everything will be working for Ghost Recon:Wildlands (as tested with the Beta version of the game files).
For Honor and Rainbow Six Siege currently support image viewing/exporting only.

Thanks for your patience,
## Post #569
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-26T19:38:31+00:00
- Post Title: Re: ARchive_neXt

Now Available!!!

ARchive_neXt v4.03.26.4

Now include full support for Ghost Recon:Wildlands (based on the Beta version game files).  Still a few things to iron out.

Also includes limited support (image viewing/exporting) for For Honor and Rainbow Six Siege (also based on the Beta version game files).  Even the limited support isn't 100%.

This is a much larger download from previous versions, roughly 100 times larger, because of the included indexes that will be used for the upcoming search function.  The immediate upside, because of these indexes, you will no longer need to hunt for textures prior to viewing/exporting models (currently only available for Ghost Recon:Wildlands).  Once I am closer to having the other new games completed I'll start adding this function to previous games.

Steep support will be added in a future release.

Enjoy
## Post #570
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-26T20:00:57+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Now Available!!!

ARchive_neXt v4.03.26.4

Now include full support for Ghost Recon:Wildlands (based on the Beta version game files).  Still a few things to iron out.

Also includes limited support (image viewing/exporting) for For Honor and Rainbow Six Siege (also based on the Beta version game files).  Even the limited support isn't 100%.

This is a much larger download from previous versions, roughly 100 times larger, because of the included indexes that will be used for the upcoming search function.  The immediate upside, because of these indexes, you will no longer need to hunt for textures prior to viewing/exporting models (currently only available for Ghost Recon:Wildlands).  Once I am closer to having the other new games completed I'll start adding this function to previous games.

Steep support will be added in a future release.

Enjoy

thanks MichaelDarkAngel      
and thanks for your time
## Post #571
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-26T21:08:51+00:00
- Post Title: Re: ARchive_neXt

_________________________________________________________________________________________________________________

it's me again with some problems, i installed all Requirements !, hope it's easy to fix, i had this problems when i try to preview a mesh !

1********


2********


3********


4 and it stuck here with this message


Rq: textures are loading correctly

Thanks
## Post #572
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-26T21:51:43+00:00
- Post Title: Re: ARchive_neXt

> Reply from ravenov
>
> _________________________________________________________________________________________________________________

it's me again with some problems, i installed all Requirements !, hope it's easy to fix, i had this problems when i try to preview a mesh !

...

Rq: textures are loading correctly

Thanks

First question:  Are you using the Beta version of the game, or the full version?

Second question:  Which datafile are you trying to view when you get the message in your first image?  (note to self: add that information to the messagebox)

Last question (for now):  Specifically, which model are you trying to view when you get the message in your second image?  I assume it's AC_Ghost_Boots_LOD0, but I would rather have verification.  (note to self: would be nice to have that information in the messagebox as well)

Whichever model you view that causes the issues in image #s 3 and 4 (in this case WS_ASR_ACR_Stock_LOD0) there should be an X file created in the temp folder (default location "Documents/TBotR/ARchive_neXt/Temp/forge file name").  If you could send me that file it might help me to determine the problem.

I thought I was done with questions, but something else just came to mind.  Is the Temp File Location you are using writeable?

Just out of curiosity, did you change the image viewer background color to black?

Sorry I could not provide a quick fix within this post
## Post #573
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-26T22:08:50+00:00
- Post Title: Re: ARchive_neXt

*i'm using the full game version (targeted the same files as you showed in the image)
* it's AC_Ghost_Boots_LOD0
*and following this path C:\Users\***\Documents\TBotR\ARchive_neXt\Temp i found this folder (not a single file ! [http://sta.sh/download/5661574948469178 ... 1490566612](http://sta.sh/download/5661574948469178/datapc_forge_by_moharder-db3naop.rar?token=e5705c0e06397acfc16b25e14cd784e49c2582d5&ts=1490566612)

*yes, i changed the background to black 
Rq: one of my friends tried the tool on beta files, and it's the same problem
## Post #574
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-26T23:39:36+00:00
- Post Title: Re: ARchive_neXt

Thanks so much for supporting this game!
I tried it on open Beta files and get the same error as ravenov, however exporting models when clicking on 'Mesh'->'Export All As' works fine
## Post #575
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-26T23:42:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from ravenov
>
> *i'm using the full game version (targeted the same files as you showed in the image)
Seems like they didn't change anything from beta to full version.  That's a plus.

I'm thinking the answer to question #2 is missing.  At least based on what I see in image 1.


> Reply from ravenov
>
> * it's AC_Ghost_Boots_LOD0
*and following this path C:\Users\***\Documents\TBotR\ARchive_neXt\Temp i found this folder (not a single file ! http://sta.sh/download/5661574948469178 ... 1490566612
When attempting to view the AC_Ghost_Boots_LOD0 model in the ...\Temp folder you should see 6 .grw files (these are the raw data files used to construct the image files), and 3 .dds files (one of these starts with dx9_, the normalmap in this instance).  In the ...\Temp\DataPC.forge folder you should see 3 files (1 .grw, 1 .png, and 1 .x; raw data of the datafile you are viewing, texture used by the model viewer, and model used by the model viewer respectively).  Based on the .x file included in what you sent me, it appears that the image files are not being created.  The normalmap for this model is a DX10 dds image and needs to be converted to DXT5, this is done by texconv.exe.  It should have been installed when you installed ARchive_neXt.  Can you look in the directory where you installed ARchive_neXt and let me know if texconv.exe is in fact there?  Another way to make sure it is working is to try and view the normalmap (AC_Ghost_Boots_NormalMap).  If ARchive_neXt crashes there's something wrong with texconv or it's missing.


> Reply from ravenov
>
> *yes, i changed the background to black
I thought this might cause an issue when viewing some of the models, but it appears I have not tied the image viewer background color to the model viewer background color.  It reverts to cornflower blue when I view a model regardless of the color I set in preferences.

TLDR
It appears images are not being created and it breaks the model file which crashes the program.
## Post #576
- Username: fahad00
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 19, 2016 3:36 am
- Post datetime: 2017-03-27T09:07:33+00:00
- Post Title: Re: ARchive_neXt

Hey Michel Bro,
Is there anything to extract one forge files at once and rebuild them at once bro 
please help I hope you can help me 
thanks
## Post #577
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-03-27T09:14:01+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> I finally managed to get some decent looking hairs (not 100% perfect, but oh well)





They are so heavy, too many polygons ahah.

MDA, I'm really grateful for the work you've done on this tool!
Do you have a skeleton?
## Post #578
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T09:18:09+00:00
- Post Title: Re: ARchive_neXt

__________________________________
___________________________________________
* About question two, yes it's about image 1
* this time i was trying to export directly without a preview of this file in the archive ;



and the generated files in temp folder of this path C:\Users\****\Documents\TBotR\ARchive_neXt\Temp\DataPC.forge are this 

[http://sta.sh/download/1810013275268022 ... 1490606478](http://sta.sh/download/1810013275268022/datapc_forge_by_moharder-db3p7bc.rar?token=0b14c15b0fc43c5456e94d053549f8e2f32ff916&ts=1490606478)
and the texconv.exe is in the installed dir / and the normal maps and other textures are showing correctly when i click on them in the tool...

*the problem stuck with mesh when i try to preview them, this error messages pop-up one after an other !
## Post #579
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T09:30:11+00:00
- Post Title: Re: ARchive_neXt

If you want to export without preview use this without expanding the 'Mesh' node:

It will still show you one error, but just click 'ok' a couple of times and it will still give you the .objs without crashing the whole program. Textures are not auto-extracted though.
## Post #580
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T09:52:54+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> Thanks so much for supporting this game!
I tried it on open Beta files and get the same error as ravenov, however exporting models when clicking on 'Mesh'->'Export All As' works fine

i tried your method to export the folder directly, the textures are exported with the .obj model too

Textures


.obj model (problem) no preview


i tried to load it in different 3D Program without any result !
maybe i'm a noob to edit something on that Obj file to correct it ?!

thanks
## Post #581
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T10:26:34+00:00
- Post Title: Re: ARchive_neXt

I import the objs to Blender without a problem, they don't show in Noesis for me too. I don't know about other programs^^
## Post #582
- Username: striking
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 10, 2017 6:14 pm
- Post datetime: 2017-03-27T10:30:29+00:00
- Post Title: Re: ARchive_neXt

Thank you MichaelDarkAngel.

I tried to use it for Rainbow with the UltraHD Textures installed and get images similar to this one:
[](http://imgur.com/k2B8DFq)
The result changes randomly after I select a different texture and switch back.
Did anyone get similar images ?

I think that the resources are at different offsets compared to the version you used (and hopefully
not in a different format).
Is there an option to search for all resources without matching them to the stored indices ?
## Post #583
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T10:45:41+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> I import the objs to Blender without a problem, they don't show in Noesis for me too. I don't know about other programs^^

Dude i always make this mistake and it's forgeting blender, finally it work the model loaded correctly, thank you   
and big thanks to MichaelDarkAngel   hope you can fix the preview problem to gain time and make it easy to know what you extract correctly thanks again 

if there is some new issus with other files, i will let you know
## Post #584
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T12:50:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> If you want to export without preview use this without expanding the 'Mesh' node:

It will still show you one error, but just click 'ok' a couple of times and it will still give you the .objs without crashing the whole program. Textures are not auto-extracted though.
-Can you try to export and import this one,  in Blender; 
****


****and i had this Error in blender !


!!
## Post #585
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T12:59:13+00:00
- Post Title: Re: ARchive_neXt

It loads without error for me 
In archive_next, after exporting the obj, make it load any texture. The error in blender appears when it cannot access the .mtl (comes with .obj) file because archive_next still uses it in some way. If you just click on any texture and then try to import the obj again in blender it should work.
## Post #586
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T13:10:10+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> It loads without error for me 
In archive_next, after exporting the obj, make it load any texture. The error in blender appears when it cannot access the .mtl (comes with .obj) file because archive_next still uses it in some way. If you just click on any texture and then try to import the obj again in blender it should work.

10/10  
i'm a f*****g idiot  

-now problem with normal maps (high resolution) 
i checked many files like this one, where normal map are in high resolution or maybe not !?
## Post #587
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T15:32:04+00:00
- Post Title: Re: ARchive_neXt

On those textures that display as 'Bad Image' use the first export option:

It will give you a dx10 .dds file, which cannot be opened with most usual programs. Use Noesis to view and convert it ^_^
## Post #588
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T15:57:45+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> On those textures that display as 'Bad Image' use the first export option:

It will give you a dx10 .dds file, which cannot be opened with most usual programs. Use Noesis to view and convert it ^_^

20 hours without sleeping   
thanks Dude again
## Post #589
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T16:00:20+00:00
- Post Title: Re: ARchive_neXt

No Problem, glad i can help
## Post #590
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T16:32:59+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> No Problem, glad i can help
thanks man    , infinit issues today, map displaced ?! i inverted the UV's and there is this map Offset 


same problem for Normal/Spec/Gloss/Diff
## Post #591
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T16:35:21+00:00
- Post Title: Re: ARchive_neXt

Which model is that?
## Post #592
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T16:36:13+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> Which model is that?
WG_ASR_ACR_Stock_LOD0

you can find it in DataPC_extra.forge
## Post #593
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-27T17:04:26+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> On those textures that display as 'Bad Image' use the first export option:

It will give you a dx10 .dds file, which cannot be opened with most usual programs. Use Noesis to view and convert it ^_^

Those are the same images that are causing your issue when trying to view models.  Which means texconv is not doing its job. I'll see if I can bypass that, the model viewer only uses the diffuse map but all textures get created at the same time.
## Post #594
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-27T17:17:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from striking
>
> Thank you MichaelDarkAngel.

I tried to use it for Rainbow with the UltraHD Textures installed
The result changes randomly after I select a different texture and switch back.
Did anyone get similar images ?

I think that the resources are at different offsets compared to the version you used (and hopefully
not in a different format).
Is there an option to search for all resources without matching them to the stored indices ?

Noticed this issue yesterday when I started digging into the RSS files. 2 problems, first is something I forgot to do for this release, second is with the images themselves.

I could release a fix for the first problem, but that wouldn't fix images that are used for textures.  

Going to work on getting the textures to work properly first.
## Post #595
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T17:33:27+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> Which model is that?

i'm trying...with this UV's
## Post #596
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-27T17:42:22+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 
Those are the same images that are causing your issue when trying to view models.  Which means texconv is not doing its job. I'll see if I can bypass that, the model viewer only uses the diffuse map but all textures get created at the same time.

Hmm, i'm not entirely sure this is the issue as usually all textures for most models display correctly in Archive next itself (normal maps aswell), but the models still throw the error when trying to preview them.

> Reply from ravenov
>
> 
i'm trying...with this UV's

[img]http://orig11.deviantart.net/ad9c/f/201 ... b3qazj.png[/ig]

I cannot check the model right now because i'm not home, but from the picture it looks like you just need to move the UV upwards a little bit.
## Post #597
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-27T17:52:18+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> MichaelDarkAngel wrote:
Those are the same images that are causing your issue when trying to view models.  Which means texconv is not doing its job. I'll see if I can bypass that, the model viewer only uses the diffuse map but all textures get created at the same time.

Hmm, i'm not entirely sure this is the issue as usually all textures for most models display correctly in Archive next itself (normal maps aswell), but the models still throw the error when trying to preview them.
ravenov wrote:
i'm trying...with this UV's



I cannot check the model right now because i'm not home, but from the picture it looks like you just need to move the UV upwards a little bit.

maybe scaling it is better, bcs when i move it upwards it's the same problem

quick scale/ not perfectly donne

set the Uv's in the middle and scale or set Uv's in a good corner of the map and Scale a little bit
## Post #598
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-27T18:08:50+00:00
- Post Title: Re: ARchive_neXt

> Reply from o0Crofty0o
>
> MichaelDarkAngel wrote:
Those are the same images that are causing your issue when trying to view models.  Which means texconv is not doing its job. I'll see if I can bypass that, the model viewer only uses the diffuse map but all textures get created at the same time.

Hmm, i'm not entirely sure this is the issue as usually all textures for most models display correctly in Archive next itself (normal maps aswell), but the models still throw the error when trying to preview them.

For whatever reason, texconv is not doing what its supposed to do, that causes ARchive_neXt to crash and not finish writing the model file. The incomplete model file never gets loaded.  I'm pretty sure I'm right about this.

What I don't know is why texconv isn't working. Could be a permissions issue, but that's just a guess.
## Post #599
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-28T00:52:33+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> For whatever reason, texconv is not doing what its supposed to do, that causes ARchive_neXt to crash and not finish writing the model file. The incomplete model file never gets loaded.  I'm pretty sure I'm right about this.
Confirmed and bypassed with error handling that informs you of the failed DX10 conversion.  Thus allowing ARchive_neXt to finish writing the model file and properly load it for viewing.  Still not sure why texconv is not working for those with this issue.  The only way I could replicate the error was to remove texconv from the installation directory.

Now to try and resolve the Rainbow Six Siege image issue...
## Post #600
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-28T03:20:17+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> MichaelDarkAngel wrote:For whatever reason, texconv is not doing what its supposed to do, that causes ARchive_neXt to crash and not finish writing the model file. The incomplete model file never gets loaded.  I'm pretty sure I'm right about this.
Confirmed and bypassed with error handling that informs you of the failed DX10 conversion.  Thus allowing ARchive_neXt to finish writing the model file and properly load it for viewing.  Still not sure why texconv is not working for those with this issue.  The only way I could replicate the error was to remove texconv from the installation directory.

Now to try and resolve the Rainbow Six Siege image issue...
MichaelDarkAngel... i want translate assassins creed games
can you help me zbout text and font files? and forge file?
## Post #601
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-28T03:32:29+00:00
- Post Title: Re: ARchive_neXt

So... on the RSS image front

The issue I am having may have more to do with the Beta version of the game than I first thought.  Some images work fine:
[](http://www.tbotr.net/images/ARchive_neXt_019.png)
Click for larger image

Others have issues:
[](http://www.tbotr.net/images/ARchive_neXt_020.png)
Click for larger image

In the image with issues, everything in the file is telling me the image should be 1024x1024.  Well after hunting down all the referenced files (which is the first problem I mentioned in an earlier post, I forgot to give it the ability to search for all those required files), piecing them together to build the DDS file, something just isn't right.  For one, file size didn't seem large enough for a 1024x1024 image.  If I edit the DDS file with a hex editor and change the height and width to 512x512...
[](http://www.tbotr.net/images/ARchive_neXt_021.png)
Click for larger image

Looks good.  Yeah, but everything tells me it should be 1024x1024.  Back to the drawing board.  In order to create an image file for RSS, there are four files required (maybe more, that could be one of the drawbacks of the Beta version).  The header file, which references the other required files and provides some other information (height, width, and a few others).  The referenced files are in reverse order (smallest mipmaps to largest).  Each of the referenced files contain image data, height and width again, the size of the image data of the previous file(s).  Well, that was the key.  Looking at that bit of information for the image that works that size is zero, meaning, there have been no image data files prior to this one.  Looking at that information for the image that doesn't work, that size is 524,288.  There is quite a large chunk of the image file that is missing!!!

So all I can do right now is fix the issue that shouldn't have been an issue in the last release and see if that works for anyone with the full version of the game.
## Post #602
- Username: Panasonic
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-28T03:42:24+00:00
- Post Title: Re: ARchive_neXt

Now Available!!!

ARchive_neXt v4.03.27.0

Better error handling of the DX10 conversion process (currently only applies to Ghost Recon:Wildlands and Rainbow Six Siege)
A fix to the Rainbow Six Siege search process when building DDS images

That is all... for now...
## Post #603
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-28T04:05:15+00:00
- Post Title: Re: ARchive_neXt

> Reply from ravenov
>
> infinit issues today, map displaced ?! i inverted the UV's and there is this map Offset 


same problem for Normal/Spec/Gloss/Diff

UVs are slightly off.  I'll see if I can get that a little closer with the next update.
## Post #604
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2017-03-28T09:59:52+00:00
- Post Title: Re: ARchive_neXt

I don't no if it happens to everyone but it happens to me 


Error.jpg (232.83 KiB) Viewed 319 times
## Post #605
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-03-28T10:27:52+00:00
- Post Title: Re: ARchive_neXt

Thanks a lot for the update, but sadly i still get the same errors. I disabled any sorts of UAC, am logged in as admin and have full acess to any folders archive next uses, also turned off anti virus but the errors are still there.

It's not a big issue for me personally as i don't mind exporting and looking through things, though.
## Post #606
- Username: merde10
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 11, 2016 2:59 am
- Post datetime: 2017-03-28T10:54:57+00:00
- Post Title: Re: ARchive_neXt

Hey guys!

Thanks a lot for this amazing tool!

I'm actually ripping some models from assassin's creed 1 on PC. 

I would like to know if is it possible to rip model with their location on the scene?

For example, i would like to rip the solomon temple, but all the assets are in the same location when i import them into blender(and it's really hard to find their real locations).

I tried with 3d ripper dx but i have no 3d capture ( the game launch but when i press the button, nothing happens...).

Thanks a lot!
## Post #607
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-28T12:00:29+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> ravenov wrote:infinit issues today, map displaced ?! i inverted the UV's and there is this map Offset 


same problem for Normal/Spec/Gloss/Diff

UVs are slightly off.  I'll see if I can get that a little closer with the next update.

i hope you can fix the preview on the tool, having so much pain with splited parts...
## Post #608
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-28T15:09:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from Faithfullfaun
>
> I don't no if it happens to everyone but it happens to me

Is this happening with every image file?

> Reply from ravenov
>
> i hope you can fix the preview on the tool, having so much pain with splited parts...

If the latest update did not fix the model viewer issue, texconv is not your only problem, and you are suffering from a problem that has plagued ARchive_neXt for a long time.
## Post #609
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-28T17:28:07+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Faithfullfaun wrote:I don't no if it happens to everyone but it happens to me

Is this happening with every image file?
ravenov wrote:i hope you can fix the preview on the tool, having so much pain with splited parts...

If the latest update did not fix the model viewer issue, texconv is not your only problem, and you are suffering from a problem that has plagued ARchive_neXt for a long time.

i don't know if this is possible can you add a search bare on the tool to find files names quicly ?
that will be really helpfull and replace the preview option !
## Post #610
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2017-03-28T17:55:28+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> Faithfullfaun wrote:I don't no if it happens to everyone but it happens to me

Is this happening with every image file?
ravenov wrote:i hope you can fix the preview on the tool, having so much pain with splited parts...

If the latest update did not fix the model viewer issue, texconv is not your only problem, and you are suffering from a problem that has plagued ARchive_neXt for a long time.

Yes every single image i select
## Post #611
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-28T19:00:18+00:00
- Post Title: Re: ARchive_neXt

> Reply from Faithfullfaun
>
> i don't know if this is possible can you add a search bare on the tool to find files names quicly ?
that will be really helpfull and replace the preview option !

Search is in the works, but most likely not until I'm further along with the new games.

> Reply from Faithfullfaun
>
> Yes every single image i select

Sounds like they did in fact change something in the full version of the game. I may have to buy the game this weekend in order to fix this issue.
## Post #612
- Username: striking
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 10, 2017 6:14 pm
- Post datetime: 2017-03-28T19:10:36+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> So... on the RSS image front

The issue I am having may have more to do with the Beta version of the game than I first thought.  Some images work fine:

...

I have the same issues with the full version.
Comparing the beta, Steam and UPlay files shows different file sizes for the same files. So they probably changed the
partition of the images. Additionally they changed some of the forge files with each update, including the largest difference
for the Ultra HD update.
## Post #613
- Username: striking
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 10, 2017 6:14 pm
- Post datetime: 2017-03-29T11:07:27+00:00
- Post Title: Re: ARchive_neXt

Would it be of any help if you have a forge file together with some of the DDS-textures obtained from NinjaRipper ?
## Post #614
- Username: W0lfy
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-29T11:59:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from striking
>
> Would it be of any help if you have a forge file together with some of the DDS-textures obtained from NinjaRipper ?

Each piece of the image is in a different forge file. So, with the beta version, that makes 4 forge files. Being that a piece is missing, it's possibly in another forge file. I'll have the game tomorrow or Friday at the latest.

In the meantime, I'm working on the search function and adding the index system to the older games.
## Post #615
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-30T14:15:14+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> striking wrote:Would it be of any help if you have a forge file together with some of the DDS-textures obtained from NinjaRipper ?

Each piece of the image is in a different forge file. So, with the beta version, that makes 4 forge files. Being that a piece is missing, it's possibly in another forge file. I'll have the game tomorrow or Friday at the latest.

In the meantime, I'm working on the search function and adding the index system to the older games.

when i try to export a mesh this Error message pop-up / and when i let the tool for a moment or changing the window and i try again it works correctly, but again for some reason this error will pop-up again trying epxorting a mesh...



```
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.NullReferenceException: Object reference not set to an instance of an object.
   at ARchive_neXt.arxForm.arxExportOBJ(TreeNode tNode, String savePath)
   at ARchive_neXt.arxForm.arxExportModels(String fileExt)
   at ARchive_neXt.arxForm.tsmiExportModels_Click(Object sender, EventArgs e)
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ToolStrip.WndProc(Message& m)
   at System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
ARchive_neXt
    Assembly Version: 4.3.27.0
    Win32 Version: 4.03.27.0
    CodeBase: file:///C:/Program%20Files%20(x86)/TBotR/ARchive_neXt/ARchive_neXt.exe
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
Microsoft.DirectX
    Assembly Version: 1.0.2902.0
    Win32 Version: 5.04.00.2904
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.DirectX/1.0.2902.0__31bf3856ad364e35/Microsoft.DirectX.dll
----------------------------------------
Microsoft.DirectX.Direct3D
    Assembly Version: 1.0.2902.0
    Win32 Version: 9.05.132.0000
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.DirectX.Direct3D/1.0.2902.0__31bf3856ad364e35/Microsoft.DirectX.Direct3D.dll
----------------------------------------
Microsoft.DirectX.Direct3DX
    Assembly Version: 1.0.2911.0
    Win32 Version: 9.12.589.0000
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.DirectX.Direct3DX/1.0.2911.0__31bf3856ad364e35/Microsoft.DirectX.Direct3DX.dll
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
ArchiveX
    Assembly Version: 4.2.3.0
    Win32 Version: 4.02.03.0
    CodeBase: file:///C:/Program%20Files%20(x86)/TBotR/ARchive_neXt/ArchiveX.DLL
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.

```


*Figured out
## Post #616
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2017-03-30T17:31:49+00:00
- Post Title: Re: ARchive_neXt

Michael, is there any way to mass-extract all files in RAW format from a .forge file?
One-by-one is unusable
## Post #617
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-03-30T19:02:59+00:00
- Post Title: Re: ARchive_neXt

did someone found the machine gun or mini-Gun Turret, pls leave just the file/s Name/s as a Reply, thanks.


Finnaly I find it !
## Post #618
- Username: HugoNoob
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 31, 2017 9:29 pm
- Post datetime: 2017-03-31T13:42:48+00:00
- Post Title: Re: ARchive_neXt

Rainbow Six Siege






nothing works

Windows 7 64-bit
.NET Framework 4.6.2
DirectX June 2010 Redistributable Runtime.
## Post #619
- Username: striking
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 10, 2017 6:14 pm
- Post datetime: 2017-03-31T14:22:06+00:00
- Post Title: Re: ARchive_neXt

> Reply from HugoNoob
>
> Rainbow Six Siege
See Michael's post above for an explanation.

Which Rainbow version are you using ? UPlay, Steam, Beta or Cracked ?
## Post #620
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-31T14:54:13+00:00
- Post Title: Re: ARchive_neXt

@HugoNoob

Rainbow Six is not going to work if you have any version other than the Beta.  Even the Beta doesn't work properly because of missing files.  I have the full version of the game now and I'm currently working on rebuilding the search index.  However, I have run into an issue with some of the forge files, so even that is taking longer than I would have hoped.

The Beta has 53 forge files, the full version has 213.  This renders the current search index useless as positions of some of the files have changed.

In regards to the search index, it will only ever be as good as the files I have on my hard drive.  If there are ever DLCs that I don't purchase, or a different supplier ships something extra, the index will not have that included and there could be issues.
## Post #621
- Username: HugoNoob
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 31, 2017 9:29 pm
- Post datetime: 2017-03-31T14:55:29+00:00
- Post Title: Re: ARchive_neXt

> Reply from striking
>
> HugoNoob wrote:Rainbow Six Siege
See Michael's post above for an explanation.

Which Rainbow version are you using ? UPlay, Steam, Beta or Cracked ?

Steam Version and Cracked Codex Version

@MichaelDarkAngel

is it possible in the future to extract world models? not only player/weapon  models
## Post #622
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-31T15:46:06+00:00
- Post Title: Re: ARchive_neXt

> Reply from HugoNoob
>
> is it possible in the future to extract world models? not only player/weapon  models

In previous games I've only ever found characters, items, and simple buildings.  I think it's safe to assume this game will be no different.  I'm sure the information is there somewhere, I just haven't found it yet.
## Post #623
- Username: HugoNoob
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 31, 2017 9:29 pm
- Post datetime: 2017-03-31T16:05:24+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> HugoNoob wrote:is it possible in the future to extract world models? not only player/weapon  models

In previous games I've only ever found characters, items, and simple buildings.  I think it's safe to assume this game will be no different.  I'm sure the information is there somewhere, I just haven't found it yet.

Okey thats sad...
## Post #624
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-03-31T20:08:59+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> @HugoNoob

Rainbow Six is not going to work if you have any version other than the Beta.  Even the Beta doesn't work properly because of missing files.  I have the full version of the game now and I'm currently working on rebuilding the search index.  However, I have run into an issue with some of the forge files, so even that is taking longer than I would have hoped.

The Beta has 53 forge files, the full version has 213.  This renders the current search index useless as positions of some of the files have changed.

In regards to the search index, it will only ever be as good as the files I have on my hard drive.  If there are ever DLCs that I don't purchase, or a different supplier ships something extra, the index will not have that included and there could be issues.
All of the micro transactions gets automatically downloaded to the game.
## Post #625
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-04-01T22:13:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> RunaWhite wrote:I finally managed to get some decent looking hairs (not 100% perfect, but oh well)





They are so heavy, too many polygons ahah.

MDA, I'm really grateful for the work you've done on this tool!
Do you have a skeleton?

Sorry for the late reply. Yes I do, but the rigged models are converted for the XNA Posing Studio program (and I don't think I can link them here). I am not able to personally extract the skeletons though, a friend is helping me with that (from Unity and Syndicate for now) 'cause as I said in my previous post he figured out the format. 

Also thank you for the updated program MDA!
## Post #626
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-04-02T11:39:50+00:00
- Post Title: Re: ARchive_neXt

Many Models (weap/vehe...) have Uv's Issues or you can say the majority of the models need a fix after extraction Which take so much time, i hope MichaelDarkAngel can fix this
## Post #627
- Username: bentroz1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2017 9:31 am
- Post datetime: 2017-04-05T02:16:31+00:00
- Post Title: Re: ARchive_neXt

Can't preview models, and textures don't export with model like some say.. Constant crash, windows 10, full version steam of Wildlands.

Any fixes? thanks.

Just want to export cars/props
## Post #628
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-04-05T06:45:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from bentroz1
>
> Can't preview models, and textures don't export with model like some say.. Constant crash, windows 10, full version steam of Wildlands.

Any fixes? thanks.

Just want to export cars/props

The last few pages have a work around for this problem.
## Post #629
- Username: bentroz1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2017 9:31 am
- Post datetime: 2017-04-05T13:39:14+00:00
- Post Title: Re: ARchive_neXt

yeah, well obviously but these workounds don't seem to work? Anyone know when there is going to be a fix, to where we can actually preview and export models?

I know you can export all and get a mesh, but a mesh is useless if there is no textures with it, for example 

_items_cocainebag = has mesh but no textures I could find.
## Post #630
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-04-05T18:19:31+00:00
- Post Title: Re: ARchive_neXt

> Reply from bentroz1
>
> yeah, well obviously but these workounds don't seem to work? Anyone know when there is going to be a fix, to where we can actually preview and export models?
I know you can export all and get a mesh, but a mesh is useless if there is no textures with it, for example 
_items_cocainebag = has mesh but no textures I could find.

The meshes not previewing thing is, as MDA said ,an older bug that happened prior to Ghost Recon too. There isn't a fix for that at the moment.

You can find the textures for meshes when you expand the 'Materials' tab. The names listed below are all textures that object uses, for example:


just search for these names with _DiffuseMap, _Mask1Map, _NormalMap, (eventually) _SpecularMap at the end. Those you can export manually in various image formats.
## Post #631
- Username: bentroz1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2017 9:31 am
- Post datetime: 2017-04-07T01:32:49+00:00
- Post Title: Re: ARchive_neXt

How come you have to find textures like _normal you cant extract anything cause all it says is "EXPORT RAW DATA"
## Post #632
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-12T06:24:12+00:00
- Post Title: Re: ARchive_neXt

hey guys... i want edit textures and reimport in geme... i downlaod ARchive_neXt but i dont know... i want edit texture. any body can help me?
## Post #633
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-04-12T11:22:09+00:00
- Post Title: Re: ARchive_neXt

> Reply from GHOST DEAD
>
> hey guys... i want edit textures and reimport in geme... i downlaod ARchive_neXt but i dont know... i want edit texture. any body can help me?
[I have a tutorial on how to edit forge files here.](http://steamcommunity.com/sharedfiles/filedetails/?id=852618479) I've only tried it on Assassins Creed files though, I don't know if it'll work with others.

EDIT: It's a shame michalss never finished his forge repacker, it would've been incredibly useful.
## Post #634
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2017-04-12T14:32:14+00:00
- Post Title: Re: ARchive_neXt

Hello, I'm downloading  v4.03.27. The installer is 332MB, did you uploaded a wrong file?
## Post #635
- Username: noirfx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 03, 2017 11:21 pm
- Post datetime: 2017-04-14T13:21:45+00:00
- Post Title: Re: ARchive_neXt

Hey, guys
can somebody rip or extracts medkits from ghost recon wildlands?
## Post #636
- Username: LeSam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 01, 2017 10:31 pm
- Post datetime: 2017-05-01T14:33:09+00:00
- Post Title: Re: ARchive_neXt

Hello,

I've been tracking this topic for a long time. Wanted to know the progress of the Rainbow Six: Siege option, I desperately need to port some of the environment assets and props.

Thanks in advance,

Sam.
## Post #637
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-05-03T09:31:35+00:00
- Post Title: Re: ARchive_neXt

Man, I LOVE this program, but it really needs a search tool with the way these Forge files are organised... Keep up the good work dude!
## Post #638
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-05-04T03:32:45+00:00
- Post Title: Re: ARchive_neXt

hey boys.... who can edit textures and reimport in game? no body! extract never was a problem! we can extract everythin in games whit scripts. codes. creat a tool, use hex editor and change header and... all guys in this work must try on repacker! extract? realy? extract is not a problem! creat a explorer(unpack, repack,editor,checkup,reimport)
this app (ARchive_neXt) use a [direct x](direct%20x) patch to extract and decompressing,
how we can make a tool: try open .exe files(crack) and extract all scrips and use those scripts to making a tool...
you must do that... well... can you know that, my frind? we need repack & reimport...
try open crack file and use those scripts in crack... i everytime use scripts in crack to make a tool(crack have all those things)
## Post #639
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-05-13T11:01:18+00:00
- Post Title: Re: ARchive_neXt

I'm still seeing this error.
...
..
.
[Ekran Alıntısı.PNG](https://xentaxbackup.github.io/file/12882_Ekran Alıntısı.PNG)
## Post #640
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2017-05-15T01:05:51+00:00
- Post Title: Re: ARchive_neXt

I've been wanting to ask for over a month but didn't want to annoy anyone so I waited till now to ask if there has been any progress on ForHonor assets?
## Post #641
- Username: VxeR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 16, 2017 11:11 pm
- Post datetime: 2017-05-16T15:49:16+00:00
- Post Title: Re: ARchive_neXt

Hey everyone. 
When trying to view for honor assets, nothing loads. Is there a fix?
## Post #642
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2017-05-23T09:15:24+00:00
- Post Title: Re: ARchive_neXt

Not yet implemented ! is there a solution for this, the Obj file is extracted but when i import in blender, Errors pop up !?
## Post #643
- Username: Mathrekxz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 25, 2017 3:54 am
- Post datetime: 2017-05-24T19:59:41+00:00
- Post Title: Re: ARchive_neXt

This is a really helpful tool, it would be even better if I could extract R6s files without that glitchy pixel effect.
## Post #644
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2017-05-31T13:01:31+00:00
- Post Title: Re: ARchive_neXt

Any updates on the tool?
## Post #645
- Username: Sargeras
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 31, 2017 9:57 pm
- Post datetime: 2017-05-31T14:04:12+00:00
- Post Title: Re: ARchive_neXt

Hey!
I've just downloaded Assassin's Creed IV and ARchive_neXt, but I can't view model meshes because of the following error:


If I click OK, I keep getting these errors infinitely (until I end the process in process manager):


I've tried rclicking on the folder instead, and doing Export All, but when I import the resulting .obj file to Blender, it doesn't have any mesh.

I'd be grateful for any assistance with this
## Post #646
- Username: Sargeras
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 31, 2017 9:57 pm
- Post datetime: 2017-05-31T15:11:41+00:00
- Post Title: Re: ARchive_neXt

Also, does anyone know where the redcoat soldiers/captains' textures are located? They seem to use CHR_Shared_Cloth_*something*, but I only managed to find the Normal and Diffuse versions, no Specular
## Post #647
- Username: fahad00
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 19, 2016 3:36 am
- Post datetime: 2017-06-01T12:54:44+00:00
- Post Title: Re: ARchive_neXt

Hello Can anyone please create Assassin's Creed 1, 2, brotherhood and syndicate forge  extractor
## Post #648
- Username: Sargeras
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 31, 2017 9:57 pm
- Post datetime: 2017-06-06T12:59:08+00:00
- Post Title: Re: ARchive_neXt

Does anyone know where CIN_Sword_R_01A is? (AC4)
## Post #649
- Username: Sargeras
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 31, 2017 9:57 pm
- Post datetime: 2017-06-07T23:39:32+00:00
- Post Title: Re: ARchive_neXt

How are the sound files called?
## Post #650
- Username: YangTuo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 28, 2017 7:56 pm
- Post datetime: 2017-06-30T12:44:52+00:00
- Post Title: Re: ARchive_neXt

Please give me ARchive_neXt v4.03.26.4 download link , 4.03.27 can't use for Ghost Recon Wildlands Beta, thanks
## Post #651
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-07-06T10:42:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from fahad00
>
> Hello Can anyone please create Assassin's Creed 1, 2, brotherhood and syndicate forge  extractor

ARchive_neXt can already extract from those games afaik.

About the missing files/textures, sadly you have to dig further into the archives. The structure is a bit messy in some cases and what you're looking for could be hidden in different packages.
## Post #652
- Username: SDWAN
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 12, 2017 9:04 pm
- Post datetime: 2017-07-08T18:20:07+00:00
- Post Title: Re: ARchive_neXt

So is For Honor able to extracted from at this moment or is it work in progress?
## Post #653
- Username: Soda1459
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Mar 02, 2017 3:03 am
- Post datetime: 2017-07-26T21:20:06+00:00
- Post Title: Re: ARchive_neXt

Is there any way to extract the text from the games, like the subtitles or description text ?
## Post #654
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-07-27T08:25:38+00:00
- Post Title: Re: ARchive_neXt

Is it possible to make extraction of all assets at once? it's very timetaking to export resources one by one to be able to combine them into full character.
## Post #655
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-08-21T08:24:33+00:00
- Post Title: Re: ARchive_neXt

> Reply from Tosyk
>
> Is it possible to make extraction of all assets at once? it's very timetaking to export resources one by one to be able to combine them into full character.

Not that I'm aware of... the way it is now you have to extract everything manually, unless I'm wrong. And even if you could extract all the parts at the same time you'd still need to combine everything yourself, loading each mesh and texture one by one.
## Post #656
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2017-08-22T09:54:52+00:00
- Post Title: Re: ARchive_neXt

> Reply from MichaelDarkAngel
>
> 

Click for larger image
--MDA

I'm unable to see the texture with the mesh like the above image. 
I can see the textures and white meshes separately but not together.

Can anybody tell me what is the problem?

I am using ARchive_neXt latest version 4.3.27.0 and trying to view model from "AC Unity".
## Post #657
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-08-22T15:03:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from blackfoxeye
>
> MichaelDarkAngel wrote:

Click for larger image
--MDA

I'm unable to see the texture with the mesh like the above image. 
I can see the textures and white meshes separately but not together.

Can anybody tell me what is the problem?

I am using ARchive_neXt latest version 4.3.27.0 and trying to view model from "AC Unity".

As far as I know, a lot of people have issues displaying models properly in ARchive_neXt. For some (like me) the models can't even be loaded and they get an error message every time. I am honestly not sure why you see the models but without textures...  does it happen with every archive? My only guess is that in some cases, the tool cannot properly locate the maps automatically and thus it won't load them along with the characters (there are some archives which contain the models, but you have to look for their textures elsewhere). If it happens with all the archives I'm afraid I have no clue... see if MDA knows what's going on on your part.
## Post #658
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2017-08-23T11:11:42+00:00
- Post Title: Re: ARchive_neXt

Yes, it happens with all the archives.
## Post #659
- Username: RunaWhite
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-09-10T07:40:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from blackfoxeye
>
> I'm unable to see the texture with the mesh like the above image. 
I can see the textures and white meshes separately but not together.

Can anybody tell me what is the problem?

I am using ARchive_neXt latest version 4.3.27.0 and trying to view model from "AC Unity".

> Reply from RunaWhite
>
> My only guess is that in some cases, the tool cannot properly locate the maps automatically and thus it won't load them along with the characters (there are some archives which contain the models, but you have to look for their textures elsewhere). If it happens with all the archives I'm afraid I have no clue... see if MDA knows what's going on on your part.

RunaWhite, has a pretty good understanding of my program.    If you are able to view the model, but it is not textured, it is most likely caused by the program not being able to find the associated textures.  If you have an idea of where those textures are located, try expanding those datafiles prior to viewing the model.  There is a video on my [website](http://www.tbotr.net/index.php) that shows what I am talking about.

If that doesn't work, give me some example models and I'll see if I can recreate the issue and possibly fix it if it's a bug.

Thanks,

--MDA
## Post #660
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-09-22T09:51:20+00:00
- Post Title: Re: ARchive_neXt

Also, this may sound weird but... I recently noticed that sometimes the tools can't properly work because of the game itself. Meaning, it all depends on how your files are structured and if everything is installed correctly. 
A few months ago I reported an issue regarding Jacob's textures in Jack the Ripper, which for some reason appeared corrupted. At some point, Uplay randomly decided to download the DLC all over again and right after that I could see the textures properly... no more issues.

So yeah, maybe this is not the case... but sometimes it's something not related to the program.
## Post #661
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-10-06T08:32:05+00:00
- Post Title: Re: ARchive_neXt

Young people, some of us are fooling us.
still the models and the skeletons were united. But we are still waiting. for what
they will never see us. The Maxscript file lies in the story of the battlefield.

There's a MaxScript they're showing us.but I still do not know what Maxscript is doing. can do the same job .obj form.

Who says the sorsam model can not be combined with the skeletons.(*arxs) But there is le who can do it. actually there is already. 
but they do not show it to us. nor do they teach us.

WHY
(send me messages to interested people.)
## Post #662
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-10-07T21:21:17+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> Young people, some of us are fooling us.
still the models and the skeletons were united. But we are still waiting. for what
they will never see us. The Maxscript file lies in the story of the battlefield.

There's a MaxScript they're showing us.but I still do not know what Maxscript is doing. can do the same job .obj form.

Who says the sorsam model can not be combined with the skeletons.(*arxs) But there is le who can do it. actually there is already. 
but they do not show it to us. nor do they teach us.

WHY
(send me messages to interested people.)

Maybe you should stop spamming people with your requests and ask politely, to begin with 

Someone managed to get functional weights and bones alright, but if they don't feel like sharing their personal script it's their choice. The person who made it is not even an active user in this forum as far as I know and MDA has stated many times he's busy and can barely update the tool from time to time.

If you want the rigged models so damn much you literally can't stop complaining around (because yes, I recognize your name, this is not the first time), maybe you should sit down and learn how to rig from scratch yourself... that is not impossible. I did so a long time ago when nobody could release the models I wanted, thus I'm sure you can easily find a lot of tutorials online.

Guys, you have to understand this is just a hobby for us. Playing around with in-game 3D models is fun, but people also got a life out there; a job, a family, friends, personal matters to take care of... if nobody has given you the answers you're looking for, most likely they can't or don't want to... and as much as you hate it you just have to be respectful and accept it.
## Post #663
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2017-10-26T21:11:17+00:00
- Post Title: Re: ARchive_neXt

Assassin's Creed Origins plx
## Post #664
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-01T06:23:13+00:00
- Post Title: Re: ARchive_neXt

Hello to everyone

I will have a wish from you.
This raw file needs to be imported into the 3d environment. 3ds max or blender script can be done.

It must not be too hard.

İs there anyone who can do this job?
I hope someone is so kind to guide me with this.
Thanks in advance

for more details: [https://forum.xentax.com/viewtopic.php? ... 61#p134861](https://forum.xentax.com/viewtopic.php?f=16&t=17210&p=134861#p134861)
## Post #665
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-01T07:44:28+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> TSelman61X wrote:Young people, some of us are fooling us.
still the models and the skeletons were united. But we are still waiting. for what
they will never see us. The Maxscript file lies in the story of the battlefield.

There's a MaxScript they're showing us.but I still do not know what Maxscript is doing. can do the same job .obj form.

Who says the sorsam model can not be combined with the skeletons.(*arxs) But there is le who can do it. actually there is already. 
but they do not show it to us. nor do they teach us.

WHY
(send me messages to interested people.)

Maybe you should stop spamming people with your requests and ask politely, to begin with 

Someone managed to get functional weights and bones alright, but if they don't feel like sharing their personal script it's their choice. The person who made it is not even an active user in this forum as far as I know and MDA has stated many times he's busy and can barely update the tool from time to time.

If you want the rigged models so damn much you literally can't stop complaining around (because yes, I recognize your name, this is not the first time), maybe you should sit down and learn how to rig from scratch yourself... that is not impossible. I did so a long time ago when nobody could release the models I wanted, thus I'm sure you can easily find a lot of tutorials online.

Guys, you have to understand this is just a hobby for us. Playing around with in-game 3D models is fun, but people also got a life out there; a job, a family, friends, personal matters to take care of... if nobody has given you the answers you're looking for, most likely they can't or don't want to... and as much as you hate it you just have to be respectful and accept it.
(I was not aware that the message was answered)

"There are too many important things in life to whine about a 3D model, don't you think? "
I know I know 
I am aware that I have done wrong with such an approach, my ...
I apologize to everyone.

you do not know the importance for me.
please do not be angry here
If it were so easy to do, we would not have gathered so many people here.
If you think Maxscript is easy, you're wrong.you also need to know how to use Hex.(there is nothing you can not do with professional Hex software.)


he will tell me now "Have you ever tried to learn?".As a matter of fact, I know. but very few and simple things. Thanks to mariokart64n. [ [https://www.youtube.com/user/mariokart64n/videos](https://www.youtube.com/user/mariokart64n/videos) ]
If you lived in my country, really do you think you can do this?(no look at where you live)
I am sure that, as someone begs you, your...   / I will stop here.
I keep my promise.
anyway

I feel like you're angry when I see your next post.
I hope you read this post.

everyone have a good day
## Post #666
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-01T12:38:51+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> TSelman61X wrote:Young people, some of us are fooling us.
still the models and the skeletons were united. But we are still waiting. for what
they will never see us. The Maxscript file lies in the story of the battlefield.

There's a MaxScript they're showing us.but I still do not know what Maxscript is doing. can do the same job .obj form.

Who says the sorsam model can not be combined with the skeletons.(*arxs) But there is le who can do it. actually there is already. 
but they do not show it to us. nor do they teach us.

WHY
(send me messages to interested people.)

Maybe you should stop spamming people with your requests and ask politely, to begin with 

Someone managed to get functional weights and bones alright, but if they don't feel like sharing their personal script it's their choice. The person who made it is not even an active user in this forum as far as I know and MDA has stated many times he's busy and can barely update the tool from time to time.

If you want the rigged models so damn much you literally can't stop complaining around (because yes, I recognize your name, this is not the first time), maybe you should sit down and learn how to rig from scratch yourself... that is not impossible. I did so a long time ago when nobody could release the models I wanted, thus I'm sure you can easily find a lot of tutorials online.

Guys, you have to understand this is just a hobby for us. Playing around with in-game 3D models is fun, but people also got a life out there; a job, a family, friends, personal matters to take care of... if nobody has given you the answers you're looking for, most likely they can't or don't want to... and as much as you hate it you just have to be respectful and accept it.

Look at the person you want to be kind. [ zaramot ]  [https://forum.xentax.com/viewtopic.php?p=134865#p134865](https://forum.xentax.com/viewtopic.php?p=134865#p134865)
how kind he is.
sorry. when he spoke badly, I talked to him badly.
I tried to be good.

Is there anything you want to say?
## Post #667
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-11-01T12:43:35+00:00
- Post Title: Re: ARchive_neXt

Does someone have Assassins Creed Origins file samples to upload?
## Post #668
- Username: Albotterin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 19, 2017 4:31 pm
- Post datetime: 2017-11-02T14:36:54+00:00
- Post Title: Re: ARchive_neXt

Is there a way to extact models from AC:Origins?
## Post #669
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-11-03T00:02:00+00:00
- Post Title: Re: ARchive_neXt

@TSelman61X: I honestly don't know why you're dragging other drama into this. Answering with a middle finger when the other person didn't really insult you is questionable, but I don't care about what kind of issues you might have with other people here. I'm not angry, just tired of reading the same complaints over and over again, so I kindly ask you to please finally drop it and interact with us in a civil way. If you don't want to do it for a perfect stranger like myself, at least do so for MDA who put a lot of time and efforts into ARchive_neXt. Sometimes I feel like some of you guys just don't appreciate his work the way it deserves.

@Gh0stBlade: Sadly I don't have the game yet. What kind of files do you need eventually?

@Albotterin: The game just came out, let's give MDA the time to buy it if he wants and explore the archives.
## Post #670
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-03T05:16:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from Gh0stBlade
>
> Does someone have Assassins Creed Origins file samples to upload?

I have the STEAM game, what files you need?
## Post #671
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:01:44+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> @TSelman61X: I honestly don't know why you're dragging other drama into this. Answering with a middle finger when the other person didn't really insult you is questionable, but I don't care about what kind of issues you might have with other people here. I'm not angry, just tired of reading the same complaints over and over again, so I kindly ask you to please finally drop it and interact with us in a civil way. If you don't want to do it for a perfect stranger like myself, at least do so for MDA who put a lot of time and efforts into ARchive_neXt. Sometimes I feel like some of you guys just don't appreciate his work the way it deserves.

@ RunaWhite Please tell me
You are saying,"But I do not care about what kind of issues you might have with other people here." please look,  If you read the head of the post, you will realize that I have not started this.
"why you're dragging other drama into this." if you want me to answer, He knows why I quote.
I tried to be polite as I said.

My respect for you and MDA  is endless.but there is a fine line. When you are insulted to me, respect will finish.

but will you tell me why you do not share these tools with us."you  know"
I hope you do not perceive this post as disrespectful.I apologize to everyone if I have a disrespect.
good luck
## Post #672
- Username: RunaWhite
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-11-03T09:25:16+00:00
- Post Title: Re: ARchive_neXt

Stay on topic please. No more arguing or spamming this thread. If you have a problem with someone report their posts.
## Post #673
- Username: Hellethia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 07, 2017 7:35 am
- Post datetime: 2017-11-06T23:40:42+00:00
- Post Title: Re: ARchive_neXt

Hello, i tried to download Archive_Next, but i can't reach the website, got a 403 error all the time whatever the link 
Any way to revocer the program somewhere ? I'd like to extract the Evie's Frye Bloofer outfit from ACS 

Thank you very much !
## Post #674
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-11-07T17:31:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from Hellethia
>
> Hello, i tried to download Archive_Next, but i can't reach the website, got a 403 error all the time whatever the link 
Any way to revocer the program somewhere ? I'd like to extract the Evie's Frye Bloofer outfit from ACS 

Thank you very much !

Weird, it works on my part... try this link and see if the download pops up [http://www.tbotr.net/modules.php?mod=Do ... 40&serve=1](http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=40&serve=1)
## Post #675
- Username: Hellethia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 07, 2017 7:35 am
- Post datetime: 2017-11-07T22:30:30+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Hellethia wrote:Hello, i tried to download Archive_Next, but i can't reach the website, got a 403 error all the time whatever the link 
Any way to revocer the program somewhere ? I'd like to extract the Evie's Frye Bloofer outfit from ACS 

Thank you very much !

Weird, it works on my part... try this link and see if the download pops up http://www.tbotr.net/modules.php?mod=Do ... 40&serve=1

Thank you, but same problem, i got the 403 error page
## Post #676
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-11-09T10:13:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from Hellethia
>
> RunaWhite wrote:Hellethia wrote:Hello, i tried to download Archive_Next, but i can't reach the website, got a 403 error all the time whatever the link 
Any way to revocer the program somewhere ? I'd like to extract the Evie's Frye Bloofer outfit from ACS 

Thank you very much !

Weird, it works on my part... try this link and see if the download pops up http://www.tbotr.net/modules.php?mod=Do ... 40&serve=1

Thank you, but same problem, i got the 403 error page

is the first time you try to reach that website? If so, maybe is blocked in your country, sometimes happens with some sites.
Try using a proxy server

```
http://11proxy.pw/b.php?u=dyRYHz%2BkNReA2nMV1ScsvmxvC9zzPznwRD2y%2B1LjTwxvXtO7QiQb%2Ft20tuxsveCNTP3mpWSwE%2F5RNnjlOYWaM9YMNV%2FV7oO1eKNq6qtLkD%2FwyCA%3D&b=14&f=norefer
```
## Post #677
- Username: Hellethia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 07, 2017 7:35 am
- Post datetime: 2017-11-09T22:54:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from fil1969
>
> 

is the first time you try to reach that website? If so, maybe is blocked in your country, sometimes happens with some sites.
Try using a proxy server
Code: Select allhttp://11proxy.pw/b.php?u=dyRYHz%2BkNReA2nMV1ScsvmxvC9zzPznwRD2y%2B1LjTwxvXtO7QiQb%2Ft20tuxsveCNTP3mpWSwE%2F5RNnjlOYWaM9YMNV%2FV7oO1eKNq6qtLkD%2FwyCA%3D&b=14&f=norefer

I'm in France, not supposed to be blocked then.
I won't pay and use a proxy for a tool anyway.

Could anybody send the tools to me ? Or host it elsewhere ?
## Post #678
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2017-11-10T06:01:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from Hellethia
>
> RunaWhite wrote:Hellethia wrote:Hello, i tried to download Archive_Next, but i can't reach the website, got a 403 error all the time whatever the link 
Any way to revocer the program somewhere ? I'd like to extract the Evie's Frye Bloofer outfit from ACS 

Thank you very much !

Weird, it works on my part... try this link and see if the download pops up http://www.tbotr.net/modules.php?mod=Do ... 40&serve=1

Thank you, but same problem, i got the 403 error page

If you still can not download it you can download it here.

ARchive_neXt_v3_02_07_0:  [https://drive.google.com/open?id=1ZlLso ... I--H-Hr-hl](https://drive.google.com/open?id=1ZlLsoWYYXGymUk697F5BrhI--H-Hr-hl)

ARchive_neXt_v4_03_27_0:  [https://drive.google.com/open?id=1LA3l7 ... T3h-dJ7gz8](https://drive.google.com/open?id=1LA3l7iFLBmL0zN56fv__1IT3h-dJ7gz8)

______________________________
Click the thanks button if I helped!
## Post #679
- Username: gentlegiantJGC
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 10, 2017 8:49 pm
- Post datetime: 2017-11-10T13:01:15+00:00
- Post Title: Re: ARchive_neXt

Hey all. This is slightly off topic but hopefully it is okay.

I have been trying to port some of the ARchive_neXt code base to python and made quite a bit of progress with AC Unity. My main aim is to be able to export sections of the world with everything alligned and scaled correctly and I have made a lot of progress. (I can now export quite a lot alligned and scaled correctly)

I just wanted to ask if anyone else has tried reverse engineering the entity and entity group file formats? (or if there is a simpler way than just manually finding the patterns in the hex) I believe these two are part of the key to get allignment and scale. I have mostly got entities working and just started on entity groups

gentlegiantJGC
## Post #680
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-11-10T18:59:40+00:00
- Post Title: Re: ARchive_neXt

Hello MichaelDarkAngel,

I'm trying to extract For Honor without success. I think you might help here because game is free for weekend and has a lot additions within.
Please take look till the end of the free weekends: 9-12 november. Game can be downloaded/play for free.

Regards,
Tosyk
## Post #681
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2017-11-21T12:16:45+00:00
- Post Title: Re: ARchive_neXt

Aguilar de Nerha
[Agulilar_T.jpg](https://xentaxbackup.github.io/file/13576_Agulilar_T.jpg)
## Post #682
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-26T08:43:49+00:00
- Post Title: Re: ARchive_neXt

hello
tell me how to convert assassins creed unity hair mesh to static object
## Post #683
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2017-11-27T00:18:03+00:00
- Post Title: Re: ARchive_neXt

> Reply from Crazy31139
>
> hello
tell me how to convert assassins creed unity hair mesh to static object

Yeah. I know how you were made, can help you.
I can do it in 2 different ways.
We can use blender.
...
## Post #684
- Username: PlatZ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 07, 2017 12:46 am
- Post datetime: 2017-12-14T19:17:17+00:00
- Post Title: Re: ARchive_neXt

Hi all !

When i'm using Archive next, I have an error from Microsoft Framework, and I can't explore the files anymore. Each time I try to explore a file, a message appears, saying "not a compressed DATA" and it's replaced by a "placholder". What can I do ?
## Post #685
- Username: GilbertTheGoose
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 30, 2017 12:23 am
- Post datetime: 2017-12-14T22:24:09+00:00
- Post Title: Re: ARchive_neXt

Does anyone know whether support for AC Origins will be added for this?
## Post #686
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2017-12-16T00:54:49+00:00
- Post Title: Re: ARchive_neXt

I've got a problem with the OBJ exporter and UV maps/Textures. When I export the OBJ file from Assassin's Creed: Syndicate (Black Flag has the same problem), I get a blank .MTL file without and UV coordinates. When I import into Blender or 3DS Max 2018, I don't get any textures. When I import the textures manually, the textures are scaled wrong, because of the broken UV maps. Any help would be appreciated. Also, textures appear pure white in the model viewer.

EDIT: Huh, weird. In Assassin's Creed Rogue, the textures show up and it exports textures and UV maps.
EDIT 2: It works now! Just make sure the textures are in the same place as the models. I was looking at the main menu archive, but I found them in datapc_london.
EDIT 3: Never mind. It worked on Jacob's fight club model, but not his player models. Looks like it works on all the unimportant files (E.G. Lydia Frye, Fight Club models)
EDIT 4: Yes! Finally! You just have to find where the textures are located and expand them. Have all the textures expanded, then open the model.
EDIT 5: Well, that fixed the preview. However, it still doesn't export textures and the .mtls are empty.

ACVI_CHR_P_JacobFrye_Outfit01_Body_LOD0.mtl:

```
# Exported by ARchive_neXt v4.03.27.0 on 12/15/2017 4:48:17 PM

```


Thanks,
TrumpetPro
## Post #687
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2017-12-16T01:38:26+00:00
- Post Title: Re: ARchive_neXt

MichaelDarkAngel, you said you figured out the bone and weight format in older AC games. Could you add support for this in Archive_Next? I know you can import skeletons, but I can't seem to import the weights.
## Post #688
- Username: Andersson799
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 08, 2016 4:16 pm
- Post datetime: 2017-12-17T13:18:13+00:00
- Post Title: Re: ARchive_neXt

Please update for the latest rainbow six siege.
I need to extract the textures...
## Post #689
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-12-18T10:56:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from TrumpetPro
>
> I've got a problem with the OBJ exporter and UV maps/Textures. When I export the OBJ file from Assassin's Creed: Syndicate (Black Flag has the same problem), I get a blank .MTL file without and UV coordinates. When I import into Blender or 3DS Max 2018, I don't get any textures. When I import the textures manually, the textures are scaled wrong, because of the broken UV maps. Any help would be appreciated. Also, textures appear pure white in the model viewer.

EDIT: Huh, weird. In Assassin's Creed Rogue, the textures show up and it exports textures and UV maps.
EDIT 2: It works now! Just make sure the textures are in the same place as the models. I was looking at the main menu archive, but I found them in datapc_london.
EDIT 3: Never mind. It worked on Jacob's fight club model, but not his player models. Looks like it works on all the unimportant files (E.G. Lydia Frye, Fight Club models)
EDIT 4: Yes! Finally! You just have to find where the textures are located and expand them. Have all the textures expanded, then open the model.
EDIT 5: Well, that fixed the preview. However, it still doesn't export textures and the .mtls are empty.

ACVI_CHR_P_JacobFrye_Outfit01_Body_LOD0.mtl:
Code: Select all# Material Library
# Exported by ARchive_neXt v4.03.27.0 on 12/15/2017 4:48:17 PM


Thanks,
TrumpetPro

You have to export textures yourself, especially if you save in OBJ format. Sometimes you automatically get DDS diffuses saved with the meshes, but in the 90% of cases you need to explore all the other directories to find what you need. Regarding the UVs issue, they are not broken but flipped vertically. This happens for some reason if you export in OBJ format, just flip the textures vertically and they should work.
## Post #690
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2017-12-18T17:06:46+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> TrumpetPro wrote:I've got a problem with the OBJ exporter and UV maps/Textures. When I export the OBJ file from Assassin's Creed: Syndicate (Black Flag has the same problem), I get a blank .MTL file without and UV coordinates. When I import into Blender or 3DS Max 2018, I don't get any textures. When I import the textures manually, the textures are scaled wrong, because of the broken UV maps. Any help would be appreciated. Also, textures appear pure white in the model viewer.

EDIT: Huh, weird. In Assassin's Creed Rogue, the textures show up and it exports textures and UV maps.
EDIT 2: It works now! Just make sure the textures are in the same place as the models. I was looking at the main menu archive, but I found them in datapc_london.
EDIT 3: Never mind. It worked on Jacob's fight club model, but not his player models. Looks like it works on all the unimportant files (E.G. Lydia Frye, Fight Club models)
EDIT 4: Yes! Finally! You just have to find where the textures are located and expand them. Have all the textures expanded, then open the model.
EDIT 5: Well, that fixed the preview. However, it still doesn't export textures and the .mtls are empty.

ACVI_CHR_P_JacobFrye_Outfit01_Body_LOD0.mtl:
Code: Select all# Material Library
# Exported by ARchive_neXt v4.03.27.0 on 12/15/2017 4:48:17 PM


Thanks,
TrumpetPro

You have to export textures yourself, especially if you save in OBJ format. Sometimes you automatically get DDS diffuses saved with the meshes, but in the 90% of cases you need to explore all the other directories to find what you need. Regarding the UVs issue, they are not broken but flipped vertically. This happens for some reason if you export in OBJ format, just flip the textures vertically and they should work.

OK Thanks. What about rigging? Any way to get the skeleton working with weights, even in the older games? I know how to export it, but not how to bind it without weight painting manually.
## Post #691
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2017-12-18T20:01:08+00:00
- Post Title: Re: ARchive_neXt

I found something interesting in the importer's code, thanks to a (lucky, I guess) crash.
Excerpt from arxfnimport.ms:

```
	
	--	Skin Meshes
	
	--	Removed
	/*
	if arxVersion == "V5" then (
	
		for i = 1 to srtArxModelData.skinCount do (
		
			arxImportUI.lblProgress.text = "Skinning"
			
			if srtArxSkinData[i].arxBoneCount > 0 then (
			
				newMesh = (getNodeByName meshArray[i])
				
				max modify mode
				select newMesh
				addModifier newMesh (skin())
				
				--	Add Bones
				
				for x = 1 to srtArxSkinData[i].arxBoneCount do (
				
					skinOps.addBone newMesh.skin (getNodeByName (boneArray[srtArxSkinData[i].arxBones[x] + 1])) 0
					
				)
				
				--	End Add Bones
				
				update newMesh
				max select none
				select newMesh
				
				--	Add Weights
				
				arxImportUI.pgbProgress.value = 0
				
				for x = 1 to srtArxMeshData[i].vertCount do (
				
					mySkin = newMesh.skin
					
					for y = 1 to 8 do (
					
						if srtArxMeshData[i].arxBones[x][y] > 0 then (
						
							myBone = srtArxMeshData[i].arxBones[x][y]
							myWeight = srtArxMeshData[i].arxWeights[x][y] / 255.0
							
							skinOps.setVertexWeights mySkin x myBone myWeight
							
						)
						
					)
					
					arxImportUI.pgbProgress.value = 100.0 * x / srtArxMeshData[i].vertCount
					
				)
				
				update newMesh
				max select none
				
				--	End Add Weights
				
			)
			
		)
		
	)
	*/

```

Looks like there was a weight importer at one point. Any way to enable this again? Uncommenting it doesn't seem to do anything with AC4.
And was it ever actually implemented in a version of the importer/software?

EDIT: Just read a bit more, some older versions did have skeleton and skin support (v2.01.17 through v2.01.22). Anybody have downloads for those?
## Post #692
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2017-12-18T21:59:26+00:00
- Post Title: Re: ARchive_neXt

Never mind about the ARXImporter. Just found ALL of TBOTR.net's downloads. [http://www.tbotr.net/Downloads/](http://www.tbotr.net/Downloads/)

EDIT: Wait, it doesn't include any of the V2 versions before they removed skinning and weights. Are they gone forever? Could somebody either give a version of the arximporter with weight support and tell me how to use it, or send me a download you happen to have on your PC? Thanks

EDIT 2: I removed all the commented skin-related lines, and now I get this error:
[https://imgur.com/a/gvoks](https://imgur.com/a/gvoks)
## Post #693
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2017-12-19T22:45:04+00:00
- Post Title: Re: ARchive_neXt

> Reply from TrumpetPro
>
> Never mind about the ARXImporter. Just found ALL of TBOTR.net's downloads. http://www.tbotr.net/Downloads/

EDIT: Wait, it doesn't include any of the V2 versions before they removed skinning and weights. Are they gone forever? Could somebody either give a version of the arximporter with weight support and tell me how to use it, or send me a download you happen to have on your PC? Thanks

EDIT 2: I removed all the commented skin-related lines, and now I get this error:
https://imgur.com/a/gvoks

What script did you use here?  [send me the linkin]

how did you know it worked before?if you are sure that you are working in advance, there is only one reason you do not work now.(you are using 3ds max 18) It does not work in the new 3ds max. 
I think you should try it in older versions to find out
## Post #694
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2017-12-20T00:53:53+00:00
- Post Title: Re: ARchive_neXt

> Reply from Eda61
>
> TrumpetPro wrote:Never mind about the ARXImporter. Just found ALL of TBOTR.net's downloads. http://www.tbotr.net/Downloads/

EDIT: Wait, it doesn't include any of the V2 versions before they removed skinning and weights. Are they gone forever? Could somebody either give a version of the arximporter with weight support and tell me how to use it, or send me a download you happen to have on your PC? Thanks

EDIT 2: I removed all the commented skin-related lines, and now I get this error:
https://imgur.com/a/gvoks

What script did you use here?  [send me the linkin]

how did you know it worked before?if you are sure that you are working in advance, there is only one reason you do not work now.(you are using 3ds max 18) It does not work in the new 3ds max. 
I think you should try it in older versions to find out

Do you know what version of 3DS Max it did work on? I have 2016 and 2018, but can download 2014 if nessessary.
[http://www.mediafire.com/file/jtloijixi ... mporter.7z](http://www.mediafire.com/file/jtloijixizmbux8/arxImporter.7z)

EDIT: Just downloaded 3DS Max 2014, wasn't working. That's the oldest version I have.
## Post #695
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2017-12-24T15:49:16+00:00
- Post Title: Re: ARchive_neXt

As far as I know the arx importer available never imported weights and bones. There only is the skeleton support with info in ARchive_NeXT, but tha't pretty much it. 
MDA will correct me if I'm wrong though.
## Post #696
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-12-27T16:04:29+00:00
- Post Title: Re: ARchive_neXt

hey guys! all of you!
i'm so sorry but all of this try (for everything about forge) is bullshit! (im so so so so so sorry about that, but thats true)
i created a tool for Price of Persia 2008 and the forgoten sands
and i edited texture, font & glyph, text of subtitles and menus
just that... and you guys are not a hard work, a humen can get to everything with trying...
just trying on a tool for unsourse & resourse forge. i did it for prince of persia... but not working on other games
and ARchive_neXt is not a real texturing...
just try on decompressing tool on forge files... just that... everything else is crap!
anyway, sorry about that...
## Post #697
- Username: ttruva
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 15, 2016 12:27 am
- Post datetime: 2017-12-29T23:23:51+00:00
- Post Title: Re: ARchive_neXt

Hi,

Thanks for this great explorer.
I wanna export a model from Assasin's Creed: Revelations, but for any model which I click, I am getting an error and it makes me terminate the program. The first error outputs the followings;
Error viewing the model!
Microsoft.DirectX.Direct3D.Mesh.FromFile(String filename, MeshFlags options, Device device, GraphicsStream& adjacency, ExtendedMaterial[]& materials, EffectInstance[]& effects)
Microsoft.DirectX.Direct3D.Mesh.FromFile(String filename, MeshFlags options, Device device, GraphicsStream& adjacency, ExtendedMaterial[]& materials, EffectInstance[]& effects)
ARchive_neXt.arxFrom.arxInitializeGraphics(String mdlFile)
After that:
Error drawing the mesh!
ARchive_neXt.arxForm.arxDrawMesh()

Did any of you guys export "Basilica Cistern" from Assasin's Creed: Revelations ?

Thanks in advance,
## Post #698
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2018-01-05T20:33:32+00:00
- Post Title: Re: ARchive_neXt

Hi guys, searching for days, for months, and it's a year now, we asked for Rainbow six siege ARchive_neXt support, but no one want to tell us the method to do that, i know two guys who are capable to do that but they don't want to share it, so it's impossible ?!
## Post #699
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-02-04T09:41:39+00:00
- Post Title: Re: ARchive_neXt

Hello guys, will there be an unpacker for AC:O ?
## Post #700
- Username: mwesten1
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jul 09, 2016 3:27 am
- Post datetime: 2018-02-19T21:35:01+00:00
- Post Title: Re: ARchive_neXt

i want to get few models from Paris in assassins creed unity, but every time i want to see a mesh, i get an error and have to close program from task manager. Anyone has the solution?
## Post #701
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2018-03-03T08:16:38+00:00
- Post Title: Re: ARchive_neXt

> Reply from mwesten1
>
> i want to get few models from Paris in assassins creed unity, but every time i want to see a mesh, i get an error and have to close program from task manager. Anyone has the solution?

I'm in pretty much exactly the same sitiation.
I want pretty much just a single weapon mesh from Unity (maybe a few others, once I find out how, but nothing grand or significant in scale) but whatever I try i get errors every time I try to open a mesh.
MDA said somewhere on here that you should, despite the error, still be able to export meshes, however, this is not true for me, ceaseless pop-ups make any sort of export quite impossible.
## Post #702
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-03-13T03:51:56+00:00
- Post Title: Re: ARchive_neXt

Any plans for Assassin's Creed: Origins or weighted skeleton support?
## Post #703
- Username: kiltro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 29, 2018 10:58 pm
- Post datetime: 2018-03-29T15:09:49+00:00
- Post Title: Re: ARchive_neXt

Getting errors and no preview here too



Also if I right click on the Mesh and export all as obj, I get nothing when imported in Blender, I've tried in Maya without any luck too... (obj are more or less 100kb)

Please help
## Post #704
- Username: halobungie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 06, 2018 11:50 pm
- Post datetime: 2018-04-06T15:51:46+00:00
- Post Title: Re: ARchive_neXt

Hello,
is it possible to rip 3d Models from Assassin's Creed Origins too? If yes, how?
## Post #705
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-04-14T21:33:11+00:00
- Post Title: Re: ARchive_neXt

I'm not sure if it's just me, but i am unable to extract succesfully any models from Ghost Recon: Wildlands. On Archive_Next, when trying to view any mesh, it gives endless amounts of errors and if you try to export the content of a spesific mesh folder into .obj format, the final product is completely broken.
## Post #706
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-04-16T21:45:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from ravenov
>
> Hi guys, searching for days, for months, and it's a year now, we asked for Rainbow six siege ARchive_neXt support, but no one want to tell us the method to do that, i know two guys who are capable to do that but they don't want to share it, so it's impossible ?!

They were probably using Intel GPA. AFAIK it is the only way ATM.

> Reply from mwesten1
>
> i want to get few models from Paris in assassins creed unity, but every time i want to see a mesh, i get an error and have to close program from task manager. Anyone has the solution?

It is working just fine here. What model exactly?

> Reply from Graesholt
>
> mwesten1 wrote:i want to get few models from Paris in assassins creed unity, but every time i want to see a mesh, i get an error and have to close program from task manager. Anyone has the solution?

I'm in pretty much exactly the same sitiation.
I want pretty much just a single weapon mesh from Unity (maybe a few others, once I find out how, but nothing grand or significant in scale) but whatever I try i get errors every time I try to open a mesh.
MDA said somewhere on here that you should, despite the error, still be able to export meshes, however, this is not true for me, ceaseless pop-ups make any sort of export quite impossible.

It is fully working here, what are you trying to extract?

> Reply from halobungie
>
> Hello,
is it possible to rip 3d Models from Assassin's Creed Origins too? If yes, how?

ATM no.
## Post #707
- Username: halobungie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 06, 2018 11:50 pm
- Post datetime: 2018-04-17T15:14:57+00:00
- Post Title: Re: ARchive_neXt

Hello, 
i am trying to extract some 3d Models from a Egypt Statue or a Sphinx from Assassin Creed Origins.
Can you help me please?
Kind regards,
Andreas
## Post #708
- Username: lilwaifu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 29, 2018 5:57 am
- Post datetime: 2018-04-28T22:03:59+00:00
- Post Title: Re: ARchive_neXt

Hello everyone! Can someone please extract the Nobushi Helmet from For Honor? Specifically the medf_hero_samurai_hybrid_set02_helm 
I'd like it as an OBJ, for some reason whenever i click on a mesh to view it the program gives me mounds of errors, and i've tried looking at older forum posts from 2017 about workarounds and fixes but to no avail. Thanks in advance 

[https://gyazo.com/5636be99c8eea4f6a9f2a91bd769a0f7](https://gyazo.com/5636be99c8eea4f6a9f2a91bd769a0f7) <- (a screenshot of the specific helmet I desire with the texture map open.)


And as a bonus, I'd actually like to get these errors fixed, This is what i'm getting.
After selecting the desired model, I am greeted with this error
[https://gyazo.com/3246b348a33c26c747dc8d9c92062c4b](https://gyazo.com/3246b348a33c26c747dc8d9c92062c4b)

Following the error, after pressing OK, I get a second error.
[https://gyazo.com/c0d682d49c6beabc01608c3a100668c6](https://gyazo.com/c0d682d49c6beabc01608c3a100668c6)

After pressing OK for the last time, the background goes from black (I set it to black) to cornflower blue.
any help would be much much appreciated, Thank you!
## Post #709
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2018-05-17T12:00:46+00:00
- Post Title: Re: ARchive_neXt

Hello, can someone say if this tool is officially obsolete on w10? I can't open a single mesh from Assassin's Creed 3. And yeah I see there a many comments with the same problem.

1. Error


2.Error


And I need to close the process with Task Manager...
## Post #710
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-05-20T16:12:52+00:00
- Post Title: Re: ARchive_neXt

Hey guys, 
whats the story with For Honor? Been looking to extract those models since it came out, and this thread is massively confusing as to what to do, and where its at.
## Post #711
- Username: pauloegidio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 30, 2018 12:17 am
- Post datetime: 2018-05-29T17:43:08+00:00
- Post Title: Re: ARchive_neXt

I extracted a ram statue model from the game.

I did it using photogrammetry, take about 400 screenshots and processed it manually. lots of work...

This is the original file exported from photoscan. You can load it in blender or other program to change things...

However it will really be nice to rip some models from the game.

[https://drive.google.com/file/d/1wLYQYN ... sp=sharing](https://drive.google.com/file/d/1wLYQYNvfatW5LHwTC0XY0WDkF4izrBcv/view?usp=sharing)

Best regards
Paulo
## Post #712
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2018-06-03T10:17:20+00:00
- Post Title: Re: ARchive_neXt

> Reply from lolwatt
>
> Graesholt wrote:I'm in pretty much exactly the same sitiation.
I want pretty much just a single weapon mesh from Unity (maybe a few others, once I find out how, but nothing grand or significant in scale) but whatever I try i get errors every time I try to open a mesh.
MDA said somewhere on here that you should, despite the error, still be able to export meshes, however, this is not true for me, ceaseless pop-ups make any sort of export quite impossible.
It is fully working here, what are you trying to extract?
I would like to extract this one long weapon called [Cogneur](https://imgur.com/a/evJFQ).
If the tool works on your machine, would you be willing to pull it out and send it to me?
## Post #713
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-06-22T22:01:26+00:00
- Post Title: Re: ARchive_neXt

Whenever I view a model in GR: Wildlands, it gives me an error saying it is unable to draw the mesh and I have to shut down the entire program to close the message. It's really annoying when I'm knee deep in the list of available things.

Edit: Also, would it be possible if the mipmap diffuse maps could be made extractable  as well?
## Post #714
- Username: killonious
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 18, 2017 2:23 am
- Post datetime: 2018-06-27T11:38:32+00:00
- Post Title: Re: ARchive_neXt

Is there a way to do a search in ARchive_neXt?
## Post #715
- Username: KhavitZ
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 02, 2018 4:57 am
- Post datetime: 2018-07-02T11:53:03+00:00
- Post Title: Re: ARchive_neXt

Any plans for AC Origins ?
## Post #716
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-07-28T11:19:19+00:00
- Post Title: Re: ARchive_neXt

Would it be possible if the mipmap textures would be extractable for GR: Wildlands? I would be very greatful for that.

Here's a sample:
[FCP_Head_Cau_NinaP_DiffuseMap_Mip1.7z](https://xentaxbackup.github.io/file/14672_FCP_Head_Cau_NinaP_DiffuseMap_Mip1.7z)
## Post #717
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2018-08-02T08:32:02+00:00
- Post Title: Re: ARchive_neXt

Anyone have the weapons already extracted?
## Post #718
- Username: jarretdd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 11, 2018 2:19 am
- Post datetime: 2018-08-09T21:31:47+00:00
- Post Title: Re: ARchive_neXt

As many other people have already posted, extracting For Honor models simply doesn't work. Clicking the mesh name in ARchibe_neXt pops errors. Right-clicking and exporting throws up an exception, and exporting raw makes a blank file.
What's going on with this?



error1.JPG (23.23 KiB) Viewed 125 times
## Post #719
- Username: Riscal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2018 4:15 pm
- Post datetime: 2018-08-14T08:40:42+00:00
- Post Title: Re: ARchive_neXt

I have the same problem, and when I also tried to run it on a machine with w7, it gives the same error, so I think it´s not related to w10 itself. Any suggestion ?

> Reply from Kaem
>
> Hello, can someone say if this tool is officially obsolete on w10? I can't open a single mesh from Assassin's Creed 3. And yeah I see there a many comments with the same problem.

1. Error


2.Error


And I need to close the process with Task Manager...
## Post #720
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2018-08-20T08:39:31+00:00
- Post Title: Re: ARchive_neXt

someone can extract exo suit and termite pack?
## Post #721
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-08-22T09:34:08+00:00
- Post Title: Re: ARchive_neXt

Tom Clancy's Ghost Recon: Wildlands  "Gabriela Contreras"
It has bone and bone weights.
[Gabrialler.jpg](https://xentaxbackup.github.io/file/14770_Gabrialler.jpg)
## Post #722
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-08-22T09:44:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from MaZTeR
>
> Would it be possible if the mipmap textures would be extractable for GR: Wildlands? I would be very greatful for that.

Here's a sample:

Mip0, Mip1 or TopMip_0, TopMip_1 I have not seen anyone who can export the file. Or it's all a conspiracy theory.

btw: I think that Mip0 maps have a better resolution than Mip1.
## Post #723
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2018-08-22T12:26:13+00:00
- Post Title: Re: ARchive_neXt

WIP LVOA


[https://sketchfab.com/models/0cac549f01 ... 9eb66af05e](https://sketchfab.com/models/0cac549f013b487eafa1c19eb66af05e)
## Post #724
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-08-22T15:49:51+00:00
- Post Title: Re: ARchive_neXt

> Reply from mattyshido
>
> WIP LVOA
https://sketchfab.com/models/0cac549f01 ... 9eb66af05e

Nice work.
But I guess you just used diffuse map. It would be nice if you used it on other maps. 
Especially the texture maps which are "MaskMap".
## Post #725
- Username: Riscal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 14, 2018 4:15 pm
- Post datetime: 2018-08-22T16:26:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from jarretdd
>
> As many other people have already posted, extracting For Honor models simply doesn't work. Clicking the mesh name in ARchibe_neXt pops errors. Right-clicking and exporting throws up an exception, and exporting raw makes a blank file.
What's going on with this?
error1.JPG

I think it´s not related to a particular game but the tool itself must have some settings we may be missing. On the other side the silence of the community on this surprises me. Hope someone can look at this and come with a helpful idea...
## Post #726
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-08-22T17:18:16+00:00
- Post Title: Re: ARchive_neXt

[quote="TSelman61X"]Tom Clancy's Ghost Recon: Wildlands  "Gabriela Contreras"
It has bone and bone weights.[/quot

Is it the bones and weight from the game?
If yes, how did you get it
## Post #727
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-08-23T09:33:51+00:00
- Post Title: Re: ARchive_neXt

> Reply from Faithfullfaun
>
> TSelman61X wrote:Tom Clancy's Ghost Recon: Wildlands  "Gabriela Contreras"
It has bone and bone weights. 
Is it the bones and weight from the game?
If yes, how did you get it
Yeah, Bones of the game.
[Gabrialler_Pose.png](https://xentaxbackup.github.io/file/14773_Gabrialler_Pose.png)
## Post #728
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2018-09-16T06:07:25+00:00
- Post Title: Re: ARchive_neXt

Any ways to get the AC Origins textures? I'm only interested in them, no need 3D models or anything else. Thanks
## Post #729
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-09-18T05:42:54+00:00
- Post Title: Re: ARchive_neXt

> Reply from CMihai
>
> Any ways to get the AC Origins textures? I'm only interested in them, no need 3D models or anything else. Thanks

Which models of or characters  texture maps do you want?
## Post #730
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2018-09-18T07:55:56+00:00
- Post Title: Re: ARchive_neXt

Not from characters, but from environment.
## Post #731
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-09-18T14:20:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from CMihai
>
> Not from characters, but from environment.
If it was a character, you would export from other games.(ffvx fc5 ...)
 It must be difficult. sorry
## Post #732
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-09-18T18:54:05+00:00
- Post Title: Re: ARchive_neXt

> Reply from MaZTeR
>
> Would it be possible if the mipmap textures would be extractable for GR: Wildlands? I would be very greatful for that.

I understand there's not much of a difference.

Normal  FCP_Head_Cau_NinaP_DiffuseMap (43.846 bayt)
 


FCP_Head_Cau_NinaP_DiffuseMap_Mip0 (524.318 bayt) 



FCP_Head_Cau_NinaP_DiffuseMap_Mip1 (131.102 bayt)  The size of the image is 512x512


Of course this picture is not yet complete. I only tested one.
I don't know, maybe I did wrong.

I think I'm done.
## Post #733
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2018-09-23T18:42:56+00:00
- Post Title: Re: ARchive_neXt

I finally got this to work and was so stoked until...

Is it accurate to say that we still don't have access to the weapon meshes of Assassin's Creed Unity?

If no, can someone point me in the right direction?
I feel like I have looked in the entire directory twice at this point.
## Post #734
- Username: TheBloodMaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 04, 2016 8:42 am
- Post datetime: 2018-10-25T18:27:11+00:00
- Post Title: Re: ARchive_neXt

So has any progress been made in cracking For Honor? From what I hear GPA and ninjarip are no good against it, and I tried archivenext with little success.
## Post #735
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-10-26T22:15:31+00:00
- Post Title: Re: ARchive_neXt

Assassin'S Creed Odyssey - Mercenary Breastplate
An icon that only belongs to the game.
[Mercenary Breastplate.png](https://xentaxbackup.github.io/file/15095_Mercenary Breastplate.png)
## Post #736
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-10-27T01:26:12+00:00
- Post Title: Re: ARchive_neXt

> Reply from Graesholt
>
> I finally got this to work and was so stoked until...

Is it accurate to say that we still don't have access to the weapon meshes of Assassin's Creed Unity?

If no, can someone point me in the right direction?
I feel like I have looked in the entire directory twice at this point.

Are the things you're looking for, silanes and swords? So you're asking where they are.   
I think there are many people who know where they are.  I mean, I don't know if you still know where they are. 

Tissues and Mesh'er are located in different locations. Of course you can find these in different locations.
     The textures are in the DataPC.forge file.
     Meshs are in DataPC_patch_01.forge > Game_Bootstrap_Settings.

This is from me... Elise Pistol
## Post #737
- Username: Lakress
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 22, 2018 10:54 pm
- Post datetime: 2018-10-30T12:48:16+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> Assassin'S Creed Odyssey - Mercenary Breastplate
An icon that only belongs to the game.

you were able to access AC:Odyssey game files?
## Post #738
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-10-30T23:32:31+00:00
- Post Title: Re: ARchive_neXt

> Reply from Lakress
>
> you were able to access AC:Odyssey game files?
Someone was supposed to do that.
## Post #739
- Username: Lakress
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 22, 2018 10:54 pm
- Post datetime: 2018-10-31T11:57:30+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> Someone was supposed to do that.

and may i ask how you did this? I am stuck with .dat files but I have no idea how to open them. 

For information: i used the AC raw script for Quickbms. Or is there a other way? 
I would really appreciate it, if you could share some insight information. I am keen on getting hold of the games 3D models and textures. For research purposes only of course
## Post #740
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-10-31T16:09:03+00:00
- Post Title: Re: ARchive_neXt

> Reply from Lakress
>
> and may i ask how you did this?
I'm sorry it's not me.
## Post #741
- Username: Lakress
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 22, 2018 10:54 pm
- Post datetime: 2018-11-01T17:00:40+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> I'm sorry it's not me.

oh, but could you tell me who it is? So i can get in touch with him/her? Would be great.
## Post #742
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-11-01T23:43:09+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> MaZTeR wrote:Would it be possible if the mipmap textures would be extractable for GR: Wildlands? I would be very greatful for that.

I understand there's not much of a difference.

Normal  FCP_Head_Cau_NinaP_DiffuseMap (43.846 bayt)
 


FCP_Head_Cau_NinaP_DiffuseMap_Mip0 (524.318 bayt) 



FCP_Head_Cau_NinaP_DiffuseMap_Mip1 (131.102 bayt)  The size of the image is 512x512


Of course this picture is not yet complete. I only tested one.
I don't know, maybe I did wrong.

I think I'm done.
Sorry for the long wait but I figured out that the mip maps are just lower resolution versions of the mipmap 0 variant.

Anyways, is there a way you could make scenery objects extractable? I'd very much like to get the insides of the Sueño masoleum. Plus having the mesh's UV maps not screwing up would be nice, as is the case with id-daemons Wildlands tool.

By the way, how did you get export Antonio's wife's skeleton with her mesh's skin information intact?
## Post #743
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-02T01:47:49+00:00
- Post Title: Re: ARchive_neXt

> Reply from MaZTeR
>
> By the way, how did you get export Antonio's wife's skeleton with her mesh's skin information intact?

I don't know what you're talking about. I have not encountered any problems.
What kind of error are you getting?
## Post #744
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-02T01:51:10+00:00
- Post Title: Re: ARchive_neXt

> Reply from Lakress
>
> oh, but could you tell me who it is? So i can get in touch with him/her? Would be great.

My sixth sense says he can find it.
## Post #745
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-11-02T10:36:20+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> MaZTeR wrote:By the way, how did you get export Antonio's wife's skeleton with her mesh's skin information intact?

I don't know what you're talking about. I have not encountered any problems.
What kind of error are you getting?
Error? I've not received any errors, just that the models exported do not have skins, nor do they have any skeletons.
## Post #746
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-02T20:32:59+00:00
- Post Title: Re: ARchive_neXt

> Reply from MaZTeR
>
> Error? I've not received any errors, just that the models exported do not have skins, nor do they have any skeletons.
I doubt we're talking about the same person.We're talking about Gabriela, right?
We must discuss this subject under the place where it belongs. Did you mention that?
## Post #747
- Username: shabaco
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 10, 2018 6:32 am
- Post datetime: 2018-11-05T10:17:15+00:00
- Post Title: Re: ARchive_neXt

will we be able to edit / replace files in the forge archives at some point?
## Post #748
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-05T10:32:28+00:00
- Post Title: Re: ARchive_neXt

> Reply from shabaco
>
> will we be able to edit / replace files in the forge archives at some point?

> Reply from MichaelDarkAngel
>
> ...
ARchive_neXt does not allow you to alter any of the .forge files.
...

-- MDA

Not with ARchive_neXt
## Post #749
- Username: shabaco
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 10, 2018 6:32 am
- Post datetime: 2018-11-05T11:11:03+00:00
- Post Title: Re: ARchive_neXt

damn....i take it there's no tools available to do that atm?
## Post #750
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-05T12:20:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from shabaco
>
> damn....i take it there's no tools available to do that atm?

I don't know a tool called atm.
## Post #751
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2018-11-12T11:44:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> Graesholt wrote:I finally got this to work and was so stoked until...

Is it accurate to say that we still don't have access to the weapon meshes of Assassin's Creed Unity?

If no, can someone point me in the right direction?
I feel like I have looked in the entire directory twice at this point.Are the things you're looking for, silanes and swords? So you're asking where they are.   
I think there are many people who know where they are.  I mean, I don't know if you still know where they are. 

Tissues and Mesh'er are located in different locations. Of course you can find these in different locations.
     The textures are in the DataPC.forge file.
     Meshs are in DataPC_patch_01.forge > Game_Bootstrap_Settings.The reason I asked the way I did was that while I could not myself find any weapon meshes in the files accessible with the archive, neither could I find documentation of people finding the weapons. On the contrary, I found a lot of people saying that they were having trouble locating these specific meshes, as well as people who could export characters and other gear, but not weapons, which let me to draw the conclution that the weapon meshes were somehow inaccessible.

I don't know what a 'silane' (I googled and got nothing).

You are correct that the files still illude me, and therefore I thank you for the suggesions as to where they can be found.
I cannot wait to look in these directories as soon as I am off work.

If I still find nothing, I will return.
Thank you.
## Post #752
- Username: Kamehudamuda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 15, 2018 4:26 am
- Post datetime: 2018-11-13T17:52:17+00:00
- Post Title: Re: ARchive_neXt

yes i know first post and request... :')

But im having the same problem many people here described with viewing and exporting meshes.
As far as i can see no one has found a solution for this yet or it hasnt be posted. If there is it obviously would be super cool if that gets posted here : D

If there isnt i would be super duper thankfull    if someone could export Elises Head Mesh for me. If i understand correctly its in DataPC_ACU_Paris.forge > Elise_Head > Mesh
## Post #753
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-13T23:20:09+00:00
- Post Title: Re: ARchive_neXt

Well, I guess that's it. Probably the last for me.
ARchive_neXt no longer works in my PC. I'm getting this error when starting the program. I don't understand why.

Anyway.
Although MDA has left this project, I owe him a lot. Thank you very much MDA. I'm sure he doesn't even have writings here anymore. 
It doesn't matter anymore.

                                                                                           Cheers
## Post #754
- Username: Nova Prima
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 07, 2018 3:38 pm
- Post datetime: 2018-11-14T06:24:15+00:00
- Post Title: Re: ARchive_neXt

I have no experience doing this sort of thing, but I'm trying to extract textures from the Ezio Collection on PS4. I have the forge files and can open them, but I can't seem to find textures, only diffuse/specular/normal maps. Or maybe I have found them, but they don't show anything in the ARchive_neXt window and can only be extracted as raw data, but the files it creates are only 80 bytes.
## Post #755
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2018-11-14T06:47:53+00:00
- Post Title: Re: ARchive_neXt

> Reply from Kamehudamuda
>
> yes i know first post and request... :')

But im having the same problem many people here described with viewing and exporting meshes.
As far as i can see no one has found a solution for this yet or it hasnt be posted. If there is it obviously would be super cool if that gets posted here : D

If there isnt i would be super duper thankfull    if someone could export Elises Head Mesh for me. If i understand correctly its in DataPC_ACU_Paris.forge > Elise_Head > MeshI can see if this is one of the meshes I am for arbitrary reasons able to extract when I get home.
Do you want textures on this head?
If I extract it without textures (which is by far easiest for me) you should be made aware that the UV maps are going to be jacked up. However if you simply want the geometry...
If you do want it textured, I'm going to require you to list the location of these (unless they are right there with the model, which is sometimes the case, but I have no way of knowing untill I have the program in front of me).

I'll take a look later, but word if you want textures or not would be appreciated.

> Reply from TSelman61X
>
> Well, I guess that's it. Probably the last for me.
ARchive_neXt no longer works in my PC. I'm getting this error when starting the program. I don't understand why.

Anyway.
Although MDA has left this project, I owe him a lot. Thank you very much MDA. I'm sure he doesn't even have writings here anymore. 
It doesn't matter anymore.

                                                                                           CheersThat sucks, dude.

I was just about to ask you if the program ran without complications for you, or if it still crashed on certain models?
I found the weapons where you indicated they would be, and was able to extract most of what I wanted. However, some models crashes my program every time I try to interact with them in any way, specifically/strangely only the models that include '1handed' or '2handed' in the name (that is the only pattern I have been able to discover anyway).
Does this behaviour sound familiar to you?
## Post #756
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-15T09:21:06+00:00
- Post Title: Re: ARchive_neXt

> Reply from Nova Prima
>
> I have no experience doing this sort of thing, but I'm trying to extract textures from the Ezio Collection on PS4. I have the forge files and can open them, but I can't seem to find textures, only diffuse/specular/normal maps. Or maybe I have found them, but they don't show anything in the ARchive_neXt window and can only be extracted as raw data, but the files it creates are only 80 bytes.
I didn't check the meshes. I'm already having some problems these days. 
I did a little test on CU_Ezio_Clothes_DiffuseMap.(From Assassin's Creed: Ezio Collection) Some files are hierarchical location different. Or it's been a long time, I may remember it wrong.

I think it should be in the data.forge file. Already a pattern texture from AC 2. 

The file is of the Jpg type.So I've compressed it to upload the file.
[CU_Ezio_Clothes_DiffuseMap.jpg](https://xentaxbackup.github.io/file/15179_CU_Ezio_Clothes_DiffuseMap.jpg)
## Post #757
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2018-11-15T10:51:32+00:00
- Post Title: Re: ARchive_neXt

Alright, Update:
It appears that I am able to extract every model that does not start with a number, but any model that starts with a number will crash my program. What's up with that?

Anyway, I have been able to extract everything I want by setting up a virtual machine running windows 7, installing the requirements (DirectX and .Net Framework), moving over the gamefiles I want to look inside, and then running ARchive_NeXt on there. I can't preview the models on there, mind you, but boy can I export them. Don't know if I'm the first on to do this, but I suggest anyone having trouble give this a shot.

I am having a spot of trouble locating something else now;
I have been able to locate the meshes of AC:Unity player gear in DataPC_ACU_Paris.forge (The entries for any specific piece of gear start with CN_P_FR_), and the textures for most of this in DataPC_SharedGroup_00.forge (Again, the entries for any specific piece of gear start with CN_P_FR_).
Most gear exports nice with textures and everything, however, the Hidden Blades (or ThrowBlade) as they are called in the gamefiles, do not get their textures applied in the program, and do not export with their textures (which would not be the biggest of deals, if that did not mean that their UV maps get screwed up).
I assume (correct me if I'm wrong) that this is most likely due to them all sharing some texture between them, possibly for the contraption and blade, which is the same on them all, but I cannot for the life of me locate this last texture I'm missing.
It's looks like people around the internet have been able to pull the blades out fine, so I might be missing something obvious, but if anyone knows anything about getting the hidden blades out correctly, that would be much appreciated.
Thanks guys!
## Post #758
- Username: Kamehudamuda
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 15, 2018 4:26 am
- Post datetime: 2018-11-15T11:16:21+00:00
- Post Title: Re: ARchive_neXt

> Reply from Graesholt
>
>  I can see if this is one of the meshes I am for arbitrary reasons able to extract when I get home.
Do you want textures on this head?
If I extract it without textures (which is by far easiest for me) you should be made aware that the UV maps are going to be jacked up. However if you simply want the geometry...
If you do want it textured, I'm going to require you to list the location of these (unless they are right there with the model, which is sometimes the case, but I have no way of knowing untill I have the program in front of me).

I'll take a look later, but word if you want textures or not would be appreciated.

Thanks for the offer! TSelman61X already was so kind and sent me the elise model.
As for textures yeah i'll need them too. Conveniently they are not in the same location (only the ones from when she's dead). I'll have to go looking for them. I can export textures tho anyway, so when i find them i able to get them myself.

Edit: Found them too. Nothing shall stand in my way now
## Post #759
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-11-15T16:33:27+00:00
- Post Title: Re: ARchive_neXt

Hi, how can I get files with the coordinates of objects ?
## Post #760
- Username: Nova Prima
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 07, 2018 3:38 pm
- Post datetime: 2018-11-16T10:00:21+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> 
I did a little test on CU_Ezio_Clothes_DiffuseMap.(From Assassin's Creed: Ezio Collection) Some files are hierarchical location different. Or it's been a long time, I may remember it wrong.

I think it should be in the data.forge file. Already a pattern texture from AC 2.

Thanks, I located that one in the forge file but when I view or export it, the result is just corruption/garbage. Any idea why?
[CU_Ezio_Clothes_DiffuseMap.jpg](https://xentaxbackup.github.io/file/15184_CU_Ezio_Clothes_DiffuseMap.jpg)
## Post #761
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-16T16:48:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from Nova Prima
>
> Thanks, I located that one in the forge file but when I view or export it, the result is just corruption/garbage. Any idea why?

Actually it works better than I thought. But the problem is that this PS4 version.
I'm exporting textures to different methods. I'm converting the raw files into DDS myself.

Have you tried ARchive_neXt on PS3 or PS4 for previous games? So I mean, was it working when you tested for AC1, AC2, AC Brotherhood and AC Revelations?

I can export for you if you have a group of tissue you want. 
Just tell me your location. maybe I can export in an empty time.
## Post #762
- Username: Nova Prima
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 07, 2018 3:38 pm
- Post datetime: 2018-11-17T03:10:51+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> Actually it works better than I thought. But the problem is that this PS4 version.
I'm exporting textures to different methods. I'm converting the raw files into DDS myself.

Have you tried ARchive_neXt on PS3 or PS4 for previous games? So I mean, was it working when you tested for AC1, AC2, AC Brotherhood and AC Revelations?

I can export for you if you have a group of tissue you want. 
Just tell me your location. maybe I can export in an empty time.

No, I haven't tried any other PS3 or PS4 versions. I just wanted to extract the upgraded textures from the Ezio Collection for use with the PC version. Can you teach me your methods?
## Post #763
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-17T12:24:26+00:00
- Post Title: Re: ARchive_neXt

> Reply from Nova Prima
>
> No, I haven't tried any other PS3 or PS4 versions. I just wanted to extract the upgraded textures from the Ezio Collection for use with the PC version. Can you teach me your methods?
I am exporting with a different Tools. But I'm already converting raw files like ARchive_neXt.  But I'm converting Raw Texture maps myself. I'm examining them one by one, then it takes some time to export.
You can examine raw files with any Hex program. then you should read the possible dimensions of the file. In fact it is usually easy to convert the textures of the Anvil engine.
## Post #764
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-11-26T22:21:20+00:00
- Post Title: Re: ARchive_neXt

I tried to download the program but it is not clear how it works. I would like to recover models from assassin's creed revelations how does it work? then if I take models of pèersonaggi as for example ezio there is the original skeleton? Is it possible to recover the maps?
## Post #765
- Username: wushuwarrior
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 27, 2018 9:24 am
- Post datetime: 2018-11-27T01:27:55+00:00
- Post Title: Re: ARchive_neXt

Probably programm doesn't work with net framework higher than 4.5. I have a 4.7. Try to downgrade. Hmm... Now work fine but didn't show models.
Any chance to make mod to replace captain aquila outfit with naval outfit? Want to replay game but with new cloth.
[ppp.JPG](https://xentaxbackup.github.io/file/15244_ppp.JPG)
## Post #766
- Username: wushuwarrior
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 27, 2018 9:24 am
- Post datetime: 2018-11-27T02:13:32+00:00
- Post Title: Re: ARchive_neXt

See, but cant edit, what a crew world   Is possible to make rename a model in DataPC_DX11.forge? CHR_P_Captain_of_the_Aquila_Uniform_OVERRIDE to CHR_P_Connor_Naval or e.t.c. Or HEX editor somehow?
[CHR_P_Connor_Naval_Body_1_DiffuseMap_PC.jpg](https://xentaxbackup.github.io/file/15245_CHR_P_Connor_Naval_Body_1_DiffuseMap_PC.jpg)
## Post #767
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-11-27T20:19:31+00:00
- Post Title: Re: ARchive_neXt

I have a problem with the 3d studio max script with the version of 2017. I tried to import a model but this happens:

[https://ibb.co/LCjHCc3](https://ibb.co/LCjHCc3)
## Post #768
- Username: wushuwarrior
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 27, 2018 9:24 am
- Post datetime: 2018-11-28T19:17:47+00:00
- Post Title: Re: ARchive_neXt

> Reply from dibe91
>
> I have a problem with the 3d studio max script with the version of 2017. I tried to import a model but this happens:

https://ibb.co/LCjHCc3
Hello! You have a to new version 3d studio. As i know script work from 2009-2016 version 3ds max. Try on older version.
## Post #769
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-11-29T12:11:07+00:00
- Post Title: Re: ARchive_neXt

is it not possible to update it?

edit: I tried with the 2009 version but it gives you the same error
## Post #770
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2018-12-04T17:45:06+00:00
- Post Title: Re: ARchive_neXt

There's no support anymore for this? Origins/Odyssey...
## Post #771
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-12-04T20:14:21+00:00
- Post Title: Re: ARchive_neXt

> Reply from CMihai
>
> There's no support anymore for this? Origins/Odyssey...

ARchive_neXt no longer supports new games.  I know it's bad news, but there's nothing to do.
## Post #772
- Username: Earthern
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 28, 2018 5:33 am
- Post datetime: 2018-12-27T21:35:19+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> CMihai wrote:There's no support anymore for this? Origins/Odyssey...

ARchive_neXt no longer supports new games.  I know it's bad news, but there's nothing to do.

Hey, does this mean there will be no more updates? No full For Honor support ever? 

Thanks
## Post #773
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-12-27T23:36:10+00:00
- Post Title: Re: ARchive_neXt

> Reply from Earthern
>
> 
Hey, does this mean there will be no more updates? No full For Honor support ever? 

Thanks

Even if ArchiveNext were updated for new UbiSoft games, there's almost no hope for "For Honor", since from certain period of time they started to encrypt everything. I have a maxscipt for this game, but for older - not recent clients. It's very sad actually, I like those armors a lot!
## Post #774
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-12-28T18:49:36+00:00
- Post Title: Re: ARchive_neXt

> Reply from zaramot
>
> Earthern wrote:
Hey, does this mean there will be no more updates? No full For Honor support ever? 
Thanks
Even if ArchiveNext were updated for new UbiSoft games, there's almost no hope for "For Honor", since from certain period of time they started to encrypt everything. I have a maxscipt for this game, but for older - not recent clients. It's very sad actually, I like those armors a lot!

Was the encryption from the beginning?  I mean, did they encrypt any games before the "For Honor" video game?
(Recently, the games developed with the Unreal engine have started to be encrypted. I think this is the future.Bad...)
## Post #775
- Username: Earthern
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 28, 2018 5:33 am
- Post datetime: 2018-12-29T20:23:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from zaramot
>
> Even if ArchiveNext were updated for new UbiSoft games, there's almost no hope for "For Honor", since from certain period of time they started to encrypt everything. I have a maxscipt for this game, but for older - not recent clients. It's very sad actually, I like those armors a lot!

> Reply from TSelman61X
>
> Was the encryption from the beginning?  I mean, did they encrypt any games before the "For Honor" video game?
(Recently, the games developed with the Unreal engine have started to be encrypted. I think this is the future.Bad...)

Yeah sounds like thats gonna be the norm for all their future games, I mean unless they've literally done it just for this game, but I don't know why they did it specifically for For Honor only if that was the case. =/

But yeah, shame, the armors are really nice, would've been great on some 3d models on stuff ;(
## Post #776
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-12-30T01:15:04+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> (Recently, the games developed with the Unreal engine have started to be encrypted. I think this is the future.Bad...)
No idea what you're smoking.. see these titles I've enabled console in; 0 encryption. I really can't say anything about ONLINE games you're perhaps dealing with. Us, in the single-player realm, aren't affected.

[http://fearlessrevolution.com/viewtopic.php?f=4&t=8410](http://fearlessrevolution.com/viewtopic.php?f=4&t=8410)
[http://fearlessrevolution.com/viewtopic.php?f=4&t=8318](http://fearlessrevolution.com/viewtopic.php?f=4&t=8318)
[http://fearlessrevolution.com/viewtopic.php?f=4&t=8247](http://fearlessrevolution.com/viewtopic.php?f=4&t=8247)

BR,
Sun
## Post #777
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-12-30T16:23:52+00:00
- Post Title: Re: ARchive_neXt

But I didn't say that all video games were encrypted. (At least not yet.)  
In the past, some unencrypted video games are now protected with a password.  [https://zenhax.com/viewtopic.php?f=9&t=1005](https://zenhax.com/viewtopic.php?f=9&t=1005)  I can give a lot of examples to this topic. 
Even in every update these passwords are changed.
## Post #778
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2019-01-02T16:47:28+00:00
- Post Title: Re: ARchive_neXt

Two dumb questions…

Firstly:
I have gotten most everything I want from Unity, except ONE damn weapon…
The weapon in the question is the ‘Cutlass’ from the [free] Dead Kings DLC.

Textures can be found in dlc_10\DataPC_10_dlc.forge\SDN_W_1H_Cutlass[etc.] like the other weapons from the DLC, however, while the other weapons will have models with the same name as their textures in dlc_11\DataPC_ACU-DLC_Saint-Denis.forge\, the cutlass does not (the textures should be found along with the model here, but they are not there either).
I have gone through the ENTIRETY of dlc_11\DataPC_ACU-DLC_Saint-Denis.forge several times with no luck.
The Cutlass is also not found anywhere in DataPC_patch_01.forge\Game_Bootstrap_Settings\Mesh\, as is the case [for some reason] with the Guillotine Guns which are added by the DLC.

Can anyone help me out?

Secondly:
How do I export Hair Meshes?
They don’t seem to display anything in the program, and exported .OBJs do not seem to display anything either…?

EDIT: Finally it would seem that I am trusted with the ability to attach images. Celebrations.
[20190102174040.png](https://xentaxbackup.github.io/file/15409_20190102174040.png)
## Post #779
- Username: LordMustang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 09, 2019 2:43 am
- Post datetime: 2019-01-08T18:51:51+00:00
- Post Title: Re: ARchive_neXt

I'm trying to get some building models from AC:U, but whenever I click on a mesh it just crashes. I'm pretty sure exporting works fine, but I wouldn't have a clue which mesh to export if I have no way of viewing. I'm pretty sure AC:U was supported by the program, any ideas?

These are the errors I'm getting: 




Translation: the object reference isn't set to an instance of an object
## Post #780
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-01-08T22:28:36+00:00
- Post Title: Re: ARchive_neXt

> Reply from LordMustang
>
> I'm trying to get some building models from AC:U, but whenever I click on a mesh it just crashes.

Unfortunately this is a very common problem.  I have the same problem with me.  Unfortunately, I don't think it's a cure.   We're just unlucky.
The only way you can see this way is by exporting models.
## Post #781
- Username: LordMustang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 09, 2019 2:43 am
- Post datetime: 2019-01-09T12:31:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> LordMustang wrote:I'm trying to get some building models from AC:U, but whenever I click on a mesh it just crashes.

Unfortunately this is a very common problem.  I have the same problem with me.  Unfortunately, I don't think it's a cure.   We're just unlucky.
The only way you can see this way is by exporting models.
That's a shame, because I don't think Unity updated in any way. If it worked before it means that an update to Archive Next could have broken it.
## Post #782
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2019-01-10T15:12:13+00:00
- Post Title: Re: ARchive_neXt

> Reply from Graesholt
>
> 
[...]
How do I export Hair Meshes?
They don’t seem to display anything in the program, and exported .OBJs do not seem to display anything either…?
[...]Quoting myself to apologise for asking a question I had not properly researched if an answer existed for.
I understand now how to export the .ARX files of the hair meshes, and open these in 3ds max.
However, how I get usefull geometry (akin to what we see [here](https://sketchfab.com/models/fda35c615ea34fca847f89721d6fc6d8), or on the picture postet by RunaWhite on page 18) out of these files still illudes me.
If anyone is able to help me out, I would be very grateful.

Also, still looking through the files again and again for that one damn Cutlass model .
Please see my previous post for more information, and reply if you have any idea where to find it...

Thanks guys
## Post #783
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2019-01-11T12:11:07+00:00
- Post Title: Re: ARchive_neXt

> Reply from Graesholt
>
> Graesholt wrote:
[...]
How do I export Hair Meshes?
They don’t seem to display anything in the program, and exported .OBJs do not seem to display anything either…?
[...]
Quoting myself to apologise for asking a question I had not properly researched if an answer existed for.
I understand now how to export the .ARX files of the hair meshes, and open these in 3ds max.
However, how I get usefull geometry (akin to what we see here, or on the picture postet by RunaWhite on page 18) out of these files still illudes me.
If anyone is able to help me out, I would be very grateful.

Also, still looking through the files again and again for that one damn Cutlass model .
Please see my previous post for more information, and reply if you have any idea where to find it...

Thanks guys

I extruded those outlines in Blender, entering Edit Mode with all vertices selected, pressed E and resized a bit to add some volume, then switched back to Object Mode. I did that process with every hair mesh extracted from the files (Lod0,1,2).

I also had to duplicate parts (at least for Arno and Elise from Unity) because that way the hair appeared way too empty and not even close to the original one. I had to do the same with Syndicate even if the meshes are better sorted there.
## Post #784
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2019-01-11T20:34:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> Graesholt wrote:Graesholt wrote:
[...]
How do I export Hair Meshes?
They don’t seem to display anything in the program, and exported .OBJs do not seem to display anything either…?
[...]
Quoting myself to apologise for asking a question I had not properly researched if an answer existed for.
I understand now how to export the .ARX files of the hair meshes, and open these in 3ds max.
However, how I get usefull geometry (akin to what we see here, or on the picture postet by RunaWhite on page 18) out of these files still illudes me.
If anyone is able to help me out, I would be very grateful.

Also, still looking through the files again and again for that one damn Cutlass model .
Please see my previous post for more information, and reply if you have any idea where to find it...

Thanks guys 

I extruded those outlines in Blender, entering Edit Mode with all vertices selected, pressed E and resized a bit to add some volume, then switched back to Objec Mode. I did that process with every hair mesh extracted from the files (Lod0,1,2).

I also had to duplicate parts (at least for Arno and Elise from Unity) because that way the hair appeared way too empty and not even close to the original one. I had to do the same with Syndicate even if the meshes are better sorted there.Didn't expect a reply from RunaWhite himself, but thank you very much for taking the time 
I'll see what I can get to work, seeing as I have mostly bad experiences with blender ;P
## Post #785
- Username: Larxian
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 09, 2018 1:47 am
- Post datetime: 2019-01-15T23:44:38+00:00
- Post Title: Re: ARchive_neXt

Hello, are older version of "ForgeX" still available to download somewhere? I read that it apparently had support for Shaun White Skateboarding, and that's the game files i'm interested in, while ARchive_neXt doesn't support this game. I tried reading the files anyway with another game profile, Prince of persia 2008 is the one that allows me to see the most of the folders tree, but I can't read or preview any textures / models.

Thank you!
## Post #786
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2019-01-23T11:32:18+00:00
- Post Title: Re: ARchive_neXt

> Reply from Larxian
>
> Hello, are older version of "ForgeX" still available to download somewhere? I read that it apparently had support for Shaun White Skateboarding, and that's the game files i'm interested in, while ARchive_neXt doesn't support this game. I tried reading the files anyway with another game profile, Prince of persia 2008 is the one that allows me to see the most of the folders tree, but I can't read or preview any textures / models.

Thank you!

Weird, usually the new versions should carry over the previous support. I wonder if it actually worked before?

I'm afraid the older versions of the program have all been replaced by the new update each time.
## Post #787
- Username: Larxian
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 09, 2018 1:47 am
- Post datetime: 2019-01-23T15:24:08+00:00
- Post Title: Re: ARchive_neXt

> Reply from RunaWhite
>
> 
Weird, usually the new versions should carry over the previous support. I wonder if it actually worked before?

I'm afraid the older versions of the program have all been replaced by the new update each time.

This is the post that mentionned support for Shaun White Skateboarding:
[viewtopic.php?f=10&t=6617&p=70532&hilit ... OaY#p70532](http://forum.xentax.com/viewtopic.php?f=10&t=6617&p=70532&hilit=shaun%20white%20skateboarding&fbclid=IwAR2svJcyOIKO0QTY9u8d5uC5dl_pMRhLrqB92OKR8sCBENR4Q0HEoByBOaY#p70532)

I also actually talked to someone from the "The Brotherhood of the Realm" page on facebook, who told me that the support was drop because the author didn't own shaun white and couldn't test it anymore apparently. The older version from what I've been told aren't available anymore and never got support past windows XP. 
I wonder if it just wouldn't work at all on W10 or if it could kinda work, would still be curious to try it if anyone still have this older version.
## Post #788
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-01-23T19:55:36+00:00
- Post Title: Re: ARchive_neXt

> Reply from Larxian
>
> ... are older version of "ForgeX" still available to download somewhere? ...

 ForgeX.exe                08-Jan-2014 00:49  1.6M    [http://www.tbotr.net/Downloads/ForgeX.exe](http://www.tbotr.net/Downloads/ForgeX.exe)
 ForgeXBeta.exe          08-Jan-2014 00:49  390K   [http://www.tbotr.net/Downloads/ForgeXBeta.exe](http://www.tbotr.net/Downloads/ForgeXBeta.exe) 

I wrote the date of publication.  I don't know what their version is. What he's looking for may not be
## Post #789
- Username: Larxian
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 09, 2018 1:47 am
- Post datetime: 2019-01-23T21:45:44+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X
>
> Larxian wrote:... are older version of "ForgeX" still available to download somewhere? ...

 ForgeX.exe                08-Jan-2014 00:49  1.6M    http://www.tbotr.net/Downloads/ForgeX.exe
 ForgeXBeta.exe          08-Jan-2014 00:49  390K   http://www.tbotr.net/Downloads/ForgeXBeta.exe 

I wrote the date of publication.  I don't know what their version is. What he's looking for may not be

Thank you!
However it does seem like it doesn't work properly indeed, at least on Windows 10. I get a "Microsoft.NET Framework" warning when I open it, I can still open it but there aren't any menus or options visible.
## Post #790
- Username: zerozone
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 16, 2015 3:17 pm
- Post datetime: 2019-01-24T10:08:59+00:00
- Post Title: Re: ARchive_neXt

Hello guys!!!

Anyone have any idea on how to convert the AC Origins textures?
I already have them unpacked, but I'm not able to read or convert the files, I know some people manage to do it already but no idea how   

Thank you guys!!!!
## Post #791
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-01-25T00:13:56+00:00
- Post Title: Re: ARchive_neXt

> Reply from Larxian
>
> ... I get a "Microsoft.NET Framework" warning when I open it, I can still open it but there aren't any menus or options visible...

There is a problem with the registry. So the program registry is unreachable.  If the program is run as an administrator, the problem does not occur. 
But unfortunately there is still nothing.   The interface is still empty. ( Maybe we know how to operate it.  It's ridiculous  )

Maybe you can try changing the compatibility mode.  I tried it but I can't say it was hardly effective. Still same.
## Post #792
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-25T06:10:32+00:00
- Post Title: Re: ARchive_neXt

> Reply from zerozone
>
> Anyone have any idea on how to convert the AC Origins textures?
create a new thread in "Graphic file formats" section and upload some samples.
## Post #793
- Username: tala
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 31, 2019 7:16 pm
- Post datetime: 2019-01-31T11:19:30+00:00
- Post Title: Re: ARchive_neXt

Hi all, is this app still working? Because everytime i try to view a mesh i'm getting 'Error Viewing Mesh' error. I got directx runtime and 4.5 NET Framework installed. I know i can still export the meshes but it doesn't help. I need to see what i'm exporting. Any help with that?
Thanks
## Post #794
- Username: ChenA
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 15, 2016 1:00 am
- Post datetime: 2019-01-31T16:23:52+00:00
- Post Title: Re: ARchive_neXt

@MichaelDarkAngel Could you please share the Ghost Recon Wildlands file format？Thanks.
## Post #795
- Username: Innuendo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 02, 2019 6:01 am
- Post datetime: 2019-03-01T22:05:19+00:00
- Post Title: Re: ARchive_neXt

I was wondering if there was a build for this that can decompile Rainbow Six Siege 1.0 files
## Post #796
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2019-04-16T06:30:55+00:00
- Post Title: Re: ARchive_neXt

Okay, so back again in those damn AC:Unity files, because apparently one of the guns' textures is not located by all the other gun textures. Figures.

So, dumb question...
The meshes clearly know where to look for their materials, and the materials in turn clearly know where to look for their textures (which they can then only load of they have been loaded in advance).
Is there any way for a person who knows where the mesh and material files are located to somehow get the location where they expect to find the textures?

Thanks guys
## Post #797
- Username: ristek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 20, 2019 4:26 pm
- Post datetime: 2019-04-20T08:37:57+00:00
- Post Title: Re: ARchive_neXt

Hi, i am extract mesh from assassin's creed IV to OBJ files. But my model extract from Assassin's creed IV so BIG. how can i small size my mesh model (OBJ)? sorry my english is bad
## Post #798
- Username: ristek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 20, 2019 4:26 pm
- Post datetime: 2019-04-28T15:23:37+00:00
- Post Title: Re: ARchive_neXt

why does the size of the model I imported from Archive_neXt have a large size?
## Post #799
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-04-28T18:16:00+00:00
- Post Title: Re: ARchive_neXt

> Reply from ristek ↑Sat Apr 20, 2019 4:37 pm at Sat Apr 20, 2019 4:37 pm
>
> 
Hi, i am extract mesh from assassin's creed IV to OBJ files. But my model extract from Assassin's creed IV so BIG. how can i small size my mesh model (OBJ)? sorry my english is bad

I didn't see any options when exporting.  I mean, I guess there's no such choice.  you must manually resize yourself.
## Post #800
- Username: ristek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 20, 2019 4:26 pm
- Post datetime: 2019-04-29T05:22:10+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X ↑Mon Apr 29, 2019 2:16 am at Mon Apr 29, 2019 2:16 am
>
> 
ristek wrote: ↑Sat Apr 20, 2019 4:37 pm
Hi, i am extract mesh from assassin's creed IV to OBJ files. But my model extract from Assassin's creed IV so BIG. how can i small size my mesh model (OBJ)? sorry my english is bad


I didn't see any options when exporting.  I mean, I guess there's no such choice.  you must manually resize yourself.

but why are the models in the game the same size as all?
## Post #801
- Username: jesus1259
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 01, 2019 12:41 pm
- Post datetime: 2019-05-01T04:44:06+00:00
- Post Title: Re: ARchive_neXt

Hey I've manage to use  the tool to extract Thomas De Carillon but I cannot find the textures for the model can anyone help me locate the textures ? I will be most thankful.
## Post #802
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-05-01T05:11:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from jesus1259 ↑Wed May 01, 2019 12:44 pm at Wed May 01, 2019 12:44 pm
>
> 
Hey I've manage to use  the tool to extract Thomas De Carillon but I cannot find the textures for the model can anyone help me locate the textures ? I will be most thankful.

You need to edit the texture maps yourself. There's a reference texture maps for this. (Diffsuse map, Mask map, Normal maps)

These are my old work.
[https://www.deviantart.com/tselman61/ar ... -766648382](https://www.deviantart.com/tselman61/art/Assassin-s-Creed-Unity-Thomas-de-Carneillon-766648382)
[https://www.deviantart.com/tselman61/ar ... -768258625](https://www.deviantart.com/tselman61/art/AC-Unity-Arno-Thomas-Master-Assassin-outfit-768258625)
## Post #803
- Username: jesus1259
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 01, 2019 12:41 pm
- Post datetime: 2019-05-01T05:19:57+00:00
- Post Title: Re: ARchive_neXt

I find the tool sort of confusing because I dont know how to find some of the stuff like for Thomas I found him in the Paris.forge but cannot find the texture maps and edit them how? your rendered model looks really good btw.
## Post #804
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-05-01T18:07:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from jesus1259 ↑Wed May 01, 2019 1:19 pm at Wed May 01, 2019 1:19 pm
>
> 
I find the tool sort of confusing because I dont know how to find some of the stuff like for Thomas I found him in the Paris.forge but cannot find the texture maps and edit them how? your rendered model looks really good btw.

I can give you these texture maps if you want. (In an edited format)
## Post #805
- Username: jesus1259
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 01, 2019 12:41 pm
- Post datetime: 2019-05-01T19:15:41+00:00
- Post Title: Re: ARchive_neXt

I would love that, also in the future if your not busy may you show me how to edit them and I will help provide some models for unity if you'd like.
## Post #806
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-05-02T19:14:05+00:00
- Post Title: Re: ARchive_neXt

> Reply from jesus1259 ↑Thu May 02, 2019 3:15 am at Thu May 02, 2019 3:15 am
>
> 
I would love that, also in the future if your not busy may you show me how to edit them and I will help provide some models for unity if you'd like.

I made them with the blender.  Shader Editor  can now use better. But you can do the same with PS if you want.

The problem is that it's not easy to show you this. I can give you ready-made texture maps.  ( Otherwise, you should learn to do this yourself. But I can only help you with that. )

[https://sta.sh/06vzcumsidk](https://sta.sh/06vzcumsidk)
## Post #807
- Username: jesus1259
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 01, 2019 12:41 pm
- Post datetime: 2019-05-02T21:40:50+00:00
- Post Title: Re: ARchive_neXt

Ohh alright that makes sense sure i would like to have the edited textures better thank you for the help
## Post #808
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-05-03T20:41:43+00:00
- Post Title: Re: ARchive_neXt

> Reply from jesus1259 ↑Fri May 03, 2019 5:40 am at Fri May 03, 2019 5:40 am
>
> 
Ohh alright that makes sense sure i would like to have the edited textures better thank you for the help

I'll give you different texture maps. I have texture maps I've arranged. (These texture are the texture maps I have previously created.)
Thomas De Carillon --> [https://drive.google.com/open?id=1T4mks ... 9HAYjxwKdY](https://drive.google.com/open?id=1T4mksgS5epiWNOinQYnz029HAYjxwKdY) I've updated it again.

But if you need any help, I can help you. (For PS)
## Post #809
- Username: jesus1259
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 01, 2019 12:41 pm
- Post datetime: 2019-05-03T20:55:08+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X ↑Sat May 04, 2019 4:41 am at Sat May 04, 2019 4:41 am
>
> 
jesus1259 wrote: ↑Fri May 03, 2019 5:40 am
Ohh alright that makes sense sure i would like to have the edited textures better thank you for the help  


I'll give you different texture maps. I have texture maps I've arranged. (These texture are the texture maps I have previously created.)
Thomas De Carillon --> wait

But if you need any help, I can help you. (For PS)

Alright for sure thank you and once i complete what im doing ill send you some images and even provide some of my works if you'd like
## Post #810
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-05-03T21:09:45+00:00
- Post Title: Re: ARchive_neXt

> Reply from jesus1259 ↑Sat May 04, 2019 4:55 am at Sat May 04, 2019 4:55 am
>
> 
Alright for sure thank you and once i complete what im doing ill send you some images and even provide some of my works if you'd like

Check the link above again. 
I had to update the files. (I noticed some of them were old games.  updated with the latest game.)
## Post #811
- Username: jesus1259
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 01, 2019 12:41 pm
- Post datetime: 2019-05-03T21:27:58+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X ↑Sat May 04, 2019 5:09 am at Sat May 04, 2019 5:09 am
>
> 
jesus1259 wrote: ↑Sat May 04, 2019 4:55 am
Alright for sure thank you and once i complete what im doing ill send you some images and even provide some of my works if you'd like


Check the link above again. 
I had to update the files. (I noticed some of them were old games.  updated with the latest game.)

Thank you so much ill apply them as soon as i can and provide some screens of it!!!
## Post #812
- Username: ullu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 07, 2019 4:51 pm
- Post datetime: 2019-05-07T08:54:33+00:00
- Post Title: Re: ARchive_neXt

Sir, I appreciate your work. Could you add support for Assasin's Creed Origin, ASAP!
## Post #813
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-05-07T15:28:37+00:00
- Post Title: Re: ARchive_neXt

> Reply from ullu ↑Tue May 07, 2019 4:54 pm at Tue May 07, 2019 4:54 pm
>
> 
Sir, I appreciate your work. Could you add support for Assasin's Creed Origin, ASAP!

Unfortunately, MDA has stopped developing this tool.   
You can find a different tool.
## Post #814
- Username: Inconnuxdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 14, 2019 9:12 pm
- Post datetime: 2019-05-15T09:48:19+00:00
- Post Title: Re: ARchive_neXt

Hello, everyone, I contact you because I worry, I use habitual Archive Next as his usual and subsequently it makes me wrong

> See the end of this message for more details on the debugging call
>
> just-in-time (JIT) instead of this dialog box.
>
> 
>
> ************ Exception text ************
>
> System.ArgumentException: The path can not be an empty string or contain only white space.
>
> à System.IO.Directory.CreateDirectory(String path)
>
> à ARchive_neXt.arxForm.arxLoadPrefs()
>
> à ARchive_neXt.arxForm.tsmiPrefs_Click(Object sender, EventArgs e)
>
> à System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
>
> à System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
>
> à System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
>
> à System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
>
> à System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
>
> à System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
>
> à System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
>
> à System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
>
> à System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
>
> à System.Windows.Forms.Control.WndProc(Message& m)
>
> à System.Windows.Forms.ScrollableControl.WndProc(Message& m)
>
> à System.Windows.Forms.ToolStrip.WndProc(Message& m)
>
> à System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
>
> à System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
>
> à System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
>
> à System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
>
> 
>
> 
>
> ************ Assemblys chargés ************
>
> mscorlib
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3324.0 built by: NET472REL1LAST_C
>
> CodeBase : file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
>
> ----------------------------------------
>
> ARchive_neXt
>
> Version de l'assembly : 4.3.27.0
>
> Version Win32 : 4.03.27.0
>
> CodeBase : file:///C:/Program%20Files%20(x86)/TBotR/ARchive_neXt/ARchive_neXt.exe
>
> ----------------------------------------
>
> System.Windows.Forms
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3324.0 built by: NET472REL1LAST_C
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
>
> ----------------------------------------
>
> System
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3353.0 built by: NET472REL1LAST_B
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
>
> ----------------------------------------
>
> System.Drawing
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3062.0 built by: NET472REL1
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
>
> ----------------------------------------
>
> Microsoft.DirectX
>
> Version de l'assembly : 1.0.2902.0
>
> Version Win32 : 5.04.00.2904
>
> CodeBase : file:///C:/WINDOWS/assembly/GAC/Microsoft.DirectX/1.0.2902.0__31bf3856ad364e35/Microsoft.DirectX.dll
>
> ----------------------------------------
>
> Microsoft.DirectX.Direct3D
>
> Version de l'assembly : 1.0.2902.0
>
> Version Win32 : 9.05.132.0000
>
> CodeBase : file:///C:/WINDOWS/assembly/GAC/Microsoft.DirectX.Direct3D/1.0.2902.0__31bf3856ad364e35/Microsoft.DirectX.Direct3D.dll
>
> ----------------------------------------
>
> Microsoft.DirectX.Direct3DX
>
> Version de l'assembly : 1.0.2911.0
>
> Version Win32 : 9.12.589.0000
>
> CodeBase : file:///C:/WINDOWS/assembly/GAC/Microsoft.DirectX.Direct3DX/1.0.2911.0__31bf3856ad364e35/Microsoft.DirectX.Direct3DX.dll
>
> ----------------------------------------
>
> System.Configuration
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3324.0 built by: NET472REL1LAST_C
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
>
> ----------------------------------------
>
> System.Core
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3324.0 built by: NET472REL1LAST_C
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
>
> ----------------------------------------
>
> System.Xml
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3062.0 built by: NET472REL1
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
>
> ----------------------------------------
>
> System.Windows.Forms.resources
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3062.0 built by: NET472REL1
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms.resources/v4.0_4.0.0.0_fr_b77a5c561934e089/System.Windows.Forms.resources.dll
>
> ----------------------------------------
>
> mscorlib.resources
>
> Version de l'assembly : 4.0.0.0
>
> Version Win32 : 4.7.3062.0 built by: NET472REL1
>
> CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/mscorlib.resources/v4.0_4.0.0.0_fr_b77a5c561934e089/mscorlib.resources.dll
>
> ----------------------------------------
>
> ************ Debug JIT ************
>
> To enable just-in-time (JIT) debugging, the configuration file for this
>
> application or this computer (machine.config) should have value
>
> jitDebugging defined in the system.windows.forms section.
>
> The application must also be compiled with debugging
>
> activated.
>
> 
>
> For example :
>
> 
>
> <Configuration>
>
> <system.windows.forms jitDebugging = "true" />
>
> </ Configuration>
>
> 
>
> When just-in-time debugging is enabled, unhandled exceptions
>
> will be sent to the JIT debugger registered on the computer
>
> rather than being handled by this dialog.
So I would like to know how to correct all this because I still do not understand the origin of the problem. Thank you in advance for your answer.
## Post #815
- Username: RusHHoster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 01, 2019 5:17 am
- Post datetime: 2019-06-30T21:33:16+00:00
- Post Title: Re: ARchive_neXt

Where can I find the model of a flintlock pistol from Assassin's Creed 3, what is displayed in the cutscene, the store and in general was demonstrated in demo at E3 2012?]
## Post #816
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-07-01T23:09:28+00:00
- Post Title: Re: ARchive_neXt

> Reply from Inconnuxdark ↑Wed May 15, 2019 5:48 pm at Wed May 15, 2019 5:48 pm
>
> 
Hello, everyone, I contact you because I worry, I use habitual Archive Next as his usual and subsequently it makes me wrong
See the end of this message for more details on the debugging call
just-in-time (JIT) instead of this dialog box.

************ Exception text ************
System.ArgumentException: The path can not be an empty string or contain only white space.
à System.IO.Directory.CreateDirectory(String path)
à ARchive_neXt.arxForm.arxLoadPrefs()
...

So I would like to know how to correct all this because I still do not understand the origin of the problem. Thank you in advance for your answer.

You did the same thing you always did, and you got this error. Am I right?
Or you're using it for the first time, and you've encountered this error.
## Post #817
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2019-07-07T18:48:42+00:00
- Post Title: Re: ARchive_neXt

Hi guys,

4.03.27.0 is the highest version ? 

Thanks.
## Post #818
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-07-07T21:16:49+00:00
- Post Title: Re: ARchive_neXt

> Reply from Damoclès ↑Mon Jul 08, 2019 2:48 am at Mon Jul 08, 2019 2:48 am
>
> 
Hi guys,

4.03.27.0 is the highest version ? 

Thanks.

 Yes, the latest release version. "v4.03.27.0"
## Post #819
- Username: derinhalil2015
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 11, 2019 4:23 am
- Post datetime: 2019-09-11T19:02:15+00:00
- Post Title: Re: ARchive_neXt

Hey guys,

So I've been trying to export the meshes for the default armor of Prince of Persia (2008). The texture files are just fine, they can be previewed and exported, however I can't do either with the 3D models. Something about FreeImage and DirectX, then the final error is about arxDrawMesh(). I don't even have to preview, really. I just want to export them. How can I do that?

Thanks in advance.
## Post #820
- Username: derinhalil2015
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 11, 2019 4:23 am
- Post datetime: 2019-09-14T11:03:37+00:00
- Post Title: Re: ARchive_neXt

Nevermind, I figured it out. You let the computer sleep, then you open it back up. It'll give an error once more, then exporting works like usual.
## Post #821
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2019-09-15T13:28:28+00:00
- Post Title: Re: ARchive_neXt

Will this get Ghost Recon: Breakpoint support?
## Post #822
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-09-16T08:29:34+00:00
- Post Title: Re: ARchive_neXt

> Reply from MaZTeR ↑Sun Sep 15, 2019 9:28 pm at Sun Sep 15, 2019 9:28 pm
>
> 
Will this get Ghost Recon: Breakpoint support?

I'm sorry, that's impossible.  It does not support.
## Post #823
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2019-09-26T19:41:42+00:00
- Post Title: Re: ARchive_neXt

Impossible? It supports Wildlands and Breakpoint's engine is pretty much a port of the former
## Post #824
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-09-26T21:04:04+00:00
- Post Title: Re: ARchive_neXt

> Reply from MaZTeR ↑Fri Sep 27, 2019 3:41 am at Fri Sep 27, 2019 3:41 am
>
> 
Impossible? It supports Wildlands and Breakpoint's engine is pretty much a port of the former

There are always differences, even if the game engines are the same. 
The compression of the game files has already changed. It could be from this.

You can say that to someone else.
## Post #825
- Username: 73lac
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 04, 2017 1:23 pm
- Post datetime: 2019-12-05T07:21:15+00:00
- Post Title: Re: ARchive_neXt

Hi does anyone know where I can locate the textures for Elise?
I currently only have the face texture and seem to be missing the mouth and eye/pupil textures for the character. 
She is from AC Unity if that helps
## Post #826
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-12-05T16:51:25+00:00
- Post Title: Re: ARchive_neXt

> Reply from 73lac ↑Thu Dec 05, 2019 3:21 pm at Thu Dec 05, 2019 3:21 pm
>
> 
Hi does anyone know where I can locate the textures for Elise?
I currently only have the face texture and seem to be missing the mouth and eye/pupil textures for the character. 
She is from AC Unity if that helps

Many other Textures are commonly used in many different models. 
(Generic, Standard, LIB)
Eye textures generic. You have to create it yourself. 

A lot of textures in the game are in this file.
DataPC_SharedGroup_00.forge
DataPC_SharedGroup_01.forge
DataPC_SharedGroup_02.forge
DataPC_SharedGroup_03.forge

Sample texture names
CN_U_Elise_Party_Body_DiffuseMap
CN_U_Elise_Head_DiffuseMap
CN_U_FR_Elise2_DiffuseMap
LIB_Eye_TeethClean_DiffuseMap_PC
LIB_Eyelashes_DiffuseMap
CE_S_LIB_EyeTech_Eyeball_DiffuseMap_TS
## Post #827
- Username: 73lac
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 04, 2017 1:23 pm
- Post datetime: 2019-12-07T14:20:56+00:00
- Post Title: Re: ARchive_neXt

TY I appreciate you taking the time to reply
## Post #828
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2019-12-07T20:01:19+00:00
- Post Title: Re: ARchive_neXt

Hy guys,

Is it possible to extract all the .forge datas in once instead of extracting them one by one ?
## Post #829
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-12-08T10:03:47+00:00
- Post Title: Re: ARchive_neXt

> Reply from Damoclès ↑Sun Dec 08, 2019 4:01 am at Sun Dec 08, 2019 4:01 am
>
> 
Hy guys,

Is it possible to extract all the .forge datas in once instead of extracting them one by one ?

Unfortunately, this is not possible as far as I know. 
there is more than one different data from within any file. 
But you can still export all the mesh or skeleton of a model as Arx or Obj.

Look at this
"CN_E_MA_PrologueAssassin_SoftBody" Let's say that there are many different sub-files. example Matrial, Texture Set, Soft Body Mesh AND Mesh. You can export all the meshes inside by right-clicking directly without expanding the "Mesh". This can speed up your work a little.
## Post #830
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-06T19:25:11+00:00
- Post Title: Re: ARchive_neXt

This is getting ridiculous, but, the tool every time I open it gives me this big message error that many have got before me.
I try either change the route of were to install it, run it as administrator, and everything on the list, but, nothing works.
Win10 with Netframework on 4.76.

EDIT:
Nevermind, found the solution my self:

It looks like the tool start with 0 configuration.
The only way for fix the annoying message of error every time one open it, it is pressing on the message "continue", and then jump to the option tab of the tool, and on the option of "temp file option" put ANY route, press save change, close and re-open.

Next time open, it should open on the option windows, then you chose what game to view (the one you want to see/explorer)
## Post #831
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-04T14:09:46+00:00
- Post Title: Re: ARchive_neXt

Dude this program's site does not work while I get "could not access network location" error. Can you give me the installation of this program? Discord: UmutUG#0604
## Post #832
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-04T14:32:23+00:00
- Post Title: Re: ARchive_neXt

> Reply from UmutUG ↑Sat Apr 04, 2020 10:09 pm at Sat Apr 04, 2020 10:09 pm
>
> 
Dude this program's site does not work while I get "could not access network location" error. Can you give me the installation of this program? Discord: UmutUG#0604
[https://www.mediafire.com/file/p5fpua5a ... t.msi/file](https://www.mediafire.com/file/p5fpua5a9fh3qtr/ARchive_neXt.msi/file)
## Post #833
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-04T17:37:56+00:00
- Post Title: Re: ARchive_neXt

Bro,

Can you send me this file directly installed? Server site is down and fails while installing. ([http://prntscr.com/rt0rml](http://prntscr.com/rt0rml))
## Post #834
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-04T17:53:46+00:00
- Post Title: Re: ARchive_neXt

Okay, I just installed it no issues
[http://www.mediafire.com/file/21tuzru6m ... R.rar/file](http://www.mediafire.com/file/21tuzru6mlz9sde/TBotR.rar/file)
## Post #835
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-04T18:41:30+00:00
- Post Title: Re: ARchive_neXt

Thanks bro!
## Post #836
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-04T18:48:04+00:00
- Post Title: Re: ARchive_neXt

Model viewing [http://prntscr.com/rt22s3](http://prntscr.com/rt22s3) error...
## Post #837
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-04T18:52:51+00:00
- Post Title: Re: ARchive_neXt

what game is it?
## Post #838
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-04T18:54:04+00:00
- Post Title: Re: ARchive_neXt

AC: Revelations
## Post #839
- Username: longpinkytoes
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Feb 27, 2018 2:19 am
- Post datetime: 2020-04-04T22:37:14+00:00
- Post Title: Re: ARchive_neXt

i have AC4 for ps3, do i need to buy AC4 again on steam for pc to be able to use XeNTaX?
## Post #840
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2020-04-05T09:38:41+00:00
- Post Title: Re: ARchive_neXt

> Reply from longpinkytoes ↑Sun Apr 05, 2020 6:37 am at Sun Apr 05, 2020 6:37 am
>
> 
i have AC4 for ps3, do i need to buy AC4 again on steam for pc to be able to use XeNTaX?

Take a cracked one.
## Post #841
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2020-04-09T16:18:41+00:00
- Post Title: Re: ARchive_neXt

Hi Guys, great tool to extract data however I am not finding ANY ships in AC:Black Flag ... if someone knows where they are located? Thanks!!
## Post #842
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2020-04-10T09:15:03+00:00
- Post Title: Re: ARchive_neXt

> Reply from zeroy ↑Fri Apr 10, 2020 12:18 am at Fri Apr 10, 2020 12:18 am
>
> 
Hi Guys, great tool to extract data however I am not finding ANY ships in AC:Black Flag ... if someone knows where they are located? Thanks!!

The only one who can be extracted in one piece is the Jackdaw, all others are splitted in many parts. 
dataPC.forge or extra_data.forge
## Post #843
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2020-04-10T10:51:33+00:00
- Post Title: Re: ARchive_neXt

> Reply from Damoclès ↑Fri Apr 10, 2020 5:15 pm at Fri Apr 10, 2020 5:15 pm
>
> 
zeroy wrote: ↑Fri Apr 10, 2020 12:18 am
Hi Guys, great tool to extract data however I am not finding ANY ships in AC:Black Flag ... if someone knows where they are located? Thanks!!


The only one who can be extracted in one piece is the Jackdaw, all others are splitted in many parts. 
dataPC.forge or extra_data.forge

Thanks, yes I did find the Jackdaw but nothing for the many boats that are in the game, do you know where those parts are located? I did find 3 Deck but with TEST in package name and no textures.
## Post #844
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-11T12:30:30+00:00
- Post Title: Re: ARchive_neXt

AC: I want to remove the palace and big buildings from the game of Revelations, but can someone (3d visualization) throw archive_next ready for me? And if anyone knows where these pieces are, thank you in advance.
## Post #845
- Username: UmutUG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 04, 2020 10:06 pm
- Post datetime: 2020-04-11T12:44:39+00:00
- Post Title: Re: ARchive_neXt

Help me!
## Post #846
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2020-04-13T18:12:50+00:00
- Post Title: Re: ARchive_neXt

> Reply from UmutUG ↑Sat Apr 11, 2020 8:44 pm at Sat Apr 11, 2020 8:44 pm
>
> 
Help me!

Some mesh just do that, not much you can do since the app is not maintained
## Post #847
- Username: akeem699
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 22, 2020 1:31 am
- Post datetime: 2020-04-21T17:39:22+00:00
- Post Title: Re: ARchive_neXt

Hi does anyone know where I can locate the model  from Thomas de Carneillon in assassins creed unity?
## Post #848
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-04-22T11:56:22+00:00
- Post Title: Re: ARchive_neXt

> Reply from akeem699 ↑Wed Apr 22, 2020 1:39 am at Wed Apr 22, 2020 1:39 am
>
> 
Hi does anyone know where I can locate the model  from Thomas de Carneillon in assassins creed unity?

I don't show you their exact location. But you should place different models. And so you have to create the textures yourself.

DataPC_ACU_LGS_BelleEpoque.forge

```
      TEST_MedievalAvatar_Altair_Set
      CN_A_FR_LegacyAvatar_Altair_Glove_Set
      CN_E_MA_PrologueAssassin_HiddenBlade_Set
Body meshs
      CN_U_MA_PrologueAssassin_HiddenBlade_LOD0
      CN_U_MA_PrologueAssassin_LOD0
      CN_U_MA_PrologueAssassin_Robe_LOD0
      CN_U_MA_PrologueAssassin_Robe2_LOD0
```


I do not remember which model I used for the head.  I think this should be it.

```
      CN_U_FR_Avatar_Head_A_Set
Head meshs
      CN_A_FR_Avatar_Head_A_LOD0
```


We have to compare 3 different maps: diffuse, mask and normal.
The textures are in the DataPC_SharedGroup_00.forge file. Or they may be in the next.

If I did it right, something like this will happen.
## Post #849
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2020-05-07T19:06:25+00:00
- Post Title: Re: ARchive_neXt

is there a working version?
I installed the version from page 56 and when I try to open meshes from Brotherhood 
the program throws an error at me and I have to force quit the program with the task manager.
## Post #850
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-05-14T20:57:26+00:00
- Post Title: Re: ARchive_neXt

Anybody knows what is the name of this NPC outfit in Assassin's Creed Unity game files?
This NPC hanging among elite in Versaille on a mission, when we had to find Elise (and almost immediately escape).



Assassin's Creed® Единство2020-5-14-22-38-10.jpg (108.64 KiB) Viewed 205 times
## Post #851
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-16T02:23:07+00:00
- Post Title: Re: ARchive_neXt

> Reply from fullinu ↑Fri May 15, 2020 4:57 am at Fri May 15, 2020 4:57 am
>
> 
Anybody knows what is the name of this NPC outfit in Assassin's Creed Unity game files?
This NPC hanging among elite in Versaille on a mission, when we had to find Elise (and almost immediately escape).
Assassin's Creed® Единство2020-5-14-22-38-10.jpg

There may be something missing. But there must be similar things. You can find missing parts by name similarity.
(I did not add everything in the picture below.)

```
    ACU_CN_U_Lafreniere
       CN_U_Lafreiniere_Head_LOD0
       CN_U_Lafreniere_Hair_LOD3
    ACU_Lafreniere_Softbody
DataPC_ACU_Paris_assets
    CN_U_Lafreiniere_Eyelash_Male_LOD0
    CN_U_Lafreiniere_Eyewet_Male_LOD0
    CN_U_Lafreniere_A_Bits_LOD0
    CN_U_Lafreniere_A_Capelet_LOD0
    CN_U_Lafreniere_A_CassockIn_LOD0
    CN_U_Lafreniere_A_HoodDown_LOD0
    CN_U_Lafreniere_A_Scarf_LOD0
    CN_U_Lafreniere_A_Sleeves_LOD0
    CN_U_Lafreniere_A_Stole_LOD0
    CN_U_Lafreniere_B_Bits_LOD0
    CN_U_Lafreniere_B_Bits_LOD0
    CN_U_Lafreniere_B_Stole_LOD0
    CN_U_Lafreniere_Hair_LOD3
DataPC_ACU_Versailles
    (Same things)
DataPC_ACU_Versailles_assets
    (Same things)
DataPC_SharedGroup_01
    (Textures)
```
## Post #852
- Username: renandantas71
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 18, 2020 10:21 am
- Post datetime: 2020-05-18T02:23:36+00:00
- Post Title: Re: ARchive_neXt

Can someone please have The Assassin's Creed 2 Ezio Trilogy (the remaster) textures?

I'm trying to port and enhance for PC mods.
Thank you very much.
## Post #853
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-18T13:12:27+00:00
- Post Title: Re: ARchive_neXt

> Reply from renandantas71 ↑Mon May 18, 2020 10:23 am at Mon May 18, 2020 10:23 am
>
> 
Can someone please have The Assassin's Creed 2 Ezio Trilogy (the remaster) textures?

I'm trying to port and enhance for PC mods.
Thank you very much.

I previously exported textures from Assassin's Creed: Ezio Collection.
[https://www.deviantart.com/tselman61/ar ... -772677644](https://www.deviantart.com/tselman61/art/PS4-Assassin-s-Creed-Ezio-Collection-Ezio-Head-772677644)
What kind of textures are you looking for?
(I don't have the files of the game right now. But if I need to download it, it will take some time.  )

Assassin's Creed: Ezio Trilogy --> PlayStation 3, Xbox 360
Assassin's Creed: Ezio Collection --> PlayStation 4, Xbox One
## Post #854
- Username: renandantas71
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 18, 2020 10:21 am
- Post datetime: 2020-05-18T13:53:27+00:00
- Post Title: Re: ARchive_neXt

The Ezio uniform textures.
The face textures of the important characters, Pazzi, Borgia, etc.

Well, if you can export the most relevant textures improvements Ubisoft have made that will be a great step in my project.

Of course, I want to implement improvements of my own allied to this. Probaly a Super-HD edition for PC, since we don't get a remaster =/


Ps.: If you want to join the project, add me on steam: renandantas71
## Post #855
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-18T15:04:31+00:00
- Post Title: Re: ARchive_neXt

I did not study all the texture maps. I have no idea what we will encounter.
I will try to download the game from the nearest time. I will review the files of the game when I download it.
I will inform you.
## Post #856
- Username: renandantas71
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 18, 2020 10:21 am
- Post datetime: 2020-05-18T15:11:19+00:00
- Post Title: Re: ARchive_neXt

Thank you very much my friend
## Post #857
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-19T14:00:03+00:00
- Post Title: Re: ARchive_neXt

> Reply from renandantas71 ↑Mon May 18, 2020 11:11 pm at Mon May 18, 2020 11:11 pm
>
> 
Thank you very much my friend

For -->Assassin's Creed The Ezio Collection
In fact, the files of the game are similar to the PC version.


ARchive_neXt works in these files because the game is exactly the same.  (They are similar in terms of archives.) You can use ARchive_neXt v4.03.27.0. (It may not run with the previous version.)

I downloaded the PS4 version of the game. These reasons export textures as if they are damaged. The textures need to be converted to DDS format.
But I didn't review the Xbox One files.  They may not need this process.

Rodrigo Borgia Head
  (Now 256x256)

The resolution of the textures in this game is 1024x1024. (I am talking about the original dimensions of the pictures above.)
Textures from 512 resolution in the original game have increased to 1024 resolution in Assassin's Creed The Ezio Collection version.
But I do not know the size of the head texture in the original game. I mean, I don't know if there is a difference in the textures of each character.
## Post #858
- Username: renandantas71
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 18, 2020 10:21 am
- Post datetime: 2020-05-20T21:03:26+00:00
- Post Title: Re: ARchive_neXt

Well, I can't find  a way to download a Xbox version of the game or a PS4 version, also I can't find a way to download ARchive neXt v4.03.27.0.
Always I try to download the page not enter.
## Post #859
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-24T13:34:20+00:00
- Post Title: Re: ARchive_neXt

Yes, there is no access to the site. I have no idea what the problem is.
My friend said he would fix the problem.
If the problem is not fixed, I will send you the vehicles. I'm looking for the XBox version. If there is an improvement, I will say this.
## Post #860
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-05-24T14:53:33+00:00
- Post Title: Re: ARchive_neXt

I'm tring to extract Evie's default outfit from assassins creed Syndicate using next, but I can only find the textures, not the meshes. Does anyone know what they are called?

Cheers
## Post #861
- Username: renandantas71
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 18, 2020 10:21 am
- Post datetime: 2020-05-30T05:39:49+00:00
- Post Title: Re: ARchive_neXt

Okay, I want to share some of my progress in the Retexture Project of Assassin's Creed 2 for PC, since I can't unpack any of the remaster content, I tried to retexture some things by my own, in my vision in a way that can bring the renaiscence feel. But.. I think the face textures, well, a lot of textures of PS4/Xbox-one remaster is A LOT BETTER, and mixed with that, the two contents togheter and improved... ohhh boy we maybe get the remaster we deserve. Here some screenshots, a Reshade is being used too, I tried to make close to the remaster colors. I don't know if I make it right.





Any help or advise is welcome. And check the moddb page too, you can see some bad things in the past, not in development itself, but personal problems, but is all solved now.

[https://www.moddb.com/mods/assassins-cr ... re-project](https://www.moddb.com/mods/assassins-creed-2-retexture-project)
## Post #862
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-05-30T14:16:31+00:00
- Post Title: Re: ARchive_neXt

You are doing a good work.
I wrote a reply to your message on Steam. 

Give me the textures you're looking for and tell them where they're. I don't know the names of these Characters.  In this way, I can export these textures to you from the PS4 version.  
But the problem is, in what format do the textures have to be?
If I remember correctly, diffuse maps were DXT1(bc1), Normal maps were DXT3(bc2) or DXT5(bc3).
## Post #863
- Username: renandantas71
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 18, 2020 10:21 am
- Post datetime: 2020-05-30T16:31:46+00:00
- Post Title: Re: ARchive_neXt

Well, I need mainly the diffuse, so DXT1 is okay, the rest you can export in DXT3 or DXT5 if necessary
## Post #864
- Username: garysplay
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 31, 2019 3:49 am
- Post datetime: 2020-06-15T18:28:59+00:00
- Post Title: Re: ARchive_neXt

A there's way to extract new Rainbow six siege (Steam) files with this tool? (i tried 1.0 (for downloading i used depotdownloader) and it barely worked)
and there's possible to extract new files with Ghost Recon: Wildlands preset?
## Post #865
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-07-07T11:58:47+00:00
- Post Title: Re: ARchive_neXt

For Honor is not supported anymore?
## Post #866
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-07-07T15:16:11+00:00
- Post Title: Re: ARchive_neXt

> Reply from ngovandang ↑Tue Jul 07, 2020 7:58 pm at Tue Jul 07, 2020 7:58 pm
>
> 


For Honor is not supported anymore?

No
## Post #867
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-07-08T06:14:41+00:00
- Post Title: Re: ARchive_neXt


## Post #868
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-07-29T22:17:50+00:00
- Post Title: Re: ARchive_neXt

Download page is down
## Post #869
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2020-09-18T11:10:09+00:00
- Post Title: Re: ARchive_neXt

Anybody willing to rehost the download? I'm trying to use some of the the other extractors but nothing's working.
## Post #870
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2020-09-18T12:50:47+00:00
- Post Title: Re: ARchive_neXt

> Reply from flipdark95 ↑Fri Sep 18, 2020 7:10 pm at Fri Sep 18, 2020 7:10 pm
>
> 
Anybody willing to rehost the download? I'm trying to use some of the the other extractors but nothing's working.
[http://www.tbotr.net/Downloads/ARchive_neXt.msi](http://www.tbotr.net/Downloads/ARchive_neXt.msi)

link still works but the website is down atm.
## Post #871
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-09-30T20:31:24+00:00
- Post Title: Re: ARchive_neXt

Can someone please reupload the Arximporter? The OBJ files I'm getting out of Archive_Next have missing UV maps, are scaled all wrong, and are positioned wrong when imported.
## Post #872
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-10-02T08:35:29+00:00
- Post Title: Re: ARchive_neXt

> Reply from kingfisher13 ↑Thu Oct 01, 2020 4:31 am at Thu Oct 01, 2020 4:31 am
>
> 
Can someone please reupload the Arximporter? The OBJ files I'm getting out of Archive_Next have missing UV maps, are scaled all wrong, and are positioned wrong when imported.

I don't know if it's right to do this. (Because we cannot access the site.)

But this must be what you want. I hope you solve your probl
[arxImporter_v2_12_20.zip](https://xentaxbackup.github.io/file/18790_arxImporter_v2_12_20.zip)
## Post #873
- Username: abodora
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 16, 2020 12:26 am
- Post datetime: 2020-10-12T12:56:53+00:00
- Post Title: Re: ARchive_neXt

> Reply from TSelman61X ↑Tue May 19, 2020 10:00 pm at Tue May 19, 2020 10:00 pm
>
> 
renandantas71 wrote: ↑Mon May 18, 2020 11:11 pm
Thank you very much my friend 


For -->Assassin's Creed The Ezio Collection
In fact, the files of the game are similar to the PC version.


ARchive_neXt works in these files because the game is exactly the same.  (They are similar in terms of archives.) You can use ARchive_neXt v4.03.27.0. (It may not run with the previous version.)

I downloaded the PS4 version of the game. These reasons export textures as if they are damaged. The textures need to be converted to DDS format.
But I didn't review the Xbox One files.  They may not need this process.

Rodrigo Borgia Head
  (Now 256x256)

The resolution of the textures in this game is 1024x1024. (I am talking about the original dimensions of the pictures above.)
Textures from 512 resolution in the original game have increased to 1024 resolution in Assassin's Creed The Ezio Collection version.
But I do not know the size of the head texture in the original game. I mean, I don't know if there is a difference in the textures of each character.

@TSelman61X
can you please check your private messages.
## Post #874
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2021-01-02T21:29:41+00:00
- Post Title: Re: ARchive_neXt

any plans for ghost recon breakpoint?
## Post #875
- Username: ChaoMaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 06, 2021 10:41 am
- Post datetime: 2021-02-06T03:03:54+00:00
- Post Title: Re: ARchive_neXt

Hi guys, I'm trying to extract a model from the PC version of Black Flag. I want to grab Duncan Walpole's outfit and I can view the model just fine in the program. When I extract as an .obj and import into Blender I get an empty file. Is there some trick or something to this?
## Post #876
- Username: yanosch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 14, 2021 10:40 pm
- Post datetime: 2021-04-14T14:51:50+00:00
- Post Title: Re: ARchive_neXt

Hi Guys!

I'm looking for a very specific character model but I have such a hard time finding it. 
Is somebody willing to share it for me?
[2c30fa03-cc1c-4056-b16c-38e932dc7ff5_rw_1200.jpg](https://xentaxbackup.github.io/file/19913_2c30fa03-cc1c-4056-b16c-38e932dc7ff5_rw_1200.jpg)
## Post #877
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2021-04-15T09:50:39+00:00
- Post Title: Re: ARchive_neXt

> Reply from yanosch ↑Wed Apr 14, 2021 10:51 pm at Wed Apr 14, 2021 10:51 pm
>
> 
Is somebody willing to share it for me?

Are you looking for this character?
Take it --> [https://www.mediafire.com/file/c5puzn50 ... pe.7z/file](https://www.mediafire.com/file/c5puzn50tj69aux/La_Volpe.7z/file)
No hands and eyes. But you can find it yourself. I think they are common meshes. (Generic)
## Post #878
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2021-08-08T16:16:25+00:00
- Post Title: Re: ARchive_neXt

So, since I wanted to play with this, but have no intention to use 3DS, I ported the ARX importer to Blender.

The importer can import multiple files at once, and will reuse materials and images between models, both when importing simultaneously and sequentially.

Since the coordinates in the models have weird big values, the importer has an option to apply a scale factor. Two useful factors are supported:

* 1/31460, which should be used for AC1 and AC2 character models (based on comparison of the same character with Brotherhood)
* 1/100000000 (default), which is suitable for most map objects, and characters in Brotherhood and presumably later games.

When looking for textures, in addition to the absolute path to the Temp directory from the arx file, it tries the same directory as the arx file, and any of its subdirectories.
[import_arx.zip](https://xentaxbackup.github.io/file/20596_import_arx.zip)
## Post #879
- Username: fn2505
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 24, 2018 9:26 pm
- Post datetime: 2021-09-13T16:00:04+00:00
- Post Title: Re: ARchive_neXt

Does the software support exporting animations?
## Post #880
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2021-09-15T23:21:24+00:00
- Post Title: Re: ARchive_neXt

> Reply from fn2505 ↑Tue Sep 14, 2021 12:00 am at Tue Sep 14, 2021 12:00 am
>
> 
Does the software support exporting animations?

Unfortunately.
Bones don't say export either.
## Post #881
- Username: Neku
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 04, 2021 2:46 am
- Post datetime: 2021-10-03T21:33:18+00:00
- Post Title: Re: ARchive_neXt

I'm trying to use this tool to extract the R6S files, but it always says there are errors and I can't export them, anyone knows how to solve this problem? Thanks
## Post #882
- Username: Alioram
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 26, 2021 8:15 pm
- Post datetime: 2021-10-26T12:20:38+00:00
- Post Title: Re: ARchive_neXt

Hi all.
Is it possible to unzip files from Assassin's Creed Odyssey? ARchive_neXt swears when trying to open these .forge files. PC game, Steam version.
## Post #883
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2021-10-29T21:09:08+00:00
- Post Title: Re: ARchive_neXt

> Reply from Alioram ↑Tue Oct 26, 2021 8:20 pm at Tue Oct 26, 2021 8:20 pm
>
> 
Hi all.
Is it possible to unzip files from Assassin's Creed Odyssey? ARchive_neXt swears when trying to open these .forge files. PC game, Steam version.

Unfortunately no.
## Post #884
- Username: ahmetoyl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 21, 2021 3:21 pm
- Post datetime: 2021-12-21T07:22:34+00:00
- Post Title: Re: ARchive_neXt

[http://www.tbotr.net/Downloads/ARchive_neXt.msi](http://www.tbotr.net/Downloads/ARchive_neXt.msi) the link is not working. Can someone give me the program?
## Post #885
- Username: momo1
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-21T12:40:54+00:00
- Post Title: Re: ARchive_neXt

> Reply from ahmetoyl ↑Tue Dec 21, 2021 3:22 pm at Tue Dec 21, 2021 3:22 pm
>
> 
http://www.tbotr.net/Downloads/ARchive_neXt.msi the link is not working. Can someone give me the program?

Here is the mirror [https://drive.google.com/file/d/10QmfUF ... sp=sharing](https://drive.google.com/file/d/10QmfUFdj4oF59eMPwbNZ6rmxzJgmcSrK/view?usp=sharing)
## Post #886
- Username: photojoe
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 27, 2016 6:49 am
- Post datetime: 2022-07-13T15:15:00+00:00
- Post Title: Re: ARchive_neXt

I'm having trouble locating the Native bodies, I've scanned through the PC_DX11 and other files. I figured frontier and found the Chief, but no other male or female Native bodies or weapons. 

I did a search on for naming conventions but came up blank. Any help finding the bodies for the soliders (American-British, and the natives, plus the weapons) would be great.

Are there better tools for the ACIII and above now that Ubisoft is pulling support for them, I want to grab the models.

Thanks,

Joe
## Post #887
- Username: ElHabto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 30, 2022 5:43 am
- Post datetime: 2023-01-01T11:40:08+00:00
- Post Title: Re: ARchive_neXt

The download link is broken. Any solution?
## Post #888
- Username: Cheatsurfer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 08, 2016 7:14 pm
- Post datetime: 2023-10-07T12:19:50+00:00
- Post Title: Re: ARchive_neXt

Links
1) original link (web archive):
[http://web.archive.org/web/201704091025 ... =1&dlid=40](http://web.archive.org/web/20170409102555/http://www.tbotr.net/modules.php?mod=Downloads&op=download&sid=4&ssid=1&dlid=40)

2) mirror (by ikskoks):

> Reply from ikskoks ↑Tue Dec 21, 2021 8:40 pm at Tue Dec 21, 2021 8:40 pm
>
> 
Here is the mirror https://drive.google.com/file/d/10QmfUF ... sp=sharing
