## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-07-25T14:18:30+00:00
- Post Title: Septerra Core .DB files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Lunarshine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 08, 2010 8:24 pm
- Post datetime: 2010-11-08T15:01:45+00:00
- Post Title: Septerra Core .DB files

I'd also greatly appreciate help to get that other data, namely character sprites and level graphics/tiles. I also got the same results in unpacking as Researchman, but these weren't all sounds. Each characters spoken dialogue maybe, but not shots, explosions, magic, etc.

thanks in advance
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-12-25T01:15:57+00:00
- Post Title: Septerra Core .DB files

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: kapusta
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 18, 2011 8:54 pm
- Post datetime: 2011-01-18T13:04:01+00:00
- Post Title: Septerra Core .DB files

Hello World!

pardon me for ressurecting this topic. Researchman, how do you managed to get that level texture in TexFinder? Any efforts are resulting into that "color noise" like on the right picture 
I am interested into some level textures (iirc graveyard? and few others) but had no luck extracting the DB file, too. 




thanks!
## Post #5
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-01-18T20:54:23+00:00
- Post Title: Septerra Core .DB files

kapusta:

> how do you managed to get that level texture in TexFinder? Any efforts are resulting into that "color noise" like on the right picture

I use ctrl+alt+delete for call the windows dispatcher and select function "create dump" on the game process.

DB files is hard format. I think this is maybe DLL-style packed, with headers for indentify file types.
## Post #6
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-01-19T14:05:30+00:00
- Post Title: Septerra Core .DB files

It is long time ago when this game was released. I made translation of texts with my own tools, but I lost my HDD (HW/e lectronic error, disk self-destroyed and there were no way how to recover data) with everything. All I know is, that text db is pretty easy. Just many TX00 blocks with multilanguage texts. Just indexes on start and then data xored and byte-shifted ( xor 96 and upper characters increment +2 - so xored text is like Dire -> Fire, Qpeed -> Speed, ...)
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-01-19T14:56:00+00:00
- Post Title: Septerra Core .DB files

> I made translation of texts with my own tools, but I lost my HDD (HW/e lectronic error, disk self-destroyed and there were no way how to recover data) with everything.
Too bad.

> All I know is, that text db is pretty easy. Just many TX00 blocks with multilanguage texts. Just indexes on start and then data xored and byte-shifted ( xor 96 and upper characters increment +2 - so xored text is like Dire -> Fire, Qpeed -> Speed, ...)
Could you tried create any simple tool?
## Post #8
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-01-19T17:01:00+00:00
- Post Title: Septerra Core .DB files

Well, I think that I don't want to reverse all files again, because it is really old game  But if someone else want to spend time on it, he will need SEPTERRA.IDX file with all indexes to DB files.

