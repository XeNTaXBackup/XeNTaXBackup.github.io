## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-01T16:25:26+00:00
- Post Title: Precomp

Precomp is a command line precompressor. You can use it to achieve better compression on some filetypes (works on files that are compressed with zLib or the Deflate compression method). Precomp tries to decompress the streams in those files, and if they can be decompressed and "re-"compressed so that they are bit-to-bit-identical with the original stream, the decompressed stream can be used instead of the compressed one.

The result is a .pcf file (PCF = PreCompressedFile) that contains more decompressed data than the original file. Note that this file is larger than the original file, but if you compress it with a compression method stronger than Deflate, the compression is better than before. 

[http://schnaader.info/coding/precomp/precomp.html#d](http://schnaader.info/coding/precomp/precomp.html#d)

Time to test
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-02T10:12:48+00:00
- Post Title: Precomp

I tested with some games prepacked with zlib and works great
