## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-03T16:11:26+00:00
- Post Title: DPK4/5 Utility

Has it really been that long since I first wrote UnDPK? In any case, there were requests for a program to pack a DPK4 file, so I wrote a new extractor with my GRAF Extractor Skeleton and added in bits to write the format.

DPK4 is a format used in games developed by Paweł Mrocheń, including various City Interactive games. This program can extract, create, and merge those archives. The program can be found on the tools blog: [blog/?p=1132](http://forum.xentax.com/blog/?p=1132)

Notes about the format:
- The engine validates the file size against the size in the header. If the file size is less than the size in header, the archive is rejected.
- The engine will only read the amount of file table that is specified in the header. It won't complain if there isn't enough data for the file count given, but it won't be able to find the remaining files.
- Each entry is 32-bit aligned. That means entries are padded with nulls as necessary. The entry size is specified with each entry, and acts sort of like a pointer in a linked list. The game won't complain if entries are not aligned, but misalignment may slow down access.
- Files are compressed with Zlib at standard compression level.
- Compressed size should be less than uncompressed size. If compressed size and uncompressed size are equal, the file is not compressed.

I've also made the tool for DPK version 5. It can be found on the tools blog: [blog/?p=1136](http://forum.xentax.com/blog/?p=1136)

Notes about the format:
- Never trust the length field. It is inaccurate for file sizes above the range of an uint, and can be different than length in archive if file is uncompressed and the engine wouldn't think anything of it.
- Flag values can only be 1 or 0, nothing else (so far).
- There's a new checksum field. It uses Adler-32. Not sure if the engine actually uses the value.
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-07T04:41:16+00:00
- Post Title: DPK4/5 Utility

If anyone's curious, here's a link to UnDPK, the predecessor of DPK4 Utility. [http://www.mediafire.com/download/7whsz ... /UnDPK.zip](http://www.mediafire.com/download/7whszfydhafon3w/UnDPK.zip)

It's written in AutoIt. Yeah. Did you know you can manipulate binary data in AutoIt? It's annoying, but it can be done. You can also embed assembly code, which is somewhat cool until Data Execution Prevention shuts it down.
