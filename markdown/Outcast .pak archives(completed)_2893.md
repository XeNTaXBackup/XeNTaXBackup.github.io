## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-14T22:34:29+00:00
- Post Title: Outcast .pak archives(completed)

```
uint NumFiles;

struct Entry {
	uint namelength;
	char name[namelength];
	uint offset;
	uint size;
	uint size_decompressed;
} entries[NumFiles]<optimize=false>;
```

All data is compressed using the PKWare Data Compression Library. You can find decompression source code on the web. 
The first two bytes (0x00 0x06) are the PKDCL header.
