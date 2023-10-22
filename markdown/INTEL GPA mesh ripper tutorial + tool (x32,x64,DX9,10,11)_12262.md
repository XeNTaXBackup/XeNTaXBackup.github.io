## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-22T11:40:29+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Posted this on facepunch but will relay here and explain some further technical info.

FULL TUTORIAL HERE
[http://dev.cra0kalo.com/?p=213](http://dev.cra0kalo.com/?p=213)

What you will need:

Intel GPA 2014 (direct msi link) or Intel GPA 2014 32bit (direct msi link)
[http://registrationcenter-download.inte ... ws_x64.msi](http://registrationcenter-download.intel.com/akdlm/irc_nas/4674/gpa_14.3_release_231370_windows_x64.msi)
[http://registrationcenter-download.inte ... ws_x86.msi](http://registrationcenter-download.intel.com/akdlm/irc_nas/4674/gpa_14.3_release_231370_windows_x86.msi)

NET Frameworks (4.5 recommended) 
[http://msdn.microsoft.com/en-us/vstudio/aa496123](http://msdn.microsoft.com/en-us/vstudio/aa496123)
GPA patched -> FrameAnalyzer.patched
[http://rel.cra0kalo.com/depot/FrameAnalyzer.patched.zip](http://rel.cra0kalo.com/depot/FrameAnalyzer.patched.zip)


Run the server monitor hook your application (titanfall in this example) then run


Control + Shift + C (capture a frame)

Fire up the Patched frame analyzer


Find your drawcall (erg) and rightclick save geometry


Ignore Roxas choose your export format and save!


Tutorial over


Top credits to master131 though for his actual .net injector

Now if only someone could help map the UV coordinates from the const shader
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-22T19:47:36+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Works well.  UV support would be a huge win. Hope you're able to figure that out. for most games, UV is usually the first or second set of TEXCOORD. But since there is no standardizaton, some guesswork is involved. You'd probably need to build up an interface to allow different sets to be tried (similar to how NinjaRipper does it).
## Post #3
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-11-22T21:26:28+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Great work men congratulations but i dont know if some ask already  ¿Did this will work on Emulators to like Dolphin, PCSX2 or just PC games?
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-11-22T21:51:31+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Oh this is very interesting.

I can't see it working well with PCSX2 since the engine renders most things to a 2D buffer I believe, nothing has much of a Z axis, but should be fine in Dolphin since that works fine with other rippers.

Are there any plans to make this work with earlier versions of direct X at all, there are a few rippers but the lowest anything goes is DirectX8, I'm really hoping for something to go as low as DX7 myself (theres something I have that outputs to DX7 that I really want the models from).
## Post #5
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2014-11-24T16:05:27+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

This is amazing！！

> Reply from lionheartuk
>
> 
I can't see it working well with PCSX2 since the engine renders most things to a 2D buffer I believe, nothing has much of a Z axis, but should be fine in Dolphin since that works fine with other rippers.

Are there any plans to make this work with earlier versions of direct X at all, there are a few rippers but the lowest anything goes is DirectX8, I'm really hoping for something to go as low as DX7 myself (theres something I have that outputs to DX7 that I really want the models from).
I also agree, a DX6-7 ripper will be awesome, there are many great games that use DX7 yet models can't be ripped from. Must test it in PCSX2 but I'm also sceptical about it (ninjaripper actually rips the models but they are out extremely skewed out, so it's impossible to make good rips of car models for example - especially if highly detailed).
## Post #6
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-11-24T19:51:53+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Ok  i tested on Dolphin and works fine but of course didnt work on PCSX2 well did make a dump but the program mention that there is no
3D on it so yea XD i will test on other PC games and see how they work.
## Post #7
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2014-11-25T09:05:14+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

> Reply from The Chief
>
> Ok  i tested on Dolphin and works fine but of course didnt work on PCSX2 well did make a dump but the program mention that there is no
3D on it so yea XD i will test on other PC games and see how they work.
Thanks for that！ I only have a 32bit machine, so I can't test it
## Post #8
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2014-11-28T21:13:58+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

About the no 3D, I had the same thing in Bad Company 2, this happened because I set the DXmode on 9, when I changed it to 10/11 it worked. Might work for PCSX2 too or if you use another video plugin

still weird that it happens as GPA works with DX9
## Post #9
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-11-28T21:30:11+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Well i test all the plugins (DX9 , DX10 , DX11 and OpenGL) of course none works XD but generate a dump file that cant be loaded but still there is some old builds with more plugins so i will make sure to fully test tose.
## Post #10
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-11-29T10:50:43+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

There aren't any tools that get full 3D Rips from PCSX2, its because the emulator itself has no actual zdepth, so things actually are more or less flat, you just need to stretch things out on the Z axis same as with other 3D Rippers, its a limitation of PCSX2 that I don't see getting fixed because it doesn't seem to matter when playing the games themselves, only when ripping meshes.
## Post #11
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2015-01-06T00:58:12+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

> Reply from The Chief
>
> Ok  i tested on Dolphin and works fine but of course didnt work on PCSX2 well did make a dump but the program mention that there is no
3D on it so yea XD i will test on other PC games and see how they work.

How did you get it to work on Dolphin? Haven't been able to even see the overlay yet even when cycling with CTRL+F1..
## Post #12
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2015-02-24T12:32:16+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

So. It works with 64-bit games like CoD:AW etc?
## Post #13
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-06-12T12:32:16+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

can we unpack the file created ???
the file .gpa_frame
## Post #14
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-06-16T04:31:50+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Updated please update to this version

> 1.2
>
> -Removed Intel Logo as requested by the Intel GPA team.
>
> -Fixed localization resulting in '.' as a ','
>
> 1.1
>
> -Added export format PLY
>
> -Removed redundant code
>
> -Added Diagnostic Framework
>
> 1.0
>
> -Inital Release
[http://rel.cra0kalo.com/depot/FrameAnalyzer.patched.zip](http://rel.cra0kalo.com/depot/FrameAnalyzer.patched.zip)
## Post #15
- Username: Userx64
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 24, 2016 3:35 pm
- Post datetime: 2016-01-24T07:40:44+00:00
- Post Title: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Just found this thread and am trying out the versions posted. However, The monitor application keeps crashing after the patched frame analyzer selects the dump to analyze.
Which leads to " Connection Lost " in the analyzer. Not exactly sure what the crash error is for the Monitor, doesn't say anything but close or analyze in Windows 7 Ultimate 64 bit.

Edit to add:

Just installed the 2015 version of the IntelGPA and everything seems to be working fine.
## Post #16
- Username: gcr27
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jul 31, 2017 8:19 am
- Post datetime: 2023-07-15T03:06:27+00:00
- Post Title: Re: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

Windows 10 not ripping uses a 64bit not saying configurate software to use in dx11 games
## Post #17
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2023-08-11T13:41:16+00:00
- Post Title: Re: INTEL GPA mesh ripper tutorial + tool (x32,x64,DX9,10,11)

This was released a while ago so I'm not surprised it's not working on the latest build.
