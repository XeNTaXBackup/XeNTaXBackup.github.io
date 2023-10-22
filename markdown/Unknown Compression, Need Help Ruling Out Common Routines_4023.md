## Post #1
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2010-01-07T18:55:35+00:00
- Post Title: Unknown Compression, Need Help Ruling Out Common Routines

Hey all, I'm investigating a circa 2001 Windows PC game that I believe uses a proprietary graphics compression algorithm, and that the compression could possibly be easy to figure out. However, I've been bothered by the "[ijl10.dll](http://www.thevbzone.com/d_DLL.htm)" Dynamic Link Library sitting in the same folder as the game's executable. Due to the presence of the dll, I guessed at first that all or some of the game's image files were compressed with JPEG compression. However, visualizing the raw compressed file with a 16bpp codec in TileMolester, this compression doesn't look like anything having to do with JPEG to me.

I'll proceed to detail what I know of the compression algorithm's characteristics. What I'm interested in are everyone's opinions on whether JPEG compression is even a remote possibility here, and furthermore whether anyone wants to take a guess as to whether the compression could involve huffman encoding, or whether it might be something much more easily dealt with.

Below is a screenshot showing a decompressed image, with a sample from the compressed file inset. I've confirmed through experimentation that the visual matchup suggested by the red circles is approximately correct -- the parts you can understand visually in the compressed file are truly literally-encoded pixels.


The literal pixels are encoded in 16 bits-per-pixel, RGB format. So, two bytes per pixel. Now, the pixels in the compressed file that appear visually as really bright colors or otherwise interrupt the literal image are probably some sort of compressed packets or decompression instructions, and I believe they may also be stored two bytes apiece -- or maybe four bytes apiece, since I'm having trouble finding a compression instruction that isn't at least "two pixels long" when the file is visualized as a 16bpp image.

The file is encoded in Little Endian byte order and all literally encoded pixels have a value of FF7F or below (since it's Little Endian, "7F" is the high byte and "FF" is the low byte, so a human would read it as "0x7FFF"). The compressed packets/decompression instructions all have a value of "0080" or above (again, we would read that as "0x8000"). 

What I'm thinking is, the game developers made some kind of proprietary compression scheme that took advantage of the fact that they only needed about half the colors available in the entire [High Color](http://en.wikipedia.org/wiki/Highcolor) range. In other words, I suspect that the decompressed images use colors 0000 ~ 7FFF, for a total of 32,768 colors, which sounds is more than satisfactory for a game released in 2001. Values 8000 ~ FFFF, then, are interpreted by the game as decompression instructions.

Interestingly, if the literally encoded pixels are nulled (well, "blacked", since I just overwrote them with the bytes 0000), the decompressed image will display with the change. If the compressed packets/decompression instructions are nulled, however, the game freezes at the point the image is to be displayed. So something must be telling the game to expect compressed packets at specific offsets, and it freaks out when it doesn't find them. There are a ton of pointers sitting at the very beginning of the image, so I think I'll try following them and see where they lead.


This is the first PC game I've looked at in depth, so I have some questions about proper tools to use (like whether there's a really good memory dumper that dumps only a game's memory and not all of Windows memory, that sort of thing); but I'll hold off on that in lieu of the JPEG question. It seems silly to ask about the possibility that this could have anything to do with JPEG compression after what I described (not to mention, the compressed files have none of the JPEG standard header material), it's just that the dll was bothering me. The game appears to use a BASS dll for music playing in most cases, and a BINK dll for its movie files, so I keep wondering whether there might be something in the Intel JPEG library that could be useful to whatever decompression scheme is happening here.
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-01-08T11:42:45+00:00
- Post Title: Unknown Compression, Need Help Ruling Out Common Routines

That doesn't look like JPEG. Can you post an example of the data file containing the graphics?
## Post #3
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2010-01-08T21:01:21+00:00
- Post Title: Unknown Compression, Need Help Ruling Out Common Routines

I was just hooked up with a program that reads this game's graphics, so problem solved. I love it when fortune smiles!   If anyone's working on games made in Asian countries (for translation projects, for example) and needs to view, edit, and re-import graphical elements representing text,  [RPGViewer](http://blog.csdn.net/vbvan/archive/2007/11/01/1860825.aspx) is a good first place to check! 

As far as the file structure is concerned, in case anyone is academically interested in obscure image encoding methodologies, I discovered that it consisted of mostly literal pixels arranged into some kind of packets of varying lengths. Using some made-up offsets to illustrate the encoding routine:

0x00: Pointer to the second packet @ 0x5C
0x01 ~ 0x5B: String of byte pairs to be written literally, the "first packet"
0x5C: Instruction to write the next byte pair twice
0x5D ~ 0x5E: Byte pair to be written twice, the "second packet"
0x5F: Pointer to the next packet @0x66
0x60 ~ 0x65: String of byte pairs to be written literally, the "third packet"
0x66: Pointer to the next packet @0x8A
0x67~0x89: String of byte pairs to be written literally, the "fourth packet"

...and so on and so on. It basically functions as an obscure form of run length encoding I think, but there are a few more commands I was in the process of investigating before I dropped it in lieu of a program that already handles the decompression very well. I found it strange that many "packets" are just series of literally-encoded pixels (confirmed this via trial and error tests). The pointers interspersed between packets may be necessitated by the fact that only one byte is ever used to represent a pointer to the next packet -- placing a limit on the pointer value of 0xFF -- or it could have something to do with the functions I hadn't studied yet.
