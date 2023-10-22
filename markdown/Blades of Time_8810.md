## Post #1
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-22T08:14:44+00:00
- Post Title: Blades of Time

Making a request for this game.

Well, the demo was released today so if someone is interested, I can give an example via PM.

See ya.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-22T09:13:54+00:00
- Post Title: Blades of Time

the PS3 version of the game used some compression, similar to the ones used in previous rebellion games. i wonder if it's the same on the PC version. i'll look at the samples... check sig for contact info. luigi had some tool for the other rebellion games, but it didn't work on the PS3 version of blades of time. i also remember the maps on the PS3 weren't compressed, but the textures and character models were.

or wait... i think i'm getting it confused with another game lol... i've been looking at so many games lately LOL! you guys ever notice that once you play or work on a lot of games they all start looking the same?

EDIT: Oh yeah, I was getting it confused with NeverDead. I have the PS3 version of Blades of Time, I just haven't had time to look at it.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-22T12:39:25+00:00
- Post Title: Blades of Time

the format is not to hard the problem is some sections are zlib compressed but i can't find any sizes anywhere for the zlib chunks.
## Post #4
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-04-22T14:43:26+00:00
- Post Title: Blades of Time

It's possible to capture the models in T-pose with GameAssassin on a Windows XP OS. 

However the UV is totally screwed but you can copy it from a 3d ripper rip. 

Well if anyone wants to look at the format anyway and needs samples..i can email some from the PC version if that helps in any way xD
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-23T16:32:10+00:00
- Post Title: Blades of Time

lol i can't even download the demo off of steam; what a piece of shit steam is.
## Post #6
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-04-23T19:10:36+00:00
- Post Title: Blades of Time

^^ yeah Steam seriously sucks pretty often -.- It's always a pain to get only downloadable games like this one or DLCs from other games. Takes so long, or doesn't start till you tried thousands of times. 
It was better when Half Life 2 was released xD
## Post #7
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-04-24T08:40:06+00:00
- Post Title: Blades of Time

Any progress?  How about monster and weapon? If anyone need an example i will post it!
## Post #8
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2012-04-27T17:07:58+00:00
- Post Title: Blades of Time

I'm trying to understand the formats, but their formats - is a quiet horror 

What I found out about the GRP format.

```
{
        DWORD Signature; // signature, always GRP1
        DWORD OffsetToIndexTable; // offset to some table indexes. adjusted to 16
        DWORD OffsetToIndexTableEnd; // offset of the end of the above table index is adjusted for 16
        DWORD DataSize; // size of data array ( FileSize - sizeof(GRPHeader) )
};
```


Further there are three types of tables

```
{
        DWORD Offset; // offset from the beginning of the file
        DWORD Count; // number of elements
};
```

 The first is the name table, the second is offset to handle table data itself. The descriptors are of type:

```
{
        DWORD ID; // it seems that the content type ID
        DWORD Offset; // offset
        DWORD Index; // index
};
```

 The third is offset to the descriptors, apparently, the same data. Are of the type:

```
{
        DWORD ID; // probably the type of content
        WORD Index1; // indexes
        WORD Index2; //
        DWORD Unknown2; // something vague, often == 0
        DWORD Unknown3; //
};
```


 After - do table names and descriptors. Well, then - indexes, which indicated the shift in the header and the actual serialized data itself.

content type IDs may be:
0xD543E771 - PhysX descriptor?
0xB4B7D9C4 - Skinned mesh?
0xA6F87A9B - chr1 signature, may be some descriptor
0x855A1BE6 - contains bones names
0x88B7A117 - effect or particle system?
0x77F8232F - Mesh?
0x56F81B6D - skin? contains bones names
0x40C586F9 - Animation or animation set
0x8F2A701A - Script? PE x86 module present!

P.S.: Sorry my bad English. I am Russian.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-27T18:04:07+00:00
- Post Title: Blades of Time

the grp format is not he problem its that parts of those chunks are compressed and no sizes are given
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-27T18:25:35+00:00
- Post Title: Blades of Time

