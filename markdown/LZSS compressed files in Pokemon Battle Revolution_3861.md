## Post #1
- Username: Poryhack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 12, 2009 8:40 am
- Post datetime: 2009-11-12T19:59:56+00:00
- Post Title: LZSS compressed files in Pokemon Battle Revolution

I was hoping to examine some files in Pokemon Battle Revolution (PBR), but most of the files are compressed in a way that I have not been able to decompress with any of the standard Nintendo schemes (both variants of LZ77, RL, and Huffman). Each compressed file begins with "LZSS" so I believe it would be a safe to assume that it uses a variant of that compression scheme.

I have made a couple basic observations, but I don't think I'd be able to puzzle out how to decompress these files on my own, hence this topic.

In traditional GBA/NDS/Wii compressed files there is a 4-byte header, the first byte of which specifies a compression method and the last 3 which give an decompressed filesize. The header in this case is preceded by "LZSS".
The compression method byte on these files is left blank (00).
The decompressed filesize seems to be big-endian.

You can download a sample file [here](http://dl.dropbox.com/u/258536/ending.001). As many more as you need are available on request.

I'd be incredibly grateful to anyone who figures this out.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-12T20:34:15+00:00
- Post Title: LZSS compressed files in Pokemon Battle Revolution

yes it looks just lzss (although I'm not 100% sure) with the only difference that the initial value of the sliding window doesn't seem to be the classical "space" char but a null one.
the following quickbms script does the job:

```
comtype lzss "12 4 2 2 0"
idstring LZSS
get SIZE long
get ZSIZE long
get DUMMY long
savepos OFFSET
math ZSIZE -= OFFSET

get NAME filename
string NAME += ".unpacked"
clog NAME OFFSET ZSIZE SIZE
```
