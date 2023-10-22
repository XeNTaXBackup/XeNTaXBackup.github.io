## Post #1
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-03-12T11:21:13+00:00
- Post Title: Hitman (2016) *.RPKG files [REQUEST]

Hello,
I want to extract files from new Hitman game, but script for Absolution from Aluigi don't work. Can someone please help me?

There is example of the files: [https://mega.nz/#F!uVUA2YKD!KOKRyKzgInfzZNDr5GggRw](https://mega.nz/#F!uVUA2YKD!KOKRyKzgInfzZNDr5GggRw)

THX
## Post #2
- Username: foobarwtf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 03, 2016 3:45 am
- Post datetime: 2016-03-15T04:09:26+00:00
- Post Title: Hitman (2016) *.RPKG files [REQUEST]

The new hitman uses denuvo, I don't think anyone can do anything about it right now...
## Post #3
- Username: faqy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2009 5:30 pm
- Post datetime: 2016-03-16T09:04:59+00:00
- Post Title: Hitman (2016) *.RPKG files [REQUEST]

This is what i found.

```
long		num
DWORD		records_size
DWORD		flinfos_size
record[num]{
	UINT64		guid
	INT64		data_offset
	DWORD		unkow
}
flinfo[num]{
	char[4]   type
	long     info_size
	byte[4]   unkow
	long     fl_size
	long		compressed_size
	long		unkow
	byte[info_size]
}
```

Most file data seems to be encrypted also compressed. I cant figure it out.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-03-16T12:01:33+00:00
- Post Title: Hitman (2016) *.RPKG files [REQUEST]

```
{
   uint32_t   dwID; // Always GKPR
   uint32_t   dwTotalFiles;
   uint32_t   dwResourceTableOffset; // Table with headers for files
   uint32_t   dwResourceTableSize;
};

struct RPKGEntry
{
   uint64_t   dwHash; // Filename hash
   uint64_t   dwOffset;
   uint32_t   dwZSize; // dwZSize & 0x3FFFFFFF
}

struct RPKGResources
{
   uint32_t   int dwType;
   uint32_t   int dwReferencesChunkSize;
   uint32_t   int dwStatesChunkSize;
   uint32_t   int dwDataSize;
   uint32_t   int dwSystemMemoryRequirement;
   uint32_t   int dwVideoMemoryRequirement;
};
```


Simple data obfuscation are present in release version.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-03-20T10:47:46+00:00
- Post Title: Hitman (2016) *.RPKG files [REQUEST]

[http://aluigi.org/bms/hitman_2016.bms](http://aluigi.org/bms/hitman_2016.bms)
