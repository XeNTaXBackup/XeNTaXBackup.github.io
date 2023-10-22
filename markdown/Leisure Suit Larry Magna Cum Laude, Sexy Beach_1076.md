## Post #1
- Username: ykrylov
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-03T10:18:59+00:00
- Post Title: Leisure Suit Larry: Magna Cum Laude, Sexy Beach

Does anybody know in which format are 3D-models, textures from this games? 

What is *.pp format ?  

Thanky in advance! 

PS. Sorry for my lousy english.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-04T10:57:57+00:00
- Post Title: Leisure Suit Larry: Magna Cum Laude, Sexy Beach

Hi mate,

I have just got a copy of this game, and have analysed the following archives...

```
| Leisure Suit Larry: Manga Cum Laude *.afs |
+-------------------------------------------+

// NOTES: Each file, and the directory, are padded to multiples of 2048 bytes using null bytes
// So, the first file will start at offset 2048, or 4096, etc, and similarly with the next files.

4 - Header (AFS + null)
4 - Number Of Files

// for each file
  4 - Offset
  4 - Length

4 - Filename Directory Offset

// go to filename directory offset

// for each file
  32 - Filename (null)
  4 - File Type ID
  2 - Unknown
  2 - Unknown
  2 - Unknown
  2 - Unknown
  4 - Junk (matches each value in the directory, including offsets and sizes, in order)


+-------------------------------------------+
| Leisure Suit Larry: Manga Cum Laude *.jam |
+-------------------------------------------+

4 - Header (JAM2)
4 - Unknown
4 - First File Offset
4 - Header 2 (none)
12 - null
2 - Number Of Filenames
2 - Number Of Extensions

// for each filename
  8 - Filename (null)

// for each extension
  4 - Extension Name (null) // the first extension is all nulls

// NOTE: Some files have invalid offset - only allow offsets >= FirstFileOffset

4 - Unknown

// for each file
  2 - Filename ID
  2 - File Extension ID
  4 - Offset


// at each file offset
4 - Compressed File Size
4 - Decompressed File Size
4 - Unknown
4 - Unknown
4 - Unknown
4 - Unknown
4 - Unknown
4 - Unknown
X - File Data
0-3 - Junk padding to a multiple of 4 bytes
```


I am not sure which files are specifically the 3D models, but I do know that they are probably in the JAM archives, and are one of the *.aXX files. 

Good luck, let us know if you would like MexCom support for this format, and we will make up a script for you.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2011-12-13T03:39:50+00:00
- Post Title: Leisure Suit Larry: Magna Cum Laude, Sexy Beach

Using Dragon Unpacker (Its easy to find and get, just google it) I discovered that the LoadScrn.JAM contains the textures and associated files for each girl, which means the models are probably there too. The textures are in .dds format, which don't need to be converted into anything if you don't want to. The other files are:

GIR(Girls's Name Here).AGD
GIR(Girls's Name Here).AGM
GIR(Girls's Name Here).AGN
GIR(Girls's Name Here).AGS
GIR(Girls's Name Here).AGT
GIR(Girls's Name Here).AKC
GIR(Girls's Name Here).AKW
GIR(Girls's Name Here).ASB
GIR(Girls's Name Here).ASD
GIR(Girls's Name Here).ASN
GIR(Girls's Name Here).WGG
G(Single Letter)WANDR1.WKA

I don't know why everybody says there are AFS model files, I haven't seen any AFS files in any of the archives in this game.
