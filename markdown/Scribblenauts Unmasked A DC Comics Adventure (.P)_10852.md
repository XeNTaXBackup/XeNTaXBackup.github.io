## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-07T15:01:19+00:00
- Post Title: Scribblenauts Unmasked: A DC Comics Adventure (*.P)

Well *.P (Archives) contains only the file data.

Also in game directory you can found 2 files: index.bin and pmindex.xml.

index.bin

```
{
 	DWORD pTotalFiles;
};

struct pIndexEntry
{
 	DWORD pHash;
 	BYTE pArchiveNum;
 	BYTE pType; // can be 0 and 6... 0 - not compressed, 6 - compressed (zlib)
 	DWORD pOffset;
 	DWORD pZSize;
 	DWORD pSize;
};
```


in the end of file we can see archive names

ArchiveNum's :

```
1 -> 1.p
2 -> 2.p
3 -> audio.p
4 -> ui.p
```

pmindex.xml
Contain only file names, hashes and type's. Hash algo used FNV.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-07T19:20:51+00:00
- Post Title: Scribblenauts Unmasked: A DC Comics Adventure (*.P)

Well here simple unpacker.   


[DL_Link.rar](https://xentaxbackup.github.io/file/6684_DL_Link.rar)
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-10-24T01:40:20+00:00
- Post Title: Scribblenauts Unmasked: A DC Comics Adventure (*.P)

Thanks for the unpacker, time to test
