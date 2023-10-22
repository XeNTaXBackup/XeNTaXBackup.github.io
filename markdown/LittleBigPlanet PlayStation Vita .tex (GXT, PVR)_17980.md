## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2018-04-15T18:49:29+00:00
- Post Title: LittleBigPlanet PlayStation Vita .tex (GXT, PVR?)

Hey, been doing some work on a tool for LBP games and I ran into a brick wall when I looked into the format for its textures. Seems that the console games used variants of DDS (LBP 1 straight up using DDS files compressed with zlib) while LBP 2 and LBP 3 have DDS files without the headers, which are manually loaded in via the header of the compressed file (see below).. Both are easy to figure out, simple DXT1 and DXT5 dds textures which my tool can read no problem.

However, I'm personally unfamiliar with PS Vita texture files, but I believe they're stored as such:
[http://www.vitadevwiki.com/index.php?title=GXT](http://www.vitadevwiki.com/index.php?title=GXT)

Here's a few samples.

[http://puu.sh/A3OUU.tex](http://puu.sh/A3OUU.tex) - doodle_lbp1tree.tex (Would be DXT5 if it were a DDS, 128x128)
[http://puu.sh/A3P8h.tex](http://puu.sh/A3P8h.tex) - susan_icon.tex (Equivalent to DXT5, 128x128)
[http://puu.sh/A3P2N.tex](http://puu.sh/A3P2N.tex) - tree_bark_diffuse.tex (Equivalent to DXT1, 256x256)
[http://puu.sh/A3P57.tex](http://puu.sh/A3P57.tex) - velvet_cushion_diffuse.tex (Equivalent to DXT1, 256x256)

Here's where I determined the above information..

The format here in the compressed data is exactly the same as LBP 2/3, aside from the magic number, which differs by 1 byte. The above information can be used to extract the raw dds file data (same structure as a dds but without a header), however here it is swizzled when viewed in a program like TextureFinder, which leads me to believe it's some form of GXT.
The compressed data is kept in chunks up to 32KiB each when decompressed, and put in sequential order, labeled by the count of zlib chunks. If there is more than one chunk, it's indexed with repeated entries of the green+yellow labeled bytes in that image.

Adding a GXT header to the raw, uncompressed data ([http://puu.sh/A3PC1.gxt](http://puu.sh/A3PC1.gxt)) and converting it with this tool: [https://github.com/xdanieldzd/GXTConvert](https://github.com/xdanieldzd/GXTConvert) results in something like this...


Also, in some of these files, there's extra added information in the header and I have no idea what it is. Files with the extra data have a magic number of "GXTS" rather than "GXTs."

Seems the 10 is referring to the number of bytes that come after that 0x10000000, but I don't think it's relevant to actually extracting the texture (unsure)

Can anyone with maybe a little knowledge of Vita file texture formats help me out with some information on this file format, or GXT stuff in general? I haven't entered the Vita scene beyond this game.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-16T00:53:42+00:00
- Post Title: LittleBigPlanet PlayStation Vita .tex (GXT, PVR?)

i'm not entirely sure what your questions is because you seem to have this thing figured out.   
here is susan_icon.tex with a gxt header prepended to the  image based on your findings and links



susan_icon.png (14.58 KiB) Viewed 200 times



i decompressed the data with offzip and used this header then opened with Noesis  

```
80 55 00 00 00 00 00 00 00 00 00 00 00 00 00 00
40 00 00 00 80 55 00 00 FF FF FF FF 00 00 00 00 
00 00 00 00 00 00 00 87 80 00 80 00 01 00 00 00
```
## Post #3
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2018-04-16T01:52:17+00:00
- Post Title: LittleBigPlanet PlayStation Vita .tex (GXT, PVR?)

My main issue was figuring out the correct GXT header setup for these textures, as I'm unfamiliar with the format. Thank you!

What about the DXT1 equivalents?

ALSO, for the hell of it is there any way to convert back to GXT, perhaps from DDS? Not a huge priority but it's something I'd like to add to my tool down the line if possible.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-16T02:13:34+00:00
- Post Title: LittleBigPlanet PlayStation Vita .tex (GXT, PVR?)

tree_bark_diffuse.tex  



tree_bark_diffuse.png (96.55 KiB) Viewed 190 times


header used

```
00 AB 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
40 00 00 00 00 AB 00 00 FF FF FF FF 00 00 00 00
00 00 00 00 00 00 00 85 00 01 00 01 01 00 00 00
```


could probably make a bms script to decompress the chunks and build a gxt header for these easily.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-18T14:32:27+00:00
- Post Title: LittleBigPlanet PlayStation Vita .tex (GXT, PVR?)

here is Noesis python script to open your 4 tex samples  


 tex_LittleBigPlanet_PSVita_tex.zip
(1019 Bytes) Downloaded 76 times


supports dxt1 and dxt5
the script will decompress the chunks on the fly and build a gxt header.
## Post #6
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2018-04-18T17:43:03+00:00
- Post Title: LittleBigPlanet PlayStation Vita .tex (GXT, PVR?)

Oh I wasn't expecting that at all - thank you so much! I'm trying to learn a bit about writing noesis plugins so this helps me out a ton.
