## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-05-10T14:31:16+00:00
- Post Title: King of Fighters 2002 (PS2)

Just trying to figure out how the sprites are compressed.  Later SNK games store sprite data as tiles which are assembled later, so I actually have a compressed sprite and an uncompressed one for comparison.

Edit: I made an error and included the wrong files, sorry.  Reuploaded with the correct ones.
[2K2Samples.zip](https://xentaxbackup.github.io/file/4223_2K2Samples.zip)
## Post #2
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-05-10T22:54:27+00:00
- Post Title: King of Fighters 2002 (PS2)

Slight update, I figured out part of the header.

First four bytes is some kind of signature, every sprite starts the same way.  The next four bytes are
Tile size?
Width (in tiles)
Height (in tiles)
Unknown

After that is a bitwise map of the sprite (Width) bytes in length such that starting from the highest bits, each 1 represents a tile that is present for that row.  This matches the sprite headers I found for 2k2UM almost exactly.

[http://www.justnopoint.com/lbends/junk/P00015.bin](http://www.justnopoint.com/lbends/junk/P00015.bin)
This file contains some image tiles used in 2k2UM, as a reference.  Every 128 byte block is a 16x16x4 image tile.
## Post #3
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-05-13T19:33:16+00:00
- Post Title: King of Fighters 2002 (PS2)

I threw up a few more examples as a reference, I think I'm getting somewhere.

[http://www.justnopoint.com/lbends/junk/kyotiles1.bin](http://www.justnopoint.com/lbends/junk/kyotiles1.bin) [http://www.justnopoint.com/lbends/junk/2k2kyo1.bin](http://www.justnopoint.com/lbends/junk/2k2kyo1.bin)
[http://www.justnopoint.com/lbends/junk/kyotiles10.bin](http://www.justnopoint.com/lbends/junk/kyotiles10.bin) [http://www.justnopoint.com/lbends/junk/2k2kyo10.bin](http://www.justnopoint.com/lbends/junk/2k2kyo10.bin)

Seems like 0xc_ and 0xd_ are opcodes of some kind, 0xc1 says to output the next byte, while 0xca - 0xcf output 2-7 bytes of 0x00.  They take a second byte but I know not what it does.  0xd_ seems to copy data from the output buffer somehow.
