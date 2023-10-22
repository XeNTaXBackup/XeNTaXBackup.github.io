## Post #1
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2013-12-26T21:24:10+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Castlevania: Lords of Shadow – Mirror of Fate HD bctex textures

Thanks to Ekey, .pkg files can be extracted which contain textures with .bctex extension:

[viewtopic.php?f=10&t=11080](http://forum.xentax.com/viewtopic.php?f=10&t=11080)

I am interested in bctex conversion to .dds or .tga, or whatever.

Per forum rules, please PM me for additional data.
## Post #2
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2014-03-27T20:46:48+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

bitmap starts at 0x24, its two 8bit interleaved channels. first channel always 0xFF, second is what you need. bfont format is almost the same as mst in big Castlevanias. at 0x28 you have offset to chars table data and there x, y, w, h all shorts. one difference - chars 0x00-0x1f are skipped so there are definitions for 0x20-xff only.
[textures.rar](https://xentaxbackup.github.io/file/7140_textures.rar)
## Post #3
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-04-02T03:37:26+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Template for PC version.

```
{
    TEXFMT_ARGB = 0x10001,
    TEXFMT_ARGB_1 = 0x20001,
    TEXFMT_A8 = 0x30001,
    TEXFMT_A8_1 = 0x40001,
    TEXFMT_R8G8_B8G8 = 0x50001,
    TEXFMT_DXT1 = 0x10003,
    TEXFMT_DXT5 = 0x20003,

    TEXFMT_U8V8 = 0xC0001,
    TEXFMT_DXT1_1 = 0xC0003,
};

struct Header
{
    BYTE Signature[4];
    DWORD Version <format=hex>; // or content ID. 0x30001 for all textures.
    TEXFORMAT Flags<format=hex>;
    DWORD Width;
    DWORD Height;
    DWORD MipLevels;
    DWORD NameOffset <format=hex>;
    DWORD DataOffset <format=hex>;
};

Header header;
DWORD MipLevelSizes[header.MipLevels];

local int i = 0;
FSeek(header.DataOffset);
for(i = 0; i < header.MipLevels; i++)
{
    struct { BYTE Data[MipLevelSizes[i]]; } level;
}
FSeek(header.NameOffset);
string name;

```


In fact, the Flags field is not an enumeration. It is a set of the flags. For example the flag 0x1 means the surface, 0x3 means the compressed format. Second word of enumeration is "usage", It also describes the format of texture.

But to extract textures you can ignore these details and use an enum TEXFORMAT.
## Post #4
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-04-11T09:32:22+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

> Reply from cienislaw
>
> bitmap starts at 0x24, its two 8bit interleaved channels. first channel always 0xFF, second is what you need. bfont format is almost the same as mst in big Castlevanias. at 0x28 you have offset to chars table data and there x, y, w, h all shorts. one difference - chars 0x00-0x1f are skipped so there are definitions for 0x20-xff only.

How to convert .bctex to png and repack it? Thanks!
## Post #5
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2014-04-17T08:32:22+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

[http://rghost.ru/54291693](http://rghost.ru/54291693)

This command line tool converts bctex texture to dds texture. Target surface remains in the same format as the original. Use bctex2dds <bctex_filename>.
## Post #6
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-04-18T01:12:33+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

> Reply from destrator
>
> http://rghost.ru/54291693

This command line tool converts bctex texture to dds texture. Target surface remains in the same format as the original. Use bctex2dds <bctex_filename>.

Work perfect!   
How to converts dds texture to bctex texture? Thanks for your help! ^^
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-10-19T18:00:22+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Hi guys, I just got my copy of the HD game of LOS

I extracted the files with the bms script:

```
get TABLESIZE long
get DATASIZE long
get FILES long

for i = 0 < FILES
  getdstring NAME 1024
  get OFFSET long
  get SIZE long
  math SIZE -= OFFSET
  log NAME OFFSET SIZE
next 


```


Works perfect!

Now the bctex2dds is nolonger available 

So i had to come up with something else, C# code  of course

```
        {
            TEXFMT_ARGB = 0x10001,
            TEXFMT_ARGB_1 = 0x20001,
            TEXFMT_A8 = 0x30001,
            TEXFMT_A8_1 = 0x40001,
            TEXFMT_R8G8_B8G8 = 0x50001,
            TEXFMT_DXT1 = 0x10003,
            TEXFMT_DXT5 = 0x20003,

            TEXFMT_U8V8 = 0xC0001,
            TEXFMT_DXT1_1 = 0xC0003,
        };

        public struct Header
        {
           public byte[] Signature; // 4 bytes
           public uint Version; // <format=hex>; // or content ID. 0x30001 for all textures.
           public TEXFORMAT Flags;// <format=hex>;
           public uint Width;
           public uint Height;
           public uint MipLevels;
           public uint NameOffset; // <format=hex>;
           public uint DataOffset; // <format=hex>;
           public uint[] MipLevelSizes;
        };

        public static void Convert2DDS(string fileName)
        {
            using (var br = new BinaryReader(File.Open(fileName, FileMode.Open)))
            {
                Header header = new Header()
                {
                    Signature = br.ReadBytes(4), // MTXT
                    Version = br.ReadUInt32(),
                    Flags = (TEXFORMAT)br.ReadUInt32(),
                    Width = br.ReadUInt32(),
                    Height = br.ReadUInt32(),
                    MipLevels = br.ReadUInt32(),
                    NameOffset = br.ReadUInt32(),
                    DataOffset = br.ReadUInt32()
                };

                header.MipLevelSizes = new uint[(int)header.MipLevels];

                for (int i = 0; i < header.MipLevels; i++)
                {
                    header.MipLevelSizes[i] = br.ReadUInt32();
                }


                br.Close();
            }
        
        
        }

```


but how do I write it out as a dds file ??

T.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-10-20T19:32:17+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Found it 

The header is 128 bytes, always, then write the exact data from the bctex file to the dds file and it works, well almost for every case.

for the formats DXT5 & DXT1, it works just fine, cause that is noted in the header:



but what is it I need to write when dealing with another format like
ARGB
ARGB_1
A8
A8_1
R8G8_B8G8
U8V8
DXT1_1

Anyone can help me out here?

T.
[hexed.png](https://xentaxbackup.github.io/file/7974_hexed.png)
## Post #9
- Username: claudiuboy83
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 02, 2014 3:38 pm
- Post datetime: 2014-11-02T10:59:14+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Still have someone the bctex2dds...?
## Post #10
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-02T12:47:56+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Yep  
[bctex2dds.zip](https://xentaxbackup.github.io/file/8021_bctex2dds.zip)
## Post #11
- Username: claudiuboy83
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 02, 2014 3:38 pm
- Post datetime: 2014-11-02T16:28:29+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

thank you but when i try to open is blinck it and disapear...is about win OS?
## Post #12
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-02T20:15:24+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

It's ok. It is a command-line tool.
## Post #13
- Username: claudiuboy83
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 02, 2014 3:38 pm
- Post datetime: 2014-11-03T07:16:43+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

Sorry but i get this info"has unknow surface format : 0x.01000400"
Can you explain me exacly how to do this?...to convert this type of files.Thank you!
Or someone have all that bctex files converted to dds?
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-03T08:20:45+00:00
- Post Title: Castlevania: LOS – Mirror of Fate HD .bctex textures

I have never used this tool, but I assume that your texture is not supported.