There is no problem with extracting files (I'm not talking about Septerra Core only), but it will take time to pack everything back.
## Post #9
- Username: kapusta
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 18, 2011 8:54 pm
- Post datetime: 2011-01-19T18:32:33+00:00
- Post Title: Septerra Core .DB files

> Reply from Researchman
>
> I use ctrl+alt+delete for call the windows dispatcher and select function "create dump" on the game process.

Cannot understand your steps. 

You run the game process, then press ctrl+alt+del, run the taskbar (assuming you are using win). There is no option to create dumps from running programs.
I am probably missing something. 

Thanks in advance!
## Post #10
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-01-19T20:47:21+00:00
- Post Title: Septerra Core .DB files

> Reply from kapusta
>
> There is no option to create dumps from running programs.
It is available in Vista and Windows 7 only. It is available in WinXP.
[http://blogs.msdn.com/b/junfeng/archive ... ocess.aspx](http://blogs.msdn.com/b/junfeng/archive/2008/06/19/getting-a-full-memory-dump-for-a-process.aspx)
## Post #11
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-01-19T23:26:52+00:00
- Post Title: Septerra Core .DB files

Archive with septerra.idx with septerra.ini and septerra.mft.
[septerra.idx.rar](https://xentaxbackup.github.io/file/3820_septerra.idx.rar)
## Post #12
- Username: kapusta
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 18, 2011 8:54 pm
- Post datetime: 2011-01-20T22:56:11+00:00
- Post Title: Septerra Core .DB files

> Reply from XRaptor
>
> It is available in Vista and Windows 7 only. It is available in WinXP

too bad for me, using XP. 


> Reply from XRaptor
>
> Well, I think that I don't want to reverse all files again, because it is really old game  But if someone else want to spend time on it, he will need SEPTERRA.IDX file with all indexes to DB files.

There is no problem with extracting files (I'm not talking about Septerra Core only), but it will take time to pack everything back.

Allright, thanks for the IDX file. How can I use it to get inside the DB archive?  I am interested into extracting all possible map tiles, so no packing back to .db

thanks in advance
## Post #13
- Username: XDarkx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 27, 2011 12:26 am
- Post datetime: 2011-05-26T16:39:56+00:00
- Post Title: Septerra Core .DB files

> Reply from XRaptor
>
> It is long time ago when this game was released. I made translation of texts with my own tools, but I lost my HDD (HW/e lectronic error, disk self-destroyed and there were no way how to recover data) with everything. All I know is, that text db is pretty easy. Just many TX00 blocks with multilanguage texts. Just indexes on start and then data xored and byte-shifted ( xor 96 and upper characters increment +2 - so xored text is like Dire -> Fire, Qpeed -> Speed, ...)
as you did for translating the game, I really wanted to be able to open it to translate it, how could it do?
in the file text.db contains the text for translate ?
## Post #14
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-06-06T16:04:49+00:00
- Post Title: Septerra Core .DB files

If anyone can help, PM for getting files for tests and research.
## Post #15
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-08-29T18:46:24+00:00
- Post Title: Septerra Core .DB files

Demo of the game - [http://www.ag.ru/games/septerra-core-le ... demos/4770](http://www.ag.ru/games/septerra-core-legacy-of-the-creator/demos/4770)

Archives is same.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-29T19:37:22+00:00
- Post Title: Re: Septerra Core .DB files

[http://aluigi.org/papers/bms/septerra_core.bms](http://aluigi.org/papers/bms/septerra_core.bms)

the script reads the list of files from the MFT file and then parses the IDX one for downloading ALL the files from ALL the archives.
so use it one time only.
## Post #17
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-09-01T17:49:49+00:00
- Post Title: Re: Septerra Core .DB files

Thanks for script, aluigi.

File Formats:
VSS - sounds and voices in mp3, VSSF header.
AM0 - sprites and animations, AM04 header.
CH1 - character data, CH14 header.
DAT - just movies in QuickTime video format.
LV2 - level data resources, LV25 header.
TX0 - texts, TX00 header.

000001e4.gv0 - global game data, GV00 header.
000002e8.il0 - need for something in game, IL00 header.


I think, uses LZSS-style compression - STUNS identify Deflate and LZO compression, except .vss files(just container).
Files can be requested in PM.
## Post #18
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-10T15:56:33+00:00
- Post Title: Re: Septerra Core .DB files

Any news here?
## Post #19
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-10T16:13:35+00:00
- Post Title: Re: Septerra Core .DB files

> Reply from Giovarco
>
> Any news here?

This could be useful: [https://github.com/FileFormatTools/jRip ... pterraCore](https://github.com/FileFormatTools/jRipper/tree/master/Tools/SepterraCore)

Can someone understand the content?
## Post #20
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-12T16:02:20+00:00
- Post Title: Re: Septerra Core .DB files

> Reply from Giovarco
>
> Giovarco wrote:Any news here?

This could be useful: https://github.com/FileFormatTools/jRip ... pterraCore

Can someone understand the content?

Up!

I took a look to JRipper. Inside TX0.vb, you can read "To decrypt TX0 files you must first XOR 96 and then increment uppercase letters +2 (i.e A = C, B = D)". 

Can someone kindly check?
## Post #21
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-24T00:38:12+00:00
- Post Title: Re: Septerra Core .DB files

Perhaps this is a seasonal exacerbation, but after 19 years, I also wanted to look inside the game. 
[https://github.com/Albeoris/Septerra](https://github.com/Albeoris/Septerra)

Features:
1. Unpack all resources (run from the game folder)
2. Decompress compressed files
3. Convert text resources to text files

The code is terrible. I'm falling asleep. -_-
## Post #22
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-25T09:42:21+00:00
- Post Title: Re: Septerra Core .DB files

> Reply from Albeoris
>
> Perhaps this is a seasonal exacerbation, but after 19 years, I also wanted to look inside the game. 
https://github.com/Albeoris/Septerra

Features:
1. Unpack all resources (run from the game folder)
2. Decompress compressed files
3. Convert text resources to text files

The code is terrible. I'm falling asleep. -_-

Hi Albeoris!

That's nice to hear that you are interested 

Can I kindly ask where is the exe file?

By the way, did you write to code to both decrypt and encrypt? frank_one already decoded successfully TX0 files into TXT files, here: [http://www.oldgamesitalia.net/forum/ind ... ntry370205](http://www.oldgamesitalia.net/forum/index.php?showtopic=22660&st=0&gopid=370205&#entry370205). Now he will try to do the opposite and test the game with the translations. I think that he would appreciate your help
## Post #23
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-25T18:26:14+00:00
- Post Title: Re: Septerra Core .DB files

Download: [https://yadi.sk/d/YOXLy--8RgoXTQ](https://yadi.sk/d/YOXLy--8RgoXTQ)

Yes, we can pack it again (without compression). But I have no time to do that right now.
## Post #24
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-25T22:25:47+00:00
- Post Title: Re: Septerra Core .DB files

Command line arguments:

Example:
septerra.exe -M -R -VMainSave

Arguments:
-A - go to advertising scene
-A[0-9] - go to advertising scene (?)
-С[directoryPath] - override HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Valkyrie Studios\Septerra Core\SourcePath
-D - disable unknown functional (something around movies)
-E - ?
-F - force fullscreen (default)
-H[directoryPath] - override HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Valkyrie Studios\Septerra Core\installpath
-L[A-Z][0-9] - load level; id = (Letter - 'A') * 1000 + Number. (Example: -LZ1 will load credits scene)
-M - disable video
-N - disable MMX CPU Instructions
-OLDSAVE - support old save file formats (before the release of the game)
-P - disable unknown functional
-Q - some "Quiet" mode + disable sound
-R - run always (without double click)
-S - disable sound
-V - load last save on startup
-V[saveName] - load specified save on startup. (Example: -VMySave)
-W - window mode (640x480, failed to initialize DirectDraw )
-X - ?
-Y - ?
Other:
You can put "tp_strip.bmp" image to the game folder and will see it on startup if movies are enabled

P.S. 
```
strcpy(&unk_4B0960, "In Memory Of\n\nRobert G. Weisz");
```
 :c
## Post #25
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-26T08:40:04+00:00
- Post Title: Re: Septerra Core .DB files

> Reply from Albeoris
>
> Command line arguments:

Example:
septerra.exe -M -R -VMainSave

Arguments:
-A - go to advertising scene
-A[0-9] - go to advertising scene (?)
-С[fullPath] - specify some file path
-D - disable unknown functional
-E - ?
-F - force fullscreen (default)
-H[directoryPath] - specify directory with septerra.ini file
-L[A-Z][0-9] - load level; id = (Letter - 'A') * 1000 + Number. (Example: -LZ1 will load credits scene)
-M - disable video
-N - disable MMX CPU Instructions
-OLDSAVE - support old save file formats (before the release of the game)
-P - disable unknown functional
-Q - some "Quiet" mode + disable sound
-R - run always (without double click)
-S - disable sound
-V - load last save on startup
-V[saveName] - load specified save on startup. (Example: -VMySave)
-W - window mode (640x480, failed to initialize DirectDraw )
-X - ?
-Y - ?
Other:
You can put "tp_strip.bmp" image to the game folder and will see it on startup if movies are enabled

P.S. Code: Select allstrcpy(&unk_4B0960, "In Memory Of\n\nRobert G. Weisz"); :c

Thanks! How can these arguments help in this case?
## Post #26
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-26T17:38:32+00:00
- Post Title: Re: Septerra Core .DB files

It's just information about a game that has nothing to do with your question. (=
## Post #27
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-26T21:06:38+00:00
- Post Title: Re: Septerra Core .DB files

Added GV Support:
Sources: [https://github.com/Albeoris/Septerra/bl ... VReader.cs](https://github.com/Albeoris/Septerra/blob/master/Septera/GV/GVReader.cs)
Result: [https://pastebin.com/TRgQq4XX](https://pastebin.com/TRgQq4XX)
## Post #28
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-26T22:21:26+00:00
- Post Title: Re: Septerra Core .DB files

Added IL Support:
Sources: [https://github.com/Albeoris/Septerra/bl ... LReader.cs](https://github.com/Albeoris/Septerra/blob/master/Septera/IL/ILReader.cs)
Result: [https://pastebin.com/PANHPMst](https://pastebin.com/PANHPMst)
## Post #29
- Username: Giovarco
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 18, 2015 12:17 am
- Post datetime: 2018-09-27T12:22:56+00:00
- Post Title: Re: Septerra Core .DB files

> Reply from Albeoris
>
> Added IL Support:
Sources: https://github.com/Albeoris/Septerra/bl ... LReader.cs
Result: https://pastebin.com/PANHPMst

What is this for?

By the way, frank_one could be able to decrypt Septerra Core TX0 files to TXT files and decrypt them back to TX0!

Now we need a way to archive the new TX0 files into the Septerra.mft again. in other words, we need to write a BMS script to do this and use QuickBMS software. Are you able to offer some support about this?
## Post #30
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-27T19:11:23+00:00
- Post Title: Re: Septerra Core .DB files

> Reply from Researchman
>
> 000002e8.il0 - need for something in game, IL00 header.

> Yes, we can pack it again (without compression). But I have no time to do that right now.

I understand you as an translator, but for now this task is not interesting for me, and I spend my free time for other formats.

Now anyone can use this knowledge to write a packer.

It's simple - you just need to add data to the end of the file without any compression and update their size and offset in the index file. It can be done by anyone who has had programming lessons at school or university. Do not be lazy. 

Sooner or later, my hands will reach. But while I'm doing what is difficult to do.
## Post #31
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-09-28T06:51:16+00:00
- Post Title: Re: Septerra Core .DB files

CH has complex format. For example, it's 7th region of 13. Constructing an actor info:

[https://pastebin.com/ufe8AFTD](https://pastebin.com/ufe8AFTD)
## Post #32
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-10-04T23:20:22+00:00
- Post Title: Re: Septerra Core .DB files

Hello. The cunning plan was a success. I modified the game engine so that it loads files directly from the file system. This gives us a wealth of opportunities for R&D. For example, data from the file system can be instantly updated in the game, without having to pack it into game archives. Some information is cached (for example, data about the characters), so to update it you will either have to load saved game or we need to integrate it deeper into the game engine. At the moment, the changes are minimal.

Hook (Septerra_DbRecord_Open);
Hook (Septerra_DbRecord_Seek);
Hook (Septerra_DbRecord_GetDecompressedSize);
Hook (Septerra_DbRecord_Read);
Hook (Septerra_DbRecord_Close);

Limitations:
1) The modification injects itself into the game process - it needs admin privileges.
2) The modification writes files to the file system (so far only the log file) - it needs write access to the game folder.
3) To start the game in the window (because without this, normal debugging is impossible) a third-party application is used - DxWnd.

I will try to update the version next week (now it’s a proof-of-concept written on my knee).
## Post #33
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-10-12T20:54:42+00:00
- Post Title: Re: Septerra Core .DB files

[https://www.youtube.com/watch?v=ruNXGj9UXdY](https://www.youtube.com/watch?v=ruNXGj9UXdY)
Almost done.
## Post #34
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-10-28T11:28:39+00:00
- Post Title: Re: Septerra Core .DB files

Since there is no great interest in these changes, I continued the research. I was able to pull out the images, although some of the animation metadata has not yet been investigated, and it is unclear in what format they are best exported for ease of editing.
## Post #35
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-10-28T22:41:42+00:00
- Post Title: Re: Septerra Core .DB files

355 of 383 image sets from the game:
[https://yadi.sk/d/0yjSKVoRJoVScg](https://yadi.sk/d/0yjSKVoRJoVScg)

This is a multipage TIFF files, each file contains from 1 to hundreds of frames of animation.

The format of the frames is now researched. But there are still gaps in the animation info. And I need to develop the correct format for storing metadata so that images can be conveniently edited, but not lose this data.
## Post #36
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2018-11-20T21:56:11+00:00
- Post Title: Re: Septerra Core .DB files

Thanks for utility!

But got error with .NET Framework 4.7.2 probably:
## Post #37
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-12-09T23:43:34+00:00
- Post Title: Re: Septerra Core .DB files

Hello! Sorry for the long absence. I finally get back to work.

You did not build a dependent assembly or assembled using a different platform instead of x86.
## Post #38
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2018-12-12T23:37:53+00:00
- Post Title: Re: Septerra Core .DB files

[https://pastebin.com/jRvGkYQH](https://pastebin.com/jRvGkYQH)
Finally, I found animation processor.
## Post #39
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-02-07T23:40:49+00:00
- Post Title: Re: Septerra Core .DB files

The way to success. Yippee, her eyes are shining! ^^

...and no more .an files in the data folder!


In fact, I have a little doubt about the selected container.
To edit TIFF, I had to use Multi-Page TIFF Editor + MSPaint + to configure it so that it does not change the color mode, and when it is saved it kills the preview image. 
Is the PSD file the best option? But I still need to save the meta information. Now I store it as XML inside TIFF.
## Post #40
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-02-10T14:47:29+00:00
- Post Title: Re: Septerra Core .DB files

It's done! The first release is available now:
[https://github.com/Albeoris/Septerra/re ... 2019.02.10](https://github.com/Albeoris/Septerra/releases/tag/v2019.02.10)

When run without archives, movies do not work. Will correct next time. Crashes are possible. Editing .tiff is very difficult, as I wrote earlier. Apparently, we will have to write a separate editor for animation, integrated with Photoshop. >_>
## Post #41
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-02-16T11:30:03+00:00
- Post Title: Re: Septerra Core .DB files

The new release is available:
[https://github.com/Albeoris/Septerra/re ... 2019.02.16](https://github.com/Albeoris/Septerra/releases/tag/v2019.02.16)
Game can load and play extracted movies.
Can convert VSSF to MP3 and load it directly in-game.
BAT-files has been renamed to:
ConvertAudio-Mp3-to-Vssf.bat
ConvertAudio-Vssf-to-Mp3.bat
## Post #42
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2019-02-20T01:26:07+00:00
- Post Title: Re: Septerra Core .DB files

Good evening Albeoris!

Thank you very much for dedicating your time to edit the game files but in the steam version it did not work!

No complaint, just informing!
## Post #43
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2019-09-21T23:12:58+00:00
- Post Title: Re: Septerra Core .DB files

The new release is available:
[https://github.com/Albeoris/Septerra/re ... 2019.09.22](https://github.com/Albeoris/Septerra/releases/tag/v2019.09.22)
Turn-based system: press F to skip waiting in a battle.
Now the game looking for the DLL in the correct location.

Also there is a huge update in the file description.
Some misstakes has been fixed. Now we have enough information to extract backgrounds of locations (not supported yet).
[https://github.com/Albeoris/Septerra/tr ... 0Templates](https://github.com/Albeoris/Septerra/tree/master/010%20Templates)
