## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-14T03:04:04+00:00
- Post Title: Rohan Online: GEM Archive

[http://www.rohan.cn/eng/index.html](http://www.rohan.cn/eng/index.html)

can someone write an container extractor for "GEM", it keeps its file names and data offsets in a separate file (>GEL)

*.GEL = Offsets
*.GEM = Data 

Below are 2 GEM/GEL archives. taking the texture gem/gel for example: in the GEM, you can clearly see where new data starts. which is were you see the magic GEO| which is actually DDS| but.. besides that i was able to determine these offsets: 0000008, 000155F8, 0001ABE8, 0001D730, 0001ED40, 0001D765

Going into the GEL index/offset file, theyre clearly seen

So in the GEL, the first 16bytes are the GEL header(not sure what these values mean) prolly number of offsets, or something

then going down the file every 152bytes is a new header, which indexes to data in the GEM
EX of GEL:

> Offset      0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
>
> 
>
> 00000140   F0 55 00 00 CD CD CD CD  06 00 00 00 06 71 C0 AD   ðU..ÍÍÍÍ.....qÀ­
>
> 00000150   64 72 6F 70 5F 61 72 72  6F 77 30 31 2E 67 74 78   drop_arrow01.gtx
>
> 00000160   00 CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD   .ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 00000170   CD CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD    ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 00000180   CD CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD    ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 00000190   CD CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD    ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 000001A0   CD CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD    ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 000001B0   CD CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD    ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 000001C0   CD CD CD CD CD CD CD CD  CD CD CD CD CD CD CD CD    ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ
>
> 000001D0   48 01 00 00 E8 AB 01 00                            H...è«..
first 16bytes - No clue >_<
next 16byes - the file name
next 122byes - buffer space for the file name, and possible other data?(time stamps)
next 4bytes - no clue >_< 48 01 flipped is is 01 48 which equals 328 in decimal
last 4bytes - finally here is the offset, at which the data starts in the GEM file ^_^ yay
one last thing on that offset though, it needs to be flipped. or a 32byte swap

So our numbers are E8 AB 01 00, flipped that be: 00 01 AB E8 and this is the offset in the GEM file.

Also one last thing on the (*.GTX) files listed in the GEL, these should be exported as (*.DDS) and when extracting that data from the GEM. The magic GEO should be changed to DDS

This allows the textures to be plainly seen in windows thumbnail view, as dds textures

{sample gel/gem files}
[http://www.datafilehost.com/download.php?file=7af1a99e](http://www.datafilehost.com/download.php?file=7af1a99e)
