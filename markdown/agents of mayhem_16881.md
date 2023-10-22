## Post #1
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2017-08-18T10:40:16+00:00
- Post Title: agents of mayhem

Does anyone know if it is possible to extract this format vpp_pc
[https://www.saintsrowmods.com/forum/att ... _pc.16416/](https://www.saintsrowmods.com/forum/attachments/agents-of-mayhem-oni-vpp_pc.16416/)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-08-18T12:25:20+00:00
- Post Title: agents of mayhem

Same here.
## Post #3
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-08-26T11:04:04+00:00
- Post Title: agents of mayhem

At the forum "Saints Row Mods" there is a message that the game support is added. But only do not know how to convert all these files into a customary exe.
Topic forum -- [https://www.saintsrowmods.com/forum/thr ... ols.15550/](https://www.saintsrowmods.com/forum/threads/for-developers-in-progress-mod-tools.15550/)
Github - [https://github.com/saintsrowmods/Saints ... tsofmayhem](https://github.com/saintsrowmods/SaintsRowTools/tree/agentsofmayhem)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-27T06:58:14+00:00
- Post Title: agents of mayhem

i see some zlib compressed blocks in that sample, offzip seems to work   
the extracted dats seem to contain a model with LODs and one or more dxt textures that go with it



02c1a471_dat.png (66.56 KiB) Viewed 328 times
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-16T21:17:53+00:00
- Post Title: agents of mayhem

> Reply from VladlenCry
>
> At the forum "Saints Row Mods" there is a message that the game support is added. But only do not know how to convert all these files into a customary exe.
Topic forum -- https://www.saintsrowmods.com/forum/thr ... ols.15550/
Github - https://github.com/saintsrowmods/Saints ... tsofmayhem

Download Visual Studio 2015 or above ( Community addition is free )

Hit the download button from the github page and open the solution file in the root ( SaintsRowTools.sln)

Once this is open in Visual Studio right click the solution and select build

in the output window you will see the location where the exe's were build, use the RecursiveExtractor to  extract AoM ( I think)

T.
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-16T21:25:51+00:00
- Post Title: agents of mayhem

I just tried that, and as usual, ppl that use git are open source minded and know shit about ppl that just want a command line tool (.exe for those that didn't get it) or a ui tool that opens does the trick in stead of download gigabytes of tools and installing for hours and than noticing that the shit they just downloaded to build does not work!!!

Just like this dumb ass ThomasJepp!

T.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-09-16T21:49:07+00:00
- Post Title: agents of mayhem

Couldn 't even build, gave me a bunch of errors.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-16T22:00:04+00:00
- Post Title: agents of mayhem

I got it to build... :/ after 2 hours

Such a bad structure...

The problem I had was, when I hit the download button on the SaintsRowTools folder, it did not download everything, the most important thing did not download...

So you need to download the "ThomasJepp.SaintsRow @ 775a30f" folder seperatly, cause when you look at the initial folder "ThomasJepp.SaintsRow" it is empty :/

copy that content in the correct folder and tried to build it. I used Visual Studio 2013 and not 2017 as it is stated, so I had to update my Nuget Package Manager too...

after that, it got build.

I'm too tired at this moment so I will try to use the extractor on the AoM pack files... in the hope it works

T.
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-09-16T22:10:40+00:00
- Post Title: agents of mayhem

ahh damn yeah i will try that.
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-09-17T00:25:30+00:00
- Post Title: agents of mayhem

Tried to use the recursive extractor but im getting tis error

Unhandled Exception: System.IO.FileNotFoundException: Could not load file or assembly 'lz4.AnyCPU.loader, Version=1.0.9.0, Culture=neutral, PublicKeyToken=7aa3c636ef56b77f' or one of its dependencies. The system cannot find the file specified.
   at ThomasJepp.SaintsRow.Packfiles.Version11.PackfileEntry.GetStream()
   at ThomasJepp.SaintsRow.RecursiveExtractor.Program.Main(String[] args) in E:\SaintsRowTools-agentsofmayhem\ThomasJepp.SaintsRow.RecursiveExtractor\Program.cs:line 98


EDIT: Found the dll file 
Works now.
## Post #11
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-17T10:28:15+00:00
- Post Title: agents of mayhem

So you got everything extracted ?

Cause when I use 

ThomasJepp.SaintsRow.ExtractPackfile.exe "aom_agents.vpp_pc" "D:\aom_extracted"

it just gives me all errors

```

[2/17832] Extracting data\aom_agents\aom_agents_precache.vpp_pc... error!

[3/17832] Extracting data\aom_agents\audio\1000048190.wem_pc... error!

[4/17832] Extracting data\aom_agents\audio\1000144019.wem_pc... error!

[5/17832] Extracting data\aom_agents\audio\1000306152.wem_pc... error!

[6/17832] Extracting data\aom_agents\audio\1000611881.wem_pc... error!

[7/17832] Extracting data\aom_agents\audio\1000663643.wem_pc... error!

```


T.
## Post #12
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-09-17T11:24:31+00:00
- Post Title: agents of mayhem

> Reply from TaylorMouse
>
> 
Download Visual Studio 2015 or above ( Community addition is free )
Hit the download button from the github page and open the solution file in the root ( SaintsRowTools.sln)
Once this is open in Visual Studio right click the solution and select build
in the output window you will see the location where the exe's were build, use the RecursiveExtractor to  extract AoM ( I think)
T.
Thanks for explaining how to get the exe. At me extraction passes without errors.
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-09-17T12:26:31+00:00
- Post Title: agents of mayhem

> Reply from TaylorMouse
>
> So you got everything extracted ?

Cause when I use 

ThomasJepp.SaintsRow.ExtractPackfile.exe "aom_agents.vpp_pc" "D:\aom_extracted"

it just gives me all errors
Code: Select all[1/17832] Extracting data\aom_agents\aom_agents.vpkg... error!

[2/17832] Extracting data\aom_agents\aom_agents_precache.vpp_pc... error!

[3/17832] Extracting data\aom_agents\audio\1000048190.wem_pc... error!

[4/17832] Extracting data\aom_agents\audio\1000144019.wem_pc... error!

[5/17832] Extracting data\aom_agents\audio\1000306152.wem_pc... error!

[6/17832] Extracting data\aom_agents\audio\1000611881.wem_pc... error!

[7/17832] Extracting data\aom_agents\audio\1000663643.wem_pc... error!


T.

Use the recursive extractor and make sure you copy the lz4.anycpu.dll from one of the folders to the bin directory.

Also it sucks the audio/music files are in mono.
## Post #14
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-17T14:27:51+00:00
- Post Title: agents of mayhem

OK I tried the RecursiveExtractor, I got the some problem as OrangeC:

```
oken=7aa3c636ef56b77f' or one of its dependencies. The system cannot find the file specified.
   at ThomasJepp.SaintsRow.Packfiles.Version11.PackfileEntry.GetStream()
   at ThomasJepp.SaintsRow.RecursiveExtractor.Program.Main(String[] args)

```


You need to manually copy the lz4.AnyCPUloader.dll to the same folder as the build exe's


T.
## Post #15
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-17T16:45:12+00:00
- Post Title: agents of mayhem

OK, more errors occur, since I got a specific path to where to extract stuff, it runs into an error that tells me that the pathname is too long :/

this happens when a str2_pc file is written, don't know why there are like a billion concatinations done to create an autpath....

you need to change that... or at least I had to ( windows 7 user ) probably fixed in windows 10


T.
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-09-17T19:05:59+00:00
- Post Title: Re: agents of mayhem

You need to be on windows 10 and enable extended path names.
## Post #17
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-18T08:02:25+00:00
- Post Title: Re: agents of mayhem

Yeah, after some time, I decided to made my own content browser UI ( treeview / listview) to look at the content of the files before I extract anything.

I'm doing this in WPF, like I did with my 3D Model Viewer.

Once it is done I'll post it here for downloading as a working executable, not some pile of code to deal with before you can do anything...

The code to list the content and the extraction itself work already, just doing the UI atm. So it will be done pretty soon.

T.
## Post #18
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-19T20:48:38+00:00
- Post Title: Re: agents of mayhem

Ok my browser is finished, still need to polish of course, time to implement the extraction method



T.
## Post #19
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-19T22:27:41+00:00
- Post Title: Re: agents of mayhem

Ok, first tests seem to be working, 

double clicking the item in the list (or via right click and view) it plays the Bink Video ( I have Bink RAD tools installed to view these files )



extracting multiple files at once works too.

going to implement the extraction of a whole folder next

T.
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-20T08:44:32+00:00
- Post Title: Re: agents of mayhem

> Reply from AceWell
>
> i see some zlib compressed blocks in that sample, offzip seems to work   
the extracted dats seem to contain a model with LODs and one or more dxt textures that go with it
02c1a471_dat.png

Which file was that, if I may ask ?

T.
## Post #21
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-09-20T18:45:50+00:00
- Post Title: Re: agents of mayhem

added:
- implemented the extraction to the same folder structure as in the pack file
- possible to delete the original file after conversion
- support conversion of .wem_pc to .ogg

T.
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-20T23:35:51+00:00
- Post Title: Re: agents of mayhem

> Reply from TaylorMouse
>
> Which file was that, if I may ask ?
02c1a471.dat extracted with offzip
## Post #23
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-10-04T14:55:20+00:00
- Post Title: Re: agents of mayhem

Finally finished the small tool, note, NO you cannot extract everything at once, you need to go through the parts one by one

[Download the AgentsOfMayhem.ContentBrowser.](https://www.dropbox.com/sh/0jewnlkjztf3777/AAAHWKDTMg2_YuMhkM99hRjya?dl=0)

If anyone wants to help out on figuring out the 3D Models, please DO!

T.
## Post #24
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2017-10-05T12:01:12+00:00
- Post Title: Re: agents of mayhem

For some of the texture, I was able to provide a dds header and that seem to work out pretty well, others, not so much

I will try to implement this in my browser

example:
[hair_normal.png](https://xentaxbackup.github.io/file/13391_hair_normal.png)
## Post #25
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-25T02:33:03+00:00
- Post Title: Re: agents of mayhem

here is a bms script for fun to extract files from vpp_pc and str2_pc files  


 AgentsofMayhem_vpp_pc__str2_pc.zip
(696 Bytes) Downloaded 96 times
## Post #26
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2018-03-23T20:47:12+00:00
- Post Title: Re: agents of mayhem

I try script in aom_agents.vpp_pc but don't work

- open input file D:\GAMES\Agents.Of.Mayhem-CPY\aom\data\aom_agents\aom_agents.vpp_pc
- open script D:\GAMES\Agents.Of.Mayhem-CPY\aom\data\aom_agents\AgentsofMayhem_vpp_pc__str2_pc.bms
- set output folder D:\GAMES\Agents.Of.Mayhem-CPY\aom\data\aom_agents\folder

  offset           filesize   filename
--------------------------------------

- error in src\extra\xalloc.c line 618: xdbg_malloc()

Error: memory allocation problem
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-23T22:33:36+00:00
- Post Title: Re: agents of mayhem

> Reply from DarthphoeniX
>
> I try script in aom_agents.vpp_pc but don't work
can't do anything without samples.
that script was written just for fun and it worked with the samples i had, so i may or may not
keep updating it, you could always try TaylorMouse's program and see if it works there too.
## Post #28
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-03-24T10:38:17+00:00
- Post Title: Re: agents of mayhem

> Reply from AceWell
>
> DarthphoeniX wrote:I try script in aom_agents.vpp_pc but don't work
can't do anything without samples.
that script was written just for fun and it worked with the samples i had, so i may or may not
keep updating it, you could always try TaylorMouse's program and see if it works there too.
filecutter 2mb: [http://dropmefiles.com/ppr2z](http://dropmefiles.com/ppr2z)
filecutter 4mb: [http://dropmefiles.com/6Cdoo](http://dropmefiles.com/6Cdoo)
[.vpp_pc files.rar](https://xentaxbackup.github.io/file/14081_.vpp_pc files.rar)
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-24T20:18:15+00:00
- Post Title: Re: agents of mayhem

i see now, my script was for file version 10 where your samples
are file version 17, so yes there is quite a few differences.
## Post #30
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2018-10-03T20:22:17+00:00
- Post Title: Re: agents of mayhem

Hello, I need your help with the game "agents of mayhem".
How did you open a file with a 3D model of your character ?
## Post #31
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-09-18T09:25:47+00:00
- Post Title: Re: agents of mayhem

Hi TaylorMouse, thanks for the tool you made but unfortunately I have to report some nuisances and probably bugs too.

First of all it's not very convenient that I have to extract subfolders separately, I mean when I choose to dump "binks" folder which has "interface" subfolder I expect the tool to dump both *.bik files from "binks" folder & all contents of "interface" subfolder too. Your EXE works differently though: first I have to extract "binks" folder then manually select "interface" subfolder then extract it too.
Just my 2 cents but isn't it something that should be fixed at some point?

What's even more important is that I experience difficulties with extraction of "audio" directory: for example I open aom_seoul.vpp_pc, go to "audio" folder then right-click it & select "extract"; the program freezes almost immediately & I get like 43 output files (I'm counting both *.ogg & *.wem_pc).
I tried exporting groups of *.wem_pc files (like the ones with names starting with "1") but it didn't really fix anything.
Finally could you please let users disable that forced conversion to Vorbis files? I think I'm not the only one who'd like to save lots of time + spare my HDD a little by making that conversion process entirely optional (I can't say for all but I'm gonna play the tracks with VGMStream plugin for Foobar2000, it'll require change of extension to *.wem but that's about it; long gone are the days when conversion with ww2ogg.exe was the only way to listen to WWise encoded sounds).

Goodbye, I hope my feedback will be taken into account & you'll make your program even better! Thnx for the work you've already done and good luck with future efforts!

PS. I'm on Windows 10 and have extended path names enabled although I'm not sure the latter is the origin of my trouble.
## Post #32
- Username: RuV9999
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 19, 2019 11:00 pm
- Post datetime: 2021-05-07T07:51:08+00:00
- Post Title: Re: agents of mayhem

i've no idea how to use ThomasJeep tools cause its too complicated to me alone to understand the tools. Any idea how to extract the file, even with ThomasJeep tools.
## Post #33
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-05-08T13:33:13+00:00
- Post Title: Re: agents of mayhem

Would be nice if some people here would look at extracting the models from Saints Row 3 Remastered, someone on the SR forums tried and gave up over a year ago and nothing since then.
