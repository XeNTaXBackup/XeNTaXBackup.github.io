## Post #1
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T09:11:45+00:00
- Post Title: Namco Text Archive [*.TXT | PS2/XBOX]

This thread is a specification of the text archive format used by Namco in game series like Soul Calibur in the PS2/XBOX era, which have the ".txt" extension.

NOTE: This format functions sort of like a non-broken version of PKG.

Format Specifications:

 PS2/XBOX Checksum Enabled [Valid If: FileSize % 16 = 0]
 32-bit Format
 Maximum capacity varies from game to game due to other files referencing to this one being limited in that way.
 Offsets are non-absolute. Length of the header must be added to each offset to get their absolute values.

String Specifications:

 There is support for special strings declared by the game's font table.
 The string can be terminated with 0x00. In some games, this termination is mandatory as you may have noticed: There is no size declaration.
 The strings are UTF8.
 The strings can support Japanese, Korean and Chinese through special font tables.

Format Structure:
The code given is a psuedo code inspired by 010 Editor's Template Language.

```
{
	struct HEADER
	{
		int TargetLanguage;
		int EntryCount;
		int FileOffsets[EntryCount];
	} header;
	
	char DATA[];
} file;

```

Interesting Tidbits:

 In some games, if the string is not terminated, the string is parsed until a terminator is found. This can lead to funny results.
