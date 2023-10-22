## Post #1
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-01-21T07:27:52+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hello. This is a revised topic, the subject of which is reading/extracting the contents of the Crash Bandicoot series' archive files.
Each game in the series uses archives with the file extension .NSF (not to be confused with NES Sound Format files.) for each .NSF archive, a .NSD file of the same name can be found within the same folder. Inside these archives are all game elements (excluding Crash Bandicoot 3's "Spyro the Dragon" demo, found under *\DRAGON.) These extensions have been found within the archives of the 2nd and 3rd games (EDIT: last updated 1:56 PM 8/06/2013:)
.c - Code
.SVTX   Object Animation(?), "Shape Vertex"(?)
.TGEO   Object Model(?), "Thing Geometry"(?)
.WGEO   Scenery Model(?), "World Geometry"(?)
.SLST   Precomputed Scenery Occlusion Data(?), "Scenery List"(?)
.TPAG   Texture Page
.LDAT   Link Data(?)
.ZDAT   Level Section (objects, collision)
.CPAT*
.BINF*
.OPAT*
.GOOL - Game Oriented Object Lisp
.ADIO - Audio
.MIDI - Musical Instrument Digital Interface
.INST - Instruments
.VCOL - Vertical Collision(?), Virtual Collision(?)
.LINK*
.MDAT*
.RAWD
.IPAL - Palette(?)
.PBAK - Playback (i.e. Demos)
.SDIO - Speech Audio
.VIDO
*Not present in any NSF file
Reply if you can identify any of the other file extensions in this list.

Objects within the .NSF files are referenced with names (some with numbering, presumably for animation.) (EDIT: Incorrect, read topic for details.)
For example, some of the objects from Crash Bandicoot 3:
obj_title
obj_elevator
obj_button_s3
obj_button_s4
obj_button_s2
obj_button_s1
obj_button_s5
obj_button_s6
obj_warp_level_stats
obj_warp_effect
...
obj_snow_ending#6
obj_snow_ending#4
obj_snow_ending#8
obj_snow_ending#7
obj_snow_ending#5
obj_snow_ending#9
obj_ending_steam#10
obj_cortex_baby
obj_ending_steam#11
obj_ending_steam#12

Below are the largest and smallest .NSF and .NSD files found within Crash Bandicoot 3's folders:
*\S3\S000003A.NSF - The largest .NSF archive found within Crash Bandicoot 3's */S3 folder. (U)
*\S3\S000003B.NSF - The smallest .NSF archive found within Crash Bandicoot 3's */S3 folder. (U)
*\S2\S0000020.NSD - The largest .NSD archive found within Crash Bandicoot 3's */S2 folder. (U)
*\S3\S000003B.NSD - The smallest .NSD archive found within Crash Bandicoot 3's */S3 folder. (U)
I own a copy of this game. My E-mail address is accessible from my profile on this forum.
## Post #2
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-02-02T15:13:15+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I'm just going to politely push this up a page...

I was wondering if these archives, or anything similar to these archives, have been inspected before?
Also, is there anything else I can do to contribute? That is, aside from cracking the archive format.
I can't read anything past strings of text right now.
## Post #3
- Username: Kasjan Dubiel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 12, 2011 6:39 am
- Post datetime: 2011-11-11T23:06:39+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hello. I want to make a polish translation to this game. How can i open this NSF files? I must open them and find video files inside. Please help me guys ; )

It is very important for me.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-07T20:44:16+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

The most important thing you should know about NSF files is that each subfile with an NSF file, can only begin at an offset
that is a multiple of 0x10000
And each file can not be bigger then 0x10000 in size.
So the first step will be to cut a file out from 0x0 to 0x10000 -1, then from 0x10000 to 0x20000 -1
ect. Then we can use the headers to give extensions to files, and also trim the null zeros, as a file does not have to use the entire 0x10000 section.

Excellent observations about the named extensions that appear in the .exe file crash.exe these will help me give names to different types of files.

Hex Header 34 12 00 00
Are archives of models or textures which we will spend most of the work, don't know what extension that is but we can figure it out. 

Hex Header 34 12 01 00
Are textures for sure.

Hex Header 34 12 03 00
Are sound archives, though if I recall correctly.

Hex Header 34 12 04 00
Are also sound archives. Maybe one is for music one for sound effects?
## Post #5
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-07-14T00:33:12+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Awesome, a little bit more info and we should be good to start cutting files out then. Thanks for the reply FurryFan.
## Post #6
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-07-21T21:13:20+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I'm working on a utility for working with the NSF files right now.



As far as I've seen, there's no filenames in these things, and all of this stuff seems to be custom formats.
## Post #7
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-07-22T04:56:27+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> As far as I've seen, there's no filenames in these things, and all of this stuff seems to be custom formats.Great stuff. But what of the names listed in the archives such as obj_title, obj_elevator, etc? Surely they would have some attachment to the files.
## Post #8
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-07-22T05:16:04+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from Friedslick6
>
> But what of the names listed in the archives such as obj_title, obj_elevator, etc? Surely they would have some attachment to the files.
Those are just for the game objects placed in the levels, such as boxes, gems, lives, and enemies. They don't really apply to the overall structure of the files. Plus, some objects don't appear to be named (probably the display lists mrbean35000vr refers to).
## Post #9
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-07-22T06:28:39+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> Friedslick6 wrote:But what of the names listed in the archives such as obj_title, obj_elevator, etc? Surely they would have some attachment to the files.Those are just for the game objects placed in the levels, such as boxes, gems, lives, and enemies. They don't really apply to the overall structure of the files. Plus, some objects don't appear to be named (probably the display lists mrbean35000vr refers to).What a shame. Oh well, at least there is a list of names. I would just have to apply them manually. As for formats, I have knowledge that the models were made with PowerAnimator. I can't recall the exact version, but I know that the model must have most likely been a conversion from one of the formats that PowerAnimator exports to. And given the models are vertex animated, it would most likely still be a wavefront object.

EDIT: Andy Gavin wrote an article containing details about the model's production on his blog, linked [here](http://blog.mascherato.com/tag/poweranimator/)
## Post #10
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-07-24T17:03:27+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I've documented most of what I know here: [https://gist.github.com/3170834](https://gist.github.com/3170834)
If any of it is confusing, let me know.
## Post #11
- Username: logan812
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-07-26T16:12:04+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> I'm working on a utility for working with the NSF files right now.
I'm waiting for your utility! It is the gratest news i've ever heard. I want to get to this files since last year. I hope you can make it!

Let us know in this topic when you finish your utility 

