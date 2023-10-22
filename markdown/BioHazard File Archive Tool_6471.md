## Post #1
- Username: MeganGrass
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 21, 2011 2:47 am
- Post datetime: 2011-04-20T19:10:29+00:00
- Post Title: BioHazard File Archive Tool

EDIT (March 22, 2022): This version of BioFAT is outdated and support for non-RE/BH (Resident Evil/BioHazard) games was dropped. Furthermore, I have not worked on this app for nearly ten years now.

A later iteration of this tool is now archived on my GitHub (reboot.exe):
[BioHazard File Archive Tool (Archive) @ GitHub](https://github.com/MeganGrass/Bio-Apps)

Sadly, this particular version of BioFAT was made while I was teaching myself C/C++ and it wasn't very stable. Fortunately, I still have the source code for this app and all variations, so if you need support, don't hesitate to reach out to me on [Twitter](https://twitter.com/MeganPuddin) or shoot me a PM here (I will get an email notification) and I will try to work something out 

ORIGINAL:

Hello,

I have been developing an application that extracts, repacks and modifies data for many different games. It started out as a utility for Bio Hazard | Resident Evil games, but I have since expanded it to support others, as well.

Currently supported:

3Xtreme [PSone]
(*.ANM;*.CMP;*.GUY;*.IMG;*.INF) - Archive File Extraction

Area 51 [PSone]
(*.ELF) - Archive File Extraction

Bio Hazard Zero | Resident Evil Zero [GameCube/Wii]
(*.ARC) - Archive File Extraction, Archive File Creation (de/compression is not yet supported)
(*.EFS) - Archive File Extraction
(*.MHP) - Archive File Extraction and automatic encoding of each *.THP to *.JPG
(*.THP) - Encoding to *.JPG (Trial Edition is not yet supported)
(*.TPP) - Archive File Extraction, Archive File Creation

Bio Hazard Rebirth | Resident Evil Remake [GameCube/Wii]
(*.DAT) - Archive File Extraction
(*.EMD) - Archive File Extraction
(*.EMG) - Archive File Extraction
(*.SND) - Archive File Extraction; allows for use of BGM+SFX in BH/RE Zero video game

Bio Hazard | Resident Evil [PSone/Saturn/PC]
(*.EMD) - Archive File Extraction, Archive File Creation
(*.EMW) - Archive File Extraction, Archive File Creation
(*.IVM) - Archive File Extraction, Archive File Creation
(*.PAK) - Image Compression, Image Decompression, Image Viewer (Credit for de/compression code: Patrice Mandin)
(*.RDT) - Archive File Extraction (work in progress)

Bio Hazard 2 | Resident Evil 2 [PSone/DreamCast/GameCube/PC]
(*.ADT) - Data Compression, Data Decompression, Image Viewer (Credit for de/compression code: Patrice Mandin, Mark Grass, gamezelda)
(*.BIN) - Archive File Extraction, Archive File Creation
(*.BSS) - Archive File Extraction, Archive File Creation
(*.EMD) - Archive File Extraction, Archive File Creation
(*.EMS) - Archive File Extraction, Archive File Creation (limited version support)
(*.MD1) - Decoding to Sony PSone format [*.TMD;*.RSD], Encoding to CAPCOM format [*.MD1]
(*.MSG) - Decoding to *.TXT, Encoding to *.MSG
(*.PLD) - Archive File Extraction, Archive File Creation
(*.PLW) - Archive File Extraction, Archive File Creation
(*.RDT) - Archive File Extraction, Archive File Creation
(*.BIOHAZARD2;*.RESIDENT2) Save Game File Assembly, Save Game File Disassembly
(*.SCD) - Game Script Disassembly (includes definitions of deciphered opcodes)

Bio Hazard 3: Last Escape | Resident Evil 3: Nemesis [PSone/DreamCast/GameCube/PC]
(*.ARD) - Archive File Extraction
(*.BSS) - Archive File Extraction, Archive File Creation
(*.EMD) - Archive File Extraction, Archive File Creation
(*.MD2) - Decoding to Sony PSone format [*.TMD;*.RSD]
(*.MSG) - Decoding to *.TXT, Encoding to *.MSG
(*.PLD) - Archive File Extraction, Archive File Creation
(*.PLW) - Archive File Extraction, Archive File Creation
(*.RBJ) - Archive File Extraction, Archive File Creation
(*.RDT) - Archive File Extraction (work in progress)

Bio Hazard 4 | Resident Evil 4 [GameCube/Wii/PS2/PC]
(*.DAS) - Archive File Extraction, Archive File Creation
(*.DAT) - Archive File Extraction, Archive File Creation
(*.DRS) - Archive File Extraction, Archive File Creation (Stage files | de/compression is not yet supported)
(*.EVD) - Archive File Extraction

Bio Hazard Gun Survivor 4: Heroes Never Die | Resident Evil Dead Aim [PS2]
(*.FPK) - Archive File Extraction

Brave Fencer Musashi [PSone]
(*.CD) - Archive File Extraction

C - The Contra Adventure [PSone]
(*.SGG) - Archive File Extraction

Celebrity Deathmatch [PSone]
(*.BOO) - Archive File Extraction

Dave Mirra Freestyle BMX [PSone]
(*.ZAL) - Archive File Extraction

Dino Crisis [PSone]
(*.DAT) - Archive File Extraction

Driver [PSone]
(*.BLK) - Archive File Extraction
(*.LEV) - Archive File Extraction

Fatal Fury: Wild Ambition [PSone]
(GAME.DAT) - Archive File Extraction

Fear Effect [PSone]
(*.WAD) - Archive File Extraction

Fear Effect 2: Retro Helix [PSone]
(*.WAD) - Archive File Extraction

Lunar Silver Star Story Complete [PSone]
(*.FIL) - Archive File Extraction
(*.SND) - Archive File Extraction

Mat Hoffman's Pro BMX [PSone]
(*.WAD) - Archive File Extraction

Rockman 8: Metal Heroes | Mega Man 8 [PSone]
(*.PAC) - Archive File Extraction

Rockman Complete Works | Mega Man Anniversary Collection [PSone/PS2/GameCube]
(*.PAC) - Archive File Extraction (work in progress)

Rockman DASH | Mega Man Legends [PSone]
(*.BIN) - Archive File Extraction (work in progress)

Rockman X4 | Mega Man X4 [PSone]
(*.ARC) - Archive File Extraction

Rockman X5 | Mega Man X5 [PSone]
(*.DAT) - Archive File Extraction

Rockman X6 | Mega Man X6 [PSone]
(*.DAT) - Archive File Extraction

MDK [PSone]
(*.WAD) - Archive File Extraction

Metal Gear Solid [PSone]
(*.DIR) - Archive File Extraction

Overblood [PSone]
(*.ROM) - Archive File Extraction

Saga Frontier [PSone]
(*.ARC) - Archive File Extraction

Street Fighter EX plus Alpha [PSone]
(*.PAC) - Archive File Extraction

Street Fighter EX2 plus [PSone]
(*.PAC) - Archive File Extraction

Super Puzzle Fighter II Turbo [PSone]
(*.EMI) - Archive File Extraction

Syphon Filter [PSone]
(*.FOG) - Archive File Extraction
(*.HOG) - Archive File Extraction

Time Crisis [PSone]
(*.FHM;*.FHT) - Archive File Extraction

Tony Hawk's Pro Skater [PSone]
(*.WAD) - Archive File Extraction

Tony Hawk's Pro Skater 2 [PSone]
(*.WAD) - Archive File Extraction

Tony Hawk's Pro Skater 3 [PSone]
(*.WAD) - Archive File Extraction

Tony Hawk's Pro Skater 4 [PSone]
(*.WAD) - Archive File Extraction

CRI Middleware
(*.AFS) - Archive File Extraction

Sony PSone
TIM Splitter - Extracts multiple *.TIM files from a single *.TIM - the *.TIM must have multiple CLUTs
TIM Viewer
TIM Converter - Convert a *.TIM to *.BMP (4bpp is not supported)
TMD-to-RSD Conversion - Convert a *.TMD file to Sony Psone ASCII 3D model development format (*.RSD)

Nintendo GameCube/Wii
(*.BTI) - Decode texture to *.DDS format (Credit for code: thakis)
(*.RARC) - Archive File Extraction (Credit for code: thakis)
(*.THP) - Video and Audio player (using thakis' thpplay 1.5)
(*.TPL) - Decode to *.TGA w/MTL (Using dev/ghostline's 'txdumper' and/or Gcube's 'tplx')
(*.YAY0) - Archive File Extraction and Decompression (Credit for decompression code: thakis)
(*.YAZ0) - Archive File Extraction Compression and Decompression (Credit for de/compression code: thakis, shevious/daegunlee)

Patrice Mandin's Reevengi Tools
adt2img
extract_bin
file2pak
pak2tim
pix2bmp
ptc2bmp
rgb2bmp
rofs (Extract *.DAT archive files from BH/RE 3 for PC)
sld (Decompress *.TIM texture archive from BH/RE 3 for PC)

Segher Boessenkool's Wii Tools
tpl2ppm


You can find more information and downloads at my site, here:

[BioHazard File Archive Tool (Archive) @ GitHub](https://github.com/MeganGrass/Bio-Apps)
## Post #2
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2011-05-06T14:53:24+00:00
- Post Title: BioHazard File Archive Tool

Hello Markgrass, I appreciate this tool and the time you put into it.

My question is will it (or does it) also work with vista?

I installed the necessary dll files but I get a error that prevents the program from running  (I get Biofat.exe error "The application failed to initialize properly (0xc0000142). Click ok to terminate the application.") and without the use of DDRAW.dll (from the common folder), the program runs but, with some errors (4 repeated errors "An unknown error occured during Device Discovery")... yet though it appears to work, it crashes when try to extract data from a bh4/re4 drs file with it. 

It seems that the Microsoft Visual C++ 2010 Redistributable Package (x86) and Sp1 work without a issue (on the MS site, it does mention compatibility with Vista SP2... so it seems to be a issue with the above mentioned DDRAW.dll; any help is appreciated in this matter.

Jodan
## Post #3
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-05-06T20:39:50+00:00
- Post Title: BioHazard File Archive Tool

Mark, i tried contacting you over at the-horror, as well as on skype/im, as i have the same problem as well.  Considering the fact that i actually code with Visual Studio 2005 - 2010, and as such have both the end-user and debug runtimes installed, it makes me wonder what the incompatibility could be.

Would be glad to help with further testing to determine the problem.
## Post #4
- Username: MeganGrass
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 21, 2011 2:47 am
- Post datetime: 2011-05-07T04:15:02+00:00
- Post Title: BioHazard File Archive Tool

> Hello Markgrass, I appreciate this tool and the time you put into it.

Thank You. 

> My question is will it (or does it) also work with vista?
>
> 
>
> I installed the necessary dll files but I get a error that prevents the program from running (I get Biofat.exe error "The application failed to initialize properly (0xc0000142). Click ok to terminate the application.") and without the use of DDRAW.dll (from the common folder), the program runs but, with some errors (4 repeated errors "An unknown error occured during Device Discovery")... yet though it appears to work, it crashes when try to extract data from a bh4/re4 drs file with it.
>
> 
>
> It seems that the Microsoft Visual C++ 2010 Redistributable Package (x86) and Sp1 work without a issue (on the MS site, it does mention compatibility with Vista SP2... so it seems to be a issue with the above mentioned DDRAW.dll; any help is appreciated in this matter.
>
> 
>
> Jodan

I had previously ran into a compatibility issue with Vista and 7 (I develop and compile on XP), but those problems have since been fixed, as I have added DX10(Vista) and DX11 (Win7) support.

See below for a status update.

> Mark, i tried contacting you over at the-horror, as well as on skype/im, as i have the same problem as well. Considering the fact that i actually code with Visual Studio 2005 - 2010, and as such have both the end-user and debug runtimes installed, it makes me wonder what the incompatibility could be.
>
> 
>
> Would be glad to help with further testing to determine the problem.

Hmm... i'm sorry, my password for THIA, credit card, etc info was recently stolen; I haven't received your contact attempt.

To the point, here's a small status update which address the issues:

I have smashed the "A referral was returned from the server." bug that was caused by using an improper manifest.

The "The application failed to initialize properly (0xc0000142). Click ok to terminate the application." bug was smashed.

I added multi-OS support, eliminating the need for separate builds. XP, Vista, 7 and Windows Server versions are supported.

Multi-OS support means no more "Use in Compatibility Mode" issues that have plagued Vista and 7 users.

With the addition of multi-OS support comes multi-version Direct X support, including versions 9 (WinXP), 10 (Vista) and 11 (Win7). Be sure to have the latest Redistributable Pack installed.

The "An unknown error occurred during device discovery" and "An unknown error occurred during DirectX Creation" errors have been fixed for Vista and 7.

A lot of commandline features have been added; there's no need for the GUI, unless desired.



I should have a new build online, soon.
## Post #5
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2011-05-07T04:31:19+00:00
- Post Title: BioHazard File Archive Tool

This is excellent news, very cool; I await the update then... 

When I get the new version, I will run it through a number of the program options and let you know how it works out.

thanks again
## Post #6
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2011-05-14T09:20:25+00:00
- Post Title: BioHazard File Archive Tool

It is extremely useful tool!   
Recently I was looking for tools that can read thps1-3 ps1 .wad files, found only dead links, wadsplit for thps1 and your tool.
Well, I have some problems. I use WinXP sp3, .NET Framework 3.5 and C++ Redistributable 2008 are both installed, DLLs are in BIOFAT folder, but, as mentioned above, it says "An unknown error occured during Window Discovery". Whatever, menu works.
So I choose "expand wad" for thps3 and it returns only CDxxx.BIN files. Is it possible to see original filenames instead of bin files and is it in your plans to add "repack wad" for thps1-4?
## Post #7
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2011-06-18T23:07:51+00:00
- Post Title: BioHazard File Archive Tool

The link seems to be dead...
## Post #8
- Username: MeganGrass
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 21, 2011 2:47 am
- Post datetime: 2011-06-23T18:14:21+00:00
- Post Title: BioHazard File Archive Tool

The [latest] source code is now available.

[BioHazard File Archive Tool (@SourceForge.net)](http://sourceforge.net/projects/biofat/)

[Browse SVN](http://biofat.svn.sourceforge.net/viewvc/biofat/)

[Checkout](https://biofat.svn.sourceforge.net/svnroot/biofat)

> So I choose "expand wad" for thps3 and it returns only CDxxx.BIN files. Is it possible to see original filenames instead of bin files and is it in your plans to add "repack wad" for thps1-4?

IIRC, only a few THPS games actually contained an original filename list... sorry; there's no way of knowing what they are supposed to be named. And, yes, I plan to add repacking functions for all file types.
## Post #9
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-06-26T22:49:18+00:00
- Post Title: BioHazard File Archive Tool

this is great!! I've been waiting for old biohazard stuff to come around
## Post #10
- Username: MiLOxentax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 26, 2010 10:39 am
- Post datetime: 2011-06-28T12:46:46+00:00
- Post Title: BioHazard File Archive Tool

This looks like an amazing application for all biohazard fans. Thank you MarkGrass, your efforts are much appreciated.

Unfortunately I am also having issues running it under Vista. The DLLs are in the same folder with BIOFAT.exe but once I try to launch the app - it gives an error ""A referral was returned from the server." 
So far I haven't found a solution to this, but will see and maybe future release will be more compatible. 

Once again, great job and good luck!
## Post #11
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-04-10T01:18:43+00:00
- Post Title: BioHazard File Archive Tool

this tool works amazingly well i got it working for some unsupported games. however I can only run the program on my old 32-bit vista pc which had very low specs is their a way to run it on my newer faster 64-bit 7 pc?
## Post #12
- Username: MeganGrass
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 21, 2011 2:47 am
- Post datetime: 2012-04-21T00:14:05+00:00
- Post Title: BioHazard File Archive Tool

SVN 2 is finally online...

[source](http://biofat.svn.sourceforge.net/viewvc/biofat/?view=tar)
[exe](https://sourceforge.net/projects/biofat/files/latest/download?source=files)

Support for non-XP OS has been added.
## Post #13
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-04-29T12:42:14+00:00
- Post Title: BioHazard File Archive Tool

thats great i'd love to try when my regular pc is up and running
## Post #14
- Username: person123456
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 03, 2011 11:21 am
- Post datetime: 2012-05-09T02:31:23+00:00
- Post Title: BioHazard File Archive Tool

hey mark grass how do u make this work? If i just run the exe it the process starts then shuts down immediately with no errors and the commandline functions are limited (I'm trying to extract RE:Remake .snd sound files). Anyone have this problem? attempting to drag and drop .snd files on top of the exe also does nothing. Sorry for being noob if its smtn obvious...
## Post #15
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-05-22T22:22:47+00:00
- Post Title: BioHazard File Archive Tool

I keep getting "this application was unable to start correctly 0xc00007b" you know how I could fix this?
## Post #16
- Username: MeganGrass
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 21, 2011 2:47 am
- Post datetime: 2014-05-07T13:55:30+00:00
- Post Title: Re: BioHazard File Archive Tool

...biofat is still alive, forgive me for neglecting to report updates to this thread.  

The application is now hosted RHDN.NET, linked below:

[http://www.romhacking.net/utilities/1019/](http://www.romhacking.net/utilities/1019/)


Only BioHazard // Resident Evil games are supported, now... but I still have sources for other games. If anyone needs something specific, just drop me a PM.

In addition, all OS compatibility issues have been smashed and are now non-existent - no more crashes in Vista, Win7, etc (personally tested in both x86 and x64 bit versions).
## Post #17
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-05-20T01:32:09+00:00
- Post Title: Re: BioHazard File Archive Tool

Hey, good it's still alive. I downloaded the source code quite some time ago and learned a couple things.
I couldn't make it work with wine, probably I'm missing libraries. No more source sharing, though? [http://biofat.sourceforge.net/](http://biofat.sourceforge.net/)
## Post #18
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-06-21T15:54:17+00:00
- Post Title: Re: BioHazard File Archive Tool

Hi mark,good program you have  i just want to know,does it support resident evil 1,2,3 pc version??or this is just console only?
## Post #19
- Username: feareffectinferno
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 13, 2011 1:43 am
- Post datetime: 2015-05-31T18:16:24+00:00
- Post Title: Re: BioHazard File Archive Tool

Hi, does somehave still have the Fear Effect WAD extractor version from that tool or knows how to contact Mark Grass ? He disappeared !
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-06-01T03:25:35+00:00
- Post Title: Re: BioHazard File Archive Tool

Try [this one](http://www.mediafire.com/download/6597al60vz2r3vm/biofat_svn06232011.zip).

Mark posted just last month on the-horror.com regarding his archive tool
[http://www.the-horror.com/forums/showth ... post275118](http://www.the-horror.com/forums/showthread.php?8052-BioHazard-File-Archive-Tool&p=275118&viewfull=1#post275118)
## Post #21
- Username: keridian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 19, 2010 9:38 pm
- Post datetime: 2015-07-01T08:25:57+00:00
- Post Title: Re: BioHazard File Archive Tool

Does anyone have the RE:Dead Aim supported version of this software?
Can't get it anywhere!
## Post #22
- Username: UltimateXeallar
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 27, 2015 3:30 am
- Post datetime: 2015-08-22T21:22:14+00:00
- Post Title: Re: BioHazard File Archive Tool

Guess this is a good place to ask...
Anyone know of the version of this tool that supports the Archives from Megaman X5/X6's DAT files?
If the OP's post is anything to go by, it seems there was a program/script/whatever that was able to handle those.
(For the record, apparently the formats for those DAT files are similar to the game Shrek 2, for the PS2?  small world...though apparently the script for that game doesn't extract anything useful.)
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-23T01:21:33+00:00
- Post Title: Re: BioHazard File Archive Tool

Is my previous post invisible or do people just give up after looking at the first post?   

lets try it again

> Reply from AceWell
>
> Try this one.
## Post #24
- Username: UltimateXeallar
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 27, 2015 3:30 am
- Post datetime: 2015-08-23T02:37:49+00:00
- Post Title: Re: BioHazard File Archive Tool

Interesting problem with opening the EXE, apparently I get this error:

Hrm, no idea what this means.  I did try to get a DLL called that elsewhere, that didn't work out for me too well.
EDIT: Feel like it's worth noting that I'm running Windows 10
## Post #25
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-23T02:57:04+00:00
- Post Title: Re: BioHazard File Archive Tool

I don't know anything about Windows 10 or if it will even work on that OS, but i use the sdl.dll from the Blender 2.49 zip to make it run.
## Post #26
- Username: pecel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2016 5:09 pm
- Post datetime: 2016-08-22T04:13:09+00:00
- Post Title: Re: BioHazard File Archive Tool

I need something to extract FHM file. I already download biofat.exe, but there's no FHM on selection. Is that file no longer supported? Please help
## Post #27
- Username: RadeonX1950
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 21, 2010 3:28 pm
- Post datetime: 2016-12-11T22:30:19+00:00
- Post Title: Re: BioHazard File Archive Tool

> Reply from AceWell
>
> Try this one.

Mark posted just last month on the-horror.com regarding his archive tool
http://www.the-horror.com/forums/showth ... post275118
DAS - Extract (Stage) for Resident Evil 4/Biohazard 4 doesn't work in this version. Is there any other version of BioFAT that does work with those files?
## Post #28
- Username: Amuroray
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 13, 2022 9:54 pm
- Post datetime: 2022-02-13T13:57:24+00:00
- Post Title: Re: BioHazard File Archive Tool

I want to replace the spanish language in the japanese iso of the gamecube, but I'm not sure about the language files, I know the files and maps, but I also want to know the sources to be able to change
