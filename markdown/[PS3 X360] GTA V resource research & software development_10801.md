## Post #1
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-09-23T07:56:14+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

Old [GTAV research thread](http://forum.xentax.com/viewtopic.php?f=10&t=10719) had been closed, so let's create a new one and continue our work. Working purposes are the same: to develop open for public (and opensource, if possible) projects in order to give everybody ability to explore and edit resources of GTAV console versions.

Different is another thing. Rules for this thread:
 - no piracy/warez (do not publish links to game download and any game archives, do not discuss piracy or illegal game sharing).
 - no encryption keys publishing (do not post keys or key containing files, if you want to use GTAV soft, you need to extract keys from game executable yourself).

News about textures and other things (like modding tutorials) will be soon   .
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T08:12:56+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

LibertyV (RPF7 Editor) /  kornto
Download: [here](https://code.google.com/p/gtav-modding/)

Console Texture Editor /  Dageron
Download: [here](http://dageron.com/?page_id=4973&lang=en)

GXT2 Text Converter /  Ekey (h4x0r)
Download: [here](http://forum.xentax.com/viewtopic.php?f=35&t=10800)

XFT Importer (3DMax) /  Chipicao
Download: Coming Soon.

Zone (DAT) / Train Paths (IPL) Importer (3DMax) /  tank
Download: [here](http://forums.dageron.com/index.php?showtopic=3603&p=13314)
## Post #3
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-09-23T09:45:01+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

And small tool that will help everybody to extract the enctyption keys yourself:
[http://dageron.com/?p=5062&lang=en](http://dageron.com/?p=5062&lang=en)

It creates key.dat and key.txt for both platforms (Xbox360 and PS3). Description and source included. You need unpacked/decrypted console executables (Xbox360: default.xex -> default.exe; PS3: EBOOT.BIN -> EBOOT.ELF) from your game disc.

Ekey
Nice thread header   .
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T09:51:03+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

> Reply from Dageron
>
> http://dageron.com/?p=5062&lang=en

Invalid link for download, missing > h 

> Reply from Dageron
>
> 
Ekey
Nice thread header   .
You are welcome
## Post #5
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-09-23T10:07:01+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

About the Texture Editor: I was busy a bit in last few days (and probably will be in a few next ones), so hadn't implemented yet PS3 support at all. Anyway will continue working on, some news soon. 

Compression *.sys/*.gfx on Xbox360 to *.xtd is half-done, on PS3 compression to *.ctd it is easier beause it uses simple Zlib.
Edition will be possible when Kronto add support for resource replacement in LibertyV and "as is" exporting.

Ekey, fixed.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T10:17:12+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

> Reply from Dageron
>
> Kronto add support for resource replacement in LibertyV and "as is" exporting.
r22 seems supported this.
## Post #7
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-23T10:24:50+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

I didn't add support for replacing resources yet. 
But I will probably add today.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T10:25:55+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

> Reply from kornto
>
> I didn't add support for replacing resources yet. 
But I will probably add today.
ah ok. btw how about xbox > keyxbox.dat, ps3 -> keyps3.dat?
## Post #9
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-23T10:27:19+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

> Reply from Ekey
>
> kornto wrote:I didn't add support for replacing resources yet. 
But I will probably add today.
ah ok. btw how about xbox > keyxbox.dat, ps3 -> keyps3.dat?
It is exactly the thing that I am working on right now
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T10:28:30+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

> Reply from kornto
>
> It is exactly the thing that I am working on right now
Very well
## Post #11
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-09-23T11:08:48+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

The way I suggest:
key_ps3.dat
key_xbox360.dat
Just because implemented that names in the GTAVKeyExtractor.
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-23T17:47:23+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

ok some info about gfx fonts/files.... I have bad news people, i'm able to edit fonts kind of way to add/replace a new chars, but problem is after repack game crashing. So this GFX Scaleform are really messed up totally. My friend trying to fix it but it does not look good. If anyone has any idea how to edit it or create a new GFX file compatible with GTA, please advice, because so far there is no any person or way how to edit it at all
## Post #13
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-09-23T17:51:36+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

sorry.
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T18:19:26+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

> Reply from redman
>
> any idea if we able to slow down the timecycle?
evening at 7pm in a sunny city is a bit strange. maybe sun goes down at 9pm and then longer nights with slower clock.
You see thread name? Don't disscuss mods, creating mods. Modding game files and .ect > [here](http://gtaforums.com/topic/597587-gta-v-files-and-modding)

> Reply from Mr. Mouse
>
> 
If you want to discuss modding GTAV start a new thread where the discussion is legitimate. We should have been faster with this measure, granted.

> Reply from michalss
>
> ok some info about gfx fonts/files.... I have bad news people, i'm able to edit fonts kind of way to add/replace a new chars, but problem is after repack game crashing. So this GFX Scaleform are really messed up totally. My friend trying to fix it but it does not look good. If anyone has any idea how to edit it or create a new GFX file compatible with GTA, please advice, because so far there is no any person or way how to edit it at all
Modified headers changed back to GFX / CFX ?
## Post #15
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-23T18:47:21+00:00
- Post Title: [PS3/ X360] GTA V resource research & software development

Is anyone working on converting the music (specifically the score) to anything that's listenable? Any information or help on this front would be most appreciated. The Tangerine Dream score is really fantastic.
## Post #16
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2013-09-23T19:46:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from AchillesPDX
>
> Is anyone working on converting the music (specifically the score) to anything that's listenable? Any information or help on this front would be most appreciated. The Tangerine Dream score is really fantastic.

You can actually listen directly to the PS3 audio (just rename to .mp3) and use a player that support partial files (like VLC). I've seen that OpenIV has a working audio explorer/extractor, but i'm not sure when (If) is going to be released.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-23T20:08:41+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Yes we know we can play the files. But first the files need to be deinterleaved and splitted up.
## Post #18
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2013-09-23T21:32:19+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

How will we know when things are updated in kornto's program?
## Post #19
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-23T21:37:19+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

LibertyV Update:
Resources can be imported now.
There is a new import files window, that give you the options to choose how to import files.

An important note about importing resources:
You can now choose how to export resources, and the default way is RSC7. (It is easier than working with two files)
But they only way to import them right now is RSC7.
RSC7 is a fake container that I created, I saw it in the binary of gta 5, but it doesn't seems that they use it in files.
The structure is:
4 bytes RSC7
DWORD - version 
DWORD - system flag
DWORD - graphics flag

The 4 lest bits of each flag represent together the byte of the version.
The other bits represents size with this calculation:

```
int size = (int)((((flag >> 17) & 0x7f) + (((flag >> 11) & 0x3f) << 1) + (((flag >> 7) & 0xf) << 2) + (((flag >> 5) & 0x3) << 3) + (((flag >> 4) & 0x1) << 4)) * newBaseSize );
for (int i = 0; i < 4; ++i)
{
            size += (((flag >> (24 + i)) & 1) == 1) ? (newBaseSize >> (1 + i)) : 0;
}
return size;
```

Where base size is 0x2000 in xbox, and 0x1000/0x1580 for system/graphics in ps3.

Maybe I should use another container? for example instead the flags, hold the sizes, and than my program will pad it/do the reverse calculation?
What do you say? In order to import I need the graphics/system parts sizes and the version.
## Post #20
- Username: xI cHOcOLaTe
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 28, 2011 1:45 am
- Post datetime: 2013-09-23T23:50:33+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I was looking into the .xsc files and they seem like they're compiled. I had an hour to myself and mapped some stuff, maybe someone else has a better idea?

```
-----------------
0x00 - 0x03 - Header (0x34274500)
0x04 - Padding (0x50)
0x05 - 0x07 - Size 1
0x08 - Padding (0x50)
0x09 - 0x0B - Size 2
0x0C - 0x0F - Magic? (0xFDF69E36)
0x10 - 0x13 - Size of Script (starting with (byte 0x2D -> byte 0x2E) with 2 nulls
0x14 - 0x17 - Padding (0x00)
0x18 - 0x1B - Size (?)
0x1C - 0x1F - Padding (0x00)
0x20 - 0x23 - Size (?)
0x24 - Padding (0x50)
0x25 - 0x27 - Size (?)
0x28 - 0x2B - Padding (0x00)
0x2C - Padding (0x50)
0x2D - 0x2F - Size (?)
0x30 - 0x33 - Padding (0x00)
0x34 - 0x37 - Padding (0x00)
0x38 - 0x3B - Checksum (probably CRC32)
0x3C-  0x3F - Count (?)
0x40 - Padding (0x50)
0x41 - 0x43 - Offset of string table.
0x44 - Padding (0x50)
0x45 - 0x47 - Offset of data/flags for string table (?)
0x48 - 0x4B - Padding (0x00)
0x4C - 0x4F - Padding (0x00)
0x50 - Start of Script. 
   if 0x50 not start of script
      0x50 - Padding (0x50)
      0x51 - 0x53 - Offset of start of script.

```
## Post #21
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-09-24T00:43:16+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Glad you started another thread.
Is anyone working on a .ctf script right now? Is there any difference between the 2 consoles? I saw that Chipicao had the basic vertex/faces done. A release of that would be great, even in its current state, for finding out what odd named models are.
## Post #22
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-24T05:46:09+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from oG Goddess
>
> How will we know when things are updated in kornto's program?

You have to follow SVN revisions!
## Post #23
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-24T08:48:53+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from oG Goddess
>
> How will we know when things are updated in kornto's program?
[https://code.google.com/p/gtav-modding/source/list](https://code.google.com/p/gtav-modding/source/list)
And if it is a big change, I write a post here.
## Post #24
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-09-24T09:34:19+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

edit: out of date
## Post #25
- Username: XBLToothPik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 23, 2013 1:44 am
- Post datetime: 2013-09-24T11:02:55+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

@Rick

Your right on the native imports, they are only added to the list once if they are called into the script so there isn't duplicate code.  Also one of those pointers takes you to a list of int32's, which I think are the 'local', variables.

EDIT:  An example of the scripting language they used was left in Disc 2 > Common.RPF "main.sc"
## Post #26
- Username: xI cHOcOLaTe
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 28, 2011 1:45 am
- Post datetime: 2013-09-24T12:41:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Rick
>
> xI cHOcOLaTe wrote:I was looking into the .xsc files and they seem like they're compiled. I had an hour to myself and mapped some stuff, maybe someone else has a better idea? edit: cleaned up opcode names, added calln/callf/some others.

Holy shit.
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-24T13:19:59+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Label names > total found 17680

to Rick: Yep used Jankins hash.
[LabelNames_17680.rar](https://xentaxbackup.github.io/file/6637_LabelNames_17680.rar)
## Post #28
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-24T13:33:39+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Natives from IV. I think some are used in V
[IV_natives.rar](https://xentaxbackup.github.io/file/6638_IV_natives.rar)
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-24T15:42:01+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

New labels + 3599

ps: can't edit posts WTF ! 
[LabelNames_21279.rar](https://xentaxbackup.github.io/file/6639_LabelNames_21279.rar)
## Post #30
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-09-25T03:25:37+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

-
## Post #31
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-25T03:59:33+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from 41hc1
>
> Can someone give me the awc file for Grass Roots (alien mission), the song that plays when Michael is killing the aliens with the minigun? I have a converter for the awc files that should work. http://www.mediafire.com/folder/ir717ym ... RAGE_Audio

It's for Red Dead, but I tried it on one awc file for GTA 5, and it did work. The khz might have to be changed for some files though. Credit goes to Apollo for making that converter.

Gah! Spoilers! I gotta be careful in here... Let me see if I can find that track... Is it a scored track?
## Post #32
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-09-25T04:11:00+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from 41hc1
>
> Can someone give me the awc file for Grass Roots (alien mission), the song that plays when Michael is killing the aliens with the minigun? I have a converter for the awc files that should work. http://www.mediafire.com/folder/ir717ym ... RAGE_Audio

Didn't get that to work, but I think this is the file you're talking about: [alien_music.awc](http://www.mediafire.com/?1kuni2l6qjci63u)
## Post #33
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-25T06:05:37+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I just found the problem on repacker RPF files. If you touch the file american.rpf. For example just reimport original en gfx2 files, game freeze just after 1 mission/prolog.... Interesting part is that this is happening only with this container. Anyone know why ?

EDIT : I made last test, and i found out if you only reimport american.rpf to Xbox360a.rpf than it is working OK, but once you touch anyfile in americaan.rpf(even original file reimport) and then import to xbox360a game freez after 1 mission  damn There is something going on with this file. I think because there is so many of them???

EDIT2: i believe all other files will be affected as well, mean rpf's in RPF files!!!
## Post #34
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-25T10:13:47+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from michalss
>
> I just found the problem on repacker RPF files. If you touch the file american.rpf. For example just reimport original en gfx2 files, game freeze just after 1 mission/prolog.... Interesting part is that this is happening only with this container. Anyone know why ?

EDIT : I made last test, and i found out if you only reimport american.rpf to Xbox360a.rpf than it is working OK, but once you touch anyfile in americaan.rpf(even original file reimport) and then import to xbox360a game freez after 1 mission  damn There is something going on with this file. I think because there is so many of them???

EDIT2: i believe all other files will be affected as well, mean rpf's in RPF files!!!
Ok this bug was fixed.
The fixed version is only in the svn right now.
## Post #35
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-25T10:50:44+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Last update added ~800. Checked all scripts, movie subs and .ect. Total labels found > 22106
[Labels_22106.rar](https://xentaxbackup.github.io/file/6644_Labels_22106.rar)
## Post #36
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-25T12:54:15+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

[http://www.mediafire.com/folder/ir717ym ... RAGE_Audio](http://www.mediafire.com/folder/ir717ymgz7f2s/RAGE_Audio)

Seems this doesn't work for GTA 5 as it splits the audio file wrong?

If anyone can please chime in on how to convert the AWC files i would really appreciate it as well as others.
## Post #37
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-25T13:22:05+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from OrangeC
>
> http://www.mediafire.com/folder/ir717ym ... RAGE_Audio

Seems this doesn't work for GTA 5 as it splits the audio file wrong?

If anyone can please chime in on how to convert the AWC files i would really appreciate it as well as others.
I am working on it, will be in LibertyV soon.
## Post #38
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-25T15:37:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Your a hero!!
## Post #39
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-25T15:55:04+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> 
I am working on it, will be in LibertyV soon.

Most excellent. Can't wait!
## Post #40
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-09-25T17:34:47+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

GTA V Console Texture Editor (version 1.2 beta)
In new version:
Full support for GTA V *.xtd-resource edition in all modes, save
More graphical formats supported
Texture import is debugged, fixed some bugs which existed since old version for GTA IV
Please, pay attention, that PS3 version is still not supported. Support for PS3 will be added later. I am still working on it.

Read more: [http://dageron.com/?p=5123&lang=en](http://dageron.com/?p=5123&lang=en)
Tool page, download: [http://dageron.com/?page_id=4973&lang=en](http://dageron.com/?page_id=4973&lang=en)

[](http://dageron.com/wp-content/uploads/2013/09/gtav_texture_editor.jpg)

Modding results:
[http://dageron.com/?p=5092&lang=en](http://dageron.com/?p=5092&lang=en)
[](http://dageron.com/wp-content/uploads/2013/09/gtav_mod_dageron_1.jpg) [](http://dageron.com/wp-content/uploads/2013/09/gtav_mod_dageron_2.jpg) [](http://dageron.com/wp-content/uploads/2013/09/gtav_mod_dageron_3.jpg) [](http://dageron.com/wp-content/uploads/2013/09/gtav_mod_dageron_4.jpg)
Если кто-нибудь не понял, это ирония). Прочитайте русскую версию заметки.

Please, test that tool   .

kornto
Good work!
## Post #41
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2013-09-25T19:43:32+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Grande Dageron, Grande.
Great work
## Post #42
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2013-09-25T21:49:07+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Dageron, Have you ever looked into adding images into a xtd or just creating a new xtd to add files to out straight. If scripts are mastered like they were for IV (and i only mean offline, probably need unsigned code for online) there is the potential to start using custom textures for things like special hud's etc, kind of like what we have here - [http://static.giantbomb.com/uploads/sca ... -56320.jpg](http://static.giantbomb.com/uploads/scale_super/18/187952/2467827-9233204142-56320.jpg)
## Post #43
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-25T23:22:47+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

LibertyV Update:

 Added basic support for awc extraction (Only for PS3 right now)

An important note about it: it doesn't work perfect yet. It has a problem with multi-channel audio: I still didn't get the splitting 100% correct, so there will be little bit "jumps" in the extracted audio. (And it extracts each channel to a separated wav because of that).
I am going to look into it.

Oh, and if someone find for what text the one-at-a-time hash is 0x81F95048 or 0x21E86A3, it would be nice.
## Post #44
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-25T23:47:06+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Thanks korto.
## Post #45
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-25T23:55:36+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> LibertyV Update:

 Added basic support for awc extraction (Only for PS3 right now)

An important note about it: it doesn't work perfect yet. It has a problem with multi-channel audio: I still didn't get the splitting 100% correct, so there will be little bit "jumps" in the extracted audio. (And it extracts each channel to a separated wav because of that).
I am going to look into it.

Oh, and if someone find for what text the one-at-a-time hash is 0x81F95048 or 0x21E86A3, it would be nice.

Awesome! Any chance you could just have it extract to MP3s instead of WAVs since that's what the audio is stored as internally anyway?

Also, doesn't seem to work on anything in the audio_music.rpf - it says failed to load AWC and to let you know
## Post #46
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-26T00:13:42+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from AchillesPDX
>
> kornto wrote:LibertyV Update:

 Added basic support for awc extraction (Only for PS3 right now)

An important note about it: it doesn't work perfect yet. It has a problem with multi-channel audio: I still didn't get the splitting 100% correct, so there will be little bit "jumps" in the extracted audio. (And it extracts each channel to a separated wav because of that).
I am going to look into it.

Oh, and if someone find for what text the one-at-a-time hash is 0x81F95048 or 0x21E86A3, it would be nice.

Awesome! Any chance you could just have it extract to MP3s instead of WAVs since that's what the audio is stored as internally anyway?

Also, doesn't seem to work on anything in the audio_music.rpf - it says failed to load AWC and to let you know
There are two downsides for doing so. 
The first one is that the sample-rate of the mp3 isn't always the real sample-rate, so I need to decode it anyway in some cases.
The second one is that it isn't mp3 on other platforms. 

I think that a better solution would be adding an mp3 encoder and an option to export it as mp3. But it isn't really with high priority right now.

And about the second thing, fixed that
## Post #47
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-26T00:17:32+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> AchillesPDX wrote:kornto wrote:LibertyV Update:

 Added basic support for awc extraction (Only for PS3 right now)

An important note about it: it doesn't work perfect yet. It has a problem with multi-channel audio: I still didn't get the splitting 100% correct, so there will be little bit "jumps" in the extracted audio. (And it extracts each channel to a separated wav because of that).
I am going to look into it.

Oh, and if someone find for what text the one-at-a-time hash is 0x81F95048 or 0x21E86A3, it would be nice.

Awesome! Any chance you could just have it extract to MP3s instead of WAVs since that's what the audio is stored as internally anyway?

Also, doesn't seem to work on anything in the audio_music.rpf - it says failed to load AWC and to let you know 
There are two downsides for doing so. 
The first one is that the sample-rate of the mp3 isn't always the real sample-rate, so I need to decode it anyway in some cases.
The second one is that it isn't mp3 on other platforms. 

I think that a better solution would be adding an mp3 encoder and an option to export it as mp3. But it isn't really with high priority right now.

And about the second thing, fixed that

Keep up the awesome work. I'm just trying to get at the music and commercials in the most un-touched format as possible and I'll eventually be going back to MP3. For the stereo tracks, outputting to WAV is fine because I'll have to recombine them into stereo tracks and then re-encode to MP3 anyway, but for the mono tracks, it'd be nice to have the un-touched MP3s as is so they don't go through a second round of compression.
## Post #48
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-09-26T03:51:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Has any work been done on XMT files? I'd like to contribute but don't want to do something someone has already done 

XMT files as in 'carcols.xmt', 'carmodcols.xmt' and that sort of thing.
## Post #49
- Username: Ekey
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-09-26T10:29:02+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

kornto, thx, but [http://pbrd.co/16LcgoR](http://pbrd.co/16LcgoR)
ps3-files from preload, valid key_ps3.dat
---
GXT2Parser by Ekey
I optimized it and now parses gtx2-file is 10 times faster. =)
Example:
Parsing file global.gxt2 (rus, 1586762 bytes) before optimization: 490 sec
Parsing file global.gxt2 (rus, 1586762 bytes) after optimization: 44 sec
---
[http://rghost.ru/48982824](http://rghost.ru/48982824) - Without display rows in a table: 22 sec =)
[GXT2Parser.7z](https://xentaxbackup.github.io/file/6646_GXT2Parser.7z)
## Post #50
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-26T16:15:31+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I fixed the audio splitting, now it is done correctly.
But there isn't an option to extract it to a multichannel wave yet (The code that does it working, but I need to fix few things first)

and Haoose, did you try it with the latest version? My first release had a bug in it. Anyway, I tried to extract all those files now and it worked.
## Post #51
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-09-26T16:56:09+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

kornto, Still does not work. Maybe because preloading files, but not final game? Tried and r31 and r32...
## Post #52
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-26T17:06:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Haoose
>
> kornto, Still does not work. Maybe because preloading files, but not final game? Tried and r31 and r32...
Can you send me a sample?
## Post #53
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-26T17:10:47+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> I fixed the audio splitting, now it is done correctly.
But there isn't an option to extract it to a multichannel wave yet (The code that does it working, but I need to fix few things first)

and Haoose, did you try it with the latest version? My first release had a bug in it. Anyway, I tried to extract all those files now and it worked.

Kornto: Awesome work. It's getting much closer now. Seems that the samples aren't quite perfectly put together still though. I just ran LibertyV on alc_agent.awc inside of audio_music and you can hear the track skip every so often. One example is at 0:15.624 - you can actually see a small gap in the waveform on all 8 channels at exactly the same place. Maybe some zeros in there that aren't getting properly removed? Let me know if there's any other way I can help.

Oh wow... and alc_pb2_pussyface gets totally screwed up with just a ton of noise on tracks 8 and 12 about halfway through...

Thanks again!
## Post #54
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-09-26T17:56:52+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> Haoose wrote:kornto, Still does not work. Maybe because preloading files, but not final game? Tried and r31 and r32...
Can you send me a sample?
It's working! I apologize for concern. Not working because missing libmad.dll and lzx.dll. Because I built it from source.
Thank you. =)
Add check for dll-files.
## Post #55
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-26T19:37:50+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from AchillesPDX
>
> kornto wrote:I fixed the audio splitting, now it is done correctly.
But there isn't an option to extract it to a multichannel wave yet (The code that does it working, but I need to fix few things first)

and Haoose, did you try it with the latest version? My first release had a bug in it. Anyway, I tried to extract all those files now and it worked.

Kornto: Awesome work. It's getting much closer now. Seems that the samples aren't quite perfectly put together still though. I just ran LibertyV on alc_agent.awc inside of audio_music and you can hear the track skip every so often. One example is at 0:15.624 - you can actually see a small gap in the waveform on all 8 channels at exactly the same place. Maybe some zeros in there that aren't getting properly removed? Let me know if there's any other way I can help.

Oh wow... and alc_pb2_pussyface gets totally screwed up with just a ton of noise on tracks 8 and 12 about halfway through...

Thanks again!
Thanks for reporting! I found what I did wrong and fixed it.


And do you still have that problem with alc_pb2_pussyface? I noticed some noises, but they were during the whole track, so I don't know if it is a low quality sound or my fault, I will test it.
Report if you find more problems 

and Haoose, those libs are included in the project. Maybe you did checkout only for the folder LibertyV. (Or opened only the project and not the whole solution)
And now that you said that I tested it and saw that one of the libs was missing a file in the svn, so I fixed it. Now everything should compile.
## Post #56
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-26T20:03:56+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> 
Thanks for reporting! I found what I did wrong and fixed it.


And do you still have that problem with alc_pb2_pussyface? I noticed some noises, but they were during the whole track, so I don't know if it is a low quality sound or my fault, I will test it.
Report if you find more problems

Still not quite perfect, but you're getting much closer. The random-ass noise is now gone from alc_pb2_pussyface (still can't believe I'm typing that) and the occasional skips with the missing waveform seem to be fixed as well. The only problem now is that each track extracted isn't always exactly the same lenght, which leads me to believe something's still a bit screwy. 

alc_pb2_pussyface as an example - 14 of the extracted tracks are all exactly the same length and 8,004KB, but tracks 11 and 12 are slightly longer at 8,069KB and 8,071KB respectively. 

alc_chop_fred_halen is even worse, with track sizes and lengths all over the place.

These track length variations make it so that the music doesn't line up with itself when you try and mix it back down into a stereo track, but because of the eclectic nature of most of the music it's hard to determine where exactly the extra time is being added or removed. The music also all seems to start in the middle of the track too, but I'm assuming that's because they're all loopable.
## Post #57
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-26T22:00:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from AchillesPDX
>
> 

Still not quite perfect, but you're getting much closer. The random-ass noise is now gone from alc_pb2_pussyface (still can't believe I'm typing that) and the occasional skips with the missing waveform seem to be fixed as well. The only problem now is that each track extracted isn't always exactly the same lenght, which leads me to believe something's still a bit screwy. 

alc_pb2_pussyface as an example - 14 of the extracted tracks are all exactly the same length and 8,004KB, but tracks 11 and 12 are slightly longer at 8,069KB and 8,071KB respectively. 

alc_chop_fred_halen is even worse, with track sizes and lengths all over the place.

These track length variations make it so that the music doesn't line up with itself when you try and mix it back down into a stereo track, but because of the eclectic nature of most of the music it's hard to determine where exactly the extra time is being added or removed. The music also all seems to start in the middle of the track too, but I'm assuming that's because they're all loopable.
Hmmm that is weird. 
Right now I decode the whole mp3 data for each channel. I tried to dump the mp3 for each channel too, but it had the same problem. 
I don't know what am I missing.
It is even more weird when two same stereo channels have different lengths. I can see that most of the time it plays at the same rate, but there are areas that are longer in one channel.
## Post #58
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-26T22:31:14+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I have some MP3 samples taken from the OPENIV torrent, I can pm you some mp3 samples.
## Post #59
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-09-27T00:06:09+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Wow, not only have the OpenIV people gotten all the separate tracks the same length with no hiccups, they've also managed to get them into native stereo MP3s... Anyone have access to this updated OpenIV?
## Post #60
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-27T00:21:13+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from AchillesPDX
>
> Wow, not only have the OpenIV people gotten all the separate tracks the same length with no hiccups, they've also managed to get them into native stereo MP3s... Anyone have access to this updated OpenIV?
It was probably made from the seperated channels, because that is how the game stores it.

Anyway, I think that I should add a support for the xbox before I try to fix that problem. Maybe the decoded audio in the xbox won't have that length problem.

Anyway, that AWC is a hell of a format.
## Post #61
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-27T00:24:38+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Yeah maybe the XMA will be more easier to figure out.
## Post #62
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2013-09-27T13:57:02+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from AchillesPDX
>
> Wow, not only have the OpenIV people gotten all the separate tracks the same length with no hiccups, they've also managed to get them into native stereo MP3s... Anyone have access to this updated OpenIV?
Thats Good-Nts and his .black rage research project. and no thats not a public program, nor will it ever be
## Post #63
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-27T15:44:20+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from zorg93
>
> AchillesPDX wrote:Wow, not only have the OpenIV people gotten all the separate tracks the same length with no hiccups, they've also managed to get them into native stereo MP3s... Anyone have access to this updated OpenIV?
Thats Good-Nts and his .black rage research project. and no thats not a public program, nor will it ever be

And this is very sad, coz why put some effort on something you never share public ?? This is stupid i guess
## Post #64
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-09-27T16:22:23+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

anyone willing to do a repack tutorial? injected a texture with no success. always game crash.
## Post #65
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2013-09-27T16:49:16+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from michalss
>
> zorg93 wrote:AchillesPDX wrote:Wow, not only have the OpenIV people gotten all the separate tracks the same length with no hiccups, they've also managed to get them into native stereo MP3s... Anyone have access to this updated OpenIV?
Thats Good-Nts and his .black rage research project. and no thats not a public program, nor will it ever be

And this is very sad, coz why put some effort on something you never share public ?? This is stupid i guess
Not entirely a wasted effort. he uses the console versions of the game to understand the new engine and file structures so when the pc version comes out he can have alot of features pretty much ready for the pc version. if you look on his site you can read why he doesnt produce tools for console editing
## Post #66
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2013-09-28T00:06:51+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Has anyone worked on the .xmt files in common? I started looking at them and they appear to have the same structure as the Save files (PSIN/PSIG/CHKSM blocks, hashes etc.) which is kind of weird (unless they are some sort of container).
## Post #67
- Username: DarkGiovy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 28, 2013 4:22 am
- Post datetime: 2013-09-29T15:10:30+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

hello, someone is able to change the audio in the game?

Congratulations to all programmers who are working on programs
## Post #68
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-29T20:15:57+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I have some good news and bad news.
The good news is that I added support for extracting audio from the xbox version.
I had to figure out how to decode XNA. So it is just WMA Pro with specific parameters. I use the ffmpeg (with very minor tweaking, the only problem was the fixed header size in XNA) to decode it, and it works now.
The bad news - the problem with the variable length audio is still there.
I am still missing something/doing some stupid mistake/doing something fundamentally wrong.
## Post #69
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-09-29T21:04:17+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Wow your probably the only other person who had figured out the XMA format and decoded it besides Towav and XMAencode. 

Sucks about that problem though. I wonder how the OpenIV people pulled it off.
## Post #70
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2013-09-30T16:04:31+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> I have some good news and bad news.
The good news is that I added support for extracting audio from the xbox version.
I had to figure out how to decode XNA. So it is just WMA Pro with specific parameters. I use the ffmpeg (with very minor tweaking, the only problem was the fixed header size in XNA) to decode it, and it works now.
The bad news - the problem with the variable length audio is still there.
I am still missing something/doing some stupid mistake/doing something fundamentally wrong.

I think the game uses the files in platform://audio/config (dat54.rel) to properly understand/decode the files.
## Post #71
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-30T19:28:55+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Fixed it! Now it works good. (If you find any problem report..)
I found what I missed. I had to skip some bytes in the start of each chunk. Those were from the end of the last chunk, for seeking/syncing purposes.

But, it is still not perfect. I found an audio that ffmpeg failed to decode, so I need to find why.
But with the PS3 it should be perfect now.
## Post #72
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2013-09-30T21:06:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I'm using the latest trunk of LibertyV and extracting audio_misc.rpf/streams/menu_music.awc (from the PS3) results in skips in every file (some have more, some less). Extracting the same files from the 360 is producing skip-free or much less skips overall.

btw 360 files result in 31999Hz sampling rate (versus 32000Hz on PS3) and thus the timing is a bit different: 00:33.105 (32Khz) (PS3) vs 00:33.1177 (31.9Khz) (360) on otherwise exact files.
## Post #73
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-30T21:30:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from peshkohacka
>
> I'm using the latest trunk of LibertyV and extracting audio_misc.rpf/streams/menu_music.awc (from the PS3) results in skips in every file (some have more, some less). Extracting the same files from the 360 is producing skip-free or much less skips overall.

btw 360 files result in 31999Hz sampling rate (versus 32000Hz on PS3) and thus the timing is a bit different: 00:33.105 (32Khz) (PS3) vs 00:33.1177 (31.9Khz) (360) on otherwise exact files.
I didn't notice any skip. I did notice noise in the xbox360 extracted audio which I fixed now.
Can you try it with the already compiled version?  If it still happens can you say at which time?
If it didn't happen I will check what is wrong with the trunk.


And about the sampling rate, that is the sampling rate that the game states and play the sound at.
## Post #74
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2013-09-30T21:40:51+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I probably shouldn't have used the term skip (though the waveform is completely flat), maybe clipping would be a better word for explaining it. With the latest trunk, extracting from PS3/audio_misc.rpf/streams/menu_music.awc results in a few files. menu_music.awc.14735460.wav is the one i've noticed issues (5.940-5.950, 7.920-7.930). You can clearly see it on the waveform.
## Post #75
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-09-30T21:44:52+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from peshkohacka
>
> I probably shouldn't have used the term skip (though the waveform is completely flat), maybe clipping would be a better word for explaining it. With the latest trunk, extracting from PS3/audio_misc.rpf/streams/menu_music.awc results in a few files. menu_music.awc.14735460.wav is the one i've noticed issues (5.940-5.950, 7.920-7.930). You can clearly see it on the waveform in the waveform.
oh ok, I will look into it.
## Post #76
- Username: appan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 01, 2013 8:25 pm
- Post datetime: 2013-10-01T15:54:10+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I was able to download my GTA V Online Save file, it's an unknown format.. probably packed with something

Anyone want to help me figure out? I'm new to this stuff.. Also I got some interesting URLs from the production servers.. like .asmx file you can send POST-request to.
## Post #77
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-10-01T17:36:56+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

general.awc from audio_radio.rpf/radio_06_country cannot be opened. I'm sure that file contains more than one tracks.
## Post #78
- Username: CRACKbomber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2011 8:13 am
- Post datetime: 2013-10-02T00:37:58+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

```
{
int hdr; //0x00 - 0x03
short ptr1; // 0x04 - 0x05
short size1; // 0x06 - 0x07
short ptr2; // 0x08 - 0x09
short ptrptrCodeStart; //0x0A-0x0B
int unk; // 0x0C-0x0F (checksum?)
int scriptSize; // 0x10 - 0x13
int unk2; // 0x14 - 0x17
int sizeUnk1; // 0x18-0x1B
int unk3; // 0x1C-0x1F
int sizeUnk2; //0x20 - 0x24
short ptr3; // 0x24 - 0x27
short offset3; // 0x26 - 0x29
int unk4; // 0x28 - 0x2D
short ptr4; // 0x2C - 0x2F
short offset4; // 0x2E - 0x2F
int unk5; // 0x30 - 0x35
int unk6; // 0x34 - 0x37
int unk7; // 0x38 - 0x3B
int unk8; // 0x3C - 0x41
short ptr5; // 0x40 - 0x41
short namePtr; // 0x42 - 0x43
short ptr6; // 0x44 - 0x45
short ptrptrStringTable; // 0x46 - 0x47
int stringTableSize; // 0x48 - 0x4F
int unk9; // 0x50 - 0x53
}
```
## Post #79
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-10-02T18:01:04+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

kornto: Music extraction seems like it's working great now for PS3. Any chance you could have it write out multiple stereo wav files instead of multiple mono wav files for anything that has more than one track? Would make mixing stuff back together quite a bit easier.
## Post #80
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-10-02T18:03:49+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from peshkohacka
>
> I probably shouldn't have used the term skip (though the waveform is completely flat), maybe clipping would be a better word for explaining it. With the latest trunk, extracting from PS3/audio_misc.rpf/streams/menu_music.awc results in a few files. menu_music.awc.14735460.wav is the one i've noticed issues (5.940-5.950, 7.920-7.930). You can clearly see it on the waveform.

If it means anything, I also see these exact same anomalies in my extraction of the PS3 version using LibertyV-r37
## Post #81
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-10-02T18:58:58+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I second about the mono to stereo muxing. Would make it easier as i dont have hundreds of files to mix.
## Post #82
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2013-10-02T21:52:13+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from OrangeC
>
> I second about the mono to stereo muxing. Would make it easier as i dont have hundreds of files to mix.

I still want the separate tracks saved out as they are now, but they're currently in "mono pairs" for each stereo track. A single stereo wav per track would cut the number of files in half.
## Post #83
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-10-03T04:36:59+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Well if they have the same file name so you know what pairs go together, you could use the Wavewizard to join them together.
## Post #84
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-10-03T19:15:01+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

why didn't I think of wave wizard
## Post #85
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-03T23:08:40+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Fixed the problem with the ps3. I already fixed that problem in the past, but this time it was harder to fix it, because of the changes that were made for the correct decoding.
And I am planning to do multi-channel wav extraction.
## Post #86
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-04T06:29:29+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I would like to see SAVE button implemented instead of dealing with music. Edit RPF in RPF system would be nice
## Post #87
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-05T05:32:23+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

GTA V Console Texture Editor is updated! (version 1.3)



[http://dageron.com/?p=5200&lang=en](http://dageron.com/?p=5200&lang=en)
PS3 support added.

You may open, edit and save PS3 *.ctd in the same way, as *.xtd.
So, that features are available, but there are still some problems.

There are three common problems which I still try to figure out:Unknown DXT formats
PS3 swizzling
Mipmaps

Not supported DXT formats for Xbox360: GPUTEXTUREFORMAT_DXN, GPUTEXTUREFORMAT_8.
Not supported DXT formats for PS3: GPUTEXTUREFORMAT_8_8_8_8 (because of swizzling), GPUTEXTUREFORMAT_8.

So, the PS3 problem is swizzling. I had never worked with it and was rather surprised that 8_8_8_8 is swizzled while DXT1/DXT5 is not. If someone has PS3 swizzling code (it should be something relative to Nvidia), please tell me.

Mipmaps is an old problem since GTA IV tool version (which I had released in 2011) - it is possible to change only "top level". Unfortunally I need to work a lot to figure that problem out, it will cause large changes in program UI and common texture reading method I currently use. I understand that mipmaps is a serious problem and hope to fix it in new release.

Test results and bug reports are welcome. The more you test, the better future version will be   .

Please, test that tool, it will be large help. If you see that Texture Editor was unable to open any *.xtd/*.ctd, then send me that files in PM (or publish path to them). Also it will be very good if you check save function.

All RSC storage modes are supported, but it is better to use LibertyV export in "RSC7" mode.
## Post #88
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-05T05:38:32+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

ps3 swizzle should be morton order
There is an example in noesis in the script for time splitters 2.

```
		data = bytearray()
		for y in range(0, imgHeight):
			for x in range(0, imgWidth):
				idx = noesis.morton2D(y, x)
				if (idx*4+4) > datasize:
					idx = 0
				bs.seek(128 + idx*4, NOESEEK_ABS)
				data += bs.readBytes(4)
		data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "b8g8r8a8")
		texFmt = noesis.NOESISTEX_RGBA32
```
also
[http://fgiesen.wordpress.com/2011/01/17 ... swizzling/](http://fgiesen.wordpress.com/2011/01/17/texture-tiling-and-swizzling/)
## Post #89
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2013-10-06T22:50:18+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I wanted to bring Marston to V since files are in game.When i went to change Trevor's head with Marston's.I had done few Hex Edits to match the head_000_r.cdd since orig file for Marstan was different.Same with texture file it should work.But i repacked the files for the PS3 correctly says currupted have to reinstall. Should work there must be a file that checks the hash. FYI here's how to test the files: part4.rpf / models/ cdimages / steameds_players.rpf But Orig Head files will be in steameds_mp.rpf if someone wants to look into this would be great.
[Compressed_1.rar](https://xentaxbackup.github.io/file/6681_Compressed_1.rar)
## Post #90
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2013-10-06T22:51:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Here's second file wish someone could increase upload size.
[Compressed_2.rar](https://xentaxbackup.github.io/file/6682_Compressed_2.rar)
## Post #91
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-10-06T23:20:05+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

del
## Post #92
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-07T05:11:45+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Dageron
>
> GTA V Console Texture Editor is updated! (version 1.3)



http://dageron.com/?p=5200&lang=en
PS3 support added.

Already tested many textures and also use the in the game as well, they all works ok
## Post #93
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-07T06:42:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Edited:

 Top Secret Post
## Post #94
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-10-08T07:39:45+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

i changed two txd files to look, if i'm able to change the green belt for franklin's dog chop with a brown one (renamed file and over hex uppr_diff_000_b_uni.xtd to uppr_diff_000_e_uni.xtd). messed up the whole game...always crashes at r* video + messed up savegame. any idea why the game is doing this?

with open iv on gta iv i was able to change every cloth modell and with no unencrypted xex.
## Post #95
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-10-08T17:41:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

What about XFT Importer for Max?
## Post #96
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-08T20:36:25+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi, just a quick update on LibertyV.
I don't have a lot of time to work on it, so that is why it doesn't update as frequent as it used to be. (It was during the holidays here so I had free time)

I gave up on the decoding bug in xbox360 right now (some audio files can't be decoded, not sure how many), because xmaencode can't decode those samples also. So right now there isn't much I can do to figure it out. (However, I didn't try it with towav).
Right now I am working on the in-place saving feature. (I am trying to do it efficient and not just rewrite the whole file)
After that I am planning to work on the resources, on a system that will do the parsing/repacking. So it will be easy to write things that deal with them.

And if there is any researcher/programmer that wants to join to the project and help me to develop it, contact me. 
(Even if you don't join, always feel free to send improvements and changes, and they may be applied.)
## Post #97
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-10-08T21:30:35+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Is so far the ps3 audio working correctly?
## Post #98
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-08T21:50:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from OrangeC
>
> Is so far the ps3 audio working correctly?
Yes. Haven't got any other report.
## Post #99
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-10-09T09:04:54+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

@kornto

can't you work with dageron together, so you able to see, extract and import the texture in the container without extracting it aso?


@dageron

you think you able to handle the mip map problem? atm we only able to edit the menu.
would be so sad when not.
## Post #100
- Username: gametalkshow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 11, 2013 10:50 pm
- Post datetime: 2013-10-11T22:06:30+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

hello friends I am making a movie and would like some help, I need the character Trevor (3d Model to 3d max)
tks
## Post #101
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-10-11T22:31:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

A lot of rpf files aren't opening anymore with later versions of LibertyV, at least with PS3 rpf files (don't have a 360). Files like ps3.rpf, part2.rpf, part3.rpf and most of the .rpfs in part0.rpf
## Post #102
- Username: gametalkshow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 11, 2013 10:50 pm
- Post datetime: 2013-10-11T23:16:04+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I followed the tips here the forum and had access to archives. rpf found within many files, but the only ones I found with the file name was trevor with the extension. xvr and. xcd

I would like to know these files are templates? and can be converted to 3d max?

I remember to. xxx can use the EU Viewer, but for. xvr and. xcd not work.

I'm trying to find the model trevor for a short film I'm doing

tks
## Post #103
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-12T08:36:39+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from SonofUgly
>
> A lot of rpf files aren't opening anymore with later versions of LibertyV, at least with PS3 rpf files (don't have a 360). Files like ps3.rpf, part2.rpf, part3.rpf and most of the .rpfs in part0.rpf

It does work for me. How do you define "aren't opening"?
## Post #104
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-10-12T09:00:31+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I can help to solve the mipmap problem if dageron wants.
## Post #105
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-10-12T09:17:55+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

would be fantastic. you should write him a pm!
## Post #106
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-10-12T15:30:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

@Dageron

Few textures can't be opened, because they are compressed by GPUTEXTUREFORMAT_DXN. Can you check it in free time?
## Post #107
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-10-12T19:25:55+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> It does work for me. How do you define "aren't opening"?
Getting an unhandled exception: Unable to read beyond the end of the stream, when I try opening them. Here's the info it gives under details: [pastebin](http://pastebin.com/MyMrqRrv)
Probably just some redistributable I need to update then?

EDIT: Nevermind about that, just noticed the filesizes for those rpf files are completely wrong (part2.rpf, part3.rpf and ps3.rpf are 0Kb...), guess it was my PC crashing when LibertyV was open?
## Post #108
- Username: gametalkshow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 11, 2013 10:50 pm
- Post datetime: 2013-10-13T15:50:41+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I followed the tips here the forum and had access to archives. rpf found within many files, but the only ones I found with the file name was trevor with the extension. xvr and. xcd

I would like to know these files are templates? and can be converted to 3d max?

I remember to. xxx can use the EU Viewer, but for. xvr and. xcd not work.

I'm trying to find the model trevor for a short film I'm doing

tks
## Post #109
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-10-13T21:15:08+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

No, nobody researched that formats.
## Post #110
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-10-14T07:38:51+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from CityPoke912
>
> No, nobody researched that formats.

Should I change my nickname to 'nobody' ?

.xcd - Clip Dictionary - animations, used instead .xad
.xvr - Vehicle Recording - new version of carrec

(sorry, no public info before PC release)
## Post #111
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-10-14T16:34:48+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from listener
>
> 

Should I change my nickname to 'nobody' ?)

Could be  But 3d model formats are still unknown, I saw Max script for importing vehicles, but author disappeared.
## Post #112
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-10-14T21:19:14+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from CityPoke912
>
> Could be  But 3d model formats are still unknown, I saw Max script for importing vehicles, but author disappeared.
Chipicao, he's over at [Kottons Chop Shop](http://kotschopshop.com/topic/5231528/1/). So far he's only got per-car model importers for the Cheetah and Banshee.

> Reply from listener
>
> (sorry, no public info before PC release)
Why's that? Model editing shouldn't have any effect on Online (at least compared to other things we can currently do) and I'd doubt R* would change anything in the PC version if tools were released early, plus others are already working on it.
## Post #113
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-15T05:09:51+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from SonofUgly
>
> CityPoke912 wrote:Could be  But 3d model formats are still unknown, I saw Max script for importing vehicles, but author disappeared.
Chipicao, he's over at Kottons Chop Shop. So far he's only got per-car model importers for the Cheetah and Banshee.
listener wrote:(sorry, no public info before PC release)
Why's that? Model editing shouldn't have any effect on Online (at least compared to other things we can currently do) and I'd doubt R* would change anything in the PC version if tools were released early, plus others are already working on it.

There is simple answer on this, listener does not care about consoles, coz he is working on OpenIV. For me and millions, this is "st....", but it is his personal choice. I have never understood why.... So it is even waste of time try to ask him, i personally dont need this, but i know it from the fact...
## Post #114
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-10-15T05:43:37+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from michalss
>
> There is simple answer on this, listener does not care about console coz he is working on OpenIV. For me and millions, this is "st....", but it is his personal choice. I have never understood why.... So it is even waste of time try to ask him, i personally dont need this, but i know it from the fact...
Oh, didn't know he was part of ClosedIV, wouldn't have have bothered asking if I'd known.
## Post #115
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-10-15T07:16:08+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hey guys!

I know many of you have asked what's the status on the vehicle importing script. And I'm sorry to say it's going to take a while.

The simple truth is I'm very busy with work and personal stuff, and I have little free time.
Starting with next month I hope for the situation to change, and for me to resume researching the format.

Cheers!
## Post #116
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-10-15T07:48:19+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from CityPoke912
>
> Could be  But 3d model formats are still unknown, I saw Max script for importing vehicles, but author disappeared.
Most of 3d formats are very similar to MaxPayne3 and RDR. (Yes, some fields changed, but, if you can read old formats - you can also read a new format with minimal changes). 

If you want only to import models, you can try to process only 'physical' part of a resource - it contains standard Xbox/PS3 index and vertex buffers (and, possible, some textures with normal maps). Also, maybe you need a vertex declaration, but it hasn't changed since IV (also, all RAGE games use small fixed set of vertex declarations (about 10), so you can just brute-force it).
And, last, but not least, in 'virtual' part of a resource, references to buffers placed in standard XDK structures D3DIndexBuffer and D3DVertexBuffer. 

> Reply from SonofUgly
>
> 
listener wrote:(sorry, no public info before PC release)
Why's that? Model editing shouldn't have any effect on Online (at least compared to other things we can currently do) and I'd doubt R* would change anything in the PC version if tools were released early, plus others are already working on it.

Community rule.

> Reply from michalss
>
> 
There is simple answer on this, listener does not care about consoles, coz he is working on OpenIV. For me and millions, this is "st....", but it is his personal choice. I have never understood why.... So it is even waste of time try to ask him, i personally dont need this, but i know it from the fact...

Again, this is community rule. Each of us has his own reasons for this policy. I'll try to explain one of my reasons. 
I need help. I need info on cloth models, ropes, cloth physics, animation blending and another advanced subjects. And I don't see anyone, who can help me. So, I will act as an egoistic elitist, in hope, to someone takes this as a challenge and make some progress beyond viewing textures and exporting small parts of models.
## Post #117
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-15T08:24:54+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from listener
>
> 
Again, this is community rule. Each of us has his own reasons for this policy. I'll try to explain one of my reasons. 
I need help. I need info on cloth models, ropes, cloth physics, animation blending and another advanced subjects. And I don't see anyone, who can help me. So, I will act as an egoistic elitist, in hope, to someone takes this as a challenge and make some progress beyond viewing textures and exporting small parts of models.

Community rule?? What that even means for you ? What community, in here, i doubt about it, i dont want to be rude bird but, for me, you and GooD-NTS are hypocrites, end of story. Sorry for this is off topic but i had to let it out !

Kornto (btw very nice guy  ) did a amazing work for community and he even share source, this is what means something for ppl in here, not just some empty talk.
## Post #118
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-15T09:33:26+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from michalss
>
> [...] for me, you and GooD-NTS are hypocrites, end of storySry?
When reading this:

> Reply from listener
>
> So, I will act as an egoistic elitist,[...]I feel this guy being a very sincere one.  

> Reply from michalss
>
> Kornto (btw very nice guy  ) did a amazing work for community and he even share source, [...]Maybe he is.
The truth is: you can't expect anything. Some people share more some do share less.
But most of them are offering their spare time for no gain.
Maybe you'll think about this?
## Post #119
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-15T09:41:10+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from shakotay2
>
> 
The truth is: you can't expect anything. Some people share more some do share less.
But most of them are offering their spare time for no gain.
Maybe you'll think about this?

Man im not expecting anything from anyone, but what pissing me of is that, gonna use OpenIV example, working on this tool many years and using Console version for research and never realease anything at all and keep saying we never gonna support consoles. Well this is why i call them hypocrites, there is nothing else. They have own reasons, i got it but it does not change my mind, of course.
## Post #120
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-10-16T07:30:01+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

i hope road not ends here because no more updates and without mip maps texture editor is only good for menu screens and hud.
would love to help but i'm no hacker.
## Post #121
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-10-16T11:49:38+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from redman
>
> i hope road not ends here because no more updates and without mip maps texture editor is only good for menu screens and hud.
would love to help but i'm no hacker.

Dageron's working on mipmaps. Be patient.
## Post #122
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-17T09:21:17+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Now GTA V Console Texture Editor has support for PS3 mipmaps, working on Xbox360.
New version is still in development stage.
[http://dageron.com/?p=5432&lang=en](http://dageron.com/?p=5432&lang=en)

[](http://dageron.com/wp-content/uploads/2013/10/gta_mipmaps.jpg)

MipMaps won't be the only new feature in the new version. Friends, be patient waiting for it, please.
Updates for the next GTA V Console Texture Editor (version 1.4) will be serious, but there won’t be much updates after it’s release.

============

I have spent a lot of time for RAGE-games resource research. Soon I will publish some interesting articles on my site, they will clarify much RSC techniques. While my goal is only textures yet, that will help others, who have plans working with models and other RSC data.

Since I haven't got much time working on other resources, my current objective is to make a complete texture builder. I mean, a console application, which will create texture dictionary resource (*.xtd/*.ctd) from input *.dds files. That is completly different level in comparsion with simple texture replacement (which is available in GTA V Console Texture Editor).

Small problem is that GTAIV, MC:LA, RDR and GTA V *.xtd/*.ctd have a bit different structure (and resource container also), so we will need separate builders for each game, or just it will be necessary to define work mode manually.

============

Btw, just ignore "OpenIV developers" and their henchmen. Since they don't support console modding and never help anybody, what are the reasons of helping them and listening what they say? I think that no such. We should just ignore them. Let them work on the PC tools.

I hadn't mentioned previously, but there is yet another (much easier) way to create a simple texture convertor from any PC version of the game: IV/EFLC, MP3, or future GTA V PC version (I mean, *.wtd to *.xtd/*.ctd). That can be useful for easy mod conversion from PC to consoles. And, it possible to do with other resources - convert them from PC, because all memory paging relocation is already done, and RSC flags are calculated.

============

More info will be published on my site.
Stay tuned and follow [the news](http://dageron.com/?cat=145&lang=en).

Sorry for a lot of technical terminology, everything will be explained in articles.
## Post #123
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-17T22:03:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I finally implemented the saving feature (but it rewrite the whole file each time) and made some GUI improvements. 
You can edit a rpf inside a rpf, but just don't forget to save it before you exit.

There are still many GUI improvements that should be done. I try to balance the developing of new core features/improvement of existing features.  But since I am the only one who works on this, and I don't have a lot of time, I prefer to focus on new features.

Now, as I said, the next thing that I am going to work on is resources.
## Post #124
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-18T08:54:10+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> I finally implemented the saving feature (but it rewrite the whole file each time) and made some GUI improvements. 
You can edit a rpf inside a rpf, but just don't forget to save it before you exit.

There are still many GUI improvements that should be done. I try to balance the developing of new core features/improvement of existing features.  But since I am the only one who works on this, and I don't have a lot of time, I prefer to focus on new features.

Now, as I said, the next thing that I am going to work on is resources.

Thank you mate, looks perfect  I guess if you focus to new features it will much better then rewrite the whole core or gui in my opinion
## Post #125
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-20T07:14:15+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I have written an article:
RSC resources in RAGE games - the introduction.
[http://dageron.com/?page_id=5446&lang=en](http://dageron.com/?page_id=5446&lang=en)

It describes the general principles of RSC-resources internal structure and logic.
Information is mainly theoretical, but should help those who tried reverse engineering RAGE-based games in IDA Pro, and tool developers. 

Most info is about GTA IV/MC:LA/MP3 RSC-resources.
There is also some about RDR and GTA V, but I don't know all details.

kornto
Hope that will help understanding some RSC-resource logic, especially about the memory paging. We need to define all bitfields in RSC7 flags.
Next it will be possible to describe some structures (for example, those which had been taken from previous games with minor changes), and make a builder   .
I may describe structures, but need explanation with bitfields.
## Post #126
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-10-20T10:24:45+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

i'm very thankful that you two still on it. spaziwa
## Post #127
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-10-20T13:14:50+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

@Dageron
Looks like, you forgot to add link to the original post:
[http://sannybuilder.com/forums/viewtopi ... 5850#p5850](http://sannybuilder.com/forums/viewtopic.php?pid=5850#p5850)
## Post #128
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-20T15:39:19+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Nope, only parts of info you have published on SB3 forum in 2008/2009 were taken into account. All info we have access to, will be used. If you don't like that any researches from SB3 forum (ie yours) are used in someone else research/developments, then you may delete it (and it would be never used again). 

And I can tell you the reasons why such info collecting have been done: if someone is really interested in spehere, he will have a headache because of necessity of reading about hundreds of pages on forums.gtamodding.ru, sannybuilder.com and gtaforums.com, cathing useful info from pieces (and, сonsidering that the first two ones are Russian-speaking, this attempt will fail). You don't want to document data and give people ability to research something themselves using ready info, but I want.

Now only lazy will be unable to extract AES keys, read RPF archives, uncompress RSC, untile textures, etc.
You know better than me: everything this is 1% in comparison with the whole panorama of RSC-resource structures.

p.s. Btw, I can't understand your (and others from OpenIV) interest for this thread, since .black project and related developments are closed for public (ie useless, let's call a spade a spade). Everything discussed here is guided by a different approach.
## Post #129
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-20T16:54:25+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Thanks for that info!

I just want to fix a little mistake that I made. I saw in the binary a reference to RSC5 ("52 53 43 35") and not RSC7.
If in GTA IV/.. it is 52 53 43 05 and in RDR it is 52 53 43 85, so it is probably only by coincidence a printable "5".
So it is better to call it RSC35. (I will change it in my tool soon). I will also change the endianity of the magic. (Which is wrong right now)

Right now I am working on the system part of the resources. I am working on a library that will be able to parse/rebuild the structures. (So it will be easier to write things that will handle and edit those structures)
And since I switched to git now, I can work on multiple features at once. So soon there will be a branch for resources.
## Post #130
- Username: ThanatosSelisen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 20, 2013 6:20 am
- Post datetime: 2013-10-20T17:33:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

thx for all the work you guys put into all your tools =)

just 2 quick questions.

will there be any chance to be able to open .cdr files in the near future? or is there allready something to view. cant get it to work somehow ^^

is there another location to dl Zone (DAT) / Train Paths (IPL) Importer (3DMax) / tank?

thx in advance =)
## Post #131
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-20T17:54:48+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

ThanatosSelisen
Don't know about others, but I haven't looked on that things yet.
(busy in yet another sphere...)

kornto
Good news!) Hope that flags bitfield documentation won't be hard. 

And, also, just one thing... I think that we have been mistaken a bit when thought about RSC exporter/importer from *.rpf. So, GTA V RSC-resources exported "as is" haven't got header and the decision was to make header ourselves, just write signature and flag values from RPF directory. But (important!) we shouldn't write this header before uncompressed data block, only before compressed. Writing RSC header before uncompressed data is wrong from a conceptual point of view, because flags has special bit which defines is resource compressed or not.

I think that only two modes are be suitable:
RSC 7 (or 5/35): header (signature + flags) + compressed data
*.sys + *.gfx + *.hdr: CPU uncompressed segment + GPU uncompressed segment + header (ie signature and flags) 

Import implementation for both modes won't be hard.
I think there is no necessity of RSC-resource exporting with "broken" header as it is stored in *.rpf, while exporting with normal header is quite useful (but data should be compressed).
## Post #132
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-20T18:04:54+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Dageron
>
> ThanatosSelisen
Don't know about others, but I haven't looked on that things yet.
(busy in yet another sphere...)

kornto
Good news!) Hope that flags bitfield documentation won't be hard. 

And, also, just one thing... I think that we have been mistaken a but when thought about RSC exporter/importer from *.rpf. So, GTA V RSC-resources exported "as is" hasn't got header and the decision was to make header ourselves, just write signature and flag values from RPF directory. But (important!) we shouldn't write this header before uncompressed data block, only before compressed. Writing RSC header before uncompressed data is wrong from a conceptual point of view, because flags has special bit which define is resource compressed or not.

I think that only two modes are be suitable:
RSC 7 (or 5/35): header (signature + flags) + compressed data
*.sys + *.gfx + *.hdr: CPU uncompressed segment + GPU uncompressed segment + header (ie signature and flags) 

Import implementation for both modes won't be hard.
I think there is no necessity of RSC-resource exporting with "broken" header as it is stored in *.rpf, while exporting with normal header is quite useful (but data should be compressed).
I don't think that it is the case here. All the resources are compressed. Some of them are encrypted, and that is decided by the code that request that resource. (At least that is the way that I understood it, but maybe I am wrong). All the bits of the flag are related to size calculation. (If you take a look at the calculation, there are 28 bits are used for system/graphics size, and 8 more bits for the version). I don't think that there are more missed flags.

So you don't really have a way to know if the resource is encrypted or not only from the container. (I decide it by the extension)
## Post #133
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-20T18:16:51+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Well, let it be as in the current LibertyV. If there is no compression bit in flags, there is no the case.
I just thought with the comparsion how it was in previous R* games.
## Post #134
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2013-10-20T21:49:13+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi,

a friend has also been reasearching the files of gta 5 and already did some extracting of some text based files.
You can find some research here [http://gtaforums.com/topic/594021-gta5- ... 1063409020](http://gtaforums.com/topic/594021-gta5-research-thread/#entry1063409020)

He found a file that could possibly be a object placement file , he wrote a small 3ds max importer for it and got this




If anyone is interested you can contact me via pm and i will further contact him.

Kilian.
## Post #135
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-10-21T10:37:54+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Dageron
>
> Nope, only parts of info you have published on SB3 forum in 2008/2009 were taken into account. All info we have access to, will be used. If you don't like that any researches from SB3 forum (ie yours) are used in someone else research/developments, then you may delete it (and it would be never used again).

Let's take it step-by-step.
1) You says: "Since they don't support console modding and never help anybody, what are the reasons of helping them and listening what they say? I think that no such. We should just ignore them. Let them work on the PC tools." 
2) You take my texts (and code), remove all credits, add some bugs and post it as yours
3) You suggest that I should remove my posts

Man, you are really funny clown ...

> Reply from Dageron
>
> 
...
Now only lazy will be unable to extract AES keys, read RPF archives, uncompress RSC, untile textures, etc.
You know better than me: everything this is 1% in comparison with the whole panorama of RSC-resource structures.

I'm doubting in a usefulness of this approach. Ok, everyone can read RPF and view textures. But, who will edit clothes and wrinkles, make blendshapes and pose transitions? A.S.Pushkin ? 

Digging thousands of pages, searching hundreds of books, collecting potentially useful info bit-by-bit - gives a momentum for making steps further.

> Reply from Dageron
>
> p.s. Btw, I can't understand your (and others from OpenIV) interest for this thread, since .black project and related developments are closed for public (ie useless, let's call a spade a spade). Everything discussed here is guided by a different approach.

It's simple: working on the map editor for V is hard, so, sometimes, I need more motivation. Reading this topic, give me a feeling of supremacy enough to move on.
## Post #136
- Username: redman
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-21T10:49:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from listener
>
> 
I'm doubting in a usefulness of this approach. Ok, everyone can read RPF and view textures. But, who will edit clothes and wrinkles, make blendshapes and pose transitions? A.S.Pushkin ? 

Digging thousands of pages, searching hundreds of books, collecting potentially useful info bit-by-bit - gives a momentum for making steps further..

Man certainly not you, at least for consoles, so what is the point to write comments/spams in here? Reconsider that "stupid" idea to release tools for PC only and might someone find your posts useful and helpful, so far, again just an empty talk. Sorry pal i had to say this.. I'm not scare to say how i feel it  Anyway i guess all this spams, even from me, need to stop!
## Post #137
- Username: ThanatosSelisen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 20, 2013 6:20 am
- Post datetime: 2013-10-21T10:51:10+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from listener
>
> 
It's simple: working on the map editor for V is hard, so, sometimes, I need more motivation. Reading this topic, give me a feeling of supremacy enough to move on.

so you wont release anything till pc version is availabel? pc version of GTAV while take quite a while to be published and then you have to port your stuff to pc. well that shouldnt take much time, but if you fail to deliver a console version before dangeron, kronto and the others do, your supremacy will be gone and even your pc version won't get you anywhere then. 1st come 1st serve. dangeron and co will be the heroes of the scene and you will stand in there shadows ^^
## Post #138
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-21T12:27:58+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

listener

> I'm doubting in a usefulness of this approach. Ok, everyone can read RPF and view textures. But, who will edit clothes and wrinkles, make blendshapes and pose transitions? A.S.Pushkin ?Interesting thing: how could it be possible in general, if people were unable to decrypt AES, read RPF, uncompress RSC? Would you provide them necessary information, or should they learn everything themselves? 

Things what you do (and others from OpenIV/.black):
Research game data youself for your own purposes (among them that one: 'weah, look! R* are ingenious inventors!')
Keeping research results in a secret (available only for OpenIV/.black team members).
All info you have even published or talked about on different forums is fragmented and more theoretical, but filled a lot with terms and concepts, which are unknown for 99% of interested people. Fortunately, I understand them.
All around are 'noobs' and 'idiots', who don't understand C++ and PowerPC assembler. Grammar nazi, don't you?
No info about console structures.
You have even found nice way to close all info about PC structures with the invention of "OpenFormats" (everybody who don't know, what it is: this is a special OpenIV module and their own format for RSC conversion in OpenIV, sure only PC). It's like: 'what are the reasons you interested in RSC file structure? Use OpenIV and OpenFormats!'

If I'm wrong on these points, prove that they are wrong. Your 010 template for RDR RSC-resoure text is not good enough evidence. I would be surprised if you publish descriptions of GTA V RSC you have already researched. Looks like you have other plans: if somebody experienced helps you with things you don't have knowledge about, you will anyway use this info only for .black/OpenIV. Not for public documentation.

I prefer different way:
No private tools, only public (open for international community).
All software - open source, if possible due to the code quality.
No matter, is the game PC, or console.
Documentation is not fragmented, but formed into the articles (understandable for experienced users and beginners).

What the different way also exactly is, had written in August: [http://dageron.com/?page_id=4578&lang=en](http://dageron.com/?page_id=4578&lang=en)
And maybe I am not so much experienced in software engineering. But my rule: if it is necessary to understand some hard structure or algorithm (some technique), better try to explain it to others.

> Let's take it step-by-step.
>
> 1) You says: "Since they don't support console modding and never help anybody, what are the reasons of helping them and listening what they say? I think that no such. We should just ignore them. Let them work on the PC tools." 
>
> 2) You take my texts (and code), remove all credits, add some bugs and post it as yours
>
> 3) You suggest that I should remove my posts
>
> 
>
> Man, you are really funny clown ...
Interesting question, who is a clown among us. The thing I actually mean: all info it is possible to have acess to, can be used for new developments, public ones. If you have described RSC-techniques first in 2008, that doesn't mean that nobody will be able to understand it except you and OpenIV/.black team. If you feel unhappy that info you published about the PC version is used in someone else developments for the console games, then it's not my problem. And I have told you, that only parts of info you have published on SB3 forum in 2008/2009 were taken into account, not copied.

So, do you want the reference to SB forum in my article? Well, it would be nice enough giving yet another reference for your words - see cursive [here](http://forums.gtamodding.ru/index.php?showtopic=21&p=13552). I remember the reasons why you hate me. This is not console modding, not GTA, even not things related to gaming and software development. We just have different ideology and picture of the world.
## Post #139
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2013-10-21T14:44:40+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Any news on a .xdr viewer ?
## Post #140
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-10-21T16:54:46+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Dageron
>
> listener
Things what you do (and others from OpenIV/.black):
...
If I'm wrong on these points, prove that they are wrong. Your 010 template for RDR RSC-resoure text is not good enoug evidence. I would be surprised if you publish descriptions of GTA V RSC you have already researched. Looks like you have other plans: if somebody experienced helps you with things you don't have knowledge about, you will anyway use this info only for .black/OpenIV. Not for public documentation.

You are mostly right. 
Almost all data, which I have, are obtained by myself. From scratch. By searching google, reading books and analyzing the code.
For example, first version of an .xtd viewer was made without using XDK. It costs me about 48 hours of searching forums, reading datasheets and experimenting non-stop.  If I can do it, why someone other can't ? Are they banned by google ? Why I can't see "somebody experienced" ?
In the last five years I've seen only two men outside .black group, who can help. And yes, they have complete access to all my data.

> Reply from Dageron
>
> I prefer different way:
...
What the different way also exactly is, had been written in August: http://dageron.com/?page_id=4578&lang=en
And maybe I am not so much experienced in software engineering. But my rule: if it is necessary to understand some hard structure or algorithm (some technique), better try to explain it to others.

OK. Let's see, which way is better. This is an OpenIV progress: [http://www.youtube.com/watch?v=4Vk6KwELEVQ](http://www.youtube.com/watch?v=4Vk6KwELEVQ)
Can you show something beyond a texture replacer ? 

> Reply from Dageron
>
> 
Interesting question, who is a clown among us. The thing I actually mean: all info it is possible to have acess to, can be used for new developments, public ones. If you have described RSC-techniques first in 2008, that doesn't mean that nobody will be able to understand it except you and OpenIV/.black team. If you feel unhappy that info you published about the PC version is used in someone else developments for the console games, then it's not my problem. And I have told you, that only parts of info you have published on SB3 forum in 2008/2009 were taken into account, not copied.

Is copying text word-by-word called "taken into account"? You even don't rewrite it. 
Anyway, usually I don't care. For me, writing texts and code, as natural as breathing. And, if someone too lazy or too dumb to write something by himself, he can use my texts and my code without restrictions (I'm always can write more). However, earlier your says, that I can't do nothing useful. I'm considering this situation as a very funny.

> Reply from Dageron
>
> 
So, do you want the reference to SB forum in my article? Well, it would be nice enough giving yet another reference for your words - see cursive here. I remember the reasons why you hate me. This is not console modding, not GTA, even not things related to gaming and software development. We just have different ideology and picture of the world.

Did you disagree with the cursive text ? Am I wrong ? 
And why should I hate someone? What will I got from it ? 

Complete emotional control is a very useful skill: I feel what I want to feel (And, mostly, I want to feel joy and happiness). And looks like you fighting imaginary foes in the dream world instead of doing something ...

> Reply from ThanatosSelisen
>
> so you wont release anything till pc version is availabel? pc version of GTAV while take quite a while to be published and then you have to port your stuff to pc. well that shouldnt take much time, but if you fail to deliver a console version before dangeron, kronto and the others do, your supremacy will be gone and even your pc version won't get you anywhere then. 1st come 1st serve. dangeron and co will be the heroes of the scene and you will stand in there shadows ^^

Supremacy is an internal feeling. Being a hero - external situation. I don't mind, if someone other will be a hero. I'm afraid, there will be no heroes at all. 
I'm expecting PC release in the next six months. Let's see, what can be done.
## Post #141
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2013-10-21T17:29:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi,

Tank the guy who also idd the text type files i posted earlier is really interested in the xenon frag type .xft for the vehicles.

Now he would like to help ChipiCao to write the max script importer so that he can look at the vehicles.

He knows you don't have so much time to work on it , but he does and would really like to contribute and cowrite the importer.

If you are interested you can contact me so i can contact him to let him know.

Kilian
## Post #142
- Username: listener
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-21T17:43:19+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from listener
>
> 
Supremacy is an internal feeling. Being a hero - external situation. I don't mind, if someone other will be a hero. I'm afraid, there will be no heroes at all. 
I'm expecting PC release in the next six months. Let's see, what can be done.

You know what cut the crap and move on, you not gonna help anyone in here, so just leave it alone and wait for PC version of the game, where you can play god, really sick of it already! Damn im pissed again... If you not gonna help, pls stop spamming
## Post #143
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-21T17:56:01+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Can we leave the childish arguments out of this thread (They aren't going to end), and focus on on the research? Please post only contributing things.
## Post #144
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-10-21T18:58:23+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> Can we leave the childish arguments out of this thread (They aren't going to end), and focus on on the research? Please post only contributing things.

I agree. Back to topic. If you have something to contribute, do so. If not, be silent.
## Post #145
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-21T19:54:01+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Figured out x360 mipmaps:
[viewtopic.php?f=18&t=10857&p=89514#p89514](http://forum.xentax.com/viewtopic.php?f=18&t=10857&p=89514#p89514)

Works fine. 
~ 90% done for GTA V Console Texture Editor 1.4.

Maybe will look at *.xhm/*.chm and other RSC which contain whole "texture dictionary" (in easier words, but with a bit wrong conceptual meaning: *.xtd/*.ctd inside other files, like *.xdr/*.cdr, *.xdd/*.cdd).
## Post #146
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2013-10-21T20:22:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Can someone share which encryption algoritihm is used for .xdr/.cdr files ?

Thanks
## Post #147
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-21T21:00:27+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kilian277
>
> Can someone share which encryption algoritihm is used for .xdr/.cdr files ?

Thanks
They not encrypted
## Post #148
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2013-10-22T07:55:24+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

oh okay,

then they must be compressed.
## Post #149
- Username: Alexander Blade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2011 5:10 am
- Post datetime: 2013-10-22T12:29:21+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

you guyz killed Online as expected
[http://www.gameranx.com/updates/id/1814 ... eta-level/](http://www.gameranx.com/updates/id/18144/article/gta-online-mega-exploit-takes-game-robberies-to-the-meta-level/)
still thinking that you did a right thing allowing to pack rpfs ?
## Post #150
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-22T13:07:26+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Alexander Blade
>
> you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ?
lol this problem also exists from RDR with modified RPF, servers just crashing
## Post #151
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-10-22T16:59:12+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Alexander Blade
>
> you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ?
We just allow rockstar to fix the game before it released on PC  (Or in other words, if we didn't allow it until pc release, it would happen on the pc release anyway)

and kilian277, I don't think that they are compressed, since all the resources are compressed anyway. So it wouldn't make sense to compress it twice.
## Post #152
- Username: Alexander Blade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2011 5:10 am
- Post datetime: 2013-10-22T19:13:06+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

it will happen on pc version anyway  probably the only place where normal online gameplay is still possible is ng console
## Post #153
- Username: ThanatosSelisen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 20, 2013 6:20 am
- Post datetime: 2013-10-22T19:34:29+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Alexander Blade
>
> it will happen on pc version anyway  probably the only place where normal online gameplay is still possible is ng console

R* should have stored the config files online for the online mode like every other online game. sadly they dont learn anything from past failures. with jtag and cfw(or ode devices) it's way to easy to cheat in every single way. before people started to mod the config files they allready had patched boot files for cheating online. and with all the money glitches people have a lot of possibillitys to make infinet money. modding game files is the lazy way. without they would have enough money. it's up to R* to make their games secure against modding game files.
## Post #154
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-22T19:47:31+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from ThanatosSelisen
>
> it's up to R* to make their games secure against modding game files.
They should realize that it is useless
## Post #155
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2013-10-22T22:13:51+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Alexander Blade
>
> you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ?
dont take this the wrong way but scocl was the final nail in the coffin for iv online on console. even though its intentions were good(like this) what it was being used for wasnt good and really harmed online
## Post #156
- Username: Alexander Blade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2011 5:10 am
- Post datetime: 2013-10-23T11:11:24+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from zorg93
>
> Alexander Blade wrote:you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ? 
dont take this the wrong way but scocl was the final nail in the coffin for iv online on console. even though its intentions were good(like this) what it was being used for wasnt good and really harmed online
scocl (first released more than 3 years after the IV) doesn't support x360 sco format among with old native hashes , this was done via script conversion by some other tool , so the thing is that I did not provide direct capabilities of console modding as opposed to the tool from this topic which allowed to cheat in an easiest way by tweaking text files , and it was like few days since the Online launch when cheaters started to appear . I wouldn't be the one writing this if not the statements here that were telling something like we won't ruin Online but doing whatever we are doing .

ThanatosSelisen said that eboot was patched even before and this is true but it's much harder then tweak text based file and the changes applied to make the "feature" in eboot are usually limited by few bytes , but config file tweaking allows to do limitless changes in the data structure because V has a lot of stuff like this in text , and as result for Online the whole game gets desynchronized with disconnecting all clients only because of one with such config . If we will look at x360 then we can see that there are no xex mods for V , it was doomed with the ability to patch config . No offense ppl , just the facts .
## Post #157
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2013-10-23T12:25:35+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from kornto
>
> Alexander Blade wrote:you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ? 
We just allow rockstar to fix the game before it released on PC  (Or in other words, if we didn't allow it until pc release, it would happen on the pc release anyway)

and kilian277, I don't think that they are compressed, since all the resources are compressed anyway. So it wouldn't make sense to compress it twice.

Yeah didn't think about it that they are already compressed in rpf not standalaone , makes sense
## Post #158
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2013-10-23T13:54:36+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Alexander Blade
>
> zorg93 wrote:Alexander Blade wrote:you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ? 
dont take this the wrong way but scocl was the final nail in the coffin for iv online on console. even though its intentions were good(like this) what it was being used for wasnt good and really harmed online
scocl (first released more than 3 years after the IV) doesn't support x360 sco format among with old native hashes , this was done via script conversion by some other tool , so the thing is that I did not provide direct capabilities of console modding as opposed to the tool from this topic which allowed to cheat in an easiest way by tweaking text files , and it was like few days since the Online launch when cheaters started to appear . I wouldn't be the one writing this if not the statements here that were telling something like we won't ruin Online but doing whatever we are doing .

ThanatosSelisen said that eboot was patched even before and this is true but it's much harder then tweak text based file and the changes applied to make the "feature" in eboot are usually limited by few bytes , but config file tweaking allows to do limitless changes in the data structure because V has a lot of stuff like this in text , and as result for Online the whole game gets desynchronized with disconnecting all clients only because of one with such config . If we will look at x360 then we can see that there are no xex mods for V , it was doomed with the ability to patch config . No offense ppl , just the facts .from what it appeared scocl just needed the hashes for the old natives to work, as rockstar kept the format consistent across all 3 platforms.

also there are xex mods for x360 , the only problem is its a lot harder to get those working online, but i have seen for myself xex mods working online you just need to manually patch the xex and remove all R/W checks
## Post #159
- Username: ThanatosSelisen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 20, 2013 6:20 am
- Post datetime: 2013-10-23T20:39:08+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Alexander Blade
>
> zorg93 wrote:Alexander Blade wrote:you guyz killed Online as expected
http://www.gameranx.com/updates/id/1814 ... eta-level/
still thinking that you did a right thing allowing to pack rpfs ? 
dont take this the wrong way but scocl was the final nail in the coffin for iv online on console. even though its intentions were good(like this) what it was being used for wasnt good and really harmed online
scocl (first released more than 3 years after the IV) doesn't support x360 sco format among with old native hashes , this was done via script conversion by some other tool , so the thing is that I did not provide direct capabilities of console modding as opposed to the tool from this topic which allowed to cheat in an easiest way by tweaking text files , and it was like few days since the Online launch when cheaters started to appear . I wouldn't be the one writing this if not the statements here that were telling something like we won't ruin Online but doing whatever we are doing .

ThanatosSelisen said that eboot was patched even before and this is true but it's much harder then tweak text based file and the changes applied to make the "feature" in eboot are usually limited by few bytes , but config file tweaking allows to do limitless changes in the data structure because V has a lot of stuff like this in text , and as result for Online the whole game gets desynchronized with disconnecting all clients only because of one with such config . If we will look at x360 then we can see that there are no xex mods for V , it was doomed with the ability to patch config . No offense ppl , just the facts .

for 360 there are rte(real time editors) available. build like a trainer. ps3 is a bit behind. thats even worse. with modified eboots you have to replace them all the time but with rtes you just have to click and done. config file cheats appeared the last week or so. as i said before all the important stuff had to be stored online for the online part of gta but r* failed there again. i have a modified ps3 but i refuse to go and play online with it. i am following the scene for quite a while and know how easy it is to cheat in ps3 games. sad thing about this is that the developers cant prevent it. and with the ode devices sony cant find cfw users anymore. they can play online use cheats as they want. it sucks. 

can only speak for myself. i like the tools provided here and i love to dig arround files of games and systems. sure those tools gave some jerks the opportunity to cheat online but R* is to blame for that too. not everyone who uses this tools does cheat online. 

thx a lot for making them and sharing guys keep it up =)
## Post #160
- Username: zorg93
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-10-24T05:17:25+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Please PPL stop spamming and leave this topic alone for boys working on the formats! It is everyone personal choice to bring modded GTA online, i personally dont care coz we using it only for localization, that's all.
## Post #161
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-10-27T11:22:24+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

New GTA V Console Texture Editor version (1.3.1) is available:
[http://dageron.com/?p=5533&lang=en](http://dageron.com/?p=5533&lang=en)

This is not 1.4 which has been mentioned earlier, this is an update for 1.3.

New improvements:
Added support for MipMaps (for Xbox360 and PS3), texture replacement is now possible for all ‘levels’
Added support for GPUTEXTUREFORMAT_8 (L8) texture format on Xbox360.
Improved support for MC:LA.
Fixed uncompression errors which caused in past texture 'cropping' while loading (new *.dll is used).

Some screens (taken from MC:LA data, but IV/RDR/MP3/V are supported in the same way):
[](http://dageron.com/wp-content/uploads/2013/10/gtav_texture_editor_1.jpg) [](http://dageron.com/wp-content/uploads/2013/10/gtav_texture_editor_2.jpg) [](http://dageron.com/wp-content/uploads/2013/10/gtav_texture_editor_3.jpg) [](http://dageron.com/wp-content/uploads/2013/10/gtav_texture_editor_4.jpg)
## Post #162
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2013-10-31T05:25:12+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Maybe someone can help.........with Dagerons program

I exported loadingscreen_gtav_logo.dds
opened it in paint
made the file transparent, saved as dxt1 
imported it back
The picture seems to be compressed.

The problem I'm running into is im used to gta4 where i could define if each .dds was gxt5 or gxt1. 

If anyone can help that would be great.
## Post #163
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2013-11-01T19:11:45+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Has anyone looked into to the files of disc 1 or were able to? The file checks seem to extend out to disc 1.
## Post #164
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-11-02T22:09:15+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Nothing very interest.
## Post #165
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-05T16:24:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Finally managed to mod a few textures.

This is s_m_y_cop_01.xtd and s_m_y_cop_01+hi.xtd from componentpeds_s_m_y.rpf from part0.rpf with an inversion of the rgb colors on the dxt1 data.



There is so much to tinker with in this game.

Btw, kornto, I had to comment out 1 line of code to get part0.rpf to re-pack.  I was getting out of memory error. (idk if anyone got this error)

```
        {
            if (progressReport != null)
            {
                //progressReport = new SubProgressReport(progressReport, entries.Sum(entry => entry is FileEntry ? ((FileEntry)entry).Data.GetSize() : 0));
            }
```
## Post #166
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-11-05T19:40:44+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

mhm, do i have to import every mip map?
my game always crashes after replacing a txd (import as file).
## Post #167
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-05T21:54:40+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I replaced all mips in the low res, and high res didn't have mips. Low res have 3 mips in the .xtd I modded.  I just directly modded the data instead of using the texture editor.  Similar to the way it was done in this post.

[viewtopic.php?p=81727#p81727](http://forum.xentax.com/viewtopic.php?p=81727#p81727)

Chances are if you don't replace the mips, you'll see the original texture once the object gets further away from the camera.
Idk if all .xtd import properly, I haven't got an error yet, What .xtd are you trying to inject redman?
## Post #168
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-11-05T22:07:28+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from EcheloCross
>
> 
Btw, koronto, I had to comment out 1 line of code to get part0.rpf to re-pack.  I was getting out of memory error. (idk if anyone got this error)
Code: Select allprivate void WriteData(Stream stream, List<Entry> entries, Dictionary<Entry, Structs.RPF7EntryInfoTemplate> entriesInfo, IProgressReport progressReport = null)
        {
            if (progressReport != null)
            {
                //progressReport = new SubProgressReport(progressReport, entries.Sum(entry => entry is FileEntry ? ((FileEntry)entry).Data.GetSize() : 0));
            }
thanks for reporting. fixed. I am not sure how I missed it and broke it.
## Post #169
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-05T22:22:25+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hey kornto, I am having trouble with part0\levels\gta5\generic\gtxd.rpf.  When I export the entire contents of it, I get this error.

> Offset and length were out of bounds for the array or count is greater than the number of elements from index to the end of the source collection.

It is happening in PartialStream.cs at _stream.Read.  The last file extracted before it errors from the whole gtxd.rpf was ch102seabed+hi.xtd.

```
{
    if ((long)count > _length - _position)
    {
        count = (int)(_length - _position);
    }
    // My try in making it thread safe
    lock (_stream)
    {
        _stream.Seek(_position + _originalPosition, SeekOrigin.Begin);
        _stream.Read(buffer, offset, count);
    }
    _position += count;
    return count;
}

```


Thanks for fixing the part0.rpf repack so quickly.
## Post #170
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-11-06T21:12:49+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from EcheloCross
>
> Hey kornto, I am having trouble with part0\levels\gta5\generic\gtxd.rpf.  When I export the entire contents of it, I get this error.
Offset and length were out of bounds for the array or count is greater than the number of elements from index to the end of the source collection.

It is happening in PartialStream.cs at _stream.Read.  The last file extracted before it errors from the whole gtxd.rpf was ch102seabed+hi.xtd.
Code: Select allpublic override int Read(byte[] buffer, int offset, int count)
{
    if ((long)count > _length - _position)
    {
        count = (int)(_length - _position);
    }
    // My try in making it thread safe
    lock (_stream)
    {
        _stream.Seek(_position + _originalPosition, SeekOrigin.Begin);
        _stream.Read(buffer, offset, count);
    }
    _position += count;
    return count;
}


Thanks for fixing the part0.rpf repack so quickly.
fixed.
## Post #171
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-11-08T19:52:40+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

thank you so much dageron & kornto.
## Post #172
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-11-10T07:00:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

If someone has problems with mipmaps, please, describe them in details. I still don't know what problems exactly are, so need info about all your steps (also better to provide me an original *.xtd/*.ctd and edited one). That would be helpful   .

Last time I spent on Midnight Club: Los Angelos, not GTA V. You may check some info [here](http://dageron.com/?p=5544&lang=en). Returning to V now.
## Post #173
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-11-11T15:47:07+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

do i have to import every mip level manually? when i import a dds with mips only level 1 is imported and the others still the same.
## Post #174
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2013-11-14T10:06:11+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Yes, each level should be imported separately.
## Post #175
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-11-14T11:00:36+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

any chance to improve this or at least import the image as png?
it's hell of a work to resize every image. working on a clothing mod and without mesh script/uvw map it's not so easy to make good textures.


or is there a easier method to resize a dds file automated? like a thumbnail creator.

thank you.
## Post #176
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-14T15:09:33+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from redman
>
> or is there a easier method to resize a dds file automated? like a thumbnail creator.

You may be able to make your dds with DDS Utilities from here: [https://developer.nvidia.com/legacy-texture-tools](https://developer.nvidia.com/legacy-texture-tools)

I haven't tested, but it might be worth a try.
## Post #177
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-14T15:17:56+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from redman
>
> any chance to improve this or at least import the image as png?
it's hell of a work to resize every image. working on a clothing mod and without mesh script/uvw map it's not so easy to make good textures.


or is there a easier method to resize a dds file automated? like a thumbnail creator.

thank you.

I could write DDS parser for you. What does it meas is that from Mipmaps DDS it will create Many DDS files as many you have maps in original DDS with or without DDS header   Not sure if i would be able to do it for all of compressions but im sure im able to do it for DXT1,5,3,RGA..
## Post #178
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2013-11-14T15:21:41+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Had anyone used paint.net to replace xtd files?  I tried this and  the images in the loading screens turned white. When I did try replacing an image in daegerons program it made the image smaller and disoriented. I daved it as a gxt1. Any help will be great.
## Post #179
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-11-16T10:59:48+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Any news about LibertyV & other tools?
## Post #180
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-11-19T04:37:58+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Anyone tried editing the in-game websites yet? Copying and renaming files will create a new site, and the images in the .ctd/.xtd are easy enough to edit with Dageron's texture editor:
[](http://i.imgur.com/3JnIMRo.png) 
But what about the .gfx files? It says <xmp:CreatorTool>Adobe Flash CS4 Professional, but flash wont open them. Editing the files manually in notepad++ results in an error:
I figured editing a website would be an easier way of getting any vehicle in the game than making a trainer  

Edit: Nevermind, they're just scaleform files, using something like JPEXS FFD does the job. [More info](http://gtaforums.com/topic/654359-doc-gta-v-in-game-websites/).
## Post #181
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-11-20T22:10:14+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Texturs from Beach Bum DLC have different format? I can't open them by Dageron's tool.
## Post #182
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2013-11-26T02:30:53+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Seems so, here's a screenshot of the error. Here are some [sample textures](http://www.mediafire.com/download/7wynn7uvx5859ja/GTA%2520V%2520Beach%2520Bum%2520DLC%2520Texture%2520Samples.rar). Also get an error when trying to resize the window.
[](http://imgur.com/vYjZkPQ)

Also the carcols file in the DLC is a readable .meta, not a .xmt/.cmt. May be useful for making a .xmt/.cmt reader? [Files](http://www.mediafire.com/download/zfcom3d5d3l8541/carcols.rar).

And lastly, files in update.rpf should overwrite files in the dlc pack, so if you want to edit/add something in the dlc, you don't need to mess around with the dlc files. Makes editing the handling for everything a lot easier.
## Post #183
- Username: kornto
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jun 24, 2007 4:53 am
- Post datetime: 2013-12-09T23:45:42+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Ok, so I finally started to work on the resources. I didn't do exactly what I planned at first.
As first step I added a resource viewer for .xtd/.ctd. (With many missing fields right now).
[](http://imgur.com/QJXiJqK)
This is just the first step towards working with resources.
So right now I want to describe as many structures and fields of the resources in the program, and I will be happy if other people will be able to help me with that.
My next target with resources is viewing/extracting 3D models. But first that I need to understand the related structures and add them to my program.
For those who are interested, the changes are available in the resources branch in the git.
## Post #184
- Username: CityPoke912
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Sep 19, 2010 3:20 am
- Post datetime: 2013-12-13T20:18:45+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

@up

Ask tgascoigne, he made a .xdr exporter, but without loading textures, you can ask him for a help.
[http://gtaforums.com/topic/656269-game- ... 1064238416](http://gtaforums.com/topic/656269-game-file-mystery-hunt/page-19#entry1064238416)
## Post #185
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-12-13T21:17:45+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

There is also C++ source to it : [https://github.com/tgascoigne/xdr2obj](https://github.com/tgascoigne/xdr2obj)
## Post #186
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2013-12-18T22:29:21+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

We need a working model importer with cords and such but we need a batch texture exporter.Also we need a max script to have those models with cords.
## Post #187
- Username: kilian277
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 13, 2012 9:45 pm
- Post datetime: 2014-01-01T20:59:53+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi folks !

I've made a small tool that exports r* .xmap files into .txt files with modelnames + coords + rotations.

I'm sure someone can use it !

If you need it pm me.
## Post #188
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-01-04T10:21:06+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi people of XeNTax...Im new to this site...but i have one problem with texture editing ps3 , i have been using the awesome libertyV RPF7 Editor by kornto  to extract .rpf files successfully and edit them.
One in particular i have edited is Franklin's face & Tshirts - part4.rpf / streamedpeds_players.rpf / player_one / uppr_diff_004_a_uni.ctd & head_diff_000_a_bla.ctd.
ive Opened them with Dageron's Awesome GTA V Console Texture Editor 1.3.1 with success. I then drag the dds files uppr_diff_004_a_uni.dds etc...to Photoshop which has a 
 NVIDIA Plug-in for Adobe Photoshop to allow for .dds files viewing  editing saving.  I then repack and save with LibertyV-r25 to player_one / streamedpeds_players.rpf / part4.rpf.  then 
Replace original part4.rpf in my actual gta 5 game folder USRDIR. My modded texture i edited "Franklins Tshirts & Franlins Face with Tattoos" are successful but only up close...when camera gets further away
from object (Franklin) it disappears and original texture comes in to play...Thats my only problem...Any advice or suggestions? heres some example images [img][[IMG]http://i1334.photobucket.com/albums/w64 ... 105911.jpg[/img]](http://s1334.photobucket.com/user/risatisone/media/20140105_003317_zps22105911.jpg.html)[/img]

And a Youtube Video sample of what i mean [http://youtu.be/Hx-4gSb-QVM](http://youtu.be/Hx-4gSb-QVM)
## Post #189
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-01-04T12:50:07+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from perese1
>
> it disappears and original texture comes in to play...Thats my only problem...Any advice or suggestions? heres some example images
no mip-maps of texture was replaced, use only lastest Dageron tools and read instruction, please
## Post #190
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2014-01-04T18:49:47+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from perese1
>
> Hi people of XeNTax...Im new to this site...but i have one problem with texture editing ps3 , i have been using the awesome libertyV RPF7 Editor by kornto  to extract .rpf files successfully and edit them.
One in particular i have edited is Franklin's face & Tshirts - part4.rpf / streamedpeds_players.rpf / player_one / uppr_diff_004_a_uni.ctd & head_diff_000_a_bla.ctd.
ive Opened them with Dageron's Awesome GTA V Console Texture Editor 1.3.1 with success. I then drag the dds files uppr_diff_004_a_uni.dds etc...to Photoshop which has a 
 NVIDIA Plug-in for Adobe Photoshop to allow for .dds files viewing  editing saving.  I then repack and save with LibertyV-r25 to player_one / streamedpeds_players.rpf / part4.rpf.  then 
Replace original part4.rpf in my actual gta 5 game folder USRDIR. My modded texture i edited "Franklins Tshirts & Franlins Face with Tattoos" are successful but only up close...when camera gets further away
from object (Franklin) it disappears and original texture comes in to play...Thats my only problem...Any advice or suggestions? heres some example images [img][IMG]http://i1334.photobucket.com/albums/w64 ... 105911.jpg[/img][/img]

And a Youtube Video sample of what i mean http://youtu.be/Hx-4gSb-QVM
You sure there isnt a very high detail copy of franklin and a lower detail of his face, still i didnt think it would change that close
## Post #191
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-01-08T08:08:47+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Thank you so much Dageron & kornto...This is my texture for franklins Hat and Stomach & arms tattoos    [](http://www.directupload.net)
## Post #192
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2014-01-09T13:48:48+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from SILENTpavel
>
> perese1 wrote:it disappears and original texture comes in to play...Thats my only problem...Any advice or suggestions? heres some example images
no mip-maps of texture was replaced, use only lastest Dageron tools and read instruction, please
in the vehicles.meta there is something that relates to this

```
      <lodDistances content="float_array">10
 25
 60
 500
</lodDistances>
```

that suggest that there are 5 different textures depending on how far away you are form the vehicle
## Post #193
- Username: ninjaneo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 29, 2013 6:49 am
- Post datetime: 2014-01-12T10:55:36+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from xI cHOcOLaTe
>
> I was looking into the .xsc files and they seem like they're compiled. I had an hour to myself and mapped some stuff, maybe someone else has a better idea?
Code: Select allXSC.sys file format
0x38 - 0x3B - Checksum (probably CRC32)

hey how were you able to spot this in particular?
## Post #194
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2014-01-12T14:22:01+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

PS3 AWC Decoder for Grand Theft Auto V

This small tool allows you to convert GTAV AWC files to mp3 or wav audio. (works only with PS3 version of GTAV.)


Features:

Open single file or process selected folder;
Export audio to MP3, WAV or Multichannel WAV (only in streams);
Support command line arguments, can be used by other tool or in scritps;

Command line arguments: 

```

	/FILE		Process single file.
	/FOLDER		Process folder with sub folders.
	input		Specifies the file or folder to be processed.
	/MP3		Export audio channels as separated MP3 files.
	/WAV		Export audio channels as separated WAV files. Converted from MP3, will take more time.
	/STERIO_WAV		Export audio channels as Multichannel WAV (only in streams) files. Converted from MP3, will take more time.
	destination		Specifies the output directory.

Examples:

	GTAV_PS3_AWCDecoder.exe /FILE "C:\DATA_V\cargobob.awc" /MP3 "C:\DATA_V\out\"
	GTAV_PS3_AWCDecoder.exe /FOLDER "C:\DATA_V\AUDIO\" /MP3 "C:\DATA_V\out\"


```

 
Donwload: [http://bit.ly/GTAVPS3AWC](http://bit.ly/GTAVPS3AWC)
## Post #195
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-01-29T07:48:16+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi guys...im trying to figure out what a GPUTEXTUREFORMAT_DXT4_5 is and if it is able to be retextured using photoshop cs5. the file i got is a dds file
but when using photoshop it has greenish look and a ALPHA1 in the channels on Photoshop  eg with pictures

PLease help me out..realy noobish when it comes to dxt4_5 stuff...Ive successfully edited the DXT1 really well also am i able to save once ive successfully edited the DXT4_5 dds file? really would like to edit these please help
[](http://www.directupload.net) [](http://www.directupload.net)
## Post #196
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-01-30T01:34:48+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from perese1
>
> 

for fix this in photoshop make this:

Move the color channels in this order for fix the diffuse textures with disordered channels

Red to Blue
Green to Red
Alpha to Green
## Post #197
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-01-30T07:12:22+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

thanks for replying...Im not too sure how to move color channels blue green etc in photoshop...it wont let me...could you please help by showing me how its done...wont let me move/swap color channels around.  also if successful with editing the dxt4_5 dds file...will i be able to save it under dxt4_5?  thank you for helping me...appreciated heaps
## Post #198
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-01-31T07:52:08+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

go to channels in photoshop and click over the channel that you want to move (for example red) then press CTRL+C, now with your already copied channel  make click over the  destination channel (for example blue) and press CTRL+V, now repeat the process with the other channels

isn't difficult
## Post #199
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-02-01T13:42:44+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I hear you and ive done exactly that...It does not allow for it to overwrite or Replace...i think it just might be locked....If i upload the file i would like modded with new textures...do you think you could unlock it for me so it can become editable?  you might have better luck then me...only if you not busy..allgood if you cant though...I appreciate your help allready...thanks man
## Post #200
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-02-01T20:42:34+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from perese1
>
> I hear you and ive done exactly that...It does not allow for it to overwrite or Replace...i think it just might be locked....If i upload the file i would like modded with new textures...do you think you could unlock it for me so it can become editable?  you might have better luck then me...only if you not busy..allgood if you cant though...I appreciate your help allready...thanks man

ok , no problem
## Post #201
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-02-01T23:08:02+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

thank you so much man...im really hoping you could be able to make it editable...but also savable under GPUTEXTUREFORMAT_DXT4_5?  i HOPE U KNOW WHAT I MEAN LOL  heres the dds alpha files...thanks man [http://rg.to/file/25006aff9ff91447af3c0 ... s.rar.html](http://rg.to/file/25006aff9ff91447af3c059f5b47eb60/Alpha_DDS_files.rar.html)   or   [https://mega.co.nz/#!iQYxXQqA!UTlv9OOeG ... Dp3OCZ2qXY](https://mega.co.nz/#!iQYxXQqA!UTlv9OOeGF1CEYkm17EK9Xzz0Ab-CKoQpDp3OCZ2qXY)    Let me know how you go
## Post #202
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-02-02T08:25:28+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

all DDS texture are already editable :/ , I don't know what is the problem with your photoshop

[http://www.mediafire.com/download/c24ox ... _a_bla.dds](http://www.mediafire.com/download/c24oxonnw5bgejl/head_diff_000_a_bla.dds)

and about murals , I think that are correct  (the black section are the black graffitis that only work in alpha because are decals)
## Post #203
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-02-02T12:56:37+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

luxox18 - you are awesome - what you did with the dds file texture head_diff_000_a_bla. You opened the texture up for me to see the real texture of the mans face  eg --> [](http://www.directupload.net)   That pic is awesome to edit...can you tell me how you did this or did it show up on your photoshop with like a green overlay or something...similar to the fist pic above. please help me to understand how to open it up like you did...and also what file did you save it under like eg  [](http://www.directupload.net)  this is been great also that Mural pic i gave...any advice on how to successfully edit it with my own Mural Tagging graffiti etc...will i have to edit all channels?  i appreciate you man thanks thanks thanks
## Post #204
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2014-02-07T17:36:04+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

He already said he just moved the channels around, it doesn't necessarily matter what compression preset you save it as.
## Post #205
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2014-02-12T01:14:35+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

is it possible to mod a games xex file to run on a pc?﻿
## Post #206
- Username: perese1
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 04, 2014 10:03 am
- Post datetime: 2014-02-14T02:44:10+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

I am still not able to move channels around with the dx4_5 dds file...still overlay green like picture above...Please im using photoshop cs5...followed instructions above...but photoshop wont allow for me to swap or move color channels around...so Frustrating man...if anyone has a step by step guide...i would appreciate heaps...It maybe my photoshp cs5? running windows 8...cheers guys
## Post #207
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-02-15T16:36:08+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from philip92dk
>
> is it possible to mod a games xex file to run on a pc?﻿
No.
## Post #208
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-17T05:10:57+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from SILENTpavel
>
> philip92dk wrote:is it possible to mod a games xex file to run on a pc?﻿
No.

Oh man that would have rocked my world, i know it cant be done but playing readdeadredemption on my pc would be epic
## Post #209
- Username: zorg93
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Sep 15, 2013 5:08 pm
- Post datetime: 2014-02-20T04:13:42+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

about the resources and the RSC7 headers
anyone know how you can work out a sys/gfx flag from the sys/gfx size
this is how to get the size from a flag

```
        {
            baseSize <<= (int)(flag & 0xf);
            int size = (int)((((flag >> 17) & 0x7f) + (((flag >> 11) & 0x3f) << 1) + (((flag >> 7) & 0xf) << 2) + (((flag >> 5) & 0x3) << 3) + (((flag >> 4) & 0x1) << 4)) * baseSize);
            for (int i = 0; i < 4; ++i)
            {
                size += (((flag >> (24 + i)) & 1) == 1) ? (baseSize >> (1 + i)) : 0;
            }
            return size;
        }
```

EDIT: NVM just made an alg to brute for it for the need i wanted

```
        {
            if (size % baseSize != 0)
                throw new Exception();
            for (uint i = 0; i < 0x7FFFFFFF; i++)
            {
                if (GetSizeFromFlag(i, baseSize) == size)
                    return i;
            }
            throw new Exception("");
        }
```
## Post #210
- Username: nikobelic12
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 01, 2011 4:36 am
- Post datetime: 2014-04-30T00:52:59+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Could you please tell me how to swap the channels in photoshop im so confused. 
I would highly appreciate it if you could tell me the steps because i have photoshoped many things but i never ran into this issue. Could you please shine a light on how to fix it because i am really wanting to reverse the textures of V i dunno how to i mean i get what your saying but everytime there just locked. why Rockstar made everything so difficult.
My Friend has Extracted the GTA V files and Now i just need to figure out how to reverse the channels.
## Post #211
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2014-05-06T09:52:34+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Looks like R* changed something in the *.xtd/*.ctd structure in last DLC-updates. Need to be fixed.
I was busy in last few months so there is no progress with GTA V Texture Editor.

Could someone send me conflicted textures from x360 and PS3?
Thanks in advance.
## Post #212
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-09T21:40:12+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

hey!Dageron sorry for disturb but is possible to implement in your tool an export option for textures inside the CDD (simple dds) - XDD files? because the normal maps and specular maps for character are inside this file and not in ctd - xtd
## Post #213
- Username: dimon4ik6565
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 22, 2012 10:48 pm
- Post datetime: 2014-05-10T17:14:16+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Dageron
>
> Looks like R* changed something in the *.xtd/*.ctd structure in last DLC-updates. Need to be fixed.
I was busy in last few months so there is no progress with GTA V Texture Editor.

Could someone send me conflicted textures from x360 and PS3?
Thanks in advance.

i have xbox360 only. [http://rghost.ru/55074609](http://rghost.ru/55074609)

wait for 1.4
## Post #214
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2014-05-25T00:35:35+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

> Reply from Dageron
>
> Could someone send me conflicted textures from x360 and PS3?
There's also some textures on disc that don't work too with your editor, like everything I've tried in levels/gta5/props/roadside/v_signs.rpf gives me an error: 
"Exception EFOpenError in module GTA V Console Texture Editor.exe at 000B553A.
Cannot open file "(directory)\ĐG.dds". The system cannot find the file specified."
Anyway, here's some sample files from the updates on both consoles, and some files on disc (PS3 version) that don't work: [mediafire](http://www.mediafire.com/download/y11j8ayi1d0nxju/GTA_V_textures_dageron.rar).
## Post #215
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2014-05-25T10:08:39+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

OpenIV with GTA V support is released here - [viewtopic.php?p=94864#p94864](http://forum.xentax.com/viewtopic.php?p=94864#p94864)
## Post #216
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2014-06-11T10:37:53+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Thanks a lot for provided textures.

Fixed DLC texture support:
[](http://dageron.com/wp-content/uploads/2014/06/scr_1.jpg) [](http://dageron.com/wp-content/uploads/2014/06/scr_2.jpg) [](http://dageron.com/wp-content/uploads/2014/06/scr_3.jpg) [](http://dageron.com/wp-content/uploads/2014/06/scr_4.jpg)

New GTA V Console Texture Editor version (1.4) is available: [see here](http://dageron.com/?p=5944&lang=en).
Source code is published [on GitHub](https://github.com/Dageron/GTA-V-Console-Texture-Editor).
## Post #217
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2014-09-02T19:17:04+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Where I can found fonts please? If I found "font_lib_efigs_ps3.ctd/gfx then ctd loaded to GTAVConssole texture editor but a Ican't load gfx, why? Thanks for answer.
## Post #218
- Username: CoreyHUN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 17, 2014 6:39 am
- Post datetime: 2014-11-16T22:44:35+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Guys, how can i fix the UV maps for models? Or how can i correctly convert them? I get results like this:
## Post #219
- Username: L3git
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 09, 2015 1:19 am
- Post datetime: 2015-06-08T17:22:30+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hi guys , can anyone tell me where can I find tattoos so I can edit them, I've tried in PART4.rpf , but couldn't find anything except clothing and accs..
## Post #220
- Username: Neosphere
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 20, 2018 4:27 pm
- Post datetime: 2018-02-20T09:08:03+00:00
- Post Title: Re: [PS3/ X360] GTA V resource research & software developme

Hello all,
I am a newbie here.
