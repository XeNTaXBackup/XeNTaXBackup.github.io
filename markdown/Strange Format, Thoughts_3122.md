## Post #1
- Username: AoiMasamune
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 27, 2008 7:00 am
- Post datetime: 2008-08-06T09:27:15+00:00
- Post Title: Strange Format, Thoughts?

Hey guys, I'd like to share something with you.

I've been working on figuring out a file format for a while now, and I finally got it to render properly, but it's using a method I've never seen or even read about before. It's from an MMO called Angels Online.

The format itself consists of 5 parts, like so:

1)Header
2)Row Pointer Table
3)Batch Table
4)Palette
5)Pixel Data

I've taken some creative liberties with the names for the various sections.

In depth:
1) Header
Contains the width and height. Lots of flags, eg AlphaChannel, ColorDepth, and DisablePalette. I still haven't completely mapped what all the flags do, but I've got everything rendering correctly, so I guess they are specific to the engine.

2) Row Pointer Table
This is where the weirdness starts. There are a bunch of entries in this table, the number of which is always exactly the image's height. Each entry consists of a 4 byte pointer to later in the file.

3) Batch Table
The entries in the Row Pointer Table point to this area. For each row, there are a series of what I am calling Batches. Each batch consists of: An X-offset, A PixelLength, and another pointer which I'll call a PixelDataPointer. 

Need to do some explaining at this point. When the image is rendered, the renderer will go through each row, skip any transparent pixels by going directly to the X-Offset variable, and draw ONLY the pixels that have color. Thus, the X-Offset variable tells the renderer at what location on the X axis (left to right) to begin copying. The PixelLength variable is how many pixels to copy from that point, and the PixelDataPointer is where the beginning of the pixels are that should be copied.   

4) Palette
Contains 256 entries. Entries are either in 16bit rgb565 format, or 24bit rgb888 format depending on the flags in the header.

5) Pixel Data
A series of bytes, each byte refering to a color in the Palette. If the AlphaChannel flag is active, then each pixel is immediately followed by an extra byte that sets it's alpha. 



So now that the wordy description is done, what I'd like to know is this: 

A) Has anyone ever seen something like this before? If so where? I couldn't find anything describing this kind of setup.
B) What is the benefit of this format? After some testing, a compressed PNG is much smaller. I think it might render faster than a normal bitmap where each pixel is tested against an color key, but doesn't including an alpha channel pretty much nullify that speed boost?
C) The game engine is using some crazy form of palette swapping to recolor sprites and images. It's not a full palette swap, rather some algorithm is being performed to changed the Hue of a target color in the palette. Is there ANYWHERE that describes these kinds of esoteric techniques? Where would you learn something like this?

Thanks in advance, I hope someone out there can help me out.
## Post #2
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-08-06T20:34:25+00:00
- Post Title: Strange Format, Thoughts?

Sounds like it's compressed almost.  It seems to be by the way you're describing these "Batch" instructions.
The indexing method (palette) is very common, used in TGA & TIM2 to name a few.  I would say it seems odd, but as you say, a decent way of rendering for the engine.  It doesn't sound out-worldly ^_^

On the colour swapping, it seems rather simple.  The pointers are pointing to palette colours that are to be changed.  Rather, these, mutable colours.  I don't know anything about it really, but the algo is most likely just (pseudocode) :

```
Read header
Go to pointers offset
Read every pointer
Edit every colour according to some form of input
Render
...

```
## Post #3
- Username: AoiMasamune
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 27, 2008 7:00 am
- Post datetime: 2008-08-06T21:20:19+00:00
- Post Title: Strange Format, Thoughts?

Here let me give an example of the recoloring.

This is the 'base' picture.


Then this string is fed through an algorithm which parses it out and performs the color change.
"BaseBias = 0x24, 0xddce, 132"

The picture then becomes:


A basic transform is being applied as well, so ignore the size change. I'm just interested in the color mechanism.

What I've figured out thus far:

1st Variable:
I have no idea what this is, it is a 24bit hexidecimal value, stored in text format. In the game files it ranges from 0x0 to 0xffffff. Changing this changes the result color in the game. It can also change the color to black and white. It is not a simple RGB value.

2nd Variable:
A 16bit hexidecimal value, stored in text format. This is a 16bit rgb565 color, that describes the target color to be changed. In the above example, it is an orange-tan sort of color. 

3rd Variable:
This is the tolerance of the target color. How far a color can deviate from the 2nd Variable and still be affected. Setting this to 255 changes the whole target picture's palette. I'm not exactly sure how this one works either. 

I want to be able to emulate this system with my custom renderer. Actually, I'd be happy just understanding how it's done, since its a neat trick, and could be really useful in my own programming. 

I'm almost convinced that the colors in the palette are being converted to HSV format, and then the Hue is being changed, since the shading of each color doesn't change. What confuses me, is the ability to change to black and white. Pure Hue can't reach black or white...
