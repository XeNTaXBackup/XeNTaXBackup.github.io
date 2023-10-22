## Post #1
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2018-10-02T07:47:36+00:00
- Post Title: Help me to extract FPK from Battle Stadium D.O.N game

Greetings to everyone!

I so needed someone who could help me to extract FPK from Battle Stadium D.O.N game.

Here is FPK file that I tried to extract: [https://www.dropbox.com/s/zrokx2j0zz490 ... 3.fpk?dl=0](https://www.dropbox.com/s/zrokx2j0zz4909a/blank_3.fpk?dl=0)

I tried to use [QuickBMS script by Chroxx](http://forum.xentax.com/viewtopic.php?p=29853#p29853), but has received the following error:

```
--------------------------------------
  00000000d0030000 2953314304 chr/ace/2000.seq

Error: incomplete input file 0: G:\MODDING\Battle Stadium DON\FULL_AFS_FILE_DUMP
\blank_3.fpk
       Can't read 524288 bytes from offset 00000000d0030000.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0     0%   64         38800      . offset 00000000d0030000

Last script line before the error or that produced the error:
  14  log NAME OFFSET ZSIZE

Press ENTER or close the window to quit
```

I tried to use [FPK extractor.exe by Chroxx](http://forum.xentax.com/viewtopic.php?p=30390#p30390), but has received the following error:

```
offset: d0030000 flen: b0080000 lenght: 00230000 file: chr/ace/2000.seq
offset: 800c0000 flen: 7c150000 lenght: 801d0000 file: chr/ace/2000_ps2.txd
```

I tried to use [TvC-VAS FPK tool by RupertAvery](https://gbatemp.net/threads/tvc-fpk-tool.207232/), but has received the following error:

```
offset: d0030000 flen: b0080000 lenght: 00230000 file: chr/ace/2000.seq
Can't open output file */chr/ace/2000.seq !
offset: 800c0000 flen: 7c150000 lenght: 801d0000 file: chr/ace/2000_ps2.txd
```

I will be exceedingly grateful and happy if anybody of you is able to help me. Maybe someone have working FPK extractor or someone can make new one.

PS: Please forgive me for bad English, it is not my first language.
## Post #2
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-10-02T13:08:47+00:00
- Post Title: Help me to extract FPK from Battle Stadium D.O.N game

You can use noesis to unpack fpk files.
## Post #3
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2018-10-02T14:38:44+00:00
- Post Title: Help me to extract FPK from Battle Stadium D.O.N game

> Reply from killercracker
>
> You can use noesis to unpack fpk files.
Thank you so much for hint!!!

Now I successfully extracted all files from FPK archives and converted all .txd files to .tga with [TXD Viewer (PS2)](http://www.steve-m.com/downloads/tools/txdviewer/). 

By the way, can someone tell me how to convert .dff to enable me to import model into 3ds Max? 
[Renderware Importer by Chroxx](http://forum.xentax.com/viewtopic.php?p=50401#p50401) not worked for me.
## Post #4
- Username: xianyi233
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 21, 2022 5:28 pm
- Post datetime: 2023-03-04T03:33:54+00:00
- Post Title: Help me to extract FPK from Battle Stadium D.O.N game

You can use GN to decompress and package FPK files

[https://github.com/NicholasMoser/GNTool/](https://github.com/NicholasMoser/GNTool/)

You can use GTASA's export import script to Blender and edit the Dff model (I have tried to import and export successfully without any errors)

[https://github.com/Parik27/DragonFF](https://github.com/Parik27/DragonFF)

Txd texture You can use "magictxd" to import and export them

DragonFF is only valid for NGC platform, PS2 can use "Game utility“