Zlib can be decompressed as a stream. If I write a file extractor, someone want to do the models? I'm still working on several (too many) things. Lemme see if steam finally fixed their demo issue... (EDIT: Yes they did, checking it out now).
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-27T19:21:14+00:00
- Post Title: Blades of Time

As long as I don't have to DL the game myself.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-27T19:41:29+00:00
- Post Title: Blades of Time

lol, don't you like to play what you rip finale?
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-27T20:21:05+00:00
- Post Title: Blades of Time

lol, just cause it has TnA?
I don't think I've played any of them.
## Post #14
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-27T21:52:48+00:00
- Post Title: Blades of Time

> Reply from howfie
>
> Zlib can be decompressed as a stream. If I write a file extractor, someone want to do the models? I'm still working on several (too many) things. Lemme see if steam finally fixed their demo issue... (EDIT: Yes they did, checking it out now).

Yep, steam demo works right now.
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-27T21:54:31+00:00
- Post Title: Blades of Time

you will have to parse the models also then its not just an entire chunk that is compressed it is parts of the model files. if there was sizes anywhere i could use noesis but i can not find any myself.
## Post #16
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2012-04-30T12:04:47+00:00
- Post Title: Re: Blades of Time

I unpacked the compressed data block from the container B4B7D9C4. But I can't understand kind of this data types. First, as I understand it is a header and a few tables. And then ... an array of structures:

> struct Vertex
>
> {
>
>     DWORD PosA; // == 31103131h
>
>     WORD PosB; // == B5F5h
>
>     WORD PosC; // == 3B8Fh
>
>     WORD PosD; // == B33Bh
>
>     WORD PosE; // == 3C00h
>
>     DWORD PosF; // == 80C731C6h
>
>     WORD PosG; // == 3A98h
>
>     WORD PosH; // == 34CCh
>
>     DWORD PosI; // == FF9A4213h
>
>     DWORD PosJ; // == FF6410B7h
>
> };

wtf? This is not the position, is not the normal and is not texture coordinates. This is something incomprehensible. What are they smoking? : )
## Post #17
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-30T12:40:33+00:00
- Post Title: Re: Blades of Time

If they are smoking something, you need to figure it out so you can smoke it too. You can smoke lots of shit, cigs, weed, grass, heroin, floats, half floats, signed ints, normalized signed ints, etc. Looks like maybe half floats since 3c00 is 1. Vertx data often contains bone and weight info and sometimes even more.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-30T17:49:20+00:00
- Post Title: Re: Blades of Time

Wow you can look at two bytes and go "half-float 1" I can't do fp conversion =(

I e-mailed 010 editor guys about adding half-float to their inspector and they said they'll add it in their "next release" lol whenever that might be. I then told them their competitors already have that functionality in their inspector and they didn't give a shit lol

Were the odd chunks decompressed manually?
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-30T18:07:02+00:00
- Post Title: Re: Blades of Time

nah, actually i forget.... i memorize stuff like 3F80 is 1.0 in float and so on but i forget what 1.0 is in half float... 3F00, 3C00 something or other lol. i wrote the above knowing i might be wrong but close. it's just memorizing after looking at this stuff for weeks on end. you know what i mean lol.
## Post #20
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-30T18:12:02+00:00
- Post Title: Re: Blades of Time

speaking of which, looking at destrator's struct code and use of WORD and DWORD, it looks like he is a pure C/C++ windows programmer like myself. in that case, use the following to load those half floats:

```
{
 // sign/exponent/mantissa
 const uint16 s = (value & 0x8000);
 const uint16 e = (value & 0x7C00) >> 10;
 const uint16 m = (value & 0x03FF);

 // ok
 const real32 sgn = (s ? -1.0f : 1.0f);
 if(e == 0) return sgn*(m == 0 ? 0.0f : std::pow(2.0f, -14.0f)*((real32)m/1024.0f));
 if(e < 32) return sgn*std::pow(2.0f, (real32)e - 15.0f)*(1.0f + ((real32)m/1024.0f));

 // not ok!
 if(m == 0) return std::numeric_limits<real32>::quiet_NaN();
 return std::numeric_limits<real32>::quiet_NaN();
}

```
## Post #21
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2012-05-03T16:52:49+00:00
- Post Title: Re: Blades of Time

