## Post #1
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2007-09-21T07:17:24+00:00
- Post Title: JUMP Ultimate Stars (Nintendo DS)

[http://en.wikipedia.org/wiki/Jump_Ultimate_Stars](http://en.wikipedia.org/wiki/Jump_Ultimate_Stars)

.AAR Archive for an unpacked Nintendo DS rom. I'm sure someone can make use of this information. I also have most of the archived file formats reverse engineered for those interested.

Type 2

```
	word		Type;
	word		NumberChunks;
	dword		ChunkType;
	dword		ChunkType;

[NumberChunks]
	dword		Type;
	dword		Start;
	dword		Size;
	word		Unknown;
	word		Unknown;
[/NumberChunks]

	//Pad to data

```


Type 3 (Main Archive)

```
	word		Type;
	dword 		NumberFiles;
	word 		unknown;
	dword 		ArrayCount;
	word 		EndOfTable;
	word 		FileTableIndex[ArrayCount+1];
	//Pad to start of table

[NumberFiles]
	word 		FileID;
	word 		Unknown;
	dword 		StartOfFile;
	dword 		SizeOfFile;
	word 		unknown;
	word 		unknown;
	word 		unknown;
	char 		FileName[18]; //max 32 byte header
[/NumberFiles]

```
