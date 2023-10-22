## Post #1
- Username: Amancue
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 25, 2008 8:19 am
- Post datetime: 2008-07-28T07:11:02+00:00
- Post Title: Appleseed EX

Im looking @ the PS2 game Appleseed EX and Im still trying to determine what all the files contain,. namely I'm looking for the models to use in a realworld model project any help would be appreciated

The File Extensions used in the game are
.AHX
.ADX
.SFD
of Course some .IRX and IMG's
.AFS
.ADS

and if anyones needs I can upload some sample files to one of the file storage places
most of the files in there are .ADX's in multiple different directorys
## Post #2
- Username: Amancue
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 25, 2008 8:19 am
- Post datetime: 2008-07-31T22:04:39+00:00
- Post Title: Appleseed EX

Im Bumping this to show I've added more info to my original post
## Post #3
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-08-02T13:03:30+00:00
- Post Title: Appleseed EX

> Reply from Amancue
>
> Im looking @ the PS2 game Appleseed EX and Im still trying to determine what all the files contain,. namely I'm looking for the models to use in a realworld model project any help would be appreciated

The File Extensions used in the game are
.AHX
.ADX
.SFD
of Course some .IRX and IMG's
.AFS
.ADS

and if anyones needs I can upload some sample files to one of the file storage places
most of the files in there are .ADX's in multiple different directorys

sfd are the video files:
[viewtopic.php?f=18&t=3084](http://forum.xentax.com/viewtopic.php?f=18&t=3084)

adx is audio, use a program called adx2wav to convert them to wav (there are others too but that's what i use, if you can't find it, tell me and i'll upload it to you

forget about the irx and img they are ps2 mdules (kinda like .dll and .exe)

afs is a file container use afsexplorer to open it (again, tell me if you can't find it)

about ahx and ads...well I'm not really sure... ahx may be renamed adx files for protection and ads may be renamed afs...
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-08-04T15:23:00+00:00
- Post Title: Appleseed EX

adx and ahx are sound files from CRI Middleware. While adx is used for sound effects, ahx is used for voice files. Like for adx, there's a program called ahx2wav for that.

Everything else is as xrevenge said, so that'd only leave ads.
## Post #5
- Username: Amancue
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 25, 2008 8:19 am
- Post datetime: 2008-08-04T16:19:48+00:00
- Post Title: Appleseed EX

well doing some research prior to my first post I had figured out most of them.. at least vaugely, but the one I still havnt figured out in the least from either my own research or here,.. is those ADS,. trying to figure out where they hide the blasted graphics/meshes,.. not that Its probably important but theres also a Dummy0 file thats about 900megs but If I recall from old PS games thats just a null file isnt it
I of course tried the whole emu route and rippers but as the only one I could get to return anything was the ZeroGS plugin and that renders everything flat if you look @ it straight on it appears to have depth and I've tried every ripper I could find so now Im trying to long way,.. if anyone needs me to post any information I'll be more then happy too when I get home search as screenshots of the file structure, or files to hack @ such as the .ads files

all this because I just can not model lowpoly enough to be useful for my project everything I end up doing tends to be way to high for most things game related
## Post #6
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-08-05T08:22:59+00:00
- Post Title: Appleseed EX

> Reply from Amancue
>
> well doing some research prior to my first post I had figured out most of them.. at least vaugely, but the one I still havnt figured out in the least from either my own research or here,.. is those ADS,. trying to figure out where they hide the blasted graphics/meshes,.. not that Its probably important but theres also a Dummy0 file thats about 900megs but If I recall from old PS games thats just a null file isnt it
I of course tried the whole emu route and rippers but as the only one I could get to return anything was the ZeroGS plugin and that renders everything flat if you look @ it straight on it appears to have depth and I've tried every ripper I could find so now Im trying to long way,.. if anyone needs me to post any information I'll be more then happy too when I get home search as screenshots of the file structure, or files to hack @ such as the .ads files

all this because I just can not model lowpoly enough to be useful for my project everything I end up doing tends to be way to high for most things game related

this *may* help:

[http://www.fileinfo.net/extension/ads](http://www.fileinfo.net/extension/ads)

or this:

> File extension ADS description:
>
> ADS applications will have to be recompiled as ADSRX applications for the Visual LISP environment to access externally defined functions.

visual lisp is:

Visual LISP

Company / developer:
  Autodesk, Inc.
Visual LISP

It is a full-featured, interpretive programming language that you can use to call AutoCAD commands, system variables, and dialog boxes. 

Visual LISP offers a complete development environment, including:
Reduced development time using the integrated development environment (IDE)
Access to ActiveX® objects and event reactors
Source code protection against theft and alteration
Operating system file-operation functions
LISP function extensions for list processing

try here:

[http://en.wikipedia.org/wiki/Ada_programming_language](http://en.wikipedia.org/wiki/Ada_programming_language)

or here:

[http://filext.com/file-extension/ADS](http://filext.com/file-extension/ADS)

oh and thanks forte i've added ahx2wav in my collection 
i've no need for it now but who knows?
besides, most of the stuff i have are unused anyway, i just like collecting them...
so its kinda like this:
[2008-08-05_112219.jpg](https://xentaxbackup.github.io/file/1603_2008-08-05_112219.jpg)
## Post #7
- Username: Amancue
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 25, 2008 8:19 am
- Post datetime: 2008-08-09T18:06:49+00:00
- Post Title: Appleseed EX

ok I was looking over the dvd since im back on my desktop and for the life of me can not figure out where I got ads from there is no ADS on the dvd anyways I opened the AFS using AFSexplorer
and theres 
.DAR Files - I did some searching and MGS using DAR as a container but Solidus cant seem to open them or I have the settings wrong
.TM2 files - I know these are Playstation Graphic Files
.DSE Files
.LDP Files
.ELO Files
.ELS Files
.EPR Files
.LFM Files

again I have no idea where my brain was when I came up with .ADS I could have sworn I double checked several times before I posted oh well,.. hope this helps so more in pointing me in the direction of other tools
