## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-03-30T16:42:51+00:00
- Post Title: RoboCop (2003) *.tpk files

[https://mega.nz/file/EDJBXDhY#fAS84mg9o ... IOHeabFdwc](https://mega.nz/file/EDJBXDhY#fAS84mg9osoxOuwmG5T5njnIFe7Ah-FBXIOHeabFdwc)

I got no filenames in RoboCop (2003) *.tpk files
Any ideas how to get the filenames?

Thanks in advance.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-03-30T20:18:38+00:00
- Post Title: RoboCop (2003) *.tpk files

Filenames in the first chunk at 0x800 offset.
## Post #3
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-05-11T17:01:51+00:00
- Post Title: RoboCop (2003) *.tpk files

To expand on what Ekey said. These files contain a 32 byte header, (usually) followed by a set of offsets that point to ZLib compressed blocks. If there are no offsets or the UseOffsets flag is not set, then there is a single compressed block at 0x800. After decompressing each of these blocks and concatenating* all the decompressed data, the first TPKHeader.FileInfoSize bytes will contain file structs which include the filenames. The remaining decompressed bytes are the raw blobs. 

* It is helpful to concatenate the blocks beforehand as the structs and blobs are not aligned and do span across multiple blocks! 

The header structure looks like this:

```
 {
   uint Magic; // TI\x01\x01
   int TotalDecompressedSize; // total size of all decompressed data
   int Unk08;
   int OffsetArrayStart; // absolute offset
   int OffsetArraySize; // in bytes, count = size / sizeof(int32)
   int Unk14;
   int FileInfoSize; // total byte size of all FileInfo structs, count = size / sizeof(FileInfo)
   TPKHeaderFlags Flags;
 }
 
 enum TPKHeaderFlags : uint
 {
   UseOffsets = 0x1, // if not set, a single block at 0x800 is expected
   Unknown02 = 0x2,
   DoNotFixNames = 0x4, // if not set, force FileInfo.Name to uppercase
   Unknown08 = 0x8
 }

```


And the file info structure looks like this:

```
 {
   string Name; // char[0xF0]
   int Offset;
   int Size;
   int Unk248; // checksum?
   int Unk252;
 }

```


Just to note, this game uses [Tagès](https://en.wikipedia.org/wiki/Tag%C3%A8s) DRM to encrypt all level file (NIV*.TPK) headers however they're still readable with a bit of bruteforcing. If one reads block offsets until they get a 0 and file struct's until an offset isn't sequential, then you have enough information to extract all the files.

If anyone wants an implementation, I have C# code for reading these files, including a workaround for the encrypted ones, [here](https://gist.github.com/barncastle/aed4cffe7e75631c6486865a6b6a59f6).
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-05-11T21:56:03+00:00
- Post Title: RoboCop (2003) *.tpk files

If you dont care about filenames at all.
you can just use offzip.exe from aluigi in tpk files, it should create all files extracted and decompressed, as per our friend say above, the game uses zlib compression.

If you want just do a simple unpack without decompression and then decompress the file separately you can use this script i wrote.
UNPACK TPK without decompress

```
GOTO 0X20
FOR

get offset long

savepos temp
get size long
if size == 0x00000000
xmath size "(file - offset)"
log "" offset size
break
endif
goto temp
xmath size "(size - offset)"
log "" offset size
next
```

decompress  unpacks files from script above.

```
get SIZE asize
get NAME filename
string NAME + ".dec"
clog NAME 0 SIZE SIZE
```


but like i said, the offzip do the job more fast.

I am attaching offzip with .bat to easy understand.

Font image from main


[ROBOCOP PACK-UNPACK.zip](https://xentaxbackup.github.io/file/22208_ROBOCOP PACK-UNPACK.zip)
## Post #5
- Username: Lotus06
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 20, 2022 4:12 pm
- Post datetime: 2022-09-20T08:39:57+00:00
- Post Title: RoboCop (2003) *.tpk files

Hello sir can you please help me identify what compression type was used on these .tpk files? We cannot edit anything until the tpk files are decompressed. If you can identify the compression type can you please also guide me how to decompress it?  @Rabatini

[https://drive.google.com/file/d/1TL4Vwv ... p=drivesdk](https://drive.google.com/file/d/1TL4Vwv0YCI58y1qPu0f5VEJ1HIiAVqai/view?usp=drivesdk)
