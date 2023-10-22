## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-08-07T18:33:56+00:00
- Post Title: PSP Mai-HiME Bakuretsu! unknown compression

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-08-12T03:33:26+00:00
- Post Title: PSP Mai-HiME Bakuretsu! unknown compression

I have almost uncompressed this, but I haven't been able to figure out this completely.

(Anything is little endian).

Header
4 bytes: "Wb16" ASCII string
4 bytes: Uncompresed file size

Custom-LZSS Compressed blocks (Come immediately after the header).
4 bytes:  Compression flags.
32 * 2 bytes: Compressed data.

The "compression flags" are interpreted from the LSB to the MSB (e.g. check compressionFlags & 1).

Compression flags: case 1
2 bytes: Uncompressed data.

Compression flags: case 0
2 bytes: Encoded position + length.

I believe that the encoding used is the following: 5 bits for the length and 11 bits for the position.

```
bufferDataPos = ((data >> 5) & 0x7FF);

```


The length is in groups of uint16_t's, so just multiply it by 2 to get the number of bytes.

---

I'm stuck with the position bits. I believe that they use a buffer of 0x2000 uint16_t's (0x4000 bytes) initialized to zero, like in this implementation.

[http://www.programmersheaven.com/downlo ... pView.aspx](http://www.programmersheaven.com/download/2260/4/ZipView.aspx)

However, even if the uncompressed result is pretty good, it seems to be wrong. I've tried different buffer initial positions (variable "r" in that implementation) without success.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-08-14T07:16:55+00:00
- Post Title: PSP Mai-HiME Bakuretsu! unknown compression

Thanks for you help GameZelda! I try to decmpress the first 2K data manually and it seems to work fine!

Strange enough the position are in +ve value!? Anyway, I'll try decompress them all to see if any special case there!
