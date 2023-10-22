## Post #1
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2008-09-30T13:46:27+00:00
- Post Title: Mercenaries 2 .WAD file.

Hey, can anyone here make a unpacker\packer for this kind of file???

i´ve attached the file, thx for the attention!!   
[Loading.zip](https://xentaxbackup.github.io/file/1669_Loading.zip)
## Post #2
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-09-30T15:26:51+00:00
- Post Title: Mercenaries 2 .WAD file.

Ok, pretty simple format. Although it does in fact have a checksum if not 2.

The header is organized in blocks, each block has a header 4 characters, and is 12 bytes long. The data is compressed, but I don't know how. The first checksum seems is simple, XOR operation, or maybe crc not sure. The second is the big blob of data after the header blocks. I'm not sure what it is exactly, but it's not long enough to be RSA, so it could be SHA1s.

Unknown
Index
Data
Checksum
Assets
Paths

Here is a layout:

```
4 - Unknown - Int32
8 - Unknown - Int32

12 - IndexBlockHeader - Chars(4)
16 - IndexOffset - Int32
20 - IndexEntryCount - Int32

24 - DataBlockHeader - Chars(4)
28 - DataStartOffset - Int32
32 - Unknown - Int32 // Something todo with Compression?

36 - ChecksumBlockHeader - Chars(4)
40 - Unknown - Int32
44 - ChecksumCount - Int32

48 - AssetsBlockHeader - Chars(4)
52 - AssetsIndexOffset - Int32
56 - AssetsEntryCount - Int32

60 - PathsBlockHeader - Chars(4)
64 - PathsStartOffset - Int32 // Null terminating strings
68 - PathsEntryCount - Int32

// The block of data under this at offset 72 seems to be some sort of hash.
// It looks like 3 hashes of 48 bytes each, if that has anything todo with the Checksum block.

// Index
public struct IndexEntry
{
    // None of these match the length of any entry's in the Paths Table
    public int Unknown;
    public int Unknown2;
    public int Unknown3;
}

// Assets
public struct AssetEntry
{
     //No offsets or sizes
     public int Unknown;
     public byte[] Null; // 6 bytes
     public short Unknown; // Maybe Enum?
     public int Unknown;
}

// Data
// Data seems to be compressed, and has an identifier in the header of each file "sges" a google search turns up 
// nothing about compression or formats related to it.
```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-09T16:16:23+00:00
- Post Title: Mercenaries 2 .WAD file.

old thread but I downloaded the demo of this game casually only today and after having done the work I noticed this thread opened so...
[http://aluigi.org/papers/bms/mercs2.bms](http://aluigi.org/papers/bms/mercs2.bms)

a small note: the archived files are not "normal" files but are contained in a certain UCFX container that looks easy to handle, for example in some of them there are also the full filenames (with the full original path!) and are usually headerless dds while others have a "data" field with zlib compressed data.
