## Post #1
- Username: GARID
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-04-06T23:09:06+00:00
- Post Title: [PSX] Silent Hill - Tools

This is pack with all useful tools for Silent Hill (PSX).
It contains:
- Silent Hill Files Extractor
- Tool for main executable (1ST/BODYPROG.BIN) encryption/decryption
- Font Editor
- DListEditor
- Source files

[DOWNLOAD SILENT HILL TOOLS](http://ikskoks.pl/XENTAX/silent_hill.zip)
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-07-21T02:10:42+00:00
- Post Title: [PSX] Silent Hill - Tools

update by CharlesM on Thu Jan 09, 2014 3:20 am
> Reply from CharlesM
>
> I've written a new files extraction tool for Silent Hill based on the original program by HoRRoR. The source and Windows binary are here:

http://cgfm2.emuviews.com/new/shx-010814.zip

It supports the following versions of the game:

JP, Full Game (SLPM-86192)
EU, Full Game (SLES-01514)
Official U.S. PlayStation Magazine Demo Disc #16 (SCUS-94278) 
US, Trial (Demo) Game (SLUS-90050) 
JP, Trial (Demo) Game (SLPM-80363) 
EU, Trial (Demo) Game (SLED-01735)

The demo versions of the game store the files differently, but I've done some research and figured out what the changes are. It is easy to add other versions of the game to the source, I just supported the ones I had. 

The program has options to view the filesystem, extract the files, and extract all unused data which comes "between" files and isn't officially part of the game data. Who knows, there could be some interesting things in there.

The earliest version of the game seems to be from the US PlayStation Magazine Demo Disc #16 listed above. I've been writing about the unused pictures, audio, and item names at The Cutting Room Floor, which were obtained using the file extraction program. The wiki page for that research is here:

http://tcrf.net/Proto:Silent_Hill

Hope this tool and information will be useful. Any feedback or suggestions are appreciated.
```
Based on an original programn (C) 2010 HoRRoR_X (www.consolegames.ru)
This program (C) 2014 Charles MacDonald (cgfm2.emuviews.com)

usage: shx <command> <parameters...>
Specify a command with no parameters to get help on use.
Available commands are: view extract unused

usage: shx extract <exe_file> <data_file> <output_dir>
example: shx extract slus_007.07 silent game_data
```
source: [http://silenthillcommunity.com/viewtopi ... 5&t=435683](http://silenthillcommunity.com/viewtopic.php?f=3335&t=435683)
[shx-010814.zip](https://xentaxbackup.github.io/file/7593_shx-010814.zip)
## Post #3
- Username: horrorx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 20, 2014 3:49 am
- Post datetime: 2014-10-19T20:02:57+00:00
- Post Title: [PSX] Silent Hill - Tools

I have updated the original file extractor, so it now works with ISO images directly and supports few more game versions.

Supported versions:
SLES-01514 - EU, Full Game
SLUS-00707 - US, Full Game (v1.1)
SLUS-00707 - US, Full Game Beta (v1.0)
SLPM-86192 - JP, Full Game (also distributed in SLPM-87029 release)
SLED-01735 - EU, Trial (Demo) Game
SLUS-90050 - US, Trial (Demo) Game
SLPM-80363 - JP, Trial (Demo) Game
SCUS-94278 - Official U.S. PlayStation Magazine Demo Disc #16
SCED-02420 - Best Horror Games Ever Demo
[Mirror 1](http://romhacking.ru/load/0-0-0-147-20), [Mirror 2](http://consolgames.ru/soft/SHExtract.7z).
[SHExtract.7z](https://xentaxbackup.github.io/file/7971_SHExtract.7z)
## Post #4
- Username: Giromancy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 21, 2014 11:11 am
- Post datetime: 2014-10-21T03:24:09+00:00
- Post Title: [PSX] Silent Hill - Tools

Thanks guys! i appreciate all the work you are doing, really
## Post #5
- Username: horrorx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 20, 2014 3:49 am
- Post datetime: 2014-11-01T17:30:00+00:00
- Post Title: [PSX] Silent Hill - Tools

Extractor updated to version 1.1.

- Fixed invalid directory structure and file extensions for SCUS-94278
- Added linux version
- Added new supported versions:

SLED-02186 - EU, Trial (Demo) Game #2
SLED-02190 - PlayStation Zone CD Vol. 10
SCED-04082 - Euro Demo (Future) 103

Links are the same.
[SHExtract.7z](https://xentaxbackup.github.io/file/8016_SHExtract.7z)
## Post #6
- Username: Giromancy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 21, 2014 11:11 am
- Post datetime: 2014-11-02T19:06:28+00:00
- Post Title: [PSX] Silent Hill - Tools

> Reply from horrorx
>
> Extractor updated to version 1.1.

- Fixed invalid directory structure and file extensions for SCUS-94278
- Added linux version
- Added new supported versions:

SLED-02186 - EU, Trial (Demo) Game #2
SLED-02190 - PlayStation Zone CD Vol. 10
SCED-04082 - Euro Demo (Future) 103

Links are the same.

Everything works fine now with SCUS-94278. Big thanks horrorx and Paul!
## Post #7
- Username: MartinBiohazard
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 03, 2014 6:49 am
- Post datetime: 2014-11-02T22:55:00+00:00
- Post Title: [PSX] Silent Hill - Tools

Thanks a lot for the updated version horrorx!!

Testing now...

Greetings.
## Post #8
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2015-02-03T10:37:26+00:00
- Post Title: [PSX] Silent Hill - Tools

Any chance you can add an option to extract files to RAW format (with sector flags etc)? VGMToolbox requires this to convert XA to playable files. So basically you can't do much with the files in the "XA" folder unless they contain all sector data.

Also I noticed some files are smaller than they should be. For example, \XA\35_26008 should be 0x3A56480, where the extracted size is 0xD7000. Tried both SLPM-86192 and SLUS-00707. I cannot find the code for it in your latest release of SHExtract, but in one of your older sources for a program called "OffsetDecoder", the masking for the size decoding seems to be incorrect:

```
{
    unsigned int lba = ((v >> 0x13) & 0xFFFF) << 8;
    return lba;
}
```
 0xFFFF should be 0xFFF:

```
sll     $v1, $a0, 1
addu    $v1, $a0
sll     $v1, 2
addu    $v1, $v0
lw      $v0, 0($v1)
nop
srl     $v0, 19
andi    $v0, 0xFFF
jr      $ra
sll     $v0, 8
```


Does it have to do with that maybe? I guess it's also possible the size is correctly specified and not a fault of your program, but somehow the game processes the size differently for XA files..
## Post #9
- Username: horrorx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 20, 2014 3:49 am
- Post datetime: 2015-04-07T00:22:23+00:00
- Post Title: [PSX] Silent Hill - Tools

> Reply from Nisto
>
> Any chance you can add an option to extract files to RAW format (with sector flags etc)?
Sorry, but I do not want to work on this tool again. But sources at your disposal.  It should be simple to implement.

> Reply from Nisto
>
> I cannot find the code for it in your latest release of SHExtract, but in one of your older sources for a program called "OffsetDecoder", the masking for the size decoding seems to be incorrect:
These sources are drafts which published without my permission. They can contain a lot of mistakes.
In new versions I used bit fields instead of logical shifts and bit masks:

```
	uint32_t startSector     : 19;  // CD start sector number
	uint32_t chunkCount      : 12;  // Size in chunks of size 0x100
	uint32_t directoryIndex0 : 1;
```

Accessing chunkCount is similar to (v >> 19) & 0xFFF.

> Reply from Nisto
>
> Does it have to do with that maybe? I guess it's also possible the size is correctly specified and not a fault of your program, but somehow the game processes the size differently for XA files..
Size of PSX RAM is 2MB. 0x3A56480 is too large byte count to read it to memory. I think specified size relates to loading to memory data. All other data can read from disc chunk-by-chunk. This logic can be specified in loaded to memory part ([overlay](http://en.wikipedia.org/wiki/Overlay_%28programming%29)), it seems that they contain executable code. So there are not quite files in the conventional sense.
## Post #10
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2015-04-14T15:22:46+00:00
- Post Title: [PSX] Silent Hill - Tools

Thanks for verifying, horrorx.
## Post #11
- Username: banderlog
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 29, 2012 12:20 am
- Post datetime: 2016-01-12T23:25:33+00:00
- Post Title: [PSX] Silent Hill - Tools

we need a new version for
Silent Hill (Trade Demo) [SLUS-80707]

[http://silenthillcommunity.com/viewtopi ... 0&t=437574](http://silenthillcommunity.com/viewtopic.php?f=20&t=437574)
## Post #12
- Username: Ranboon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 23, 2016 3:05 pm
- Post datetime: 2016-09-24T06:44:27+00:00
- Post Title: [PSX] Silent Hill - Tools

> Reply from ikskoks
>
> This excellent review of Viasil is pack with all useful tools for Silent Hill (PSX).
It contains:
- Silent Hill Files Extractor
- Tool for main executable (1ST/BODYPROG.BIN) encryption/decryption
- Font Editor
- DListEditor
- Source files

DOWNLOAD SILENT HILL TOOLS

Sweet, is there an update for this?
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-09-24T09:16:38+00:00
- Post Title: [PSX] Silent Hill - Tools

> Reply from Ranboon
>
> 
Sweet, is there an update for this?

There is a new link in the first post.
## Post #14
- Username: KUTSHKY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 15, 2020 9:58 am
- Post datetime: 2020-10-15T02:31:42+00:00
- Post Title: [PSX] Silent Hill - Tools

HOW TO USE Font Editor??? PLS HELP
## Post #15
- Username: Mitasoft
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 09, 2019 5:08 pm
- Post datetime: 2022-04-27T09:24:11+00:00
- Post Title: [PSX] Silent Hill - Tools

how to use this, dos window opens and immediately closes
## Post #16
- Username: Mitasoft
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-27T19:52:32+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

> Reply from Mitasoft ↑Wed Apr 27, 2022 5:24 pm at Wed Apr 27, 2022 5:24 pm
>
> 
how to use this, dos window opens and immediately closes

It's the command line tool.
There are many tutorials on the web on how to run this
[https://www.google.com/search?client=fi ... ne+program](https://www.google.com/search?client=firefox-b-d&q=how+to+run+command+line+program)
## Post #17
- Username: 3pacalypse2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 19, 2022 7:29 am
- Post datetime: 2022-12-19T18:03:58+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

Hi Ikskoks, I have a question for you, since I think you've done a similar project on the PSX and might be able to help.
I have translated the game in my language at 100% using these tools, the only assets I have remaining are the graphics/textures, which should be fairly easy, however since this is my first time attempting a localization of a PSX game, I am a bit of a noob with the whole CLUT/Color restrictions. 

I am using TIMVIEWER and TIM2VIEW, I know how to export and reimport images and have tried both the options:

EXPORT to PNG and IMPORT PNG
EXPORT to TIM and Convert to BMP and Convert back to TIM and IMPORT TIM

However for some reason some of my edits keep on getting messed up after re-inserting them or work to a various degree of success.

First I was thinking this has something to do with the limited pallettes. So I ran Photoshop and used the sampler to only use colors that are already in the texture/image, but this works to a very limited degree of success as well. I also now know that I cannot use the eraser always to remove the old text without screwing the texture.

My question to you is if you have any recommendation about a tool for editing the textures OR do you have any idea how I can edit the images using valid colors without screwing them up. Is there a soundproof method that works flawlessly or a program that I am not aware of?
Do you use Photoshop/GIMP/Paint etc for the process? And if so are there any special settings I should be aware of.


Thank you so much for your help!
## Post #18
- Username: 3pacalypse2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 19, 2022 7:29 am
- Post datetime: 2022-12-19T18:06:48+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

> Reply from KUTSHKY ↑Thu Oct 15, 2020 10:31 am at Thu Oct 15, 2020 10:31 am
>
> 
HOW TO USE Font Editor??? PLS HELP

I don't know how to use the FONT editor program that was provided here, but I can give you some tips on how you can edit the fonts.

Use TIM2VIEW to scan the bin file for images/textures. One of the first images you will see is the FONT used inside the game. Edit the image by placing carefully the letters of your language in the spots you want them to be. Reinsert the Picture you just edited using the same program in that same location.
## Post #19
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-20T00:43:32+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

> My question to you is if you have any recommendation about a tool for editing the textures OR do you have any idea how I can edit the images using valid colors without screwing them up. Is there a soundproof method that works flawlessly or a program that I am not aware of?
>
> Do you use Photoshop/GIMP/Paint etc for the process? And if so are there any special settings I should be aware of.

There are many tools for TIM format. Whole list of tools that I'm aware of is here
[http://wiki.xentax.com/index.php/TIM_Image](http://wiki.xentax.com/index.php/TIM_Image)

I've also shared a lot of PSX tools here [viewtopic.php?t=10136](https://forum.xentax.com/viewtopic.php?t=10136)

And if you're using TIM2VIEW, always make sure that you are using newest version.
Currently the newest one is "r90" [https://github.com/lab313ru/tim2view/releases/tag/r90](https://github.com/lab313ru/tim2view/releases/tag/r90)
(And I think this is the last version, as this tool is dead since 2016   )

I don't have any personal recomendation for editing TIMs, but I think I've spent most time using Tim2View and GIMP with TIM plugin.
Converting to  BMP/PNG and back to TIM also worked for me in most cases.
And for viewing them I'm always using Noesis as it has native support for them.

Sadly, there is no soundproof method. There's always a chance that you will encounter graphics with custom file format and no tool will help you in that situation.
## Post #20
- Username: 3pacalypse2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 19, 2022 7:29 am
- Post datetime: 2022-12-20T15:07:26+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

Thanks for the suggestions. 

After 3 days into the problem, with various degree of success with some images, I keep on having a problem with some that I can only attribute to some issue with the transparency.

Perhaps here is a good example of what is going on:

Here is the image preview in Tim2View before I edit the image:
[https://ibb.co/QJRQd08](https://ibb.co/QJRQd08)

Here is me inserting a TEST edit of the Map sprites after using Tim2View with Export PNG and Insert PNG:

[https://ibb.co/WxmXSyN](https://ibb.co/WxmXSyN)
[https://ibb.co/v14tC63](https://ibb.co/v14tC63)

Here is me inserting a test edit of the Map sprites after using Tim2View to Export TIM, Convert TIM to BMP with TIMVIEWER and following the edit, doing the reverse and reinserting the TIIM:

[https://ibb.co/4snmNC0](https://ibb.co/4snmNC0)
[https://ibb.co/XDQYj24](https://ibb.co/XDQYj24)

It's not working either way and as you can see the preview visualisation in Tim2View changes even before I test it in game, but perhaps it gives an example of the issue that I have not yet figured out. In the first case when using PNG it retains the color, but it drops some "static" on top, in the BMP case it changes the color altogether and adds less static, but there is still some visible.

I am using the Russian translation of Horror and co as a basis for mine, as it was easier for me to follow along.
For the edits I am simply using Photoshop and saving over the original file, without using additional colors, just sampling the ones that are on the image itself. 

I will check the tools that you have suggested. I will also really appreciate it if you have some idea of what is causing this?
## Post #21
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-20T20:10:02+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

> I will also really appreciate it if you have some idea of what is causing this?
Currently - I have no idea what is the issue.

If I do a little testing in game, I think I may be able to help you.
But let's talk about it privately on xentax or on Discord (write to PatrickHamster#8775), because I feel like it may be a little off-topic.
You know, it is a topic about Silent Hill Tools, not TIM tools in general.
## Post #22
- Username: 3pacalypse2
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 19, 2022 7:29 am
- Post datetime: 2022-12-20T20:16:10+00:00
- Post Title: Re: [PSX] Silent Hill - Tools

Sure, thank you for your time. 
I will ping you in Discord.
