## Post #1
- Username: djhAeon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 14, 2010 12:08 pm
- Post datetime: 2023-07-18T08:42:30+00:00
- Post Title: Rock Band 2 (360) .tex files

I'm trying to figure out how to create new .tex files for Rock Band 2. The originals have important metadata in the headers and I'm trying to figure out where the header stops and the raw image data starts. Size for the attached file is 256x128 (despite what the filename says) and it's DXT5.  If someone can suss out an offset I can put into Rawtex it'd much appreciated!
[01_futurebike_bg_color_256x256.zip](https://xentaxbackup.github.io/file/24083_01_futurebike_bg_color_256x256.zip)
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2023-09-10T12:26:50+00:00
- Post Title: Rock Band 2 (360) .tex files

You can't put it onto the RAW tex since byte order is bigendian. You must swap each 2 bytes. And RAW data offset is variable but can't say more from one sample.
Post more samples. I can write noesis python script to convert em to dds. But if you want put them back you must revers byte order.
Also texture dimension are not as in file name. 256x256. Texture dimensions are 256 x 128 px. And RAW data starts on 250 byte or hex 0xFA.

Here's 010 script to swap bytes. Works both ways. Use on dds once you get em.

```
//--- 010 Editor v14.0 Script File
//
//      File: 
//   Authors: 
//   Version: 
//   Purpose: 
//  Category: 
//   History: 
//------------------------------------------------
local uint32 i;
local uint32 Filesize=FileSize();
local uint32 RawDataSize=Filesize-128;
FSeek(128);
for (i=0; i < RawDataSize/2; i++)
local struct SWAPBYTES {
    uint32 bytearrayoff = FTell();
    uint16 bytearray=ReadUShort(FTell());
    uint16 bytearrayswap = SwapBytes(bytearray);
    WriteUShort(bytearrayoff,bytearrayswap);
    FSkip(2);
}swap;
FileSave();
```
## Post #3
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-09-17T12:01:27+00:00
- Post Title: Rock Band 2 (360) .tex files

> If someone can suss out an offset

For this specific file, the DXT5 data starts at 0x00FA. Following GRiNDERKILLER's advice of swapping every 8 bits per 16 bits (including the 4x4 block's two palette colors and each row of data) gives a good output:
[Rock Band 2 texture offset=0x00FA swap 8 bits per every 16.png](https://xentaxbackup.github.io/file/24357_Rock Band 2 texture offset=0x00FA swap 8 bits per every 16.png)
