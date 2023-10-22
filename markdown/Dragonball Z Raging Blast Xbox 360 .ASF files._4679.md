## Post #1
- Username: StalkerUKCG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 28, 2010 11:13 am
- Post datetime: 2010-06-29T04:37:38+00:00
- Post Title: Dragonball Z Raging Blast Xbox 360 .ASF files.

Hey iv decided i want to start editing textures from DBZ RB on 360, Iv got a JTAG and legal backups of the game on  my computer. 
Theres 4 .afs files which make up the game. 

St-pack_boot_pt_x360.afs
St-pack_game_pt_x360.afs
St-pack_progress_pt_x360.afs
St-pack_sound_pt_x360.afs

I assume the textures lie within St-pack_game_pt_x360.afs, problem is i cant seem to unpack it or get the textures out. iv tried using AFSExplorer to view the files but it just shows 3462 files which names names just show up as letters, starting with b and ending with s 



id upload the file for some of you guys to look at but its 1.58Gb. Im really stumped on where to go from here any and all help will welcome.
## Post #2
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2010-08-19T22:58:29+00:00
- Post Title: Dragonball Z Raging Blast Xbox 360 .ASF files.

Yeah I'd like to know more about this. Is there a way to figure out how this works. The models file format is what I'm more interested in since those models are very nice compared to how they look in Raging Blast 2 plus if someone could figure this we could swap the textures out if there the same mappings and all. 

This would be very nice to figure out if someone could put forth the time. Alas I'm just a beginner.
## Post #3
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-08-21T01:09:53+00:00
- Post Title: Dragonball Z Raging Blast Xbox 360 .ASF files.

The ASF files are the least of your worries...

[viewtopic.php?f=21&t=4039](http://forum.xentax.com/viewtopic.php?f=21&t=4039)

Once i can get past the internal format packing i will gladly work on the rest of the data, heh.

```
 * afs.bt - Structure definitions for Dragon Ball: Raging Blast - afs file related entities.
 *
 *****************************************************************************
 * Revision History:
 *  2009/12/03 - revel8n - Original
 */

#include "common-types.bt"

SetReadOnly(true);

// #pragma displayname("afs structures")
// #pragma fileextensions(".afs")

// #pragma byteorder(little_endian)
LittleEndian();

// mark used bytes with a light green background
SetBackColor(cLtGreen);

// AFS File Structure
struct AFS_FILE
{
//	#pragma lockAt(0x00000000)

	// AFS File Header Structure - 0x04 (4) bytes
	struct AFS_HEADER
	{
		uint32 fileTag; // 'AFS'
		uint32 fileCount;
		
		struct
		{
			uint32 fileOffset <format = hex>;
			uint32 fileSize <format = hex>;
		} fileTable[fileCount + 1];
	} fileHeader;
	
	FSkip((0x10 - (FTell() & 0x0F)) & 0x0F);
	struct
	{
		local uint32 fileNum = 0;
		for (fileNum = 0; fileNum <= fileHeader.fileCount; ++fileNum)
		{
			FSeek(fileHeader.fileTable[fileNum].fileOffset);
			union
			{
				uint8  dataBytes[fileHeader.fileTable[fileNum].fileSize];
			} fileData;
		}
	} fileData;
};

struct AFS_FILE fileInfo;

```
## Post #4
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2010-10-23T01:37:28+00:00
- Post Title: Dragonball Z Raging Blast Xbox 360 .ASF files.

Well love to see more progress on this. Best of luck to you.