howfie
Thanks.

I use this algorithm for half-floats:

```
{
    DWORD u;
    float f;
    struct
    {
        DWORD Mantissa : 23;
        DWORD Exponent : 8;
        DWORD Sign : 1;
    };
} FP32;

typedef union FP16
{
    WORD u;
    struct
    {
        WORD Mantissa : 10;
        WORD Exponent : 5;
        WORD Sign : 1;
    };
} FP16;

static FP32 half_to_float(FP16 h)
{
    FP32 o = { 0 };

    // From ISPC ref code
    if (h.Exponent == 0 && h.Mantissa == 0) // (Signed) zero
        o.Sign = h.Sign;
    else
    {
        if (h.Exponent == 0) // Denormal (will convert to normalized)
        {
            // Adjust mantissa so it's normalized (and keep track of exp adjust)
            int e = -1;
            DWORD m = h.Mantissa;
            do
            {
                e++;
                m <<= 1;
            } while ((m & 0x400) == 0);

            o.Mantissa = (m & 0x3ff) << 13;
            o.Exponent = 127 - 15 - e;
            o.Sign = h.Sign;
        }
        else if (h.Exponent == 0x1f) // Inf/NaN
        {
            // NOTE: It's safe to treat both with the same code path by just truncating
            // lower Mantissa bits in NaNs (this is valid).
            o.Mantissa = h.Mantissa << 13;
            o.Exponent = 255;
            o.Sign = h.Sign;
        }
        else // Normalized number
        {
            o.Mantissa = h.Mantissa << 13;
            o.Exponent = 127 - 15 + h.Exponent; 
            o.Sign = h.Sign;
        }
    }

    return o;
}

```


And I have question about vertex format of skinned meshes. Vertex has the following format:

```
{
	char x;
	char y;
	char z;
	char w;
};

struct Vertex
{
    VECTOR4S8 Unknown0;
    FP16 PosX; // Position
    FP16 PosY; //
    FP16 PosZ; //
    FP16 Unknown1;
    VECTOR4S8 Unknown2;
    FP16 TexU; // texture coords 
    FP16 TexV; //
    VECTOR4S8 Unknown3;
    VECTOR4S8 Unknown4;
};

```


Has anyone figured out what means members of the structure: Unknown0-Unknown4? It may be packed normals, binormals, tangents, vertex weights or indices or anything other.
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-03T17:23:29+00:00
- Post Title: Re: Blades of Time

