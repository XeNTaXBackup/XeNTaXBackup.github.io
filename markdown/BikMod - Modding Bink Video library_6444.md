## Post #1
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2011-04-17T14:34:31+00:00
- Post Title: BikMod - Modding Bink Video library

Taken from official forum: [http://tools.game-alive.com/forums/](http://tools.game-alive.com/forums/)
-------------------------------------------------------------------------------------

The BikMod library is a tool that allows extending control of video playback and modding possibilities in games that uses [Bink Video](http://radgametools.com/bnkmain.htm) library from [RAD Game Tools](http://radgametools.com/).

Current features:
-Subtitle displaying, support for unicode, placement and position control, custom fonts and font styles.
-Possibility to disable Bink library and video playback completely.
-Runtime dynamic linking of Bink library, and safe function calling.
-Advanced debugging, memory leak detection and function error checking.
-Advanced logging of function calls, errors and debug messages.
-Advanced configuration.
-Support for older and newer games.
-Freeware (zlib license).

Planned features:
-Frame scaling, video filters.
-Support for more subtitle file formats. (Currently only SubRip is supported.)
-Cross platformability. (Currently only Windows is supported.)
-Plugin SDK.

How to request a new features:
-Post in this topic.

Before downloading, please read this announcement: [Click](http://tools.game-alive.com/forums/viewtopic.php?f=4&t=2).

Download:
[http://tools.game-alive.com/download/bikmod_v0.3c.zip](http://tools.game-alive.com/download/bikmod_v0.3c.zip)

Installation:
-Open game installation folder.
-Rename file binkw32.dll to libbinkw32.dll.
-Extract BikMod installation archive to game folder.
-Thats it, run game.

Uninstallation:
-Delete file binkw32.dll.
-Rename file libbinkw32.dll to binkw32.dll
-Done.

Configuration:
-Open file binkw32.cfg in text editor, modify and save.

Using subtitles:
-Rename subtitle file to name of .bik file, and append underscore, language code and track index, e.g. SierraLogo.bik -> SierraLogo_en0.srt.
-Copy subtitle file to folder "subtitle" or to folder where .bik file is located.

Known bugs:
-Doesn't work properly with DirectDraw games when running fullscreen. Will be fixed in new version.

Tested games:
-Arcanum - Steamworks and Magick Obscura
-Fallout: New Vegas
-Hitman - Blood Money
-Urban Chaos
-Diablo 2
-C&C: Red Alert 2

Screenshots:
## Post #2
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2011-04-28T12:27:23+00:00
- Post Title: BikMod - Modding Bink Video library

New version available!

-Added support for .bik files that are opened from archive or memory. Filenames are now automatically generated from .bik's file header, and it's possible to load and display subtitles for them.
-Added version checking. It will also inform you when new version of BikMod library is available to download.
-Fixed bug that in some cases caused host application crash when copying frame data back to buffer.
-Fixed some minor bugs.

Download: [http://tools.game-alive.com/forums/view ... p?f=4&t=10](http://tools.game-alive.com/forums/viewtopic.php?f=4&t=10)
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-04-29T21:59:16+00:00
- Post Title: BikMod - Modding Bink Video library

So I guess the OFFICIAL tool and SDK isn't enough?

Edit: Nevermind, I suppose some people may not have the SDK, since it's not totally free, but even the free tool really does all you need, I've never had a problem making a video file made with the official tool and it not working with any game.
## Post #4
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2011-04-30T03:42:11+00:00
- Post Title: BikMod - Modding Bink Video library

> Reply from brienj
>
> So I guess the OFFICIAL tool and SDK isn't enough?

Edit: Nevermind, I suppose some people may not have the SDK, since it's not totally free, but even the free tool really does all you need, I've never had a problem making a video file made with the official tool and it not working with any game.

I really doubt that there is such tool in the official SDK. This is a proxy library that extends features of original library. Also, this tool is made for any game, including those with closed source codes.
## Post #5
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2011-05-27T05:36:58+00:00
- Post Title: BikMod - Modding Bink Video library

Announcement: The development has been abandoned  

All files will be taken down on 31.5, you better download it now, because it won't be reuploaded.

Good bye.
## Post #6
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2015-11-16T11:12:59+00:00
- Post Title: BikMod - Modding Bink Video library

Hi, I'm actually testing this library, is there a solution for 2nd version of bink files (bink2w64.dll) ? Thanks
## Post #7
- Username: Loomy
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-12-19T21:44:29+00:00
- Post Title: BikMod - Modding Bink Video library

There actually is a later version 0.3e here: 
[http://tools.game-alive.com/forums/view ... p?f=4&t=10](http://tools.game-alive.com/forums/viewtopic.php?f=4&t=10)
Direct: [http://tools.game-alive.com/download/bikmod_v0.3e.zip](http://tools.game-alive.com/download/bikmod_v0.3e.zip)
Or take the attachment:


 bikmod_v0.3e.zip
(75.36 KiB) Downloaded 139 times
## Post #8
- Username: riadaendo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 28, 2016 8:24 pm
- Post datetime: 2016-03-28T12:30:22+00:00
- Post Title: BikMod - Modding Bink Video library

> Reply from phill05
>
> Hi, I'm actually testing this library, is there a solution for 2nd version of bink files (bink2w64.dll) ? Thanks

Hi, when you work with different software you may have a problem like Bink2w64.dll because of several reason for example because of error about of its absence. So to deal with this you could reinstall your software or you can install something like fix dll tool for example from here: [http://fix4dll.com/bink2w64_dll](http://fix4dll.com/bink2w64_dll) .Good Luck.
## Post #9
- Username: Saeid0034
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 13, 2020 11:54 pm
- Post datetime: 2020-06-16T17:18:23+00:00
- Post Title: BikMod - Modding Bink Video library

hi, sorry for get this old topic up again
anyone here have bikmod 5.9e?
all link are dead
or at least anyone can give me radtools 1.5x ?



Annotation 2020-06-16 214951.jpg (12.16 KiB) Viewed 304 times
## Post #10
- Username: Saeid0034
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-16T21:44:32+00:00
- Post Title: BikMod - Modding Bink Video library

Maybe this will help you --> [viewtopic.php?p=129908#p129908](https://forum.xentax.com/viewtopic.php?p=129908#p129908)
## Post #11
- Username: Saeid0034
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 13, 2020 11:54 pm
- Post datetime: 2020-06-17T13:40:46+00:00
- Post Title: BikMod - Modding Bink Video library

> Reply from ikskoks ↑Wed Jun 17, 2020 5:44 am at Wed Jun 17, 2020 5:44 am
>
> 
Maybe this will help you --> viewtopic.php?p=129908#p129908
thanks for reply
my game is Obscure 1
by check binkw32.dll i find out this game use v1.5x of radtools
sadly i cant find it anyway
i use all files you put on your post But the problem remains and is not solved
my problem is after i create a new bik video, game cant play audio from it any more and only show video! This is a very strange problem because radtools play both audio and video without any problem
can you help me a little about it?
