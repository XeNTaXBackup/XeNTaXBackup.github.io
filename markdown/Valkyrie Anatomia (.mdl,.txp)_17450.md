## Post #1
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2017-12-23T07:07:50+00:00
- Post Title: Valkyrie Anatomia (*.mdl,*.txp)

Hi everyone,  I want request to extracting the 3D model files.
anyone can help me?

*Renarii's extract apk files (filename already Base64 decoded)
[https://mega.nz/#!9JVFGC4D!xeA3Vl5JT3hE ... cGB91huGLU](https://mega.nz/#!9JVFGC4D!xeA3Vl5JT3hEJ-bQmYVVr9HUldeNJRCrgcGB91huGLU)

I think a model datas in "ObjectModel" directory.
*.txp files maybe texture file, *.mdl files maybe mesh files.
especially, txp file header a like ctpk files.
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-12-27T10:02:16+00:00
- Post Title: Valkyrie Anatomia (*.mdl,*.txp)

.PCK structure is easy:

```
0x04 - Should be 0x80, if not, then it's different PCK file
0x10 - File descriptor (136 bytes)
0xYY - Files data

```


File descriptor data:

```
0x04 - File size
0x08 - Char[128] - file string. Allocated 128 bytes

```


Files data:

```
UNKNOWN
EOF - Looks like additional file information. Maybe multi-archive format or something?

```


Oh! found something interesting: Fbx7thExport.py
Textures turns to be TARGA .TGA


Sounds are unknown header, but inside it has FMT. I'm pretty sure FMT sounds are playable and extractable by some neat tool somewhere here.

Many .DAT files are compressed. Those files have MAGIC 0xBDDBC20B ALWAYS. I don't know what compression is that. Not LZS-like. In 0xC it has some size that is always smaller than aboslute file size. Maybe unpacked size? Therefore it may look like it's not compression but obfuscation. 


TXP files:
GLTP magic at 0x5. Example:
ObjectModel/ms031_Dwolf/00_00.txp - see 0x25 to 0x3B:
00_DWolf_XR ( 0x04) bodyg ( 0x05 ) a.tga
String has no terminator. Last byte is 0x84. Hmph, weird.

I couldn't export textures. Tried 8BPP, 12BPP, 16BPP, 32BPP, DXT1, DXT3. Nothing.

MDLs are also complicated. Couldn't find anything. This may need heavy reverse engineering
