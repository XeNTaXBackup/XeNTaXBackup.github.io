## Post #1
- Username: Ikeness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 10, 2007 2:09 am
- Post datetime: 2007-07-28T17:44:15+00:00
- Post Title: Recognize this Texture File Format? Megaman Legends

Alright.  I've fallen back into MegamanLegends.  The program [Yu_Ri](http://romhack.org/old-site/utils/graphics.php) can do near perfect extractions of all the textures in this game (indicating to me that the file type might not be so strange).
Anyway.  I'll just try to describe what I've found.  Lemme know if it sounds familiar.  Let me know if there is some database of image file formats that I can brouse.  Thanks.

Here's a summary:

```
[1 or 8 Color Palettes, each color is a Short , 16 Colors to a Palette]
[Some information on size and deminsions]
[Pixels represented by 4bits each, or 1 hex value each, referencing one of the 16 Colors from the palette.  Pixels go left to right and up to down]

```

So basically, thanks to Yu_Ri, I could quickly determine what is the color palettes and what are the pixels.  But the other info is kind of confusing.

The last short before the pixels gives the height.
The short before that gives the width BUT NOT DIRECTLY. ie, hex 4000 means 256w and hex 2000 means 128 width.  Some other data imediately after the palette appears to indicate something about the size.  Lemme put up some examples.

Here is an example of a texture file, with the color palettes and pixels removed.  Note the 2 areas remaining are the part that are still confusing to me.

```
544D00000000000010000000080000000C0100000000F00010000800
[Main Color Palette]
[7 other Color Palettes each lighter than the last]
0C8000004001000040000001
[Pixels]

```


Here are several "headers" that I have taking from various files to compair them. (the names next to each header are just descriptions I've made for myself.  There are no file names that I know of.)

```
544D00000000000010000000080000000C0100000000FF0110000800 Green Rects 256x64
544D00000000000010000000080000000C0100000000F80110000800 Long Bricky 256x32
544D00000000000010000000080000000C0100000000F10110000800 Water 128x128
544D00000000000010000000080000002C0000000000F00110000100 Gameover 256x128 (only 1 palette)
544D00000000000010000000080000000C0100000000F40010000800 Reaver 256x256
544D00000000000010000000080000000C0100008000F90010000800 Face 256x256
544D00000000000010000000080000000C0100000000F00010000800 Body 256x256
544D00000000000010000000080000000C0100000000F70010000800 Bird 256x128

```


More interesting is the data between the color palettes and the pixels.  Here are some examples:

```
0C280000A00200012000A000 Green Hex 128x160
0C2000004003400140004000 Green Rects 256x64
0C1000004003600140002000 Long Bricky 256x32
0C8000000002000040000001 Reaver 256x256
0C2000008001000120008000 Water 128x128
0C4000008002000040008000 Bird 256x128
0C4000004001000140008000 Gameover 256x128 (only 1 palette)
0C8000004001000040000001 Body 256x256
0C800000C003000040000001 Face 256x256

```


You can see that the first portion of each of these (after the consistant 0C) indicates something of the size.  The last two shorts indicate deminision.  As all with width of 256 have 4000 as the second to last short.  All textures with height of 256 have the short 0001.

K.  So if you recognize any of this, or have an idea of what is going on, please let me know.  Or atleast refer me to where I can look up descriptions of different image formats so that I can try to find something simular.

Thanks
## Post #2
- Username: BetaSword
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 25, 2008 3:21 pm
- Post datetime: 2008-01-26T09:40:55+00:00
- Post Title: Recognize this Texture File Format? Megaman Legends

I realize this is an uber-bump, and I apologize, but I didn't really want to leave this topic open when I have... Well, as close to an answer as I can find, really 

Anyways, the texture format used in Megaman Legends would appear to be the .TIM format used in a lot of PSX games (and it seems they didn't change the format at all for the PC version). It does appear to be slightly different than normal .TIM textures, as, while some programs like PSicture can read the textures, and display them with the correct palette and everything, they are somewhat scrambled. It isn't too hard to unscramble them, though, once they're extracted into a useable format, such as .BMP, preferably through PSicture.

Basically, you need to open the extracted texture in an image editting program. I prefer photoshop, simply for the column selector, useful for what needs to be done. After opening, then select the first two columns of pixels (this is where the column selector comes in), and flip them horizontally. Then do the same with the next two columns after that. And the next two. And so on, until you get to the other side of the texture. And then the texture is fixed. Of course, to make all future fixings easier, you can also record all of that into a macro as you're doing it, so you can just play back the macro to fix any future textures as well.

Again, I realize this is a super-bump, and that the original posted probably won't see this, but hopefully, if someone else is wondering the same thing and happens across this in Google, as I did, then they'll have the answer here.
## Post #3
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2012-02-14T04:54:19+00:00
- Post Title: Recognize this Texture File Format? Megaman Legends

Hi!!! Im trying to develope a megaman legend model extractor. You have the YuRi program? I need it!
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-22T00:26:31+00:00
- Post Title: Recognize this Texture File Format? Megaman Legends

> Reply from denetsu ↑Tue Feb 14, 2012 12:54 pm at Tue Feb 14, 2012 12:54 pm
>
> You have the YuRi program? I need it!
found a copy of YuRi here   
[https://guiamania.com/ffmaniacs/ffzone/download/](https://guiamania.com/ffmaniacs/ffzone/download/)
## Post #5
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2019-03-21T13:24:59+00:00
- Post Title: Recognize this Texture File Format? Megaman Legends

> Reply from Acewell ↑Fri Feb 22, 2019 8:26 am at Fri Feb 22, 2019 8:26 am
>
> 
denetsu wrote: ↑Tue Feb 14, 2012 12:54 pmYou have the YuRi program? I need it!
found a copy of YuRi here   
https://guiamania.com/ffmaniacs/ffzone/download/

Cool thanks!! 7 years after XD
