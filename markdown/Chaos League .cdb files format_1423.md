## Post #1
- Username: VirtualSoldier
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 02, 2005 2:26 am
- Post datetime: 2005-08-01T18:54:53+00:00
- Post Title: Chaos League .cdb files format?

Game: Chaos League ([http://www.chaosleaguegame.com/](http://www.chaosleaguegame.com/))
Developer: Cyanide Studio ([http://www.cyanide-studio.com/](http://www.cyanide-studio.com/))

I need description of .cdb files format or tool to unpack (decode) these files. Files used as databases to store game and save data.

<GameDir>\database\database.cdb
<GameDir>\database\local.cdb
<GameDir>\savegame\championship\*.cdb
<GameDir>\savegame\exportedteam\*.cdb
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-01T21:25:24+00:00
- Post Title: Chaos League .cdb files format?

You can attach small CDB file ?
## Post #3
- Username: VirtualSoldier
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 02, 2005 2:26 am
- Post datetime: 2005-08-03T03:31:57+00:00
- Post Title: Chaos League .cdb files format?

There is one uncompressed file <GameDir>\Database\local.cdb,
all other files (.cdb, .rpl) - possibly compressed (or encrypted).

I've found information:
Main executable file: ChaosLeague.exe (Size: 4075520 bytes)
Offset: 0309EBDh...0309EE4h
Text: "unzip 0.15 Copyright 1998 Gilles Vollant"

If the game use zip compression - in which files?

Files in the game:
.anm, .spl - animation
.csv - match export
.bsp - maps
.dds, .tga, .tif - textures, graphics
.def - fonts definition
.dff - models
.msh - mesh
.ogg, .wav - sound
.cdb, .rpl - game data, saves and replays
[ChaosLeague.zip](https://xentaxbackup.github.io/file/396_ChaosLeague.zip)
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-03T15:24:01+00:00
- Post Title: Chaos League .cdb files format?

In file Local.cdb files without expansion are packed
## Post #5
- Username: sigzegv
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 23, 2008 6:31 pm
- Post datetime: 2008-01-23T20:05:43+00:00
- Post Title: Chaos League .cdb files format?

Hello

I just read this ( old ) post, and I am interested in founding a way to decode team files structure.

A team file have PK bits set in the header. But I didn't manage to unpack the file. I seems to be slightly modified.

Could somebody take a look a the team file in the attechment given by VirtualSoldier ? ( in ExportedTeam folder )
## Post #6
- Username: sigzegv
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 23, 2008 6:31 pm
- Post datetime: 2008-01-24T09:02:17+00:00
- Post Title: Chaos League .cdb files format?

here is the archive .cdb I try to extract. It is not the same a VirtualSoldierbut it is valid in the game... It seems to be a modified PKzip...
[teamfile.zip](https://xentaxbackup.github.io/file/1431_teamfile.zip)
## Post #7
- Username: sigzegv
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 23, 2008 6:31 pm
- Post datetime: 2008-01-28T12:42:38+00:00
- Post Title: Chaos League .cdb files format?

I have found how to read a cdb team file ( thanks to florian for helping ).

First , the 12 first bytes must be removed, compressed stream begins at 13th byte.

After that, I use zlib's uncompress function ( in C, and gzuncompress with PHP ) to decompress all.

[Here is my sample code.](http://xblasters.free.fr/ztoon/cdbtest/testcdb.cpp)

All should be readable, parsing the data may be trivial.
## Post #8
- Username: sigzegv
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 23, 2008 6:31 pm
- Post datetime: 2008-02-01T22:15:22+00:00
- Post Title: Chaos League .cdb files format?

I just forgot to tell the signification of the header, the twelve first bytes.

Bytes 1 to 4 are always FFFF FFFF
Bytes 5 to 8 is uncompressed file size.
Bytes 9 to 12 is compressed file size.
## Post #9
- Username: lordsomar999
- Rank: Banned
- Number of posts: 3
- Joined date: Wed Apr 13, 2011 10:04 pm
- Post datetime: 2011-04-13T14:27:43+00:00
- Post Title: Chaos League .cdb files format?

so what does a newb like me have to do to make my database readable? (just wanna change what for skills units can learn and their stats)
