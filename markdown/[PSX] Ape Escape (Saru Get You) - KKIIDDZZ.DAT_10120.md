## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-02-08T00:38:00+00:00
- Post Title: [PSX] Ape Escape (Saru Get You) - KKIIDDZZ.DAT

Hello. I need help with unpacking and repacking archive KKIIDDZZ.DAT in this game. Can someone look at this files and create quick bms script or tool/unpacker? Please 

This game has these files/folders:

DEMO folder - there are many files with *.str extension (movies in psx games)
MINIGAME folder - many files with *.BIN extension and few files with *.GRD and *.EXE extension
STR folder - sounds and possibly movies
KKIIDDZZ.BNS - I'm not sure
KKIIDDZZ.DAT - archive or just container with data
KKIIDDZZ.HED - small file with header or something like that
SCUS_944.23 / SYSTEM.CNF - default psx files, not very important

I think that textures, models, texts and scripts are compressed in this KKIIDDZZ.DAT file, so it is very important for me to extract and import them to this file 

I also uploaded cutted files (KKIIDDZZ.BNS / KKIIDDZZ.DAT / KKIIDDZZ.HED) for analysis to this post. Download below.
[Ape Escape PSX - files for analysis.zip](https://xentaxbackup.github.io/file/6173_Ape Escape PSX - files for analysis.zip)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-03-22T18:00:26+00:00
- Post Title: [PSX] Ape Escape (Saru Get You) - KKIIDDZZ.DAT

Gold Digger!!!
I was taking a look about this game with a friend, he want do localization

So, i managed to extract the files without the filenames, but better than nothing...   

```
# Ape Escape - PSX (.HED/DAT)
# Version 0.1b

open FDSE "KKIIDDZZ.HED"
open FDSE "KKIIDDZZ.DAT" 1
Get however long

do
    get offset short
    get size short
    math offset * 0x800
    math size * 0x80
    log "" offset size 1
while offset != 0 
```
