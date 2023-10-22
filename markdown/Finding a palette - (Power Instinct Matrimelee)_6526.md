## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-04-29T14:36:57+00:00
- Post Title: Finding a palette - (Power Instinct Matrimelee)

I've created a viewer for the game Power Instinct Matrimelee (Shin Ichizoku Gouketsuji - Bonno no Kaiho) which shows sprites and collision boxes, but curiously I was never able to find the palettes it uses.  My usual approach is opening up binary data as image data to see if anything looks like a palette, but it hasn't worked.

[http://www.justnopoint.com/lbends/junk/ ... oTools.zip](http://www.justnopoint.com/lbends/junk/BonnoKaihoTools.zip)
Usage - load the included data folder, use A-Z to cycle sprites.
Right now it uses a 16 color gradation as the palette, but I know at least 8 palettes exist for each character somewhere.
The files I have provided are just extracted from an AFS file on the disc. The character files are .pak and start with the prefix pl#
It's a very simple container format, and there are three for each character.  The first one is all 4bit image data split into 256x256 sheets. The _bin contains relevant data that the game uses (boxes, animation data, etc.) and the _se contains sound data.  I've uploaded the contents of pl00_or_bin.pak
[http://www.justnopoint.com/lbends/junk/pl00_or_bin.zip](http://www.justnopoint.com/lbends/junk/pl00_or_bin.zip)

File 0 is the sprite data (The image data is tiled)
File 1 is the animation data (I have not fully deciphered it, nor do I intend to)
File 2 is the collision box data (100% figured out)
File 3 is unknown to me, if it's palette data it doesn't look like it.
