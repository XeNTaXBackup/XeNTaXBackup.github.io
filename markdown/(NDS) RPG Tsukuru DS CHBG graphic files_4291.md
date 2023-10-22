## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-04-02T10:26:09+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

These are almost viewable in TiledGGD with tiled mode set to 8x8. Colors are BGR and usually start at the offset 0xA, 2 bytes per color. The files all come with the extension "bin". I have so far seen no record of this format on any DS site but seems fairly simple, only problem is getting it to be assembled correctly.
[CHBG.rar](https://xentaxbackup.github.io/file/2907_CHBG.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-04-17T07:59:15+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Here's an almost perfect display. The image can be made out, the palette is correctly displayed. Everything is right... except for that the image is off.
[CloseButNo.png](https://xentaxbackup.github.io/file/2937_CloseButNo.png)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-04-21T04:51:45+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Updating, it seems like the image is pushed off center a bit in 8 pixel high pieces. Is there a way to fix this?
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-05-08T19:55:53+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Still made no progress. I've tried just about every setting and still nothing.
## Post #5
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-08T21:54:50+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Looks like some sort of compression is going on, there are quite a few tiles missing that are probably all one color--I showed them by making them green.



missingdata.png (5.77 KiB) Viewed 169 times



**actually they aren't skipped, the tiles are used as a palette... 

ColorPalette @ 0x10
Image @ 0x110
TilePalette @ 0x110 + numTilesInImage
## Post #6
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-09T00:39:04+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

I realized I was running into the same problem with another game, so I searched around for a comparable format.

[http://dev-scene.com/NDS/DOCgraphicmodes](http://dev-scene.com/NDS/DOCgraphicmodes)

Looks like what we are seeing here is the Rotation Background type.  Maybe a new setting in TGGD is in order.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-05-11T15:31:37+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

I see, thanks. But does this mean there is currently no means to view it without manually reassembling?
## Post #8
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-11T19:37:13+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Yeah 

I did play around with TGGD and got it to work by adding in some code, I'll see about cleaning that up and submitting the change to Barubary.
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-17T17:49:00+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Im going to make a rough guess, but according to the images posted here it seems like they have a block compression scheme,
such as , if the encoder detects 8x8 pixels has the same color, it will replace this block with something like 2 bytes,
the first byte would say that the block is compressed, and the second byte says what color the block should be filled with when decompressed.

For example, say that color 255 is unused, then they would use the value 255 for telling the decompressor that the following block is compressed.
So this should be fixable without manual rearranging the images.
## Post #10
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-17T22:56:04+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Nope, it's exactly as the doc I linked stated.  There are 3 sections of the file: palette (if needed), list of tiles (8x8 pixels in this case) that use the palette as a CLUT, and then an array of indices into that tile list to make up the complete image.

I've already added in code into TGGD to use the indexed tiles, but it hasn't been made as nice as the original program yet... to do it properly you'd have to extend the entire app to handle a 3rd data section of the file which would touch almost every part of the code.

If you don't mind a buggy app that will crash if you give it incorrect info, then I guess I could give you what I've already got.

** I went ahead and made my hacked version "less crashy" and "more usable".  Let me know if this exe is usable--put it in the folder of your TGGD, and possibly rename it to something other than the original filename.  But by all means, it's not a good final fix. (This shouldn't affect any other functions of TGGD btw)

I included a README.txt that just warns you to use at your own risk, but I believe this program is pretty harmless.  Also, a rundown of the bin/CHBG format that I figured out so far.

> the bin files are either 4 or 8bit tiled bgd images.
>
> 
>
> Format as follows:
>
> 0x0 is "CHBG"
>
> 0x4 is width
>
> 0x6 is height
>
> 0x8 is flags
>
> 0xA is #of tiles (I think)
>
> 0x10 is palette (variable size)
>
> 
>
> after palette is the image indices (width * height)/(tile area, ie: 8*8) in shorts (2 bytes)
>
> 
>
> after indices is the tiled images array
>
> 
>
> To set the tiled image offset, look under the graphics menu--there is a new item that lets you set the offset, and this is the only way to set it other than a binding file, no skipping/browsing.
>
> To toggle the tiled image on/off use teh V key.
>
> To add in the tiled image offset, add a line like: "tileoffset = readDWORD(0x20);" to the graphics binding
>
> 
>
> example:
>
> width : 64
>
> height : 128
>
> 8bits
>
> 109 tiles
>
> 0x10 @ 256 color palette 2bytes/color
>
> 0x210 @ image indices (64/8 * 128/8) = 128 = 0x80 => 0x100 bytes
>
> 0x310 @ image tiles
[TiledGGD_hackedTiles.zip](https://xentaxbackup.github.io/file/3061_TiledGGD_hackedTiles.zip)
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-05-20T23:14:14+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Strangely when I try this tiled offset refuses to change.
## Post #12
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-21T01:07:06+00:00
- Post Title: (NDS) RPG Tsukuru DS CHBG graphic files

Sorry about that, I almost never open a file from the menu so I missed that place to put in a load for the tiled info.  The previous exe should work the same way as the updated one I just put in its place if you just drag/drop a file onto the graphics area.
