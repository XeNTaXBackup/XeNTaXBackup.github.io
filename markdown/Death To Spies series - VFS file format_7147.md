## Post #1
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2011-08-09T03:13:05+00:00
- Post Title: Death To Spies series - VFS file format

This is an interesting format because these files have a tree-like directory structure which needs to develop a more complicated algorithm to reconstruct the file structure.
There exists an extractor already but it runs with .net stuff installed only and therefore I felt I had to get involved with this.

```

Bytes	Content	Description

4		VFSR	Magic
4		2		Version (?)
4		114h	Length of Header
100h			Description
				Number of entries
4				?
xxxx			Data, ZLIB-compressed/stored
xxxx			Table, ZLIB-compressed
4				Uncompressed table length
4				Compressed table length


Decompressed Table

Bytes	Description

4		Data offset
4		Compressed size
4		Uncompressed size
4		Index to parent directory, -1 = root
4		Index of current directory or -1 (file)
2		1 		= entry is a directory
		2		= entry is a file
2		Compression flag
		0ffh	= directory
		0		= uncompressed
		1		= ZLIB compressed
4		Length of name including trailing zero
4		CRC/Garbage
x		File-/Directory name

```
