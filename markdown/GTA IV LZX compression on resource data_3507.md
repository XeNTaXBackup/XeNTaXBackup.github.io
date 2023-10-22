## Post #1
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2009-05-25T07:45:40+00:00
- Post Title: GTA IV LZX compression on resource data

I want to ask help for solving Xbox360 resource compression problem, it is very important to me... 

Every GTAIV resource (xtd-textures for example) has got following stucture:
4 bytes - Magic ('RSC')
4 bytes - Type (version - textures has "7")
4 bytes - Flags
<<Data in ZLIB on PC and LZX on XBox360>>
From 'flags' value can be calculated sizes of SysSegment and GpuSegment of unpacked data.
Delphi:

```
 GpuSegSiz := ((flags shr 15) and $7FF) shl (((flags shr 26) and $F) + 8);

```

C#:

```
uint gpuSegSize = ((flags >> 15) & 0x7FF) << (((flags >> 26) & 0xF) + 8);

```

Of course on PC everything is very easy because of primitive compression, but I dont know how to work with X360 data. Here it is archive which includes three examples of texture RSC.
[http://www.sendspace.com/file/u4dk34](http://www.sendspace.com/file/u4dk34)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-25T10:33:00+00:00
- Post Title: GTA IV LZX compression on resource data

So why don't you just write an extractor if you already know that it is LZX?
Already seen some C code for decompression.
## Post #3
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2009-05-25T11:25:13+00:00
- Post Title: GTA IV LZX compression on resource data

Unfortunally I am not so strong in C++/C#, it is the reason of my ask. 
Anyway, I will be happy to look at decompress code (can not found it)
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-25T11:28:42+00:00
- Post Title: GTA IV LZX compression on resource data

[http://www.gtaforums.com/index.php?showtopic=410041](http://www.gtaforums.com/index.php?showtopic=410041)
At the bottom. You already posted in that thread it seems.
## Post #5
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2009-05-25T11:41:06+00:00
- Post Title: GTA IV LZX compression on resource data

This is not decompress code, this is code for segment sizes calculation. Tool "unlzx" is not useful.
But I found some info about decompression in SparkIV source:
[http://www.google.com/codesearch/p?hl=r ... ZXCodec.cs](http://www.google.com/codesearch/p?hl=ru#fFVohHNu2aU/trunk/RageLib/Common/Compression/CompressionLZXCodec.cs)
Major part removed - it "is ommitted due to licensing issues".
Nobody of gtaF knows how to work with LZX, and who know will not tell because of some "staff agreement"
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-25T11:46:03+00:00
- Post Title: GTA IV LZX compression on resource data

Yeah exactly that unlzx code.
You just need to adapt some things (OS and platform-specific stuff).
## Post #7
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2009-05-25T12:15:46+00:00
- Post Title: GTA IV LZX compression on resource data

No future...   If you could help me with decompressor writing it will be more than good, for all people who interested in X360 GTAIV.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-25T12:34:19+00:00
- Post Title: GTA IV LZX compression on resource data

I'm too busy. Going through all that code takes some time.
## Post #9
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2009-05-25T12:36:19+00:00
- Post Title: GTA IV LZX compression on resource data

Maybe a bit later? (Week/Mounth and etc?...) Want to hope because it is very important
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-25T12:47:02+00:00
- Post Title: GTA IV LZX compression on resource data

Years is more likely
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-25T14:19:05+00:00
- Post Title: GTA IV LZX compression on resource data

are you really sure that it's a LZX block?
I have tried to use the m$ lzx decompression which comes in [libmspack](http://www.cabextract.org.uk/libmspack/) but it doesn't work.

*edit*: with "doesn't work" I mean that the input data is not accepted as valid by the lzx_decompressor function ("bad block type") and even scanning the first bytes there are ever errors reported
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-29T16:53:54+00:00
- Post Title: GTA IV LZX compression on resource data

Maybe it's a variation of LZX.
## Post #13
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-05-29T17:19:59+00:00
- Post Title: GTA IV LZX compression on resource data

Are you kidding people?!! There are a lot of tools at the moment about editing the game such is GTA4! Where are you searching it? Through the Internet or into the Jungles? 

[Edited, sorry for bad English]
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-30T15:29:32+00:00
- Post Title: GTA IV LZX compression on resource data

Learn english before speaking.
This is about the xbox version of gta.
## Post #15
- Username: AnthonyFiveSixTwo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 24, 2008 11:52 am
- Post datetime: 2009-06-22T06:58:19+00:00
- Post Title: GTA IV LZX compression on resource data

Well today I got around to looking at the xtd files that were posted and I was able to decompress them. I will make a tool to do it later on once we get a bit more info on the actual format of the decompressed data.

Im kinda tired right now but maybe tomorrow ill post some more info.
## Post #16
- Username: AnthonyFiveSixTwo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 24, 2008 11:52 am
- Post datetime: 2009-06-22T21:59:16+00:00
- Post Title: Re: GTA IV LZX compression on resource data

Post removed due to legal reasons
## Post #17
- Username: IIVEnnEII
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 03, 2009 7:27 pm
- Post datetime: 2009-06-23T09:00:06+00:00
- Post Title: Re: GTA IV LZX compression on resource data

Well, but whats about the LZX thing ?
Are they using a custom Compression layout ?

About the Textures:
I guess they use the normal 360 Swizzling like in Halo 3 or Dead or Alive Xtreme 2.

Did you allready check the XEX for something like a security check or something ?
## Post #18
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2009-06-24T11:48:52+00:00
- Post Title: Re: GTA IV LZX compression on resource data

All progress is very nice, espesially if uncompression process is now known. Special thanks to AnthonyFiveSixTwo)
Yeah, the DLL is from x360 Development SDK, but anyway it is great because of LZX was large roadblock. 

The rest of unpacked .xtd is now known, it is not totally differs from PC .wtd. Main difference is swizzling method - as far as I know, it is usual for x360 (some guys are already researched .xtd format - gtaforums.com staff and PC GTA IV tool developers, but keept everything in secret because of "legality" of their actions).

It means that structure of .xtd header and texturetable is not as imporntant, as  texture data. IIVEnnEII (or somerbody else), can you post some code to deal with x360 swizzling?
## Post #19
- Username: IIVEnnEII
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 03, 2009 7:27 pm
- Post datetime: 2009-06-24T17:28:54+00:00
- Post Title: Re: GTA IV LZX compression on resource data

I allready talked to Anthony about that.
Well, I think they are using the "normal" swizzling method.

I got some code, maybe you have to adjust the code a bit:

```
            {
                MemoryStream ms = new MemoryStream();
                core.IO.EndianIO.EndianWriter ew = new core.IO.EndianIO.EndianWriter(ms, core.IO.EndianType.LittleEndian);
                ew.BaseStream.Position = 0;

                int realsize = width * height * 4;
                int lines = realsize / 16;

                int templine = 0;
                int rowcount = 0;
                int offsetby = 0;
                int i = 0;
                int sections = width / 32;
                for (int x = 0; x < lines; x++)
                {


                    if (rowcount % 32 == 0 && rowcount != 0)
                    {

                        templine = (i+1)*((width * 32) /4);

                        i++;

                    }



                    if (rowcount % 8 == 0 && rowcount != 0)
                    {
                        if (offsetby == 0)
                        {
                            offsetby = 8 * 16;
                        }
                        else
                        {
                            offsetby = 0;
                        }
                    }


                    if (rowcount == height) break;

                    ///get row 1 - 224 pixels(one row) = 7 * 32   
                    for (int y = 0; y < sections; y++)
                    {

                        //get 32 pixels
                        for (int z = 0; z < 8; z++)
                        {
                            if (z < 4)
                            {
                                int offset = (templine * 16) + ((y * 256) * 16) + ((z * 2) * 16) + offsetby;
                                int oi1 = BitConverter.ToInt32(raw, offset + 0);
                                int oi2 = BitConverter.ToInt32(raw, offset + 4);
                                int oi3 = BitConverter.ToInt32(raw, offset + 8);
                                int oi4 = BitConverter.ToInt32(raw, offset + 12);

                                ew.Write(oi1);
                                ew.Write(oi2);
                                ew.Write(oi3);
                                ew.Write(oi4);
                            }
                            else
                            {
                                int offset = (templine * 16) + ((y * 256) * 16) + ((z * 2) * 16) - offsetby;
                                int oi1 = BitConverter.ToInt32(raw, offset + 0);
                                int oi2 = BitConverter.ToInt32(raw, offset + 4);
                                int oi3 = BitConverter.ToInt32(raw, offset + 8);
                                int oi4 = BitConverter.ToInt32(raw, offset + 12);

                                ew.Write(oi1);
                                ew.Write(oi2);
                                ew.Write(oi3);
                                ew.Write(oi4);
                            }
                        }

                    }
                    rowcount++;

                    if (rowcount == height) break;
                    ///get row 2
                    for (int y = 0; y < sections; y++)
                    {

                        //get 32 pixels
                        for (int z = 0; z < 8; z++)
                        {
                            if (offsetby != 0)
                            {
                            }
                            if (z < 4)
                            {
                                int offset = (templine * 16) + 16 + ((y * 256) * 16) + ((z * 2) * 16) + offsetby;
                                int oi1 = BitConverter.ToInt32(raw, offset + 0);
                                int oi2 = BitConverter.ToInt32(raw, offset + 4);
                                int oi3 = BitConverter.ToInt32(raw, offset + 8);
                                int oi4 = BitConverter.ToInt32(raw, offset + 12);
                                ew.Write(oi1);
                                ew.Write(oi2);
                                ew.Write(oi3);
                                ew.Write(oi4);
                            }
                            else
                            {
                                int offset = (templine * 16) + 16 + ((y * 256) * 16) + ((z * 2) * 16) - offsetby;
                                int oi1 = BitConverter.ToInt32(raw, offset + 0);
                                int oi2 = BitConverter.ToInt32(raw, offset + 4);
                                int oi3 = BitConverter.ToInt32(raw, offset + 8);
                                int oi4 = BitConverter.ToInt32(raw, offset + 12);
                                ew.Write(oi1);
                                ew.Write(oi2);
                                ew.Write(oi3);
                                ew.Write(oi4);
                            }
                        }

                    }
                    rowcount++;
                    templine += 16;
                }
                return ms.ToArray();
            }

```


> Reply from pokecancer
>
> I figured I would release my deswizzle method for A8R8G8B8 so people can do more research on bitmaps. This applies to not only H3 but most game's resources for Xbox 360 and could probably be easily adjusted to deal with different argb formats by changing some of the math in my code. BTW this is using my own modified BinaryReader class so you will have to change that if you want to use this code. also keep in mind the data is in big endian format and need to 32 bit swapped in order to be in a format the pc can understand.
All credit goes to pokecancer

Well, you need a EndianWriter.
I got a library for all that Xbox 360 stuff, but its not created by me.
Maybe Anthony can provide a DLL for "Free to use" purposes
## Post #20
- Username: bigBear
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Oct 09, 2009 2:51 am
- Post datetime: 2009-10-10T15:04:45+00:00
- Post Title: Re: GTA IV LZX compression on resource data

So the xbox360 gets the files with x at begin.
Like .xft, xwd and such.
How are these textures inside?
Are they .dds or .xds?
I still havent found a way how to view or convert .xds textures.
## Post #21
- Username: marcello
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 05, 2009 7:19 am
- Post datetime: 2009-11-13T22:39:43+00:00
- Post Title: Re: GTA IV LZX compression on resource data

> Reply from bigBear
>
> So the xbox360 gets the files with x at begin.
Like .xft, xwd and such.
How are these textures inside?
Are they .dds or .xds?
I still havent found a way how to view or convert .xds textures.

Files into .xtd are the same what you can find in .wtd PC version of GTA4.

Simply: 
.xtd -> .dds
.wtd -> .dds

Look this:




Sorry for big image.




Anyone find method to extract this  .xtd   files ?
## Post #22
- Username: DvT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 15, 2009 9:09 pm
- Post datetime: 2009-11-15T22:12:00+00:00
- Post Title: Re: GTA IV LZX compression on resource data

What has AnthonyFiveSixTwo said, that it has been removed?  
Anyway I got the TBoGT and TLAD files, and can give you guys every file you want.

Maybe you can compare the freeway.xft and freeway.wft (from original IV) with a HEX editor?
Or luis.xdd and luis.wdd (from original IV)? Same story for texture files...
## Post #23
- Username: marcello
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 05, 2009 7:19 am
- Post datetime: 2009-11-16T15:41:28+00:00
- Post Title: Re: GTA IV LZX compression on resource data

No.. modders from france use this "compare" method and they find nothing usefull.
## Post #24
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-03-14T19:51:23+00:00
- Post Title: Re: GTA IV LZX compression on resource data

Hello, I know that this post is ancient, if I break some norm, erase it.
Have some time looking for the library or "something" to be able to open these files but I have not been lucky.
Those who have obtained it, looking for help for the forums, (in these forums also) now do not give information.
> Reply from Dageron
>
> No future...   If you could help me with decompressor writing it will be more than good, for all people who interested in X360 GTAIV.
I have interest to open GTA's textures the IVth in XBOX 360 for exclusively private use.
Probably someone could give me information or to help myself.
Post dates back: I have sent some private messages but it do not belong(do not perform,am not) if I have done it well. I it sit Post it dates 2: EFLC, will work out very prompt for PC and PS3 so I do not believe that there is no problem in which someone helps me.
Thank you
Hallo weiß ich, dass dieser Posten(Post) alt ist, wenn ich eine Norm breche(durchbreche), es ausradiere.
Haben Sie eine Zeit, die nach der Bibliothek oder "etwas" sucht, um imstande zu sein, diese Dateien zu öffnen, aber ich habe Glück nicht gehabt.
Diejenigen, die es erlangt haben, nach Hilfe für die Foren, (in diesen Foren auch) jetzt suchend, geben Information nicht.
Ich habe Interesse, Gewebe von GTA der IVTH IN XBOX 360 für ausschließlich privaten Gebrauch zu öffnen.
Wahrscheinlich konnte jemand mir Information geben oder mir zu helfen.
Posten(Post) reicht zurück: Ich habe einige private Nachrichten gesandt, aber es gehört nicht (führen Sie nicht aus, sind nicht) wenn ich es gut getan habe. Ich es sitzt Posten(Post), es datiere 2: EFLC, wird sehr pünktlich für PC und PS3 ausarbeiten, so dass ich nicht glaube, dass es kein Problem gibt, in dem jemand mir hilft.
Dank Sie
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-15T15:33:19+00:00
- Post Title: Re: GTA IV LZX compression on resource data

So nobody here will help you? Is that what you are saying? Is the information here not enough?
## Post #26
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-03-26T13:36:55+00:00
- Post Title: Re: GTA IV LZX compression on resource data

Sorry old post,...
Well, searching carefully in my things, I have found some (enough) codes that are almost exact to others exposed in the previous page.
Might they use me as something? That is to say, on this topic I deal little (nothing) but I am trying(mean) it to forced marches.

```

namespace RageLib.Common.Resources
{
    internal class ResourceHeader
    {
        private const uint MagicBigEndian = 0x52534305;
        public const uint MagicValue = 0x05435352;

        public uint Magic { get; set; }
        public ResourceType Type { get; set; }
        public uint Flags { get; set; }
        public CompressionType CompressCodec { get; set; }

        public int GetSystemMemSize()
        {
            return (int)(Flags & 0x7FF) << (int)(((Flags >> 11) & 0xF) + 8);
        }

        public int GetGraphicsMemSize()
        {
            return (int)((Flags >> 15) & 0x7FF) << (int)(((Flags >> 26) & 0xF) + 8);
        }

        public void SetMemSizes(int systemMemSize, int graphicsMemSize)
        {
            // gfx = a << (b + 8)
            // minimum representable is block of 0x100 bytes

            const int maxA = 0x3F;

            int sysA = systemMemSize >> 8;
            int sysB = 0;

            while(sysA > maxA)
            {
                if ((sysA & 1) != 0)
                {
                    sysA += 2;
                }
                sysA >>= 1;
                sysB++;
            }

            int gfxA = graphicsMemSize >> 8;
            int gfxB = 0;

            while (gfxA > maxA)
            {
                if ((gfxA & 1) != 0)
                {
                    gfxA += 2;
                }
                gfxA >>= 1;
                gfxB++;
            }
            
            Flags = (Flags & 0xC0000000) | (uint)(sysA | (sysB << 11) | (gfxA << 15) | (gfxB << 26));
        }

        public void Read(BinaryReader br)
        {
            Magic = br.ReadUInt32();
            Type = (ResourceType) br.ReadUInt32();
            Flags = br.ReadUInt32();
            CompressCodec = (CompressionType)br.ReadUInt16();

            if (Magic == MagicBigEndian)
            {
                Magic = DataUtil.SwapEndian(Magic);
                Type = (ResourceType)DataUtil.SwapEndian((uint)Type);
                Flags = DataUtil.SwapEndian(Flags);
            }
        }

        public void Write(BinaryWriter bw)
        {
            bw.Write( MagicValue );
            bw.Write( (uint)Type );
            bw.Write( Flags );
            bw.Write( (ushort)CompressCodec );
        }
    }
}
```

And

```

namespace RageLib.Common.Resources
{
    [Obfuscation(StripAfterObfuscation = true, ApplyToMembers = true, Exclude = true)]
    public enum ResourceType
    {
        TextureXBOX = 0x7, // xtd
        ModelXBOX = 0x6D, // xdr
        Generic = 0x01, // xhm / xad (Generic files as rsc?)
        Bounds = 0x20, // xbd, wbd
        Particles = 0x24, // xpfl
        Particles2 = 0x1B, // xpfl

        Texture = 0x8, // wtd
        Model = 0x6E, // wdr
        ModelFrag = 0x70, //wft
    }
}
```

and

```
// Note that the data has to be untiled before running the decoder on it

//#define XBOX360

using System;

namespace RageLib.Textures.Decoder
{
    internal static class DXTDecoder
    {
        internal static byte[] DecodeDXT1(byte[] data, int width, int height)
        {
            byte[] pixData = new byte[width * height * 4];
            int xBlocks = width / 4;
            int yBlocks = height / 4;
            for (int y = 0; y < yBlocks; y++)
            {
                for (int x = 0; x < xBlocks; x++)
                {
                    int blockDataStart = ((y * xBlocks) + x) * 8;

#if XBOX360
                    uint color0 = ((uint)data[blockDataStart + 0] << 8) + data[blockDataStart + 1];
                    uint color1 = ((uint)data[blockDataStart + 2] << 8) + data[blockDataStart + 3];
#else
                    uint color0 = BitConverter.ToUInt16(data, blockDataStart);
                    uint color1 = BitConverter.ToUInt16(data, blockDataStart + 2);
#endif

                    uint code = BitConverter.ToUInt32(data, blockDataStart + 4);

                    ushort r0 = 0, g0 = 0, b0 = 0, r1 = 0, g1 = 0, b1 = 0;
                    r0 = (ushort)(8 * (color0 & 31));
                    g0 = (ushort)(4 * ((color0 >> 5) & 63));
                    b0 = (ushort)(8 * ((color0 >> 11) & 31));

                    r1 = (ushort)(8 * (color1 & 31));
                    g1 = (ushort)(4 * ((color1 >> 5) & 63));
                    b1 = (ushort)(8 * ((color1 >> 11) & 31));

                    for (int k = 0; k < 4; k++)
                    {
#if XBOX360
                        int j = k ^ 1;
#else
                        int j = k;
#endif

                        for (int i = 0; i < 4; i++)
                        {
                            int pixDataStart = (width * (y * 4 + j) * 4) + ((x * 4 + i) * 4);
                            uint codeDec = code & 0x3;

                            switch (codeDec)
                            {
                                case 0:
                                    pixData[pixDataStart + 0] = (byte)r0;
                                    pixData[pixDataStart + 1] = (byte)g0;
                                    pixData[pixDataStart + 2] = (byte)b0;
                                    pixData[pixDataStart + 3] = 255;
                                    break;
                                case 1:
                                    pixData[pixDataStart + 0] = (byte)r1;
                                    pixData[pixDataStart + 1] = (byte)g1;
                                    pixData[pixDataStart + 2] = (byte)b1;
                                    pixData[pixDataStart + 3] = 255;
                                    break;
                                case 2:
                                    pixData[pixDataStart + 3] = 255;
                                    if (color0 > color1)
                                    {
                                        pixData[pixDataStart + 0] = (byte)((2 * r0 + r1) / 3);
                                        pixData[pixDataStart + 1] = (byte)((2 * g0 + g1) / 3);
                                        pixData[pixDataStart + 2] = (byte)((2 * b0 + b1) / 3);
                                    }
                                    else
                                    {
                                        pixData[pixDataStart + 0] = (byte)((r0 + r1) / 2);
                                        pixData[pixDataStart + 1] = (byte)((g0 + g1) / 2);
                                        pixData[pixDataStart + 2] = (byte)((b0 + b1) / 2);
                                    }
                                    break;
                                case 3:
                                    if (color0 > color1)
                                    {
                                        pixData[pixDataStart + 0] = (byte)((r0 + 2 * r1) / 3);
                                        pixData[pixDataStart + 1] = (byte)((g0 + 2 * g1) / 3);
                                        pixData[pixDataStart + 2] = (byte)((b0 + 2 * b1) / 3);
                                        pixData[pixDataStart + 3] = 255;
                                    }
                                    else
                                    {
                                        pixData[pixDataStart + 0] = 0;
                                        pixData[pixDataStart + 1] = 0;
                                        pixData[pixDataStart + 2] = 0;
                                        pixData[pixDataStart + 3] = 0;
                                    }
                                    break;
                            }

                            code >>= 2;
                        }
                    }


                }
            }
            return pixData;
        }

        internal static byte[] DecodeDXT3(byte[] data, int width, int height)
        {
            byte[] pixData = new byte[width * height * 4];
            int xBlocks = width / 4;
            int yBlocks = height / 4;
            for (int y = 0; y < yBlocks; y++)
            {
                for (int x = 0; x < xBlocks; x++)
                {
                    int blockDataStart = ((y * xBlocks) + x) * 16;
                    ushort[] alphaData = new ushort[4];
                    
#if XBOX360
                    alphaData[0] = (ushort)((data[blockDataStart + 0] << 8) + data[blockDataStart + 1]);
                    alphaData[1] = (ushort)((data[blockDataStart + 2] << 8) + data[blockDataStart + 3]);
                    alphaData[2] = (ushort)((data[blockDataStart + 4] << 8) + data[blockDataStart + 5]);
                    alphaData[3] = (ushort)((data[blockDataStart + 6] << 8) + data[blockDataStart + 7]);
#else
                    alphaData[0] = BitConverter.ToUInt16(data, blockDataStart + 0);
                    alphaData[1] = BitConverter.ToUInt16(data, blockDataStart + 2);
                    alphaData[2] = BitConverter.ToUInt16(data, blockDataStart + 4);
                    alphaData[3] = BitConverter.ToUInt16(data, blockDataStart + 6);
#endif

                    byte[,] alpha = new byte[4, 4];
                    for (int j = 0; j < 4; j++)
                    {
                        for (int i = 0; i < 4; i++)
                        {
                            alpha[i, j] = (byte)((alphaData[j] & 0xF) * 16);
                            alphaData[j] >>= 4;
                        }
                    }

#if XBOX360
                    ushort color0 = (ushort)((data[blockDataStart + 8] << 8) + data[blockDataStart + 9]);
                    ushort color1 = (ushort)((data[blockDataStart + 10] << 8) + data[blockDataStart + 11]);
#else
                    ushort color0 = BitConverter.ToUInt16(data, blockDataStart + 8);
                    ushort color1 = BitConverter.ToUInt16(data, blockDataStart + 8 + 2);
#endif

                    uint code = BitConverter.ToUInt32(data, blockDataStart + 8 + 4);

                    ushort r0 = 0, g0 = 0, b0 = 0, r1 = 0, g1 = 0, b1 = 0;
                    r0 = (ushort)(8 * (color0 & 31));
                    g0 = (ushort)(4 * ((color0 >> 5) & 63));
                    b0 = (ushort)(8 * ((color0 >> 11) & 31));

                    r1 = (ushort)(8 * (color1 & 31));
                    g1 = (ushort)(4 * ((color1 >> 5) & 63));
                    b1 = (ushort)(8 * ((color1 >> 11) & 31));

                    for (int k = 0; k < 4; k++)
                    {
#if XBOX360
                        int j = k ^ 1;
#else
                        int j = k;
#endif
                        
                        for (int i = 0; i < 4; i++)
                        {
                            int pixDataStart = (width * (y * 4 + j) * 4) + ((x * 4 + i) * 4);
                            uint codeDec = code & 0x3;

                            pixData[pixDataStart + 3] = alpha[i, j];

                            switch (codeDec)
                            {
                                case 0:
                                    pixData[pixDataStart + 0] = (byte)r0;
                                    pixData[pixDataStart + 1] = (byte)g0;
                                    pixData[pixDataStart + 2] = (byte)b0;
                                    break;
                                case 1:
                                    pixData[pixDataStart + 0] = (byte)r1;
                                    pixData[pixDataStart + 1] = (byte)g1;
                                    pixData[pixDataStart + 2] = (byte)b1;
                                    break;
                                case 2:
                                    if (color0 > color1)
                                    {
                                        pixData[pixDataStart + 0] = (byte)((2 * r0 + r1) / 3);
                                        pixData[pixDataStart + 1] = (byte)((2 * g0 + g1) / 3);
                                        pixData[pixDataStart + 2] = (byte)((2 * b0 + b1) / 3);
                                    }
                                    else
                                    {
                                        pixData[pixDataStart + 0] = (byte)((r0 + r1) / 2);
                                        pixData[pixDataStart + 1] = (byte)((g0 + g1) / 2);
                                        pixData[pixDataStart + 2] = (byte)((b0 + b1) / 2);
                                    }
                                    break;
                                case 3:
                                    if (color0 > color1)
                                    {
                                        pixData[pixDataStart + 0] = (byte)((r0 + 2 * r1) / 3);
                                        pixData[pixDataStart + 1] = (byte)((g0 + 2 * g1) / 3);
                                        pixData[pixDataStart + 2] = (byte)((b0 + 2 * b1) / 3);
                                    }
                                    else
                                    {
                                        pixData[pixDataStart + 0] = 0;
                                        pixData[pixDataStart + 1] = 0;
                                        pixData[pixDataStart + 2] = 0;
                                    }
                                    break;
                            }

                            code >>= 2;
                        }
                    }


                }
            }
            return pixData;
        }

        internal static byte[] DecodeDXT5(byte[] data, int width, int height)
        {
            byte[] pixData = new byte[width * height * 4];
            int xBlocks = width / 4;
            int yBlocks = height / 4;
            for (int y = 0; y < yBlocks; y++)
            {
                for (int x = 0; x < xBlocks; x++)
                {
                    int blockDataStart = ((y * xBlocks) + x) * 16;
                    uint[] alphas = new uint[8];
                    ulong alphaMask = 0;

#if XBOX360

                    alphas[0] = data[blockDataStart + 1];
                    alphas[1] = data[blockDataStart + 0];

                    alphaMask |= data[blockDataStart + 6];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 7];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 4];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 5];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 2];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 3];

#else

                    alphas[0] = data[blockDataStart + 0];
                    alphas[1] = data[blockDataStart + 1];

                    alphaMask |= data[blockDataStart + 7];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 6];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 5];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 4];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 3];
                    alphaMask <<= 8;
                    alphaMask |= data[blockDataStart + 2];

#endif

                    // 8-alpha or 6-alpha block
                    if (alphas[0] > alphas[1])
                    {
                        // 8-alpha block: derive the other 6
                        // Bit code 000 = alpha_0, 001 = alpha_1, others are interpolated.
                        alphas[2] = (byte)((6 * alphas[0] + 1 * alphas[1] + 3) / 7);    // bit code 010
                        alphas[3] = (byte)((5 * alphas[0] + 2 * alphas[1] + 3) / 7);    // bit code 011
                        alphas[4] = (byte)((4 * alphas[0] + 3 * alphas[1] + 3) / 7);    // bit code 100
                        alphas[5] = (byte)((3 * alphas[0] + 4 * alphas[1] + 3) / 7);    // bit code 101
                        alphas[6] = (byte)((2 * alphas[0] + 5 * alphas[1] + 3) / 7);    // bit code 110
                        alphas[7] = (byte)((1 * alphas[0] + 6 * alphas[1] + 3) / 7);    // bit code 111
                    }
                    else
                    {
                        // 6-alpha block.
                        // Bit code 000 = alpha_0, 001 = alpha_1, others are interpolated.
                        alphas[2] = (byte)((4 * alphas[0] + 1 * alphas[1] + 2) / 5);    // Bit code 010
                        alphas[3] = (byte)((3 * alphas[0] + 2 * alphas[1] + 2) / 5);    // Bit code 011
                        alphas[4] = (byte)((2 * alphas[0] + 3 * alphas[1] + 2) / 5);    // Bit code 100
                        alphas[5] = (byte)((1 * alphas[0] + 4 * alphas[1] + 2) / 5);    // Bit code 101
                        alphas[6] = 0x00;                                               // Bit code 110
                        alphas[7] = 0xFF;                                               // Bit code 111
                    }

                    byte[,] alpha = new byte[4, 4];

                    for (int i = 0; i < 4; i++)
                    {
                        for (int j = 0; j < 4; j++)
                        {
                            alpha[j, i] = (byte)alphas[alphaMask & 7];
                            alphaMask >>= 3;
                        }
                    }

#if XBOX360
                    ushort color0 = (ushort)((data[blockDataStart + 8] << 8) + data[blockDataStart + 9]);
                    ushort color1 = (ushort)((data[blockDataStart + 10] << 8) + data[blockDataStart + 11]);
#else
                    ushort color0 = BitConverter.ToUInt16(data, blockDataStart + 8);
                    ushort color1 = BitConverter.ToUInt16(data, blockDataStart + 8 + 2);
#endif

                    uint code = BitConverter.ToUInt32(data, blockDataStart + 8 + 4);

                    ushort r0 = 0, g0 = 0, b0 = 0, r1 = 0, g1 = 0, b1 = 0;
                    r0 = (ushort)(8 * (color0 & 31));
                    g0 = (ushort)(4 * ((color0 >> 5) & 63));
                    b0 = (ushort)(8 * ((color0 >> 11) & 31));

                    r1 = (ushort)(8 * (color1 & 31));
                    g1 = (ushort)(4 * ((color1 >> 5) & 63));
                    b1 = (ushort)(8 * ((color1 >> 11) & 31));

                    for (int k = 0; k < 4; k++)
                    {
#if XBOX360
                        int j = k ^ 1;
#else
                        int j = k;
#endif

                        for (int i = 0; i < 4; i++)
                        {
                            int pixDataStart = (width * (y * 4 + j) * 4) + ((x * 4 + i) * 4);
                            uint codeDec = code & 0x3;

                            pixData[pixDataStart + 3] = alpha[i, j];

                            switch (codeDec)
                            {
                                case 0:
                                    pixData[pixDataStart + 0] = (byte)r0;
                                    pixData[pixDataStart + 1] = (byte)g0;
                                    pixData[pixDataStart + 2] = (byte)b0;
                                    break;
                                case 1:
                                    pixData[pixDataStart + 0] = (byte)r1;
                                    pixData[pixDataStart + 1] = (byte)g1;
                                    pixData[pixDataStart + 2] = (byte)b1;
                                    break;
                                case 2:
                                    if (color0 > color1)
                                    {
                                        pixData[pixDataStart + 0] = (byte)((2 * r0 + r1) / 3);
                                        pixData[pixDataStart + 1] = (byte)((2 * g0 + g1) / 3);
                                        pixData[pixDataStart + 2] = (byte)((2 * b0 + b1) / 3);
                                    }
                                    else
                                    {
                                        pixData[pixDataStart + 0] = (byte)((r0 + r1) / 2);
                                        pixData[pixDataStart + 1] = (byte)((g0 + g1) / 2);
                                        pixData[pixDataStart + 2] = (byte)((b0 + b1) / 2);
                                    }
                                    break;
                                case 3:
                                    if (color0 > color1)
                                    {
                                        pixData[pixDataStart + 0] = (byte)((r0 + 2 * r1) / 3);
                                        pixData[pixDataStart + 1] = (byte)((g0 + 2 * g1) / 3);
                                        pixData[pixDataStart + 2] = (byte)((b0 + 2 * b1) / 3);
                                    }
                                    else
                                    {
                                        pixData[pixDataStart + 0] = 0;
                                        pixData[pixDataStart + 1] = 0;
                                        pixData[pixDataStart + 2] = 0;
                                    }
                                    break;
                            }

                            code >>= 2;
                        }
                    }


                }
            }
            return pixData;
        }

    }
}

```

Sorry for very long post.
Another thing, all the textures of PC have a heading RSC and some of xbox, the most common but others have heading .CSI.
Is it important?
Thank you for reading myself.
## Post #27
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-05-10T23:11:20+00:00
- Post Title: Re: GTA IV LZX compression on resource data

So does anyone here have a way to decompress the files with the RSC header? The program "quickbms" supports XBOXMEM compression, but I can not figure out how to implement a quickbms script that works. Quickbms either crashes or produces an output file of size 0.
