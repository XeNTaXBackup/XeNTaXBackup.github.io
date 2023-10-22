## Post #1
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-15T01:14:39+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-05-15T15:01:48+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

i hope to be posting more on these and related formats in the future once i get time.

The Colosseum files at least (after decompression), are a derivative of the archive format used by the sysdolphin api from hal laboratories.  There are a number of games that use it either directly or as a base (Kirby Air Ride, Smash Brothers Melee, Sonic Unleashed, Pokemon Colosseum, ...).  It would be really nice if i could find data or resources from the actual sdk (any gamecube developers out there, heh?), but eventually i did get some very helpful information on some of the format internals.

The main thing of note in these formats is the offset/pointer relocation table information referenced in the file header.  This allows the file to be read in-place with little to no further parsing of the format (assuming you know the data structures at said offsets).  One other very helpful thing about the relocation table is the fact that offsets are highly unlikely to jump into the middle of a structure, as such you can be fairly certain that if there is an offset to a data location, that is also the beginning of a particular data structure.  After the relocation table are a list of offsets to the root nodes of the data and usually a string table (depending on the format).  From the root nodes the data follows the hierarchy given by the file offsets in the various structures.

There has been a rather long discussion of the information regarding the Smash Brothers Melee data over on the emutalk.net forum.
[http://www.emutalk.net/showthread.php?t=50312](http://www.emutalk.net/showthread.php?t=50312)

The binary template posted later on in the above thread will parse a good deal of the base information, and Tcll posted a version of it up on his site as well.

i'll see if i can either dig up my notes on the format, or get to finishing my investigations in a more timely manner (though the emutalk posts have most of the things presented in some form, but the Pokemon data differs somewhat from Melee).  My list of format work keeps getting longer, heh.  Need to work on completing the work and getting the information posted.  Will see what i can do.
## Post #3
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-27T08:00:24+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

Hah, well, thanks for the heads-up anyway, revelation. 

I've looked through the model files again recently, and I believe that the Wii's MDL0 format is actually based off of that same model format, because of the way the polygon data's set up (type, length, then vertex ID, normal ID, UV ID, vertex ID, normal ID, UV ID, etc.). Since I've actually built a few MDL0 files by hand, I'm gonna see what happens when I inject the vertex, normal, UV and polygon data into an MDL0 file... starting with Porygon, since that oughta be an easy one to work with.
## Post #4
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-05-28T01:39:08+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

As far as i can tell there is no correlation between the MDL0 sections and that of these files.  If you are talking about the blocks of data that start with 0x98, 0xB8, 0x80, and the like when you mention the vertex data, then that is just the normal way the gamecube/wii expect to receive data for rendering, and for most file formats designed specifically for these systems will always contain blocks like this.  Without the vertex declarations located in the file you will not be able to get an accurate size of the vertex information automatically though.

```
 * fsys.bt - Structure definitions for Pokemon Colosseum - fsys file related entities.
 *
 *****************************************************************************
 * Revision History:
 *  2009/09/29 - revel8n - Original
 *  2010/02/22 - breakpoint - Initial changes from SSBM format
 *  2010/02/22 - revel8n - minor updates
 *  2010/02/24 - revel8n - updates to compensate for lack of script pointer type
 *  2010/02/24 - revel8n - addition of initial jobj structure
 */

#include "common-types.bt"

local uint32 t, cnt, savedFilePointer;

void PushFP(void) { savedFilePointer = FTell(); }
void PopFP(void) { FSeek(savedFilePointer); }
// used only to provide a way of giving "empty" structures a perceived size
void PopOffsetFP(uint32 offset) {FSeek(savedFilePointer + offset);}

void FSeekOfs(uint32 ofs) { FSeek(sizeof(fileInfo.fileHeader) + ofs); }

// returns the number of consecutive 32-bit values until zero is reached
// zero itself is not included in the count, and file pointer is not moved
uint32 GetArrayCount(void)
{
    local uint32 cnt = 0;

    PushFP();
    while (ReadUInt(FTell()) != 0)
    {
        FSeek(FTell() + 4);
        cnt++;
    }
    PopFP();
    return cnt;
}

SetReadOnly(true);

// #pragma displayname("fsys structures")
// #pragma fileextensions(".fsys")

// #pragma byteorder(big_endian)
BigEndian();

// DAT_FILE File Structure
struct DAT_FILE
{
	// DAT_HEADER - DAT file header information structure
	SetBackColor(cLtGreen);
	struct DAT_HEADER
	{
        // small hack to determine difference between Pokemon .dat and SSBM .dat
        if (ReadUInt(0x00) == ReadUInt(0x40))
    		uint32 unknown[16];     // unknown 0x40 (64) byte header information

		uint32 origDataSize  <format = hex>; // matches value at offset 0x00 and corresopnds with possibly being the original file/data size as it ends just after the string table if starting
        uint32 dataBlockSize <format = hex>;
        uint32 relocTableEntryCount;
		uint32 stringTableCount;
        uint32 unknown2[4];
	} fileHeader;

    SetBackColor(cLtRed);
    struct DATA_BLOCK
    {
        uint8 data[fileHeader.dataBlockSize];
    } dataBlock;

    SetBackColor(cLtBlue);
    struct RELOC_TABLE
    {
        uint32 relocOffset[fileHeader.relocTableEntryCount] <format = hex>;
    } relocTable;

    SetBackColor(cLtYellow);
	struct ROOT_NODE
	{
		uint32 dataOffset <format = hex>;
		uint32 nameOffset <format = hex>;
	} rootNode;

    SetBackColor(cLtAqua);
	struct
	{
		string nodeName;
	} stringTable[fileHeader.stringTableCount] <optimize = false>;
};

struct DAT_FILE fileInfo;

```


That is just the main structure of the file data, it does not go into the other internal structures.  i will post more when i get access to the files again.
## Post #5
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-05-28T08:31:14+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

> Reply from revelation
>
> As far as i can tell there is no correlation between the MDL0 sections and that of these files.  If you are talking about the blocks of data that start with 0x98, 0xB8, 0x80, and the like when you mention the vertex data, then that is just the normal way the gamecube/wii expect to receive data for rendering, and for most file formats designed specifically for these systems will always contain blocks like this.  Without the vertex declarations located in the file you will not be able to get an accurate size of the vertex information automatically though.Yeah, that's what I had meant about it being similar to the Wii's format. I should've been a little bit more specific about that.
## Post #6
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-07-17T09:20:47+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

It's been a while. Has there been progress? Yes, there has.

Even though I've had trouble figuring out how to export models from Battle Revolution, it seems that Pharrox, a member of the Smash Boards, is getting closer to completing an exporter for the models from that game, so it's good that someone else understands how it's set up.



He was able to export Ninetales's model into Maya, for example.

And, from parsing the information from a bunch of decompressed files from Pokémon XD, I was able to export these models:



It's not much, but it's some sort of progress. I'm gonna look through some more of the files at a later time, but I'm probably gonna be really busy for the next few weeks...
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-07-19T21:01:58+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

i thought there was a decompressor for pokepark, that used MDL0. meaning people already had access to a very large pokemon model library. models better in Colosseum?
## Post #8
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2010-07-19T21:45:54+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

> Reply from Mario_Kart
>
> i thought there was a decompressor for pokepark, that used MDL0. meaning people already had access to a very large pokemon model library. models better in Colosseum?Well, PokéPark only has 194 of them, not including alternate forms, so more than half of them can't even be ripped from that game, so the only other games they could be ripped from are Colosseum/XD or Battle Revolution.

For example, a few people asked me for Typhlosion's model, and that one's not in PokéPark, so ripping its model from that game is not an option.
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-07-20T21:55:18+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

oh yeah, but Colosseum is an older game, it wont have all the new ones either. so whats the game plan on cetching them all? I'm surprised none of the games actually have a complete library of pokemon
## Post #10
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-22T20:31:30+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

Been a while and i am just getting back to this for a brief moment.  At least on the Pokemon Colosseum side i never did update my progress to match that of what i have already shown of the Smash Brothers Melee format for which that one is derived from.  So here are some screen shots and an update FSYS decompression bms script.

[](http://img703.imageshack.us/i/mpxvrarethunder.jpg/)[](http://img132.imageshack.us/i/mpxvmewtwo.jpg/)

```
comtype lzss "12 4 2 2 0"

# 0x00
idstring "FSYS"
get TEMP long
get TEMP long
get DATA_COUNT long
# 0x10
get TEMP long
get TEMP long
get INFO_OFFSET long
get DATA_BASE long
# 0x20
get FILE_SIZE long

goto INFO_OFFSET
# 0x00
get OFFSET_ARRAY long
get NAME_TABLE   long
get BASE_OFFSET  long

For i = 0 < DATA_COUNT
	goto OFFSET_ARRAY
	get DATA_OFFSET long
	
	goto DATA_OFFSET
	# 0x00
	get DATA_HASH   long
	get OFFSET      long
	get SIZE        long
	get TEMP        long
	# 0x10
	get TEMP        long
	get ZSIZE       long
	get TEMP        long
	get TEMP        long
	# 0x20
	get TEMP        long
	get NAME_OFFSET long
	
	goto NAME_OFFSET
	get NAME string
	string NAME += ".fdat"
	
	goto OFFSET
	idstring "LZSS"
	get SIZE  long
	get ZSIZE long
	get DUMMY long
	savepos OFFSET
	math ZSIZE -= 12

	clog NAME OFFSET ZSIZE SIZE
	
	math OFFSET_ARRAY += 4
next i

```
## Post #11
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2011-07-30T03:18:35+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

Sorry to bring up such an old topic. But I'm wondering if any progress has been on this. I would love to look into the trainer models if this where to get complete.

At least decompress and extract the fsys file to look at the main files. Just curious seeing where this went.
## Post #12
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2012-03-31T01:25:13+00:00
- Post Title: Pokémon Battle Revolution (or Pokémon Colosseum)

> Reply from RandomTBush
>
> It's been a while. Has there been progress? Yes, there has.

Even though I've had trouble figuring out how to export models from Battle Revolution, it seems that Pharrox, a member of the Smash Boards, is getting closer to completing an exporter for the models from that game, so it's good that someone else understands how it's set up.



He was able to export Ninetales's model into Maya, for example.

And, from parsing the information from a bunch of decompressed files from Pokémon XD, I was able to export these models:



It's not much, but it's some sort of progress. I'm gonna look through some more of the files at a later time, but I'm probably gonna be really busy for the next few weeks...

RandomTBush How did Pharrox import Ninetales's model into Maya? Can you ask him to import Giratina from Battle Revolution into Maya?
