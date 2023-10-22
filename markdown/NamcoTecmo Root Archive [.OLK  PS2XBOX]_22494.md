## Post #1
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T08:23:17+00:00
- Post Title: Namco/Tecmo Root Archive [*.OLK | PS2/XBOX]

This thread is a specification of the archive format used by Namco and Tecmo in game series like Soul Calibur and Dead or Alive respectively in the PS2/XBOX era, which have the ".olk" extension.

Format Specifications:

 PS2/XBOX Checksum Enabled [Valid If: FileSize % 16 = 0]
 32-bit Format
 Sub-File Offsets must be divisible by OffsetPad.
 Maximum Capacity of over 2.000.000 Sub-files
 Minimum Capacity of 0 Sub-files
 Unused Section do NOT affect the game.
 Value-Dependent Archive, any sections not declared by Offset+Size does NOT affect the game.

Format Structure:
The code given is a psuedo code inspired by 010 Editor's Template Language.

```
{
	struct HEADER
	{
		int EntryCount;
		int MagicCode; // Always 0x6B6E6C6F
		int OffsetPad;
		int UNUSED;
		int ArchiveOffset;
		int ArchiveSize;
		time_t ArchiveDate;
		int UNUSED;
	} header;
	
	struct ENTRY
	{
		int FileOffset;
		int FileSize;
		time_t FileDate;
		int UNUSED;
	} entry[file.header.EntryCount];
	
	char DATA[];
} file;

```

Interesting Tidbits:

 Format is Value-Dependent, it does not care what happens outside of it's declared offsets and unused offsets do not affect the game if changed. Meaning the format can be modified alongside with unused offsets to give it extra functionality with modding tools, such as sub-file names, etc.
