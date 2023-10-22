## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-26T06:40:39+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Wolfenstein the new order is a Id Tech 5 x64 game that run under opengl but textures can't be extracted or ripped because use the virtual textures system. (same engine that RAGE)

We can obtain models but no textures 

the *.pages files contain all textures but are compressed

someone can take a look of these *.pages files please? 



here are two pages files , one of 13mb and other 26mb

thanks
## Post #2
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-26T09:31:34+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

.pages file structure , all little endian

```
----------------------------
0x00   int[4]    0x77339904
0x04   int[4]    size in tiles
0x08   int[4]    ?
0x0c   int[4]    log2(size in tiles)
0x10   char[2]   'UU'
0x12   char[6]   ?
0x18   int[4]    size of the file in bytes
0x1c   int[4]    0x0
```


Information taken from this thread : [viewtopic.php?f=18&t=7763](http://forum.xentax.com/viewtopic.php?f=18&t=7763)

Hope someone can complete the job.
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-06-01T04:07:56+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

apparently the textures in *.pages files use JPEG XR with DCT based compression and the game transcode this images to DXT
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-06-03T08:57:17+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

here are some DCT images extracted from the game, the pages files have the same format but are compressed :/

DCT have the same header from a simple JPEG image but compression is different 

[http://www.mediafire.com/download/8yv1s ... acters.rar](http://www.mediafire.com/download/8yv1sn7d60y6d5j/characters.rar)
## Post #5
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-06-13T16:43:25+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

File structures:

```
enum pageCompression_t : int
{
	COMP_INVALID,
	COMP_NONE,
	COMP_DXT,
	COMP_LZW,
	COMP_DCT,
	COMP_HDP,
	COMP_JXR,
	COMP_MAX_COMPRESSIONS
};
enum  HDPFlags_t : int
{
	HDP_SPECULAR_SHIFT_MASK = 0x3,
	HDP_MONO_SPECULAR = 0x4,
	HDP_HAS_COVER = 0x8
};

struct pageHeader_t
{
	int magic;
	pageCompression_t pageCompression;
	unsigned int finerDiskOffset[4];
	unsigned short finerDiskLength[4];
	unsigned short x;
	unsigned short y;
	unsigned short level;
	unsigned short reserved;
};


struct pageFileHeader_t
{
	int magic;
	int pagesWide;
	int installedMipAndOffset;
	short numLevels;
	short layoutVersion;
	int totalPages;
	int diskOffsetScale;
	long long totalFileSize;
	//pageHeader_t subRoot;
};


struct HDPHeader_t
{
	unsigned char qualityDiffuse;
	unsigned char qualityNormal;
	unsigned char qualitySpecular;
	unsigned char qualityPower;
	unsigned char flags;
	unsigned char pad;
	unsigned short diffuseSize;
	unsigned short normalSize;
	unsigned short specularSize;
	unsigned short powerSize;
	unsigned short alphaSize;
};


```


Now used HD photo, very similar to [this specification](http://www.microsoft.com/en-us/download/details.aspx?id=5863).
## Post #6
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2014-06-20T19:13:01+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Any new news?
## Post #7
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-06-24T03:17:13+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

nope , nothing
## Post #8
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2014-07-06T10:29:57+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Can somebody please figure out that.
## Post #9
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-11T23:53:45+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Well, thanks to the info m0xF posted, I can now navigate the QuadTree pretty well.

This 010 script will break down a single branch of the quadtree in most any *.pages file:

```
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
LittleEndian();

enum pageCompression_t 
{
   COMP_INVALID,
   COMP_NONE,
   COMP_DXT,
   COMP_LZW,
   COMP_DCT,
   COMP_HDP,
   COMP_JXR,
   COMP_MAX_COMPRESSIONS
};

enum  HDPFlags_t
{
   HDP_SPECULAR_SHIFT_MASK = 0x3,
   HDP_MONO_SPECULAR = 0x4,
   HDP_HAS_COVER = 0x8
};

typedef struct HDPHeader_t
{
   unsigned char qualityDiffuse;
   unsigned char qualityNormal;
   unsigned char qualitySpecular;
   unsigned char qualityPower;
   unsigned char flags;
   unsigned char pad;
   unsigned short diffuseSize;
   unsigned short normalSize;
   unsigned short specularSize;
   unsigned short powerSize;
   unsigned short alphaSize;
};

typedef struct pageHeader_t
{
   uint magic_signature; // Signatuer ID 0xCABFED04
   pageCompression_t pageCompression; // Compression Type (seems always 0x05, HDP Type)
   uint PageDiskOffset[4];  // Sub-Node Offset from start of file, divided by DiskOffsetScale
   ushort PageDiskLength[4]; // Sub-Node Length, divided by DiskOffsetScale
   ushort x; // Unclear, deeper nodes have larger values (Perhaps quardrant location)
   ushort y; // Unclear, deeper nodes have larger values (Perhaps quardrant location)
   ushort QuadTreeLevel;  // Node's level in the Quadtree
   ushort reserved;
};


 struct Pages_File { 
    char Signature[4]; // Signatuer ID 0x77339904
    ulong pageswide;  // # of pages wide (always square so also # of pages tall) Possibly needs multiplied by DiskOffsetScale.
    ulong installedMipAndOffset; // purpose unclear
    ushort QuadtreeLevelCount;   // How many levels to the Quadtree
    ushort LayoutVer; // always zero?
    ulong totalPages; // Number seems inaccurate, almost always 0x155555
    ulong DiskOffsetScale; // Factor to scale various offsets and sizes by. 
    uint64 totalFileSize; // Size of the file in bytes.


// Root node
pageHeader_t SubRoot; 

// subnodes
pageHeader_t SubRoot; // Read Leaf Data
BigEndian();
HDPHeader_t test; // Get DCT header data
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata1[SubRoot[0].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[0].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[1].PageDiskOffset[0]*DiskOffsetScale);


pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata2[SubRoot[1].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[1].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[2].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata3[SubRoot[2].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[2].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[3].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata4[SubRoot[3].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[3].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[4].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata5[SubRoot[4].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[4].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[5].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata6[SubRoot[5].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[5].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[6].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata7[SubRoot[6].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[6].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[7].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;
BigEndian();
HDPHeader_t test;
LittleEndian();
// Get Data for Leaf (based on Offset/Length parent leaf specified)
char compdata8[SubRoot[7].PageDiskLength[0]*DiskOffsetScale-(FTell()-SubRoot[7].PageDiskOffset[0]*DiskOffsetScale)];
// Move to first subleaf of leaf we just read.
FSeek(SubRoot[8].PageDiskOffset[0]*DiskOffsetScale);

pageHeader_t SubRoot;

} MegaTexture;
```


I only go 8 levels deep, though most of these quadtrees have 12 levels. I'm only skimming the outer edge of the tree.

At any rate, it breaks the file down to the page level.  

The Page_Block data is the data in the arrays named compdata1 thru compdata8.

According to what ID has said, a Page_Block should be a 128x128 pixel block with 10 layers (3 layers; RGB diffuse, 3 layers; RGB Specular, 2 Layers; RG Normal, 1 Layer; Alpha, 1 Layer; Power). 

So this is where I am now, figuring out how this block of data decodes to a 10 layer 128 by 128 pixel block. The endcoing is supposed to be JPEG XR type DCT, but that leaves things very open ended. There's also a lot of talk about Huffman encoding, so I'm unclear if the disk image is Huffman compressed on top of DCT compressed or not.

I notice these blocks tend to all start with the same byte sequence:

```
0x71 0x00 0xA3 0xC6 0x0A 0x3C 0x60 0xA3 0xC6 0x00 0xFF 0x00 0x00
```

which tells me there is probably another data structure on top here yet undiscovered.  But at least a few layers of the onion are now peeled away. I'll keep at it.
## Post #10
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2014-07-12T10:39:57+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Nice work many THX.   

How can i load this script to test it.
## Post #11
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-12T16:51:07+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from ZerOHearth
>
> Nice work many THX.   

How can i load this script to test it.
It's scripted in 010 Editor. [http://www.010editor.com](http://www.010editor.com)

You would open the *.pages file with 010 editor, then the file I pasted above as a template (usually named *.bt)

For viewing data 010 is pretty good. Things like QuickBMS are better at creating output once you know what's what. I could probably make a QuickBMS script based on this to dump the Page_Blocks for easier examination. but will be a day or two. I have some other work to do first.
## Post #12
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-14T03:51:19+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Here's a BMS script to cut out the first 3 page_blocks it encounters as 3 discrete files "Page_Block0.dat", "Page_Block1.dat", and "Page_block2.dat". It also prints the header info for those blocks.  

```

endian little

startfunction Print_Header
	endian big # header is Big Endian for some reason
	print "---"
	get DiffuseQuality byte
	print "DiffuseMap Quality: %DiffuseQuality%"
	get NormalQuality byte
	print "NormalMap Quality: %NormalQuality%"
	get SpecularQuality byte
	print "SpecularMap Quality: %SpecularQuality%"
	get PowerQuality byte
	print "PowerMap Quality: %PowerQuality%"
	get Flags byte
	print "Flags: %Flags%"
	get padding byte
	print "padding ignore?: %padding%"

	get DiffuseSize short
	print "DiffuseMap DataSize: %DiffuseSize%"
	get NormalSize short
	print "NormalMap DataSize: %NormalSize%"
	get SpecularSize short
	print "SpecularMap DataSize: %SpecularSize%"
	get PowerSize short
	print "PowerMap DataSize: %PowerSize%"
	get AlphaSize short
	print "AlphaMap DataSize: %AlphaSize%"
	print "---------------------------"
	endian little # back to little for the rest of the file
endfunction

goto 0x14 
get DiskOffsetScale long
print "Diskoffsetscale:%DiskOffsetScale%"
goto 0x28
get Block0_Offset long 
goto 0x38
get Block0_Length short

math Block0_Offset * DiskOffsetScale
math Block0_Length * DiskOffsetScale
print "-- Page_Block0.dat ------------------------"

xmath Block0_Offset_skipheader "Block0_Offset + 56"
xmath Block0_Length_skipheader "Block0_Length - 56"
print "Block0_Offset:%Block0_Offset_skipheader%"
print "Block0_Length:%Block0_Length_skipheader%"
# skip to header and print it.
xmath Block0_Offset_atheader "Block0_Offset + 40"
goto Block0_Offset_atheader
callfunction Print_Header

#dump Page_block zero
log "Page_Block0.dat" Block0_Offset_skipheader Block0_Length_skipheader

math Block0_Offset + 8 #skip to first sub-Page_block
goto Block0_Offset

# get all the branches for testing
get Block1_Offset1 long 
get Block1_Offset2 long
get Block1_Offset3 long
get Block1_Offset4 long
get Block1_Length1 short
get Block1_Length2 short
get Block1_Length3 short
get Block1_Length4 short

# Find a branch that's populated (the first may not always be at the top)
if Block1_Offset1 != 0
	print "Branch 1 chosen."
	math Block1_Offset = Block1_Offset1
	math Block1_Length = Block1_Length1
elif Block1_Offset2 != 0
	print "Branch 2 chosen."
	math Block1_Offset = Block1_Offset2
	math Block1_Length = Block1_Length2
elif Block1_Offset3 != 0
	print "Branch 3 chosen."
	math Block1_Offset = Block1_Offset3
	math Block1_Length = Block1_Length3
elif Block1_Offset4 != 0
	print "Branch 4 chosen."
	math Block1_Offset = Block1_Offset4
	math Block1_Length = Block1_Length4
endif

math Block1_Offset * DiskOffsetScale
math Block1_Length * DiskOffsetScale
print "-- Page_Block1.dat ------------------------"

xmath Block1_Offset_skipheader "Block1_Offset + 56"
xmath Block1_Length_skipheader "Block1_Length - 56"
print "Block1_Offset:%Block1_Offset_skipheader%"
print "Block1_Length:%Block1_Length_skipheader%"

# skip to header and print it.
xmath Block1_Offset_atheader "Block1_Offset + 40"
goto Block1_Offset_atheader
callfunction Print_Header

#dump Page_block zero
log "Page_Block1.dat" Block1_Offset_skipheader Block1_Length_skipheader

math Block1_Offset + 8 #skip to first sub-Page_block
goto Block1_Offset
get Block2_Offset long 
math Block1_Offset + 16 
goto Block1_Offset
get Block2_Length short
math Block2_Offset * DiskOffsetScale
math Block2_Length * DiskOffsetScale
print "-- Page_Block2.dat ------------------------"

xmath Block2_Offset_skipheader "Block2_Offset + 56"
xmath Block2_Length_skipheader "Block2_Length - 56"
print "Block2_Offset:%Block2_Offset_skipheader%"
print "Block2_Length:%Block2_Length_skipheader%"

# skip to header and print it.
xmath Block2_Offset_atheader "Block2_Offset + 40"
goto Block2_Offset_atheader
callfunction Print_Header

#dump Page_block zero
log "Page_Block2.dat" Block2_Offset_skipheader Block2_Length_skipheader

cleanexit
```


Here's a sample of the printout from "c12p1.pages"

> Diskoffsetscale:2
>
> 
>
>   -- Page_Block0.dat ------------------------
>
> 
>
>   Block0_Offset:128
>
>   Block0_Length:5870
>
>   ---
>
>   DiffuseMap Quality: 30
>
>   NormalMap Quality: 13
>
>   SpecularMap Quality: 25
>
>   PowerMap Quality: 40
>
>   Flags: 6
>
>   padding ignore?: 0
>
>   DiffuseMap DataSize: 1720
>
>   NormalMap DataSize: 3218
>
>   SpecularMap DataSize: 803
>
>   PowerMap DataSize: 128
>
>   AlphaMap DataSize: 0
>
>   ---------------------------
>
> 
>
>   00000080 5870       Page_Block0.dat
>
> 
>
>   Branch 2 chosen.
>
> 
>
> 
>
>   -- Page_Block1.dat ------------------------
>
> 
>
>   Block1_Offset:6054
>
>   Block1_Length:9170
>
>   ---
>
>   DiffuseMap Quality: 30
>
>   NormalMap Quality: 13
>
>   SpecularMap Quality: 25
>
>   PowerMap Quality: 40
>
>   Flags: 6
>
>   padding ignore?: 0
>
>   DiffuseMap DataSize: 3043
>
>   NormalMap DataSize: 4004
>
>   SpecularMap DataSize: 1951
>
>   PowerMap DataSize: 171
>
>   AlphaMap DataSize: 0
>
>   ---------------------------
>
> 
>
>   000017a6 9170       Page_Block1.dat
>
> 
>
>   -- Page_Block2.dat ------------------------
>
> 
>
>   Block2_Offset:21758
>
>   Block2_Length:13040
>
>   ---
>
>   DiffuseMap Quality: 30
>
>   NormalMap Quality: 13
>
>   SpecularMap Quality: 25
>
>   PowerMap Quality: 40
>
>   Flags: 5
>
>   padding ignore?: 0
>
>   DiffuseMap DataSize: 4655
>
>   NormalMap DataSize: 4633
>
>   SpecularMap DataSize: 3514
>
>   PowerMap DataSize: 238
>
>   AlphaMap DataSize: 0
>
>   ---------------------------
>
> 
>
>   000054fe 13040      Page_Block2.dat
>
> 
>
> - 3 files found in 0 seconds
>
>   coverage file 0     0%   28168      13563938

There's some interesting patterns in these numbers. For one, the sum of the different *Map DataSizes adds up to the whole block size. For example on Block 2: 4655+4633+3514+238+0=13040 which you notice is the size of that block (Block2_Length).

So those likely point into the block to indicate where the various layer types start. The "Quality" parameters probably indicate the amount of DCT compression peformed on each layer. And the "Flags" may be in reference to the "HDPFlags_t" type m0xF laid out earlier. but if so, some values are missing. 

Perhaps this will help someone with exploring these Page_Blocks as a discrete entity. I feel we only need to determine how to decode a single Page_Block to crack this open. Knowing where the layers begin/end is a small but important step toward that.
## Post #13
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-07-14T04:51:43+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

amazing work volfin! keep it up
## Post #14
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-07-16T14:13:24+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

Data blocks represents HDPhoto bitstream without IMAGE_HEADER (see "HDPhoto_Bitstream_Spec_1.0.doc"). It's very complex format. I tried to adapt HD photo decoding library, but without results.
## Post #15
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-16T20:05:15+00:00
- Post Title: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from m0xf
>
> Data blocks represents HDPhoto bitstream without IMAGE_HEADER (see "HDPhoto_Bitstream_Spec_1.0.doc"). It's very complex format. I tried to adapt HD photo decoding library, but without results.

yes, i've been pursuing that as well, though using the JPEG XR specification (which is materially identical). [http://www.itu.int/rec/T-REC-T.832](http://www.itu.int/rec/T-REC-T.832)
So far I haven't  been able to produce any recognizable output either.  I fear they may be LZW compressing it on top of the DCT transform, or may be using a custom colorspace (some slides talk about using 5:4:0 which isn't a standard colorspace for HDP; it only recognizes 4:2:0/4:4:4/4:2:2)

So right now i've pretty much hit a brick wall.
## Post #16
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-07-17T19:06:07+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Images are compressed with HDphoto, not Jpeg XR. This specs are similar, but has some difference. And yes, duffuse map using YCoCg color space.
## Post #17
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-17T21:40:51+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from m0xf
>
> Images are compressed with HDphoto, not Jpeg XR. This specs are similar, but has some difference. And yes, duffuse map using YCoCg color space.

Ok, I'll have a look then. I've saved files as both JXR (Jpeg XR) and WDP (Windows HD Photo) using a popular imaging app, and the formats seemed identical. But i'll take your word for it they are not the same. At least from what I observed with this template file I created for JXR.

```
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author: Volfin
// Revision:
// Purpose: Decode Jpeg XR headers
//--------------------------------------

local ulong n;
local int i;
local ulong ifd_offset;
local ubyte x;
local ushort Num_Components;
local ushort NumLPQPs;
local ushort NumHPQPs;
local ubyte NumBands;
local ulong valueNumIndexTableEntries;
local uint NumMBInTile[100];

local ulong NumMBInCurrentTile;
local ulong NumBandsOfPrimary;
local ubyte IsCurrPlaneAlphaFlag=FALSE;
local uint64 Subsequent_Bytes;
local ulong valueAdditionalBytes;
local ulong iBytes;
local ubyte lastflag;
local ushort Num_Vert_Tiles_Minus1=0;
local ushort Num_Horiz_Tiles_Minus1=0; 
local uint64 IndexOffsetTile[16];

void do_coded_tiles()
{
   local uint64 current_pointer;
   current_pointer=FTell();

   Printf("staring do_coded_tiles() FilePos:%ld\n",FTell());
    // 8.7.1
    if (IMG_HDR.Freq_Mode_Codestream_Flag == 0)
    {
        for(n=0;n<(Num_Horiz_Tiles_Minus1+1)*(Num_Vert_Tiles_Minus1+1);n++)
        {
            NumMBInCurrentTile=NumMBInTile[n];
            FSeek(IndexOffsetTile[n]+current_pointer);
            TILE_SPATIAL();
        }
    }
    else
    {
        for(n=0;n<(Num_Horiz_Tiles_Minus1+1)*(Num_Vert_Tiles_Minus1+1);n++)
        {
            NumMBInCurrentTile=NumMBInTile[n];
            FSeek(IndexOffsetTile[n*NumBandsOfPrimary]+current_pointer);
            TILE_DC();
        }        
    }

    if (NumBandsOfPrimary > 1)
    {
        for(n=0;n<(Num_Horiz_Tiles_Minus1+1)*(Num_Vert_Tiles_Minus1+1);n++)
        {
            NumMBInCurrentTile=NumMBInTile[n];
            FSeek(IndexOffsetTile[n*NumBandsOfPrimary+1]+current_pointer);
            TILE_LOWPASS();
        }            
    }

    if (NumBandsOfPrimary > 2)
    {
        for(n=0;n<(Num_Horiz_Tiles_Minus1+1)*(Num_Vert_Tiles_Minus1+1);n++)
        {
            NumMBInCurrentTile=NumMBInTile[n];
            FSeek(IndexOffsetTile[n*NumBandsOfPrimary+2]+current_pointer);
            TILE_HIGHPASS();
        }            
    }

    if (NumBandsOfPrimary > 3)
    {
        for(n=0;n<(Num_Horiz_Tiles_Minus1+1)*(Num_Vert_Tiles_Minus1+1);n++)
        {
            NumMBInCurrentTile=NumMBInTile[n];
            FSeek(IndexOffsetTile[n*NumBandsOfPrimary+3]+current_pointer);
            TILE_FLEXBITS();
        }            
    }
}

void TILE_SPATIAL()
{
    Printf("Tile_Spatial\n");
    ulong Tile_Startcode:24;
    uchar Arbitrary_Byte;    
}
///////////////////////////////////////////////////////
void TILE_DC()
{
    Printf("Tile_DC\n");
    ulong Tile_Startcode:24;
    uchar Arbitrary_Byte;
    IsCurrPlaneAlphaFlag=FALSE;
    TILE_HEADER_DC();
    if (IMG_HDR.Alpha_Image_Plane_Flag)
    {
        IsCurrPlaneAlphaFlag = TRUE;
        TILE_HEADER_DC( ); //8.7.4
    }
    for (n = 0; n < NumMBInCurrentTile; n++)
    {
        IsCurrPlaneAlphaFlag = FALSE;
        MB_DC( ); //8.7.11
        if (IMG_HDR.Alpha_Image_Plane_Flag)
        {
            IsCurrPlaneAlphaFlag = TRUE;
            MB_DC( ); //8.7.11
        }
    }

    //while (!IS_BYTE_ALIGNED( ))
        //BYTE_ALIGNMENT_BIT
}

void TILE_HEADER_DC()
{
    if (IMG_PL_HDR.DC_Image_Plane_Uniform_Flag == FALSE)
    {
        DC_QP( ); //8.4.22
    }    
}
//////////////////////////////////////////////////////////
void TILE_LOWPASS()
{
    Printf("Tile_Lowpass\n");
    ulong Tile_Startcode:24;
    uchar Arbitrary_Byte;

    IsCurrPlaneAlphaFlag=FALSE;
    if (IMG_PL_HDR.Bands_Present!= 3) /*  DCONLY - BANDS_PRESENT of primary image plane */
        TILE_HEADER_LOWPASS( ); // 8.7.6

    if (IMG_HDR.Alpha_Image_Plane_Flag)
    {
        IsCurrPlaneAlphaFlag = TRUE;
        if (IMG_PL_HDR.Bands_Present != 3) /* DCONLY - BANDS_PRESENT of alpha image plane */
            TILE_HEADER_LOWPASS( ); //8.7.6
    }

    for (n = 0; n < NumMBInCurrentTile; n++)
    {
        IsCurrPlaneAlphaFlag = FALSE;
        if (IMG_PL_HDR.Bands_Present != 3) // DCONLY 
        { /* BANDS_PRESENT of primary image plane */
            if (NumLPQPs > 1 && USE_DC_QP_FLAG == FALSE)
            LP_QP_INDEX[n] = DECODE_QP_INDEX(NumLPQPs); /* primary image plane */
            MB_LP( ); //8.7.16.1
        }
        if (IMG_HDR.Alpha_Image_Plane_Flag)
        {
            IsCurrPlaneAlphaFlag = TRUE;
            if (IMG_PL_HDR.Bands_Present != 3) // DCONLY
            { /* BANDS_PRESENT of alpha image plane */
                if (NumLPQPs > 1 && USE_DC_QP_FLAG == FALSE)
                    LP_QP_INDEX[n] = DECODE_QP_INDEX(NumLPQPs);  /* alpha image plane */

                MB_LP( );
            }
        }
    }

    //while (!IS_BYTE_ALIGNED( ))
      //  BYTE_ALIGNMENT_BIT
}

void TILE_HEADER_LOWPASS()
{
    if (IMG_PL_HDR.DC_Image_Plane_Uniform_Flag == FALSE)
    {
        ubyte USE_DC_QP_FLAG:1;
        if (USE_DC_QP_FLAG)
        {
            NumLPQPs = 1;
        }
        else
        {
            ubyte NUM_LP_QPS_MINUS1:4;
            NumLPQPs = NUM_LP_QPS_MINUS1+1;
            LP_QP();
        }
    }    
}
/////////////////////////////////////////////////////////
void TILE_HIGHPASS()
{
    Printf("Tile_HighPass\n");
    ulong Tile_Startcode:24;
    uchar Arbitrary_Byte;
}
/////////////////////////////////////////////////////////
void TILE_FLEXBITS()
{
    Printf("Tile_FLEXBITS\n");
    ulong Tile_Startcode:24;
    uchar Arbitrary_Byte;
}
/////////////////////////////////////////////////////////
void DC_QP()
{
    if (Num_Components != 1)
    {
        ubyte Component_Mode:2;
        if (Component_Mode == 0) //UNIFORM
        {
            ubyte DC_QUANT:8;
        }
        else if (Component_Mode == 1) //SEPARATE
        {
            ubyte DC_QUANT_LUMA:8;
            ubyte DC_QUANT_CHROMA:8;
        }
        else if (Component_Mode == 2) //INDEPENDENT
        {
            for (i=0;i<Num_Components;i++)
            {
                ubyte DC_QUANT_CH:8;
            }         
        }    
    }    
}

void LP_QP()
{
    for (i = 0; i < NumLPQPs; i++)
    {
        if (Num_Components != 1)
        {
            ubyte COMPONENT_MODE:2;

            if (COMPONENT_MODE == 0) // UNIFORM
            {
                ubyte LP_QUANT:8;
            }
            else if (COMPONENT_MODE == 1)//SEPARATE
            {
                ubyte LP_QUANT_LUMA:8;
                ubyte LP_QUANT_CHROMA:8;
            }
            else if (COMPONENT_MODE == 2)//INDEPENDENT
            {
                for (i = 0; i < Num_Components; i++)
                {
                    ubyte LP_QUANT_CH:8;
                }
            }
        }
    }
}

void HP_QP()
{
    for (i = 0; i < NumHPQPs; i++)
    {
        if (Num_Components != 1)
        {
            ubyte COMPONENT_MODE:2;

            if (COMPONENT_MODE == 0) // UNIFORM
            {
                ubyte HP_QUANT:8;
            }
            else if (COMPONENT_MODE == 1)//SEPARATE
            {
                ubyte HP_QUANT_LUMA:8;
                ubyte HP_QUANT_CHROMA:8;
            }
            else if (COMPONENT_MODE == 2)//INDEPENDENT
            {
                for (i = 0; i < Num_Components; i++)
                {
                    ubyte HP_QUANT_CH:8;
                }
            }
        }
    }
}

void do_IMG_PL_HDR()
{
  // 8.4.1
    struct IMG_PLANE_HDR
    {
        ubyte Internal_CLR_Format:3;
        ubyte Scaled_flag:1;
        ubyte Bands_Present:4;
        
        if (Bands_Present == 0)
            NumBands=4;
        else if (Bands_Present == 1)
            NumBands=3;
        else if (Bands_Present == 2)
            NumBands=2;
        else if (Bands_Present == 3)
            NumBands=1;
        if (IsCurrPlaneAlphaFlag==0)
        {
            NumBandsOfPrimary = NumBands;
        }
    
        if (Internal_CLR_Format == 1 || Internal_CLR_Format == 2 || Internal_CLR_Format == 3)
        {
            Num_Components=3;
            // YUV420 or YUV422 or YUV444
            if (Internal_CLR_Format == 1 || Internal_CLR_Format == 2)
            {
                // YUV420/YUV422
                ubyte Reserved_E:1;
                ubyte Chroma_Centering_X:3;                
            }
            else
            {
                ubyte Reserved_F:4;
            }


            if (Internal_CLR_Format == 1)
            {
                // YUV420
                ubyte Reserved_G:1;
                ubyte Chroma_Centering_Y:3;
            }
            else
            {
                ubyte Reserved_H:4;
            }
        }
        else if (Internal_CLR_Format == 6)
        {
            // NComponent 
            ubyte Num_Components_Minus1:4;
            if (Num_Components_Minus1 == 0xF)
            {
                ushort Num_Components_Extended_Minus16:12;
                Num_Components=Num_Components_Extended_Minus16+16;
            }
            else
            {
                ubyte Reserved_H2:4;
                Num_Components=Num_Components_Minus1+1;
            }
            
        }
        else if (Internal_CLR_Format == 4) //YUVK
            Num_Components=4;
        else if (Internal_CLR_Format == 0) // YONLY
            Num_Components=1;
      
        // Bitdepth from IMG_HDR.Output_Bitdepth
        if (IMG_HDR.Output_Bitdepth == 2 || IMG_HDR.Output_Bitdepth == 3 || IMG_HDR.Output_Bitdepth == 6)
        {
            ubyte Shift_Bits;
        }
        if (IMG_HDR.Output_Bitdepth == 7)
        {
            ubyte LEN_Mantissa;
            byte EXP_Bias;
        }
    
        ubyte DC_Image_Plane_Uniform_Flag:1;
    
        if (DC_Image_Plane_Uniform_Flag)
        {
            DC_QP();
        }

        if (Bands_Present != 3) // DCONLY
        {
            ubyte Reserved_I:1;
            ubyte LP_Image_Plane_Uniform_Flag:1;
            if (LP_Image_Plane_Uniform_Flag)
            {
                NumLPQPs=1;
                LP_QP();
            }
            if (Bands_Present != 2) // NOHIGHPASS
            {
                ubyte Reserved_J:1;
                ubyte HP_Image_Plane_Uniform_Flag:1;
                if (HP_Image_Plane_Uniform_Flag)
                {
                    NumHPQPs=1;
                    HP_QP();
                }        
            }        
        }
        
//        ubyte IsByteAligned;
//        ubyte dummy;  
    } IMG_PL_HDR;
}

uint64 VLW_ESC()
{
    struct VLW_Bytes
    {
        ubyte FIRST_BYTE:8;
        if (FIRST_BYTE <0xFB)
        {
            ubyte SECOND_BYTE:8;
            return(FIRST_BYTE*256+SECOND_BYTE);
        }
        else if (FIRST_BYTE==0xFB)
        {
            ulong FOUR_BYTES:32;
            return FOUR_BYTES;
        }
        else if (FIRST_BYTE==0xFC)
        {
            uint64 EIGHT_BYTES:64;
            return EIGHT_BYTES;
        }
        else return 0;
    } VLW_BYTES;
}

ulong Profile_Level_Info()
{
    local ulong mmBytes=0;
    local ulong iLast;
    lastflag=0;
    for (iLast=0;iLast==0;iLast=lastflag)
    {
        struct Profile 
        {
            ubyte PROFILE_IDC;
            ubyte LEVEL_IDC;
            ushort Reserved_L:15;
            ubyte LAST_FLAG:1;
            lastflag=LAST_FLAG;
        } PROFILE;
        mmBytes=mmBytes+4;
    }
    return mmBytes;
}

//////////////////////////////////////
LittleEndian();
BitfieldLeftToRight();
BitfieldDisablePadding();


struct Header { 
    char fixed_header_II[2]; 
    ubyte fixed_header_0XBC;
    ubyte version_id;
    long first_IFD_Offset;    
  } HEADER;

FSeek(HEADER.first_IFD_Offset);

struct Image_File_Directory {
    short NUM_ENTRIES;
    for (i=0;i<NUM_ENTRIES;i++)
    {
        struct IFD_ENTRY {
            short FIELD_TAG;
            short ELEMENT_TYPE;
            long NUM_ELEMENTS;
            long VALUES_OR_OFFSET;
        } IFDE;
    }
    long NEXT_IFD;
}IFD;

BigEndian();

struct Image_Header {
    char GDI_SIG[8];
    ubyte Reserved_B:4;
    ubyte Hard_tiling_flag:1;
    ubyte Reserved_C:3;
    ubyte Tiling_Flag:1;
    ubyte Freq_Mode_Codestream_Flag:1;
    ubyte Spatial_Xfrm_Subordinate:3;
    ubyte Index_Table_Flag:1;
    ubyte Overlap_Mode:2;
    ubyte Short_header_flag:1;
    ubyte Long_Word_Flag:1;
    ubyte Windowing_Flag:1;
    ubyte Trim_Flexbits_Flag:1;
    ubyte Reserved_D:1;
    ubyte Red_Blue_not_Swapped_Flag:1;
    ubyte Premultiplied_Alpha_Flag:1;
    ubyte Alpha_Image_Plane_Flag:1;
    ubyte Output_CLR_FMT:4;
    ubyte Output_Bitdepth:4;

    if (Short_header_flag)
    {
        ushort Width_Minus1;
        ushort Height_Minus1;
    }
    else
    {
        ulong Width_Minus1;
        ulong Height_Minus1;
    }

    if (Tiling_Flag)
    {
        // numbers are in 12 bits for some reason
        ushort Num_Vert_Tiles_Minus1t:12;
        ushort Num_Horiz_Tiles_Minus1t:12;
        Num_Vert_Tiles_Minus1=Num_Vert_Tiles_Minus1t;
        Num_Horiz_Tiles_Minus1=Num_Horiz_Tiles_Minus1t;

        for (i=0;i<Num_Vert_Tiles_Minus1;i++)
        {
            if (Short_header_flag)
            {
                ubyte Tile_Width_In_MB;
            }
            else
            {
                ushort Tile_Width_In_MB;
            }
        }

        for (i=0;i<Num_Horiz_Tiles_Minus1;i++)
        {
            if (Short_header_flag)
            {
                ubyte Tile_Height_In_MB;
            }
            else
            {
                ushort Tile_Height_In_MB;
            }
        }

        
    }


    if (Windowing_Flag)
    {
        ubyte TOP_MARGIN:6;
        ubyte LEFT_MARGIN:6;
        ubyte BOTTOM_MARGIN:6;
        ubyte RIGHT_MARGIN:6;
    }

} IMG_HDR;

do_IMG_PL_HDR();

if (IMG_HDR.Alpha_Image_Plane_Flag)
{
    IsCurrPlaneAlphaFlag=TRUE;
    do_IMG_PL_HDR();
}

if (IMG_HDR.Index_Table_Flag)
{
    struct INDEX_TABLE_TILES
    {
        if (IMG_HDR.Freq_Mode_Codestream_Flag == 0)
        {
            valueNumIndexTableEntries=1;
        }
        else
        {
            valueNumIndexTableEntries=(1*NumBandsOfPrimary);
        }
        ushort Index_Table_Startcode;
        
        Printf("valueNumIndexTableEntries:%ld\n",valueNumIndexTableEntries);

        
        for (n = 0; n < valueNumIndexTableEntries; n++)
        {   
            IndexOffsetTile[n]=VLW_ESC();         
            Printf("Tile offset %d: %ud\n",n,IndexOffsetTile[n]);
 
        }
        
    }IDX_T_TILES;
}

Subsequent_Bytes=VLW_ESC();
Printf("Subsequent Bytes:%d\n",Subsequent_Bytes);
if (Subsequent_Bytes > 0)
{
    //  etc.. See 8.2.1
    iBytes=Profile_Level_Info();
    Printf("iBytes:%d\n",iBytes);
    valueAdditionalBytes=Subsequent_Bytes - iBytes;
    Printf("valueAdditionalBytes:%d\n",valueAdditionalBytes);
    for(iBytes=0;iBytes < valueAdditionalBytes; iBytes++)
        ubyte RESERVED_A_BYTE;
}

// 8.7.1
do_coded_tiles();
```


It breaks the header info down as far as the CODED_BLOCKS, but it's still not 100 complete/tested.
## Post #18
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-19T21:40:08+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

I finally bought the Rage Toolkit to see if it would offer any insight. And I did find it useful to create a test dataset. I made 4 textures, which are 512x512, with a simple descriptive text on each layer, saying what it is.  (Diffuse/Specular/Normal/Bump).

I then created a simple map with only this texture used, and built the map so it's own virtual texture file would be created.  During the build process, an intermediate file is created, with the *.cpuvmtr extention.  And this intermediate file seems to be the raw texture before compression. By examining it one can see what is stored in the *.pages file.  I found they actually store 11 layers, in this order:

Diffuse Red
Diffuse Green
Diffuse Blue
Specular Red
Specular Green
Specular Blue
Normal Red
Normal Green
Normal Blue
Power Map Red
Blank Layer (white)

I'm including this intermediate file, along with my source images, and the compressed megatexture output, as a test dataset. Having a known imput will make working backward easier.  As the texture contained within is my own orignal work, I hereby give full permission to copy and distribute.

[http://home.comcast.net/~volfin/Known%20Image.rar](http://home.comcast.net/~volfin/Known%20Image.rar)

You can open the cpuvmtr as a raw file, 512x512 dimensions, 11 channels interleaved, with a 212 byte header.
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-22T02:29:52+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

[out]
## Post #20
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-22T03:07:14+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from Wobble
>
> volfin wrote:I finally bought the Rage Toolkit to see if it would offer any insight.

What else can you do with the Rage Took Kit?

I read it has a MD6 Model Editor.  Can it be used to reverse the md6model format?
I still don't know how bone-vertex assignments work.

No, it only allows editing maps, creating walls and ground and doors, that type of thing. And you can place 'entities' and 'objects' which are the predefined models included in Rage. But it doesn't really have a way to introduce new models.  In fact the only way i could get it to use my custom texture was to replace the pre-existing TGAs for an existing texture with my own. There's no way to simply tell it to use custom textures either. Very, very limited.

EDIT: now that I look harder, it does have a model viewer, that does read in the md6model. There's no import and there's no type of export except for something called "Transformed LWO" which doesn't actually seem to do anything (no files produced). I don't see it being much help for understanding the format.
## Post #21
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-07-29T05:16:02+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

I extracted some virtual textures from the game with AMD CODEXL but the software not support resolutions over 8192.

this is a normal texture from Infantry46 character (4096x4096)

[http://www.mediafire.com/view/oa2a7r3pp ... level0.png](http://www.mediafire.com/view/oa2a7r3pp83vlo3/WolfNewOrder_x64-Context2-Texture50level0.png)

and this is {Diffuse?, maybe damaged} texture from the same character (4096x4096)

[http://www.mediafire.com/view/0t343kw2w ... level0.png](http://www.mediafire.com/view/0t343kw2wvzppr9/WolfNewOrder_x64-Context2-Texture48level0.png)

apply zoom in both images or download the file for see the detail.


AMD codexl is a profiling tool for Directx, opencl and opengl , maybe can help to know how the game transcode the textures with the CPU-GPU analysis and other useful options
## Post #22
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-29T07:32:44+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from luxox18
>
> I extracted some virtual textures from the game with AMD CODEXL but the software not support resolutions over 8192.

this is a normal texture from Infantry46 character (4096x4096)

http://www.mediafire.com/view/oa2a7r3pp ... level0.png

and this is {Diffuse?, maybe damaged} texture from the same character (4096x4096)

http://www.mediafire.com/view/0t343kw2w ... level0.png

apply zoom in both images or download the file for see the detail.

AMD codexl is a profiling tool for Directx, opencl and opengl , maybe can help to know how the game transcode the textures with the CPU-GPU analysis and other useful options

Very Interesting. This isn't exactly how I imagined it, but it does make sense I guess. To the engine it's not important that the tiles be in order, only that they be present in memory. Likely pulled straight from the Quadtree in the order stored.

This confirms the page block is 128x128 pixels as inferred from the presentations, that's something at least.

You can actually see how the texture Mip-Maps on the lower tiles, one 128x128 block contains a reduced-size version of several blocks for far-away items. Very cool.
## Post #23
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-08-08T09:33:54+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

I found way to extract textures. To do this, I load the game exe in memory and call the decoding function. Tiles overlapped 4px. Effective tile size is 120x120.

Textures really large, therefore I split it to 15630x15630 images.
To use this tool you need get "Reloaded" exe v1.0.0.1 (md5: e0617f6cbbe81cfdcfbedb7f6f01a557).
[](http://postimg.org/image/t732jb7sf/)
[vtex.zip](https://xentaxbackup.github.io/file/7643_vtex.zip)
## Post #24
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-08-09T03:34:27+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Impressive. I'll have to give this a go tomorrow.

I got the EXE with the matching MD5, and tried it. But for me the program fails with a BEX64 error. tragic.
## Post #25
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-08-09T18:37:58+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Yes, I see some error on clean system. Try to disable ASLR (disable_aslr.reg and reboot). You can enable it again after using vtex.
[aslr.ZIP](https://xentaxbackup.github.io/file/7650_aslr.ZIP)
## Post #26
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-08-09T22:41:40+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from m0xf
>
> Yes, I see some error on clean system. Try to disable ASLR (disable_aslr.reg and reboot). You can enable it again after using vtex.

Yes! That got it. Working great. I tip my hat to you sir.
## Post #27
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-09T22:53:57+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

sorry for the noob question but what do you mean with " I load the game exe in memory and call the decoding function" ?
can you explain how to make this?

EDIT......

Solved! thanks volfin
## Post #28
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-08-14T10:10:18+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from luxox18
>
> sorry for the noob question but what do you mean with " I load the game exe in memory and call the decoding function" ?
can you explain how to make this?

EDIT......

Solved! thanks volfin

Hi, Could you tell me How can I load the game exe in memory and call the decoding function? "
## Post #29
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-15T00:30:08+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

put the vtex.exe tool in the main directory  of the game, run the tool, load the pages file and add the output directory

example: vtex.exe C:\Blah-Blah...\virtualpages\chunk2_vmtr.pages C:\base

then use irfanview for edit and view the DDS file
## Post #30
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-08-15T16:27:27+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from luxox18
>
> put the vtex.exe tool in the main directory  of the game, run the tool, load the pages file and add the output directory

example: vtex.exe C:\Blah-Blah...\virtualpages\chunk2_vmtr.pages C:\base

then use irfanview for edit and view the DDS file

Thanks . but it' didn't worked for me .

this is my directory  of the game : 
D:\Wolfenstein - The New Order

i put vtex.exe in  the main directory (beside WolfNewOrder_x64.exe )
and then run this Command :

"vtex.exe D:\Wolfenstein - The New Order\virtualtextures\chunk1_vmtr.pages D:\Wolfenstein - The New Order\EXTRACTED "

also try this :

"vtex.exe virtualtextures\chunk1_vmtr.pages EXTRACTED "

But it's not worked

I used to this kind of command line tools before...but i don't know why it's not worked. did i something wrong?
## Post #31
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-15T20:52:41+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

remember , you need the Reloaded exe version
## Post #32
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-08-16T13:37:17+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from luxox18
>
> remember , you need the Reloaded exe version

Thanks, mate. it's worked. the error,  Because of " - "  Between " Wolfenstein - The New Order ". when i rename it to " Wolfenstein The New Order " , it's worked.

but. we can't use edited textures in the game, right?
## Post #33
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-16T21:04:05+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

yes , this tool only export textures , repack for now isn't possible

maybe with rage toolkit.........
## Post #34
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2014-09-04T15:54:03+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Is there still something in progress to repack the files!?
## Post #35
- Username: ELCID777
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 07, 2014 5:44 am
- Post datetime: 2014-10-14T22:13:59+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Bump:

Any way to repack the textures? In-game textures look like complete shit, which is why I'd like to edit and replace some of the textures with better ones.
## Post #36
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2015-01-04T16:27:58+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from ZerOHearth
>
> Is there still something in progress to repack the files!?Again.

Or reimport!?
## Post #37
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-04T18:38:40+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

You can just stop asking, Will never support reimport. Virtualtextures are a huge technical hurdle and if you read the thread you'd see we only got them out by a type of exploit. no way to reverse that the other way.
## Post #38
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2015-01-11T18:12:15+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from volfin
>
> You can just stop asking, [...]no way to reverse that the other way.I´ve read the thread, too. But i think there is a way to do, because "Evil Within" is the same engine. And you find now a way....  

So. Ok. I hope you have better news on other games in future.
## Post #39
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-11T19:36:02+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from ZerOHearth
>
> volfin wrote:You can just stop asking, [...]no way to reverse that the other way.I´ve read the thread, too. But i think there is a way to do, because "Evil Within" is the same engine. And you find now a way....  

So. Ok. I hope you have better news on other games in future.

Um, no, we never even got textures out of Evil Within, let alone reimported any. (sadly)
## Post #40
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-06-06T19:05:20+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Hello again

I want to obtain textures from Wolfenstein The Old Blood but for the moment is not possible, not even the physical textures with AMD codeXL.

my question is.
anyone here knows how to m0xf  managed to decode the textures from the game?

thanks
## Post #41
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-06-07T15:52:47+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from luxox18
>
> Hello again

I want to obtain textures from Wolfenstein The Old Blood but for the moment is not possible, not even the physical textures with AMD codeXL.

my question is.
anyone here knows how to m0xf  managed to decode the textures from the game?

thanks

As he stated, he wrote a program that loads the game's EXE and hooked into the game's code for decoding. Not a simple process by far.
## Post #42
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-25T00:36:45+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

The vtex method works nicely (thanks again for that).
_vmtr.pages doesn't give me any files at all.
the c01p1.pages (and so on) seem to be purely level architecture textures.
That leaves the chunk1-13_vmtr.pages, they contain the character, weapon and object textures, and they're the only ones i'm interested in.
However, each chunk only gives me about 1-4 (multi-)textures at most, plus their normals and speculars. Altogether about 84GB worth.
I've looked through all of them, but i'm still missing a lot of files, most of the weapons textures or frau engel for example.
I've also searched the .bimage files, but most of those seem to be fx and ambient occlusion maps.
Has anyone a little more insight into the structure of the game?
Do some files simply not get extracted, or what am i missing?

EDIT: got it working, it was in the _vmtr.pages
Apparently the previous sessions cluttered up my harddisk completely, so it couldn't extract because there simply was no room.
## Post #43
- Username: RTCWREMAKE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 09, 2015 9:54 am
- Post datetime: 2015-08-09T01:57:11+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Hello. Someone can send me B.J face texture? pleaseee!
## Post #44
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-09-22T02:17:54+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from m0xf
>
> I found way to extract textures. To do this, I load the game exe in memory and call the decoding function. Tiles overlapped 4px. Effective tile size is 120x120.

Textures really large, therefore I split it to 15630x15630 images.
To use this tool you need get "Reloaded" exe v1.0.0.1 (md5: e0617f6cbbe81cfdcfbedb7f6f01a557).

I download the right exe, and try type "vtex.exe E:\games\WolfensteinTheNewOrder\virtualtextures\c01p1.pages c:\000"
but vtex.exe stop work 



Snap2.jpg (107.55 KiB) Viewed 201 times
## Post #45
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-09-22T17:45:30+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from amzerof6
>
> m0xf wrote:I found way to extract textures. To do this, I load the game exe in memory and call the decoding function. Tiles overlapped 4px. Effective tile size is 120x120.

Textures really large, therefore I split it to 15630x15630 images.
To use this tool you need get "Reloaded" exe v1.0.0.1 (md5: e0617f6cbbe81cfdcfbedb7f6f01a557).


I download the right exe, and try type "vtex.exe E:\games\WolfensteinTheNewOrder\virtualtextures\c01p1.pages c:\000"
but vtex.exe stop work 
Snap2.jpg

If you look back through the thread, he explains how to disable ASLR, you must do this to make it work.
## Post #46
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-09-23T12:14:49+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> If you look back through the thread, he explains how to disable ASLR, you must do this to make it work.

thankU very much!  I get those textures, so large.
how could U resplit those dds? memory not enough

btw,Hi luxox18 , how could U get "the last of us"s 3d model? that's great job,I just only get textures.
## Post #47
- Username: theddd1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 14, 2015 4:04 pm
- Post datetime: 2016-02-27T06:29:25+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

I'm sorry for the super necro, just jumped in late on this bandwagon. I'm not sure if I can get help after all of this time, but I still gotta try. I've managed to extract all the models from the game now I just need the textures for them, but I'm having a lot of difficulty with this.

Whenever I run the line in cmd, vtex.exe just stops working and crashes when trying to extract the textures. Now I have already disabled ASLR/rebooted yet the problem continues to persist. I'm really stuck on why it could still be crashing like this.
## Post #48
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2016-05-27T11:43:15+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

I have the same problem as my upstairs neighbor :/

Is it compatible for Windows 10? (vtex)
## Post #49
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-06-08T16:35:57+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

How to deal with _vmtr_q3.mega2 ?

And I have Win10
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-10T15:09:08+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Megatextures are solved. Research progress and tool will be posted here [viewtopic.php?f=18&t=16112](http://forum.xentax.com/viewtopic.php?f=18&t=16112)
## Post #51
- Username: spartan1096
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 17, 2017 12:20 pm
- Post datetime: 2017-06-25T07:27:52+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Please help, I want to extract textures from Wolfenstein the Old Blood, I disable aslr, got the reloaded exe of TNO with the matching MD5, but when I tried to run the vtex, it do nothing, like this



捕获2.JPG (32.89 KiB) Viewed 255 times
## Post #52
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-01-18T12:57:40+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Hi all! Sorry for necro, but I need help with vtex program.

I disabled the ASLR, like was said in thread, but I'm afraid, that I misunderstand the part with "reloaded exe". I downloaded the "reloaded exe", replaced the original one in the game directory, put there vtex and tried to type in cmd the following:

D:\Spiele\WolfensteinTheNewOrder\vtex.exe D:\Spiele\WolfensteinTheNewOrder\virtualtextures\chunk1_vmtr.pages D:\Spiele\WolfensteinTheNewOrder\

I got the "extracting..." message and... nothing. What I have done wrong?
[14.png](https://xentaxbackup.github.io/file/15507_14.png)
## Post #53
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-01-18T17:06:33+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from Koralan
>
> Hi all! Sorry for necro, but I need help with vtex program.

I disabled the ASLR, like was said in thread, but I'm afraid, that I misunderstand the part with "reloaded exe". I downloaded the "reloaded exe", replaced the original one in the game directory, put there vtex and tried to type in cmd the following:

D:\Spiele\WolfensteinTheNewOrder\vtex.exe D:\Spiele\WolfensteinTheNewOrder\virtualtextures\chunk1_vmtr.pages D:\Spiele\WolfensteinTheNewOrder\

I got the "extracting..." message and... nothing. What I have done wrong?

"Reloaded" is a pirating group. he got a pirated version of the game exe, without the copy protection. it won't work unless copy protection is removed.
## Post #54
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-01-19T13:20:09+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from volfin
>
> Koralan wrote:Hi all! Sorry for necro, but I need help with vtex program.

I disabled the ASLR, like was said in thread, but I'm afraid, that I misunderstand the part with "reloaded exe". I downloaded the "reloaded exe", replaced the original one in the game directory, put there vtex and tried to type in cmd the following:

D:\Spiele\WolfensteinTheNewOrder\vtex.exe D:\Spiele\WolfensteinTheNewOrder\virtualtextures\chunk1_vmtr.pages D:\Spiele\WolfensteinTheNewOrder\

I got the "extracting..." message and... nothing. What I have done wrong?

"Reloaded" is a pirating group. he got a pirated version of the game exe, without the copy protection. it won't work unless copy protection is removed.

Thank you!

Where it can be downloaded? I tried to search Internet, but have no luck. Or it is forbidden to give such links on the forum?
## Post #55
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-01-19T16:16:39+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from Koralan
>
> volfin wrote:Koralan wrote:Hi all! Sorry for necro, but I need help with vtex program.

I disabled the ASLR, like was said in thread, but I'm afraid, that I misunderstand the part with "reloaded exe". I downloaded the "reloaded exe", replaced the original one in the game directory, put there vtex and tried to type in cmd the following:

D:\Spiele\WolfensteinTheNewOrder\vtex.exe D:\Spiele\WolfensteinTheNewOrder\virtualtextures\chunk1_vmtr.pages D:\Spiele\WolfensteinTheNewOrder\

I got the "extracting..." message and... nothing. What I have done wrong?

"Reloaded" is a pirating group. he got a pirated version of the game exe, without the copy protection. it won't work unless copy protection is removed.

Thank you!

Where it can be downloaded? I tried to search Internet, but have no luck. Or it is forbidden to give such links on the forum?

Yes it's forbidden, but even if it wasn't, I have no idea where to find it anymore. the game is old and things tend to disappear once their popularity is over.
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-19T17:38:17+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from volfin
>
> I have no idea where to find it anymore. the game is old and things tend to disappear once their popularity is over.
i must disagree with that
there are still a lot of places where you can get reloaded version
i think it will be safe to say that there are lots of pirate bays who still share it
including of course the most famous pirate bay
## Post #57
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-01-20T14:31:20+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Thanks volfin and daemon1! I found the reloaded version and installed it, put in its directory vtex.exe, disabled aslr and wrote into cmd next command:
D:\WolfensteinTheNewOrder\vtex.exe D:\WolfensteinTheNewOrder\virtualtextures\c01p1.pages D:\WolfensteinTheNewOrder\
But nothing happened again! 
I don't know, what I could done wrong this time, all seems just like said in thread...
[111.png](https://xentaxbackup.github.io/file/15535_111.png)
## Post #58
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-01-22T12:43:32+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Can anybody help me?
## Post #59
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2019-04-11T02:01:03+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

hey guys sorry for the very late necro but when i run the vtex tool i disabled aslr btw
nothing happens the command line appears and instantly closes
what do i do
## Post #60
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2019-04-22T04:01:05+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

it shows this and closes immediately this is windows 8 btw
[Screenshot_1.png](https://xentaxbackup.github.io/file/16080_Screenshot_1.png)
## Post #61
- Username: CloudyMosy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 02, 2020 2:03 am
- Post datetime: 2020-09-02T09:44:37+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from m0xf ↑Fri Aug 08, 2014 5:33 pm at Fri Aug 08, 2014 5:33 pm
>
> 
I found way to extract textures. To do this, I load the game exe in memory and call the decoding function. Tiles overlapped 4px. Effective tile size is 120x120.

Textures really large, therefore I split it to 15630x15630 images.
To use this tool you need get "Reloaded" exe v1.0.0.1 (md5: e0617f6cbbe81cfdcfbedb7f6f01a557).

Sorry for super-duper-necro, but your lovely program closes after I launch it (tried launching it as an administrator too.), and yes I launched disable.aslr then I launched the vtex.exe, moved the Crack to the Wolfenstein The New Order direction before doing the first step, but I'm still ecountering the problem that it starts writing the "Virtual texture extractor..." and then it immediately closes, and I'm a bit confused with the "reboot" part too. By the way, Here is my file status.
[Snímka obrazovky (1346).png](https://xentaxbackup.github.io/file/18734_Snímka obrazovky (1346).png)
## Post #62
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2022-01-09T21:22:52+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

> Reply from CloudyMosy ↑Wed Sep 02, 2020 5:44 pm at Wed Sep 02, 2020 5:44 pm
>
> 
m0xf wrote: ↑Fri Aug 08, 2014 5:33 pm
I found way to extract textures. To do this, I load the game exe in memory and call the decoding function. Tiles overlapped 4px. Effective tile size is 120x120.

Textures really large, therefore I split it to 15630x15630 images.
To use this tool you need get "Reloaded" exe v1.0.0.1 (md5: e0617f6cbbe81cfdcfbedb7f6f01a557).



Sorry for super-duper-necro, but your lovely program closes after I launch it (tried launching it as an administrator too.), and yes I launched disable.aslr then I launched the vtex.exe, moved the Crack to the Wolfenstein The New Order direction before doing the first step, but I'm still ecountering the problem that it starts writing the "Virtual texture extractor..." and then it immediately closes, and I'm a bit confused with the "reboot" part too. By the way, Here is my file status.

I think you need to use Windows 7
## Post #63
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2022-01-19T23:50:54+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

Welp, nothing is happening here
## Post #64
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2023-02-05T04:34:30+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

I have a Main .exe load error.
## Post #65
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2023-04-26T18:17:35+00:00
- Post Title: Re: Wolfenstein .Pages files (idtech5 virtualtextures)

So, I wanted to bring this back since nobody brought this up before.

For both Wolfenstein games, with CheatEngine anyone can access and use the console commands + restricted cvars. (link: [https://fearlessrevolution.com/viewtopic.php?t=9936](https://fearlessrevolution.com/viewtopic.php?t=9936))

This means ALL debug and developer tools are available.
I started playing with TNO and you can export all the things, including the virtual textures to tga format, using 'writeImage'.
Problem though is that similar to dumping from memory, all the megatexture tiles are scrambled.

There are hundreds of commands you can use (use 'find', 'listCvars', 'listCmds' and here [https://steamcommunity.com/sharedfiles/ ... 2182215806](https://steamcommunity.com/sharedfiles/filedetails/?id=2182215806)) and I haven't found a way to sort the tiles yet but perhaps there is one?

This could make extraction easier, since you just have to load what you want textures to, set the quality to max with no compression and dump the images. Anyone tried this out yet?

If I figure it out, I'll write down here.


example of what I got from exporting with tiles debug ON: [https://drive.google.com/file/d/1JL2cLL ... share_link](https://drive.google.com/file/d/1JL2cLLbEMmOP45NqscTsnKgEvqQpJbPP/view?usp=share_link)
