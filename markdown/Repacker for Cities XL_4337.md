## Post #1
- Username: gfred
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 15, 2010 6:36 pm
- Post datetime: 2010-04-15T18:28:01+00:00
- Post Title: Repacker for Cities XL

Hello all,

I come to you for a request: 
After the success of the Forum to unpack the .Pak files (I thank you for this excellent work) of the Game Cities XL ([viewtopic.php?f=10&t=3544](http://forum.xentax.com/viewtopic.php?f=10&t=3544)), I tried to make a repacker to be able to realize some mods for the Game.
I tried to do it using the BMS extraction script but I'm not a programmer (I work in advertising) so I have obtained no results. (And most BMS commands are Chinese for me)

The bytes having no secret for you, I humbly ask if you could not try to create a repacker for the game ?

PS: there are already repacker, unfortunately the people who own them do not want to share or distribute.They keep it like the Holy Grail.

You can find the game files in this topic [viewtopic.php?f=10&t=3544](http://forum.xentax.com/viewtopic.php?f=10&t=3544)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-15T20:27:59+00:00
- Post Title: Repacker for Cities XL

> PS: there are already repacker, unfortunately the people who own them do not want to share or distribute.They keep it like the Holy Grail.
yeah exist lot of those idiots that are very happy to ask here and there and have big "eyes" when they look at the code/scripts of other people to avoid to spend time on reversing (because they aren't able to do it pfff) or looking for support forcing other people to waste their time for them but then... then they adopt an atypical meaning of the word "sharing":
- sharing from the world to them = sure at full hands
- sharing from them to the world = ops, closed hands (aka "take take take, no give")

well I have taken this thread to explain my position on this matter because obviously this is not the first time that something similar happens, it's enough to read the current last posts in the Avatar and the other CitiesXL thread as most recent examples (and casually both are about games for which I wrote the only public unpackers).
so sorry for the OT but was necessary because I don't like that the wheel is reinvented 1000 times, and is not important if this is something that doesn't interest or touch me (because I have no direct interest in all these games).

returning in topic I already know Fred but I can't help him since my policy is to write only unpackers because they are the only thing I like and do for fun.
## Post #3
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-04-24T04:49:32+00:00
- Post Title: Repacker for Cities XL

Well, aluigi did the hard work with the DirTable decrypter.
That can be used with minimal change to ENCODE The new DirTable!
So it's theoretically possible to write the PAK MAKER proggy.
I'w working on it. (The source code will be FREE! I'm not familiar with C, so I use Delphi)
But I found some unknown bytes:
20 bytes in the Header
20 bytes for each file in the DirTable.
What are these exactly? Maybe some hash values. But how to calculate them?
The calculation code is surely hidden somewhere in the game's core.dll,
but I did't find it yet.
Any idea?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-24T10:51:06+00:00
- Post Title: Repacker for Cities XL

as already said I guess it's the sha1 hash.
to know on which it's calculated you must do some tests for example first verifying the one you see in each file entry with the archived and the extracted file.
if it's the same (I guess it's the one of the extracted file) the job is done.
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-04-24T22:40:40+00:00
- Post Title: Repacker for Cities XL

Yes! The DirTable stores the SHA-160 sum of the original (unpacked) files!
Now we are one step closer to the end!
## Post #6
- Username: dakutis
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 13, 2009 11:11 pm
- Post datetime: 2010-04-25T08:03:39+00:00
- Post Title: Repacker for Cities XL

> Reply from bacter
>
> Yes! The DirTable stores the SHA-160 sum of the original (unpacked) files!
Now we are one step closer to the end!

Many of the player is waiting for your result, I am one of them   We believe that you can do it, and that you give us the ability to modify this game.
## Post #7
- Username: RexHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2010 3:19 pm
- Post datetime: 2010-04-26T16:31:16+00:00
- Post Title: Repacker for Cities XL

I think this is something you want.
You'll need .Net Framework 3.5.


 CitiesXLLocBin.rar
(207.88 KiB) Downloaded 50 times



The hash is ignored in this version.
Maybe it shall be recalculated.
## Post #8
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-04-26T18:53:19+00:00
- Post Title: Repacker for Cities XL

Meanwhile I created a very primitive PAK extractor / maker.

Now I replaced the PAK maker with a new, slightly modified version!
(The final version, with source code is coming soon!)

Now, this is another, bugfixed, the Almost-Final-Version!

[The attached file deleted! See my latest post for the newest version.]
## Post #9
- Username: RexHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2010 3:19 pm
- Post datetime: 2010-05-06T17:26:29+00:00
- Post Title: Repacker for Cities XL

Ignore this... repeated post.
## Post #10
- Username: RexHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2010 3:19 pm
- Post datetime: 2010-05-06T17:26:51+00:00
- Post Title: Repacker for Cities XL

Ignore this... repeated post.
## Post #11
- Username: RexHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2010 3:19 pm
- Post datetime: 2010-05-06T17:28:03+00:00
- Post Title: Repacker for Cities XL

The SHA-1 calculating is handled in the new version.


 CitiesXLLocBin.rar
(247.01 KiB) Downloaded 51 times


Sorry for not localizing the GUI tool to English.
The command line PackageManipulator.exe is in English.
The GUI PackageManager.exe is simply drag and drop, except that you need to use File(F)-Open(O) to open the package.

en..
This time it requires .Net Framework 4.0.
## Post #12
- Username: RexHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2010 3:19 pm
- Post datetime: 2010-05-06T17:28:03+00:00
- Post Title: Repacker for Cities XL

The source is here.


 CitiesXLLocSrc.rar
(238 KiB) Downloaded 42 times


Sorry for many repeated posts caused by slow connection.
## Post #13
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-05-15T17:25:07+00:00
- Post Title: Repacker for Cities XL

Here's my PAK maker/extractor with delphi source code.

[The attached file deleted! See my latest post for the newest version.]
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-15T22:56:06+00:00
- Post Title: Repacker for Cities XL

Nice work!
## Post #15
- Username: arcadoli
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 01, 2010 2:09 pm
- Post datetime: 2010-05-30T20:16:39+00:00
- Post Title: Repacker for Cities XL

Hi all,

I've programmed a complete tool for pak/unpak, import/export cities / new map, file explorer, etc.
I'm about to finish english localization of the tool, and some minor corrections.
I will post a link here when finished.
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:31:04+00:00
- Post Title: Re: Repacker for Cities XL

Cool! Why not upload it at the Tools Blog as well?  [blog](http://forum.xentax.com/blog)
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:32:24+00:00
- Post Title: Re: Repacker for Cities XL

Cool! Why not post it at the [blog](http://forum.xentax.com/blog) as well?
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:39:35+00:00
- Post Title: Re: Repacker for Cities XL

Interesting!
## Post #19
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2010-05-30T20:44:11+00:00
- Post Title: Re: Repacker for Cities XL

test
## Post #20
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2010-05-30T20:47:20+00:00
- Post Title: Re: Repacker for Cities XL

test2
## Post #21
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2010-05-30T20:48:31+00:00
- Post Title: Re: Repacker for Cities XL

test3 this is very weird

ignore me please, there's something odd going on in this thread.
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:48:57+00:00
- Post Title: Re: Repacker for Cities XL

Test4 ignore me as well
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:50:12+00:00
- Post Title: Re: Repacker for Cities XL

This thread has posts not visible with normal view. if you click Reply you will see them. Very, very odd.
## Post #24
- Username: jeremy12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 01, 2010 2:45 am
- Post datetime: 2010-06-03T03:43:09+00:00
- Post Title: Re: Repacker for Cities XL

With the Great Code base from bacter i have created a Application with a nice UI that even uses language configuration files so it can be localized.

You can find and download the application (and source) Over on Google Projects at [http://code.google.com/p/citiesxlextractor/](http://code.google.com/p/citiesxlextractor/)
There is also a Issue Tracker so if you have any issues please post it there or in this thread.

I started the project originally as a extractor and with the recent repackager code surfacing i have included it
## Post #25
- Username: arcadoli
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 01, 2010 2:09 pm
- Post datetime: 2010-06-12T16:18:20+00:00
- Post Title: Re: Repacker for Cities XL

Hi all,

With a big thanks to Xentax forum which make this possible,
here is Cities Xl PakUnpak, the first public release.

Link : [http://www.generation-city.com/citiesxl ... glish.html](http://www.generation-city.com/citiesxl/pakunpak/English.html)

Features 
•Unpak of a file or of a folder of Pak, Patch, Lvl, Sol, Sgbin files.
•Pak of a folder data\... in a Patch file.
•Unpak of a SGBIN file with automatic conversion of MC-DDS files into DDS standards and editable.
•Duplication of objects thanks to the compression SGBIN which redeploys DDS to MC-DDS and offers you to enter a new name for the object. You can so duplicate an object, change its textures and its properties.
•Explorer allows you to show all unpaked data in the preview window. It shows game graphics and texts with the possibility to configure external editors (text and graphic) to edit them more easily with a simple right click. 
•Export / Backup of your cities (Save game) with creation of a text file which contains the list of your mods installed to return easier the distribution of your city online. (If a mod was used for a city, it will be necessary on another computer to open this city) 
•Import: up to 10 cities are possible to be imported on Slots added for this occasion to not replace the official maps. A (playable) map "Plat-Pays" was added with that end in view, two by region for firsts 5 regions. It is on these maps that will be imported cities.
•This help file which will become rich progressively, with tutorials..
•A link "Check for updates"  
•Other improvements will follow: (Easy Addition of new maps (9 maximum) in the region "Generation City", ...



Thank you for your interest.

Arcadoli
## Post #26
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-12T11:31:03+00:00
- Post Title: Re: Repacker for Cities XL

I tried Cities Xl PakUnpak and crashes unpacking and packing and needs .Net 4..

Anyway i found another tool to extract and repack, with license GPL 3
[http://code.google.com/p/citiesxlextractor/](http://code.google.com/p/citiesxlextractor/)

@bacter
It's possible to make the tool in command line? or create a batch process?
Thanks!
## Post #27
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-12T15:22:13+00:00
- Post Title: Re: Repacker for Cities XL

Here is a very simple command line util for making or extracting the citiesXL .pak files. (Delphi source code included.)

```
Make   :         citiesXL_PAK_util.exe M <SourceDir> <PAK_File>
Extract:         citiesXL_PAK_util.exe E <PAK_File> <TargetDir>
     or:         citiesXL_PAK_util.exe X <PAK_File> <TargetDir>
```

[The attached file deleted! See my latest post for the newest version.]
## Post #28
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-12T16:11:43+00:00
- Post Title: Re: Repacker for Cities XL

Cool i will try, any special switch for compression mode? i saw: 0 1 and 2 in the source code..
## Post #29
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-13T06:01:29+00:00
- Post Title: Re: Repacker for Cities XL

O.K. I modified the program. The available commands:
E or X = Extract 
M0 = Make, NO ZLIB compression
M1 or M = Make, use ZLIB cleverly
M2 = Make, alvays use ZLIB, even if the compressed data is bigger, than the original.

[The attached file deleted! See my latest post for the newest version.]
## Post #30
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-13T11:24:15+00:00
- Post Title: Re: Repacker for Cities XL

Thanks!!   nice tool and small, cool.
## Post #31
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-20T15:56:01+00:00
- Post Title: Re: Repacker for Cities XL

Some files (sgbin) can't be unpacked, i attach a file:
[x_ma_glass00.sgbin - 0.19MB](http://www.zshare.net/download/79542027bc6969b8/)
And the error:

> -----------------------------------------------------------------------------
>
>  Cities XL .PAK file Maker/eXtractor v0.2
>
>  Created by The Bacter
>
>  -----------------------------------------------------------------------------
>
> 
>
> -> generating the file list...: O.K.
>
>  Sorry, but some error occured
## Post #32
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-20T19:41:24+00:00
- Post Title: Re: Repacker for Cities XL

O.K. I solved the problem.
The Header.Version of this new file is: 2. (The others' were: 3)
This means, that the directory data is not encrypted in this file.
Here are my modified programs. (Both the graphical and the commandline version.)
[citiesXL_PAK_maker_v1_10_BACTER.rar](https://xentaxbackup.github.io/file/3359_citiesXL_PAK_maker_v1_10_BACTER.rar)
## Post #33
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-20T21:54:01+00:00
- Post Title: Re: Repacker for Cities XL

Thanks for the changes!! Let's to test!!
## Post #34
- Username: vizipok
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jun 23, 2009 7:13 pm
- Post datetime: 2010-09-02T13:02:58+00:00
- Post Title: Re: Repacker for Cities XL

Cities XL uses unicode fonts, so I would like to create hungarian fonts for the game:
I decompiled font.fnt (it's in all_fnt.pak) with FontManipulator.exe (CitiesXLLocBin). 
A font.bmp and a font.fd (font description) was created.

But how to compile these files again?
## Post #35
- Username: vizipok
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jun 23, 2009 7:13 pm
- Post datetime: 2010-09-02T13:10:44+00:00
- Post Title: Re: Repacker for Cities XL

Cities XL uses unicode fonts, so I would like to create a hungarian font for the game.

Fonts are in all_fnt.pak file: font.fnt and debug.fnt
I decompiled font .fnt with CitiesXLLocBin (FontManipulator.exe): font.bmp and font.fd (font description).

How can I compile these two files again?
## Post #36
- Username: MediaWindowsIntel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 11, 2012 8:41 pm
- Post datetime: 2012-06-03T09:41:16+00:00
- Post Title: Re: Repacker for Cities XL

Hello Bacter, I want to know if I can include your program citiesXL_PAK_maker_v1_10_BACTER in lines of commandes (without the source code of course) in my program [Cities XL programme de modifications.7z](https://skydrive.live.com/?cid=7d380b04c7ddfb1e&resid=7D380B04C7DDFB1E!262&id=7D380B04C7DDFB1E%21262)? by quoting you and your pseudo course, with a link to this site.

And sorry but I Am French and I use google translator.
## Post #37
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-06-03T11:13:22+00:00
- Post Title: Re: Repacker for Cities XL

No problem. You can freely use my program if you want. I'm glad that you found it useful
## Post #38
- Username: MediaWindowsIntel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 11, 2012 8:41 pm
- Post datetime: 2012-06-22T12:28:14+00:00
- Post Title: Re: Repacker for Cities XL

Thank You
THX
Edit: Hello again, batcher, your program is a problem bug, create the files are not accepted by CitiesXLPakUnpak_v1.3.0 and Cities XL game. Invalid file, apparently. Ideas?

MediaWindowsIntel
