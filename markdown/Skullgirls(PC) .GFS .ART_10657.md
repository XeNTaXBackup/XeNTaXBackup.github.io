## Post #1
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-04T01:05:49+00:00
- Post Title: Skullgirls(PC) .GFS .ART

Can a bms script be made to extract .GFS files which supposedly contain .ART/.ART-PT files and them as well? 
[http://en.wikipedia.org/wiki/ART_image_file_format](http://en.wikipedia.org/wiki/ART_image_file_format) <--- more info on after .GFS is extracted.
For a year now everyone has been trying, but sadly to no avail thus I humbly ask anyone capable to give it a try. 

A chunk of data (both files, characters-art.gfs/characters-art-pt.gfs) 2MB:
[http://www.sendspace.com/file/lxakdd](http://www.sendspace.com/file/lxakdd)

This is what we can see from just viewing (Reverge Package File 1.1?):

```
temp/boss_marie.art
temp/boss_marie.art-8bit   ¡6          
temp/cerebella.art    
LÜN   temp/cerebella.art-8bit  
 temp/msfortune.art 
```
## Post #2
- Username: FinalBlast
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-04T13:57:31+00:00
- Post Title: Skullgirls(PC) .GFS .ART

quickbms script

```
#quickbms script by chrrox
endian big
get offset long
goto 0x2F
get files long
for i = 0 < files
get nsize longlong
getdstring name nsize
get size longlong
get align long
math offset x align
log name offset size
math offset += size
next i

```
## Post #3
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-04T17:47:28+00:00
- Post Title: Skullgirls(PC) .GFS .ART

Thank you, here is a chunk file of each: .art/.art-pt/.art-8bit,3MB can they be also extracted? 

[http://www.sendspace.com/file/8m9f21](http://www.sendspace.com/file/8m9f21)
## Post #4
- Username: FinalBlast
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-04T18:12:11+00:00
- Post Title: Skullgirls(PC) .GFS .ART

you can't just extract them  they need to be converted to standard image files.
## Post #5
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-04T18:17:53+00:00
- Post Title: Skullgirls(PC) .GFS .ART

I cannot find such a program that opens them, it doesn't seem to be just an .art file since it's 2 other formats and it's certainly not a single still image inside of these archives. Not sure what to do next.

edit: I tried the stated program "Graphics Workshop" but it says they are all damaged files, more like it isn't compatible...
       it's definitely an archive containing hundreds if not thousands of images inside of it I assure you.
## Post #6
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2013-08-10T17:02:52+00:00
- Post Title: Skullgirls(PC) .GFS .ART

GUI drag'n'drop packer/unpacker for gfs: [viewtopic.php?f=32&t=10677](http://forum.xentax.com/viewtopic.php?f=32&t=10677)
And a level editor (not presentable yet)

=====

All frames are probably in the format found in "temp\palettized_hud_art\" in dev.gfs

One palettized picture that shows which color goes where (character_cerebella_colors.pcx)
One for the outlines (character_cerebella_lines.pcx)
One for the derivation from the actual palette color (character_cerebella_shade.pcx)

There are no pcx headers in any of the art files, but the data is probably packed the same way

=====

The shader source is thankfully still available in "shaders" in dev.gfs

=====

The .art files are not the same as described in the wiki link

=====

Btw. funny little picture left from development in "temp\levels\textures\background.dds" in levels.gfs
## Post #7
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-10T22:30:03+00:00
- Post Title: Skullgirls(PC) .GFS .ART

test poo v1.0 
Upon using your tool I could not unpack any of the .gfs files, the bms script is the only one that works for me as provided above, 
I've installed Java Ver. 7 using XP, perhaps that's the problem? And about the the .art files...I think they might be .PNG perhaps...

I've tried using texture ripping programs such as NinjaRipper the result was a lot of .DDS files and this is a piece I got that resembles 
fight effectsFX, but I couldn't understand why it was so distorted and bizzaire it might be .DDS after all in the .art packages: 

[http://filetrip.net/dl?PCj5eJWYsS](http://filetrip.net/dl?PCj5eJWYsS) 1MB
## Post #8
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2013-08-11T09:41:13+00:00
- Post Title: Skullgirls(PC) .GFS .ART

[https://github.com/0xFAIL/SkullMod/releases/tag/v0.7](https://github.com/0xFAIL/SkullMod/releases/tag/v0.7) Should work now

(use the exe instead of the jar file)

If it doesn't work please PM me with the details

=====

The dds files seem swizzled, some have channels switched, nothing impossible
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-11T11:28:32+00:00
- Post Title: Skullgirls(PC) .GFS .ART

I am on windows 8 x64 and i click unpack and noting happens.
## Post #10
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-11T13:16:06+00:00
- Post Title: Skullgirls(PC) .GFS .ART

I've tried both .jar and .exe on XP using 0.7 clicking unpack and nothing happens ,hmm..
## Post #11
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2013-08-11T15:12:25+00:00
- Post Title: Skullgirls(PC) .GFS .ART

FinalBlast: So the exe/jar starts but nothing happens when you press unpack? That should mean that there are no files to process.
Look at the attachement, do the things happen like they are described there?
[howto.jpg](https://xentaxbackup.github.io/file/6551_howto.jpg)
## Post #12
- Username: 0xFAIL
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-11T15:19:28+00:00
- Post Title: Skullgirls(PC) .GFS .ART

yeah that screen shows up and the file is listed under valid files but no files show up in the bottom box and unpack does nothing.
## Post #13
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-11T16:32:49+00:00
- Post Title: Skullgirls(PC) .GFS .ART

Same with me, nothing shows in the Internal Files list.
## Post #14
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2013-08-11T17:33:07+00:00
- Post Title: Skullgirls(PC) .GFS .ART

Missed an included library, changed the file.
Tested it on another PC.
[https://github.com/0xFAIL/SkullMod/releases/tag/v0.7](https://github.com/0xFAIL/SkullMod/releases/tag/v0.7)

Please verify that the .exe and the .jar both work now.

Gonna add packing of .gsf files tomorrow. Then I'm gonna look into the dds files in the .art files.

Thank you for your help FinalBlast and chrrox.
## Post #15
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-11T21:03:40+00:00
- Post Title: Skullgirls(PC) .GFS .ART

It works now!   

[http://i.imgur.com/mQVC0Wb.jpg](http://i.imgur.com/mQVC0Wb.jpg)

Extracting Sprites.gfs results in those strange .DDS textures I spoke about earlier previewing pieces of char sprites and their respective FX, distorted completely, one .dds in particular looked like a human guy with a beard if my eyes do not deceive me. There is also for each .dds title a .MSB file which has these lines at start:

2.0 character_select_cerebella  % ,unigned char tile_x, tile_y, tile_u, tile_v; 

Other interesting thing is in the dev.gfs we see from compile.ini this about art files:

```
ArtAssets/valentine/valentine.spt #input export/temp/valentine.foit #output
```

Here is a piece of example files for those who don't have the game to see for themselves 
[http://filetrip.net/dl?C7fntTWBVi](http://filetrip.net/dl?C7fntTWBVi)
## Post #16
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2013-08-13T20:27:03+00:00
- Post Title: Re: Skullgirls(PC) .GFS .ART

Version 0.8 of gfsEdit released
-Packing .gfs files is now possible

[https://github.com/0xFAIL/SkullMod/releases](https://github.com/0xFAIL/SkullMod/releases)


@FinalBlast:
That guy might be drsubzero: [http://www.twitch.tv/askdrsubzero](http://www.twitch.tv/askdrsubzero)
## Post #17
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-12-28T16:15:13+00:00
- Post Title: Re: Skullgirls(PC) .GFS .ART

I've been following your updates, is there more info on the .art format?
## Post #18
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-06-03T21:48:03+00:00
- Post Title: Re: Skullgirls(PC) .GFS .ART

Thanks for the tools, but it's not working.
GFS file to make unpack, no lines are starting to appear in the game when I pack.
Sorry bad eng.
