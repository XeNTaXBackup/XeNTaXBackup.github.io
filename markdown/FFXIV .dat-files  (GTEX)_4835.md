## Post #1
- Username: ShadowRoze
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 24, 2008 1:50 am
- Post datetime: 2010-08-03T14:45:30+00:00
- Post Title: FFXIV .dat-files  (GTEX)

Game: Final Fantasy XIV, Developer: SquareEnix, engine: Supposedly WhiteEngine/Crystal Tools. Platform: PC.

Hi, I have been trying to read the in-game icon images from FFXIV, but I cannot seem to find out how to read the pixels correctly, all my attempts this far have resulted in weird colored images, but the shape is right.
Leading bytes of a typical file:

```
#0000-0020:  00 00 00 18-00 00 00 40-00 00 00 00-00 00 20 00  .......@ ........
#0000-0030:  00 00 20 00-00 00 08 00-00 00 28 00-00 00 02 00  ........ ..(.....
#0000-0040:  00 00 2a 00-00 00 00 80-00 00 00 00-00 00 00 00  ..*..... ........
#0000-0050:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-0060:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-0070:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-0080:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-0090:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-00a0:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-00b0:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-00c0:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-00d0:  00 00 ff ff-ff ff ff ff-00 00 ff ff-ff ff ff ff  ........ ........
#0000-00e0 to end in submitted file.

```

[http://roze.ridorana.se/old/files/5F.dat](http://roze.ridorana.se/old/files/5F.dat) <-- full file
[http://pastebin.com/KBzwvNtU](http://pastebin.com/KBzwvNtU) <-- full file in hex.

Since I more or less suck at this kind of thing but tries anyway, I boldly ignored the header section, but I do think the following is more or less true:
int32@0x001E is widht
int32@0x0022 is height
int32@0x0026 is bytes per pixel, but I'm prob wrong here.


This is my work this far: RGBA is not listed, but tried and failed 
[http://roze.ridorana.se:8800/list2.html](http://roze.ridorana.se:8800/list2.html)
(Work down atm)

Any help towards rendering with correct colors is appreciated.

//Regards
## Post #2
- Username: ShadowRoze
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 24, 2008 1:50 am
- Post datetime: 2010-08-21T22:39:55+00:00
- Post Title: FFXIV .dat-files  (GTEX)

After a lot of reading and staring at numbers in different forms. I came to the conclusion that the GTEX-files are simply different texture compressions in one type of file. The header tells the compression used (among other things). The file posted is compressed using DTX1, treating all black pixels as transparent. I've also found files in raw format, simply RGBA-values. as well as DTX5 encodings.

However, there is some (extremely few) DTX1-files that deviate from the others and those my script fail to render.

final render of the file posted earlier. (I believe ^^ )


Regards everyone! hope this helps someone.

```
Byte   @ 0x0006:			 Content Format
Byte   @ 0x0007:			 Seems to be the number of mip-maps, May be zero in compressions not utilizing mip-maps.
Short  @ 0x000a-0x000b:	Texture Width
Short  @ 0x000c-0x000d:	Texture Height
Word   @ 0x0017-0x0020:	Data start/Header end
Word   @ 0x001e-0x0021:	Compressed width
Word   @ 0x0022-0x0025:	Compressed height (Might be something other)

Other byte is still undecoded, but seems unnessesary in this case.

```
