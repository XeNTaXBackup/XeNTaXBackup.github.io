## Post #1
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-05T08:53:17+00:00
- Post Title: Namco Archive [*.PKG | PS2/XBOX]

This thread is a specification of the archive format used by Namco in game series like Soul Calibur in the PS2/XBOX era, which have the ".pkg" extension.

NOTE: This format seems really simple, but it's way of actual function is extremely bizzare. As such, many of it's properties are... uncertain.

Format Specifications:

 PS2/XBOX Checksum Enabled [Valid If: FileSize % 16 = 0]
 32-bit Format
 Capacity unknown due to it's bizzare nature.
 Value-Dependent Archive, any sections not declared by Offset+Size does NOT affect the game.

Format Structure:
The code given is a psuedo code inspired by 010 Editor's Template Language.

```
{
	struct HEADER
	{
		int EntryCount;
		int FileOffsets[EntryCount];
		int EOF_Offset;
	} header;
	
	char DATA[];
} file;

```

Interesting Tidbits:

 Format is Value-Dependent, it does not care what happens outside of it's declared offsets and unused offsets do not affect the game if changed. However, because of this format's bizzare nature, extra functionality cannot be given to it without serious consequences.
