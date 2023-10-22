## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2014-06-18T23:23:30+00:00
- Post Title: Tales of Graces f .FPS4 and .tex help?

Since I can't create my own script I was wondering if someone could create a script to open the models and textures of Tales of Graces f. I think the models are FPS4 and the textures are .tex
I have tried to create my own script for them in Noesis but I do not know anything about binary x.x

[https://docs.google.com/uc?authuser=0&i ... t=download](https://docs.google.com/uc?authuser=0&id=0B6qG6uBULh2TT1pKSjZEUXlkZjQ&export=download)
## Post #2
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-19T13:24:01+00:00
- Post Title: Tales of Graces f .FPS4 and .tex help?

```
======

Byte { 4 } - Magic ID ("FPS4")
DWORD { 4 } - Number of files
DWORD { 4 } - Offset to file info table" (offset - 12)

> When seeked to "file info table"
Byte { x } - Filename with extension (nullterminated)
Byte { 37 } - File info (maybe filesize, fileoffset) <- I don't think any info about faces, vertices, imagewidth or BitsPerPixel is stored here
```

Models also contain bones. As I'm not familiar with skeletal-animation data, I've stopped researching here.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-19T17:01:50+00:00
- Post Title: Tales of Graces f .FPS4 and .tex help?

finding some submesh parameters is easy, just search for 00 00 00 01:

```

013D60                                       00 00 00 01
013D70  01 F4 03 64 00 00 00 01  00 02 FF FF 00 03 00 00
```

the following word 0x1F4 is the vertex count, 0x364 is the face indices count
succeeding 00 00 00 01 00 02 are face indices
so the submesh params are like this
868 face indices, 500 verts
------------------------------
vertex start address: 0xDA6C/ face indices start address: 0x13d74



TalesOfG.JPG (42.81 KiB) Viewed 153 times



same goes for the hands:
0x12770 554
Vb1
28 99
0x2410 294
121010
0x0 255

copy the above 6 lines into an empty text file, rename it to anyname.H2O and load it
and the mesh into hex2obj (view link in my sig)

for the body it seems to be a little bit different:

```

012BC0  01 25 01 1D 00 00 00 02  04 00 06 AD 00 FD 01 C2
```

behind 00 00 00 02 there's 1024 as a vertex count and 0x6AD = 1709, face indices count
0x12BCC supposed face indices start address
but using 0x4448 as vertex start addres gives a part of the body only and some weird faces.
## Post #4
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2014-06-19T21:40:04+00:00
- Post Title: Tales of Graces f .FPS4 and .tex help?

I'm kind of confused.... owo; Sorry Im just really bad with binary and stuff so yeah ^^"
