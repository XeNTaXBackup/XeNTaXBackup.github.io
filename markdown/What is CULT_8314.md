## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-02-17T09:49:24+00:00
- Post Title: What is CULT?

Does anyone know anything about CULT?
[http://neko68k.blogspot.com/2011/08/vir ... wip-2.html](http://neko68k.blogspot.com/2011/08/virtual-on-marz-wip-2.html)
neko68k spoke, 

> http://dl.dropbox.com/u/51368068/vomarz_pvrcvt.rar
>
> This works from the command line, it converts PS2 PVR files to TGA files.
>
> It requires a PVR and a CLUT. It's been months, I dont remember how to tell what the CLUT files are. 
>
> Some of the PVR are 8-bit and others are 4-bit, you have to sort out which is which and what CLUT files they go with on your own.
I want to know what is CULT
PVRT samples : [http://www.mediafire.com/?kqfemm82kpif074](http://www.mediafire.com/?kqfemm82kpif074)
## Post #2
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-02-17T19:01:37+00:00
- Post Title: What is CULT?

CLUT (not CULT) is short for Colo(u)r Look-Up Table, sometimes it's called a palette

Basically it's [http://en.wikipedia.org/wiki/Paint_by_number](http://en.wikipedia.org/wiki/Paint_by_number), you have a palette of colors (let's say 1 to 4)
the palette is definied (in your case in an external file, NOT in the files provided, look at other files in the same directory)
in a certain color space (e.g. as R8G8B8 with alpha or just R5G6B5 or as luminance ...)

e.g. a 32 bit RGBA CLUT (palette) with 4 entries

```
Color 2: R = 255 G = 255 B = 255 A = 255
Color 3: R = 0   G = 0   B = 0   A = 0
Color 4: R = 255 G = 0   B = 0   A = 0

```


And an image (here 4x4) that doesn't contain actual color data, instead it has references to the CLUT.

```
4 2 1 2
3 3 3 3
1 2 1 2

```




An easy example is on the wiki page: http://en.wikipedia.org/wiki/Colour_look-up_table


If you don't understand the example provided or want a quick real life example just write back.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T19:20:44+00:00
- Post Title: What is CULT?

Real-life example would be nice.
I don't see what makes it efficient, considering how many combinations of RGBA values you could possibly have.
## Post #4
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-02-17T19:48:20+00:00
- Post Title: What is CULT?

If you want a ton of examples for CLUTs on different platforms: http://en.wikipedia.org/wiki/List_of_palettes

I forgot to say why CLUTs are/were used:
A single pixel only has 2 bits instead of the full 32 bit it would take for R8G8B8A8 (in the example above), see example below to see how much this saves
They were primarily used to save space in the 'old' days, nowadays CLUTs are getting rare (but they aren't gone)

An easy example:
You have a R5G6B5 colorspace (quite common on the PSP) so 16 bits = 2 bytes per pixel
Now that would be (for a 64x64 image): 64*64*2 bytes = 8192 bytes (8 KibiByte or 8.192 KiloByte)

Assume there are only 32 different colors in this 64x64 picture (or reduce them to the 32 most used)

We make a CLUT of 32 colors with the length of 2 bytes (one color needs 5+6+5 bit = 2 bytes) = 64 bytes
Now we can address each pixel with just 5 bit (2^5 = 32 different colors) instead of using the full R5G6B5 notation (5+6+5 = 16 bit)
So CLUT + image data: 64 bytes + (64 * 64 * (5/8) byte) = 2624 bytes


If you want a practical appliciance: The GIF file format, every .gif file has a palette that consists of up to 256 colors! They are very small in size.
See: [http://en.wikipedia.org/wiki/Indexed_co ... exed_color](http://en.wikipedia.org/wiki/Indexed_color#Image_file_formats_supporting_indexed_color)

Is it clear now why it is efficient? Are you sure you need an example from start to finish? (it's quite some work explaining  it completly)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T20:19:35+00:00
- Post Title: What is CULT?

So basically CLUT's are often used when you know that the range of colors you're going to be using is limited (either by the dev, or by other factors like software/hardware)
## Post #6
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-02-17T20:40:30+00:00
- Post Title: What is CULT?

.
## Post #7
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-02-18T01:48:59+00:00
- Post Title: What is CULT?

Quite frankly,Your explanation is over my head.
neko68k said

> clut files are SVP
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T02:14:32+00:00
- Post Title: What is CULT?

That is definitely more informative than the walls of information that was provided lol
## Post #9
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2012-02-19T05:06:30+00:00
- Post Title: What is CULT?

the clut files that virtual on uses with its pvr files are used to save space because multiple textures use the same colors and the color space is small. the SVP fileswere ripped from the Ninja containers. There is an issue with texture coordinates or something though and the objects don't look correct when textured. 

and just to clarify the difference between dreamcast and ps2 pvr textures, ps2 textures have a flag that specifies if the pixel data is swizzled or not and you have to handle it accordingly. iirc you also have to handle palettes in ps2 format. there may be an alpha issue with my converter also, I ran into the same issue with rtype final. I'm not familiar enough with ps2 hardware but the alpha values seem to be 16-bit or possible 32-bit signed but it seems well enough they way I deal with it.

another note about pvr and nj models, pvr files have a sub header with the magic GBIX. the GBIX header defines a global identifier for that the ninja system uses. the nj models refer to this identifier to pick what texture they use.

also a note about vo: marz. the japanese version is pretty interesting because the symbols weren't stripped from the executable. static analysis is a pain and pcsx2 doesn't have a functional debugger, but it should be possible to reverse engineer the entire ninja system from rofs encryption to handling models and textures in great detail. I'm not that interested but the possibility exists.
## Post #10
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-02-19T06:56:42+00:00
- Post Title: What is CULT?

I am grateful for a clear explanation.
But my biggest problem is my lack of basic knowledge.

Is there anyone who could upload the edited sampls?
## Post #11
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2012-02-19T15:24:35+00:00
- Post Title: What is CULT?

Because you hand ripped them there isn't really anything I can do, sorry. Is there a particular texture that you were looking for, I could maybe help with that.
