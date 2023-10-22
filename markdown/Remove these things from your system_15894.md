## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2017-02-18T07:05:05+00:00
- Post Title: Remove these things from your system

Most of the Noesis crashes I see are caused by horrible software that infests virtually every facet of the user's system. Having just gone through a backlog of crash reports from the last 4 months, I've compiled a list of the top offenders.

Many of these are modules associated with applications/malware/spyware which are loaded into virtually every process on your machine (or in some cases, any application with Explorer hooks), which will cause many programs to crash outright. This software is all trash, which is at best making your system run worse and at worst sending information about everything you do and see to someone else. In most cases, this is software that was written by terrible, horrible programmers who gave up on living and resigned themselves to writing garbage for giant corporations and/or porn sites.

SageThumbs
"C:\Program Files (x86)\SageThumbs\32\libgfl340.dll"
SageThumbs is a huge turd. The above module is just one particular version of an integral module for this program, but I've seen crashes stem from many different versions of SageThumbs. The software isn't meant to be malware or spyware, but it's extremely unstable, very bad at handling corrupted data, and will be causing crashes in Explorer and many different programs with Explorer interfaces or hooks. Do not use it.

Brazilian Banking Plugin
"C:\Program Files (x86)\GbPlugin\gbieh.dll"
"C:\Program Files (x86)\GbPlugin\gbiehbnt.dll"
"C:\Program Files\GbPlugin\gbiehCef.dll"
...

This module, or some variant thereof, is often required by Brazilian banks to perform any manner of online banking transaction. Problem is, this very module is very commonly spyware/malware, or the target of many potential exploits. It also needlessly infests the process space of many applications on your system even if it isn't a malware variant. If your bank requires this plugin, tell them they're idiots and that they're putting their clients at risk. Also uninstall it and find some other way to do your banking.

RealPlayer
"C:\Program Files (x86)\Real\realplayer\RealDownloader\dtvhooks.dll"
It's a terrible shame that RealPlayer somehow survived the 90's, and it's maintained its status through the ages as a hideous suite of bloatware. This thing will infest every process on your system, doing awful things and probably monitoring plenty of what you do. Get rid of it, and use a better audio/video player.

AMD HydraVision Desktop Manager
"C:\Program Files (x86)\ATI Technologies\HydraVision\HydraDMH.dll"
The AMD/ATI desktop manager is horrible, and frequently causes compatibility issues with OpenGL. This software isn't required and doesn't help or accelerate your graphics hardware in any way. If it isn't essential to you, you'd be better off removing it.

NielsenOnline
"C:\Program Files (x86)\NetRatingsNetSight\NetSight\meter1\nphooks.dll"
This software can live anywhere, but wherever it lives, it will be infesting most processes on your machine. It's watching everything you do. Get rid of it.

AMD/ATI OpenGL Driver
"C:\WINDOWS\System32\...\atioglxx.dll"
It's pretty terrifying how many crashes come out of here, as compared to the number of crashes I've seen coming out of the NVIDIA OpenGL driver. It's probably safe to say AMD is doing a really bad job maintaining their various OpenGL implementations. Typically, when someone comes to me with the ATI OGL driver in a crash callstack, it's immediately fixed by updating their drivers. However, AMD is also prone to breaking critical aspects of the OpenGL driver in latest driver releases, so you may also have luck in rolling back your driver version.

Remotr
"C:\Program Files (x86)\Remotr\GfxHelper.dll"
This program registers Windows GDI hooks which appear to cause crashes even when you aren't using it for remote access. Pretty nasty. Recommend finding an alternative remote desktop solution.

Raptr Plays.tv
"C:\PROGRA~2\RAPTRI~1\PlaysTV\ltc_game32-118416.dll"
This thing is also horrendous and causes a wide variety of crashes via GDI hooks. Do not use it. There are plenty of other capture solutions that don't suck.

BitDefender AVCUF32 Module
"c:\avc3\avcuf32.dll"
There's a good chance this file is malware in disguise or from a dated version of BitDefender, especially if it's on a questionable path like the above. This is a semi-common crash, with the module size being in excess of 1MB, and not matching any legitimate BitDefender distribution. If you have this file, you should probably stop running those .exe files that naughtyrussianslutspeeingonoranges.com tells you to download.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2017-02-18T11:36:06+00:00
- Post Title: Remove these things from your system

Say this to the software mentioned. 

It makes one
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-08-11T01:26:12+00:00
- Post Title: Remove these things from your system

Does anyone have a recommendation over SageThumbs?

For work I regularly use .tga, .dds .jpg, .bmp and a few other formats including tiff, and finding something free and good that supports them all can be a tad difficult.

Hell even if its paid but really cheap it'd be ok.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-08-16T07:17:15+00:00
- Post Title: Remove these things from your system

> Reply from lionheartuk
>
> Does anyone have a recommendation over SageThumbs?
i installed Pictus for the tga and psd thumbnail support 
[https://poppeman.se/pictus/](https://poppeman.se/pictus/)

and the TxView.dll from the Directx SDK for dds support
[https://www.microsoft.com/en-us/downloa ... px?id=6812](https://www.microsoft.com/en-us/download/details.aspx?id=6812) 
just had to copy TxView.dll to Windows\System32 folder and register it in command prompt with regsvr32 txview.dll
got the instruction from here
[https://superuser.com/questions/738684/ ... ge-formats](https://superuser.com/questions/738684/windows-7-show-thumbnails-for-special-image-formats)


there is also these you could try
FastPictureViewer codec pack for $9.99
[https://www.fastpictureviewer.com/codecs/](https://www.fastpictureviewer.com/codecs/)
last free version was 1.70 from what i read, i think you can get it here
[http://wareseeker.com/free-fastpicturev ... k-version/](http://wareseeker.com/free-fastpictureviewer-wic-codec-pack-version/)

and MysticThumbs for $24.95
[https://mysticcoder.net/mysticthumbs/](https://mysticcoder.net/mysticthumbs/)
last free version here
[http://www.321download.com/LastFreeware ... c%20Thumbs](http://www.321download.com/LastFreeware/page40.html#Mystic%20Thumbs)
