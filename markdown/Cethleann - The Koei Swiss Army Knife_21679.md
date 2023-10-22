## Post #1
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-29T15:05:55+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

Over the last couple of months I've been working on a bunch of open-source tools to extract and work with various Koei Tecmo games such as Fire Emblem: Three Houses and Dissidia Final Fantasy NT Free Edition (Steam.) It has tools for uncompressing files, virtual FS containers (FETH's DATA0/DATA1, Atelier PAKs) and unwrapping concatinated files (.bin, .gmpk, .mdlk)

The main tool to use is Cethleann.Unbundler, this tool will take most concatinated files and output individual files. It has support for FETH SCENE, MDLK, KTSR, KTSC, LX19, GMPK, GAPK, G1L, KOVS, and RTRPK files.

This has ZERO SUPPORT for Big Endian files.
Source: https://github.com/yretenai/Cethleann
Builds: https://github.com/yretenai/Cethleann/r ... ag/1.1.104
This project REQUIRES .NET Core 5 Runtime (x64.) Download here

Click on the latest build and download the Cethleann-Standalone artifact.

This tool is created in tandem with Joschka's Noesis fmt_g1m plugin.
[viewtopic.php?f=16&t=21666](https://forum.xentax.com/viewtopic.php?f=16&t=21666)

Special Thanks To:
- id-daemon's Dissidia model converter which gave me reference data to test again
- HeartHeroDE's th-hack-tools whose implementation helped me understand STRUCT formats
- The Fire Emblem Three Houses Datamining Community for creating binary templates
- Ploaj's Metanoia whose implementatino helped me understand G1Ms
- Quickbms' arslan.bms for having a LINKDATA implementation to base off
- VitaSmith's gust_tools whose implementation helped me understand Gust PAKs and textures
- Eternity's rdbtool for helping me understand animatinos, RDBs, RDB hashing algorithms, and the DoA6 file list
- chrrox for helping me understand RDBs and figuring out what compression algorithm the switch uses.


Latest Version: 1.1.104
Changes: here

I only have one conclusion going down this journey:
## Post #2
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-01-29T21:55:42+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

Weird, one of the links gives 404 error on github...

Anyway, will love to try, but, I kind suck to build stuff from github.
## Post #3
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-29T22:17:03+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from Darkhowlings ↑Thu Jan 30, 2020 5:55 am at Thu Jan 30, 2020 5:55 am
>
> 
Weird, one of the links gives 404 error on github...

Anyway, will love to try, but, I kind suck to build stuff from github.

Ah, I forgot it requires a GitHub account to view the builds. I linked a direct link which should work.
Sorting out a different build solution.

Builds are now on AppVeyor, which should be public for all
## Post #4
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-01-30T22:35:02+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

Tried it with Attack on Titan 2, but ye

> Unhandled exception. System.ArgumentOutOfRangeException: Index was out of range. Must be non-negative and less than the size of the collection. (Parameter 'index')
>
>    at DragonLib.CLI.CommandLineFlags.ParseFlags[T](Action`1 printHelp, String[] arguments)
>
>    at Koei.DataExporter.Program.Main(String[] args)

but then noticed that LINKDATA isn't supported yet lmao
## Post #5
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-31T02:17:50+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Fri Jan 31, 2020 6:35 am at Fri Jan 31, 2020 6:35 am
>
> 
Tried it with Attack on Titan 2, but ye
Unhandled exception. System.ArgumentOutOfRangeException: Index was out of range. Must be non-negative and less than the size of the collection. (Parameter 'index')
   at DragonLib.CLI.CommandLineFlags.ParseFlags[T](Action`1 printHelp, String[] arguments)
   at Koei.DataExporter.Program.Main(String[] args)

but then noticed that LINKDATA isn't supported yet lmao

Yeah LINKDATA support is soon, I mostly started this for Fire Emblem 3 Houses, Atelier, and Dissidia NT

Edit: Added LINKDATA support, check the AppVeyor build artifacts for a new build.
Please tell me if it works, I'm not 100% on it working.
Please note that I haven't tested this but it should work.
## Post #6
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-01-31T04:23:19+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Jan 31, 2020 10:17 am at Fri Jan 31, 2020 10:17 am
>
> 
demonslayerx8 wrote: ↑Fri Jan 31, 2020 6:35 am
Tried it with Attack on Titan 2, but ye
Unhandled exception. System.ArgumentOutOfRangeException: Index was out of range. Must be non-negative and less than the size of the collection. (Parameter 'index')
   at DragonLib.CLI.CommandLineFlags.ParseFlags[T](Action`1 printHelp, String[] arguments)
   at Koei.DataExporter.Program.Main(String[] args)

but then noticed that LINKDATA isn't supported yet lmao


Yeah LINKDATA support is soon, I mostly started this for Fire Emblem 3 Houses, Atelier, and Dissidia NT

Edit: Added LINKDATA support, check the AppVeyor build artifacts for a new build.
Please tell me if it works, I'm not 100% on it working.
Please note that I haven't tested this but it should work.
Alright, I'll test it soon.

update:
nadda


dunno if the file setup has to be proper...
## Post #7
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-31T06:02:51+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Fri Jan 31, 2020 12:23 pm at Fri Jan 31, 2020 12:23 pm
>
> 
Yretenai wrote: ↑Fri Jan 31, 2020 10:17 am
demonslayerx8 wrote: ↑Fri Jan 31, 2020 6:35 am
Tried it with Attack on Titan 2, but ye


but then noticed that LINKDATA isn't supported yet lmao


Yeah LINKDATA support is soon, I mostly started this for Fire Emblem 3 Houses, Atelier, and Dissidia NT

Edit: Added LINKDATA support, check the AppVeyor build artifacts for a new build.
Please tell me if it works, I'm not 100% on it working.
Please note that I haven't tested this but it should work.

Alright, I'll test it soon.

update:
nadda


dunno if the file setup has to be proper...

Can't view the images
## Post #8
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-01-31T18:42:37+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Jan 31, 2020 2:02 pm at Fri Jan 31, 2020 2:02 pm
>
> 
demonslayerx8 wrote: ↑Fri Jan 31, 2020 12:23 pm
Yretenai wrote: ↑Fri Jan 31, 2020 10:17 am


Yeah LINKDATA support is soon, I mostly started this for Fire Emblem 3 Houses, Atelier, and Dissidia NT

Edit: Added LINKDATA support, check the AppVeyor build artifacts for a new build.
Please tell me if it works, I'm not 100% on it working.
Please note that I haven't tested this but it should work.

Alright, I'll test it soon.

update:
nadda


dunno if the file setup has to be proper...



Can't view the images
oops, fixed
## Post #9
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-31T23:08:22+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Sat Feb 01, 2020 2:42 am at Sat Feb 01, 2020 2:42 am
>
> 
oops, fixed

Fixed!

Added a new tool: Omega.DataExtractor.exe-- Usage:

```

```


In your case it would be:

```

```


It will create a new folder for each LINKDATA bin.

Models are wrapped in a container, will add support for that tomorrow.
## Post #10
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-01-31T23:21:40+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

Alright cool, I'll wait til the container support is added~
## Post #11
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-01T13:17:25+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Sat Feb 01, 2020 7:21 am at Sat Feb 01, 2020 7:21 am
>
> 
Alright cool, I'll wait til the container support is added~

Wrapped files are now supported.
Keep in mind that AOT2 has no filenames, so you just have to do the tried and tested method of unwrapping every file.
Use Cethleann.Unbundler.exe to unwrap them, or pass --recursive to Omega.DataExporter.exe's command line options

Models and textures tend to be in ptrbundle files.
## Post #12
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-02-01T16:07:21+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

what am I doing wrong?
## Post #13
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-01T16:27:10+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from Skykila ↑Sun Feb 02, 2020 12:07 am at Sun Feb 02, 2020 12:07 am
>
> 

what am I doing wrong?

Nothing, there was a bug.
I just fixed it. Appveyor should have a fixed build in 5 mins.
## Post #14
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-02-01T17:50:47+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sun Feb 02, 2020 12:27 am at Sun Feb 02, 2020 12:27 am
>
> 
I just fixed it. Appveyor should have a fixed build in 5 mins.
## Post #15
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-01T18:05:02+00:00
- Post Title: Cethleann - The Koei Swiss Army Knife

> Reply from Skykila ↑Sun Feb 02, 2020 1:50 am at Sun Feb 02, 2020 1:50 am
>
> 
Yretenai wrote: ↑Sun Feb 02, 2020 12:27 am
I just fixed it. Appveyor should have a fixed build in 5 mins.

Ugh, AOT2's file bundle code is crashing. It's fixed in the new build. (Give appveyor another 5 minutes)

Sorry that it's crashing so much.
## Post #16
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-02-01T18:23:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sun Feb 02, 2020 2:05 am at Sun Feb 02, 2020 2:05 am
>
> 
Sorry that it's crashing so much.

I understand. Impossible to do such complicated things and not make mistakes. Errare humanum est.

Everything was unpacked successfully!
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-02T03:39:57+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I saw the profile for Nioh, and went ahead and gave it a try, unfortunately it wont extract, due to missing pairs, it has only following files.

```
    18,300,536,832 archive_01.lnk
        54,765,568 archive_02.lnk
         5,863,424 archive_03.lnk
     1,255,540,736 archive_04.lnk
        48,822,272 archive_05.lnk
             6,144 archive_06.lnk
           192,512 archive_07.lnk
        12,562,432 archive_08.lnk
           182,272 archive_09.lnk
     6,289,604,608 archive_10.lnk
     3,346,188,288 archive_11.lnk
     2,137,982,976 archive_12.lnk
     1,963,837,440 archive_13.lnk
        66,791,424 archive_14.lnk
         1,136,640 archive_15.lnk
       916,418,560 archive_16.lnk
    35,856,300,032 archive_17.lnk
       866,738,176 archive_18.lnk
        35,041,280 archive_19.lnk
            18,878 lfm_order_00.bin
           339,224 lfm_order_01.bin
               363 lfm_order_02.bin
            40,406 lfm_order_03.bin
            13,184 lfm_order_04.bin
               782 lfm_order_05.bin
               236 lfm_order_06.bin
             3,746 lfm_order_07.bin
            22,466 lfm_order_08.bin
               401 lfm_order_09.bin
            81,356 lfm_order_10.bin
            20,594 lfm_order_11.bin
             8,816 lfm_order_12.bin
           232,052 lfm_order_13.bin
             7,778 lfm_order_14.bin
            16,616 lfm_order_15.bin
            14,432 lfm_order_16.bin
           162,710 lfm_order_17.bin
            31,982 lfm_order_18.bin
            21,218 lfm_order_19.bin
             2,884 load_inf_00.bin
            52,168 load_inf_01.bin
                52 load_inf_02.bin
             6,196 load_inf_03.bin
             2,008 load_inf_04.bin
               100 load_inf_05.bin
                16 load_inf_06.bin
               556 load_inf_07.bin
             3,436 load_inf_08.bin
                76 load_inf_09.bin
            12,496 load_inf_10.bin
             3,148 load_inf_11.bin
             1,336 load_inf_12.bin
            35,680 load_inf_13.bin
             2,572 load_inf_14.bin
             2,536 load_inf_15.bin
             2,200 load_inf_16.bin
            25,012 load_inf_17.bin
             4,900 load_inf_18.bin
             3,244 load_inf_19.bin
60 File(s) 71,178,647,328 bytes
```

Also wanted to try for Dynasty Warriors 8

```
    2,030,172,160 LINKDATA0.BIN
    2,040,986,368 LINKDATA1.BIN
    2,041,652,480 LINKDATA2.BIN
    1,306,806,528 LINKDATA3.BIN
```

and 9, but same result, it has different structured archives.

```
     4,014,750,208 LINKFILE_001.BIN
     4,001,928,448 LINKFILE_002.BIN
     4,007,272,704 LINKFILE_003.BIN
     2,851,092,992 LINKFILE_004.BIN
     2,469,982,720 LINKFILE_005.BIN
     4,000,041,984 LINKFILE_006.BIN
     4,000,377,088 LINKFILE_007.BIN
     4,000,110,336 LINKFILE_008.BIN
     3,996,307,456 LINKFILE_009.BIN
     3,715,878,144 LINKFILE_010.BIN
        21,763,840 LINKFILE_BPR.BIN
        23,771,136 LINKFILE_CHS.BIN
        24,589,568 LINKFILE_CHT.BIN
        21,647,616 LINKFILE_ENG.BIN
        22,058,496 LINKFILE_FRA.BIN
        22,017,792 LINKFILE_GER.BIN
        22,077,184 LINKFILE_HAN.BIN
        21,830,656 LINKFILE_ITA.BIN
        25,118,976 LINKFILE_JPN.BIN
        21,863,680 LINKFILE_SPA.BIN
         4,019,680 LINKIDX_000.BIN
         4,019,680 LINKIDX_001.BIN
         4,019,680 LINKIDX_002.BIN
         4,019,680 LINKIDX_003.BIN
         4,019,680 LINKIDX_004.BIN
         4,019,680 LINKIDX_005.BIN
         4,019,680 LINKIDX_006.BIN
         4,019,680 LINKIDX_007.BIN
         4,019,680 LINKIDX_008.BIN
         4,019,680 LINKIDX_009.BIN
         4,019,680 LINKIDX_010.BIN
         4,019,680 LINKIDX_BPR.BIN
         4,019,680 LINKIDX_CHS.BIN
         4,019,680 LINKIDX_CHT.BIN
         4,019,680 LINKIDX_ENG.BIN
         4,019,680 LINKIDX_FRA.BIN
         4,019,680 LINKIDX_GER.BIN
         4,019,680 LINKIDX_HAN.BIN
         4,019,680 LINKIDX_ITA.BIN
         4,019,680 LINKIDX_JPN.BIN
         4,019,680 LINKIDX_SPA.BIN
```

         Nioh does not have extra patch/dlc folders, while Dynasty Wrriors games have.
## Post #18
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-02T18:53:29+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Sun Feb 02, 2020 11:39 am at Sun Feb 02, 2020 11:39 am
>
> 
I saw the profile for Nioh, and went ahead and gave it a try, unfortunately it wont extract, due to missing pairs, it has only following files.
Code: Select all        18,937,856 archive_00.lnk
    18,300,536,832 archive_01.lnk
        54,765,568 archive_02.lnk
         5,863,424 archive_03.lnk
     1,255,540,736 archive_04.lnk
        48,822,272 archive_05.lnk
             6,144 archive_06.lnk
           192,512 archive_07.lnk
        12,562,432 archive_08.lnk
           182,272 archive_09.lnk
     6,289,604,608 archive_10.lnk
     3,346,188,288 archive_11.lnk
     2,137,982,976 archive_12.lnk
     1,963,837,440 archive_13.lnk
        66,791,424 archive_14.lnk
         1,136,640 archive_15.lnk
       916,418,560 archive_16.lnk
    35,856,300,032 archive_17.lnk
       866,738,176 archive_18.lnk
        35,041,280 archive_19.lnk
            18,878 lfm_order_00.bin
           339,224 lfm_order_01.bin
               363 lfm_order_02.bin
            40,406 lfm_order_03.bin
            13,184 lfm_order_04.bin
               782 lfm_order_05.bin
               236 lfm_order_06.bin
             3,746 lfm_order_07.bin
            22,466 lfm_order_08.bin
               401 lfm_order_09.bin
            81,356 lfm_order_10.bin
            20,594 lfm_order_11.bin
             8,816 lfm_order_12.bin
           232,052 lfm_order_13.bin
             7,778 lfm_order_14.bin
            16,616 lfm_order_15.bin
            14,432 lfm_order_16.bin
           162,710 lfm_order_17.bin
            31,982 lfm_order_18.bin
            21,218 lfm_order_19.bin
             2,884 load_inf_00.bin
            52,168 load_inf_01.bin
                52 load_inf_02.bin
             6,196 load_inf_03.bin
             2,008 load_inf_04.bin
               100 load_inf_05.bin
                16 load_inf_06.bin
               556 load_inf_07.bin
             3,436 load_inf_08.bin
                76 load_inf_09.bin
            12,496 load_inf_10.bin
             3,148 load_inf_11.bin
             1,336 load_inf_12.bin
            35,680 load_inf_13.bin
             2,572 load_inf_14.bin
             2,536 load_inf_15.bin
             2,200 load_inf_16.bin
            25,012 load_inf_17.bin
             4,900 load_inf_18.bin
             3,244 load_inf_19.bin
60 File(s) 71,178,647,328 bytes
Also wanted to try for Dynasty Warriors 8
Code: Select all        1,302,848 LINKDATA.IDX
    2,030,172,160 LINKDATA0.BIN
    2,040,986,368 LINKDATA1.BIN
    2,041,652,480 LINKDATA2.BIN
    1,306,806,528 LINKDATA3.BIN
and 9, but same result, it has different structured archives.
Code: Select all       938,236,416 LINKFILE_000.BIN
     4,014,750,208 LINKFILE_001.BIN
     4,001,928,448 LINKFILE_002.BIN
     4,007,272,704 LINKFILE_003.BIN
     2,851,092,992 LINKFILE_004.BIN
     2,469,982,720 LINKFILE_005.BIN
     4,000,041,984 LINKFILE_006.BIN
     4,000,377,088 LINKFILE_007.BIN
     4,000,110,336 LINKFILE_008.BIN
     3,996,307,456 LINKFILE_009.BIN
     3,715,878,144 LINKFILE_010.BIN
        21,763,840 LINKFILE_BPR.BIN
        23,771,136 LINKFILE_CHS.BIN
        24,589,568 LINKFILE_CHT.BIN
        21,647,616 LINKFILE_ENG.BIN
        22,058,496 LINKFILE_FRA.BIN
        22,017,792 LINKFILE_GER.BIN
        22,077,184 LINKFILE_HAN.BIN
        21,830,656 LINKFILE_ITA.BIN
        25,118,976 LINKFILE_JPN.BIN
        21,863,680 LINKFILE_SPA.BIN
         4,019,680 LINKIDX_000.BIN
         4,019,680 LINKIDX_001.BIN
         4,019,680 LINKIDX_002.BIN
         4,019,680 LINKIDX_003.BIN
         4,019,680 LINKIDX_004.BIN
         4,019,680 LINKIDX_005.BIN
         4,019,680 LINKIDX_006.BIN
         4,019,680 LINKIDX_007.BIN
         4,019,680 LINKIDX_008.BIN
         4,019,680 LINKIDX_009.BIN
         4,019,680 LINKIDX_010.BIN
         4,019,680 LINKIDX_BPR.BIN
         4,019,680 LINKIDX_CHS.BIN
         4,019,680 LINKIDX_CHT.BIN
         4,019,680 LINKIDX_ENG.BIN
         4,019,680 LINKIDX_FRA.BIN
         4,019,680 LINKIDX_GER.BIN
         4,019,680 LINKIDX_HAN.BIN
         4,019,680 LINKIDX_ITA.BIN
         4,019,680 LINKIDX_JPN.BIN
         4,019,680 LINKIDX_SPA.BIN
         Nioh does not have extra patch/dlc folders, while Dynasty Wrriors games have.

What platform?
## Post #19
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-02-03T08:55:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

i only get this
## Post #20
- Username: zory16
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 26, 2016 11:38 pm
- Post datetime: 2020-02-03T13:28:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is it possible to get support for Dragon Quest Heroes II?
## Post #21
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-03T16:08:10+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Skykila ↑Mon Feb 03, 2020 4:55 pm at Mon Feb 03, 2020 4:55 pm
>
> 
i only get this

I mean what platform is the game from? I've got it on PC and will implement that soon
DW7/8 I don't own so I'll implement that when I get the games.

> Reply from zory16 ↑Mon Feb 03, 2020 9:28 pm at Mon Feb 03, 2020 9:28 pm
>
> 
Is it possible to get support for Dragon Quest Heroes II?

Depends on if and when I can buy it. I don't have the means to buy every single Koei game.
## Post #22
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-02-03T16:53:25+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Tue Feb 04, 2020 12:08 am at Tue Feb 04, 2020 12:08 am
>
> 
 I've got it on PC and will implement that soon
I can't wait!
## Post #23
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-04T15:24:33+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Skykila ↑Tue Feb 04, 2020 12:53 am at Tue Feb 04, 2020 12:53 am
>
> 
Yretenai wrote: ↑Tue Feb 04, 2020 12:08 am
 I've got it on PC and will implement that soon

I can't wait!

Nioh support added.
Models are double wrapped in MDLPACK and G1MPACK files, animations are in G2APACK files, textures are just straight G1Ts

The textures for the models is the model ID plus 1 (so model 929 has texture 930)

The Noesis plugin will struggle with some of the G1M files, because there's some unoptimized code in the script (which will be fixed soon,) and Team Ninja models tend to be high detail. So if Noesis freezes while loading a model, give it a few minutes. This will be fixed soon (some models will always lag a bit though, Nioh has a 70 MB model somewhere)
## Post #24
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-02-04T16:54:06+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Thanks
## Post #25
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-02-04T16:57:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

How can I extract fatal frame models and animations
## Post #26
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-04T17:04:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from gamer1977 ↑Wed Feb 05, 2020 12:57 am at Wed Feb 05, 2020 12:57 am
>
> 
How can I extract fatal frame models and animations

Use the quickbms script, I don't own Fatal Frame so I can't explore the files.
## Post #27
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-05T23:07:23+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Mon Feb 03, 2020 2:53 am at Mon Feb 03, 2020 2:53 am
>
> What platform?
My apologies for the delay, I was away, and all mentioned games are PC versions, I thought it was already known due to archive format, sorry.
And now that I see Nioh is supported, will give it a try and test things out.
## Post #28
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-06T00:28:24+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Tue Feb 04, 2020 11:24 pm at Tue Feb 04, 2020 11:24 pm
>
> 
Nioh support added.
Models are double wrapped in MDLPACK and G1MPACK files, animations are in G2APACK files, textures are just straight G1Ts

Regarding Nioh, it seems that Archive 10 has models which i think are from cutscene and such, Archive 11 has more models + some scenery one.
Archive 17 seems to contain only Scenery meshes, same for Archive 18.
I couldn't find any models regarding enemies/player items, Wild guess: they're in Archive_01 which, atm, has a whooping 16.6 gb unknown file, having only G2A packs extracted. Would it be possible to refine the extraction?
## Post #29
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-06T03:24:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Allanoon ↑Thu Feb 06, 2020 8:28 am at Thu Feb 06, 2020 8:28 am
>
> 
Yretenai wrote: ↑Tue Feb 04, 2020 11:24 pm
Nioh support added.
Models are double wrapped in MDLPACK and G1MPACK files, animations are in G2APACK files, textures are just straight G1Ts


Regarding Nioh, it seems that Archive 10 has models which i think are from cutscene and such, Archive 11 has more models + some scenery one.
Archive 17 seems to contain only Scenery meshes, same for Archive 18.
I couldn't find any models regarding enemies/player items, Wild guess: they're in Archive_01 which, atm, has a whooping 16.6 gb unknown file, having only G2A packs extracted. Would it be possible to refine the extraction?

yeah, I think so too. The G2A files in Archive 1 are character animations, the bin files seem to be XOR rotated with a 32-bit constant(?)

The BIN files clearly start with a G1T header, but instead of GT1G it's 0x345C6632

Ugh. I'm at an impasse. I'm sick atm so I can't just spend a day disassembling and debugging the game to find where it does this dumbass XOR operation, and if it's KTGL it's gonna be extremely dumb.

For now Nioh support will be limited to this.
## Post #30
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-06T12:19:50+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Thu Feb 06, 2020 11:24 am at Thu Feb 06, 2020 11:24 am
>
> 
Allanoon wrote: ↑Thu Feb 06, 2020 8:28 am
Yretenai wrote: ↑Tue Feb 04, 2020 11:24 pm
Nioh support added.
Models are double wrapped in MDLPACK and G1MPACK files, animations are in G2APACK files, textures are just straight G1Ts


Regarding Nioh, it seems that Archive 10 has models which i think are from cutscene and such, Archive 11 has more models + some scenery one.
Archive 17 seems to contain only Scenery meshes, same for Archive 18.
I couldn't find any models regarding enemies/player items, Wild guess: they're in Archive_01 which, atm, has a whooping 16.6 gb unknown file, having only G2A packs extracted. Would it be possible to refine the extraction? 


yeah, I think so too. The G2A files in Archive 1 are character animations, the bin files seem to be XOR rotated with a 32-bit constant(?)

The BIN files clearly start with a G1T header, but instead of GT1G it's 0x345C6632

Ugh. I'm at an impasse. I'm sick atm so I can't just spend a day disassembling and debugging the game to find where it does this dumbass XOR operation, and if it's KTGL it's gonna be extremely dumb.

For now Nioh support will be limited to this.

It's fine, we can wait for as long as you need, the game won't go anywhere   
Thanks for your help, get well!
## Post #31
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-06T18:25:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann now can also extract any LINKDATA pair (.IDX and .BIN file) by providing --idx and --bin values to Koei.DataExporter's arguments
i.e. for Dragon Quest Heroes you would call

```

```


Cethleann now can also extract RDB files from both Windows (Dead or Alive 6, Romance of the Three Kingdoms 14) and Switch (Persona 5 Scramble) using the new Softness.DataExporter.exe tool.

```

```


It's important to pass "-g GameId" when exporting RDBs as files have hashed filenames. Currently I only have a partial Dead or Alive 6 filelist (from rdbtool)
## Post #32
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-02-07T09:28:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

the unbundle with dissidia nt outputs some .wav files from the .sed files but the wav format is not playable with anyting I have, anyone know how to decode it or conver it?
[Cloud_121.zip](https://xentaxbackup.github.io/file/17471_Cloud_121.zip)
## Post #33
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-07T16:29:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from GDL ↑Fri Feb 07, 2020 5:28 pm at Fri Feb 07, 2020 5:28 pm
>
> 
the unbundle with dissidia nt outputs some .wav files from the .sed files but the wav format is not playable with anyting I have, anyone know how to decode it or conver it?

The wav files are MSADPCM streams, VLC can play it, as can PotPlayer. However the tool can convert these to normal WAV files. Do not run the unbundler with  --pcm if you want it converted to 16-bit PCM. The default is enabled so invoking that option will disable the functionality.

If all else fails, try vgmstream as that has support for SED files now.
## Post #34
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-02-07T21:15:40+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sat Feb 08, 2020 12:29 am at Sat Feb 08, 2020 12:29 am
>
> 
GDL wrote: ↑Fri Feb 07, 2020 5:28 pm
the unbundle with dissidia nt outputs some .wav files from the .sed files but the wav format is not playable with anyting I have, anyone know how to decode it or conver it?


The wav files are MSADPCM streams, VLC can play it, as can PotPlayer. However the tool can convert these to normal WAV files. Do not run the unbundler with  --pcm if you want it converted to 16-bit PCM. The default is enabled so invoking that option will disable the functionality.

If all else fails, try vgmstream as that has support for SED files now.

Got it, thx  

EDIT:

Ok, this was weird, if you try to play the previous example the voice is all jumbled, like if someone was speaking inside a metal pipe and all audio was being unbundled like that, even playing them from the sed file gave me just a bunch of weird voices in every media player.

I'm not sure what happened but I suspect it the culprit was overwriting previous versions of your tool, all I've been doing is getting the latest release and unzipping the new files over the old ones and then this started happening, after a fresh unzipping from the latest release to a new folder everything extracted fine.
## Post #35
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-08T07:59:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from GDL ↑Sat Feb 08, 2020 5:15 am at Sat Feb 08, 2020 5:15 am
>
> 
Yretenai wrote: ↑Sat Feb 08, 2020 12:29 am
GDL wrote: ↑Fri Feb 07, 2020 5:28 pm
the unbundle with dissidia nt outputs some .wav files from the .sed files but the wav format is not playable with anyting I have, anyone know how to decode it or conver it?


The wav files are MSADPCM streams, VLC can play it, as can PotPlayer. However the tool can convert these to normal WAV files. Do not run the unbundler with  --pcm if you want it converted to 16-bit PCM. The default is enabled so invoking that option will disable the functionality.

If all else fails, try vgmstream as that has support for SED files now.


Got it, thx  

EDIT:

Ok, this was weird, if you try to play the previous example the voice is all jumbled, like if someone was speaking inside a metal pipe and all audio was being unbundled like that, even playing them from the sed file gave me just a bunch of weird voices in every media player.

I'm not sure what happened but I suspect it the culprit was overwriting previous versions of your tool, all I've been doing is getting the latest release and unzipping the new files over the old ones and then this started happening, after a fresh unzipping from the latest release to a new folder everything extracted fine.

does the sed file start with im_?
## Post #36
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-02-08T08:44:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sat Feb 08, 2020 12:29 am at Sat Feb 08, 2020 12:29 am
>
> 
does the sed file start with im_?

Not sure, all I see is a bunch of wav files with numeric values but playing the im_ sed files seem to all sound like that
## Post #37
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-08T09:00:53+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from GDL ↑Sat Feb 08, 2020 4:44 pm at Sat Feb 08, 2020 4:44 pm
>
> 
Yretenai wrote: ↑Sat Feb 08, 2020 12:29 am
does the sed file start with im_?


Not sure, all I see is a bunch of wav files with numeric values but playing the im_ sed files seem to all sound like that

sed files starting with im_ are "impostor" sound files, used by AI
the normal VOX starts with p_
## Post #38
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-02-09T00:47:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sat Feb 08, 2020 5:00 pm at Sat Feb 08, 2020 5:00 pm
>
> 
GDL wrote: ↑Sat Feb 08, 2020 4:44 pm
Yretenai wrote: ↑Sat Feb 08, 2020 12:29 am
does the sed file start with im_?


Not sure, all I see is a bunch of wav files with numeric values but playing the im_ sed files seem to all sound like that


sed files starting with im_ are "impostor" sound files, used by AI
the normal VOX starts with p_

D'oh! No wonder
## Post #39
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-02-11T19:05:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Sorry, i dont understand how i can extract Nioh using this tool
Please make little tutorial, thanx
## Post #40
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-12T19:27:36+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Crazy31139 ↑Wed Feb 12, 2020 3:05 am at Wed Feb 12, 2020 3:05 am
>
> 
Sorry, i dont understand how i can extract Nioh using this tool
Please make little tutorial, thanx

No.
Besides, Nioh is broken rn.
## Post #41
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-02-15T05:22:57+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

So I'm trying to extract the files from Dynasty Warriors 8 Xtreme Legends, but doesn't seem to be working for me... even tho I put the right directory in. Don't ask how or why the date for those files say 12/12/1999, even I don't know xD



update:
got it to work, but with issues
## Post #42
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-15T07:57:55+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Sat Feb 15, 2020 1:22 pm at Sat Feb 15, 2020 1:22 pm
>
> 
So I'm trying to extract the files from Dynasty Warriors 8 Xtreme Legends, but doesn't seem to be working for me... even tho I put the right directory in. Don't ask how or why the date for those files say 12/12/1999, even I don't know xD

update:
got it to work, but with issues

DW8 has the same problem as DW9. IDK when I'll have those fixed.
## Post #43
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-02-15T18:55:24+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sat Feb 15, 2020 3:57 pm at Sat Feb 15, 2020 3:57 pm
>
> 
demonslayerx8 wrote: ↑Sat Feb 15, 2020 1:22 pm
So I'm trying to extract the files from Dynasty Warriors 8 Xtreme Legends, but doesn't seem to be working for me... even tho I put the right directory in. Don't ask how or why the date for those files say 12/12/1999, even I don't know xD

update:
got it to work, but with issues


DW8 has the same problem as DW9. IDK when I'll have those fixed.
oh alright, no problem.

Update:
I can confirm that the Koei.DataExporter works fine with Warriors Orochi 4 Ultimate [switch]
## Post #44
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-16T18:50:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Sun Feb 16, 2020 2:55 am at Sun Feb 16, 2020 2:55 am
>
> 
I can confirm that the Koei.DataExporter works fine with Warriors Orochi 4 Ultimate [switch]

that's good to know.
## Post #45
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-18T17:02:23+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Thanks for a awesome tool.

I asked a question because it was listed in the --game option. Is DOAXVV supported?
## Post #46
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-18T17:06:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from einherjar007 ↑Wed Feb 19, 2020 1:02 am at Wed Feb 19, 2020 1:02 am
>
> 
Thanks for a awesome tool.

I asked a question because it was listed in the --game option. Is DOAXVV supported?

Soon

The games listed in --game are not per se the games supported, just added as a future-proofing thing incase they somehow already work but need a filelist.
## Post #47
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-18T17:17:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Wed Feb 19, 2020 1:06 am at Wed Feb 19, 2020 1:06 am
>
> 
einherjar007 wrote: ↑Wed Feb 19, 2020 1:02 am
Thanks for a awesome tool.

I asked a question because it was listed in the --game option. Is DOAXVV supported?


Soon

The games listed in --game are not per se the games supported, just added as a future-proofing thing incase they somehow already work but need a filelist.

thanks reply.
that's a miracle job. thanks!
## Post #48
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-18T17:22:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from einherjar007 ↑Wed Feb 19, 2020 1:17 am at Wed Feb 19, 2020 1:17 am
>
> 
thanks reply.
that's a miracle job. thanks!

Just a note as warning: the game isn't KTGL and still has (packed) DDS files and TMC models.
Also no fileames.
## Post #49
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-20T06:54:05+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann Version 1.0.23 released.
Changes:

All DataExporter projects are merged into Cethleann.DataExporter. You now need to specify which subsystem to use:

--flayn for LINKDATA pairs
--leonhart for single LINKARCHIVE files
--mitsunari for LNK files
--nyotengu for RDB files
--reisalin for Atelier PAKs
--yshtola for COMMON games (DOAXVV/DFFNT)

Alternatively you can also use --linkdata, --linkarchive, --linkbin, --rdb, --pak, --pkg for each of the options respectively.
The file list for Persona 5 Scramble has been updated with more filenames.
Flayn has been rewritten to support multiple LINKDATA archives
Yshtola has DOAXVV support now, however no filenames are present for that game and the files are for an engine besides KTGL (packed DDS files and TMC.)


When extracting a game, make sure to also provide the -g, or --game option to specify which game it is you're processing. If the game you're extracting isn't present, don't worry about it.

This is used to determine what filelist to load and in the case of Yshtola/COMMON how to decrypt the files.

Cethleann Version 1.0.24 released.
Changes:

 DOAXVV extraction fix for uncompressed/unencrypted files. -- Note: You need to pass the DX11_global_data/DL folder in addition to DX11_global_data.
 Elixir (Atelier container) support


Up next:

 A tool to recombine G1T textures from RDB-archived games
 DW7+ compression support
 Nioh's compression format (still unsure if I'll ever be able to implement this.)

DO NOT MESSAGE ME ABOUT DOAXVV
I will not be adding any new features relating to that game.
## Post #50
- Username: Arcana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 09, 2016 4:49 pm
- Post datetime: 2020-02-21T14:00:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Sorry for the stupid question, but what's the syntax for using the new combined dataexporter?
## Post #51
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-22T16:32:58+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Arcana ↑Fri Feb 21, 2020 10:00 pm at Fri Feb 21, 2020 10:00 pm
>
> 
Sorry for the stupid question, but what's the syntax for using the new combined dataexporter?

```

```


i.e.

```
Cethleann.DataExporter.exe --flayn -g ThreeHouses L:\KTGL\Extract\FETH "K:\nx\ThreeHouses\base\romfs" "K:\nx\ThreeHouses\dlc1\romfs" ...

```
## Post #52
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-28T08:37:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann updated to version 1.0.28
There are no changes to extraction.

This version adds two new programs: Nyotengu.Database, and Nyotengu.KTID.
Nyotengu.Database dumps information from OBJDB files, and KTID uses a .ktid file to combine multiple G1Ts into a single G1T so you can use the texture with fmt_g1m.

Usage for it is kind of tricky.

```

```


For example, to "recompile" Persona 5 Scramble's Joker G1T you have to call:

```
-g Scramble
X:\path\to\scrambleoutput\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
X:\path\to\scrambleoutput\MaterialEditor\g1t 
X:\path\to\scrambleoutput\CharacterEditor\ktid\H0000_Joker.ktid 
X:\path\to\scrambleoutput\CharacterEditor\ktid\H0050_Joker_Fake.ktid

```


You can specify an unlimited amount of KTID files, the G1T will be placed in the ktid folder with the same name as the ktid.
i.e.
X:\path\to\scrambleoutput\CharacterEditor\ktid\H0000_Joker.g1t and
X:\path\to\scrambleoutput\CharacterEditor\ktid\H0050_Joker_Fake.g1t

CharacterEditor.kidssingletondb HAS TO MATCH the RDB folder the KTID is in. Since the KTID is in CharacterEditor, we need to use CharacterEditor.kidssingletondb
If the KTID was in MaterialEditor, we would use MaterialEditor.kidssingletondb
## Post #53
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2020-03-08T13:54:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I tested several gmpks, and all of them consistently work (on Dissidia NT), except the ones from the stage folder, where i get the following error:

```
[2020-03-07T15:07:15][GMPK] Failed unpacking GMPK
[2020-03-07T15:07:15][GMPK] System.ArgumentOutOfRangeException: Index was out of range. Must be non-negative and less than the size of the collection. (Parameter 'index')
   at Cethleann.Unbundler.UnbundlerLogic.TryExtractGMPK(String pathBase, Span`1 data, UnbundlerFlags flags) in C:\projects\cethleann\Cethleann.Unbundler\UnbundlerLogic.cs:line 265
```


Any gmpk from stage has this index out of range error, could it be that the gmpks for stages are used differently? Or is there a parameter that could be used for these?

I would attach one of them for testing, but these files are really big (like, 30-100 mb). Could that be the cause?
## Post #54
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-08T15:18:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Seyren ↑Sun Mar 08, 2020 9:54 pm at Sun Mar 08, 2020 9:54 pm
>
> 
I tested several gmpks, and all of them consistently work (on Dissidia NT), except the ones from the stage folder, where i get the following error:
Code: Select all[2020-03-07T15:07:15][Cethleann] Extracting SMALE_00.gmpk...
[2020-03-07T15:07:15][GMPK] Failed unpacking GMPK
[2020-03-07T15:07:15][GMPK] System.ArgumentOutOfRangeException: Index was out of range. Must be non-negative and less than the size of the collection. (Parameter 'index')
   at Cethleann.Unbundler.UnbundlerLogic.TryExtractGMPK(String pathBase, Span`1 data, UnbundlerFlags flags) in C:\projects\cethleann\Cethleann.Unbundler\UnbundlerLogic.cs:line 265

Any gmpk from stage has this index out of range error, could it be that the gmpks for stages are used differently? Or is there a parameter that could be used for these?

I would attach one of them for testing, but these files are really big (like, 30-100 mb). Could that be the cause?

huh, i'll check it out.

Edit: Fixed in build 29.
## Post #55
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2020-03-10T14:28:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Tested it again and it works, thank you so much!
## Post #56
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-03-11T06:02:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

When trying to export pg1m and pg2a bundler from ps4 version of Nioh I get an error.
## Post #57
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-11T06:09:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Skykila ↑Wed Mar 11, 2020 2:02 pm at Wed Mar 11, 2020 2:02 pm
>
> 
When trying to export pg1m and pg2a bundler from ps4 version of Nioh I get an error.

those are not errors
## Post #58
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-03-11T06:16:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Wed Mar 11, 2020 2:09 pm at Wed Mar 11, 2020 2:09 pm
>
> 
those are not errors
But nothing is exported (CP_HUMAN_COMMON.pg2a 12,5Mb).
## Post #59
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-11T15:11:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Skykila ↑Wed Mar 11, 2020 2:16 pm at Wed Mar 11, 2020 2:16 pm
>
> 
Yretenai wrote: ↑Wed Mar 11, 2020 2:09 pm
those are not errors

But nothing is exported (CP_HUMAN_COMMON.pg2a 12,5Mb).

I can't verify because I don't have Nioh PS4.
## Post #60
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-03-11T16:19:10+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Wed Mar 11, 2020 2:09 pm at Wed Mar 11, 2020 2:09 pm
>
> 
Skykila wrote: ↑Wed Mar 11, 2020 2:02 pm
When trying to export pg1m and pg2a bundler from ps4 version of Nioh I get an error.




those are not errors

I'm getting the same problem with the latest tool version, the old one (1.0.18) extract them just fine.
Here some files if you wana check [https://www.mediafire.com/file/04x3pkdc ... 4.rar/file](https://www.mediafire.com/file/04x3pkdc5oggpr7/NiohPS4.rar/file)
## Post #61
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-12T06:23:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Allanoon ↑Thu Mar 12, 2020 12:19 am at Thu Mar 12, 2020 12:19 am
>
> 
Yretenai wrote: ↑Wed Mar 11, 2020 2:09 pm
Skykila wrote: ↑Wed Mar 11, 2020 2:02 pm
When trying to export pg1m and pg2a bundler from ps4 version of Nioh I get an error.




those are not errors


I'm getting the same problem with the latest tool version, the old one (1.0.18) extract them just fine.
Here some files if you wana check https://www.mediafire.com/file/04x3pkdc ... 4.rar/file

Fixed in build 30.
## Post #62
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-13T01:06:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Build 32 introduces a new tool:
Nyotengu.AnimationGraph
You can find info on previous versions [here](https://forum.xentax.com/viewtopic.php?f=10&t=21679&p=160417#p160417)

This tool will (attempt to) collect G1A animation files given a particular RDB hash. This allows one to easily find compatible  animations if the game has been extracted with --nyotengu (as in the game has .rdb files)

Usage is even more complicated than Nyotengu.KTID, the tool to recombine G1T textures from KTID files.

```

```

i.e.

```

```


would find all animations for H0000_Joker.g1m.

In case you have filenames enabled during extraction:

```
285cb0c3 = CE1CommonResource.motor.kidssingletondb

```

Caveat: Some RDB games define models by TypeInfo::Object::3D::Displayset::Model, and other games define them by TypeInfo::Object::3D::Placeable::Model::WorldPQ (Scramble uses WorldPQ, Dead or Alive 6 uses model hashes)-- As of build 32 this tool ONLY supports the former.

Finding model G1As is a bit more complicated, will implement automatic lookup for these types next update.

In other words, right now Nyotengu.AnimationGraph ONLY SUPPORTS  Dead or Alive 6 for now.
## Post #63
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2020-03-13T02:23:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

This is super helpful! I was cross-referencing those database files manually to dig Persona animations out. Now I don't have too.
## Post #64
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-13T02:59:35+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Simguy ↑Fri Mar 13, 2020 10:23 am at Fri Mar 13, 2020 10:23 am
>
> 
This is super helpful! I was cross-referencing those database files manually to dig Persona animations out. Now I don't have too.

If you can find the KTID for WorldPQ, you can pass that as the hash instead of the model hash, and it'll work.

For example, 418f67bf is the WorldPQ for H000_Joker, look at DisplaysetObjectNameHash
## Post #65
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2020-03-13T21:13:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Yup, thats what I was doing. I'm sure you already know, but just in case: some references in "CharacterActionObjectNameHashArray" refer to an unknown property type ("7bdd07f3") which still contains a reference to a G1A property.
## Post #66
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-15T14:47:36+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Simguy ↑Sat Mar 14, 2020 5:13 am at Sat Mar 14, 2020 5:13 am
>
> 
Yup, thats what I was doing. I'm sure you already know, but just in case: some references in "CharacterActionObjectNameHashArray" refer to an unknown property type ("7bdd07f3") which still contains a reference to a G1A property.

The unknown property is DstAnimationDataObjectNameHash, there's also SrcAnimationDataObjectNameHash, and FCurveAnimationDataObjectNameHash. These are usually only used for map geometry, I'll add support in next update.

I gotta add an option to collect missing property hashes so I can find them more easily in the binary-- since it's a manual process.
Most of the properties are from DOA6 NAME database files (which haven't been updated in a while,) but for Sangokushi 14 and Scramble I have to find the serializing methods in the executable.

Updated to build 34: has support for DstAnimationDataObjectNameHash, a few more property hashes, updated the DoA6 and Sangokushi 14 filelists.
## Post #67
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-19T03:06:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I would like to ask if you could add support for OPPW3 DLC BIN files, I extracted the base game LINKDATA_EU_OS_EUNA.A, .B, .C and .D using Steven's Gas Machine, but it doesn't look like it has support for the DLC files, and it hasn't been updated since 2018, there doesn't seem to be an IDX file.

[OPPW3 BIN files](https://www.mediafire.com/file/e6bx461fj24mgdp/OPPW3_DLC_BIN.7z/file)
## Post #68
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-19T03:57:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from JosouKitsune ↑Thu Mar 19, 2020 11:06 am at Thu Mar 19, 2020 11:06 am
>
> 
I would like to ask if you could add support for OPPW3 DLC BIN files, I extracted the base game LINKDATA_EU_OS_EUNA.A, .B, .C and .D using Steven's Gas Machine, but it doesn't look like it has support for the DLC files, and it hasn't been updated since 2018, there doesn't seem to be an IDX file.

OPPW3 BIN files

Support added in Version 35. If this happens to ever be extracted by Cethleann, the extension will be slcbundle. There was also bug with pointer bundles.
The files have a texture and geometry data. The 000C.ptrbundle has the geometry, the skeleton and model is split so you have to find the skeleton model in this same extract.
## Post #69
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-19T04:38:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Thu Mar 19, 2020 11:57 am at Thu Mar 19, 2020 11:57 am
>
> 

Support added in Version 35. If this happens to ever be extracted by Cethleann, the extension will be slcbundle. There was also bug with pointer bundles.
The files have a texture and geometry data. The 000C.ptrbundle has the geometry, the skeleton and model is split so you have to find the skeleton model in this same extract.

Wow that was fast, thanks, should I use Cethleann data exporter or unbundler? and which is the correct mode?

NVM I figured it was unbunbler, again thanks for your work.
## Post #70
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-03-19T11:05:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I just wanted to stop by and thank Yretenai for their work! Because of the tools you and the community have developed, I've been able to start work on a fan site for the game Final Fantasy Opera Omnia using textures and animations right from the files. 

One mystery in the game files I've yet to solve has been some of these so called "XL" header bins that are likely xor-ed json files that contain ability data and text strings. Being that I heard from chrrox on Discord that all Team Ninja games might use the same encryption (not sure if that's true) I was wondering if there was a process I could check these files with.

Thank you!


 Opera Omnia Bins.zip
(25.9 KiB) Downloaded 17 times
## Post #71
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-19T19:58:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi I found this voice.pac that contains multiple KOVS, alongside a voice.hed with the offsets and lengths of each kovs, voice.enum and VoiceLinkList.txt in the OPPW3 sound folder, are these file types supported?



[OPPW3 Voice files](http://www.mediafire.com/file/7uq8ceigey1jp9i/OPPW3_VOICE.7z/file)
## Post #72
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-20T06:57:50+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from hellacopters ↑Thu Mar 19, 2020 7:05 pm at Thu Mar 19, 2020 7:05 pm
>
> 
I just wanted to stop by and thank Yretenai for their work! Because of the tools you and the community have developed, I've been able to start work on a fan site for the game Final Fantasy Opera Omnia using textures and animations right from the files. 

One mystery in the game files I've yet to solve has been some of these so called "XL" header bins that are likely xor-ed json files that contain ability data and text strings. Being that I heard from chrrox on Discord that all Team Ninja games might use the same encryption (not sure if that's true) I was wondering if there was a process I could check these files with.

Thank you!

Opera Omnia Bins.zip

These are not XORed json files.
I looked at DFFOO before, it does not use this encryption when it caches downloaded files.
XL files in this case are a deriviation of ECB files, which are repeated structures with numerical data-- DFFNT has a more "advanced" version of this.
TL;DR it's a specialized serialized format without names, usually an array of numbers-- not an obfuscated json file.

Thanks for reminding me I gotta figure out how to download and decrypt DFFOO files.

> Reply from JosouKitsune ↑Fri Mar 20, 2020 3:58 am at Fri Mar 20, 2020 3:58 am
>
> 
Hi I found this voice.pac that contains multiple KOVS, alongside a voice.hed with the offsets and lengths of each kovs, voice.enum and VoiceLinkList.txt in the OPPW3 sound folder, are these file types supported?

I'll add support for this. KVS is typically supported, but this archive is unimplemented atm.
Should have it in a day or two.
## Post #73
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-03-20T21:54:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Mar 20, 2020 2:57 pm at Fri Mar 20, 2020 2:57 pm
>
> 
These are not XORed json files.
I looked at DFFOO before, it does not use this encryption when it caches downloaded files.
XL files in this case are a deriviation of ECB files, which are repeated structures with numerical data-- DFFNT has a more "advanced" version of this.
TL;DR it's a specialized serialized format without names, usually an array of numbers-- not an obfuscated json file.

Thanks for reminding me I gotta figure out how to download and decrypt DFFOO files.

And the plot thickens  

Thank you for all you do! Allow me to be of help if you need anything. I keep directory of all game files from both the JP and GL versions!

Very interested in contributing!
## Post #74
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-22T02:52:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from hellacopters ↑Sat Mar 21, 2020 5:54 am at Sat Mar 21, 2020 5:54 am
>
> 
And the plot thickens  

Thank you for all you do! Allow me to be of help if you need anything. I keep directory of all game files from both the JP and GL versions!

Very interested in contributing!

The issue is I barely have knowledge on getting the XOR table on PC, I haven't got the faintest clue on getting it on Android or iOS.
I got the URLs, apks, and the filelist but I can't figure the table out.
## Post #75
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-03-22T07:40:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sun Mar 22, 2020 10:52 am at Sun Mar 22, 2020 10:52 am
>
> 
The issue is I barely have knowledge on getting the XOR table on PC, I haven't got the faintest clue on getting it on Android or iOS.
I got the URLs, apks, and the filelist but I can't figure the table out.

Same Boat. I've been playing around with the Android Studio SDK. Seeing if I could somehow recompile the APK in a working environment. But I haven't been able to get it to run yet to find anything
## Post #76
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-25T01:38:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Sorry for the possible dumb questions, but I've only recently found this thread, and I'm trying to get the models from AOT2 Final Battle

Could someone tell me the correct tools to use inside the build?
## Post #77
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-27T05:47:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

New build 37: OPPW4 filetable.

> Reply from Eag1e ↑Wed Mar 25, 2020 9:38 am at Wed Mar 25, 2020 9:38 am
>
> 
Sorry for the possible dumb questions, but I've only recently found this thread, and I'm trying to get the models from AOT2 Final Battle

Could someone tell me the correct tools to use inside the build?

Cethleann.DataExporter, I think for AOT2 it's mode is --lnk or --linkbin.
## Post #78
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-27T06:04:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Mar 27, 2020 1:47 pm at Fri Mar 27, 2020 1:47 pm
>
> 
New build 37: OPPW4 filetable.

Thanks for your work, does it support the Linkdata bins? I tried using unbunbler, but they didn't extract.

Sample: [OPPW4 LINKDATA BINS](https://www.mediafire.com/file/muxxjgvx111y8nm/OPPW4_LINKDATA_BIN_CMN.7z/file)

Also the tool ask for these .file


But I only see these
## Post #79
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-27T14:06:47+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from JosouKitsune ↑Fri Mar 27, 2020 2:04 pm at Fri Mar 27, 2020 2:04 pm
>
> 
Yretenai wrote: ↑Fri Mar 27, 2020 1:47 pm
New build 37: OPPW4 filetable.


Thanks for your work, does it support the Linkdata bins? I tried using unbunbler, but they didn't extract.

Sample: OPPW4 LINKDATA BINS

Also the tool ask for these .file

But I only see these

DataExtractor should be able to extract them with --flayn.
Also, that's an expected outcome. those files are .NAME files which are very rarely shipped with games. Safe to ignore.
## Post #80
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-27T15:17:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Mar 27, 2020 10:06 pm at Fri Mar 27, 2020 10:06 pm
>
> 

DataExtractor should be able to extract them with --flayn.
Also, that's an expected outcome. those files are .NAME files which are very rarely shipped with games. Safe to ignore.

Doesn't Flayn need the IDX pair? PW4 only has the bin files.
## Post #81
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-27T21:09:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is there a way to repack the RDB, I want to add a PlayStation layout.
## Post #82
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-28T15:21:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from JosouKitsune ↑Sat Mar 28, 2020 5:09 am at Sat Mar 28, 2020 5:09 am
>
> 
Is there a way to repack the RDB, I want to add a PlayStation layout.

no, not yet anyway

> Reply from JosouKitsune ↑Fri Mar 27, 2020 11:17 pm at Fri Mar 27, 2020 11:17 pm
>
> 
Yretenai wrote: ↑Fri Mar 27, 2020 10:06 pm

DataExtractor should be able to extract them with --flayn.
Also, that's an expected outcome. those files are .NAME files which are very rarely shipped with games. Safe to ignore.


Doesn't Flayn need the IDX pair? PW4 only has the bin files.

--leonhart / --linkarchive
## Post #83
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-29T21:04:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

So I tried the tool with AOT2 and PW4, and trying to put in the tools commands, but I'm not sure if I'm doing it right? 
One thing I noticed is I put in the directory for my external hard drive (E:) but it's trying to locate the folder in C: it seems
I'm pretty new to using Command Prompt with tools so apologies for being a noob lol
## Post #84
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-29T22:44:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Eag1e ↑Mon Mar 30, 2020 5:04 am at Mon Mar 30, 2020 5:04 am
>
> 

So I tried the tool with AOT2 and PW4, and trying to put in the tools commands, but I'm not sure if I'm doing it right? 
One thing I noticed is I put in the directory for my external hard drive (E:) but it's trying to locate the folder in C: it seems
I'm pretty new to using Command Prompt with tools so apologies for being a noob lol

put the path (E:\Games\One Piece Pirate Warriors 4\File\CMN\AssetRelease\Retail) in quiotatino marks.
i.e.
"E:\Games\One Piece Pirate Warriors 4\File\CMN\AssetRelease\Retail"

you want to put all paths that have have a space in quotation marks.
## Post #85
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-29T23:36:29+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Eag1e ↑Mon Mar 30, 2020 5:04 am at Mon Mar 30, 2020 5:04 am
>
> 

So I tried the tool with AOT2 and PW4, and trying to put in the tools commands, but I'm not sure if I'm doing it right? 
One thing I noticed is I put in the directory for my external hard drive (E:) but it's trying to locate the folder in C: it seems
I'm pretty new to using Command Prompt with tools so apologies for being a noob lol

Also for OPPW4 it's not --leonhart but --nyotengu (or --rdb).
And you swapped the paths, you must put the output directory first then the RDB location after the --nyotengoku command
## Post #86
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-30T01:00:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Oooh ok, I'll try that tomorrow, thanks for all the help!
## Post #87
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-03-30T15:16:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

How do I extract G1Ms from MDLPACK and G1MPACK from Nioh?
## Post #88
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-30T16:16:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from ngovandang ↑Mon Mar 30, 2020 11:16 pm at Mon Mar 30, 2020 11:16 pm
>
> 
How do I extract G1Ms from MDLPACK and G1MPACK from Nioh?
You drag and drop it on to the Cethleann.Unbundler.exe and it will get unpacked from where ever the sample is located.
## Post #89
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-03-30T16:19:29+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Tue Mar 31, 2020 12:16 am at Tue Mar 31, 2020 12:16 am
>
> 
You drag and drop it on to the Cethleann.Unbundler.exe and it will get unpacked from where ever the sample is located.
Great, thank you. I did the same with g1t but seem to not working
## Post #90
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-03-30T16:20:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Can Cethleann extract the OPPW4 file? I suspect this is a sound file.
[1.png](https://xentaxbackup.github.io/file/17845_1.png)
## Post #91
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-03-30T16:22:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from bymutou ↑Tue Mar 31, 2020 12:20 am at Tue Mar 31, 2020 12:20 am
>
> 
Can Cethleann extract the OPPW4 file? I suspect this is a sound file.
## Post #92
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-30T16:24:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from ngovandang ↑Tue Mar 31, 2020 12:19 am at Tue Mar 31, 2020 12:19 am
>
> Great, thank you. I did the same with g1t but seem to not working
G1T only works when you drag and drop it in Noesis, (or on to daemon's tool) then it will load all textures, and on export it will save them to your desired format.
Assuming you have the python script installed in the python folder.
## Post #93
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-30T20:26:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from ngovandang ↑Tue Mar 31, 2020 12:19 am at Tue Mar 31, 2020 12:19 am
>
> 
mono24 wrote: ↑Tue Mar 31, 2020 12:16 am
You drag and drop it on to the Cethleann.Unbundler.exe and it will get unpacked from where ever the sample is located.

Great, thank you. I did the same with g1t but seem to not working

G1Ts are textures, use the noesis plugin.
## Post #94
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-30T20:27:29+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from bymutou ↑Tue Mar 31, 2020 12:20 am at Tue Mar 31, 2020 12:20 am
>
> 
Can Cethleann extract the OPPW4 file? I suspect this is a sound file.

it extracts it but it can't convert it.
## Post #95
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-03-30T21:25:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Tue Mar 31, 2020 4:27 am at Tue Mar 31, 2020 4:27 am
>
> 
bymutou wrote: ↑Tue Mar 31, 2020 12:20 am
Can Cethleann extract the OPPW4 file? I suspect this is a sound file.


it extracts it but it can't convert it.

How to extract it? Let me see if there is a way to convert
## Post #96
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-03-30T21:26:56+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Tue Mar 31, 2020 4:27 am at Tue Mar 31, 2020 4:27 am
>
> 
bymutou wrote: ↑Tue Mar 31, 2020 12:20 am
Can Cethleann extract the OPPW4 file? I suspect this is a sound file.


it extracts it but it can't convert it.

When I use rdb to extract, Cethleann will report an error
## Post #97
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-31T03:48:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from bymutou ↑Tue Mar 31, 2020 5:26 am at Tue Mar 31, 2020 5:26 am
>
> 
When I use rdb to extract, Cethleann will report an error

what error?
## Post #98
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-31T17:39:33+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from bymutou ↑Tue Mar 31, 2020 5:26 am at Tue Mar 31, 2020 5:26 am
>
> 

When I use rdb to extract, Cethleann will report an error

This is the command I used, it extracted fine.

```
Cethleann.DataExporter --rdb -g OnePiece4 "path-to-extract" "C:\Program Files (x86)\Steam\steamapps\common\OPPW4\File\CMN\AssetRelease\Retail"
```


Replace path-to-extract with your desired path.
## Post #99
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-03-31T20:35:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from JosouKitsune ↑Wed Apr 01, 2020 1:39 am at Wed Apr 01, 2020 1:39 am
>
> 
bymutou wrote: ↑Tue Mar 31, 2020 5:26 am

When I use rdb to extract, Cethleann will report an error


This is the command I used, it extracted fine.
Code: Select allCethleann.DataExporter --rdb -g OnePiece4 "path-to-extract" "C:\Program Files (x86)\Steam\steamapps\common\OPPW4\File\CMN\AssetRelease\Retail"

Replace path-to-extract with your desired path.
Unable to extract .files in the data folder, an error will be reported
[1.png](https://xentaxbackup.github.io/file/17852_1.png)
## Post #100
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-31T23:28:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from bymutou ↑Wed Apr 01, 2020 4:35 am at Wed Apr 01, 2020 4:35 am
>
> 
JosouKitsune wrote: ↑Wed Apr 01, 2020 1:39 am
bymutou wrote: ↑Tue Mar 31, 2020 5:26 am

When I use rdb to extract, Cethleann will report an error


This is the command I used, it extracted fine.
Code: Select allCethleann.DataExporter --rdb -g OnePiece4 "path-to-extract" "C:\Program Files (x86)\Steam\steamapps\common\OPPW4\File\CMN\AssetRelease\Retail"

Replace path-to-extract with your desired path.

Unable to extract .files in the data folder, an error will be reported
Just let the program finish, that message is due to some files not being in the retail build.
## Post #101
- Username: Enola
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 27, 2019 4:44 pm
- Post datetime: 2020-04-01T09:48:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

support to text file export ?
## Post #102
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-01T17:18:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from JosouKitsune ↑Wed Apr 01, 2020 7:28 am at Wed Apr 01, 2020 7:28 am
>
> 
bymutou wrote: ↑Wed Apr 01, 2020 4:35 am
JosouKitsune wrote: ↑Wed Apr 01, 2020 1:39 am


This is the command I used, it extracted fine.
Code: Select allCethleann.DataExporter --rdb -g OnePiece4 "path-to-extract" "C:\Program Files (x86)\Steam\steamapps\common\OPPW4\File\CMN\AssetRelease\Retail"

Replace path-to-extract with your desired path.

Unable to extract .files in the data folder, an error will be reported

Just let the program finish, that message is due to some files not being in the retail build.

Correct, it's complaining about NAME files, which are used for filenames.

> Reply from Enola ↑Wed Apr 01, 2020 5:48 pm at Wed Apr 01, 2020 5:48 pm
>
> 
support to text file export ?

wdym text file export?
## Post #103
- Username: Enola
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 27, 2019 4:44 pm
- Post datetime: 2020-04-02T00:19:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Correction 
Is it possible to extract language text files
## Post #104
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-02T04:09:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Enola ↑Thu Apr 02, 2020 8:19 am at Thu Apr 02, 2020 8:19 am
>
> 
Correction 
Is it possible to extract language text files

depends on game. FETH is the only one supported I think.
## Post #105
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-04-02T16:37:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

so I got an error for OPPW4 G1T merger, dunno if I did anything wrong here or not...

> Nyotengu.KTID.exe -g OnePiece4 F:\HACTool\OPPW4\secure\RomFS\File\CMN\AssetRelease\Retail\extract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidsobjdb F:\HACTool\OPPW4\secure\RomFS\File\CMN\AssetRelease\Retail\extract\MaterialEditor\g1t F:\HACTool\OPPW4\secure\RomFS\File\CMN\AssetRelease\Retail\extract\CharacterEditor\ktid\MPLC009_Ace.ktid
>
> [2020-04-02T16:25:27][Nyotengu] Nyotengu.KTID v1.0.42.0
>
> Unhandled exception. System.NullReferenceException: Object reference not set to an instance of an object.
>
>    at System.Linq.Enumerable.SelectManySingleSelectorIterator`2.MoveNext()
>
>    at Nyotengu.KTID.Program.Main(String[] args) in C:\projects\cethleann\Nyotengu.KTID\Program.cs:line 65

edit:
nvm, solved my issue, did the wrong file lol
## Post #106
- Username: meecube
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 04, 2020 9:04 pm
- Post datetime: 2020-04-05T20:45:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hey! once getting the final file into Blender, the rig is broken, only affecting the shins, but the placement is completely off too. any advice?
## Post #107
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-05T21:09:35+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from meecube ↑Mon Apr 06, 2020 4:45 am at Mon Apr 06, 2020 4:45 am
>
> 
Hey! once getting the final file into Blender, the rig is broken, only affecting the shins, but the placement is completely off too. any advice?

wrong thread
## Post #108
- Username: Grayfall
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 18, 2019 4:18 pm
- Post datetime: 2020-04-07T19:42:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

dude i have no idea since its no actual tutorial but this is what i got
## Post #109
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-04-08T01:50:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Will tool support extracting new One Piece 4 DLCs .bin files?
## Post #110
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-04-12T03:44:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sat Feb 01, 2020 9:17 pm at Sat Feb 01, 2020 9:17 pm
>
> 
demonslayerx8 wrote: ↑Sat Feb 01, 2020 7:21 am
Alright cool, I'll wait til the container support is added~


Wrapped files are now supported.
Keep in mind that AOT2 has no filenames, so you just have to do the tried and tested method of unwrapping every file.
Use Cethleann.Unbundler.exe to unwrap them, or pass --recursive to Omega.DataExporter.exe's command line options

Models and textures tend to be in ptrbundle files.

So I was able to extract the files for AOT2, folders with g1t textures seem to be working fine. 
Although unpacking the ptrbundles with Cethleann.Unbundler for the model files gave me g1m files, noesis gave an error message when trying to preview them  
is there any way to fix them/make them work?
## Post #111
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-13T03:42:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Eag1e ↑Sun Apr 12, 2020 11:44 am at Sun Apr 12, 2020 11:44 am
>
> 
So I was able to extract the files for AOT2, folders with g1t textures seem to be working fine. 
Although unpacking the ptrbundles with Cethleann.Unbundler for the model files gave me g1m files, noesis gave an error message when trying to preview them  
is there any way to fix them/make them work?

make a reply in the g1m plugin thread
## Post #112
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-13T06:45:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann.Unbundler has been updated to support Nobunaga Online .PC and .BIN files.
This update is also a major refactor so please report any crashes, and no I'm still not going to write a tutorial- The lower I make the barrier for using these tools the more stress I get trying to maintain it.
## Post #113
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-04-13T21:30:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Does this tool support the .ZL_ files from marvel ultimate alliance 3?
## Post #114
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-14T00:03:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from CosmicDreams ↑Tue Apr 14, 2020 5:30 am at Tue Apr 14, 2020 5:30 am
>
> 
Does this tool support the .ZL_ files from marvel ultimate alliance 3?

MUA3 ZL files are stream compressed files, use Cethleann.Gz.

```

```


i.e.

```

```
## Post #115
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2020-04-14T18:05:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Mon Apr 13, 2020 2:45 pm at Mon Apr 13, 2020 2:45 pm
>
> 
Cethleann.Unbundler has been updated to support Nobunaga Online .PC and .BIN files.
This update is also a major refactor so please report any crashes, and no I'm still not going to write a tutorial- The lower I make the barrier for using these tools the more stress I get trying to maintain it.
Thank you for your support

```

```

I gave instructions, but nothing happened, how do I use it
## Post #116
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-14T19:38:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from wordhg ↑Wed Apr 15, 2020 2:05 am at Wed Apr 15, 2020 2:05 am
>
> 
Yretenai wrote: ↑Mon Apr 13, 2020 2:45 pm
Cethleann.Unbundler has been updated to support Nobunaga Online .PC and .BIN files.
This update is also a major refactor so please report any crashes, and no I'm still not going to write a tutorial- The lower I make the barrier for using these tools the more stress I get trying to maintain it.

Thank you for your support
Code: Select allCethleann.DataExporter --flayn -g NobunagaOnline "F:\extract\nol\HD\dump" "F:\extract\nol\HD\data" "F:\extract\nol\HD\data\battle" "F:\extract\nol\HD\data\common"

I gave instructions, but nothing happened, how do I use it

use unbundler,. not dataexporter


```

```
## Post #117
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-04-15T15:09:58+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Tue Apr 14, 2020 8:03 am at Tue Apr 14, 2020 8:03 am
>
> 
CosmicDreams wrote: ↑Tue Apr 14, 2020 5:30 am
Does this tool support the .ZL_ files from marvel ultimate alliance 3?


MUA3 ZL files are stream compressed files, use Cethleann.Gz.
Code: Select allCethleann.Gz.exe --stream --prefixed-size -t Deflate {ZL files}


i.e.
Code: Select allCethleann.Gz.exe --stream --prefixed-size -t Deflate 0400_DLC_00_mdl.bin.ZL

Ah thanks. One thing tho is that the motion archives don't do anything when used with the unbundler. they do decompress though.
## Post #118
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-15T23:35:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from CosmicDreams ↑Wed Apr 15, 2020 11:09 pm at Wed Apr 15, 2020 11:09 pm
>
> 

Ah thanks. One thing tho is that the motion archives don't do anything when used with the unbundler. they do decompress though.

can you upload some of the motion archives?
## Post #119
- Username: zhanghongming123
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 16, 2019 1:01 pm
- Post datetime: 2020-04-16T12:34:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

this is a MUA3's motion archive
[http://www.mediafire.com/file/9cg6xxfes ... n.ZL_/file](http://www.mediafire.com/file/9cg6xxfeslci879/0000_AMERICA_mot.bin.ZL_/file)
## Post #120
- Username: TableCloth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 17, 2020 3:17 am
- Post datetime: 2020-04-17T07:24:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Real new to this type of stuff, but trying my best to understand.
It keeps saying game-dirs need a value, but I'm pretty sure I've done everything right?
Cethleann.DataExporter --rdb --game OnePiece4 "C:\Users\PC\Downloads\export" "D:\Games\One Piece Pirate Warriors 4\File\CMN\AssetRelease\Retail"
this is what I ran
[OPW4.PNG](https://xentaxbackup.github.io/file/17935_OPW4.PNG)
## Post #121
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-04-17T07:26:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Thanks for this extremely awesome tool!!!  
But how can i extract the animation properly?
I've a game named Warriors Orochi 4(PC)and there is a Linkdata.bin file(12GB). 
I drag this big file onto the "Cethleann.Unbundler.exe" then nothing happened and it closed.
I must have done something wrong but i have no idea on it. 

I successfully got those .G2A files by using Steven's Gas Machine. It decompressed the whole bin files and decrepted these files it extracted one by one. I am not sure whether i can do it more efficently like extracting the animation .G2A files only by using this tools.
Thanks in advance!
## Post #122
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-18T20:33:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from TableCloth ↑Fri Apr 17, 2020 3:24 pm at Fri Apr 17, 2020 3:24 pm
>
> 
Real new to this type of stuff, but trying my best to understand.
It keeps saying game-dirs need a value, but I'm pretty sure I've done everything right?
Cethleann.DataExporter --rdb --game OnePiece4 "C:\Users\PC\Downloads\export" "D:\Games\One Piece Pirate Warriors 4\File\CMN\AssetRelease\Retail"
this is what I ran

Cannot reproduce, please verify you're using the latest version.
## Post #123
- Username: TableCloth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 17, 2020 3:17 am
- Post datetime: 2020-04-18T20:52:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Might be because cause It's a cracked game, no idea at this point.
## Post #124
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-19T18:27:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Kanbara ↑Fri Apr 17, 2020 3:26 pm at Fri Apr 17, 2020 3:26 pm
>
> 
Thanks for this extremely awesome tool!!!  
But how can i extract the animation properly?
I've a game named Warriors Orochi 4(PC)and there is a Linkdata.bin file(12GB). 
I drag this big file onto the "Cethleann.Unbundler.exe" then nothing happened and it closed.
I must have done something wrong but i have no idea on it. 

I successfully got those .G2A files by using Steven's Gas Machine. It decompressed the whole bin files and decrepted these files it extracted one by one. I am not sure whether i can do it more efficently like extracting the animation .G2A files only by using this tools.
Thanks in advance!

You should use the Cethleann.DataExporter with the --linkarchive option (double check the previous posts to make sure) 

> Reply from TableCloth ↑Fri Apr 17, 2020 3:24 pm at Fri Apr 17, 2020 3:24 pm
>
> 
Real new to this type of stuff, but trying my best to understand.
It keeps saying game-dirs need a value, but I'm pretty sure I've done everything right?
Cethleann.DataExporter --rdb --game OnePiece4 "C:\Users\PC\Downloads\export" "D:\Games\One Piece Pirate Warriors 4\File\CMN\AssetRelease\Retail"
this is what I ran

Try to put all of your stuff on the same Disk (the tools, the destination directory and the game directory all on C: or D:) and try again. If you put all on D and want to use the command line on that disk simply type "D:" first in the cmd
## Post #125
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-05-03T16:17:33+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I lost track of this thread. I'm trying to extract from One Piece: Pirate Warriors 3 for PC, which uses 'LINKDATA_EU_OS_EUNA.A' and so on for Archive files. I've been trying to specify it to extract these files into a specific folder but any time I try the usual methods with DataExporter all it does is inform me of the program name and version, and nothing else. Am I messing up the command line? Currently I'm trying...
D:\Downloads\CethleannStandalone_netcore30\Cethleann.DataExporter.exe --flayn "D:\Downloads\OPPW3" "D:\SteamLibrary\steamapps\common\OPPW3\LINKDATA_DX9"
And the result is always just
[2020-05-03T16:03:04][Cethleann] Cethleann.DataExporter v1.0.46.0

It doesn't seem to recognize any of them.
## Post #126
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-05-03T20:18:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Doctor Loboto ↑Mon May 04, 2020 12:17 am at Mon May 04, 2020 12:17 am
>
> 
I lost track of this thread. I'm trying to extract from One Piece: Pirate Warriors 3 for PC, which uses 'LINKDATA_EU_OS_EUNA.A' and so on for Archive files. I've been trying to specify it to extract these files into a specific folder but any time I try the usual methods with DataExporter all it does is inform me of the program name and version, and nothing else. Am I messing up the command line? Currently I'm trying...
D:\Downloads\CethleannStandalone_netcore30\Cethleann.DataExporter.exe --flayn "D:\Downloads\OPPW3" "D:\SteamLibrary\steamapps\common\OPPW3\LINKDATA_DX9"
And the result is always just
[2020-05-03T16:03:04][Cethleann] Cethleann.DataExporter v1.0.46.0

It doesn't seem to recognize any of them.
This tool only works with the dlc bin files, to extract the linkdata you need to use Steven gas machine
## Post #127
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-05-07T11:12:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hi, I have a question.
Does Cethleann support Dynasty Warrior 9?
I previously extracted them on Gas machine.
This time, my friend bought DW9, so he tried to extract LINKDATA(multiple) with Cethleann, but it didn't work.
## Post #128
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-05-07T15:48:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from einherjar007 ↑Thu May 07, 2020 7:12 pm at Thu May 07, 2020 7:12 pm
>
> Does Cethleann support Dynasty Warrior 9?
I think DW8/9/Nioh still can not be extracted in a proper way, some compression issues if I remember correctly.
## Post #129
- Username: LillianGoulston
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 13, 2020 4:29 am
- Post datetime: 2020-05-12T20:35:37+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm trying to repack an RDB file from Persona 5 Scramble (Switch) so I can localize some of the .g1t UI elements. Unpacking has been easy, but repacking is something I haven't been able to figure out. Is there a way to do this with Cethleann (or any other tool)? The file path is: 
```
/ROMFS/data/motor_rsc/ScreenLayout.rdb
```
## Post #130
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-05-13T10:57:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from LillianGoulston ↑Wed May 13, 2020 4:35 am at Wed May 13, 2020 4:35 am
>
> 
I'm trying to repack an RDB file from Persona 5 Scramble (Switch) so I can localize some of the .g1t UI elements. Unpacking has been easy, but repacking is something I haven't been able to figure out. Is there a way to do this with Cethleann (or any other tool)? The file path is: Code: Select all/ROMFS/data/motor_rsc/ScreenLayout.rdb

Not yet.
## Post #131
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-05-15T10:37:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Thu May 07, 2020 11:48 pm at Thu May 07, 2020 11:48 pm
>
> 
einherjar007 wrote: ↑Thu May 07, 2020 7:12 pmDoes Cethleann support Dynasty Warrior 9?
I think DW8/9/Nioh still can not be extracted in a proper way, some compression issues if I remember correctly.

Is this right? @Yretenai
## Post #132
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-05-16T13:25:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Thu May 07, 2020 11:48 pm at Thu May 07, 2020 11:48 pm
>
> 
einherjar007 wrote: ↑Thu May 07, 2020 7:12 pmDoes Cethleann support Dynasty Warrior 9?
I think DW8/9/Nioh still can not be extracted in a proper way, some compression issues if I remember correctly.

Can't talk 'bout DW8/9 as i didn't extract them. As for Nioh, you'll be missing the characters from the PC version as those files where xored and Yretenai wasn't sure to spend more time looking for the key. But you can look for Nioh PS4 fake pkg and get the files from that version, i remember the extractor working properly~
## Post #133
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-05-17T00:38:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from KingJuls ↑Fri May 15, 2020 6:37 pm at Fri May 15, 2020 6:37 pm
>
> 
mono24 wrote: ↑Thu May 07, 2020 11:48 pm
einherjar007 wrote: ↑Thu May 07, 2020 7:12 pmDoes Cethleann support Dynasty Warrior 9?
I think DW8/9/Nioh still can not be extracted in a proper way, some compression issues if I remember correctly.


Is this right? @Yretenai

yes, DW8/9 is indev, Nioh support is abandoned due to me not having a clue.
## Post #134
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2020-05-25T03:31:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I wanted to ask a bit of a question regarding packing back resources again, specifically NT.

Currently, thanks to your tool, i am able to unpack resources by decrypting them and so on, but i wonder, how hard would it be to pack them back?

I know this not something that you have around now, and maybe not anytime soon, but is packing something you are currently working on? I was curious to know if repacking resources is far or close in your priority list.

If that isn't the case, which is fine, i was wondering if it's something i could do myself based off your source? I have experience in importing and exporting 3D models in other games, which is basically following the same structure, writing a binary reader to the 3d edtor and then you use the same structure with a binary writer and bam, you slam it into the resources, that's not an issue when it comes to 3D files, but when decrypting and encrypting, is it the same logic?

Encryption is not my field of knowledge, so i am not aware how hard this is, but if it's as easy as doing the reverse process as you did for unpacking the NT resources following your source (aka you followed a strucutre for reading so writing it back should give us the same file), i could look into doing that myself, but if it requires more things that are exclusive to encryption then i'll probably get lost, but i could still try.

I am asking this basically because, i want to expand the game's lifespan by modding the game, skins being the first objective, since skin mods always bring people together, and maybe other resources in the game.

It's one of my favorite games and i'd like to do whatever i can to make it more accesible with lower poly models and so on to make more people play, for example.
## Post #135
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-05-25T23:57:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Seyren ↑Mon May 25, 2020 11:31 am at Mon May 25, 2020 11:31 am
>
> 
I wanted to ask a bit of a question regarding packing back resources again, specifically NT.

Currently, thanks to your tool, i am able to unpack resources by decrypting them and so on, but i wonder, how hard would it be to pack them back?

I know this not something that you have around now, and maybe not anytime soon, but is packing something you are currently working on? I was curious to know if repacking resources is far or close in your priority list.

If that isn't the case, which is fine, i was wondering if it's something i could do myself based off your source? I have experience in importing and exporting 3D models in other games, which is basically following the same structure, writing a binary reader to the 3d edtor and then you use the same structure with a binary writer and bam, you slam it into the resources, that's not an issue when it comes to 3D files, but when decrypting and encrypting, is it the same logic?

Encryption is not my field of knowledge, so i am not aware how hard this is, but if it's as easy as doing the reverse process as you did for unpacking the NT resources following your source (aka you followed a strucutre for reading so writing it back should give us the same file), i could look into doing that myself, but if it requires more things that are exclusive to encryption then i'll probably get lost, but i could still try.

I am asking this basically because, i want to expand the game's lifespan by modding the game, skins being the first objective, since skin mods always bring people together, and maybe other resources in the game.

It's one of my favorite games and i'd like to do whatever i can to make it more accesible with lower poly models and so on to make more people play, for example.

DFFNT's storage and encryption is not the issue, but it's the underlying engine systems.
A lot of the """dynamic""" data is defined in ECB files which change structure frequently (also from file to file)
Graphical formats cannot be exported as of right now either.

But yes, it should be relatively easy to repack game assets. All I have to do is determine how they calculate the checksum.
## Post #136
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2020-05-29T22:24:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Tue May 26, 2020 7:57 am at Tue May 26, 2020 7:57 am
>
> 


DFFNT's storage and encryption is not the issue, but it's the underlying engine systems.
A lot of the """dynamic""" data is defined in ECB files which change structure frequently (also from file to file)
Graphical formats cannot be exported as of right now either.

But yes, it should be relatively easy to repack game assets. All I have to do is determine how they calculate the checksum.

That would be awesome if you could! Even if 3D models can't be done for now, anything we can do to play around with the game would be a blessing, thank you so much for the answer!
## Post #137
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-06-09T21:58:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Being that this thread is a great resource for all Koei Tecmo games, I figured this would be best the place to post about my on gong mission with Dissidia Opera Omnia.

For a while now I've been running a fan site where I post character information and resources. The biggest drag is that there is no direct way to access this information other than copying it from in game, because the game doesn't store this information in its local files. 

[I recently captured some api calls](https://drive.google.com/drive/folders/1x_h552grvUsEtkL9gL5nPcjnQkSWivCS?usp=sharing) and wanted to see if I could get some direction on the best way to go about decrypting them. Decompile the dex? Load the .so file into IDA pro? Capture the game's memory after it's decrypted them? This is the info I'm looking for and it's super frustrating being this close yet so far   

Maybe someone else out there has taken a look around or is familiar with how KT works and could give me a head start.

Thanks!
## Post #138
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2020-06-11T11:47:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Vagonumero13 has been commisioned by a Deviantart user to make a modder for NT, it can be downloaded here:
[https://www.deviantart.com/monkeygigabu ... -845032207](https://www.deviantart.com/monkeygigabuster/art/DFFNT-mod-Lion-Heart-for-Squall-845032207)

So it's technically possible to mod the game now with this, i will look into it and see if he makes any upgrades.

Maybe this tool can help in any way the swiss knife? Just wanted to put it here because i think it's an important achievement!
## Post #139
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-06-12T20:59:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from hellacopters ↑Wed Jun 10, 2020 5:58 am at Wed Jun 10, 2020 5:58 am
>
> 
Being that this thread is a great resource for all Koei Tecmo games, I figured this would be best the place to post about my on gong mission with Dissidia Opera Omnia.

For a while now I've been running a fan site where I post character information and resources. The biggest drag is that there is no direct way to access this information other than copying it from in game, because the game doesn't store this information in its local files. 

I recently captured some api calls and wanted to see if I could get some direction on the best way to go about decrypting them. Decompile the dex? Load the .so file into IDA pro? Capture the game's memory after it's decrypted them? This is the info I'm looking for and it's super frustrating being this close yet so far   

Maybe someone else out there has taken a look around or is familiar with how KT works and could give me a head start.

Thanks!

The game downloads files from a server (I can DM you this) but the filelist it downloads is encrypted using an AES key.

I don't know how to get the decryption key on android.
## Post #140
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-06-12T21:15:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Seyren ↑Thu Jun 11, 2020 7:47 pm at Thu Jun 11, 2020 7:47 pm
>
> 
Vagonumero13 has been commisioned by a Deviantart user to make a modder for NT, it can be downloaded here:
https://www.deviantart.com/monkeygigabu ... -845032207

So it's technically possible to mod the game now with this, i will look into it and see if he makes any upgrades.

Maybe this tool can help in any way the swiss knife? Just wanted to put it here because i think it's an important achievement!

Maybe. I'm still considering adding a DFFNT repacker, but I really want to control ECB files because if I can do that we'll be able to add files into DFFNT rather than replace stuff. That said for DFFNT to be moddable with Cethleann you'd need a G1T and G1M exporter. That said Ceth can dump files for you to potentially mod.

It's a lot of work and IDK if I have the motiviation atm.
## Post #141
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-06-17T15:13:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Build 54 adds a new tool DataProcessor which is a development tool to processes structures.
Along with that it adds support for new Nioh 2 RESPACK bundles and fixes a lot of bugs.

Previous changes: [viewtopic.php?f=10&t=21679&p=160886#p160886](https://forum.xentax.com/viewtopic.php?f=10&t=21679&p=160886#p160886)
## Post #142
- Username: Gagnetar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 04, 2018 7:20 am
- Post datetime: 2020-07-09T05:34:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Took a while but I figured out how to extract stuff from Three Houses as intended.
It dumps a se_ktsl2 folder with .KTSRw files that don't seem to be extractable by Cethleann.
From what I understand this audio collection includes attack grunts and/or general SFX.
Anyway we'll see compatibility for them?
## Post #143
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2020-07-26T09:40:03+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I have been trying to extract the character animation files from FETH, but I having some issues on trying to figuring it out.

I have used Cethleann.Unbundler on the character bin files by dragging said files into the executable, but it only returns the G1M and G1T files, but no G2A files. 

My question is, how do I extract the animation files from FETH? I have tried googling for answers, but I couldn't find any information regrading extracting the FETH character animations whatsoever.
## Post #144
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-26T12:56:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Tangil ↑Sun Jul 26, 2020 5:40 pm at Sun Jul 26, 2020 5:40 pm
>
> 
Hi, I have been trying to extract the character animation files from FETH, but I having some issues on trying to figuring it out.

I have used Cethleann.Unbundler on the character bin files by dragging said files into the executable, but it only returns the G1M and G1T files, but no G2A files. 

My question is, how do I extract the animation files from FETH? I have tried googling for answers, but I couldn't find any information regrading extracting the FETH character animations whatsoever.

Animations are not in the same place as the models, since they're shared by all the characters or sorted by specific classes/monster species
## Post #145
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2020-07-26T17:55:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Sun Jul 26, 2020 8:56 pm at Sun Jul 26, 2020 8:56 pm
>
> 
Animations are not in the same place as the models, since they're shared by all the characters or sorted by specific classes/monster species

Thanks for replying. I figured I was looking in the wrong place. 

There's a motion folder that also contains .bin files. I assume that's where the animations are stored for all the models since I was able to find some g1a animations upon using the Unbundler on the datatable files. The filenames are numbered and they range from 4253 - 4273 and 4622 - 4632. 

However, the files numbered, 4622 - 4632 and correct me if I am wrong. I am assuming those are the character animations, since upon dragging files to the Unbundler, yields .gz  archive files that I can't seem to extract with any of the Cethleann tools provided nor that I open directly with an archive extraction tool. 

In that case, do I need to rename those files or use another tool to open these .gz files? Because I also couldn't find any answers on trying to extract those files.

EDIT: Also, I have noticed there were also .g1t.bin files that contains the character portraits, but renaming them to .g1t file format or using the Unbundler doesn't seem to do anything. So, I presuming I am missing an intermediate step in the extraction process.
## Post #146
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-26T20:42:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Tangil ↑Mon Jul 27, 2020 1:55 am at Mon Jul 27, 2020 1:55 am
>
> 
Joschka wrote: ↑Sun Jul 26, 2020 8:56 pm
Animations are not in the same place as the models, since they're shared by all the characters or sorted by specific classes/monster species


Thanks for replying. I figured I was looking in the wrong place. 

There's a motion folder that also contains .bin files. I assume that's where the animations are stored for all the models since I was able to find some g1a animations upon using the Unbundler on the datatable files. The filenames are numbered and they range from 4253 - 4273 and 4622 - 4632. 

However, the files numbered, 4622 - 4632 and correct me if I am wrong. I am assuming those are the character animations, since upon dragging files to the Unbundler, yields .gz  archive files that I can't seem to extract with any of the Cethleann tools provided nor that I open directly with an archive extraction tool. 

In that case, do I need to rename those files or use another tool to open these .gz files? Because I also couldn't find any answers on trying to extract those files.

EDIT: Also, I have noticed there were also .g1t.bin files that contains the character portraits, but renaming them to .g1t file format or using the Unbundler doesn't seem to do anything. So, I presuming I am missing an intermediate step in the extraction process.

Yeah it's because KT has containers in compressed containers, and the latter are in containers too.
Here's how you get the anim files, going to use container 4623.bin as an example.

-Drag and drop 4623.bin on the Unbundler, you'll get .gz files.
-You first need to decompress these gz files. To decompress 0001.gz for example use

```
Cethleann.Gz.exe --gz path\to\gz\file\0001.gz
```

You'll get a container with the same name, without a .gz (so 0001 here).
-This is a container too. You could continue the drag and dropping but better use the recursive command to fully unpack everything directly

```
Cethleann.Unbundler.exe -R path\to\container\file\0001
```


The folders you're interested in are the 000F.datatable and the 0010.datatable, these are the ones with the animation files. 000F will always be there but 0010 will sometimes don't exist. The former is the most important, with all the body anims usually, 0010 usually has only 1 or two anims, which I think are for some face expressions, didn't test it myself. 

A few notes from when I looked a bit into these files :
-4622 seems to have all attack anims, sorted by classes. It's like 4622\classID\000F
-4623\0001\000F has some "being hit" anims, with some dodges too
-4624\0001\000F is the same but with mounts
-Monastery anims (like walking, running, eating etc) seem to be in the 4632 folder

Happy digging
## Post #147
- Username: Ctvicky
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 29, 2020 5:30 am
- Post datetime: 2020-07-28T21:37:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I just used the tool for FairytailRPG and it seems to work perfectly. Im trying to extract the audio files from the game and these were all of the files I could find. Just wondering if anyone knows how I can extract these files, I couldnt find anything on .srst or .srsa files
[494ec0475ed2c86230304c76d0c4d1a9.png](https://xentaxbackup.github.io/file/18526_494ec0475ed2c86230304c76d0c4d1a9.png)
## Post #148
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-29T00:17:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Ctvicky ↑Wed Jul 29, 2020 5:37 am at Wed Jul 29, 2020 5:37 am
>
> 
I just used the tool for FairytailRPG and it seems to work perfectly. Im trying to extract the audio files from the game and these were all of the files I could find. Just wondering if anyone knows how I can extract these files, I couldnt find anything on .srst or .srsa files

There was a discussion about these here [https://github.com/losnoco/vgmstream/issues/623](https://github.com/losnoco/vgmstream/issues/623)
## Post #149
- Username: DrDemon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 30, 2020 9:32 pm
- Post datetime: 2020-07-30T13:33:46+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I have been trying to rip Fairy Tail models since the game came out and am having no luck. 

Any Ideas?
[Capture.PNG](https://xentaxbackup.github.io/file/18532_Capture.PNG)
## Post #150
- Username: DrDemon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 30, 2020 9:32 pm
- Post datetime: 2020-07-30T13:38:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

This is what the files are for the models. Not really sure how to go about it.
[Capture.PNG](https://xentaxbackup.github.io/file/18534_Capture.PNG)
## Post #151
- Username: DrDemon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 30, 2020 9:32 pm
- Post datetime: 2020-07-30T14:17:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Update: I can rip everything except the files I want to rip. Hope the screenshot can help someone tell me what I am doing wrong.
[Untitled.png](https://xentaxbackup.github.io/file/18535_Untitled.png)
## Post #152
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-07-30T20:40:10+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from DrDemon ↑Thu Jul 30, 2020 10:17 pm at Thu Jul 30, 2020 10:17 pm
>
> 
Update: I can rip everything except the files I want to rip. Hope the screenshot can help someone tell me what I am doing wrong.

The tool extracts everything correctly with those parameters. . .



erza.png (96.91 KiB) Viewed 226 times
## Post #153
- Username: crist0393
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 31, 2018 1:54 am
- Post datetime: 2020-07-30T22:14:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is there a way to identify what texture goes with what model?
[Captura.PNG](https://xentaxbackup.github.io/file/18539_Captura.PNG)
## Post #154
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-30T22:30:03+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from crist0393 ↑Fri Jul 31, 2020 6:14 am at Fri Jul 31, 2020 6:14 am
>
> 
Is there a way to identify what texture goes with what model?

Yeah, just need to repack the g1t first since it's split in single texture g1t [viewtopic.php?f=10&t=21679&start=45#p160417](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=45#p160417)
Then just give the g1t when asked by the script

You can get animations associated to this character too, a tutorial is on that thread
## Post #155
- Username: narken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 31, 2020 6:56 am
- Post datetime: 2020-07-30T23:39:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm pretty noob, how do I get the g1m into blender or another program?
## Post #156
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-07-30T23:50:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm using the latest version of the fmt py for noesis and some models throw this exception:

(example model [https://mega.nz/file/YbgzjRgA#u_hhdXPgW ... 0e9zKFFk-E](https://mega.nz/file/YbgzjRgA#u_hhdXPgWljKF_cZjL3NJDiJKxX6OXRQ10e9zKFFk-E))




error.png (8.06 KiB) Viewed 204 times
## Post #157
- Username: crist0393
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 31, 2018 1:54 am
- Post datetime: 2020-07-30T23:56:46+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Fri Jul 31, 2020 6:30 am at Fri Jul 31, 2020 6:30 am
>
> 
crist0393 wrote: ↑Fri Jul 31, 2020 6:14 am
Is there a way to identify what texture goes with what model?


Yeah, just need to repack the g1t first since it's split in single texture g1t viewtopic.php?f=10&t=21679&start=45#p160417
Then just give the g1t when asked by the script

You can get animations associated to this character too, a tutorial is on that thread

Will it work with Fairy Tail models? The names are all random
## Post #158
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-31T00:10:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from narken ↑Fri Jul 31, 2020 7:39 am at Fri Jul 31, 2020 7:39 am
>
> 
I'm pretty noob, how do I get the g1m into blender or another program?
[viewtopic.php?f=16&t=21666](https://forum.xentax.com/viewtopic.php?f=16&t=21666)

> Reply from GDL ↑Fri Jul 31, 2020 7:50 am at Fri Jul 31, 2020 7:50 am
>
> 
I'm using the latest version of the fmt py for noesis and some models throw this exception:

(example model https://mega.nz/file/YbgzjRgA#u_hhdXPgW ... 0e9zKFFk-E)
[viewtopic.php?f=16&t=21666&start=225#p165428](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=225#p165428)



Capture.PNG (42.16 KiB) Viewed 197 times



> Reply from crist0393 ↑Fri Jul 31, 2020 7:56 am at Fri Jul 31, 2020 7:56 am
>
> 
Joschka wrote: ↑Fri Jul 31, 2020 6:30 am
crist0393 wrote: ↑Fri Jul 31, 2020 6:14 am
Is there a way to identify what texture goes with what model?


Yeah, just need to repack the g1t first since it's split in single texture g1t viewtopic.php?f=10&t=21679&start=45#p160417
Then just give the g1t when asked by the script

You can get animations associated to this character too, a tutorial is on that thread


Will it work with Fairy Tail models? The names are all random

I don't remember, maybe, it's just a command line so you can test but it probably works, filenames are just for readability anyways. I don't have that game myself, only got a few samples from people so I could check if the formats didn't change.
If you really want filenames the Switch version has them
## Post #159
- Username: narken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 31, 2020 6:56 am
- Post datetime: 2020-07-31T03:55:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

The KTID listed for the model I am trying to find the textures for doesn't actually exist in the KTID folder.  Am I misunderstanding something?
## Post #160
- Username: narken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 31, 2020 6:56 am
- Post datetime: 2020-07-31T04:01:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

For example, take Erza. 

 This model is 84447684.g1m. 

 I find that in the charactereditor db export, and then search that KTID, and it doesn't exist as a file.



Capsaasture.PNG (55.57 KiB) Viewed 177 times
## Post #161
- Username: narken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 31, 2020 6:56 am
- Post datetime: 2020-07-31T07:22:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Ok ran a cmd line prompt to redo the KTID script for every KTID in the character editor and manually found the texture bunch I wanted and made my edits.. now is it possible to get it back into the game?
## Post #162
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-31T10:01:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

As of now these tools are used for extraction and viewing only, a repacker would need to be made to put the files back
For your KTID stuff better download the latest build of the tools and do another clean extraction with the -g FairyTale option, you'll have the correct filenames.
## Post #163
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2020-07-31T12:36:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

About Fairy Tail, where I could access the ktid characters db export?

edit : nevermind I found it
## Post #164
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-07-31T13:07:25+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

The One Piece Pirate Warriors 4 DLC characters get included in the main rdb files for the game but obviously the file list doesn't list them so stuff like textures are confusing to sort through, what is the method of getting a file list or would someone be able to update it?
## Post #165
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-31T13:44:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from TRDaz ↑Fri Jul 31, 2020 9:07 pm at Fri Jul 31, 2020 9:07 pm
>
> 
The One Piece Pirate Warriors 4 DLC characters get included in the main rdb files for the game but obviously the file list doesn't list them so stuff like textures are confusing to sort through, what is the method of getting a file list or would someone be able to update it?

Names need to be cracked, using a dictionary brute force attack or something like that.
## Post #166
- Username: DrDemon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 30, 2020 9:32 pm
- Post datetime: 2020-07-31T14:22:12+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

As of right now Ninja Ripping the textures works for me.
## Post #167
- Username: DrDemon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 30, 2020 9:32 pm
- Post datetime: 2020-07-31T15:16:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

MaterialEditor/g1t texure files need to be renamed. Those are the model textures.
I saw FieldEditor4 Textures were renamed.
## Post #168
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2020-08-01T04:15:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

The new build gave me a named ktid files for Fairy Tail with the new -g FairyTail usage
so getting the git pack texture are much easier with the repacking git method, and its easier to preview the models with noesis script.
Thank you Yretenai

Previously I was using Ninjaripper to get the texture, in the end the mask and the texture color are kinda burned up, so I prefer using the extract it manualluy with the git files
[ezra.png](https://xentaxbackup.github.io/file/18550_ezra.png)
## Post #169
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-08-02T01:54:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Theres some unnamed files in Fairy Tail, they should be so or I am missing something?
## Post #170
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-08-03T20:21:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I'm trying to extract some characters from the PS4 version of Nioh. So far, I can successfully get the textures and meshes with the correct UV maps, but I can't work out how to successfully import a character with a skeleton and weights into a 3d program.

I'm quite new to this, so any help given would be deeply appreciated
## Post #171
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-08-03T22:22:12+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Do we have file list for Niohs yet?
## Post #172
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-03T22:56:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from ngovandang ↑Tue Aug 04, 2020 6:22 am at Tue Aug 04, 2020 6:22 am
>
> 
Do we have file list for Niohs yet?
For PC no, might as well use PS4 files since PC ones are a mess and no current extractor exists that supports it entirely.
## Post #173
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-08-04T09:24:58+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Tue Aug 04, 2020 6:56 am at Tue Aug 04, 2020 6:56 am
>
> 
For PC no, might as well use PS4 files since PC ones are a mess and no current extractor exists that supports it entirely.

OMG you are right, this is cool. Doesnt even require Cethleann's tool to extract them XD
[Annotation 2020-08-04 162406.png](https://xentaxbackup.github.io/file/18556_Annotation 2020-08-04 162406.png)
## Post #174
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-04T15:17:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from ngovandang ↑Tue Aug 04, 2020 5:24 pm at Tue Aug 04, 2020 5:24 pm
>
> ...Doesnt even require Cethleann's tool to extract them XD
You still need it to unpack them, assuming you want both model/animations, if not use daemon's tool just for models.
## Post #175
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-08-04T17:33:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Tue Aug 04, 2020 11:17 pm at Tue Aug 04, 2020 11:17 pm
>
> 
ngovandang wrote: ↑Tue Aug 04, 2020 5:24 pm...Doesnt even require Cethleann's tool to extract them XD

You still need it to unpack them, assuming you want both model/animations, if not use daemon's tool just for models.

Daemon's tool doesn't grab the physics bones correctly unfortunately so make sure the model you're interested in don't use them : [viewtopic.php?f=16&t=18042&start=180#p164321](https://forum.xentax.com/viewtopic.php?f=16&t=18042&start=180#p164321)
## Post #176
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-08-08T01:54:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello I've tried to extract the linkdata BIN files from OPPW4, since they don't have IDX I used Unbundler but they don't output anything. [Here](https://www.mediafire.com/file/uee5z81143o7iwk/OPPW4_LINKDATA.7z/file) are the samples, I want to do a translation mod, since the spanish one was done with machine translation, Trafalgar Law to Ley de Trafalgar.
## Post #177
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-08-18T16:32:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi there, today I wanted to try extracting the AoT2 files again, this time with the --AttackOnTitan2 command since last time I did it without.
But uuh, I'm not sure if I have anything set wrong (or dumb mistake) but none of the commands seem to be working/doing anything at all? 
(at least it's not giving me errors but still nothing)   

FYI I downloaded the latest build, installed the .NET Core 3.1 Runtime (x64.) so I believe I'm using the right things?
## Post #178
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-19T14:45:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Eag1e ↑Wed Aug 19, 2020 12:32 am at Wed Aug 19, 2020 12:32 am
>
> 
Hi there, today I wanted to try extracting the AoT2 files again, this time with the --AttackOnTitan2 command since last time I did it without.
But uuh, I'm not sure if I have anything set wrong (or dumb mistake) but none of the commands seem to be working/doing anything at all? 
(at least it's not giving me errors but still nothing)   

FYI I downloaded the latest build, installed the .NET Core 3.1 Runtime (x64.) so I believe I'm using the right things?

There's no AttackOnTitan2 command, you need to use the --game or -g command and then put the value
So 
```
-g AttackOnTitan2
```
## Post #179
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-08-19T15:35:43+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Wed Aug 19, 2020 10:45 pm at Wed Aug 19, 2020 10:45 pm
>
> 
Eag1e wrote: ↑Wed Aug 19, 2020 12:32 am
Hi there, today I wanted to try extracting the AoT2 files again, this time with the --AttackOnTitan2 command since last time I did it without.
But uuh, I'm not sure if I have anything set wrong (or dumb mistake) but none of the commands seem to be working/doing anything at all? 
(at least it's not giving me errors but still nothing)   

FYI I downloaded the latest build, installed the .NET Core 3.1 Runtime (x64.) so I believe I'm using the right things?



There's no AttackOnTitan2 command, you need to use the --game or -g command and then put the value
So Code: Select all-g AttackOnTitan2

Hmm, I think I put the commands in correct this time, still not working, is there anything else I may be doing wrong?
## Post #180
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-19T16:22:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I can't test right now but it may be because you put the parameters not in order, try to put the "--linkdata -g AttackOnTitan2" before the folders. 

It shouldn't matter though so my guess is that it may come from the fact that your source folder, destination folder and the folder you're executing the command from are on different disks. I remember taht another user had some issues due to this, you may want to try to put everything on the same disk.
## Post #181
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-08-19T18:24:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Thu Aug 20, 2020 12:22 am at Thu Aug 20, 2020 12:22 am
>
> 
I can't test right now but it may be because you put the parameters not in order, try to put the "--linkdata -g AttackOnTitan2" before the folders. 

It shouldn't matter though so my guess is that it may come from the fact that your source folder, destination folder and the folder you're executing the command from are on different disks. I remember taht another user had some issues due to this, you may want to try to put everything on the same disk.

Alright I'll try those options!
## Post #182
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2020-08-23T09:10:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Can someone please write proper manual how to actually use this tool? I have zero idea what should i do and where should i press to extract models from Dissidia for example.
## Post #183
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2020-09-07T08:51:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

i still dont get this tool at all. doing something wrong or i need to use something else (not cmd)?
[Безымянный.png](https://xentaxbackup.github.io/file/18706_Безымянный.png)
## Post #184
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-09-09T11:25:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from rotteneyed ↑Mon Sep 07, 2020 4:51 pm at Mon Sep 07, 2020 4:51 pm
>
> 
i still dont get this tool at all. doing something wrong or i need to use something else (not cmd)?

I believe you need to use --linkarchive, not linkdata.
## Post #185
- Username: Ctvicky
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 29, 2020 5:30 am
- Post datetime: 2020-09-10T20:42:42+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Anyone know what this error means? Im trying to extract the bgm file of Hyrule Warriors (switch version).
[40898b5544432cb5037cc13193572a4f.png](https://xentaxbackup.github.io/file/18723_40898b5544432cb5037cc13193572a4f.png)
## Post #186
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-09-22T17:10:37+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Ctvicky ↑Fri Sep 11, 2020 4:42 am at Fri Sep 11, 2020 4:42 am
>
> 
Anyone know what this error means? Im trying to extract the bgm file of Hyrule Warriors (switch version).

Not an error, just a sanity check. There are a bunch of them for "unknown" fields so I can check what changes
## Post #187
- Username: mistralsiege
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 08, 2019 5:45 am
- Post datetime: 2020-10-05T05:16:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Trying to open my Dissidia NT Free Edition, but this is the error I'm getting. I already checked to make sure I had the file in question, but I'm still getting the same error. What should I do to properly open Dissidia NT?
[unknown3.png](https://xentaxbackup.github.io/file/18798_unknown3.png)
## Post #188
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-05T11:27:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Iirc you need to give the "free edition" folder, not the "common" one. So try replacing 
```
...\steamapps\common\Dissidiat FINAL FANTASY NT Free Edition\COMMON
```
 by 
```
...\steamapps\common\Dissidiat FINAL FANTASY NT Free Edition
```
## Post #189
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-10-09T12:32:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello and thx for ur great tools , today i extract op4 assets with [Cethleann.DataExporter --rdb -g OnePiece4] command but i got files without proper name , is this normal or i did something wrong?



edit : sry my cethleann is old version lol , the newest version unpack them with real name , thnnkas
## Post #190
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-15T14:14:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Wed Jan 29, 2020 11:05 pm at Wed Jan 29, 2020 11:05 pm
>
> 
Over the last couple of months I've been working on a bunch of open-source tools to extract and work with various Koei Tecmo games such as Fire Emblem: Three Houses and Dissidia Final Fantasy NT Free Edition (Steam.) It has tools for uncompressing files, virtual FS containers (FETH's DATA0/DATA1, Atelier PAKs) and unwrapping concatinated files (.bin, .gmpk, .mdlk)

The main tool to use is Cethleann.Unbundler, this tool will take most concatinated files and output individual files. It has support for FETH SCENE, MDLK, KTSR, KTSC, LX19, GMPK, GAPK, G1L, KOVS, and RTRPK files.

This has ZERO SUPPORT for Big Endian files.
Source: https://github.com/healingbrew/Cethleann
Builds: https://ci.appveyor.com/project/yretena ... /artifacts
This project REQUIRES .NET Core 3.1 Runtime (x64.) Download here

Click on the latest build and download the Cethleann-Standalone artifact.
Atelier support is experimental, "should work." 
Gust elixir.gz support coming soon.
Support for Nioh VFS is coming soon.

This tool is created in tandem with Joschka's Noesis fmt_g1m plugin.
viewtopic.php?f=16&t=21666

Special Thanks To:
- id-daemon's Dissidia model converter which gave me reference data to test again
- HeartHeroDE's th-hack-tools whose implementation helped me understand STRUCT formats
- The Fire Emblem Three Houses Datamining Community for creating binary templates
- Ploaj's Metanoia whose implementatino helped me understand G1Ms
- Quickbms' arslan.bms for having a LINKDATA implementation to base off
- VitaSmith's gust_tools whose implementation helped me understand Gust PAKs and textures
- Eternity's rdbtool for helping me understand animatinos, RDBs, RDB hashing algorithms, and the DoA6 file list
- chrrox for helping me understand RDBs and figuring out what compression algorithm the switch uses.


Latest Version: 1.0.58
Changes: here

I only have one conclusion going down this journey:
Hi,Do you know how to extract the wbd/whd files？
it's Koei Tecmo's special audio container .
samples:[https://drive.google.com/file/d/1Bj75mG ... Erc2z/view](https://drive.google.com/file/d/1Bj75mGMZUcp7AlzzOGwBY_4pdGJErc2z/view)
[https://drive.google.com/file/d/1shE0YU ... 9-EXJ/view](https://drive.google.com/file/d/1shE0YUlFOXaFX5PgaXFIGT-kDVg9-EXJ/view)
## Post #191
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-10-15T22:03:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from kaimuangel ↑Thu Oct 15, 2020 10:14 pm at Thu Oct 15, 2020 10:14 pm
>
> 
Hi,Do you know how to extract the wbd/whd files？
it's Koei Tecmo's special audio container .
samples:https://drive.google.com/file/d/1Bj75mG ... Erc2z/view
https://drive.google.com/file/d/1shE0YU ... 9-EXJ/view

What game? vgmstream supports most wbh/whd files. Cethleann.Unbundler can extract the sounds from the soundbanks but not decode them, vgmstream can.
## Post #192
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-16T03:38:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Oct 16, 2020 6:03 am at Fri Oct 16, 2020 6:03 am
>
> 
kaimuangel wrote: ↑Thu Oct 15, 2020 10:14 pm
Hi,Do you know how to extract the wbd/whd files？
it's Koei Tecmo's special audio container .
samples:https://drive.google.com/file/d/1Bj75mG ... Erc2z/view
https://drive.google.com/file/d/1shE0YU ... 9-EXJ/view


What game? vgmstream supports most wbh/whd files. Cethleann.Unbundler can extract the sounds from the soundbanks but not decode them, vgmstream can.

The game is Deception IV(PS4) ,How do i use Cethleann.Unbundler to extract the sound files？what command should i to enter？
## Post #193
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-16T09:27:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from kaimuangel ↑Fri Oct 16, 2020 11:38 am at Fri Oct 16, 2020 11:38 am
>
> ...How do i use Cethleann.Unbundler to extract the sound files？...
Drag and drop your archive on to it, and it will unpack it for you automatically.
## Post #194
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-16T10:35:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Fri Oct 16, 2020 5:27 pm at Fri Oct 16, 2020 5:27 pm
>
> 
kaimuangel wrote: ↑Fri Oct 16, 2020 11:38 am...How do i use Cethleann.Unbundler to extract the sound files？...
Drag and drop your archive on to it, and it will unpack it for you automatically.

Thanks
## Post #195
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-16T12:41:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from mono24 ↑Fri Oct 16, 2020 5:27 pm at Fri Oct 16, 2020 5:27 pm
>
> 
kaimuangel wrote: ↑Fri Oct 16, 2020 11:38 am...How do i use Cethleann.Unbundler to extract the sound files？...
Drag and drop your archive on to it, and it will unpack it for you automatically.

I'm trying to Drag and drop the whd/wbd files to Cethleann.Unbundler.exe，but seem to not working，and I trying to play them with vgmstream but they don't work.
please help
## Post #196
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-16T12:55:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Oct 16, 2020 6:03 am at Fri Oct 16, 2020 6:03 am
>
> 
kaimuangel wrote: ↑Thu Oct 15, 2020 10:14 pm
Hi,Do you know how to extract the wbd/whd files？
it's Koei Tecmo's special audio container .
samples:https://drive.google.com/file/d/1Bj75mG ... Erc2z/view
https://drive.google.com/file/d/1shE0YU ... 9-EXJ/view


What game? vgmstream supports most wbh/whd files. Cethleann.Unbundler can extract the sounds from the soundbanks but not decode them, vgmstream can.

Cethleann.Unbundler.exe and vgmstream seem to not working，Is there any other way?
## Post #197
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-10-16T20:54:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from kaimuangel ↑Fri Oct 16, 2020 8:55 pm at Fri Oct 16, 2020 8:55 pm
>
> 
Yretenai wrote: ↑Fri Oct 16, 2020 6:03 am
kaimuangel wrote: ↑Thu Oct 15, 2020 10:14 pm
Hi,Do you know how to extract the wbd/whd files？
it's Koei Tecmo's special audio container .
samples:https://drive.google.com/file/d/1Bj75mG ... Erc2z/view
https://drive.google.com/file/d/1shE0YU ... 9-EXJ/view


What game? vgmstream supports most wbh/whd files. Cethleann.Unbundler can extract the sounds from the soundbanks but not decode them, vgmstream can.


Cethleann.Unbundler.exe and vgmstream seem to not working，Is there any other way?

vgmsteam supports the codec in those sound files (K4HD/AATRAC), just change the WHD file's extension to WBH (so you have a WBD and WBH file) and then use vgmstream on the wbd file:

```

```
## Post #198
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-17T05:15:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Sat Oct 17, 2020 4:54 am at Sat Oct 17, 2020 4:54 am
>
> 
kaimuangel wrote: ↑Fri Oct 16, 2020 8:55 pm
Yretenai wrote: ↑Fri Oct 16, 2020 6:03 am


What game? vgmstream supports most wbh/whd files. Cethleann.Unbundler can extract the sounds from the soundbanks but not decode them, vgmstream can.


Cethleann.Unbundler.exe and vgmstream seem to not working，Is there any other way?


vgmsteam supports the codec in those sound files (K4HD/AATRAC), just change the WHD file's extension to WBH (so you have a WBD and WBH file) and then use vgmstream on the wbd file:
Code: Select alltest.exe VOICE12KNIGHTS_A.wbd
thanks so much ! and I extract a sed file（from game Fatal Frame Maiden of Black Water），it outputs a .dat with a .wbh file,Is this dat file actually a wbd file?
Thanks in advance.
samples：[https://drive.google.com/file/d/12GLKA8 ... sp=sharing](https://drive.google.com/file/d/12GLKA8Zyzggr62BS48rCQEq8K98QuGAB/view?usp=sharing)
SED file：[https://drive.google.com/file/d/1c8b_ru ... sp=sharing](https://drive.google.com/file/d/1c8b_ru2pgbY7H7XPaYrdWXpVBsJqtsbk/view?usp=sharing)
[20201018214037.png](https://xentaxbackup.github.io/file/18853_20201018214037.png)
## Post #199
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-18T02:03:12+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from kaimuangel ↑Sat Oct 17, 2020 1:15 pm at Sat Oct 17, 2020 1:15 pm
>
> 
Yretenai wrote: ↑Sat Oct 17, 2020 4:54 am
kaimuangel wrote: ↑Fri Oct 16, 2020 8:55 pm


Cethleann.Unbundler.exe and vgmstream seem to not working，Is there any other way?


vgmsteam supports the codec in those sound files (K4HD/AATRAC), just change the WHD file's extension to WBH (so you have a WBD and WBH file) and then use vgmstream on the wbd file:
Code: Select alltest.exe VOICE12KNIGHTS_A.wbd
## Post #200
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-10-18T17:55:03+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from kaimuangel ↑Sat Oct 17, 2020 1:15 pm at Sat Oct 17, 2020 1:15 pm
>
> 
Yretenai wrote: ↑Sat Oct 17, 2020 4:54 am
kaimuangel wrote: ↑Fri Oct 16, 2020 8:55 pm


Cethleann.Unbundler.exe and vgmstream seem to not working，Is there any other way?


vgmsteam supports the codec in those sound files (K4HD/AATRAC), just change the WHD file's extension to WBH (so you have a WBD and WBH file) and then use vgmstream on the wbd file:
Code: Select alltest.exe VOICE12KNIGHTS_A.wbd


thanks so much ! and I extract a sed file（from game Fatal Frame Maiden of Black Water），it outputs a .dat with a .wbh file,Is this dat file actually a wbd file?
Thanks in advance.
samples：https://drive.google.com/file/d/12GLKA8 ... sp=sharing
SED file：https://drive.google.com/file/d/1c8b_ru ... sp=sharing

yeah just remove the bytes before the WBD_0000 marker.
Do a serach for WBD_0000 in that file too it might contain multiple.
## Post #201
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-19T01:30:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Mon Oct 19, 2020 1:55 am at Mon Oct 19, 2020 1:55 am
>
> 
kaimuangel wrote: ↑Sat Oct 17, 2020 1:15 pm
Yretenai wrote: ↑Sat Oct 17, 2020 4:54 am


vgmsteam supports the codec in those sound files (K4HD/AATRAC), just change the WHD file's extension to WBH (so you have a WBD and WBH file) and then use vgmstream on the wbd file:
Code: Select alltest.exe VOICE12KNIGHTS_A.wbd


thanks so much ! and I extract a sed file（from game Fatal Frame Maiden of Black Water），it outputs a .dat with a .wbh file,Is this dat file actually a wbd file?
Thanks in advance.
samples：https://drive.google.com/file/d/12GLKA8 ... sp=sharing
SED file：https://drive.google.com/file/d/1c8b_ru ... sp=sharing


yeah just remove the bytes before the WBD_0000 marker.
Do a serach for WBD_0000 in that file too it might contain multiple.

So I remove the bytes before the WBD_0000，and I change the DAT file's extension to WBD,use vgmstream to play them,but they don't work.Am I doing something wrong?
WBD_0000 Only one。
[20201019091845.png](https://xentaxbackup.github.io/file/18859_20201019091845.png)
## Post #202
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-10-21T22:07:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

delete
## Post #203
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-22T00:03:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Mon Oct 19, 2020 1:55 am at Mon Oct 19, 2020 1:55 am
>
> 
kaimuangel wrote: ↑Sat Oct 17, 2020 1:15 pm
Yretenai wrote: ↑Sat Oct 17, 2020 4:54 am


vgmsteam supports the codec in those sound files (K4HD/AATRAC), just change the WHD file's extension to WBH (so you have a WBD and WBH file) and then use vgmstream on the wbd file:
Code: Select alltest.exe VOICE12KNIGHTS_A.wbd


thanks so much ! and I extract a sed file（from game Fatal Frame Maiden of Black Water），it outputs a .dat with a .wbh file,Is this dat file actually a wbd file?
Thanks in advance.
samples：https://drive.google.com/file/d/12GLKA8 ... sp=sharing
SED file：https://drive.google.com/file/d/1c8b_ru ... sp=sharing


yeah just remove the bytes before the WBD_0000 marker.
Do a serach for WBD_0000 in that file too it might contain multiple.
I remove the bytes before the WBD_0000 and change the extension，But can't play the wbd(dat) file，Is there any other way? Or am I doing something wrong?
## Post #204
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-10-28T17:54:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann works with Hyrule warriors age of calamity demo version's rdb files but with no filenames.



093202394902390423.png (42.82 KiB) Viewed 298 times
## Post #205
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-10-29T15:39:55+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from andree ↑Thu Oct 29, 2020 1:54 am at Thu Oct 29, 2020 1:54 am
>
> 
Cethleann works with Hyrule warriors age of calamity demo version's rdb files but with no filenames.
093202394902390423.png

what was the command you used? i tried one from long ago that i used on one piece and it didn't work. There isn't much stuff so i'm ok with no names until full game is out
## Post #206
- Username: crist0393
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 31, 2018 1:54 am
- Post datetime: 2020-10-29T23:15:53+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

How can I extract the models from Switch games like FE Three Houses and HW Age of Calamity? can I extracted them without a Nintendo Switch?
## Post #207
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-10-30T02:06:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Am i doing something wrong? or am i missing a step?
[cmd.PNG](https://xentaxbackup.github.io/file/18927_cmd.PNG)
## Post #208
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-11-05T15:33:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Enkidu115 ↑Fri Oct 30, 2020 10:06 am at Fri Oct 30, 2020 10:06 am
>
> 
Am i doing something wrong? or am i missing a step?

What game are you extracting it from?
## Post #209
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2020-11-06T01:11:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

About hyrule warriors age of calamity. I've extracted the file but need help.
Files extracted by Cethleann.DataExporter have their own file format.
I would like to know more information about these file formats.
In particular, I would like to see the game text and icons. Where are these included?



zelda.png (3.26 KiB) Viewed 163 times
## Post #210
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2020-11-06T15:57:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

How do you get to do that? I got the .NCA and then the romsf.bin file from Age of Calamity but nothing seems to work for me. I can´t get the G1M files and I have no idea what to do...
## Post #211
- Username: Mastersys
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 04, 2020 12:53 am
- Post datetime: 2020-11-06T17:08:56+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Enderfacio ↑Fri Nov 06, 2020 11:57 pm at Fri Nov 06, 2020 11:57 pm
>
> 
How do you get to do that? I got the .NCA and then the romsf.bin file from Age of Calamity but nothing seems to work for me. I can´t get the G1M files and I have no idea what to do...

Extract the NCA content with NSC Builder from the .nsp, after that look for the biggest asset folder and extract the content with Cathleann data exporter with this command \Cethleann.DataExporter.exe --nyotengu, --rdb "directory from asset folder" "output folder"
I´m looking for the Soundfiles, but it semms they use another encryption for the files.
## Post #212
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2020-11-06T23:01:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Mastersys ↑Sat Nov 07, 2020 1:08 am at Sat Nov 07, 2020 1:08 am
>
> 
Enderfacio wrote: ↑Fri Nov 06, 2020 11:57 pm
How do you get to do that? I got the .NCA and then the romsf.bin file from Age of Calamity but nothing seems to work for me. I can´t get the G1M files and I have no idea what to do...


Extract the NCA content with NSC Builder from the .nsp, after that look for the biggest asset folder and extract the content with Cathleann data exporter with this command \Cethleann.DataExporter.exe --nyotengu, --rdb "directory from asset folder" "output folder"
I´m looking for the Soundfiles, but it semms they use another encryption for the files.

I tried that command but nothing happens:
[NotWorking.png](https://xentaxbackup.github.io/file/18970_NotWorking.png)
## Post #213
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2020-11-07T02:32:04+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Enderfacio ↑Sat Nov 07, 2020 7:01 am at Sat Nov 07, 2020 7:01 am
>
> 
Mastersys wrote: ↑Sat Nov 07, 2020 1:08 am
Enderfacio wrote: ↑Fri Nov 06, 2020 11:57 pm
How do you get to do that? I got the .NCA and then the romsf.bin file from Age of Calamity but nothing seems to work for me. I can´t get the G1M files and I have no idea what to do...


Extract the NCA content with NSC Builder from the .nsp, after that look for the biggest asset folder and extract the content with Cathleann data exporter with this command \Cethleann.DataExporter.exe --nyotengu, --rdb "directory from asset folder" "output folder"
I´m looking for the Soundfiles, but it semms they use another encryption for the files.


I tried that command but nothing happens:
Cethleann.DataExporter --nyotengu --rdb "outputfolder" "assetfolder"
my command: Cethleann.DataExporter --nyotengu --rdb D:\HyruleWarriors\romfs\out D:\HyruleWarriors\romfs\asset
## Post #214
- Username: Century300
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 08, 2020 11:36 pm
- Post datetime: 2020-11-09T03:37:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm trying to get model specific animations from Persona 5 Scramble but I don't know how. I know that I hate to use Nyotengu.AnimationGraph but the program only works with dead or alive 6 hashes. I saw on the thread that the KTID from WolrdPQ can be used as the hash in the program but I don't know where or how to find that value. Can anyone help me?
## Post #215
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2020-11-09T13:49:38+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from yham ↑Sat Nov 07, 2020 10:32 am at Sat Nov 07, 2020 10:32 am
>
> 
Enderfacio wrote: ↑Sat Nov 07, 2020 7:01 am
Mastersys wrote: ↑Sat Nov 07, 2020 1:08 am


Extract the NCA content with NSC Builder from the .nsp, after that look for the biggest asset folder and extract the content with Cathleann data exporter with this command \Cethleann.DataExporter.exe --nyotengu, --rdb "directory from asset folder" "output folder"
I´m looking for the Soundfiles, but it semms they use another encryption for the files.


I tried that command but nothing happens:

Cethleann.DataExporter --nyotengu --rdb "outputfolder" "assetfolder"
my command: Cethleann.DataExporter --nyotengu --rdb D:\HyruleWarriors\romfs\out D:\HyruleWarriors\romfs\asset

Thank you very much!!! It finally works!!!
## Post #216
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-11-20T00:33:55+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I need help on extracting the .bin files from  attack on titan 1 (Steam version).

```
Cethleann.DataExporter.exe -g AttackOnTitan -P Windows --flayn "directory from asset folder" "output folder"
```

I used this command with these files:

LINKDATA_EU_A.BIN
LINKDATA_EU_B.BIN
LINKDATA_EU_C.BIN
LINKDATA_EU_D.BIN
LINKDATA_EU_PLATFORM.BIN

and it didn't work. Please find a command that works with these files please?
## Post #217
- Username: banan039eu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 12, 2020 4:52 am
- Post datetime: 2020-11-21T08:38:35+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I used this tool to extract Hyrule Warriors Age of Calamity rdb files and it worked flawlessly. I have all g1m and g1t files I needed. Is there any way to pair g1m file to correct g1t file? I tried extracting that information from materials files, but I failed. I am 90% sure it has to do something with .ktid and .kidsobjdb files. Can please someone help me?
## Post #218
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-11-22T06:38:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from banan039eu ↑Sat Nov 21, 2020 4:38 pm at Sat Nov 21, 2020 4:38 pm
>
> 
I used this tool to extract Hyrule Warriors Age of Calamity rdb files and it worked flawlessly. I have all g1m and g1t files I needed. Is there any way to pair g1m file to correct g1t file? I tried extracting that information from materials files, but I failed. I am 90% sure it has to do something with .ktid and .kidsobjdb files. Can please someone help me?

can you please tell me the command you used to get file with names out of age of calamity?
## Post #219
- Username: Julian0555
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 23, 2015 10:53 pm
- Post datetime: 2020-11-23T04:02:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

(Hyrule Warriors: Age of Calamity) 
Is there any possibility to find the g1a files associated with a g1m file? I'm specifically looking to get the animations for Zelda without having to go through literally every character animation. I'd appreciate any help I can get.
## Post #220
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-23T10:39:33+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Makoto ↑Sun Nov 22, 2020 2:38 pm at Sun Nov 22, 2020 2:38 pm
>
> 
banan039eu wrote: ↑Sat Nov 21, 2020 4:38 pm
I used this tool to extract Hyrule Warriors Age of Calamity rdb files and it worked flawlessly. I have all g1m and g1t files I needed. Is there any way to pair g1m file to correct g1t file? I tried extracting that information from materials files, but I failed. I am 90% sure it has to do something with .ktid and .kidsobjdb files. Can please someone help me?


can you please tell me the command you used to get file with names out of age of calamity?

There are no filenames for now, they didn't leave them contrary to some other RDB games and they changed the way they store them in the binary. The methods used to get them before don't work for now.
## Post #221
- Username: neonvegax
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 02, 2020 1:28 am
- Post datetime: 2020-11-23T12:24:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

i need help so i sent the tools for the g1tm models into NOESIS PLUGINS python but when i load up a g1tm model from NOESIS all im getting are the animations which step am I missing to actually load the models into Noesis along with the bones?
## Post #222
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-23T12:39:23+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from neonvegax ↑Mon Nov 23, 2020 8:24 pm at Mon Nov 23, 2020 8:24 pm
>
> 
i need help so i sent the tools for the g1tm models into NOESIS PLUGINS python but when i load up a g1tm model from NOESIS all im getting are the animations which step am I missing to actually load the models into Noesis along with the bones?

Wrong thread for those issues + don't use the python plugin, it's outdated.
## Post #223
- Username: neonvegax
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 02, 2020 1:28 am
- Post datetime: 2020-11-23T15:05:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

[https://www.mediafire.com/file/cq2ffu6x ... 8.mp4/file](https://www.mediafire.com/file/cq2ffu6xt79j9o1/2020-11-23_09h02_08.mp4/file)

can someone pls watch video and tell me what i did wrong? trying to load model into Noesis but I felt i did the right steps can someone point out what i am missing or failed to do?
## Post #224
- Username: colorido10
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 11, 2018 5:07 am
- Post datetime: 2020-11-23T20:43:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

It's great Cethleann but I don't understand how they repackage everything with the modifications they make and use it in the game.

I managed to unpack the sounds in the DATA folder in Age Of Calamity's Asset, I got .ktss files but I have no idea how to repackage them back into a .file file
## Post #225
- Username: Noob
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 02, 2020 11:26 am
- Post datetime: 2020-12-02T03:29:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from colorido10 ↑Tue Nov 24, 2020 4:43 am at Tue Nov 24, 2020 4:43 am
>
> 
It's great Cethleann but I don't understand how they repackage everything with the modifications they make and use it in the game.

I managed to unpack the sounds in the DATA folder in Age Of Calamity's Asset, I got .ktss files but I have no idea how to repackage them back into a .file file

Please, what command did you use to get the sound files? I can only get the .rdb files to extract
## Post #226
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-12-05T05:55:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Does anyone know how to extract MUA3 animations? Tried the Unbundler but nothing gets extracted.
## Post #227
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-12-08T04:59:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Build 75 adds support for Portable RDB (PRDB) files, seen in Dynasty Warriors Mobile.
To use this file system pass --zhao, or --prdb to DataExporter.

Previous changes: [viewtopic.php?f=10&t=21679&p=164258#p164258](https://forum.xentax.com/viewtopic.php?f=10&t=21679&p=164258#p164258)

Edit: there's a bug with extraction, will fix today.

Edit 2: Fixed in build 76! Regular RDB containers might be broken, will test those later and fix if it is but it should still work.

Edit 3: Build 78 adds support for Hyrule Warriors Legends, use the flayn extraction method and pass --flayn-tiny.
## Post #228
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2020-12-21T19:50:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Okay so I've gathered what I can from this thread and from what I can see, I should be using "Nyotengu.KTID.exe" to get the g1t textures to make the models and textures automatically line up.
But, as always, I'm stuck. From what I can see I should be using the following command

```
nyotengu.KTID.exe -g "*MyPath*\KIDSSystemResource\kidsobjdb", "*MyPath*\MaterialEditor\g1t", "*MyPath*\CharacterEditor\ktid"
```


Where am I going wrong here?
## Post #229
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-12-24T19:56:57+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I've pretty much given up on getting the 'matched' files from Age of Calamity, since I can't get a straight answer anywhere and I've tried everything I could imagine myself.
I've moved on to Dragon Quest Builders 2. I'm having trouble extracting the files, even though they should be compatible... Here's my current method, not sure what's going wrong.

```
[2020-12-24T19:52:51][Cethleann] Cethleann.DataExporter v1.1.79.0
[2020-12-24T19:52:51][Cethleann] Arguments: ["--linkdata","--idx=D:\\DRAGON QUEST BUILDERS 2\\LINKDATA.IDX","--bin=D:\\DRAGON QUEST BUILDERS 2\\LINKDATA.BIN","D:\\DRAGON QUEST BUILDERS 2","G:\\DQB2"]
[2020-12-24T19:52:51][FileList] Loading filelist for LINKDATAPatterns-link
[2020-12-24T19:52:51][FileList] Loading filelist for unknown-link
```
## Post #230
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2020-12-24T20:20:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Has someone extract the animations from Marvel Ultimate Alliance 3? because I tried and can't succeed (models and texture work perfectly)

Run this command and it does nothing



Capture9.PNG (9.62 KiB) Viewed 405 times



Thanks a lot, this is an amazing tool!!
## Post #231
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-26T19:31:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Delbozkester ↑Fri Dec 25, 2020 4:20 am at Fri Dec 25, 2020 4:20 am
>
> 
Has someone extract the animations from Marvel Ultimate Alliance 3? because I tried and can't succeed (models and texture work perfectly)

Run this command and it does nothing

Capture9.PNG

Thanks a lot, this is an amazing tool!!

Try this [viewtopic.php?f=16&t=21666&start=300#p169358](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=300#p169358)
## Post #232
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2020-12-26T21:49:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Sun Dec 27, 2020 3:31 am at Sun Dec 27, 2020 3:31 am
>
> 
Delbozkester wrote: ↑Fri Dec 25, 2020 4:20 am
Has someone extract the animations from Marvel Ultimate Alliance 3? because I tried and can't succeed (models and texture work perfectly)

Run this command and it does nothing

Capture9.PNG

Thanks a lot, this is an amazing tool!!


Try this viewtopic.php?f=16&t=21666&start=300#p169358

Thank you very much, it works   



MUA3 Captain America with texture and animation Capture10.PNG (249.16 KiB) Viewed 367 times
## Post #233
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2021-01-01T12:23:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Doctor Loboto ↑Fri Dec 25, 2020 3:56 am at Fri Dec 25, 2020 3:56 am
>
> 
I've pretty much given up on getting the 'matched' files from Age of Calamity, since I can't get a straight answer anywhere and I've tried everything I could imagine myself.

Unfortunately the current way is to put the G1m file into a folder with all the G1t files, enable "Select g1t when non/partial merge" and then select the g1m in Noesis and work your way through all the g1t's until you find the 1 that matches. My method is to copy all the g1t's to a separate folder, place the character you want in the file alongside it, and delete a file after it proves to be the incorrect match.
It's a very time-consuming process but from what I've been told, it's the best way we have.
## Post #234
- Username: TabuuForteAkugun
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 06, 2021 7:40 am
- Post datetime: 2021-01-05T23:47:46+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Reading your reply, @ninetalescommander, I'm glad I already had most of the textures I wanted for the model I sought. lol. Soon it's on to her animations, I need bases after all
## Post #235
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-14T00:43:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello Yretenai, I downloaded 3 zip files found on the site: appveyor, but the extractor (Omega.DataExtractor.exe) is not in any of the folders.
I really wanted to extract the 3d models of the attack on titan 2 final battle characters, but I don't understand almost anything how these file extraction procedures work using cmd.
can you tell me if initially the correct one would be:

1 Create a folder on the desktop
2 rename the folder with the name: aot2
3 inside this folder put the LINKDATA_A file for the attack on titan 2 final battle game, and the (Omega.DataExtractor.exe)
4 type the command line and hit enter, so the extraction will start, is that Yretenai?

please are there more detailed tutorials on how to use each Cethleann tool here on xentax, or on another website?
I have version 5.0 of Net Core installed on my pc
## Post #236
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-16T02:56:06+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

can someone help me extract the LINKDATA_A file from AOT2 final battle?
I don't know how to organize the LINKDATA_A file
and Cethleann.DataExporter.exe in the folders.
please how the files have to be in the folders, and how would the command line for the export process to work?
## Post #237
- Username: ranjer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 19, 2021 12:06 am
- Post datetime: 2021-01-18T16:07:55+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

do you have tutorials to use this tool ?
## Post #238
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-20T01:04:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello Ranjer, I don't have a tutorial, I also don't understand anything about the extraction process using cmd.
I am very lay in this type of file extraction, in this case I want to extract the 3d models (attack on titan 2), I know that the 3d models are in the LINKDATA_A file, and the tool to extract this file is Cethleann.DataExporter.exe, but I don't know how to use this tool with cmd.
can you help me?
I have Cethleann.DataExporter.exe, the LINKDATA_A file, but I don't know how to do the process to extract it
## Post #239
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-22T00:35:57+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

can someone help me, what is wrong on the command line in cmd?
I'm trying to extract attack on titan 2 final battle.
[cmd.png](https://xentaxbackup.github.io/file/19358_cmd.png)
## Post #240
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-22T01:00:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

please help me
what's missing from that command line?
what did I misspell?
[picture 2.jpg](https://xentaxbackup.github.io/file/19359_picture 2.jpg)
## Post #241
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-01-22T01:40:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Should be something like

```
Cethleann.DataExporter.exe --linkarchive -g AttackOnTitan2 "C:\3D Models\AOT2" "C:\file\LINKDATA"
```


Don't have the game myself though so can't confirm if that's the correct one, read the previous posts if that doesn't work
## Post #242
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-22T22:56:58+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Joschka, the command didn't work, I checked all the other questions, here in this topic by cethleann.
a user managed to extract the LINKDATA_A from attack on titan 2, but he did not add it here in the topic as he did.
he had your help and Yretenai's.
what is missing from that command line?
I have Netcore version 5.0 installed on my computer
I appreciate all the help you can offer, and I would like to post a complete tutorial here on the topic, when I can do this extraction, just like the user thony did on the topic of the fmt_g1m plugin.
a very detailed tutorial on how to obtain the oppw4 models
[vai da certo.png](https://xentaxbackup.github.io/file/19363_vai da certo.png)
## Post #243
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-23T00:32:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Joschka, if that helps in any way, on my computer the three folders: CethleannStandalone, AOT2 and the file are in Users \ user

Note: file is the folder where LINKDATA_A is located
[pc.png](https://xentaxbackup.github.io/file/19368_pc.png)
## Post #244
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2021-01-23T05:30:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I hope ur aware that u were supposed to edit the paths on ur end instead of using the same command he gave ya

like for example, mine was

> Cethleann.DataExporter.exe --linkarchive -g AttackOnTitan2 "K:\Games\Attack on Titan 2\LINKDATA\Extract" "K:\Games\Attack on Titan 2\LINKDATA"
## Post #245
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-23T20:29:54+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I didn't understand demonslayerx8, sorry, but, what did you mean by editing the paths at the end?

the folders are in this place; they are:
1 CethleannStandalone (Cethleann.DataExporter.exe)
2 AOT2 (empty folder to receive the LINKDATA_A estraido)
3 file (folder where the game's LINKDATA-A is)

how would be the command line in cmd, which I have to type, now you can see in the image the location of my folders
  can you help me?
[Users User.png](https://xentaxbackup.github.io/file/19372_Users User.png)
## Post #246
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-01-24T15:48:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from vanilla1 ↑Sun Jan 24, 2021 4:29 am at Sun Jan 24, 2021 4:29 am
>
> 
I didn't understand demonslayerx8, sorry, but, what did you mean by editing the paths at the end?

the folders are in this place; they are:
1 CethleannStandalone (Cethleann.DataExporter.exe)
2 AOT2 (empty folder to receive the LINKDATA_A estraido)
3 file (folder where the game's LINKDATA-A is)

how would be the command line in cmd, which I have to type, now you can see in the image the location of my folders
  can you help me?

```
Cethleann.DataExporter.exe --linkarchive -g AttackOnTitan2 "C:\3D Models\AOT2" "C:\file\LINKDATA"
```

Just replace "C:\3D Models\AOT2" with the path of the folder where you want to extract into and "C:\file\LINKDATA" with the path of folder that has the LINKDATA-A file.
## Post #247
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-25T18:10:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello andree, I did what you said, but it didn't work
as you can see in the image
I don't know if I typed the command correctly
what did I miss?
this is the command I typed:
C:\Users\User\Desktop\3D Models\CethleannStandalone> Cethleannn.DataExporter.exe --linkarchive -g AttackOnTitan2 C: \ Desktop \ 3D Models \ AOT2 \ C: \ Desktop \ 3D Models \ file \ LINKDATA
[cmd picture.png](https://xentaxbackup.github.io/file/19395_cmd picture.png)
## Post #248
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-01-27T01:15:42+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Build 82 fixes support for Ryza 2 PAK archives.
To extract you MUST provide --reisalin-keyfix as an argument.
i.e.

```
 
```


Previous changes:
[viewtopic.php?f=10&t=21679&p=169433#p169433](https://forum.xentax.com/viewtopic.php?f=10&t=21679&p=169433#p169433)
## Post #249
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-27T21:58:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I tried to extract the LINKDATA_A file from attack on titan 2 with the new construction 82 from Yretenai, but it also didn't work.
I'll be able to extract it, but, I don't know what the problem is; the command line I think I typed correctly, taking into account the location of the CethleannStandalone folder, AOT2 folder and file folder, (where the LINKDATA_A of attack on titan 2 is located)
this is my command that I am executing inside the Cethleann folder:
C: \ Users \ User \ Desktop \ 3D Models \ CethleannStandalone> Cethleannn.DataExporter.exe --linkarchive -g AttackOnTitan2 C: \ Desktop \ 3D Models \ AOT2  C: \ Desktop \ 3D Models \ file


what am i typing wrong on the command line?
[picture.png](https://xentaxbackup.github.io/file/19407_picture.png)
## Post #250
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-01-28T05:52:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Wed Jan 27, 2021 9:15 am at Wed Jan 27, 2021 9:15 am
>
> 
Build 82 fixes support for Ryza 2 PAK archives.
To extract you MUST provide --reisalin-keyfix as an argument.
i.e.
Code: Select allCethleann.DataExporter.exe --reisalin D:\Ryza2Data "D:\Steam\steamapps\common\Atelier Ryza 2\Data" --reisalin-keyfix
 

Previous changes:
viewtopic.php?f=10&t=21679&p=169433#p169433

worked very well on ryza2 , thanks for the update
## Post #251
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-01-28T19:27:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from vanilla1 ↑Thu Jan 28, 2021 5:58 am at Thu Jan 28, 2021 5:58 am
>
> 
I tried to extract the LINKDATA_A file from attack on titan 2 with the new construction 82 from Yretenai, but it also didn't work.
I'll be able to extract it, but, I don't know what the problem is; the command line I think I typed correctly, taking into account the location of the CethleannStandalone folder, AOT2 folder and file folder, (where the LINKDATA_A of attack on titan 2 is located)
this is my command that I am executing inside the Cethleann folder:
C: \ Users \ User \ Desktop \ 3D Models \ CethleannStandalone> Cethleannn.DataExporter.exe --linkarchive -g AttackOnTitan2 C: \ Desktop \ 3D Models \ AOT2  C: \ Desktop \ 3D Models \ file


what am i typing wrong on the command line?
change from this:
Cethleannn.DataExporter.exe --linkarchive -g AttackOnTitan2 C: \ Desktop \ 3D Models \ AOT2  C: \ Desktop \ 3D Models \ file

to this:
Cethleannn.DataExporter.exe --linkarchive -g AttackOnTitan2 C:\Desktop\3D Models\AOT2  C:\Desktop\3D Models\file
## Post #252
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-28T22:21:47+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello andree, it didn't work, as you can see in the image.
I noticed that you removed Usuarios \ Usuario in the second and third part of my command line, ok?
  I don't know how to delete Users \ Users, on the second and third lines.
so I typed the line manually the way you gave it to me, but it didn't work either.
I was unable to add the image of my second command line typed in cmd, but I typed it in cmd like this:

C: \ Users \ User \ CethleannStandalone \ Cethleannn.DataExporter.exe --linkarchive -g AttackOnTitan2 C: \ Desktop \ 3D Models \ AOT2 C: \ Desktop \ 3D Models \ file

in my cmd, just below the command line, the message appears:
(Cethleann.Exporter.exe is not recognized as an internal or external command, an operable program or a batch file)

I noticed today that the version of Netcore installed on my pc is 5.0
so I uninstalled and installed version 3.1, which Yretenai provided the link at the beginning of this topic.
I will try now again to find out if the problem would be the version of Netcore
[cmd.png](https://xentaxbackup.github.io/file/19419_cmd.png)
## Post #253
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-02-02T10:07:04+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello. I've seen in the g1m noesis plugin thread that here people might be of help on how to know what g1t is for what g1m when it comes to Hyrule warriors age of calamity. How can i understand what textures are for what model? For characters it's easy enough, but props, sowrds, enemies and especially maps are hard to figure out.
## Post #254
- Username: revell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 06, 2021 4:45 am
- Post datetime: 2021-02-05T20:55:05+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

How would I change these .bin files to something I see on the preview in Noesis
[](https://ibb.co/TLS2rP5)
## Post #255
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2021-02-10T08:47:56+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

So I have been messing with Nioh 2 (PS4) game files, there are these files with a .pbkt extention. These have multiple GT1G36008 headers in them, aka multiple dds files. I believe your program and the one made for nioh2 specifically can't correctly convert these files. I manually edited the hex to separate them, and did find different textures within. Would you consider adding this so we can export them?


Examples below

[Examples](https://drive.google.com/file/d/1Xb2f98RL7eMeFp58AGYYXkYXwPHpavnQ/view?usp=sharing)
## Post #256
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-26T19:54:57+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I've read through this whole forum post looking to see if there is a fix but to no avail, I have been having an issue trying to dump animations from persona 5 strikers (PC) specifically from 'a5bb4218' (Sophia daily) using the command 

.\Nyotengu.AnimationGraph.exe -g Scramble E:\Steam\Steam\steamapps\common\P5S\P5SDump\KIDSSystemResource\kidsobjdb\CE1CommonResource.motor.kidsobjdb E:\Steam\Steam\steamapps\common\P5S\P5SDump\KIDSSystemResource\kidsobjdb\CE1CommonResource.motor.kidssingletondb -o anims -d E:\Steam\Steam\steamapps\common\P5S\P5SDump\CharacterEditor\g1a -d E:\Steam\Steam\steamapps\common\P5S\P5SDump\FieldEditor4\g1a -d E:\Steam\Steam\steamapps\common\P5S\P5SDump\RRPreview\g1a a5bb4218

I get no error message but it just ends like the model has no anims, when this isn't the case, I have also tried all the variants on her anims such as the other 2 models she has. 

This works fine with joker's (948554ec) animations and Wolf's (732d2f08) but not for some others who I have tried. I'm not all too knowledgeable about dumping animations so I was hoping there would be someone who could explain if there's more I need to add to this command line to dump these. Many thanks in advance!
[snip.PNG](https://xentaxbackup.github.io/file/19606_snip.PNG)
## Post #257
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-02-28T14:15:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Build 94 adds support for Persona 5 Strikers thanks to two contributors (zarroboogs & TGEnigma on github)
To properly export RDB/LINKDATA content you MUST pass 

```

```

to Cethleann.DataExporter.exe

Previous changes:
[viewtopic.php?f=10&t=21679&p=170833#p170833](https://forum.xentax.com/viewtopic.php?f=10&t=21679&p=170833#p170833)
## Post #258
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-28T16:25:46+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Oh I completely missed that! Thank you so much, slightly unrelated but I figured I may report it, some character animations I do have exported have some weird issues mostly cloth physics this could also be due to the exporting issues but I'll try it again later and say if that fixes it, but figured I would report it just in case! Many thanks again!
[cloth sim explosion.PNG](https://xentaxbackup.github.io/file/19615_cloth sim explosion.PNG)
## Post #259
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-28T17:15:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

So I tried to dump the files again but the command I was using

.\Cethleann.DataExporter.exe --rdb -g P5SPC E:\Steam\Steam\steamapps\common\P5S\P5SDump E:\Steam\Steam\steamapps\common\P5S\data\motor_rsc

Is still providing the same results, do I need to do --game at the end of it? (Sorry I'm rather new to using things more command prompt oriented)
## Post #260
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-02-28T17:55:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Crash ↑Mon Mar 01, 2021 12:25 am at Mon Mar 01, 2021 12:25 am
>
> 
Oh I completely missed that! Thank you so much, slightly unrelated but I figured I may report it, some character animations I do have exported have some weird issues mostly cloth physics this could also be due to the exporting issues but I'll try it again later and say if that fixes it, but figured I would report it just in case! Many thanks again!

Not a bug with cethleann, report it in the g1m plugin thread.
## Post #261
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-28T17:55:53+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Noted! will do that in a few
> Reply from Yretenai ↑Mon Mar 01, 2021 1:55 am at Mon Mar 01, 2021 1:55 am
>
> 
Crash wrote: ↑Mon Mar 01, 2021 12:25 am
Oh I completely missed that! Thank you so much, slightly unrelated but I figured I may report it, some character animations I do have exported have some weird issues mostly cloth physics this could also be due to the exporting issues but I'll try it again later and say if that fixes it, but figured I would report it just in case! Many thanks again!


Not a bug with cethleann, report it in the g1m plugin thread.
## Post #262
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-28T20:02:04+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Crash ↑Mon Mar 01, 2021 1:15 am at Mon Mar 01, 2021 1:15 am
>
> 
So I tried to dump the files again but the command I was using

.\Cethleann.DataExporter.exe --rdb -g P5SPC E:\Steam\Steam\steamapps\common\P5S\P5SDump E:\Steam\Steam\steamapps\common\P5S\data\motor_rsc

Is still providing the same results, do I need to do --game at the end of it? (Sorry I'm rather new to using things more command prompt oriented)

Tried this again just to be sure nothing went wrong and trying to dump anims from this still yeilds no luck with some charcters, only some though...
## Post #263
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-03-01T14:52:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I tried dumping it again but with --game P5SPC at the end and it dumped to the cethleann folder rather than the specified output, which isn't a huge issue, but it still doesn't seem to export the animations of the models I give the input 

.\Nyotengu.AnimationGraph.exe -g Scramble O:\Cethleann\P5SPC\KIDSSystemResource\kidsobjdb\CE1CommonResource.motor.kidsobjdb O:\Cethleann\P5SPC\KIDSSystemResource\kidsobjdb\CE1CommonResource.motor.kidssingletondb -o anims -d O:\Cethleann\P5SPC\CharacterEditor\g1a -d O:\Cethleann\P5SPC\FieldEditor4\g1a -d O:\Cethleann\P5SPC\RRPreview\g1a a5bb4218

I'm still given the 'Loading filelist for Scramble-rdb' then after about a second it just allows me to run another command, trying this with a model I know has worked before still does work, and I am at a loss for as to why this is happening
## Post #264
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-03-06T22:26:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I do have another question I'm not sure about (Sorry If I'm posting a lot in a row) is there a better way of getting all the G1T texture files for a Persona 5 Strikers model rather than having to scroll through all 29k textures? I remember vaugely reading on it but couldn't find anything definitive on it.
## Post #265
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2021-03-06T23:48:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Crash ↑Sun Mar 07, 2021 6:26 am at Sun Mar 07, 2021 6:26 am
>
> 
I do have another question I'm not sure about (Sorry If I'm posting a lot in a row) is there a better way of getting all the G1T texture files for a Persona 5 Strikers model rather than having to scroll through all 29k textures? I remember vaugely reading on it but couldn't find anything definitive on it.

This is the same issue we have with Hyrule Warriors: Age of Calamity, and no, that was never solved either, so I doubt there's a way to with Persona 5 Strikers.
## Post #266
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-03-07T02:05:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Doctor Loboto ↑Sun Mar 07, 2021 7:48 am at Sun Mar 07, 2021 7:48 am
>
> 
Crash wrote: ↑Sun Mar 07, 2021 6:26 am
I do have another question I'm not sure about (Sorry If I'm posting a lot in a row) is there a better way of getting all the G1T texture files for a Persona 5 Strikers model rather than having to scroll through all 29k textures? I remember vaugely reading on it but couldn't find anything definitive on it.


This is the same issue we have with Hyrule Warriors: Age of Calamity, and no, that was never solved either, so I doubt there's a way to with Persona 5 Strikers.

Ah damn that sucks, thanks for letting me know anywhom!
## Post #267
- Username: StyleKiller
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 07, 2021 3:43 pm
- Post datetime: 2021-03-07T08:06:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm trying to extract the sound files from P5 Strikers but don't know how  

I used Cethleann.DataExporter to get everything inside the .rdb files, but I'm not sure how to proceed. Can anyone help me?
## Post #268
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-03-19T01:41:15+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

does the Cethleann tool have enough information on age of calamity, so that files or skeletal mesh have bone and mesh names?
## Post #269
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2021-03-24T01:49:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, just started using this today to try and extract some AOT2 models. I have effectively no idea what I'm doing, but I've got to the point where I need to use Cethleann.Unbundler.exe. 

The only way I've managed to use it is by unbundling .ptrbundle files one-by-one in command prompt. Is there an easier way to extract multiple .ptrbundle files at once rather than going through so many files by hand? Dragging and dropping them onto Cethleann.Unbundler.exe seems to give me an 'access denied' error (which is probably due to admin privileges but as far as I'm aware there's no way to run a program with admin privileges when you're opening it by dragging and dropping something onto its icon):



Additionally, is there a way to convert the resulting .g1m files in batch/bulk after they're extracted?
## Post #270
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2021-03-24T12:11:21+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Game Hyrule Warriors: Age of Calamity
Do you have any possibility of packing LinkData.bin or a way to get the names of the .bin files that contain the game texts? we are trying to translate the same.
## Post #271
- Username: BettyBalloon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 25, 2021 3:38 am
- Post datetime: 2021-03-24T19:48:55+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I'm new here, made this account just for this.. 

I'd like to rip some models and animations and I've never done stuff like this before have not really idea what to do.. I'm assuming I have to open "cmd" and enter something like "Cethleann.Unbundler.exe <path>" or "Cethleann.DataExporter.exe <some parameters>".. Or drag and drop something onto "Cethleann.DataExporter.exe"? Is that correct? Do I have to do something before that? 

Problem is, it always says "access denied" when trying to do that (using windows 10)...

Would try the Steam version of Atelier Sophie or the switch version of Hyrule Warriors..
## Post #272
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-03-31T09:57:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi,

Can you also make this tool to support both Koei Tecmo and Compile Heart/ Idea Factory archive files. 


Compile Heart/ Idea Factory now use .dat archives with .csh tables, but i can't read them, especially some Neptunia games have them.

(well....actually 2 of them)


please?
## Post #273
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2021-04-01T03:11:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from BettyBalloon ↑Thu Mar 25, 2021 3:48 am at Thu Mar 25, 2021 3:48 am
>
> 
Hi, I'm new here, made this account just for this.. 

I'd like to rip some models and animations and I've never done stuff like this before have not really idea what to do.. I'm assuming I have to open "cmd" and enter something like "Cethleann.Unbundler.exe <path>" or "Cethleann.DataExporter.exe <some parameters>".. Or drag and drop something onto "Cethleann.DataExporter.exe"? Is that correct? Do I have to do something before that? 

Problem is, it always says "access denied" when trying to do that (using windows 10)...

Would try the Steam version of Atelier Sophie or the switch version of Hyrule Warriors..

Same issue here. I believe the "access denied" is something to do with needing to run the unbundler with administrator privileges, but there's no way to do that when you're dragging and dropping files onto an .exe.

Maybe there's a way to do it with a .bat file? I wouldn't know where to start on that.
## Post #274
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-04-02T07:59:38+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello,how can i get the animation file from Dynasty Warriors 9?
## Post #275
- Username: Kisuma
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 02, 2021 11:45 pm
- Post datetime: 2021-04-02T20:27:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello, can someone explain me how to exctract 3D models from Attack on Titan 2 ? I downloaded everything i need i think but i don't understand how to use all of this... I have Discord if you guys prefer, I would really like someone to help me, I'm just getting started in this, there is no tutorial anywhere... (my Discord tag : Kisuma#9943) 

Thanks !
## Post #276
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2021-04-03T23:18:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Kisuma ↑Sat Apr 03, 2021 4:27 am at Sat Apr 03, 2021 4:27 am
>
> 
Hello, can someone explain me how to exctract 3D models from Attack on Titan 2 ? I downloaded everything i need i think but i don't understand how to use all of this... I have Discord if you guys prefer, I would really like someone to help me, I'm just getting started in this, there is no tutorial anywhere... (my Discord tag : Kisuma#9943) 

Thanks !

Also looking to extract the models from AOT2... this program really needs a tutorial, but from the lack of response it seems like it might be dead?
## Post #277
- Username: Kisuma
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 02, 2021 11:45 pm
- Post datetime: 2021-04-04T22:52:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from jayko ↑Sun Apr 04, 2021 7:18 am at Sun Apr 04, 2021 7:18 am
>
> 
Kisuma wrote: ↑Sat Apr 03, 2021 4:27 am
Hello, can someone explain me how to exctract 3D models from Attack on Titan 2 ? I downloaded everything i need i think but i don't understand how to use all of this... I have Discord if you guys prefer, I would really like someone to help me, I'm just getting started in this, there is no tutorial anywhere... (my Discord tag : Kisuma#9943) 

Thanks !


Also looking to extract the models from AOT2... this program really needs a tutorial, but from the lack of response it seems like it might be dead?

yeah it's possible, unfortunately ...
## Post #278
- Username: GameAreAwesome
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 07, 2010 1:49 pm
- Post datetime: 2021-04-07T03:49:40+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hey there,
So I've been trying to get AOT2 map models (i.e. buildings, houses, etc.) but so far all I've been able to extract were character textures and models.
I was able to also extract the textures for the map models but I could not find any of the models.
As far as I understand all the models are stored inside of the PTRBUNDLE folder. But all that was inside is character models.

Did I miss a step or am I suppose to look for the map models somewhere else?
## Post #279
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2021-04-26T19:57:50+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Does anyone know where Aelfric's model is stored for Fire Emblem Three Houses? Been scouring the G1m models, I have the 4 DLC characters, but can't find him.
## Post #280
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2021-05-01T00:16:54+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from jayko ↑Wed Mar 24, 2021 9:49 am at Wed Mar 24, 2021 9:49 am
>
> 
Hi, just started using this today to try and extract some AOT2 models. I have effectively no idea what I'm doing, but I've got to the point where I need to use Cethleann.Unbundler.exe.

I need to reextract LINKDATA_A.BIN and I've completely forgotten how I did it the first time.
## Post #281
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2021-05-02T06:52:50+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I am trying to unbundle the FE3H DLC assets from the DATA0/DATA1.bin files, but the Unbundler doesn't work as it outputs no files.

Previously, I have tried to use this [python script from this github wiki.](https://github.com/three-houses-research-team/Throne-of-Knowledge/wiki/Dump-&-Extract-Game) However, I end up getting [scripting errors](https://github.com/three-houses-research-team/Throne-of-Knowledge/issues/4) and I have created an issue on their github repo, but I have doubts that they will respond at all, given the lack of responses on the previous issues. 

In that case, what's the command to unbundle the assets from the DATA0/DATA1.bin files?

EDIT: With Joschuka's assistance, I was able to extract from all DLC and Update bin files, but the 1.2.0 update. It was repetitively giving out this error message when attempting to extract from the 1.2.0 DATA bin files:

```
   at System.IO.FileStream.set_Position(Int64 value)
   at Cethleann.Archive.DATA0.ReadEntry(Stream data1, DATA0Entry entry) in C:\projects\cethleann\Cethleann\Archive\DATA0.cs:line 93
   at Cethleann.Archive.DATA0.ReadEntry(Stream data1, Int32 index) in C:\projects\cethleann\Cethleann\Archive\DATA0.cs:line 66
   at Cethleann.ManagedFS.Flayn.ReadEntry(Int32 index) in C:\projects\cethleann\Cethleann\ManagedFS\Flayn.cs:line 120
   at Cethleann.DataExporter.Program.Main(String[] args) in C:\projects\cethleann\Cethleann.DataExporter\Program.cs:line 106
```
## Post #282
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-05-13T10:21:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi Everyone!

I´m new at this and I´m exporting the models for Nioh 2 I have access to all the characters and item models from the base game and the first 2 DLCs thanks to the tool, but I havent been able to find the data for the 3 DLC, The First Samurai, has anyone been able to find it?
## Post #283
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-05-13T21:56:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

can someone send the PTRBUNDLE folder, extracted from the linkdata file, from the attack on titan 2 final battle game?
I have tried to extract this folder from the linkdata with the tool here in the topic, but I couldn't.
Thank you all for the attention
## Post #284
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2021-05-19T22:50:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from JosouKitsune ↑Mon May 04, 2020 4:18 am at Mon May 04, 2020 4:18 am
>
> 
Doctor Loboto wrote: ↑Mon May 04, 2020 12:17 am
I lost track of this thread. I'm trying to extract from One Piece: Pirate Warriors 3 for PC, which uses 'LINKDATA_EU_OS_EUNA.A' and so on for Archive files. I've been trying to specify it to extract these files into a specific folder but any time I try the usual methods with DataExporter all it does is inform me of the program name and version, and nothing else. Am I messing up the command line? Currently I'm trying...
D:\Downloads\CethleannStandalone_netcore30\Cethleann.DataExporter.exe --flayn "D:\Downloads\OPPW3" "D:\SteamLibrary\steamapps\common\OPPW3\LINKDATA_DX9"
And the result is always just
[2020-05-03T16:03:04][Cethleann] Cethleann.DataExporter v1.0.46.0

It doesn't seem to recognize any of them.

This tool only works with the dlc bin files, to extract the linkdata you need to use Steven gas machine

Sorry to bother on an old reply, the dlc bin files located in FILE_DX9\DLC\EFIGS right? I'm trying to get those to work but none of the command options seem to work for it, do you happen to know which one works with it?
## Post #285
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2021-05-23T23:52:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Yretenai ↑Fri Feb 07, 2020 2:25 am at Fri Feb 07, 2020 2:25 am
>
> 
Cethleann now can also extract any LINKDATA pair (.IDX and .BIN file) by providing --idx and --bin values to Koei.DataExporter's arguments
i.e. for Dragon Quest Heroes you would call
Code: Select allKoei.DataExporter.exe --idx LINKDATA --bin LINKDATA "InstallDir" "ExportDir"


Cethleann now can also extract RDB files from both Windows (Dead or Alive 6, Romance of the Three Kingdoms 14) and Switch (Persona 5 Scramble) using the new Softness.DataExporter.exe tool.
Code: Select allSoftness.DataExporter.exe -g Scramble ExportDir DirectoryWithRDBs


It's important to pass "-g GameId" when exporting RDBs as files have hashed filenames. Currently I only have a partial Dead or Alive 6 filelist (from rdbtool)

Thank you for your amazing program. If i may ask, may i have the GameID list? I only have knowledge how to extract P5S but not other Koei Tecmo game due to not knowing their GameID. I want to try and extract DOA6 model and get their animation so I can import to Persona 5
## Post #286
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2021-05-24T01:11:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Eag1e ↑Thu May 20, 2021 6:50 am at Thu May 20, 2021 6:50 am
>
> 
JosouKitsune wrote: ↑Mon May 04, 2020 4:18 am

This tool only works with the dlc bin files, to extract the linkdata you need to use Steven gas machine


Sorry to bother on an old reply, the dlc bin files located in FILE_DX9\DLC\EFIGS right? I'm trying to get those to work but none of the command options seem to work for it, do you happen to know which one works with it?

You need to use Cethleann.Unbundler

```
Cethleann.Unbundler.exe -R game_path\FILE_DX9\DLC\EFIGS
```
## Post #287
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-05-24T21:30:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from demonslayerx8 ↑Sat Jan 23, 2021 1:30 pm at Sat Jan 23, 2021 1:30 pm
>
> 
I hope ur aware that u were supposed to edit the paths on ur end instead of using the same command he gave ya

like for example, mine was
Cethleann.DataExporter.exe --linkarchive -g AttackOnTitan2 "K:\Games\Attack on Titan 2\LINKDATA\Extract" "K:\Games\Attack on Titan 2\LINKDATA"

could you kindly take a picture of your cmd of how you typed your command to be able to extract the LINKDATA files for attack on titan 2 final battle?
I would like to see the command you used on your cmd in an image.
## Post #288
- Username: galianbeast
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 12, 2014 1:38 pm
- Post datetime: 2021-05-29T14:25:52+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi! I'm trying to download the latest build, but there doesn't seem to be any links in Appveyor. It shows there's 3 files in Artifacts but they might have been automatically deleted. Is this the case, or am I just being dumb?
[appveyor.png](https://xentaxbackup.github.io/file/20225_appveyor.png)
## Post #289
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2021-05-30T20:10:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Sorry if this is off-topic, but is there a list of Koei games that this tool works on?
## Post #290
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2021-06-07T10:37:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from galianbeast ↑Sat May 29, 2021 10:25 pm at Sat May 29, 2021 10:25 pm
>
> 
Hi! I'm trying to download the latest build, but there doesn't seem to be any links in Appveyor. It shows there's 3 files in Artifacts but they might have been automatically deleted. Is this the case, or am I just being dumb?

That's cause that one is no longer available. U want to use this one now
[https://ci.appveyor.com/project/yretena ... /artifacts](https://ci.appveyor.com/project/yretenai/cethleann/builds/39392090/artifacts)
## Post #291
- Username: Joee99
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2021 11:12 pm
- Post datetime: 2021-06-11T15:14:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I'm just checking if there has been any way to identify the filenames for pairing the textures to the model files with Hyrule Warriors: Age of Calamity yet, or is it still not possible? 

I'd rather not have to go through and manually identify each texture...
## Post #292
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-11T15:42:39+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joee99 ↑Fri Jun 11, 2021 11:14 pm at Fri Jun 11, 2021 11:14 pm
>
> 
Hi, I'm just checking if there has been any way to identify the filenames for pairing the textures to the model files with Hyrule Warriors: Age of Calamity yet, or is it still not possible? 

I'd rather not have to go through and manually identify each texture...

What do you mean ? It's been possible since day one : [viewtopic.php?f=10&t=21679&start=45#p160417](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=45#p160417)
## Post #293
- Username: Joee99
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2021 11:12 pm
- Post datetime: 2021-06-11T20:34:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Fri Jun 11, 2021 11:42 pm at Fri Jun 11, 2021 11:42 pm
>
> 
Joee99 wrote: ↑Fri Jun 11, 2021 11:14 pm
Hi, I'm just checking if there has been any way to identify the filenames for pairing the textures to the model files with Hyrule Warriors: Age of Calamity yet, or is it still not possible? 

I'd rather not have to go through and manually identify each texture...


What do you mean ? It's been possible since day one : viewtopic.php?f=10&t=21679&start=45#p160417

From what I know, this method doesn't work with Age of Calamity. I was wondering if any workarounds have been found.
## Post #294
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-12T15:40:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joee99 ↑Sat Jun 12, 2021 4:34 am at Sat Jun 12, 2021 4:34 am
>
> 
Joschka wrote: ↑Fri Jun 11, 2021 11:42 pm
Joee99 wrote: ↑Fri Jun 11, 2021 11:14 pm
Hi, I'm just checking if there has been any way to identify the filenames for pairing the textures to the model files with Hyrule Warriors: Age of Calamity yet, or is it still not possible? 

I'd rather not have to go through and manually identify each texture...


What do you mean ? It's been possible since day one : viewtopic.php?f=10&t=21679&start=45#p160417


From what I know, this method doesn't work with Age of Calamity. I was wondering if any workarounds have been found.

Hmm, who told you that ? It's working fine, they didn't change anything
## Post #295
- Username: Mukojin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 13, 2021 4:02 am
- Post datetime: 2021-06-12T20:06:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, when I open doa6 hair in noesis the hair seems to not have any weights. is there a way to fix that?
## Post #296
- Username: Joee99
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2021 11:12 pm
- Post datetime: 2021-06-12T20:25:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Sat Jun 12, 2021 11:40 pm at Sat Jun 12, 2021 11:40 pm
>
> 
Joee99 wrote: ↑Sat Jun 12, 2021 4:34 am
Joschka wrote: ↑Fri Jun 11, 2021 11:42 pm


What do you mean ? It's been possible since day one : viewtopic.php?f=10&t=21679&start=45#p160417


From what I know, this method doesn't work with Age of Calamity. I was wondering if any workarounds have been found.


Hmm, who told you that ? It's working fine, they didn't change anything

Sorry, I should have clarified, the file names are all hexadecimal. I'd like to be able export the files with the actual file names or restore them, so I can see which textures are used with which models.
## Post #297
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-13T05:06:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Mukojin ↑Sun Jun 13, 2021 4:06 am at Sun Jun 13, 2021 4:06 am
>
> 
Hi, when I open doa6 hair in noesis the hair seems to not have any weights. is there a way to fix that?

No, hair is simulated at runtime and doesn't have classic weights.

> Reply from Joee99 ↑Sun Jun 13, 2021 4:25 am at Sun Jun 13, 2021 4:25 am
>
> 
Joschka wrote: ↑Sat Jun 12, 2021 11:40 pm
Joee99 wrote: ↑Sat Jun 12, 2021 4:34 am


From what I know, this method doesn't work with Age of Calamity. I was wondering if any workarounds have been found.


Hmm, who told you that ? It's working fine, they didn't change anything


Sorry, I should have clarified, the file names are all hexadecimal. I'd like to be able export the files with the actual file names or restore them, so I can see which textures are used with which models.

You don't need filenames to reconstruct textures. Actually just grab this list, it'll be easier for you. 


 AoCThingy.zip
(117.19 KiB) Downloaded 64 times


Take your g1mHash and read the associated textureID and resource name.
For ex Impa is f23c0538, you get a2cf3043 and CharacterEditor.kidssingletondb from the list. She comes from CharacterEditor\g1m so you type :

```
Nyotengu.KTID.exe ..\AocExtract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb ..\AocExtract\MaterialEditor\g1t ..\AocExtract\CharacterEditor\ktid\a2cf3043.ktid
```

It'll parse and reconstruct the correct g1t and will output it in the same folder as the ktid (so characterEditor\ktid here)
Then you can just open it in Noesis on your model
## Post #298
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-06-14T21:09:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Sun Jun 13, 2021 1:06 pm at Sun Jun 13, 2021 1:06 pm
>
> 
Mukojin wrote: ↑Sun Jun 13, 2021 4:06 am
Hi, when I open doa6 hair in noesis the hair seems to not have any weights. is there a way to fix that?


No, hair is simulated at runtime and doesn't have classic weights.
Joee99 wrote: ↑Sun Jun 13, 2021 4:25 am
Joschka wrote: ↑Sat Jun 12, 2021 11:40 pm


Hmm, who told you that ? It's working fine, they didn't change anything


Sorry, I should have clarified, the file names are all hexadecimal. I'd like to be able export the files with the actual file names or restore them, so I can see which textures are used with which models.


You don't need filenames to reconstruct textures. Actually just grab this list, it'll be easier for you. 
AoCThingy.zip
Take your g1mHash and read the associated textureID and resource name.
For ex Impa is f23c0538, you get a2cf3043 and CharacterEditor.kidssingletondb from the list. She comes from CharacterEditor\g1m so you type :
Code: Select allNyotengu.KTID.exe ..\AocExtract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb ..\AocExtract\MaterialEditor\g1t ..\AocExtract\CharacterEditor\ktid\a2cf3043.ktid
It'll parse and reconstruct the correct g1t and will output it in the same folder as the ktid (so characterEditor\ktid here)
Then you can just open it in Noesis on your model

will there be updates to the list for the dlc?
## Post #299
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-14T22:37:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Enkidu115 ↑Tue Jun 15, 2021 5:09 am at Tue Jun 15, 2021 5:09 am
>
> 
Joschka wrote: ↑Sun Jun 13, 2021 1:06 pm
Mukojin wrote: ↑Sun Jun 13, 2021 4:06 am
Hi, when I open doa6 hair in noesis the hair seems to not have any weights. is there a way to fix that?


No, hair is simulated at runtime and doesn't have classic weights.
Joee99 wrote: ↑Sun Jun 13, 2021 4:25 am


Sorry, I should have clarified, the file names are all hexadecimal. I'd like to be able export the files with the actual file names or restore them, so I can see which textures are used with which models.


You don't need filenames to reconstruct textures. Actually just grab this list, it'll be easier for you. 
AoCThingy.zip
Take your g1mHash and read the associated textureID and resource name.
For ex Impa is f23c0538, you get a2cf3043 and CharacterEditor.kidssingletondb from the list. She comes from CharacterEditor\g1m so you type :
Code: Select allNyotengu.KTID.exe ..\AocExtract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb ..\AocExtract\MaterialEditor\g1t ..\AocExtract\CharacterEditor\ktid\a2cf3043.ktid
It'll parse and reconstruct the correct g1t and will output it in the same folder as the ktid (so characterEditor\ktid here)
Then you can just open it in Noesis on your model


will there be updates to the list for the dlc?

If I buy it yeah. Will depend on what Nintendo will show tomorrow but I'm not too optimistic about its content so not sure, will have to be really worth the price.
## Post #300
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-06-15T02:55:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Tue Jun 15, 2021 6:37 am at Tue Jun 15, 2021 6:37 am
>
> 
Enkidu115 wrote: ↑Tue Jun 15, 2021 5:09 am
Joschka wrote: ↑Sun Jun 13, 2021 1:06 pm


No, hair is simulated at runtime and doesn't have classic weights.



You don't need filenames to reconstruct textures. Actually just grab this list, it'll be easier for you. 
AoCThingy.zip
Take your g1mHash and read the associated textureID and resource name.
For ex Impa is f23c0538, you get a2cf3043 and CharacterEditor.kidssingletondb from the list. She comes from CharacterEditor\g1m so you type :
Code: Select allNyotengu.KTID.exe ..\AocExtract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb ..\AocExtract\MaterialEditor\g1t ..\AocExtract\CharacterEditor\ktid\a2cf3043.ktid
It'll parse and reconstruct the correct g1t and will output it in the same folder as the ktid (so characterEditor\ktid here)
Then you can just open it in Noesis on your model


will there be updates to the list for the dlc?


If I buy it yeah. Will depend on what Nintendo will show tomorrow but I'm not too optimistic about its content so not sure, will have to be really worth the price.

thats understandable lol
## Post #301
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2021-06-18T21:01:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Has there been any progress on the DLC for HW:AOC? Been trying to get the files open the same way as the base game but doesn't seem to work.
## Post #302
- Username: Rokki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 05, 2016 2:03 pm
- Post datetime: 2021-06-26T03:37:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Tue Jun 15, 2021 6:37 am at Tue Jun 15, 2021 6:37 am
>
> 
Enkidu115 wrote: ↑Tue Jun 15, 2021 5:09 am
Joschka wrote: ↑Sun Jun 13, 2021 1:06 pm


No, hair is simulated at runtime and doesn't have classic weights.



You don't need filenames to reconstruct textures. Actually just grab this list, it'll be easier for you. 
AoCThingy.zip
Take your g1mHash and read the associated textureID and resource name.
For ex Impa is f23c0538, you get a2cf3043 and CharacterEditor.kidssingletondb from the list. She comes from CharacterEditor\g1m so you type :
Code: Select allNyotengu.KTID.exe ..\AocExtract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb ..\AocExtract\MaterialEditor\g1t ..\AocExtract\CharacterEditor\ktid\a2cf3043.ktid
It'll parse and reconstruct the correct g1t and will output it in the same folder as the ktid (so characterEditor\ktid here)
Then you can just open it in Noesis on your model


will there be updates to the list for the dlc?


If I buy it yeah. Will depend on what Nintendo will show tomorrow but I'm not too optimistic about its content so not sure, will have to be really worth the price.
Anything news about DOA6 DLC?
I can export the textured fbx through the paired g1m/g1t from here: [viewtopic.php?f=16&p=164234#p164234](https://forum.xentax.com/viewtopic.php?f=16&p=164234#p164234)
If the ktid file is named by hash, g1t can be successfully exported, but I cannot find the corresponding g1m file.
Is there something like ‘DOA6thingy’?
Thanks
## Post #303
- Username: liquer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 28, 2021 10:44 pm
- Post datetime: 2021-06-28T14:30:35+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi everyone, as you may know, samurai warriors 5 has been released. So I tried to extract its switch version with --nyotengu. I definitely got some g1m and g1t files, just as P5S. I mean it also has rdb files and linkdata files at the same time. I recognized a few characters' g1m files such as nobunaga and mitsuhide.
But I met some troubles when I tried to find textures. I got that rdb file system has a series of g1t files so it need ktid to assemble. But I don't know how to analyze the different ktid files. So can anyone give some tutorial or tips? If I make a list I will be glad to share it.

update: completely resolved. Thanks to Nyogentu.KTID!
## Post #304
- Username: Equirah
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 16, 2021 4:49 am
- Post datetime: 2021-07-03T12:26:56+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is this compatible with Nioh 2? If so, what are the decryption settings?
## Post #305
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-07-04T14:40:47+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Equirah ↑Sat Jul 03, 2021 8:26 pm at Sat Jul 03, 2021 8:26 pm
>
> 
Is this compatible with Nioh 2? If so, what are the decryption settings?
Use PS4 game, not PC.
## Post #306
- Username: atreyugam3r10
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 15, 2021 7:01 am
- Post datetime: 2021-07-14T23:04:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Ha im having alot of issues figuring out how to run this
## Post #307
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2021-07-27T15:46:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi! Could you support toukiden 2 PC! I tried all command but it won't work.
Thanks in advance.
## Post #308
- Username: crabsmack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 05, 2021 11:44 pm
- Post datetime: 2021-08-05T15:49:04+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi; I can't seem to find any artifacts on Appveyor. Forgive me if I'm missing something obvious but neither the latest build nor any of the historical builds I checked have artifacts. It shows "Artifacts: 3" and then below "The build job does not contain any artifacts." I found this post with a similar issue:

> Reply from demonslayerx8 ↑Mon Jun 07, 2021 6:37 pm at Mon Jun 07, 2021 6:37 pm
>
> 
galianbeast wrote: ↑Sat May 29, 2021 10:25 pm
Hi! I'm trying to download the latest build, but there doesn't seem to be any links in Appveyor. It shows there's 3 files in Artifacts but they might have been automatically deleted. Is this the case, or am I just being dumb?


That's cause that one is no longer available. U want to use this one now
https://ci.appveyor.com/project/yretena ... /artifacts

Are the artifacts deleted after some period of time? Is there another way to access the latest builds?
## Post #309
- Username: Amal Kotay
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 11, 2011 11:04 pm
- Post datetime: 2021-08-07T20:42:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from crabsmack ↑Thu Aug 05, 2021 11:49 pm at Thu Aug 05, 2021 11:49 pm
>
> 
Hi; I can't seem to find any artifacts on Appveyor. Forgive me if I'm missing something obvious but neither the latest build nor any of the historical builds I checked have artifacts. It shows "Artifacts: 3" and then below "The build job does not contain any artifacts." I found this post with a similar issue:
demonslayerx8 wrote: ↑Mon Jun 07, 2021 6:37 pm
galianbeast wrote: ↑Sat May 29, 2021 10:25 pm
Hi! I'm trying to download the latest build, but there doesn't seem to be any links in Appveyor. It shows there's 3 files in Artifacts but they might have been automatically deleted. Is this the case, or am I just being dumb?


That's cause that one is no longer available. U want to use this one now
https://ci.appveyor.com/project/yretena ... /artifacts


Are the artifacts deleted after some period of time? Is there another way to access the latest builds?

Same question, Appveyor link is empty.
## Post #310
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-08-08T12:31:25+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Appveyor deletes files after 1 month now. I'm likely going to host the latest version somewhere more persistent.

Anyway the builds are up again.
## Post #311
- Username: crabsmack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 05, 2021 11:44 pm
- Post datetime: 2021-08-08T19:57:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Thank you! I'm trying to decipher Marvel Ultimate Alliance 3 files. I ran Cethleann.Unbundler on the romfs directory and it was able to extract many of the sound and UI string files. And I had success with Cethleann.Gz on the ZL_ files for models and textures. But the files I'm trying to figure out are those in the DATA directory which are relatively small .bin files.

I've read through the thread and tried out commands and arguments suggested for other games with the Unbundler and DataExporter but I'm not getting any output. Earlier in the thread someone mentioned that Team Ninja uses XOR'd json files in their games but I don't know if that's the case here.

I've attached a set of those .bin files. Do you have any idea where I should start with these? Thank you 
[MUA3 bins.zip](https://xentaxbackup.github.io/file/20598_MUA3 bins.zip)
## Post #312
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-08-09T17:58:36+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from crabsmack ↑Mon Aug 09, 2021 3:57 am at Mon Aug 09, 2021 3:57 am
>
> 
Thank you! I'm trying to decipher Marvel Ultimate Alliance 3 files. I ran Cethleann.Unbundler on the romfs directory and it was able to extract many of the sound and UI string files. And I had success with Cethleann.Gz on the ZL_ files for models and textures. But the files I'm trying to figure out are those in the DATA directory which are relatively small .bin files.

I've read through the thread and tried out commands and arguments suggested for other games with the Unbundler and DataExporter but I'm not getting any output. Earlier in the thread someone mentioned that Team Ninja uses XOR'd json files in their games but I don't know if that's the case here.

I've attached a set of those .bin files. Do you have any idea where I should start with these? Thank you

Seems to be some kind of serialized data structure, eeach of the files has a different header.  Hard to say what it is without reference data.
## Post #313
- Username: atreyugam3r10
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 15, 2021 7:01 am
- Post datetime: 2021-08-22T08:23:23+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Would someone PLEASE tell me how to run this ive been asking for months and not a single person has even made a reply point me in the direction i need to go or to someone that can
## Post #314
- Username: alkdjfalj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 20, 2021 8:37 pm
- Post datetime: 2021-09-10T03:11:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I'm sorry could you please re-upload the build?
## Post #315
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-09-10T19:30:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from alkdjfalj ↑Fri Sep 10, 2021 11:11 am at Fri Sep 10, 2021 11:11 am
>
> 
Hi, I'm sorry could you please re-upload the build?
[https://github.com/yretenai/Cethleann/r ... ag/1.1.104](https://github.com/yretenai/Cethleann/releases/tag/1.1.104)
## Post #316
- Username: tachiban
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 18, 2021 2:09 pm
- Post datetime: 2021-09-17T10:23:05+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I am sorry to bother you.I am trying to get nioh2's lfm_order_01.bin.But i don't know how to use the tool to get G1 documents。What need i do?
## Post #317
- Username: foubou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 04, 2017 8:23 am
- Post datetime: 2021-10-07T18:23:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is there a tuto or something to unpack the LINKDATx.bin of Toukiden KIwami please ?
What are the commands to use to extract the files ?
Thank you for the tool !
## Post #318
- Username: atreyugam3r10
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 15, 2021 7:01 am
- Post datetime: 2021-10-08T03:35:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hey i've figured out how to use cethlean. however I'm trying to get into the DLC bin files from Aot 2 (AttackOnTitan 2) would anyone know what to do to extract those? ive tried a few different things but none of them worked Thanks.
## Post #319
- Username: liquer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 28, 2021 10:44 pm
- Post datetime: 2021-10-08T11:21:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hi, I have a question is there any support for linkdata.bns file? The old format for PS3 Samurai Warrirors 3/Sengoku Musou 3 I mean.
## Post #320
- Username: TheCowness
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 14, 2021 1:22 pm
- Post datetime: 2021-10-14T05:52:06+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Doctor Loboto ↑Fri Dec 25, 2020 3:56 am at Fri Dec 25, 2020 3:56 am
>
> 
I've pretty much given up on getting the 'matched' files from Age of Calamity, since I can't get a straight answer anywhere and I've tried everything I could imagine myself.
I've moved on to Dragon Quest Builders 2. I'm having trouble extracting the files, even though they should be compatible... Here's my current method, not sure what's going wrong.
Code: Select allCethleann.DataExporter.exe --linkdata --idx="D:\DRAGON QUEST BUILDERS 2\LINKDATA.IDX" --bin="D:\DRAGON QUEST BUILDERS 2\LINKDATA.BIN" "D:\DRAGON QUEST BUILDERS 2" G:\DQB2
[2020-12-24T19:52:51][Cethleann] Cethleann.DataExporter v1.1.79.0
[2020-12-24T19:52:51][Cethleann] Arguments: ["--linkdata","--idx=D:\\DRAGON QUEST BUILDERS 2\\LINKDATA.IDX","--bin=D:\\DRAGON QUEST BUILDERS 2\\LINKDATA.BIN","D:\\DRAGON QUEST BUILDERS 2","G:\\DQB2"]
[2020-12-24T19:52:51][FileList] Loading filelist for LINKDATAPatterns-link
[2020-12-24T19:52:51][FileList] Loading filelist for unknown-link

I'm trying to open up Builders 2 as well, trying to rip some models for 3D printing.  I think Doctor Loboto's problem is that he has equal signs between his --idx and --bin parameters and the paths instead of spaces, but when I use spaces it still doesn't work.  My error is:

Unhandled exception. System.IO.IOException: The parameter is incorrect. : 'D:\DQB2\LINKDATA.BIN'

This is of course my path after the --bin parameter:

Cethleann.DataExporter.exe --linkdata --idx "D:\DQB2\LINKDATA.IDX" --bin "D:\DQB2\LINKDATA.BIN" "D:\DQB2\" "D:\DQB2CethExtract"

I don't fully understand the parameters.  I think the last one is the target where the program's exporting to, but what's the purpose of the one before that?  I'm using a dump of the Switch version if it matters.

I'm also confused by references to other executable names in this thread, such as "koei.dataexporter.exe".  Were those older names of the same tool?
## Post #321
- Username: wuxiao
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 07, 2021 3:36 pm
- Post datetime: 2021-11-10T07:06:54+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann DataExporter I installed net5.0 but it can’t be opened??
## Post #322
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-11-11T16:26:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Does anyone have a command to extract blue reflection tie paks?
## Post #323
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-11-11T16:47:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Makoto ↑Fri Nov 12, 2021 12:26 am at Fri Nov 12, 2021 12:26 am
>
> 
Does anyone have a command to extract blue reflection tie paks?
use gust_tools.
[https://github.com/VitaSmith/gust_tools](https://github.com/VitaSmith/gust_tools)
## Post #324
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-11-15T06:56:10+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello everyone how can i extract Dynasty Warriors 9 LINKFILE .BIN files
## Post #325
- Username: Psycoskel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 19, 2021 10:53 pm
- Post datetime: 2021-12-19T14:59:14+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hey, I'm trying to extract models and animations from Fatal Frame 5 and I've had no problem extracting and viewing the models + textures in Noesis of the characters in Fatal Frame 5, but I'm having some issue tracking down the animations. the closest I can find to anything like an animation are .anmsrc and .anmpk files, but they seem to not be what I'm looking for. Can anyone guide me in the right direction here? These are the only files I have found relating to characters that I have to work with and I'm not exactly sure what each do. I apologize for asking to have my hand held with this, but I'm having trouble finding documentation on how to use these files, or how this toolset interacts with some of them. Can anyone give me some tips or point me in the right direction? I would greatly appreciate it.
[Yuri_A files.PNG](https://xentaxbackup.github.io/file/21421_Yuri_A files.PNG)
## Post #326
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-19T18:47:07+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Psycoskel ↑Sun Dec 19, 2021 10:59 pm at Sun Dec 19, 2021 10:59 pm
>
> 
Hey, I'm trying to extract models and animations from Fatal Frame 5 and I've had no problem extracting and viewing the models + textures in Noesis of the characters in Fatal Frame 5, but I'm having some issue tracking down the animations. the closest I can find to anything like an animation are .anmsrc and .anmpk files, but they seem to not be what I'm looking for. Can anyone guide me in the right direction here? These are the only files I have found relating to characters that I have to work with and I'm not exactly sure what each do. I apologize for asking to have my hand held with this, but I'm having trouble finding documentation on how to use these files, or how this toolset interacts with some of them. Can anyone give me some tips or point me in the right direction? I would greatly appreciate it.

Try drag and dropping the .gmpk and .gapk on Cethleann.Unbundler
## Post #327
- Username: Psycoskel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 19, 2021 10:53 pm
- Post datetime: 2021-12-20T03:12:06+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Mon Dec 20, 2021 2:47 am at Mon Dec 20, 2021 2:47 am
>
> 
Try drag and dropping the .gmpk and .gapk on Cethleann.Unbundler

unbundling the gmpk is how I was able to access the models and textures, but if I unbundle the gapk it gives me a long list of files that end in a filetype of .00000 all the way up to .08002 and I'm not sure what I'm supposed to do with any of these. I appreciate the help.
[H_YRI files.PNG](https://xentaxbackup.github.io/file/21425_H_YRI files.PNG)
## Post #328
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-20T15:50:42+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Psycoskel ↑Mon Dec 20, 2021 11:12 am at Mon Dec 20, 2021 11:12 am
>
> 
Joschka wrote: ↑Mon Dec 20, 2021 2:47 am
Try drag and dropping the .gmpk and .gapk on Cethleann.Unbundler


unbundling the gmpk is how I was able to access the models and textures, but if I unbundle the gapk it gives me a long list of files that end in a filetype of .00000 all the way up to .08002 and I'm not sure what I'm supposed to do with any of these. I appreciate the help.

Can you send the gmpk and the gapk ? Going to take a look
## Post #329
- Username: Psycoskel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 19, 2021 10:53 pm
- Post datetime: 2021-12-21T06:06:27+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Mon Dec 20, 2021 11:50 pm at Mon Dec 20, 2021 11:50 pm
>
> 
Psycoskel wrote: ↑Mon Dec 20, 2021 11:12 am
Joschka wrote: ↑Mon Dec 20, 2021 2:47 am
Try drag and dropping the .gmpk and .gapk on Cethleann.Unbundler


unbundling the gmpk is how I was able to access the models and textures, but if I unbundle the gapk it gives me a long list of files that end in a filetype of .00000 all the way up to .08002 and I'm not sure what I'm supposed to do with any of these. I appreciate the help.


Can you send the gmpk and the gapk ? Going to take a look

Here's a mega link to the gmpk and gapk files for Yuri's default outfit. 
[https://mega.nz/file/Co1jSSbb#Ltg8etePH ... I3aw1RPeMc](https://mega.nz/file/Co1jSSbb#Ltg8etePHHQ8GUrnpguvcDKsY74gGJ0RoI3aw1RPeMc)
## Post #330
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-21T06:52:26+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Psycoskel ↑Tue Dec 21, 2021 2:06 pm at Tue Dec 21, 2021 2:06 pm
>
> 
Joschka wrote: ↑Mon Dec 20, 2021 11:50 pm
Psycoskel wrote: ↑Mon Dec 20, 2021 11:12 am


unbundling the gmpk is how I was able to access the models and textures, but if I unbundle the gapk it gives me a long list of files that end in a filetype of .00000 all the way up to .08002 and I'm not sure what I'm supposed to do with any of these. I appreciate the help.


Can you send the gmpk and the gapk ? Going to take a look


Here's a mega link to the gmpk and gapk files for Yuri's default outfit. 
https://mega.nz/file/Co1jSSbb#Ltg8etePH ... I3aw1RPeMc

Yeah they're valid anim files, simply batch rename them to .g1a (on windows just do ren * *.*.g1a) then you'll be able to load up the anims. 
To sum up :
-unbundle gapk, rename the files
-unbundle gmpk (the files will end up in the same folder, that's good so keep it that way)
-load whatever g1m in the folder and make sure the "merge all assets in the same folder" plugin option is ticked
## Post #331
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-12-21T06:58:57+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Psycoskel ↑Mon Dec 20, 2021 11:12 am at Mon Dec 20, 2021 11:12 am
>
> 
Joschka wrote: ↑Mon Dec 20, 2021 2:47 am
Try drag and dropping the .gmpk and .gapk on Cethleann.Unbundler


unbundling the gmpk is how I was able to access the models and textures, but if I unbundle the gapk it gives me a long list of files that end in a filetype of .00000 all the way up to .08002 and I'm not sure what I'm supposed to do with any of these. I appreciate the help.

those are the filenames present in the gapk, only way to fix it is to use the method Joschka stated
## Post #332
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-12-21T07:45:09+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

Hard to believe it has being 3 years and nobody has managed to unpack right or even play the .sed files of Dissidia NT (mostly voice data).
Being reading this:

[https://zenhax.com/viewtopic.php?t=8205](https://zenhax.com/viewtopic.php?t=8205)

But it just end on the same way as other pages pointed out: no way of play it. They even say in one that the .bms was write wrong and it is not compatible with the .sed NT has. Tested the steam version and I got only a small .hb and a big one .dat, both sharing what they say on the link to Zenhax.

I'm mostly curious about the data because they say it has voice lines that aren't in-game. Still wonder how they find it out as it is pretty impossible to unpack & play the voice data.
## Post #333
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-21T08:07:39+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Darkhowlings ↑Tue Dec 21, 2021 3:45 pm at Tue Dec 21, 2021 3:45 pm
>
> 
Hard to believe it has being 3 years and nobody has managed to unpack right or even play the .sed files of Dissidia NT (mostly voice data).
Being reading this:

https://zenhax.com/viewtopic.php?t=8205

But it just end on the same way as other pages pointed out: no way of play it. They even say in one that the .bms was write wrong and it is not compatible with the .sed NT has. Tested the steam version and I got only a small .hb and a big one .dat, both sharing what they say on the link to Zenhax.

I'm mostly curious about the data because they say it has voice lines that aren't in-game. Still wonder how they find it out as it is pretty impossible to unpack & play the voice data.

I tried to load these using foobar + vgmstream and it worked, unless I'm missing something ?
## Post #334
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-12-21T14:06:42+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Joschka ↑Tue Dec 21, 2021 4:07 pm at Tue Dec 21, 2021 4:07 pm
>
> 
I tried to load these using foobar + vgmstream and it worked, unless I'm missing something ?
I wonder how because I try to do it and they didn't load.
Unless the PC version have the data different compared too PS4 one
## Post #335
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-22T09:27:20+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Darkhowlings ↑Tue Dec 21, 2021 10:06 pm at Tue Dec 21, 2021 10:06 pm
>
> 
Joschka wrote: ↑Tue Dec 21, 2021 4:07 pm
I tried to load these using foobar + vgmstream and it worked, unless I'm missing something ?

I wonder how because I try to do it and they didn't load.
Unless the PC version have the data different compared too PS4 one

I tried the examples in the zenhax thread above, not sure about the PS4 ones but I wouldn't be surprised if they were different. The Dissidia NT PC demo on Steam has all the files anyways so you can grab it for free and check the data.
## Post #336
- Username: Psycoskel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 19, 2021 10:53 pm
- Post datetime: 2021-12-23T06:56:46+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Joschka ↑Tue Dec 21, 2021 2:52 pm at Tue Dec 21, 2021 2:52 pm
>
> 
Yeah they're valid anim files, simply batch rename them to .g1a (on windows just do ren * *.*.g1a) then you'll be able to load up the anims. 
To sum up :
-unbundle gapk, rename the files
-unbundle gmpk (the files will end up in the same folder, that's good so keep it that way)
-load whatever g1m in the folder and make sure the "merge all assets in the same folder" plugin option is ticked

Works perfectly. I'm very new to this so I appreciate all the generous help you gave, thank you very much for not only the help but these great tools as well.
## Post #337
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-23T13:21:23+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Psycoskel ↑Thu Dec 23, 2021 2:56 pm at Thu Dec 23, 2021 2:56 pm
>
> 
Joschka wrote: ↑Tue Dec 21, 2021 2:52 pm
Yeah they're valid anim files, simply batch rename them to .g1a (on windows just do ren * *.*.g1a) then you'll be able to load up the anims. 
To sum up :
-unbundle gapk, rename the files
-unbundle gmpk (the files will end up in the same folder, that's good so keep it that way)
-load whatever g1m in the folder and make sure the "merge all assets in the same folder" plugin option is ticked


Works perfectly. I'm very new to this so I appreciate all the generous help you gave, thank you very much for not only the help but these great tools as well.

You're welcome, glad you enjoy the tools.
## Post #338
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-12-23T21:25:10+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Joschka ↑Wed Dec 22, 2021 5:27 pm at Wed Dec 22, 2021 5:27 pm
>
> 
I tried the examples in the zenhax thread above, not sure about the PS4 ones but I wouldn't be surprised if they were different. The Dissidia NT PC demo on Steam has all the files anyways so you can grab it for free and check the data.

Thanks for pointing me on the right direction!

For anyone in the future wondering how open .sed files of Dissidia NT (at least Steam):

The .sed can be open & converted with Winamp.
It only needs the .dll vgmstream mentioned on they page for allowed Winamp to read others format, this includes .sed files.

No need to unpack the .sed, just drag & drop on Winamp after the .dll of vgmstream are placed on Winamp folder as vgmstream describe it.
## Post #339
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-12-25T05:56:48+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

Hello everyone, please help me how to extract Marvel Ultimate Alliance 3 animations
## Post #340
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-12-25T06:25:11+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

this is sample
[https://www.mediafire.com/file/7c1sbncp ... t.bin/file](https://www.mediafire.com/file/7c1sbncpgo2egi9/0000_AMERICA_mot.bin/file)
## Post #341
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2022-02-28T04:08:55+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

Does this tool work on Atelier Sophie 2's pak files?
## Post #342
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-02-28T23:42:40+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

the --reisalin-keyfix trick dun work on soph2 
wait for script update
## Post #343
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2022-03-14T07:11:40+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

> Reply from Atlus ↑Mon Feb 28, 2022 12:08 pm at Mon Feb 28, 2022 12:08 pm
>
> 
Does this tool work on Atelier Sophie 2's pak files?
try 'gust tools' work fine with pak
## Post #344
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2022-03-19T12:52:08+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

The file name of Touken Ranbu Musou is incorrect
Waiting for someone to create a file list
If you have the files you need, you can pass them
[2.png](https://xentaxbackup.github.io/file/21966_2.png)
## Post #345
- Username: Rookie201
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 18, 2019 1:19 pm
- Post datetime: 2022-03-23T20:20:16+00:00
- Post Title: Re: Extracting and viewing Fatal Frame/Project Zero 5 animation files

Can someone help me with extraction files for Stranger of Paradise Final Fantasy Origin?
Can't figure out how to properly do it
Thanks in advance
## Post #346
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2022-03-27T01:27:06+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello, I would like to know how to use these 3 downloaded files containing the Cethleann tools (Cethleann.zip, CethleannDebug.zip and CethleannStandalone.zip
would be first unzipping them in a single folder ?how do I use this?
how would the compilation be to extract the LINKDATA.BIN from the game attack on titan 2 final battle?
could you explain me step by step?
Are there video tutorials teaching how to use these tools?
## Post #347
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2022-03-28T23:47:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello Yretenai, I installed netcore on my pc, but before opening cmd to type the command line, I would like to know about these 3 folders that I downloaded: (Cethleann.zip, CethleannDebug.zip and CethleannStandalone.zip), how to organize?
1 Do I create a folder and unzip the 3 .zip files inside it?
2 Do I unzip only the file that has the necessary tool for a given file? How do I do this?
## Post #348
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2022-04-01T22:59:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hello andree, could you please tell me what I'm doing wrong in this procedure for extracting the files from the LINKDATA folder, from the game attack on titan 2 final battle?
I'm sending you a link so you can download the video I recorded from my pc screen using atube catcher


[https://drive.google.com/file/d/1XSZrb9 ... =drive_web](https://drive.google.com/file/d/1XSZrb9ZuyPYm13M3580IsxZJcuEJc-R7/view?usp=drive_web)
## Post #349
- Username: Gakken
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 06, 2021 10:47 am
- Post datetime: 2022-04-13T01:43:04+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I honestly have no idea what to do  I have a GIM file and I have Project GIM.dll I just have no idea how to do it exactly
## Post #350
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2022-04-19T18:35:55+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello, i want extract bin files from Stranger of Paradise Final Fantasy 0, How can i do ?
## Post #351
- Username: Sakahiro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 28, 2022 9:37 pm
- Post datetime: 2022-04-28T13:39:44+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi.

I'm interested in ripping FF0 SoP models too. I downloaded Cethleann along a plugin called "Project g1m", but I don't know how to install this plugin.

Also, I don't really know what I should run and in what folder, does anyone have a clue? I'm really new to the ripping scene, this is my first time ever, I opened a powershell in my cethleann folder and ran Unbundler, and DataExporter, but none of these worked. Unbundler does nothing, andDataExporter is loading filelists , then do nothing. Can I have some help please?

Regards
## Post #352
- Username: Rookie201
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 18, 2019 1:19 pm
- Post datetime: 2022-04-29T15:07:04+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Sakahiro ↑Thu Apr 28, 2022 9:39 pm at Thu Apr 28, 2022 9:39 pm
>
> 
Hi.

I'm interested in ripping FF0 SoP models too. I downloaded Cethleann along a plugin called "Project g1m", but I don't know how to install this plugin.

Also, I don't really know what I should run and in what folder, does anyone have a clue? I'm really new to the ripping scene, this is my first time ever, I opened a powershell in my cethleann folder and ran Unbundler, and DataExporter, but none of these worked. Unbundler does nothing, andDataExporter is loading filelists , then do nothing. Can I have some help please?

Regards

To rip the game files you need to open cmd in the folder where your Cethleann is located.
[https://www.thewindowsclub.com/how-to-o ... click-menu](https://www.thewindowsclub.com/how-to-open-command-prompt-from-right-click-menu)
Then you need to enter this command Cethleann.DataExporter.exe --rdb -g Scramble [Extraction Dir] [motor_package dir] 
For example:  Cethleann.DataExporter.exe --rdb -g Scramble H:\SOPFinalFantasyOrigin\unpacked H:\SOPFinalFantasyOrigin\motor_package
You need approximatley 150 gigs of free space to full rip the files.
Then
Project g1m is a script for a program called Noesis
[viewtopic.php?f=16&t=21666](https://forum.xentax.com/viewtopic.php?f=16&t=21666)
You can get it here 
[https://richwhitehouse.com/index.php?co ... ojects.php](https://richwhitehouse.com/index.php?content=inc_projects.php)
Well..that's all i know.Maybe there is more but i've used this method
Have fun:)
## Post #353
- Username: Sakahiro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 28, 2022 9:37 pm
- Post datetime: 2022-04-29T15:49:42+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Thank you very much for the info!
## Post #354
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2022-05-03T23:36:42+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello, i tried to recompile animation from stranger of paradise, if i'm right, i have to use Nyotengu.AnimationGraph, but i don't understand how it's supposed to work.
## Post #355
- Username: sakez
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 05, 2022 9:27 pm
- Post datetime: 2022-05-05T13:48:33+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hey, 
Would anyone happen to know where sound effects, voice lines and music are stored in Stranger of Paradise, 
also finding a way to extract them would be nice.
## Post #356
- Username: Rookie201
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 18, 2019 1:19 pm
- Post datetime: 2022-05-06T20:05:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from sakez ↑Thu May 05, 2022 9:48 pm at Thu May 05, 2022 9:48 pm
>
> 
Hey, 
Would anyone happen to know where sound effects, voice lines and music are stored in Stranger of Paradise, 
also finding a way to extract them would be nice.

Fortunately, i know where they are and how to extract them.
So they are located in RRPreview.In SRSA ans SRST folders
They can be extracted with foobar2000 with wgmstream plugin installed
For SRSA files you can use quickbms script:

get NAME basename
get SIZE asize
string NAME + ".ktsl2asbin"
set OFFSET 16
math SIZE - OFFSET
log NAME OFFSET SIZE

For SRST you can use this quickbms script: 

# Fairy Tail
# Extract KOVS audio files from SRST archives
# QuickBMS script by DKDave, 2021


Get TEMPNAME basename
Get FILE_END asize

Math A = 0
Math OFFSET = 0x50


For A
	If OFFSET = FILE_END
		Break
	Endif

	Goto OFFSET
	Get JUNK Long
	Get SIZE Long

	XMath OFFSET2 "OFFSET + 0x20"
	Goto OFFSET2
	Get JUNK Long
	Get SIZE2 Long

	String FILENAME P "%TEMPNAME%_%A%.kovs"
	Log FILENAME OFFSET2 SIZE2

	Math OFFSET + SIZE
Next A

You may find them here as well.
[viewtopic.php?p=176959#p176959](https://forum.xentax.com/viewtopic.php?p=176959#p176959)
[http://wiki.xentax.com/index.php/Koei_T ... _SRSA_SRST](http://wiki.xentax.com/index.php/Koei_Tecmo_Audio_SRSA_SRST)

So this pretty much it.
Enjoy 

(killing Chaos)
## Post #357
- Username: sakez
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 05, 2022 9:27 pm
- Post datetime: 2022-05-07T16:37:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Thank you so much and really appreciate the detailed instructions!
## Post #358
- Username: razzorj
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 07, 2022 11:34 pm
- Post datetime: 2022-05-07T16:53:24+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I am confused about how to export and preview the file with g1a extensions. It seems the neosis that I downloaded is unable to open this kind of extension. Am I missing some plugins or some other stuff?
## Post #359
- Username: Rookie201
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 18, 2019 1:19 pm
- Post datetime: 2022-05-07T21:38:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from sakez ↑Sun May 08, 2022 12:37 am at Sun May 08, 2022 12:37 am
>
> 
Thank you so much and really appreciate the detailed instructions!

You're welcome:)
## Post #360
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-08T19:25:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

So, I wanna ask about Pirate Warriors 4 files. After unpacking them using Cethleann Data exporter, I don't see any g1a folder files in Character Editor folder. 

Because of this, I am stuck in getting the model and animations for the characters. 

The cmd would be:

Nyotengu.AnimationGraph.exe -g OnePiece4 “D:\DOWNLOADED\Cethleann\KIDSSystemResource\kidsobjdb\CE1CommonResource.motor.kidsobjdb” “D:\DOWNLOADED\Cethleann\KIDSSystemResource\kidsobjdb\CE1CommonResource.motor.kidssingletondb” -o anims -d “E:\DOWNLOADED\Cethleann\New folder2\CharacterEditor\g1a” -d “D:\DOWNLOADED\Cethleann\FieldEditor4\g1a” -d “D:\DOWNLOADED\Cethleann\RRPreview\g1a” 162f0015"

The missing one is the g1a folder in character editor. Would anyone know how to get this? Thanks
## Post #361
- Username: dark9090
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 09, 2021 4:55 pm
- Post datetime: 2022-05-11T22:19:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Does anyone know if it is possible that when loading a g1m noesis somehow recognizes its g1t textures, I've been ordering textures all day, stranger of paradise XD
## Post #362
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-05-11T23:41:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from dark9090 ↑Thu May 12, 2022 6:19 am at Thu May 12, 2022 6:19 am
>
> ...anyone know if it is possible that when loading a g1m noesis somehow recognizes its g1t textures...
If all required assets are in the same folder, the textures will be loaded automatically.
Also this is the wrong thread to ask the question that is specific to the plugin in question, go to: viewtopic.php?f=16&t=21666
## Post #363
- Username: OMGCaprat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 04, 2022 4:10 am
- Post datetime: 2022-06-03T20:15:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Heyo, a little new to this! My goal is to extract the VA from DW8, and apply it in Warriors orochi 4 where applicable (battle grunts and generic lines, etc.) Would these tools be able to help me accomplish that? I'm fairly certain if I have a tool that can extract and repack the audio, I'm none too worried about replacing audio, but I'm in need of something that can get to and repack the linkdata the audio is in in the first place.
## Post #364
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-06-08T22:13:11+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I tried this with Fire Emblem Warriors Three Hopes demo to extract it's .fdata files and it gave me a error.
Here's what I inputted in.

```
Cethleann.DataExporter.exe --zhao --platform Switch *output folder* *Three Hopes folder* 
```


and this is what the error says.

```
   at System.Number.ThrowOverflowOrFormatException(ParsingStatus status, TypeCode type)
   at System.Number.ParseInt64(ReadOnlySpan`1 value, NumberStyles styles, NumberFormatInfo info)
   at System.Int64.Parse(String s, NumberStyles style)
   at Cethleann.Archive.RDB.DecodeOffset(String packed) in C:\projects\cethleann\Cethleann\Archive\RDB.cs:line 284
   at Cethleann.Archive.RDB..ctor(Span`1 buffer, String name, String directory) in C:\projects\cethleann\Cethleann\Archive\RDB.cs:line 63
   at Cethleann.ManagedFS.Nyotengu.AddDataFS(String path) in C:\projects\cethleann\Cethleann\ManagedFS\Nyotengu.cs:line 84
   at Cethleann.DataExporter.Program.Main(String[] args) in C:\projects\cethleann\Cethleann.DataExporter\Program.cs:line 50
```


I have access to the files from the game, I've provided several files [here](https://cdn.discordapp.com/attachments/493153242104987669/984222771297021962/FEWTH_Demo_files.zip), so if you want to test more of them, please dm me.
## Post #365
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2022-06-09T12:56:54+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I imagine the current scripts aren't updated for FEW:TH, either we are doing something wrong or we just need to wait.
## Post #366
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-06-09T13:22:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from ninetalescommander ↑Thu Jun 09, 2022 8:56 pm at Thu Jun 09, 2022 8:56 pm
>
> 
I imagine the current scripts aren't updated for FEW:TH, either we are doing something wrong or we just need to wait.

Yretenai updated it but it is WIP, so wait for it to be finalized.
## Post #367
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2022-06-10T08:06:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

At the latest update, has Yretenai ceased development?
I had high hopes for Fire Emblem Warriors: Three Hopes as well...
## Post #368
- Username: wahwahweewah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 09, 2022 9:47 am
- Post datetime: 2022-06-10T08:46:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from yham ↑Fri Jun 10, 2022 4:06 pm at Fri Jun 10, 2022 4:06 pm
>
> 
At the latest update, has Yretenai ceased development?
I had high hopes for Fire Emblem Warriors: Three Hopes as well...

You can extract the files with the latest update, however they will not be named. The command I got to work was

> Cethleann.DataExporter -P switch --rdb D:\fe\cethleann\hopeout D:\fe\dir\romfsa\File\CMN\Asset\FDataPackage\Trial

with hopeout being my out directory and \trial being a subdirectory of my extracted romfs.



It works mostly, however some textures are very swizzled/compressed in a strange way. (At least I hope it's that and they're not completely corrupted...)
## Post #369
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-10T09:08:59+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Just use Noesis to view the g1t files directly instead, everything works. [viewtopic.php?f=16&p=185143#p185143](https://forum.xentax.com/viewtopic.php?f=16&p=185143#p185143)

And yeah after working on these Koei archives for nearly two years Yretenai is taking a break to focus on other projects. Needless to say, a huge thanks for all the hard work done on all these tools, without having someone focusing on the archives/bundles I wouldn't have been able to add support for as many games to Project G1M.
## Post #370
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2022-06-10T10:13:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from wahwahweewah ↑Fri Jun 10, 2022 4:46 pm at Fri Jun 10, 2022 4:46 pm
>
> 
yham wrote: ↑Fri Jun 10, 2022 4:06 pm
At the latest update, has Yretenai ceased development?
I had high hopes for Fire Emblem Warriors: Three Hopes as well...


You can extract the files with the latest update, however they will not be named. The command I got to work was
Cethleann.DataExporter -P switch --rdb D:\fe\cethleann\hopeout D:\fe\dir\romfsa\File\CMN\Asset\FDataPackage\Trial

with hopeout being my out directory and \trial being a subdirectory of my extracted romfs.

It works mostly, however some textures are very swizzled/compressed in a strange way. (At least I hope it's that and they're not completely corrupted...)

Thanks for letting me know. It worked well. And thanks to the hard work of the developer.
As for the file name, LINKDATA is not sure about the file name either, so is there any way to resolve this?
## Post #371
- Username: Jacien
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 21, 2020 4:49 am
- Post datetime: 2022-06-10T10:24:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Some images swizzle for me too, and when I try to batch export with Noesis (it has Project G1M plugin), it'll reach certain images and just crash. For example

> BEGINNING JOB 0175 - F:\Fire Emblem Three Hopes\Output\root\g1t\0170fe53.g1t
>
> Detected file type: G1T File (Little Endian)
>
> WARNING: Invalid dimensions on DDS! (1324016369x-698799644)
>
> DXT-compressed files must be divisible by 4.Unsupported DDS format: -1.
>
> WARNING: Constructing default image because data could not be decoded.

I used Cethleann with that above command to extract all files out:

> Cethleann.DataExporter -P switch --rdb "PathOut" "PathTrial"

It takes a while to extract everything, is there a command so it only extracts .g1t?
## Post #372
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-10T11:01:57+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Jacien ↑Fri Jun 10, 2022 6:24 pm at Fri Jun 10, 2022 6:24 pm
>
> 
Some images swizzle for me too, and when I try to batch export with Noesis (it has Project G1M plugin), it'll reach certain images and just crash. For example
BEGINNING JOB 0175 - F:\Fire Emblem Three Hopes\Output\root\g1t\0170fe53.g1t
Detected file type: G1T File (Little Endian)
WARNING: Invalid dimensions on DDS! (1324016369x-698799644)
DXT-compressed files must be divisible by 4.Unsupported DDS format: -1.
WARNING: Constructing default image because data could not be decoded.

I used Cethleann with that above command to extract all files out:
Cethleann.DataExporter -P switch --rdb "PathOut" "PathTrial"

It takes a while to extract everything, is there a command so it only extracts .g1t?

Not sure about the batch export but previewing the one you're talking about individually works fine (3 texture container) 
Also these tiling issues are non existent with the plugin. And no you cannot extract g1t files only.
## Post #373
- Username: Jacien
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 21, 2020 4:49 am
- Post datetime: 2022-06-10T11:27:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Fri Jun 10, 2022 7:01 pm at Fri Jun 10, 2022 7:01 pm
>
> 
Jacien wrote: ↑Fri Jun 10, 2022 6:24 pm
Some images swizzle for me too, and when I try to batch export with Noesis (it has Project G1M plugin), it'll reach certain images and just crash. For example
BEGINNING JOB 0175 - F:\Fire Emblem Three Hopes\Output\root\g1t\0170fe53.g1t
Detected file type: G1T File (Little Endian)
WARNING: Invalid dimensions on DDS! (1324016369x-698799644)
DXT-compressed files must be divisible by 4.Unsupported DDS format: -1.
WARNING: Constructing default image because data could not be decoded.

I used Cethleann with that above command to extract all files out:
Cethleann.DataExporter -P switch --rdb "PathOut" "PathTrial"

It takes a while to extract everything, is there a command so it only extracts .g1t?


Not sure about the batch export but previewing the one you're talking about individually works fine (3 texture container) 
Also these tiling issues are non existent with the plugin. And no you cannot extract g1t files only.

Okay, then I wonder what I'm doing wrong with Cethleann or Noesis.

Here, I'll upload the file I just got from this run: [https://www.dropbox.com/s/3wc0m18erfsyz ... 3.g1t?dl=0](https://www.dropbox.com/s/3wc0m18erfsyzyw/0170fe53.g1t?dl=0)

I did the command:

> Cethleann.DataExporter --platform Switch --rdb "F:\Fire Emblem Three Hopes\Output" "F:\Fire Emblem Three Hopes\Fire Emblem Warriors_ Three Hopes Demo v0 (01006E6017792000) (BASE)\File\CMN\Asset\FDataPackage\Trial"

Does that work in your Noesis? If it does then I have something wrong with Noesis. If it doesn't work, then I'm doing the export wrong.
## Post #374
- Username: Ghosttoast
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 07, 2020 7:08 pm
- Post datetime: 2022-06-10T12:07:43+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is there a way to combine or find the three hopes G1T's for characters or is going through one by one the only option now?
## Post #375
- Username: Jacien
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 21, 2020 4:49 am
- Post datetime: 2022-06-10T20:58:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Jacien ↑Fri Jun 10, 2022 7:27 pm at Fri Jun 10, 2022 7:27 pm
>
> 
Joschka wrote: ↑Fri Jun 10, 2022 7:01 pm
Jacien wrote: ↑Fri Jun 10, 2022 6:24 pm
Some images swizzle for me too, and when I try to batch export with Noesis (it has Project G1M plugin), it'll reach certain images and just crash. For example



I used Cethleann with that above command to extract all files out:


It takes a while to extract everything, is there a command so it only extracts .g1t?


Not sure about the batch export but previewing the one you're talking about individually works fine (3 texture container) 
Also these tiling issues are non existent with the plugin. And no you cannot extract g1t files only.


Okay, then I wonder what I'm doing wrong with Cethleann or Noesis.

Here, I'll upload the file I just got from this run: https://www.dropbox.com/s/3wc0m18erfsyz ... 3.g1t?dl=0

I did the command:
Cethleann.DataExporter --platform Switch --rdb "F:\Fire Emblem Three Hopes\Output" "F:\Fire Emblem Three Hopes\Fire Emblem Warriors_ Three Hopes Demo v0 (01006E6017792000) (BASE)\File\CMN\Asset\FDataPackage\Trial"

Does that work in your Noesis? If it does then I have something wrong with Noesis. If it doesn't work, then I'm doing the export wrong.

Figured out my issue, it was the 1.2.1 build of Cethleann that wasn't extracting Three Hopes correctly. 1.2.0 worked and now when i look at it in Noesis, it's not scrambled



120Cethleann.jpg (122.6 KiB) Viewed 250 times

.
## Post #376
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-10T21:32:46+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Was away so couldn't try your sample earlier, it indeed crashes since most of you took the release that is specific to Persona Strikers on PC, which had encryption. As a result some of your files got corrupted. Make sure that you're extracting using 1.2.0 and everything will work as stated above by Jacien.

> Reply from Ghosttoast ↑Fri Jun 10, 2022 8:07 pm at Fri Jun 10, 2022 8:07 pm
>
> 
Is there a way to combine or find the three hopes G1T's for characters or is going through one by one the only option now?
[viewtopic.php?f=16&t=21666&start=450#p185167](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=450#p185167)
## Post #377
- Username: greg234
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 16, 2017 12:25 am
- Post datetime: 2022-06-26T05:39:54+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Does this work for the samurai warrior series of games? If so can someone give me the exact commands please? I'm sorry. Usually I try to figure things out my own and not bother others, but without a start guide, I'm just lost on what games this works on; And what precise command lines to use.
## Post #378
- Username: dmon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 22, 2022 5:45 am
- Post datetime: 2022-07-08T22:14:31+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I know from the repo that you've stopped development on the tool, but I'm having an issue with it that I'm sure isn't a toolwide bug - when I try to use the DataExporter for Three Houses files, the output stops after it states that it's loading the filelist for ThreeHouses-link and it gives me an open prompt like it's finished the process. I'm running it on Ubuntu under Wine, which might be the problem, but if there's something else that might be causing this then I'd like to figure it out.
## Post #379
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2022-07-10T01:39:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

The UV Maps are coming up broken on certain meshes like with this one. This is d37edda3 by the way.
## Post #380
- Username: BenXX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 16, 2019 10:32 pm
- Post datetime: 2022-07-12T23:30:10+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I've used Cethleann.Unbundler to export G1M files from a bin archive. 
Is there a way to also rebundle those G1M files back into a bin archive?
## Post #381
- Username: scarfhero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 20, 2022 3:59 am
- Post datetime: 2022-08-19T20:02:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

ive been trying to use this program however my pc says it cannot run it. anybody know the issue?
## Post #382
- Username: CarpetStain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 27, 2022 8:11 pm
- Post datetime: 2022-08-27T12:16:16+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, i'm new to all of this type of stuff so i'm sorry if this is a noobish question, i was trying to extract dqheros2 files and it has a simple "LINKDATA.BIN" archive but i don't know what cmd to use or how to export it from there to unbundle afterward, i've done this prior with dissida nt but i am unsure what to use with dqheroes 2. if anyone has any advice please let me know
## Post #383
- Username: ArchLeaders
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 22, 2022 11:35 am
- Post datetime: 2022-10-22T05:13:29+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello,

I recently started exploring extracting Age of Calamity game asset files (RDB) and came across an issue while using Cetheann.DataExporter .
For some reason the RDB and BIN files shown in the screenshot are skipped; there doesn't seem to be any error causing this (at least none thrown to the CLI), so I'm not really sure where to go from here. Has anyone had similar issues or know a solution?



EDIT: I'm just dumb. The rdb file was missing. I hadn't realized rdb.bin would not suffice.
## Post #384
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2022-10-25T03:08:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I've been trying to deduce the compression algorithm used for the Ninja Gaiden Master Collection, but have repeatedly struck out. The databin tells me nothing--at least nothing obvious--and though I've read up a bit on this suite of tools, how to employ them is just over my head at the moment. Is anyone able to help investigate this with me?
## Post #385
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-11-08T23:59:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi guys,

I am trying to extracted linkfile_n.bin of Warrior Orochi 3 Ultimate Definitive Edition PC ( there are several of them). My comand line was the following:


```
C:\Users\****\Downloads\Cethleann\Cethleann.DataExporter.exe --linkbin C:\Users\****\Desktop\here "C:\Games\WARRIORS OROCHI 3 Ultimate Definitive Edition" 
```


However after "[FileList] Loading filelist for unknown-archive" nothing happen. 

I also tried with --no-filelist but still nothing happen. Is there anyone that succeded in extracting the data ?
## Post #386
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2022-11-16T00:19:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Is there a way to repack/build an .rdb/.rdb.bin file with this (or any other tool)? Specifically trying to repack Stranger of Paradise .rdbs.
## Post #387
- Username: xieronis
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 20, 2021 11:43 pm
- Post datetime: 2022-11-25T21:27:34+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm really hoping someone can assist me. 
I've ripped everything from Nioh 2, but for the life of me I'm having a huge issue trying to get the textures at their correct sizes.
I ran the .g1t file through the nioh2 application provided in the FFSNT zip, the unbundler in Cethleann, **and** the deprecated fmt_g1m script and all of them provide either dds files that are unsupported on both Photoshop and Paint.NET, or are no larger than 125x125. Could someone tell me the process to properly extract the textures at their proper resolution?
## Post #388
- Username: Sakahiro
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 28, 2022 9:37 pm
- Post datetime: 2022-12-04T15:59:49+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Heyo,

Sorry for the bother but since I updated to W11 , Cethleann doesn't work anymore ( or at least, Unbundler.exe doesn't ).

I'm on winver 21H2 , and I installed net framework. so I don't know if this is a known issue or am I doing something wrong?

Kind regards
## Post #389
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2022-12-20T13:56:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from SonofUgly ↑Wed Nov 16, 2022 8:19 am at Wed Nov 16, 2022 8:19 am
>
> 
Is there a way to repack/build an .rdb/.rdb.bin file with this (or any other tool)? Specifically trying to repack Stranger of Paradise .rdbs.

hi SonofUgly, i recently tried to extract RRPreview.rdb contents and a bit confused now. by any chance do you know which files considered as BGM?

most of content i've converted to KOVS were character voices & cutscene dubbings
## Post #390
- Username: Buzzy1989
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 23, 2023 3:06 am
- Post datetime: 2023-01-22T19:09:53+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I am not the sharpest tool in the shed. can someone help me out exporting data from age of calamity? I don't know what commands I should type in. any help appreciated.
## Post #391
- Username: Zeee
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 21, 2020 8:15 am
- Post datetime: 2023-02-02T12:11:48+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Doesn't seem to work with OPPW4 DLC files, the unbundler can't detect the data type nor data blob
[Capture.PNG](https://xentaxbackup.github.io/file/23372_Capture.PNG)
## Post #392
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-10T04:35:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello, I'm editing the voice files of the game Samurai Warriors 4 II for PC. I will replace the Japanese voice to the Brazilian Portuguese voice.
I was able to extract the .BIN file using VGMToolbox.
I used Foobar2000 to convert .KOVS to .WAV

I don't know how to convert my .WAV/.OGG audio to .KOVS
Can someone help me?   

sample:
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1kxgrCT36spDexz1B4bkj83Xzf4ndYx_3?usp=share_link)

THX
## Post #393
- Username: xieronis
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 20, 2021 11:43 pm
- Post datetime: 2023-02-17T04:52:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Using Cethleann's Data Exporter to turn .fdata files into g1m files appears to have worked for Wild Hearts, but Noesis keeps crashing every time I try to view a g1m or g1t file, leaving me unsure if I've done something incorrectly. Any guidance?
## Post #394
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2023-02-17T16:44:00+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from xieronis ↑Fri Feb 17, 2023 12:52 pm at Fri Feb 17, 2023 12:52 pm
>
> 
Using Cethleann's Data Exporter to turn .fdata files into g1m files appears to have worked for Wild Hearts, but Noesis keeps crashing every time I try to view a g1m or g1t file, leaving me unsure if I've done something incorrectly. Any guidance?

Can you post a sample?
## Post #395
- Username: xieronis
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 20, 2021 11:43 pm
- Post datetime: 2023-02-17T19:12:35+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from hellacopters ↑Sat Feb 18, 2023 12:44 am at Sat Feb 18, 2023 12:44 am
>
> 
xieronis wrote: ↑Fri Feb 17, 2023 12:52 pm
Using Cethleann's Data Exporter to turn .fdata files into g1m files appears to have worked for Wild Hearts, but Noesis keeps crashing every time I try to view a g1m or g1t file, leaving me unsure if I've done something incorrectly. Any guidance?


Can you post a sample?
Here's a random g1m. 
[https://u.pcloud.link/publink/show?code ... LN4fJGgzBV](https://u.pcloud.link/publink/show?code=XZasDgVZK1N9iH2EcuBCzX8LKJLN4fJGgzBV)
## Post #396
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2023-02-17T19:54:40+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from xieronis ↑Sat Feb 18, 2023 3:12 am at Sat Feb 18, 2023 3:12 am
>
> 
hellacopters wrote: ↑Sat Feb 18, 2023 12:44 am
xieronis wrote: ↑Fri Feb 17, 2023 12:52 pm
Using Cethleann's Data Exporter to turn .fdata files into g1m files appears to have worked for Wild Hearts, but Noesis keeps crashing every time I try to view a g1m or g1t file, leaving me unsure if I've done something incorrectly. Any guidance?


Can you post a sample?

Here's a random g1m. 
https://u.pcloud.link/publink/show?code ... LN4fJGgzBV

Doesn't appear to have exported correctly. There is no header information.
[Screenshot 2023-02-17 145336.jpg](https://xentaxbackup.github.io/file/23418_Screenshot 2023-02-17 145336.jpg)
## Post #397
- Username: xieronis
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 20, 2021 11:43 pm
- Post datetime: 2023-02-17T21:11:53+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from hellacopters ↑Sat Feb 18, 2023 3:54 am at Sat Feb 18, 2023 3:54 am
>
> 
xieronis wrote: ↑Sat Feb 18, 2023 3:12 am
hellacopters wrote: ↑Sat Feb 18, 2023 12:44 am


Can you post a sample?

Here's a random g1m. 
https://u.pcloud.link/publink/show?code ... LN4fJGgzBV


Doesn't appear to have exported correctly. There is no header information.

Any guidance on this? I attempted to use the Data.Exporter command (slightly adjusted) used for FE3H throughout this thread. 

```
Cethleann.DataExporter -P Windows --rdb  C:\ExportPath C:\PathofFilestoExport
```


Which then started a huge chain of load logs and produced those files. Some errors did occur. All of which read as follows:

 System.ArgumentOutOfRangeException: Non-negative number required. (Parameter 'value')
   at System.IO.FileStream.set_Position(Int64 value)
   at Cethleann.Archive.RDX.ReadEntry(Int32 index) in D:\a\Cethleann\Cethleann\Cethleann\Archive\RDX.cs:line 82
   at Cethleann.Archive.RDB.ReadEntry(Int32 index) in D:\a\Cethleann\Cethleann\Cethleann\Archive\RDB.cs:line 276
   at Cethleann.ManagedFS.Nyotengu.ReadEntry(Int32 index) in D:\a\Cethleann\Cethleann\Cethleann\ManagedFS\Nyotengu.cs:line 70
   at Cethleann.DataExporter.Program.Main(String[] args) in D:\a\Cethleann\Cethleann\Cethleann.DataExporter\Program.cs:line 99
## Post #398
- Username: tatsumaki02
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 12, 2021 5:06 am
- Post datetime: 2023-02-22T07:30:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from EcosEstudio ↑Fri Feb 10, 2023 12:35 pm at Fri Feb 10, 2023 12:35 pm
>
> 
Hello, I'm editing the voice files of the game Samurai Warriors 4 II for PC. I will replace the Japanese voice to the Brazilian Portuguese voice.
I was able to extract the .BIN file using VGMToolbox.
I used Foobar2000 to convert .KOVS to .WAV

I don't know how to convert my .WAV/.OGG audio to .KOVS
Can someone help me?   

sample:
https://drive.google.com/drive/folders/ ... share_link

THX

Hello, can you tell step by steps on how you was able to extract the voices? i tried using VGMToolbox on Samurai Warriors Spirit of Sanada, but can't get the program to add the "VOICE.BIN". 
I think this game has same file/folder structure as SW4-II. And is it through "Iso/Archive Extractor" you put the VOICE.bin? cause everytime i click n drag the file to the program, nothing happens.
## Post #399
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-24T06:55:41+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from tatsumaki02 ↑Wed Feb 22, 2023 3:30 pm at Wed Feb 22, 2023 3:30 pm
>
> 
Hello, can you tell step by steps on how you was able to extract the voices? i tried using VGMToolbox on Samurai Warriors Spirit of Sanada, but can't get the program to add the "VOICE.BIN". 
I think this game has same file/folder structure as SW4-II. And is it through "Iso/Archive Extractor" you put the VOICE.bin? cause everytime i click n drag the file to the program, nothing happens.

Hello my friend!
[https://imgur.com/AZ8WPmS](https://imgur.com/AZ8WPmS)
In VGMTollbox use the option: Advanced Cutter/Offset;
[https://imgur.com/aUkDPc9](https://imgur.com/aUkDPc9)
In "Search String" write: 4B4F5653 - which is "kovs" in hexadecimal;
In "Output File Extension" type: .kovs;
Click the "Use Terminator String" box. And then write: 4B4F5653;
Check the "Treat as Hex" box;
Take your file and drop it into the program;
It will create a folder in the same place as the file.
Hope it works 

This program converts .KOVS to .OGG (.KOVS or .KVS file is the same)
[https://mega.nz/file/n3BRCLQa#kG8Uh1hjo ... aLY-PLiEn8](https://mega.nz/file/n3BRCLQa#kG8Uh1hjodicLiVCwJI17UgK8Vx4U4u2qaLY-PLiEn8)

If you want to listen to the .KOVS files, install the foobar2000 program and download the vgmstream plug-in "foo_input_vgmstream.fb2k-component". It's easy to find on Google.
## Post #400
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-02-24T19:24:24+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Zeee ↑Thu Feb 02, 2023 8:11 pm at Thu Feb 02, 2023 8:11 pm
>
> 
Doesn't seem to work with OPPW4 DLC files, the unbundler can't detect the data type nor data blob

it also doesnt seem to be working with the demo of Wo Long
## Post #401
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2023-03-02T03:10:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from liquer ↑Mon Jun 28, 2021 10:30 pm at Mon Jun 28, 2021 10:30 pm
>
> 
Hi everyone, as you may know, samurai warriors 5 has been released. So I tried to extract its switch version with --nyotengu. I definitely got some g1m and g1t files, just as P5S. I mean it also has rdb files and linkdata files at the same time. I recognized a few characters' g1m files such as nobunaga and mitsuhide.
But I met some troubles when I tried to find textures. I got that rdb file system has a series of g1t files so it need ktid to assemble. But I don't know how to analyze the different ktid files. So can anyone give some tutorial or tips? If I make a list I will be glad to share it.

update: completely resolved. Thanks to Nyogentu.KTID!

Hello, I also have the folders g1m, g1t, and ktid now, but noesisv can only look at the model and has no textures. Can you share the specific steps of using Nyogentu.KTID in samurai warriors 5?
thank you very much
## Post #402
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2023-03-03T04:21:10+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Joschka ↑Sun Jun 13, 2021 1:06 pm at Sun Jun 13, 2021 1:06 pm
>
> 
Mukojin wrote: ↑Sun Jun 13, 2021 4:06 am
Hi, when I open doa6 hair in noesis the hair seems to not have any weights. is there a way to fix that?


No, hair is simulated at runtime and doesn't have classic weights.
Joee99 wrote: ↑Sun Jun 13, 2021 4:25 am
Joschka wrote: ↑Sat Jun 12, 2021 11:40 pm


Hmm, who told you that ? It's working fine, they didn't change anything


Sorry, I should have clarified, the file names are all hexadecimal. I'd like to be able export the files with the actual file names or restore them, so I can see which textures are used with which models.


You don't need filenames to reconstruct textures. Actually just grab this list, it'll be easier for you. 
AoCThingy.zip
Take your g1mHash and read the associated textureID and resource name.
For ex Impa is f23c0538, you get a2cf3043 and CharacterEditor.kidssingletondb from the list. She comes from CharacterEditor\g1m so you type :
Code: Select allNyotengu.KTID.exe ..\AocExtract\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb ..\AocExtract\MaterialEditor\g1t ..\AocExtract\CharacterEditor\ktid\a2cf3043.ktid
It'll parse and reconstruct the correct g1t and will output it in the same folder as the ktid (so characterEditor\ktid here)
Then you can just open it in Noesis on your model

I've parsed and rebuilt the correct g1t and outputted it in the same folder as ktid
But when I browse g1m in Noesis, I don't see the textrue display.
May I ask how to get the AoCThingy table so that g1m and g1t can correspond?
## Post #403
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-03-03T18:47:47+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello there!

I tried using Cethleann to extract Wo Long Fallen Dynasty, with the following syntax

 Cethleann.DataExporter -P Windows --rdb  C:\ExportPath C:\PathofFilestoExport 

I was able to do so but the resulting .g1m files are not readable in Noesis nor can they be extracted using the Cethleann.Unbundler. By trying that I get the following argument but nothing else.

I:\WORKING ON\Wo Long\New folder\CharacterEditor\g1m\New folder>"I:\WORKING ON\Tools\cethleann-net7-win-x86-64-rel\Cethleann.Unbundler.exe" "I:\WORKING ON\Wo Long\New folder\CharacterEditor\g1m\New folder\00b5cb62.g1m"
[2023-03-03T18:45:26][Cethleann] Cethleann.Unbundler v1.0.0.0
[2023-03-03T18:45:26][Cethleann] Arguments: ["I:\\WORKING ON\\Wo Long\\New folder\\CharacterEditor\\g1m\\New folder\\00b5cb62.g1m"]
[2023-03-03T18:45:26][Cethleann] Extracting 00b5cb62.g1m...

I:\WORKING ON\Wo Long\New folder\CharacterEditor\g1m\New folder>

Here is the g1m I attempted to extract:
[https://disk.yandex.com/d/R3Fia2u44sZoCA](https://disk.yandex.com/d/R3Fia2u44sZoCA)
## Post #404
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-03-03T22:36:56+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from AzothRaven ↑Sat Mar 04, 2023 2:47 am at Sat Mar 04, 2023 2:47 am
>
> 
...

Use the fdata.bms script at the bottom of this link [viewtopic.php?t=21666&start=465](https://forum.xentax.com/viewtopic.php?t=21666&start=465)
Do mind, many g1m (especially the ones from the Character files) will make noesis crash.
## Post #405
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-03-03T23:27:42+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Allanoon ↑Sat Mar 04, 2023 6:36 am at Sat Mar 04, 2023 6:36 am
>
> 
AzothRaven wrote: ↑Sat Mar 04, 2023 2:47 am
...


Use the fdata.bms script at the bottom of this link viewtopic.php?t=21666&start=465
Do mind, many g1m (especially the ones from the Character files) will make noesis crash.

Hi!
Thanks for the help,

Just tried to do so but quickBMS gives me this error:

by Luigi Auriemma
e-mail: [me@aluigi.org](mailto:me@aluigi.org)
web:    aluigi.org
        (Aug 24 2022 - 10:50:22)

                          quickbms.com  Homepage
                            zenhax.com  ZenHAX Forum
                     @zenhax @quickbms  Twitter & Scripts

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select BMS script. type ? for using the content of clipboard like a script
- select input archives/files, type * for the whole folder and subfolders
- select output folder where extracting files
- open input file I:\WORKING ON\Wo Long\CharacterEditor.rdb
- open script I:\WORKING ON\Wo Long\quickbms\fdata.bms
- set output folder I:\WORKING ON\Wo Long\New folder (2)

  offset           filesize   filename
--------------------------------------
16

Error: [myfseek] offset 0xcfcfcfff16221cef in file 0 can't be reached

Last script line before the error or that produced the error:
  20  Goto SKIP 0 SEEK_CUR
  coverage file 0     0%   44         1408756    . offset 0000000000010010

Press ENTER or close the window to quit

Did I do something wrong?
## Post #406
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-03-03T23:42:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

use it on the large files only (*.rdb.bin)
## Post #407
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-03-04T00:26:24+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from GDL ↑Sat Mar 04, 2023 7:42 am at Sat Mar 04, 2023 7:42 am
>
> 
use it on the large files only (*.rdb.bin)

Worked perfectly!!!
Its a pain in the ass that the meshes and textures are hashed but if you use the Cethleann.Unbundler you can extract the g1m that Noesis cannot see:

[https://ibb.co/GpRFbfx](https://ibb.co/GpRFbfx)
## Post #408
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-03-04T07:25:56+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from AzothRaven ↑Sat Mar 04, 2023 7:27 am at Sat Mar 04, 2023 7:27 am
>
> 
...

IF i'm not wrong... you're trying to open CharacterEditor.rdb while you should use it on CharacterEditor.rdb.bin (the big one)

Edit: Eh, i had the notification of your quote on the other page, didn't notice someone had already answered  

Edit2: 

> Reply from AzothRaven ↑Sat Mar 04, 2023 8:26 am at Sat Mar 04, 2023 8:26 am
>
> 
Worked perfectly!!!
Its a pain in the ass that the meshes and textures are hashed but if you use the Cethleann.Unbundler you can extract the g1m that Noesis cannot see:

https://ibb.co/GpRFbfx

That's interesting! But how does it work exactly? I see that dropping the file into the unbundler is not enough
## Post #409
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-03-05T00:36:35+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Allanoon ↑Sat Mar 04, 2023 3:25 pm at Sat Mar 04, 2023 3:25 pm
>
> 
AzothRaven wrote: ↑Sat Mar 04, 2023 7:27 am
...


IF i'm not wrong... you're trying to open CharacterEditor.rdb while you should use it on CharacterEditor.rdb.bin (the big one)

Edit: Eh, i had the notification of your quote on the other page, didn't notice someone had already answered  

Edit2: 
AzothRaven wrote: ↑Sat Mar 04, 2023 8:26 am
Worked perfectly!!!
Its a pain in the ass that the meshes and textures are hashed but if you use the Cethleann.Unbundler you can extract the g1m that Noesis cannot see:

https://ibb.co/GpRFbfx


That's interesting! But how does it work exactly? I see that dropping the file into the unbundler is not enough

The nio2.exe from this post can turn all the g1m files into ascii+smd files (mesh+bones)

[viewtopic.php?p=140154#p140154](https://forum.xentax.com/viewtopic.php?p=140154#p140154)
## Post #410
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-03-05T18:26:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

The message above is completely right, my g1m files were pointing towards the nioh2.exe that Daemon1 made for the game and that is how it extract them to ascii. It has sense, I have checked various hair models and they are the exact same as in Nioh2
## Post #411
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2023-03-06T01:05:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello, Wo Long Fallen Dynastie seems to have the same structure as Stranger of Paradise, but Nyotengu.Database, Nyotengu.KTID and Nyotengu.AnimationGraph doesn't work and like the post above said, the g1m files cannot be opened with noesis.
## Post #412
- Username: Lasaga
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 05, 2023 3:15 am
- Post datetime: 2023-03-09T03:10:43+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hello! I have been working on extracting what I can of the Wild Hearts files, and after getting all the .fdata files into a manageable state where I can play the sfx and view the models within, I am stumped on opening the .rdb, .file (which is similar to p5s .files with the IDRK0000), and the .arc files. Any suggestions would be welcome, I am very new to this sort of thing and realizing that I may have bitten off more than I can chew.

Here is a sample of the files I am messing with [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1MDcr6T_4cxcFH97RDtNghL0du9KzF4Gz?usp=sharing)
## Post #413
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2023-03-09T20:05:43+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Wo Long Fallen Dynasty model error


Desktop 3-9-2023 11-28-53 PM-946.png (90.19 KiB) Viewed 553 times
## Post #414
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-03-09T20:19:20+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Cethleann still works with the latest "FATAL FRAME / PROJECT ZERO: Mask of the Lunar Eclipse" files released today:



ffmol.jpg (121.12 KiB) Viewed 553 times
## Post #415
- Username: Ethan88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 10, 2023 7:46 am
- Post datetime: 2023-03-10T17:11:03+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from GDL ↑Fri Mar 10, 2023 4:19 am at Fri Mar 10, 2023 4:19 am
>
> 
Cethleann still works with the latest "FATAL FRAME / PROJECT ZERO: Mask of the Lunar Eclipse" files released today:

ffmol.jpg

neat where would I put cathleann into? Edit, NVM got it
## Post #416
- Username: Razzoriel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 20, 2016 5:51 am
- Post datetime: 2023-03-22T18:42:36+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I'm trying to find out a tool that can detect and extract ALL of Dynasty Warriors 8's weapons. So far I tried extracting with Steven's Gas and it exports flawlessly, but for some reason skips the final weapon upgrades with all three DW8 titles; DW8 (understandable; wasn't around), DW8: XL (should be there) and DW8:Empires (Also should be there)

For my understanding it extracts all models and bundles them in order. It seems the last weapons are not in the same bundle as the normal weapons, for some reasons, and after days searching for them, could not find jack. Not sure now if its a tool issue or me not doing something right. Can anyone confirm if its possible to extract the Xtreme Legends variations? Examples: Radiant Flash Spear (final Spear weapon) and Double Demon Flash (final Double Voulge weapon).
## Post #417
- Username: RedipsTheCooler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 20, 2022 12:28 am
- Post datetime: 2023-03-23T19:29:30+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from Century300 ↑Mon Nov 09, 2020 11:37 am at Mon Nov 09, 2020 11:37 am
>
> 
I'm trying to get model specific animations from Persona 5 Scramble but I don't know how. I know that I hate to use Nyotengu.AnimationGraph but the program only works with dead or alive 6 hashes. I saw on the thread that the KTID from WolrdPQ can be used as the hash in the program but I don't know where or how to find that value. Can anyone help me?

Does anyone have an answer to this? I need this information to rip P5S animations.
## Post #418
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2023-03-24T06:33:45+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

please update for ryza 3
## Post #419
- Username: AetherSomerset
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 19, 2023 6:28 pm
- Post datetime: 2023-04-19T10:49:09+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hey, I'm super new here. Would anyone be able to advise me on how to extract text data from Three Hopes? I managed to successfully use the DataExporter to extract all the files after following some advice from earlier in this thread but what I ended up with was like thirty folders with names like grp, ktid and texinfo with files inside that have matching extensions, and I'm completely lost on what to do with all that.

I tried googling some of the extensions but the only match I found was for animation and model data which isn't what I'm looking for. Any help would be super appreciated!
## Post #420
- Username: Relyt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 22, 2021 4:43 pm
- Post datetime: 2023-04-21T17:53:51+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

i got almost 5000 g1a animation files in aot1 by putting all the ptrbundle files into Cethleann.Unbundler.exe,but when I do the same in aot2 I only get 200 g1a animation files.am i doing something wrong?i really want the animation files from aot2.
## Post #421
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-05-31T13:54:08+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

hi guys, im newbie here. i tried to learn how to extract wo long 3d models. I downloaded Cethleann, but i cant get it to run. whenever i click on Cethleann.Unbundler, it wont run on my PC. Any helps would be much appreciate. Thanks a lot
## Post #422
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2023-07-11T02:49:32+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hate to bump, but I'm a little lost in understanding how to use cethleann to extract files. I have Samurai Warriors ripped to an ISO and I want to extract the FMV's and some sound files from the game. Extracting the contents of the ISO looks like this:

MODULES

SAMWAR.IRX
IOPRP300.IMG
MODULE.BIN

DUMMY.DAT
LINKDATA.ANS
LINKDATA.BNS
LINKDATA.CNS
LINKDATA.DNS
SLUS_208.78
SYSTEM.CNF


I came across cethleann but there's so many executables included in the release and there's no documentation on how to use any of them. Can anyone guide me on what to do here do get the video and sound files out?
## Post #423
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-07-11T06:12:18+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I don't think Cethleann supports PS2 era Omega Force titles.
Also, the problem is Omega Force sometimes changes the way how the archives are stored with every of their games during that time.
Sometimes the TOC (Table of Contents) are inside the LINKDATAs, sometimes it was hardcoded into the game executables (SLUS/SLES/SLPM)
Table of contents contains stuff like offset address and size for each files inside the archive (and sometimes filenames if you're lucky).

Last time I've checked SW1's LINKDATA TOC's was hardcoded.
## Post #424
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2023-07-14T03:43:28+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I don't want to derail from the actual thread topic, but do you know of any resources for extracting assets out of the older PS2 Omega Force games? I did find some posts on Zenhax but it seems to be down and may not come back.
## Post #425
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-07-14T04:47:22+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Info for older Omega Force titles are pretty scarce unfortunately even when ZenHAX was still around AFAIK.

But that doesn't mean the extractor couldn't be made. Should be possible with a QuickBMS script.
AFAIR the TOC structure is pretty simple (for SW1 and possibly older the only hurdle is the TOC for each LINKDATAs are scattered inside the executables).
## Post #426
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2023-07-14T18:08:02+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

There is a script for QuickBMS on the site named [Sengoku Musou / SAMURAI WARRIORS](http://aluigi.zenhax.com/bms/sengoku_musou.bms) but it doesn't work on any of previously mentioned extracted files (the script doesn't really say how to even use it / what files to use this on)

There's also one for Dynasty Warriors 4 that looks for an IDX file and a BIN file with the same name, but this also doesn't seem to successfully grab anything.

Trying to scan the archive files with the comtype2 BMS script but I'm not sure if it'll actually give any useful information the files
## Post #427
- Username: KristalWolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 19, 2023 6:04 am
- Post datetime: 2023-08-18T22:12:19+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hiya~
Dunno if this or the Noesis discussion are the right places, and I dunno if this forum discussion is still alive but I need to ask; How does one go about getting the One Piece Pirate Warriors 4 PC files ready to be ready to be accessed and extracted?

So far I've tried using Cethleann.DataExporter with --rdb and --nyotengu and got close enough where I can find the right models, but it doesn't seem to get all the character textures (.g1t) or character animations (.g1a), and after hopping around most of the 29 pages of discussion I'm at a loss.

Any help would be appreciated, thanks~
## Post #428
- Username: zaay
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 16, 2023 10:30 pm
- Post datetime: 2023-09-16T14:32:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

how do i use this every time i open the Cethleann.Unbundler it just closes can someone please help?
## Post #429
- Username: jiku
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 18, 2023 5:25 pm
- Post datetime: 2023-09-18T09:32:23+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

Hi, I'm trying to extract SW4-II PC models but I don't know how. I've tried the unbundler and nyotengu ktid no luck
## Post #430
- Username: MRSBeaTheLow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 02, 2023 7:56 pm
- Post datetime: 2023-10-02T12:05:01+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

> Reply from KristalWolf ↑Sat Aug 19, 2023 6:12 am at Sat Aug 19, 2023 6:12 am
>
> 

How do you even extract the game files ? What is the command prompt i have to use and is it working for the actual new DLC (Onigashima pack)?
## Post #431
- Username: crist0393
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 31, 2018 1:54 am
- Post datetime: 2023-10-18T22:47:13+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

I'm trying to extract the models from DOAXVV but I have this. Am I doing something wrong?
## Post #432
- Username: kuzon1
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 08, 2018 4:23 pm
- Post datetime: 2023-10-19T12:53:17+00:00
- Post Title: Re: Cethleann - The Koei Swiss Army Knife

about AOT2 models .\Cethleann.DataExporter.exe -g AttackOnTitan2 --linkarchive "X:\games\AOT\LINKDATA\Extract" "X:\games\AOT\LINKDATA" command work, but maybe you will need Unpack each file separately, placing them in the queue one by one, to avoid an error. For example leave only the file LINKDATA_EU_A.BIN in AOT\LINKDATA" folder if you have an overflow error
