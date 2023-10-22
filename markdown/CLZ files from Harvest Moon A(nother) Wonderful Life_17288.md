## Post #1
- Username: seangibbz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 14, 2017 4:28 am
- Post datetime: 2017-11-13T21:02:20+00:00
- Post Title: CLZ files from Harvest Moon: A(nother) Wonderful Life

I've been working on a mod for some old gamecube games, Harvest Moon: A Wonderful Life and Harvest Moon:
 Another Wonderful Life.

However, I've hit into a wall as I can't seem to figure out the CLZ file format that seems to contain a large number of the game's data.

From what I've been able to figure out, they appear to be single-file compressed archives.

In some cases, the developers have managed to get around the single-file limitation by archiving multiple game files into a single U8 archive (*.arc file) and then compressing that (creating a *.arc.clz file).



The file seems to consist of the following:
The CLZ header at 0x00000000 (43 4C 5A)
Some variable at 0x00000005 (in this case, 53 54 90)
The same variable also at 0x0000000d (in this case, 53 54 90)
The compressed data starting at 0x00000011 (in this case, a U8 archive, noted by the U8 header 55 AA 38 2D)

The files are also present in the PS2 version of the game Harvest Moon: A Wonderful Life - Special Edition.
Moreover, the PS2 version seems to contain both a compressed and uncompressed version of one of the files (mainchapter0.arc and mainchapter0.arc.clz). Although, I won't be able to fully confirm that they are the same until I get the clz version decompressed to compare the contents.



What advice could you guys give on decompressing these CLZ files?

I've started making a QuickBMS script to detect the file header, but I'm unsure of how to proceed.  Most of the tutorials I've found all go over how to extract multi-file archives (with different offsets and filenames), as opposed to single compressed files (with only one output filename and always the same offset).

```
idstring "CLZ\x00"      //CLZ file identifier

get unknownVar1 long    //Unknown variable
get null long           //Blank space
get unknownVar2 long    //Repeat of unknown variable
get null byte           //More blank space

/* Compressed file contents start now */
//log compressed contents to other file
```
## Post #2
- Username: seangibbz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 14, 2017 4:28 am
- Post datetime: 2019-01-07T07:36:26+00:00
- Post Title: CLZ files from Harvest Moon: A(nother) Wonderful Life

Additional notes:
- The files use big endian encoding
- The compressed archives only contain one file (e.g. commonall.arc.clz would be a compressed version of commonall.arc)

I've tried testing file decompression using [comtype_scan2](https://aluigi.altervista.org/quickbms/comtype_scan.htm), but have thus far been unsuccessful in finding a suitable match.

I've tried analyzing the [game's main executable (dol file)](https://mega.nz/#!VRVGWYyb!ri-5USvMpW3YhYwLywZxVf4Qi_xOP3TrSsdFgbXSiv0) and found that the loading of certain clz files [seems to be linked to a SceneInit function](https://zenhax.com/viewtopic.php?f=9&t=8874#p41708).

I've also managed to [decompile the executable](https://github.com/sgibbz/A-nother-Proud-Life/blob/master/Executable%20Decompilation/AWL_Start/Python/AWL_Start.py) into human-readable (sort of) python format.