EDIT: @ ckeckwob, do you know something about this?
[http://crash2masterquest.blogspot.com/](http://crash2masterquest.blogspot.com/)


Will be "extract STR files" and "Import STR files" options in your utility?
It could be very helpful for me.
## Post #12
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-07-26T17:49:34+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from ikskoks
>
> EDIT: @ ckeckwob, do you know something about this?
http://crash2masterquest.blogspot.com/
Yes. That is what got me interested in modding crash 2.

> Reply from ikskoks
>
> Will be "extract STR files" and "Import STR files" options in your utility?
It could be very helpful for me.
STR files?
## Post #13
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-07-26T18:38:14+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> STR files?

STR files often contains movies in psx games (or music and voices of the characters). I thought the same is with crash bandicoot cutscenes ([http://www.youtube.com/watch?v=nOsTziwPrmU](http://www.youtube.com/watch?v=nOsTziwPrmU)) I have to extract this movies from iso image, add subtitles and import them  to the image. I have good utilities for converting STR to AVI and AVI to STR, but i need for this STR file extracted and decompressed from game.

For example MediEvil has not compressed STR files in main directory of the iso image.

I think STR files are compressed somewhere in NSF/NSD archives and i will be very grateful when i could extract this files by your utility. Can you do that?
## Post #14
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-07-26T18:44:02+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from ikskoks
>
> chekwob wrote:STR files?I think STR files are compressed somewhere in NSF/NSD archives and i will be very grateful when i could extract this files by your utility. Can you do that?The Japanese version of the Crash Bandicoot PSX series use STR video, but it isn't held within the NSF/NSD archives. Are you sure that there are STR files within the other versions?
## Post #15
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-07-26T18:57:27+00:00
- Post Title: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I suppose so, but i'm not sure...

 If i am right, it will be great opportunity to make a good translation for me. I'm good at editing STR files.

EDIT: @ chekwob, are you able to do working extractor/importer?
## Post #16
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-07-26T22:08:11+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from ikskoks
>
> EDIT: @ chekwob, are you able to do working extractor/importer?
Extraction is possible, yes, but there's no filenames.
Importing is a bit more involved. Aside from messing with a few boxes in a hex editor, I haven't actually tried modifying the files yet. Replacing already-existing data might be easily done, but I can't really guarantee that.

Another thing that worries me is this, from the "Crash Bandicoot 2 Game Mod: Master Quest" blog:

> All of Crash 2's NSF files have a checksum on them, and changing any data means the checksum needs recalculating. Chadderz, my younger brother, was the one who cracked the checksum; the program updates it upon saving. The "Rehash a file" button has the same functionality, only you don't have to load the file into the editor if you use that button. It's useful if you've been messing with things in a hex editor and want to quickly get things tested.
I haven't run into any kind of checksum that I'm aware of. Moving boxes around at the start of Snow Go didn't seem to result in any kind of errors when testing in ePSXe. Is the checksum a PAL-specific thing (I have the NTSC-U version)? Is my emulator setup somehow bypassing this checksum?

On a side note, my hex editing of the boxes was done on a raw ".bin" image of the disc. These things have an error detection and correction system. A small alteration like changing a box to a nitro should have been corrected, but it wasn't. Does ePSXe not do error correction? If not, does the actual PSX do it?
## Post #17
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-07-26T23:00:42+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> Is the checksum a PAL-specific thing (I have the NTSC-U version)? Is my emulator setup somehow bypassing this checksum?

On a side note, my hex editing of the boxes was done on a raw ".bin" image of the disc. These things have an error detection and correction system. A small alteration like changing a box to a nitro should have been corrected, but it wasn't. Does ePSXe not do error correction? If not, does the actual PSX do it?

Yes, checksum is a PAL-specifing thing, but i can work on NTSC-u version too. It doesn't matter.
Also libcrypt is specific for PAL games.

From what i know ePSXe has error correction (ECC/EDC). PSX doesn't have that function and games with errors can't launch at all.

EDIT: @ chekwob, i am waiting with pleasure for your great utility
## Post #18
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-11-08T08:47:22+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Here's a compiled version of my program so far (.NET 2.0):

[https://www.dropbox.com/sh/yv93g4wsdde32s3/NuCSJR37Oo](https://www.dropbox.com/sh/yv93g4wsdde32s3/NuCSJR37Oo)

It can open NSF files and extract individual items from it, but nothing more. This isn't really useful for any modding purposes yet; my focus right now is on reverse engineering.

That aside, here's a general overview of the NSF file format: (EDIT: I've updated this list a bit)
The NSF files are containers for "chunks", which are containers for "entries", which are containers for actual strings of data (often one string per entry, but not always). These terms are made up and don't appear anywhere on the actual game disc. There are 5 types of chunks:

 T0 - The most common type. Any entries which don't belong in another chunk type end up in these.
 T3 - Container for T12 entries (sound effects).
 T4 - Container for T14 entries (music instruments).
 T5 - Container for T20 entries (speech).
 T1 - Not actually an entry container. These contain textures and have a completely different format from the other chunk types.
There are 13 types of entries:

 T1 - ???
 T2 - ???
 T3 - ???
 T4 - ???
 T7 - Entities
 T11 - ???
 T12 - Sound effects
 T13 - Music (VH & SEP)
 T14 - Music (VB)
 T15 - ???
 T19 - Demos
 T20 - Speech
 T21 - ???
I've figured out a little bit of the T7 entry format, but it's not enough to do any serious modification. The sound effects and speech are ps1 adpcm format. The music appears to be standard playstation VAB and SEP. I was able to guess the purpose of the T19 entries based on which files they appear in and how many times they do so.
## Post #19
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-11-08T10:28:24+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> Here's a compiled version of my program so far (.NET 2.0):

https://github.com/ughman/CrashEdit/downloads

It can open NSF files and extract individual items from it, but nothing more. This isn't really useful for any modding purposes yet; my focus right now is on reverse engineering.Oh, that's great development! Have you notified MrBean35000vr about your progress yet? He would probably be interested.
## Post #20
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-11-10T22:11:31+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Some more information:

 The crash 1 nsf files seem to have a significantly different format.
 I'm almost certain the T12 entries are VAG files without the header. It is also likely that T14 entries are "VAD" (edit: I meant VAB) files without the header.
 There's actually T17 entries as well. They only appear in crash 3, and only in a few levels.
 T11 entries sometimes have string constants in them, such as "SEWER OR LATER" or "BONUS". My guess is these are related to GOOL, the LISP dialect used in the games.
I've been working on adding a function to extract T12 entries as WAV files, but this sound format is balls, and there's not much available information on it.

> Reply from Friedslick6
>
> Have you notified MrBean35000vr about your progress yet? He would probably be interested.
I have not. I'm not sure what I could even say.
## Post #21
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-11-10T22:29:46+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hmm, I think I'll just post him a comment about this topic then...
## Post #22
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2012-12-01T10:57:47+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Another version available (v0.02):
[https://www.dropbox.com/sh/yv93g4wsdde32s3/NuCSJR37Oo](https://www.dropbox.com/sh/yv93g4wsdde32s3/NuCSJR37Oo)

New features:

 Playing sounds/speech and extracting them as wave files. Only 11025 Hz and 22050 Hz are supported. Some sound effects use neither of these, but most speech does.
 Texture chunks are displayed as 8bpp grayscale and 16bpp BGR555 graphics.
 Entity entries are partially parsed now.
 Various other minor changes.

It's still not extraordinarily useful for modding, but it's progress. Crash 1 archives are still unsupported.

A list of the levels and their associated filenames can be found at [https://sites.google.com/site/crashpsxsite/structure](https://sites.google.com/site/crashpsxsite/structure). The list misses 3A for crash 3, which is the vortexy area where the enemy bosses talk to you. (EDIT: nevermind, it has that now too)
## Post #23
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-01-14T14:47:57+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I don't want this to become an announcement thread for my program, but I feel that some people might be particularly interested in this release.

New download link for v0.04:
[https://www.dropbox.com/sh/yv93g4wsdde32s3/NuCSJR37Oo](https://www.dropbox.com/sh/yv93g4wsdde32s3/NuCSJR37Oo)
(github has [deprecated the downloads page](https://github.com/blog/1302-goodbye-uploads), so I'm using dropbox now)

This version features extracting music in SEQ or MIDI format. I've made a post explaining how to do this [here](http://hpzr.proboards.com/index.cgi?board=tech&action=display&thread=7208#tr_post300696).
## Post #24
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-01-14T18:41:26+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> some people might be particularly interested in this release.

I'm very interested
## Post #25
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-03-15T14:08:44+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I've been creating some new documentation, this time with diagrams and stuff.
[https://dl.dropbox.com/s/fu29g6xn97sa4p ... ormat.html](https://dl.dropbox.com/s/fu29g6xn97sa4pl/crash2fileformat.html)
This is most of what I know, but it is missing a few details. This document also includes details on the common playstation formats SEQ, SEP, VAB, VH, and VB.

Something I noticed a few weeks ago is that I can't actually modify the PAL game files. Loading and saving them works fine, but the PAL game engine rejects any changes. I've spoken with MrBean, and learned that there are indeed checksums in the NSF files. Every 64kb section in the file has a checksum, and if the checksum doesn't match up with the rest of the data, the game rejects the data as invalid. MrBean's master quest blog post said as much, but I had no idea what he was talking about at the time because, as it turns out, the NTSC version of the game engine doesn't care about the checksums. Why it doesn't care is a mystery, but it's thanks to that that I was able to get this far. This puts a stop to modifying the PAL version until I can acquire more details on the checksum.

I've made some progress on modifying the in-game demos that play when you idle at the title screen. There's some weird incremental values in there before each set of inputs, probably some kind of timing information to ensure they don't desync.

MrBean found where the 3d models are inside the files, but nobody really knows the format, so ripping and modifying them is not possible at the moment.

Most of the music-related stuff is well known now. I'm trying to implement exporting DLS files so the extracted MIDIs can be played back and sound (mostly) like they do in-game. Unfortunately, I have no idea what I'm doing with this DLS stuff. I may have to read the entire DLS spec from front to back to figure it out.

On another note, there was a beta version of Crash 2 PAL released recently. I've confirmed that it works with my code, but unfortunately it also has the checksum limitation of the retail PAL version. This checksum thing always seems to be PAL-specific. Even the retail crash 3 ntsc doesn't care about the checksum. Maybe the checksum was something SCEE wanted?

Also, still no progress on Crash 1. My current theory is that Crash 1 NSF files are compressed in some way. I haven't really paid much attention to Crash 1, sorry.
## Post #26
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-03-15T16:03:54+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Good news. I cross my fingers for your work 

> This checksum thing always seems to be PAL-specific.
Yeah, the same situation was in MediEvil PAL. Guys from Russia solved that problem by deleting some files from game image and creating new iso ;p
## Post #27
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-03-22T02:02:05+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I've made two significant breakthroughs since my last post.

The first is the checksum. Someone sent me an email with some very useful information on how the checksum is calculated in the crash games. Thanks to that, I was able to write an implementation in C#, and CrashEdit can now modify the PAL versions.

The second is Crash 1's NSF files. I had previously assumed that Crash 1's NSF files would be left a mystery for a long time due to lack of interest, but today I took a crack at disassembling the Crash 1 EXE. I've made a surprising amount of progress, and I believe I can implement loading of Crash 1 NSF's into CrashEdit soon.

Also, if any of you have a real, non-downloaded copy of Crash 2 PAL, could you please post the md5 hashes of the following files:

S2/S000002D.NSF
S2/S000002E.NSF
S2/S000002F.NSF

Thanks.
## Post #28
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2013-03-27T13:02:59+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

you are doing a great job dude! adding this thread to bookmarks.
## Post #29
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-04-23T20:36:00+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I have identified the models for game objects as entries with type 3. (EDIT: I meant type 2, why do I keep mixing these numbers up) I'm still working on figuring out the format. Most likely, color will be figured out first (as it appears to be fairly simple), then texture mapping, and then eventually the actual vertices of the model. Animation data may or may not be separate from the models themselves, I'm not sure yet but I suspect that it is.
## Post #30
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2013-04-23T23:02:26+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Animation data didn't appear to be separated from the model when I tried forcing a bind pose on Crash Bandicoot's model, but we'll see.
I can't be of much use except in telling you what I already know and haven't posted in this thread already (regardless of redundancy lol.)
The colours are applied through a gouraud shading method.Crash's eyebrows are grey-scale and the assigned polygons are coloured separately.When Crash's back texture was ripped through an emulator using ePSXe with the Next 3D 1.5 Video plugin and through 3D Ripper DX, the textures were stacked in an unusual way:
	Segmented into 32*32 sized tiles, with each top-right tile moved below the top-left tile, and each bottom-left tile moved above the bottom-right tile within each group of 2*2 tiles.
	(Other ripped textures did not share this oddity.)
Good luck to you.
## Post #31
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-04-24T19:23:08+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from Friedslick6
>
> Animation data didn't appear to be separated from the model when I tried forcing a bind pose on Crash Bandicoot's model
What do you mean by "forcing a bind pose"?
## Post #32
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-24T20:26:58+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

make the model into a t-pose
## Post #33
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-06-08T03:56:08+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

So it turns out those file extension-looking things are directly related to the entry types. This is the list I found in Crash 2 NTSC-U and my guesses/knowledge of the contents:

```
SVTX	Object Animation(?), "Shape Vertex"(?)
TGEO	Object Model(?), "Thing Geometry"(?)
WGEO	Scenery Model(?), "World Geometry"(?)
SLST	Precomputed Scenery Occlusion Data(?), "Scenery List"(?)
TPAG	Texture Page
LDAT	Link Data(?)
ZDAT	Level Section (objects, collision)
CPAT*
BINF*
OPAT*
GOOL	Game Code
ADIO	Audio
MIDI	Music
INST	Instruments
VCOL	Vertical Collision(?), Virtual Collision(?)
LINK*
MDAT*
IPAL	Palette(?)
PBAK	Playback (i.e. Demos)
SDIO	Speech Audio
VIDO

(*) Not present in any NSF file

```

It all matches up, but a bunch of these types don't appear in NSF files at all. I'm thinking the game engine uses the same format internally for all kinds of run-time generated data as it does in the NSF files. So just because something doesn't appear in an NSF file doesn't necessarily mean that it isn't used internally.

I haven't made any progress on the models, sorry. Can't seem to figure out how they work.
I made some minor progress with editing level scenery. I can move some vertices around, but only the X and Y coordinates. I can't seem to find the Z coordinates anywhere.
## Post #34
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2013-06-08T05:25:40+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Man, all this time I always thought that .INST might be short for "Instance". "Instrument" makes way more sense.
Anyway, It's good that I managed to have some correct foresight for once lol.
About the Z-coordinates, to quote Andy Gavin's blog:

> Dave and I experimented with pre-calculating the visibility and sort (the Playstation had no z-buffer, and hence no easy way to sort polygons) ahead of time on the SGI workstations the artists used. Although painful and expensive, this worked really well.
I'm guessing that acronym is a misspelling of CGI.
EDIT: Nope, stands for Silicon Graphics International.
## Post #35
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-08-04T15:11:28+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

[](http://i.imgur.com/7ZywdUl.png)

Download Link - CrashEdit v0.09

New version of CrashEdit, v0.09. This will let you mess around with the objects in-game, changing their positions, types, some settings, and a few other things. With the 3d area view thing, you can press D to undock it into a separate window, so you can glance over at it while changing settings in the objects. You can also use the arrow keys and A/Z to reposition the camera's focus point, and click+drag to change the angle and zoom. Just hit find and type "entity entry".

You'll have to rebuild the disc image yourself to test any changes, which can be complicated because of how PSX disc images work (they're Mode 2/Form 1 format, which is unusual). I'll work on making a program to do this later.

EDIT: Made the download link a bit more obvious.
## Post #36
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2013-08-04T15:41:46+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Wonderful development! The GUI's looking good.
Regarding the 3D preview textures, you may want to temporarily use the crate textures I ripped [here](http://www.textures-resource.com/playstation/ps1crash1/sheet/2960/). No credit required, just until proper textures are implemented.
## Post #37
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-08-04T17:36:44+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Something I forgot to point out in my post is that the 3d viewer doesn't quite work right for Crash 3, because the objects in that game are actually 4 times the size of the Crash 2 ones. So while boxes are 400x400x400 in Crash 3, they'll be rendered as 100x100x100 in the viewer because it's based off of Crash 2. This leaves a lot of spacing between objects, and makes adjusting the camera more tedious.

> Reply from Friedslick6
>
>  Wonderful development! The GUI's looking good.
Regarding the 3D preview textures, you may want to temporarily use the crate textures I ripped here. No credit required, just until proper textures are implemented.
I didn't use those initially for copyright reasons, but now that I think about it, I could add support so that if your texture rip image is in the same folder as the exe, it will use those instead. I think that's what I'll do.
## Post #38
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2013-08-04T17:53:48+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> I didn't use those initially for copyright reasons, but now that I think about it, I could add support so that if your texture rip image is in the same folder as the exe, it will use those instead. I think that's what I'll do.But then wouldn't any texture/model data previews will also be excluded for copyright reasons? That sounds like a good work-around...
## Post #39
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-08-04T18:19:18+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from Friedslick6
>
> chekwob wrote:I didn't use those initially for copyright reasons, but now that I think about it, I could add support so that if your texture rip image is in the same folder as the exe, it will use those instead. I think that's what I'll do.But then wouldn't any texture/model data previews will also be excluded for copyright reasons? That sounds like a good work-around...
My intent is for the program to rip the models and textures for the objects at run-time, so even if you found some weird modified NSF file with all kinds of different models, it would show them just like they would appear in-game. This is especially important because (IIRC) different level themes will have entirely different objects for a specific type:subtype pair, eg 4:0 might be a walking robot in the futuristic levels, while it might be a falling platform in the ruin levels (just an example, probably wrong in this case).
## Post #40
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2013-08-04T18:27:35+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Ah, okay thanks for clearing that up.
## Post #41
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-10-10T12:33:45+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I think I should turn everyone's attention to a thread on the HPZR forums:
[http://hpzr.proboards.com/thread/7484/c ... ting-suite](http://hpzr.proboards.com/thread/7484/crash-hacking-utility-editing-suite)

An excerpt from that thread:

> Reply from wurlitzerfox
>
> I'm currently working on a sort of hacking utility/editing suite for Crash 1. It's still at an early development stage so I can't release too many details, but as of right now I'm only able to view object models, level models, and disassemble executable GOOL binary code (GOOL is the scripting language that Andy Gavin/Naughty Dog developed for the Crash series; a majority of the game's function is the result of executing 'GOOL processes' for every conceivable game object, which are managed by the game engine in much the same way an operating system manages its processes, where a sort of inter-process communication/event based system allows objects to communicate with one another).

From the screenshots, you can see that there is a significant level of support for extracting level and object models for Crash 1 (although currently untextured). There's also some kind of GOOL bytecode disassembler shown in the screenshots.

This is easily the most significant work done so far (at least that I know of) on reverse-engineering the game. Although most of it applies directly to Crash 1, a lot of it is still very much applicable to Crash 2 and 3.

Anyway, that aside, there have been some stuff:

Entries actually have names, interestingly enough. I just assumed they were identified in an arbitrary numerical manner, but sure enough the "entry ID's" were specially-encoded strings. Credits to wurlitzerfox (from that thread) for finding this one. These strings can sometimes be pretty human-recognizable, so I don't think they are necessarily computer-generated. Names like "WillC", "FruiC", "BoxsC", and "ScrbC" show up for GOOL entries, for example, and they contain the code for objects identified by the same name.


SVTX is apparently the vertices for the object models. The polygon/texture-mapping data is held elsewhere, in the TGEO entries (or so I've come to understand, I don't know the specifics to this one). Presumably, each SVTX would be one frame or keyframe of animation for a given model, considering that texturing does not change between different frames of a given animation. Again credits to wurlitzerfox, he's the guy who's figuring out all this stuff.

As of commit [ddc78cf](https://github.com/ughman/CrashEdit/commit/ddc78cf9bc716e5e52b0ed00a52c0a244af8535a), CrashEdit supports viewing Crash 1 level scenery (minus the texturing) and exporting to OBJ and COLLADA formats, although blender really doesn't like opening the output models (maybe they're too big or something? I think I should scale them way down). Noesis supports them just fine, though. There's no vertex color support in OBJ, which means all you'll get is vertices and colorless, untextured polygons. It's really unfortunate, because the only format I know of that supports this is COLLADA, and that's a super-complicated (and surprisingly strictly trademarked) mess. I don't think I'm even exporting to it properly, either. Anyway, there's no compiled build for this version of CrashEdit, but I can make one if someone requests.

I've got some part of the Crash 2/3 scenery models down (vertices are good, polygons are not yet understood). Nothing reliable enough so far, though. (EDIT: oh yeah, I found the Z coordinates by the way)

Anyway, that's all I can think of right now. That guy's reverse-engineering progress is amazing. All kinds of great stuff is coming from that.
## Post #42
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-10-10T14:13:38+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Anyway, there's no compiled build for this version of CrashEdit, but I can make one if someone requests.

I request :3

The most interesting feature from that post you linked is audio editor. It would be amazing to record voices in different languages and create a dubbing. Also font and text editing would be appreciated by translators. ^^

I wish good luck and many thanks for you and wurlitzerfox for making impossible possible!
## Post #43
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-10-10T14:58:45+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

[https://www.dropbox.com/sh/yv93g4wsdde3 ... netest.zip](https://www.dropbox.com/sh/yv93g4wsdde32s3/kU68xwnEzQ/CrashEdit-c1scenetest.zip)
This version's a bit modified, adding a "View all C1 scenery" option to open a window displaying the entire level's scenery.
 
You can do a search for "scenery" with the find feature, and hit "find next" to cycle through them. You'll most likely get a lot of errors when opening the NSF files because the program still doesn't fully support crash 1 NSF's yet, but it's enough to read the models and view/extract them. There will also be duplicate scenery entries for the non-beta versions because of the way the editor handles the crash 1 retail version's compression system (or rather, that it doesn't). This is all stuff I'm trying to iron out before I up the version number to v0.10.

Again, NOESIS is the only thing I've found so far that will actually load the output COLLADA file. However, you can open it in NOESIS and then save it back out again from there and then blender will be able to open it. For some reason, Blender doesn't recognize the colors at all. Makes me wonder if Blender even supports vertex colors.

EDIT: I should mention, you can drag with the mouse to zoom/rotate the camera, and the arrow keys and a/z keys to move the camera's focus point.
## Post #44
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2013-10-14T00:52:48+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob
>
> I think I should turn everyone's attention to a thread on the HPZR forums:
http://hpzr.proboards.com/thread/7484/c ... ting-suite

From the screenshots, you can see that there is a significant level of support for extracting level and object models for Crash 1 (although currently untextured). There's also some kind of GOOL bytecode disassembler shown in the screenshots.

This is easily the most significant work done so far (at least that I know of) on reverse-engineering the game. Although most of it applies directly to Crash 1, a lot of it is still very much applicable to Crash 2 and 3.

That's a huge development update! I'm trying to wrap my head around it as I write this. A thanks to you and wurlitzerfox for your continued efforts. 
> Reply from chekwob
>
> As of commit ddc78cf, CrashEdit supports viewing Crash 1 level scenery (minus the texturing) and exporting to OBJ and COLLADA formats, although blender really doesn't like opening the output models (maybe they're too big or something? I think I should scale them way down). Noesis supports them just fine, though. There's no vertex color support in OBJ, which means all you'll get is vertices and colorless, untextured polygons. It's really unfortunate, because the only format I know of that supports this is COLLADA, and that's a super-complicated (and surprisingly strictly trademarked) mess. I don't think I'm even exporting to it properly, either.The most compatible option would be a COLLADA format w/ baked maps and a separately baked alpha map, imo. Compatibility can be dealt with externally though, so it's not a high priority. Ultimately it's just impressive that model conversion is a reality at this point.

Edit: Changed opinion
## Post #45
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2013-10-24T12:13:00+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

v0.10 is out.

 C2/C3 level box count can be changed (it's a property set in obj_willy). You can also make it negative. I'm not sure why you would want to do that, but it works and the game renders the "-" sign properly and everything.
 The entityentry viewer now shows objects in nearby entries, making it easier to identify which part of the level the entry defines.
 You can use Friedslick6's box texture rip (found here) by saving the image into the same folder as CrashEdit and naming it Textures.png.
 C1 scenery entries are viewable in 3d, untextured, and may also be extracted in OBJ or COLLADA format. The COLLADA export function is broken, and you will need to import the model into NOESIS and save it back out to correct this.
 There is now a game version selection window which will prompt you to select a game version when opening an NSF file.
 You can now save Crash 1 retail NSF files, but will discard the "chunk prelude" if you do so. You will also need to zero-out the bytes 0x418 to 0x4AF in the associated NSD file so that the game knows the prelude is absent. This will increase load times for that level. Note that the two beta versions were already supported because they do not use these preludes.
 If you open a Crash 1 NSF file you will receive a warning about VABv6 not being fully supported. This is very minor and can safely be ignored.

Right now I have a bunch of work to do on crash 1 models, both object and scenery, so that might be my next milestone for v0.11. We'll see.
## Post #46
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-10-16T11:07:33+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I've been trying to recreate the music in Crash. I extracted the .mid files and they sound okay, but the hard part is actually placing the soundfont for each song in the midi tracks so you can listen to the song exactly as it sounds in the games.

Each level has its own instrument samples (you can hear and convert them to WAV using PSound). Extracting them and placing them in a DAW such as FL Studio does not yield 100% accurate results.

There's a person on YouTube who has made a pretty damn good [Crash Bandicoot soundfont](http://www.youtube.com/watch?v=tYYKMt3wlG0), but some instruments are missing and, again, the sound is not entirely accurate when applied to a midi, even if you choose the correct sound banks.

In Game Boy Advance games, there's a method of extracting a midi, then a soundfont, and then putting them together, which works great. Now we need to find how PSX's midi sequencer (or, at least, the one in Crash games) works.

EDIT: Will this method work? I cannot try it at the moment. [viewtopic.php?f=29&t=9880](http://forum.xentax.com/viewtopic.php?f=29&t=9880)
## Post #47
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2014-10-19T18:57:04+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

That VGMTrans program seems to work well if you extract the SEQ and VAB with crashedit before-hand instead of letting it automatically find them in the NSF file; it seems to "find" some music that isn't actually music and then crashes when you try to play it.

CrashEdit actually has a "extract linked VAB as DLS" option on music entries, though it is rather broken:

 DLS file is broken in some way and needs to be opened and resaved through awave studio to work
 Volume on the instruments seems to be really loud
 Whatever ADSR envelope something or other is not copied over or something, I seriously have no idea how that stuff works, but as a result some sounds don't fade in or out the way they would in-game
But other than that, the frequencies and ranges for all of the notes should be good. Probably better off using VGMTrans, though.
## Post #48
- Username: Kedde
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 09, 2014 8:14 pm
- Post datetime: 2014-11-09T12:19:23+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hi there!

First of all, such an amazing job on this subject! I have always been a huge fan of the first Crash Bandicoot games and always wondered if it indeed would be possible someday to customize things.

I have a very general wondering though. How do you manage to get the games to work? I mean, my first step was to just try to replace the first level in Crash Bandicoot 2 with (in this example) level 7 - so basically copy/paste and rename. I then packed it to a ISO, but it won't load in ePSXe. I believe there has to made some sort of check for the real image file - and this is clearly not. 
How do you fix this issue? I know I am missing something really simple and logic here...
## Post #49
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2014-11-09T14:16:42+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from Kedde
>
> Hi there!

First of all, such an amazing job on this subject! I have always been a huge fan of the first Crash Bandicoot games and always wondered if it indeed would be possible someday to customize things.

I have a very general wondering though. How do you manage to get the games to work? I mean, my first step was to just try to replace the first level in Crash Bandicoot 2 with (in this example) level 7 - so basically copy/paste and rename. I then packed it to a ISO, but it won't load in ePSXe. I believe there has to made some sort of check for the real image file - and this is clearly not. 
How do you fix this issue? I know I am missing something really simple and logic here...
It was probably a mistake to add .ISO to the file types filter in ePSXe since the emulator doesn't actually support normal ISO's like that. The deal is it really only takes a raw disc image (generally these come with the extension .BIN or .IMG) which is similar to an ISO but also contains CDROM sector header and ECC/EDC data. Another issue is that the headers need to be formatted like a "MODE 2 FORM 1" track (which the playstation uses) which is different from the much more common "MODE 1" that is generally used.

Basically, when you burn an ISO it essentially gets converted into a MODE 1 .BIN as it is burned. Whatever image creator you use will need to be able to create BIN's directly instead of ISO's, and it will also need to be able to use "MODE 2 FORM 1" instead of "MODE 1". It's all really a pain, and I plan to add a feature to CrashEdit that will just turn a folder directly into a BIN ready to play on emulator or burn for console just because it's so complicated.

Other than that, it should mostly work, but you will run into another problem where the level won't actually play. Switching level ID's around like that is sort of involved, a copy of the level ID is present in the NSD file and you'll need to change it in a hex editor (manually, patch NSD doesn't do it yet) for the level to even load. Once that works, there can still be issues depending on which ID's you switched. As an example, if you take Turtle Woods and give it an ID for another level, you might find that the game freezes whenever you touch the mud, just because crash's code will do checks like "is this level ID 1F? well then I need to do (something to prepare things for mud to work properly)", and the new level ID might not fit the same checks. Another more obvious one is if you swap the title screen (3C) with a level, the level starts immediately after the playstation logo (3C is hardcoded to be the first NSF to "run"), but things like pressing triangle to view the fruit/life/box counters or even just opening the pause menu might not work at all, several death animations won't run, maybe crash is immune to certain types of damage, etc.
## Post #50
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2014-11-22T11:25:19+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hey there (I was able to register, yay), I am having some problems with modding Piston it Away, I want to make the player spawn at the end and leave the level at the start, but moving obj_willy does not make him spawn there (everything else can be freely moved). In levels with multiple warp ins (Road to Ruin, Snow Go, Air Crash), moving willy (not obj_willy#2 or sthg, just willy) does move his warping spot too, but when entering from the secret warp (Edit: No it does not.) So where is Crash's main spawning point specified? I thought the NSD but I don't have the guts to see it.

Oh and in Tiny's boss fight in Crash 3, there is an entity called "tiny-tiger" and another one called "tiny-generator". What could this mean? I don't think it's related to the lions.
## Post #51
- Username: Mystie
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 11, 2014 1:38 am
- Post datetime: 2014-11-29T17:56:09+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Every time I try to open an .nsf with this tool, on all three games, it always gives me this error message:

"Unhandled exception has occurred in your application. If you click Continue, the application will ignore this error and attempt to continue. If you click Quit, the application will close immediately."

Why does this happen?
## Post #52
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-01-11T00:27:56+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

You probably have a corrupted version of the game, or maybe it's the region of the file. What is the region of the games you extracted the NSFs from?
## Post #53
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-01-12T22:11:30+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

<The content of this post has been removed by the author.>
## Post #54
- Username: Mystie
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 11, 2014 1:38 am
- Post datetime: 2015-01-14T23:53:17+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from ManDude
>
> You probably have a corrupted version of the game, or maybe it's the region of the file. What is the region of the games you extracted the NSFs from?

I am using the NTSC-U/C versions, and accessing the files straight from the discs.
## Post #55
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2015-01-15T02:06:46+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from Mystie
>
> ManDude wrote:You probably have a corrupted version of the game, or maybe it's the region of the file. What is the region of the games you extracted the NSFs from?

I am using the NTSC-U/C versions, and accessing the files straight from the discs.
Try copying the files off the disc onto your hard drive and then opening the copies. If that doesn't work, I'll need more details on the exception.
## Post #56
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-01-17T02:38:04+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

@Mystie Try deactivating anti-virus and open CrashEdit (then activate anti-virus again, of course), if that doesn't work then daww. 

Anyway, I just decided to take a crack at Crash 1 Prototype's objects n crap, and I actually got further than I thought (in less time than I thought too), it helps that each crate is ~28 bytes in size (which is like, a fifth when compared to Crash 2's). Here's what I got - hopefully this can be helpful to some of you (this is the first bounce box, the nearest one from Crash):

<updated image below>

I STILL haven't found object type/subtype though, and I can't believe it's not some of the first bytes in there (before the ID, though they are probably the ones right before the x-coordinates). I'll probably update this post with info on it minutes after posting it. Hehe.

EDIT: Yup, I was right:



I replaced the 22 06 bytes before the x-coordinates to 00 00 (which happens to be Crash's object). 22 happens to be 34 in hex, and 06 is, well, 6 in hex, and type 34 subtype 6 is also a bounce box (which is the box I used to test) in other Crash games. Now this is progress. Updated first image too. Now I need to see how the ! box works (how does it say which box is triggered in only that space?), problem  is, it will be quite hard finding where the box is.

EDIT 2: I found another thing related to boxes, updated first image again.

EDIT 3: I found more stuff. Here's an updated version of the 1st image:

 (NOTE: This image is for CRATES. Settings marked as yellow, grey and cyan may mean other stuff in other kinds of objects.)

By the way, crates in Crash 1 (at least in the prototype) don't seem to have "states" like they do in the sequels, so to make ghost crates you need to use subtype 13, and the reward value determines what box it turns into. Though, The Lost City has some invisible crates that turn into bounce ones (that don't work properly), so I'll have to take a look at that sooner or later.

EDIT 4: The third and 4th setting (grey and cyan) can also be used to change the potency of arrow boxes.
## Post #57
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-01-28T19:06:52+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Also, there is a slight difference between Crash 1 pickups/crates and Crash 2 pickups/crates, which is their origin point:
For crates, it's their bottom-left-back point (which makes sense).
For pickups, it's their center.
I suppose this is enough Crash 1 support. The Prototype is EXACTLY like the retail versions (I tested all 3, all work the same way) too.
## Post #58
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-01-29T09:27:34+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Was there ever a version of crashEdit released above v0.10 at all or is that still the most recent version?
## Post #59
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2015-01-29T16:20:52+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from lionheartuk
>
> Was there ever a version of crashEdit released above v0.10 at all or is that still the most recent version?
There's this: [http://cheek.us.to/CrashEdit.zip](http://cheek.us.to/CrashEdit.zip)
It's newer, but I never set a version number for it. It was just supposed to be a temporary holdover until the next proper version, but that's ended up taking a long time.
## Post #60
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-02-06T19:32:21+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Anyone having problems going to [http://www.sites.google.com/site/crashpsxsite/structure](http://www.sites.google.com/site/crashpsxsite/structure)? The site seems to be down. Could anyone get me Ruination's ID? I need to restart that level. EDIT: Nevermind, it's 0F (I got it first try lol).
## Post #61
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2015-02-06T19:48:02+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from ManDude
>
> Anyone having problems going to http://www.sites.google.com/site/crashpsxsite/structure? The site seems to be down. Could anyone get me Ruination's ID? I need to restart that level. EDIT: Nevermind, it's 0F (I got it first try lol).
Due to some circumstances, that page is gone now. There is supposedly a new list here: [https://docs.google.com/document/d/1yZX ... i5IOk/edit](https://docs.google.com/document/d/1yZX49fsW7VpN7ODnFbugFIpSGbajqPsFHUqMdti5IOk/edit) (seems to require javascript). I still need to update the link in the readme.
## Post #62
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-02-11T20:46:21+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

That list also includes 02 for Crash 1, nice.

By the way, box count in Crash 1 isn't specified anywhere (at least I didn't find it yet, and no, it's not in Crash's spawning point), so it can be automatic. Need to test it out.
## Post #63
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-02-26T18:52:13+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I'm having a problem trying to change Cortex's (CB2) music in his boss battle (ID is 07 btw). I was successfully able to change the music, but it doesn't play properly in-game: It's slowed down alot, and some instruments can't even be heard. The changed SEQ works correctly, so I would've thought this was a problem with CrashEdit replacing SEQs. Help? This isn't caused by making the music entry be in another chunk either, as this problem was occurring before I added the chunk.

EDIT: It is, I exported the SEQ I replaced with and heard it with Awave Studio and it was broken. Also FL Studio (11) doesn't even recognize notes in there.
## Post #64
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2015-03-06T12:33:15+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from ManDude
>
> I'm having a problem trying to change Cortex's (CB2) music in his boss battle (ID is 07 btw). I was successfully able to change the music, but it doesn't play properly in-game: It's slowed down alot, and some instruments can't even be heard. The changed SEQ works correctly, so I would've thought this was a problem with CrashEdit replacing SEQs. Help? This isn't caused by making the music entry be in another chunk either, as this problem was occurring before I added the chunk.

EDIT: It is, I exported the SEQ I replaced with and heard it with Awave Studio and it was broken. Also FL Studio (11) doesn't even recognize notes in there.

Interesting. Are you sure what you imported was a SEQ and not a SEP? They have mostly the same header, so crashedit and other programs can't even tell the difference between them, and will end up loading it as the wrong format if you specify the wrong one. This is what I experienced when I was first working on the music support, I was unaware that I was exporting SEP instead of SEQ and most of the initial notes would get discarded. If any of the data before it gets back on track contains tempo change or program change events, it'll mess up the rest of the playback.

I'll try messing around with the cortex music.
## Post #65
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-03-06T14:57:52+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I exported the edited SEQ that I imported to CrashEdit and checked it with Awave Studio (10.6 btw) and one of the events was to set tempo to 7 BPM at the start right after an event that sets the tempo to 165 BPM (the correct amount), and the ticks (edit: steps, not ticks) were all messed up (so it has over 16k ticks (edit: I mean steps) instead of 224).

Though, this is not as important now, since I found how to rip the instruments with CrashEdit (too lazy for PSound), the VAGs have really low volume though (this I fix manually).

EDIT: I right-clicked the SEQ and exported it in CrashEdit (it saves as SEQ), plus Awave doesn't recognize SEP so I don't know what's wrong.
## Post #66
- Username: ManDude
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 7:08 pm
- Post datetime: 2015-05-30T16:53:57+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Since there is literally nowhere else to post this on, here is some stuff found by me and others and that hasn't been documented already (most of it is just random facts):

 Game doesn't like if you delete code or models in Crash 2-3. It's fine if you delete anything else. EDIT: I found something in the "new" NSD that fixes this for some code entries, it's a list of 64 entries, which will be called NONE! if they do not correspond to an actual code entry in the file.
 VCOL (T15) stands for Video Collision.
 Using NONE! in load lists can confuse the game, and makes it have short freezes all the time while in that zone.
 Where are Crash 1's box count values?
 Scenery draw lists don't use scenery names to draw polygons, instead they trust the zone entry's index item to tell them which scenery is being drawn. i.e. A zone (10_0Z) tells 1000S to draw polygon X on the second scenery entry in the index (12_0W), can cause glitches if you swap 10_0W with 12_0W for example.
 Using NONE! in index items works perfectly (Edit: If Crash is not in his normal form or Polar), which can be used to make the game not draw something (useful in space levels if you use doors properly).
 Each zone in the index item has 3 (known) switches 32 bytes below it. 0x10 means "objects on", 0x0E means " solid on" and 0x07 means something I don't know yet. These can be combined. Note that "objects on" doesn't mean objects will not be drawn, but will just not run their "events" (if you touch them it crashes).
 Some chunks do not like intruders.
 There should be a list in the NSD that tells the game which chunks to load at startup. At the start, maybe?
 Model, animation and code names are consistent throughout the trilogy, except for Crash.
 What is the .BIN file in S0 in Crash 3 (all versions)? A second executable?
## Post #67
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-07-04T09:37:40+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hello. I haven't checked this thread for some time. I'm interested in replacing audio in speech chunks. I saw that replacing data in speech chunk is allowed in CrashEdit, but only as a raw data, not wav audio files. Is there any possibility to prepare wav file and replace it in game? I also read that chunk maximum size is 64kb, so I wonder how to deal with wav file with size 200kb and how to compress it to be smaller or equal chunk maximum size.

I'm also interested in modifying text in game like NEW GAME, LOAD GAME, EXIT etc. Have anyone tried that before? I can't find any chunk with that kind of data. 

Chekwob, I wish you good luck with your work!
## Post #68
- Username: XenTaxMario1989
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 26, 2017 3:03 am
- Post datetime: 2017-07-25T19:17:35+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hi, I'm new to this site, And where is the .nsf file for Crash 1/3? I tried one of the folders, S1, S2 and S3. But it only gives me the textures and sounds.
## Post #69
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-19T15:01:44+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

When I looked into the .NSF files, they had the audio data! Cool isn't that? You'll need to download the toolkit for Crash Bandicoot Hacking, then use CrashEdit, Select one of the .NSF files, then select any supported game disc for example: Crash Bandicoot 3: Warped.
When you chose a supported game disc, press OK. Search for Audio, then if you press right arrow on a audio chunk, you'll get sounds from one Crash Bandicoot videogame. Example: TNT crate explosion/countdown or "WHOA!" sound.
Hope this helps for CrashEdit!
Edit: Don't forget to press the thank button if I have helped with CrashEdit's audio rips.
Plus, If you have a issue of extracting audio data, send a reply.
Edit 2: When I was ripping models from Crash 1, I saw some of the colored gems from the Options, title sequence and map screen. The NSF file for that is: S0000019.NSF, I'll see if I can rip the Level Completion Screen map another time.
## Post #70
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-20T15:23:19+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

I tried to rip something from this .ISO, "Crash Bandicoot (NTSC-J)" with CrashEdit, and when I checked in this NSF file, S0000019.NSF, I had the results and it was the title screen, map and options, containing the keys and gems too. Note that I ripped the Orange Gem and there was no textures.
I have a problem, unprocessed chunks happened for me when I used S0000019.NSF.
## Post #71
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2021-06-20T15:41:42+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

You can try out this build which is the latest at this time.
[https://builds.crashedit.cbhacks.com/ap ... 412da3.zip](https://builds.crashedit.cbhacks.com/appveyor/build-10192/CrashEdit-10192-647a97b004e7324ac4f648dcfcecc7d3f8412da3.zip)

You should get one warning "NSF: Prelude saving is not yet implemented" and three warnings "Entry: Processed entry deprocesses to different item data". Ignoring these is fine, and there shouldn't be any unprocessed chunks afterwards.
## Post #72
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-20T16:17:01+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from chekwob ↑Sun Jun 20, 2021 11:41 pm at Sun Jun 20, 2021 11:41 pm
>
> 
You can try out this build which is the latest at this time.
https://builds.crashedit.cbhacks.com/ap ... 412da3.zip

You should get one warning "NSF: Prelude saving is not yet implemented" and three warnings "Entry: Processed entry deprocesses to different item data". Ignoring these is fine, and there shouldn't be any unprocessed chunks afterwards.
Thanks! I'll see if that works.
Edit: I saw those colored gems have vertex color. but how? Example here: It's a blue gem.



Crashedit_blue_gem.png (82.3 KiB) Viewed 89 times
## Post #73
- Username: chekwob
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Jul 20, 2012 8:59 pm
- Post datetime: 2021-06-21T00:19:59+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

> Reply from lilyampykidYTXeNTaX ↑Mon Jun 21, 2021 12:17 am at Mon Jun 21, 2021 12:17 am
>
> 
I saw those colored gems have vertex color. but how? Example here: It's a blue gem.
Some crash 1 animations have vertex colors instead of vertex normals (xyz is swapped for rgb). These use a different entry type id. You can tell them apart by the type name used in the listing on the left side.
## Post #74
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T09:44:01+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Thanks man! You're the best! Plus, I've gotten the Purple Gem, Green Gem, Orange Gem, Blue Gem and Yellow Gems on my Crash 1 gamsave on my PSP.
## Post #75
- Username: Nik Pi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 23, 2022 1:14 pm
- Post datetime: 2022-01-23T05:20:35+00:00
- Post Title: Re: Crash Bandicoot 1/2/3 (PSX) - NSF/NSD File Archives

Hello everyone)
This topic has been without new messages for a very long time, but I have a question:
How can I edit textures? It is possible to do this using this program, or it can only export .PNG files? It's just that there are 2 fonts in Crash 1, one can be found by the tile editor:
[https://d.radikal.ru/d33/2201/78/6a1d6bbf16d9.png](https://d.radikal.ru/d33/2201/78/6a1d6bbf16d9.png)
And the second one, I suppose, is compressed:
[https://c.radikal.ru/c04/2201/40/f3f3f1b92235.png](https://c.radikal.ru/c04/2201/40/f3f3f1b92235.png)
How can I edit these textures, and can they be edited in Crash Edit? Thank you in advance
