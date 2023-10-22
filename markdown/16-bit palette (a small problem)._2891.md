## Post #1
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-09T18:51:57+00:00
- Post Title: 16-bit palette (a small problem).

I'm trying to convert the GH3 image files but I have a little problem with some files with a 16-bit palette.

Apparently they have the palette messed up, in 32-bit, the order is "BGRA" instead of the normal "RGBA".

I can view the 16-bit images now, but I can't figure out how to change it. I've tried to swap them assuming that instead of using 1 byte for each color, they could have used 1 nibble for each color, but it doesn't seem to work    

So basically, the question is: How are the colors organized in a 16-bit palette (I'm using TGA as target format)? (The images show basically fine, but some colors are messed up   ).

Thanks!
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-09T21:49:37+00:00
- Post Title: 16-bit palette (a small problem).

a 16-Bit palette? don't understand what you mean.
so the palette has 65536 BGRA entries and the picture uses 16 bit per pixel to set the color?
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-10T18:02:45+00:00
- Post Title: 16-bit palette (a small problem).

No. It's a 16-bit (color depth) palette (this means, 2 bytes per entry/color), with 256 entries (with a total of 2*256=512 bytes).

I just want to know, of each entry, what bits are green, what are red, what blue, and what alpha (not sure if there's alpha).

For example, in a 32-bit palette the colors are just:

-8 bits: Red
-8 bits: Green
-8 bits: Blue
-8 bits: Alpha

I just want to know how it works for 16-bit palettes...
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-10T18:35:33+00:00
- Post Title: 16-bit palette (a small problem).

Well, finally solved it (thanks to Wikipedia: [http://en.wikipedia.org/wiki/Highcolor](http://en.wikipedia.org/wiki/Highcolor) )

It's just 5 bits for red, 6 for green and 5 for blue.

Here's my swapping formula. Notice that palette[] is an array of integers, so I'm swapping 2 colors at the same time.

```
palette[i] = (palette[i] & 0x07E007E0) | ((palette[i] >> 10) & 0x001F001F) | ((palette[i] << 10) & 0xF800F800);
```


Also, here's the formula for the 32-bit palettes, MUCH easier:

```
palette[i] = (palette[i] & 0xFF00FF00) | ((palette[i] >> 16) & 0x000000FF) | ((palette[i] << 16) & 0x00FF0000);
```


I don't know if it will be useful, but I think that PS2 uses that format for palettes. Guitar Hero 1, 2, 3 games use those palettes, and GH3 is developed by a different company (Neversoft), so it's not exclusive of the GH1/2 developer (Harmonix)
