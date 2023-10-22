## Post #1
- Username: Bean387
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 27, 2011 6:50 am
- Post datetime: 2011-02-26T23:03:02+00:00
- Post Title: Compressing N64 roms to romc format

I'm new, but I'd like to get the ball rolling on reversing hcs' romc decompressor, romchu, and giving it the ability to compress N64 roms into romc format.  I'm combing over the source code now, but I'm not sure where to start exactly.  Any help would be appreciated.

[http://hcs64.com/files/romchu06.zip](http://hcs64.com/files/romchu06.zip)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-03-03T02:46:45+00:00
- Post Title: Compressing N64 roms to romc format

Fyi you don't need to use the type 2 compression in order to compress roms for those games, you can use the existing type 1 compressor.

For a similar compression and decompression you might look at lzh8_cmpdec: [http://hcs64.com/files/lzh8_cmpdec08.zip](http://hcs64.com/files/lzh8_cmpdec08.zip)
That gives a compressor and decompressor for "LZH8", which is LZ77+Huffman for 8-bit symbols.  It's a lot better documented than romchu.
Type 2 romc has a [canonical Huffman code](http://en.wikipedia.org/wiki/Canonical_Huffman_code) instead of the serialized tree LZH8 uses (inherited from Huf8), which is fortunate as that method is pretty ugly.  It also works with 0x10000 byte chunks (possibly more if a backreference goes beyond this) to better adapt to changing data profiles, where LZH8 deals with the whole file at once. Additionally each 0x10000 byte chunk may be given uncompressed if it would have inflated.
