## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-07T20:03:35+00:00
- Post Title: Ikki Tousen: Shining Dragon

The game uses a bunch of TM2's for its menu graphics, but for its character models, or level models aswell it uses an extension called *.mpt, which in turns seems to be another container to me. as it has 2 headers. and for this image format is uses the magic Lbin.

anyway, I've tried to just import this as raw, but I'm not having any luck I did how ever see something using raw import options of:
32x256 8channels 16bit with macbyte order, not interleaved. using photoshopcs2

the image in actuality must be 256x256, because when I combine the 8chanels of 32x256 in series, I get this 256x256. where you can see it has a face on the left and hair on the right.

 

i attached a few mpt's, if anyone wants to try and get this working
[CHOUUN.rar](https://xentaxbackup.github.io/file/1304_CHOUUN.rar)
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-08T00:26:23+00:00
- Post Title: Ikki Tousen: Shining Dragon

Well, this is kind of an odd format ... looks a bit like patch-work to me.
Anyway, I believe I have identified enough information to extract images. A rough format outline:

```
byte {4}     - unknown
uint32 {4}   - number of names
byte {12}    - unknown

// for each name
  char {32}    - name

char {4}     - Lbin ID // (Lbin)
uint32 {4}   - number of blocks
uint32 {4}   - image descriptor offset (relative to Lbin ID)
uint32 {4}   - number of images

// for each block
  uint32 {4}   - block offset (relative to Lbin ID)

byte {x}     - padding up to image descriptors

// for each image
  uint32 {4}   - number of image data block
  uint32 {4}   - number of palette data block
  byte {4}     - unknown
  uint16 {2}   - image width
  uint16 {2}   - image height

// for each block
  byte {x}     - padding up to block offset
  uint32 {4}   - data offset (relative to block offset)
  uint32 {4}   - width for images, usually 16 for palettes
  uint32 {4}   - height for images, usually 16 for palettes
  uint32 {4}   - unknown, set for image blocks

  // if image block
    byte {x}     - image data, tiled into vertical stripes of 64 pixels (?) width

  // else if palette block
    // for each of the 256 (?) entries
      byte {4}     - colour data
```


However, a problem remains: I can't make anything out of the palette data. I does not (at least not trivially) contain RGB colour encodings, unless I'm too tired to see them. I've also tried a YCrCb conversion, but the results remain unsatisfactory.

Attached is an extracted example, with wrong colours obviously.
[0001C500.mpt_chouun_face.jpg](https://xentaxbackup.github.io/file/1306_0001C500.mpt_chouun_face.jpg)
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-08T00:52:13+00:00
- Post Title: Ikki Tousen: Shining Dragon

oh cool, i guess it wasn't 256x256

also thats a very nicely detailed format outline, thats awesome 

there were 2 other files, mpd, and smp, but I wouldn't imagine these are in  any way connected as a palette. 

anyway thanks for taking a look, I had thought it was compressed for a while
[C_UKITU.rar](https://xentaxbackup.github.io/file/1307_C_UKITU.rar)
## Post #4
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-08-08T08:03:26+00:00
- Post Title: Ikki Tousen: Shining Dragon

Have you tried all possible 15/16 bit pixel formats, both little-endian and big-endian? Especially if the game is a console game (or a console conversion) it might be a very "uncommon" format.
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-08T09:01:32+00:00
- Post Title: Ikki Tousen: Shining Dragon

I'm quite certain that the image data itself is 8-bit indexed. As this obviously leaves room for up to 256 different colours and the (what I suspect to be) palette blocks are usually 1024 bytes in size, I tend to believe that each colour is somehow encoded into a 4-byte tuple. I have attached one such block in case you want to take a look at it.

(Ah, yes: The MPD and SMP files contain float values, so they're most probably models and/or animations.)
[00013600.mpt_block1.zip](https://xentaxbackup.github.io/file/1308_00013600.mpt_block1.zip)
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-08T19:43:28+00:00
- Post Title: Ikki Tousen: Shining Dragon

I tired extracting the textures from PCSX2, with RipperDX, but I got scrambled data, its not even holding it differently in memory.    only thing I can cetch are the TIMs, but if pcsx2 is showing the correct textures in the game, I don't get why its not converted properly in the d3d buffer...

maybe I should try a different emu's or plugins. having a reference texture will defiantly help
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-08T20:41:48+00:00
- Post Title: Ikki Tousen: Shining Dragon

ok, used a different d3d plugin for pcsx2, and forced d3d textures, I was able to rip some from the buffer, thx to ripperdx 

Anyway interesting enough, all the flesh textures, are blue! i have no clue if this is fault of the emulator or what  though its not really a step forward, till I can get a proper coloured/palletized img


[Textures.zip](https://xentaxbackup.github.io/file/1309_Textures.zip)
## Post #8
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-08-08T21:40:51+00:00
- Post Title: Ikki Tousen: Shining Dragon

I not really strong in graphics format, but maybe there is some different color pallet like cmyk or...
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-08T21:43:13+00:00
- Post Title: Ikki Tousen: Shining Dragon

Now I recall such blue skin problem in another game where the palette was read in reverse or something of that effect. I lost contact with Strobe who was going to fix it for that game. Not sure if that is the case here or not.
## Post #10
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-08T22:47:59+00:00
- Post Title: Ikki Tousen: Shining Dragon

aww, you are correct, instead of RGBA, it was BGRA.. well just for the pcsx2 rip. as for extracting from the raw file, i'm still completely in the dark
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-08T23:22:03+00:00
- Post Title: Ikki Tousen: Shining Dragon

That rip was actually very helpful! (Never mind the RGB/BGR switch, I already suspected that.)

Contrary to my previous assumption, the palette is indeed pure RGB. But it is addressed in the weirdest way I have ever seen. Actually, it too is saved in some sort of tiled manner, each tile having a size of 8x2 in a 16x16 "palette image". Very odd stuff.

Anyway, try [this converter](http://www.xentax.com/uploads/author/denizoezmen/_MPT2TGA.zip). I'm not sure whether I'm handling the alpha channel correctly, but scaling it up by a factor of two seemed reasonable:

```
MPT2TGA *.mpt
```


Please note that there is still some unknown stuff in the file, so the converter might fail in some cases.
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-09T01:34:11+00:00
- Post Title: Ikki Tousen: Shining Dragon

incredible!!

I was trying to compare between the 2, and really couldn't see much of a connect. 

many, many thanks
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-10T07:15:09+00:00
- Post Title: Ikki Tousen: Shining Dragon

You're welcome!
