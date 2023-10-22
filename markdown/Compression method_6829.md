## Post #1
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-06-21T19:40:42+00:00
- Post Title: Compression method

Hi guys, I need help with one compression method. It is little complicated, but the method seems to be familiar.
Check attached file, there is compressed and uncompressed file.


 data.zip
(897 Bytes) Downloaded 30 times



What I know about structure:
4B - Compressed/Uncompressed size (based on compression type)
4B - Compression method (1 = looks for RA MagicID etc.)
2B - MagicID ("RA")
2B - ?? (Version?)
4B - Compressed size
4B - No idea

Then starts data block with little encrypted control values. Like from LZW if I remember (or RLE?)
0x40B - control bytes

Then starts compressed data block.

I can't fully compare this, but inside exe I found some strange code that decrypts control block to new bytes, then use bytes to decompress data block. It is simmilar like in RLE or LZW (can't remember) where it just read byte then just copy existing values from buffer.

If someone know if it is something easy to decrypt, please let me know. Anything could help me.
