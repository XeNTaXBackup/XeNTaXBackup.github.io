## Post #1
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2011-06-17T14:44:59+00:00
- Post Title: Dungeon Siege 3 *.oaf file format

With the help of offzip/packzip and Raptor's extractor, I get know some format of *.oaf file, but still not know about everything. Do you guys have some idea about this?

Basically, the file has four parts: file header, zlib stream offset table, zlib stream, file name and tree structure table.

1). File header:
 0x0: 3 bytes. Magic number of *.oaf file. 'OAF'
 0x3: 9 bytes. Unknown. Maybe part of the magic number.
 0xC: 4 bytes. File name table entry offset.
0x10: 4 bytes. Unknown.
0x14: 4 bytes. Entry number. zlib stream should contain the same number of blocks as file name table.
0x18: 4 bytes. Unknown. Looks like some checksum.

2). Zlib stream offset table:
Each entry is 0x14 bytes, so this part should be 0x14 * EntryNumber. Some zeros bytes for alignment may be found after this part.
For each entry:
 0x0: 4 bytes. Zlib block start offset.
 0x4: 4 bytes. Unknown. Maybe related to the compression algorithm.
 0x8: 4 bytes. Raw data size. The unpacked data size in bytes.
 0xC: 4 bytes. Packed data size. If this field is zero, it means the raw data is not compressed.
0x10: 4 bytes. Unknown. Looks like some kind of hash related to raw data checksum.

3). Zlib stream.
Note that this part should align at 0x10 bytes, which means the start address of this part & 0xF = 0.
According to the offset table found in the 2nd part, we can dump each block of compressed data.

4). File name and tree structure
Relative directory and filename. Each entry is ended with 0x0 (string end). 

Do you guys know the unknown part which I listed?
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-17T15:06:30+00:00
- Post Title: Dungeon Siege 3 *.oaf file format

Header
    4B - MagicID ("OAF!")
    8B - Unknown - IMHO there is version, align type etc.
    8B - Offset to File list (64bit)
    4B - File count

Items - Aligned to 0x10
    4B - Unknown - maybe unique ID of file, CRC of filename, but it is not CRC of data
    4B - Data offset
    4B - Item Type - 0x10=zlib compressed, 0=not compressed
    4B - Uncompressed size
    4B - Compressed size - 0 if not compressed
