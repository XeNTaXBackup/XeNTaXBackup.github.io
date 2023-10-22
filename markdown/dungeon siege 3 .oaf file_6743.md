## Post #1
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-06-07T13:19:30+00:00
- Post Title: dungeon siege 3 *.oaf file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-07T13:55:19+00:00
- Post Title: dungeon siege 3 *.oaf file

just use offzip.
## Post #3
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-07T21:08:35+00:00
- Post Title: dungeon siege 3 *.oaf file

My extractor will be online tomorrow. I'm going to sleep tonight
## Post #4
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-08T15:37:11+00:00
- Post Title: dungeon siege 3 *.oaf file

So here it is   

Dungeon Siege 3 OAF Files Extractor
[http://raptor.cestiny.cz/download/dunge ... actor.html](http://raptor.cestiny.cz/download/dungeon-siege-3-oaf-files-extractor.html)

Use it to extract and rebuild game archives.

Dungeon Siege 3 Translator
[http://raptor.cestiny.cz/download/dunge ... lator.html](http://raptor.cestiny.cz/download/dungeon-siege-3-translator.html)

Use it to translate game, if you want to do it.

I hope it will work fine. It is tested, but you know. Game is in demo state, so maybe there will be something wrong with retail game archives. But I will update it. Any errors? Just let me know.
## Post #5
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-06-08T17:27:19+00:00
- Post Title: dungeon siege 3 *.oaf file

> Reply from XRaptor
>
> So here it is   

Dungeon Siege 3 OAF Files Extractor
http://raptor.cestiny.cz/download/dunge ... actor.html

Use it to extract and rebuild game archives.

Dungeon Siege 3 Translator
http://raptor.cestiny.cz/download/dunge ... lator.html

Use it to translate game, if you want to do it.

I hope it will work fine. It is tested, but you know. Game is in demo state, so maybe there will be something wrong with retail game archives. But I will update it. Any errors? Just let me know.

Thank You!
Perfectly Working!
## Post #6
- Username: Jack LD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 09, 2011 7:55 pm
- Post datetime: 2011-06-09T12:07:01+00:00
- Post Title: dungeon siege 3 *.oaf file

Thank you!
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-10T22:47:11+00:00
- Post Title: dungeon siege 3 *.oaf file

if you need the big archive extracted for the data files here is a quickbms script.

```
get unk01 short
get unk02 short
get unk03 short
get unk04 short
get nametableoff long
get null long
get files long
get unk05 long
savepos filetble
for i = 0 < files
goto filetble
get offset long
get type long
get size long
get zsize long
get unk06 long
savepos filetble
goto nametableoff
get name string
savepos nametableoff
if zsize == 0
log name offset size
else
clog name offset zsize size
endif
next i

```
## Post #8
- Username: Doublehex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 13, 2011 12:50 am
- Post datetime: 2011-06-12T16:53:55+00:00
- Post Title: dungeon siege 3 *.oaf file

> Reply from XRaptor
>
> So here it is   

I hope it will work fine. It is tested, but you know. Game is in demo state, so maybe there will be something wrong with retail game archives. But I will update it. Any errors? Just let me know.

When I try to open the big .oaf file, data_archive.oaf, the program displays the file names as a bunch of unrecognizable symbols and is unable to extract the files. Take note that it has no problem with any of the other .oaf files - it is just the biggest one that has issues.
## Post #9
- Username: kaine9mm
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2011 1:00 am
- Post datetime: 2011-06-12T17:05:20+00:00
- Post Title: dungeon siege 3 *.oaf file

Hey doublehex don't know if you are just commenting on it or need help. If you havnt been able to extract it check out the post above yours, and use quickbms to extract it. I've done it and some basic editing is possible with the files (mostly in global folder).  But the Dungeon Siege extractor works very well for all the other files ^_^. Nice work.
## Post #10
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-12T18:35:12+00:00
- Post Title: dungeon siege 3 *.oaf file

> Reply from Doublehex
>
> When I try to open the big .oaf file, data_archive.oaf, the program displays the file names as a bunch of unrecognizable symbols and is unable to extract the files. Take note that it has no problem with any of the other .oaf files - it is just the biggest one that has issues.
This tool was made based on demo files. I will fix it asap.
## Post #11
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-12T19:21:40+00:00
- Post Title: dungeon siege 3 *.oaf file

Version 1.1 is out, sorry for problems 
[http://raptor.cestiny.cz/download/dunge ... actor.html](http://raptor.cestiny.cz/download/dungeon-siege-3-oaf-files-extractor.html)

Simple error - overflow in one 32bit value. Now it is handled as 64bit.
## Post #12
- Username: Doublehex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 13, 2011 12:50 am
- Post datetime: 2011-06-12T22:50:08+00:00
- Post Title: dungeon siege 3 *.oaf file

Found another problem: OGG plays no sound. Despire them having various file sizes, they have a running time of 0. This may not be directly related to your extractor, but I'd thought I'd go by you first.
## Post #13
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-13T05:51:54+00:00
- Post Title: dungeon siege 3 *.oaf file

That's because ogg files are NOT ogg files. They have wav header but all seems to be somehow modified. Maybe to prevent direct play.
## Post #14
- Username: Doublehex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 13, 2011 12:50 am
- Post datetime: 2011-06-13T06:48:21+00:00
- Post Title: dungeon siege 3 *.oaf file

> Reply from XRaptor
>
> That's because ogg files are NOT ogg files. They have wav header but all seems to be somehow modified. Maybe to prevent direct play.

Well,do you happen to know where I can find a tutorial that could show me how to change the header to .OGG or some other method that would make them playable?
## Post #15
- Username: kaine9mm
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2011 1:00 am
- Post datetime: 2011-06-13T12:41:11+00:00
- Post Title: dungeon siege 3 *.oaf file

anyone know how to open the .amx files in the "scripts" folder? I've tried some basic stuff, but the format isnt exactly normal for script writing. also i'm a newb so sorry if i say anything...you know...newbish lol.
## Post #16
- Username: Auumar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 29, 2010 12:56 pm
- Post datetime: 2011-06-13T13:45:13+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Hmm. I am able to open dds files I extracted from the Beta with the above tool just fine, but ones out of retail are giving me errors in both irfanview and photoshop. Did they become encrypted/compressed or something?

/e I've been told they lack a header and are compressed. Or something like that.

/edit 2

It may just be specific files as well. One that is broken is effects/fx_chroma_x_01.dds
## Post #17
- Username: kaine9mm
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2011 1:00 am
- Post datetime: 2011-06-13T14:32:34+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from Auumar
>
> Hmm. I am able to open dds files I extracted from the Beta with the above tool just fine, but ones out of retail are giving me errors in both irfanview and photoshop. Did they become encrypted/compressed or something?

/e I've been told they lack a header and are compressed. Or something like that.

/edit 2

It may just be specific files as well. One that is broken is effects/fx_chroma_x_01.dds

I've successfully edited dds files but i did not use the extractor i used quickbms to extract. and i only messed with some character textures so that could be a difference.

using photoshop btw.
## Post #18
- Username: Doublehex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 13, 2011 12:50 am
- Post datetime: 2011-06-13T14:42:39+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from kaine9mm
>
> Auumar wrote:Hmm. I am able to open dds files I extracted from the Beta with the above tool just fine, but ones out of retail are giving me errors in both irfanview and photoshop. Did they become encrypted/compressed or something?

/e I've been told they lack a header and are compressed. Or something like that.

/edit 2

It may just be specific files as well. One that is broken is effects/fx_chroma_x_01.dds

I've successfully edited dds files but i did not use the extractor i used quickbms to extract. and i only messed with some character textures so that could be a difference.

using photoshop btw.

Think you could post the .bms script so that the rest of us can give it a try?
## Post #19
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-06-13T15:07:27+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from Doublehex
>
> kaine9mm wrote:Auumar wrote:Hmm. I am able to open dds files I extracted from the Beta with the above tool just fine, but ones out of retail are giving me errors in both irfanview and photoshop. Did they become encrypted/compressed or something?

/e I've been told they lack a header and are compressed. Or something like that.

/edit 2

It may just be specific files as well. One that is broken is effects/fx_chroma_x_01.dds

I've successfully edited dds files but i did not use the extractor i used quickbms to extract. and i only messed with some character textures so that could be a difference.

using photoshop btw.

Think you could post the .bms script so that the rest of us can give it a try?

Check chorrox's post on page 1.
## Post #20
- Username: Doublehex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 13, 2011 12:50 am
- Post datetime: 2011-06-13T15:29:56+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Kinda hard to believe I missed that. Sorry.

It made no difference with the .OGG, though. Pity.
## Post #21
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-13T15:49:31+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Blah, shame on me. I made a new bug in extractor. Never try to fix bugs as quick as possible  64bit offsets is fixed now everywhere (I hope). You can now safely rebuild all archives (big one included) 

Dungeon Siege 3 OAF Files Extractor v1.2
[http://raptor.cestiny.cz/download/dunge ... actor.html](http://raptor.cestiny.cz/download/dungeon-siege-3-oaf-files-extractor.html)
## Post #22
- Username: kaine9mm
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2011 1:00 am
- Post datetime: 2011-06-13T15:53:57+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

So don't really know where to post this question, but since it's on the topic of ds3, know how to or if you can, enable the console? Ive tried basic stuff. No freakin controls configuration either. Also there's a folder in the "globals" folder called console_scripts. Which contains...console scripts? in text file. Id like to be able to run w/ some of these parameters to mess around with, but I don't know how or if you can actually get them to load.
## Post #23
- Username: Auumar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 29, 2010 12:56 pm
- Post datetime: 2011-06-13T23:50:01+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Awesome, thanks bros! The dds files work fine.
## Post #24
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2011-06-17T10:03:53+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

First extracted all the files from data_archive.oaf.
Then edit some files. Since I've added many new contents, the modified file became larger than before, i.e. 10k to 5M.
Finally, I use raptor's extract to pack all the files again.

It took a long very long time, since data_archive.oaf is a very large file, 2G. But the output file is very large, about 5G. How could it happen? Is there something wrong with the packer?
## Post #25
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-17T10:43:13+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Make sure you have last version 1.2 of this tool. Then if there is problem in this version, let me know. I made many fixes to version 1.2 because of 32bit values overflow, so I hope all are fixed.
## Post #26
- Username: kaine9mm
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 13, 2011 1:00 am
- Post datetime: 2011-06-17T12:52:28+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from supercolin
>
> First extracted all the files from data_archive.oaf.
Then edit some files. Since I've added many new contents, the modified file became larger than before, i.e. 10k to 5M.
Finally, I use raptor's extract to pack all the files again.

It took a long very long time, since data_archive.oaf is a very large file, 2G. But the output file is very large, about 5G. How could it happen? Is there something wrong with the packer?

I would like to help but since I never used the repack I can't comment on that. Only bit of info I can give is that it isn't necessary to repack the files.
## Post #27
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2011-06-17T13:23:26+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from XRaptor
>
> Make sure you have last version 1.2 of this tool. Then if there is problem in this version, let me know. I made many fixes to version 1.2 because of 32bit values overflow, so I hope all are fixed.

Yes, I used the latest version 1.2. It works on the other files, but the largest one data_archive.oaf fails.
Anyway I'll try again on data_archive.oaf. It really takes a long time..
## Post #28
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-17T14:52:20+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Are you using for "patch" action all extracted files, or modified only? (Just to let you know, there is no need to pack again all files). If there is any way how to send me files you have modified, I can test it on my side to find out where the problem is.
## Post #29
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2011-06-19T03:59:05+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from XRaptor
>
> Are you using for "patch" action all extracted files, or modified only? (Just to let you know, there is no need to pack again all files). If there is any way how to send me files you have modified, I can test it on my side to find out where the problem is.

This time I only "patch" the modified ones.
My steps:
1. select file to extract.
2. replace the files with the modified ones.
In order to change the font, I replaced localized_fonts.gfx and localized_fonts_stddef.gfx.
3. Use the extractor to patch and pack to the new data_archive.oaf. 
The file size looks normal. But after run the game, it crashes after the "Obsidian" loading screen.

I'll check if it is caused by the modified files or the patching.
## Post #30
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-06-23T16:34:11+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Hi guys, I would like to extract files from .std
I know there we have translator already done, but I wanted to learn myself something..

So far, I have something like this:

```
get unk1 short
get NUMBEROFLINES short

for i = 0 < NUMBEROFLINES
get ID long
get unk3 long
get LENGTH long
get OFFSET long
get EMPTY long
Next i


```


ID - seems to be some kind of ID (used in XML files), 'cos it's increasing +1
I wonder if I could have XML file as output, something like this: <String ID="32090" Tag="ABILITY_UNAVAILABLE"/>

update: ok, unk1 long are:
unk1 short (always 00 14)
NUMBEROFLINES short
## Post #31
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-24T11:37:50+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

There is nothing special in structure:

Header:
 4B - Version
 2B - Unknown
 4B - ItemCount

Items (array[ItemsCount]):
 4B - ItemID
 4B - String Length
 4B - Block Length (it is real block size used for Unicode/utf-8 bytes)
 4B - Offset
 4B - Unkown

String block starts and ends with separator value 0x0A0B0C0D
## Post #32
- Username: Kaviash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 28, 2010 1:26 am
- Post datetime: 2011-06-28T18:00:16+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Has anyone succeeded in converting this .ogg to something normal ? Because the music is really beautiful
They are using Autodesk Wwise
I can extract .wav from .bnk using bnkextr but I cannot convert those .wav
## Post #33
- Username: snakely
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 20, 2011 6:02 am
- Post datetime: 2011-12-19T22:57:09+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

regarding the ogg music files, i have successfully converted them into properly playable OGGs.  Here's how:

Download the archive extractor that RaptorX posted on page one: viewtopic.php?f=10&t=6743#p55150
Run DungeonSiege3Extractor.exe and use it to open data_archive.oaf in the DS3 root
Show only OGG files using the file type dropdown, CTRL-A to select all, save selected to somewhere. Note that the files are extracted into their existing directory structure, i.e. \global\audio\sound_bank
Download the program ww2ogg from http://hcs64.com/vgm_ripping.html and put it in the directory with your extracted OGGs.  You only need the files ww2ogg.exe and packed_codebooks.bin from this archive.
Download revorb from http://www.hydrogenaudio.org/forums/lof ... 64328.html and put it in the directory with all the OGGs.  This program fixes the "granulepos", which is apparently used by some players to determine duration.
Save my attached batch in the directory with all the OGGs and then run it.
Step 3: Profit!
[ds3_music_batch.zip](https://xentaxbackup.github.io/file/4919_ds3_music_batch.zip)
## Post #34
- Username: sacah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 02, 2012 5:31 pm
- Post datetime: 2012-01-02T09:35:32+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Got the game recently, tried to fix the camera angles, in the process I've enabled the console, thought you guys might be interested, or have more to add
[http://www.sacah.net/2012/01/dungeon-si ... nsole.html](http://www.sacah.net/2012/01/dungeon-siege-iii-enable-console.html)

I'll be posting more info as I find it.
## Post #35
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-05-09T17:03:44+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

In what file are fonts ?
THX
## Post #36
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-27T11:22:58+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Friend, you can give support. oaf Dungeon Siege II

[http://www.mediafire.com/?gk4xc8qy2c1cwwx](http://www.mediafire.com/?gk4xc8qy2c1cwwx)
## Post #37
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-11-29T19:44:08+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

> Reply from timartinelli
>
> Friend, you can give support. oaf Dungeon Siege II

http://www.mediafire.com/?gk4xc8qy2c1cwwx

It is that strange PS3 version. I'm not able to extract it, because part of this file is encrypted somehow. Or it is not fully decrypted from PS3 image. I have no idea. Maybe it is just different compression. Original game is using zlib, this should be LZW or anything?
## Post #38
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-12-05T01:52:32+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

Okay, Thanks for looking.

Hug.
## Post #39
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2014-03-02T02:52:36+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

I just wanted to point out, that South Park - The Stick of Truth seems to use a similar format. I tried both the BMS script and the extractor and both seem to fail on the OAF files.

Here is one sample file of the game: [https://mega.co.nz/#!pBZmQJAa!CZFfnxuMY ... Jb7Dzjx6NM](https://mega.co.nz/#!pBZmQJAa!CZFfnxuMY1H1YasiycHxo80JemFx218hdJb7Dzjx6NM)
## Post #40
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2014-03-05T18:08:58+00:00
- Post Title: Re: dungeon siege 3 *.oaf file

If anyone can investigate the South Park archive, that'd be awesome. I'd love to get my ears on the music. Thanks so much for everything you all do here!

EDIT: Err... nevermind. The file extractor seems to work just fine. Now to find the music....
