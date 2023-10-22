## Post #1
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-01T17:18:36+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

I've been trying to decipher RRM files from this game. They are background image files and I am trying to create a viewer. But how do you guys do it to reverse engineer image files? I know these files contain more than the background image itself. What can I do to look for the image bits?

Denis Oezmen created a viewer for a previous version of the format (used in the previous Sherlock Holmes game), if it's any help it's here: [http://oezmen.eu/gameresources/](http://oezmen.eu/gameresources/) In this case you only have to offset from the eof (image width*height + palette size) bytes to get to the important bits, then read the palette and the pixel info consecutively. But this clearly does not apply in this case; just opening the file reveals that the last bytes correspond to some other metadata.

I used Process Monitor during an execution of the game to find out which offsets are being read, but I can't make heads or tails of it; I look for reading blocks of sizes that make sense in the game, which is 640x480 with a 256 color palette. So I look for reading blocks of 307200 bytes (640x480) or 768 (256*3, for the color palette), but I can't find any. Also tried modifying certain hex values of candidate blocks to see if any colors are changed in-game but I only get a crash.

Also I don't understand why data is being read in blocks of 512 or 4096 bytes, instead of bigger blocks for data or smaller blocks for headers.

I have though found several offsets in the header of the file but I don't know how to hack the areas they're pointing at... I am kind of lost here. Maybe some of you can help me by taking a look a sample file? I am new to reverse engineering file formats so some help or tips would be appreciated.


This is the file corresponding to the first playable area:
[http://www.fileswap.com/dl/EulsQ7bRwf/](http://www.fileswap.com/dl/EulsQ7bRwf/)

And this is the PML process monitor resulting from loading that area and the next one:
[http://www.fileswap.com/dl/1egG0LV72a/](http://www.fileswap.com/dl/1egG0LV72a/)
## Post #2
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-02T19:29:31+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

Maybe this should have been on the Game Archive Research subforum? Can some moderator move it please?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-03T06:26:09+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

> Reply from kelmer
>
> Denis Oezmen created a viewer for a previous version of the format (used in the previous Sherlock Holmes game)I'mpretty sure this is a compressed file despite the ASCII data at the file end.

Denis Oezmen wrote "Note that the game has to be installed in the "save time" mode (i. e. the resource files have to be decompressed) for these utilities to work correctly. "

So does "The case of the Rose Tatoo" also have this mode? Then upload an uncompressed RRM, please.

> Also I don't understand why data is being read in blocks of 512 or 4096 bytes, instead of bigger blocks for data or smaller blocks for headers.This depends on how the engine software is written. setvbuf() in C for example allows buffersizes of 2 <= size <= INT_MAX (2147483647). 512 and 4096 are customary values. Afair the filebuffer is setup once keeping its size. Another means would be fscanf() (any one still using it?) allowing reading single chars or ints for example.

> I have though found several offsets in the header of the file but I don't know how to hack the areas they're pointing at...Yes, 0x367974 looks like an offset. You won't hack this without an debugger and setting breakpoints on the file reading routine(s).
---
I was wondering about the starting address of the compressed data. Is it 0x99 or 0x9E or, or?
## Post #4
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-03T07:29:28+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

> Reply from shakotay2
>
> 
So does "The case of the Rose Tatoo" also have this mode? Then upload an uncompressed RRM, please.
It does not, the files are read directly from the CD.

> Reply from shakotay2
>
> 
I was wondering about the starting address of the compressed data. Is it 0x99 or 0x9E or, or?
What do you mean by this? How can I check that?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-03T08:03:19+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

Know quickbms from aluigi? There you can use comtype_scan on compressed files using various decompression algos. (comtype_scan.bat and bms are separate files)

But I prefer cutting the headers. So starting with first compressed byte I hope to get better results. (But what's the starting address? That's the question.)

Maybe you don't need this - anyway: did not get uncompressed data looking like image data so far.

(If you're having some debugging skills you could look for the uncompressed file data in the game's RAM using OllyDbg for example.)
## Post #6
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-03T10:38:46+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

I don't have much debugging skills (no assembler at all), honestly I wouldn't even know where to start.

Just curious, what does "uncompressed data looking like image data" actually look like?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-03T12:41:45+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

> Reply from kelmer
>
> Just curious, what does "uncompressed data looking like image data" actually look like?You mean "is expected to look like"? Cause as I wrote I didn't get any.

Sometimes you can recognize image data from some regular patterns. This data excerpt for example could apply to dds format:

```

06E90 FF FF 00 00 00 00 00 00  CF 7B 00 00 55 55 D5 15   ÿÿ......Ï{..UUÕ.
06EA0 FF FF 00 00 00 00 00 00  71 8C 00 00 09 03 00 00   ÿÿ......qŒ......
06EB0 FF FF 00 00 00 00 00 00  71 8C 00 00 80 60 50 5C   ÿÿ......qŒ..€`P\
06EC0 FF FF 00 00 00 00 00 00  71 8C 00 00 55 35 0D 02   ÿÿ......qŒ..U5..
06ED0 FF FF 00 00 00 00 00 00  71 8C 00 00 03 C0 58 26   ÿÿ......qŒ...ÀX&
06EE0 FF FF 00 00 00 00 00 00  71 8C 00 00 56 55 F5 00   ÿÿ......qŒ..VUõ.
06EF0 FF FF 00 00 00 00 00 00  71 8C 00 00 55 55 7E 00   ÿÿ......qŒ..UU~.
06F00 FF FF 00 00 00 00 00 00  71 8C 00 00 09 05 25 30   ÿÿ......qŒ....%0
06F10 FF FF 00 00 00 00 00 00  71 8C 00 00 78 00 34 94   ÿÿ......qŒ..x.4”
06F20 FF FF 00 00 00 00 00 00  71 8C 00 00 55 57 5C 5C   ÿÿ......qŒ..UW\\
```

You would apply a dds header and load it into a dds viewer. If it's not loaded, well, then you'll have to change the header params.

Or you could load the raw data (for example name it test.bin, without header) into TextureFinder and try out the different format radio buttons.

But, ok, some image data don't show patterns. So maybe I wrongly discarded/missed correct image data amongst the multitude of decompressed dmp files.
## Post #8
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-03T18:11:22+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

I tried with comp_type in combination with TextureFinder as you suggested and actually got something that does resemble like the original image:



What I got:



Algorithms that showed something similar to this were COMP_MSLZSS2, COMP_MSLZSS, COMP_SAINT_SEYA, COMP_PUYO_LZ01 and COMP_LZSS.

What would the steps be from here?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-03T21:47:25+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

> Reply from kelmer
>
> What I got:Well, seems you're on the right way.  
What file did you feed to quickbms? The unchanged RES01.RRM? Or did you cut the header?

What are your params in TextureFinder? I used pixel format 332 = 8 and a width of 486. Got some structures but not as nice as yours.

> What would the steps be from here?Good question. Next question, please!  
(You could look for a new version of TextureFinder (v1.3.2.))
There are no sharp outlines in the pic you got. Very noisy. Maybe a grayscale would give a better impression.
edit: selective Gaussian blur then sharpening again in gimp does not really help

I never saw such image before - I'm no expert with image processing but I guess it will be a hard way to get the original data.
Maybe try the other five compression algos.
## Post #10
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-04T06:37:34+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

I used 332 = 8 and 640 of width. I tried with the first screen of the game (unchanged), which is not playable (thus removing any interaction information from the file).

All five compression algorithms look more or less the same (they all seem to be from the same family, attending to their name)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T08:32:04+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

> Reply from kelmer
>
> I tried with the first screen of the game (unchanged), which is not playable (thus removing any interaction information from the file).Don't understand what you did - I get this only: [](http://www.pic-upload.de/view-20619185/noise.jpg.html)

Anyway, it's wasted time, imho. You should try some ripper on the game (3d Ripper or Ninja ripper).
## Post #12
- Username: kelmer
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 03, 2008 4:16 am
- Post datetime: 2013-09-04T08:35:58+00:00
- Post Title: Lost Files of Sherlock Holmes: The case of the Rose Tatoo

I used a different image, the one I posted is the first playable image, the pics I posted belong to the first screen (which is not playable).

I will try those rippers, then. Thanks for all your help
