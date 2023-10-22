## Post #1
- Username: ifrit05
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 06, 2015 10:10 am
- Post datetime: 2018-02-02T18:30:17+00:00
- Post Title: FFXII .vbf format

Anyone mind looking into the .vbf format Final Fantasy XII: The Zodiac Age (Steam) uses for it's data? None of the tools for .vbf's from FFX|X-2 work.

Thanks!
## Post #2
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-04T12:39:33+00:00
- Post Title: FFXII .vbf format

Actually, the vbftool1.1 by tek547 works just fine. It's slow (unpacking and repacking on a single HDD takes like 2.5 hours, it's much faster with two separate drives or SSD). It's fully functional for now, though. I'm working right now on my own tool that can reinsert files muuuch faster. Will update you once it's ready.

[viewtopic.php?f=10&t=14340&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=14340&start=15)
## Post #3
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2018-02-06T23:03:07+00:00
- Post Title: FFXII .vbf format

I was also looking for a different solution, though the old tool works, it takes quite some time. I'd love to see what you can come up with ffgriever. If you update on it, would it be on the forums here or elsewhere?
## Post #4
- Username: Tohru Adachi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 07, 2018 7:06 am
- Post datetime: 2018-02-06T23:13:31+00:00
- Post Title: FFXII .vbf format

I Have Looked in It. on Steam to learn what we know right Now [https://steamcommunity.com/linkfilter/? ... 21&t=17648](https://steamcommunity.com/linkfilter/?url=http://forum.xentax.com/viewtopic.php?f=21&t=17648) a LIcense Board Editor Mod has been Made, and i am Researching the Character Model Files to see if i can Play as Unplayable Characters. Join The Modding Discussion on that Page. And Also, and someone open some of the game's character Phyre Files? Because i don't know how to do it.
## Post #5
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-12T01:42:32+00:00
- Post Title: FFXII .vbf format

As promised, a tool to quickly insert changed files into FF12 vbf archive. Please note it's still WORK IN PROGRESS. Keep a copy of your original file, just in case.

So what's the problem? Repacking 30GB archive can take even two hours (eg. with both unpacked directory and vbf on the same HDD).

With this tool it takes a few seconds at most (though it depends on number of files and their size).

The general idea of vbf:
1. All files are compressed (with uncompressed chunks whenever compression wasn't viable).
2. Static sections written one after another (header, md5s, file data, names, block data, compressed files).
3. If a file is modified and compressed, few issues are possible:
   a). the original file is the same size, the compressed file is of a greater size.
   b). the original file is of a greater size.

In case of a) there is a problem, because the file doesn't fit into space available. My solution is to move the file to the end of VBF archive, leave the original space unused.
In case of b) there is a problem, because the file has more blocks (64kB each block), so the block data is larger, yet doesn't fit into space available. My solution is to move few first files in archive to the end of VBF archive to make some room for all the additional header data (trying to free at least 10MB but have to always move whole files).

Now, the file data contains sizes and offsets, but in case a modified file compresses to a smaller size, we don't know anymore, what was the original space available (you can't subtract offsets of two consecutive files, as these do not have to be placed one after another). So let's say the next time the file after additional modifications is slightly larger but sill would fit within original boundaries. But since we don't know what the boundaries were, the file would be relocated to the end anyway.

To solve that, I've added additional file to the VBF archive, that keeps track of original offsets and sizes, so such an issue won't happen (the files when relocating, are getting some additional padding, so further alleviate the issue). If VBF doesn't contain this "vbf_extra.bin" file, it will be automatically created. If it exists, it will be read and used during reinsertions. This extra file is uncompressed to make it easier to read/modify.

Basically, only headers are recalculated each time. Only files present in patch directory are compressed and inserted.

```

Usage: ff12-vbf option input output

Options:
        -r              replace files in output vbf with files in input dir
                        (output defaults to {input}.bin)
        -u              unpack vbf into output dir
                        (output defaults to {input}_dir)
```


As you see it lacks "creation" mode (full repack). I will add that later for completion sake, but I'm actually trying to avoid the hassle of rebuilding whole archive - that's the whole point of the tool, to save time .

