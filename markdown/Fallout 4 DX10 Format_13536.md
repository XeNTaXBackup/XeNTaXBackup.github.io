## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-14T09:41:19+00:00
- Post Title: Fallout 4 DX10 Format

Hi all,

It should be DX10 UNIFORM, not sure it is stupid format 

Can anyone please help me correct header for this files ?
[Crane.rar](https://xentaxbackup.github.io/file/10007_Crane.rar)
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-14T10:16:54+00:00
- Post Title: Fallout 4 DX10 Format

i guess i found it
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-11-15T20:55:26+00:00
- Post Title: Fallout 4 DX10 Format

Maybe is late but,I replace the DX10 header for ATI2 header and works fine.





here are the files.

[http://www.mediafire.com/download/8hpn5 ... /crane.rar](http://www.mediafire.com/download/8hpn5o2nzr13h4a/crane.rar)

use noesis or other tool with ati2 support.
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-17T09:32:27+00:00
- Post Title: Fallout 4 DX10 Format

Good job following up with the specifics instead of just telling people you figured it out, luxox18. 

FYI, Noesis ATI2 is BC5 (the name is from before the Block Compression designations existed), and BC4 is also available as ATI1. I'll be including my own software decoders for BC6H and BC7 in some future release.
## Post #5
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-01-02T23:57:20+00:00
- Post Title: Fallout 4 DX10 Format

Guys help me please with understanding this DDS header format. Here is my finding.
Please correct me if I am wrong. Thanks in advance!

The "?" is for me still unknow.

```
uint filetype
uint dxcomptype <hell knows how to decode>
ubyte zero
ubyte ?
ubyte depth?
ubyte zero
ushort width  <can be swapped>
ushort height <can be swapped>
ubyte mipscount
ubyte ?
ubyte ?
ubyte ?
uint startoffset
uint zero
uint compsize
uint pixscount
uint zero
uint ?
uint startoffset_mips
uint zero
uint compsize_mips
uint pixscount_mips
uint ?
uint ?

```

See attachment. Include sample of archive dds header + compressed/uncompressed blocks of main layer and mips.

EDiT: My goal is reduce textures. But there is 2 way hot do it.

First is delete blocks with main layer a edit headers.

Second is fake the texture streamer to load lower textures without removing blocks with main layer. <--- Tested I just edit the width height a mip count and game run fine. But didn't see any changes. Maybe I must edit too mips blocks position instead of main layers.

So which way may be better guys?
[sample.rar](https://xentaxbackup.github.io/file/10260_sample.rar)
## Post #6
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2016-04-20T22:53:09+00:00
- Post Title: Fallout 4 DX10 Format

there is a number of references on the subject but issue in my case i was scratching head for hours, meanwhile dm thing was compressed whole time lol.  i eventually gave up trying and i might have borked this up, trying to account for what data  i found,but hopefuilly easily fixedand maybe prove useful :-  (just header& partial mips i kinda lost the plot halfway through)

check for a Github project named DDS-READER or something like this, it gives some useful info on some of the more common dds formats, 

if u ever finish this please send me a copy or post here 

cheers and good luck mate

//--------------------------------------
//--- 010 Editor v6.0.1 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------

//HEADER
typedef struct {   // bmfh
    CHAR    fType[4];
    uint32  size;//124
    ubyte   flags[4];
    uint32  height;
    uint32  width;
    uint32  sizeorpitch;
    uint32  depth;
    uint32  mipmapcount;
    uint32  alphabitdepth;
    uint32  reserved[10];
} DDSHEADER;

//PIXELFORMAT
typedef struct {   // 
    uint32  size;//??
    ubyte   flags[4];
    uint32  fourcc;
    uint32  rgbbitcount;
    uint32  rbitmask;
    uint32  gbitmask;
    uint32  bbitmask;
    uint32  alphabitmask;
} PIXELFORMAT;

//caps
typedef struct {   // 
    uint32  caps1;//??
    uint32  caps2;
    uint32  caps3;
    uint32  caps4;
    uint32  texturestage;
} CAPS;
struct DDSorig
    {
        DDSHEADER header;
        PIXELFORMAT pixelformat;
        CAPS ddscaps;
    };
//cal uint32 tag22;
LittleEndian();

DDSorig ddsfile;
## Post #7
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-04T03:49:44+00:00
- Post Title: Fallout 4 DX10 Format

detailed info about BCx formats is here:
[http://www.reedbeta.com/blog/2012/02/12 ... n-formats/](http://www.reedbeta.com/blog/2012/02/12/understanding-bcn-texture-compression-formats/)

Simplest is to get Intel's DDS Photoshop plugin, handles BCx formats natively:

[https://software.intel.com/en-us/articl ... rks-plugin](https://software.intel.com/en-us/articles/intel-texture-works-plugin)
