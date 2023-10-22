## Post #1
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-10-16T05:02:32+00:00
- Post Title: Zone 66 compression format

Hi all,

I've seen a few references to Zone 66 but nobody seems to have worked out the compression algorithm applied to most of the game's files.  I'm new to XeNTaX and unfortunately the wiki seems to be down so I am unsure if anyone here has worked out how to decompress its files.

So, does anyone know if the Zone 66 decompression algorithm is documented anywhere?  If not I think I might be able to provide a compressed and decompressed version of the same file if anyone is familiar enough with compression algorithms to take a look.

Thanks!
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-10-16T13:23:22+00:00
- Post Title: Zone 66 compression format

try to attach what you said
## Post #3
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-10-17T05:15:22+00:00
- Post Title: Zone 66 compression format

Okay, [here's a zip file](http://www.shikadi.net/files/zone66_compression.zip) with four files in it.

"orig.z66" is the original file from the game, it is a compressed version of a standard VGA palette (768 bytes.)  All I know about the format is that the first four bytes store a 32-bit integer containing the decompressed file size (0x00000300 here, because the palette is 0x300 bytes long once decompressed.)

I have obtained the decompressed version by taking a screenshot during the game and extracting the palette, and writing it out in the same file format.  This is "orig.pal" in the zip.

To confirm I got the correct file, I changed a byte in orig.z66, this is "tweaked.z66".

After playing the game one of the colours had changed (black became dark purple), so captured the palette in the same way as before to create "tweaked.pal".  Between "orig.pal" and "tweaked.pal" the first palette entry (first three bytes) has changed from black to dark purple, so this suggests everything is as it seems.

The only caveat is that because the .png screenshots store values from 0-255 and palette files only use 0-63, I had to transform the values.  I have seen some games use values 0-64, in which case each byte in "orig.pal" and "tweaked.pal" *might* be 3-4 values larger than it should be.  Unfortunately I do not know a way around this, other than modifying DOSBox to capture the values the game sends to the VGA registers.

Please let me know if you're able to work anything out!

EDIT: Here's a couple more tweaks in case they're useful: (first line is the original data)

```
00 00 40 00 05 40 10  ->  00 00 00  00 00 2A  00 2A 00  00 2A 2A
30 00 40 00 05 40 10  ->  20 00 20  00 00 2A  00 2A 00  00 2A 2A
10 00 40 00 05 40 10  ->  20 00 20  00 00 2A  00 2A 00  00 2A 2A
11 00 40 00 05 40 10  ->  22 00 22  00 00 2A  00 2A 00  00 2A 2A
00 11 40 00 05 40 10  ->  00 22 00  22 00 2A  00 2A 00  00 2A 2A
20 00 40 00 05 40 10  ->  no effect
40 00 40 00 05 40 10  ->  no effect
00 00 41 00 05 40 10  ->  00 00 28  00 00 00  00 00 2A  00 2A 00 [extra three bytes inserted at start]
00 00 20 00 05 40 10  ->  00 00 00  00 2A ...  [only four 00 at start]
00 00 10 00 05 40 10  ->  00 00 00  00 2A ... [only four 00 at start]
00 00 80 00 05 40 10  ->  00 00 00  00 2A ...  [only four 00 at start]
00 00 50 00 05 40 10  ->  00 00 00  00 00 00  00 00 09  31 00 2A
00 00 60 00 05 40 10  ->  crash
00 00 42 00 05 40 10  ->  freeze

```
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-10-23T23:02:23+00:00
- Post Title: Zone 66 compression format

There were discussions done here before and the game data was decompressed:

[viewtopic.php?f=10&t=2475](http://forum.xentax.com/viewtopic.php?f=10&t=2475)

[viewtopic.php?f=13&t=2595](http://forum.xentax.com/viewtopic.php?f=13&t=2595)

[viewtopic.php?f=21&t=2593](http://forum.xentax.com/viewtopic.php?f=21&t=2593)

Unfortunately, no working tools came from it.

Also, music is, I believe, IMF.
## Post #5
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-10-24T06:49:38+00:00
- Post Title: Zone 66 compression format

Thanks for the pointers.  I sent john_doe a PM to ask about the details, as I was unable to get an LZW algorithm to decompress the data.  I tried big/little endian byte order, a varying number of reserved codewords and even starting at codeword lengths other than nine bits, but nothing.  And yes I did remove the four-byte length from the front of the file first (although to be sure I also tried all of the above only removing two bytes.)  Alas, I was unable to produce any valid data.

Re the music format it is unlikely to be IMF (if you mean IMF as in id Software Music Format) as the game was released by id's competitor Epic.  The fact that each song includes both sampled instruments (ala MOD) and OPL instruments (ala IMF) means it is probably a custom format (although I believe S3M may also be capable of this.)  However the game was developed by the Renaissance group, who also created the [CDFM tracker format](http://www.oldskool.org/demos/explained/demo_misc.html) which was capable of both digitised and OPL playback in the same song.  I would be willing to bet this is the format they used for Zone 66.
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-10-25T18:03:32+00:00
- Post Title: Zone 66 compression format

Oh, right, sorry. I mean the music uses OPL as people were able to make DROs of the ingame music using DOsBOX's built-in raw OPL recorder. I've been wanting to deal with the music myself as well if I wanted to... per example have a new level that has custom music.

john_doe was going to give me a source code of his work regarding Z66 files but he disappeared soon after leaving me not being of much use here and without a means to read or write Z66 files. Only information that I have are that modding and custom level addon packs are indeed possible.

Edit: ...! Oh! Momentary lapse of memory there. I know who you are! Your planning to add Camoto support for Zone 66, eh? I really wish you luck on this venture, I've only brushed the surface really and it has been on a backburner forever since john_doe disappeared before a source code could be delivered. I look forward to Camoto (music compartment mainly, for a Corridor 7 remake and some other musical enhancement projects), best of luck with it.
## Post #7
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-10-31T01:13:44+00:00
- Post Title: Zone 66 compression format

Oh I only just saw your edit - yes I hope to add Zone 66 support to Camoto!  The music is my main focus too...  I don't recognise your username, do I know you from somewhere else?? 

john_doe's profile says he's still logging in but I haven't received a reply, so I guess he's no longer interested in Zone 66, which is a shame because he seemed to have it all figured out.  I still have no idea how he was able to get LZW working, I've been staring at those bytes for days manually following the LZW algorithm through and no variations produce anything like valid data, but then again I'm certainly no expert on decompression!
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-11-01T18:26:48+00:00
- Post Title: Zone 66 compression format

No, I don't think so, I tend to keep tabs on people and their projects especially if they involve retro 1990s games (my main stay). And same here, compression is really out of my area, which is a shame because I really wish I had that source code to share with you. I just don't know what has happened.
## Post #9
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-11-04T12:20:38+00:00
- Post Title: Zone 66 compression format

Hi,

Sorry for disappearring but here I am 
I'll try to find the source code I have and upload it somewhere this evening after work.
(I got involved with ScummVM and reverse engineering of complete games so I didn't have much time for Xentax anymore.)

Edit: I uploaded the source code here: [http://www.xentax.com/uploads/author/johndoe/Z66.zip](http://www.xentax.com/uploads/author/johndoe/Z66.zip)
It contains code for the sprite viewer, decompression and map viewer. It's not ready-to-use and you'll have to compile it with Mingw and SDL and change the filenames for it to work. Also the sprite and map viewer work with uncompressed files so they'll need to be uncompressed before. Also, the decompression code doesn't work with all files yet, some files have 13 bits maximum code size while others have 14 bits (this can be changed easily, though). For a standalone decompressor you'd need to have a mapping of filename->bits and chose the correct bit size from there as this can't be detected automatically.

I haven't figured out yet the rest of the map data, this probably contains animations, enemies, triggers etc. Maybe I'll find some time to have a look at them.
## Post #10
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-11-07T02:39:57+00:00
- Post Title: Zone 66 compression format

Oh wow that's fantastic!  Many thanks for posting the info.  The decompression code compiled and worked fine on my Linux system.  Now I understand why it looks nothing like normal LZW - it seems to read a byte's worth of data in between each LZW code...bizarre.

Well this will keep me busy for a while - thanks again
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-11-11T10:24:59+00:00
- Post Title: Zone 66 compression format

Thanks for the code post, and glad your still around (kinda), and I look forward to if you ever do finish it.
## Post #12
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-11-13T04:07:38+00:00
- Post Title: Zone 66 compression format

Looks like there's a couple of bugs in the compression algorithm, I'm currently attempting to solve them (with limited success!)  Using tpal.z66:

```
decompressed: 00 00 ff ff 00 2a 00 2a  00
      actual: 00 00 00 00 00 2a 00 2a  00

```

I think this one is because the file has some invalid LZW tokens in it, and john_doe's code initialises the dictionary to -1 (0xff).  I changed it to initialise the dictionary entries to 0 and it fixed this issue.  But there is another:

```
decompressed: 0a 31 00 2a 2a 00 00 00 2a 2a 00 00 00 00 2a 2a 00 00 00 00 00 2a 2a 00 00 00 00 00 00 00 31 0a 0a 31
      actual: 0a 31 00 00    00 00 00 00    00 00 00 00 00    00 00 00 00 00 00    00 00 00 00 00 00 00 31 0a 0a 31

```

This one I'm not sure about, the tokens being read in go something like this:

```
Read 101+000, write 00 2a 2a 00 + 00      // looks like token 101 is wrong, see @offset 0 above
Read 224+000, write 00 2a 2a 00 00 + 00   // not sure, wrong token again?

```
## Post #13
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-11-13T04:21:44+00:00
- Post Title: Zone 66 compression format

Hooray, posting in a forum when I was stuck meant I immediately found the solution 

The problem was that the first code read in was 108 (which doesn't exist yet) and this was stored as codeword 101.  Later on in the file when code 101 is used, it still references code 108 (which is now valid) causing code 108's data to be inserted when we don't want it.

I added another check so that any invalid codes were pointed back to the first code in the dictionary before being stored.  I'm not sure if this is correct but it appears to be as the output file is now the correct size and contains the correct data.

```
nodes[curDicIndex].code = code;
nodes[curDicIndex].nextCode = value;

```

EDIT: Whoops, 0x100 not zero!
## Post #14
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-11-14T07:39:06+00:00
- Post Title: Zone 66 compression format

Hey Darkfox - you said you were interested in the Zone 66 music?  I just found a new track I've never heard before, so perhaps you know where in the game it is used (maybe win/game over music or something.)  I discovered it as I was browsing through the decompressed files, it looked the same as the other songs.  (And I also extracted a CDFM/670 file from the [Amnesia demo](http://www.pouet.net/prod.php?which=2902) and they look the same as well, so now I'm certain this is the music format used.)

The song is stored in zim00.z66 (Adlib version), zim01.z66 (SB version) and zim02.z66 (GUS version).

To listen, overwrite m01gmuz.z66 (the SB version of the intro song) with zim00.z66 or zim01.z66, or for the GUS version, overwrite m03gmuz.z66 with zim02.z66.  Then run the game (in DOSBox use "zone66 /sb" or "zone66 /gus" depending on which version you want to hear.)

Granted I never made it all the way to the end of the game, but it's still a surprise to hear a new song!  (And this is the second time Zone 66 has done it, I was just as surprised when I found the GUS version of the intro music is a different song to the SB version.)
## Post #15
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-11-16T14:30:45+00:00
- Post Title: Zone 66 compression format

I toyed around with some of the unknown files.
MAP?DAT2.Z66 stores the positions of cannons, ship generators etc.

Here's the structure (in pseudocode), note that all coordinates are in tile-space, they need to be multiplicated by 32 to get pixel-coordinates.

```
	uint8 type; // the type of cannon, refers to the cannon definitions in MAP?DAT3.Z66
	uint8 x, y;
}

ShipGenerator {
	uint8 type; // the type of ship, refers to the ship definitions in MAP?DAT3.Z66
	uint8 x, y;
}

Base {
	uint8 x, y;
}

// Yet unknown, this seems to specify which map elements can be destroyed (?)
Unknown {
	uint8 x, y;
}

Map2 {
	uint8 startPosX, startPosY; // the player's starting position
	uint8 cannonCount;
	uint8 shipGeneratorCount;
	uint8 baseCount;
	uint8 unknownCount;
	Cannon cannons[cannonCount];
	ShipGenerator shipGenerators[shipGeneratorCount];
	Base bases[baseCount];
	Unknown unknowns[unknownCount];
}


```


I also have some specs for MAP?DAT3.Z66 which I will post later.

Edit: I also tried to write a compressor to use modified files in Zone 66. The original algorithm used in Zone 66 is LZ78 with some improvements borrowed from LZW. Sadly it didn't turn out good. One simple solution would be to ignore compression and simply write uncompressed data in (9 bit, 8 bit) pairs. I haven't tried it but it should work.
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-11-16T17:22:37+00:00
- Post Title: Re: Zone 66 compression format

> Reply from Malvineous
>
> Hey Darkfox - you said you were interested in the Zone 66 music?  I just found a new track I've never heard before, so perhaps you know where in the game it is used (maybe win/game over music or something.)  I discovered it as I was browsing through the decompressed files, it looked the same as the other songs.  (And I also extracted a CDFM/670 file from the Amnesia demo and they look the same as well, so now I'm certain this is the music format used.)

The song is stored in zim00.z66 (Adlib version), zim01.z66 (SB version) and zim02.z66 (GUS version).

To listen, overwrite m01gmuz.z66 (the SB version of the intro song) with zim00.z66 or zim01.z66, or for the GUS version, overwrite m03gmuz.z66 with zim02.z66.  Then run the game (in DOSBox use "zone66 /sb" or "zone66 /gus" depending on which version you want to hear.)

Granted I never made it all the way to the end of the game, but it's still a surprise to hear a new song!  (And this is the second time Zone 66 has done it, I was just as surprised when I found the GUS version of the intro music is a different song to the SB version.)

I do NOT recognize this track either, nice find! But I speculate that this is the end credits/sequence theme. I've never beaten all the zones but I could try to sometime to be certain.

And nice discovery john_doe!    I was wondering where those were stored.
## Post #17
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-11-16T17:48:06+00:00
- Post Title: Re: Zone 66 compression format

Also some quick info:
SHIPDAT0.Z66, SHIPDAT1.Z66 and MAPDAT.Z66 are recreated each time when the game starts. The ship files collect player/enemy ship data from each MAP?DAT3.Z66 file and MAPDAT is a list of available maps.
## Post #18
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2010-11-16T22:47:00+00:00
- Post Title: Re: Zone 66 compression format

Very useful, thanks for the info!  I'm (slowly) documenting all this on the [ModdingWiki](http://www.shikadi.net/moddingwiki/Zone_66) as I get it implemented in my own utility, and crediting john_doe with it - but let me know if you would prefer some other name to go there instead!
## Post #19
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-11-17T12:43:09+00:00
- Post Title: Re: Zone 66 compression format

And here's the spec for MAP?DAT3.Z66. There are still some unknown values left to decipher.

```
	uint8 textColor; // some text color, no clue where this is used
	uint8 cannonCount;
	uint8 enemyShipCount;
	uint8 playerShipCount;
	uint8 unk[32]; // This is also stored in MAPDAT.Z66 on game startup
	CannonDef cannons[cannonCount];
	ShipDef enemyShips[enemyShipCount];
	ShipDef playerShips[playerShipCount];
}

CannonDef {
	// The unknown values here are also probably similar to the ones used in the ShipDef (armor etc.)
	uint16 chunkSize;
	char gfx[2]; // Used to build the filename for the graphics in the form "CN??GRFX.Z66"
	uint8 unk1;
	uint8 gunCount;
	uint8 unk3;
	uint8 unk4;
	uint8 unk5;
	coord gfxOffs[16];
	coord gunOffs[gunCount];
}

ShipDef {
	uint16 chunkSize;
	char gfx[2]; // Used to build the filename for the graphics in the form "SH??GRFX.Z66"
	char shipName[32];
	uint8 payload;
	uint8 fuel;
	uint8 armor;
	uint8 topspeed;
	uint8 accel;
	uint8 turning;
	coord gfxOffs[16];
	// No clue what these unks are used for
	coord unk1, unk2;
	uint8 unk3;
	uint8 enginesCount;
	coord enginesOffs[enginesCount];
	uint8 gunCount;
	{
	    uint8 gunType;
	    uint8 gunDirection;
	    coord gunOffs[16];
	} guns[gunCount];
}

```
## Post #20
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-11-18T11:19:43+00:00
- Post Title: Re: Zone 66 compression format

I went though the others files left (besides maps, cannon/ship graphics and music):

```
DEMOK.Z66 - Recorder demo
DEMOT.Z66 - Text displayed during demo
DSFX.Z66 - Sound effects archive (some are raw, some with a ScremTracker 3 instrument header)
ET.Z66 - Text screen
FONT/FONT2.Z66 - Pretty obvious
INSTR.Z66 - Instructions text
MAINGRFX.Z66 - Sprites for weapons/explosions/smoke
MAPAM0.Z66 - Sprite for the tornado
MAPBM0.Z66 - Sprites for water effect (?)
MAPCM0.Z66 - Sprite for a single bird
MAPDM0.Z66 - Sprites for clouds and birds
MISCGRFX.Z66 - Misc sprites (radar etc.)
OS.Z66 - Ordering info screens (uncompressed)
SBG.Z66 - Background screen for campaign texts
TITLE.Z66 - Title screen
ZIL0/1/2.Z66 - Intro animations
ZONE66T.Z66 - Company intro screens

```


Also, I had a look at MAP?DAT4/5/6.Z66. While 5 and 6 contain the text before and after a campaign, they, along with DAT4, also contain a little x86 code which is executed. I have no clue what that code exactly does.
## Post #21
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-11-28T06:18:49+00:00
- Post Title: Re: Zone 66 compression format

I look forward to the day it is possible to make custom map/ship packs. Would add to the fun of the game to have easily added user content (easy because there are several unused letters so no need to replace maps, and they are automatically added to the list). Looking forward to Camoto, not just for Zone 66 support but music conversion as well.
## Post #22
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-11-30T10:47:00+00:00
- Post Title: Re: Zone 66 compression format

I actually thought about making a map/sprite editor since we now know enough to create our own maps and ship sprites.
If I decide to do it, I'll probably write it with Lazarus/Free Pascal since I want it to be cross-platform (Win and Linux) and also want a reasonable UI. I would write it in C++ but I'm not familiar with wxWidgets or similar toolkits. Writing it with SDL only would also be possible but it would have a non-standard UI....

Edit: I started with the editor  in Lazarus. Only time will tell when it's in usable state, though.
While working on it I just remembered that I forgot one thing: I don't know yet how animated tiles are handled. The graphics for these are also in the MAP?GRFX file but I can't find (yet) anything about number of frames etc.

Edit 2: It seems the animation info is also stored in MAP?DAT, I only read part of that file so far.
## Post #23
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-12-01T09:45:11+00:00
- Post Title: Re: Zone 66 compression format

Here's the structure for MAP?DAT.Z66 (in pseudocode again):

```
	uint16 tilesCount;
	uint16 animatedTilesCount;
	// Tiles with an even index are normal, odd index is the destroyed tile
	uint16 tiles[tilesCount * 2];
	// Score given when this tile is destroyed 
	uint18 tilesDestroyScore[tilesCount];
	// Map with info if the given tile can be destroyed (1) or not (0)
	uint18 tilesDestroyable[tilesCount];
	{
		// Tile index in tiles of the tile to be animated
		uint16 tileIndex;
		// First/last index into the tile graphics
		uint16 firstTileGfxIndex, lastTileGfxIndex;
		// 0: tile loops; 1: tile is played forward, then backward (ping-pong)
		int8 tileLoop;
		// Used only internally by the game
		uint8 unused1, unused2;
		// Ticks until the next tile graphic is displayed
		uint8 tickCount;
	} animatedTiles[animatedTilesCount];
}


```
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-12-02T20:54:05+00:00
- Post Title: Re: Zone 66 compression format

That would be awesome and great find on the animated tiles! Will there eventually be a way to easily customize ships, their weapons, stats, and so forth or is that part of the ship graphic editing? When using ships as bases it is difficult to add guns, for instance, since I have to add positional coordinates per gun which in turn as I recall have to be manually recalculated in the file size.
## Post #25
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2010-12-06T09:40:13+00:00
- Post Title: Re: Zone 66 compression format

Yes, I'm planning to make everything customizable where we know the format with a nice GUI.
Here are some very early screenshots:
The map editor:
[http://img593.imageshack.us/img593/1822/screen1s.png](http://img593.imageshack.us/img593/1822/screen1s.png)
The map editor showing all tiles as destroyed:
[http://img593.imageshack.us/img593/9493/screen2c.png](http://img593.imageshack.us/img593/9493/screen2c.png)
The map obect editor (cannons ans enemy/player ships):
[http://img411.imageshack.us/img411/117/screen3gz.png](http://img411.imageshack.us/img411/117/screen3gz.png)
The ship editor:
[http://img109.imageshack.us/img109/3482/screen401.png](http://img109.imageshack.us/img109/3482/screen401.png)

I'll also make a sprite (ship and cannon) editor where guns etc. can be placed on a grid like the map.
## Post #26
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-12-06T22:30:03+00:00
- Post Title: Re: Zone 66 compression format

That sounds and looks really good, great work!
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-04T03:55:37+00:00
- Post Title: Re: Zone 66 compression format

Sorry to bump but haven't read or seen any updates on this in around 2 months, any updates or things get really busy? Just curious, since it was looking really far in, most stuff was worked out and all. Noticed Camoto stalled too, guess school/jobs came into play.
## Post #28
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2011-02-05T02:23:04+00:00
- Post Title: Re: Zone 66 compression format

Yeah there's never enough time in the day unfortunately.  Especially not when [linux.conf.au](http://linux.conf.au) is happening, and someone put malware all over my web server and it had to be reinstalled.  Oh and [my city flooded](http://www.google.com.au/images?q=brisbane+flood+2011) 

As for Camoto, it's able to decompress the files and edit some of the graphics, but more recently I've gotten sidetracked by the music converter (not Z66 related...yet) as I got annoyed with some very difficult to find bugs in the Blood RFF encryption code.  So it may take a while, but we'll get there in the end!
## Post #29
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-05T08:02:22+00:00
- Post Title: Re: Zone 66 compression format

Ooh, woah, think I heard that on the news, sorry to hear that man, everything alright there? Wasn't much damages was there? And damn kids and their malware...

And oh? You mean the portion of Camoto that will be the successor of DRO2MID and other such tools? I'm looking forward to that as well so I don't mind, really. .
## Post #30
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2011-02-06T02:09:22+00:00
- Post Title: Re: Zone 66 compression format

Yeah everything's almost back to normal now, just a lot of cleanup going on.  My local supermarket is still closed while they clean out the mud, but at least I didn't have to rip out and replace everything in my home (including the walls) like those people whose places went under...

And yes, this is the DRO2MID replacement part of Camoto.  Currently it can convert between IMF, WLF, RAW and DRO v1+v2 formats (all Adlib/OPL) so the main bits left are MIDI support and a GUI.
## Post #31
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-02-06T06:00:34+00:00
- Post Title: Re: Zone 66 compression format

Good, good, glad things are getting back to some normalcy!  Though I feel bad for those people who's places went under...

And that is good to hear! The V2 DRO support has me excited. The only way for some games to get the music is to use DosBox (Shakii the Wolf). So a preemptive thanks there.
## Post #32
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2011-03-08T12:24:13+00:00
- Post Title: Re: Zone 66 compression format

Sorry, got busy with other stuff (luckily no flooding here).
I can't say when I'll continue with the project but I expect it to bee soon-ish.
I'm also planning to add XML import/export just for fun, so other tools could use the XML data instead of implementing the low-level read/write code themselves, and later one can recreate the game files from the XML.
## Post #33
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-09T03:50:01+00:00
- Post Title: Re: Zone 66 compression format

Hey! Glad to hear your doing well. XML for fun, eh? That sounds like an interesting way to go about it. Like turning it into a readable text code that can later be compiled back into the data file. In any case, I am looking forward to the results. Thanks for the update!
## Post #34
- Username: Mikemc
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 04, 2011 10:50 am
- Post datetime: 2011-04-12T11:30:17+00:00
- Post Title: Re: Zone 66 compression format

Since you have access to the tiles, would there be a chance of you posting a complete tileset image? I'd like to make some maps, if only just to look at .

- Mike
## Post #35
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-05-09T07:11:59+00:00
- Post Title: Re: Zone 66 compression format

Well, as john_doe said, a complete editor will be coming eventually, he's been busy with other things. This will include a ship, map, tile, gun emplacement, possible selection screen, etc editor which will be great and will allow enthusiasts (like me) to make their own missions packs.

Edit: BTW, how goes the Camoto music converter UI, Malvineous?
## Post #36
- Username: Mikemc
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 04, 2011 10:50 am
- Post datetime: 2011-05-11T10:41:53+00:00
- Post Title: Re: Zone 66 compression format

I don't need the editor for now, just the tiles.
## Post #37
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-05-13T06:40:28+00:00
- Post Title: Re: Zone 66 compression format

I understand that, just really looking forward to it myself. XD
## Post #38
- Username: Ardent
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 06, 2007 4:23 am
- Post datetime: 2013-08-04T05:06:17+00:00
- Post Title: Re: Zone 66 compression format

it's been forever since I've been on here, but it's good to see that there are still people looking into this. Are there any updates?
## Post #39
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-11-17T11:40:01+00:00
- Post Title: Re: Zone 66 compression format

I've just posted a version of [Camoto](http://www.shikadi.net/camoto) (version 20131117) that can kind of edit Zone 66 levels.  You can open the level, change it, and save it, but for some reason the game locks up when it tries to load the modified level.

I don't know why it does this, but there must be a problem with the compression algorithm somewhere...
