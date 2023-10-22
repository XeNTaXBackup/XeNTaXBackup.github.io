## Post #1
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2012-03-10T10:15:27+00:00
- Post Title: Chaos Wars .UN2 (Seems very easy)

I'm looking for a means to ripping the sprites from this game, but so far I've only found a japanese application that will extract the CG artwork, and is hard coded just to do that.

The format seems pretty standard, but I'm a moron when it comes to this stuff.

I'd love something that could just output the sprites in a .png format, with the correct palettes and offsets.

There's a couple files that use this format, they seem pretty much the same in structure - i've uploaded the smallest one here: 
[http://www.mediafire.com/?27cv911m1um32wy](http://www.mediafire.com/?27cv911m1um32wy)


From what I gather, it contains the character's attack sprites, and their "basic" weapon above them.

Graphics:
4 bits/pixel
Big Endian
linear

Palettes:
4 bytes/colour
BGR
Big Endian
Tiled 8x2


Any and all help would be greatly appreciated.
## Post #2
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2012-03-15T17:28:58+00:00
- Post Title: Chaos Wars .UN2 (Seems very easy)

I hate to bump, but I've not yet had any assistance on this yet... Any help?
## Post #3
- Username: XeroNazoBlaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 06, 2009 3:34 am
- Post datetime: 2012-03-30T21:51:27+00:00
- Post Title: Chaos Wars .UN2 (Seems very easy)

Oh mang, I'm really sorry, I wish I had viewed this thread sooner.

I have no idea about how to convert the sprites to PNG, but luckily the data isn't compressed or encrypted, so I suggest you using TiledGGD.

Here's the script to unpack the UN2 files. Have fun!  :

```
# Made by XeroNazoBlaze

ImpType Standard ;
Idstring "UNI2"
Get NULL1 long ;
Get NOFFILES long ;
Get NULL2 long ;
Get FFOM long ;
Math FFOM *= 2048 ;
Set FFOFFSET FFOM ;
GoTo 0x800 ;
For I = 0 < NOFFILES ;
Get NULL3 long ;
Get FOFFSET long ;
Get FSIZE long ;
Get NULL4 long ;
Math FOFFSET *= 2048 ;
Math FOFFSET += FFOM ;
Math FSIZE *= 2048 ;
Log "" FOFFSET FSIZE ;
Next I

```


Let me know if there's something wrong.
## Post #4
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2012-03-31T09:15:02+00:00
- Post Title: Chaos Wars .UN2 (Seems very easy)

Hey man, thanks so much! This is a great start to getting this all sorted!! Thank you!
