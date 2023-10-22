## Post #1
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-02-25T18:18:16+00:00
- Post Title: Front Mission 2 (PSX) Character Portrait Compression

While the vast majority of Front Mission 2's graphics are uncompressed on the game CD, it appears that the character portraits are compressed in a manner reminiscent of RLE compression, i.e., runs of identical bytes or repeating byte patterns are collapsed into just a few. However, it doesn't seem to be simple RLE and I can't find any sort of identifying marker at the beginning of the compressed graphics data that would indicate what type of compression is being used. I'm interested in the opinions and observations of this forum's veteran game resource investigators.

The following pics are three comparisons between the compressed data on the game CD (top) and uncompressed form as it appears in VRAM (bottom). Green bytes in the upper section of the examples are the compressed form of their expanded counterparts in the lower section of each example. Red bytes are identical in both the data on the game CD and in VRAM, meaning they are not compressed on the game CD.

[](http://imageshack.us)

[](http://imageshack.us)
This comparison is particularly interesting. Notice the compressed code 41 E9 04 from the game CD. This corresponds to four E9 bytes of uncompressed data, as if the compressed code specified that there would be four E9 bytes in a row.

[](http://imageshack.us)
Ah, you can see another instance of what appears to be near-straight RLE compression here. There's a compressed run that reads 40 08 03 in the upper portion of this pic, and it corresponds to an expanded run of 08 08 08 in the lower portion.

Another thing I've noticed is that the first byte in many runs of compressed data may have something to do with the uncompressed length of that run. For example, if a compressed run begins with the byte 9D, the uncompressed run has 31 bytes. Here's a list of equivalencies that appear in these examples:

9A: uncompressed run has 28 bytes
9B: uncompressed run has 29 bytes
9C: uncompressed run has 30 bytes
9D: " " 31 bytes.
A0: " " 34 bytes.

But this pattern doesn't hold all the time. I observe one compressed run beginning with 82 that has an uncompressed length of 10 bytes, and a compressed run beginning with C2 that has an uncompressed length of 30 bytes. Is it possible that the compression scheme being used here involves a mixture of compression techniques?
## Post #2
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-02-25T23:01:58+00:00
- Post Title: Front Mission 2 (PSX) Character Portrait Compression

There are other instances in the data where a run beginning with 0x41 is straight-RLE compressed. For example, there's a 41 00 04, which represents 00 00 00 00. This specific example isn't pictured, but it's interesting. Given that there's a 40 08 03 in one of the posted examples, and that uncompresses to 08 08 08, we have...

40: Tells whatever device is responsible for decompression that the next two bytes represent RLE compression with an uncompressed run of 3 bytes.

41: " " the next two bytes represent RLE compression with an uncompressed run of 4 bytes.

Could the first byte of any compressed run be an opcode of sorts, perhaps? The general magnitude of its value might determine the type of compression used, and its exact value indicates the uncompressed length as well. The bytes after the opcode determine the content of the uncompressed run. Anyone ever see a compression method like this before?

EDIT: Okay, I've found a file identifier for the compressed portrait files. In ASCII, it's PB.., or in hex, 50 42 00 00. This header does not exist in the uncompressed equivalent. It's within the realm of possibility that this "header" is actually the uncompressed file size, but I'm not so sure. Does compressed data typically begin by specifying the uncompressed file size?
