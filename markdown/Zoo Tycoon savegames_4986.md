## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2010-09-07T00:20:35+00:00
- Post Title: Zoo Tycoon savegames

I've been having fun with this; see [Zoo (Zoo Tycoon)](http://wiki.xentax.com/index.php?title=Zoo (Zoo Tycoon)) on the wiki for what I have so far (and if you're aware of any other documentation or any savegame editors, I'd appreciate links  ).
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2010-10-22T20:18:21+00:00
- Post Title: Zoo Tycoon savegames

I don't suppose anyone got a copy of the wiki page before the DB corruption, did they? I didn't have the foresight to save an offline copy, Google didn't seem to cache the page, and I'd really prefer not to redo that work.
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-12-14T18:31:46+00:00
- Post Title: Zoo Tycoon savegames

You could try the [Waybackmachine](http://www.archive.org/web/web.php) but as it looks there is no entry for the page. But [http://web.archive.org/web/*/http://wiki.xentax.com/](http://web.archive.org/web/*/http://wiki.xentax.com/) is working.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2010-12-14T19:16:01+00:00
- Post Title: Zoo Tycoon savegames

I already thought of that, but Wayback doesn't display anything newer than six months old (and that's even assuming they archived the page in the first place).

I also thought of Google's cache, but it seems they didn't get it either: [http://webcache.googleusercontent.com/s ... 520Tycoon)](http://webcache.googleusercontent.com/search?q=cache:http://wiki.xentax.com/index.php/Zoo%2520%28Zoo%2520Tycoon%29); [http://webcache.googleusercontent.com/s ... 520Tycoon)](http://webcache.googleusercontent.com/search?q=cache:http://wiki.xentax.com/index.php%3Ftitle%3DZoo%2520%28Zoo%2520Tycoon%29). Does anyone know of any other website archivers that may have gotten it?
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-18T07:00:38+00:00
- Post Title: Zoo Tycoon savegames

After having nothing better to do, I spent more time on this and re-discovered much of what I'd already gotten, and then quite a bit more:

```
uint32 {4} @0008	- Unknown (always 0x09 0x04 0x00 0x00?)
uint32 {4} @000C	- Map width
uint32 {4} @0010	- Map height
uint32 {4} @0014	- Unknown (always 0x0B 0x00 0x00 0x00?)
uint32 {4} @0018	- Unknown (always 0x2A 0x00 0x00 0x00?)
uint32 {4} @001C	- Number of exhibits
uint32 {4} @0020	- Unknown (always 0x01 0x00 0x00 0x00?)

// for each exhibit (77 + x bytes per exhibit (?) )
	uint32 {4}			- Unknown
	uint32 {4}			- Length of exhibit name field
	byte {x}			- Exhibit name
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	byte {25}			- Unknown (always null?)
	uint32 {4}			- Unknown
	uint32 {4}			- In-game date exhibit was constructed (bitshifted)
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown (always null?)

uint32 {4} @0024 - Unknown

// for each tile (10 bytes per tile)
	uint32 {4}			- Elevation
	uint8 {1}			- Slope type (North = top, East = right, South = bottom, West = left)
							0x00 - None (TL:0, TR:0, BL:0, BR:0)
							0x01 - Southwest floor down (TL:0, TR:-1, BL:-1, BR:-1)
							0x02 - buggy/crashes
							0x03 - buggy/crashes
							0x04 - Southeast corner up (TL:0, TR:0, BL:1, BR:0)
							0x05 - East side down (TL:0, TR:-1, BL:0, BR:-1)
							0x06 - buggy/crashes
							0x07 - buggy/crashes
							0x08 - buggy/crashes
							0x09 - buggy/crashes
							0x0A - buggy/crashes
							0x0B - buggy/crashes
							0x0C - buggy/crashes
							0x0D - buggy/crashes
							0x0E - buggy/crashes
							0x0F - buggy/crashes
							0x10 - Southeast corner up (TL:0, TR:0, BL:0, BR:1)
							0x11 - Northeast to Southwest center down (TL:0, TR:-1, BL:-1, BR:0)
							0x12 - buggy/crashes
							0x13 - buggy/crashes
							0x14 - South side up (TL:0, TR:0, BL:1, BR:1)
							0x15 - Northeast corner down (TL:0, TR:-1, BL:0, BR:0)
							0x16 - buggy/crashes
							0x17 - buggy/crashes
							0x18 - buggy/crashes
							0x19 - Southwest corner up to Northeast corner down (TL:0, TR:-1, BL:1, BR:0)
							0x1A - buggy/crashes
							0x1B - buggy/crashes
							0x1C - buggy/crashes
							0x1D - buggy/crashes
							0x1E - buggy/crashes
							0x1F - buggy/crashes
	uint8 {1}			- Terrain type (0x00 - Grass, 0x01 - Savannah Grass, 0x02 - Sand, 0x03 - Dirt, 0x04 - Rainforest Floor, 0x05 - Brown Stone, 0x06 - Gray Stone, 0x07 - Gravel, 0x08 - Snow, 0x09 - Fresh Water, 0x0A - Salt Water, 0x0B - Deciduous Floor, 0x0C - Waterfall, 0x0D - Coniferous Floor, 0x0E - Concrete, 0x0F - Asphalt, 0x10 - Trampled Terrain; all other values are treated as Grass (tested up to 0x4F))
	uint32 {4}			- Tile sides

uint32 {4}			- Number of objects?

// for each object (12 + x + x + x + x + ? ... bytes per object?)
	uint32 {4}			- Length of object identifier 1 field
	byte {x}			- Object identifier 1
	uint32 {4}			- Length of object identifier 2 field
	byte {x}			- Object identifier 2
	uint32 {4}			- Length of object identifier 3 field
	byte {x}			- Object identifier 3
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Unknown
	uint32 {4}			- Length of object name field
	byte {x}			- Object name
	...

```

Obviously, there's still a lot of the format left to deduce, including an absolutely massive chunk following the objects/entities block that I have no idea at all what it's used for. For now, though, I'm more interested in just learning enough about the format to be able to add or remove rows and columns to the map (thus allowing me to resize them); this will require, at the very least, figuring out how the locations of exhibits and objects/entities is stored.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-20T06:21:26+00:00
- Post Title: Zoo Tycoon savegames

Nice work!
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-07-20T07:13:45+00:00
- Post Title: Zoo Tycoon savegames

I started taking a look in passing because surprisingly I had a copy of this that I never opened.

strings are dword length, char[length]
bools are uint8

```
uint32 version; // base game is version 71 I guess? with the addons in the Complete Collection it's 106
uint32 locale; // only present if version >= 69, defaults to 1033 (enUS) if earlier
uint32 unknown3; // only present if version >= 82
uint32 width;
uint32 height;
uint32 unknown6;
uint32 unknown7;
uint32 exhibitCount;
exhibit exhibits[exhibitCount]
uint32 unknown10; // only present if version >= 64, may default to 2 otherwise? needs research
if (version >= 97)
  unknownData1 unknown11;
uint32 unknown12;
tile tiles[width*height];
uint32 objectCount;
object objects[objectCount];
int32 unknown16;
int32 unknown17;
int32 unknown18;
int32 unknown19;
int32 unknown20;
// further file needs research...

for exhibit:
  uint32 unknown0;
  uint32 unknown1;
  string name;
  int32 unknown3; // only present if version >= 21, defaults to -1 otherwise
  int32 unknown4; // only present if version >= 21, defaults to -1 otherwise
  int32 unknown5; // only present if version >= 21, defaults to -1 otherwise
  uint32 unknown6; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown7; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown8; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown9; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown10; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown11; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown12; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown13; // only present if version >= 34, defaults to 0 otherwise
  uint32 unknown14; // only present if version >= 34, defaults to 0 otherwise
  uint64 unknown15; // only present if version >= 34, defaults to 0 otherwise
  uint64 unknown16; // only present if version >= 37, defaults to 0 otherwise
  uint32 unknown17; // only present if version >= 83, defaults to 0 otherwise
  bool unknown18; // only present if version >= 85, defaults to false otherwise
  bool unknown19; // only present if version >= 90, defaults to false otherwise
  if (unknown19 == true)
    // unknown data... needs research
  if (unknown18 == true)
    uint32 unknown20;
    uint32 unknown21;
    bool unknown22; // only present if version >= 88, defaults to true otherwise
    uint32 unknown23; // only present if version >= 100, defaults to 100 otherwise
    uint32 unknown24; // only present if version >= 100, defaults to 100 otherwise
    uint32 unknown25; // only present if version >= 100, defaults to 100 otherwise

for unknownData1:
  uint32 unknownCount0; // only present if version >= 89, defaults to 0 otherwise
  // if unknownCount0 > 0 there's more data, needs research...
  uint16 unknown2; // only present if version >= 97, not sure what it defaults to, needs research
  uint16 unknown3; // only present if version >= 97, not sure what it defaults to, needs research

for tile:
  uint32 unknown0;
  uint8 unknown1;
  uint8 unknown2;
  uint32 unknown3;

for object:
  string unknown0;
  string unknown1;
  string unknown2;
  uint32 dataSize; // only present if version >= 70, defaults to 0 otherwise -- though I think following data will still probably be present
  uint8 data[dataSize]; // data depends on unknown0/unknown1/unknown2
```
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-20T07:21:00+00:00
- Post Title: Zoo Tycoon savegames

Cool work, Rick, that helps fill in some gaps on my description (I only have the original Zoo Tycoon to play with, though I'm also going to have a look at the demos at some point); I'm not sure how closely you looked at what I've got so far, but I have some stuff you don't as well (for instance, I have the tile data almost completely figured out; I just need to finish up the slope values and re-figure out how the tile sides work).
