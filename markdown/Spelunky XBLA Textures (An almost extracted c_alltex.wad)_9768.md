## Post #1
- Username: Tanks
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 23, 2010 9:23 am
- Post datetime: 2012-10-20T22:55:45+00:00
- Post Title: Spelunky XBLA Textures (An almost extracted c_alltex.wad)

So, a friend of mine took a look into a certain set of files I sent on over to him from a Spelunky extract I was looking into. Basically, the \Textures\ folder has a few uncompressed (quite possibly unused) textures in .dds format. But there's a ~60 MB file called c_alltex.wad which houses all the sprites seen in game. Its accompanied by c_alltex.wad.wix which appears to provide some offsets to files within c_alltex.wad. Here's a write up my friend here did after he managed to get some bits of it extracted:

> Reply from GuyPerfect via Jul
>
> Okay, I don't have everything figured out, but I've got a good lead.

c_alltex.wad is an archive file of sorts. It doesn't contain any directory information; it's just one big ol' box of file data.

c_alltex.wad.wix is a plain text file describing the directory information for the .wad file. It lists file names, the starting offset for the files in the aforementioned box of file data, and the length of the file. In theory. Since the lengths are redundant, adding the length for any one file with its offset will yield the offset of the next file.

Problem is, the .wad file isn't just a bunch of files stuck end to end. At least, not exactly. There's some additional processing going on that will still take some more investigation. I could spend a zillion hours on it, so what I'll do instead is give you the information and maybe one of your contacts might be able to take it to the next step.

The first file in the manifest, hudelements.png, specifies a starting offset of 0. Its actual starting location in the .wad file is 0x000004C2. Exactly what the data is before that, I haven't the foggiest. What I do know is that if you use the manifest to add the length of the file, which it claims is 219253 bytes (in decimal), you'll pretty clearly end up two bytes short of a new PNG file header.

Examining the IDAT chunk header of the first PNG file in the .wad, I found that the file does indeed think itself to be 219253 bytes in size, meaning there are two extra bytes somewhere in the IDAT chunk that shouldn't be there.

Extracting hudelements.png directly from the .wad produces this:



Not surprisingly, the image has an error. The CRC32 in the IDAT chunk won't match, and half of the image is missing. I hunted down the exact location in the PNG file where those two bytes were and removed them. The result looks a lot better:



The bytes removed were 00 00. Their location in the original .wad file was exactly 0x00020000.

The next file in the manifest, effects.png, is likewise broken when pulled straight from the .wad:



Again, there was a stray 00 00 near the top of the image. Their location in the .wad file? Exactly 0x00040000. Removing them cleared up the image for, you guessed it, another 0x00020000 bytes. However, THIS time there was something different.

At 0x00060000 in the .wad file, rather that 00 00 like there were before, this time it's 80 10. These two byte are followed immediately by 16 more bytes not from the original data; they represent 4 32-bit values. What do they mean? I don't know. How are they processed? I don't know. I was able to delete the whole set of 18 bytes, though, and it recovered some more of the image, but not all of it:



According to the .wix manifest, this file is 233946 bytes (decimal). According to the IDAT header of this file, it is indeed 233946 bytes. However, curiously, the next PNG file in the .wad doesn't begin until 463155 bytes later. The remainder of this image's IDAT chunk, its IEND chunk, the file header for the next file and some of that file's data are all encoded in some manner that can't be read verbatim from the .wad file.

PNG images are compressed with DEFLATE, the same algorithm that runs ZIP archives. It has a property such that the resulting compressed data has very low redundancy, meaning it's difficult to compress. The fact that the bottom of this image got wrapped in some other layer of encoding is out of the ordinary.

The .wad storage format doesn't seem to be used for encryption of any kind, since hudelements.png was all present in the file data plain as day. If it's used for compression instead, then the bottom of effects.png was able to be re-compressed and traversing the overarching pool of file data requires stepping through the .wad file one chunk at a time.

So to recapitulate...

• The .wad file represents a big pool of bytes
• The .wix file gives names to specific sections of that pool of bytes
• There are 0x4C2 bytes of mystery data at the beginning of the .wad file before the first file begins
• Every 0x20000 bytes in the .wad file, at least initially, is a 16-bit chunk header
- • If the header is 00 00, the chunk is not encoded and the bytes can be read as-is
- • If the header is 80 10, then 16 more bytes are present (4 32-bit values) and the chunk may have an alternate encoding
- • The header can be other values as well, but I haven't looked into it

The key to extracting files from the .wad archive (using the .wix manifest) is to find out how the encoding varies depending on the value of the 16-bit chunk headers. Like I said, though, I don't especially want to keep at it right now, but this should give you some helpful information towards getting the rest of it figured out. (-:

So if anyone wants to take a stab at it, it would be much appreciated. Here's the files in question:

[c_alltex.wad & c_alltex.wad.wix (mediafire 3x files)](http://www.mediafire.com/?2v5cdv3g83hsk)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-21T00:19:23+00:00
- Post Title: Spelunky XBLA Textures (An almost extracted c_alltex.wad)

interesting problem - and you made a good start!

i think the .wad data is most likely to be compressed using a run-length encoding algorithm - while there is bits of data you can extract - 15 png headers - there are 162 png files expected, and a suspicious data at the start of the file. while you can sort of extract some images, you'd need to reconstruct the entire file block expected by the .wix format to get the offsets and sizes to properly match. 

i'm unsure how to do it with an xbla application, but you'd need to try reversing the method from the game
[lobbyart.png](https://xentaxbackup.github.io/file/5908_lobbyart.png)
## Post #3
- Username: Tanks
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 23, 2010 9:23 am
- Post datetime: 2012-10-25T04:19:51+00:00
- Post Title: Spelunky XBLA Textures (An almost extracted c_alltex.wad)

Thanks for the help! Though I still have little to no idea where to go here. I mean, I wasn't the person who arrived at the original conclusion there after all...