Typical output (first time, creating vbf_extra.bin):

```
Reading file structure...
Reading directory structure
gamedata/d3d11/artdata/font/us/fontex_subtitle.dds.phyre (5546.47kB)
ps2data/plan_master/us/plan_map/naf_a/naf_a01/global/naf_a01.ebp (50.62kB)
Creating indexes
vbf_extra.bin not found. Creating and moving files around.
Freed 172803635 bytes, vbf_extra.bin written at 0x74d4e1e9e
Patching gamedata/d3d11/artdata/font/us/fontex_subtitle.dds.phyre
Not enough space, file has been relocated to 74d661e9e...
Patching ps2data/plan_master/us/plan_map/naf_a/naf_a01/global/naf_a01.ebp
Not enough space, file has been relocated to 74d68d4ea...
Done!
```


Typical output (consecutive times): 

```
Reading file structure...
Reading directory structure
gamedata/d3d11/artdata/font/us/fontex_subtitle.dds.phyre (5546.47kB)
ps2data/plan_master/us/plan_map/naf_a/naf_a01/global/naf_a01.ebp (50.62kB)
Creating indexes
Patching gamedata/d3d11/artdata/font/us/fontex_subtitle.dds.phyre
Patching ps2data/plan_master/us/plan_map/naf_a/naf_a01/global/naf_a01.ebp
Done!
```


In my case the structure of "pliki_gotowe" was:

```
│   └───d3d11
│       └───artdata
│           └───font
│               └───us
│                       fontex_subtitle.dds.phyre
│
└───ps2data
    └───plan_master
        └───us
            └───plan_map
                └───naf_a
                    └───naf_a01
                        └───global
                                naf_a01.ebp

```


Basically, all the files you want to insert, all in appropriate directories. The insertion took less than three seconds instead of 50 minutes.

