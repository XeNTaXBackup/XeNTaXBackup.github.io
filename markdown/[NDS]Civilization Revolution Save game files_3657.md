## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-21T20:28:25+00:00
- Post Title: [NDS]Civilization Revolution Save game files

I've got trouble figuring out the complete format of the Nintendo DS savegame files. There seems to be some kind of compression or CRC going on. Parts start with 90 XX and then actual values that make sense, but this is not consistent. If I alter those parts that make sense, the game detects corruption, which means the files are checksummed or crc-ed somehow. The files start with a size parameter.  

Somebody dealt with this type of compression/saving before?


 civsaves.zip
(13.87 KiB) Downloaded 62 times



Here's the whole Sav file that stores 5 savegames.


 Sid_Meiers_Civ.zip
(70.87 KiB) Downloaded 52 times
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-29T12:44:41+00:00
- Post Title: [NDS]Civilization Revolution Save game files

OK, I think I've located the CRC/Hash. 

The save games are stored the .sav file, of course. And the .sav start off with the magic word "RCMS". At 0x14 is the first checksum, of 4 bytes long, followed by the second etc. up to 5 savegames. The first savegame starts at 0x800, the second at 0xd000, the third at 19800 etc (each savegame has 0xc800 of bytes reserved for it). 

Savegames start with an unsigned 32-bit integer that is the whole size of the savegame. 

At 0x11 in the savegame there is also an unsigned 32-bit integer that I do not know the meaning of. I've attached a number of savegame files, first an empty one, then one right after the game initialized (so no actual games were saved) and finally one with three savegames: The first and second savegame are the same, except for slot and time. They are identical except for the unsigned 32-bit value I just spoke off. The third savegame is one where only one action different from the other savegames was done (a city founded with the first settler).


 clean_savegames.zip
(10.78 KiB) Downloaded 36 times



Luckily I found a plugin for IDA Pro 5.x that you can copy to IDA's loader folder. 


 nds_loader_idapro5.zip
(23.04 KiB) Downloaded 42 times



By having that you can open .nds files (rom files, e.g. games). 

Perhaps that will help in figuring out the hash/checksum/crc method used to check for savegame-corruption used in the game.
