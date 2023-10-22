## Post #1
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2022-12-14T11:56:50+00:00
- Post Title: RockSmith+ .sdfdata files

Does anyone know working tools to extract .sdfdata from RockSmith+?

Sample files: [https://anonfiles.com/L9R96dM6y8/data_zip](https://anonfiles.com/L9R96dM6y8/data_zip)
## Post #2
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2023-01-25T12:22:10+00:00
- Post Title: RockSmith+ .sdfdata files

I found the QuickBMS script from [https://wiki.xentax.com/index.php/Snowd ... ATA_SDFTOC](https://wiki.xentax.com/index.php/Snowdrop_SDFDATA_SDFTOC) but it's not working, even Rocksmith+ is listed in the Wiki. Who is the author of this script?

```
--------------------------------------
- enter in folder F:\Games\Rocksmith+\ibex\sdf\pc\data
  coverage file 0     0%   0          152081428  . offset 00000000
- open input file F:\Games\Rocksmith+\ibex\sdf\pc\data\sdf.sdftoc

Error: incomplete input file 0: F:\Games\Rocksmith+\ibex\sdf\pc\data\sdf.sdftoc
       Can't read 388815 bytes from offset 0005a7ec.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0     0%   68         370668     . offset 0005a7ec

Last script line before the error or that produced the error:
  31  clog MEMORY_FILE OFFSET INFO_ZSIZE INFO_SIZE

- OFFSET       0x0005a7bc
- ZSIZE        0x00000000
- SIZE         0x0005eeff
  coverage file 0     0%   68         370668     . offset 0005a7ec

Press ENTER or close the window to quit
```
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-25T18:22:50+00:00
- Post Title: RockSmith+ .sdfdata files

It's script written by aluigi [memberlist.php?mode=viewprofile&u=889](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=889)
