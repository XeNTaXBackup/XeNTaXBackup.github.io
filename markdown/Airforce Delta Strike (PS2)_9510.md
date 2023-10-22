## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-08-19T22:10:28+00:00
- Post Title: Airforce Delta Strike (PS2)

I made a tool for extracting most files (it also automatically converts most PSS files to TGA): [http://www.tzarsectus.com/tools/ADStool.rar](http://www.tzarsectus.com/tools/ADStool.rar)

Some info about the formats. Header of the archive files:

```
{
	unsigned int magic;
	unsigned int totalSize;
	unsigned int unkA;
	unsigned int unkB;

	unsigned int startofFileEntryList;
	unsigned int sizeoFileEntryList;
	unsigned int startofOtherEntryList;
	unsigned int sizeofOtherEntryList;
	unsigned int sizeofUnk;
	unsigned int sizeofUnk2; //This is totalSize - sizeofUnk
};

struct ADSarchiveFileEntry_s
{
	unsigned char filename[48];
	unsigned int size;
	unsigned int offset;
	unsigned int unkA;
	unsigned int unkB;
};

struct ADSarchiveDirectoryEntry_s
{
	unsigned char name[16];
	unsigned int fileCount;
	unsigned int unkB;
	unsigned int unkC;
};

```


Everything is little endian and there's no compression.

Header for pss files:

```
	unsigned int magic;
	float unkA; //Seen as 1.0
	unsigned char paddingA[40];
	unsigned int type; //0=32bit, 19=256 colour palette, 20=16 colour palette
	unsigned int unkC; //Seen as null
	unsigned int width;
	unsigned int height;
	unsigned int paletteOffset;
	unsigned int paletteSize;
	unsigned int imagedataOffset;
	unsigned int imagedataSize;
	unsigned char paddingB[16];
} pssHeader_t;

```


Most PSS files have palettes (256 colours) and an alpha channel, which is a pretty rare format. Again, no compression.

Edit: I've updated my tool with support for replacing files within the archives. I doubt many people are interested in modding the game, but if anyone are, let me know and I'll write more detailed information on how to use my tool.
