## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-10T01:26:33+00:00
- Post Title: Dishonored2 (.bimage7)

It seems that it has similar structure with id tech5 but I can't get right image when I open it as raw file on Photoshop.

ex) 64_df.bimage7 in idsettler_heavy folder

```
UNK byte
UNK 13 00 00 00 00 00 00 00 14 00 00 00 06 00 00 00 01 00 00 00
0x18 width long
0x1C height long
0x20 width long
0x24 height long
UNK 01 00 00 00 01 00 00 00 01 00 00 00 00 00 00 80 00 00 00 00 00 00 00 00 00 00
0x46 width long
0x4A height long
0x4E Data_Size long
```

Samples. [https://www.sendspace.com/file/a7sf6i](https://www.sendspace.com/file/a7sf6i)
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-10T11:09:04+00:00
- Post Title: Dishonored2 (.bimage7)

texture it is fliped and reversed, mostlikely kind of strange format DX10 ? Hard to say yet still investigating..
## Post #3
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-11-10T19:39:12+00:00
- Post Title: Dishonored2 (.bimage7)

Ouch!  


And here is template for 010. Some of values are still unknown for me...

```
//--- 010 Editor v6.0.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
LittleEndian();

local uint i;
struct BIMAGE {

uint64 Id;
uint Zero;
uint CompressionChar; //probably
uint Par1;
uint Mipmaps;
uint MainWidth;
uint MainHeigth;

for(i=0;i<Mipmaps;i++) {
struct Mipmap {

uint Width;
uint Heigth;
uint MipmapNum;
uint Par2;
uint Par3;
uint Par4;
uint Par5;
uint64 Zero;
short Zero;
uint Width;
uint Heigth;
uint Mipmapsize;
ubyte data[Mipmapsize];
        } record;
    }
} record;
```
## Post #4
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-11T04:23:29+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from GRiNDERKILLER
>
> And here is template for 010. Some of values are still unknown for me...

Hi, there! Can you upload dds file? I'll try to make bms script for it.
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-11T06:38:53+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from adol365
>
> GRiNDERKILLER wrote:And here is template for 010. Some of values are still unknown for me...


Hi, there! Can you upload dds file? I'll try to make bms script for it.

This wont help you allready try to put it back, game wont take uncopressed textures. Problem is custom setup for zlib, someone has to remade zlib compressor. Gonna ask alugii
## Post #6
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-11T09:02:03+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from michalss
>
> This wont help you allready try to put it back, game wont take uncopressed textures.
Just let me know what is the correct header information.

```

get NAME basename
string NAME += ".dds"

get Id longlong
get Null long
get CompressionChar long
get Parl long
get Mipmaps long

goto 0x46
get WIDTH long
get HEIGHT long
get SIZE long
savepos OFFSET

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 SIZE long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short

append
log MEMORY_FILE OFFSET SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE
```
## Post #7
- Username: swinei
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-11T09:29:44+00:00
- Post Title: Dishonored2 (.bimage7)

ok this is also sorted but it wont help that much as fonts are also in scaleform format IGGY..

classic textures are DXT10 - that is not a problem... attached correct DDS
[64_df.bimage7.rar](https://xentaxbackup.github.io/file/11898_64_df.bimage7.rar)
## Post #8
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-12T07:32:06+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from michalss
>
> ok this is also sorted but it wont help that much as fonts are also in scaleform format IGGY..

classic textures are DXT10 - that is not a problem... attached correct DDS

I can't see any glyphs. It's black.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-12T08:14:03+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from adol365
>
> I can't see any glyphs. It's black.
Noesis has native support for that dx10 image
## Post #10
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-12T08:21:14+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from AceWell
>
> adol365 wrote:I can't see any glyphs. It's black.
Noesis has native support for that dx10 image

Hi, AceWell.   Can't I open it on Photoshop?
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-12T09:03:10+00:00
- Post Title: Dishonored2 (.bimage7)

i suppose if you have a plugin like this for it   
[https://github.com/GameTechDev/Intel-Te ... rks-Plugin](https://github.com/GameTechDev/Intel-Texture-Works-Plugin)
## Post #12
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-12T09:23:24+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from AceWell
>
> i suppose if you have a plugin like this for it   
https://github.com/GameTechDev/Intel-Te ... rks-Plugin

Thank you!
## Post #13
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2016-11-18T00:17:15+00:00
- Post Title: Dishonored2 (.bimage7)

> Reply from michalss
>
> ok this is also sorted but it wont help that much as fonts are also in scaleform format IGGY..

classic textures are DXT10 - that is not a problem... attached correct DDS

How does saving the file as DDS work? I opened a .bimage7 in 010 and the template ran successfully what do I do now? -> find the right header for the ubyte data (last field of the template output)

e: IGGY fies are made by this [http://www.radgametools.com/iggy.htm](http://www.radgametools.com/iggy.htm)

e2: I read about the DDS header here [https://msdn.microsoft.com/en-us/librar ... s.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/bb943982%28v=vs.85%29.aspx) I copied the header from the file michalss posted, adjusted width, height, and dwPitchOrLinearSize, but it is not displaying correctly. It looks like this:


When I open the file in Texture Finder I can display the texture with correct color and alignment with an offset of 198. This makes me think the dds data needs to be padded? I tried adding 00s in front of the data but it didn't help. What do I need to do?

This is an image with 198 offset in Texture Finder:


e3: Since Texture Finder doesnt read the header at all that's a dead end. So my question is what do I need to put into the header? I used the same dxgiFormat as michaelss, is that the issue?
[quest_corrupt_rune_is.zip](https://xentaxbackup.github.io/file/11935_quest_corrupt_rune_is.zip)
## Post #14
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-11-19T16:09:36+00:00
- Post Title: Dishonored2 (.bimage7)

It's DXT5 compression  So 128 bytes dds header. DX10 header has 148.
## Post #15
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2016-11-19T16:41:34+00:00
- Post Title: Dishonored2 (.bimage7)

Oh yeah I figured that out after a lot of trial and error 

I made a bms for the DXT5 .bimage7s

```



get NAME basename
string NAME += ".dds"

get Id longlong
get Null long
get CompressionChar long
get Parl long
get Mipmaps long

goto 0x46
get WIDTH long
get HEIGHT long
get SIZE long
savepos OFFSET

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 SIZE long

append
log MEMORY_FILE OFFSET SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE
```


The problem now is that only some are in DXT5. Is there a way to automatically detect which compression it is? I couldn't figure anything out from the BIMAGE header

Also some textures have a .bimage7 and bimage7_mip0/1/2/3. Those are different sizes of the same texture but the _mips only contain the image data. I'm currently working on a script that stitches those parts together, I'll share it when it's done.
## Post #16
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-19T17:40:36+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> e: IGGY fies are made by this http://www.radgametools.com/iggy.htm

Do you have any idea for modding *.iggy?
[https://www.sendspace.com/file/8trh37](https://www.sendspace.com/file/8trh37)
## Post #17
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2016-11-19T18:53:20+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from adol365
>
> swinei wrote:e: IGGY fies are made by this http://www.radgametools.com/iggy.htm

Do you have any idea for modding *.iggy?
https://www.sendspace.com/file/8trh37

I will try to extract .iggy files once I'm done with the .bimage7 files, I don't know anything about modding tho.
## Post #18
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2016-11-20T02:42:25+00:00
- Post Title: Re: Dishonored2 (.bimage7)

These are all the Compression Chars and Par1 pairs. I added pixelformat where I know it:

{02, 07}
{04, 05}
{05, 14}
{06, 07}
{10, 05}
{10, 06}
{12, 07}
{16, 05} DXT5
{17, 05}
{18, 04}
{19, 03} 
{20, 06} DX10

What's the best way to get the corresponding format? Is there any way around trial and error?
## Post #19
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-11-20T08:48:54+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Possible formats used in this game. Still have no idea about compression char or how it can be converted to pixel format.

```
RG
RED
R32_G32_B32_A32_FLOAT
R32_G32_B32_A32_UNSIGNED
R32_G32_B32_A32_SIGNED
R32_G32_B32_FLOAT
R32_G32_B32_UNSIGNED
R32_G32_B32_SIGNED
R32_G32_FLOAT
R32_G32_UNSIGNED
R32_G32_SIGNED
R32_FLOAT
R32_UNSIGNED
R32_SIGNED
R16_G16_B16_A16_FLOAT
R16_G16_B16_A16_UNSIGNED
R16_G16_B16_A16_SIGNED
R16_G16_B16_A16_UNSIGNED_NORMALIZED
R16_G16_B16_A16_SIGNED_NORMALIZED
R16_G16_FLOAT
R16_G16_UNSIGNED
R16_G16_SIGNED
R16_G16_UNSIGNED_NORMALIZED
R16_G16_SIGNED_NORMALIZED
R16_FLOAT
R16_UNSIGNED
R16_SIGNED
R16_UNSIGNED_NORMALIZED
R16_SIGNED_NORMALIZED
R8_G8_B8_A8_UNSIGNED
R8_G8_B8_A8_SIGNED
R8_G8_B8_A8_UNSIGNED_NORMALIZED
R8_G8_B8_A8_SIGNED_NORMALIZED
R8_G8_B8_A8_UNSIGNED_NORMALIZED_SRGB
B8_G8_R8_A8_UNSIGNED_NORMALIZED
B8_G8_R8_A8_UNSIGNED_NORMALIZED_SRGB
B8_G8_R8_X8_UNSIGNED_NORMALIZED
B8_G8_R8_X8_UNSIGNED_NORMALIZED_SRGB
B8_G8_R8_UNSIGNED_NORMALIZED
B8_G8_R8_UNSIGNED_NORMALIZED_SRGB
R8_G8_UNSIGNED
R8_G8_SIGNED
R8_G8_UNSIGNED_NORMALIZED
R8_G8_SIGNED_NORMALIZED
R8_UNSIGNED
R8_SIGNED
R8_UNSIGNED_NORMALIZED
R8_SIGNED_NORMALIZED
BC1_UNSIGNED_NORMALIZED
BC1_UNSIGNED_NORMALIZED_SRGB
BC2_UNSIGNED_NORMALIZED
BC2_UNSIGNED_NORMALIZED_SRGB
BC3_UNSIGNED_NORMALIZED
BC3_UNSIGNED_NORMALIZED_SRGB
BC4_UNSIGNED_NORMALIZED
BC4_SIGNED_NORMALIZED
BC5_UNSIGNED_NORMALIZED
BC5_SIGNED_NORMALIZED
BC6_F16_UNSIGNED
BC6_F16_SIGNED
BC7_UNSIGNED_NORMALIZED
BC7_UNSIGNED_NORMALIZED_SRGB
B5_G6_R5_UNSIGNED_NORMALIZED
B5_G5_R5_A1_UNSIGNED_NORMALIZED
B4_G4_R4_A4_UNSIGNED_NORMALIZED
R11_G11_B10_UNSIGNED_FLOAT
R10_G10_B10_A2_UNSIGNED
R10_G10_B10_A2_UNSIGNED_NORMALIZED
D32F
D32F_S8_X24
D24_S8
D16
ETC1_RGB_4BPP
PVRTC_RGBA_2BPP
PVRTC_RGBA_4BPP
PVRTC_RGB_2BPP
PVRTC_RGB_4BPP
```


And here is updated template. Now it shows MipMaps position. Won't work on CubeMap images.

```
//--- 010 Editor v6.0.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
LittleEndian();

local uint i;

struct BIMAGE {

        uint64 Id;
        uint Zero;
        uint CompressionChar; //probably
        uint Par1;
        uint LayerNum;
        uint MainWidth;
        uint MainHeigth;

struct SubHeader {

        uint Width;
        uint Heigth;
        uint Layer;
        uint MipmapsNum;
        uint Par3;
        uint Par4;
        uint Par5;
        short Zero;

for(i=0;i<MipmapsNum;i++) {

struct Mipmap {

        uint64 MipmapNum;
        uint MipWidth;
        uint MipHeigth;
        uint MipSize;
        ubyte data[MipSize];
            } record;
        }
    } record;
} record;
```
## Post #20
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2016-11-20T14:07:51+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from GRiNDERKILLER
>
> Possible formats used in this game. Still have no idea about compression char or how it can be converted to pixel format.


And here is updated template. Now it shows MipMaps position. Won't work on CubeMap images.

To match the formats with the compression char I would get samples for each possibility and write all possible headers. Is the data from [here](https://msdn.microsoft.com/en-us/library/windows/desktop/bb943991%28v=vs.85%29.aspx#common_dds_file_resource_formats_and_associated_header_content) all that I need to consider? Or is there some other values I need to change depending on the file (except width, height and MipSize)?

I copied part of your template for the .mip files:

```
//--- 010 Editor v6.0.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
LittleEndian();

struct Mipmap {

    uint64 MipmapNum;
    uint MipWidth;
    uint MipHeigth;
    uint MipSize;
    ubyte data[MipSize];

} record;

```
## Post #21
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-21T18:08:02+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from adol365
>
> Do you have any idea for modding *.iggy?Is there any documentation available about the vector fonts that are stored in the *.iggy files?
## Post #22
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-21T19:18:39+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from herbert3000
>
> adol365 wrote:Do you have any idea for modding *.iggy?Is there any documentation available about the vector fonts that are stored in the *.iggy files?

Dont think so..
## Post #23
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-22T02:08:11+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from herbert3000
>
> Is there any documentation available about the vector fonts that are stored in the *.iggy files?

That's the problem.  The only information that we have is this.
[http://www.radgametools.com/iggyhist.htm](http://www.radgametools.com/iggyhist.htm)
Dishonoerd2 use 1.49 version.

```
...

Font A data
Font B data
...
Font E data
Font A tag
Font B tag
...
Font E tag
Action acript

```
## Post #24
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-22T09:49:20+00:00
- Post Title: Re: Dishonored2 (.bimage7)

fonts are not only problem, i wrote tools last night and there is maximum size of archive allowed, if you add all necessary file on the end of the archive, game wont start, so i made a few tests and try to add only a few files and that is work, so there is somewhere set maximum of archive size...  Means only possible way would be to try make a patch system or try to repack whole archive to make sure it fits into maximum size... 

Fonts - found out that diff lang containing diff font sets, english is the worst as you can think...
## Post #25
- Username: adol365
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-23T09:31:36+00:00
- Post Title: Re: Dishonored2 (.bimage7)

we made some progress 






[fonts.rar](https://xentaxbackup.github.io/file/11948_fonts.rar)
## Post #26
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-23T12:54:56+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I used the block 0x1F30 - 0x15EE17 from lib_loc_english_font.iggy and got this:



iggy.png (37.67 KiB) Viewed 246 times

(the letter on the right is from the russian font)

```
00 40 33 BF 
00 00 82 3E 
00 00 80 3B 
30 00 00 00 
00 00 00 00 
0E 00 00 00 	 numPoints
00 00 00 00 
01 00 00 00 
00 00 00 00 
01 00 00 00 
00 00 00 00 
01 00 00 00 
00 00 00 00 
01 00 0D 00 
02 00 0D 00

for (numPoints) {
00 00 C5 3D 	x    (red crosses on screenshot)
00 80 33 BF 	y
00 00 BF 3E 	ctrl x (is 0 if straight line)    (blue crosses on screenshot)
00 40 E1 BE	ctrl y (is 0 if straight line)
03 		type (1 = moveTo, 2 = straight, 3 = curved)
00 
00 00 
01 00 
00 00 
}
```
## Post #27
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-23T15:42:28+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from herbert3000
>
> I used the block 0x1F30 - 0x15EE17 from lib_loc_english_font.iggy and got this:
(the letter on the right is from the russian font)
Code: Select all00 00 20 3D 
00 40 33 BF 
00 00 82 3E 
00 00 80 3B 
30 00 00 00 
00 00 00 00 
0E 00 00 00 	 numPoints
00 00 00 00 
01 00 00 00 
00 00 00 00 
01 00 00 00 
00 00 00 00 
01 00 00 00 
00 00 00 00 
01 00 0D 00 
02 00 0D 00

for (numPoints) {
00 00 C5 3D 	x    (red crosses on screenshot)
00 80 33 BF 	y
00 00 BF 3E 	ctrl x (is 0 if straight line)    (blue crosses on screenshot)
00 40 E1 BE	ctrl y (is 0 if straight line)
03 		type (1 = moveTo, 2 = straight, 3 = curved)
00 
00 00 
01 00 
00 00 
}

also very nice  edit possible?  or not yet ?
## Post #28
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-23T22:31:07+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from michalss
>
> also very nice  edit possible?  or not yet ?not yet  I'm still skipping too many parts of the file.
At the moment I'm primarily focused on reading the iggy files.


 FontViewer.zip
(9.9 KiB) Downloaded 100 times
## Post #29
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-24T10:35:12+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from herbert3000
>
> michalss wrote:also very nice  edit possible?  or not yet ?not yet  I'm still skipping too many parts of the file.
At the moment I'm primarily focused on reading the iggy files.
FontViewer.zip

Nice mate can you also please send me source to PM ?
## Post #30
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-25T05:03:16+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Here's the source code of the Font Viewer:


 IggyTools_src.zip
(7.2 KiB) Downloaded 86 times
## Post #31
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-25T11:36:58+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from herbert3000
>
> Here's the source code of the Font Viewer:
IggyTools_src.zip

I'm look forward to release iggy font editing tool!
## Post #32
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2016-11-26T01:35:25+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I found "iggy_w32.dll" it's from the game Trove and includes references to AS3 and fonts: [http://www28.zippyshare.com/v/Sbd6j66N/file.html](http://www28.zippyshare.com/v/Sbd6j66N/file.html)
## Post #33
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-27T10:04:06+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> I found "iggy_w32.dll" it's from the game Trove and includes references to AS3 and fonts: http://www28.zippyshare.com/v/Sbd6j66N/file.html

But Dishonored2 doesn't use iggy_w32.dll or iggy_w64.dll. By the way, it contains *.dll in the exe file.
## Post #34
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-27T21:42:43+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Here you go, first test.....
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-10T02:04:33+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Attached is texture converter for Dishonored 2. It should support conversion of all texture types, except for one I can't quite figure out yet. (but it's a very rare type, won't really affect anything).  

Be sure the *.bimage7_mip0 file is with the base *.bimage7 file if one exists; the utility will detect when one is supposed to be there and try to access it (to output the highest resolution texture possible).

Also at this time, Cubemaps aren't converted properly, only one side of the cube is converted. I'll continue to work to output a proper cubemap.

Normal maps will appear grey, this is because the Blue channel is set grey. Set Blue channel to White to produce a typical Normal Map used in most applications.

if the utility outputs any unknown format codes, feel free to share the filename of the bimage7 file that produces the code so I can add support.

Enjoy.

Edit: Fixed Cubemap support.

Edit: new version below.
## Post #36
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-10T10:28:44+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I have only one question. 

This game uses virtual textures  ??
## Post #37
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-10T16:29:49+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from luxox18
>
> I have only one question. 

This game uses virtual textures  ??

not that I've seen so far. Everything seems to be in bimage7 image format. In tech5 games like Wolfenstein, Bimage was only used for certain alpha textures like hair and eyebrows.  I'm seeing everything in Dishonored using Bimage7 though.  Diffuse maps, Normal maps, AO maps. So appears they opted not to use MegaTextures at all, though I still haven't checked into things like the overall Maps and static props yet.
## Post #38
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-12-12T09:18:12+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> 
not that I've seen so far. Everything seems to be in bimage7 image format. In tech5 games like Wolfenstein, Bimage was only used for certain alpha textures like hair and eyebrows.  I'm seeing everything in Dishonored using Bimage7 though.  Diffuse maps, Normal maps, AO maps. So appears they opted not to use MegaTextures at all, though I still haven't checked into things like the overall Maps and static props yet.

Thanks! that sounds good
## Post #39
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-12T17:23:52+00:00
- Post Title: Re: Dishonored2 (.bimage7)

p.s. for those interested I released first revision of my Dishonored model importer for blender here: [viewtopic.php?p=124978#p124978](http://forum.xentax.com/viewtopic.php?p=124978#p124978)
## Post #40
- Username: haluk444
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 13, 2016 6:49 am
- Post datetime: 2016-12-14T01:26:36+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I cannot use this texture program, I drag and drop the bimage7 and bimage7_mip0 files but it doesn't work. What should I do?
I only want the mask and the ring of the game, hence their textures.
## Post #41
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-14T18:20:06+00:00
- Post Title: Re: Dishonored2 (.bimage7)

you can't just drag and drop a file on it. It's a command line tool. Also you shouldn't be dropping Mip0 files on it even if it was. only bimage7 files. it detects and uses Mip0 automatically if applicable.

if you run it on the command line, you'd see the usage information:


it will process every texture in the input folder automatically, no need to drop one at a time and take forever.
## Post #42
- Username: haluk444
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 13, 2016 6:49 am
- Post datetime: 2016-12-15T16:50:27+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> you can't just drag and drop a file on it. It's a command line tool. Also you shouldn't be dropping Mip0 files on it even if it was. only bimage7 files. it detects and uses Mip0 automatically if applicable.

if you run it on the command line, you'd see the usage information:


it will process every texture in the input folder automatically, no need to drop one at a time and take forever.

I executed the program but it gives me highly erroneous results. Big pixels with no actual data.
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-15T17:33:12+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I'm not sure what that means. I can't help if you don't give me the name and location of the file you are having problems with.

Edit: after more thought, I think I know what the problem is. 

let me guess, by "big pixels", you mean the textures look something like this?



This has nothing to do with my converter. it works fine. It means your DDS viewer is outdated and can't handle the new BCx DDS formats. 

You need to get some tool that can handle BCx DDS. (also known as DX10 DDS formats).  Pretty much every game uses these new formats now, so it's a good investment. Unfortunately there's not a lot of tools yet.  Visual Studio 2013 or newer can handle it, there's also some Nvidia tools, but Mostly I prefer Photoshop with this new DDS plugin: [https://software.intel.com/en-us/articl ... rks-plugin](https://software.intel.com/en-us/articles/intel-texture-works-plugin)

Good luck.
## Post #44
- Username: haluk444
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 13, 2016 6:49 am
- Post datetime: 2016-12-15T18:03:45+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> I'm not sure what that means. I can't help if you don't give me the name and location of the file you are having problems with.

Edit: after more thought, I think I know what the problem is. 

let me guess, by "big pixels", you mean the textures look something like this?



This has nothing to do with my converter. it works fine. It means your DDS viewer is outdated and can't handle the new BCx DDS formats. 

You need to get some tool that can handle BCx DDS. (also known as DX10 DDS formats).  Pretty much every game uses these new formats now, so it's a good investment. Unfortunately there's not a lot of tools yet.  Visual Studio 2013 or newer can handle it, there's also some Nvidia tools, but Mostly I prefer Photoshop with this new DDS plugin: https://software.intel.com/en-us/articl ... rks-plugin

Good luck.
IT WORKED, THANK YOU SOO MUCH! I am doing a cosplay prop and when I put the 3d file on myminifactory.com I won't forget your name, Volfin!
## Post #45
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2016-12-25T20:48:43+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I managed to pull a few prop textures but when I got to characters (specifically The Outsider texture group, like t_str_outsider01_body_d.bimage7) the converter crashes on me with no error. Is it just me?

Edit: Alright, so over on my end when I use the command line with any file that doesn't include Mip0 files, I just get a program has stopped working error. Anything with Mips convert out and I can open them no problem.
## Post #46
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-26T00:55:27+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from windswept
>
> I managed to pull a few prop textures but when I got to characters (specifically The Outsider texture group, like t_str_outsider01_body_d.bimage7) the converter crashes on me with no error. Is it just me?

Edit: Alright, so over on my end when I use the command line with any file that doesn't include Mip0 files, I just get a program has stopped working error. Anything with Mips convert out and I can open them no problem.

I'd need example filename and extraction directory location.
## Post #47
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2016-12-26T14:20:55+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Sure! I'm copying out everything from \generated\image\models\characters\tall\str\outsider\textures, and any of those files singled out in a folder by themselves return a generic "Dishonored2_tex.exe has stopped working" error after I put in the command and the program confirms it's going to start converting the first file in the folder.
## Post #48
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-26T17:23:22+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from windswept
>
> Sure! I'm copying out everything from \generated\image\models\characters\tall\str\outsider\textures, and any of those files singled out in a folder by themselves return a generic "Dishonored2_tex.exe has stopped working" error after I put in the command and the program confirms it's going to start converting the first file in the folder.

I can't reproduce the error.  I tried with those files from both Game2.Resources, and Game3.Resources.  Both directories contain 52 files, you must have all 52 present.  I run the utility on the files and...



all 19 textures converted successfully.  The only possible thing I can think of is if you use a pathname that is too long, or has strange characters in it.  As you see I ran it from the file directory itself.   If you find out what is causing the failure, let me know, for future reference.  Thanks
## Post #49
- Username: MrKred
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 01, 2017 3:57 pm
- Post datetime: 2017-01-02T20:57:28+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from AceWell
>
> adol365 wrote:I can't see any glyphs. It's black.
Noesis has native support for that dx10 image

It doesn't work. Ive tried texture finder (which does display it if you compile it with the dev made dishonored 2 script but I doesnt render it properly), noesis, photoshop with Intel Texture Works Plugin. Nothing Works! Please I really want to view bimage7 files.
## Post #50
- Username: MrKred
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 01, 2017 3:57 pm
- Post datetime: 2017-01-02T21:04:26+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> Oh yeah I figured that out after a lot of trial and error 

I made a bms for the DXT5 .bimage7s
Code: Select allset MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x01\x00\x00\x80\x03\x00\x00\x00\x40\x0C\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"



get NAME basename
string NAME += ".dds"

get Id longlong
get Null long
get CompressionChar long
get Parl long
get Mipmaps long

goto 0x46
get WIDTH long
get HEIGHT long
get SIZE long
savepos OFFSET

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 SIZE long

append
log MEMORY_FILE OFFSET SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE

The problem now is that only some are in DXT5. Is there a way to automatically detect which compression it is? I couldn't figure anything out from the BIMAGE header

Also some textures have a .bimage7 and bimage7_mip0/1/2/3. Those are different sizes of the same texture but the _mips only contain the image data. I'm currently working on a script that stitches those parts together, I'll share it when it's done.

I run the script and it creats the dds file but its color is extremely messed up however I can still make out the outline of the object. Its the same thing that happens when Im using Texture Finder
## Post #51
- Username: MrKred
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 01, 2017 3:57 pm
- Post datetime: 2017-01-02T21:05:06+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> Oh yeah I figured that out after a lot of trial and error 

I made a bms for the DXT5 .bimage7s
Code: Select allset MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x01\x00\x00\x80\x03\x00\x00\x00\x40\x0C\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"



get NAME basename
string NAME += ".dds"

get Id longlong
get Null long
get CompressionChar long
get Parl long
get Mipmaps long

goto 0x46
get WIDTH long
get HEIGHT long
get SIZE long
savepos OFFSET

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 SIZE long

append
log MEMORY_FILE OFFSET SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE

The problem now is that only some are in DXT5. Is there a way to automatically detect which compression it is? I couldn't figure anything out from the BIMAGE header

Also some textures have a .bimage7 and bimage7_mip0/1/2/3. Those are different sizes of the same texture but the _mips only contain the image data. I'm currently working on a script that stitches those parts together, I'll share it when it's done.

I run the script and it creats the dds file but its color is extremely messed up however I can still make out the outline of the object. Its the same thing that happens when Im using Texture Finder
## Post #52
- Username: MrKred
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 01, 2017 3:57 pm
- Post datetime: 2017-01-02T21:44:36+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> Attached is texture converter for Dishonored 2. It should support conversion of all texture types, except for one I can't quite figure out yet. (but it's a very rare type, won't really affect anything).  

Be sure the *.bimage7_mip0 file is with the base *.bimage7 file if one exists; the utility will detect when one is supposed to be there and try to access it (to output the highest resolution texture possible).

Also at this time, Cubemaps aren't converted properly, only one side of the cube is converted. I'll continue to work to output a proper cubemap.

Normal maps will appear grey, this is because the Blue channel is set grey. Set Blue channel to White to produce a typical Normal Map used in most applications.

if the utility outputs any unknown format codes, feel free to share the filename of the bimage7 file that produces the code so I can add support.

Enjoy.

Edit: Fixed Cubemap support.

It goes to not responding one I try to compile whale_wet_01_d.bimage7 (Ive checked there's no mip files)
## Post #53
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-02T23:36:52+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from MrKred
>
> 
It goes to not responding one I try to compile whale_wet_01_d.bimage7 (Ive checked there's no mip files)

I have mip files, the *.mip0 is required.



However, it's not much use, it seems the unpacker is spitting out bad data:


You can make out "DUNWALL" at the bottom if you squint, this Mip0 block isn't the right data. So the texture is not recoverable. I suspect the actual data is considered "Shared" since this texture exists in both Pack 2 and Pack3  (shared_2_3...)

The fact remains that out of all the resource files, "Share_2_3.sharedrsc" is still not unpacked. It contains all the data shared between the "Good" and "Bad states of the world as you progress. So i'm not surprised to see something missing. Much in the game is missing because this file is still not unpacked.
## Post #54
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-03T02:08:37+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from MrKred
>
> AceWell wrote:adol365 wrote:I can't see any glyphs. It's black.
Noesis has native support for that dx10 image  

It doesn't work. Ive tried texture finder (which does display it if you compile it with the dev made dishonored 2 script but I doesnt render it properly), noesis, photoshop with Intel Texture Works Plugin. Nothing Works! Please I really want to view bimage7 files.
i don't know what you are trying to do here but the dx10 texture
i was refering to from michalss' post certainly opens fine in Noesis   
[viewtopic.php?p=124204#p124204](http://forum.xentax.com/viewtopic.php?p=124204#p124204)
and adol365 confirmed it works in Photoshop with the Intel-Texture-Works-Plugin too
## Post #55
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2017-01-13T20:53:16+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> The fact remains that out of all the resource files, "Share_2_3.sharedrsc" is still not unpacked. It contains all the data shared between the "Good" and "Bad states of the world as you progress. So i'm not surprised to see something missing. Much in the game is missing because this file is still not unpacked.

You can extract non compressed data from sharedrsc, see [http://zenhax.com/viewtopic.php?f=9&t=3678](http://zenhax.com/viewtopic.php?f=9&t=3678)
I'm still trying to extract compressed files but I'm not getting anywhere. Hopefully somebody can help.

There's also some image data somewhere in the .iggy files, any clue on how to get to that?
## Post #56
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-13T23:25:24+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> volfin wrote:The fact remains that out of all the resource files, "Share_2_3.sharedrsc" is still not unpacked. It contains all the data shared between the "Good" and "Bad states of the world as you progress. So i'm not surprised to see something missing. Much in the game is missing because this file is still not unpacked.

You can extract non compressed data from sharedrsc, see http://zenhax.com/viewtopic.php?f=9&t=3678
I'm still trying to extract compressed files but I'm not getting anywhere. Hopefully somebody can help.

There's also some image data somewhere in the .iggy files, any clue on how to get to that?

I recall there's a whole thread about the Iggy format elsewhere in the forum. I think under Localization.
## Post #57
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-17T08:25:32+00:00
- Post Title: Re: Dishonored2 (.bimage7)

There's now a way to unpack shared_2_3.sharedrsc.  Nice work by swinei figuring it mostly out.   

[http://zenhax.com/viewtopic.php?p=20249#p20249](http://zenhax.com/viewtopic.php?p=20249#p20249)

and yeah that missing whale texture is in there.
## Post #58
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2017-01-18T19:13:57+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> I recall there's a whole thread about the Iggy format elsewhere in the forum. I think under Localization.

Yeah, but that's mostly about the fonts. I'll definitely check it out.

> Reply from volfin
>
> There's now a way to unpack shared_2_3.sharedrsc.  Nice work by swinei figuring it mostly out.   

http://zenhax.com/viewtopic.php?p=20249#p20249

and yeah that missing whale texture is in there.

Props to you too!  I used dishonored2.bms 0.2.1 on all the index files and didn't get any errors.

e: I noticed that some files have the same name but different file sizes. Do you know what's up with that?
## Post #59
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-18T22:31:24+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> volfin wrote:I recall there's a whole thread about the Iggy format elsewhere in the forum. I think under Localization.

Yeah, but that's mostly about the fonts. I'll definitely check it out.
volfin wrote:There's now a way to unpack shared_2_3.sharedrsc.  Nice work by swinei figuring it mostly out.   

http://zenhax.com/viewtopic.php?p=20249#p20249

and yeah that missing whale texture is in there.  

Props to you too!  I used dishonored2.bms 0.2.1 on all the index files and didn't get any errors.

e: I noticed that some files have the same name but different file sizes. Do you know what's up with that?

yeah I think at least in the case of mip files, they probably handle high/ultra texture config that way. bigger files are higher rez textures. anything else, I don't know.
## Post #60
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2017-02-20T10:52:10+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from volfin
>
> yeah I think at least in the case of mip files, they probably handle high/ultra texture config that way. bigger files are higher rez textures. anything else, I don't know.

That makes sense. I converted all available bimage7 files to dds, there are about 600 files from the unknown format. I tried converting the dds files to png but many of them fail. I tried texconv imagemagick and Noesis. Noesis says it can't read the header. Could you share the source of your tool? I wanna try to change the headers to be able to convert them. Another thing I'd like to implement is recursive folder search because I'd like to keep the folder structure.
## Post #61
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-20T20:43:31+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Because I spend so much time making tools, I rarely get to play with the tools.    I rely on people to report issues, like things not converting. Why I made this program output clear failure info, so people would report it.  but since nobody did that, this morning I did 2 things.

A) added recursive batch file support   
B) ran it on all the files from pack 1

I found 5 new formats I hadn't seen before. So I added supports for 4 of them.  The 5th, there was only one example, and it seems to be a type of Cubemap which I will have to dig into more.  So if you see any other failures for format code 12 - 7, let me know, because only 1 example isn't much to go on. And if there's still any other codes that don't convert, let me know.

So enjoy the updated version.

- Added recursive batch file support. (place exe and included batch file in root directory, will process all files in all subdirectories, preserving hierarchy. output log is saved to converter.txt)
- Added support for format codes: 16 - 5, 4 -5, 10 - 6, 14 - 5

Enjoy.

Edit: newer below.
## Post #62
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2017-02-21T09:33:11+00:00
- Post Title: Re: Dishonored2 (.bimage7)

This is great, thank you very much! I found a couple 12 - 7 files, some 2 - 5 files and only one 6 - 7 file. Could you add the file name to the log output? I will send you the files then.

Also do you have any idea about converting the resulting dds files to png? I haven't tried Photoshop yet because I don't have it, and texconv, imagemagick and Noesis fail on many of the files.
## Post #63
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-21T17:37:36+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> This is great, thank you very much! I found a couple 12 - 7 files, some 2 - 5 files and only one 6 - 7 file. Could you add the file name to the log output? I will send you the files then.

Also do you have any idea about converting the resulting dds files to png? I haven't tried Photoshop yet because I don't have it, and texconv, imagemagick and Noesis fail on many of the files.

The file that fails is right above the failure message. 

example:
Converting D:\Program Files\SteamLibrary\steamapps\common\Dishonored2\base\out\Pack 1\generated\image\maps\campaign\dust\dust_sky_reflection.bimage7 ( 1 / 1 )
Unknown Format 12 - 7

so dust_sky_reflection.bimage7 failed.

As for conversion, there's very few tools that work with DX10 textures. the Photoshop Intel plugin is about it.  But a couple years ago before that was around, I tried to get a command line tool working.  You can give it a try, I have no idea if it handles all BCx formats, it may handle some:  [viewtopic.php?p=126949#p126949](http://forum.xentax.com/viewtopic.php?p=126949#p126949)

Also I understand the DirectX SDK (June 2010) should have a command line tool as well.
## Post #64
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2017-02-22T05:32:01+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Ah okay, you could put an empty line to make that more obvious. I uploaded the 2 - 5 and 12 - 7 files [here](https://drive.google.com/open?id=0B0SafYAmNuM4NVZMWGdtVnhrTWc). 12 -7 is still only two files but two is better than one 

About converting the files, I went with the new texconv.exe from DirectXTex, which is based on the SDK. One of the creators says [here](https://msdn.microsoft.com/library/windows/apps/hh452744) to use [DirectXTex](https://github.com/Microsoft/DirectXTex). It fails on two formats: BC6UCube and BC5S, could you take another look at those?
## Post #65
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-22T17:48:50+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from swinei
>
> Ah okay, you could put an empty line to make that more obvious. I uploaded the 2 - 5 and 12 - 7 files here. 12 -7 is still only two files but two is better than one 

About converting the files, I went with the new texconv.exe from DirectXTex, which is based on the SDK. One of the creators says here to use DirectXTex. It fails on two formats: BC6UCube and BC5S, could you take another look at those?

Well there's nothing for me to look at. I output industry standard DDS, which is why they all work with Intel Texturworks. if directxtex is failing it's something on their end. AFAIK that tool was only for Metal Gear Solid V, so probably has some quirks it expects. I'll look at the files you provided when I get time, had one of my PC's disk fail so recovery is my priority atm.
## Post #66
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-24T03:45:23+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Here's the version that adds support for the 2-5 textures. They aren't very useful, they seem to be data textures for calculating depth of field or something. but they convert now.

The 12-7 textures I simply can't figure out. They might also be strange data.  But since there's only less than a handful of them, and they are labeled as a cubemap, I think they are no big loss. I added the format code as a known but non-convertible.

Enjoy
[Dishonored2_tex v1.03.rar](https://xentaxbackup.github.io/file/12506_Dishonored2_tex v1.03.rar)
## Post #67
- Username: swinei
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Nov 18, 2016 6:22 am
- Post datetime: 2017-03-06T15:31:12+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Cool! And about those files I couldn't convert:

> For the BC5S files, they load with DirectXTex/texconv DDS loader just fine. The reason you are getting 80070032 (which is HRESULT_FROM_WIN32(ERROR_NOT_SUPPORTED)) is because PNG files don’t support writing the ‘native’ BC5S decompressed pixel format which is R8G8_SNORM. If you provide a format conversion it will work:
>
> 
>
>     texconv addermire_glass_01_n.bimage7.BC5S.dds -ft png -f R8G8B8A8_UNORM
>
> 
>
> The same problem is impacting your BC6H files because the native decompressed pixel format is R32G32B32A32_FLOAT which again is not a format supported by PNG—it is supported by HDR and WDP (HD Photo):
>
> 
>
>     texconv aud_pr_obe_1397_cube_bc6h_uf16.bimage7.BC6UCube.dds -ft hdr
>
> 
>
> There is a second issue in that the cubemap files contain 6 images, not just one. The TGA and HDR writers will just write the first image, but the WIC writer tries to encode multi-frame images, but this is not supported by PNG. You can use TIF to encode R32G32B32A32_FLOAT multi-frame images which works as well:
>
> 
>
>     texconv aud_pr_obe_1397_cube_bc6h_uf16.bimage7.BC6UCube.dds -ft tif
>
> 
>
> or
>
> 
>
>     texconv aud_pr_obe_1397_cube_bc6h_uf16.bimage7.BC6UCube.dds -ft tif -f R8G8B8A8_UNORM
>
> 
>
> You can also make use of the texassemble tool to write a cubemap in various single-image ways:
>
> 
>
>     texassemble h-strip aud_pr_obe_1397_cube_bc6h_uf16.bimage7.BC6UCube.dds -o cube.png -f R8G8B8A8_UNORM
>
> 
>
> -Chuck Walbourn
>
> 
>
> https://blogs.msdn.microsoft.com/chuckw/
## Post #68
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-06T17:11:59+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Ah, glad you were able to find a solution. I figured it had to be something with their tool. I appreciate you providing the details, they are interesting.
## Post #69
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2017-03-13T15:39:53+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Have weights been figured out yet?
## Post #70
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-13T16:05:12+00:00
- Post Title: Re: Dishonored2 (.bimage7)

they probably could be, but I  have no time to spend on it.
## Post #71
- Username: halfriv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 31, 2016 2:06 am
- Post datetime: 2017-04-07T07:20:56+00:00
- Post Title: Re: Dishonored2 (.bimage7)

I can't seem to get the converter to work? something about missing a heap.dll
## Post #72
- Username: NervousEnergy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 01, 2018 11:18 pm
- Post datetime: 2018-01-01T15:22:39+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Hey @volfin, thanks for the wonderful converter. Really helped me digging around the Dishonored game files. I just have two questions:

I've converted a few of the bimage textures to DDS using your converter, and then to PNG using Photoshop and the DDS plugin; mostly in-game posters and signs.

However they appear to be stretched thin a lil bit, see attached image. Anyone know the correct ratio the images should be in? I can then just resize the PNGs in Photoshop, but I want to know what ratio they should be. 

Secondly; I can't find anywhere the textures for Delilah's paintings that appear in end of Dunwall Tower. They don't appear to be in any of the normal folders like /pickups or /props. I've gone through hundreds of files. Are they stored in the maps directly...? Shame as they're really nice.
## Post #73
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-01-01T17:16:09+00:00
- Post Title: Re: Dishonored2 (.bimage7)

You'd have to find the mesh that the poster textures were applied to. They likely used the mesh UV mapping to alter the ratio.  It would probably be easier to take a screenshot in-game and eyeball what the in-game ratio should be.

I don't know anything about the location of Delilah's Paintings, sorry.
## Post #74
- Username: kodachrome
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 31, 2017 8:11 am
- Post datetime: 2018-01-01T22:36:42+00:00
- Post Title: Re: Dishonored2 (.bimage7)

On a related note, what about the paintings in general, the art-canvas looking ones? Id love to extract them and see what the would look like in the real world, on a real canvas print. But I cant find the asset files in the extracted resource container files!?

EDIT: Looks like I found them in 
game2.resources\generated\image\models\environment\props\generic\paintings_large

Not all of them mind you but its a start!
## Post #75
- Username: NervousEnergy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 01, 2018 11:18 pm
- Post datetime: 2018-01-02T06:57:56+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Hey @Kodachrome,

I actually found all the paintings in the files for Dishonored 2 Death of the Outsider! DofO basically seems to have all the textures from the original game in it's files, and has a lot of missing textures I've not been able to find (because they're stored directly in the map files maybe?). I've uploaded the PNGs for you here: [https://drive.google.com/open?id=1rlANv ... 89JsOsbPNx](https://drive.google.com/open?id=1rlANvKCz0ZWwnjyQmWD-tM89JsOsbPNx)
However, most of the paintings are actually concept art for the games - so you can generally find higher quality images online on ArtStation, or in the various art books. The textures are unfortunately fairly low quality.

@volfin thanks, good shout. I'll try that!
## Post #76
- Username: kodachrome
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 31, 2017 8:11 am
- Post datetime: 2018-01-02T15:49:03+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from NervousEnergy
>
> Hey @Kodachrome,

I actually found all the paintings in the files for Dishonored 2 Death of the Outsider! DofO basically seems to have all the textures from the original game in it's files, and has a lot of missing textures I've not been able to find (because they're stored directly in the map files maybe?). I've uploaded the PNGs for you here: https://drive.google.com/open?id=1rlANv ... 89JsOsbPNx
However, most of the paintings are actually concept art for the games - so you can generally find higher quality images online on ArtStation, or in the various art books. The textures are unfortunately fairly low quality.

@volfin thanks, good shout. I'll try that!
Many thanks, looks like you did indeed find more paintings than I did!  Thanks for sharing, though you are correct in that I might be better to span in Art book images. I do have a Dishonored 2 Artbook here already.. hmm. 

thanks again!
## Post #77
- Username: Goju Ponu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jan 03, 2018 7:28 am
- Post datetime: 2018-01-02T23:32:56+00:00
- Post Title: Re: Dishonored2 (.bimage7)

New here so I do not inherently know how links or other things are added, but I believe volfin said he had released a texture converter, yet I cannot seem to find a download link whatsoever on this post. Is it because the link was removed or am I just too much of a noob?
## Post #78
- Username: NervousEnergy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 01, 2018 11:18 pm
- Post datetime: 2018-01-02T23:38:41+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from Goju Ponu
>
> New here so I do not inherently know how links or other things are added, but I believe volfin said he had released a texture converter, yet I cannot seem to find a download link whatsoever on this post. Is it because the link was removed or am I just too much of a noob?

It's half way down the previous page;


> Reply from volfin
>
> Here's the version that adds support for the 2-5 textures. They aren't very useful, they seem to be data textures for calculating depth of field or something. but they convert now.

The 12-7 textures I simply can't figure out. They might also be strange data.  But since there's only less than a handful of them, and they are labeled as a cubemap, I think they are no big loss. I added the format code as a known but non-convertible.

Enjoy

Attachments:
File comment: V1.03

(This ad will go away if you contribute regularly.)

Dishonored2_tex v1.03.rar [13.55 KiB]

Downloaded 138 times
## Post #79
- Username: Goju Ponu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jan 03, 2018 7:28 am
- Post datetime: 2018-01-02T23:55:43+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from NervousEnergy
>
> Goju Ponu wrote:New here so I do not inherently know how links or other things are added, but I believe volfin said he had released a texture converter, yet I cannot seem to find a download link whatsoever on this post. Is it because the link was removed or am I just too much of a noob?

It's half way down the previous page;

volfin wrote:Here's the version that adds support for the 2-5 textures. They aren't very useful, they seem to be data textures for calculating depth of field or something. but they convert now.

The 12-7 textures I simply can't figure out. They might also be strange data.  But since there's only less than a handful of them, and they are labeled as a cubemap, I think they are no big loss. I added the format code as a known but non-convertible.

Enjoy

Attachments:
File comment: V1.03

(This ad will go away if you contribute regularly.)

Dishonored2_tex v1.03.rar [13.55 KiB]

Downloaded 138 times
Ah thank you so very much
## Post #80
- Username: Goju Ponu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jan 03, 2018 7:28 am
- Post datetime: 2018-01-03T00:18:37+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Another question, how exactly do I use this to convert the textures? 
I am trying to extract the Karnaca fish located in generated\image\models\environment\props\karnaca\dead_fish_01
## Post #81
- Username: NervousEnergy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 01, 2018 11:18 pm
- Post datetime: 2018-01-03T13:48:26+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from Goju Ponu
>
> Another question, how exactly do I use this to convert the textures? 
I am trying to extract the Karnaca fish located in generated\image\models\environment\props\karnaca\dead_fish_01

Did you figure it out in the end? It's a command line interface so maybe a lil bit confusing.
I've already converted all the textures, so I've uploaded the dead_fish ones for you in case you haven't figured it out yet! Here: [https://drive.google.com/open?id=1BwFbt ... 4rlcZ12I5a](https://drive.google.com/open?id=1BwFbtTUb2WDin_LCa1RQdj4rlcZ12I5a)
## Post #82
- Username: Goju Ponu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jan 03, 2018 7:28 am
- Post datetime: 2018-01-23T16:34:12+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from NervousEnergy
>
> Goju Ponu wrote:Another question, how exactly do I use this to convert the textures? 
I am trying to extract the Karnaca fish located in generated\image\models\environment\props\karnaca\dead_fish_01

Did you figure it out in the end? It's a command line interface so maybe a lil bit confusing.
I've already converted all the textures, so I've uploaded the dead_fish ones for you in case you haven't figured it out yet! Here: https://drive.google.com/open?id=1BwFbt ... 4rlcZ12I5a
Thank you so much. To answer your question no I still have not found out a way to convert or decrypt them. Very new to any sort of modding or model extracting, or anything on this forum.
## Post #83
- Username: NervousEnergy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 01, 2018 11:18 pm
- Post datetime: 2018-01-27T23:13:10+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from Goju Ponu
>
> NervousEnergy wrote:Goju Ponu wrote:Another question, how exactly do I use this to convert the textures? 
I am trying to extract the Karnaca fish located in generated\image\models\environment\props\karnaca\dead_fish_01

Did you figure it out in the end? It's a command line interface so maybe a lil bit confusing.
I've already converted all the textures, so I've uploaded the dead_fish ones for you in case you haven't figured it out yet! Here: https://drive.google.com/open?id=1BwFbt ... 4rlcZ12I5a
Thank you so much. To answer your question no I still have not found out a way to convert or decrypt them. Very new to any sort of modding or model extracting, or anything on this forum.

Ill do a lil walkthrough on how to do it.

We'll use generated\image\models\environment\props\karnaca\dead_fish_01 as an example.

There's two ways to use the texture converter. The first way is by using the programme via command prompt.

1. Navigate to where your 'Dishonored2_tex.exe' is located in Windows Explorer. On my machine it's located in 'C:\[my username]\Downloads\Dishonored2_tex v1.03'. Now create two folders in this directory; let's call one 'Input' and one called 'Output'.
2. Put ALL the dead_fish_01 files you want to convert into the 'Input' folder. In Dishonored 2's case a single texture is made up of a couple of files, so you need to put em all in.
2. Open up the command prompt by typing in 'cmd' into the Start Menu (if you're on Windows 10), or by typing 'cmd' into Run... (if you're on Windows 7). A black box will appear with some text. After "All rights reserved." will be a folder path, like 'C:\', with a blinking _ after it.
3. We need to tell command prompt to navigate to where Dishonored2_tex.exe is located. So type in 'cd [full folder path]'. For example on my machine I would type 'cd C:\[my username]\Downloads\Dishonored2_tex v1.03'. Now press enter. You'll see that the folder path will now appear. For reference 'cd' means 'change directory'; we're telling command prompt to navigate to that folder.
4. Now we need to start the converter program, so type in 'Dishonored2_tex.exe' and press enter. This opens the program in command prompt.
5. You'll see some text, the top of which says 'Must give 2 parameters!'. If you read it, you can see that the program needs the input and output folder locations too.
6. So now, type in 'Dishonored2_tex input output'. That's telling the program to look in the 'Input' folder for files to convert, and save them into the 'Output' folder.
7. Press enter - it'll tell you it will have converted the files!
8. Have a look at the 'Output' folder- all the converted DDS files are there!

That's the harder way to do this, and I thought it would be useful. But you'll also see in the initial download a 'convert_all_recursive.bat' file. What this bat file does is do steps 1 to 8 from above for you, but instantaneously. And instead of looking for the Input and Output folder it will look in all the folders and subfolders to the directory it is in, and save them into the same folders.

For example, place the texture converter files into the directory where you previously extracted all the .resource files. Now run the .bat file - it will take a while but it will eventually have converted the thousands and thousands (approx 10,000) textures into DDS format for you.

I hope that made sense!
## Post #84
- Username: Sinister
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 16, 2020 10:07 pm
- Post datetime: 2020-12-28T15:06:58+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Sorry, late for the party. Has anyone still got a link to that texture converter please?
## Post #85
- Username: Stut29
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 07, 2017 2:17 pm
- Post datetime: 2021-01-18T01:54:15+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from Sinister ↑Mon Dec 28, 2020 11:06 pm at Mon Dec 28, 2020 11:06 pm
>
> 
Sorry, late for the party. Has anyone still got a link to that texture converter please?
[viewtopic.php?f=10&p=127948#p127948](https://forum.xentax.com/viewtopic.php?f=10&p=127948#p127948)

I believe this is the latest version.
## Post #86
- Username: (HP)
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 14, 2022 7:15 am
- Post datetime: 2022-07-13T23:25:38+00:00
- Post Title: Re: Dishonored2 (.bimage7)

> Reply from Stut29 ↑Mon Jan 18, 2021 9:54 am at Mon Jan 18, 2021 9:54 am
>
> 
Sinister wrote: ↑Mon Dec 28, 2020 11:06 pm
Sorry, late for the party. Has anyone still got a link to that texture converter please?

viewtopic.php?f=10&p=127948#p127948

I believe this is the latest version.
Thanks man!
## Post #87
- Username: (HP)
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 14, 2022 7:15 am
- Post datetime: 2022-07-14T01:31:20+00:00
- Post Title: Re: Dishonored2 (.bimage7)

Because sometimes this kind of stuff gets lost in the ether of the internet and it becomes harder to puzzle it all together as time goes on, I've placed both the quickbms with the dishonored2.bms on the same folder, plus Dishonored2_tex v1.03 to convert all texs to .DDS file format.

[https://drive.google.com/file/d/1tzEaOa ... sp=sharing](https://drive.google.com/file/d/1tzEaOat4YGmDGKUCzE8sBCOXnk5Ln22N/view?usp=sharing)