Here is the link: [http://ff12.pl/down/ff12-tools-20180212.7z](http://ff12.pl/down/ff12-tools-20180212.7z)

Let me know if you find any bugs.
## Post #6
- Username: Rhaes
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Sep 09, 2016 12:19 pm
- Post datetime: 2018-02-12T02:10:53+00:00
- Post Title: FFXII .vbf format

Holy cow ffbriever! Thank you! I'm going to test it now with one of the license board mods the Steam community created and tell you how it went! 

By the way, [they are keeping an eye out on this thread as well apparently](http://steamcommunity.com/app/595520/discussions/0/1700541698690214622/?ctp=22)! Thank you for creating the tool for the community, we appreciate it man!
## Post #7
- Username: Tohru Adachi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 07, 2018 7:06 am
- Post datetime: 2018-02-12T02:26:27+00:00
- Post Title: FFXII .vbf format

Great Work ffGriever!
## Post #8
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2018-02-12T04:02:32+00:00
- Post Title: FFXII .vbf format

Great work, is it possible to make a version for FFX HD ?
## Post #9
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-12T08:00:10+00:00
- Post Title: FFXII .vbf format

> Reply from Beyond69
>
> Great work, is it possible to make a version for FFX HD ?
If the file format is the same, it should work. And since FFX tools work just fine with FFXII, I'd say just give it a try.
## Post #10
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2018-02-12T16:22:47+00:00
- Post Title: FFXII .vbf format

Works for FFX as well thank you
## Post #11
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-03-03T10:08:08+00:00
- Post Title: FFXII .vbf format

A quick find that I made when working on a Polish translation. The files are properly inserted into the VBF, but if the size of a file is greater, you also have to modify an appropriate entry in FileSizeTable_US.fst (or any other of these if necessary). Otherwise, depending on situation, the excess memory used might be overwritten by another file or the game will stop loading file at block boundary. It's actually very surprising so many modifications DO work without changing sizes (pure luck, I guess).
## Post #12
- Username: josecarlosdomingos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 03, 2016 7:57 pm
- Post datetime: 2018-03-11T01:28:41+00:00
- Post Title: FFXII .vbf format

> Reply from ffgriever
>
> A quick find that I made when working on a Polish translation. The files are properly inserted into the VBF, but if the size of a file is greater, you also have to modify an appropriate entry in FileSizeTable_US.fst (or any other of these if necessary). Otherwise, depending on situation, the excess memory used might be overwritten by another file or the game will stop loading file at block boundary. It's actually very surprising so many modifications DO work without changing sizes (pure luck, I guess).

I need help with FileSizeTable_US.fst
## Post #13
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-04-10T13:56:18+00:00
- Post Title: FFXII .vbf format

I've seen you've already coped with "FileSizeTable_US.fst". Just for future reference then.

The file consists of sections. Each section is 20000 bytes long and contains 32bit elements. In theory each section contains 5000 entries, but in reality most wrappers (there is a bunch of them) of the "getSize(file, section)" function will return -1 for file number greater than 4096.

A value of -1 for an element says that the file is not present/not used (if needed, game will try to read it from other languages that are considered higher level: eg. if a file is not present in "es" spanish dir, it will search in "us" dir, then in either "in" or "jp", etc.).

Most files are in pretty much the same order they were on PS2. Files within one directory are (most of the time) close together, but folders that are close together, many times aren't close in the table. Here is and example (file;offset)

```
ps2data/plan_master/us/event/byu_a/byu_a0400/byu_a0400.ebp;0x28200
ps2data/plan_master/us/event/byu_a/byu_a0480/byu_a0480.ebp;0x29d10
ps2data/plan_master/us/event/byu_a/byu_a0481/byu_a0481.ebp;0x29e50
ps2data/plan_master/us/event/byu_a/byu_a1880/byu_a1880.ebp;0x28190
```


Still, it's consistent with the PS2 order (there were no files, there wasn't even a munge/bigfile, just raw sectors on DVD and a raw sector table that links file numbers to sector locations and sizes).

AFAICT, many file size requests are hardcoded (with both file number and section number directly in code), but some are read from other tables.

I've attached a list of all the files I had to change for Polish translation of the game (I'm pretty sure everything is translated, I omitted offsets for bitmaps and other gfx files, as their size doesn't change unless you change the resolution, which I didn't do).
[sizeOffsets.zip](https://xentaxbackup.github.io/file/14192_sizeOffsets.zip)
## Post #14
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2018-04-10T16:23:03+00:00
- Post Title: FFXII .vbf format

@ ffgriever, shift all the data +10mb, re-write the entire toc.  This makes space for more entries in the compressed chunks table.  Then you can inject any file to the end regardless of it being larger than the original file.  It only takes a one time re-write of the archive.  After that all injects are instant and you don't have to worry about the file size or if it has more 64kb chunks than the original.
## Post #15
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-04-10T17:25:32+00:00
- Post Title: FFXII .vbf format

> Reply from EcheloCross
>
> @ ffgriever, shift all the data +10mb, re-write the entire toc.  This makes space for more entries in the compressed chunks table.  Then you can inject any file to the end regardless of it being larger than the original file.  It only takes a one time re-write of the archive.  After that all injects are instant and you don't have to worry about the file size or if it has more 64kb chunks than the original.
Shifting all the data by 10MB would mean shifting 30GB+ of data... That could take over 10 minutes on a typical HDD, so it's a big no.

It still does something similar. It just moves few first files (relocates these to the end) to free at least a given amount of space at the beginning (no need to move entire file). In an unmodified vbf it will move few small files and one movie. The other relocations are done only for the particular files that won't fit into original space. The tables are rebuilt each time anyway and there is plenty of space for the TOC.

In my case (over 1000 files, most of which are larger than original so they have to be relocated) the difference between first run (including freeing up the space for new toc and moving over 100MB of data, as you cannot move files partially and the movie that's near the beginning is over 100MB) and each consecutive run on a HDD is 10 vs 7 seconds. On SSD it's CPU bound and it's pretty much the same in both cases on a solid rig.

The whole point was to not move entire 30GB file 

As for tracking the space usage. If you just keep adding everything at the end, soon you will end up with 30GB file growing to 100GB. In my case it's ~400MB per try/test for all the files. And I've done it probably over a hundred times while modifying and testing. Unless you restore 30GB backup each time... Which takes A LOT of time.
## Post #16
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2018-04-10T23:58:17+00:00
- Post Title: Re: FFXII .vbf format

Yeah, it does take some time when moving the 30gb the first time.  After that its smooth sailing though.  I don't see why your method would have issues with the files that contain more 64kb chunks though.  If you move just the first few files to the end, it gives plenty of space to re-write the compressed chunk sizes so your method should be good.  I was only suggesting to move the 30gb because you mentioned that files that when modded contain more 64kb chunks than the original may cause an issue.
## Post #17
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-04-11T07:11:30+00:00
- Post Title: Re: FFXII .vbf format

> Reply from EcheloCross
>
> Yeah, it does take some time when moving the 30gb the first time.  After that its smooth sailing though.  I don't see why your method would have issues with the files that contain more 64kb chunks though.  If you move just the first few files to the end, it gives plenty of space to re-write the compressed chunk sizes so your method should be good.  I was only suggesting to move the 30gb because you mentioned that files that when modded contain more 64kb chunks than the original may cause an issue.
Ah, ok. Now I get it. You were just trying to solve a problem that doesn't exist. Sorry, I probably wasn't clear enough. The tool works perfectly and as intended. There is no problem with rebuilding the TOC nor anything I know about. It's been tested quite thoroughly and only problem I know about was someone trying to modify vbf archive in program files directory without admin privileges (which obviously failed).

I wasn't updating it because it was all I actually needed to complete the task I had.

There is one problem that might occur, though - if a user completely rebuilds the archive with another tool and doesn't remove the vbf_extra.bin file, there will be a mismatch between offsets and sizes in the extra file and real files, so that could cause some issues - the check is done by offset, so it's still very unlikely to cause issues. I could make a check for such a scenario, but it's very unlikely to happen, tbh.

I wasn't describing the problem I had, rather explaining the solution to a problem, things I've done to make it work. You see, I'm that kind of person that you'd rather not ask for a technical advice. I will give you a solution, but then I'll feel obliged to teach you how to get to that solution yourself, then how to solve any similar problems... and probably how solving a problem works at all. After half an hour you're wondering why won't he shut the F. up, because you don't actually need to know how to solve the problem, you just need a solution.

TL;DR;
Thank you and sorry, it was just a misunderstanding.
## Post #18
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2019-05-17T19:51:19+00:00
- Post Title: Re: FFXII .vbf format

Just to get the PC version on par with the tool I made for nintendo switch.

[https://ff12.pl/down/ff12-vbf-20190517.7z](https://ff12.pl/down/ff12-vbf-20190517.7z)

```

Usage: ff12-vbf option input output

Options:
        -c              creates output vbf from files in input dir
                        (output defaults to {input}.vbf)
        -a              replace or add new files in output vbf with files in input dir
                        (output defaults to {input}.vbf)
        -i=pattern      semicolon separated list of patterns to ignore
                        (defaults to: "*/desktop.ini; */thumbs.db;")
        -r              replace files in output vbf with files in input dir
                        (output defaults to {input}.vbf)
        -u              unpack vbf into output dir
                        (output defaults to {input}_dir)
```


So since the last version:
- minor fixes
- option to create a new archive
- option to both replace already existing and add new files to an archive
- option to define a pattern for files that have to be ignored during creation/adding
- I've also made the compression multithreaded. It operates on blocks within one file, so on files smaller than block size (64kB) you won't see any dfference and the best speed will be achieved on files greater in size than "number of cores/threads" x "block size". With some intermediate buffers it could work for smaller files, but I don't think it's really worth it, considering, that people usually just replace small amounts of files, so it wouldn't save more than a few seconds. Anyway, compressing back all 50GB of game files takes now ~4 minutes on my machine instead of 25-30, so it quite a nice time saver (not that I compress the archive very often, only for testing, there is a reason I made the replacement tool).
- I significantly decreased file i/o operation count, so it should work a little bit faster with HDDs.

Also, I've changed compiler from gcc to ms vcc, so instead of the previous dlls, it needs vc++ redist, but most people already have it installed.

For more info regarding usage and reasons for some workarounds see post on the first page: [https://forum.xentax.com/viewtopic.php? ... 48#p137847](https://forum.xentax.com/viewtopic.php?f=21&t=17648#p137847)
