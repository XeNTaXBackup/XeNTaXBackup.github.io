## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-07T21:41:29+00:00
- Post Title: Street Wars gfx

EDIT:
I've found the files which must contain the graphics data.
[http://uploaded.to/?id=0oaqob](http://uploaded.to/?id=0oaqob)

Any help appreciated. 

Edit:
Here's my current 010 Editor template. It works for BUTTONS.SPR but I still don't know in which order the colors in the palettes are stored and in which order they are indexed in the data field.

The sprites are stored upside down. Some SPRs contain their own palette at the end of the file. Those who don't use the palettes in the game's PALETTES folder. Those files are available here: [http://uploaded.to/?id=gw4oz6](http://uploaded.to/?id=gw4oz6)

Additionally they seem to use some unknown compression in the other ones cause the data block is smaller than width*height there.

```

struct Header {
	uint	NumSprites;
	uint	offsets[NumSprites];
	uint	PaletteOffset;
} header;

struct Sprite {
	ushort	uk1;
	ushort	uk2;
	ushort	width;
	ushort	height;
	ubyte	data[width*height]; // works only for buttons.spr, others seem to use unknown compression
};

for(i=0; i<header.NumSprites; i++)
{
	if (header.offsets[i] != 0)
	{
		FSeek(header.offsets[i]);
		Sprite sprites;
	}
}

if (header.PaletteOffset != 0)
{
//	FSeek(header.PaletteOffset);
	struct RGB {
		ubyte r;
		ubyte g;
		ubyte b;
	} palette[256];
}
```

[MICE.SPR15.jpg](https://xentaxbackup.github.io/file/1269_MICE.SPR15.jpg)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-11T15:08:08+00:00
- Post Title: Street Wars gfx

Hmm still don't know how the palette is indexed and what compression is used.
Don't know any reason why it shouldn't be indexed normally 
[sprites.rar](https://xentaxbackup.github.io/file/2861_sprites.rar)
