## Post #1
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-03-09T23:45:37+00:00
- Post Title: Extreme G III Racing Help? .RB B File

I wasn't sure if I should post here or on another topic.

I'm trying to figure out how this .RBB file is packed it's from a gamecube game I'm trying to learn how to reverse engineer it so I can extract the file and look at its contents.
I had asked on a few different forums and this guy's response was this

'The bytes at offset 0x10 are 78 DA, which hints very strongly to the zlib compression algorithm. 

```
0000000010: 78 DA 74 9D 0B BC 97 63 │ D6 F7 77 24 A9 B0 25 95  xÚt♂¼—cÖ÷w$©°%•
            ^^^^^
```


I use this small Python script to decompress zlib-compressed streams:

```
import zlib, sys
inf = open(sys.argv[1],"rb")
off = 0
if len(sys.argv)>3: off = int(sys.argv[3],16)
inf.seek(off)
cdata = inf.read()
# auto-detect zlib/gzip/deflate
# http://stackoverflow.com/a/22310760/422797
d = zlib.decompressobj(zlib.MAX_WBITS|32)
udata = d.decompress(cdata)
udata += d.flush()

clen = len(cdata) - len(d.unused_data)
ulen = len(udata)

open(sys.argv[2],"wb").write(udata)
print("%d -> %d; end of data: %08X" % (clen, ulen, off+clen))
```


If I use it like this:

```
unz.py CITY.RBB CITY.UNP 10
```


It decompresses Nicely

```
3696259 -> 7113808; end of data: 00386693
```


And the output has some structure

```
0000000010: 00 00 00 01 02 00 00 02 │ 00 00 00 50 00 6C 8C 10     ☺☻  ☻   P lŒ►
0000000020: 00 00 00 10 00 00 00 01 │ 00 00 00 00 00 00 00 00     ►   ☺
0000000030: CA 60 FA A2 42 43 52 00 │ 00 00 00 00 00 00 00 61  Ê`ú¢BCR        a
0000000040: 58 58 58 58 58 58 58 58 │ 58 58 58 58 58 58 58 58  XXXXXXXXXXXXXXXX
0000000050: 00 00 00 00 00 0D C4 6C │ 00 55 35 E0 00 61 3E 30       ♪Äl U5à a>0
0000000060: 00 63 79 F0 00 01 30 D3 │ 00 00 43 C7 00 03 02 14   cyð ☺0Ó  CÇ ♥☻¶
0000000070: 00 00 8E F0 00 00 C1 7E │ 00 00 00 00 00 00 00 00    Žð  Á~
0000000080: 00 61 3E 30 FF FF FF FF │ C3 7C D3 18 C2 B4 AF 10   a>0ÿÿÿÿÃ|Ó↑Â´¯►
0000000090: C4 74 57 67 C4 FB 0A 00 │ C4 A2 0D 4B C4 F5 E2 F3  ÄtWgÄû◙ Ä¢♪KÄõâó
00000000A0: 44 BB D5 3A 44 8B 77 68 │ 41 45 C6 00 00 00 00 00  D»Õ:D‹whAEÆ
```


However, making sense of it may require you to look at the game code.

[https://dl.dropboxusercontent.com/u/227520696/CITY.RBB](https://dl.dropboxusercontent.com/u/227520696/CITY.RBB) <-- Sample File
