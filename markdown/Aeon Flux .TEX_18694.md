## Post #1
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-17T05:01:56+00:00
- Post Title: Aeon Flux *.TEX

Hey all,

Started looking at this texture format and have already figured out what the format is for the most part. It is structured as so:

```
Uint32 - Codec ID:
0xC = dxt3
0xE = ? another dxt compression type?
Uint32 width
Uint32 height
Uint32 0
Uint32 unkown (don’t know what it’s for. Some type of flag maybe)
Uint64 0’s
Byte [] pixel data (data start is usually 0x20). 

```


The ones I have cracked are the headerless DXT3 DDS files that contain mip-maps. So I have two questions:

1. How would I go about building a header for the DDS file? I know it's been done before, but I have no clue what the header format would be, and or specifics needed for it.  I'm still very new to this, and have no clue where to start with that (I think it's usually done through a QuickBMS script).

2. The unknown pixel format is only used in the bump maps. I had a strong feeling it was DXT1, but it looked weird in texture finder. Could anyone give a shot at figuring it out? Thanks!

Attached are sample files for your perusal (I've attached ones with the 0xC ID for DXT3, and the unknown bump map ones). I would mainly love to learn how to build a DDS header for cases such as this. Thanks in advance!

~Anexenaumoon


 tex.zip
(77.11 KiB) Downloaded 19 times
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-17T20:51:36+00:00
- Post Title: Aeon Flux *.TEX

Little update:

I found a little doc containing the specifics of a DDS header. I mostly understand how to build the header of one now(Woo-hoo!). I'm not worried about mip-mapping necessarily because I only care for the main texture anyway, and mip-maps can be auto-generated anyways. So now all I need help with is that unknown codec in the bump maps.
