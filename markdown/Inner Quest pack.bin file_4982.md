## Post #1
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-06T06:41:28+00:00
- Post Title: Inner Quest pack.bin file

Inner Quest		pack.bin
some about format:

```
SIZE	LONG			0E 00 00 00
FLAG	SIZE	CHAR		RESOURCES PACK
	{
	SIZE	LONG
	NAME	SIZE	CHAR
	HASH	LONG		67 A0 BB 2C
	NULL	LONG
	0X0166	BYTE
	}
	{
	SIZE	LONG
	NAME	SIZE	CHAR
	HASH	LONG		1E AA 3F 11
	NULL	LONG
	0x140A	BYTE
	}
	SIZE	LONG
	NAME	SIZE	CHAR
	HASH	LONG		CA 8C EB 5F
	NULL	LONG
	0x4EDF	BYTE
	}
	...
}

```

how to comput the HASH.need get size by HASH.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-06T11:20:28+00:00
- Post Title: Inner Quest pack.bin file

This is the (possible) structure of the .bin files:

```
    -> ID_len : dword // (14)
    -> ID : char[ID_len] // 'RESOURCES PACK'
-> For each file:
    -> Name_len : dword
    -> Name : char[Name_len] // name of the file
    -> CRC32 : dword    // crc32 value of the original data
    -> Flag : dword // 0=zlib compressed  1 or 2 =not compressed
    -> OrigSize : dword  // the original size of the file
    -> StoredSize : dword // the compressed size (or the original size, if not compressed)
    -> file data : byte[StoredSize]
```
## Post #3
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-07T03:26:52+00:00
- Post Title: Inner Quest pack.bin file

i can't unpack this ,and thanks you support.
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-10T03:55:21+00:00
- Post Title: Inner Quest pack.bin file

Here's a QuickBMS script:

```
idstring "RESOURCES PACK"

savepos DirStart
goto 0 0 SEEK_END
savepos PAK_FILE_SIZE
goto DirStart 0 SEEK_SET
savepos ActPos
do
  get Name_len long
  getdstring Name Name_len
  get CRC32 long
  get Flag long
  get OrigSize long
  get StoredSize long
  savepos ActPos
  if Flag == 0
    clog Name ActPos StoredSize OrigSize
  elif Flag == 1
    log Name ActPos OrigSize
  elif Flag == 2
    log Name ActPos OrigSize
  else
    math ActPos -= 12
    string PosX p= "%08x" ActPos
    print "Unknown Flag: %Flag% at pos %PosX%"
    cleanexit
  endif
  math ActPos += StoredSize
  goto ActPos 0 SEEK_SET
while ActPos < PAK_FILE_SIZE

```
## Post #5
- Username: thesnow
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2010 1:52 pm
- Post datetime: 2010-09-10T09:41:45+00:00
- Post Title: Inner Quest pack.bin file

wow!

thanks!