To figure out weights, you should print out a hex dump for each vertex like so (this is from my rise of nightmares output, it's the first vertex for each model that uses the 0x4 0x1800 0xffc3 vertex format):

```
00000000:3f3c4fbb:3e881da1:ff000000:00000000:7fb6:f1fe:9f11:b5fe:29c3:355e - 0x4 0x1800 0xffc3
3ecba6a5:417e26fb:3f2859b9:d7120f06:18020f1b:b889:f0fe:f07a:46fe:38f2:373a - 0x4 0x1800 0xffc3
00000000:41777d42:3f47768b:eb0a0a00:08070900:7fb3:0bfe:7ff3:b3fe:3806:3bf4 - 0x4 0x1800 0xffc3
bd1b98e0:4121cae9:3f8a6744:99660000:00010000:c6af:ddfe:1a7e:cc00:393d:385d - 0x4 0x1800 0xffc3
bd1b98e0:4121cae9:3f8a6744:99660000:00010000:c6af:ddfe:1a7e:cc00:393d:385d - 0x4 0x1800 0xffc3
40285398:4155265d:3d0bdd03:ff000000:00000000:f5ae:8684:8581:00fe:214e:3603 - 0x4 0x1800 0xffc3
41038bf9:41658845:bf498bb6:ff000000:06000000:8fe9:3bfe:5344:1800:3a28:2b91 - 0x4 0x1800 0xffc3
bd1b98e0:4121cae9:3f8a6744:99660000:00010000:c6af:ddfe:1a7e:cc00:393d:385d - 0x4 0x1800 0xffc3
41038bf9:41658845:bf498bb6:ff000000:06000000:8fe9:3bfe:5344:1800:3a28:2b91 - 0x4 0x1800 0xffc3
00000000:41777d42:3f47768b:eb0a0a00:08070900:7fb3:0bfe:7ff3:b3fe:3806:3bf4 - 0x4 0x1800 0xffc3
3e518aa7:4181a31b:3f2c3902:b6341500:00040200:792a:ddfe:f79b:a000:3b5d:28cf - 0x4 0x1800 0xffc3
bf383c7a:4181d00d:bdbc36b9:ff000000:06000000:3ba9:e1fe:8d0f:b900:3320:3579 - 0x4 0x1800 0xffc3

```


The dead giveaway for weights is you'll see something like (look for the FF and some zeros and a bunch of bytes that sum to 0xFF):

```
b6341500:00040200

```


0xb6 + 0x34 + 0x15 = 0xFF
ff -> 06 = 1.0 weight and 06 = bone or weight map index

Sometimes you'll see weights as half-floats. If they are, usually they are between 0 and 1 so look for anything 0x2??? and 0x3???. Bone indices are almost always bytes. If you post a hex dump of some vertices, we can take a look at it.
## Post #23
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2012-05-19T10:18:10+00:00
- Post Title: Re: Blades of Time

Blenderv249 grp model importer:(for Xblades too)
-geometry
-uv
[http://www.mediafire.com/?mqo8lq6bwhoo18w](http://www.mediafire.com/?mqo8lq6bwhoo18w)
## Post #24
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-05-19T10:55:36+00:00
- Post Title: Re: Blades of Time

It's cool, thank you very much Szkaradek123! You rock!
## Post #25
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-20T00:18:46+00:00
- Post Title: Re: Blades of Time

> Reply from Szkaradek123
>
> Blenderv249 grp model importer:(for Xblades too)
-geometry
-uv
http://www.mediafire.com/?mqo8lq6bwhoo18w

Thanks, just one thing: is there a way to extract textures??
## Post #26
- Username: mincartoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 30, 2012 11:37 pm
- Post datetime: 2012-05-30T15:41:39+00:00
- Post Title: Re: Blades of Time

I wanna make some Skyrim mods with the Ayumi model.

Have no clue how to use offzip or hex editors...

Can anyone help me? I am a 3DSMAX user btw...
## Post #27
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-11-21T00:48:34+00:00
- Post Title: Re: Blades of Time

To get the textures, you can use offzip like this:
- copy offzip to the /res/texpack directory;
- create a new directory called "gameres";
- run offzip like this:

offzip.exe -a bot.gameres.dxp.bin gameres 0x10

- find the files called "0005ccd8.dat", "004fc078.dat", and "000cfd00.dat", and open them in a hex editor;

- put a DXT1 header (1024x1024, no MIPMAPS) on top of 0005ccd8.dat, and save it as "body_diffuse.dds";
- put a DXT5 header (1024x1024, no MIPMAPS) on top of 004fc078.dat, and save it as "hair_diffuse.dds";
- put a DXT5 header (2048x2048, no MIPMAPS) on top of 000cfd00.dat, and save it as "body_bump.dds".
## Post #28
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-11-28T02:17:27+00:00
- Post Title: Re: Blades of Time

With the Blender script the exported models still need a lot of work to display them correctly, especially the eyes.
Once given the correct material, the eyes appear very beautifully modeled.

The attachment shows examples of Ayumi, her dragon form, and Michelle.

The Blender script also doesn't export the model's skeleton, but for other games a different skeleton has to be applied anyway.
For example in Sacred 2 with a Seraphim skeleton:

[threesome.jpg](https://xentaxbackup.github.io/file/8157_threesome.jpg)
## Post #29
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-04T08:44:32+00:00
- Post Title: Re: Blades of Time

> Reply from Szkaradek123
>
> Blenderv249 grp model importer:(for Xblades too)
Hi!
Thank you for script 
Btw, can you update it to work with WarThunder grp's also?
It's tries to load them, do some listing of internal meshes, but loads nothing.
I posted some detailed info and samples in [WT topic](http://forum.xentax.com/viewtopic.php?p=113015#p113015).
