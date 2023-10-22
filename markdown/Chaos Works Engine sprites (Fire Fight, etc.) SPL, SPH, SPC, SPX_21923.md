## Post #1
- Username: alcexhim
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 05, 2013 9:37 pm
- Post datetime: 2020-03-23T00:16:56+00:00
- Post Title: Chaos Works Engine sprites (Fire Fight, etc.) SPL, SPH, SPC, SPX

Hello all, long time no see!

Many thanks to WRS for his help on understanding the original VOL archive format in Fire Fight. I finally fixed the problem I was having in my program (the LZRW1 decompression routine was buggy) and was able to extract some sprites! And based on the knowledge I have gained since then, I was able to decipher the VOL format used in newer games all by myself!   

Unfortunately, I am kind of stuck again. I am trying to understand the format of the SPL, SPH, and SPC (SPX In newer games) sprites that start with the signature, "CWE sprite". From what I have been able to discover through trial and error, they definitely contain multiple images, and the format of the sprite container is pretty straightforward. It's decoding and understanding the pixel data that's giving me issues...

The game engine makes reference to the FLIC file format, although this is clearly not a standard FLIC file, it seems to take inspiration from it in some respects. I haven't tried reverse-engineering the game engine, as I'm not at all fluent in that... this is all trial-and-error for me.

Here is the format I have so far:

> HEADER DATA
>
> 11 bytes - null-terminated string "CWE sprite\0"
>
> 4 bytes - version, perhaps (always 36 in fire fight sprites)
>
> 4 bytes - version, perhaps (always 12 in fire fight sprites)
>
> 4 bytes - unknown, perhaps a key or hash or CRC for this sprite or filename (always the same in same-named SPH, SPL, and SPC files)
>
> 20 bytes - unknown
>
> 8 bytes - unknown, only present in newer games' SPX files
>
> 4 bytes - length of pixel data
>
> 4 bytes - number of images in this sprite
>
> 
>
> PIXEL DATA
>
> for each image,
>
> 2 bytes - length of this block
>
> 2 bytes - number of frames (x-pixels) in this block
>
> for each frame,
>
> 2 bytes - number of y-pixels to skip
>
> 2 bytes - number of y-pixels to draw
>
> if number of y-pixels is less than zero,
>
> 1 byte - I use this as an index into the color palette, but this could be wrong
>
> repeat this byte for -(number of y pixels)
>
> otherwise,
>
> for each y-pixel to draw,
>
> 1 byte - I use this as an index into the color palette, but this could be wrong
>
> 
>
> IMAGE DEFINITION DATA
>
> for each image,
>
> 4 bytes - unknown (maybe animation frame time)
>
> 4 bytes - unknown
>
> 2 bytes - x coordinate (for what?)
>
> 2 bytes - y coordinate (for what?)
>
> 2 bytes - width
>
> 2 bytes - height
>
> 2 bytes - unknown (only present in newer games' SPX files)
>
> 
>
> EMBEDDED PALETTE DATA
>
> I usually read this until the end of the file, but there seems to always be 768 bytes (256 colors, with 3 bytes per color R,G,B except in SPX that has an additional alpha value)

In addition to the sprite's own 256-color embedded palette, the game includes external PALETTE.SPP files in various directories, which are simply a four-byte what appears to be a version number, and then a whole bunch of RGBA (or BGRA) four bytes per color. Of course, I only read a single byte color index, and there are waaaaay more than 256 colors in the external palette, so I'm not sure how it is referenced by the sprite file.

I've attached a few samples to illustrate some of the issues I'm having. Some images come out "okay" (though I think the color is still off), while others clearly have issues (the one image is "shifted" to the left).

Any advice or suggestions would be greatly appreciated. Even if you don't know much about this particular file format, any suggestions based on prior experience with image formats might help (I know I've seen the "shifting" behavior before, though I can't recall what might cause it).

THANK YOU!!!
[sample.7z](https://xentaxbackup.github.io/file/17785_sample.7z)
## Post #2
- Username: alcexhim
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 05, 2013 9:37 pm
- Post datetime: 2020-04-29T05:03:03+00:00
- Post Title: Chaos Works Engine sprites (Fire Fight, etc.) SPL, SPH, SPC, SPX

Hello everyone,

Any thoughts on this? I see this topic has been viewed 88 times but hasn't generated any replies. I'm thinking it might be a "swizzle" issue or something like that, which I'll try to work on if I have the time.

But I'm still bugged about the colors being off. I think the external palette has something to do with it (it has an insane amount of colors if I'm reading it correctly), but I can't seem to find anything in the sprite file that indicates which part of the external palette to select the colors from.

Hoping someone smarter than me might have an answer! Thank you for all you do.
## Post #3
- Username: Pejti
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 01, 2020 11:48 am
- Post datetime: 2021-04-13T17:53:15+00:00
- Post Title: Chaos Works Engine sprites (Fire Fight, etc.) SPL, SPH, SPC, SPX

So are you still making something with this?
## Post #4
- Username: kagato1980
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 14, 2023 7:01 pm
- Post datetime: 2023-08-14T18:12:32+00:00
- Post Title: Chaos Works Engine sprites (Fire Fight, etc.) SPL, SPH, SPC, SPX

I'm trying to decompress the Fire Fight VOL to extract sounds, but existing tools and random scripts I found haven't helped me much yet..Care to share how the VOL is constructed? Or got a script to share?
## Post #5
- Username: jalbr74
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 30, 2023 6:21 am
- Post datetime: 2023-09-29T23:00:33+00:00
- Post Title: Chaos Works Engine sprites (Fire Fight, etc.) SPL, SPH, SPC, SPX

@kagato1980 I'm trying to extract Fire Fight VOL archives as well, and I came across this post:
[viewtopic.php?p=84495#p84495](https://forum.xentax.com/viewtopic.php?p=84495#p84495)

It appears the user: WRS created a script that can extract the firefight VOL archive format, but you have to run it using the BMS Scripting tool: quickbms.

Here's more information on basic BMS Scripting:
[viewtopic.php?t=17892](https://forum.xentax.com/viewtopic.php?t=17892)

I've been trying to learn the tool myself, and I've been running commands like the following:
> quickbms -l firefight.bms FIREFGHT\BROWN1.VOL extracted

However, I just get errors like the following:

```
- open script firefight.bms

  offset   filesize   filename
--------------------------------------

-------------------
*EXCEPTION HANDLER*
-------------------
An error or crash occurred:

*EH* ExceptionCode      80000001 guard page violation
*EH* ExceptionFlags     00000000
*EH* ExceptionAddress   01065CD2
                        00F40000 + 00125cd2 quickbms.exe
*EH* NumberParameters   00000002
*EH*                    00000000
*EH*                    0D7919DF

Last script line before the error or that produced the error:
  41  clog MEMORY_FILE CURPOS CHUNKSIZE 0xfffff

- OFFSET       0x00000002
- ZSIZE        0x00002a8b
- SIZE         0x000fffff
  coverage file 0     3%   10913      317397     . offset 00002a8d

```


I'm not sure if I'm using the tool right, but I figured I'd keep at it until I get something out of it. Hope you have better luck!
